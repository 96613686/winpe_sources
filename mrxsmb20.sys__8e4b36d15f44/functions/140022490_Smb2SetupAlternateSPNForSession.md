# Smb2SetupAlternateSPNForSession

- ea: `0x140022490`
- end: `0x1400226f2`
- name: `Smb2SetupAlternateSPNForSession`
- size: `610`
- prototype: `__int64 __fastcall(__int64, USHORT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140021fb0`
- `0x1400236b0`

## callees

- `0x140022490`
- `0x1400297fc`
- `0x140029c14`
- `0x1400372c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400225a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400225a1`
- `ntoskrnl!ExAllocatePool2` at `0x140022505`
- `ntoskrnl!ExAllocatePool2` at `0x140022505`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002258d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140022622`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002258d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140022622`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002253e`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002253e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002254e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002254e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400226a5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400226a5`

## pseudocode

```c
__int64 __fastcall Smb2SetupAlternateSPNForSession(__int64 a1, USHORT *a2)
{
  unsigned int v4; // ebp
  void *Pool2; // rax
  void *v6; // rsi
  USHORT v7; // r12
  WCHAR *v8; // r13
  __int64 v9; // rdi
  KIRQL v10; // r15
  UNICODE_STRING *v11; // rdi
  __int64 v12; // rdx
  volatile LONG *v13; // rcx
  USHORT v14; // cx
  UNICODE_STRING String1; // [rsp+30h] [rbp-38h] BYREF

  if ( !a2 || !*a2 )
    return 0;
  v4 = 0;
  if ( *(_QWORD *)(a1 + 592) )
  {
    v8 = a2 + 1;
    v11 = (UNICODE_STRING *)(a1 + 584);
LABEL_21:
    v14 = *a2;
    *(_DWORD *)(&String1.MaximumLength + 1) = 0;
    String1.MaximumLength = v14;
    String1.Length = v14;
    String1.Buffer = v8;
    if ( !RtlEqualUnicodeString(&String1, v11, 1u) )
      return (unsigned int)-1073741311;
  }
  else
  {
    while ( !*(_BYTE *)(a1 + 465) || *(_BYTE *)(a1 + 466) )
    {
      Pool2 = (void *)ExAllocatePool2(66, *a2, 1834185555);
      v6 = Pool2;
      if ( !Pool2 )
        return (unsigned int)-1073741670;
      v7 = *a2;
      v8 = a2 + 1;
      memmove(Pool2, a2 + 1, *a2);
      v9 = *(_QWORD *)(a1 + 24);
      v10 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v9 + 1920));
      *(_DWORD *)(v9 + 2352) = (unsigned int)PsGetCurrentThreadId();
      v11 = (UNICODE_STRING *)(a1 + 584);
      v12 = *(_QWORD *)(a1 + 24);
      v13 = (volatile LONG *)(v12 + 1920);
      if ( !*(_QWORD *)(a1 + 592) )
      {
        *(_QWORD *)(a1 + 592) = v6;
        v11->Length = v7;
        *(_WORD *)(a1 + 586) = v7;
        *(_DWORD *)(v12 + 2352) = -1;
        ExReleaseSpinLockExclusive(v13, v10);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qZ(
            WPP_GLOBAL_Control->AttachedDevice,
            45,
            (unsigned int)WPP_981a12f1532a3df13e243e2e48204374_Traceguids,
            a1,
            a1 + 584);
        }
        return v4;
      }
      *(_DWORD *)(v12 + 2352) = -1;
      ExReleaseSpinLockExclusive(v13, v10);
      ExFreePoolWithTag(v6, 0x6D537353u);
      if ( *(_QWORD *)(a1 + 592) )
        goto LABEL_21;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_981a12f1532a3df13e243e2e48204374_Traceguids, a1);
    }
    return (unsigned int)-1073741557;
  }
  return v4;
}

```

## disassembly

```asm
0x140022490  mov     r11, rsp
0x140022493  push    rbx
0x140022494  push    r14
0x140022496  sub     rsp, 58h
0x14002249a  mov     r14, rdx
0x14002249d  mov     rbx, rcx
0x1400224a0  test    rdx, rdx
0x1400224a3  jz      loc_1400226E7
0x1400224a9  xor     eax, eax
0x1400224ab  cmp     ax, [rdx]
0x1400224ae  jz      loc_1400226E7
0x1400224b4  mov     [r11+8], rbp
0x1400224b8  xor     ebp, ebp
0x1400224ba  mov     [r11+10h], rsi
0x1400224be  mov     [r11+18h], rdi
0x1400224c2  mov     [r11-18h], r12
0x1400224c6  mov     [r11-20h], r13
0x1400224ca  mov     [r11-28h], r15
0x1400224ce  cmp     [rcx+250h], rax
0x1400224d5  jnz     loc_140022674
0x1400224db  nop     dword ptr [rax+rax+00h]
0x1400224e0  cmp     [rbx+1D1h], bpl
0x1400224e7  jz      short loc_1400224F6
0x1400224e9  cmp     [rbx+1D2h], bpl
0x1400224f0  jz      loc_1400225BF
0x1400224f6  movzx   edx, word ptr [r14]
0x1400224fa  mov     ecx, 42h ; 'B'
0x1400224ff  mov     r8d, 6D537353h
0x140022505  call    cs:__imp_ExAllocatePool2
0x14002250c  nop     dword ptr [rax+rax+00h]
0x140022511  mov     rsi, rax
0x140022514  test    rax, rax
0x140022517  jz      loc_14002266D
0x14002251d  movzx   r12d, word ptr [r14]
0x140022521  lea     r13, [r14+2]
0x140022525  mov     r8d, r12d; Size
0x140022528  mov     rdx, r13; Src
0x14002252b  mov     rcx, rax; void *
0x14002252e  call    memmove
0x140022533  mov     rdi, [rbx+18h]
0x140022537  lea     rcx, [rdi+780h]; SpinLock
0x14002253e  call    cs:__imp_ExAcquireSpinLockExclusive
0x140022545  nop     dword ptr [rax+rax+00h]
0x14002254a  movzx   r15d, al
0x14002254e  call    cs:__imp_PsGetCurrentThreadId
0x140022555  nop     dword ptr [rax+rax+00h]
0x14002255a  mov     [rdi+930h], eax
0x140022560  lea     rdi, [rbx+248h]
0x140022567  mov     rdx, [rbx+18h]
0x14002256b  lea     rcx, [rdx+780h]; SpinLock
0x140022572  cmp     [rbx+250h], rbp
0x140022579  jz      loc_140022601
0x14002257f  mov     dword ptr [rdx+930h], 0FFFFFFFFh
0x140022589  movzx   edx, r15b; OldIrql
0x14002258d  call    cs:__imp_ExReleaseSpinLockExclusive
0x140022594  nop     dword ptr [rax+rax+00h]
0x140022599  mov     edx, 6D537353h; Tag
0x14002259e  mov     rcx, rsi; P
0x1400225a1  call    cs:__imp_ExFreePoolWithTag
0x1400225a8  nop     dword ptr [rax+rax+00h]
0x1400225ad  cmp     [rbx+250h], rbp
0x1400225b4  jz      loc_1400224E0
0x1400225ba  jmp     loc_14002267F
0x1400225bf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400225c6  lea     rax, WPP_GLOBAL_Control
0x1400225cd  cmp     rcx, rax
0x1400225d0  jz      short loc_1400225F7
0x1400225d2  mov     eax, [rcx+2Ch]
0x1400225d5  test    al, 1
0x1400225d7  jz      short loc_1400225F7
0x1400225d9  cmp     byte ptr [rcx+29h], 1
0x1400225dd  jb      short loc_1400225F7
0x1400225df  mov     rcx, [rcx+18h]
0x1400225e3  lea     r8, WPP_981a12f1532a3df13e243e2e48204374_Traceguids
0x1400225ea  mov     edx, 2Ch ; ','
0x1400225ef  mov     r9, rbx
0x1400225f2  call    WPP_SF_q
0x1400225f7  mov     ebp, 0C000010Bh
0x1400225fc  jmp     loc_1400226BB
0x140022601  mov     [rbx+250h], rsi
0x140022608  mov     [rdi], r12w
0x14002260c  mov     [rbx+24Ah], r12w
0x140022614  mov     dword ptr [rdx+930h], 0FFFFFFFFh
0x14002261e  movzx   edx, r15b; OldIrql
0x140022622  call    cs:__imp_ExReleaseSpinLockExclusive
0x140022629  nop     dword ptr [rax+rax+00h]
0x14002262e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140022635  lea     rax, WPP_GLOBAL_Control
0x14002263c  cmp     rcx, rax
0x14002263f  jz      short loc_1400226BB
0x140022641  mov     eax, [rcx+2Ch]
0x140022644  test    al, 8
0x140022646  jz      short loc_1400226BB
0x140022648  cmp     byte ptr [rcx+29h], 2
0x14002264c  jb      short loc_1400226BB
0x14002264e  mov     rcx, [rcx+18h]
0x140022652  lea     r8, WPP_981a12f1532a3df13e243e2e48204374_Traceguids
0x140022659  mov     edx, 2Dh ; '-'
0x14002265e  mov     [rsp+68h+var_48], rdi
0x140022663  mov     r9, rbx
0x140022666  call    WPP_SF_qZ
0x14002266b  jmp     short loc_1400226BB
0x14002266d  mov     ebp, 0C000009Ah
0x140022672  jmp     short loc_1400226BB
0x140022674  lea     r13, [rdx+2]
0x140022678  lea     rdi, [rcx+248h]
0x14002267f  movzx   ecx, word ptr [r14]
0x140022683  xorps   xmm0, xmm0
0x140022686  movups  xmmword ptr [rsp+68h+String1.Length], xmm0
0x14002268b  mov     [rsp+68h+String1.MaximumLength], cx
0x140022690  mov     r8b, 1; CaseInSensitive
0x140022693  mov     [rsp+68h+String1.Length], cx
0x140022698  mov     rdx, rdi; String2
0x14002269b  lea     rcx, [rsp+68h+String1]; String1
0x1400226a0  mov     [rsp+68h+String1.Buffer], r13
0x1400226a5  call    cs:__imp_RtlEqualUnicodeString
0x1400226ac  nop     dword ptr [rax+rax+00h]
0x1400226b1  test    al, al
0x1400226b3  mov     ecx, 0C0000201h
0x1400226b8  cmovz   ebp, ecx
0x1400226bb  mov     r15, [rsp+68h+var_28]
0x1400226c0  mov     eax, ebp
0x1400226c2  mov     rbp, [rsp+68h+arg_0]
0x1400226c7  mov     r13, [rsp+68h+var_20]
0x1400226cc  mov     r12, [rsp+68h+var_18]
0x1400226d1  mov     rdi, [rsp+68h+arg_10]
0x1400226d9  mov     rsi, [rsp+68h+arg_8]
0x1400226de  add     rsp, 58h
0x1400226e2  pop     r14
0x1400226e4  pop     rbx
0x1400226e5  retn
0x1400226e7  xor     eax, eax
0x1400226e9  add     rsp, 58h
0x1400226ed  pop     r14
0x1400226ef  pop     rbx
0x1400226f0  retn
```
