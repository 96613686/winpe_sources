# CSyncMLCmdCopy::BatchUpItemExecution(IConfigManager2 *,CSyncMLItem *)

- ea: `0x18001f290`
- end: `0x18001f59a`
- name: `?BatchUpItemExecution@CSyncMLCmdCopy@@EEAAJPEAUIConfigManager2@@PEAVCSyncMLItem@@@Z`
- size: `778`
- prototype: `int(CSyncMLCmdCopy *__hidden this, struct IConfigManager2 *, struct CSyncMLItem *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800034d0`
- `0x1800038a0`
- `0x1800046f0`
- `0x1800160ac`
- `0x18001f290`
- `0x180020ef4`
- `0x18002164c`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001f308`
- `OLEAUT32!__imp_VariantInit` at `0x18001f308`
- `OLEAUT32!__imp_VariantClear` at `0x18001f551`
- `OLEAUT32!__imp_VariantClear` at `0x18001f551`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdCopy::BatchUpItemExecution(
        CSyncMLCmdCopy *this,
        struct IConfigManager2 *a2,
        struct CSyncMLItem *a3)
{
  struct IConfigManager2URI *TargetLocURI; // r15
  struct IConfigManager2URI *SourceLocURI; // rdi
  int NodeDataType; // ebx
  struct IConfigNode *v8; // rcx
  __int64 v9; // rax
  struct IConfigNode *v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  struct IConfigNode *v14; // [rsp+30h] [rbp-39h] BYREF
  int v15; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v16; // [rsp+3Ch] [rbp-2Dh] BYREF
  int v17; // [rsp+40h] [rbp-29h] BYREF
  struct IConfigNode *v18; // [rsp+48h] [rbp-21h] BYREF
  int v19; // [rsp+50h] [rbp-19h] BYREF
  int v20; // [rsp+54h] [rbp-15h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-11h] BYREF
  VARIANTARG v22; // [rsp+70h] [rbp+7h] BYREF
  int v23; // [rsp+E8h] [rbp+7Fh] BYREF

  v15 = 0;
  TargetLocURI = CSyncMLItem::GetTargetLocURI(a3);
  SourceLocURI = CSyncMLItem::GetSourceLocURI(a3);
  v18 = 0;
  v14 = 0;
  v23 = 0;
  v16 = 1;
  v19 = 1;
  v17 = 0;
  v20 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !TargetLocURI )
  {
    NodeDataType = -2102788095;
    goto LABEL_28;
  }
  if ( SourceLocURI )
  {
    NodeDataType = (*(__int64 (__fastcall **)(struct IConfigManager2 *, struct IConfigManager2URI *, struct IConfigNode **))(*(_QWORD *)a2 + 88LL))(
                     a2,
                     SourceLocURI,
                     &v18);
    if ( NodeDataType < 0 )
      goto LABEL_27;
    if ( (int)GetCSPProviderType(v18, (enum Provider_Type *)&v23) >= 0 && v23 == 1 )
    {
LABEL_8:
      NodeDataType = 0;
      goto LABEL_27;
    }
    NodeDataType = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v18 + 224LL))(v18, &v15);
    if ( NodeDataType < 0 )
      goto LABEL_27;
    if ( v15 )
    {
      NodeDataType = (*(__int64 (__fastcall **)(struct IConfigManager2 *, struct IConfigManager2URI *, struct IConfigNode **))(*(_QWORD *)a2 + 88LL))(
                       a2,
                       TargetLocURI,
                       &v14);
      if ( NodeDataType < 0 )
        goto LABEL_27;
      if ( (int)GetCSPProviderType(v14, (enum Provider_Type *)&v23) >= 0 && v23 == 1 )
        goto LABEL_8;
      NodeDataType = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v14 + 224LL))(v14, &v15);
      if ( NodeDataType < 0 )
        goto LABEL_27;
      if ( v15 )
      {
        NodeDataType = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v14 + 144LL))(v14, &v17);
        if ( NodeDataType >= 0 )
        {
          v8 = v18;
          *((_DWORD *)a3 + 8) = v17;
          NodeDataType = GetNodeDataType(v8, (enum ConfigDataType *)&v16);
          if ( NodeDataType >= 0 )
          {
            NodeDataType = GetNodeDataType(v14, (enum ConfigDataType *)&v19);
            if ( NodeDataType >= 0 )
            {
              if ( v16 == 8 || v19 == 8 )
              {
                NodeDataType = -2102722555;
              }
              else
              {
                NodeDataType = (*(__int64 (__fastcall **)(struct IConfigNode *, VARIANTARG *))(*(_QWORD *)v18 + 104LL))(
                                 v18,
                                 &pvarg);
                if ( NodeDataType >= 0 )
                {
                  v9 = *(_QWORD *)v14;
                  v22 = pvarg;
                  NodeDataType = (*(__int64 (__fastcall **)(struct IConfigNode *, VARIANTARG *, _QWORD))(v9 + 96))(
                                   v14,
                                   &v22,
                                   v16);
                  if ( NodeDataType >= 0 )
                  {
                    NodeDataType = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v14 + 144LL))(
                                     v14,
                                     &v20);
                    if ( NodeDataType >= 0 )
                    {
                      v10 = v14;
                      *((_DWORD *)a3 + 10) = v20 - v17;
                      NodeDataType = CSyncMLItem::SetCfgNode(a3, v10, 0);
                    }
                  }
                }
              }
            }
          }
        }
        goto LABEL_27;
      }
    }
    NodeDataType = -2046820350;
    goto LABEL_27;
  }
  NodeDataType = -2102788095;
LABEL_27:
  (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)TargetLocURI + 16LL))(TargetLocURI);
LABEL_28:
  if ( SourceLocURI )
    (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)SourceLocURI + 16LL))(SourceLocURI);
  if ( v18 )
  {
    (*(void (__fastcall **)(struct IConfigNode *))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(struct IConfigNode *))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  VariantClear(&pvarg);
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v23 = NodeDataType;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)&dword_180036FEC,
      v11,
      v12,
      (__int64)&v23);
  }
  return (unsigned int)NodeDataType;
}

```

## disassembly

```asm
0x18001f290  push    rbp
0x18001f292  push    rbx
0x18001f293  push    rsi
0x18001f294  push    rdi
0x18001f295  push    r14
0x18001f297  push    r15
0x18001f299  lea     rbp, [rsp-2Fh]
0x18001f29e  sub     rsp, 98h
0x18001f2a5  mov     rcx, r8; this
0x18001f2a8  mov     [rbp+57h+var_88], 0
0x18001f2af  mov     rsi, r8
0x18001f2b2  mov     r14, rdx
0x18001f2b5  call    ?GetTargetLocURI@CSyncMLItem@@QEAAPEAUIConfigManager2URI@@XZ; CSyncMLItem::GetTargetLocURI(void)
0x18001f2ba  mov     rcx, rsi; this
0x18001f2bd  mov     r15, rax
0x18001f2c0  call    ?GetSourceLocURI@CSyncMLItem@@QEAAPEAUIConfigManager2URI@@XZ; CSyncMLItem::GetSourceLocURI(void)
0x18001f2c5  mov     rdi, rax
0x18001f2c8  mov     [rbp+57h+var_78], 0
0x18001f2d0  xor     eax, eax
0x18001f2d2  mov     [rbp+57h+var_90], 0
0x18001f2da  xorps   xmm0, xmm0
0x18001f2dd  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18001f2e1  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001f2e5  mov     [rbp+57h+arg_18], eax
0x18001f2e8  mov     [rbp+57h+var_84], 1
0x18001f2ef  mov     [rbp+57h+var_70], 1
0x18001f2f6  mov     [rbp+57h+var_80], 0
0x18001f2fd  mov     [rbp+57h+var_6C], 0
0x18001f304  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001f308  call    cs:__imp_VariantInit
0x18001f30f  nop     dword ptr [rax+rax+00h]
0x18001f314  test    r15, r15
0x18001f317  jnz     short loc_18001F323
0x18001f319  mov     ebx, 82AA0001h
0x18001f31e  jmp     loc_18001F4FF
0x18001f323  test    rdi, rdi
0x18001f326  jnz     short loc_18001F332
0x18001f328  mov     ebx, 82AA0001h
0x18001f32d  jmp     loc_18001F4F0
0x18001f332  mov     rax, [r14]
0x18001f335  lea     r8, [rbp+57h+var_78]
0x18001f339  mov     rdx, rdi
0x18001f33c  mov     rcx, r14
0x18001f33f  mov     rax, [rax+58h]
0x18001f343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f348  mov     ebx, eax
0x18001f34a  test    eax, eax
0x18001f34c  js      loc_18001F4F0
0x18001f352  mov     rcx, [rbp+57h+var_78]; struct IConfigNode *
0x18001f356  lea     rdx, [rbp+57h+arg_18]; enum Provider_Type *
0x18001f35a  call    ?GetCSPProviderType@@YAJPEAUIConfigNode@@AEAW4Provider_Type@@@Z; GetCSPProviderType(IConfigNode *,Provider_Type &)
0x18001f35f  test    eax, eax
0x18001f361  js      short loc_18001F370
0x18001f363  cmp     [rbp+57h+arg_18], 1
0x18001f367  jnz     short loc_18001F370
0x18001f369  xor     ebx, ebx
0x18001f36b  jmp     loc_18001F4F0
0x18001f370  mov     rcx, [rbp+57h+var_78]
0x18001f374  lea     rdx, [rbp+57h+var_88]
0x18001f378  mov     rax, [rcx]
0x18001f37b  mov     rax, [rax+0E0h]
0x18001f382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f387  mov     ebx, eax
0x18001f389  test    eax, eax
0x18001f38b  js      loc_18001F4F0
0x18001f391  cmp     [rbp+57h+var_88], 0
0x18001f395  jnz     short loc_18001F3A1
0x18001f397  mov     ebx, 86000002h
0x18001f39c  jmp     loc_18001F4F0
0x18001f3a1  mov     rax, [r14]
0x18001f3a4  lea     r8, [rbp+57h+var_90]
0x18001f3a8  mov     rdx, r15
0x18001f3ab  mov     rcx, r14
0x18001f3ae  mov     rax, [rax+58h]
0x18001f3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3b7  mov     ebx, eax
0x18001f3b9  test    eax, eax
0x18001f3bb  js      loc_18001F4F0
0x18001f3c1  mov     rcx, [rbp+57h+var_90]; struct IConfigNode *
0x18001f3c5  lea     rdx, [rbp+57h+arg_18]; enum Provider_Type *
0x18001f3c9  call    ?GetCSPProviderType@@YAJPEAUIConfigNode@@AEAW4Provider_Type@@@Z; GetCSPProviderType(IConfigNode *,Provider_Type &)
0x18001f3ce  test    eax, eax
0x18001f3d0  js      short loc_18001F3D8
0x18001f3d2  cmp     [rbp+57h+arg_18], 1
0x18001f3d6  jz      short loc_18001F369
0x18001f3d8  mov     rcx, [rbp+57h+var_90]
0x18001f3dc  lea     rdx, [rbp+57h+var_88]
0x18001f3e0  mov     rax, [rcx]
0x18001f3e3  mov     rax, [rax+0E0h]
0x18001f3ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3ef  mov     ebx, eax
0x18001f3f1  test    eax, eax
0x18001f3f3  js      loc_18001F4F0
0x18001f3f9  cmp     [rbp+57h+var_88], 0
0x18001f3fd  jz      short loc_18001F397
0x18001f3ff  mov     rcx, [rbp+57h+var_90]
0x18001f403  lea     rdx, [rbp+57h+var_80]
0x18001f407  mov     rax, [rcx]
0x18001f40a  mov     rax, [rax+90h]
0x18001f411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f416  mov     ebx, eax
0x18001f418  test    eax, eax
0x18001f41a  js      loc_18001F4F0
0x18001f420  mov     eax, [rbp+57h+var_80]
0x18001f423  lea     rdx, [rbp+57h+var_84]; enum ConfigDataType *
0x18001f427  mov     rcx, [rbp+57h+var_78]; struct IConfigNode *
0x18001f42b  mov     [rsi+20h], eax
0x18001f42e  call    ?GetNodeDataType@@YAJPEAUIConfigNode@@PEAW4ConfigDataType@@@Z; GetNodeDataType(IConfigNode *,ConfigDataType *)
0x18001f433  mov     ebx, eax
0x18001f435  test    eax, eax
0x18001f437  js      loc_18001F4F0
0x18001f43d  mov     rcx, [rbp+57h+var_90]; struct IConfigNode *
0x18001f441  lea     rdx, [rbp+57h+var_70]; enum ConfigDataType *
0x18001f445  call    ?GetNodeDataType@@YAJPEAUIConfigNode@@PEAW4ConfigDataType@@@Z; GetNodeDataType(IConfigNode *,ConfigDataType *)
0x18001f44a  mov     ebx, eax
0x18001f44c  test    eax, eax
0x18001f44e  js      loc_18001F4F0
0x18001f454  cmp     [rbp+57h+var_84], 8
0x18001f458  jz      loc_18001F4EB
0x18001f45e  cmp     [rbp+57h+var_70], 8
0x18001f462  jz      loc_18001F4EB
0x18001f468  mov     rcx, [rbp+57h+var_78]
0x18001f46c  lea     rdx, [rbp+57h+pvarg]
0x18001f470  mov     rax, [rcx]
0x18001f473  mov     rax, [rax+68h]
0x18001f477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f47c  mov     ebx, eax
0x18001f47e  test    eax, eax
0x18001f480  js      short loc_18001F4F0
0x18001f482  mov     rcx, [rbp+57h+var_90]
0x18001f486  lea     rdx, [rbp+57h+var_50]
0x18001f48a  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18001f48e  mov     r8d, [rbp+57h+var_84]
0x18001f492  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18001f497  mov     rax, [rcx]
0x18001f49a  movaps  [rbp+57h+var_50], xmm0
0x18001f49e  movsd   [rbp+57h+var_40], xmm1
0x18001f4a3  mov     rax, [rax+60h]
0x18001f4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4ac  mov     ebx, eax
0x18001f4ae  test    eax, eax
0x18001f4b0  js      short loc_18001F4F0
0x18001f4b2  mov     rcx, [rbp+57h+var_90]
0x18001f4b6  lea     rdx, [rbp+57h+var_6C]
0x18001f4ba  mov     rax, [rcx]
0x18001f4bd  mov     rax, [rax+90h]
0x18001f4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4c9  mov     ebx, eax
0x18001f4cb  test    eax, eax
0x18001f4cd  js      short loc_18001F4F0
0x18001f4cf  mov     eax, [rbp+57h+var_6C]
0x18001f4d2  xor     r8d, r8d; unsigned int
0x18001f4d5  sub     eax, [rbp+57h+var_80]
0x18001f4d8  mov     rcx, rsi; this
0x18001f4db  mov     rdx, [rbp+57h+var_90]; struct IConfigNode *
0x18001f4df  mov     [rsi+28h], eax
0x18001f4e2  call    ?SetCfgNode@CSyncMLItem@@QEAAJPEAUIConfigNode@@K@Z; CSyncMLItem::SetCfgNode(IConfigNode *,ulong)
0x18001f4e7  mov     ebx, eax
0x18001f4e9  jmp     short loc_18001F4F0
0x18001f4eb  mov     ebx, 82AB0005h
0x18001f4f0  mov     rax, [r15]
0x18001f4f3  mov     rcx, r15
0x18001f4f6  mov     rax, [rax+10h]
0x18001f4fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4ff  test    rdi, rdi
0x18001f502  jz      short loc_18001F513
0x18001f504  mov     rax, [rdi]
0x18001f507  mov     rcx, rdi
0x18001f50a  mov     rax, [rax+10h]
0x18001f50e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f513  mov     rcx, [rbp+57h+var_78]
0x18001f517  test    rcx, rcx
0x18001f51a  jz      short loc_18001F530
0x18001f51c  mov     rax, [rcx]
0x18001f51f  mov     rax, [rax+10h]
0x18001f523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f528  mov     [rbp+57h+var_78], 0
0x18001f530  mov     rcx, [rbp+57h+var_90]
0x18001f534  test    rcx, rcx
0x18001f537  jz      short loc_18001F54D
0x18001f539  mov     rax, [rcx]
0x18001f53c  mov     rax, [rax+10h]
0x18001f540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f545  mov     [rbp+57h+var_90], 0
0x18001f54d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001f551  call    cs:__imp_VariantClear
0x18001f558  nop     dword ptr [rax+rax+00h]
0x18001f55d  mov     eax, cs:dword_18003E048
0x18001f563  cmp     eax, 5
0x18001f566  jbe     short loc_18001F587
0x18001f568  lea     rax, [rbp+57h+arg_18]
0x18001f56c  mov     [rbp+57h+arg_18], ebx
0x18001f56f  lea     rdx, dword_180036FEC
0x18001f576  mov     [rsp+0C0h+var_A0], rax
0x18001f57b  lea     rcx, dword_18003E048
0x18001f582  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001f587  mov     eax, ebx
0x18001f589  add     rsp, 98h
0x18001f590  pop     r15
0x18001f592  pop     r14
0x18001f594  pop     rdi
0x18001f595  pop     rsi
0x18001f596  pop     rbx
0x18001f597  pop     rbp
0x18001f598  retn
```
