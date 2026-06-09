# MRxDAVFormatUserModeFobxFinalizeRequest

- ea: `0x140023cc0`
- end: `0x140023e14`
- name: `MRxDAVFormatUserModeFobxFinalizeRequest`
- size: `340`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x140001b64`
- `0x140023cc0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140023cf4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023d30`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023d89`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023ddb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023cf4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023d30`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023d89`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023ddb`

## pseudocode

```c
__int64 __fastcall MRxDAVFormatUserModeFobxFinalizeRequest(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v8; // rbx
  HANDLE v9; // rax
  __int64 *v10; // rsi
  __int64 v11; // rbx
  __int64 v12; // rdi
  HANDLE v13; // rax
  __int64 v14; // rbx
  HANDLE v15; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v6, 18, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v9 = PsGetCurrentThreadId();
      WPP_SF_qqq(v8, 19, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v9, a1, a2);
    }
  }
  v10 = *(__int64 **)(a2 + 216);
  if ( v10 )
    v10 = (__int64 *)v10[7];
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v11 = *v10;
    v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v13 = PsGetCurrentThreadId();
    WPP_SF_qq(v12, 20, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v13, v11);
  }
  *(_DWORD *)(a3 + 48) = 6;
  *(_QWORD *)(a3 + 632) = *v10;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v14 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v15 = PsGetCurrentThreadId();
    WPP_SF_qD(v14, 21, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v15, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140023cc0  push    rbx
0x140023cc2  push    rbp
0x140023cc3  push    rsi
0x140023cc4  push    rdi
0x140023cc5  push    r14
0x140023cc7  sub     rsp, 30h
0x140023ccb  mov     rbp, r8
0x140023cce  mov     rsi, rdx
0x140023cd1  mov     rdi, rcx
0x140023cd4  mov     rbx, cs:WPP_GLOBAL_Control
0x140023cdb  lea     r14, WPP_GLOBAL_Control
0x140023ce2  cmp     rbx, r14
0x140023ce5  jz      short loc_140023D5D
0x140023ce7  test    dword ptr [rbx+2Ch], 4000h
0x140023cee  jz      short loc_140023D17
0x140023cf0  mov     rbx, [rbx+18h]
0x140023cf4  call    cs:__imp_PsGetCurrentThreadId
0x140023cfb  nop     dword ptr [rax+rax+00h]
0x140023d00  mov     edx, 12h
0x140023d05  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140023d0c  mov     r9, rax
0x140023d0f  mov     rcx, rbx
0x140023d12  call    WPP_SF_q
0x140023d17  mov     rbx, cs:WPP_GLOBAL_Control
0x140023d1e  cmp     rbx, r14
0x140023d21  jz      short loc_140023D5D
0x140023d23  test    dword ptr [rbx+2Ch], 2000h
0x140023d2a  jz      short loc_140023D5D
0x140023d2c  mov     rbx, [rbx+18h]
0x140023d30  call    cs:__imp_PsGetCurrentThreadId
0x140023d37  nop     dword ptr [rax+rax+00h]
0x140023d3c  mov     edx, 13h
0x140023d41  mov     [rsp+58h+var_30], rsi
0x140023d46  mov     r9, rax
0x140023d49  mov     [rsp+58h+var_38], rdi
0x140023d4e  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140023d55  mov     rcx, rbx
0x140023d58  call    WPP_SF_qqq
0x140023d5d  mov     rsi, [rsi+0D8h]
0x140023d64  test    rsi, rsi
0x140023d67  jz      short loc_140023D6D
0x140023d69  mov     rsi, [rsi+38h]
0x140023d6d  mov     rdi, cs:WPP_GLOBAL_Control
0x140023d74  cmp     rdi, r14
0x140023d77  jz      short loc_140023DB1
0x140023d79  test    dword ptr [rdi+2Ch], 4000h
0x140023d80  jz      short loc_140023DB1
0x140023d82  mov     rbx, [rsi]
0x140023d85  mov     rdi, [rdi+18h]
0x140023d89  call    cs:__imp_PsGetCurrentThreadId
0x140023d90  nop     dword ptr [rax+rax+00h]
0x140023d95  mov     edx, 14h
0x140023d9a  mov     [rsp+58h+var_38], rbx
0x140023d9f  mov     r9, rax
0x140023da2  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140023da9  mov     rcx, rdi
0x140023dac  call    WPP_SF_qq
0x140023db1  mov     dword ptr [rbp+30h], 6
0x140023db8  mov     rax, [rsi]
0x140023dbb  mov     [rbp+278h], rax
0x140023dc2  mov     rbx, cs:WPP_GLOBAL_Control
0x140023dc9  cmp     rbx, r14
0x140023dcc  jz      short loc_140023E06
0x140023dce  test    dword ptr [rbx+2Ch], 4000h
0x140023dd5  jz      short loc_140023E06
0x140023dd7  mov     rbx, [rbx+18h]
0x140023ddb  call    cs:__imp_PsGetCurrentThreadId
0x140023de2  nop     dword ptr [rax+rax+00h]
0x140023de7  mov     edx, 15h
0x140023dec  mov     dword ptr [rsp+58h+var_38], 0
0x140023df4  mov     r9, rax
0x140023df7  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140023dfe  mov     rcx, rbx
0x140023e01  call    WPP_SF_qD
0x140023e06  xor     eax, eax
0x140023e08  add     rsp, 30h
0x140023e0c  pop     r14
0x140023e0e  pop     rdi
0x140023e0f  pop     rsi
0x140023e10  pop     rbp
0x140023e11  pop     rbx
0x140023e12  retn
```
