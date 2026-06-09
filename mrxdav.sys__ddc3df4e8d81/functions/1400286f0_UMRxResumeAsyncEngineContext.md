# UMRxResumeAsyncEngineContext

- ea: `0x1400286f0`
- end: `0x1400287ed`
- name: `UMRxResumeAsyncEngineContext`
- size: `253`
- prototype: `void __fastcall(_QWORD *Context)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14001d020`
- `0x1400241b0`
- `0x1400287f4`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x140027658`
- `0x1400286f0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140028728`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028764`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400287ba`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028728`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140028764`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400287ba`

## pseudocode

```c
void __fastcall UMRxResumeAsyncEngineContext(_QWORD *Context)
{
  __int64 v1; // rdi
  __int64 v3; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v5; // rbx
  HANDLE v6; // rax
  int v7; // edi
  __int64 v8; // rbx
  HANDLE v9; // rax
  __int64 v10; // [rsp+60h] [rbp+8h] BYREF

  v1 = Context[26];
  v10 = v1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v3 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v3, 21, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v5 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v6 = PsGetCurrentThreadId();
      WPP_SF_qqq(v5, 22, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v6, v1, Context);
    }
  }
  v7 = *(_DWORD *)(v1 + 128);
  UMRxFinalizeAsyncEngineContext(&v10);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
  {
    v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v9 = PsGetCurrentThreadId();
    WPP_SF_qD(v8, 23, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v9, v7);
  }
}

```

## disassembly

```asm
0x1400286f0  push    rbx
0x1400286f2  push    rbp
0x1400286f3  push    rsi
0x1400286f4  push    rdi
0x1400286f5  sub     rsp, 38h
0x1400286f9  mov     rdi, [rcx+0D0h]
0x140028700  mov     rsi, rcx
0x140028703  mov     [rsp+58h+arg_0], rdi
0x140028708  mov     rbx, cs:WPP_GLOBAL_Control
0x14002870f  lea     rbp, WPP_GLOBAL_Control
0x140028716  cmp     rbx, rbp
0x140028719  jz      short loc_140028791
0x14002871b  test    dword ptr [rbx+2Ch], 800h
0x140028722  jz      short loc_14002874B
0x140028724  mov     rbx, [rbx+18h]
0x140028728  call    cs:__imp_PsGetCurrentThreadId
0x14002872f  nop     dword ptr [rax+rax+00h]
0x140028734  mov     edx, 15h
0x140028739  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140028740  mov     r9, rax
0x140028743  mov     rcx, rbx
0x140028746  call    WPP_SF_q
0x14002874b  mov     rbx, cs:WPP_GLOBAL_Control
0x140028752  cmp     rbx, rbp
0x140028755  jz      short loc_140028791
0x140028757  test    dword ptr [rbx+2Ch], 200h
0x14002875e  jz      short loc_140028791
0x140028760  mov     rbx, [rbx+18h]
0x140028764  call    cs:__imp_PsGetCurrentThreadId
0x14002876b  nop     dword ptr [rax+rax+00h]
0x140028770  mov     edx, 16h
0x140028775  mov     [rsp+58h+var_30], rsi
0x14002877a  mov     r9, rax
0x14002877d  mov     [rsp+58h+var_38], rdi
0x140028782  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140028789  mov     rcx, rbx
0x14002878c  call    WPP_SF_qqq
0x140028791  mov     edi, [rdi+80h]
0x140028797  lea     rcx, [rsp+58h+arg_0]
0x14002879c  call    UMRxFinalizeAsyncEngineContext
0x1400287a1  mov     rbx, cs:WPP_GLOBAL_Control
0x1400287a8  cmp     rbx, rbp
0x1400287ab  jz      short loc_1400287E1
0x1400287ad  test    dword ptr [rbx+2Ch], 800h
0x1400287b4  jz      short loc_1400287E1
0x1400287b6  mov     rbx, [rbx+18h]
0x1400287ba  call    cs:__imp_PsGetCurrentThreadId
0x1400287c1  nop     dword ptr [rax+rax+00h]
0x1400287c6  mov     edx, 17h
0x1400287cb  mov     dword ptr [rsp+58h+var_38], edi
0x1400287cf  mov     r9, rax
0x1400287d2  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x1400287d9  mov     rcx, rbx
0x1400287dc  call    WPP_SF_qD
0x1400287e1  mov     eax, edi
0x1400287e3  add     rsp, 38h
0x1400287e7  pop     rdi
0x1400287e8  pop     rsi
0x1400287e9  pop     rbp
0x1400287ea  pop     rbx
0x1400287eb  retn
```
