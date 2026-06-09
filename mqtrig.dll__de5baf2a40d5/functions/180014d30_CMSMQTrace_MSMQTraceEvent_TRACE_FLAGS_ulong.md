# CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)

- ea: `0x180014d30`
- end: `0x180014e46`
- name: `?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ`
- size: `278`
- prototype: `signed int(__int64, int, ULONG, ...)`
- caller_count: `43`
- callee_count: `3`
- tags: ``

## callers

- `0x180003460`
- `0x180003640`
- `0x180004fc4`
- `0x180005078`
- `0x180005930`
- `0x180005c10`
- `0x180005df4`
- `0x180006a50`
- `0x180006bec`
- `0x180006ef0`
- `0x1800084d0`
- `0x18000897c`
- `0x180008d68`
- `0x180009420`
- `0x1800097c8`
- `0x18000a300`
- `0x18000aa80`
- `0x18000aea0`
- `0x18000b310`
- `0x18000b5e0`
- `0x18000b760`
- `0x18000bb20`
- `0x18000bda0`
- `0x18000c340`
- `0x18000c4b0`
- `0x18000ce94`
- `0x18000d520`
- `0x18000f290`
- `0x18000f310`
- `0x18001e8ae`
- `0x18001ecef`
- `0x18001ee86`
- `0x18001efb1`
- `0x18001f159`
- `0x18001f2e5`
- `0x18001f3e7`
- `0x18001f81b`
- `0x18001f92f`
- `0x18001fa21`
- `0x18001fb01`
- `0x18001fcda`
- `0x18001fdcc`
- `0x18001feac`

## callees

- `0x180014d30`
- `0x18001e35a`
- `0x18001e380`

## import_xrefs

- `ADVAPI32!TraceEvent` at `0x180014e1a`
- `ADVAPI32!TraceEvent` at `0x180014e1a`

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
  v11 = _InterlockedIncrement(&dword_18002D694);
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
0x180014d30  mov     [rsp-8+arg_10], r8d
0x180014d35  mov     [rsp-8+arg_18], r9
0x180014d3a  push    rbp
0x180014d3b  push    rbx
0x180014d3c  lea     rbp, [rsp-88h]
0x180014d44  sub     rsp, 188h
0x180014d4b  mov     rax, cs:__security_cookie
0x180014d52  xor     rax, rsp
0x180014d55  mov     [rbp+90h+var_20], rax
0x180014d59  cmp     byte ptr [rcx+60h], 0
0x180014d5d  mov     rbx, rcx
0x180014d60  jnz     short loc_180014D6C
0x180014d62  mov     eax, 8007065Bh
0x180014d67  jmp     loc_180014E30
0x180014d6c  cmp     dword ptr [rcx], 0
0x180014d6f  jz      loc_180014E2E
0x180014d75  test    [rcx], edx
0x180014d77  jz      loc_180014E2E
0x180014d7d  mov     eax, 1
0x180014d82  lock xadd cs:dword_18002D694, eax
0x180014d8a  inc     eax
0x180014d8c  lea     rcx, [rsp+190h+EventTrace]; void *
0x180014d91  xor     edx, edx; Val
0x180014d93  mov     [rsp+190h+var_170], eax
0x180014d97  mov     r8d, 140h; Size
0x180014d9d  call    memset_0
0x180014da2  mov     eax, [rbp+90h+arg_10]
0x180014da8  lea     rdx, [rsp+190h+var_120]
0x180014dad  movups  xmm0, xmmword ptr [rbx+38h]
0x180014db1  mov     dword ptr [rsp+190h+EventTrace.4], eax
0x180014db5  lea     rcx, [rbp+90h+arg_18]
0x180014dbc  lea     rax, [rsp+190h+var_170]
0x180014dc1  mov     dword ptr [rsp+190h+EventTrace.28h+4], 120000h
0x180014dc9  movdqu  xmmword ptr [rsp+190h+EventTrace.18h], xmm0
0x180014dcf  mov     [rsp+190h+var_130], rax
0x180014dd4  mov     [rsp+190h+var_168], 0
0x180014ddd  mov     [rsp+190h+var_128], 4
0x180014de5  mov     eax, [rcx]
0x180014de7  mov     [rdx+8], eax
0x180014dea  test    eax, eax
0x180014dec  jz      short loc_180014E06
0x180014dee  mov     rax, [rcx+8]
0x180014df2  add     rcx, 10h
0x180014df6  mov     [rdx], rax
0x180014df9  add     rdx, 10h
0x180014dfd  lea     rax, [rbp+90h+var_30]
0x180014e01  cmp     rdx, rax
0x180014e04  jb      short loc_180014DE5
0x180014e06  mov     rcx, [rbx+8]; TraceHandle
0x180014e0a  lea     rax, [rsp+190h+EventTrace]
0x180014e0f  sub     edx, eax
0x180014e11  mov     dword ptr [rsp+190h+EventTrace.Size], edx
0x180014e15  lea     rdx, [rsp+190h+EventTrace]; EventTrace
0x180014e1a  call    cs:__imp_TraceEvent
0x180014e20  test    eax, eax
0x180014e22  jle     short loc_180014E30
0x180014e24  movzx   eax, ax
0x180014e27  or      eax, 80070000h
0x180014e2c  jmp     short loc_180014E30
0x180014e2e  xor     eax, eax
0x180014e30  mov     rcx, [rbp+90h+var_20]
0x180014e34  xor     rcx, rsp; StackCookie
0x180014e37  call    __security_check_cookie
0x180014e3c  add     rsp, 188h
0x180014e43  pop     rbx
0x180014e44  pop     rbp
0x180014e45  retn
```
