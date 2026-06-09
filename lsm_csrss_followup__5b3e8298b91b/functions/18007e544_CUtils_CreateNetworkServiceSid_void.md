# CUtils::CreateNetworkServiceSid(void * *)

- ea: `0x18007e544`
- end: `0x18007e5de`
- name: `?CreateNetworkServiceSid@CUtils@@SAJPEAPEAX@Z`
- size: `154`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002d804`

## callees

- `0x1800074c0`
- `0x18007e544`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e5a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e5a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007e55f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007e55f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e5c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e5c0`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18007e59a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18007e59a`

## string_xrefs

- `0x18007e572`: `CUtils::CreateNetworkServiceSid`
- `0x18007e57c`: `new pLocalNetworkServiceSid failed: 0x%x in %s`

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
0x18007e544  mov     [rsp+arg_8], rbx
0x18007e549  mov     qword ptr [rsp+cbSid], rcx
0x18007e54e  push    rdi
0x18007e54f  sub     rsp, 20h
0x18007e553  mov     edx, 44h ; 'D'; uBytes
0x18007e558  mov     [rsp+28h+cbSid], edx
0x18007e55c  lea     ecx, [rdx-4]; uFlags
0x18007e55f  call    cs:__imp_LocalAlloc
0x18007e565  mov     rdi, rax
0x18007e568  test    rax, rax
0x18007e56b  jnz     short loc_18007E58D
0x18007e56d  mov     ebx, 8007000Eh
0x18007e572  lea     r9, aCutilsCreatene_0; "CUtils::CreateNetworkServiceSid"
0x18007e579  mov     r8d, ebx
0x18007e57c  lea     rdx, aNewPlocalnetwo; "new pLocalNetworkServiceSid failed: 0x%"...
0x18007e583  lea     ecx, [rax+8]; int
0x18007e586  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007e58b  jmp     short loc_18007E5D1
0x18007e58d  xor     edx, edx; DomainSid
0x18007e58f  lea     r9, [rsp+28h+cbSid]; cbSid
0x18007e594  mov     r8, rdi; pSid
0x18007e597  lea     ecx, [rdx+18h]; WellKnownSidType
0x18007e59a  call    cs:__imp_CreateWellKnownSid
0x18007e5a0  test    eax, eax
0x18007e5a2  jnz     short loc_18007E5C8
0x18007e5a4  call    cs:__imp_GetLastError
0x18007e5aa  mov     ebx, eax
0x18007e5ac  test    eax, eax
0x18007e5ae  jle     short loc_18007E5B9
0x18007e5b0  movzx   ebx, ax
0x18007e5b3  or      ebx, 80070000h
0x18007e5b9  test    ebx, ebx
0x18007e5bb  jns     short loc_18007E5D1
0x18007e5bd  mov     rcx, rdi; hMem
0x18007e5c0  call    cs:__imp_LocalFree
0x18007e5c6  jmp     short loc_18007E5D1
0x18007e5c8  mov     cs:?pNetworkServiceSid@CUtils@@0PEAXEA, rdi; void * CUtils::pNetworkServiceSid
0x18007e5cf  xor     ebx, ebx
0x18007e5d1  mov     eax, ebx
0x18007e5d3  mov     rbx, [rsp+28h+arg_8]
0x18007e5d8  add     rsp, 20h
0x18007e5dc  pop     rdi
0x18007e5dd  retn
```
