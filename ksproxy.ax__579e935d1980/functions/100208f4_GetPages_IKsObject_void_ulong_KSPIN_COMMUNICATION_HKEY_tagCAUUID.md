# GetPages(IKsObject *,void *,ulong,KSPIN_COMMUNICATION,HKEY__ *,tagCAUUID *)

- ea: `0x100208f4`
- end: `0x10020b25`
- name: `?GetPages@@YGJPAUIKsObject@@PAXKW4KSPIN_COMMUNICATION@@PAUHKEY__@@PAUtagCAUUID@@@Z`
- size: `561`
- prototype: `int __stdcall(struct IKsObject *, void *, unsigned int, enum KSPIN_COMMUNICATION, HKEY, struct tagCAUUID *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x100135e0`
- `0x10017540`

## callees

- `0x10006937`
- `0x1001f3b0`
- `0x1001ff00`
- `0x1001ffa0`
- `0x100206a3`
- `0x100208f4`
- `0x1002d510`
- `0x1003aba0`
- `0x1003b5e4`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x10020a3d`
- `ADVAPI32!RegQueryValueExW` at `0x10020a3d`
- `ADVAPI32!RegCloseKey` at `0x10020a49`
- `ADVAPI32!RegCloseKey` at `0x10020a49`
- `ADVAPI32!RegOpenKeyExW` at `0x10020a14`
- `ADVAPI32!RegOpenKeyExW` at `0x10020a14`
- `ole32!CoTaskMemAlloc` at `0x10020978`
- `ole32!CoTaskMemAlloc` at `0x10020978`
- `ole32!StringFromGUID2` at `0x100209d3`
- `ole32!StringFromGUID2` at `0x100209d3`

## string_xrefs

- `0x10020a34`: `clsid`

## pseudocode

```c
int __userpurge GetPages@<eax>(
        void *a1@<edx>,
        int a2@<ecx>,
        struct IKsObject *a3,
        void *a4,
        HKEY a5,
        int *a6,
        HKEY a7,
        struct tagCAUUID *a8)
{
  int *v8; // edi
  HANDLE v9; // ebx
  HKEY v10; // ebx
  _DWORD *v11; // esi
  LSTATUS v13; // esi
  int v14; // eax
  int v15; // ecx
  int v16; // esi
  int v17; // edx
  _DWORD *v18; // edi
  unsigned __int16 *v19; // [esp+0h] [ebp-308h]
  HKEY v20; // [esp+4h] [ebp-304h]
  HKEY phkResult; // [esp+Ch] [ebp-2FCh] BYREF
  HANDLE hDevice; // [esp+10h] [ebp-2F8h]
  _DWORD *v23; // [esp+14h] [ebp-2F4h]
  enum KSPIN_COMMUNICATION v24; // [esp+18h] [ebp-2F0h]
  DWORD cbData; // [esp+1Ch] [ebp-2ECh] BYREF
  DWORD BytesReturned; // [esp+20h] [ebp-2E8h] BYREF
  HKEY hKey; // [esp+24h] [ebp-2E4h]
  GUID InBuffer; // [esp+28h] [ebp-2E0h] BYREF
  int v29; // [esp+38h] [ebp-2D0h]
  int v30; // [esp+3Ch] [ebp-2CCh]
  struct IKsObject *v31; // [esp+40h] [ebp-2C8h]
  int v32; // [esp+44h] [ebp-2C4h]
  _DWORD Data[4]; // [esp+48h] [ebp-2C0h] BYREF
  struct tagCAUUID OutBuffer[2]; // [esp+58h] [ebp-2B0h] BYREF
  CMediaType v35; // [esp+68h] [ebp-2A0h] BYREF
  OLECHAR sz[40]; // [esp+B0h] [ebp-258h] BYREF
  WCHAR SubKey[258]; // [esp+100h] [ebp-208h] BYREF

  v8 = a6;
  v9 = a1;
  hKey = a5;
  hDevice = a1;
  v24 = (enum KSPIN_COMMUNICATION)a6;
  BytesReturned = 0;
  phkResult = 0;
  *a6 = 0;
  a6[1] = 0;
  if ( a4 == (void *)4
    && !(*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)a2 + 12))(*(_DWORD *)(*(_DWORD *)a2 + 12), a2) )
  {
    KsGetMediaTypeCount(v9, (int)a3, (int)&phkResult);
    v10 = phkResult;
    if ( phkResult )
    {
      v11 = CoTaskMemAlloc(16 * (_DWORD)phkResult);
      v23 = v11;
      a6[1] = (int)v11;
      if ( !v11 )
        return -2147024882;
      do
      {
        v10 = (HKEY)((char *)v10 - 1);
        memset(&v35, 0, sizeof(v35));
        if ( KsGetMediaType((int)v10, &v35, hDevice, (int)a3) >= 0 )
        {
          StringFromGUID2(&v35.formattype, sz, 39);
          StringCchPrintfW(SubKey, 0x100u, L"SYSTEM\\CurrentControlSet\\Control\\MediaSpecifiers\\%s", sz);
          if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &phkResult) )
          {
            cbData = 16;
            v13 = RegQueryValueExW(phkResult, L"clsid", 0, 0, (LPBYTE)Data, &cbData);
            RegCloseKey(phkResult);
            if ( !v13 )
            {
              v14 = *v8;
              v15 = *v8;
              v16 = v8[1];
              if ( *v8 )
              {
                do
                {
                  v17 = 0;
                  while ( Data[v17] == *(_DWORD *)(v16 + 4 * v17) )
                  {
                    if ( ++v17 == 4 )
                      goto LABEL_17;
                  }
                  v16 += 16;
                  --v15;
                }
                while ( v15 );
                v14 = *v8;
              }
              *v8 = v14 + 1;
              v18 = v23;
              v23 += 4;
              *v18++ = Data[0];
              *v18++ = Data[1];
              *v18 = Data[2];
              v18[1] = Data[3];
              v8 = (int *)v24;
            }
          }
        }
LABEL_17:
        ;
      }
      while ( v10 );
    }
    v9 = hDevice;
  }
  InBuffer = _GUID_8c134960_51ad_11cf_878a_94f801c10000;
  v31 = a3;
  v29 = 11;
  v32 = 0;
  v30 = 1;
  if ( KsSynchronousDeviceControl(v9, 0x2F0003u, &InBuffer, 0x20u, OutBuffer, 0x10u, &BytesReturned) >= 0 )
    AppendSpecificPropertyPages(
      1,
      v24,
      OutBuffer,
      (unsigned int)L"SYSTEM\\CurrentControlSet\\Control\\MediaCategories",
      hKey,
      v19,
      v20);
  return 0;
}

```

## disassembly

```asm
0x100208f4  mov     edi, edi
0x100208f6  push    ebp
0x100208f7  mov     ebp, esp
0x100208f9  and     esp, 0FFFFFFF8h
0x100208fc  sub     esp, 2FCh
0x10020902  mov     eax, ___security_cookie
0x10020907  xor     eax, esp
0x10020909  mov     [esp+2FCh+var_4], eax
0x10020910  mov     eax, [ebp+arg_8]
0x10020913  push    ebx
0x10020914  push    esi; HKEY
0x10020915  push    edi; unsigned __int16 *
0x10020916  mov     edi, [ebp+arg_C]
0x10020919  mov     ebx, edx
0x1002091b  mov     [esp+308h+hKey], eax
0x1002091f  xor     eax, eax
0x10020921  cmp     [ebp+arg_4], 4
0x10020925  mov     [esp+308h+hDevice], ebx
0x10020929  mov     [esp+308h+var_2F0], edi
0x1002092d  mov     [esp+308h+BytesReturned], eax
0x10020931  mov     [esp+308h+phkResult], eax
0x10020935  mov     [edi], eax
0x10020937  mov     [edi+4], eax
0x1002093a  jnz     loc_10020AA6
0x10020940  mov     eax, [ecx]
0x10020942  push    ecx
0x10020943  mov     esi, [eax+0Ch]
0x10020946  mov     ecx, esi; this
0x10020948  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002094e  call    esi
0x10020950  test    eax, eax
0x10020952  jnz     loc_10020AA6
0x10020958  lea     eax, [esp+308h+phkResult]
0x1002095c  push    eax; int
0x1002095d  push    [ebp+arg_0]; int
0x10020960  push    ebx; hDevice
0x10020961  call    _KsGetMediaTypeCount@12; KsGetMediaTypeCount(x,x,x)
0x10020966  mov     ebx, [esp+308h+phkResult]
0x1002096a  test    ebx, ebx
0x1002096c  jz      loc_10020AA2
0x10020972  mov     eax, ebx
0x10020974  shl     eax, 4
0x10020977  push    eax; cb
0x10020978  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1002097e  mov     esi, eax
0x10020980  mov     [esp+308h+var_2F4], esi
0x10020984  mov     [edi+4], esi
0x10020987  test    esi, esi
0x10020989  jnz     short loc_10020995
0x1002098b  mov     eax, 8007000Eh
0x10020990  jmp     loc_10020B0E
0x10020995  push    48h ; 'H'; Size
0x10020997  lea     eax, [esp+30Ch+var_2A0]
0x1002099b  dec     ebx
0x1002099c  push    0; Val
0x1002099e  push    eax; void *
0x1002099f  call    _memset
0x100209a4  add     esp, 0Ch
0x100209a7  lea     eax, [esp+308h+var_2A0]
0x100209ab  push    [ebp+arg_0]; int
0x100209ae  push    [esp+30Ch+hDevice]; hDevice
0x100209b2  push    eax; CMediaType *
0x100209b3  push    ebx; int
0x100209b4  call    _KsGetMediaType@16; KsGetMediaType(x,x,x,x)
0x100209b9  test    eax, eax
0x100209bb  js      loc_10020A9A
0x100209c1  push    27h ; '''; cchMax
0x100209c3  lea     eax, [esp+30Ch+sz]
0x100209ca  push    eax; lpsz
0x100209cb  lea     eax, [esp+310h+var_2A0.formattype]
0x100209d2  push    eax; rguid
0x100209d3  call    ds:__imp__StringFromGUID2@12; StringFromGUID2(x,x,x)
0x100209d9  lea     eax, [esp+308h+sz]
0x100209e0  push    eax
0x100209e1  push    offset aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Med"...
0x100209e6  lea     eax, [esp+310h+SubKey]
0x100209ed  push    100h; unsigned int
0x100209f2  push    eax; unsigned __int16 *
0x100209f3  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x100209f8  add     esp, 10h
0x100209fb  lea     eax, [esp+308h+phkResult]
0x100209ff  push    eax; phkResult
0x10020a00  push    20019h; samDesired
0x10020a05  push    0; ulOptions
0x10020a07  lea     eax, [esp+314h+SubKey]
0x10020a0e  push    eax; lpSubKey
0x10020a0f  push    80000002h; hKey
0x10020a14  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x10020a1a  test    eax, eax
0x10020a1c  jnz     short loc_10020A9A
0x10020a1e  lea     eax, [esp+308h+cbData]
0x10020a22  mov     [esp+308h+cbData], 10h
0x10020a2a  push    eax; lpcbData
0x10020a2b  lea     eax, [esp+30Ch+Data]
0x10020a2f  push    eax; lpData
0x10020a30  push    0; lpType
0x10020a32  push    0; lpReserved
0x10020a34  push    offset aClsid; "clsid"
0x10020a39  push    [esp+31Ch+phkResult]; hKey
0x10020a3d  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x10020a43  push    [esp+308h+phkResult]; hKey
0x10020a47  mov     esi, eax
0x10020a49  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10020a4f  test    esi, esi
0x10020a51  jnz     short loc_10020A9A
0x10020a53  mov     eax, [edi]
0x10020a55  mov     ecx, eax
0x10020a57  mov     esi, [edi+4]
0x10020a5a  test    ecx, ecx
0x10020a5c  jz      short loc_10020A7E
0x10020a5e  xor     edx, edx
0x10020a60  lea     eax, [esp+308h+Data]
0x10020a64  mov     eax, [eax+edx*4]
0x10020a67  cmp     eax, [esi+edx*4]
0x10020a6a  jnz     short loc_10020A74
0x10020a6c  inc     edx
0x10020a6d  cmp     edx, 4
0x10020a70  jz      short loc_10020A9A
0x10020a72  jmp     short loc_10020A60
0x10020a74  add     esi, 10h
0x10020a77  sub     ecx, 1
0x10020a7a  jnz     short loc_10020A5E
0x10020a7c  mov     eax, [edi]
0x10020a7e  inc     eax
0x10020a7f  lea     esi, [esp+308h+Data]
0x10020a83  mov     [edi], eax
0x10020a85  mov     eax, [esp+308h+var_2F4]
0x10020a89  mov     edi, eax
0x10020a8b  add     eax, 10h
0x10020a8e  mov     [esp+308h+var_2F4], eax
0x10020a92  movsd
0x10020a93  movsd
0x10020a94  movsd
0x10020a95  movsd
0x10020a96  mov     edi, [esp+308h+var_2F0]
0x10020a9a  test    ebx, ebx
0x10020a9c  jnz     loc_10020995
0x10020aa2  mov     ebx, [esp+308h+hDevice]
0x10020aa6  mov     eax, [ebp+arg_0]
0x10020aa9  lea     edi, [esp+308h+InBuffer]
0x10020aad  mov     esi, offset __GUID_8c134960_51ad_11cf_878a_94f801c10000
0x10020ab2  movsd
0x10020ab3  movsd
0x10020ab4  movsd
0x10020ab5  movsd
0x10020ab6  mov     [esp+308h+var_2C8], eax
0x10020aba  xor     esi, esi
0x10020abc  lea     eax, [esp+308h+BytesReturned]
0x10020ac0  mov     [esp+308h+var_2D0], 0Bh
0x10020ac8  push    eax; lpBytesReturned
0x10020ac9  push    10h; nOutBufferSize
0x10020acb  lea     eax, [esp+310h+OutBuffer]
0x10020acf  mov     [esp+310h+var_2C4], 0
0x10020ad7  push    eax; lpOutBuffer
0x10020ad8  push    20h ; ' '; nInBufferSize
0x10020ada  lea     eax, [esp+318h+InBuffer]
0x10020ade  inc     esi
0x10020adf  push    eax; lpInBuffer
0x10020ae0  push    2F0003h; dwIoControlCode
0x10020ae5  push    ebx; hDevice
0x10020ae6  mov     [esp+324h+var_2CC], esi
0x10020aea  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x10020aef  test    eax, eax
0x10020af1  js      short loc_10020B0C
0x10020af3  push    [esp+308h+hKey]; hKey
0x10020af7  mov     ecx, [esp+30Ch+var_2F0]
0x10020afb  lea     eax, [esp+30Ch+OutBuffer]
0x10020aff  push    offset aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Med"...
0x10020b04  push    eax; struct tagCAUUID *
0x10020b05  mov     edx, esi
0x10020b07  call    ?AppendSpecificPropertyPages@@YGXPAUtagCAUUID@@KPAU_GUID@@PAGPAUHKEY__@@@Z; AppendSpecificPropertyPages(tagCAUUID *,ulong,_GUID *,ushort *,HKEY__ *)
0x10020b0c  xor     eax, eax
0x10020b0e  mov     ecx, [esp+308h+var_4]
0x10020b15  pop     edi
0x10020b16  pop     esi
0x10020b17  pop     ebx
0x10020b18  xor     ecx, esp; StackCookie
0x10020b1a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10020b1f  mov     esp, ebp
0x10020b21  pop     ebp
0x10020b22  retn    10h
```
