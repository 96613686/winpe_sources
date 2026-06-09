# ClOpenAfCompleteEx

- ea: `0x1400060f0`
- end: `0x140006395`
- name: `ClOpenAfCompleteEx`
- size: `677`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003c30`

## callees

- `0x1400060f0`
- `0x140006860`
- `0x14000a290`
- `0x14000a68c`
- `0x1400161f0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140006384`
- `ntoskrnl!KeSetEvent` at `0x140006384`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006173`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400061bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400062ca`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006313`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006173`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400061bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400062ca`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006313`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006140`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006182`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400062ef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006140`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006182`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400062ef`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400062e0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400062e0`
- `NDIS!NdisClRegisterSap` at `0x140006206`
- `NDIS!NdisClRegisterSap` at `0x140006206`

## pseudocode

```c
void __fastcall ClOpenAfCompleteEx(_QWORD *Entry, __int64 a2, int a3)
{
  __int64 v3; // rdi
  KIRQL v7; // al
  unsigned int v8; // edx
  KSPIN_LOCK *v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  void *v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // edi
  KIRQL v15; // al
  bool v16; // zf
  PVOID NdisSapHandle; // [rsp+30h] [rbp-68h] BYREF
  _DWORD Sap[2]; // [rsp+40h] [rbp-58h] BYREF
  __int64 Sap_8; // [rsp+48h] [rbp-50h]
  wchar_t v20; // [rsp+50h] [rbp-48h]

  v3 = Entry[4];
  NdisSapHandle = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids, Entry, a3);
  }
  v7 = KeAcquireSpinLockRaiseToDpc(Entry + 11);
  v8 = Entry[3] & 0xFFFFFFFE;
  *((_BYTE *)Entry + 96) = v7;
  v9 = Entry + 11;
  if ( a3 )
  {
    *((_DWORD *)Entry + 6) = v8 | 4;
    KeReleaseSpinLock(v9, v7);
    ExFreeToNPagedLookasideList(&AfSapVcCBList, Entry);
    v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 504));
    v16 = (*(_DWORD *)(v3 + 448))-- == 1;
    *(_BYTE *)(v3 + 512) = v15;
    if ( v16 )
      KeSetEvent((PRKEVENT)(v3 + 456), 0, 0);
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 504), *(_BYTE *)(v3 + 512));
    goto LABEL_9;
  }
  Entry[7] = a2;
  *((_DWORD *)Entry + 6) = v8 | 0x22;
  KeReleaseSpinLock(v9, v7);
  *(_BYTE *)(v3 + 512) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 504));
  v10 = (_QWORD *)(v3 + 224);
  v11 = *(_QWORD *)(v3 + 224);
  if ( *(_QWORD *)(v11 + 8) != v3 + 224 )
    __fastfail(3u);
  *Entry = v11;
  Entry[1] = v10;
  *(_QWORD *)(v11 + 8) = Entry;
  *v10 = Entry;
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 504), *(_BYTE *)(v3 + 512));
  v12 = (void *)Entry[7];
  Sap_8 = *(_QWORD *)L"NDIS";
  v20 = aNdis[4];
  Sap[0] = 4;
  Sap[1] = 10;
  v13 = NdisClRegisterSap(v12, Entry, (PCO_SAP)Sap, &NdisSapHandle);
  v14 = v13;
  if ( v13 != 259 )
    ClRegisterSapComplete(v13, Entry, Sap, NdisSapHandle);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids,
        NdisSapHandle,
        v14);
LABEL_9:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x1400060f0  push    rbx
0x1400060f2  push    rbp
0x1400060f3  push    rsi
0x1400060f4  push    rdi
0x1400060f5  push    r14
0x1400060f7  push    r15
0x1400060f9  sub     rsp, 68h
0x1400060fd  mov     rax, cs:__security_cookie
0x140006104  xor     rax, rsp
0x140006107  mov     [rsp+98h+var_40], rax
0x14000610c  mov     rdi, [rcx+20h]
0x140006110  mov     ebp, r8d
0x140006113  mov     r15, rdx
0x140006116  mov     [rsp+98h+NdisSapHandle], 0
0x14000611f  mov     rbx, rcx
0x140006122  mov     rcx, cs:WPP_GLOBAL_Control
0x140006129  lea     rax, WPP_GLOBAL_Control
0x140006130  cmp     rcx, rax
0x140006133  jnz     loc_14000628A
0x140006139  lea     r14, [rbx+58h]
0x14000613d  mov     rcx, r14; SpinLock
0x140006140  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006147  nop     dword ptr [rax+rax+00h]
0x14000614c  mov     edx, [rbx+18h]
0x14000614f  lea     rsi, [rdi+1F8h]
0x140006156  and     edx, 0FFFFFFFEh
0x140006159  mov     [rbx+60h], al
0x14000615c  mov     rcx, r14; SpinLock
0x14000615f  test    ebp, ebp
0x140006161  jnz     loc_1400062C2
0x140006167  or      edx, 22h
0x14000616a  mov     [rbx+38h], r15
0x14000616e  mov     [rbx+18h], edx
0x140006171  mov     dl, al; NewIrql
0x140006173  call    cs:__imp_KeReleaseSpinLock
0x14000617a  nop     dword ptr [rax+rax+00h]
0x14000617f  mov     rcx, rsi; SpinLock
0x140006182  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006189  nop     dword ptr [rax+rax+00h]
0x14000618e  mov     [rdi+200h], al
0x140006194  lea     rax, [rdi+0E0h]
0x14000619b  mov     rcx, [rax]
0x14000619e  cmp     [rcx+8], rax
0x1400061a2  jnz     loc_14000632B
0x1400061a8  mov     [rbx], rcx
0x1400061ab  mov     [rbx+8], rax
0x1400061af  mov     [rcx+8], rbx
0x1400061b3  mov     rcx, rsi; SpinLock
0x1400061b6  mov     [rax], rbx
0x1400061b9  mov     dl, [rdi+200h]; NewIrql
0x1400061bf  call    cs:__imp_KeReleaseSpinLock
0x1400061c6  nop     dword ptr [rax+rax+00h]
0x1400061cb  movsd   xmm0, qword ptr cs:aNdis; "NDIS"
0x1400061d3  lea     r9, [rsp+98h+NdisSapHandle]; NdisSapHandle
0x1400061d8  movzx   eax, word ptr cs:aNdis+8; ""
0x1400061df  lea     r8, [rsp+98h+Sap]; Sap
0x1400061e4  mov     rcx, [rbx+38h]; NdisAfHandle
0x1400061e8  mov     rdx, rbx; ProtocolSapContext
0x1400061eb  movsd   qword ptr [rsp+98h+Sap+8], xmm0
0x1400061f1  mov     [rsp+98h+var_48], ax
0x1400061f6  mov     dword ptr [rsp+98h+Sap], 4
0x1400061fe  mov     dword ptr [rsp+98h+Sap+4], 0Ah
0x140006206  call    cs:__imp_NdisClRegisterSap
0x14000620d  nop     dword ptr [rax+rax+00h]
0x140006212  mov     edi, eax
0x140006214  cmp     eax, 103h
0x140006219  jnz     loc_140006332
0x14000621f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006226  lea     rbx, WPP_GLOBAL_Control
0x14000622d  cmp     rcx, rbx
0x140006230  jnz     short loc_14000624D
0x140006232  mov     rcx, [rsp+98h+var_40]
0x140006237  xor     rcx, rsp; StackCookie
0x14000623a  call    __security_check_cookie
0x14000623f  add     rsp, 68h
0x140006243  pop     r15
0x140006245  pop     r14
0x140006247  pop     rdi
0x140006248  pop     rsi
0x140006249  pop     rbp
0x14000624a  pop     rbx
0x14000624b  retn
0x14000624d  mov     eax, [rcx+2Ch]
0x140006250  test    al, 4
0x140006252  jnz     loc_14000634B
0x140006258  mov     rcx, cs:WPP_GLOBAL_Control
0x14000625f  cmp     rcx, rbx
0x140006262  jz      short loc_140006232
0x140006264  test    dword ptr [rcx+2Ch], 8000h
0x14000626b  jz      short loc_140006232
0x14000626d  cmp     byte ptr [rcx+29h], 5
0x140006271  jb      short loc_140006232
0x140006273  mov     rcx, [rcx+18h]
0x140006277  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x14000627e  mov     edx, 12h
0x140006283  call    WPP_SF_
0x140006288  jmp     short loc_140006232
0x14000628a  test    dword ptr [rcx+2Ch], 8000h
0x140006291  jz      loc_140006139
0x140006297  cmp     byte ptr [rcx+29h], 5
0x14000629b  jb      loc_140006139
0x1400062a1  mov     rcx, [rcx+18h]
0x1400062a5  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x1400062ac  mov     edx, 10h
0x1400062b1  mov     [rsp+98h+var_78], ebp
0x1400062b5  mov     r9, rbx
0x1400062b8  call    WPP_SF_qD
0x1400062bd  jmp     loc_140006139
0x1400062c2  or      edx, 4
0x1400062c5  mov     [rbx+18h], edx
0x1400062c8  mov     dl, al; NewIrql
0x1400062ca  call    cs:__imp_KeReleaseSpinLock
0x1400062d1  nop     dword ptr [rax+rax+00h]
0x1400062d6  mov     rdx, rbx; Entry
0x1400062d9  lea     rcx, AfSapVcCBList; Lookaside
0x1400062e0  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400062e7  nop     dword ptr [rax+rax+00h]
0x1400062ec  mov     rcx, rsi; SpinLock
0x1400062ef  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400062f6  nop     dword ptr [rax+rax+00h]
0x1400062fb  add     dword ptr [rdi+1C0h], 0FFFFFFFFh
0x140006302  mov     [rdi+200h], al
0x140006308  jz      short loc_140006378
0x14000630a  mov     dl, [rdi+200h]; NewIrql
0x140006310  mov     rcx, rsi; SpinLock
0x140006313  call    cs:__imp_KeReleaseSpinLock
0x14000631a  nop     dword ptr [rax+rax+00h]
0x14000631f  lea     rbx, WPP_GLOBAL_Control
0x140006326  jmp     loc_140006258
0x14000632b  mov     ecx, 3
0x140006330  int     29h; Win8: RtlFailFast(ecx)
0x140006332  mov     r9, [rsp+98h+NdisSapHandle]
0x140006337  lea     r8, [rsp+98h+Sap]
0x14000633c  mov     rdx, rbx
0x14000633f  mov     ecx, edi
0x140006341  call    ClRegisterSapComplete
0x140006346  jmp     loc_14000621F
0x14000634b  cmp     byte ptr [rcx+29h], 5
0x14000634f  jb      loc_140006258
0x140006355  mov     r9, [rsp+98h+NdisSapHandle]
0x14000635a  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x140006361  mov     rcx, [rcx+18h]
0x140006365  mov     edx, 11h
0x14000636a  mov     [rsp+98h+var_78], edi
0x14000636e  call    WPP_SF_qD
0x140006373  jmp     loc_140006258
0x140006378  lea     rcx, [rdi+1C8h]; Event
0x14000637f  xor     r8d, r8d; Wait
0x140006382  xor     edx, edx; Increment
0x140006384  call    cs:__imp_KeSetEvent
0x14000638b  nop     dword ptr [rax+rax+00h]
0x140006390  jmp     loc_14000630A
```
