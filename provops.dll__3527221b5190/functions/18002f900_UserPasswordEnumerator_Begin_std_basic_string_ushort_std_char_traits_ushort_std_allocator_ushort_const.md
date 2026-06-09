# UserPasswordEnumerator::Begin(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002f900`
- end: `0x18002f997`
- name: `?Begin@UserPasswordEnumerator@@UEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001b388`
- `0x180020fe0`
- `0x18002f900`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f938`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f938`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f94b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f94b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f943`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f943`
- `ext-ms-win-provisioning-platform-l1-1-0!GetPackagePassword` at `0x18002f96a`
- `ext-ms-win-provisioning-platform-l1-1-0!GetPackagePassword` at `0x18002f96a`

## pseudocode

```c
__int64 __fastcall UserPasswordEnumerator::Begin(_QWORD *a1, void **a2)
{
  _QWORD *v2; // rdi
  _QWORD *v4; // rsi
  void *v5; // rbp
  DWORD LastError; // ebx
  __int64 result; // rax
  int v8; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = a1 + 1;
  if ( a1 + 1 != a2 )
    std::wstring::assign((void **)a1 + 1, a2, 0, 0xFFFFFFFFFFFFFFFFuLL);
  v4 = a1 + 5;
  a1[6] = 0;
  v5 = (void *)a1[5];
  if ( v5 )
  {
    LastError = GetLastError();
    CoTaskMemFree(v5);
    SetLastError(LastError);
  }
  *v4 = 0;
  if ( v2[3] >= 8u )
    v2 = (_QWORD *)*v2;
  result = GetPackagePassword(v2, 0, v4);
  if ( (int)result < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\passwordenumerator.cpp",
      (const char *)(unsigned int)result,
      v8);
  return result;
}

```

## disassembly

```asm
0x18002f900  push    rbx
0x18002f902  push    rbp
0x18002f903  push    rsi
0x18002f904  push    rdi
0x18002f905  sub     rsp, 28h
0x18002f909  lea     rdi, [rcx+8]
0x18002f90d  mov     rbx, rcx
0x18002f910  cmp     rdi, rdx
0x18002f913  jz      short loc_18002F924
0x18002f915  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002f919  xor     r8d, r8d
0x18002f91c  mov     rcx, rdi; void *
0x18002f91f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002f924  lea     rsi, [rbx+28h]
0x18002f928  mov     qword ptr [rbx+30h], 0
0x18002f930  mov     rbp, [rsi]
0x18002f933  test    rbp, rbp
0x18002f936  jz      short loc_18002F951
0x18002f938  call    cs:__imp_GetLastError
0x18002f93e  mov     rcx, rbp; pv
0x18002f941  mov     ebx, eax
0x18002f943  call    cs:__imp_CoTaskMemFree
0x18002f949  mov     ecx, ebx; dwErrCode
0x18002f94b  call    cs:__imp_SetLastError
0x18002f951  mov     qword ptr [rsi], 0
0x18002f958  cmp     qword ptr [rdi+18h], 8
0x18002f95d  jb      short loc_18002F962
0x18002f95f  mov     rdi, [rdi]
0x18002f962  mov     r8, rsi
0x18002f965  xor     edx, edx
0x18002f967  mov     rcx, rdi
0x18002f96a  call    cs:__imp_GetPackagePassword
0x18002f970  test    eax, eax
0x18002f972  js      short loc_18002F97D
0x18002f974  add     rsp, 28h
0x18002f978  pop     rdi
0x18002f979  pop     rsi
0x18002f97a  pop     rbp
0x18002f97b  pop     rbx
0x18002f97c  retn
0x18002f97d  mov     rcx, [rsp+48h]; this
0x18002f982  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\lib\\passworde"...
0x18002f989  mov     r9d, eax; char *
0x18002f98c  mov     edx, 2Fh ; '/'; void *
0x18002f991  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
