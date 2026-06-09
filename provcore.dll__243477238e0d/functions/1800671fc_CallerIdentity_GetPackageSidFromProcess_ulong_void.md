# CallerIdentity::GetPackageSidFromProcess(ulong,void * *)

- ea: `0x1800671fc`
- end: `0x18006726a`
- name: `?GetPackageSidFromProcess@CallerIdentity@@YAJKPEAPEAX@Z`
- size: `110`
- prototype: `HRESULT __fastcall(unsigned int dwPid, void **ppPackageSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180067020`

## callees

- `0x180066b68`
- `0x1800671fc`
- `0x180067270`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067252`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067252`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006721f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006721f`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetPackageSidFromProcess(DWORD dwPid, void **ppPackageSid)
{
  char *v3; // rbx
  int PackageSidFromProcessHandle; // edi

  *ppPackageSid = 0;
  v3 = (char *)OpenProcess(0x1000u, 0, dwPid);
  if ( v3 || (PackageSidFromProcessHandle = ResultFromKnownLastError(), PackageSidFromProcessHandle >= 0) )
  {
    PackageSidFromProcessHandle = CallerIdentity::GetPackageSidFromProcessHandle(v3, ppPackageSid);
    if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v3);
  }
  return (unsigned int)PackageSidFromProcessHandle;
}

```

## disassembly

```asm
0x1800671fc  mov     [rsp+arg_0], rbx
0x180067201  mov     [rsp+arg_8], rsi
0x180067206  push    rdi
0x180067207  sub     rsp, 20h
0x18006720b  mov     rsi, ppPackageSid
0x18006720e  mov     qword ptr [ppPackageSid], 0
0x180067215  mov     r8d, dwPid; dwProcessId
0x180067218  xor     edx, edx; bInheritHandle
0x18006721a  mov     dwPid, 1000h; dwDesiredAccess
0x18006721f  call    cs:__imp_OpenProcess
0x180067225  mov     rbx, rax
0x180067228  test    rax, rax
0x18006722b  jnz     short loc_180067238
0x18006722d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180067232  mov     edi, eax
0x180067234  test    eax, eax
0x180067236  js      short loc_180067258
0x180067238  mov     ppPackageSid, rsi; ppPackageSid
0x18006723b  mov     rcx, rbx; hProcess
0x18006723e  call    ?GetPackageSidFromProcessHandle@CallerIdentity@@YAJPEAXPEAPEAX@Z; CallerIdentity::GetPackageSidFromProcessHandle(void *,void * *)
0x180067243  mov     edi, eax
0x180067245  lea     rax, [rbx-1]
0x180067249  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006724d  ja      short loc_180067258
0x18006724f  mov     rcx, rbx; hObject
0x180067252  call    cs:__imp_CloseHandle
0x180067258  mov     rbx, [rsp+28h+arg_0]
0x18006725d  mov     eax, edi
0x18006725f  mov     rsi, [rsp+28h+arg_8]
0x180067264  add     rsp, 20h
0x180067268  pop     rdi
0x180067269  retn
```
