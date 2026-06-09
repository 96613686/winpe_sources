# thread_start_unsigned_int_(__cdecl_)(void__)_1_

- ea: `0x180344a10`
- end: `0x180344a75`
- name: `thread_start_unsigned_int_(__cdecl_)(void__)_1_`
- size: `101`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180344a10`
- `0x180344c20`
- `0x1803536d4`
- `0x180354c48`
- `0x1803597e8`
- `0x180359b64`
- `0x180375c80`

## import_xrefs

- `KERNEL32!ExitThread` at `0x180344a26`
- `KERNEL32!ExitThread` at `0x180344a26`
- `KERNEL32!GetLastError` at `0x180344a1e`
- `KERNEL32!GetLastError` at `0x180344a1e`

## pseudocode

```c
void __fastcall __noreturn thread_start_unsigned_int____cdecl___void____1_(_BYTE *Parameter)
{
  DWORD LastError; // eax
  unsigned int v3; // eax

  if ( !Parameter )
  {
    LastError = GetLastError();
    ExitThread(LastError);
  }
  *(_QWORD *)(_acrt_getptd() + 960) = Parameter;
  if ( (unsigned int)_acrt_get_begin_thread_init_policy() == 2 )
    Parameter[32] = (unsigned int)_acrt_RoInitialize(1) == 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD))Parameter)(*((_QWORD *)Parameter + 1));
  endthreadex(v3);
}

```

## disassembly

```asm
0x180344a10  push    rbx
0x180344a12  sub     rsp, 20h
0x180344a16  mov     rbx, rcx
0x180344a19  test    rcx, rcx
0x180344a1c  jnz     short loc_180344A2D
0x180344a1e  call    cs:__imp_GetLastError
0x180344a24  mov     ecx, eax; dwExitCode
0x180344a26  call    cs:__imp_ExitThread
0x180344a2d  call    __acrt_getptd
0x180344a32  mov     [rax+3C0h], rbx
0x180344a39  call    __acrt_get_begin_thread_init_policy
0x180344a3e  cmp     eax, 2
0x180344a41  jnz     short loc_180344A53
0x180344a43  lea     ecx, [rax-1]
0x180344a46  call    __acrt_RoInitialize
0x180344a4b  test    eax, eax
0x180344a4d  setz    al
0x180344a50  mov     [rbx+20h], al
0x180344a53  mov     rcx, [rbx+8]
0x180344a57  mov     rax, [rbx]
0x180344a5a  call    _guard_dispatch_icall
0x180344a5f  mov     ecx, eax; ReturnCode
0x180344a61  call    _endthreadex
0x180344a67  mov     ecx, eax; Code
0x180344a69  call    _exit
0x180344a6f  add     rsp, 20h
0x180344a73  pop     rbx
0x180344a74  retn
```
