# CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)

- ea: `0x180017430`
- end: `0x180017546`
- name: `?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ`
- size: `278`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `80`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d940`
- `0x18000da54`
- `0x18000dde0`
- `0x180012158`
- `0x180012604`
- `0x1800138c0`
- `0x180013940`
- `0x1800139dc`
- `0x180017fd0`
- `0x1800181c4`
- `0x180018350`
- `0x180018530`
- `0x180018780`
- `0x180018b40`
- `0x180019950`
- `0x18001aeb0`
- `0x18001b060`
- `0x18001b240`
- `0x18001b4c0`
- `0x18001b810`
- `0x18001b9e0`
- `0x18001bbb0`
- `0x18001be70`
- `0x18001c3ec`
- `0x18001c6bc`
- `0x18001c80c`
- `0x18001c8bc`
- `0x18001cbac`
- `0x18001ce80`
- `0x18001cfc0`
- `0x18001d340`
- `0x18001d5c0`
- `0x18001d770`
- `0x18001d8d0`
- `0x18001dfd0`
- `0x18001e1d0`
- `0x18001e380`
- `0x18001e4e0`
- `0x18001e5c0`
- `0x18001e8f0`
- `0x18001eb24`
- `0x18001eda0`
- `0x18001f038`
- `0x18001f1d0`
- `0x18001f5c0`
- `0x1800209a8`
- `0x180020fe0`
- `0x1800216f0`
- `0x180021d10`
- `0x180023310`

## callees

- `0x180017430`
- `0x18002f0ba`
- `0x18002f0e0`

## import_xrefs

- `ADVAPI32!TraceEvent` at `0x18001751a`
- `ADVAPI32!TraceEvent` at `0x18001751a`

## pseudocode

```c
signed int CMSMQTrace::MSMQTraceEvent(__int64 a1, int a2, ULONG a3, ...)
{
  signed int result; // eax
  char *v5; // rdx
  union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F v6; // xmm0
  va_list v7; // rcx
  int v8; // eax
  __int64 v9; // rax
  TRACEHANDLE v10; // rcx
  signed __int32 v11; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v12; // [rsp+28h] [rbp-D8h]
  _EVENT_TRACE_HEADER EventTrace; // [rsp+30h] [rbp-D0h] BYREF
  signed __int32 *v14; // [rsp+60h] [rbp-A0h]
  int v15; // [rsp+68h] [rbp-98h]
  char v16; // [rsp+70h] [rbp-90h] BYREF
  char v17; // [rsp+160h] [rbp+60h] BYREF
  va_list va; // [rsp+1B8h] [rbp+B8h] BYREF

  va_start(va, a3);
  if ( !*(_BYTE *)(a1 + 96) )
    return -2147023269;
  if ( !*(_DWORD *)a1 || (a2 & *(_DWORD *)a1) == 0 )
    return 0;
  v11 = _InterlockedIncrement(&dword_180043130);
  memset_0(&EventTrace, 0, 0x140u);
  v5 = &v16;
  v6 = *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)(a1 + 56);
  EventTrace.Version = a3;
  va_copy(v7, va);
  EventTrace.UserTime = 1179648;
  EventTrace.24 = v6;
  v14 = &v11;
  v12 = 0;
  v15 = 4;
  do
  {
    v8 = *(_DWORD *)v7;
    *((_DWORD *)v5 + 2) = *(_DWORD *)v7;
    if ( !v8 )
      break;
    v9 = *((_QWORD *)v7 + 1);
    v7 += 16;
    *(_QWORD *)v5 = v9;
    v5 += 16;
  }
  while ( v5 < &v17 );
  v10 = *(_QWORD *)(a1 + 8);
  *(_DWORD *)&EventTrace.Size = (_DWORD)v5 - (unsigned int)&EventTrace;
  result = TraceEvent(v10, &EventTrace);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180017430  mov     [rsp-8+arg_10], r8d
0x180017435  mov     [rsp-8+arg_18], r9
0x18001743a  push    rbp
0x18001743b  push    rbx
0x18001743c  lea     rbp, [rsp-88h]
0x180017444  sub     rsp, 188h
0x18001744b  mov     rax, cs:__security_cookie
0x180017452  xor     rax, rsp
0x180017455  mov     [rbp+90h+var_20], rax
0x180017459  cmp     byte ptr [rcx+60h], 0
0x18001745d  mov     rbx, rcx
0x180017460  jnz     short loc_18001746C
0x180017462  mov     eax, 8007065Bh
0x180017467  jmp     loc_180017530
0x18001746c  cmp     dword ptr [rcx], 0
0x18001746f  jz      loc_18001752E
0x180017475  test    [rcx], edx
0x180017477  jz      loc_18001752E
0x18001747d  mov     eax, 1
0x180017482  lock xadd cs:dword_180043130, eax
0x18001748a  inc     eax
0x18001748c  lea     rcx, [rsp+190h+EventTrace]; void *
0x180017491  xor     edx, edx; Val
0x180017493  mov     [rsp+190h+var_170], eax
0x180017497  mov     r8d, 140h; Size
0x18001749d  call    memset_0
0x1800174a2  mov     eax, [rbp+90h+arg_10]
0x1800174a8  lea     rdx, [rsp+190h+var_120]
0x1800174ad  movups  xmm0, xmmword ptr [rbx+38h]
0x1800174b1  mov     dword ptr [rsp+190h+EventTrace.4], eax
0x1800174b5  lea     rcx, [rbp+90h+arg_18]
0x1800174bc  lea     rax, [rsp+190h+var_170]
0x1800174c1  mov     dword ptr [rsp+190h+EventTrace.28h+4], 120000h
0x1800174c9  movdqu  xmmword ptr [rsp+190h+EventTrace.18h], xmm0
0x1800174cf  mov     [rsp+190h+var_130], rax
0x1800174d4  mov     [rsp+190h+var_168], 0
0x1800174dd  mov     [rsp+190h+var_128], 4
0x1800174e5  mov     eax, [rcx]
0x1800174e7  mov     [rdx+8], eax
0x1800174ea  test    eax, eax
0x1800174ec  jz      short loc_180017506
0x1800174ee  mov     rax, [rcx+8]
0x1800174f2  add     rcx, 10h
0x1800174f6  mov     [rdx], rax
0x1800174f9  add     rdx, 10h
0x1800174fd  lea     rax, [rbp+90h+var_30]
0x180017501  cmp     rdx, rax
0x180017504  jb      short loc_1800174E5
0x180017506  mov     rcx, [rbx+8]; TraceHandle
0x18001750a  lea     rax, [rsp+190h+EventTrace]
0x18001750f  sub     edx, eax
0x180017511  mov     dword ptr [rsp+190h+EventTrace.Size], edx
0x180017515  lea     rdx, [rsp+190h+EventTrace]; EventTrace
0x18001751a  call    cs:__imp_TraceEvent
0x180017520  test    eax, eax
0x180017522  jle     short loc_180017530
0x180017524  movzx   eax, ax
0x180017527  or      eax, 80070000h
0x18001752c  jmp     short loc_180017530
0x18001752e  xor     eax, eax
0x180017530  mov     rcx, [rbp+90h+var_20]
0x180017534  xor     rcx, rsp; StackCookie
0x180017537  call    __security_check_cookie
0x18001753c  add     rsp, 188h
0x180017543  pop     rbx
0x180017544  pop     rbp
0x180017545  retn
```
