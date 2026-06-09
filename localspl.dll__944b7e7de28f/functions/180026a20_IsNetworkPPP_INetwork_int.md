# IsNetworkPPP(INetwork *,int *)

- ea: `0x180026a20`
- end: `0x180026c90`
- name: `?IsNetworkPPP@@YAJPEAUINetwork@@PEAH@Z`
- size: `624`
- prototype: `__int64 __fastcall(struct INetwork *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001446c`

## callees

- `0x180026a20`
- `0x180046650`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180026bb5`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180026bb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b8c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180026b82`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180026b82`
- `SPOOLSS!DllFreeSplMem` at `0x180026af8`
- `SPOOLSS!DllFreeSplMem` at `0x180026c5e`
- `SPOOLSS!DllFreeSplMem` at `0x180026af8`
- `SPOOLSS!DllFreeSplMem` at `0x180026c5e`
- `SPOOLSS!DllAllocSplMem` at `0x180026ab1`
- `SPOOLSS!DllAllocSplMem` at `0x180026ab1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026bfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026bfa`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180026b4b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180026b4b`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180026ad8`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180026ad8`

## pseudocode

```c
__int64 __fastcall IsNetworkPPP(struct INetwork *a1, int *a2)
{
  IP_ADAPTER_ADDRESSES_LH *v3; // rsi
  int v4; // r14d
  struct INetworkVtbl *lpVtbl; // rax
  int v6; // ebx
  signed int AdaptersAddresses; // eax
  __int64 v8; // rcx
  signed int LastError; // eax
  IP_ADAPTER_ADDRESSES_LH *i; // rdi
  bool v11; // zf
  int v12; // eax
  __int64 v14; // [rsp+40h] [rbp-29h] BYREF
  ULONG SizePointer; // [rsp+48h] [rbp-21h] BYREF
  __int64 v16; // [rsp+50h] [rbp-19h] BYREF
  LPOLESTR lpsz; // [rsp+58h] [rbp-11h] BYREF
  IID rclsid; // [rsp+60h] [rbp-9h] BYREF
  CHAR MultiByteStr[40]; // [rsp+70h] [rbp+7h] BYREF

  v16 = 0;
  v3 = 0;
  v14 = 0;
  *a2 = 0;
  v4 = 0;
  lpVtbl = a1->lpVtbl;
  SizePointer = 10000;
  v6 = ((__int64 (__fastcall *)(struct INetwork *, __int64 *))lpVtbl->GetNetworkConnections)(a1, &v16);
  if ( v6 >= 0 )
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(*(_QWORD *)v16 + 64LL))(v16, 1, &v14, 0);
  if ( !v6 && v14 )
  {
    while ( 1 )
    {
      v3 = (IP_ADAPTER_ADDRESSES_LH *)DllAllocSplMem(SizePointer);
      if ( !v3 )
      {
        v6 = -2147024882;
        goto LABEL_32;
      }
      AdaptersAddresses = GetAdaptersAddresses(0, 0x2Fu, 0, v3, &SizePointer);
      v6 = AdaptersAddresses;
      if ( AdaptersAddresses > 0 )
        v6 = (unsigned __int16)AdaptersAddresses | 0x80070000;
      if ( v6 != -2147024785 )
        break;
      DllFreeSplMem(v3);
    }
    if ( !v6 )
    {
      v8 = v14;
      do
      {
        if ( !v8 || v4 )
          break;
        lpsz = 0;
        rclsid = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, IID *))(*(_QWORD *)v8 + 96LL))(v8, &rclsid);
        if ( v6 >= 0 )
          v6 = StringFromCLSID(&rclsid, &lpsz);
        if ( !WideCharToMultiByte(0, 0, lpsz, -1, MultiByteStr, 40, 0, 0) )
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError > 0 )
            v6 = (unsigned __int16)LastError | 0x80070000;
        }
        if ( v6 >= 0 )
        {
          for ( i = v3; i; i = i->Next )
          {
            if ( !(unsigned int)_o__stricmp(i->AdapterName, MultiByteStr) && i->IfType == 23 )
            {
              v4 = 1;
              break;
            }
          }
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        v8 = 0;
        v14 = 0;
        if ( lpsz )
        {
          CoTaskMemFree(lpsz);
          v8 = v14;
          lpsz = 0;
        }
        v11 = v6 == 0;
        if ( v6 >= 0 )
        {
          v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v16 + 64LL))(v16, 1, &v14);
          v8 = v14;
          v6 = v12;
          v11 = v12 == 0;
        }
      }
      while ( v11 );
    }
  }
LABEL_32:
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v3 )
    DllFreeSplMem(v3);
  if ( v6 >= 0 )
    *a2 = v4;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180026a20  mov     [rsp-8+arg_10], rbx
0x180026a25  push    rbp
0x180026a26  push    rsi
0x180026a27  push    rdi
0x180026a28  push    r14
0x180026a2a  push    r15
0x180026a2c  lea     rbp, [rsp-37h]
0x180026a31  sub     rsp, 0A0h
0x180026a38  mov     rax, cs:__security_cookie
0x180026a3f  xor     rax, rsp
0x180026a42  mov     [rbp+57h+var_28], rax
0x180026a46  mov     r15, rdx
0x180026a49  mov     [rbp+57h+var_70], 0
0x180026a51  xor     esi, esi
0x180026a53  mov     [rbp+57h+var_80], 0
0x180026a5b  mov     [rdx], esi
0x180026a5d  xor     r14d, r14d
0x180026a60  mov     rax, [rcx]
0x180026a63  lea     rdx, [rbp+57h+var_70]
0x180026a67  mov     [rbp+57h+var_78], 2710h
0x180026a6e  mov     rax, [rax+68h]
0x180026a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a77  mov     ebx, eax
0x180026a79  test    eax, eax
0x180026a7b  js      short loc_180026A99
0x180026a7d  mov     rcx, [rbp+57h+var_70]
0x180026a81  lea     r8, [rbp+57h+var_80]
0x180026a85  xor     r9d, r9d
0x180026a88  lea     edx, [rsi+1]
0x180026a8b  mov     rax, [rcx]
0x180026a8e  mov     rax, [rax+40h]
0x180026a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a97  mov     ebx, eax
0x180026a99  test    ebx, ebx
0x180026a9b  jnz     loc_180026C39
0x180026aa1  mov     rcx, [rbp+57h+var_80]
0x180026aa5  test    rcx, rcx
0x180026aa8  jz      loc_180026C39
0x180026aae  mov     ecx, [rbp+57h+var_78]
0x180026ab1  call    cs:__imp_DllAllocSplMem
0x180026ab7  mov     rsi, rax
0x180026aba  test    rax, rax
0x180026abd  jz      loc_180026BCB
0x180026ac3  xor     r8d, r8d; Reserved
0x180026ac6  lea     rax, [rbp+57h+var_78]
0x180026aca  mov     r9, rsi; AdapterAddresses
0x180026acd  mov     [rsp+0C0h+SizePointer], rax; SizePointer
0x180026ad2  xor     ecx, ecx; Family
0x180026ad4  lea     edx, [r8+2Fh]; Flags
0x180026ad8  call    cs:__imp_GetAdaptersAddresses
0x180026ade  mov     ebx, eax
0x180026ae0  test    eax, eax
0x180026ae2  jle     short loc_180026AED
0x180026ae4  movzx   ebx, ax
0x180026ae7  or      ebx, 80070000h
0x180026aed  cmp     ebx, 8007006Fh
0x180026af3  jnz     short loc_180026B00
0x180026af5  mov     rcx, rsi
0x180026af8  call    cs:__imp_DllFreeSplMem
0x180026afe  jmp     short loc_180026AAE
0x180026b00  test    ebx, ebx
0x180026b02  jnz     loc_180026C39
0x180026b08  mov     rcx, [rbp+57h+var_80]
0x180026b0c  test    rcx, rcx
0x180026b0f  jz      loc_180026C39
0x180026b15  test    r14d, r14d
0x180026b18  jnz     loc_180026C39
0x180026b1e  xorps   xmm0, xmm0
0x180026b21  mov     [rbp+57h+lpsz], 0
0x180026b29  movups  xmmword ptr [rbp+57h+rclsid.Data1], xmm0
0x180026b2d  mov     rax, [rcx]
0x180026b30  lea     rdx, [rbp+57h+rclsid]
0x180026b34  mov     rax, [rax+60h]
0x180026b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b3d  mov     ebx, eax
0x180026b3f  test    eax, eax
0x180026b41  js      short loc_180026B53
0x180026b43  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x180026b47  lea     rcx, [rbp+57h+rclsid]; rclsid
0x180026b4b  call    cs:__imp_StringFromCLSID
0x180026b51  mov     ebx, eax
0x180026b53  mov     r8, [rbp+57h+lpsz]; lpWideCharStr
0x180026b57  lea     rax, [rbp+57h+MultiByteStr]
0x180026b5b  mov     [rsp+0C0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180026b64  or      r9d, 0FFFFFFFFh; cchWideChar
0x180026b68  mov     [rsp+0C0h+lpDefaultChar], 0; lpDefaultChar
0x180026b71  xor     edx, edx; dwFlags
0x180026b73  mov     [rsp+0C0h+cbMultiByte], 28h ; '('; cbMultiByte
0x180026b7b  xor     ecx, ecx; CodePage
0x180026b7d  mov     [rsp+0C0h+SizePointer], rax; lpMultiByteStr
0x180026b82  call    cs:__imp_WideCharToMultiByte
0x180026b88  test    eax, eax
0x180026b8a  jnz     short loc_180026BA1
0x180026b8c  call    cs:__imp_GetLastError
0x180026b92  mov     ebx, eax
0x180026b94  test    eax, eax
0x180026b96  jle     short loc_180026BA1
0x180026b98  movzx   ebx, ax
0x180026b9b  or      ebx, 80070000h
0x180026ba1  test    ebx, ebx
0x180026ba3  js      short loc_180026BD8
0x180026ba5  mov     rdi, rsi
0x180026ba8  test    rdi, rdi
0x180026bab  jz      short loc_180026BD8
0x180026bad  mov     rcx, [rdi+10h]
0x180026bb1  lea     rdx, [rbp+57h+MultiByteStr]
0x180026bb5  call    cs:__imp__o__stricmp
0x180026bbb  test    eax, eax
0x180026bbd  jnz     short loc_180026BC5
0x180026bbf  cmp     dword ptr [rdi+64h], 17h
0x180026bc3  jz      short loc_180026BD2
0x180026bc5  mov     rdi, [rdi+8]
0x180026bc9  jmp     short loc_180026BA8
0x180026bcb  mov     ebx, 8007000Eh
0x180026bd0  jmp     short loc_180026C39
0x180026bd2  mov     r14d, 1
0x180026bd8  mov     rcx, [rbp+57h+var_80]
0x180026bdc  mov     rax, [rcx]
0x180026bdf  mov     rax, [rax+10h]
0x180026be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026be8  mov     rax, [rbp+57h+lpsz]
0x180026bec  xor     ecx, ecx
0x180026bee  mov     [rbp+57h+var_80], rcx
0x180026bf2  test    rax, rax
0x180026bf5  jz      short loc_180026C0C
0x180026bf7  mov     rcx, rax; pv
0x180026bfa  call    cs:__imp_CoTaskMemFree
0x180026c00  mov     rcx, [rbp+57h+var_80]
0x180026c04  mov     [rbp+57h+lpsz], 0
0x180026c0c  test    ebx, ebx
0x180026c0e  js      short loc_180026C33
0x180026c10  mov     rcx, [rbp+57h+var_70]
0x180026c14  lea     r8, [rbp+57h+var_80]
0x180026c18  xor     r9d, r9d
0x180026c1b  mov     rax, [rcx]
0x180026c1e  lea     edx, [r9+1]
0x180026c22  mov     rax, [rax+40h]
0x180026c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c2b  mov     rcx, [rbp+57h+var_80]
0x180026c2f  mov     ebx, eax
0x180026c31  test    eax, eax
0x180026c33  jz      loc_180026B0C
0x180026c39  mov     rcx, [rbp+57h+var_70]
0x180026c3d  test    rcx, rcx
0x180026c40  jz      short loc_180026C56
0x180026c42  mov     rax, [rcx]
0x180026c45  mov     rax, [rax+10h]
0x180026c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c4e  mov     [rbp+57h+var_70], 0
0x180026c56  test    rsi, rsi
0x180026c59  jz      short loc_180026C64
0x180026c5b  mov     rcx, rsi
0x180026c5e  call    cs:__imp_DllFreeSplMem
0x180026c64  test    ebx, ebx
0x180026c66  js      short loc_180026C6B
0x180026c68  mov     [r15], r14d
0x180026c6b  mov     eax, ebx
0x180026c6d  mov     rcx, [rbp+57h+var_28]
0x180026c71  xor     rcx, rsp; StackCookie
0x180026c74  call    __security_check_cookie
0x180026c79  mov     rbx, [rsp+0C0h+arg_10]
0x180026c81  add     rsp, 0A0h
0x180026c88  pop     r15
0x180026c8a  pop     r14
0x180026c8c  pop     rdi
0x180026c8d  pop     rsi
0x180026c8e  pop     rbp
0x180026c8f  retn
```
