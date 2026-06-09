# DfscNetUseRelease

- ea: `0x14001f8a0`
- end: `0x14001fb49`
- name: `DfscNetUseRelease`
- size: `681`
- prototype: `__int64 __fastcall(__int64, ULONG_PTR, unsigned __int8, char)`
- caller_count: `10`
- callee_count: `6`
- tags: ``

## callers

- `0x140003a94`
- `0x14001134c`
- `0x140013db8`
- `0x140017458`
- `0x140018130`
- `0x14001d9b0`
- `0x14001e3d0`
- `0x140021300`
- `0x14002545c`
- `0x140025f20`

## callees

- `0x1400025f4`
- `0x140002fcc`
- `0x140004d5c`
- `0x140017fb8`
- `0x14001f8a0`
- `0x1400252b0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14001fae9`
- `ntoskrnl!ZwClose` at `0x14001fae9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f93c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001fa9c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f93c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001fa9c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001f930`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001fa90`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001f930`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001fa90`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001f8e7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001f8e7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001f8c6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001f8c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fb38`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fb38`

## pseudocode

```c
__int64 __fastcall DfscNetUseRelease(__int64 a1, ULONG_PTR a2, unsigned __int8 a3, char a4)
{
  __int64 v4; // r13
  int v6; // r12d
  unsigned int v9; // r14d
  struct _ERESOURCE *p_WaitListHead; // rbp
  struct _ERESOURCE *v11; // rcx
  __int64 v12; // r8
  signed __int32 v13; // edi
  void *v15; // r15
  __int64 v16; // r9

  v4 = *(_QWORD *)(a2 + 120);
  v6 = a3;
  v9 = 0;
  KeEnterCriticalRegion();
  p_WaitListHead = (struct _ERESOURCE *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
  if ( a1 )
    v11 = (struct _ERESOURCE *)(a1 + 152);
  else
    v11 = (struct _ERESOURCE *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
  ExAcquireResourceExclusiveLite(v11, 1u);
  v13 = _InterlockedDecrement((volatile signed __int32 *)(a2 + 4));
  if ( a4 == 1 )
    --*(_DWORD *)(a2 + 144);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_qdd(WPP_GLOBAL_Control->AttachedDevice, 13, v12, a2, v13, *(_DWORD *)(a2 + 144));
  if ( !v13 || (_BYTE)v6 == 1 )
  {
    v15 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_qdd(WPP_GLOBAL_Control->AttachedDevice, 14, v12, a2, v13, v6);
    }
    if ( v4 && *(_QWORD *)(a2 + 120) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_87cf2b6004dc3e7f3eb3e63342a64277_Traceguids, a2);
      }
      DfscNetUseTableDelete(*(struct _RTL_AVL_TABLE **)(a2 + 120), a2);
    }
    if ( (_BYTE)v6 )
    {
      v16 = *(_QWORD *)(a2 + 112);
      if ( v16 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
        {
          WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_87cf2b6004dc3e7f3eb3e63342a64277_Traceguids, v16, a2);
        }
        v9 = DfscCredRelease(*(_QWORD *)(a2 + 112));
        *(_QWORD *)(a2 + 112) = 0;
      }
      v15 = *(void **)(a2 + 136);
      *(_QWORD *)(a2 + 136) = 0;
    }
    if ( a1 )
      p_WaitListHead = (struct _ERESOURCE *)(a1 + 152);
    ExReleaseResourceLite(p_WaitListHead);
    KeLeaveCriticalRegion();
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_87cf2b6004dc3e7f3eb3e63342a64277_Traceguids, v15, a2);
      }
      ZwClose(v15);
    }
    if ( !v13 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_87cf2b6004dc3e7f3eb3e63342a64277_Traceguids, a2);
      }
      ExFreePoolWithTag((PVOID)a2, 0);
    }
  }
  else
  {
    if ( a1 )
      p_WaitListHead = (struct _ERESOURCE *)(a1 + 152);
    ExReleaseResourceLite(p_WaitListHead);
    KeLeaveCriticalRegion();
  }
  return v9;
}

```

## disassembly

```asm
0x14001f8a0  push    rbx
0x14001f8a2  push    rbp
0x14001f8a3  push    rsi
0x14001f8a4  push    rdi
0x14001f8a5  push    r12
0x14001f8a7  push    r13
0x14001f8a9  push    r14
0x14001f8ab  push    r15
0x14001f8ad  sub     rsp, 38h
0x14001f8b1  mov     r13, [rdx+78h]
0x14001f8b5  movzx   r15d, r9b
0x14001f8b9  movzx   r12d, r8b
0x14001f8bd  mov     rbx, rdx
0x14001f8c0  mov     rsi, rcx
0x14001f8c3  xor     r14d, r14d
0x14001f8c6  call    cs:__imp_KeEnterCriticalRegion
0x14001f8cd  nop     dword ptr [rax+rax+00h]
0x14001f8d2  lea     rbp, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14001f8d9  test    rsi, rsi
0x14001f8dc  jz      short loc_14001F95D
0x14001f8de  lea     rcx, [rsi+98h]; Resource
0x14001f8e5  mov     dl, 1; Wait
0x14001f8e7  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001f8ee  nop     dword ptr [rax+rax+00h]
0x14001f8f3  mov     edi, 0FFFFFFFFh
0x14001f8f8  lock xadd [rbx+4], edi
0x14001f8fd  dec     edi
0x14001f8ff  cmp     r15b, 1
0x14001f903  jnz     short loc_14001F90B
0x14001f905  dec     dword ptr [rbx+90h]
0x14001f90b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f912  lea     rax, WPP_GLOBAL_Control
0x14001f919  cmp     rcx, rax
0x14001f91c  jnz     short loc_14001F962
0x14001f91e  test    edi, edi
0x14001f920  jz      short loc_14001F99E
0x14001f922  cmp     r12b, 1
0x14001f926  jz      short loc_14001F99E
0x14001f928  test    rsi, rsi
0x14001f92b  jnz     short loc_14001F995
0x14001f92d  mov     rcx, rbp; Resource
0x14001f930  call    cs:__imp_ExReleaseResourceLite
0x14001f937  nop     dword ptr [rax+rax+00h]
0x14001f93c  call    cs:__imp_KeLeaveCriticalRegion
0x14001f943  nop     dword ptr [rax+rax+00h]
0x14001f948  mov     eax, r14d
0x14001f94b  add     rsp, 38h
0x14001f94f  pop     r15
0x14001f951  pop     r14
0x14001f953  pop     r13
0x14001f955  pop     r12
0x14001f957  pop     rdi
0x14001f958  pop     rsi
0x14001f959  pop     rbp
0x14001f95a  pop     rbx
0x14001f95b  retn
0x14001f95d  mov     rcx, rbp
0x14001f960  jmp     short loc_14001F8E5
0x14001f962  test    dword ptr [rcx+2Ch], 400000h
0x14001f969  jnz     short loc_14001F974
0x14001f96b  lea     rax, WPP_GLOBAL_Control
0x14001f972  jmp     short loc_14001F91E
0x14001f974  mov     eax, [rbx+90h]
0x14001f97a  mov     edx, 0Dh
0x14001f97f  mov     rcx, [rcx+18h]
0x14001f983  mov     r9, rbx
0x14001f986  mov     [rsp+78h+var_50], eax
0x14001f98a  mov     dword ptr [rsp+78h+var_58], edi
0x14001f98e  call    WPP_SF_qdd
0x14001f993  jmp     short loc_14001F96B
0x14001f995  lea     rbp, [rsi+98h]
0x14001f99c  jmp     short loc_14001F92D
0x14001f99e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f9a5  xor     r15d, r15d
0x14001f9a8  cmp     rcx, rax
0x14001f9ab  jz      short loc_14001F9D7
0x14001f9ad  test    dword ptr [rcx+2Ch], 400000h
0x14001f9b4  jz      short loc_14001F9D0
0x14001f9b6  mov     rcx, [rcx+18h]
0x14001f9ba  mov     edx, 0Eh
0x14001f9bf  mov     [rsp+78h+var_50], r12d
0x14001f9c4  mov     r9, rbx
0x14001f9c7  mov     dword ptr [rsp+78h+var_58], edi
0x14001f9cb  call    WPP_SF_qdd
0x14001f9d0  lea     rax, WPP_GLOBAL_Control
0x14001f9d7  test    r13, r13
0x14001f9da  jz      short loc_14001FA22
0x14001f9dc  cmp     [rbx+78h], r14
0x14001f9e0  jz      short loc_14001FA22
0x14001f9e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f9e9  cmp     rcx, rax
0x14001f9ec  jz      short loc_14001FA0F
0x14001f9ee  test    dword ptr [rcx+2Ch], 400000h
0x14001f9f5  jz      short loc_14001FA0F
0x14001f9f7  mov     rcx, [rcx+18h]
0x14001f9fb  lea     r8, WPP_87cf2b6004dc3e7f3eb3e63342a64277_Traceguids
0x14001fa02  mov     edx, 0Fh
0x14001fa07  mov     r9, rbx
0x14001fa0a  call    WPP_SF_q
0x14001fa0f  mov     rcx, [rbx+78h]; BugCheckParameter2
0x14001fa13  mov     rdx, rbx; BugCheckParameter3
0x14001fa16  call    DfscNetUseTableDelete
0x14001fa1b  lea     rax, WPP_GLOBAL_Control
0x14001fa22  test    r12b, r12b
0x14001fa25  jz      short loc_14001FA81
0x14001fa27  mov     r9, [rbx+70h]
0x14001fa2b  test    r9, r9
0x14001fa2e  jz      short loc_14001FA6F
0x14001fa30  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fa37  cmp     rcx, rax
0x14001fa3a  jz      short loc_14001FA5F
0x14001fa3c  test    dword ptr [rcx+2Ch], 400000h
0x14001fa43  jz      short loc_14001FA5F
0x14001fa45  mov     rcx, [rcx+18h]
0x14001fa49  lea     r8, WPP_87cf2b6004dc3e7f3eb3e63342a64277_Traceguids
0x14001fa50  mov     edx, 10h
0x14001fa55  mov     [rsp+78h+var_58], rbx
0x14001fa5a  call    WPP_SF_qq
0x14001fa5f  mov     rcx, [rbx+70h]; BugCheckParameter3
0x14001fa63  call    DfscCredRelease
0x14001fa68  mov     r14d, eax
0x14001fa6b  mov     [rbx+70h], r15
0x14001fa6f  mov     r15, [rbx+88h]
0x14001fa76  mov     qword ptr [rbx+88h], 0
0x14001fa81  test    rsi, rsi
0x14001fa84  jz      short loc_14001FA8D
0x14001fa86  lea     rbp, [rsi+98h]
0x14001fa8d  mov     rcx, rbp; Resource
0x14001fa90  call    cs:__imp_ExReleaseResourceLite
0x14001fa97  nop     dword ptr [rax+rax+00h]
0x14001fa9c  call    cs:__imp_KeLeaveCriticalRegion
0x14001faa3  nop     dword ptr [rax+rax+00h]
0x14001faa8  test    r15, r15
0x14001faab  jz      short loc_14001FAF7
0x14001faad  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fab4  lea     rsi, WPP_GLOBAL_Control
0x14001fabb  cmp     rcx, rsi
0x14001fabe  jz      short loc_14001FAE6
0x14001fac0  test    dword ptr [rcx+2Ch], 400000h
0x14001fac7  jz      short loc_14001FAE6
0x14001fac9  mov     rcx, [rcx+18h]
0x14001facd  lea     r8, WPP_87cf2b6004dc3e7f3eb3e63342a64277_Traceguids
0x14001fad4  mov     edx, 11h
0x14001fad9  mov     [rsp+78h+var_58], rbx
0x14001fade  mov     r9, r15
0x14001fae1  call    WPP_SF_qq
0x14001fae6  mov     rcx, r15; Handle
0x14001fae9  call    cs:__imp_ZwClose
0x14001faf0  nop     dword ptr [rax+rax+00h]
0x14001faf5  jmp     short loc_14001FAFE
0x14001faf7  lea     rsi, WPP_GLOBAL_Control
0x14001fafe  test    edi, edi
0x14001fb00  jnz     loc_14001F948
0x14001fb06  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fb0d  cmp     rcx, rsi
0x14001fb10  jz      short loc_14001FB33
0x14001fb12  test    dword ptr [rcx+2Ch], 400000h
0x14001fb19  jz      short loc_14001FB33
0x14001fb1b  mov     rcx, [rcx+18h]
0x14001fb1f  lea     r8, WPP_87cf2b6004dc3e7f3eb3e63342a64277_Traceguids
0x14001fb26  mov     edx, 12h
0x14001fb2b  mov     r9, rbx
0x14001fb2e  call    WPP_SF_q
0x14001fb33  xor     edx, edx; Tag
0x14001fb35  mov     rcx, rbx; P
0x14001fb38  call    cs:__imp_ExFreePoolWithTag
0x14001fb3f  nop     dword ptr [rax+rax+00h]
0x14001fb44  jmp     loc_14001F948
```
