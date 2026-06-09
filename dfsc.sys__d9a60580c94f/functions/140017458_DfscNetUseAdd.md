# DfscNetUseAdd

- ea: `0x140017458`
- end: `0x14001778f`
- name: `DfscNetUseAdd`
- size: `823`
- prototype: `__int64 __fastcall(__int64, DWORD, struct _LUID *, unsigned __int16 *, __int64, __int64, __int64, int, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x14001338c`

## callees

- `0x1400049a8`
- `0x140004b18`
- `0x140004bd4`
- `0x140004c88`
- `0x140011a34`
- `0x140012158`
- `0x140017458`
- `0x140017798`
- `0x140017dfc`
- `0x14001824c`
- `0x14001f8a0`
- `0x1400252b0`
- `0x140025d4c`
- `0x140025efc`
- `0x140026ed0`

## import_xrefs

- `ntoskrnl!RtlCopyLuid` at `0x1400174e6`
- `ntoskrnl!RtlCopyLuid` at `0x1400174e6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140017765`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140017765`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017759`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017759`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140017519`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140017519`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400174f5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400174f5`

## pseudocode

```c
__int64 __fastcall DfscNetUseAdd(
        __int64 a1,
        DWORD a2,
        struct _LUID *a3,
        unsigned __int16 *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int a8,
        __int64 a9,
        _BYTE *a10)
{
  __int64 v11; // rdx
  ULONG_PTR v15; // rbx
  __int64 DriveLetterNetUseTable; // rax
  __int128 *v17; // rdx
  __int128 v18; // xmm0
  __int64 v19; // r9
  struct _ERESOURCE *p_WaitListHead; // r13
  struct _ERESOURCE *v21; // rcx
  ULONG_PTR CredTable; // rax
  unsigned int KeymgrCredentials; // eax
  __int64 v24; // r8
  ULONG_PTR v25; // r14
  unsigned int v26; // edi
  ULONG_PTR v27; // rax
  int v28; // edx
  int v29; // r8d
  int v30; // eax
  int DevicelessNetUseTable; // eax
  unsigned int v32; // eax
  int v33; // edx
  ULONG_PTR BugCheckParameter2; // [rsp+48h] [rbp-49h]
  ULONG_PTR BugCheckParameter3; // [rsp+50h] [rbp-41h] BYREF
  __int64 v37; // [rsp+58h] [rbp-39h] BYREF
  ULONG_PTR BugCheckParameter4[2]; // [rsp+60h] [rbp-31h] BYREF
  struct _LUID DestinationLuid[2]; // [rsp+70h] [rbp-21h] BYREF
  __int128 v40; // [rsp+80h] [rbp-11h]
  TABLE_SEARCH_RESULT v41; // [rsp+D8h] [rbp+47h] BYREF
  DWORD v42; // [rsp+E0h] [rbp+4Fh]
  unsigned __int16 *v43; // [rsp+F0h] [rbp+5Fh]

  v43 = a4;
  v42 = a2;
  BugCheckParameter3 = 0;
  v37 = 0;
  v11 = a6;
  *a10 = 0;
  v41 = TableEmptyTree;
  v15 = 0;
  *(_OWORD *)BugCheckParameter4 = 0;
  *(_OWORD *)&DestinationLuid[0].LowPart = 0;
  v40 = 0;
  if ( v11 )
  {
    DriveLetterNetUseTable = DfscGetDriveLetterNetUseTable(a1);
    v18 = *v17;
    DWORD2(v40) = 1;
  }
  else
  {
    DriveLetterNetUseTable = DfscGetDevicelessNetUseTable(a1);
    v18 = *(_OWORD *)(v19 + 80);
  }
  BugCheckParameter2 = DriveLetterNetUseTable;
  *(_OWORD *)BugCheckParameter4 = v18;
  RtlCopyLuid((PLUID)&DestinationLuid[0].HighPart, a3);
  DestinationLuid[0].LowPart = a2;
  KeEnterCriticalRegion();
  p_WaitListHead = (struct _ERESOURCE *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
  v21 = (struct _ERESOURCE *)(a1 + 152);
  if ( !a1 )
    v21 = (struct _ERESOURCE *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
  ExAcquireResourceExclusiveLite(v21, 1u);
  CredTable = DfscGetCredTable(a1);
  KeymgrCredentials = DfscCredGetKeymgrCredentials(CredTable, a2, a3, a4, a7, &BugCheckParameter3);
  v25 = BugCheckParameter3;
  v26 = KeymgrCredentials;
  if ( !KeymgrCredentials )
  {
    v27 = DfscNetUseTableLookup(BugCheckParameter2, BugCheckParameter4, &v37, &v41);
    BugCheckParameter3 = v27;
    v15 = v27;
    if ( v27 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u) )
      {
        WPP_SF_qZq(WPP_GLOBAL_Control->AttachedDevice, 11, v27 + 88, v27, v27 + 88, *(_QWORD *)(v27 + 112));
      }
      if ( v25 )
      {
        if ( !*(_QWORD *)(v15 + 112) )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v25 + 4));
          *(_QWORD *)(v15 + 112) = v25;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u) )
              WPP_SF_qZqD(WPP_GLOBAL_Control->AttachedDevice, v28, v29, v15, v15 + 88, v25, 0);
          }
        }
      }
      v26 = DfscTransportConflictDetect(v15, a9);
    }
    else
    {
      v30 = DfscGetDriveLetterNetUseTable(a1);
      v26 = DfscNetUseTableConflictDetect(v30, a7, v42, (_DWORD)a3, a9);
      if ( !v26 )
      {
        DevicelessNetUseTable = DfscGetDevicelessNetUseTable(a1);
        v26 = DfscNetUseTableConflictDetect(DevicelessNetUseTable, a7, v42, (_DWORD)a3, a9);
        if ( !v26 )
        {
          v32 = DfscNetUseCreate((_DWORD)a4, a6, a5, v25, a8, a9, (__int64)&BugCheckParameter3);
          v15 = BugCheckParameter3;
          v26 = v32;
          if ( !v32 )
          {
            v26 = DfscNetUseTableStore(BugCheckParameter2, BugCheckParameter3, (ULONG_PTR)BugCheckParameter4, v41);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u) )
            {
              WPP_SF_qZD(WPP_GLOBAL_Control->AttachedDevice, v33, v24, v15, (__int64)(v43 + 40), v26);
            }
            if ( !v26 )
              *a10 = 1;
          }
        }
      }
    }
  }
  if ( v25 )
    DfscCredRelease(v25);
  if ( v15 )
  {
    LOBYTE(v24) = v26 != 0;
    DfscNetUseRelease(a1, v15, v24, 0);
  }
  if ( a1 )
    p_WaitListHead = (struct _ERESOURCE *)(a1 + 152);
  ExReleaseResourceLite(p_WaitListHead);
  KeLeaveCriticalRegion();
  return v26;
}

```

## disassembly

```asm
0x140017458  mov     rax, rsp
0x14001745b  mov     [rax+18h], rbx
0x14001745f  mov     [rax+20h], r9
0x140017463  mov     [rax+10h], edx
0x140017466  push    rbp
0x140017467  push    rsi
0x140017468  push    rdi
0x140017469  push    r12
0x14001746b  push    r13
0x14001746d  push    r14
0x14001746f  push    r15
0x140017471  lea     rbp, [rax-3Fh]
0x140017475  sub     rsp, 90h
0x14001747c  mov     rax, [rbp+37h+arg_48]
0x140017483  xor     r14d, r14d
0x140017486  xorps   xmm0, xmm0
0x140017489  mov     [rbp+37h+BugCheckParameter3], r14
0x14001748d  mov     edi, edx
0x14001748f  mov     [rbp+37h+var_70], r14
0x140017493  mov     rdx, [rbp+37h+arg_28]
0x140017497  mov     r15, r9
0x14001749a  mov     [rax], r14b
0x14001749d  mov     r12, r8
0x1400174a0  mov     [rbp+37h+arg_0], r14d
0x1400174a4  mov     rsi, rcx
0x1400174a7  mov     ebx, r14d
0x1400174aa  movups  xmmword ptr [rbp+37h+BugCheckParameter4], xmm0
0x1400174ae  movups  xmmword ptr [rbp+37h+DestinationLuid.LowPart], xmm0
0x1400174b2  movups  [rbp+37h+var_48], xmm0
0x1400174b6  test    rdx, rdx
0x1400174b9  jz      short loc_1400174CC
0x1400174bb  call    DfscGetDriveLetterNetUseTable
0x1400174c0  movups  xmm0, xmmword ptr [rdx]
0x1400174c3  mov     dword ptr [rbp+37h+var_48+8], 1
0x1400174ca  jmp     short loc_1400174D6
0x1400174cc  call    DfscGetDevicelessNetUseTable
0x1400174d1  movups  xmm0, xmmword ptr [r9+50h]
0x1400174d6  mov     rdx, r12; SourceLuid
0x1400174d9  mov     [rbp+37h+BugCheckParameter2], rax
0x1400174dd  lea     rcx, [rbp+37h+DestinationLuid.HighPart]; DestinationLuid
0x1400174e1  movdqu  xmmword ptr [rbp+37h+BugCheckParameter4], xmm0
0x1400174e6  call    cs:__imp_RtlCopyLuid
0x1400174ed  nop     dword ptr [rax+rax+00h]
0x1400174f2  mov     [rbp+37h+DestinationLuid.LowPart], edi
0x1400174f5  call    cs:__imp_KeEnterCriticalRegion
0x1400174fc  nop     dword ptr [rax+rax+00h]
0x140017501  lea     r13, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140017508  lea     rcx, [rsi+98h]
0x14001750f  test    rsi, rsi
0x140017512  jnz     short loc_140017517
0x140017514  mov     rcx, r13; Resource
0x140017517  mov     dl, 1; Wait
0x140017519  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140017520  nop     dword ptr [rax+rax+00h]
0x140017525  mov     rcx, rsi
0x140017528  call    DfscGetCredTable
0x14001752d  mov     rcx, rax; BugCheckParameter2
0x140017530  mov     r9, r15
0x140017533  lea     rax, [rbp+37h+BugCheckParameter3]
0x140017537  mov     r8, r12
0x14001753a  mov     [rsp+0C0h+var_98], rax; BugCheckParameter3
0x14001753f  mov     edx, edi
0x140017541  mov     rax, [rbp+37h+arg_30]
0x140017545  mov     qword ptr [rsp+0C0h+var_A0], rax; __int64
0x14001754a  call    DfscCredGetKeymgrCredentials
0x14001754f  mov     r14, [rbp+37h+BugCheckParameter3]
0x140017553  mov     edi, eax
0x140017555  test    eax, eax
0x140017557  jnz     loc_140017724
0x14001755d  mov     rcx, [rbp+37h+BugCheckParameter2]
0x140017561  lea     r9, [rbp+37h+arg_0]
0x140017565  lea     r8, [rbp+37h+var_70]
0x140017569  lea     rdx, [rbp+37h+BugCheckParameter4]
0x14001756d  call    DfscNetUseTableLookup
0x140017572  mov     [rbp+37h+BugCheckParameter3], rax
0x140017576  mov     rbx, rax
0x140017579  test    rax, rax
0x14001757c  jnz     loc_14001768C
0x140017582  mov     rcx, rsi
0x140017585  call    DfscGetDriveLetterNetUseTable
0x14001758a  mov     r8d, [rbp+37h+arg_8]
0x14001758e  mov     rcx, rax
0x140017591  mov     rax, [rbp+37h+arg_40]
0x140017598  mov     r9, r12
0x14001759b  mov     rdx, [rbp+37h+arg_30]
0x14001759f  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1400175a4  call    DfscNetUseTableConflictDetect
0x1400175a9  mov     edi, eax
0x1400175ab  test    eax, eax
0x1400175ad  jnz     loc_140017724
0x1400175b3  mov     rcx, rsi
0x1400175b6  call    DfscGetDevicelessNetUseTable
0x1400175bb  mov     r8d, [rbp+37h+arg_8]
0x1400175bf  mov     rcx, rax
0x1400175c2  mov     rax, [rbp+37h+arg_40]
0x1400175c9  mov     r9, r12
0x1400175cc  mov     rdx, [rbp+37h+arg_30]
0x1400175d0  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1400175d5  call    DfscNetUseTableConflictDetect
0x1400175da  mov     edi, eax
0x1400175dc  test    eax, eax
0x1400175de  jnz     loc_140017724
0x1400175e4  mov     r8, [rbp+37h+arg_20]
0x1400175e8  lea     rax, [rbp+37h+BugCheckParameter3]
0x1400175ec  mov     rdx, [rbp+37h+arg_28]
0x1400175f0  mov     r9, r14
0x1400175f3  mov     [rsp+30h], rax
0x1400175f8  mov     rcx, r15
0x1400175fb  mov     rax, [rbp+37h+arg_40]
0x140017602  mov     [rsp+0C0h+var_98], rax
0x140017607  mov     eax, [rbp+37h+arg_38]
0x14001760a  mov     [rsp+0C0h+var_A0], eax
0x14001760e  call    DfscNetUseCreate
0x140017613  mov     rbx, [rbp+37h+BugCheckParameter3]
0x140017617  mov     edi, eax
0x140017619  test    eax, eax
0x14001761b  jnz     loc_140017724
0x140017621  mov     eax, [rbp+37h+arg_0]
0x140017624  lea     r8, [rbp+37h+BugCheckParameter4]; BugCheckParameter4
0x140017628  mov     r9, [rbp+37h+var_70]
0x14001762c  mov     rdx, rbx; BugCheckParameter3
0x14001762f  mov     rcx, [rbp+37h+BugCheckParameter2]; BugCheckParameter2
0x140017633  mov     [rsp+0C0h+var_A0], eax; TABLE_SEARCH_RESULT
0x140017637  call    DfscNetUseTableStore
0x14001763c  mov     edi, eax
0x14001763e  mov     rcx, cs:WPP_GLOBAL_Control
0x140017645  lea     r12, WPP_GLOBAL_Control
0x14001764c  cmp     rcx, r12
0x14001764f  jz      short loc_140017675
0x140017651  bt      dword ptr [rcx+2Ch], 16h
0x140017656  jnb     short loc_140017675
0x140017658  mov     rax, [rbp+37h+arg_18]
0x14001765c  mov     r9, rbx
0x14001765f  mov     rcx, [rcx+18h]
0x140017663  add     rax, 50h ; 'P'
0x140017667  mov     dword ptr [rsp+0C0h+var_98], edi
0x14001766b  mov     qword ptr [rsp+0C0h+var_A0], rax
0x140017670  call    WPP_SF_qZD
0x140017675  test    edi, edi
0x140017677  jnz     loc_140017724
0x14001767d  mov     rax, [rbp+37h+arg_48]
0x140017684  mov     byte ptr [rax], 1
0x140017687  jmp     loc_140017724
0x14001768c  mov     rcx, cs:WPP_GLOBAL_Control
0x140017693  lea     r12, WPP_GLOBAL_Control
0x14001769a  cmp     rcx, r12
0x14001769d  jz      short loc_1400176C9
0x14001769f  bt      dword ptr [rcx+2Ch], 16h
0x1400176a4  jnb     short loc_1400176C9
0x1400176a6  mov     rcx, [rcx+18h]
0x1400176aa  lea     r8, [rax+58h]
0x1400176ae  mov     rax, [rax+70h]
0x1400176b2  mov     edx, 0Bh
0x1400176b7  mov     [rsp+0C0h+var_98], rax
0x1400176bc  mov     r9, rbx
0x1400176bf  mov     qword ptr [rsp+0C0h+var_A0], r8
0x1400176c4  call    WPP_SF_qZq
0x1400176c9  test    r14, r14
0x1400176cc  jz      short loc_140017713
0x1400176ce  cmp     qword ptr [rbx+70h], 0
0x1400176d3  jnz     short loc_140017713
0x1400176d5  lock inc dword ptr [r14+4]
0x1400176da  mov     [rbx+70h], r14
0x1400176de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400176e5  cmp     rcx, r12
0x1400176e8  jz      short loc_140017713
0x1400176ea  bt      dword ptr [rcx+2Ch], 16h
0x1400176ef  jnb     short loc_140017713
0x1400176f1  mov     rcx, [rcx+18h]
0x1400176f5  lea     rax, [rbx+58h]
0x1400176f9  mov     dword ptr [rsp+30h], 0
0x140017701  mov     r9, rbx
0x140017704  mov     [rsp+0C0h+var_98], r14
0x140017709  mov     qword ptr [rsp+0C0h+var_A0], rax
0x14001770e  call    WPP_SF_qZqD
0x140017713  mov     rdx, [rbp+37h+arg_40]
0x14001771a  mov     rcx, rbx
0x14001771d  call    DfscTransportConflictDetect
0x140017722  mov     edi, eax
0x140017724  test    r14, r14
0x140017727  jz      short loc_140017731
0x140017729  mov     rcx, r14; BugCheckParameter3
0x14001772c  call    DfscCredRelease
0x140017731  test    rbx, rbx
0x140017734  jz      short loc_14001774A
0x140017736  test    edi, edi
0x140017738  mov     rdx, rbx
0x14001773b  mov     rcx, rsi
0x14001773e  setnz   r8b
0x140017742  xor     r9d, r9d
0x140017745  call    DfscNetUseRelease
0x14001774a  test    rsi, rsi
0x14001774d  jz      short loc_140017756
0x14001774f  lea     r13, [rsi+98h]
0x140017756  mov     rcx, r13; Resource
0x140017759  call    cs:__imp_ExReleaseResourceLite
0x140017760  nop     dword ptr [rax+rax+00h]
0x140017765  call    cs:__imp_KeLeaveCriticalRegion
0x14001776c  nop     dword ptr [rax+rax+00h]
0x140017771  mov     rbx, [rsp+0C0h+arg_10]
0x140017779  mov     eax, edi
0x14001777b  add     rsp, 90h
0x140017782  pop     r15
0x140017784  pop     r14
0x140017786  pop     r13
0x140017788  pop     r12
0x14001778a  pop     rdi
0x14001778b  pop     rsi
0x14001778c  pop     rbp
0x14001778d  retn
```
