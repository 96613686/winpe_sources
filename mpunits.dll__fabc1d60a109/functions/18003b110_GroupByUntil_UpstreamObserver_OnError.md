# GroupByUntil_UpstreamObserver_OnError

- ea: `0x18003b110`
- end: `0x18003b1f5`
- name: `GroupByUntil_UpstreamObserver_OnError`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18003b110`
- `0x180043e7c`
- `0x180044464`
- `0x18004449c`
- `0x1800444f4`
- `0x18004462c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b12b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b1c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b12b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b1c8`

## pseudocode

```c
__int64 __fastcall GroupByUntil_UpstreamObserver_OnError(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v4; // rbx
  bool v7; // zf
  void (__fastcall *v8)(_QWORD, _QWORD, __int64); // rax
  __int64 v9; // rax
  _QWORD *v10; // rdi
  __int64 result; // rax
  __int64 v12; // [rsp+20h] [rbp-38h] BYREF
  __int64 v13; // [rsp+28h] [rbp-30h]

  v4 = a1 + 360;
  if ( *(_QWORD *)(a1 + 400) != GetCurrentThreadId() && (unsigned int)_Pump_BeginDeferringHelper(v4) )
    _Pump_BeginDeferring(v4);
  v7 = *(_QWORD *)(a1 + 56) == 0;
  v12 = 0;
  if ( v7 )
    v13 = 0;
  else
    v13 = **(_QWORD **)(a1 + 48);
  while ( 1 )
  {
    v9 = HashMap_Iterate(a1 + 48, &v12);
    v10 = (_QWORD *)v9;
    if ( !v9 )
      break;
    v8 = *(void (__fastcall **)(_QWORD, _QWORD, __int64))(v9 + 72);
    if ( v8 )
      v8(v10[6], a2, a3);
    v10[8] = 0;
    v10[9] = 0;
    ((void (__fastcall *)(_QWORD *))CompositeDisposable_Dispose)(v10 + 15);
  }
  result = GetCurrentThreadId();
  if ( *(_QWORD *)(v4 + 40) != (unsigned int)result )
  {
    result = _Pump_EndDeferringHelper(v4);
    if ( (_DWORD)result )
      return _Pump_EndDeferring(v4);
  }
  return result;
}

```

## disassembly

```asm
0x18003b110  push    rbx
0x18003b112  push    rbp
0x18003b113  push    rsi
0x18003b114  push    rdi
0x18003b115  push    r14
0x18003b117  sub     rsp, 30h
0x18003b11b  mov     rbp, r8
0x18003b11e  lea     rbx, [rcx+168h]
0x18003b125  mov     r14d, edx
0x18003b128  mov     rsi, rcx
0x18003b12b  call    cs:__imp_GetCurrentThreadId
0x18003b131  mov     eax, eax
0x18003b133  cmp     [rbx+28h], rax
0x18003b137  jz      short loc_18003B14D
0x18003b139  mov     rcx, rbx
0x18003b13c  call    __Pump_BeginDeferringHelper
0x18003b141  test    eax, eax
0x18003b143  jz      short loc_18003B14D
0x18003b145  mov     rcx, rbx
0x18003b148  call    __Pump_BeginDeferring
0x18003b14d  cmp     qword ptr [rsi+38h], 0
0x18003b152  mov     [rsp+58h+var_38], 0
0x18003b15b  jbe     short loc_18003B16B
0x18003b15d  mov     rax, [rsi+30h]
0x18003b161  mov     rcx, [rax]
0x18003b164  mov     [rsp+58h+var_30], rcx
0x18003b169  jmp     short loc_18003B1B2
0x18003b16b  mov     [rsp+58h+var_30], 0
0x18003b174  jmp     short loc_18003B1B2
0x18003b176  mov     rax, [rdi+48h]
0x18003b17a  test    rax, rax
0x18003b17d  jz      short loc_18003B18E
0x18003b17f  mov     rcx, [rdi+30h]
0x18003b183  mov     r8, rbp
0x18003b186  mov     edx, r14d
0x18003b189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b18e  mov     qword ptr [rdi+40h], 0
0x18003b196  lea     rcx, [rdi+78h]
0x18003b19a  mov     qword ptr [rdi+48h], 0
0x18003b1a2  mov     rax, cs:off_180047BA8
0x18003b1a9  mov     rax, [rax+18h]
0x18003b1ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1b2  lea     rdx, [rsp+58h+var_38]
0x18003b1b7  lea     rcx, [rsi+30h]
0x18003b1bb  call    HashMap_Iterate
0x18003b1c0  mov     rdi, rax
0x18003b1c3  test    rax, rax
0x18003b1c6  jnz     short loc_18003B176
0x18003b1c8  call    cs:__imp_GetCurrentThreadId
0x18003b1ce  mov     eax, eax
0x18003b1d0  cmp     [rbx+28h], rax
0x18003b1d4  jz      short loc_18003B1EA
0x18003b1d6  mov     rcx, rbx
0x18003b1d9  call    __Pump_EndDeferringHelper
0x18003b1de  test    eax, eax
0x18003b1e0  jz      short loc_18003B1EA
0x18003b1e2  mov     rcx, rbx
0x18003b1e5  call    __Pump_EndDeferring
0x18003b1ea  add     rsp, 30h
0x18003b1ee  pop     r14
0x18003b1f0  pop     rdi
0x18003b1f1  pop     rsi
0x18003b1f2  pop     rbp
0x18003b1f3  pop     rbx
0x18003b1f4  retn
```
