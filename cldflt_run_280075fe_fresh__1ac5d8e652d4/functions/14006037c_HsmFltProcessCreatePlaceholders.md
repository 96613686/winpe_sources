# HsmFltProcessCreatePlaceholders

- ea: `0x14006037c`
- end: `0x140060796`
- name: `HsmFltProcessCreatePlaceholders`
- size: `1050`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14004ded0`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x140050ca0`
- `0x140052454`
- `0x14005cd20`
- `0x14005eb40`
- `0x14006037c`
- `0x14006079c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400605cb`
- `ntoskrnl!ObfDereferenceObject` at `0x1400605cb`
- `FLTMGR!FltClose` at `0x1400605e4`
- `FLTMGR!FltClose` at `0x1400605e4`
- `FLTMGR!FltGetRequestorProcess` at `0x140060501`
- `FLTMGR!FltGetRequestorProcess` at `0x140060501`
- `FLTMGR!FltReleasePushLockEx` at `0x1400605b7`
- `FLTMGR!FltReleasePushLockEx` at `0x1400605b7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006049b`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006049b`

## pseudocode

```c
__int64 __fastcall HsmFltProcessCreatePlaceholders(
        __int64 a1,
        __int64 a2,
        struct _FILE_OBJECT *a3,
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
  int v22; // r12d
  int v23; // r8d
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
    HsmDbgBreakOnStatus(3221278475LL);
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
  SyncPolicy = HsmpRelativeStreamOpen(a2, a3, 0, 0x100000u, 1u, 32, v27, &FileHandle, (PFILE_OBJECT *)&Object);
  HsmDbgBreakOnStatus((unsigned int)SyncPolicy);
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
  SyncPolicy = HsmpPrepareForMgmtOperation(a2, (struct _FILE_OBJECT *)Object, 8, 0);
  HsmDbgBreakOnStatus((unsigned int)SyncPolicy);
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
    SyncPolicy = HsmpCldGetSyncPolicy(a2, v18, (_DWORD)a3, 5, (__int64)&v30);
    HsmDbgBreakOnStatus((unsigned int)SyncPolicy);
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
        SyncPolicy = HsmpOpCreatePlaceholders(a2, FileHandle, v23, *(void **)(a9 + 24), *(_DWORD *)(a9 + 16), &v28);
        HsmDbgBreakOnStatus((unsigned int)SyncPolicy);
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
      SyncPolicy = HsmpCldCheckSyncProviderAccess(a2, v18, (_DWORD)a3, RequestorProcess, (__int64)&a10);
      HsmDbgBreakOnStatus((unsigned int)SyncPolicy);
      if ( SyncPolicy >= 0 )
      {
        if ( (_BYTE)a10 )
          goto LABEL_15;
        SyncPolicy = -1073688808;
        HsmDbgBreakOnStatus(3221278488LL);
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
0x14006037c  mov     [rsp-38h+arg_8], rbx
0x140060381  mov     [rsp-38h+arg_18], r9
0x140060386  mov     [rsp-38h+arg_0], rcx
0x14006038b  push    rbp
0x14006038c  push    rsi
0x14006038d  push    rdi
0x14006038e  push    r12
0x140060390  push    r13
0x140060392  push    r14
0x140060394  push    r15
0x140060396  mov     rbp, rsp
0x140060399  sub     rsp, 50h
0x14006039d  xor     r14d, r14d
0x1400603a0  mov     dword ptr [rbp+arg_18], 0
0x1400603a7  cmp     [rbp+arg_48], 20h ; ' '
0x1400603ae  mov     r15, r8
0x1400603b1  mov     rsi, rdx
0x1400603b4  mov     [rbp+FileHandle], 0
0x1400603bc  mov     [rbp+Object], r14
0x1400603c0  mov     dword ptr [rbp+arg_0], r14d
0x1400603c4  jnb     short loc_140060404
0x1400603c6  mov     edi, 0C000CF0Bh
0x1400603cb  mov     ecx, edi
0x1400603cd  call    HsmDbgBreakOnStatus
0x1400603d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400603d9  lea     rax, WPP_GLOBAL_Control
0x1400603e0  cmp     rcx, rax
0x1400603e3  jnz     loc_140060752
0x1400603e9  mov     rbx, [rsp+50h+arg_8]
0x1400603f1  mov     eax, edi
0x1400603f3  add     rsp, 50h
0x1400603f7  pop     r15
0x1400603f9  pop     r14
0x1400603fb  pop     r13
0x1400603fd  pop     r12
0x1400603ff  pop     rdi
0x140060400  pop     rsi
0x140060401  pop     rbp
0x140060402  retn
0x140060404  mov     r12, [rbp+arg_40]
0x14006040b  cmp     dword ptr [r12+10h], 50h ; 'P'
0x140060411  jb      short loc_1400603C6
0x140060413  lea     rax, [rbp+Object]
0x140060417  mov     r9d, 100000h; int
0x14006041d  mov     [rsp+50h+var_10], rax; __int64
0x140060422  xor     r8d, r8d; int
0x140060425  lea     rax, [rbp+FileHandle]
0x140060429  mov     rdx, r15; int
0x14006042c  mov     [rsp+50h+var_18], rax; __int64
0x140060431  mov     rcx, rsi; int
0x140060434  mov     [rsp+50h+var_28], 20h ; ' '; int
0x14006043c  mov     [rsp+50h+var_30], 1; ULONG
0x140060444  call    HsmpRelativeStreamOpen
0x140060449  mov     ecx, eax
0x14006044b  mov     edi, eax
0x14006044d  call    HsmDbgBreakOnStatus
0x140060452  test    edi, edi
0x140060454  js      loc_14006065A
0x14006045a  mov     r14, [rbp+Object]
0x14006045e  xor     r9d, r9d
0x140060461  mov     rdx, r14
0x140060464  mov     rcx, rsi
0x140060467  lea     r8d, [r9+8]
0x14006046b  call    HsmpPrepareForMgmtOperation
0x140060470  mov     ecx, eax
0x140060472  mov     edi, eax
0x140060474  call    HsmDbgBreakOnStatus
0x140060479  test    edi, edi
0x14006047b  js      loc_1400606B0
0x140060481  mov     r13, [rbp+arg_20]
0x140060485  mov     [rbp+arg_50], 0
0x14006048c  test    r13, r13
0x14006048f  jz      short loc_1400604AE
0x140060491  mov     rcx, [r13+10h]
0x140060495  xor     edx, edx
0x140060497  add     rcx, 18h
0x14006049b  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400604a2  nop     dword ptr [rax+rax+00h]
0x1400604a7  mov     [rbp+arg_50], 1
0x1400604ae  mov     r12d, [r12+8]
0x1400604b3  lea     rax, [rbp+arg_18]
0x1400604b7  mov     r9d, 5
0x1400604bd  mov     qword ptr [rsp+50h+var_30], rax
0x1400604c2  mov     r8, r15
0x1400604c5  mov     rdx, r13
0x1400604c8  mov     rcx, rsi
0x1400604cb  call    HsmpCldGetSyncPolicy
0x1400604d0  mov     ecx, eax
0x1400604d2  mov     edi, eax
0x1400604d4  call    HsmDbgBreakOnStatus
0x1400604d9  test    edi, edi
0x1400604db  js      loc_1400605F5
0x1400604e1  mov     ebx, dword ptr [rbp+arg_18]
0x1400604e4  bt      ebx, 1Bh
0x1400604e8  jb      short loc_140060548
0x1400604ea  mov     rax, [rbp+CallbackData]
0x1400604ee  mov     byte ptr [rbp+arg_48], 0
0x1400604f5  test    rax, rax
0x1400604f8  jz      loc_140060655
0x1400604fe  mov     rcx, rax; CallbackData
0x140060501  call    cs:__imp_FltGetRequestorProcess
0x140060508  nop     dword ptr [rax+rax+00h]
0x14006050d  lea     rcx, [rbp+arg_48]
0x140060514  mov     r9, rax
0x140060517  mov     qword ptr [rsp+50h+var_30], rcx
0x14006051c  mov     r8, r15
0x14006051f  mov     rcx, rsi
0x140060522  mov     rdx, r13
0x140060525  call    HsmpCldCheckSyncProviderAccess
0x14006052a  mov     ecx, eax
0x14006052c  mov     edi, eax
0x14006052e  call    HsmDbgBreakOnStatus
0x140060533  test    edi, edi
0x140060535  js      loc_14006061F
0x14006053b  cmp     byte ptr [rbp+arg_48], 0
0x140060542  jz      loc_1400606E6
0x140060548  mov     eax, ebx
0x14006054a  and     r12d, 1
0x14006054e  and     al, 0Fh
0x140060550  cmp     al, 4
0x140060552  jnb     short loc_140060558
0x140060554  or      r12d, 2
0x140060558  mov     rcx, [rbp+arg_40]
0x14006055f  lea     rax, [rbp+arg_0]
0x140060563  mov     rdx, [rbp+FileHandle]
0x140060567  mov     r8d, r12d
0x14006056a  or      r8d, 4
0x14006056e  mov     qword ptr [rsp+50h+var_28], rax
0x140060573  and     ebx, 0F0h
0x140060579  mov     eax, [rcx+10h]
0x14006057c  cmp     ebx, 40h ; '@'
0x14006057f  mov     r9, [rcx+18h]
0x140060583  mov     rcx, rsi
0x140060586  cmovnb  r8d, r12d
0x14006058a  mov     [rsp+50h+var_30], eax
0x14006058e  call    HsmpOpCreatePlaceholders
0x140060593  mov     ecx, eax
0x140060595  mov     edi, eax
0x140060597  call    HsmDbgBreakOnStatus
0x14006059c  test    edi, edi
0x14006059e  js      loc_1400606F7
0x1400605a4  cmp     [rbp+arg_50], 0
0x1400605ab  jz      short loc_1400605C3
0x1400605ad  mov     rcx, [r13+10h]
0x1400605b1  xor     edx, edx
0x1400605b3  add     rcx, 18h
0x1400605b7  call    cs:__imp_FltReleasePushLockEx
0x1400605be  nop     dword ptr [rax+rax+00h]
0x1400605c3  test    r14, r14
0x1400605c6  jz      short loc_1400605D7
0x1400605c8  mov     rcx, r14; Object
0x1400605cb  call    cs:__imp_ObfDereferenceObject
0x1400605d2  nop     dword ptr [rax+rax+00h]
0x1400605d7  mov     rcx, [rbp+FileHandle]; FileHandle
0x1400605db  test    rcx, rcx
0x1400605de  jz      loc_1400603E9
0x1400605e4  call    cs:__imp_FltClose
0x1400605eb  nop     dword ptr [rax+rax+00h]
0x1400605f0  jmp     loc_1400603E9
0x1400605f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400605fc  lea     rax, WPP_GLOBAL_Control
0x140060603  cmp     rcx, rax
0x140060606  jz      short loc_1400605A4
0x140060608  mov     eax, [rcx+2Ch]
0x14006060b  test    al, 1
0x14006060d  jz      short loc_1400605A4
0x14006060f  cmp     byte ptr [rcx+29h], 2
0x140060613  jb      short loc_1400605A4
0x140060615  mov     edx, 84h
0x14006061a  jmp     loc_140060728
0x14006061f  mov     rcx, cs:WPP_GLOBAL_Control
0x140060626  lea     rax, WPP_GLOBAL_Control
0x14006062d  cmp     rcx, rax
0x140060630  jz      loc_1400605A4
0x140060636  mov     eax, [rcx+2Ch]
0x140060639  test    al, 1
0x14006063b  jz      loc_1400605A4
0x140060641  cmp     byte ptr [rcx+29h], 2
0x140060645  jb      loc_1400605A4
0x14006064b  mov     edx, 85h
0x140060650  jmp     loc_140060728
0x140060655  jmp     loc_14006050D
0x14006065a  mov     r10, cs:WPP_GLOBAL_Control
0x140060661  lea     rax, WPP_GLOBAL_Control
0x140060668  cmp     r10, rax
0x14006066b  jz      short loc_1400606A7
0x14006066d  mov     ecx, [r10+2Ch]
0x140060671  test    cl, 1
0x140060674  jz      short loc_1400606A7
0x140060676  cmp     byte ptr [r10+29h], 2
0x14006067b  jb      short loc_1400606A7
0x14006067d  mov     rax, [rbp+CallbackData]
0x140060681  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140060688  mov     rcx, [r10+18h]
0x14006068c  mov     edx, 81h
0x140060691  mov     dword ptr [rsp+50h+var_20], edi
0x140060695  mov     r9, rsi
0x140060698  mov     qword ptr [rsp+50h+var_28], r15
0x14006069d  mov     qword ptr [rsp+50h+var_30], rax
0x1400606a2  call    WPP_SF_qqqd
0x1400606a7  mov     r14, [rbp+Object]
0x1400606ab  jmp     loc_1400605C3
0x1400606b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400606b7  lea     rax, WPP_GLOBAL_Control
0x1400606be  cmp     rcx, rax
0x1400606c1  jz      loc_1400605C3
0x1400606c7  mov     eax, [rcx+2Ch]
0x1400606ca  test    al, 1
0x1400606cc  jz      loc_1400605C3
0x1400606d2  cmp     byte ptr [rcx+29h], 2
0x1400606d6  jb      loc_1400605C3
0x1400606dc  mov     edx, 82h
0x1400606e1  jmp     loc_14006076C
0x1400606e6  mov     edi, 0C000CF18h
0x1400606eb  mov     ecx, edi
0x1400606ed  call    HsmDbgBreakOnStatus
0x1400606f2  jmp     loc_14006061F
0x1400606f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400606fe  lea     rax, WPP_GLOBAL_Control
0x140060705  cmp     rcx, rax
0x140060708  jz      loc_1400605A4
0x14006070e  mov     eax, [rcx+2Ch]
0x140060711  test    al, 1
0x140060713  jz      loc_1400605A4
0x140060719  cmp     byte ptr [rcx+29h], 2
0x14006071d  jb      loc_1400605A4
0x140060723  mov     edx, 86h
0x140060728  mov     rax, [rbp+CallbackData]
0x14006072c  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140060733  mov     rcx, [rcx+18h]
0x140060737  mov     r9, rsi
0x14006073a  mov     dword ptr [rsp+50h+var_20], edi
0x14006073e  mov     qword ptr [rsp+50h+var_28], r15
0x140060743  mov     qword ptr [rsp+50h+var_30], rax
0x140060748  call    WPP_SF_qqqd
0x14006074d  jmp     loc_1400605A4
0x140060752  mov     eax, [rcx+2Ch]
0x140060755  test    al, 1
0x140060757  jz      loc_1400603E9
0x14006075d  cmp     byte ptr [rcx+29h], 2
0x140060761  jb      loc_1400603E9
0x140060767  mov     edx, 80h
0x14006076c  mov     rax, [rbp+CallbackData]
0x140060770  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140060777  mov     rcx, [rcx+18h]
0x14006077b  mov     r9, rsi
0x14006077e  mov     dword ptr [rsp+50h+var_20], edi
0x140060782  mov     qword ptr [rsp+50h+var_28], r15
0x140060787  mov     qword ptr [rsp+50h+var_30], rax
0x14006078c  call    WPP_SF_qqqd
0x140060791  jmp     loc_1400605C3
```
