# PrjfGetUnionContextByFileNameEx

- ea: `0x1400037e0`
- end: `0x140003a86`
- name: `PrjfGetUnionContextByFileNameEx`
- size: `678`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, char, struct _FLT_INSTANCE *, UNICODE_STRING *, char **, __int64, char *)`
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140001b3c`
- `0x140006a58`
- `0x140006ca0`
- `0x140022320`
- `0x140039de8`

## callees

- `0x1400035d4`
- `0x1400037e0`
- `0x140003e6c`
- `0x14000b1d0`
- `0x14000d128`
- `0x14003775c`
- `0x140037ac0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140003a71`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003a71`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003917`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003917`
- `FLTMGR!FltGetFileNameInformation` at `0x140003833`
- `FLTMGR!FltGetFileNameInformation` at `0x140003833`

## pseudocode

```c
__int64 __fastcall PrjfGetUnionContextByFileNameEx(
        PFLT_CALLBACK_DATA CallbackData,
        char a2,
        struct _FLT_INSTANCE *a3,
        UNICODE_STRING *a4,
        char **a5,
        __int64 a6,
        char *a7)
{
  char **v7; // rbp
  UNICODE_STRING *p_Name; // r14
  NTSTATUS UnicodeString; // edi
  int v12; // edx
  int v13; // r8d
  char *v14; // rsi
  char *UnionContextByFileName; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rbx
  USHORT v20; // ax
  int v21; // edx
  int v22; // r8d
  int v23; // edx
  int v24; // r8d
  void *v25; // rcx
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+A8h] [rbp+20h] BYREF

  v7 = a5;
  FileNameInformation = 0;
  p_Name = a4;
  UnicodeString = 0;
  *a5 = 0;
  if ( !a4 )
  {
    UnicodeString = FltGetFileNameInformation(CallbackData, a2 != 0 ? 67109121 : 257, &FileNameInformation);
    if ( UnicodeString < 0 )
    {
      v14 = 0;
      if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = BYTE1(xmmword_14001A3D0) & 2;
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          521,
          v12,
          v13,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          9,
          37,
          (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
          71,
          UnicodeString);
      }
      goto LABEL_12;
    }
    p_Name = &FileNameInformation->Name;
  }
  UnionContextByFileName = PrjfGetUnionContextByFileName(CallbackData, a3, p_Name, a7);
  v14 = UnionContextByFileName;
  if ( !UnionContextByFileName )
    goto LABEL_12;
  v17 = *((unsigned __int16 *)UnionContextByFileName + 20);
  v18 = a6;
  if ( p_Name->Length == (_WORD)v17 )
  {
    *(_QWORD *)(a6 + 8) = 0;
    *(_DWORD *)v18 = 0;
LABEL_11:
    *v7 = v14;
    v14 = 0;
    goto LABEL_12;
  }
  v20 = p_Name->Length - v17 - 2;
  *(_WORD *)(a6 + 2) = v20;
  if ( v20 >= p_Name->Length )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16);
  if ( !*(_WORD *)(v18 + 2) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16);
  UnicodeString = PrjfAllocateUnicodeString(1852197456, v18);
  if ( UnicodeString >= 0 )
  {
    UnicodeString = PrjfConvertFullPathToRelative(v14 + 40, p_Name, v18);
    if ( UnicodeString >= 0 )
      goto LABEL_11;
    if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v23) = BYTE1(xmmword_14001A3D0) & 2;
      LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        521,
        v23,
        v24,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        9,
        39,
        (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
        128,
        UnicodeString);
    }
    v25 = *(void **)(v18 + 8);
    if ( v25 )
    {
      ExFreePoolWithTag(v25, 0x6E664A50u);
      *(_QWORD *)(v18 + 8) = 0;
    }
  }
  else if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v21) = BYTE1(xmmword_14001A3D0) & 2;
    LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      521,
      v21,
      v22,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      9,
      38,
      (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
      115,
      UnicodeString);
  }
LABEL_12:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v14 )
    PrjfReleaseUnionContext(v14);
  return (unsigned int)UnicodeString;
}

```

## disassembly

```asm
0x1400037e0  mov     rax, rsp
0x1400037e3  mov     [rax+8], rbx
0x1400037e7  mov     [rax+10h], rbp
0x1400037eb  push    rsi
0x1400037ec  push    rdi
0x1400037ed  push    r12
0x1400037ef  push    r14
0x1400037f1  push    r15
0x1400037f3  sub     rsp, 60h
0x1400037f7  mov     rbp, [rsp+88h+arg_20]
0x1400037ff  xor     r12d, r12d
0x140003802  mov     [rax+20h], r12
0x140003806  mov     r14, r9
0x140003809  mov     rsi, r8
0x14000380c  mov     rbx, rcx
0x14000380f  mov     edi, r12d
0x140003812  mov     [rbp+0], r12
0x140003816  test    r9, r9
0x140003819  jnz     loc_1400038C9
0x14000381f  neg     dl
0x140003821  lea     r8, [rax+20h]; FileNameInformation
0x140003825  sbb     edx, edx
0x140003827  and     edx, 4000000h
0x14000382d  add     edx, 101h; NameOptions
0x140003833  call    cs:__imp_FltGetFileNameInformation
0x14000383a  nop     dword ptr [rax+rax+00h]
0x14000383f  mov     edi, eax
0x140003841  test    eax, eax
0x140003843  jns     short loc_1400038BD
0x140003845  mov     esi, r12d
0x140003848  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14000384e  lea     rax, WPP_RECORDER_INITIALIZED
0x140003855  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000385c  setnz   r8b
0x140003860  and     dl, 2
0x140003863  jnz     short loc_14000386E
0x140003865  test    r8b, r8b
0x140003868  jz      loc_14000390A
0x14000386e  mov     [rsp+88h+var_38], edi
0x140003872  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140003879  mov     [rsp+88h+var_40], 847h
0x140003881  mov     [rsp+88h+var_48], rax
0x140003886  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x14000388d  mov     [rsp+88h+var_50], rax
0x140003892  mov     [rsp+88h+var_58], 25h ; '%'
0x140003899  mov     r9, cs:WPP_GLOBAL_Control
0x1400038a0  mov     ecx, 209h
0x1400038a5  mov     [rsp+88h+var_60], 9
0x1400038ad  mov     [rsp+88h+var_68], 2
0x1400038b2  mov     r9, [r9+40h]
0x1400038b6  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400038bb  jmp     short loc_14000390A
0x1400038bd  mov     r14, [rsp+88h+FileNameInformation]
0x1400038c5  add     r14, 8
0x1400038c9  mov     r9, [rsp+88h+arg_30]
0x1400038d1  mov     r8, r14; String2
0x1400038d4  mov     rdx, rsi; Instance
0x1400038d7  mov     rcx, rbx; CallbackData
0x1400038da  call    PrjfGetUnionContextByFileName
0x1400038df  mov     rsi, rax
0x1400038e2  test    rax, rax
0x1400038e5  jz      short loc_14000390A
0x1400038e7  movzx   ecx, word ptr [rax+28h]
0x1400038eb  movzx   eax, word ptr [r14]
0x1400038ef  mov     rbx, [rsp+88h+arg_28]
0x1400038f7  cmp     ax, cx
0x1400038fa  jnz     short loc_14000394C
0x1400038fc  mov     [rbx+8], r12
0x140003900  mov     [rbx], r12d
0x140003903  mov     [rbp+0], rsi
0x140003907  mov     rsi, r12
0x14000390a  mov     rcx, [rsp+88h+FileNameInformation]; FileNameInformation
0x140003912  test    rcx, rcx
0x140003915  jz      short loc_140003923
0x140003917  call    cs:__imp_FltReleaseFileNameInformation
0x14000391e  nop     dword ptr [rax+rax+00h]
0x140003923  test    rsi, rsi
0x140003926  jz      short loc_140003930
0x140003928  mov     rcx, rsi; P
0x14000392b  call    PrjfReleaseUnionContext
0x140003930  lea     r11, [rsp+88h+var_28]
0x140003935  mov     eax, edi
0x140003937  mov     rbx, [r11+30h]
0x14000393b  mov     rbp, [r11+38h]
0x14000393f  mov     rsp, r11
0x140003942  pop     r15
0x140003944  pop     r14
0x140003946  pop     r12
0x140003948  pop     rdi
0x140003949  pop     rsi
0x14000394a  retn
0x14000394c  sub     ax, cx
0x14000394f  sub     ax, 2
0x140003953  mov     [rbx+2], ax
0x140003957  cmp     ax, [r14]
0x14000395b  jb      short loc_140003962
0x14000395d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140003962  cmp     [rbx+2], r12w
0x140003967  ja      short loc_14000396E
0x140003969  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000396e  mov     rdx, rbx
0x140003971  mov     ecx, 6E664A50h
0x140003976  call    PrjfAllocateUnicodeString
0x14000397b  mov     edi, eax
0x14000397d  test    eax, eax
0x14000397f  jns     short loc_1400039D7
0x140003981  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140003987  lea     rax, WPP_RECORDER_INITIALIZED
0x14000398e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003995  setnz   r8b
0x140003999  and     dl, 2
0x14000399c  jnz     short loc_1400039A7
0x14000399e  test    r8b, r8b
0x1400039a1  jz      loc_14000390A
0x1400039a7  mov     [rsp+88h+var_38], edi
0x1400039ab  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400039b2  mov     [rsp+88h+var_40], 873h
0x1400039ba  mov     [rsp+88h+var_48], rax
0x1400039bf  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x1400039c6  mov     [rsp+88h+var_50], rax
0x1400039cb  mov     [rsp+88h+var_58], 26h ; '&'
0x1400039d2  jmp     loc_140003899
0x1400039d7  mov     r8, rbx
0x1400039da  lea     rcx, [rsi+28h]
0x1400039de  mov     rdx, r14
0x1400039e1  call    PrjfConvertFullPathToRelative
0x1400039e6  mov     edi, eax
0x1400039e8  test    eax, eax
0x1400039ea  jns     loc_140003903
0x1400039f0  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400039f6  lea     rax, WPP_RECORDER_INITIALIZED
0x1400039fd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140003a04  setnz   r8b
0x140003a08  and     dl, 2
0x140003a0b  jnz     short loc_140003A12
0x140003a0d  test    r8b, r8b
0x140003a10  jz      short loc_140003A5F
0x140003a12  mov     r9, cs:WPP_GLOBAL_Control
0x140003a19  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140003a20  mov     [rsp+88h+var_38], edi
0x140003a24  mov     ecx, 209h
0x140003a29  mov     [rsp+88h+var_40], 880h
0x140003a31  mov     [rsp+88h+var_48], rax
0x140003a36  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140003a3d  mov     r9, [r9+40h]
0x140003a41  mov     [rsp+88h+var_50], rax
0x140003a46  mov     [rsp+88h+var_58], 27h ; '''
0x140003a4d  mov     [rsp+88h+var_60], 9
0x140003a55  mov     [rsp+88h+var_68], 2
0x140003a5a  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140003a5f  mov     rcx, [rbx+8]; P
0x140003a63  test    rcx, rcx
0x140003a66  jz      loc_14000390A
0x140003a6c  mov     edx, 6E664A50h; Tag
0x140003a71  call    cs:__imp_ExFreePoolWithTag
0x140003a78  nop     dword ptr [rax+rax+00h]
0x140003a7d  mov     [rbx+8], r12
0x140003a81  jmp     loc_14000390A
```
