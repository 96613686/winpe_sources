# HsmFltProcessCreatePlaceholders

- ea: `0x14006049c`
- end: `0x1400608b6`
- name: `HsmFltProcessCreatePlaceholders`
- size: `1050`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, PVOID Object, HANDLE FileHandle, PFLT_CALLBACK_DATA CallbackData, __int64, unsigned int, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14004dff0`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x140050dc0`
- `0x140052574`
- `0x14005ce40`
- `0x14005ec60`
- `0x14006049c`
- `0x1400608bc`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400606eb`
- `ntoskrnl!ObfDereferenceObject` at `0x1400606eb`
- `FLTMGR!FltClose` at `0x140060704`
- `FLTMGR!FltClose` at `0x140060704`
- `FLTMGR!FltGetRequestorProcess` at `0x140060621`
- `FLTMGR!FltGetRequestorProcess` at `0x140060621`
- `FLTMGR!FltReleasePushLockEx` at `0x1400606d7`
- `FLTMGR!FltReleasePushLockEx` at `0x1400606d7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400605bb`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400605bb`

## pseudocode

```c
__int64 __fastcall HsmFltProcessCreatePlaceholders(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        PVOID Object,
        HANDLE FileHandle,
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a9,
        unsigned int a10,
        char a11)
{
  PVOID v11; // r14
  int SyncPolicy; // edi
  PDEVICE_OBJECT v15; // rcx
  __int64 v17; // r12
  __int64 v18; // r13
  int v19; // r12d
  char v20; // bl
  unsigned int RequestorProcess; // eax
  unsigned int v22; // r12d
  __int64 v23; // r8
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rdx
  void *v27; // [rsp+30h] [rbp-20h]
  int v28; // [rsp+90h] [rbp+40h] BYREF
  int v29; // [rsp+94h] [rbp+44h]
  int v30; // [rsp+A8h] [rbp+58h] BYREF
  int v31; // [rsp+ACh] [rbp+5Ch]

  v31 = HIDWORD(a4);
  v29 = HIDWORD(a1);
  v11 = 0;
  v30 = 0;
  FileHandle = 0;
  Object = 0;
  v28 = 0;
  if ( a10 < 0x20 || (v17 = a9, *(_DWORD *)(a9 + 16) < 0x50u) )
  {
    SyncPolicy = -1073688821;
    HsmDbgBreakOnStatus(-1073688821);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return (unsigned int)SyncPolicy;
    }
    v26 = 128;
    goto LABEL_53;
  }
  SyncPolicy = HsmpRelativeStreamOpen(a2, a3, 0, 0x100000, 1u, 32, v27, (__int64)&FileHandle, (__int64)&Object);
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( SyncPolicy < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        129,
        WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
        a2,
        CallbackData,
        a3,
        SyncPolicy);
    }
    v11 = Object;
    goto LABEL_22;
  }
  v11 = Object;
  SyncPolicy = HsmpPrepareForMgmtOperation(a2, Object, 8);
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( SyncPolicy >= 0 )
  {
    v18 = a5;
    a11 = 0;
    if ( a5 )
    {
      FltAcquirePushLockExclusiveEx(*(_QWORD *)(a5 + 16) + 24LL, 0);
      a11 = 1;
    }
    v19 = *(_DWORD *)(v17 + 8);
    SyncPolicy = HsmpCldGetSyncPolicy(a2, v18, a3, 5, (__int64)&v30);
    HsmDbgBreakOnStatus(SyncPolicy);
    if ( SyncPolicy < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v25 = 132;
LABEL_49:
        WPP_SF_qqqd(
          v24->AttachedDevice,
          v25,
          WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
          a2,
          CallbackData,
          a3,
          SyncPolicy);
      }
    }
    else
    {
      v20 = v30;
      if ( (v30 & 0x8000000) != 0 )
      {
LABEL_15:
        v22 = v19 & 1;
        if ( (v20 & 0xFu) < 4 )
          v22 |= 2u;
        v23 = v22 | 4;
        if ( (v20 & 0xF0u) >= 0x40 )
          v23 = v22;
        SyncPolicy = HsmpOpCreatePlaceholders(a2, FileHandle, v23, *(_QWORD *)(a9 + 24), *(_DWORD *)(a9 + 16), &v28);
        HsmDbgBreakOnStatus(SyncPolicy);
        if ( SyncPolicy >= 0 )
          goto LABEL_20;
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_20;
        }
        v25 = 134;
        goto LABEL_49;
      }
      RequestorProcess = (unsigned int)CallbackData;
      LOBYTE(a10) = 0;
      if ( CallbackData )
        RequestorProcess = (unsigned int)FltGetRequestorProcess(CallbackData);
      SyncPolicy = HsmpCldCheckSyncProviderAccess(a2, v18, a3, RequestorProcess, (__int64)&a10);
      HsmDbgBreakOnStatus(SyncPolicy);
      if ( SyncPolicy >= 0 )
      {
        if ( (_BYTE)a10 )
          goto LABEL_15;
        SyncPolicy = -1073688808;
        HsmDbgBreakOnStatus(-1073688808);
      }
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v25 = 133;
        goto LABEL_49;
      }
    }
LABEL_20:
    if ( a11 )
      FltReleasePushLockEx(*(_QWORD *)(v18 + 16) + 24LL, 0);
    goto LABEL_22;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v26 = 130;
LABEL_53:
    WPP_SF_qqqd(
      v15->AttachedDevice,
      v26,
      WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
      a2,
      CallbackData,
      a3,
      SyncPolicy);
  }
LABEL_22:
  if ( v11 )
    ObfDereferenceObject(v11);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)SyncPolicy;
}

```

## disassembly

```asm
0x14006049c  mov     [rsp-38h+arg_8], rbx
0x1400604a1  mov     [rsp-38h+arg_18], r9
0x1400604a6  mov     [rsp-38h+arg_0], rcx
0x1400604ab  push    rbp
0x1400604ac  push    rsi
0x1400604ad  push    rdi
0x1400604ae  push    r12
0x1400604b0  push    r13
0x1400604b2  push    r14
0x1400604b4  push    r15
0x1400604b6  mov     rbp, rsp
0x1400604b9  sub     rsp, 50h
0x1400604bd  xor     r14d, r14d
0x1400604c0  mov     dword ptr [rbp+arg_18], 0
0x1400604c7  cmp     [rbp+arg_48], 20h ; ' '
0x1400604ce  mov     r15, r8
0x1400604d1  mov     rsi, rdx
0x1400604d4  mov     [rbp+FileHandle], 0
0x1400604dc  mov     [rbp+Object], r14
0x1400604e0  mov     dword ptr [rbp+arg_0], r14d
0x1400604e4  jnb     short loc_140060524
0x1400604e6  mov     edi, 0C000CF0Bh
0x1400604eb  mov     ecx, edi
0x1400604ed  call    HsmDbgBreakOnStatus
0x1400604f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400604f9  lea     rax, WPP_GLOBAL_Control
0x140060500  cmp     rcx, rax
0x140060503  jnz     loc_140060872
0x140060509  mov     rbx, [rsp+50h+arg_8]
0x140060511  mov     eax, edi
0x140060513  add     rsp, 50h
0x140060517  pop     r15
0x140060519  pop     r14
0x14006051b  pop     r13
0x14006051d  pop     r12
0x14006051f  pop     rdi
0x140060520  pop     rsi
0x140060521  pop     rbp
0x140060522  retn
0x140060524  mov     r12, [rbp+arg_40]
0x14006052b  cmp     dword ptr [r12+10h], 50h ; 'P'
0x140060531  jb      short loc_1400604E6
0x140060533  lea     rax, [rbp+Object]
0x140060537  mov     r9d, 100000h; int
0x14006053d  mov     [rsp+50h+var_10], rax; __int64
0x140060542  xor     r8d, r8d; int
0x140060545  lea     rax, [rbp+FileHandle]
0x140060549  mov     rdx, r15; int
0x14006054c  mov     [rsp+50h+var_18], rax; __int64
0x140060551  mov     rcx, rsi; int
0x140060554  mov     [rsp+50h+var_28], 20h ; ' '; int
0x14006055c  mov     [rsp+50h+var_30], 1; ULONG
0x140060564  call    HsmpRelativeStreamOpen
0x140060569  mov     ecx, eax
0x14006056b  mov     edi, eax
0x14006056d  call    HsmDbgBreakOnStatus
0x140060572  test    edi, edi
0x140060574  js      loc_14006077A
0x14006057a  mov     r14, [rbp+Object]
0x14006057e  xor     r9d, r9d
0x140060581  mov     rdx, r14
0x140060584  mov     rcx, rsi
0x140060587  lea     r8d, [r9+8]
0x14006058b  call    HsmpPrepareForMgmtOperation
0x140060590  mov     ecx, eax
0x140060592  mov     edi, eax
0x140060594  call    HsmDbgBreakOnStatus
0x140060599  test    edi, edi
0x14006059b  js      loc_1400607D0
0x1400605a1  mov     r13, [rbp+arg_20]
0x1400605a5  mov     [rbp+arg_50], 0
0x1400605ac  test    r13, r13
0x1400605af  jz      short loc_1400605CE
0x1400605b1  mov     rcx, [r13+10h]
0x1400605b5  xor     edx, edx
0x1400605b7  add     rcx, 18h
0x1400605bb  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400605c2  nop     dword ptr [rax+rax+00h]
0x1400605c7  mov     [rbp+arg_50], 1
0x1400605ce  mov     r12d, [r12+8]
0x1400605d3  lea     rax, [rbp+arg_18]
0x1400605d7  mov     r9d, 5
0x1400605dd  mov     qword ptr [rsp+50h+var_30], rax
0x1400605e2  mov     r8, r15
0x1400605e5  mov     rdx, r13
0x1400605e8  mov     rcx, rsi
0x1400605eb  call    HsmpCldGetSyncPolicy
0x1400605f0  mov     ecx, eax
0x1400605f2  mov     edi, eax
0x1400605f4  call    HsmDbgBreakOnStatus
0x1400605f9  test    edi, edi
0x1400605fb  js      loc_140060715
0x140060601  mov     ebx, dword ptr [rbp+arg_18]
0x140060604  bt      ebx, 1Bh
0x140060608  jb      short loc_140060668
0x14006060a  mov     rax, [rbp+CallbackData]
0x14006060e  mov     byte ptr [rbp+arg_48], 0
0x140060615  test    rax, rax
0x140060618  jz      loc_140060775
0x14006061e  mov     rcx, rax; CallbackData
0x140060621  call    cs:__imp_FltGetRequestorProcess
0x140060628  nop     dword ptr [rax+rax+00h]
0x14006062d  lea     rcx, [rbp+arg_48]
0x140060634  mov     r9, rax
0x140060637  mov     qword ptr [rsp+50h+var_30], rcx
0x14006063c  mov     r8, r15
0x14006063f  mov     rcx, rsi
0x140060642  mov     rdx, r13
0x140060645  call    HsmpCldCheckSyncProviderAccess
0x14006064a  mov     ecx, eax
0x14006064c  mov     edi, eax
0x14006064e  call    HsmDbgBreakOnStatus
0x140060653  test    edi, edi
0x140060655  js      loc_14006073F
0x14006065b  cmp     byte ptr [rbp+arg_48], 0
0x140060662  jz      loc_140060806
0x140060668  mov     eax, ebx
0x14006066a  and     r12d, 1
0x14006066e  and     al, 0Fh
0x140060670  cmp     al, 4
0x140060672  jnb     short loc_140060678
0x140060674  or      r12d, 2
0x140060678  mov     rcx, [rbp+arg_40]
0x14006067f  lea     rax, [rbp+arg_0]
0x140060683  mov     rdx, [rbp+FileHandle]
0x140060687  mov     r8d, r12d
0x14006068a  or      r8d, 4
0x14006068e  mov     qword ptr [rsp+50h+var_28], rax
0x140060693  and     ebx, 0F0h
0x140060699  mov     eax, [rcx+10h]
0x14006069c  cmp     ebx, 40h ; '@'
0x14006069f  mov     r9, [rcx+18h]
0x1400606a3  mov     rcx, rsi
0x1400606a6  cmovnb  r8d, r12d
0x1400606aa  mov     [rsp+50h+var_30], eax
0x1400606ae  call    HsmpOpCreatePlaceholders
0x1400606b3  mov     ecx, eax
0x1400606b5  mov     edi, eax
0x1400606b7  call    HsmDbgBreakOnStatus
0x1400606bc  test    edi, edi
0x1400606be  js      loc_140060817
0x1400606c4  cmp     [rbp+arg_50], 0
0x1400606cb  jz      short loc_1400606E3
0x1400606cd  mov     rcx, [r13+10h]
0x1400606d1  xor     edx, edx
0x1400606d3  add     rcx, 18h
0x1400606d7  call    cs:__imp_FltReleasePushLockEx
0x1400606de  nop     dword ptr [rax+rax+00h]
0x1400606e3  test    r14, r14
0x1400606e6  jz      short loc_1400606F7
0x1400606e8  mov     rcx, r14; Object
0x1400606eb  call    cs:__imp_ObfDereferenceObject
0x1400606f2  nop     dword ptr [rax+rax+00h]
0x1400606f7  mov     rcx, [rbp+FileHandle]; FileHandle
0x1400606fb  test    rcx, rcx
0x1400606fe  jz      loc_140060509
0x140060704  call    cs:__imp_FltClose
0x14006070b  nop     dword ptr [rax+rax+00h]
0x140060710  jmp     loc_140060509
0x140060715  mov     rcx, cs:WPP_GLOBAL_Control
0x14006071c  lea     rax, WPP_GLOBAL_Control
0x140060723  cmp     rcx, rax
0x140060726  jz      short loc_1400606C4
0x140060728  mov     eax, [rcx+2Ch]
0x14006072b  test    al, 1
0x14006072d  jz      short loc_1400606C4
0x14006072f  cmp     byte ptr [rcx+29h], 2
0x140060733  jb      short loc_1400606C4
0x140060735  mov     edx, 84h
0x14006073a  jmp     loc_140060848
0x14006073f  mov     rcx, cs:WPP_GLOBAL_Control
0x140060746  lea     rax, WPP_GLOBAL_Control
0x14006074d  cmp     rcx, rax
0x140060750  jz      loc_1400606C4
0x140060756  mov     eax, [rcx+2Ch]
0x140060759  test    al, 1
0x14006075b  jz      loc_1400606C4
0x140060761  cmp     byte ptr [rcx+29h], 2
0x140060765  jb      loc_1400606C4
0x14006076b  mov     edx, 85h
0x140060770  jmp     loc_140060848
0x140060775  jmp     loc_14006062D
0x14006077a  mov     r10, cs:WPP_GLOBAL_Control
0x140060781  lea     rax, WPP_GLOBAL_Control
0x140060788  cmp     r10, rax
0x14006078b  jz      short loc_1400607C7
0x14006078d  mov     ecx, [r10+2Ch]
0x140060791  test    cl, 1
0x140060794  jz      short loc_1400607C7
0x140060796  cmp     byte ptr [r10+29h], 2
0x14006079b  jb      short loc_1400607C7
0x14006079d  mov     rax, [rbp+CallbackData]
0x1400607a1  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x1400607a8  mov     rcx, [r10+18h]
0x1400607ac  mov     edx, 81h
0x1400607b1  mov     dword ptr [rsp+50h+var_20], edi
0x1400607b5  mov     r9, rsi
0x1400607b8  mov     qword ptr [rsp+50h+var_28], r15
0x1400607bd  mov     qword ptr [rsp+50h+var_30], rax
0x1400607c2  call    WPP_SF_qqqd
0x1400607c7  mov     r14, [rbp+Object]
0x1400607cb  jmp     loc_1400606E3
0x1400607d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400607d7  lea     rax, WPP_GLOBAL_Control
0x1400607de  cmp     rcx, rax
0x1400607e1  jz      loc_1400606E3
0x1400607e7  mov     eax, [rcx+2Ch]
0x1400607ea  test    al, 1
0x1400607ec  jz      loc_1400606E3
0x1400607f2  cmp     byte ptr [rcx+29h], 2
0x1400607f6  jb      loc_1400606E3
0x1400607fc  mov     edx, 82h
0x140060801  jmp     loc_14006088C
0x140060806  mov     edi, 0C000CF18h
0x14006080b  mov     ecx, edi
0x14006080d  call    HsmDbgBreakOnStatus
0x140060812  jmp     loc_14006073F
0x140060817  mov     rcx, cs:WPP_GLOBAL_Control
0x14006081e  lea     rax, WPP_GLOBAL_Control
0x140060825  cmp     rcx, rax
0x140060828  jz      loc_1400606C4
0x14006082e  mov     eax, [rcx+2Ch]
0x140060831  test    al, 1
0x140060833  jz      loc_1400606C4
0x140060839  cmp     byte ptr [rcx+29h], 2
0x14006083d  jb      loc_1400606C4
0x140060843  mov     edx, 86h
0x140060848  mov     rax, [rbp+CallbackData]
0x14006084c  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140060853  mov     rcx, [rcx+18h]
0x140060857  mov     r9, rsi
0x14006085a  mov     dword ptr [rsp+50h+var_20], edi
0x14006085e  mov     qword ptr [rsp+50h+var_28], r15
0x140060863  mov     qword ptr [rsp+50h+var_30], rax
0x140060868  call    WPP_SF_qqqd
0x14006086d  jmp     loc_1400606C4
0x140060872  mov     eax, [rcx+2Ch]
0x140060875  test    al, 1
0x140060877  jz      loc_140060509
0x14006087d  cmp     byte ptr [rcx+29h], 2
0x140060881  jb      loc_140060509
0x140060887  mov     edx, 80h
0x14006088c  mov     rax, [rbp+CallbackData]
0x140060890  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140060897  mov     rcx, [rcx+18h]
0x14006089b  mov     r9, rsi
0x14006089e  mov     dword ptr [rsp+50h+var_20], edi
0x1400608a2  mov     qword ptr [rsp+50h+var_28], r15
0x1400608a7  mov     qword ptr [rsp+50h+var_30], rax
0x1400608ac  call    WPP_SF_qqqd
0x1400608b1  jmp     loc_1400606E3
```
