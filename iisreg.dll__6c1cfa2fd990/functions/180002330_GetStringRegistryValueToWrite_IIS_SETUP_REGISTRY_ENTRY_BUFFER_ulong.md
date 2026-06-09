# GetStringRegistryValueToWrite(IIS_SETUP_REGISTRY_ENTRY *,BUFFER *,ulong *)

- ea: `0x180002330`
- end: `0x180002605`
- name: `?GetStringRegistryValueToWrite@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@PEAVBUFFER@@PEAK@Z`
- size: `725`
- prototype: `int(struct IIS_SETUP_REGISTRY_ENTRY *, struct BUFFER *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x18000224c`

## callees

- `0x180002330`
- `0x180002ff8`
- `0x180003024`
- `0x1800030b8`
- `0x180003164`
- `0x180003328`
- `0x180003605`
- `0x180003611`
- `0x180003650`

## import_xrefs

- `msvcrt!_wtoi` at `0x180002463`
- `msvcrt!_wtoi` at `0x180002463`
- `msvcrt!wcsnlen` at `0x180002547`
- `msvcrt!wcsnlen` at `0x180002547`
- `KERNEL32!GetLastError` at `0x180002441`
- `KERNEL32!GetLastError` at `0x1800024f4`
- `KERNEL32!GetLastError` at `0x180002570`
- `KERNEL32!GetLastError` at `0x18000259e`
- `KERNEL32!GetLastError` at `0x180002441`
- `KERNEL32!GetLastError` at `0x1800024f4`
- `KERNEL32!GetLastError` at `0x180002570`
- `KERNEL32!GetLastError` at `0x18000259e`
- `KERNEL32!GetModuleHandleW` at `0x180002433`
- `KERNEL32!GetModuleHandleW` at `0x180002433`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800024cb`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180002521`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800024cb`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180002521`

## pseudocode

```c
__int64 __fastcall GetStringRegistryValueToWrite(struct IIS_SETUP_REGISTRY_ENTRY *a1, void **a2, unsigned int *a3)
{
  int v6; // eax
  const unsigned __int8 *v7; // rdx
  __int64 v8; // r8
  signed int StringW; // ebx
  HMODULE ModuleHandleW; // rbx
  signed int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // r8
  DWORD v14; // eax
  DWORD v15; // esi
  unsigned int v16; // edx
  signed int v17; // eax
  DWORD v18; // eax
  int v19; // eax
  unsigned int v20; // edi
  signed int LastError; // eax
  LPWSTR v22; // rdx
  signed int v23; // eax
  _BYTE v25[32]; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR lpDst; // [rsp+50h] [rbp-B0h]
  unsigned int v27; // [rsp+58h] [rbp-A8h]
  __int16 v28; // [rsp+5Ch] [rbp-A4h]
  int v29; // [rsp+60h] [rbp-A0h]
  _BYTE v30[32]; // [rsp+68h] [rbp-98h] BYREF
  LPCCH lpMultiByteStr; // [rsp+88h] [rbp-78h]
  int v32; // [rsp+90h] [rbp-70h]
  __int16 v33; // [rsp+94h] [rbp-6Ch]
  int v34; // [rsp+98h] [rbp-68h]
  char v35; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v36; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v37[526]; // [rsp+1B2h] [rbp+B2h] BYREF

  memset_0(v37, 0, 0x206u);
  v28 = 256;
  v29 = 0;
  lpDst = (LPWSTR)&v36;
  lpMultiByteStr = &v35;
  v27 = 520;
  v36 = 0;
  v32 = 260;
  v33 = 256;
  v34 = 0;
  v35 = 0;
  if ( !a1 || !a2 || !a3 )
  {
    StringW = -2147024809;
    goto LABEL_44;
  }
  v6 = *((_DWORD *)a1 + 12);
  if ( !v6 )
  {
    v7 = (const unsigned __int8 *)*((_QWORD *)a1 + 5);
    if ( v7 )
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)&v7[2 * v8] );
      StringW = STRU::AuxAppend((STRU *)v25, v7, (unsigned int)(2 * v8), 0, 1);
      if ( StringW >= 0 )
        goto LABEL_35;
    }
    else
    {
      StringW = -2147024809;
    }
LABEL_46:
    if ( (_BYTE)v28 )
      BUFFER::FreeMemoryInternal((BUFFER *)v25);
    return (unsigned int)StringW;
  }
  if ( v6 == 1 )
  {
    ModuleHandleW = GetModuleHandleW(0);
    if ( !ModuleHandleW )
      goto LABEL_13;
    v12 = _wtoi(*((const wchar_t **)a1 + 5));
    StringW = STRA::LoadStringW((STRA *)v30, v12, ModuleHandleW);
    if ( StringW >= 0 )
    {
      v13 = -1;
      do
        ++v13;
      while ( lpMultiByteStr[v13] );
      StringW = STRU::AuxAppendA((STRU *)v25, lpMultiByteStr, v13, 0, 1, 0);
      if ( StringW >= 0 )
      {
LABEL_35:
        v20 = 2 * v29 + 2;
        if ( v20 <= *((_DWORD *)a2 + 10) || BUFFER::ReallocStorage((BUFFER *)a2, v20) )
        {
          v22 = lpDst;
          *a3 = v20;
          memcpy_0(a2[4], v22, v20);
        }
        else
        {
          LastError = GetLastError();
          StringW = LastError;
          if ( LastError > 0 )
            StringW = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
LABEL_44:
    if ( (_BYTE)v33 )
      BUFFER::FreeMemoryInternal((BUFFER *)v30);
    goto LABEL_46;
  }
  if ( v6 != 2 )
    return (unsigned int)-2147024883;
  v14 = ExpandEnvironmentStringsW(*((LPCWSTR *)a1 + 5), 0, 0);
  v15 = v14;
  if ( v14 )
  {
    v16 = 2 * v14 + 2;
    if ( v16 <= 0x208 || BUFFER::ReallocStorage((BUFFER *)v25, v16) )
    {
      StringW = 0;
    }
    else
    {
      v17 = GetLastError();
      StringW = v17;
      if ( v17 > 0 )
        StringW = (unsigned __int16)v17 | 0x80070000;
      if ( StringW < 0 )
        goto LABEL_46;
    }
    v18 = ExpandEnvironmentStringsW(*((LPCWSTR *)a1 + 5), lpDst, v15);
    if ( !v18 || v18 > v15 )
    {
      v23 = GetLastError();
      StringW = v23;
      if ( v23 > 0 )
        StringW = (unsigned __int16)v23 | 0x80070000;
      goto LABEL_46;
    }
    if ( lpDst )
      v19 = wcsnlen(lpDst, (unsigned __int64)v27 >> 1);
    else
      v19 = 0;
    v29 = v19;
    goto LABEL_35;
  }
LABEL_13:
  v11 = GetLastError();
  StringW = v11;
  if ( v11 > 0 )
    return (unsigned __int16)v11 | 0x80070000;
  return (unsigned int)StringW;
}

```

## disassembly

```asm
0x180002330  push    rbp
0x180002332  push    rbx
0x180002333  push    rsi
0x180002334  push    rdi
0x180002335  push    r12
0x180002337  push    r13
0x180002339  push    r15
0x18000233b  lea     rbp, [rsp-2D0h]
0x180002343  sub     rsp, 3D0h
0x18000234a  mov     rax, cs:__security_cookie
0x180002351  xor     rax, rsp
0x180002354  mov     [rbp+300h+var_40], rax
0x18000235b  mov     r12, r8
0x18000235e  mov     r15, rdx
0x180002361  mov     rdi, rcx
0x180002364  xor     edx, edx; Val
0x180002366  mov     r8d, 206h; Size
0x18000236c  lea     rcx, [rbp+300h+var_24E]; void *
0x180002373  call    memset_0
0x180002378  xor     r13d, r13d
0x18000237b  mov     [rsp+400h+var_3A4], 100h
0x180002382  mov     [rsp+400h+var_3A0], r13d
0x180002387  lea     rax, [rbp+300h+var_250]
0x18000238e  mov     [rsp+400h+lpDst], rax
0x180002393  lea     rax, [rbp+300h+var_360]
0x180002397  mov     [rbp+300h+lpMultiByteStr], rax
0x18000239b  mov     ebx, 208h
0x1800023a0  mov     [rsp+400h+var_3A8], ebx
0x1800023a4  mov     [rbp+300h+var_250], r13w
0x1800023ac  mov     [rbp+300h+var_370], 104h
0x1800023b3  mov     [rbp+300h+var_36C], 100h
0x1800023b9  mov     [rbp+300h+var_368], r13d
0x1800023bd  mov     [rbp+300h+var_360], r13b
0x1800023c1  test    rdi, rdi
0x1800023c4  jz      loc_1800025BC
0x1800023ca  test    r15, r15
0x1800023cd  jz      loc_1800025BC
0x1800023d3  test    r12, r12
0x1800023d6  jz      loc_1800025BC
0x1800023dc  mov     eax, [rdi+30h]
0x1800023df  test    eax, eax
0x1800023e1  jnz     short loc_180002428
0x1800023e3  mov     rdx, [rdi+28h]; Src
0x1800023e7  test    rdx, rdx
0x1800023ea  jz      short loc_18000241E
0x1800023ec  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800023f0  inc     r8
0x1800023f3  cmp     [rdx+r8*2], r13w
0x1800023f8  jnz     short loc_1800023F0
0x1800023fa  add     r8d, r8d; Size
0x1800023fd  mov     [rsp+400h+var_3E0], 1; bool
0x180002402  xor     r9d, r9d; unsigned int
0x180002405  lea     rcx, [rsp+400h+var_3D0]; this
0x18000240a  call    ?AuxAppend@STRU@@AEAAJPEBEKK_N@Z; STRU::AuxAppend(uchar const *,ulong,ulong,bool)
0x18000240f  mov     ebx, eax
0x180002411  test    eax, eax
0x180002413  js      loc_1800025D1
0x180002419  jmp     loc_180002551
0x18000241e  mov     ebx, 80070057h
0x180002423  jmp     loc_1800025D1
0x180002428  cmp     eax, 1
0x18000242b  jnz     loc_1800024B9
0x180002431  xor     ecx, ecx; lpModuleName
0x180002433  call    cs:__imp_GetModuleHandleW
0x180002439  mov     rbx, rax
0x18000243c  test    rax, rax
0x18000243f  jnz     short loc_18000245F
0x180002441  call    cs:__imp_GetLastError
0x180002447  mov     ebx, eax
0x180002449  test    eax, eax
0x18000244b  jle     loc_1800025E2
0x180002451  movzx   ebx, ax
0x180002454  or      ebx, 80070000h
0x18000245a  jmp     loc_1800025E2
0x18000245f  mov     rcx, [rdi+28h]; String
0x180002463  call    cs:__imp__wtoi
0x180002469  mov     r8, rbx; HINSTANCE
0x18000246c  lea     rcx, [rsp+400h+var_398]; this
0x180002471  mov     edx, eax; unsigned int
0x180002473  call    ?LoadStringW@STRA@@QEAAJKPEAUHINSTANCE__@@@Z; STRA::LoadStringW(ulong,HINSTANCE__ *)
0x180002478  mov     ebx, eax
0x18000247a  test    eax, eax
0x18000247c  js      loc_1800025C1
0x180002482  mov     rdx, [rbp+300h+lpMultiByteStr]; lpMultiByteStr
0x180002486  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000248a  inc     r8; cbMultiByte
0x18000248d  cmp     [rdx+r8], r13b
0x180002491  jnz     short loc_18000248A
0x180002493  mov     [rsp+400h+var_3D8], r13b; bool
0x180002498  lea     rcx, [rsp+400h+var_3D0]; this
0x18000249d  xor     r9d, r9d; unsigned int
0x1800024a0  mov     [rsp+400h+var_3E0], 1; bool
0x1800024a5  call    ?AuxAppendA@STRU@@AEAAJPEBEKK_N1@Z; STRU::AuxAppendA(uchar const *,ulong,ulong,bool,bool)
0x1800024aa  mov     ebx, eax
0x1800024ac  test    eax, eax
0x1800024ae  jns     loc_180002551
0x1800024b4  jmp     loc_1800025C1
0x1800024b9  cmp     eax, 2
0x1800024bc  jnz     loc_1800025B5
0x1800024c2  mov     rcx, [rdi+28h]; lpSrc
0x1800024c6  xor     r8d, r8d; nSize
0x1800024c9  xor     edx, edx; lpDst
0x1800024cb  call    cs:__imp_ExpandEnvironmentStringsW
0x1800024d1  mov     esi, eax
0x1800024d3  test    eax, eax
0x1800024d5  jz      loc_180002441
0x1800024db  lea     edx, ds:2[rax*2]; unsigned int
0x1800024e2  cmp     edx, ebx
0x1800024e4  jbe     short loc_180002512
0x1800024e6  lea     rcx, [rsp+400h+var_3D0]; this
0x1800024eb  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x1800024f0  test    al, al
0x1800024f2  jnz     short loc_180002512
0x1800024f4  call    cs:__imp_GetLastError
0x1800024fa  mov     ebx, eax
0x1800024fc  test    eax, eax
0x1800024fe  jle     short loc_180002509
0x180002500  movzx   ebx, ax
0x180002503  or      ebx, 80070000h
0x180002509  test    ebx, ebx
0x18000250b  jns     short loc_180002515
0x18000250d  jmp     loc_1800025D1
0x180002512  mov     ebx, r13d
0x180002515  mov     rdx, [rsp+400h+lpDst]; lpDst
0x18000251a  mov     r8d, esi; nSize
0x18000251d  mov     rcx, [rdi+28h]; lpSrc
0x180002521  call    cs:__imp_ExpandEnvironmentStringsW
0x180002527  test    eax, eax
0x180002529  jz      short loc_18000259E
0x18000252b  cmp     eax, esi
0x18000252d  ja      short loc_18000259E
0x18000252f  cmp     [rsp+400h+lpDst], r13
0x180002534  jnz     short loc_18000253B
0x180002536  mov     rax, r13
0x180002539  jmp     short loc_18000254D
0x18000253b  mov     edx, [rsp+400h+var_3A8]
0x18000253f  mov     rcx, [rsp+400h+lpDst]; Source
0x180002544  shr     rdx, 1; MaxCount
0x180002547  call    cs:__imp_wcsnlen
0x18000254d  mov     [rsp+400h+var_3A0], eax
0x180002551  mov     eax, [rsp+400h+var_3A0]
0x180002555  lea     edi, ds:2[rax*2]
0x18000255c  cmp     edi, [r15+28h]
0x180002560  jbe     short loc_180002587
0x180002562  mov     edx, edi; unsigned int
0x180002564  mov     rcx, r15; this
0x180002567  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x18000256c  test    al, al
0x18000256e  jnz     short loc_180002587
0x180002570  call    cs:__imp_GetLastError
0x180002576  mov     ebx, eax
0x180002578  test    eax, eax
0x18000257a  jle     short loc_1800025C1
0x18000257c  movzx   ebx, ax
0x18000257f  or      ebx, 80070000h
0x180002585  jmp     short loc_1800025C1
0x180002587  mov     rdx, [rsp+400h+lpDst]; Src
0x18000258c  mov     [r12], edi
0x180002590  mov     rcx, [r15+20h]; void *
0x180002594  mov     r8d, edi; Size
0x180002597  call    memcpy_0
0x18000259c  jmp     short loc_1800025C1
0x18000259e  call    cs:__imp_GetLastError
0x1800025a4  mov     ebx, eax
0x1800025a6  test    eax, eax
0x1800025a8  jle     short loc_1800025D1
0x1800025aa  movzx   ebx, ax
0x1800025ad  or      ebx, 80070000h
0x1800025b3  jmp     short loc_1800025D1
0x1800025b5  mov     ebx, 8007000Dh
0x1800025ba  jmp     short loc_1800025E2
0x1800025bc  mov     ebx, 80070057h
0x1800025c1  cmp     byte ptr [rbp+300h+var_36C], r13b
0x1800025c5  jz      short loc_1800025D1
0x1800025c7  lea     rcx, [rsp+400h+var_398]; this
0x1800025cc  call    ?FreeMemoryInternal@BUFFER@@AEAAXXZ; BUFFER::FreeMemoryInternal(void)
0x1800025d1  cmp     byte ptr [rsp+400h+var_3A4], r13b
0x1800025d6  jz      short loc_1800025E2
0x1800025d8  lea     rcx, [rsp+400h+var_3D0]; this
0x1800025dd  call    ?FreeMemoryInternal@BUFFER@@AEAAXXZ; BUFFER::FreeMemoryInternal(void)
0x1800025e2  mov     eax, ebx
0x1800025e4  mov     rcx, [rbp+300h+var_40]
0x1800025eb  xor     rcx, rsp; StackCookie
0x1800025ee  call    __security_check_cookie
0x1800025f3  add     rsp, 3D0h
0x1800025fa  pop     r15
0x1800025fc  pop     r13
0x1800025fe  pop     r12
0x180002600  pop     rdi
0x180002601  pop     rsi
0x180002602  pop     rbx
0x180002603  pop     rbp
0x180002604  retn
```
