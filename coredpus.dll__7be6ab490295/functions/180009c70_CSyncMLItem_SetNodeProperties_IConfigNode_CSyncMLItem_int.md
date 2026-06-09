# CSyncMLItem::SetNodeProperties(IConfigNode *,CSyncMLItem *,int)

- ea: `0x180009c70`
- end: `0x18000a0c7`
- name: `?SetNodeProperties@CSyncMLItem@@SAJPEAUIConfigNode@@PEAV1@H@Z`
- size: `1111`
- prototype: `__int64 __fastcall(struct IConfigNode *, struct CSyncMLItem *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e940`
- `0x18001ef60`

## callees

- `0x180009c70`
- `0x180014330`
- `0x180016208`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009fa2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009fa2`
- `OLEAUT32!__imp_SysAllocString` at `0x180009daa`
- `OLEAUT32!__imp_SysAllocString` at `0x180009daa`
- `OLEAUT32!__imp_VariantInit` at `0x180009d03`
- `OLEAUT32!__imp_VariantInit` at `0x180009d03`
- `OLEAUT32!__imp_VariantClear` at `0x180009d34`
- `OLEAUT32!__imp_VariantClear` at `0x180009d95`
- `OLEAUT32!__imp_VariantClear` at `0x180009e73`
- `OLEAUT32!__imp_VariantClear` at `0x180009ec4`
- `OLEAUT32!__imp_VariantClear` at `0x180009d34`
- `OLEAUT32!__imp_VariantClear` at `0x180009d95`
- `OLEAUT32!__imp_VariantClear` at `0x180009e73`
- `OLEAUT32!__imp_VariantClear` at `0x180009ec4`
- `DMCmnUtils!InvStrCmpIW` at `0x18000a006`
- `DMCmnUtils!InvStrCmpIW` at `0x18000a006`

## pseudocode

```c
__int64 __fastcall CSyncMLItem::SetNodeProperties(struct IConfigNode *a1, struct CSyncMLItem *a2, int a3)
{
  int v3; // ebx
  struct IConfigNode *v4; // rsi
  __int64 *v5; // rdi
  __int64 v7; // r14
  __int64 v8; // rax
  int v9; // r12d
  int v10; // edi
  __int64 v11; // rbx
  int v12; // edx
  __int64 v13; // rcx
  int v14; // eax
  VARTYPE vt; // ax
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 (__fastcall *v21)(struct IConfigNode *, GUID *, struct _EVENT_DATA_DESCRIPTOR *); // rax
  __int64 v23; // rax
  __int64 (__fastcall *v24)(struct IConfigNode *, GUID *, struct _EVENT_DATA_DESCRIPTOR *); // rax
  __int64 v25; // rcx
  int v26; // eax
  int v27; // [rsp+38h] [rbp-69h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-61h] BYREF
  struct IConfigNode *v29; // [rsp+58h] [rbp-49h]
  __int64 v30; // [rsp+60h] [rbp-41h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-39h] BYREF
  GUID v32; // [rsp+78h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+88h] [rbp-19h] BYREF
  IRecordInfo *pRecInfo; // [rsp+98h] [rbp-9h]
  int v35; // [rsp+A0h] [rbp-1h]
  int v36; // [rsp+A4h] [rbp+3h]
  int *v37; // [rsp+A8h] [rbp+7h]
  __int64 v38; // [rsp+B0h] [rbp+Fh]

  v3 = 0;
  v4 = a1;
  v5 = (__int64 *)((char *)a2 + 16);
  v7 = *((_QWORD *)a2 + 2);
  v27 = a3;
  v29 = a1;
  *(_QWORD *)&EventDescriptor.Id = (char *)a2 + 16;
  if ( !v7 )
  {
    v8 = *((_QWORD *)a2 + 1);
    if ( v8 )
    {
      while ( 1 )
      {
        v7 = *(_QWORD *)(v8 + 96);
        if ( v7 )
          break;
        v8 = *(_QWORD *)(v8 + 136);
        if ( !v8 )
          goto LABEL_5;
      }
    }
    else
    {
LABEL_5:
      v7 = 0;
    }
  }
  v30 = 8;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !v7 )
  {
LABEL_29:
    if ( v27 )
      goto LABEL_36;
    v17 = *v5;
    if ( !*v5 )
    {
      v18 = *(_QWORD *)((char *)a2 + v30);
      if ( !v18 )
      {
LABEL_34:
        LODWORD(v19) = 1;
LABEL_35:
        VariantClear(&pvarg);
        v20 = *(_QWORD *)v4;
        pvarg.lVal = v19;
        pvarg.vt = 3;
        v21 = *(__int64 (__fastcall **)(struct IConfigNode *, GUID *, struct _EVENT_DATA_DESCRIPTOR *))(v20 + 168);
        v32 = gc_pgmPropsToGuid;
        UserData = *(struct _EVENT_DATA_DESCRIPTOR *)&pvarg.vt;
        pRecInfo = pvarg.pRecInfo;
        v3 = v21(v4, &v32, &UserData);
        goto LABEL_36;
      }
      while ( 1 )
      {
        v17 = *(_QWORD *)(v18 + 96);
        if ( v17 )
          break;
        v18 = *(_QWORD *)(v18 + 136);
        if ( !v18 )
          goto LABEL_34;
      }
    }
    v25 = 0;
    while ( *((_DWORD *)&CSyncMLMeta::rgSupportedProps + v25) )
    {
      v25 = (unsigned int)(v25 + 1);
      if ( (unsigned int)v25 >= 0x10 )
      {
        LODWORD(v25) = -1;
        break;
      }
    }
    v26 = *(_DWORD *)(v17 + 128);
    if ( _bittest(&v26, v25) )
      v19 = *(_QWORD *)(v17 + 8LL * (unsigned int)v25);
    else
      LODWORD(v19) = 1;
    goto LABEL_35;
  }
  v9 = 0;
  v10 = 0;
  while ( 2 )
  {
    while ( 2 )
    {
      while ( 2 )
      {
        VariantClear(&pvarg);
        v11 = 0;
        while ( 1 )
        {
          v12 = *((_DWORD *)&CSyncMLMeta::rgSupportedProps + v11);
          if ( v12 == v10 )
            break;
          v11 = (unsigned int)(v11 + 1);
          if ( (unsigned int)v11 >= 0x10 )
          {
            v3 = -2147024809;
            goto LABEL_36;
          }
        }
        v13 = 0;
        do
        {
          if ( *((_DWORD *)&CSyncMLMeta::rgUnimplementedProps + v13) == v12 )
            goto LABEL_24;
          v13 = (unsigned int)(v13 + 1);
        }
        while ( (unsigned int)v13 < 3 );
        v14 = *(_DWORD *)(v7 + 128);
        if ( !_bittest(&v14, v11) )
          goto LABEL_24;
        VariantClear(&pvarg);
        if ( (unsigned int)v11 <= 4 )
        {
          pvarg.llVal = (LONGLONG)SysAllocString(*(const OLECHAR **)(v7 + 8 * v11));
          if ( !pvarg.llVal )
          {
            v3 = -2147024882;
            goto LABEL_36;
          }
          vt = 8;
          goto LABEL_40;
        }
        if ( v10 != 11 )
        {
          pvarg.lVal = *(_DWORD *)(v7 + 8 * v11);
          vt = 3;
LABEL_40:
          v3 = 0;
          pvarg.vt = vt;
          goto LABEL_41;
        }
        v16 = MultipleToVariant(*(const unsigned __int16 **)(v7 + 8 * v11), &pvarg);
        v3 = v16;
        if ( v16 < 0 )
        {
          if ( v16 != -2147467263 && v16 != -2147023728 )
            goto LABEL_36;
LABEL_24:
          v3 = 0;
LABEL_25:
          v4 = v29;
          goto LABEL_26;
        }
        vt = pvarg.vt;
LABEL_41:
        if ( v27 && !v10 )
        {
          v9 = 1;
          v10 = 1;
          continue;
        }
        break;
      }
      if ( v10 == 6 && vt == 8 && !InvStrCmpIW(L"text/plain", pvarg.bstrVal) )
        goto LABEL_25;
      v4 = v29;
      UserData = *(struct _EVENT_DATA_DESCRIPTOR *)&pvarg.vt;
      v23 = *(_QWORD *)v29;
      v32 = (GUID)*((_OWORD *)&gc_pgmPropsToGuid + v10);
      v24 = *(__int64 (__fastcall **)(struct IConfigNode *, GUID *, struct _EVENT_DATA_DESCRIPTOR *))(v23 + 168);
      pRecInfo = pvarg.pRecInfo;
      v3 = v24(v29, &v32, &UserData);
      if ( v3 < 0 )
        goto LABEL_36;
      if ( !v10 )
      {
        v9 = 1;
        v10 = 1;
        continue;
      }
      break;
    }
LABEL_26:
    if ( (unsigned int)++v10 <= 0xE )
      continue;
    break;
  }
  if ( !v9 )
  {
    v5 = *(__int64 **)&EventDescriptor.Id;
    goto LABEL_29;
  }
LABEL_36:
  VariantClear(&pvarg);
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v27 = v3;
    EventDescriptor.Keyword = 0;
    v37 = &v27;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v38 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    UserData.Size = (unsigned __int16)*off_18003E050;
    pRecInfo = (IRecordInfo *)byte_180036389;
    UserData.Reserved = 2;
    v35 = 30;
    v36 = 1;
    LODWORD(v29) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180009c70  mov     r11, rsp
0x180009c73  push    rbp
0x180009c74  push    rbx
0x180009c75  lea     rbp, [r11-5Fh]
0x180009c79  sub     rsp, 0E8h
0x180009c80  mov     rax, cs:__security_cookie
0x180009c87  xor     rax, rsp
0x180009c8a  mov     [rbp+57h+var_40], rax
0x180009c8e  mov     [r11+18h], rsi
0x180009c92  xor     ebx, ebx
0x180009c94  mov     [r11-18h], rdi
0x180009c98  mov     rsi, rcx
0x180009c9b  mov     [r11-20h], r12
0x180009c9f  lea     rdi, [rdx+10h]
0x180009ca3  mov     [r11-28h], r13
0x180009ca7  mov     r13, rdx
0x180009caa  mov     [r11-30h], r14
0x180009cae  mov     r14, [rdi]
0x180009cb1  mov     [r11-38h], r15
0x180009cb5  mov     [rbp+57h+var_C0], r8d
0x180009cb9  mov     [rbp+57h+var_A0], rcx
0x180009cbd  mov     qword ptr [rbp+57h+EventDescriptor.Id], rdi
0x180009cc1  test    r14, r14
0x180009cc4  jnz     short loc_180009CE8
0x180009cc6  mov     rax, [rdx+8]
0x180009cca  test    rax, rax
0x180009ccd  jz      short loc_180009CE5
0x180009ccf  nop
0x180009cd0  mov     r14, [rax+60h]
0x180009cd4  test    r14, r14
0x180009cd7  jnz     short loc_180009CE8
0x180009cd9  mov     rax, [rax+88h]
0x180009ce0  test    rax, rax
0x180009ce3  jnz     short loc_180009CD0
0x180009ce5  xor     r14d, r14d
0x180009ce8  xorps   xmm0, xmm0
0x180009ceb  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180009cef  xor     eax, eax
0x180009cf1  mov     r15d, 8
0x180009cf7  mov     [rbp+57h+var_98], r15
0x180009cfb  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180009cff  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180009d03  call    cs:__imp_VariantInit
0x180009d0a  nop     dword ptr [rax+rax+00h]
0x180009d0f  lea     r8, __ImageBase
0x180009d16  mov     r12d, 3
0x180009d1c  test    r14, r14
0x180009d1f  jz      loc_180009E2E
0x180009d25  xor     r12d, r12d
0x180009d28  xor     edi, edi
0x180009d2a  nop     word ptr [rax+rax+00h]
0x180009d30  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180009d34  call    cs:__imp_VariantClear
0x180009d3b  nop     dword ptr [rax+rax+00h]
0x180009d40  xor     ebx, ebx
0x180009d42  lea     r8, __ImageBase
0x180009d49  nop     dword ptr [rax+00000000h]
0x180009d50  mov     edx, ds:rva ?rgSupportedProps@CSyncMLMeta@@0QBW4SyncMLProp@@B[r8+rbx*4]; SyncMLProp const near * const CSyncMLMeta::rgSupportedProps ...
0x180009d58  cmp     edx, edi
0x180009d5a  jz      short loc_180009D6D
0x180009d5c  inc     ebx
0x180009d5e  cmp     ebx, 10h
0x180009d61  jb      short loc_180009D50
0x180009d63  mov     ebx, 80070057h
0x180009d68  jmp     loc_180009EC0
0x180009d6d  xor     ecx, ecx
0x180009d6f  nop
0x180009d70  cmp     ds:rva ?rgUnimplementedProps@CSyncMLMeta@@0QBW4SyncMLProp@@B[r8+rcx*4], edx; SyncMLProp const near * const CSyncMLMeta::rgUnimplementedProps ...
0x180009d78  jz      loc_180009E03
0x180009d7e  inc     ecx
0x180009d80  cmp     ecx, 3
0x180009d83  jb      short loc_180009D70
0x180009d85  mov     eax, [r14+80h]
0x180009d8c  bt      eax, ebx
0x180009d8f  jnb     short loc_180009E03
0x180009d91  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180009d95  call    cs:__imp_VariantClear
0x180009d9c  nop     dword ptr [rax+rax+00h]
0x180009da1  cmp     ebx, 4
0x180009da4  ja      short loc_180009DCC
0x180009da6  mov     rcx, [r14+rbx*8]; psz
0x180009daa  call    cs:__imp_SysAllocString
0x180009db1  nop     dword ptr [rax+rax+00h]
0x180009db6  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180009dba  test    rax, rax
0x180009dbd  jz      loc_18000A082
0x180009dc3  movzx   eax, r15w
0x180009dc7  jmp     loc_180009FD3
0x180009dcc  cmp     edi, 0Bh
0x180009dcf  jnz     loc_180009FC7
0x180009dd5  mov     rcx, [r14+rbx*8]; unsigned __int16 *
0x180009dd9  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x180009ddd  call    ?MultipleToVariant@@YAJPEBGPEAUtagVARIANT@@@Z; MultipleToVariant(ushort const *,tagVARIANT *)
0x180009de2  mov     ebx, eax
0x180009de4  test    eax, eax
0x180009de6  js      short loc_180009DF1
0x180009de8  movzx   eax, word ptr [rbp+57h+pvarg]
0x180009dec  jmp     loc_180009FD9
0x180009df1  cmp     eax, 80004001h
0x180009df6  jz      short loc_180009E03
0x180009df8  cmp     eax, 80070490h
0x180009dfd  jnz     loc_180009EC0
0x180009e03  xor     ebx, ebx
0x180009e05  mov     rsi, [rbp+57h+var_A0]
0x180009e09  inc     edi
0x180009e0b  cmp     edi, 0Eh
0x180009e0e  jbe     loc_180009D30
0x180009e14  test    r12d, r12d
0x180009e17  jnz     loc_180009EC0
0x180009e1d  mov     rdi, qword ptr [rbp+57h+EventDescriptor.Id]
0x180009e21  lea     r8, __ImageBase
0x180009e28  mov     r12d, 3
0x180009e2e  cmp     [rbp+57h+var_C0], 0
0x180009e32  jnz     loc_180009EC0
0x180009e38  mov     rdx, [rdi]
0x180009e3b  test    rdx, rdx
0x180009e3e  jnz     loc_18000A08C
0x180009e44  mov     rax, [rbp+57h+var_98]
0x180009e48  mov     rax, [rax+r13]
0x180009e4c  test    rax, rax
0x180009e4f  jz      short loc_180009E6A
0x180009e51  mov     rdx, [rax+60h]
0x180009e55  test    rdx, rdx
0x180009e58  jnz     loc_18000A08C
0x180009e5e  mov     rax, [rax+88h]
0x180009e65  test    rax, rax
0x180009e68  jnz     short loc_180009E51
0x180009e6a  mov     ebx, 1
0x180009e6f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180009e73  call    cs:__imp_VariantClear
0x180009e7a  nop     dword ptr [rax+rax+00h]
0x180009e7f  movaps  xmm0, xmmword ptr cs:?gc_pgmPropsToGuid@@3QBU_GUID@@B.Data1; _GUID const near * const gc_pgmPropsToGuid ...
0x180009e86  lea     r8, [rbp+57h+UserData]
0x180009e8a  mov     rax, [rsi]
0x180009e8d  lea     rdx, [rbp+57h+var_80]
0x180009e91  mov     dword ptr [rbp+57h+pvarg+8], ebx
0x180009e94  mov     rcx, rsi
0x180009e97  mov     word ptr [rbp+57h+pvarg], r12w
0x180009e9c  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x180009ea0  mov     rax, [rax+0A8h]
0x180009ea7  movups  [rbp+57h+var_80], xmm0
0x180009eab  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x180009eb0  movaps  xmmword ptr [rbp+57h+UserData.Ptr], xmm1
0x180009eb4  movsd   [rbp+57h+var_60], xmm0
0x180009eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ebe  mov     ebx, eax
0x180009ec0  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180009ec4  call    cs:__imp_VariantClear
0x180009ecb  nop     dword ptr [rax+rax+00h]
0x180009ed0  mov     eax, cs:dword_18003E048
0x180009ed6  mov     r15, [rsp+0F0h+var_30]
0x180009ede  mov     r14, [rsp+0F0h+var_28]
0x180009ee6  mov     r13, [rsp+0F0h+var_20]
0x180009eee  mov     r12, [rsp+0F0h+var_18]
0x180009ef6  mov     rdi, [rsp+0E0h]
0x180009efe  mov     rsi, [rsp+0F0h+arg_10]
0x180009f06  cmp     eax, 5
0x180009f09  jbe     loc_180009FAE
0x180009f0f  xor     ecx, ecx
0x180009f11  mov     [rbp+57h+var_C0], ebx
0x180009f14  mov     [rbp+57h+EventDescriptor.Keyword], rcx
0x180009f18  lea     rax, [rbp+57h+var_C0]
0x180009f1c  mov     [rbp+57h+var_50], rax
0x180009f20  lea     rcx, _TraceLoggingMetadata
0x180009f27  movzx   eax, cs:word_18003637F
0x180009f2e  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180009f32  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180009f35  xor     r9d, r9d; RelatedActivityId
0x180009f38  mov     rax, cs:off_18003E050
0x180009f3f  xor     r8d, r8d; ActivityId
0x180009f42  mov     [rbp+57h+UserData.Ptr], rax
0x180009f46  mov     [rbp+57h+var_48], 4
0x180009f4e  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180009f55  movzx   eax, word ptr [rax]
0x180009f58  mov     [rbp+57h+UserData.Size], eax
0x180009f5b  lea     rax, byte_180036389
0x180009f62  mov     [rbp+57h+var_60], rax
0x180009f66  lea     rax, _TraceLoggingMetadataEnd
0x180009f6d  sub     eax, ecx
0x180009f6f  mov     dword ptr [rbp+57h+UserData.0Ch], 2
0x180009f76  mov     [rbp+57h+var_58], 1Eh
0x180009f7d  mov     [rbp+57h+var_54], 1
0x180009f84  mov     dword ptr [rbp+57h+var_A0], eax
0x180009f87  mov     eax, dword ptr [rbp+57h+var_A0]
0x180009f8a  mov     rcx, cs:RegHandle; RegHandle
0x180009f91  lea     rax, [rbp+57h+UserData]
0x180009f95  mov     [rsp+28h], rax; UserData
0x180009f9a  mov     [rsp+0F0h+UserDataCount], 3; UserDataCount
0x180009fa2  call    cs:__imp_EventWriteTransfer
0x180009fa9  nop     dword ptr [rax+rax+00h]
0x180009fae  mov     eax, ebx
0x180009fb0  mov     rcx, [rbp+57h+var_40]
0x180009fb4  xor     rcx, rsp; StackCookie
0x180009fb7  call    __security_check_cookie
0x180009fbc  add     rsp, 0E8h
0x180009fc3  pop     rbx
0x180009fc4  pop     rbp
0x180009fc5  retn
0x180009fc7  mov     eax, [r14+rbx*8]
0x180009fcb  mov     dword ptr [rbp+57h+pvarg+8], eax
0x180009fce  mov     eax, 3
0x180009fd3  xor     ebx, ebx
0x180009fd5  mov     word ptr [rbp+57h+pvarg], ax
0x180009fd9  cmp     [rbp+57h+var_C0], 0
0x180009fdd  jz      short loc_180009FF0
0x180009fdf  test    edi, edi
0x180009fe1  jnz     short loc_180009FF0
0x180009fe3  mov     r12d, 1
0x180009fe9  inc     edi
0x180009feb  jmp     loc_180009D30
0x180009ff0  cmp     edi, 6
0x180009ff3  jnz     short loc_18000A01A
0x180009ff5  cmp     r15w, ax
0x180009ff9  jnz     short loc_18000A01A
0x180009ffb  mov     rdx, qword ptr [rbp+57h+pvarg+8]
0x180009fff  lea     rcx, ?gc_szDefaultType@@3QBGB; "text/plain"
0x18000a006  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x18000a00d  nop     dword ptr [rax+rax+00h]
0x18000a012  test    eax, eax
0x18000a014  jz      loc_180009E05
0x18000a01a  mov     rsi, [rbp+57h+var_A0]
0x18000a01e  lea     rcx, __ImageBase
0x18000a025  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18000a029  movsxd  rax, edi
0x18000a02c  lea     r8, [rbp+57h+UserData]
0x18000a030  add     rax, rax
0x18000a033  lea     rdx, [rbp+57h+var_80]
0x18000a037  movaps  xmmword ptr [rbp+57h+UserData.Ptr], xmm1
0x18000a03b  movups  xmm0, xmmword ptr rva ?gc_pgmPropsToGuid@@3QBU_GUID@@B.Data1[rcx+rax*8]; _GUID const near * const gc_pgmPropsToGuid ...
0x18000a043  mov     rax, [rsi]
0x18000a046  mov     rcx, rsi
0x18000a049  movups  [rbp+57h+var_80], xmm0
0x18000a04d  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x18000a052  mov     rax, [rax+0A8h]
0x18000a059  movsd   [rbp+57h+var_60], xmm0
0x18000a05e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a063  mov     ebx, eax
0x18000a065  test    eax, eax
0x18000a067  js      loc_180009EC0
0x18000a06d  test    edi, edi
0x18000a06f  jnz     loc_180009E09
0x18000a075  mov     r12d, 1
0x18000a07b  inc     edi
0x18000a07d  jmp     loc_180009D30
0x18000a082  mov     ebx, 8007000Eh
0x18000a087  jmp     loc_180009EC0
0x18000a08c  xor     ecx, ecx
0x18000a08e  xchg    ax, ax
0x18000a090  cmp     ds:rva ?rgSupportedProps@CSyncMLMeta@@0QBW4SyncMLProp@@B[r8+rcx*4], 0; SyncMLProp const near * const CSyncMLMeta::rgSupportedProps ...
0x18000a099  jz      short loc_18000A0A7
0x18000a09b  inc     ecx
0x18000a09d  cmp     ecx, 10h
0x18000a0a0  jb      short loc_18000A090
0x18000a0a2  mov     ecx, 0FFFFFFFFh
0x18000a0a7  mov     eax, [rdx+80h]
0x18000a0ad  bt      eax, ecx
0x18000a0b0  jb      short loc_18000A0BC
0x18000a0b2  mov     ebx, 1
0x18000a0b7  jmp     loc_180009E6F
0x18000a0bc  mov     eax, ecx
0x18000a0be  mov     rbx, [rdx+rax*8]
0x18000a0c2  jmp     loc_180009E6F
```
