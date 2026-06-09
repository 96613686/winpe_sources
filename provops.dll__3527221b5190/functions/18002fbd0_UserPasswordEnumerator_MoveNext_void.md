# UserPasswordEnumerator::MoveNext(void)

- ea: `0x18002fbd0`
- end: `0x18002fc73`
- name: `?MoveNext@UserPasswordEnumerator@@UEAAXXZ`
- size: `163`
- prototype: `void __fastcall(UserPasswordEnumerator *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001b388`
- `0x18002fbd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fbf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fbf3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fc06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fc06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fbfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fbfe`
- `ext-ms-win-provisioning-platform-l1-1-0!GetPackagePassword` at `0x18002fc29`
- `ext-ms-win-provisioning-platform-l1-1-0!GetPackagePassword` at `0x18002fc29`

## pseudocode

```c
void __fastcall UserPasswordEnumerator::MoveNext(UserPasswordEnumerator *this)
{
  _QWORD *v2; // rsi
  void *v3; // rbp
  DWORD LastError; // ebx
  _QWORD *v5; // rcx
  int PackagePassword; // eax
  int v7; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( ++*((_QWORD *)this + 6) >= 5u )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\passwordenumerator.cpp",
      (const char *)0x80004004LL,
      v7);
  v2 = (_QWORD *)((char *)this + 40);
  v3 = (void *)*((_QWORD *)this + 5);
  if ( v3 )
  {
    LastError = GetLastError();
    CoTaskMemFree(v3);
    SetLastError(LastError);
  }
  v5 = (_QWORD *)((char *)this + 8);
  *v2 = 0;
  if ( *((_QWORD *)this + 4) >= 8u )
    v5 = (_QWORD *)*v5;
  PackagePassword = GetPackagePassword(v5, 1, v2);
  if ( PackagePassword < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\passwordenumerator.cpp",
      (const char *)(unsigned int)PackagePassword,
      v7);
}

```

## disassembly

```asm
0x18002fbd0  push    rbx
0x18002fbd2  push    rbp
0x18002fbd3  push    rsi
0x18002fbd4  push    rdi
0x18002fbd5  sub     rsp, 28h
0x18002fbd9  inc     qword ptr [rcx+30h]
0x18002fbdd  mov     rdi, rcx
0x18002fbe0  cmp     qword ptr [rcx+30h], 5
0x18002fbe5  jnb     short loc_18002FC56
0x18002fbe7  lea     rsi, [rcx+28h]
0x18002fbeb  mov     rbp, [rsi]
0x18002fbee  test    rbp, rbp
0x18002fbf1  jz      short loc_18002FC0C
0x18002fbf3  call    cs:__imp_GetLastError
0x18002fbf9  mov     rcx, rbp; pv
0x18002fbfc  mov     ebx, eax
0x18002fbfe  call    cs:__imp_CoTaskMemFree
0x18002fc04  mov     ecx, ebx; dwErrCode
0x18002fc06  call    cs:__imp_SetLastError
0x18002fc0c  lea     rcx, [rdi+8]
0x18002fc10  mov     qword ptr [rsi], 0
0x18002fc17  cmp     qword ptr [rcx+18h], 8
0x18002fc1c  jb      short loc_18002FC21
0x18002fc1e  mov     rcx, [rcx]
0x18002fc21  mov     r8, rsi
0x18002fc24  mov     edx, 1
0x18002fc29  call    cs:__imp_GetPackagePassword
0x18002fc2f  test    eax, eax
0x18002fc31  js      short loc_18002FC3C
0x18002fc33  add     rsp, 28h
0x18002fc37  pop     rdi
0x18002fc38  pop     rsi
0x18002fc39  pop     rbp
0x18002fc3a  pop     rbx
0x18002fc3b  retn
0x18002fc3c  mov     rcx, [rsp+48h]; this
0x18002fc41  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\lib\\passworde"...
0x18002fc48  mov     r9d, eax; char *
0x18002fc4b  mov     edx, 37h ; '7'; void *
0x18002fc50  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002fc56  mov     rcx, [rsp+48h]; this
0x18002fc5b  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\lib\\passworde"...
0x18002fc62  mov     r9d, 80004004h; char *
0x18002fc68  mov     edx, 36h ; '6'; void *
0x18002fc6d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
