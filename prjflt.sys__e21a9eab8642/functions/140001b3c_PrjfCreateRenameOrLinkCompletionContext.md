# PrjfCreateRenameOrLinkCompletionContext

- ea: `0x140001b3c`
- end: `0x1400020ac`
- name: `PrjfCreateRenameOrLinkCompletionContext`
- size: `1392`
- prototype: `__int64 __fastcall(__int64, struct _FLT_INSTANCE *, __int64, __int64, PFILE_OBJECT **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002c98c`

## callees

- `0x140001b3c`
- `0x140002f3c`
- `0x1400037e0`
- `0x140003d9c`
- `0x140003e6c`
- `0x14000b1d0`
- `0x14000be80`
- `0x14000d008`
- `0x14000d128`
- `0x14000d754`
- `0x14000dc28`
- `0x14000de28`
- `0x14003c4b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000206b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002082`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000206b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002082`
- `ntoskrnl!ObfReferenceObject` at `0x140001fd3`
- `ntoskrnl!ObfReferenceObject` at `0x140001fd3`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140001d9f`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140001d9f`
- `FLTMGR!FltParseFileNameInformation` at `0x140001e75`
- `FLTMGR!FltParseFileNameInformation` at `0x140001e75`
- `FLTMGR!FltClose` at `0x140002042`
- `FLTMGR!FltClose` at `0x140002042`
- `FLTMGR!FltReleaseContext` at `0x140002018`
- `FLTMGR!FltReleaseContext` at `0x14000202d`
- `FLTMGR!FltReleaseContext` at `0x140002018`
- `FLTMGR!FltReleaseContext` at `0x14000202d`

## pseudocode

```c
__int64 __fastcall PrjfCreateRenameOrLinkCompletionContext(
        __int64 a1,
        struct _FLT_INSTANCE *a2,
        __int64 a3,
        __int64 a4,
        PFILE_OBJECT **a5)
{
  PFILE_OBJECT *v9; // rbx
  struct _FILE_OBJECT *v10; // r14
  __int64 v11; // rsi
  int UnionContextByFileName; // eax
  int v13; // edx
  int v14; // r8d
  int SetContextFileObject; // edi
  struct _FILE_OBJECT *v16; // rsi
  int v17; // eax
  int v18; // edx
  int v19; // r8d
  PFILE_OBJECT *v20; // rax
  int v21; // edx
  int v22; // r8d
  __int128 v23; // xmm0
  __int128 v24; // xmm0
  int v25; // r8d
  void *v26; // rcx
  __int64 v27; // rcx
  __int16 v28; // ax
  int v29; // edx
  int v30; // r8d
  int v31; // edx
  int v32; // r8d
  int v34; // [rsp+20h] [rbp-91h]
  int v35; // [rsp+20h] [rbp-91h]
  int v36; // [rsp+28h] [rbp-89h]
  int v37; // [rsp+28h] [rbp-89h]
  int v38; // [rsp+30h] [rbp-81h]
  int v39; // [rsp+30h] [rbp-81h]
  int v40; // [rsp+38h] [rbp-79h]
  int v41; // [rsp+40h] [rbp-71h]
  __int64 v42; // [rsp+80h] [rbp-31h] BYREF
  PFLT_CONTEXT Context; // [rsp+88h] [rbp-29h] BYREF
  PFLT_CONTEXT v44; // [rsp+90h] [rbp-21h] BYREF
  HANDLE FileHandle; // [rsp+98h] [rbp-19h] BYREF
  __m128i v46; // [rsp+A0h] [rbp-11h] BYREF
  PVOID P[2]; // [rsp+B0h] [rbp-1h] BYREF
  PVOID v48[2]; // [rsp+C0h] [rbp+Fh] BYREF
  char v49; // [rsp+120h] [rbp+6Fh] BYREF
  PVOID v50; // [rsp+128h] [rbp+77h] BYREF

  v50 = 0;
  v42 = 0;
  FileHandle = 0;
  v49 = 0;
  Context = 0;
  v44 = 0;
  v9 = 0;
  v10 = 0;
  *(_OWORD *)P = 0;
  *(_OWORD *)v48 = 0;
  v46 = 0;
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, 0);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3);
  *a5 = 0;
  v11 = a3 + 8;
  UnionContextByFileName = PrjfGetUnionContextByFileNameEx(0, (__int64)&v50, (__int64)P, 0);
  SetContextFileObject = UnionContextByFileName;
  if ( UnionContextByFileName < 0 )
  {
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        526,
        v13,
        v14,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        51,
        (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
        8,
        UnionContextByFileName,
        v11);
    }
    v16 = (struct _FILE_OBJECT *)v50;
    goto LABEL_42;
  }
  v17 = PrjfGetUnionContextByFileNameEx(0, (__int64)&v42, (__int64)v48, 0);
  SetContextFileObject = v17;
  if ( v17 < 0 )
  {
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v18) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        526,
        v18,
        v19,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        52,
        (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
        26,
        v17,
        a4 + 8);
    }
    v16 = (struct _FILE_OBJECT *)v50;
    v10 = (struct _FILE_OBJECT *)v42;
    goto LABEL_42;
  }
  v16 = (struct _FILE_OBJECT *)v50;
  v10 = (struct _FILE_OBJECT *)v42;
  if ( v50 || v42 )
  {
    v20 = (PFILE_OBJECT *)ExAllocateFromPagedLookasideList(&Lookaside);
    v9 = v20;
    if ( !v20 )
    {
      SetContextFileObject = -1073741670;
      if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v21) = xmmword_14001A3D0 & 0x20;
        LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          517,
          v21,
          v22,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          5,
          54,
          (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
          45,
          154);
      }
      goto LABEL_42;
    }
    memset(v20, 0, 0x58u);
    if ( v16 )
    {
      v23 = *(_OWORD *)P;
      *v9 = v16;
      v16 = 0;
      P[1] = 0;
      *(_OWORD *)(v9 + 1) = v23;
    }
    if ( v10 )
    {
      v24 = *(_OWORD *)v48;
      v9[7] = v10;
      v10 = 0;
      *((_OWORD *)v9 + 4) = v24;
      v48[1] = 0;
      SetContextFileObject = FltParseFileNameInformation((PFLT_FILE_NAME_INFORMATION)a4);
      if ( SetContextFileObject < 0 )
      {
LABEL_42:
        if ( v16 )
          PrjfReleaseUnionContext(v16);
        if ( v10 )
          PrjfReleaseUnionContext(v10);
        if ( Context )
          FltReleaseContext(Context);
        if ( v44 )
          FltReleaseContext(v44);
        if ( FileHandle )
          FltClose(FileHandle);
        if ( v9 )
          PrjfReleaseRenameOrLinkCompletionContext(v9);
        goto LABEL_54;
      }
      v26 = *(void **)(*(_QWORD *)(a1 + 16) + 40LL);
      if ( v26 )
      {
        ObfReferenceObject(v26);
        v9[10] = *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 16) + 40LL);
      }
      else
      {
        v46 = *(__m128i *)(a4 + 8);
        v27 = (unsigned __int16)(_mm_cvtsi128_si32(v46) - *(_WORD *)(a4 + 88));
        v28 = v27 - 2;
        if ( (_WORD)v27 - 2 == *(_WORD *)(a4 + 24) )
          v28 = v27;
        v46.m128i_i16[0] = v28;
        SetContextFileObject = PrjfOpenPlaceHolder(
                                 (_DWORD)a2,
                                 (unsigned int)&v46,
                                 v25,
                                 (unsigned int)&FileHandle,
                                 (__int64)(v9 + 10),
                                 (__int64)&v49);
        if ( SetContextFileObject < 0 )
        {
          if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v29) = BYTE1(xmmword_14001A3D0) & 0x20;
            LOBYTE(v30) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDqqZd(
              (unsigned int)&WPP_RECORDER_INITIALIZED,
              v29,
              v30,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              v34,
              v36,
              v38);
          }
          goto LABEL_42;
        }
        if ( v49 )
        {
          SetContextFileObject = PrjfGetSetContextFileObject(a2, v9[10], 0x80000000, 1, 0, 0, 0, &Context, &v44);
          if ( SetContextFileObject < 0 )
          {
            if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0
              || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v31) = BYTE1(xmmword_14001A3D0) & 0x20;
              LOBYTE(v32) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDqqqZd(
                (unsigned int)&WPP_RECORDER_INITIALIZED,
                v31,
                v32,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                v35,
                v37,
                v39,
                v40,
                v41);
            }
            goto LABEL_42;
          }
        }
      }
    }
    *a5 = v9;
    v9 = 0;
    goto LABEL_42;
  }
  if ( (BYTE1(xmmword_14001A3E0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v18) = BYTE1(xmmword_14001A3E0) & 0x40;
    LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(
      1038,
      v18,
      v19,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      4,
      14,
      53,
      (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
      35);
  }
LABEL_54:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x6E664A50u);
  if ( v48[1] )
    ExFreePoolWithTag(v48[1], 0x6E664A50u);
  return (unsigned int)SetContextFileObject;
}

```

## disassembly

```asm
0x140001b3c  mov     [rsp-8+arg_0], rbx
0x140001b41  push    rbp
0x140001b42  push    rsi
0x140001b43  push    rdi
0x140001b44  push    r12
0x140001b46  push    r13
0x140001b48  push    r14
0x140001b4a  push    r15
0x140001b4c  lea     rbp, [rsp-1Fh]
0x140001b51  sub     rsp, 0D0h
0x140001b58  xor     esi, esi
0x140001b5a  xorps   xmm0, xmm0
0x140001b5d  mov     [rbp+4Fh+arg_18], rsi
0x140001b61  xorps   xmm1, xmm1
0x140001b64  mov     [rbp+4Fh+var_80], rsi
0x140001b68  mov     r13, r9
0x140001b6b  mov     [rbp+4Fh+FileHandle], rsi
0x140001b6f  mov     rdi, r8
0x140001b72  mov     [rbp+4Fh+arg_10], sil
0x140001b76  mov     r15, rdx
0x140001b79  mov     [rbp+4Fh+Context], rsi
0x140001b7d  mov     r12, rcx
0x140001b80  mov     [rbp+4Fh+var_70], rsi
0x140001b84  mov     ebx, esi
0x140001b86  mov     r14d, esi
0x140001b89  movups  xmmword ptr [rbp+4Fh+P], xmm0
0x140001b8d  movups  xmmword ptr [rbp+4Fh+var_40], xmm1
0x140001b91  movups  [rbp+4Fh+var_60], xmm0
0x140001b95  test    r8, r8
0x140001b98  jnz     short loc_140001B9F
0x140001b9a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140001b9f  test    r13, r13
0x140001ba2  jnz     short loc_140001BA9
0x140001ba4  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140001ba9  mov     rax, [rbp+4Fh+arg_20]
0x140001bad  mov     r8, r15
0x140001bb0  mov     [rsp+100h+var_D0], rbx; __int64
0x140001bb5  xor     edx, edx
0x140001bb7  xor     ecx, ecx; CallbackData
0x140001bb9  mov     [rax], rsi
0x140001bbc  lea     rax, [rbp+4Fh+P]
0x140001bc0  mov     [rsp+100h+var_D8], rax; __int64
0x140001bc5  lea     rsi, [rdi+8]
0x140001bc9  lea     rax, [rbp+4Fh+arg_18]
0x140001bcd  mov     r9, rsi
0x140001bd0  mov     qword ptr [rsp+100h+var_E0], rax; __int64
0x140001bd5  call    PrjfGetUnionContextByFileNameEx
0x140001bda  mov     edi, eax
0x140001bdc  test    eax, eax
0x140001bde  jns     short loc_140001C5D
0x140001be0  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140001be6  lea     rcx, WPP_RECORDER_INITIALIZED
0x140001bed  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140001bf4  setnz   r8b
0x140001bf8  and     dl, 40h
0x140001bfb  jnz     short loc_140001C02
0x140001bfd  test    r8b, r8b
0x140001c00  jz      short loc_140001C54
0x140001c02  mov     r9, cs:WPP_GLOBAL_Control
0x140001c09  mov     ecx, 20Eh
0x140001c0e  mov     [rsp+100h+var_A8], rsi
0x140001c13  mov     dword ptr [rsp+100h+var_B0], eax
0x140001c17  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140001c1e  mov     [rsp+100h+var_B8], 0B08h
0x140001c26  mov     r9, [r9+40h]
0x140001c2a  mov     [rsp+100h+var_C0], rax
0x140001c2f  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140001c36  mov     [rsp+100h+var_C8], rax
0x140001c3b  mov     word ptr [rsp+100h+var_D0], 33h ; '3'
0x140001c42  mov     dword ptr [rsp+100h+var_D8], 0Eh
0x140001c4a  mov     [rsp+100h+var_E0], 2
0x140001c4f  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140001c54  mov     rsi, [rbp+4Fh+arg_18]
0x140001c58  jmp     loc_140001FF5
0x140001c5d  lea     rax, [rbp+4Fh+var_40]
0x140001c61  mov     [rsp+100h+var_D0], rbx; __int64
0x140001c66  mov     [rsp+100h+var_D8], rax; __int64
0x140001c6b  lea     rsi, [r13+8]
0x140001c6f  lea     rax, [rbp+4Fh+var_80]
0x140001c73  mov     r9, rsi
0x140001c76  mov     r8, r15
0x140001c79  mov     qword ptr [rsp+100h+var_E0], rax; __int64
0x140001c7e  xor     edx, edx
0x140001c80  xor     ecx, ecx; CallbackData
0x140001c82  call    PrjfGetUnionContextByFileNameEx
0x140001c87  mov     edi, eax
0x140001c89  test    eax, eax
0x140001c8b  jns     loc_140001D12
0x140001c91  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140001c97  lea     rcx, WPP_RECORDER_INITIALIZED
0x140001c9e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140001ca5  setnz   r8b
0x140001ca9  and     dl, 40h
0x140001cac  jnz     short loc_140001CB3
0x140001cae  test    r8b, r8b
0x140001cb1  jz      short loc_140001D05
0x140001cb3  mov     r9, cs:WPP_GLOBAL_Control
0x140001cba  mov     ecx, 20Eh
0x140001cbf  mov     [rsp+100h+var_A8], rsi
0x140001cc4  mov     dword ptr [rsp+100h+var_B0], eax
0x140001cc8  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140001ccf  mov     [rsp+100h+var_B8], 0B1Ah
0x140001cd7  mov     r9, [r9+40h]
0x140001cdb  mov     [rsp+100h+var_C0], rax
0x140001ce0  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140001ce7  mov     [rsp+100h+var_C8], rax
0x140001cec  mov     word ptr [rsp+100h+var_D0], 34h ; '4'
0x140001cf3  mov     dword ptr [rsp+100h+var_D8], 0Eh
0x140001cfb  mov     [rsp+100h+var_E0], 2
0x140001d00  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140001d05  mov     rsi, [rbp+4Fh+arg_18]
0x140001d09  mov     r14, [rbp+4Fh+var_80]
0x140001d0d  jmp     loc_140001FF5
0x140001d12  mov     rsi, [rbp+4Fh+arg_18]
0x140001d16  mov     r14, [rbp+4Fh+var_80]
0x140001d1a  test    rsi, rsi
0x140001d1d  jnz     short loc_140001D98
0x140001d1f  test    r14, r14
0x140001d22  jnz     short loc_140001D98
0x140001d24  mov     dl, byte ptr cs:xmmword_14001A3E0+1
0x140001d2a  lea     rcx, WPP_RECORDER_INITIALIZED
0x140001d31  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140001d38  setnz   r8b
0x140001d3c  and     dl, 40h
0x140001d3f  jnz     short loc_140001D4A
0x140001d41  test    r8b, r8b
0x140001d44  jz      loc_14000205B
0x140001d4a  mov     r9, cs:WPP_GLOBAL_Control
0x140001d51  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140001d58  mov     [rsp+100h+var_B8], 0B23h
0x140001d60  mov     ecx, 40Eh
0x140001d65  mov     [rsp+100h+var_C0], rax
0x140001d6a  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140001d71  mov     [rsp+100h+var_C8], rax
0x140001d76  mov     r9, [r9+40h]
0x140001d7a  mov     word ptr [rsp+100h+var_D0], 35h ; '5'
0x140001d81  mov     dword ptr [rsp+100h+var_D8], 0Eh
0x140001d89  mov     [rsp+100h+var_E0], 4
0x140001d8e  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140001d93  jmp     loc_14000205B
0x140001d98  lea     rcx, Lookaside; Lookaside
0x140001d9f  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140001da6  nop     dword ptr [rax+rax+00h]
0x140001dab  mov     rbx, rax
0x140001dae  test    rax, rax
0x140001db1  jnz     short loc_140001E30
0x140001db3  mov     edi, 0C000009Ah
0x140001db8  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140001dbe  lea     rcx, WPP_RECORDER_INITIALIZED
0x140001dc5  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140001dcc  setnz   r8b
0x140001dd0  and     dl, 20h
0x140001dd3  jnz     short loc_140001DDE
0x140001dd5  test    r8b, r8b
0x140001dd8  jz      loc_140001FF5
0x140001dde  mov     r9, cs:WPP_GLOBAL_Control
0x140001de5  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140001dec  mov     dword ptr [rsp+100h+var_B0], edi
0x140001df0  mov     ecx, 205h
0x140001df5  mov     [rsp+100h+var_B8], 0B2Dh
0x140001dfd  mov     [rsp+100h+var_C0], rax
0x140001e02  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140001e09  mov     r9, [r9+40h]
0x140001e0d  mov     [rsp+100h+var_C8], rax
0x140001e12  mov     word ptr [rsp+100h+var_D0], 36h ; '6'
0x140001e19  mov     dword ptr [rsp+100h+var_D8], 5
0x140001e21  mov     [rsp+100h+var_E0], 2
0x140001e26  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140001e2b  jmp     loc_140001FF5
0x140001e30  xor     edx, edx; Val
0x140001e32  mov     rcx, rbx; void *
0x140001e35  lea     r8d, [rdx+58h]; Size
0x140001e39  call    memset
0x140001e3e  test    rsi, rsi
0x140001e41  jz      short loc_140001E55
0x140001e43  movups  xmm0, xmmword ptr [rbp+4Fh+P]
0x140001e47  mov     [rbx], rsi
0x140001e4a  xor     esi, esi
0x140001e4c  mov     [rbp+4Fh+P+8], rsi
0x140001e50  movdqu  xmmword ptr [rbx+8], xmm0
0x140001e55  test    r14, r14
0x140001e58  jz      loc_140001FEC
0x140001e5e  movups  xmm0, xmmword ptr [rbp+4Fh+var_40]
0x140001e62  mov     [rbx+38h], r14
0x140001e66  mov     rcx, r13; FileNameInformation
0x140001e69  xor     r14d, r14d
0x140001e6c  movdqu  xmmword ptr [rbx+40h], xmm0
0x140001e71  mov     [rbp+4Fh+var_40+8], r14
0x140001e75  call    cs:__imp_FltParseFileNameInformation
0x140001e7c  nop     dword ptr [rax+rax+00h]
0x140001e81  mov     edi, eax
0x140001e83  test    eax, eax
0x140001e85  js      loc_140001FF5
0x140001e8b  mov     rax, [r12+10h]
0x140001e90  mov     rcx, [rax+28h]; Object
0x140001e94  test    rcx, rcx
0x140001e97  jnz     loc_140001FD3
0x140001e9d  movups  xmm0, xmmword ptr [r13+8]
0x140001ea2  lea     r9, [rbp+4Fh+FileHandle]
0x140001ea6  lea     rdx, [rbp+4Fh+var_60]
0x140001eaa  movd    ecx, xmm0
0x140001eae  movups  [rbp+4Fh+var_60], xmm0
0x140001eb2  sub     cx, [r13+58h]
0x140001eb7  lea     eax, [rcx-2]
0x140001eba  cmp     ax, [r13+18h]
0x140001ebf  lea     r13, [rbx+50h]
0x140001ec3  cmovz   ax, cx
0x140001ec7  mov     rcx, r15
0x140001eca  mov     word ptr [rbp+4Fh+var_60], ax
0x140001ece  lea     rax, [rbp+4Fh+arg_10]
0x140001ed2  mov     [rsp+100h+var_D8], rax
0x140001ed7  mov     qword ptr [rsp+100h+var_E0], r13
0x140001edc  call    PrjfOpenPlaceHolder
0x140001ee1  mov     edi, eax
0x140001ee3  test    eax, eax
0x140001ee5  jns     short loc_140001F39
0x140001ee7  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140001eed  lea     rcx, WPP_RECORDER_INITIALIZED
0x140001ef4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140001efb  setnz   r8b
0x140001eff  and     dl, 20h
0x140001f02  jnz     short loc_140001F0D
0x140001f04  test    r8b, r8b
0x140001f07  jz      loc_140001FF5
0x140001f0d  mov     r9, cs:WPP_GLOBAL_Control
0x140001f14  mov     dword ptr [rsp+100h+var_98], eax
0x140001f18  lea     rax, [rbp+4Fh+var_60]
0x140001f1c  mov     [rsp+100h+var_A0], rax
0x140001f21  mov     [rsp+100h+var_A8], r15
0x140001f26  mov     r9, [r9+40h]
0x140001f2a  mov     [rsp+100h+var_B0], r12
0x140001f2f  call    WPP_RECORDER_AND_TRACE_SF_sDqqZd
0x140001f34  jmp     loc_140001FF5
0x140001f39  cmp     [rbp+4Fh+arg_10], r14b
0x140001f3d  jz      loc_140001FEC
0x140001f43  mov     rdx, [r13+0]; FileObject
0x140001f47  lea     rax, [rbp+4Fh+var_70]
0x140001f4b  mov     [rsp+100h+var_C0], rax; __int64
0x140001f50  mov     r9b, 1
0x140001f53  lea     rax, [rbp+4Fh+Context]
0x140001f57  mov     r8d, 80000000h
0x140001f5d  mov     [rsp+100h+var_C8], rax; __int64
0x140001f62  mov     rcx, r15; Instance
0x140001f65  mov     [rsp+100h+var_D0], r14; __int64
0x140001f6a  mov     [rsp+100h+var_D8], r14; __int64
0x140001f6f  mov     [rsp+100h+var_E0], r14b; char
0x140001f74  call    PrjfGetSetContextFileObject
0x140001f79  mov     edi, eax
0x140001f7b  test    eax, eax
0x140001f7d  jns     short loc_140001FEC
0x140001f7f  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140001f85  lea     rcx, WPP_RECORDER_INITIALIZED
0x140001f8c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140001f93  setnz   r8b
0x140001f97  and     dl, 20h
0x140001f9a  jnz     short loc_140001FA1
0x140001f9c  test    r8b, r8b
0x140001f9f  jz      short loc_140001FF5
0x140001fa1  mov     r9, cs:WPP_GLOBAL_Control
0x140001fa8  mov     [rsp+100h+var_90], eax
0x140001fac  lea     rax, [rbp+4Fh+var_60]
0x140001fb0  mov     [rsp+100h+var_98], rax
0x140001fb5  mov     rax, [r13+0]
0x140001fb9  mov     r9, [r9+40h]
0x140001fbd  mov     [rsp+100h+var_A0], rax
0x140001fc2  mov     [rsp+100h+var_A8], r15
0x140001fc7  mov     [rsp+100h+var_B0], r12
0x140001fcc  call    WPP_RECORDER_AND_TRACE_SF_sDqqqZd
0x140001fd1  jmp     short loc_140001FF5
0x140001fd3  call    cs:__imp_ObfReferenceObject
0x140001fda  nop     dword ptr [rax+rax+00h]
0x140001fdf  mov     rax, [r12+10h]
0x140001fe4  mov     rdx, [rax+28h]
0x140001fe8  mov     [rbx+50h], rdx
0x140001fec  mov     rax, [rbp+4Fh+arg_20]
0x140001ff0  mov     [rax], rbx
0x140001ff3  xor     ebx, ebx
0x140001ff5  test    rsi, rsi
0x140001ff8  jz      short loc_140002002
0x140001ffa  mov     rcx, rsi; P
0x140001ffd  call    PrjfReleaseUnionContext
0x140002002  test    r14, r14
0x140002005  jz      short loc_14000200F
0x140002007  mov     rcx, r14; P
0x14000200a  call    PrjfReleaseUnionContext
0x14000200f  mov     rcx, [rbp+4Fh+Context]; Context
0x140002013  test    rcx, rcx
0x140002016  jz      short loc_140002024
0x140002018  call    cs:__imp_FltReleaseContext
0x14000201f  nop     dword ptr [rax+rax+00h]
0x140002024  mov     rcx, [rbp+4Fh+var_70]; Context
0x140002028  test    rcx, rcx
0x14000202b  jz      short loc_140002039
0x14000202d  call    cs:__imp_FltReleaseContext
0x140002034  nop     dword ptr [rax+rax+00h]
0x140002039  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x14000203d  test    rcx, rcx
0x140002040  jz      short loc_14000204E
0x140002042  call    cs:__imp_FltClose
0x140002049  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
