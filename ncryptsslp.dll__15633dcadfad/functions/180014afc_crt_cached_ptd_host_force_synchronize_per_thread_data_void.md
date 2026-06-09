# __crt_cached_ptd_host::force_synchronize_per_thread_data(void)

- ea: `0x180014afc`
- end: `0x180014b50`
- name: `?force_synchronize_per_thread_data@__crt_cached_ptd_host@@AEAAPEAU__acrt_ptd@@XZ`
- size: `84`
- prototype: `struct __acrt_ptd *__fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018020`

## callees

- `0x180014afc`
- `0x1800154e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014b3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014b3c`

## pseudocode

```c
struct __acrt_ptd *__fastcall __crt_cached_ptd_host::force_synchronize_per_thread_data(__crt_cached_ptd_host *this)
{
  DWORD LastError; // eax
  __int64 v3; // rdx
  __int64 v4; // rax
  DWORD v5; // ecx
  __int64 v6; // rbx
  DWORD dwErrCode; // [rsp+30h] [rbp+8h] BYREF

  LastError = GetLastError();
  v3 = 0;
  dwErrCode = LastError;
  if ( *((_BYTE *)this + 16) )
  {
    v3 = *((_QWORD *)this + 1);
  }
  else
  {
    *((_QWORD *)this + 1) = 0;
    *((_BYTE *)this + 16) = 1;
  }
  v4 = _acrt_getptd_noexit_explicit(&dwErrCode, v3);
  v5 = dwErrCode;
  v6 = v4;
  *(_QWORD *)this = v4;
  SetLastError(v5);
  return (struct __acrt_ptd *)v6;
}

```

## disassembly

```asm
0x180014afc  mov     [rsp+arg_8], rbx
0x180014b01  push    rdi
0x180014b02  sub     rsp, 20h
0x180014b06  mov     rdi, rcx
0x180014b09  call    cs:__imp_GetLastError
0x180014b0f  xor     edx, edx
0x180014b11  mov     [rsp+28h+dwErrCode], eax
0x180014b15  cmp     [rdi+10h], dl
0x180014b18  jnz     short loc_180014B24
0x180014b1a  mov     [rdi+8], rdx
0x180014b1e  mov     byte ptr [rdi+10h], 1
0x180014b22  jmp     short loc_180014B28
0x180014b24  mov     rdx, [rdi+8]
0x180014b28  lea     rcx, [rsp+28h+dwErrCode]
0x180014b2d  call    __acrt_getptd_noexit_explicit
0x180014b32  mov     ecx, [rsp+28h+dwErrCode]; dwErrCode
0x180014b36  mov     rbx, rax
0x180014b39  mov     [rdi], rax
0x180014b3c  call    cs:__imp_SetLastError
0x180014b42  mov     rax, rbx
0x180014b45  mov     rbx, [rsp+28h+arg_8]
0x180014b4a  add     rsp, 20h
0x180014b4e  pop     rdi
0x180014b4f  retn
```
