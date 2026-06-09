# GetGUIDForFirstDADAdapter(_GUID * *)

- ea: `0x180008cb8`
- end: `0x180008f14`
- name: `?GetGUIDForFirstDADAdapter@@YAXPEAPEAU_GUID@@@Z`
- size: `604`
- prototype: `void __fastcall(struct _GUID **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180009750`

## callees

- `0x18000797c`
- `0x1800086a8`
- `0x180008cb8`
- `0x18001f690`

## import_xrefs

- `msvcrt!free` at `0x180008e91`
- `msvcrt!free` at `0x180008edf`
- `msvcrt!free` at `0x180008e91`
- `msvcrt!free` at `0x180008edf`
- `KERNEL32!GetLastError` at `0x180008dfb`
- `KERNEL32!GetLastError` at `0x180008dfb`
- `KERNEL32!MultiByteToWideChar` at `0x180008df1`
- `KERNEL32!MultiByteToWideChar` at `0x180008e26`
- `KERNEL32!MultiByteToWideChar` at `0x180008e58`
- `KERNEL32!MultiByteToWideChar` at `0x180008df1`
- `KERNEL32!MultiByteToWideChar` at `0x180008e26`
- `KERNEL32!MultiByteToWideChar` at `0x180008e58`
- `ole32!CoTaskMemAlloc` at `0x180008d1e`
- `ole32!CoTaskMemAlloc` at `0x180008eb8`
- `ole32!CoTaskMemAlloc` at `0x180008d1e`
- `ole32!CoTaskMemAlloc` at `0x180008eb8`
- `ole32!CLSIDFromString` at `0x180008e78`
- `ole32!CLSIDFromString` at `0x180008e78`
- `ole32!CoTaskMemFree` at `0x180008ee8`
- `ole32!CoTaskMemFree` at `0x180008ee8`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180008d0b`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180008d44`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180008d0b`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180008d44`

## pseudocode

```c
void __fastcall GetGUIDForFirstDADAdapter(struct _GUID **a1)
{
  IP_ADAPTER_ADDRESSES_LH *v2; // r14
  IP_ADAPTER_ADDRESSES_LH *v3; // rdi
  IFTYPE IfType; // ecx
  unsigned __int64 v5; // rax
  __int64 v6; // rdx
  PIP_ADAPTER_UNICAST_ADDRESS_LH i; // rsi
  const CHAR *AdapterName; // r15
  const OLECHAR *v9; // rcx
  __int64 v10; // rax
  int cchWideChar; // r13d
  __int64 v12; // rbx
  struct _GUID *v13; // rax
  ULONG SizePointer; // [rsp+30h] [rbp-D0h] BYREF
  CLSID pclsid; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR lpWideCharStr; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v17[264]; // [rsp+58h] [rbp-A8h] BYREF

  if ( a1 )
  {
    v2 = 0;
    SizePointer = 0;
    if ( GetAdaptersAddresses(0, 0x86u, 0, 0, &SizePointer) == 111 )
    {
      v2 = (IP_ADAPTER_ADDRESSES_LH *)CoTaskMemAlloc(SizePointer);
      if ( v2 )
      {
        if ( !GetAdaptersAddresses(0, 0x86u, 0, v2, &SizePointer) )
        {
          v3 = v2;
          do
          {
            IfType = v3->IfType;
            if ( IfType == 6
              || (v5 = IfType - 55, (unsigned int)v5 <= 0x3E) && (v6 = 0x4000000000014081LL, _bittest64(&v6, v5))
              || IfType == 161 )
            {
              for ( i = v3->FirstUnicastAddress; i; i = i->Next )
              {
                if ( i->DadState == NldsDuplicate )
                {
                  AdapterName = v3->AdapterName;
                  lpWideCharStr = (LPWSTR)v17;
                  if ( AdapterName )
                  {
                    v10 = -1;
                    do
                      ++v10;
                    while ( AdapterName[v10] );
                    cchWideChar = v10 + 1;
                    ATL::AtlConvAllocMemory<unsigned short>(&lpWideCharStr, (unsigned int)(v10 + 1), v17);
                    if ( !MultiByteToWideChar(3u, 0, AdapterName, cchWideChar, lpWideCharStr, cchWideChar) )
                    {
                      if ( GetLastError() != 122
                        || (v12 = (unsigned int)MultiByteToWideChar(3u, 0, AdapterName, cchWideChar, 0, 0),
                            ATL::AtlConvAllocMemory<unsigned short>(&lpWideCharStr, v12, v17),
                            !MultiByteToWideChar(3u, 0, AdapterName, cchWideChar, lpWideCharStr, v12)) )
                      {
                        ATL::AtlThrowLastWin32();
                      }
                    }
                    v9 = lpWideCharStr;
                  }
                  else
                  {
                    v9 = 0;
                    lpWideCharStr = 0;
                  }
                  pclsid = 0;
                  if ( !CLSIDFromString(v9, &pclsid) )
                  {
                    v13 = (struct _GUID *)CoTaskMemAlloc(0x10u);
                    *a1 = v13;
                    if ( v13 )
                      *v13 = pclsid;
                    if ( lpWideCharStr != (LPWSTR)v17 )
                      free(lpWideCharStr);
                    goto LABEL_31;
                  }
                  if ( lpWideCharStr != (LPWSTR)v17 )
                    free(lpWideCharStr);
                }
              }
            }
            v3 = v3->Next;
          }
          while ( v3 );
        }
      }
    }
LABEL_31:
    CoTaskMemFree(v2);
  }
}

```

## disassembly

```asm
0x180008cb8  test    rcx, rcx
0x180008cbb  jz      locret_180008F0D
0x180008cc1  push    rbp
0x180008cc2  push    rbx
0x180008cc3  push    rsi
0x180008cc4  push    rdi
0x180008cc5  push    r12
0x180008cc7  push    r13
0x180008cc9  push    r14
0x180008ccb  push    r15
0x180008ccd  lea     rbp, [rsp-78h]
0x180008cd2  sub     rsp, 178h
0x180008cd9  mov     rax, cs:__security_cookie
0x180008ce0  xor     rax, rsp
0x180008ce3  mov     [rbp+0B0h+var_50], rax
0x180008ce7  mov     r12, rcx
0x180008cea  lea     rax, [rsp+1B0h+var_180]
0x180008cef  mov     ebx, 86h
0x180008cf4  mov     [rsp+1B0h+SizePointer], rax; SizePointer
0x180008cf9  xor     r14d, r14d
0x180008cfc  mov     edx, ebx; Flags
0x180008cfe  xor     r9d, r9d; AdapterAddresses
0x180008d01  mov     [rsp+1B0h+var_180], r14d
0x180008d06  xor     r8d, r8d; Reserved
0x180008d09  xor     ecx, ecx; Family
0x180008d0b  call    cs:__imp_GetAdaptersAddresses
0x180008d11  cmp     eax, 6Fh ; 'o'
0x180008d14  jnz     loc_180008EE5
0x180008d1a  mov     ecx, [rsp+1B0h+var_180]; cb
0x180008d1e  call    cs:__imp_CoTaskMemAlloc
0x180008d24  mov     r14, rax
0x180008d27  test    rax, rax
0x180008d2a  jz      loc_180008EE5
0x180008d30  lea     rax, [rsp+1B0h+var_180]
0x180008d35  mov     r9, r14; AdapterAddresses
0x180008d38  xor     r8d, r8d; Reserved
0x180008d3b  mov     [rsp+1B0h+SizePointer], rax; SizePointer
0x180008d40  mov     edx, ebx; Flags
0x180008d42  xor     ecx, ecx; Family
0x180008d44  call    cs:__imp_GetAdaptersAddresses
0x180008d4a  test    eax, eax
0x180008d4c  jnz     loc_180008EE5
0x180008d52  mov     rdi, r14
0x180008d55  mov     ecx, [rdi+64h]
0x180008d58  cmp     ecx, 6
0x180008d5b  jz      short loc_180008D81
0x180008d5d  lea     eax, [rcx-37h]
0x180008d60  cmp     eax, 3Eh ; '>'
0x180008d63  ja      short loc_180008D75
0x180008d65  mov     rdx, 4000000000014081h
0x180008d6f  bt      rdx, rax
0x180008d73  jb      short loc_180008D81
0x180008d75  cmp     ecx, 0A1h
0x180008d7b  jnz     loc_180008EA4
0x180008d81  mov     rsi, [rdi+18h]
0x180008d85  jmp     loc_180008E9B
0x180008d8a  cmp     dword ptr [rsi+28h], 2
0x180008d8e  jnz     loc_180008E97
0x180008d94  mov     r15, [rdi+10h]
0x180008d98  lea     rax, [rsp+1B0h+var_158]
0x180008d9d  mov     [rsp+1B0h+lpWideCharStr], rax
0x180008da2  test    r15, r15
0x180008da5  jnz     short loc_180008DB3
0x180008da7  xor     ecx, ecx
0x180008da9  mov     [rsp+1B0h+lpWideCharStr], rcx
0x180008dae  jmp     loc_180008E6B
0x180008db3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008db7  inc     rax
0x180008dba  cmp     byte ptr [r15+rax], 0
0x180008dbf  jnz     short loc_180008DB7
0x180008dc1  lea     r13d, [rax+1]
0x180008dc5  mov     edx, r13d
0x180008dc8  lea     r8, [rsp+1B0h+var_158]
0x180008dcd  lea     rcx, [rsp+1B0h+lpWideCharStr]
0x180008dd2  call    ??$AtlConvAllocMemory@G@ATL@@YAXPEAPEAGHPEAGH@Z; ATL::AtlConvAllocMemory<ushort>(ushort * *,int,ushort *,int)
0x180008dd7  mov     rax, [rsp+1B0h+lpWideCharStr]
0x180008ddc  xor     edx, edx; dwFlags
0x180008dde  mov     [rsp+1B0h+cchWideChar], r13d; cchWideChar
0x180008de3  mov     r9d, r13d; cbMultiByte
0x180008de6  mov     r8, r15; lpMultiByteStr
0x180008de9  mov     [rsp+1B0h+SizePointer], rax; lpWideCharStr
0x180008dee  lea     ecx, [rdx+3]; CodePage
0x180008df1  call    cs:__imp_MultiByteToWideChar
0x180008df7  test    eax, eax
0x180008df9  jnz     short loc_180008E66
0x180008dfb  call    cs:__imp_GetLastError
0x180008e01  cmp     eax, 7Ah ; 'z'
0x180008e04  jnz     loc_180008F0E
0x180008e0a  mov     [rsp+1B0h+cchWideChar], 0; cchWideChar
0x180008e12  lea     ecx, [rax-77h]; CodePage
0x180008e15  mov     r9d, r13d; cbMultiByte
0x180008e18  mov     [rsp+1B0h+SizePointer], 0; lpWideCharStr
0x180008e21  mov     r8, r15; lpMultiByteStr
0x180008e24  xor     edx, edx; dwFlags
0x180008e26  call    cs:__imp_MultiByteToWideChar
0x180008e2c  mov     edx, eax
0x180008e2e  lea     r8, [rsp+1B0h+var_158]
0x180008e33  lea     rcx, [rsp+1B0h+lpWideCharStr]
0x180008e38  mov     ebx, eax
0x180008e3a  call    ??$AtlConvAllocMemory@G@ATL@@YAXPEAPEAGHPEAGH@Z; ATL::AtlConvAllocMemory<ushort>(ushort * *,int,ushort *,int)
0x180008e3f  mov     rax, [rsp+1B0h+lpWideCharStr]
0x180008e44  xor     edx, edx; dwFlags
0x180008e46  mov     [rsp+1B0h+cchWideChar], ebx; cchWideChar
0x180008e4a  mov     r9d, r13d; cbMultiByte
0x180008e4d  mov     r8, r15; lpMultiByteStr
0x180008e50  mov     [rsp+1B0h+SizePointer], rax; lpWideCharStr
0x180008e55  lea     ecx, [rdx+3]; CodePage
0x180008e58  call    cs:__imp_MultiByteToWideChar
0x180008e5e  test    eax, eax
0x180008e60  jz      loc_180008F0E
0x180008e66  mov     rcx, [rsp+1B0h+lpWideCharStr]; lpsz
0x180008e6b  xorps   xmm0, xmm0
0x180008e6e  lea     rdx, [rsp+1B0h+pclsid]; pclsid
0x180008e73  movups  xmmword ptr [rsp+1B0h+pclsid.Data1], xmm0
0x180008e78  call    cs:__imp_CLSIDFromString
0x180008e7e  test    eax, eax
0x180008e80  jz      short loc_180008EB3
0x180008e82  mov     rcx, [rsp+1B0h+lpWideCharStr]; Block
0x180008e87  lea     rax, [rsp+1B0h+var_158]
0x180008e8c  cmp     rcx, rax
0x180008e8f  jz      short loc_180008E97
0x180008e91  call    cs:__imp_free
0x180008e97  mov     rsi, [rsi+8]
0x180008e9b  test    rsi, rsi
0x180008e9e  jnz     loc_180008D8A
0x180008ea4  mov     rdi, [rdi+8]
0x180008ea8  test    rdi, rdi
0x180008eab  jnz     loc_180008D55
0x180008eb1  jmp     short loc_180008EE5
0x180008eb3  mov     ecx, 10h; cb
0x180008eb8  call    cs:__imp_CoTaskMemAlloc
0x180008ebe  mov     [r12], rax
0x180008ec2  test    rax, rax
0x180008ec5  jz      short loc_180008ED0
0x180008ec7  movups  xmm0, xmmword ptr [rsp+1B0h+pclsid.Data1]
0x180008ecc  movdqu  xmmword ptr [rax], xmm0
0x180008ed0  mov     rcx, [rsp+1B0h+lpWideCharStr]; Block
0x180008ed5  lea     rax, [rsp+1B0h+var_158]
0x180008eda  cmp     rcx, rax
0x180008edd  jz      short loc_180008EE5
0x180008edf  call    cs:__imp_free
0x180008ee5  mov     rcx, r14; pv
0x180008ee8  call    cs:__imp_CoTaskMemFree
0x180008eee  mov     rcx, [rbp+0B0h+var_50]
0x180008ef2  xor     rcx, rsp; StackCookie
0x180008ef5  call    __security_check_cookie
0x180008efa  add     rsp, 178h
0x180008f01  pop     r15
0x180008f03  pop     r14
0x180008f05  pop     r13
0x180008f07  pop     r12
0x180008f09  pop     rdi
0x180008f0a  pop     rsi
0x180008f0b  pop     rbx
0x180008f0c  pop     rbp
0x180008f0d  retn
0x180008f0e  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
```
