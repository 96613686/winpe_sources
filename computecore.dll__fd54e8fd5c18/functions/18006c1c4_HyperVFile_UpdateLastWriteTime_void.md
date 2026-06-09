# HyperVFile::UpdateLastWriteTime(void)

- ea: `0x18006c1c4`
- end: `0x18006c28e`
- name: `?UpdateLastWriteTime@HyperVFile@@IEAAXXZ`
- size: `202`
- prototype: `void __fastcall(HyperVFile *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800655f0`

## callees

- `0x1800067c0`
- `0x18006c1c4`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006c22d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006c22d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18006c20a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18006c23d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18006c20a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18006c23d`

## pseudocode

```c
void __fastcall HyperVFile::UpdateLastWriteTime(HyperVFile *this)
{
  FILETIME *v2; // rbx
  FILETIME v3; // rax
  FILETIME FileTime1; // [rsp+20h] [rbp-28h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+28h] [rbp-20h] BYREF

  (*(void (__fastcall **)(_QWORD, FILETIME *))(**((_QWORD **)this + 75) + 168LL))(*((_QWORD *)this + 75), &FileTime1);
  v2 = (FILETIME *)((char *)this + 776);
  if ( CompareFileTime(&FileTime1, (const FILETIME *)this + 97) <= 0 )
  {
    v3 = (FILETIME)(*(_QWORD *)v2 + 1LL);
    SystemTimeAsFileTime = 0;
    FileTime1 = v3;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( CompareFileTime(&FileTime1, &SystemTimeAsFileTime) < 0 )
      FileTime1 = SystemTimeAsFileTime;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 75) + 176LL))(*((_QWORD *)this + 75));
  }
  *v2 = FileTime1;
}

```

## disassembly

```asm
0x18006c1c4  mov     [rsp+arg_8], rbx
0x18006c1c9  push    rdi
0x18006c1ca  sub     rsp, 40h
0x18006c1ce  mov     rax, cs:__security_cookie
0x18006c1d5  xor     rax, rsp
0x18006c1d8  mov     [rsp+48h+var_18], rax
0x18006c1dd  mov     rdi, rcx
0x18006c1e0  lea     rdx, [rsp+48h+FileTime1]
0x18006c1e5  mov     rcx, [rcx+258h]
0x18006c1ec  mov     rax, [rcx]
0x18006c1ef  mov     rax, [rax+0A8h]
0x18006c1f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c1fb  lea     rbx, [rdi+308h]
0x18006c202  mov     rdx, rbx; lpFileTime2
0x18006c205  lea     rcx, [rsp+48h+FileTime1]; lpFileTime1
0x18006c20a  call    cs:__imp_CompareFileTime
0x18006c210  test    eax, eax
0x18006c212  jg      short loc_18006C26E
0x18006c214  mov     rax, [rbx]
0x18006c217  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006c21c  inc     rax
0x18006c21f  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18006c228  mov     qword ptr [rsp+48h+FileTime1.dwLowDateTime], rax
0x18006c22d  call    cs:__imp_GetSystemTimeAsFileTime
0x18006c233  lea     rdx, [rsp+48h+SystemTimeAsFileTime]; lpFileTime2
0x18006c238  lea     rcx, [rsp+48h+FileTime1]; lpFileTime1
0x18006c23d  call    cs:__imp_CompareFileTime
0x18006c243  test    eax, eax
0x18006c245  jns     short loc_18006C253
0x18006c247  mov     rdx, qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime]
0x18006c24c  mov     qword ptr [rsp+48h+FileTime1.dwLowDateTime], rdx
0x18006c251  jmp     short loc_18006C258
0x18006c253  mov     rdx, qword ptr [rsp+48h+FileTime1.dwLowDateTime]
0x18006c258  mov     rcx, [rdi+258h]
0x18006c25f  mov     rax, [rcx]
0x18006c262  mov     rax, [rax+0B0h]
0x18006c269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c26e  mov     rax, qword ptr [rsp+48h+FileTime1.dwLowDateTime]
0x18006c273  mov     [rbx], rax
0x18006c276  mov     rcx, [rsp+48h+var_18]
0x18006c27b  xor     rcx, rsp; StackCookie
0x18006c27e  call    __security_check_cookie
0x18006c283  mov     rbx, [rsp+48h+arg_8]
0x18006c288  add     rsp, 40h
0x18006c28c  pop     rdi
0x18006c28d  retn
```
