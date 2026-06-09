# CscSyncAddNewLocalItemToItemTree

- ea: `0x180037420`
- end: `0x180037876`
- name: `CscSyncAddNewLocalItemToItemTree`
- size: `1110`
- prototype: `__int64 __fastcall(PCWSTR SourceString, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, loader_planting`

## callers

- `0x180037290`

## callees

- `0x180004c40`
- `0x1800060a0`
- `0x1800134c0`
- `0x180015230`
- `0x180020ef0`
- `0x1800223c0`
- `0x1800360c0`
- `0x180036394`
- `0x180037420`
- `0x180039610`
- `0x180039fb4`
- `0x180071d68`
- `0x180071e7c`

## import_xrefs

- `ntdll!RtlGetLengthWithoutTrailingPathSeperators` at `0x1800374ff`
- `ntdll!RtlGetLengthWithoutLastFullDosOrNtPathElement` at `0x1800374a4`
- `ntdll!RtlpApplyLengthFunction` at `0x1800374b5`
- `ntdll!RtlpApplyLengthFunction` at `0x180037512`
- `ntdll!RtlpApplyLengthFunction` at `0x1800374b5`
- `ntdll!RtlpApplyLengthFunction` at `0x180037512`
- `ntdll!RtlInitUnicodeString` at `0x18003749e`
- `ntdll!RtlInitUnicodeString` at `0x180037564`
- `ntdll!RtlInitUnicodeString` at `0x18003749e`
- `ntdll!RtlInitUnicodeString` at `0x180037564`
- `ntdll!RtlNtStatusToDosError` at `0x180037850`
- `ntdll!RtlNtStatusToDosError` at `0x180037850`

## string_xrefs

- `0x1800374eb`: `CscSyncAddNewLocalItemToItemTree: RtlRemoveLastFullDosOrNtPathElement failed with %x`
- `0x18003753a`: `CscSyncAddNewLocalItemToItemTree: RtlRemoveTrailingPathSeperators failed with %x`
- `0x1800375c4`: `CscSyncAddNewLocalItemToItemTree: SyncOpenUNCPathLocalForEnumeration failed with %x`
- `0x180037680`: `CscSyncAddNewLocalItemToItemTree: SyncQueryDirectory failed with %x`
- `0x1800377b3`: `CscSyncAddNewLocalItemToItemTree: CscSyncpCreateNewTreeFullItem failed with %x`

## pseudocode

```c
ULONG __fastcall CscSyncAddNewLocalItemToItemTree(PCWSTR SourceString, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v7; // r13
  unsigned int NewTreeFullItem; // ebx
  __int64 v9; // rdx
  __int64 v10; // r9
  int v11; // r14d
  __int64 v12; // rsi
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  int v17[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING v21; // [rsp+78h] [rbp-88h] BYREF
  int v22[2]; // [rsp+88h] [rbp-78h]
  _QWORD *v23; // [rsp+90h] [rbp-70h]
  __int128 v24; // [rsp+A8h] [rbp-58h]
  _DWORD v25[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v26; // [rsp+C8h] [rbp-38h]
  __int64 v27; // [rsp+D0h] [rbp-30h]
  __int64 v28; // [rsp+D8h] [rbp-28h]
  int v29; // [rsp+E0h] [rbp-20h]
  int v30; // [rsp+E4h] [rbp-1Ch]

  *(_QWORD *)v22 = a3;
  *(_QWORD *)v17 = 0;
  v23 = a4;
  hHandle = 0;
  v18 = 0;
  v25[1] = 0;
  v7 = 0;
  memset_0(v25, 0, 0x7Cu);
  *a4 = 0;
  v24 = 0;
  v21 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  NewTreeFullItem = RtlpApplyLengthFunction(0, 0x10u, &DestinationString, RtlGetLengthWithoutLastFullDosOrNtPathElement);
  if ( NewTreeFullItem )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(
        L"CscSyncAddNewLocalItemToItemTree: RtlRemoveLastFullDosOrNtPathElement failed with %x",
        NewTreeFullItem);
      v9 = 49;
LABEL_31:
      v10 = NewTreeFullItem;
      goto LABEL_32;
    }
  }
  else
  {
    NewTreeFullItem = RtlpApplyLengthFunction(0, 0x10u, &DestinationString, RtlGetLengthWithoutTrailingPathSeperators);
    if ( NewTreeFullItem )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        SyncTraceOutputInternal(
          L"CscSyncAddNewLocalItemToItemTree: RtlRemoveTrailingPathSeperators failed with %x",
          NewTreeFullItem);
        v9 = 50;
        goto LABEL_31;
      }
    }
    else
    {
      RtlInitUnicodeString(&v21, &SourceString[((unsigned __int64)DestinationString.Length >> 1) + 1]);
      NewTreeFullItem = SyncOpenUNCPathLocalForEnumeration(&hHandle, 5u, 0, 0, 0, 1, 0);
      if ( NewTreeFullItem )
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(
            L"CscSyncAddNewLocalItemToItemTree: SyncOpenUNCPathLocalForEnumeration failed with %x",
            NewTreeFullItem);
          v9 = 51;
          goto LABEL_31;
        }
      }
      else
      {
        v7 = SyncAlloc(0x10000);
        if ( v7 )
        {
          NewTreeFullItem = SyncQueryDirectory(
                              hHandle,
                              &v18,
                              (void *)v7,
                              0x10000u,
                              FileBothDirectoryInformation,
                              1u,
                              &v21,
                              1u,
                              1);
          if ( NewTreeFullItem )
          {
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              SyncTraceOutputInternal(
                L"CscSyncAddNewLocalItemToItemTree: SyncQueryDirectory failed with %x",
                NewTreeFullItem);
              v9 = 53;
              goto LABEL_31;
            }
          }
          else
          {
            NewTreeFullItem = CscSyncpCreateNewTreeFullItem(a2, v17, v21.Length);
            if ( NewTreeFullItem || !*(_QWORD *)v17 )
            {
              if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
              {
                SyncTraceOutputInternal(
                  L"CscSyncAddNewLocalItemToItemTree: CscSyncpCreateNewTreeFullItem failed with %x",
                  NewTreeFullItem);
                v9 = 54;
                goto LABEL_31;
              }
            }
            else
            {
              v11 = *(_DWORD *)(v7 + 56);
              v12 = *(_QWORD *)(v7 + 24);
              v13 = *(_QWORD *)(v7 + 32);
              v14 = *(_QWORD *)(v7 + 40);
              memset_0(v25, 0, 0x80u);
              v30 = HIDWORD(v24);
              v25[0] = 589824;
              v26 = v14;
              v27 = v13;
              v28 = v12;
              v29 = v11;
              SyncItemAddStateToItem(v21.Buffer, v21.Length, v25);
              NewTreeFullItem = CscSyncpAddNewTreeFullItem(a2, v22[0], v17[0], 622608, 0);
              if ( NewTreeFullItem )
              {
                if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
                {
                  SyncTraceOutputInternal(
                    L"CscSyncAddNewLocalItemToItemTree: SyncKeepBoth_AddNewTreeFullItem failed with %x",
                    NewTreeFullItem);
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 12),
                    55,
                    WPP_49c63760df5a37e97d50b2be11371744_Traceguids,
                    NewTreeFullItem);
                }
              }
              else
              {
                v15 = *(_QWORD *)v17;
                *(_QWORD *)v17 = 0;
                *v23 = v15;
              }
            }
          }
        }
        else if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
        {
          SyncTraceOutputInternal(L"CscSyncAddNewLocalItemToItemTree: 0x%x", 3221225626LL);
          v9 = 52;
          v10 = 3221225626LL;
LABEL_32:
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), v9, WPP_49c63760df5a37e97d50b2be11371744_Traceguids, v10);
        }
      }
    }
  }
  if ( hHandle )
    SyncCloseFile(hHandle);
  if ( v7 )
    SyncFree(v7);
  if ( *(_QWORD *)v17 )
    SyncFree(*(_QWORD *)v17);
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"CscSyncAddNewLocalItemToItemTree: 0x%x", NewTreeFullItem);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 56, WPP_49c63760df5a37e97d50b2be11371744_Traceguids, NewTreeFullItem);
  }
  return RtlNtStatusToDosError(NewTreeFullItem);
}

```

## disassembly

```asm
0x180037420  push    rbp
0x180037422  push    rbx
0x180037423  push    rsi
0x180037424  push    rdi
0x180037425  push    r12
0x180037427  push    r13
0x180037429  push    r14
0x18003742b  push    r15
0x18003742d  lea     rbp, [rsp-58h]
0x180037432  sub     rsp, 158h
0x180037439  mov     rax, cs:__security_cookie
0x180037440  xor     rax, rsp
0x180037443  mov     [rbp+90h+var_50], rax
0x180037447  xor     esi, esi
0x180037449  mov     qword ptr [rbp+90h+var_108], r8
0x18003744d  mov     rbx, r9
0x180037450  mov     qword ptr [rsp+190h+var_140], rsi
0x180037455  mov     r12, rdx
0x180037458  mov     [rbp+90h+var_100], rbx
0x18003745c  mov     rdi, rcx
0x18003745f  mov     [rsp+190h+hHandle], rsi
0x180037464  xor     eax, eax
0x180037466  mov     [rsp+190h+var_138], esi
0x18003746a  lea     r8d, [rsi+7Ch]; Size
0x18003746e  mov     [rbp+90h+var_CC], eax
0x180037471  xor     edx, edx; Val
0x180037473  lea     rcx, [rbp+90h+var_D0]; void *
0x180037477  mov     r13d, esi
0x18003747a  call    memset_0
0x18003747f  xorps   xmm0, xmm0
0x180037482  mov     [rbx], rsi
0x180037485  xorps   xmm1, xmm1
0x180037488  lea     rcx, [rsp+190h+DestinationString]; DestinationString
0x18003748d  mov     rdx, rdi; SourceString
0x180037490  movups  [rbp+90h+var_E8], xmm0
0x180037494  movups  xmmword ptr [rsp+190h+var_118.Length], xmm0
0x180037499  movups  xmmword ptr [rsp+190h+DestinationString.Length], xmm1
0x18003749e  call    cs:__imp_RtlInitUnicodeString
0x1800374a4  mov     r9, cs:__imp_RtlGetLengthWithoutLastFullDosOrNtPathElement; LengthFunction
0x1800374ab  lea     r8, [rsp+190h+DestinationString]; UnicodeStringOrUnicodeStringBuffer
0x1800374b0  lea     edx, [rsi+10h]; Type
0x1800374b3  xor     ecx, ecx; Flags
0x1800374b5  call    cs:__imp_RtlpApplyLengthFunction
0x1800374bb  lea     r14, WPP_GLOBAL_Control
0x1800374c2  mov     ebx, eax
0x1800374c4  lea     r15, WPP_49c63760df5a37e97d50b2be11371744_Traceguids
0x1800374cb  test    eax, eax
0x1800374cd  jz      short loc_1800374FF
0x1800374cf  mov     rax, cs:WPP_GLOBAL_Control
0x1800374d6  cmp     rax, r14
0x1800374d9  jz      loc_1800377DA
0x1800374df  test    byte ptr [rax+6Ch], 1
0x1800374e3  jz      loc_1800377DA
0x1800374e9  mov     edx, ebx
0x1800374eb  lea     rcx, aCscsyncaddnewl_5; "CscSyncAddNewLocalItemToItemTree: RtlRe"...
0x1800374f2  call    SyncTraceOutputInternal
0x1800374f7  lea     edx, [rsi+31h]
0x1800374fa  jmp     loc_1800377C4
0x1800374ff  mov     r9, cs:__imp_RtlGetLengthWithoutTrailingPathSeperators; LengthFunction
0x180037506  lea     r8, [rsp+190h+DestinationString]; UnicodeStringOrUnicodeStringBuffer
0x18003750b  mov     edx, 10h; Type
0x180037510  xor     ecx, ecx; Flags
0x180037512  call    cs:__imp_RtlpApplyLengthFunction
0x180037518  mov     ebx, eax
0x18003751a  test    eax, eax
0x18003751c  jz      short loc_180037550
0x18003751e  mov     rax, cs:WPP_GLOBAL_Control
0x180037525  cmp     rax, r14
0x180037528  jz      loc_1800377DA
0x18003752e  test    byte ptr [rax+6Ch], 1
0x180037532  jz      loc_1800377DA
0x180037538  mov     edx, ebx
0x18003753a  lea     rcx, aCscsyncaddnewl_2; "CscSyncAddNewLocalItemToItemTree: RtlRe"...
0x180037541  call    SyncTraceOutputInternal
0x180037546  mov     edx, 32h ; '2'
0x18003754b  jmp     loc_1800377C4
0x180037550  movzx   eax, [rsp+190h+DestinationString.Length]
0x180037555  lea     rcx, [rsp+190h+var_118]; DestinationString
0x18003755a  shr     rax, 1
0x18003755d  inc     rax
0x180037560  lea     rdx, [rdi+rax*2]; SourceString
0x180037564  call    cs:__imp_RtlInitUnicodeString
0x18003756a  mov     [rsp+190h+var_148], rsi; __int64
0x18003756f  lea     r8, [rsp+190h+DestinationString]
0x180037574  mov     [rsp+190h+var_150], 1; char
0x180037579  lea     rcx, [rsp+190h+hHandle]; FileHandle
0x18003757e  mov     qword ptr [rsp+190h+var_158], rsi; __int64
0x180037583  mov     r9d, 81h
0x180037589  mov     [rsp+190h+var_160], rsi; __int64
0x18003758e  xor     edx, edx
0x180037590  mov     qword ptr [rsp+190h+var_168], rsi; __int64
0x180037595  mov     [rsp+190h+var_170], 5; ULONG
0x18003759d  call    SyncOpenUNCPathLocalForEnumeration
0x1800375a2  mov     ebx, eax
0x1800375a4  test    eax, eax
0x1800375a6  jz      short loc_1800375DA
0x1800375a8  mov     rax, cs:WPP_GLOBAL_Control
0x1800375af  cmp     rax, r14
0x1800375b2  jz      loc_1800377DA
0x1800375b8  test    byte ptr [rax+6Ch], 1
0x1800375bc  jz      loc_1800377DA
0x1800375c2  mov     edx, ebx
0x1800375c4  lea     rcx, aCscsyncaddnewl_4; "CscSyncAddNewLocalItemToItemTree: SyncO"...
0x1800375cb  call    SyncTraceOutputInternal
0x1800375d0  mov     edx, 33h ; '3'
0x1800375d5  jmp     loc_1800377C4
0x1800375da  mov     edi, 10000h
0x1800375df  mov     ecx, edi
0x1800375e1  call    SyncAlloc
0x1800375e6  mov     r13, rax
0x1800375e9  test    rax, rax
0x1800375ec  jnz     short loc_180037628
0x1800375ee  mov     rax, cs:WPP_GLOBAL_Control
0x1800375f5  cmp     rax, r14
0x1800375f8  jz      loc_1800377DA
0x1800375fe  test    byte ptr [rax+6Ch], 8
0x180037602  jz      loc_1800377DA
0x180037608  mov     edx, 0C000009Ah
0x18003760d  lea     rcx, aCscsyncaddnewl_3; "CscSyncAddNewLocalItemToItemTree: 0x%x"
0x180037614  call    SyncTraceOutputInternal
0x180037619  lea     edx, [r13+34h]
0x18003761d  mov     r9d, 0C000009Ah
0x180037623  jmp     loc_1800377C7
0x180037628  mov     rcx, [rsp+190h+hHandle]; hHandle
0x18003762d  lea     rax, [rsp+190h+var_118]
0x180037632  mov     [rsp+190h+var_150], 1; char
0x180037637  lea     rdx, [rsp+190h+var_138]
0x18003763c  mov     [rsp+190h+var_158], 1; char
0x180037641  mov     r9d, edi
0x180037644  mov     [rsp+190h+var_160], rax; PUNICODE_STRING
0x180037649  mov     r8, r13
0x18003764c  mov     [rsp+190h+var_168], 1; char
0x180037651  mov     [rsp+190h+var_170], 3; FILE_INFORMATION_CLASS
0x180037659  call    SyncQueryDirectory
0x18003765e  mov     ebx, eax
0x180037660  test    eax, eax
0x180037662  jz      short loc_180037696
0x180037664  mov     rax, cs:WPP_GLOBAL_Control
0x18003766b  cmp     rax, r14
0x18003766e  jz      loc_1800377DA
0x180037674  test    byte ptr [rax+6Ch], 1
0x180037678  jz      loc_1800377DA
0x18003767e  mov     edx, ebx
0x180037680  lea     rcx, aCscsyncaddnewl_0; "CscSyncAddNewLocalItemToItemTree: SyncQ"...
0x180037687  call    SyncTraceOutputInternal
0x18003768c  mov     edx, 35h ; '5'
0x180037691  jmp     loc_1800377C4
0x180037696  movzx   r8d, [rsp+190h+var_118.Length]
0x18003769c  lea     rdx, [rsp+190h+var_140]
0x1800376a1  mov     rcx, r12
0x1800376a4  call    CscSyncpCreateNewTreeFullItem
0x1800376a9  mov     ebx, eax
0x1800376ab  test    eax, eax
0x1800376ad  jnz     loc_18003779F
0x1800376b3  mov     r15, qword ptr [rsp+190h+var_140]
0x1800376b8  test    r15, r15
0x1800376bb  jz      loc_180037798
0x1800376c1  mov     r14d, [r13+38h]
0x1800376c5  lea     rcx, [rbp+90h+var_D0]; void *
0x1800376c9  mov     rsi, [r13+18h]
0x1800376cd  xor     edx, edx; Val
0x1800376cf  mov     rdi, [r13+20h]
0x1800376d3  mov     r8d, 80h; Size
0x1800376d9  mov     rbx, [r13+28h]
0x1800376dd  call    memset_0
0x1800376e2  mov     eax, dword ptr [rbp+90h+var_E8+0Ch]
0x1800376e5  lea     r8, [rbp+90h+var_D0]
0x1800376e9  movzx   edx, [rsp+190h+var_118.Length]
0x1800376ee  mov     r9, r15
0x1800376f1  mov     rcx, [rbp+90h+var_118.Buffer]
0x1800376f5  mov     [rbp+90h+var_AC], eax
0x1800376f8  mov     [rbp+90h+var_D0], 90000h
0x1800376ff  mov     [rbp+90h+var_C8], rbx
0x180037703  mov     [rbp+90h+var_C0], rdi
0x180037707  mov     [rbp+90h+var_B8], rsi
0x18003770b  mov     [rbp+90h+var_B0], r14d
0x18003770f  call    SyncItemAddStateToItem
0x180037714  mov     r8, qword ptr [rsp+190h+var_140]; int
0x180037719  xor     esi, esi
0x18003771b  mov     rdx, qword ptr [rbp+90h+var_108]; int
0x18003771f  mov     r9d, 98010h; int
0x180037725  mov     rcx, r12; int
0x180037728  mov     [rsp+190h+var_170], esi; Status
0x18003772c  call    CscSyncpAddNewTreeFullItem
0x180037731  mov     ebx, eax
0x180037733  test    eax, eax
0x180037735  jz      short loc_180037785
0x180037737  mov     rax, cs:WPP_GLOBAL_Control
0x18003773e  lea     rdi, WPP_GLOBAL_Control
0x180037745  cmp     rax, rdi
0x180037748  jz      loc_1800377E1
0x18003774e  test    byte ptr [rax+6Ch], 1
0x180037752  jz      loc_1800377E1
0x180037758  mov     edx, ebx
0x18003775a  lea     rcx, aCscsyncaddnewl; "CscSyncAddNewLocalItemToItemTree: SyncK"...
0x180037761  call    SyncTraceOutputInternal
0x180037766  mov     rcx, cs:WPP_GLOBAL_Control
0x18003776d  lea     edx, [rsi+37h]
0x180037770  mov     r9d, ebx
0x180037773  lea     r8, WPP_49c63760df5a37e97d50b2be11371744_Traceguids
0x18003777a  mov     rcx, [rcx+60h]
0x18003777e  call    WPP_SF_d
0x180037783  jmp     short loc_1800377E1
0x180037785  mov     rax, qword ptr [rsp+190h+var_140]
0x18003778a  mov     rcx, [rbp+90h+var_100]
0x18003778e  mov     qword ptr [rsp+190h+var_140], rsi
0x180037793  mov     [rcx], rax
0x180037796  jmp     short loc_1800377DA
0x180037798  lea     r15, WPP_49c63760df5a37e97d50b2be11371744_Traceguids
0x18003779f  mov     rax, cs:WPP_GLOBAL_Control
0x1800377a6  cmp     rax, r14
0x1800377a9  jz      short loc_1800377DA
0x1800377ab  test    byte ptr [rax+6Ch], 1
0x1800377af  jz      short loc_1800377DA
0x1800377b1  mov     edx, ebx
0x1800377b3  lea     rcx, aCscsyncaddnewl_1; "CscSyncAddNewLocalItemToItemTree: CscSy"...
0x1800377ba  call    SyncTraceOutputInternal
0x1800377bf  mov     edx, 36h ; '6'
0x1800377c4  mov     r9d, ebx
0x1800377c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800377ce  mov     r8, r15
0x1800377d1  mov     rcx, [rcx+60h]
0x1800377d5  call    WPP_SF_d
0x1800377da  lea     rdi, WPP_GLOBAL_Control
0x1800377e1  mov     rcx, [rsp+190h+hHandle]; Handle
0x1800377e6  test    rcx, rcx
0x1800377e9  jz      short loc_1800377F0
0x1800377eb  call    SyncCloseFile
0x1800377f0  test    r13, r13
0x1800377f3  jz      short loc_1800377FD
0x1800377f5  mov     rcx, r13
0x1800377f8  call    SyncFree
0x1800377fd  mov     r15, qword ptr [rsp+190h+var_140]
0x180037802  test    r15, r15
0x180037805  jz      short loc_18003780F
0x180037807  mov     rcx, r15
0x18003780a  call    SyncFree
0x18003780f  mov     rax, cs:WPP_GLOBAL_Control
0x180037816  cmp     rax, rdi
0x180037819  jz      short loc_18003784E
0x18003781b  test    byte ptr [rax+6Ch], 8
0x18003781f  jz      short loc_18003784E
0x180037821  mov     edx, ebx
0x180037823  lea     rcx, aCscsyncaddnewl_3; "CscSyncAddNewLocalItemToItemTree: 0x%x"
0x18003782a  call    SyncTraceOutputInternal
0x18003782f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037836  lea     r8, WPP_49c63760df5a37e97d50b2be11371744_Traceguids
0x18003783d  mov     edx, 38h ; '8'
0x180037842  mov     r9d, ebx
0x180037845  mov     rcx, [rcx+60h]
0x180037849  call    WPP_SF_d
0x18003784e  mov     ecx, ebx; Status
0x180037850  call    cs:__imp_RtlNtStatusToDosError
0x180037856  mov     rcx, [rbp+90h+var_50]
0x18003785a  xor     rcx, rsp; StackCookie
0x18003785d  call    __security_check_cookie
0x180037862  add     rsp, 158h
0x180037869  pop     r15
0x18003786b  pop     r14
0x18003786d  pop     r13
0x18003786f  pop     r12
0x180037871  pop     rdi
0x180037872  pop     rsi
0x180037873  pop     rbx
0x180037874  pop     rbp
0x180037875  retn
```
