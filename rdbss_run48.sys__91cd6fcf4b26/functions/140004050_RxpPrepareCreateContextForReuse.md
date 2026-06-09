# RxpPrepareCreateContextForReuse

- ea: `0x140004050`
- end: `0x14000416e`
- name: `RxpPrepareCreateContextForReuse`
- size: `286`
- prototype: `void __stdcall(PRX_CONTEXT RxContext)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x140003f50`
- `0x140017540`
- `0x140048874`
- `0x140053400`

## callees

- `0x140004050`
- `0x140009b80`
- `0x140009ea0`
- `0x140016e70`
- `0x140058f00`
- `0x14006f970`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140004112`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004112`

## pseudocode

```c
void __stdcall RxpPrepareCreateContextForReuse(PRX_CONTEXT RxContext)
{
  ULONG v1; // r8d
  const CHAR *v2; // r9
  __int64 v4; // r9
  void *v5; // rcx
  ULONG v6; // [rsp+20h] [rbp-8h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      18,
      &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
      RxContext->Create.UserDomainName.Buffer);
  }
  if ( (BYTE5(RxContext->TrackerHistory[4].FileName) & 1) != 0 )
  {
    _RxReleaseFcb(RxContext, RxContext->pFcb, v1, v2, v6);
    BYTE5(RxContext->TrackerHistory[4].FileName) &= ~1u;
    WORD1(RxContext->TrackerHistory[4].FileName) &= ~4u;
    RxContext->pFcb = 0;
  }
  v4 = *(_QWORD *)&RxContext->TrackerHistory[6].Flags;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids, v4);
    }
    ExFreePoolWithTag(*(PVOID *)&RxContext->TrackerHistory[6].Flags, 0x79537852u);
    *(_QWORD *)&RxContext->TrackerHistory[6].Flags = 0;
  }
  RxFreeCanonicalNameBuffer(RxContext);
  v5 = *(void **)&RxContext->TrackerHistory[0].Flags;
  *(_QWORD *)&RxContext->TrackerHistory[7].Flags = 0;
  LOWORD(RxContext->TrackerHistory[7].FileName) = 0;
  if ( v5 )
  {
    RxDereference(v5, LHS_LockNotHeld);
    *(_QWORD *)&RxContext->TrackerHistory[0].Flags = 0;
  }
  RxReleaseLViewRundown(RxContext);
}

```

## disassembly

```asm
0x140004050  mov     [rsp+arg_0], rbx
0x140004055  mov     [rsp+arg_8], rsi
0x14000405a  push    rdi; SerialNumber
0x14000405b  sub     rsp, 20h
0x14000405f  mov     rbx, rcx
0x140004062  mov     rcx, cs:WPP_GLOBAL_Control
0x140004069  lea     rsi, WPP_GLOBAL_Control
0x140004070  cmp     rcx, rsi
0x140004073  jz      short loc_14000409E
0x140004075  mov     eax, [rcx+2Ch]
0x140004078  test    al, 8
0x14000407a  jz      short loc_14000409E
0x14000407c  cmp     byte ptr [rcx+29h], 4
0x140004080  jb      short loc_14000409E
0x140004082  mov     r9, [rbx+260h]
0x140004089  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x140004090  mov     rcx, [rcx+18h]
0x140004094  mov     edx, 12h
0x140004099  call    WPP_SF_q
0x14000409e  xor     edi, edi
0x1400040a0  test    byte ptr [rbx+2EDh], 1
0x1400040a7  jz      short loc_1400040CC
0x1400040a9  mov     rdx, [rbx+38h]; MrxFcb
0x1400040ad  mov     rcx, rbx; RxContext
0x1400040b0  call    __RxReleaseFcb
0x1400040b5  and     byte ptr [rbx+2EDh], 0FEh
0x1400040bc  mov     eax, 0FFFBh
0x1400040c1  and     [rbx+2EAh], ax
0x1400040c8  mov     [rbx+38h], rdi
0x1400040cc  mov     r9, [rbx+320h]
0x1400040d3  test    r9, r9
0x1400040d6  jz      short loc_140004125
0x1400040d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400040df  cmp     rcx, rsi
0x1400040e2  jz      short loc_140004106
0x1400040e4  mov     eax, [rcx+2Ch]
0x1400040e7  test    al, 8
0x1400040e9  jz      short loc_140004106
0x1400040eb  cmp     byte ptr [rcx+29h], 4
0x1400040ef  jb      short loc_140004106
0x1400040f1  mov     rcx, [rcx+18h]
0x1400040f5  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x1400040fc  mov     edx, 13h
0x140004101  call    WPP_SF_q
0x140004106  mov     rcx, [rbx+320h]; P
0x14000410d  mov     edx, 79537852h; Tag
0x140004112  call    cs:__imp_ExFreePoolWithTag
0x140004119  nop     dword ptr [rax+rax+00h]
0x14000411e  mov     [rbx+320h], rdi
0x140004125  mov     rcx, rbx
0x140004128  call    RxFreeCanonicalNameBuffer
0x14000412d  mov     rcx, [rbx+290h]; Instance
0x140004134  mov     [rbx+338h], rdi
0x14000413b  mov     [rbx+330h], di
0x140004142  test    rcx, rcx
0x140004145  jz      short loc_140004155
0x140004147  xor     edx, edx; LockHoldingState
0x140004149  call    RxDereference
0x14000414e  mov     [rbx+290h], rdi
0x140004155  mov     rcx, rbx
0x140004158  call    RxReleaseLViewRundown
0x14000415d  mov     rbx, [rsp+28h+arg_0]
0x140004162  mov     rsi, [rsp+28h+arg_8]
0x140004167  add     rsp, 20h
0x14000416b  pop     rdi
0x14000416c  retn
```
