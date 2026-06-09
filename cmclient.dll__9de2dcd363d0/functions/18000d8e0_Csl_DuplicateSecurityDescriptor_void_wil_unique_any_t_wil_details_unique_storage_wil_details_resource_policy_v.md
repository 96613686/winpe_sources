# Csl::DuplicateSecurityDescriptor(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)

- ea: `0x18000d8e0`
- end: `0x18000d9e2`
- name: `?DuplicateSecurityDescriptor@Csl@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `258`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007610`

## callees

- `0x1800066e4`
- `0x180006708`
- `0x18000d8e0`
- `0x18000ee00`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x18000d8f8`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18000d8f8`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18000d991`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x18000d991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d968`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d97b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d97b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d909`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d909`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d973`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d9b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d9c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d973`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d9b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d9c7`

## string_xrefs

- `0x18000d91f`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18000d9a0`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`

## pseudocode

```c
__int64 __fastcall Csl::DuplicateSecurityDescriptor(void *Src, int *a2)
{
  HLOCAL v4; // rax
  void *v5; // rdi
  unsigned int v6; // ebx
  void *v8; // rbp
  DWORD LastError; // ebx
  NTSTATUS v10; // eax
  int v11; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  size_t Size; // [rsp+60h] [rbp+18h] BYREF

  LODWORD(Size) = RtlLengthSecurityDescriptor(Src);
  v4 = LocalAlloc(0x40u, (unsigned int)Size);
  v5 = v4;
  if ( !v4 )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31B,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
      (const char *)0x8007000ELL,
      v11);
    return v6;
  }
  if ( *((__int16 *)Src + 1) >= 0 )
  {
    v10 = RtlAbsoluteToSelfRelativeSD(Src, v4, (PULONG)&Size);
    if ( v10 < 0 )
    {
      v6 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x32A,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
             (const char *)(unsigned int)v10,
             v11);
      LocalFree(v5);
      return v6;
    }
  }
  else
  {
    memcpy_0(v4, Src, (unsigned int)Size);
  }
  if ( a2 == &v11 )
  {
    LocalFree(v5);
  }
  else
  {
    v8 = *(void **)a2;
    if ( *(_QWORD *)a2 )
    {
      LastError = GetLastError();
      LocalFree(v8);
      SetLastError(LastError);
    }
    *(_QWORD *)a2 = v5;
  }
  return 0;
}

```

## disassembly

```asm
0x18000d8e0  mov     [rsp+arg_0], rbx
0x18000d8e5  mov     [rsp+arg_8], rbp
0x18000d8ea  push    rsi
0x18000d8eb  push    rdi
0x18000d8ec  push    r14
0x18000d8ee  sub     rsp, 30h
0x18000d8f2  mov     rsi, rdx
0x18000d8f5  mov     rbx, rcx
0x18000d8f8  call    cs:__imp_RtlLengthSecurityDescriptor
0x18000d8fe  mov     edx, eax; uBytes
0x18000d900  mov     ecx, 40h ; '@'; uFlags
0x18000d905  mov     dword ptr [rsp+48h+Size], edx
0x18000d909  call    cs:__imp_LocalAlloc
0x18000d90f  xor     r14d, r14d
0x18000d912  mov     rdi, rax
0x18000d915  test    rax, rax
0x18000d918  jnz     short loc_18000D93F
0x18000d91a  mov     rcx, [rsp+48h]; this
0x18000d91f  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000d926  mov     ebx, 8007000Eh
0x18000d92b  mov     edx, 31Bh; void *
0x18000d930  mov     r9d, ebx; char *
0x18000d933  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d938  mov     eax, ebx
0x18000d93a  jmp     loc_18000D9CF
0x18000d93f  cmp     [rbx+2], r14w
0x18000d944  jge     short loc_18000D986
0x18000d946  mov     r8d, dword ptr [rsp+48h+Size]; Size
0x18000d94b  mov     rdx, rbx; Src
0x18000d94e  mov     rcx, rdi; void *
0x18000d951  call    memcpy_0
0x18000d956  lea     rax, [rsp+48h+var_28]
0x18000d95b  cmp     rsi, rax
0x18000d95e  jz      short loc_18000D9C4
0x18000d960  mov     rbp, [rsi]
0x18000d963  test    rbp, rbp
0x18000d966  jz      short loc_18000D981
0x18000d968  call    cs:__imp_GetLastError
0x18000d96e  mov     rcx, rbp; hMem
0x18000d971  mov     ebx, eax
0x18000d973  call    cs:__imp_LocalFree
0x18000d979  mov     ecx, ebx; dwErrCode
0x18000d97b  call    cs:__imp_SetLastError
0x18000d981  mov     [rsi], rdi
0x18000d984  jmp     short loc_18000D9CD
0x18000d986  lea     r8, [rsp+48h+Size]; BufferLength
0x18000d98b  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x18000d98e  mov     rcx, rbx; AbsoluteSecurityDescriptor
0x18000d991  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x18000d997  test    eax, eax
0x18000d999  jns     short loc_18000D956
0x18000d99b  mov     rcx, [rsp+48h]; this
0x18000d9a0  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000d9a7  mov     r9d, eax; char *
0x18000d9aa  mov     edx, 32Ah; void *
0x18000d9af  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000d9b4  mov     rcx, rdi; hMem
0x18000d9b7  mov     ebx, eax
0x18000d9b9  call    cs:__imp_LocalFree
0x18000d9bf  jmp     loc_18000D938
0x18000d9c4  mov     rcx, rdi; hMem
0x18000d9c7  call    cs:__imp_LocalFree
0x18000d9cd  xor     eax, eax
0x18000d9cf  mov     rbx, [rsp+48h+arg_0]
0x18000d9d4  mov     rbp, [rsp+48h+arg_8]
0x18000d9d9  add     rsp, 30h
0x18000d9dd  pop     r14
0x18000d9df  pop     rdi
0x18000d9e0  pop     rsi
0x18000d9e1  retn
```
