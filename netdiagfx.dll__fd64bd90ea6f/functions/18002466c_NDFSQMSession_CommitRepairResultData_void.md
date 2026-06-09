# NDFSQMSession::CommitRepairResultData(void)

- ea: `0x18002466c`
- end: `0x18002489e`
- name: `?CommitRepairResultData@NDFSQMSession@@AEAAJXZ`
- size: `562`
- prototype: `__int64 __fastcall(NDFSQMSession *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180024640`

## callees

- `0x18000579c`
- `0x180006d58`
- `0x180023c48`
- `0x180023e98`
- `0x18002466c`
- `0x180025fe4`
- `0x1800263e0`
- `0x18002c802`
- `0x18002c840`

## import_xrefs

- `ntdll!WinSqmAddToStream` at `0x180024816`
- `ntdll!WinSqmAddToStream` at `0x180024816`

## pseudocode

```c
__int64 __fastcall NDFSQMSession::CommitRepairResultData(NDFSQMSession *this)
{
  const struct NDFSQMSession::SQMRepairResultData *v2; // rsi
  const unsigned __int16 *v3; // rdx
  unsigned __int16 *v4; // rdi
  unsigned __int16 *v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // rdx
  unsigned int v9; // [rsp+20h] [rbp-178h]
  unsigned __int16 *v10; // [rsp+28h] [rbp-170h] BYREF
  unsigned __int16 *v11[2]; // [rsp+30h] [rbp-168h] BYREF
  __int128 v12; // [rsp+40h] [rbp-158h] BYREF
  ATL::CAtlException *v13; // [rsp+50h] [rbp-148h] BYREF
  unsigned __int16 *v14[8]; // [rsp+60h] [rbp-138h] BYREF
  int v15; // [rsp+A0h] [rbp-F8h]
  int v16; // [rsp+A4h] [rbp-F4h]
  unsigned __int8 v17; // [rsp+A8h] [rbp-F0h]
  __int128 v18; // [rsp+ACh] [rbp-ECh]
  __int128 v19; // [rsp+BCh] [rbp-DCh]
  int v20; // [rsp+CCh] [rbp-CCh]
  int v21; // [rsp+D0h] [rbp-C8h]
  int v22; // [rsp+D4h] [rbp-C4h]
  int v23; // [rsp+E0h] [rbp-B8h] BYREF
  _BYTE v24[8]; // [rsp+E8h] [rbp-B0h] BYREF
  int v25; // [rsp+F0h] [rbp-A8h]
  int v26; // [rsp+F8h] [rbp-A0h]
  int v27; // [rsp+100h] [rbp-98h]
  int v28; // [rsp+108h] [rbp-90h]
  int v29; // [rsp+110h] [rbp-88h]
  int v30; // [rsp+118h] [rbp-80h]
  _BYTE v31[16]; // [rsp+120h] [rbp-78h] BYREF
  _BYTE v32[16]; // [rsp+130h] [rbp-68h] BYREF
  int v33; // [rsp+140h] [rbp-58h]
  int v34; // [rsp+148h] [rbp-50h]
  int v35; // [rsp+150h] [rbp-48h]
  int v36; // [rsp+158h] [rbp-40h]
  int v37; // [rsp+160h] [rbp-38h]
  int v38; // [rsp+168h] [rbp-30h]

  v9 = 0;
  v2 = (const struct NDFSQMSession::SQMRepairResultData *)*((_QWORD *)this + 3);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    while ( v2 != *((const struct NDFSQMSession::SQMRepairResultData **)this + 4) )
    {
      NDFSQMSession::SQMRepairResultData::SQMRepairResultData((NDFSQMSession::SQMRepairResultData *)v14, v2);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)v11);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v10);
      if ( __eh34_try(0, 1) )
      {
        __eh34_scope_strut(1);
        v12 = v19;
        AttributeConverter::GuidToString((unsigned int *)&v12, (__int64)v11);
        v12 = v18;
        AttributeConverter::GuidToString((unsigned int *)&v12, (__int64)&v10);
      }
      if ( __eh34_catch(1) )
      {
        if ( __eh34_catch_type(1, &ATL::CAtlException `RTTI Type Descriptor', &v13) )
        {
          v9 = *(_DWORD *)v13;
          __eh34_try_continuation(1, &ATL::CAtlException `RTTI Type Descriptor', &loc_180024844);
          ATL::CStringData::Release((ATL::CStringData *)(v10 - 12));
          ATL::CStringData::Release((ATL::CStringData *)(v11[0] - 12));
          NDFSQMSession::SQMRepairResultData::~SQMRepairResultData((NDFSQMSession::SQMRepairResultData *)v14, v7);
          return v9;
        }
      }
      v23 = 0;
      memset_0(v24, 0, 0x88u);
      v3 = (const unsigned __int16 *)v14;
      if ( v14[3] >= (unsigned __int16 *)8 )
        v3 = v14[0];
      WinSqmCreateStringStreamEntry((struct _SQM_STREAM_ENTRY *)&v23, v3);
      v26 = v15;
      v25 = 1;
      v28 = v16;
      v27 = 1;
      v30 = v17;
      v29 = 1;
      v4 = v11[0];
      WinSqmCreateStringStreamEntry((struct _SQM_STREAM_ENTRY *)v31, v11[0]);
      v5 = v10;
      WinSqmCreateStringStreamEntry((struct _SQM_STREAM_ENTRY *)v32, v10);
      v34 = v20;
      v33 = 1;
      v36 = v21;
      v35 = 1;
      v38 = v22;
      v37 = 1;
      WinSqmAddToStream(*((_QWORD *)this + 1), 3684, 9, &v23);
      ATL::CStringData::Release((ATL::CStringData *)(v5 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v4 - 12));
      NDFSQMSession::SQMRepairResultData::~SQMRepairResultData((NDFSQMSession::SQMRepairResultData *)v14, v6);
      v2 = (const struct NDFSQMSession::SQMRepairResultData *)((char *)v2 + 128);
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v9 = -2147024882;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18002486F);
      return v9;
    }
    if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
    {
      v9 = -2147467259;
      __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_180024871);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18002466c  mov     [rsp+arg_8], rbx
0x180024671  mov     [rsp+arg_10], rsi
0x180024676  push    rdi
0x180024677  push    r14
0x180024679  push    r15
0x18002467b  sub     rsp, 180h
0x180024682  mov     rax, cs:__security_cookie
0x180024689  xor     rax, rsp
0x18002468c  mov     [rsp+198h+var_28], rax
0x180024694  mov     r14, rcx
0x180024697  mov     [rsp+198h+var_178], 0
0x18002469f  mov     rsi, [rcx+18h]
0x1800246a3  mov     r15d, 1
0x1800246a9  cmp     rsi, [r14+20h]
0x1800246ad  jz      loc_18002486D
0x1800246b3  mov     rdx, rsi; struct NDFSQMSession::SQMRepairResultData *
0x1800246b6  lea     rcx, [rsp+198h+var_138]; this
0x1800246bb  call    ??0SQMRepairResultData@NDFSQMSession@@QEAA@AEBU01@@Z; NDFSQMSession::SQMRepairResultData::SQMRepairResultData(NDFSQMSession::SQMRepairResultData const &)
0x1800246c0  nop
0x1800246c1  lea     rcx, [rsp+198h+var_168]
0x1800246c6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800246cb  nop
0x1800246cc  lea     rcx, [rsp+198h+var_170]
0x1800246d1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800246d6  nop
0x1800246d7  movups  xmm0, [rsp+198h+var_DC]
0x1800246df  movdqu  [rsp+198h+var_158], xmm0
0x1800246e5  lea     rdx, [rsp+198h+var_168]
0x1800246ea  lea     rcx, [rsp+198h+var_158]
0x1800246ef  call    ?GuidToString@AttributeConverter@@SAXU_GUID@@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; AttributeConverter::GuidToString(_GUID,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x1800246f4  movups  xmm0, [rsp+198h+var_EC]
0x1800246fc  movdqu  [rsp+198h+var_158], xmm0
0x180024702  lea     rdx, [rsp+198h+var_170]
0x180024707  lea     rcx, [rsp+198h+var_158]
0x18002470c  call    ?GuidToString@AttributeConverter@@SAXU_GUID@@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; AttributeConverter::GuidToString(_GUID,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180024711  nop
0x180024712  mov     [rsp+198h+var_B8], 0
0x18002471d  xor     edx, edx; Val
0x18002471f  mov     r8d, 88h; Size
0x180024725  lea     rcx, [rsp+198h+var_B0]; void *
0x18002472d  call    memset_0
0x180024732  lea     rdx, [rsp+198h+var_138]
0x180024737  cmp     [rsp+198h+var_120], 8
0x18002473d  cmovnb  rdx, [rsp+198h+var_138]; unsigned __int16 *
0x180024743  lea     rcx, [rsp+198h+var_B8]; struct _SQM_STREAM_ENTRY *
0x18002474b  call    ?WinSqmCreateStringStreamEntry@@YAXPEAU_SQM_STREAM_ENTRY@@PEBG@Z; WinSqmCreateStringStreamEntry(_SQM_STREAM_ENTRY *,ushort const *)
0x180024750  mov     ecx, [rsp+198h+var_F8]
0x180024757  mov     [rsp+198h+var_A0], ecx
0x18002475e  mov     [rsp+198h+var_A8], r15d
0x180024766  mov     eax, [rsp+198h+var_F4]
0x18002476d  mov     [rsp+198h+var_90], eax
0x180024774  mov     [rsp+198h+var_98], r15d
0x18002477c  movzx   eax, [rsp+198h+var_F0]
0x180024784  mov     [rsp+198h+var_80], eax
0x18002478b  mov     [rsp+198h+var_88], r15d
0x180024793  mov     rdi, [rsp+198h+var_168]
0x180024798  mov     rdx, rdi; unsigned __int16 *
0x18002479b  lea     rcx, [rsp+198h+var_78]; struct _SQM_STREAM_ENTRY *
0x1800247a3  call    ?WinSqmCreateStringStreamEntry@@YAXPEAU_SQM_STREAM_ENTRY@@PEBG@Z; WinSqmCreateStringStreamEntry(_SQM_STREAM_ENTRY *,ushort const *)
0x1800247a8  mov     rbx, [rsp+198h+var_170]
0x1800247ad  mov     rdx, rbx; unsigned __int16 *
0x1800247b0  lea     rcx, [rsp+198h+var_68]; struct _SQM_STREAM_ENTRY *
0x1800247b8  call    ?WinSqmCreateStringStreamEntry@@YAXPEAU_SQM_STREAM_ENTRY@@PEBG@Z; WinSqmCreateStringStreamEntry(_SQM_STREAM_ENTRY *,ushort const *)
0x1800247bd  mov     ecx, [rsp+198h+var_CC]
0x1800247c4  mov     [rsp+198h+var_50], ecx
0x1800247cb  mov     [rsp+198h+var_58], r15d
0x1800247d3  mov     eax, [rsp+198h+var_C8]
0x1800247da  mov     [rsp+198h+var_40], eax
0x1800247e1  mov     [rsp+198h+var_48], r15d
0x1800247e9  mov     eax, [rsp+198h+var_C4]
0x1800247f0  mov     [rsp+198h+var_30], eax
0x1800247f7  mov     [rsp+198h+var_38], r15d
0x1800247ff  lea     r9, [rsp+198h+var_B8]
0x180024807  mov     edx, 0E64h
0x18002480c  mov     r8d, 9
0x180024812  mov     rcx, [r14+8]
0x180024816  call    cs:__imp_WinSqmAddToStream
0x18002481c  nop
0x18002481d  lea     rcx, [rbx-18h]; this
0x180024821  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024826  nop
0x180024827  lea     rcx, [rdi-18h]; this
0x18002482b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024830  nop
0x180024831  lea     rcx, [rsp+198h+var_138]; this
0x180024836  call    ??1SQMRepairResultData@NDFSQMSession@@QEAA@XZ; NDFSQMSession::SQMRepairResultData::~SQMRepairResultData(void)
0x18002483b  sub     rsi, 0FFFFFFFFFFFFFF80h
0x18002483f  jmp     loc_1800246A9
0x180024844  mov     rcx, [rsp+198h+var_170]
0x180024849  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002484d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024852  nop
0x180024853  mov     rcx, [rsp+198h+var_168]
0x180024858  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002485c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024861  nop
0x180024862  lea     rcx, [rsp+198h+var_138]; this
0x180024867  call    ??1SQMRepairResultData@NDFSQMSession@@QEAA@XZ; NDFSQMSession::SQMRepairResultData::~SQMRepairResultData(void)
0x18002486c  nop
0x18002486d  jmp     short loc_180024871
0x18002486f  jmp     short $+2
0x180024871  mov     eax, [rsp+198h+var_178]
0x180024875  mov     rcx, [rsp+198h+var_28]
0x18002487d  xor     rcx, rsp; StackCookie
0x180024880  call    __security_check_cookie
0x180024885  lea     r11, [rsp+198h+var_18]
0x18002488d  mov     rbx, [r11+28h]
0x180024891  mov     rsi, [r11+30h]
0x180024895  mov     rsp, r11
0x180024898  pop     r15
0x18002489a  pop     r14
0x18002489c  pop     rdi
0x18002489d  retn
```
