# ClCloseAfComplete

- ea: `0x140006430`
- end: `0x140006577`
- name: `ClCloseAfComplete`
- size: `327`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140006860`
- `0x140006a50`

## callees

- `0x140006430`
- `0x14000a290`
- `0x14000a68c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400064b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400064fa`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400064b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400064fa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000648f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400064c6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000648f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400064c6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006510`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006510`

## pseudocode

```c
void __fastcall ClCloseAfComplete(int a1, _QWORD *a2)
{
  __int64 v2; // rsi
  KIRQL v5; // al
  unsigned int v6; // edx
  _QWORD *v7; // rdx
  void **v8; // rax

  v2 = a2[4];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids, a2, a1);
  }
  if ( !a1 )
  {
    v5 = KeAcquireSpinLockRaiseToDpc(a2 + 11);
    v6 = a2[3] & 0xFFFFFFF7;
    *((_BYTE *)a2 + 96) = v5;
    *((_DWORD *)a2 + 6) = v6 | 0x10;
    KeReleaseSpinLock(a2 + 11, v5);
    *(_BYTE *)(v2 + 512) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 504));
    v7 = (_QWORD *)*a2;
    if ( *(_QWORD **)(*a2 + 8LL) != a2 || (v8 = (void **)a2[1], *v8 != a2) )
      __fastfail(3u);
    *v8 = v7;
    v7[1] = v8;
    KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 504), *(_BYTE *)(v2 + 512));
    ExFreeToNPagedLookasideList(&AfSapVcCBList, a2);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids);
  }
}

```

## disassembly

```asm
0x140006430  push    rbx
0x140006432  push    rsi
0x140006433  push    rdi
0x140006434  push    r14
0x140006436  sub     rsp, 38h
0x14000643a  mov     rsi, [rdx+20h]
0x14000643e  mov     rdi, rdx
0x140006441  mov     ebx, ecx
0x140006443  mov     rcx, cs:WPP_GLOBAL_Control
0x14000644a  lea     r14, WPP_GLOBAL_Control
0x140006451  cmp     rcx, r14
0x140006454  jz      short loc_140006463
0x140006456  test    dword ptr [rcx+2Ch], 8000h
0x14000645d  jnz     loc_140006521
0x140006463  test    ebx, ebx
0x140006465  jz      short loc_14000648B
0x140006467  mov     rcx, cs:WPP_GLOBAL_Control
0x14000646e  cmp     rcx, r14
0x140006471  jz      short loc_140006480
0x140006473  test    dword ptr [rcx+2Ch], 8000h
0x14000647a  jnz     loc_140006553
0x140006480  add     rsp, 38h
0x140006484  pop     r14
0x140006486  pop     rdi
0x140006487  pop     rsi
0x140006488  pop     rbx
0x140006489  retn
0x14000648b  lea     rcx, [rdi+58h]; SpinLock
0x14000648f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006496  nop     dword ptr [rax+rax+00h]
0x14000649b  mov     edx, [rdi+18h]
0x14000649e  lea     rcx, [rdi+58h]; SpinLock
0x1400064a2  and     edx, 0FFFFFFF7h
0x1400064a5  mov     [rdi+60h], al
0x1400064a8  or      edx, 10h
0x1400064ab  mov     [rdi+18h], edx
0x1400064ae  mov     dl, al; NewIrql
0x1400064b0  call    cs:__imp_KeReleaseSpinLock
0x1400064b7  nop     dword ptr [rax+rax+00h]
0x1400064bc  lea     rbx, [rsi+1F8h]
0x1400064c3  mov     rcx, rbx; SpinLock
0x1400064c6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400064cd  nop     dword ptr [rax+rax+00h]
0x1400064d2  mov     [rsi+200h], al
0x1400064d8  mov     rdx, [rdi]
0x1400064db  cmp     [rdx+8], rdi
0x1400064df  jnz     short loc_14000654C
0x1400064e1  mov     rax, [rdi+8]
0x1400064e5  cmp     [rax], rdi
0x1400064e8  jnz     short loc_14000654C
0x1400064ea  mov     [rax], rdx
0x1400064ed  mov     rcx, rbx; SpinLock
0x1400064f0  mov     [rdx+8], rax
0x1400064f4  mov     dl, [rsi+200h]; NewIrql
0x1400064fa  call    cs:__imp_KeReleaseSpinLock
0x140006501  nop     dword ptr [rax+rax+00h]
0x140006506  mov     rdx, rdi; Entry
0x140006509  lea     rcx, AfSapVcCBList; Lookaside
0x140006510  call    cs:__imp_ExFreeToNPagedLookasideList
0x140006517  nop     dword ptr [rax+rax+00h]
0x14000651c  jmp     loc_140006467
0x140006521  cmp     byte ptr [rcx+29h], 5
0x140006525  jb      loc_140006463
0x14000652b  mov     rcx, [rcx+18h]
0x14000652f  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x140006536  mov     edx, 13h
0x14000653b  mov     [rsp+58h+var_38], ebx
0x14000653f  mov     r9, rdi
0x140006542  call    WPP_SF_qD
0x140006547  jmp     loc_140006463
0x14000654c  mov     ecx, 3
0x140006551  int     29h; Win8: RtlFailFast(ecx)
0x140006553  cmp     byte ptr [rcx+29h], 5
0x140006557  jb      loc_140006480
0x14000655d  mov     rcx, [rcx+18h]
0x140006561  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x140006568  mov     edx, 14h
0x14000656d  call    WPP_SF_
0x140006572  jmp     loc_140006480
```
