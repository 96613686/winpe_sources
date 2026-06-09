# __crt_cached_ptd_host::get_raw_ptd(void)

- ea: `0x180014b58`
- end: `0x180014bc2`
- name: `?get_raw_ptd@__crt_cached_ptd_host@@QEAAPEAU__acrt_ptd@@XZ`
- size: `106`
- prototype: `struct __acrt_ptd *__fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180014d98`
- `0x18001bc50`
- `0x18001c098`

## callees

- `0x180014b58`
- `0x1800150f8`
- `0x1800154e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014ba3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014ba3`

## pseudocode

```c
struct __acrt_ptd *__fastcall __crt_cached_ptd_host::get_raw_ptd(__crt_cached_ptd_host *this)
{
  DWORD LastError; // eax
  bool v3; // zf
  __int64 v4; // rdx
  __int64 v5; // rax
  DWORD v6; // ecx
  __int64 v7; // rbx
  DWORD dwErrCode; // [rsp+30h] [rbp+8h] BYREF

  if ( !*(_QWORD *)this )
  {
    LastError = GetLastError();
    v3 = *((_BYTE *)this + 16) == 0;
    dwErrCode = LastError;
    if ( v3 )
    {
      *((_QWORD *)this + 1) = 0;
      v4 = 0;
      *((_BYTE *)this + 16) = 1;
    }
    else
    {
      v4 = *((_QWORD *)this + 1);
    }
    v5 = _acrt_getptd_noexit_explicit(&dwErrCode, v4);
    v6 = dwErrCode;
    v7 = v5;
    *(_QWORD *)this = v5;
    SetLastError(v6);
    if ( !v7 )
      abort();
  }
  return *(struct __acrt_ptd **)this;
}

```

## disassembly

```asm
0x180014b58  mov     [rsp+arg_8], rbx
0x180014b5d  push    rdi
0x180014b5e  sub     rsp, 20h
0x180014b62  cmp     qword ptr [rcx], 0
0x180014b66  mov     rdi, rcx
0x180014b69  jnz     short loc_180014BAE
0x180014b6b  call    cs:__imp_GetLastError
0x180014b71  cmp     byte ptr [rdi+10h], 0
0x180014b75  mov     [rsp+28h+dwErrCode], eax
0x180014b79  jnz     short loc_180014B8B
0x180014b7b  mov     qword ptr [rdi+8], 0
0x180014b83  xor     edx, edx
0x180014b85  mov     byte ptr [rdi+10h], 1
0x180014b89  jmp     short loc_180014B8F
0x180014b8b  mov     rdx, [rdi+8]
0x180014b8f  lea     rcx, [rsp+28h+dwErrCode]
0x180014b94  call    __acrt_getptd_noexit_explicit
0x180014b99  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x180014b9d  mov     rbx, rax
0x180014ba0  mov     [rdi], rax
0x180014ba3  call    cs:__imp_SetLastError
0x180014ba9  test    rbx, rbx
0x180014bac  jz      short loc_180014BBC
0x180014bae  mov     rax, [rdi]
0x180014bb1  mov     rbx, [rsp+28h+arg_8]
0x180014bb6  add     rsp, 20h
0x180014bba  pop     rdi
0x180014bbb  retn
0x180014bbc  call    abort
```
