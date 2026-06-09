# MRxDAVCollapseOpen

- ea: `0x140012ee0`
- end: `0x140012f78`
- name: `MRxDAVCollapseOpen`
- size: `152`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000163c`
- `0x140012ee0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140012f16`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012f16`
- `rdbss!RxCreateNetFobx` at `0x140012f3f`
- `rdbss!RxCreateNetFobx` at `0x140012f3f`

## pseudocode

```c
__int64 __fastcall MRxDAVCollapseOpen(PRX_CONTEXT RxContext)
{
  struct _MRX_SRV_OPEN_ *pRelevantSrvOpen; // rsi
  __int64 v3; // rbx
  HANDLE CurrentThreadId; // rax
  struct _MRX_FOBX_ *NetFobx; // rax
  struct _MRX_FOBX_ *v6; // rcx
  __int64 result; // rax

  pRelevantSrvOpen = RxContext->pRelevantSrvOpen;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v3 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_q(v3, 96, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, CurrentThreadId);
  }
  NetFobx = RxCreateNetFobx(RxContext, pRelevantSrvOpen);
  RxContext->pFobx = NetFobx;
  v6 = NetFobx;
  if ( !NetFobx )
    return 3221225626LL;
  result = 0;
  LODWORD(v6[1].Context) = 1;
  return result;
}

```

## disassembly

```asm
0x140012ee0  mov     [rsp+arg_0], rbx
0x140012ee5  mov     [rsp+arg_8], rsi
0x140012eea  push    rdi
0x140012eeb  sub     rsp, 20h
0x140012eef  mov     rsi, [rcx+48h]
0x140012ef3  mov     rdi, rcx
0x140012ef6  mov     rbx, cs:WPP_GLOBAL_Control
0x140012efd  lea     rax, WPP_GLOBAL_Control
0x140012f04  cmp     rbx, rax
0x140012f07  jz      short loc_140012F39
0x140012f09  test    dword ptr [rbx+2Ch], 2000h
0x140012f10  jz      short loc_140012F39
0x140012f12  mov     rbx, [rbx+18h]
0x140012f16  call    cs:__imp_PsGetCurrentThreadId
0x140012f1d  nop     dword ptr [rax+rax+00h]
0x140012f22  mov     edx, 60h ; '`'
0x140012f27  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140012f2e  mov     r9, rax
0x140012f31  mov     rcx, rbx
0x140012f34  call    WPP_SF_q
0x140012f39  mov     rdx, rsi; MrxSrvOpen
0x140012f3c  mov     rcx, rdi; RxContext
0x140012f3f  call    cs:__imp_RxCreateNetFobx
0x140012f46  nop     dword ptr [rax+rax+00h]
0x140012f4b  mov     [rdi+40h], rax
0x140012f4f  mov     rcx, rax
0x140012f52  test    rax, rax
0x140012f55  jz      short loc_140012F62
0x140012f57  xor     eax, eax
0x140012f59  mov     dword ptr [rcx+60h], 1
0x140012f60  jmp     short loc_140012F67
0x140012f62  mov     eax, 0C000009Ah
0x140012f67  mov     rbx, [rsp+28h+arg_0]
0x140012f6c  mov     rsi, [rsp+28h+arg_8]
0x140012f71  add     rsp, 20h
0x140012f75  pop     rdi
0x140012f76  retn
```
