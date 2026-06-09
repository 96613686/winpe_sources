# GetPages(IKsObject *,void *,ulong,KSPIN_COMMUNICATION,HKEY__ *,tagCAUUID *)

- ea: `0x180038344`
- end: `0x1800385f5`
- name: `?GetPages@@YAJPEAUIKsObject@@PEAXKW4KSPIN_COMMUNICATION@@PEAUHKEY__@@PEAUtagCAUUID@@@Z`
- size: `689`
- prototype: `__int64 __fastcall(struct IKsObject *, char *, unsigned int, enum KSPIN_COMMUNICATION, HKEY, struct tagCAUUID *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180027460`
- `0x18002b520`

## callees

- `0x180004f70`
- `0x180005850`
- `0x18000909c`
- `0x18000bde0`
- `0x18001f620`
- `0x18001ffb0`
- `0x18003238c`
- `0x180038344`
- `0x180045010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800384dd`
- `ADVAPI32!RegQueryValueExW` at `0x1800384dd`
- `ADVAPI32!RegCloseKey` at `0x1800384f0`
- `ADVAPI32!RegCloseKey` at `0x1800384f0`
- `ADVAPI32!RegOpenKeyExW` at `0x18003849b`
- `ADVAPI32!RegOpenKeyExW` at `0x18003849b`
- `ole32!CoTaskMemAlloc` at `0x1800383ed`
- `ole32!CoTaskMemAlloc` at `0x1800383ed`
- `ole32!StringFromGUID2` at `0x180038458`
- `ole32!StringFromGUID2` at `0x180038458`

## string_xrefs

- `0x1800384be`: `clsid`

## pseudocode

```c
__int64 __fastcall GetPages(
        struct IKsObject *a1,
        char *a2,
        unsigned int a3,
        enum KSPIN_COMMUNICATION a4,
        HKEY a5,
        struct tagCAUUID *a6)
{
  DWORD v8; // esi
  _GUID *v9; // rax
  _GUID *v10; // r14
  LSTATUS v12; // ebx
  _GUID *pElems; // rdx
  unsigned int cElems; // ecx
  __int64 v15; // rax
  _GUID v16; // xmm0
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  GUID InBuffer; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v21; // [rsp+60h] [rbp-A0h]
  BYTE Data[16]; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID v23; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v24[44]; // [rsp+90h] [rbp-70h] BYREF
  GUID rguid; // [rsp+BCh] [rbp-44h] BYREF
  OLECHAR sz[40]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR SubKey[256]; // [rsp+140h] [rbp+40h] BYREF

  NumberOfBytesTransferred = 0;
  cbData = 0;
  a6->cElems = 0;
  a6->pElems = 0;
  v23 = 0;
  InBuffer = 0;
  v21 = 0;
  if ( a4 == KSPIN_COMMUNICATION_BRIDGE && !a1->KsGetObjectHandle(a1) )
  {
    KsGetMediaTypeCount(a2, a3, &cbData);
    v8 = cbData;
    if ( cbData )
    {
      v9 = (_GUID *)CoTaskMemAlloc(16LL * cbData);
      a6->pElems = v9;
      v10 = v9;
      if ( !v9 )
        return 2147942414LL;
      do
      {
        --v8;
        memset_0(v24, 0, 0x58u);
        if ( (int)KsGetMediaType(v8, (__int64)v24, a2, a3) >= 0 )
        {
          hKey = 0;
          cbData = 0;
          *(_OWORD *)Data = 0;
          StringFromGUID2(&rguid, sz, 39);
          StringCchPrintfW(SubKey, 0x100u, L"SYSTEM\\CurrentControlSet\\Control\\MediaSpecifiers\\%s", sz);
          if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
          {
            cbData = 16;
            v12 = RegQueryValueExW(hKey, L"clsid", 0, 0, Data, &cbData);
            RegCloseKey(hKey);
            if ( !v12 )
            {
              pElems = a6->pElems;
              cElems = a6->cElems;
              if ( a6->cElems )
              {
                while ( 1 )
                {
                  v15 = *(_QWORD *)Data - *(_QWORD *)&pElems->Data1;
                  if ( *(_QWORD *)Data == *(_QWORD *)&pElems->Data1 )
                    v15 = *(_QWORD *)&Data[8] - *(_QWORD *)pElems->Data4;
                  if ( !v15 )
                    break;
                  ++pElems;
                  if ( !--cElems )
                    goto LABEL_14;
                }
              }
              else
              {
LABEL_14:
                v16 = *(_GUID *)Data;
                ++a6->cElems;
                *v10++ = v16;
              }
            }
          }
        }
      }
      while ( v8 );
    }
  }
  *(_QWORD *)&v21 = 0x10000000BLL;
  *((_QWORD *)&v21 + 1) = a3;
  InBuffer = GUID_8c134960_51ad_11cf_878a_94f801c10000;
  if ( KsSynchronousDeviceControl(a2, 0x2F0003u, &InBuffer, 0x20u, &v23, 0x10u, &NumberOfBytesTransferred) >= 0 )
    AppendSpecificPropertyPages(a6, 1, &v23, L"SYSTEM\\CurrentControlSet\\Control\\MediaCategories", a5);
  return 0;
}

```

## disassembly

```asm
0x180038344  mov     [rsp-8+arg_18], rbx
0x180038349  push    rbp
0x18003834a  push    rsi
0x18003834b  push    rdi
0x18003834c  push    r12
0x18003834e  push    r13
0x180038350  push    r14
0x180038352  push    r15
0x180038354  lea     rbp, [rsp-250h]
0x18003835c  sub     rsp, 350h
0x180038363  mov     rax, cs:__security_cookie
0x18003836a  xor     rax, rsp
0x18003836d  mov     [rbp+280h+var_40], rax
0x180038374  mov     rdi, [rbp+280h+arg_28]
0x18003837b  xor     ebx, ebx
0x18003837d  mov     r13, [rbp+280h+arg_20]
0x180038384  xorps   xmm1, xmm1
0x180038387  mov     [rsp+380h+NumberOfBytesTransferred], ebx
0x18003838b  xorps   xmm0, xmm0
0x18003838e  mov     [rsp+380h+cbData], ebx
0x180038392  mov     r12d, r8d
0x180038395  mov     [rdi], ebx
0x180038397  mov     r15, rdx
0x18003839a  mov     [rdi+8], rbx
0x18003839e  movups  xmmword ptr [rbp+280h+var_300.Data1], xmm0
0x1800383a2  movups  [rsp+380h+InBuffer], xmm1
0x1800383a7  movups  [rsp+380h+var_320], xmm1
0x1800383ac  cmp     r9d, 4
0x1800383b0  jnz     loc_180038552
0x1800383b6  mov     rax, [rcx]
0x1800383b9  mov     rax, [rax+18h]
0x1800383bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383c2  test    rax, rax
0x1800383c5  jnz     loc_180038552
0x1800383cb  lea     r8, [rsp+380h+cbData]
0x1800383d0  mov     edx, r12d
0x1800383d3  mov     rcx, r15; hFile
0x1800383d6  call    KsGetMediaTypeCount
0x1800383db  mov     esi, [rsp+380h+cbData]
0x1800383df  test    esi, esi
0x1800383e1  jz      loc_180038552
0x1800383e7  mov     ecx, esi
0x1800383e9  shl     rcx, 4; cb
0x1800383ed  call    cs:__imp_CoTaskMemAlloc
0x1800383f4  nop     dword ptr [rax+rax+00h]
0x1800383f9  mov     [rdi+8], rax
0x1800383fd  mov     r14, rax
0x180038400  test    rax, rax
0x180038403  jnz     short loc_18003840F
0x180038405  mov     eax, 8007000Eh
0x18003840a  jmp     loc_1800385CA
0x18003840f  xor     edx, edx; Val
0x180038411  lea     rcx, [rbp+280h+var_2F0]; void *
0x180038415  dec     esi
0x180038417  lea     r8d, [rdx+58h]; Size
0x18003841b  call    memset_0
0x180038420  mov     r9d, r12d
0x180038423  lea     rdx, [rbp+280h+var_2F0]
0x180038427  mov     r8, r15
0x18003842a  mov     ecx, esi
0x18003842c  call    KsGetMediaType
0x180038431  test    eax, eax
0x180038433  js      loc_18003854A
0x180038439  xorps   xmm0, xmm0
0x18003843c  mov     [rsp+380h+hKey], rbx
0x180038441  mov     r8d, 27h ; '''; cchMax
0x180038447  mov     [rsp+380h+cbData], ebx
0x18003844b  lea     rdx, [rbp+280h+sz]; lpsz
0x18003844f  lea     rcx, [rbp+280h+rguid]; rguid
0x180038453  movups  xmmword ptr [rsp+380h+Data], xmm0
0x180038458  call    cs:__imp_StringFromGUID2
0x18003845f  nop     dword ptr [rax+rax+00h]
0x180038464  lea     r9, [rbp+280h+sz]
0x180038468  mov     edx, 100h; unsigned __int64
0x18003846d  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Med"...
0x180038474  lea     rcx, [rbp+280h+SubKey]; unsigned __int16 *
0x180038478  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003847d  lea     rax, [rsp+380h+hKey]
0x180038482  mov     r9d, 20019h; samDesired
0x180038488  xor     r8d, r8d; ulOptions
0x18003848b  mov     [rsp+380h+phkResult], rax; phkResult
0x180038490  lea     rdx, [rbp+280h+SubKey]; lpSubKey
0x180038494  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003849b  call    cs:__imp_RegOpenKeyExW
0x1800384a2  nop     dword ptr [rax+rax+00h]
0x1800384a7  test    eax, eax
0x1800384a9  jnz     loc_18003854A
0x1800384af  mov     rcx, [rsp+380h+hKey]; hKey
0x1800384b4  lea     rax, [rsp+380h+cbData]
0x1800384b9  mov     [rsp+380h+lpcbData], rax; lpcbData
0x1800384be  lea     rdx, aClsid; "clsid"
0x1800384c5  lea     rax, [rsp+380h+Data]
0x1800384ca  mov     [rsp+380h+cbData], 10h
0x1800384d2  xor     r9d, r9d; lpType
0x1800384d5  mov     [rsp+380h+phkResult], rax; lpData
0x1800384da  xor     r8d, r8d; lpReserved
0x1800384dd  call    cs:__imp_RegQueryValueExW
0x1800384e4  nop     dword ptr [rax+rax+00h]
0x1800384e9  mov     rcx, [rsp+380h+hKey]; hKey
0x1800384ee  mov     ebx, eax
0x1800384f0  call    cs:__imp_RegCloseKey
0x1800384f7  nop     dword ptr [rax+rax+00h]
0x1800384fc  test    ebx, ebx
0x1800384fe  jnz     short loc_180038548
0x180038500  mov     r8d, [rdi]
0x180038503  xor     ebx, ebx
0x180038505  mov     rdx, [rdi+8]
0x180038509  mov     ecx, r8d
0x18003850c  test    r8d, r8d
0x18003850f  jz      short loc_180038532
0x180038511  mov     rax, qword ptr [rsp+380h+Data]
0x180038516  sub     rax, [rdx]
0x180038519  jnz     short loc_180038524
0x18003851b  mov     rax, qword ptr [rsp+380h+Data+8]
0x180038520  sub     rax, [rdx+8]
0x180038524  test    rax, rax
0x180038527  jz      short loc_18003854A
0x180038529  add     rdx, 10h
0x18003852d  add     ecx, 0FFFFFFFFh
0x180038530  jnz     short loc_180038511
0x180038532  movups  xmm0, xmmword ptr [rsp+380h+Data]
0x180038537  lea     eax, [r8+1]
0x18003853b  mov     [rdi], eax
0x18003853d  movdqu  xmmword ptr [r14], xmm0
0x180038542  add     r14, 10h
0x180038546  jmp     short loc_18003854A
0x180038548  xor     ebx, ebx
0x18003854a  test    esi, esi
0x18003854c  jnz     loc_18003840F
0x180038552  movups  xmm0, xmmword ptr cs:_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1
0x180038559  mov     esi, 1
0x18003855e  mov     dword ptr [rsp+380h+var_320], 0Bh
0x180038566  lea     rax, [rsp+380h+NumberOfBytesTransferred]
0x18003856b  mov     dword ptr [rsp+380h+var_320+4], esi
0x18003856f  mov     [rsp+380h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180038574  lea     r8, [rsp+380h+InBuffer]; lpInBuffer
0x180038579  lea     rax, [rbp+280h+var_300]
0x18003857d  mov     dword ptr [rsp+380h+lpcbData], 10h; DWORD
0x180038585  lea     r9d, [rsi+1Fh]; nInBufferSize
0x180038589  mov     dword ptr [rsp+380h+var_320+8], r12d
0x18003858e  mov     edx, 2F0003h; dwIoControlCode
0x180038593  mov     dword ptr [rsp+380h+var_320+0Ch], ebx
0x180038597  mov     rcx, r15; hFile
0x18003859a  mov     [rsp+380h+phkResult], rax; LPVOID
0x18003859f  movdqu  [rsp+380h+InBuffer], xmm0
0x1800385a5  call    KsSynchronousDeviceControl
0x1800385aa  test    eax, eax
0x1800385ac  js      short loc_1800385C8
0x1800385ae  lea     r9, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Med"...
0x1800385b5  mov     [rsp+380h+phkResult], r13; hKey
0x1800385ba  lea     r8, [rbp+280h+var_300]; struct _GUID *
0x1800385be  mov     edx, esi; unsigned int
0x1800385c0  mov     rcx, rdi; struct tagCAUUID *
0x1800385c3  call    ?AppendSpecificPropertyPages@@YAXPEAUtagCAUUID@@KPEAU_GUID@@PEAGPEAUHKEY__@@@Z; AppendSpecificPropertyPages(tagCAUUID *,ulong,_GUID *,ushort *,HKEY__ *)
0x1800385c8  xor     eax, eax
0x1800385ca  mov     rcx, [rbp+280h+var_40]
0x1800385d1  xor     rcx, rsp; StackCookie
0x1800385d4  call    __security_check_cookie
0x1800385d9  mov     rbx, [rsp+380h+arg_18]
0x1800385e1  add     rsp, 350h
0x1800385e8  pop     r15
0x1800385ea  pop     r14
0x1800385ec  pop     r13
0x1800385ee  pop     r12
0x1800385f0  pop     rdi
0x1800385f1  pop     rsi
0x1800385f2  pop     rbp
0x1800385f3  retn
```
