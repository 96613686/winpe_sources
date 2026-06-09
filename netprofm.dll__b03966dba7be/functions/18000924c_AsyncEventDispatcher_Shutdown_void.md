# AsyncEventDispatcher::Shutdown(void)

- ea: `0x18000924c`
- end: `0x180009328`
- name: `?Shutdown@AsyncEventDispatcher@@QEAAXXZ`
- size: `220`
- prototype: `void __fastcall(AsyncEventDispatcher *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800091e0`
- `0x180028bb0`
- `0x180028c24`

## callees

- `0x18000924c`
- `0x1800120d0`
- `0x180033a1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000928b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009319`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000928b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009319`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000926f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000926f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800092d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800092d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092ec`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleObjects` at `0x1800092c3`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleObjects` at `0x1800092c3`

## pseudocode

```c
void __fastcall AsyncEventDispatcher::Shutdown(AsyncEventDispatcher *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  HANDLE *v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // rcx
  struct _TP_WORK *v6; // rcx
  int v7; // [rsp+30h] [rbp-18h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( *((_BYTE *)this + 88) )
  {
    if ( v1 )
      LeaveCriticalSection(v1);
  }
  else
  {
    *((_BYTE *)this + 88) = 1;
    if ( v1 )
      LeaveCriticalSection(v1);
    v3 = (HANDLE *)((char *)this + 16);
    if ( *((_QWORD *)this + 2) )
    {
      if ( *((_QWORD *)this + 1) )
      {
        v7 = 0;
        if ( (int)CoWaitForMultipleObjects(1, 0xFFFFFFFFLL, 1, (char *)this + 16, &v7) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
      }
    }
    v6 = (struct _TP_WORK *)*((_QWORD *)this + 1);
    if ( v6 )
    {
      CloseThreadpoolWork(v6);
      *((_QWORD *)this + 1) = 0;
    }
    if ( *v3 )
    {
      CloseHandle(*v3);
      *v3 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000924c  mov     [rsp+arg_8], rbx
0x180009251  push    rdi
0x180009252  sub     rsp, 40h
0x180009256  mov     rax, cs:__security_cookie
0x18000925d  xor     rax, rsp
0x180009260  mov     [rsp+48h+var_10], rax
0x180009265  lea     rdi, [rcx+18h]
0x180009269  mov     rbx, rcx
0x18000926c  mov     rcx, rdi; lpCriticalSection
0x18000926f  call    cs:__imp_EnterCriticalSection
0x180009275  cmp     byte ptr [rbx+58h], 0
0x180009279  jnz     loc_180009311
0x18000927f  mov     byte ptr [rbx+58h], 1
0x180009283  test    rdi, rdi
0x180009286  jz      short loc_180009291
0x180009288  mov     rcx, rdi; lpCriticalSection
0x18000928b  call    cs:__imp_LeaveCriticalSection
0x180009291  lea     rdi, [rbx+10h]
0x180009295  cmp     qword ptr [rdi], 0
0x180009299  jz      short loc_1800092CD
0x18000929b  cmp     qword ptr [rbx+8], 0
0x1800092a0  jz      short loc_1800092CD
0x1800092a2  mov     r8d, 1
0x1800092a8  mov     [rsp+48h+var_18], 0
0x1800092b0  lea     rax, [rsp+48h+var_18]
0x1800092b5  mov     ecx, r8d
0x1800092b8  mov     r9, rdi
0x1800092bb  mov     [rsp+48h+var_28], rax
0x1800092c0  or      edx, 0FFFFFFFFh
0x1800092c3  call    cs:__imp_CoWaitForMultipleObjects
0x1800092c9  test    eax, eax
0x1800092cb  js      short loc_180009321
0x1800092cd  mov     rcx, [rbx+8]; pwk
0x1800092d1  test    rcx, rcx
0x1800092d4  jz      short loc_1800092E4
0x1800092d6  call    cs:__imp_CloseThreadpoolWork
0x1800092dc  mov     qword ptr [rbx+8], 0
0x1800092e4  mov     rcx, [rdi]; hObject
0x1800092e7  test    rcx, rcx
0x1800092ea  jz      short loc_1800092F9
0x1800092ec  call    cs:__imp_CloseHandle
0x1800092f2  mov     qword ptr [rdi], 0
0x1800092f9  mov     rcx, [rsp+48h+var_10]
0x1800092fe  xor     rcx, rsp; StackCookie
0x180009301  call    __security_check_cookie
0x180009306  mov     rbx, [rsp+48h+arg_8]
0x18000930b  add     rsp, 40h
0x18000930f  pop     rdi
0x180009310  retn
0x180009311  test    rdi, rdi
0x180009314  jz      short loc_1800092F9
0x180009316  mov     rcx, rdi; lpCriticalSection
0x180009319  call    cs:__imp_LeaveCriticalSection
0x18000931f  jmp     short loc_1800092F9
0x180009321  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)")
0x180009326  jmp     short loc_1800092CD
```
