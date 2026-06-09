# CSyncMLCmdAdd::BatchUpItemExecution(IConfigManager2 *,CSyncMLItem *)

- ea: `0x18001ef60`
- end: `0x18001f284`
- name: `?BatchUpItemExecution@CSyncMLCmdAdd@@EEAAJPEAUIConfigManager2@@PEAVCSyncMLItem@@@Z`
- size: `804`
- prototype: `int(CSyncMLCmdAdd *__hidden this, struct IConfigManager2 *, struct CSyncMLItem *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800032d0`
- `0x1800034d0`
- `0x1800038a0`
- `0x180004220`
- `0x180009380`
- `0x180009c70`
- `0x180010f0c`
- `0x18001e454`
- `0x18001ef60`
- `0x18002164c`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001efba`
- `OLEAUT32!__imp_VariantInit` at `0x18001efba`
- `OLEAUT32!__imp_VariantClear` at `0x18001f23b`
- `OLEAUT32!__imp_VariantClear` at `0x18001f23b`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdAdd::BatchUpItemExecution(
        CSyncMLCmdAdd *this,
        struct IConfigManager2 *a2,
        struct CSyncMLItem *a3)
{
  struct IConfigManager2URI *TargetLocURI; // rsi
  int DataAsVariant; // ebx
  __int128 v7; // xmm0
  unsigned int Format; // eax
  __int64 v9; // r10
  __int64 v10; // r11
  struct IConfigNode *v11; // rcx
  struct IConfigNode *v12; // rcx
  struct IConfigNode *v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  int v17; // [rsp+30h] [rbp-49h] BYREF
  int v18; // [rsp+34h] [rbp-45h] BYREF
  struct IConfigNode *v19; // [rsp+38h] [rbp-41h] BYREF
  struct IConfigNode *v20; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v21; // [rsp+48h] [rbp-31h] BYREF
  __int64 v22; // [rsp+50h] [rbp-29h] BYREF
  __int64 v23; // [rsp+58h] [rbp-21h] BYREF
  int v24; // [rsp+60h] [rbp-19h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-11h] BYREF
  __int128 v26; // [rsp+80h] [rbp+7h] BYREF
  IRecordInfo *pRecInfo; // [rsp+90h] [rbp+17h]
  int v28; // [rsp+F8h] [rbp+7Fh] BYREF

  v21 = 0;
  v17 = 0;
  v28 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  TargetLocURI = CSyncMLItem::GetTargetLocURI(a3);
  v22 = 0;
  v23 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( TargetLocURI )
  {
    DataAsVariant = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, unsigned int *))(*(_QWORD *)TargetLocURI
                                                                                           + 136LL))(
                      TargetLocURI,
                      &v21);
    if ( DataAsVariant >= 0 )
    {
      if ( v21 > 1 )
      {
        DataAsVariant = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, _QWORD, __int64 *, __int64 *))(*(_QWORD *)TargetLocURI + 80LL))(
                          TargetLocURI,
                          v21 - 1,
                          0,
                          &v22,
                          &v23);
        if ( DataAsVariant >= 0 )
        {
          DataAsVariant = (*(__int64 (__fastcall **)(struct IConfigManager2 *, __int64, struct IConfigNode **))(*(_QWORD *)a2 + 88LL))(
                            a2,
                            v22,
                            &v20);
          if ( DataAsVariant >= 0 )
          {
            if ( !(unsigned int)CSyncMLItem::HasMultiStringData(a3)
              || (DataAsVariant = CSyncMLItem::SetFormat((__int64)a3, 7), DataAsVariant >= 0) )
            {
              DataAsVariant = CSyncMLItem::ValidateData(a3);
              if ( DataAsVariant >= 0 )
              {
                DataAsVariant = CSyncMLItem::GetDataAsVariant(a3, &pvarg);
                if ( DataAsVariant >= 0 )
                {
                  DataAsVariant = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v20 + 144LL))(
                                    v20,
                                    &v17);
                  if ( DataAsVariant >= 0 )
                  {
                    v7 = *(_OWORD *)&pvarg.vt;
                    *((_DWORD *)a3 + 8) = v17;
                    v26 = v7;
                    pRecInfo = pvarg.pRecInfo;
                    Format = CSyncMLItem::GetFormat(a3);
                    DataAsVariant = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int128 *, struct IConfigNode **))(v9 + 32))(
                                      v10,
                                      v23,
                                      Format,
                                      &v26,
                                      &v19);
                    if ( DataAsVariant >= 0 )
                    {
                      DataAsVariant = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v19 + 144LL))(
                                        v19,
                                        &v18);
                      if ( DataAsVariant >= 0 )
                      {
                        v11 = v19;
                        *((_DWORD *)a3 + 9) = v18;
                        DataAsVariant = CSyncMLItem::SetNodeProperties(v11, a3, 1);
                        if ( DataAsVariant >= 0 )
                        {
                          DataAsVariant = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v20 + 144LL))(
                                            v20,
                                            &v28);
                          if ( DataAsVariant >= 0 )
                          {
                            v12 = v19;
                            *((_DWORD *)a3 + 10) = v28 - v17;
                            DataAsVariant = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v12 + 144LL))(
                                              v12,
                                              &v28);
                            if ( DataAsVariant >= 0 )
                            {
                              v13 = v20;
                              *((_DWORD *)a3 + 11) = v28 - v18;
                              DataAsVariant = CSyncMLItem::SetCfgNode(a3, v13, 0);
                              if ( DataAsVariant >= 0 )
                                DataAsVariant = CSyncMLItem::SetCfgNode(a3, v19, 1u);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        DataAsVariant = -2046820335;
      }
    }
    (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)TargetLocURI + 16LL))(TargetLocURI);
  }
  else
  {
    DataAsVariant = -2102788095;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(struct IConfigNode *))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(struct IConfigNode *))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  VariantClear(&pvarg);
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v24 = DataAsVariant;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)byte_180036D31,
      v14,
      v15,
      (__int64)&v24);
  }
  return (unsigned int)DataAsVariant;
}

```

## disassembly

```asm
0x18001ef60  push    rbp
0x18001ef62  push    rbx
0x18001ef63  push    rsi
0x18001ef64  push    rdi
0x18001ef65  push    r14
0x18001ef67  push    r15
0x18001ef69  lea     rbp, [rsp-2Fh]
0x18001ef6e  sub     rsp, 0A8h
0x18001ef75  xor     r15d, r15d
0x18001ef78  mov     rcx, r8; this
0x18001ef7b  mov     [rbp+57h+var_88], r15d
0x18001ef7f  mov     rdi, r8
0x18001ef82  mov     [rbp+57h+var_A0], r15d
0x18001ef86  mov     r14, rdx
0x18001ef89  mov     [rbp+57h+arg_18], r15d
0x18001ef8d  mov     [rbp+57h+var_9C], r15d
0x18001ef91  mov     [rbp+57h+var_98], r15
0x18001ef95  mov     [rbp+57h+var_90], r15
0x18001ef99  call    ?GetTargetLocURI@CSyncMLItem@@QEAAPEAUIConfigManager2URI@@XZ; CSyncMLItem::GetTargetLocURI(void)
0x18001ef9e  mov     rsi, rax
0x18001efa1  mov     [rbp+57h+var_80], r15
0x18001efa5  xor     eax, eax
0x18001efa7  mov     [rbp+57h+var_78], r15
0x18001efab  xorps   xmm0, xmm0
0x18001efae  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18001efb2  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001efb6  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18001efba  call    cs:__imp_VariantInit
0x18001efc1  nop     dword ptr [rax+rax+00h]
0x18001efc6  test    rsi, rsi
0x18001efc9  jnz     short loc_18001EFD5
0x18001efcb  mov     ebx, 82AA0001h
0x18001efd0  jmp     loc_18001F1D3
0x18001efd5  mov     rax, [rsi]
0x18001efd8  lea     rdx, [rbp+57h+var_88]
0x18001efdc  mov     rcx, rsi
0x18001efdf  mov     rax, [rax+88h]
0x18001efe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efeb  mov     ebx, eax
0x18001efed  test    eax, eax
0x18001efef  js      loc_18001F1C4
0x18001eff5  mov     edx, [rbp+57h+var_88]
0x18001eff8  cmp     edx, 1
0x18001effb  ja      short loc_18001F007
0x18001effd  mov     ebx, 86000011h
0x18001f002  jmp     loc_18001F1C4
0x18001f007  mov     rax, [rsi]
0x18001f00a  lea     rcx, [rbp+57h+var_78]
0x18001f00e  mov     [rsp+0D0h+var_B0], rcx
0x18001f013  lea     r9, [rbp+57h+var_80]
0x18001f017  dec     edx
0x18001f019  xor     r8d, r8d
0x18001f01c  mov     rcx, rsi
0x18001f01f  mov     rax, [rax+50h]
0x18001f023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f028  mov     ebx, eax
0x18001f02a  test    eax, eax
0x18001f02c  js      loc_18001F1C4
0x18001f032  mov     rax, [r14]
0x18001f035  lea     r8, [rbp+57h+var_90]
0x18001f039  mov     rdx, [rbp+57h+var_80]
0x18001f03d  mov     rcx, r14
0x18001f040  mov     rax, [rax+58h]
0x18001f044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f049  mov     ebx, eax
0x18001f04b  test    eax, eax
0x18001f04d  js      loc_18001F1C4
0x18001f053  mov     rcx, rdi; this
0x18001f056  call    ?HasMultiStringData@CSyncMLItem@@QEBAHXZ; CSyncMLItem::HasMultiStringData(void)
0x18001f05b  test    eax, eax
0x18001f05d  jz      short loc_18001F076
0x18001f05f  mov     edx, 7
0x18001f064  mov     rcx, rdi
0x18001f067  call    ?SetFormat@CSyncMLItem@@QEAAJW4ConfigDataType@@@Z; CSyncMLItem::SetFormat(ConfigDataType)
0x18001f06c  mov     ebx, eax
0x18001f06e  test    eax, eax
0x18001f070  js      loc_18001F1C4
0x18001f076  mov     rcx, rdi; struct CSyncMLItem *
0x18001f079  call    ?ValidateData@CSyncMLItem@@SAJPEAV1@@Z; CSyncMLItem::ValidateData(CSyncMLItem *)
0x18001f07e  mov     ebx, eax
0x18001f080  test    eax, eax
0x18001f082  js      loc_18001F1C4
0x18001f088  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x18001f08c  mov     rcx, rdi; this
0x18001f08f  call    ?GetDataAsVariant@CSyncMLItem@@QEBAJPEAUtagVARIANT@@@Z; CSyncMLItem::GetDataAsVariant(tagVARIANT *)
0x18001f094  mov     ebx, eax
0x18001f096  test    eax, eax
0x18001f098  js      loc_18001F1C4
0x18001f09e  mov     rcx, [rbp+57h+var_90]
0x18001f0a2  lea     rdx, [rbp+57h+var_A0]
0x18001f0a6  mov     rax, [rcx]
0x18001f0a9  mov     rax, [rax+90h]
0x18001f0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0b5  mov     ebx, eax
0x18001f0b7  test    eax, eax
0x18001f0b9  js      loc_18001F1C4
0x18001f0bf  mov     eax, [rbp+57h+var_A0]
0x18001f0c2  mov     rcx, rdi
0x18001f0c5  mov     r11, [rbp+57h+var_90]
0x18001f0c9  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18001f0cd  mov     [rdi+20h], eax
0x18001f0d0  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18001f0d5  mov     r10, [r11]
0x18001f0d8  movaps  [rbp+57h+var_50], xmm0
0x18001f0dc  movsd   [rbp+57h+var_40], xmm1
0x18001f0e1  call    ?GetFormat@CSyncMLItem@@QEBA?AW4ConfigDataType@@XZ; CSyncMLItem::GetFormat(void)
0x18001f0e6  mov     rdx, [rbp+57h+var_78]
0x18001f0ea  lea     r9, [rbp+57h+var_50]
0x18001f0ee  mov     r8d, eax
0x18001f0f1  mov     rcx, r11
0x18001f0f4  lea     rax, [rbp+57h+var_98]
0x18001f0f8  mov     [rsp+0D0h+var_B0], rax
0x18001f0fd  mov     rax, [r10+20h]
0x18001f101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f106  mov     ebx, eax
0x18001f108  test    eax, eax
0x18001f10a  js      loc_18001F1C4
0x18001f110  mov     rcx, [rbp+57h+var_98]
0x18001f114  lea     rdx, [rbp+57h+var_9C]
0x18001f118  mov     rax, [rcx]
0x18001f11b  mov     rax, [rax+90h]
0x18001f122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f127  mov     ebx, eax
0x18001f129  test    eax, eax
0x18001f12b  js      loc_18001F1C4
0x18001f131  mov     eax, [rbp+57h+var_9C]
0x18001f134  mov     r8d, 1; int
0x18001f13a  mov     rcx, [rbp+57h+var_98]; struct IConfigNode *
0x18001f13e  mov     rdx, rdi; struct CSyncMLItem *
0x18001f141  mov     [rdi+24h], eax
0x18001f144  call    ?SetNodeProperties@CSyncMLItem@@SAJPEAUIConfigNode@@PEAV1@H@Z; CSyncMLItem::SetNodeProperties(IConfigNode *,CSyncMLItem *,int)
0x18001f149  mov     ebx, eax
0x18001f14b  test    eax, eax
0x18001f14d  js      short loc_18001F1C4
0x18001f14f  mov     rcx, [rbp+57h+var_90]
0x18001f153  lea     rdx, [rbp+57h+arg_18]
0x18001f157  mov     rax, [rcx]
0x18001f15a  mov     rax, [rax+90h]
0x18001f161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f166  mov     ebx, eax
0x18001f168  test    eax, eax
0x18001f16a  js      short loc_18001F1C4
0x18001f16c  mov     eax, [rbp+57h+arg_18]
0x18001f16f  lea     rdx, [rbp+57h+arg_18]
0x18001f173  sub     eax, [rbp+57h+var_A0]
0x18001f176  mov     rcx, [rbp+57h+var_98]
0x18001f17a  mov     [rdi+28h], eax
0x18001f17d  mov     rax, [rcx]
0x18001f180  mov     rax, [rax+90h]
0x18001f187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f18c  mov     ebx, eax
0x18001f18e  test    eax, eax
0x18001f190  js      short loc_18001F1C4
0x18001f192  mov     eax, [rbp+57h+arg_18]
0x18001f195  xor     r8d, r8d; unsigned int
0x18001f198  sub     eax, [rbp+57h+var_9C]
0x18001f19b  mov     rcx, rdi; this
0x18001f19e  mov     rdx, [rbp+57h+var_90]; struct IConfigNode *
0x18001f1a2  mov     [rdi+2Ch], eax
0x18001f1a5  call    ?SetCfgNode@CSyncMLItem@@QEAAJPEAUIConfigNode@@K@Z; CSyncMLItem::SetCfgNode(IConfigNode *,ulong)
0x18001f1aa  mov     ebx, eax
0x18001f1ac  test    eax, eax
0x18001f1ae  js      short loc_18001F1C4
0x18001f1b0  mov     rdx, [rbp+57h+var_98]; struct IConfigNode *
0x18001f1b4  mov     r8d, 1; unsigned int
0x18001f1ba  mov     rcx, rdi; this
0x18001f1bd  call    ?SetCfgNode@CSyncMLItem@@QEAAJPEAUIConfigNode@@K@Z; CSyncMLItem::SetCfgNode(IConfigNode *,ulong)
0x18001f1c2  mov     ebx, eax
0x18001f1c4  mov     rax, [rsi]
0x18001f1c7  mov     rcx, rsi
0x18001f1ca  mov     rax, [rax+10h]
0x18001f1ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1d3  mov     rcx, [rbp+57h+var_80]
0x18001f1d7  test    rcx, rcx
0x18001f1da  jz      short loc_18001F1EC
0x18001f1dc  mov     rax, [rcx]
0x18001f1df  mov     rax, [rax+10h]
0x18001f1e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1e8  mov     [rbp+57h+var_80], r15
0x18001f1ec  mov     rcx, [rbp+57h+var_78]
0x18001f1f0  test    rcx, rcx
0x18001f1f3  jz      short loc_18001F205
0x18001f1f5  mov     rax, [rcx]
0x18001f1f8  mov     rax, [rax+10h]
0x18001f1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f201  mov     [rbp+57h+var_78], r15
0x18001f205  mov     rcx, [rbp+57h+var_98]
0x18001f209  test    rcx, rcx
0x18001f20c  jz      short loc_18001F21E
0x18001f20e  mov     rax, [rcx]
0x18001f211  mov     rax, [rax+10h]
0x18001f215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f21a  mov     [rbp+57h+var_98], r15
0x18001f21e  mov     rcx, [rbp+57h+var_90]
0x18001f222  test    rcx, rcx
0x18001f225  jz      short loc_18001F237
0x18001f227  mov     rax, [rcx]
0x18001f22a  mov     rax, [rax+10h]
0x18001f22e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f233  mov     [rbp+57h+var_90], r15
0x18001f237  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001f23b  call    cs:__imp_VariantClear
0x18001f242  nop     dword ptr [rax+rax+00h]
0x18001f247  mov     eax, cs:dword_18003E048
0x18001f24d  cmp     eax, 5
0x18001f250  jbe     short loc_18001F271
0x18001f252  lea     rax, [rbp+57h+var_70]
0x18001f256  mov     [rbp+57h+var_70], ebx
0x18001f259  lea     rdx, byte_180036D31
0x18001f260  mov     [rsp+0D0h+var_B0], rax
0x18001f265  lea     rcx, dword_18003E048
0x18001f26c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001f271  mov     eax, ebx
0x18001f273  add     rsp, 0A8h
0x18001f27a  pop     r15
0x18001f27c  pop     r14
0x18001f27e  pop     rdi
0x18001f27f  pop     rsi
0x18001f280  pop     rbx
0x18001f281  pop     rbp
0x18001f282  retn
```
