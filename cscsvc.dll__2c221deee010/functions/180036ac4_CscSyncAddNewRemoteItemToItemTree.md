# CscSyncAddNewRemoteItemToItemTree

- ea: `0x180036ac4`
- end: `0x180036f03`
- name: `CscSyncAddNewRemoteItemToItemTree`
- size: `1087`
- prototype: `__int64 __fastcall(PCWSTR SourceString, int, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, loader_planting`

## callers

- `0x180036a70`

## callees

- `0x180003a00`
- `0x180004c40`
- `0x1800134c0`
- `0x180015230`
- `0x180020ef0`
- `0x1800223c0`
- `0x18002a524`
- `0x1800360c0`
- `0x180036394`
- `0x180036ac4`
- `0x180039610`
- `0x180039fb4`
- `0x180071d68`
- `0x180071e7c`

## import_xrefs

- `ntdll!RtlGetLengthWithoutTrailingPathSeperators` at `0x180036bc9`
- `ntdll!RtlGetLengthWithoutLastFullDosOrNtPathElement` at `0x180036b45`
- `ntdll!RtlpApplyLengthFunction` at `0x180036b56`
- `ntdll!RtlpApplyLengthFunction` at `0x180036bdc`
- `ntdll!RtlpApplyLengthFunction` at `0x180036b56`
- `ntdll!RtlpApplyLengthFunction` at `0x180036bdc`
- `ntdll!RtlInitUnicodeString` at `0x180036b3f`
- `ntdll!RtlInitUnicodeString` at `0x180036bc3`
- `ntdll!RtlInitUnicodeString` at `0x180036b3f`
- `ntdll!RtlInitUnicodeString` at `0x180036bc3`
- `ntdll!RtlNtStatusToDosError` at `0x180036edf`
- `ntdll!RtlNtStatusToDosError` at `0x180036edf`

## string_xrefs

- `0x180036b7d`: `CscSyncAddNewRemoteItemToItemTree: RtlRemoveLastFullDosOrNtPathElement failed with %x`
- `0x180036c0b`: `CscSyncAddNewRemoteItemToItemTree: RtlRemoveTrailingPathSeperators failed with %x`
- `0x180036c69`: `CscSyncAddNewRemoteItemToItemTree: SyncOpenUNCPathServerForEnumeration failed with %x`
- `0x180036d32`: `CscSyncAddNewRemoteItemToItemTree: SyncQueryDirectory failed with %x`
- `0x180036e45`: `CscSyncAddNewRemoteItemToItemTree: CscSyncpCreateNewTreeFullItem failed with %x`

## pseudocode

```c
ULONG __fastcall CscSyncAddNewRemoteItemToItemTree(PCWSTR SourceString, __int64 a2, int a3, _QWORD *a4)
{
  __int64 v4; // rsi
  unsigned int NewTreeFullItem; // ebx
  __int64 v10; // rdx
  __int64 v11; // r9
  int v13[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v14; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING v17; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v18[3]; // [rsp+88h] [rbp-78h] BYREF
  int v19; // [rsp+A0h] [rbp-60h]
  int v20; // [rsp+A4h] [rbp-5Ch]
  _BYTE v21[4]; // [rsp+B0h] [rbp-50h] BYREF
  int v22; // [rsp+B4h] [rbp-4Ch]

  v4 = 0;
  *(_QWORD *)v13 = 0;
  hHandle = 0;
  v14 = 0;
  v22 = 0;
  memset_0(v21, 0, 0x7Cu);
  v20 = 0;
  *a4 = 0;
  v17 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  NewTreeFullItem = RtlpApplyLengthFunction(0, 0x10u, &DestinationString, RtlGetLengthWithoutLastFullDosOrNtPathElement);
  if ( NewTreeFullItem )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(
        L"CscSyncAddNewRemoteItemToItemTree: RtlRemoveLastFullDosOrNtPathElement failed with %x",
        NewTreeFullItem);
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        41,
        WPP_49c63760df5a37e97d50b2be11371744_Traceguids,
        NewTreeFullItem);
    }
    goto LABEL_34;
  }
  RtlInitUnicodeString(&v17, &SourceString[(unsigned __int64)DestinationString.Length >> 1]);
  NewTreeFullItem = RtlpApplyLengthFunction(0, 0x10u, &DestinationString, RtlGetLengthWithoutTrailingPathSeperators);
  if ( NewTreeFullItem )
  {
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_34;
    SyncTraceOutputInternal(
      L"CscSyncAddNewRemoteItemToItemTree: RtlRemoveTrailingPathSeperators failed with %x",
      NewTreeFullItem);
    v10 = 42;
    goto LABEL_32;
  }
  NewTreeFullItem = SyncOpenUNCPathServerForEnumeration(&hHandle, 0, &DestinationString, 129, 5u);
  if ( NewTreeFullItem )
  {
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_34;
    SyncTraceOutputInternal(
      L"CscSyncAddNewRemoteItemToItemTree: SyncOpenUNCPathServerForEnumeration failed with %x",
      NewTreeFullItem);
    v10 = 43;
    goto LABEL_32;
  }
  v4 = SyncAlloc(0x10000);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) == 0 )
      goto LABEL_34;
    SyncTraceOutputInternal(L"CscSyncAddNewRemoteItemToItemTree: 0x%x", 3221225626LL);
    v10 = 44;
    v11 = 3221225626LL;
LABEL_33:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), v10, WPP_49c63760df5a37e97d50b2be11371744_Traceguids, v11);
    goto LABEL_34;
  }
  NewTreeFullItem = SyncQueryDirectory(
                      hHandle,
                      &v14,
                      (void *)v4,
                      0x10000u,
                      FileBothDirectoryInformation,
                      1u,
                      &v17,
                      1u,
                      0);
  if ( NewTreeFullItem )
  {
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_34;
    SyncTraceOutputInternal(L"CscSyncAddNewRemoteItemToItemTree: SyncQueryDirectory failed with %x", NewTreeFullItem);
    v10 = 45;
    goto LABEL_32;
  }
  NewTreeFullItem = CscSyncpCreateNewTreeFullItem(a2, v13, v17.Length);
  if ( NewTreeFullItem || !*(_QWORD *)v13 )
  {
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_34;
    SyncTraceOutputInternal(
      L"CscSyncAddNewRemoteItemToItemTree: CscSyncpCreateNewTreeFullItem failed with %x",
      NewTreeFullItem);
    v10 = 46;
    goto LABEL_32;
  }
  v19 = *(_DWORD *)(v4 + 56);
  v18[2] = *(_QWORD *)(v4 + 24);
  v18[1] = *(_QWORD *)(v4 + 32);
  v18[0] = *(_QWORD *)(v4 + 40);
  memset_0(v21, 0, 0x80u);
  SyncItemAddServerEnumInfo(v18, 0, v21);
  SyncItemAddStateToItem(v17.Buffer, v17.Length, v21);
  NewTreeFullItem = CscSyncpAddNewTreeFullItem(a2, a3, v13[0], 360449, NewTreeFullItem);
  if ( !NewTreeFullItem )
  {
    *a4 = *(_QWORD *)v13;
    *(_QWORD *)v13 = 0;
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    SyncTraceOutputInternal(
      L"CscSyncAddNewRemoteItemToItemTree: SyncKeepBoth_AddNewTreeFullItem failed with %x",
      NewTreeFullItem);
    v10 = 47;
LABEL_32:
    v11 = NewTreeFullItem;
    goto LABEL_33;
  }
LABEL_34:
  if ( hHandle )
    SyncCloseFile(hHandle);
  if ( v4 )
    SyncFree(v4);
  if ( *(_QWORD *)v13 )
    SyncFree(*(_QWORD *)v13);
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"CscSyncAddNewRemoteItemToItemTree: 0x%x", NewTreeFullItem);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 48, WPP_49c63760df5a37e97d50b2be11371744_Traceguids, NewTreeFullItem);
  }
  return RtlNtStatusToDosError(NewTreeFullItem);
}

```

## disassembly

```asm
0x180036ac4  push    rbp
0x180036ac6  push    rbx
0x180036ac7  push    rsi
0x180036ac8  push    rdi
0x180036ac9  push    r12
0x180036acb  push    r14
0x180036acd  push    r15
0x180036acf  lea     rbp, [rsp-40h]
0x180036ad4  sub     rsp, 140h
0x180036adb  mov     rax, cs:__security_cookie
0x180036ae2  xor     rax, rsp
0x180036ae5  mov     [rbp+70h+var_40], rax
0x180036ae9  xor     esi, esi
0x180036aeb  mov     qword ptr [rsp+170h+var_120], 0
0x180036af4  mov     r12, r8
0x180036af7  mov     [rsp+170h+hHandle], 0
0x180036b00  mov     r14, rdx
0x180036b03  mov     [rsp+170h+var_118], esi
0x180036b07  mov     rdi, rcx
0x180036b0a  xor     eax, eax
0x180036b0c  lea     r8d, [rsi+7Ch]; Size
0x180036b10  mov     [rbp+70h+var_BC], eax
0x180036b13  xor     edx, edx; Val
0x180036b15  lea     rcx, [rbp+70h+var_C0]; void *
0x180036b19  mov     r15, r9
0x180036b1c  call    memset_0
0x180036b21  xorps   xmm0, xmm0
0x180036b24  mov     [rbp+70h+var_CC], esi
0x180036b27  xorps   xmm1, xmm1
0x180036b2a  mov     [r15], rsi
0x180036b2d  mov     rdx, rdi; SourceString
0x180036b30  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x180036b35  movups  xmmword ptr [rsp+170h+var_F8.Length], xmm0
0x180036b3a  movups  xmmword ptr [rsp+170h+DestinationString.Length], xmm1
0x180036b3f  call    cs:__imp_RtlInitUnicodeString
0x180036b45  mov     r9, cs:__imp_RtlGetLengthWithoutLastFullDosOrNtPathElement; LengthFunction
0x180036b4c  lea     r8, [rsp+170h+DestinationString]; UnicodeStringOrUnicodeStringBuffer
0x180036b51  lea     edx, [rsi+10h]; Type
0x180036b54  xor     ecx, ecx; Flags
0x180036b56  call    cs:__imp_RtlpApplyLengthFunction
0x180036b5c  lea     rcx, WPP_GLOBAL_Control
0x180036b63  mov     ebx, eax
0x180036b65  test    eax, eax
0x180036b67  jz      short loc_180036BB2
0x180036b69  mov     rax, cs:WPP_GLOBAL_Control
0x180036b70  cmp     rax, rcx
0x180036b73  jz      short loc_180036BA6
0x180036b75  test    byte ptr [rax+6Ch], 1
0x180036b79  jz      short loc_180036BA6
0x180036b7b  mov     edx, ebx
0x180036b7d  lea     rcx, aCscsyncaddnewr_5; "CscSyncAddNewRemoteItemToItemTree: RtlR"...
0x180036b84  call    SyncTraceOutputInternal
0x180036b89  mov     rcx, cs:WPP_GLOBAL_Control
0x180036b90  lea     edx, [rsi+29h]
0x180036b93  mov     r9d, ebx
0x180036b96  lea     r8, WPP_49c63760df5a37e97d50b2be11371744_Traceguids
0x180036b9d  mov     rcx, [rcx+60h]
0x180036ba1  call    WPP_SF_d
0x180036ba6  lea     r14, WPP_GLOBAL_Control
0x180036bad  jmp     loc_180036E70
0x180036bb2  movzx   eax, [rsp+170h+DestinationString.Length]
0x180036bb7  lea     rcx, [rsp+170h+var_F8]; DestinationString
0x180036bbc  shr     rax, 1
0x180036bbf  lea     rdx, [rdi+rax*2]; SourceString
0x180036bc3  call    cs:__imp_RtlInitUnicodeString
0x180036bc9  mov     r9, cs:__imp_RtlGetLengthWithoutTrailingPathSeperators; LengthFunction
0x180036bd0  lea     r8, [rsp+170h+DestinationString]; UnicodeStringOrUnicodeStringBuffer
0x180036bd5  mov     edx, 10h; Type
0x180036bda  xor     ecx, ecx; Flags
0x180036bdc  call    cs:__imp_RtlpApplyLengthFunction
0x180036be2  mov     ebx, eax
0x180036be4  test    eax, eax
0x180036be6  jz      short loc_180036C21
0x180036be8  mov     rax, cs:WPP_GLOBAL_Control
0x180036bef  lea     r14, WPP_GLOBAL_Control
0x180036bf6  cmp     rax, r14
0x180036bf9  jz      loc_180036E70
0x180036bff  test    byte ptr [rax+6Ch], 1
0x180036c03  jz      loc_180036E70
0x180036c09  mov     edx, ebx
0x180036c0b  lea     rcx, aCscsyncaddnewr_1; "CscSyncAddNewRemoteItemToItemTree: RtlR"...
0x180036c12  call    SyncTraceOutputInternal
0x180036c17  mov     edx, 2Ah ; '*'
0x180036c1c  jmp     loc_180036E56
0x180036c21  mov     r9d, 81h
0x180036c27  mov     [rsp+170h+var_150], 5
0x180036c2f  lea     r8, [rsp+170h+DestinationString]
0x180036c34  xor     edx, edx
0x180036c36  lea     rcx, [rsp+170h+hHandle]
0x180036c3b  call    SyncOpenUNCPathServerForEnumeration
0x180036c40  mov     ebx, eax
0x180036c42  test    eax, eax
0x180036c44  jz      short loc_180036C7F
0x180036c46  mov     rax, cs:WPP_GLOBAL_Control
0x180036c4d  lea     r14, WPP_GLOBAL_Control
0x180036c54  cmp     rax, r14
0x180036c57  jz      loc_180036E70
0x180036c5d  test    byte ptr [rax+6Ch], 1
0x180036c61  jz      loc_180036E70
0x180036c67  mov     edx, ebx
0x180036c69  lea     rcx, aCscsyncaddnewr; "CscSyncAddNewRemoteItemToItemTree: Sync"...
0x180036c70  call    SyncTraceOutputInternal
0x180036c75  mov     edx, 2Bh ; '+'
0x180036c7a  jmp     loc_180036E56
0x180036c7f  mov     edi, 10000h
0x180036c84  mov     ecx, edi
0x180036c86  call    SyncAlloc
0x180036c8b  mov     rsi, rax
0x180036c8e  test    rax, rax
0x180036c91  jnz     short loc_180036CD3
0x180036c93  mov     rax, cs:WPP_GLOBAL_Control
0x180036c9a  lea     r14, WPP_GLOBAL_Control
0x180036ca1  cmp     rax, r14
0x180036ca4  jz      loc_180036E70
0x180036caa  test    byte ptr [rax+6Ch], 8
0x180036cae  jz      loc_180036E70
0x180036cb4  mov     edx, 0C000009Ah
0x180036cb9  lea     rcx, aCscsyncaddnewr_2; "CscSyncAddNewRemoteItemToItemTree: 0x%x"
0x180036cc0  call    SyncTraceOutputInternal
0x180036cc5  lea     edx, [rsi+2Ch]
0x180036cc8  mov     r9d, 0C000009Ah
0x180036cce  jmp     loc_180036E59
0x180036cd3  mov     rcx, [rsp+170h+hHandle]; hHandle
0x180036cd8  lea     rax, [rsp+170h+var_F8]
0x180036cdd  mov     [rsp+170h+var_130], 0; char
0x180036ce2  lea     rdx, [rsp+170h+var_118]
0x180036ce7  mov     [rsp+170h+var_138], 1; char
0x180036cec  mov     r9d, edi
0x180036cef  mov     [rsp+170h+var_140], rax; PUNICODE_STRING
0x180036cf4  mov     r8, rsi
0x180036cf7  mov     [rsp+170h+var_148], 1; char
0x180036cfc  mov     [rsp+170h+var_150], 3; FILE_INFORMATION_CLASS
0x180036d04  call    SyncQueryDirectory
0x180036d09  mov     ebx, eax
0x180036d0b  test    eax, eax
0x180036d0d  jz      short loc_180036D48
0x180036d0f  mov     rax, cs:WPP_GLOBAL_Control
0x180036d16  lea     r14, WPP_GLOBAL_Control
0x180036d1d  cmp     rax, r14
0x180036d20  jz      loc_180036E70
0x180036d26  test    byte ptr [rax+6Ch], 1
0x180036d2a  jz      loc_180036E70
0x180036d30  mov     edx, ebx
0x180036d32  lea     rcx, aCscsyncaddnewr_4; "CscSyncAddNewRemoteItemToItemTree: Sync"...
0x180036d39  call    SyncTraceOutputInternal
0x180036d3e  mov     edx, 2Dh ; '-'
0x180036d43  jmp     loc_180036E56
0x180036d48  movzx   r8d, [rsp+170h+var_F8.Length]
0x180036d4e  lea     rdx, [rsp+170h+var_120]
0x180036d53  mov     rcx, r14
0x180036d56  call    CscSyncpCreateNewTreeFullItem
0x180036d5b  mov     ebx, eax
0x180036d5d  test    eax, eax
0x180036d5f  jnz     loc_180036E2A
0x180036d65  mov     rdi, qword ptr [rsp+170h+var_120]
0x180036d6a  test    rdi, rdi
0x180036d6d  jz      loc_180036E2A
0x180036d73  mov     eax, [rsi+38h]
0x180036d76  lea     rcx, [rbp+70h+var_C0]; void *
0x180036d7a  mov     [rbp+70h+var_D0], eax
0x180036d7d  xor     edx, edx; Val
0x180036d7f  mov     rax, [rsi+18h]
0x180036d83  mov     r8d, 80h; Size
0x180036d89  mov     [rbp+70h+var_D8], rax
0x180036d8d  mov     rax, [rsi+20h]
0x180036d91  mov     [rbp+70h+var_E0], rax
0x180036d95  mov     rax, [rsi+28h]
0x180036d99  mov     [rbp+70h+var_E8], rax
0x180036d9d  call    memset_0
0x180036da2  lea     r8, [rbp+70h+var_C0]
0x180036da6  xor     edx, edx
0x180036da8  lea     rcx, [rbp+70h+var_E8]
0x180036dac  call    SyncItemAddServerEnumInfo
0x180036db1  movzx   edx, [rsp+170h+var_F8.Length]
0x180036db6  lea     r8, [rbp+70h+var_C0]
0x180036dba  mov     rcx, [rbp+70h+var_F8.Buffer]
0x180036dbe  mov     r9, rdi
0x180036dc1  call    SyncItemAddStateToItem
0x180036dc6  mov     r8, qword ptr [rsp+170h+var_120]; int
0x180036dcb  mov     r9d, 58001h; int
0x180036dd1  mov     rdx, r12; int
0x180036dd4  mov     [rsp+170h+var_150], ebx; Status
0x180036dd8  mov     rcx, r14; int
0x180036ddb  call    CscSyncpAddNewTreeFullItem
0x180036de0  mov     ebx, eax
0x180036de2  test    eax, eax
0x180036de4  jz      short loc_180036E14
0x180036de6  mov     rax, cs:WPP_GLOBAL_Control
0x180036ded  lea     r14, WPP_GLOBAL_Control
0x180036df4  cmp     rax, r14
0x180036df7  jz      short loc_180036E70
0x180036df9  test    byte ptr [rax+6Ch], 1
0x180036dfd  jz      short loc_180036E70
0x180036dff  mov     edx, ebx
0x180036e01  lea     rcx, aCscsyncaddnewr_3; "CscSyncAddNewRemoteItemToItemTree: Sync"...
0x180036e08  call    SyncTraceOutputInternal
0x180036e0d  mov     edx, 2Fh ; '/'
0x180036e12  jmp     short loc_180036E56
0x180036e14  mov     rax, qword ptr [rsp+170h+var_120]
0x180036e19  mov     [r15], rax
0x180036e1c  mov     qword ptr [rsp+170h+var_120], 0
0x180036e25  jmp     loc_180036BA6
0x180036e2a  mov     rax, cs:WPP_GLOBAL_Control
0x180036e31  lea     r14, WPP_GLOBAL_Control
0x180036e38  cmp     rax, r14
0x180036e3b  jz      short loc_180036E70
0x180036e3d  test    byte ptr [rax+6Ch], 1
0x180036e41  jz      short loc_180036E70
0x180036e43  mov     edx, ebx
0x180036e45  lea     rcx, aCscsyncaddnewr_0; "CscSyncAddNewRemoteItemToItemTree: CscS"...
0x180036e4c  call    SyncTraceOutputInternal
0x180036e51  mov     edx, 2Eh ; '.'
0x180036e56  mov     r9d, ebx
0x180036e59  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e60  lea     r8, WPP_49c63760df5a37e97d50b2be11371744_Traceguids
0x180036e67  mov     rcx, [rcx+60h]
0x180036e6b  call    WPP_SF_d
0x180036e70  mov     rcx, [rsp+170h+hHandle]; Handle
0x180036e75  test    rcx, rcx
0x180036e78  jz      short loc_180036E7F
0x180036e7a  call    SyncCloseFile
0x180036e7f  test    rsi, rsi
0x180036e82  jz      short loc_180036E8C
0x180036e84  mov     rcx, rsi
0x180036e87  call    SyncFree
0x180036e8c  mov     rdi, qword ptr [rsp+170h+var_120]
0x180036e91  test    rdi, rdi
0x180036e94  jz      short loc_180036E9E
0x180036e96  mov     rcx, rdi
0x180036e99  call    SyncFree
0x180036e9e  mov     rax, cs:WPP_GLOBAL_Control
0x180036ea5  cmp     rax, r14
0x180036ea8  jz      short loc_180036EDD
0x180036eaa  test    byte ptr [rax+6Ch], 8
0x180036eae  jz      short loc_180036EDD
0x180036eb0  mov     edx, ebx
0x180036eb2  lea     rcx, aCscsyncaddnewr_2; "CscSyncAddNewRemoteItemToItemTree: 0x%x"
0x180036eb9  call    SyncTraceOutputInternal
0x180036ebe  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ec5  lea     r8, WPP_49c63760df5a37e97d50b2be11371744_Traceguids
0x180036ecc  mov     edx, 30h ; '0'
0x180036ed1  mov     r9d, ebx
0x180036ed4  mov     rcx, [rcx+60h]
0x180036ed8  call    WPP_SF_d
0x180036edd  mov     ecx, ebx; Status
0x180036edf  call    cs:__imp_RtlNtStatusToDosError
0x180036ee5  mov     rcx, [rbp+70h+var_40]
0x180036ee9  xor     rcx, rsp; StackCookie
0x180036eec  call    __security_check_cookie
0x180036ef1  add     rsp, 140h
0x180036ef8  pop     r15
0x180036efa  pop     r14
0x180036efc  pop     r12
0x180036efe  pop     rdi
0x180036eff  pop     rsi
0x180036f00  pop     rbx
0x180036f01  pop     rbp
0x180036f02  retn
```
