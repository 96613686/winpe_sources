# PrjfUpdatePlaceholderIfNeededHandler

- ea: `0x140035238`
- end: `0x140035997`
- name: `PrjfUpdatePlaceholderIfNeededHandler`
- size: `1887`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE *, __int64, __int64, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140031a00`

## callees

- `0x140003e6c`
- `0x140006660`
- `0x1400089d8`
- `0x14000b1d0`
- `0x14000ba20`
- `0x14000be80`
- `0x14000d128`
- `0x140021f8c`
- `0x14002f494`
- `0x140033878`
- `0x140035238`
- `0x140037b8c`
- `0x1400396a4`
- `0x14003d620`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003593e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035958`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003593e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035958`
- `ntoskrnl!RtlCompareMemory` at `0x1400355b4`
- `ntoskrnl!RtlCompareMemory` at `0x1400355b4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400356d0`
- `ntoskrnl!ObfDereferenceObject` at `0x140035925`
- `ntoskrnl!ObfDereferenceObject` at `0x1400356d0`
- `ntoskrnl!ObfDereferenceObject` at `0x140035925`
- `ntoskrnl!ExAllocatePool2` at `0x14003549c`
- `ntoskrnl!ExAllocatePool2` at `0x14003549c`
- `FLTMGR!FltClose` at `0x1400356ba`
- `FLTMGR!FltClose` at `0x14003590f`
- `FLTMGR!FltClose` at `0x1400356ba`
- `FLTMGR!FltClose` at `0x14003590f`

## pseudocode

```c
__int64 __fastcall PrjfUpdatePlaceholderIfNeededHandler(
        struct _FLT_INSTANCE *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        _DWORD *a5)
{
  void *v7; // r12
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  signed int v13; // ebx
  int v14; // r8d
  char *UnionContextByVirtualizationInstanceInfo; // r13
  int v16; // r8d
  WCHAR *v17; // r8
  _WORD *v18; // rax
  unsigned __int64 i; // rcx
  int v20; // r14d
  const void *v21; // r15
  __int64 v22; // rdx
  WCHAR *v23; // rax
  int v24; // ecx
  int v25; // r8d
  __int64 v26; // r15
  __int64 v27; // r14
  int v28; // r8d
  int v29; // r8d
  __int64 v30; // r8
  int v31; // r8d
  int v32; // r8d
  char v34; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v35[3]; // [rsp+61h] [rbp-9Fh] BYREF
  unsigned int FileObject[3]; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v37; // [rsp+70h] [rbp-90h] BYREF
  HANDLE FileHandle; // [rsp+78h] [rbp-88h] BYREF
  PVOID P[2]; // [rsp+80h] [rbp-80h] BYREF
  PFLT_INSTANCE Instance; // [rsp+90h] [rbp-70h]
  UNICODE_STRING SourceString; // [rsp+98h] [rbp-68h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v43[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v44; // [rsp+C0h] [rbp-40h]
  _BYTE v45[256]; // [rsp+D0h] [rbp-30h] BYREF

  v44 = a3;
  Instance = a1;
  v43[0] = (__int64)a5;
  v42 = 0;
  v37 = 0;
  memset(FileObject, 0, sizeof(FileObject));
  FileHandle = 0;
  v7 = 0;
  SourceString = 0;
  v34 = 0;
  *(_OWORD *)P = 0;
  v35[0] = 0;
  memset(v45, 0, sizeof(v45));
  *a5 = 0;
  if ( (*(_DWORD *)(a2 + 4) & 0x10) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v10, v9);
  v13 = PrjfValidatePlaceholderInformationMessage(a2, a4, &v42);
  if ( v42 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v12, v11);
  if ( v13 < 0 )
  {
    UnionContextByVirtualizationInstanceInfo = 0;
    LOBYTE(v11) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        v11,
        v14,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        203,
        (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        92,
        v13);
    }
    goto LABEL_59;
  }
  UnionContextByVirtualizationInstanceInfo = (char *)PrjfGetUnionContextByVirtualizationInstanceInfo(
                                                       (__int128 *)(a2 + 8),
                                                       a1);
  if ( !UnionContextByVirtualizationInstanceInfo )
  {
    v13 = -1073741811;
    LOBYTE(v11) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        v11,
        v16,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        204,
        (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        103,
        13);
    }
    goto LABEL_59;
  }
  v17 = (WCHAR *)(a2 + *(unsigned int *)(a2 + 88));
  if ( !v17 )
  {
    v13 = -1073741811;
    goto LABEL_56;
  }
  v18 = (_WORD *)(a2 + *(unsigned int *)(a2 + 88));
  for ( i = (unsigned __int64)*(unsigned __int16 *)(a2 + 92) >> 1; i; --i )
  {
    if ( !*v18 )
      break;
    ++v18;
  }
  v11 = i == 0 ? 0xC000000D : 0;
  if ( !i )
  {
    v13 = -1073741811;
LABEL_56:
    LOBYTE(v11) = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        v11,
        (_DWORD)v17,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        205,
        (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        123,
        13);
    }
    goto LABEL_59;
  }
  v20 = *((unsigned __int16 *)UnionContextByVirtualizationInstanceInfo + 20);
  v21 = (const void *)*((_QWORD *)UnionContextByVirtualizationInstanceInfo + 6);
  v22 = 0x7FFF;
  SourceString = 0;
  v23 = v17;
  do
  {
    if ( !*v23 )
      break;
    ++v23;
    --v22;
  }
  while ( v22 );
  v13 = v22 == 0 ? 0xC000000D : 0;
  if ( v22 )
  {
    SourceString.Buffer = v17;
    v24 = (unsigned __int16)(-2 - 2 * v22);
    SourceString.Length = -2 - 2 * v22;
    v11 = (unsigned int)(v24 + v20);
    SourceString.MaximumLength = v24 + 2;
    if ( (unsigned __int16)(v24 + v20) < (unsigned __int16)v20
      || (LOWORD(v11) = v24 + v20 + 2, (unsigned __int16)v11 < 2u) )
    {
      v13 = -1073741675;
      WORD1(P[0]) = -1;
    }
    else
    {
      WORD1(P[0]) = v24 + v20 + 2;
      LOWORD(P[0]) = 0;
      P[1] = (PVOID)ExAllocatePool2(256, (unsigned __int16)v11, 1953319504);
      if ( P[1] )
      {
        v13 = PrjfRelPathToFullPath((__int64)P, v20, v21, SourceString.Buffer, SourceString.Length);
        if ( v13 >= 0 )
        {
          v13 = PrjfDecideUpdateDeleteOnFileStateAndUpdateFlags(
                  (_DWORD)Instance,
                  *(_DWORD *)(a2 + 4),
                  (unsigned int)P,
                  (unsigned int)&FileHandle,
                  (__int64)&FileObject[1],
                  v43[0],
                  (__int64)&v34,
                  (__int64)v45,
                  (__int64)v35);
          if ( v13 >= 0 && (*(_DWORD *)(a2 + 4) & 8) != 0 )
          {
            v26 = *(unsigned int *)(a2 + 96);
            v27 = v26 + a2;
            if ( v34 && RtlCompareMemory((const void *)(v27 + 208), &v45[128], 0x80u) == 128 )
            {
              v13 = 0;
              LOBYTE(v11) = BYTE1(xmmword_14001A3E0) & 0x40;
              if ( (BYTE1(xmmword_14001A3E0) & 0x40) != 0
                || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                WPP_RECORDER_AND_TRACE_SF_sDL(
                  1038,
                  v11,
                  v28,
                  *((_QWORD *)WPP_GLOBAL_Control + 8),
                  4,
                  14,
                  208,
                  (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
                  (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
                  222,
                  0);
              }
            }
            else
            {
              v13 = PrjfSetDeleteDisposition(
                      Instance,
                      *(PFILE_OBJECT *)&FileObject[1],
                      (__int64)UnionContextByVirtualizationInstanceInfo,
                      v43[0]);
              if ( v13 >= 0 )
              {
                FltClose(FileHandle);
                FileHandle = 0;
                ObfDereferenceObject(*(PVOID *)&FileObject[1]);
                *(_QWORD *)&FileObject[1] = 0;
                tlgDefineProvider_annotation__TlgProjfsTelemetryProviderProv();
                *(_OWORD *)v43 = *(_OWORD *)(a2 + 8);
                v13 = PrjfCreatePrjReparseBuffer(
                        &SourceString,
                        (__int128 *)v43,
                        v30,
                        (_OWORD *)(v27 + 80),
                        (WCHAR **)&v37,
                        FileObject);
                if ( v13 >= 0 )
                {
                  v7 = (void *)v37;
                  v13 = PrjfCopyAsPlaceHolder(
                          (int)v26 + (int)a2,
                          (int)v26 + (int)v44,
                          (unsigned int)P,
                          (_DWORD)Instance,
                          v37,
                          FileObject[0],
                          0,
                          *(_DWORD *)(a2 + 100));
                  if ( v13 < 0 )
                  {
                    LOBYTE(v11) = BYTE1(xmmword_14001A3D0) & 0x40;
                    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
                      || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    {
                      LOBYTE(v32) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                      WPP_RECORDER_AND_TRACE_SF_sDL(
                        526,
                        v11,
                        v32,
                        *((_QWORD *)WPP_GLOBAL_Control + 8),
                        2,
                        14,
                        211,
                        (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
                        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
                        26,
                        v13);
                    }
                  }
                }
                else
                {
                  LOBYTE(v11) = BYTE1(xmmword_14001A3D0) & 0x40;
                  if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
                    || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    LOBYTE(v31) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                    WPP_RECORDER_AND_TRACE_SF_sDL(
                      526,
                      v11,
                      v31,
                      *((_QWORD *)WPP_GLOBAL_Control + 8),
                      2,
                      14,
                      210,
                      (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
                      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
                      11,
                      v13);
                  }
                  v7 = (void *)v37;
                }
              }
              else
              {
                LOBYTE(v11) = BYTE1(xmmword_14001A3D0) & 0x40;
                if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
                  || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v29) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                  WPP_RECORDER_AND_TRACE_SF_sDL(
                    526,
                    v11,
                    v29,
                    *((_QWORD *)WPP_GLOBAL_Control + 8),
                    2,
                    14,
                    209,
                    (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
                    (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
                    236,
                    v13);
                }
              }
            }
          }
        }
        else
        {
          LOBYTE(v11) = BYTE1(xmmword_14001A3D0) & 0x40;
          if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v25) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDL(
              526,
              v11,
              v25,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              14,
              207,
              (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
              169,
              v13);
          }
        }
      }
      else
      {
        v13 = -1073741670;
      }
    }
  }
  else
  {
    v11 = BYTE1(xmmword_14001A3D0) & 0x40;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v17) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        v11,
        (_DWORD)v17,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        206,
        (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        131,
        v13);
    }
  }
LABEL_59:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( *(_QWORD *)&FileObject[1] )
    ObfDereferenceObject(*(PVOID *)&FileObject[1]);
  if ( v7 )
    ExFreePoolWithTag(v7, 0x69724A50u);
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x746D4A50u);
  if ( UnionContextByVirtualizationInstanceInfo )
    PrjfReleaseUnionContext(UnionContextByVirtualizationInstanceInfo, v11);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140035238  push    rbp
0x14003523a  push    rbx
0x14003523b  push    rsi
0x14003523c  push    rdi
0x14003523d  push    r12
0x14003523f  push    r13
0x140035241  push    r14
0x140035243  push    r15
0x140035245  lea     rbp, [rsp-0E8h]
0x14003524d  sub     rsp, 1E8h
0x140035254  mov     rax, cs:__security_cookie
0x14003525b  xor     rax, rsp
0x14003525e  mov     [rbp+120h+var_50], rax
0x140035265  mov     r14, [rbp+120h+arg_20]
0x14003526c  xor     r15d, r15d
0x14003526f  mov     [rbp+120h+var_160], r8
0x140035273  mov     rdi, rdx
0x140035276  mov     rsi, rcx
0x140035279  mov     [rbp+120h+Instance], rcx
0x14003527d  xorps   xmm0, xmm0
0x140035280  mov     [rbp+120h+var_170], r14
0x140035284  xorps   xmm1, xmm1
0x140035287  mov     [rbp+120h+var_178], r15
0x14003528b  xor     edx, edx; Val
0x14003528d  mov     [rsp+220h+var_1B0], r15
0x140035292  mov     r8d, 100h; Size
0x140035298  mov     dword ptr [rsp+220h+FileObject], r15d
0x14003529d  lea     rcx, [rbp+120h+var_150]; void *
0x1400352a1  mov     [rsp+220h+FileHandle], r15
0x1400352a6  mov     r12d, r15d
0x1400352a9  mov     qword ptr [rsp+220h+FileObject+4], r15
0x1400352ae  movups  xmmword ptr [rbp+120h+SourceString.Length], xmm0
0x1400352b2  mov     [rsp+220h+var_1C0], r15b
0x1400352b7  mov     ebx, r9d
0x1400352ba  movups  xmmword ptr [rbp+120h+P], xmm1
0x1400352be  mov     [rsp+220h+var_1BF], r15b
0x1400352c3  call    memset
0x1400352c8  mov     [r14], r15d
0x1400352cb  mov     eax, [rdi+4]
0x1400352ce  test    al, 10h
0x1400352d0  jz      short loc_1400352D7
0x1400352d2  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400352d7  lea     r8, [rbp+120h+var_178]
0x1400352db  mov     edx, ebx
0x1400352dd  mov     rcx, rdi
0x1400352e0  call    PrjfValidatePlaceholderInformationMessage
0x1400352e5  mov     ebx, eax
0x1400352e7  cmp     [rbp+120h+var_178], r15
0x1400352eb  jz      short loc_1400352F2
0x1400352ed  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400352f2  test    ebx, ebx
0x1400352f4  jns     short loc_14003535C
0x1400352f6  mov     r13, r15
0x1400352f9  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400352ff  lea     rax, WPP_RECORDER_INITIALIZED
0x140035306  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003530d  setnz   r8b
0x140035311  and     dl, 40h
0x140035314  jnz     short loc_14003531F
0x140035316  test    r8b, r8b
0x140035319  jz      loc_140035905
0x14003531f  mov     [rsp+220h+var_1D0], ebx
0x140035323  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003532a  mov     [rsp+220h+var_1D8], 185Ch
0x140035332  mov     [rsp+220h+var_1E0], rax
0x140035337  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14003533e  mov     [rsp+220h+var_1E8], rax
0x140035343  mov     word ptr [rsp+220h+var_1F0], 0CBh
0x14003534a  mov     dword ptr [rsp+220h+var_1F8], 0Eh
0x140035352  mov     byte ptr [rsp+220h+var_200], 2
0x140035357  jmp     loc_1400358F0
0x14003535c  lea     rcx, [rdi+8]
0x140035360  mov     rdx, rsi
0x140035363  call    PrjfGetUnionContextByVirtualizationInstanceInfo
0x140035368  mov     r13, rax
0x14003536b  test    rax, rax
0x14003536e  jnz     short loc_1400353C8
0x140035370  mov     ebx, 0C000000Dh
0x140035375  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003537b  lea     rax, WPP_RECORDER_INITIALIZED
0x140035382  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140035389  setnz   r8b
0x14003538d  and     dl, 40h
0x140035390  jnz     short loc_14003539B
0x140035392  test    r8b, r8b
0x140035395  jz      loc_140035905
0x14003539b  mov     [rsp+220h+var_1D0], ebx
0x14003539f  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400353a6  mov     [rsp+220h+var_1D8], 1867h
0x1400353ae  mov     [rsp+220h+var_1E0], rax
0x1400353b3  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400353ba  mov     [rsp+220h+var_1E8], rax
0x1400353bf  mov     word ptr [rsp+220h+var_1F0], 0CCh
0x1400353c6  jmp     short loc_14003534A
0x1400353c8  mov     r8d, [rdi+58h]
0x1400353cc  mov     esi, 2
0x1400353d1  add     r8, rdi
0x1400353d4  jz      loc_140035891
0x1400353da  movzx   ecx, word ptr [rdi+5Ch]
0x1400353de  mov     rax, r8
0x1400353e1  shr     rcx, 1
0x1400353e4  jz      short loc_1400353F5
0x1400353e6  cmp     [rax], r15w
0x1400353ea  jz      short loc_1400353F5
0x1400353ec  add     rax, rsi
0x1400353ef  sub     rcx, 1
0x1400353f3  jnz     short loc_1400353E6
0x1400353f5  mov     rax, rcx
0x1400353f8  mov     ebx, 0C000000Dh
0x1400353fd  neg     rax
0x140035400  sbb     edx, edx
0x140035402  not     edx
0x140035404  and     edx, ebx
0x140035406  test    rcx, rcx
0x140035409  jnz     short loc_140035412
0x14003540b  mov     ebx, edx
0x14003540d  jmp     loc_140035896
0x140035412  movzx   r14d, word ptr [r13+28h]
0x140035417  xorps   xmm0, xmm0
0x14003541a  mov     r15, [r13+30h]
0x14003541e  mov     edx, 7FFFh
0x140035423  movups  xmmword ptr [rbp+120h+SourceString.Length], xmm0
0x140035427  mov     rax, r8
0x14003542a  xor     r9d, r9d
0x14003542d  cmp     [rax], r9w
0x140035431  jz      short loc_14003543C
0x140035433  add     rax, rsi
0x140035436  sub     rdx, 1
0x14003543a  jnz     short loc_14003542D
0x14003543c  mov     rax, rdx
0x14003543f  neg     rax
0x140035442  sbb     ecx, ecx
0x140035444  not     ecx
0x140035446  and     ebx, ecx
0x140035448  test    rdx, rdx
0x14003544b  jz      loc_14003583E
0x140035451  add     dx, dx
0x140035454  mov     [rbp+120h+SourceString.Buffer], r8
0x140035458  mov     ecx, 0FFFEh
0x14003545d  sub     cx, dx
0x140035460  mov     [rbp+120h+SourceString.Length], cx
0x140035464  lea     edx, [rcx+r14]
0x140035468  lea     eax, [rsi+rcx]
0x14003546b  mov     [rbp+120h+SourceString.MaximumLength], ax
0x14003546f  cmp     dx, r14w
0x140035473  jb      loc_14003582B
0x140035479  add     dx, si
0x14003547c  cmp     dx, si
0x14003547f  jb      loc_14003582B
0x140035485  mov     word ptr [rbp+120h+P+2], dx
0x140035489  mov     ecx, 100h
0x14003548e  movzx   edx, dx
0x140035491  mov     r8d, 746D4A50h
0x140035497  mov     word ptr [rbp+120h+P], r9w
0x14003549c  call    cs:__imp_ExAllocatePool2
0x1400354a3  nop     dword ptr [rax+rax+00h]
0x1400354a8  mov     [rbp+120h+P+8], rax
0x1400354ac  test    rax, rax
0x1400354af  jnz     short loc_1400354BB
0x1400354b1  mov     ebx, 0C000009Ah
0x1400354b6  jmp     loc_140035905
0x1400354bb  movzx   eax, [rbp+120h+SourceString.Length]
0x1400354bf  lea     rcx, [rbp+120h+P]
0x1400354c3  mov     r9, [rbp+120h+SourceString.Buffer]
0x1400354c7  mov     r8, r15
0x1400354ca  movzx   edx, r14w
0x1400354ce  mov     word ptr [rsp+220h+var_200], ax
0x1400354d3  call    PrjfRelPathToFullPath
0x1400354d8  mov     ebx, eax
0x1400354da  test    eax, eax
0x1400354dc  jns     short loc_140035534
0x1400354de  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400354e4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400354eb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400354f2  setnz   r8b
0x1400354f6  and     dl, 40h
0x1400354f9  jnz     short loc_140035504
0x1400354fb  test    r8b, r8b
0x1400354fe  jz      loc_140035905
0x140035504  mov     [rsp+220h+var_1D0], ebx
0x140035508  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003550f  mov     [rsp+220h+var_1D8], 18A9h
0x140035517  mov     [rsp+220h+var_1E0], rax
0x14003551c  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140035523  mov     [rsp+220h+var_1E8], rax
0x140035528  mov     word ptr [rsp+220h+var_1F0], 0CFh
0x14003552f  jmp     loc_1400358E3
0x140035534  mov     edx, [rdi+4]
0x140035537  lea     rax, [rsp+220h+var_1BF]
0x14003553c  mov     rcx, [rbp+120h+Instance]
0x140035540  lea     r9, [rsp+220h+FileHandle]
0x140035545  mov     [rsp+220h+var_1E0], rax
0x14003554a  lea     r8, [rbp+120h+P]
0x14003554e  lea     rax, [rbp+120h+var_150]
0x140035552  mov     [rsp+220h+var_1E8], rax
0x140035557  lea     rax, [rsp+220h+var_1C0]
0x14003555c  mov     [rsp+220h+var_1F0], rax
0x140035561  mov     rax, [rbp+120h+var_170]
0x140035565  mov     [rsp+220h+var_1F8], rax
0x14003556a  lea     rax, [rsp+220h+FileObject+4]
0x14003556f  mov     [rsp+220h+var_200], rax
0x140035574  call    PrjfDecideUpdateDeleteOnFileStateAndUpdateFlags
0x140035579  mov     ebx, eax
0x14003557b  test    eax, eax
0x14003557d  js      loc_140035905
0x140035583  mov     eax, [rdi+4]
0x140035586  test    al, 8
0x140035588  jz      loc_140035905
0x14003558e  mov     r15d, [rdi+60h]
0x140035592  lea     r14, [r15+rdi]
0x140035596  cmp     [rsp+220h+var_1C0], r12b
0x14003559b  jz      loc_140035634
0x1400355a1  mov     ebx, 80h
0x1400355a6  lea     rcx, [r14+0D0h]; Source1
0x1400355ad  mov     r8d, ebx; Length
0x1400355b0  lea     rdx, [rbp+120h+Source2]; Source2
0x1400355b4  call    cs:__imp_RtlCompareMemory
0x1400355bb  nop     dword ptr [rax+rax+00h]
0x1400355c0  cmp     rax, rbx
0x1400355c3  jnz     short loc_140035634
0x1400355c5  xor     r15d, r15d
0x1400355c8  mov     ebx, r15d
0x1400355cb  mov     dl, byte ptr cs:xmmword_14001A3E0+1
0x1400355d1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400355d8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400355df  setnz   r8b
0x1400355e3  and     dl, 40h
0x1400355e6  jnz     short loc_1400355F1
0x1400355e8  test    r8b, r8b
0x1400355eb  jz      loc_140035905
0x1400355f1  mov     [rsp+220h+var_1D0], r15d
0x1400355f6  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400355fd  mov     [rsp+220h+var_1D8], 18DEh
0x140035605  mov     ecx, 40Eh
0x14003560a  mov     [rsp+220h+var_1E0], rax
0x14003560f  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140035616  mov     [rsp+220h+var_1E8], rax
0x14003561b  mov     word ptr [rsp+220h+var_1F0], 0D0h
0x140035622  mov     dword ptr [rsp+220h+var_1F8], 0Eh
0x14003562a  mov     byte ptr [rsp+220h+var_200], 4
0x14003562f  jmp     loc_1400358F5
0x140035634  mov     rax, [rbp+120h+var_170]
0x140035638  mov     r9b, [rsp+220h+var_1BF]
0x14003563d  mov     r8d, [rdi+4]
0x140035641  mov     rdx, qword ptr [rsp+220h+FileObject+4]; FileObject
0x140035646  mov     rcx, [rbp+120h+Instance]; Instance
0x14003564a  mov     [rsp+220h+var_1F8], rax; __int64
0x14003564f  mov     [rsp+220h+var_200], r13; __int64
0x140035654  call    PrjfSetDeleteDisposition
0x140035659  mov     ebx, eax
0x14003565b  test    eax, eax
0x14003565d  jns     short loc_1400356B5
0x14003565f  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140035665  lea     rax, WPP_RECORDER_INITIALIZED
0x14003566c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140035673  setnz   r8b
0x140035677  and     dl, 40h
0x14003567a  jnz     short loc_140035685
0x14003567c  test    r8b, r8b
0x14003567f  jz      loc_140035905
0x140035685  mov     [rsp+220h+var_1D0], ebx
0x140035689  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140035690  mov     [rsp+220h+var_1D8], 18ECh
0x140035698  mov     [rsp+220h+var_1E0], rax
0x14003569d  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400356a4  mov     [rsp+220h+var_1E8], rax
0x1400356a9  mov     word ptr [rsp+220h+var_1F0], 0D1h
0x1400356b0  jmp     loc_1400358E3
0x1400356b5  mov     rcx, [rsp+220h+FileHandle]; FileHandle
0x1400356ba  call    cs:__imp_FltClose
0x1400356c1  nop     dword ptr [rax+rax+00h]
0x1400356c6  mov     rcx, qword ptr [rsp+220h+FileObject+4]; Object
0x1400356cb  mov     [rsp+220h+FileHandle], r12
0x1400356d0  call    cs:__imp_ObfDereferenceObject
0x1400356d7  nop     dword ptr [rax+rax+00h]
0x1400356dc  mov     qword ptr [rsp+220h+FileObject+4], r12
0x1400356e1  call    _tlgDefineProvider_annotation__TlgProjfsTelemetryProviderProv
0x1400356e6  movups  xmm0, xmmword ptr [rdi+8]
0x1400356ea  lea     rax, [rsp+220h+FileObject]
0x1400356ef  mov     [rsp+220h+var_1F8], rax; __int64
0x1400356f4  lea     r9, [r14+50h]
0x1400356f8  lea     rax, [rsp+220h+var_1B0]
0x1400356fd  lea     rdx, [rbp+120h+var_170]
0x140035701  mov     [rsp+220h+var_200], rax; __int64
0x140035706  lea     rcx, [rbp+120h+SourceString]; SourceString
0x14003570a  movdqu  xmmword ptr [rbp+120h+var_170], xmm0
0x14003570f  call    PrjfCreatePrjReparseBuffer
0x140035714  mov     ebx, eax
0x140035716  test    eax, eax
0x140035718  jns     short loc_140035793
0x14003571a  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140035720  lea     rax, WPP_RECORDER_INITIALIZED
0x140035727  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003572e  setnz   r8b
0x140035732  and     dl, 40h
0x140035735  jnz     short loc_14003573C
0x140035737  test    r8b, r8b
0x14003573a  jz      short loc_140035789
0x14003573c  mov     r9, cs:WPP_GLOBAL_Control
0x140035743  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
  ... truncated ...
```
