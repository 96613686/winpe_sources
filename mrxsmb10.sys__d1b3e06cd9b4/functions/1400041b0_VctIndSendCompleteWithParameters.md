# VctIndSendCompleteWithParameters

- ea: `0x1400041b0`
- end: `0x140004328`
- name: `VctIndSendCompleteWithParameters`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400041b0`
- `0x1400054b0`
- `0x14000dfd8`
- `0x140016640`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000422f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000422f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400041d6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400041d6`
- `ntoskrnl!IoFreeMdl` at `0x1400042da`
- `ntoskrnl!IoFreeMdl` at `0x1400042da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400042f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400042f6`

## pseudocode

```c
__int64 __fastcall VctIndSendCompleteWithParameters(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v6; // rdi
  _QWORD *v7; // rbx
  _QWORD *i; // rcx
  _QWORD *v9; // rdx
  unsigned int v11; // ebx
  __int64 (__fastcall *v12)(__int64, __int64, _QWORD); // rax
  void *v13; // rcx

  if ( a2 )
  {
    v6 = 0;
    v7 = (_QWORD *)(*(_QWORD *)(a1 + 384) + 368LL);
    s_SmbCeDbSpinLockSavedIrql = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
    for ( i = (_QWORD *)*v7; ; i = (_QWORD *)v9[4] )
    {
      v9 = 0;
      if ( i != v7 )
        v9 = i - 4;
      if ( !v9 )
        break;
      if ( *((_DWORD *)v9 + 12) == 1 && v9[9] == a2 )
      {
        v6 = v9[7];
        v9[9] = 0;
        break;
      }
    }
    KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
    if ( v6 )
    {
      v11 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids, a4);
      }
      if ( *(_QWORD *)(v6 + 320) )
      {
        IoFreeMdl(*(PMDL *)(v6 + 328));
        v13 = *(void **)(v6 + 320);
        *(_QWORD *)(v6 + 328) = 0;
        ExFreePoolWithTag(v13, 0);
        *(_QWORD *)(v6 + 320) = 0;
      }
      v12 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)(v6 + 152) + 24LL);
      if ( v12 )
        v11 = v12(v6, a2, a4);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids, v11);
      }
      SmbCeDecrementPendingOperationsAndFinalize((PVOID)v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400041b0  push    rbx
0x1400041b2  push    rbp
0x1400041b3  push    rsi
0x1400041b4  push    rdi
0x1400041b5  push    r12
0x1400041b7  sub     rsp, 20h
0x1400041bb  mov     ebp, r9d
0x1400041be  mov     rsi, rdx
0x1400041c1  test    rdx, rdx
0x1400041c4  jz      short loc_140004240
0x1400041c6  mov     rbx, [rcx+180h]
0x1400041cd  xor     edi, edi
0x1400041cf  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x1400041d6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400041dd  nop     dword ptr [rax+rax+00h]
0x1400041e2  add     rbx, 170h
0x1400041e9  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x1400041ef  mov     rcx, [rbx]
0x1400041f2  xor     edx, edx
0x1400041f4  lea     rax, [rcx-20h]
0x1400041f8  cmp     rcx, rbx
0x1400041fb  cmovnz  rdx, rax
0x1400041ff  test    rdx, rdx
0x140004202  jz      short loc_140004222
0x140004204  cmp     dword ptr [rdx+30h], 1
0x140004208  jnz     short loc_140004210
0x14000420a  cmp     [rdx+48h], rsi
0x14000420e  jz      short loc_140004216
0x140004210  mov     rcx, [rdx+20h]
0x140004214  jmp     short loc_1400041F2
0x140004216  mov     rdi, [rdx+38h]
0x14000421a  mov     qword ptr [rdx+48h], 0
0x140004222  mov     dl, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x140004228  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000422f  call    cs:__imp_KeReleaseSpinLock
0x140004236  nop     dword ptr [rax+rax+00h]
0x14000423b  test    rdi, rdi
0x14000423e  jnz     short loc_14000424E
0x140004240  xor     eax, eax
0x140004242  add     rsp, 20h
0x140004246  pop     r12
0x140004248  pop     rdi
0x140004249  pop     rsi
0x14000424a  pop     rbp
0x14000424b  pop     rbx
0x14000424c  retn
0x14000424e  xor     ebx, ebx
0x140004250  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140004257  lea     r12, WPP_GLOBAL_Control
0x14000425e  cmp     rcx, r12
0x140004261  jz      short loc_14000426C
0x140004263  test    dword ptr [rcx+2Ch], 400h
0x14000426a  jnz     short loc_1400042B9
0x14000426c  cmp     [rdi+140h], rbx
0x140004273  jnz     short loc_1400042D3
0x140004275  mov     rax, [rdi+98h]
0x14000427c  mov     rax, [rax+18h]
0x140004280  test    rax, rax
0x140004283  jz      short loc_140004295
0x140004285  mov     r8d, ebp
0x140004288  mov     rdx, rsi
0x14000428b  mov     rcx, rdi
0x14000428e  call    _guard_dispatch_icall
0x140004293  mov     ebx, eax
0x140004295  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000429c  cmp     rcx, r12
0x14000429f  jz      short loc_1400042AA
0x1400042a1  test    dword ptr [rcx+2Ch], 400h
0x1400042a8  jnz     short loc_14000430E
0x1400042aa  mov     edx, 2
0x1400042af  mov     rcx, rdi; pContext
0x1400042b2  call    SmbCeDecrementPendingOperationsAndFinalize
0x1400042b7  jmp     short loc_140004240
0x1400042b9  mov     rcx, [rcx+18h]
0x1400042bd  lea     r8, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids
0x1400042c4  mov     edx, 15h
0x1400042c9  mov     r9d, ebp
0x1400042cc  call    WPP_SF_d
0x1400042d1  jmp     short loc_14000426C
0x1400042d3  mov     rcx, [rdi+148h]; Mdl
0x1400042da  call    cs:__imp_IoFreeMdl
0x1400042e1  nop     dword ptr [rax+rax+00h]
0x1400042e6  mov     rcx, [rdi+140h]; P
0x1400042ed  xor     edx, edx; Tag
0x1400042ef  mov     [rdi+148h], rbx
0x1400042f6  call    cs:__imp_ExFreePoolWithTag
0x1400042fd  nop     dword ptr [rax+rax+00h]
0x140004302  mov     [rdi+140h], rbx
0x140004309  jmp     loc_140004275
0x14000430e  mov     rcx, [rcx+18h]
0x140004312  lea     r8, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids
0x140004319  mov     edx, 16h
0x14000431e  mov     r9d, ebx
0x140004321  call    WPP_SF_d
0x140004326  jmp     short loc_1400042AA
```
