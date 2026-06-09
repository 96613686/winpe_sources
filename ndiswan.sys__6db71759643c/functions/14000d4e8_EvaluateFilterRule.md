# EvaluateFilterRule

- ea: `0x14000d4e8`
- end: `0x14000d659`
- name: `EvaluateFilterRule`
- size: `369`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000d660`
- `0x140026c80`

## callees

- `0x14000d4e8`
- `0x14000dbc4`
- `0x1400161f0`
- `0x140016700`

## import_xrefs

- `ntoskrnl!wcscpy_s` at `0x14000d5ab`
- `ntoskrnl!wcscpy_s` at `0x14000d5ab`
- `ntoskrnl!_wcslwr` at `0x14000d5bb`
- `ntoskrnl!_wcslwr` at `0x14000d5bb`
- `NDIS!NdisReleaseRWLock` at `0x14000d628`
- `NDIS!NdisReleaseRWLock` at `0x14000d628`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000d559`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000d559`

## pseudocode

```c
char __fastcall EvaluateFilterRule(int a1, const wchar_t *a2)
{
  int v3; // r9d
  int v4; // ebx
  __int64 v5; // rax
  int v6; // eax
  _BYTE v8[4]; // [rsp+30h] [rbp-D0h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+34h] [rbp-CCh] BYREF
  _QWORD v10[8]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Dst[280]; // [rsp+80h] [rbp-80h] BYREF
  int v12; // [rsp+2E0h] [rbp+1E0h] BYREF

  v12 = a1;
  memset(v10, 0, sizeof(v10));
  memset(Dst, 0, 0x224u);
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v8[0] = 0;
  NdisAcquireRWLockWrite(NdisWanPacketCapFilterLock, &LockState, 0);
  v4 = 1;
  if ( NDISWanPacketCapRules )
  {
    LOBYTE(v10[0]) = 24;
    v10[1] = &v12;
    HIDWORD(v10[0]) = 4;
    v10[3] = 0;
    LODWORD(v10[2]) = 0;
    if ( *a2 )
    {
      v4 = 2;
      wcscpy_s(Dst, 0x112u, a2);
      _wcslwr(Dst);
      LOBYTE(v10[4]) = 25;
      v10[5] = Dst;
      v5 = -1;
      do
        ++v5;
      while ( Dst[v5] );
      v10[7] = 0;
      HIDWORD(v10[4]) = 2 * v5;
      LODWORD(v10[6]) = 0;
    }
    v6 = TraceFilterEngineEvaluateFilterExpressionInternal(
           (unsigned int)v10,
           v4,
           (_DWORD)NDISWanPacketCapRules,
           v3,
           (__int64)v8);
    LOBYTE(v4) = v8[0];
    if ( v6 )
      LOBYTE(v4) = 0;
  }
  NdisReleaseRWLock(NdisWanPacketCapFilterLock, &LockState);
  return v4;
}

```

## disassembly

```asm
0x14000d4e8  mov     [rsp-8+arg_10], rbx
0x14000d4ed  mov     [rsp-8+arg_0], ecx
0x14000d4f1  push    rbp
0x14000d4f2  push    rsi
0x14000d4f3  push    rdi
0x14000d4f4  lea     rbp, [rsp-1C0h]
0x14000d4fc  sub     rsp, 2C0h
0x14000d503  mov     rax, cs:__security_cookie
0x14000d50a  xor     rax, rsp
0x14000d50d  mov     [rbp+1D0h+var_20], rax
0x14000d514  mov     rdi, rdx
0x14000d517  lea     rcx, [rsp+2D0h+var_290]; void *
0x14000d51c  xor     edx, edx; Val
0x14000d51e  lea     r8d, [rdx+40h]; Size
0x14000d522  call    memset
0x14000d527  xor     edx, edx; Val
0x14000d529  lea     rcx, [rbp+1D0h+Dst]; void *
0x14000d52d  mov     r8d, 224h; Size
0x14000d533  call    memset
0x14000d538  mov     rcx, cs:NdisWanPacketCapFilterLock; Lock
0x14000d53f  lea     rdx, [rsp+2D0h+LockState]; LockState
0x14000d544  xor     eax, eax
0x14000d546  xor     esi, esi
0x14000d548  xor     r8d, r8d; Flags
0x14000d54b  mov     word ptr [rsp+2D0h+LockState.OldIrql], ax
0x14000d550  mov     [rsp+2D0h+LockState.Flags], al
0x14000d554  mov     [rsp+2D0h+var_2A0], sil
0x14000d559  call    cs:__imp_NdisAcquireRWLockWrite
0x14000d560  nop     dword ptr [rax+rax+00h]
0x14000d565  cmp     cs:NDISWanPacketCapRules, rsi
0x14000d56c  lea     ebx, [rsi+1]
0x14000d56f  jz      loc_14000D61C
0x14000d575  lea     rax, [rbp+1D0h+arg_0]
0x14000d57c  mov     [rsp+2D0h+var_290], 18h
0x14000d581  mov     [rsp+2D0h+var_288], rax
0x14000d586  mov     [rsp+2D0h+var_28C], 4
0x14000d58e  mov     [rsp+2D0h+var_278], rsi
0x14000d593  mov     [rsp+2D0h+var_280], esi
0x14000d597  cmp     [rdi], si
0x14000d59a  jz      short loc_14000D5F5
0x14000d59c  mov     r8, rdi; Src
0x14000d59f  lea     rcx, [rbp+1D0h+Dst]; Dst
0x14000d5a3  mov     edx, 112h; SizeInWords
0x14000d5a8  lea     ebx, [rsi+2]
0x14000d5ab  call    cs:__imp_wcscpy_s
0x14000d5b2  nop     dword ptr [rax+rax+00h]
0x14000d5b7  lea     rcx, [rbp+1D0h+Dst]; String
0x14000d5bb  call    cs:__imp__wcslwr
0x14000d5c2  nop     dword ptr [rax+rax+00h]
0x14000d5c7  lea     rax, [rbp+1D0h+Dst]
0x14000d5cb  mov     [rsp+2D0h+var_270], 19h
0x14000d5d0  mov     [rsp+2D0h+var_268], rax
0x14000d5d5  lea     rcx, [rbp+1D0h+Dst]
0x14000d5d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d5dd  inc     rax
0x14000d5e0  cmp     [rcx+rax*2], si
0x14000d5e4  jnz     short loc_14000D5DD
0x14000d5e6  add     eax, eax
0x14000d5e8  mov     [rsp+2D0h+var_258], rsi
0x14000d5ed  mov     [rsp+2D0h+var_26C], eax
0x14000d5f1  mov     [rsp+2D0h+var_260], esi
0x14000d5f5  mov     r8, cs:NDISWanPacketCapRules
0x14000d5fc  lea     rax, [rsp+2D0h+var_2A0]
0x14000d601  mov     edx, ebx
0x14000d603  mov     [rsp+2D0h+var_2B0], rax
0x14000d608  lea     rcx, [rsp+2D0h+var_290]
0x14000d60d  call    TraceFilterEngineEvaluateFilterExpressionInternal
0x14000d612  movzx   ebx, [rsp+2D0h+var_2A0]
0x14000d617  test    eax, eax
0x14000d619  cmovnz  ebx, esi
0x14000d61c  mov     rcx, cs:NdisWanPacketCapFilterLock; Lock
0x14000d623  lea     rdx, [rsp+2D0h+LockState]; LockState
0x14000d628  call    cs:__imp_NdisReleaseRWLock
0x14000d62f  nop     dword ptr [rax+rax+00h]
0x14000d634  mov     al, bl
0x14000d636  mov     rcx, [rbp+1D0h+var_20]
0x14000d63d  xor     rcx, rsp; StackCookie
0x14000d640  call    __security_check_cookie
0x14000d645  mov     rbx, [rsp+2D0h+arg_10]
0x14000d64d  add     rsp, 2C0h
0x14000d654  pop     rdi
0x14000d655  pop     rsi
0x14000d656  pop     rbp
0x14000d657  retn
```
