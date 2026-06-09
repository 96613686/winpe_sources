# CSyncMLCmdReplace::ReplaceNodeValue(CSyncMLItem *,IConfigNode *,int)

- ea: `0x18000e940`
- end: `0x18000ec5b`
- name: `?ReplaceNodeValue@CSyncMLCmdReplace@@AEBAJPEAVCSyncMLItem@@PEAUIConfigNode@@H@Z`
- size: `795`
- prototype: `int(CSyncMLCmdReplace *__hidden this, struct CSyncMLItem *, struct IConfigNode *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000bc70`

## callees

- `0x180004220`
- `0x180009380`
- `0x180009c70`
- `0x18000e940`
- `0x180014330`
- `0x18001e454`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ec29`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ec29`
- `OLEAUT32!__imp_VariantInit` at `0x18000e980`
- `OLEAUT32!__imp_VariantInit` at `0x18000ea54`
- `OLEAUT32!__imp_VariantInit` at `0x18000e980`
- `OLEAUT32!__imp_VariantInit` at `0x18000ea54`
- `OLEAUT32!__imp_VariantClear` at `0x18000ea93`
- `OLEAUT32!__imp_VariantClear` at `0x18000eada`
- `OLEAUT32!__imp_VariantClear` at `0x18000eb06`
- `OLEAUT32!__imp_VariantClear` at `0x18000eb79`
- `OLEAUT32!__imp_VariantClear` at `0x18000ea93`
- `OLEAUT32!__imp_VariantClear` at `0x18000eada`
- `OLEAUT32!__imp_VariantClear` at `0x18000eb06`
- `OLEAUT32!__imp_VariantClear` at `0x18000eb79`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdReplace::ReplaceNodeValue(
        CSyncMLCmdReplace *this,
        struct CSyncMLItem *a2,
        struct IConfigNode *a3,
        int a4)
{
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdi
  int DataAsVariant; // ebx
  __int64 v17; // rcx
  int v18; // eax
  LONG lVal; // ebx
  __int64 (__fastcall *v20)(struct IConfigNode *, VARIANTARG *, _QWORD); // rax
  VARIANTARG v22; // [rsp+30h] [rbp-49h] BYREF
  _DWORD v23[2]; // [rsp+50h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-9h] BYREF
  __int16 *v26; // [rsp+80h] [rbp+7h]
  int v27; // [rsp+88h] [rbp+Fh]
  int v28; // [rsp+8Ch] [rbp+13h]
  _DWORD *v29; // [rsp+90h] [rbp+17h]
  __int64 v30; // [rsp+98h] [rbp+1Fh]

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v7 = *((_QWORD *)a2 + 2);
  v8 = -1;
  if ( !v7 )
  {
    v9 = *((_QWORD *)a2 + 1);
    if ( !v9 )
      goto LABEL_15;
    while ( 1 )
    {
      v7 = *(_QWORD *)(v9 + 96);
      if ( v7 )
        break;
      v9 = *(_QWORD *)(v9 + 136);
      if ( !v9 )
        goto LABEL_15;
    }
  }
  v10 = 0;
  while ( *((_DWORD *)&CSyncMLMeta::rgSupportedProps + v10) )
  {
    v10 = (unsigned int)(v10 + 1);
    if ( (unsigned int)v10 >= 0x10 )
    {
      LODWORD(v10) = -1;
      break;
    }
  }
  v11 = *(_DWORD *)(v7 + 128);
  if ( _bittest(&v11, v10) )
    v12 = *(_QWORD *)(v7 + 8LL * (unsigned int)v10);
  else
    LODWORD(v12) = 1;
  if ( (_DWORD)v12 == 7 )
    CSyncMLItem::SetFormat((__int64)a2, 7);
LABEL_15:
  v13 = *((_QWORD *)a2 + 2);
  if ( !v13 )
  {
    v14 = *((_QWORD *)a2 + 1);
    if ( !v14 )
    {
LABEL_19:
      LODWORD(v15) = 1;
      goto LABEL_20;
    }
    while ( 1 )
    {
      v13 = *(_QWORD *)(v14 + 96);
      if ( v13 )
        break;
      v14 = *(_QWORD *)(v14 + 136);
      if ( !v14 )
        goto LABEL_19;
    }
  }
  v17 = 0;
  while ( *((_DWORD *)&CSyncMLMeta::rgSupportedProps + v17) )
  {
    v17 = (unsigned int)(v17 + 1);
    if ( (unsigned int)v17 >= 0x10 )
      goto LABEL_30;
  }
  v8 = v17;
LABEL_30:
  v18 = *(_DWORD *)(v13 + 128);
  if ( _bittest(&v18, v8) )
    v15 = *(_QWORD *)(v13 + 8LL * v8);
  else
    LODWORD(v15) = 1;
LABEL_20:
  if ( !a4 )
    goto LABEL_35;
  memset(&v22, 0, sizeof(v22));
  VariantInit(&v22);
  DataAsVariant = (*(__int64 (__fastcall **)(struct IConfigNode *, __int64 *, VARIANTARG *))(*(_QWORD *)a3 + 160LL))(
                    a3,
                    CFGMGR_PROPERTY_DATATYPE,
                    &v22);
  if ( DataAsVariant < 0 )
  {
LABEL_24:
    VariantClear(&v22);
    goto LABEL_44;
  }
  if ( v22.vt != 3 )
  {
    DataAsVariant = -2147467259;
    goto LABEL_24;
  }
  lVal = v22.lVal;
  VariantClear(&v22);
  if ( lVal == 8 )
  {
    if ( (_DWORD)v15 == 8 )
      goto LABEL_35;
LABEL_39:
    DataAsVariant = -2046820335;
    goto LABEL_44;
  }
  if ( (_DWORD)v15 == 8 )
    goto LABEL_39;
LABEL_35:
  DataAsVariant = CSyncMLItem::ValidateData(a2);
  if ( DataAsVariant < 0 )
    goto LABEL_44;
  if ( (_DWORD)v15 == 9 )
  {
    VariantClear(&pvarg);
    goto LABEL_42;
  }
  if ( (_DWORD)v15 != 8 )
  {
    DataAsVariant = CSyncMLItem::GetDataAsVariant(a2, &pvarg);
    if ( DataAsVariant < 0 )
      goto LABEL_44;
LABEL_42:
    v20 = *(__int64 (__fastcall **)(struct IConfigNode *, VARIANTARG *, _QWORD))(*(_QWORD *)a3 + 96LL);
    v22 = pvarg;
    DataAsVariant = v20(a3, &v22, (unsigned int)v15);
    if ( DataAsVariant < 0 )
      goto LABEL_44;
  }
  DataAsVariant = CSyncMLItem::SetNodeProperties(a3, a2, 0);
LABEL_44:
  VariantClear(&pvarg);
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v23[0] = DataAsVariant;
    v29 = v23;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v30 = 4;
    *(_OWORD *)&v22.vt = 0x50B000000uLL;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v26 = word_180036822;
    UserData.Reserved = 2;
    v27 = 29;
    v28 = 1;
    v23[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&v22, 0, 0, 3u, &UserData);
  }
  return (unsigned int)DataAsVariant;
}

```

## disassembly

```asm
0x18000e940  mov     [rsp-8+arg_0], rbx
0x18000e945  push    rbp
0x18000e946  push    rsi
0x18000e947  push    rdi
0x18000e948  push    r14
0x18000e94a  push    r15
0x18000e94c  lea     rbp, [rsp-37h]
0x18000e951  sub     rsp, 0B0h
0x18000e958  mov     rax, cs:__security_cookie
0x18000e95f  xor     rax, rsp
0x18000e962  mov     [rbp+57h+var_30], rax
0x18000e966  xorps   xmm0, xmm0
0x18000e969  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000e96d  xor     eax, eax
0x18000e96f  mov     r15d, r9d
0x18000e972  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18000e976  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18000e97a  mov     r14, r8
0x18000e97d  mov     rsi, rdx
0x18000e980  call    cs:__imp_VariantInit
0x18000e987  nop     dword ptr [rax+rax+00h]
0x18000e98c  mov     rdx, [rsi+10h]
0x18000e990  lea     rdi, ?rgSupportedProps@CSyncMLMeta@@0QBW4SyncMLProp@@B; SyncMLProp const near * const CSyncMLMeta::rgSupportedProps
0x18000e997  mov     ebx, 0FFFFFFFFh
0x18000e99c  test    rdx, rdx
0x18000e99f  jnz     short loc_18000E9C7
0x18000e9a1  mov     rax, [rsi+8]
0x18000e9a5  test    rax, rax
0x18000e9a8  jz      short loc_18000EA06
0x18000e9aa  nop     word ptr [rax+rax+00h]
0x18000e9b0  mov     rdx, [rax+60h]
0x18000e9b4  test    rdx, rdx
0x18000e9b7  jnz     short loc_18000E9C7
0x18000e9b9  mov     rax, [rax+88h]
0x18000e9c0  test    rax, rax
0x18000e9c3  jnz     short loc_18000E9B0
0x18000e9c5  jmp     short loc_18000EA06
0x18000e9c7  xor     ecx, ecx
0x18000e9c9  nop     dword ptr [rax+00000000h]
0x18000e9d0  cmp     dword ptr [rdi+rcx*4], 0
0x18000e9d4  jz      short loc_18000E9DF
0x18000e9d6  inc     ecx
0x18000e9d8  cmp     ecx, 10h
0x18000e9db  jb      short loc_18000E9D0
0x18000e9dd  mov     ecx, ebx
0x18000e9df  mov     eax, [rdx+80h]
0x18000e9e5  bt      eax, ecx
0x18000e9e8  jb      short loc_18000E9F1
0x18000e9ea  mov     eax, 1
0x18000e9ef  jmp     short loc_18000E9F7
0x18000e9f1  mov     eax, ecx
0x18000e9f3  mov     rax, [rdx+rax*8]
0x18000e9f7  cmp     eax, 7
0x18000e9fa  jnz     short loc_18000EA06
0x18000e9fc  mov     edx, eax
0x18000e9fe  mov     rcx, rsi
0x18000ea01  call    ?SetFormat@CSyncMLItem@@QEAAJW4ConfigDataType@@@Z; CSyncMLItem::SetFormat(ConfigDataType)
0x18000ea06  mov     rdx, [rsi+10h]
0x18000ea0a  test    rdx, rdx
0x18000ea0d  jnz     loc_18000EAA4
0x18000ea13  mov     rax, [rsi+8]
0x18000ea17  test    rax, rax
0x18000ea1a  jz      short loc_18000EA35
0x18000ea1c  nop     dword ptr [rax+00h]
0x18000ea20  mov     rdx, [rax+60h]
0x18000ea24  test    rdx, rdx
0x18000ea27  jnz     short loc_18000EAA4
0x18000ea29  mov     rax, [rax+88h]
0x18000ea30  test    rax, rax
0x18000ea33  jnz     short loc_18000EA20
0x18000ea35  mov     edi, 1
0x18000ea3a  test    r15d, r15d
0x18000ea3d  jz      loc_18000EAEF
0x18000ea43  xorps   xmm0, xmm0
0x18000ea46  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18000ea4a  xor     eax, eax
0x18000ea4c  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x18000ea50  mov     qword ptr [rbp+57h+var_A0+10h], rax
0x18000ea54  call    cs:__imp_VariantInit
0x18000ea5b  nop     dword ptr [rax+rax+00h]
0x18000ea60  mov     rax, [r14]
0x18000ea63  lea     r8, [rbp+57h+var_A0]
0x18000ea67  lea     rdx, CFGMGR_PROPERTY_DATATYPE
0x18000ea6e  mov     rcx, r14
0x18000ea71  mov     rax, [rax+0A0h]
0x18000ea78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea7d  lea     rcx, [rbp+57h+var_A0]; pvarg
0x18000ea81  mov     ebx, eax
0x18000ea83  test    eax, eax
0x18000ea85  js      short loc_18000EA93
0x18000ea87  cmp     word ptr [rbp+57h+var_A0], 3
0x18000ea8c  jz      short loc_18000EAD7
0x18000ea8e  mov     ebx, 80004005h
0x18000ea93  call    cs:__imp_VariantClear
0x18000ea9a  nop     dword ptr [rax+rax+00h]
0x18000ea9f  jmp     loc_18000EB75
0x18000eaa4  xor     ecx, ecx
0x18000eaa6  cmp     dword ptr [rdi+rcx*4], 0
0x18000eaaa  jz      short loc_18000EAB5
0x18000eaac  inc     ecx
0x18000eaae  cmp     ecx, 10h
0x18000eab1  jb      short loc_18000EAA6
0x18000eab3  jmp     short loc_18000EAB7
0x18000eab5  mov     ebx, ecx
0x18000eab7  mov     eax, [rdx+80h]
0x18000eabd  bt      eax, ebx
0x18000eac0  jb      short loc_18000EACC
0x18000eac2  mov     edi, 1
0x18000eac7  jmp     loc_18000EA3A
0x18000eacc  mov     eax, ebx
0x18000eace  mov     rdi, [rdx+rax*8]
0x18000ead2  jmp     loc_18000EA3A
0x18000ead7  mov     ebx, dword ptr [rbp+57h+var_A0+8]
0x18000eada  call    cs:__imp_VariantClear
0x18000eae1  nop     dword ptr [rax+rax+00h]
0x18000eae6  cmp     ebx, 8
0x18000eae9  jnz     short loc_18000EB14
0x18000eaeb  cmp     edi, ebx
0x18000eaed  jnz     short loc_18000EB19
0x18000eaef  mov     rcx, rsi; struct CSyncMLItem *
0x18000eaf2  call    ?ValidateData@CSyncMLItem@@SAJPEAV1@@Z; CSyncMLItem::ValidateData(CSyncMLItem *)
0x18000eaf7  mov     ebx, eax
0x18000eaf9  test    eax, eax
0x18000eafb  js      short loc_18000EB75
0x18000eafd  cmp     edi, 9
0x18000eb00  jnz     short loc_18000EB20
0x18000eb02  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000eb06  call    cs:__imp_VariantClear
0x18000eb0d  nop     dword ptr [rax+rax+00h]
0x18000eb12  jmp     short loc_18000EB37
0x18000eb14  cmp     edi, 8
0x18000eb17  jnz     short loc_18000EAEF
0x18000eb19  mov     ebx, 86000011h
0x18000eb1e  jmp     short loc_18000EB75
0x18000eb20  cmp     edi, 8
0x18000eb23  jz      short loc_18000EB65
0x18000eb25  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x18000eb29  mov     rcx, rsi; this
0x18000eb2c  call    ?GetDataAsVariant@CSyncMLItem@@QEBAJPEAUtagVARIANT@@@Z; CSyncMLItem::GetDataAsVariant(tagVARIANT *)
0x18000eb31  mov     ebx, eax
0x18000eb33  test    eax, eax
0x18000eb35  js      short loc_18000EB75
0x18000eb37  mov     rax, [r14]
0x18000eb3a  lea     rdx, [rbp+57h+var_A0]
0x18000eb3e  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18000eb42  mov     r8d, edi
0x18000eb45  mov     rcx, r14
0x18000eb48  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18000eb4d  mov     rax, [rax+60h]
0x18000eb51  movaps  xmmword ptr [rbp+57h+var_A0], xmm0
0x18000eb55  movsd   qword ptr [rbp+57h+var_A0+10h], xmm1
0x18000eb5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb5f  mov     ebx, eax
0x18000eb61  test    eax, eax
0x18000eb63  js      short loc_18000EB75
0x18000eb65  xor     r8d, r8d; int
0x18000eb68  mov     rdx, rsi; struct CSyncMLItem *
0x18000eb6b  mov     rcx, r14; struct IConfigNode *
0x18000eb6e  call    ?SetNodeProperties@CSyncMLItem@@SAJPEAUIConfigNode@@PEAV1@H@Z; CSyncMLItem::SetNodeProperties(IConfigNode *,CSyncMLItem *,int)
0x18000eb73  mov     ebx, eax
0x18000eb75  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000eb79  call    cs:__imp_VariantClear
0x18000eb80  nop     dword ptr [rax+rax+00h]
0x18000eb85  mov     eax, cs:dword_18003E048
0x18000eb8b  cmp     eax, 5
0x18000eb8e  jbe     loc_18000EC35
0x18000eb94  lea     rax, [rbp+57h+var_80]
0x18000eb98  mov     [rbp+57h+var_80], ebx
0x18000eb9b  mov     [rbp+57h+var_40], rax
0x18000eb9f  lea     rcx, _TraceLoggingMetadata
0x18000eba6  movzx   eax, cs:word_180036818
0x18000ebad  lea     rdx, [rbp+57h+var_A0]; EventDescriptor
0x18000ebb1  mov     dword ptr [rbp+57h+var_A0+4], eax
0x18000ebb4  xor     r9d, r9d; RelatedActivityId
0x18000ebb7  mov     rax, cs:off_18003E050
0x18000ebbe  xor     r8d, r8d; ActivityId
0x18000ebc1  mov     [rbp+57h+var_60.Ptr], rax
0x18000ebc5  mov     [rbp+57h+var_38], 4
0x18000ebcd  mov     dword ptr [rbp+57h+var_A0], 0B000000h
0x18000ebd4  mov     qword ptr [rbp+57h+var_A0+8], 0
0x18000ebdc  movzx   eax, word ptr [rax]
0x18000ebdf  mov     [rbp+57h+var_60.Size], eax
0x18000ebe2  lea     rax, word_180036822
0x18000ebe9  mov     [rbp+57h+var_50], rax
0x18000ebed  lea     rax, _TraceLoggingMetadataEnd
0x18000ebf4  sub     eax, ecx
0x18000ebf6  mov     dword ptr [rbp+57h+var_60.0Ch], 2
0x18000ebfd  mov     [rbp+57h+var_48], 1Dh
0x18000ec04  mov     [rbp+57h+var_44], 1
0x18000ec0b  mov     [rbp+57h+var_7C], eax
0x18000ec0e  mov     eax, [rbp+57h+var_7C]
0x18000ec11  mov     rcx, cs:RegHandle; RegHandle
0x18000ec18  lea     rax, [rbp+57h+var_60]
0x18000ec1c  mov     [rsp+0D0h+UserData], rax; UserData
0x18000ec21  mov     [rsp+0D0h+UserDataCount], 3; UserDataCount
0x18000ec29  call    cs:__imp_EventWriteTransfer
0x18000ec30  nop     dword ptr [rax+rax+00h]
0x18000ec35  mov     eax, ebx
0x18000ec37  mov     rcx, [rbp+57h+var_30]
0x18000ec3b  xor     rcx, rsp; StackCookie
0x18000ec3e  call    __security_check_cookie
0x18000ec43  mov     rbx, [rsp+0D0h+arg_0]
0x18000ec4b  add     rsp, 0B0h
0x18000ec52  pop     r15
0x18000ec54  pop     r14
0x18000ec56  pop     rdi
0x18000ec57  pop     rsi
0x18000ec58  pop     rbp
0x18000ec59  retn
```
