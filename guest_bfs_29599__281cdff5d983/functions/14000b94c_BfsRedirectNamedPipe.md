# BfsRedirectNamedPipe

- ea: `0x14000b94c`
- end: `0x14000be93`
- name: `BfsRedirectNamedPipe`
- size: `1351`
- prototype: `__int64 __fastcall(PFLT_FILTER Filter, PFLT_CALLBACK_DATA Data, PSID SourceSid, PSID, __int64, PCUNICODE_STRING Source)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x140002d30`

## callees

- `0x140001008`
- `0x14000b94c`
- `0x14000bf74`
- `0x140013860`

## import_xrefs

- `ntoskrnl!RtlCopySid` at `0x14000ba20`
- `ntoskrnl!RtlCopySid` at `0x14000bb3d`
- `ntoskrnl!RtlCopySid` at `0x14000ba20`
- `ntoskrnl!RtlCopySid` at `0x14000bb3d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000bbfa`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000bc61`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000bbfa`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000bc61`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ba72`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ba88`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000baa8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000babf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bad0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bc49`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ba72`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ba88`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000baa8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000babf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bad0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bc49`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000bbe3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000bd39`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000bd7b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000bbe3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000bd39`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000bd7b`
- `ntoskrnl!ExAllocatePool2` at `0x14000b9b4`
- `ntoskrnl!ExAllocatePool2` at `0x14000baf9`
- `ntoskrnl!ExAllocatePool2` at `0x14000bbb0`
- `ntoskrnl!ExAllocatePool2` at `0x14000bc87`
- `ntoskrnl!ExAllocatePool2` at `0x14000bcd1`
- `ntoskrnl!ExAllocatePool2` at `0x14000bd52`
- `ntoskrnl!ExAllocatePool2` at `0x14000b9b4`
- `ntoskrnl!ExAllocatePool2` at `0x14000baf9`
- `ntoskrnl!ExAllocatePool2` at `0x14000bbb0`
- `ntoskrnl!ExAllocatePool2` at `0x14000bc87`
- `ntoskrnl!ExAllocatePool2` at `0x14000bcd1`
- `ntoskrnl!ExAllocatePool2` at `0x14000bd52`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14000bd91`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14000bd91`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14000be52`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14000be52`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x14000be0c`
- `FLTMGR!FltAllocateExtraCreateParameter` at `0x14000be0c`
- `FLTMGR!FltSetEcpListIntoCallbackData` at `0x14000bdcf`
- `FLTMGR!FltSetEcpListIntoCallbackData` at `0x14000bdcf`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14000bdb3`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14000bdb3`

## pseudocode

```c
__int64 __fastcall BfsRedirectNamedPipe(
        PFLT_FILTER Filter,
        PFLT_CALLBACK_DATA Data,
        unsigned __int8 *SourceSid,
        unsigned __int8 *a4,
        __int64 a5,
        PCUNICODE_STRING Source)
{
  __int64 v7; // rdx
  void *v10; // rsi
  void *Pool2; // rax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  NTSTATUS appended; // ebx
  struct _UNICODE_STRING *v17; // rdi
  NTSTATUS v18; // eax
  int v19; // r8d
  int v20; // r9d
  int v21; // ecx
  PVOID v22; // r15
  PWSTR Buffer; // rcx
  PWSTR v24; // rcx
  void *v25; // rax
  bool v26; // cc
  unsigned __int16 v27; // ax
  unsigned __int16 v28; // cx
  USHORT v29; // bx
  void *v30; // rax
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  PVOID *v34; // rax
  __int64 v35; // rbx
  __int64 v36; // rax
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  __int64 v40; // rax
  int CleanupCallback; // [rsp+20h] [rbp-89h]
  __int64 v43; // [rsp+40h] [rbp-69h] BYREF
  PVOID P; // [rsp+48h] [rbp-61h]
  PECP_LIST EcpList; // [rsp+50h] [rbp-59h] BYREF
  PVOID EcpContext; // [rsp+58h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-49h] BYREF
  PVOID v48; // [rsp+70h] [rbp-39h]
  struct _EVENT_DATA_DESCRIPTOR v49; // [rsp+78h] [rbp-31h] BYREF
  __int64 *v50; // [rsp+98h] [rbp-11h]
  __int64 v51; // [rsp+A0h] [rbp-9h]

  v7 = SourceSid[1];
  v10 = 0;
  v43 = a5;
  EcpContext = 0;
  EcpList = 0;
  DestinationString = 0;
  Pool2 = (void *)ExAllocatePool2(256, 4 * v7 + 8, 1400071746);
  P = Pool2;
  if ( !Pool2 )
  {
    appended = -1073741801;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      LODWORD(v43) = -1073741801;
      v50 = &v43;
      v51 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v13, (int)&byte_140016D91, v14, v15, CleanupCallback, &v49);
    }
    return (unsigned int)appended;
  }
  v17 = 0;
  v18 = RtlCopySid(4 * SourceSid[1] + 8, Pool2, SourceSid);
  appended = v18;
  if ( v18 >= 0 )
  {
    v25 = (void *)ExAllocatePool2(256, 4LL * a4[1] + 8, 1400071746);
    v10 = v25;
    if ( !v25 )
    {
      v21 = dword_140019000;
      v26 = (unsigned int)dword_140019000 <= 3;
LABEL_19:
      appended = -1073741801;
      if ( v26 )
        goto LABEL_8;
      LODWORD(v43) = -1073741801;
      goto LABEL_7;
    }
    appended = RtlCopySid(4 * a4[1] + 8, v25, a4);
    if ( appended < 0 )
    {
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_8;
      LODWORD(v43) = appended;
      goto LABEL_7;
    }
    v27 = *(_WORD *)(v43 + 24);
    v28 = v27 + 14;
    if ( (unsigned __int16)(v27 + 14) < v27 || (v29 = Source->Length + v28, v29 < v28) )
    {
      v21 = -1073741675;
      appended = -1073741675;
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_8;
      LODWORD(v43) = -1073741675;
      goto LABEL_7;
    }
    v30 = (void *)ExAllocatePool2(256, v29, 1181967938);
    v48 = v30;
    if ( !v30 )
    {
      v26 = (unsigned int)dword_140019000 <= 3;
      goto LABEL_19;
    }
    DestinationString.Buffer = (PWSTR)v30;
    DestinationString.MaximumLength = v29;
    RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(v43 + 24));
    appended = RtlAppendUnicodeStringToString(&DestinationString, &ReparsePrefixString);
    if ( appended < 0 || (appended = RtlAppendUnicodeStringToString(&DestinationString, Source), appended < 0) )
    {
      if ( (unsigned int)dword_140019000 > 3 )
      {
        LODWORD(v43) = appended;
LABEL_33:
        v51 = 4;
        v50 = &v43;
        tlgWriteTransfer_EtwWriteTransfer(v31, (int)&byte_140016D91, v32, v33, CleanupCallback, &v49);
      }
    }
    else
    {
      v34 = (PVOID *)ExAllocatePool2(256, 48, 1383294530);
      v17 = (struct _UNICODE_STRING *)v34;
      if ( v34 )
      {
        v35 = v43;
        v22 = P;
        *v34 = P;
        v34[1] = v10;
        v36 = ExAllocatePool2(256, *(unsigned __int16 *)(v35 + 8), 1181967938);
        v17[1].Buffer = (PWSTR)v36;
        if ( v36
          && (v17[1].MaximumLength = *(_WORD *)(v35 + 8),
              RtlCopyUnicodeString(v17 + 1, (PCUNICODE_STRING)(v35 + 8)),
              v40 = ExAllocatePool2(256, DestinationString.Length, 1181967938),
              (v17[2].Buffer = (PWSTR)v40) != 0) )
        {
          v17[2].MaximumLength = DestinationString.Length;
          RtlCopyUnicodeString(v17 + 2, &DestinationString);
          appended = FltGetEcpListFromCallbackData(Filter, Data, &EcpList);
          if ( appended >= 0 )
          {
            if ( EcpList
              || (appended = FltAllocateExtraCreateParameterList(Filter, 0, &EcpList), appended >= 0)
              && (appended = FltSetEcpListIntoCallbackData(Filter, Data, EcpList), appended >= 0) )
            {
              appended = FltAllocateExtraCreateParameter(Filter, &BfsEcpType, 0x10u, 0, 0, 0x70736642u, &EcpContext);
              if ( appended >= 0 )
              {
                *(_DWORD *)EcpContext = 1;
                *((_QWORD *)EcpContext + 1) = v17;
                appended = FltInsertExtraCreateParameter(Filter, EcpList, EcpContext);
                if ( appended >= 0 )
                {
                  BfsReparseNamedPipe(Data);
                  return (unsigned int)appended;
                }
              }
            }
          }
          if ( (unsigned int)dword_140019000 <= 3 )
            goto LABEL_35;
          LODWORD(v43) = appended;
        }
        else
        {
          appended = -1073741801;
          if ( (unsigned int)dword_140019000 <= 3 )
            goto LABEL_35;
          LODWORD(v43) = -1073741801;
        }
        v51 = 4;
        v50 = &v43;
        tlgWriteTransfer_EtwWriteTransfer(v37, (int)&byte_140016D91, v38, v39, CleanupCallback, &v49);
        goto LABEL_35;
      }
      appended = -1073741801;
      if ( (unsigned int)dword_140019000 > 3 )
      {
        LODWORD(v43) = -1073741801;
        goto LABEL_33;
      }
    }
    v22 = P;
LABEL_35:
    ExFreePoolWithTag(v48, 0);
    goto LABEL_9;
  }
  v21 = dword_140019000;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    LODWORD(v43) = v18;
LABEL_7:
    v51 = 4;
    v50 = &v43;
    tlgWriteTransfer_EtwWriteTransfer(v21, (int)&byte_140016D91, v19, v20, CleanupCallback, &v49);
  }
LABEL_8:
  v22 = P;
LABEL_9:
  ExFreePoolWithTag(v22, 0);
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  if ( v17 )
  {
    Buffer = v17[1].Buffer;
    if ( Buffer )
      ExFreePoolWithTag(Buffer, 0);
    v24 = v17[2].Buffer;
    if ( v24 )
      ExFreePoolWithTag(v24, 0);
    ExFreePoolWithTag(v17, 0);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14000b94c  push    rbp
0x14000b94e  push    rbx
0x14000b94f  push    rsi
0x14000b950  push    rdi
0x14000b951  push    r12
0x14000b953  push    r13
0x14000b955  push    r14
0x14000b957  push    r15
0x14000b959  lea     rbp, [rsp-0Fh]
0x14000b95e  sub     rsp, 0B8h
0x14000b965  mov     rax, cs:__security_cookie
0x14000b96c  xor     rax, rsp
0x14000b96f  mov     [rbp+47h+var_48], rax
0x14000b973  mov     rax, [rbp+47h+arg_20]
0x14000b977  mov     r12, rdx
0x14000b97a  movzx   edx, byte ptr [r8+1]
0x14000b97f  mov     rbx, r8
0x14000b982  mov     r13, [rbp+47h+Source]
0x14000b986  mov     r14, rcx
0x14000b989  xor     esi, esi
0x14000b98b  mov     [rbp+47h+var_B0], rax
0x14000b98f  xorps   xmm0, xmm0
0x14000b992  mov     [rbp+47h+var_98], rsi
0x14000b996  lea     rdx, ds:8[rdx*4]
0x14000b99e  mov     [rbp+47h+EcpList], rsi
0x14000b9a2  mov     ecx, 100h
0x14000b9a7  mov     r8d, 53736642h
0x14000b9ad  mov     r15, r9
0x14000b9b0  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x14000b9b4  call    cs:__imp_ExAllocatePool2
0x14000b9bb  nop     dword ptr [rax+rax+00h]
0x14000b9c0  mov     [rbp+47h+P], rax
0x14000b9c4  test    rax, rax
0x14000b9c7  jnz     short loc_14000BA0C
0x14000b9c9  mov     eax, cs:dword_140019000
0x14000b9cf  mov     edx, 0C0000017h
0x14000b9d4  mov     ebx, edx
0x14000b9d6  cmp     eax, 3
0x14000b9d9  jbe     loc_14000BE70
0x14000b9df  lea     rax, [rbp+47h+var_B0]
0x14000b9e3  mov     dword ptr [rbp+47h+var_B0], edx
0x14000b9e6  mov     [rbp+47h+var_58], rax
0x14000b9ea  lea     rdx, byte_140016D91; int
0x14000b9f1  lea     rax, [rbp+47h+var_78]
0x14000b9f5  mov     [rbp+47h+var_50], 4
0x14000b9fd  mov     qword ptr [rsp+0F0h+PoolTag], rax; PEVENT_DATA_DESCRIPTOR
0x14000ba02  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000ba07  jmp     loc_14000BE70
0x14000ba0c  movzx   ecx, byte ptr [rbx+1]
0x14000ba10  mov     r8, rbx; SourceSid
0x14000ba13  mov     rdx, rax; DestinationSid
0x14000ba16  mov     rdi, rsi
0x14000ba19  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x14000ba20  call    cs:__imp_RtlCopySid
0x14000ba27  nop     dword ptr [rax+rax+00h]
0x14000ba2c  mov     ebx, eax
0x14000ba2e  test    eax, eax
0x14000ba30  jns     loc_14000BAE1
0x14000ba36  mov     ecx, cs:dword_140019000; int
0x14000ba3c  cmp     ecx, 3
0x14000ba3f  jbe     short loc_14000BA69
0x14000ba41  mov     dword ptr [rbp+47h+var_B0], eax
0x14000ba44  lea     rax, [rbp+47h+var_B0]
0x14000ba48  mov     [rbp+47h+var_50], 4
0x14000ba50  mov     [rbp+47h+var_58], rax
0x14000ba54  lea     rdx, byte_140016D91; int
0x14000ba5b  lea     rax, [rbp+47h+var_78]
0x14000ba5f  mov     qword ptr [rsp+0F0h+PoolTag], rax; PEVENT_DATA_DESCRIPTOR
0x14000ba64  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000ba69  mov     r15, [rbp+47h+P]
0x14000ba6d  xor     edx, edx; Tag
0x14000ba6f  mov     rcx, r15; P
0x14000ba72  call    cs:__imp_ExFreePoolWithTag
0x14000ba79  nop     dword ptr [rax+rax+00h]
0x14000ba7e  test    rsi, rsi
0x14000ba81  jz      short loc_14000BA94
0x14000ba83  xor     edx, edx; Tag
0x14000ba85  mov     rcx, rsi; P
0x14000ba88  call    cs:__imp_ExFreePoolWithTag
0x14000ba8f  nop     dword ptr [rax+rax+00h]
0x14000ba94  test    rdi, rdi
0x14000ba97  jz      loc_14000BE70
0x14000ba9d  mov     rcx, [rdi+18h]; P
0x14000baa1  test    rcx, rcx
0x14000baa4  jz      short loc_14000BAB4
0x14000baa6  xor     edx, edx; Tag
0x14000baa8  call    cs:__imp_ExFreePoolWithTag
0x14000baaf  nop     dword ptr [rax+rax+00h]
0x14000bab4  mov     rcx, [rdi+28h]; P
0x14000bab8  test    rcx, rcx
0x14000babb  jz      short loc_14000BACB
0x14000babd  xor     edx, edx; Tag
0x14000babf  call    cs:__imp_ExFreePoolWithTag
0x14000bac6  nop     dword ptr [rax+rax+00h]
0x14000bacb  xor     edx, edx; Tag
0x14000bacd  mov     rcx, rdi; P
0x14000bad0  call    cs:__imp_ExFreePoolWithTag
0x14000bad7  nop     dword ptr [rax+rax+00h]
0x14000badc  jmp     loc_14000BE70
0x14000bae1  movzx   edx, byte ptr [r15+1]
0x14000bae6  mov     ecx, 100h
0x14000baeb  mov     r8d, 53736642h
0x14000baf1  lea     rdx, ds:8[rdx*4]
0x14000baf9  call    cs:__imp_ExAllocatePool2
0x14000bb00  nop     dword ptr [rax+rax+00h]
0x14000bb05  mov     rsi, rax
0x14000bb08  test    rax, rax
0x14000bb0b  jnz     short loc_14000BB2B
0x14000bb0d  mov     ecx, cs:dword_140019000
0x14000bb13  cmp     ecx, 3
0x14000bb16  mov     edx, 0C0000017h
0x14000bb1b  mov     ebx, edx
0x14000bb1d  jbe     loc_14000BA69
0x14000bb23  mov     dword ptr [rbp+47h+var_B0], edx
0x14000bb26  jmp     loc_14000BA44
0x14000bb2b  movzx   ecx, byte ptr [r15+1]
0x14000bb30  mov     r8, r15; SourceSid
0x14000bb33  mov     rdx, rsi; DestinationSid
0x14000bb36  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x14000bb3d  call    cs:__imp_RtlCopySid
0x14000bb44  nop     dword ptr [rax+rax+00h]
0x14000bb49  mov     ebx, eax
0x14000bb4b  test    eax, eax
0x14000bb4d  jns     short loc_14000BB66
0x14000bb4f  mov     eax, cs:dword_140019000
0x14000bb55  cmp     eax, 3
0x14000bb58  jbe     loc_14000BA69
0x14000bb5e  mov     dword ptr [rbp+47h+var_B0], ebx
0x14000bb61  jmp     loc_14000BA44
0x14000bb66  mov     r15, [rbp+47h+var_B0]
0x14000bb6a  movzx   eax, word ptr [r15+18h]
0x14000bb6f  lea     ecx, [rax+0Eh]
0x14000bb72  cmp     cx, ax
0x14000bb75  jnb     short loc_14000BB95
0x14000bb77  mov     eax, cs:dword_140019000
0x14000bb7d  mov     ecx, 0C0000095h
0x14000bb82  mov     ebx, ecx
0x14000bb84  cmp     eax, 3
0x14000bb87  jbe     loc_14000BA69
0x14000bb8d  mov     dword ptr [rbp+47h+var_B0], ecx
0x14000bb90  jmp     loc_14000BA44
0x14000bb95  movzx   ebx, cx
0x14000bb98  add     bx, [r13+0]
0x14000bb9d  cmp     bx, cx
0x14000bba0  jb      short loc_14000BB77
0x14000bba2  movzx   edx, bx
0x14000bba5  mov     ecx, 100h
0x14000bbaa  mov     r8d, 46736642h
0x14000bbb0  call    cs:__imp_ExAllocatePool2
0x14000bbb7  nop     dword ptr [rax+rax+00h]
0x14000bbbc  mov     [rbp+47h+var_80], rax
0x14000bbc0  test    rax, rax
0x14000bbc3  jnz     short loc_14000BBD3
0x14000bbc5  mov     eax, cs:dword_140019000
0x14000bbcb  cmp     eax, 3
0x14000bbce  jmp     loc_14000BB16
0x14000bbd3  lea     rdx, [r15+18h]; SourceString
0x14000bbd7  mov     [rbp+47h+DestinationString.Buffer], rax
0x14000bbdb  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x14000bbdf  mov     [rbp+47h+DestinationString.MaximumLength], bx
0x14000bbe3  call    cs:__imp_RtlCopyUnicodeString
0x14000bbea  nop     dword ptr [rax+rax+00h]
0x14000bbef  lea     rdx, ReparsePrefixString; Source
0x14000bbf6  lea     rcx, [rbp+47h+DestinationString]; Destination
0x14000bbfa  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000bc01  nop     dword ptr [rax+rax+00h]
0x14000bc06  mov     ebx, eax
0x14000bc08  test    eax, eax
0x14000bc0a  jns     short loc_14000BC5A
0x14000bc0c  mov     eax, cs:dword_140019000
0x14000bc12  cmp     eax, 3
0x14000bc15  jbe     short loc_14000BC3F
0x14000bc17  mov     dword ptr [rbp+47h+var_B0], ebx
0x14000bc1a  lea     rax, [rbp+47h+var_B0]
0x14000bc1e  mov     [rbp+47h+var_50], 4
0x14000bc26  mov     [rbp+47h+var_58], rax
0x14000bc2a  lea     rdx, byte_140016D91; int
0x14000bc31  lea     rax, [rbp+47h+var_78]
0x14000bc35  mov     qword ptr [rsp+0F0h+PoolTag], rax; PEVENT_DATA_DESCRIPTOR
0x14000bc3a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000bc3f  mov     r15, [rbp+47h+P]
0x14000bc43  mov     rcx, [rbp+47h+var_80]; P
0x14000bc47  xor     edx, edx; Tag
0x14000bc49  call    cs:__imp_ExFreePoolWithTag
0x14000bc50  nop     dword ptr [rax+rax+00h]
0x14000bc55  jmp     loc_14000BA6D
0x14000bc5a  mov     rdx, r13; Source
0x14000bc5d  lea     rcx, [rbp+47h+DestinationString]; Destination
0x14000bc61  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000bc68  nop     dword ptr [rax+rax+00h]
0x14000bc6d  mov     ebx, eax
0x14000bc6f  test    eax, eax
0x14000bc71  js      short loc_14000BC0C
0x14000bc73  mov     r13d, 100h
0x14000bc79  mov     edx, 30h ; '0'
0x14000bc7e  mov     ecx, r13d
0x14000bc81  mov     r8d, 52736642h
0x14000bc87  call    cs:__imp_ExAllocatePool2
0x14000bc8e  nop     dword ptr [rax+rax+00h]
0x14000bc93  mov     rdi, rax
0x14000bc96  test    rax, rax
0x14000bc99  jnz     short loc_14000BCB5
0x14000bc9b  mov     eax, cs:dword_140019000
0x14000bca1  mov     edx, 0C0000017h
0x14000bca6  mov     ebx, edx
0x14000bca8  cmp     eax, 3
0x14000bcab  jbe     short loc_14000BC3F
0x14000bcad  mov     dword ptr [rbp+47h+var_B0], edx
0x14000bcb0  jmp     loc_14000BC1A
0x14000bcb5  mov     rbx, [rbp+47h+var_B0]
0x14000bcb9  mov     r8d, 46736642h
0x14000bcbf  mov     r15, [rbp+47h+P]
0x14000bcc3  mov     rcx, r13
0x14000bcc6  mov     [rax], r15
0x14000bcc9  mov     [rax+8], rsi
0x14000bccd  movzx   edx, word ptr [rbx+8]
0x14000bcd1  call    cs:__imp_ExAllocatePool2
0x14000bcd8  nop     dword ptr [rax+rax+00h]
0x14000bcdd  mov     [rdi+18h], rax
0x14000bce1  test    rax, rax
0x14000bce4  jnz     short loc_14000BD29
0x14000bce6  mov     eax, cs:dword_140019000
0x14000bcec  mov     edx, 0C0000017h
0x14000bcf1  mov     ebx, edx
0x14000bcf3  cmp     eax, 3
0x14000bcf6  jbe     loc_14000BC43
0x14000bcfc  mov     dword ptr [rbp+47h+var_B0], edx
0x14000bcff  lea     rax, [rbp+47h+var_B0]
0x14000bd03  mov     [rbp+47h+var_50], 4
0x14000bd0b  mov     [rbp+47h+var_58], rax
0x14000bd0f  lea     rdx, byte_140016D91; int
0x14000bd16  lea     rax, [rbp+47h+var_78]
0x14000bd1a  mov     qword ptr [rsp+0F0h+PoolTag], rax; PEVENT_DATA_DESCRIPTOR
0x14000bd1f  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000bd24  jmp     loc_14000BC43
0x14000bd29  movzx   eax, word ptr [rbx+8]
0x14000bd2d  lea     rcx, [rdi+10h]; DestinationString
0x14000bd31  lea     rdx, [rbx+8]; SourceString
0x14000bd35  mov     [rdi+12h], ax
0x14000bd39  call    cs:__imp_RtlCopyUnicodeString
0x14000bd40  nop     dword ptr [rax+rax+00h]
0x14000bd45  movzx   edx, [rbp+47h+DestinationString.Length]
0x14000bd49  mov     r8d, 46736642h
0x14000bd4f  mov     rcx, r13
0x14000bd52  call    cs:__imp_ExAllocatePool2
0x14000bd59  nop     dword ptr [rax+rax+00h]
0x14000bd5e  mov     [rdi+28h], rax
0x14000bd62  test    rax, rax
0x14000bd65  jz      loc_14000BCE6
0x14000bd6b  movzx   eax, [rbp+47h+DestinationString.Length]
0x14000bd6f  lea     rcx, [rdi+20h]; DestinationString
0x14000bd73  lea     rdx, [rbp+47h+DestinationString]; SourceString
0x14000bd77  mov     [rdi+22h], ax
0x14000bd7b  call    cs:__imp_RtlCopyUnicodeString
0x14000bd82  nop     dword ptr [rax+rax+00h]
0x14000bd87  lea     r8, [rbp+47h+EcpList]; EcpList
0x14000bd8b  mov     rdx, r12; CallbackData
0x14000bd8e  mov     rcx, r14; Filter
0x14000bd91  call    cs:__imp_FltGetEcpListFromCallbackData
0x14000bd98  nop     dword ptr [rax+rax+00h]
0x14000bd9d  mov     ebx, eax
0x14000bd9f  test    eax, eax
0x14000bda1  js      short loc_14000BE1E
0x14000bda3  cmp     [rbp+47h+EcpList], 0
0x14000bda8  jnz     short loc_14000BDE1
0x14000bdaa  lea     r8, [rbp+47h+EcpList]; EcpList
0x14000bdae  xor     edx, edx; Flags
0x14000bdb0  mov     rcx, r14; Filter
0x14000bdb3  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14000bdba  nop     dword ptr [rax+rax+00h]
0x14000bdbf  mov     ebx, eax
0x14000bdc1  test    eax, eax
0x14000bdc3  js      short loc_14000BE1E
0x14000bdc5  mov     r8, [rbp+47h+EcpList]; EcpList
0x14000bdc9  mov     rdx, r12; CallbackData
0x14000bdcc  mov     rcx, r14; Filter
0x14000bdcf  call    cs:__imp_FltSetEcpListIntoCallbackData
0x14000bdd6  nop     dword ptr [rax+rax+00h]
0x14000bddb  mov     ebx, eax
0x14000bddd  test    eax, eax
0x14000bddf  js      short loc_14000BE1E
0x14000bde1  xor     r9d, r9d; Flags
0x14000bde4  lea     rax, [rbp+47h+var_98]
0x14000bde8  mov     [rsp+0F0h+EcpContext], rax; EcpContext
0x14000bded  lea     rdx, BfsEcpType; EcpType
0x14000bdf4  mov     [rsp+0F0h+PoolTag], 70736642h; PoolTag
0x14000bdfc  mov     rcx, r14; Filter
0x14000bdff  mov     [rsp+0F0h+CleanupCallback], 0; CleanupCallback
0x14000be08  lea     r8d, [r9+10h]; SizeOfContext
0x14000be0c  call    cs:__imp_FltAllocateExtraCreateParameter
0x14000be13  nop     dword ptr [rax+rax+00h]
0x14000be18  mov     ebx, eax
0x14000be1a  test    eax, eax
0x14000be1c  jns     short loc_14000BE35
0x14000be1e  mov     eax, cs:dword_140019000
0x14000be24  cmp     eax, 3
0x14000be27  jbe     loc_14000BC43
0x14000be2d  mov     dword ptr [rbp+47h+var_B0], ebx
0x14000be30  jmp     loc_14000BCFF
0x14000be35  mov     rax, [rbp+47h+var_98]
  ... truncated ...
```
