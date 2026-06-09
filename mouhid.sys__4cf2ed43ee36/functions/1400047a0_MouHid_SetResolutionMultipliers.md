# MouHid_SetResolutionMultipliers

- ea: `0x1400047a0`
- end: `0x1400048b8`
- name: `MouHid_SetResolutionMultipliers`
- size: `280`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140002370`
- `0x140003fd0`

## callees

- `0x140002af0`
- `0x1400044bc`
- `0x1400047a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004836`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004836`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000484e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000484e`

## pseudocode

```c
__int64 __fastcall MouHid_SetResolutionMultipliers(__int64 a1)
{
  _WORD *v1; // rbx
  int v2; // esi
  int v4; // ebp
  int v5; // r14d
  int v6; // eax
  KIRQL v7; // al
  int v8; // edx
  int v10; // [rsp+70h] [rbp+8h] BYREF
  int v11; // [rsp+78h] [rbp+10h] BYREF

  v1 = *(_WORD **)(a1 + 216);
  v2 = 1;
  v10 = 1;
  v11 = 1;
  v4 = 1;
  v5 = 0;
  if ( v1[2] && !*(_BYTE *)(a1 + 88) )
  {
    v5 = MouHid_SetResolutionFeatureForUsage((_QWORD *)a1, v1[9], v1[10], &v10);
    if ( v5 < 0 )
      goto LABEL_10;
    v4 = v10;
  }
  if ( *(_WORD *)(*(_QWORD *)(a1 + 216) + 6LL) && !*(_BYTE *)(a1 + 94) )
  {
    v5 = MouHid_SetResolutionFeatureForUsage((_QWORD *)a1, v1[12], v1[13], &v11);
    v6 = v11;
    if ( v5 < 0 )
      v6 = 1;
    v2 = v6;
  }
LABEL_10:
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 64));
  *(_DWORD *)(a1 + 100) = v4;
  *(_DWORD *)(a1 + 104) = v2;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 64), v7);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qdd(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      5,
      13,
      (__int64)WPP_bce545a1de1235e2be96703916423b99_Traceguids,
      *(_QWORD *)a1,
      v4,
      v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400047a0  mov     rax, rsp
0x1400047a3  mov     [rax+18h], rbx
0x1400047a7  push    rbp
0x1400047a8  push    rsi
0x1400047a9  push    rdi
0x1400047aa  push    r14
0x1400047ac  push    r15
0x1400047ae  sub     rsp, 40h
0x1400047b2  mov     rbx, [rcx+0D8h]
0x1400047b9  mov     esi, 1
0x1400047be  xor     r15d, r15d
0x1400047c1  mov     [rax+8], esi
0x1400047c4  mov     rdi, rcx
0x1400047c7  mov     [rax+10h], esi
0x1400047ca  mov     ebp, esi
0x1400047cc  mov     r14d, r15d
0x1400047cf  cmp     [rbx+4], r15w
0x1400047d4  jz      short loc_1400047F9
0x1400047d6  cmp     [rcx+58h], r15b
0x1400047da  jnz     short loc_1400047F9
0x1400047dc  movzx   r8d, word ptr [rbx+14h]
0x1400047e1  lea     r9, [rax+8]
0x1400047e5  movzx   edx, word ptr [rbx+12h]
0x1400047e9  call    MouHid_SetResolutionFeatureForUsage
0x1400047ee  mov     r14d, eax
0x1400047f1  test    eax, eax
0x1400047f3  js      short loc_140004832
0x1400047f5  mov     ebp, [rsp+68h+arg_0]
0x1400047f9  mov     rax, [rdi+0D8h]
0x140004800  cmp     [rax+6], r15w
0x140004805  jz      short loc_140004832
0x140004807  cmp     [rdi+5Eh], r15b
0x14000480b  jnz     short loc_140004832
0x14000480d  movzx   r8d, word ptr [rbx+1Ah]
0x140004812  lea     r9, [rsp+68h+arg_8]
0x140004817  movzx   edx, word ptr [rbx+18h]
0x14000481b  mov     rcx, rdi
0x14000481e  call    MouHid_SetResolutionFeatureForUsage
0x140004823  mov     r14d, eax
0x140004826  mov     eax, [rsp+68h+arg_8]
0x14000482a  test    r14d, r14d
0x14000482d  cmovs   eax, esi
0x140004830  mov     esi, eax
0x140004832  lea     rcx, [rdi+40h]; SpinLock
0x140004836  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000483d  nop     dword ptr [rax+rax+00h]
0x140004842  lea     rcx, [rdi+40h]; SpinLock
0x140004846  mov     [rdi+64h], ebp
0x140004849  mov     dl, al; NewIrql
0x14000484b  mov     [rdi+68h], esi
0x14000484e  call    cs:__imp_KeReleaseSpinLock
0x140004855  nop     dword ptr [rax+rax+00h]
0x14000485a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140004861  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140004868  jz      short loc_1400048A0
0x14000486a  mov     rax, [rdi]
0x14000486d  mov     r9d, 0Dh
0x140004873  mov     rcx, cs:WPP_GLOBAL_Control
0x14000487a  mov     [rsp+68h+var_30], esi
0x14000487e  mov     [rsp+68h+var_38], ebp
0x140004882  mov     [rsp+68h+var_40], rax
0x140004887  lea     r8d, [r9-8]
0x14000488b  mov     rcx, [rcx+40h]
0x14000488f  lea     rax, WPP_bce545a1de1235e2be96703916423b99_Traceguids
0x140004896  mov     [rsp+68h+var_48], rax
0x14000489b  call    WPP_RECORDER_SF_qdd
0x1400048a0  mov     rbx, [rsp+68h+arg_10]
0x1400048a8  mov     eax, r14d
0x1400048ab  add     rsp, 40h
0x1400048af  pop     r15
0x1400048b1  pop     r14
0x1400048b3  pop     rdi
0x1400048b4  pop     rsi
0x1400048b5  pop     rbp
0x1400048b6  retn
```
