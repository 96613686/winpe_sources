# Microsoft::IoT::Utility::MTAThread::Start(void)

- ea: `0x18000dce4`
- end: `0x18000dd7a`
- name: `?Start@MTAThread@Utility@IoT@Microsoft@@QEAAJXZ`
- size: `150`
- prototype: `__int64 __fastcall(Microsoft::IoT::Utility::MTAThread *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d82c`
- `0x18000da64`

## callees

- `0x18000430c`
- `0x180004580`
- `0x180006af4`
- `0x18000dce4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000dd14`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000dd14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dd38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dd38`

## string_xrefs

- `0x18000dd56`: `onecoreuap\shell\embedded\shell\iotshellhostext\iotshellcbt\mtathreadpool.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::IoT::Utility::MTAThread::Start(Microsoft::IoT::Utility::MTAThread *this)
{
  HANDLE Thread; // rax
  const char *v3; // r9
  char *v4; // rsi
  HANDLE v5; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v8; // [rsp+40h] [rbp+8h] BYREF

  Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)Microsoft::IoT::Utility::MTAThread::_WorkerThread, this, 0, 0);
  v4 = (char *)*((_QWORD *)this + 3);
  v5 = Thread;
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v8);
    CloseHandle(v4);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v8);
  }
  *((_QWORD *)this + 3) = v5;
  if ( !v5 )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\mtathreadpool.cpp",
      v3);
  return 0;
}

```

## disassembly

```asm
0x18000dce4  mov     rax, rsp
0x18000dce7  mov     [rax+10h], rbx
0x18000dceb  mov     [rax+18h], rsi
0x18000dcef  push    rdi
0x18000dcf0  sub     rsp, 30h
0x18000dcf4  mov     rdi, rcx
0x18000dcf7  mov     qword ptr [rax-10h], 0
0x18000dcff  mov     r9, rcx; lpParameter
0x18000dd02  mov     dword ptr [rax-18h], 0
0x18000dd09  xor     ecx, ecx; lpThreadAttributes
0x18000dd0b  lea     r8, ?_WorkerThread@MTAThread@Utility@IoT@Microsoft@@CAKPEAX@Z; lpStartAddress
0x18000dd12  xor     edx, edx; dwStackSize
0x18000dd14  call    cs:__imp_CreateThread
0x18000dd1a  mov     rsi, [rdi+18h]
0x18000dd1e  mov     rbx, rax
0x18000dd21  lea     rdx, [rsi-1]
0x18000dd25  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000dd29  ja      short loc_18000DD48
0x18000dd2b  lea     rcx, [rsp+38h+arg_0]; this
0x18000dd30  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000dd35  mov     rcx, rsi; hObject
0x18000dd38  call    cs:__imp_CloseHandle
0x18000dd3e  lea     rcx, [rsp+38h+arg_0]; this
0x18000dd43  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000dd48  mov     [rdi+18h], rbx
0x18000dd4c  test    rbx, rbx
0x18000dd4f  jnz     short loc_18000DD68
0x18000dd51  mov     rcx, [rsp+38h]; this
0x18000dd56  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x18000dd5d  mov     edx, 92h; void *
0x18000dd62  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000dd68  mov     rbx, [rsp+38h+arg_8]
0x18000dd6d  xor     eax, eax
0x18000dd6f  mov     rsi, [rsp+38h+arg_10]
0x18000dd74  add     rsp, 30h
0x18000dd78  pop     rdi
0x18000dd79  retn
```
