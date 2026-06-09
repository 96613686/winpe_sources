# GroupByUntil_UpstreamObserver_OnCompleted

- ea: `0x18003b020`
- end: `0x18003b102`
- name: `GroupByUntil_UpstreamObserver_OnCompleted`
- size: `226`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18003b020`
- `0x180043e7c`
- `0x180044464`
- `0x18004449c`
- `0x1800444f4`
- `0x18004462c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b039`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b0d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b039`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b0d0`

## pseudocode

```c
__int64 __fastcall GroupByUntil_UpstreamObserver_OnCompleted(__int64 a1)
{
  __int64 v2; // rbx
  bool v3; // zf
  void (__fastcall *v4)(_QWORD); // rax
  __int64 v5; // rax
  _QWORD *v6; // rdi
  __int64 result; // rax
  __int64 v8; // [rsp+20h] [rbp-18h] BYREF
  __int64 v9; // [rsp+28h] [rbp-10h]

  v2 = a1 + 360;
  if ( *(_QWORD *)(a1 + 400) != GetCurrentThreadId() && (unsigned int)_Pump_BeginDeferringHelper(v2) )
    _Pump_BeginDeferring(v2);
  v3 = *(_QWORD *)(a1 + 56) == 0;
  v8 = 0;
  if ( v3 )
    v9 = 0;
  else
    v9 = **(_QWORD **)(a1 + 48);
  while ( 1 )
  {
    v5 = HashMap_Iterate(a1 + 48, &v8);
    v6 = (_QWORD *)v5;
    if ( !v5 )
      break;
    v4 = *(void (__fastcall **)(_QWORD))(v5 + 64);
    if ( v4 )
      v4(v6[6]);
    v6[8] = 0;
    v6[9] = 0;
    ((void (__fastcall *)(_QWORD *))CompositeDisposable_Dispose)(v6 + 15);
  }
  result = GetCurrentThreadId();
  if ( *(_QWORD *)(v2 + 40) != (unsigned int)result )
  {
    result = _Pump_EndDeferringHelper(v2);
    if ( (_DWORD)result )
      return _Pump_EndDeferring(v2);
  }
  return result;
}

```

## disassembly

```asm
0x18003b020  mov     [rsp+arg_0], rbx
0x18003b025  mov     [rsp+arg_8], rsi
0x18003b02a  push    rdi
0x18003b02b  sub     rsp, 30h
0x18003b02f  mov     rsi, rcx
0x18003b032  lea     rbx, [rcx+168h]
0x18003b039  call    cs:__imp_GetCurrentThreadId
0x18003b03f  mov     eax, eax
0x18003b041  cmp     [rbx+28h], rax
0x18003b045  jz      short loc_18003B05B
0x18003b047  mov     rcx, rbx
0x18003b04a  call    __Pump_BeginDeferringHelper
0x18003b04f  test    eax, eax
0x18003b051  jz      short loc_18003B05B
0x18003b053  mov     rcx, rbx
0x18003b056  call    __Pump_BeginDeferring
0x18003b05b  cmp     qword ptr [rsi+38h], 0
0x18003b060  mov     [rsp+38h+var_18], 0
0x18003b069  jbe     short loc_18003B079
0x18003b06b  mov     rax, [rsi+30h]
0x18003b06f  mov     rcx, [rax]
0x18003b072  mov     [rsp+38h+var_10], rcx
0x18003b077  jmp     short loc_18003B0BA
0x18003b079  mov     [rsp+38h+var_10], 0
0x18003b082  jmp     short loc_18003B0BA
0x18003b084  mov     rax, [rdi+40h]
0x18003b088  test    rax, rax
0x18003b08b  jz      short loc_18003B096
0x18003b08d  mov     rcx, [rdi+30h]
0x18003b091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b096  mov     qword ptr [rdi+40h], 0
0x18003b09e  lea     rcx, [rdi+78h]
0x18003b0a2  mov     qword ptr [rdi+48h], 0
0x18003b0aa  mov     rax, cs:off_180047BA8
0x18003b0b1  mov     rax, [rax+18h]
0x18003b0b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b0ba  lea     rdx, [rsp+38h+var_18]
0x18003b0bf  lea     rcx, [rsi+30h]
0x18003b0c3  call    HashMap_Iterate
0x18003b0c8  mov     rdi, rax
0x18003b0cb  test    rax, rax
0x18003b0ce  jnz     short loc_18003B084
0x18003b0d0  call    cs:__imp_GetCurrentThreadId
0x18003b0d6  mov     eax, eax
0x18003b0d8  cmp     [rbx+28h], rax
0x18003b0dc  jz      short loc_18003B0F2
0x18003b0de  mov     rcx, rbx
0x18003b0e1  call    __Pump_EndDeferringHelper
0x18003b0e6  test    eax, eax
0x18003b0e8  jz      short loc_18003B0F2
0x18003b0ea  mov     rcx, rbx
0x18003b0ed  call    __Pump_EndDeferring
0x18003b0f2  mov     rbx, [rsp+38h+arg_0]
0x18003b0f7  mov     rsi, [rsp+38h+arg_8]
0x18003b0fc  add     rsp, 30h
0x18003b100  pop     rdi
0x18003b101  retn
```
