# CUtils::CreateNetworkServiceSid(void * *)

- ea: `0x180082f50`
- end: `0x180083003`
- name: `?CreateNetworkServiceSid@CUtils@@SAJPEAPEAX@Z`
- size: `179`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002f7c0`

## callees

- `0x1800077a0`
- `0x180082f50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082fbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082fbc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180082f6b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180082f6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082fde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180082fde`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180082fac`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180082fac`

## string_xrefs

- `0x180082f8e`: `new pLocalNetworkServiceSid failed: 0x%x in %s`
- `0x180082f84`: `CUtils::CreateNetworkServiceSid`

## pseudocode

```c
__int64 __fastcall CUtils::CreateNetworkServiceSid(void **a1)
{
  HLOCAL v1; // rax
  void *v2; // rdi
  signed int v3; // ebx
  signed int LastError; // eax
  DWORD cbSid; // [rsp+30h] [rbp+8h] BYREF
  int v7; // [rsp+34h] [rbp+Ch]

  v7 = HIDWORD(a1);
  cbSid = 68;
  v1 = LocalAlloc(0x40u, 0x44u);
  v2 = v1;
  if ( v1 )
  {
    if ( CreateWellKnownSid(WinNetworkServiceSid, 0, v1, &cbSid) )
    {
      CUtils::pNetworkServiceSid = v2;
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 < 0 )
        LocalFree(v2);
    }
  }
  else
  {
    v3 = -2147024882;
    _DbgPrintMessage(
      8,
      "new pLocalNetworkServiceSid failed: 0x%x in %s",
      -2147024882,
      "CUtils::CreateNetworkServiceSid");
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180082f50  mov     [rsp+arg_8], rbx
0x180082f55  mov     qword ptr [rsp+cbSid], rcx
0x180082f5a  push    rdi
0x180082f5b  sub     rsp, 20h
0x180082f5f  mov     edx, 44h ; 'D'; uBytes
0x180082f64  mov     [rsp+28h+cbSid], edx
0x180082f68  lea     ecx, [rdx-4]; uFlags
0x180082f6b  call    cs:__imp_LocalAlloc
0x180082f72  nop     dword ptr [rax+rax+00h]
0x180082f77  mov     rdi, rax
0x180082f7a  test    rax, rax
0x180082f7d  jnz     short loc_180082F9F
0x180082f7f  mov     ebx, 8007000Eh
0x180082f84  lea     r9, aCutilsCreatene_0; "CUtils::CreateNetworkServiceSid"
0x180082f8b  mov     r8d, ebx
0x180082f8e  lea     rdx, aNewPlocalnetwo; "new pLocalNetworkServiceSid failed: 0x%"...
0x180082f95  lea     ecx, [rax+8]; int
0x180082f98  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180082f9d  jmp     short loc_180082FF5
0x180082f9f  xor     edx, edx; DomainSid
0x180082fa1  lea     r9, [rsp+28h+cbSid]; cbSid
0x180082fa6  mov     r8, rdi; pSid
0x180082fa9  lea     ecx, [rdx+18h]; WellKnownSidType
0x180082fac  call    cs:__imp_CreateWellKnownSid
0x180082fb3  nop     dword ptr [rax+rax+00h]
0x180082fb8  test    eax, eax
0x180082fba  jnz     short loc_180082FEC
0x180082fbc  call    cs:__imp_GetLastError
0x180082fc3  nop     dword ptr [rax+rax+00h]
0x180082fc8  mov     ebx, eax
0x180082fca  test    eax, eax
0x180082fcc  jle     short loc_180082FD7
0x180082fce  movzx   ebx, ax
0x180082fd1  or      ebx, 80070000h
0x180082fd7  test    ebx, ebx
0x180082fd9  jns     short loc_180082FF5
0x180082fdb  mov     rcx, rdi; hMem
0x180082fde  call    cs:__imp_LocalFree
0x180082fe5  nop     dword ptr [rax+rax+00h]
0x180082fea  jmp     short loc_180082FF5
0x180082fec  mov     cs:?pNetworkServiceSid@CUtils@@0PEAXEA, rdi; void * CUtils::pNetworkServiceSid
0x180082ff3  xor     ebx, ebx
0x180082ff5  mov     eax, ebx
0x180082ff7  mov     rbx, [rsp+28h+arg_8]
0x180082ffc  add     rsp, 20h
0x180083000  pop     rdi
0x180083001  retn
```
