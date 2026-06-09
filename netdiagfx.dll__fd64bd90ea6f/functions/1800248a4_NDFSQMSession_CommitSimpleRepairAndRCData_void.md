# NDFSQMSession::CommitSimpleRepairAndRCData(void)

- ea: `0x1800248a4`
- end: `0x180024a30`
- name: `?CommitSimpleRepairAndRCData@NDFSQMSession@@AEAAJXZ`
- size: `396`
- prototype: `__int64 __fastcall(NDFSQMSession *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180024640`

## callees

- `0x1800056bc`
- `0x18000579c`
- `0x180006d58`
- `0x180023c48`
- `0x180023e98`
- `0x1800248a4`
- `0x1800263e0`
- `0x18002c840`

## import_xrefs

- `ntdll!WinSqmSetString` at `0x180024999`
- `ntdll!WinSqmSetString` at `0x1800249d8`
- `ntdll!WinSqmSetString` at `0x180024999`
- `ntdll!WinSqmSetString` at `0x1800249d8`
- `ntdll!WinSqmSetDWORD` at `0x1800248e3`
- `ntdll!WinSqmSetDWORD` at `0x18002494e`
- `ntdll!WinSqmSetDWORD` at `0x1800248e3`
- `ntdll!WinSqmSetDWORD` at `0x18002494e`

## pseudocode

```c
__int64 __fastcall NDFSQMSession::CommitSimpleRepairAndRCData(NDFSQMSession *this)
{
  unsigned int v2; // eax
  int v3; // edi
  const struct NDFSQMSession::SQMRepairResultData *i; // rbx
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 v7; // rbx
  __int64; // rax
  unsigned int v9[4]; // [rsp+20h] [rbp-F8h] BYREF
  __int128 v10; // [rsp+30h] [rbp-E8h] BYREF
  ATL::CAtlException *v11; // [rsp+40h] [rbp-D8h] BYREF
  __int128 v12; // [rsp+50h] [rbp-C8h] BYREF
  _BYTE v13[112]; // [rsp+60h] [rbp-B8h] BYREF
  int v14; // [rsp+D0h] [rbp-48h]
  int v15; // [rsp+D8h] [rbp-40h]

  v2 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>((__int64)(*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) >> 7);
  WinSqmSetDWORD(*((_QWORD *)this + 1), 3649, v2);
  v3 = -1;
  for ( i = (const struct NDFSQMSession::SQMRepairResultData *)*((_QWORD *)this + 3);
        ;
        i = (const struct NDFSQMSession::SQMRepairResultData *)((char *)i + 128) )
  {
    if ( i == *((const struct NDFSQMSession::SQMRepairResultData **)this + 4) )
    {
      if ( v3 != -1 )
LABEL_9:
        WinSqmSetDWORD(*((_QWORD *)this + 1), 3651, (unsigned int)v3);
      if ( *((_QWORD *)this + 2) )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)v9);
        if ( __eh34_try(-1, 2) )
        {
          __eh34_scope_strut(2);
          v10 = *(_OWORD *)(*((_QWORD *)this + 2) + 76LL);
          AttributeConverter::GuidToString((unsigned int *)&v10, (__int64)v9);
          v6 = *(_QWORD *)v9;
          WinSqmSetString(*((_QWORD *)this + 1), 3663, *(_QWORD *)v9);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v10);
          v12 = *(_OWORD *)(*((_QWORD *)this + 2) + 92LL);
          AttributeConverter::GuidToString((unsigned int *)&v12, (__int64)&v10);
          v7 = v10;
          WinSqmSetString(*((_QWORD *)this + 1), 3664, v10);
          ATL::CStringData::Release((ATL::CStringData *)(v7 - 24));
          ATL::CStringData::Release((ATL::CStringData *)(v6 - 24));
        }
        if ( __eh34_catch(2) )
        {
          if ( __eh34_catch_type(2, &ATL::CAtlException `RTTI Type Descriptor', &v11) )
          {
            v9[0] = *(_DWORD *)v11;
            __eh34_try_continuation(2, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800249FA);
            goto LABEL_13;
          }
        }
      }
      v9[0] = 0;
      goto LABEL_13;
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      NDFSQMSession::SQMRepairResultData::SQMRepairResultData((NDFSQMSession::SQMRepairResultData *)v13, i);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v9[0] = -2147024882;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180024A2E);
        goto LABEL_13;
      }
      if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
      {
        v9[0] = -2147467259;
        __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_1800249FA);
LABEL_13:
         = v9[0];
      }
    }
    if ( v14 )
    {
      if ( v15 > v3 )
      {
        v3 = v15;
        if ( v15 == 4 )
        {
          NDFSQMSession::SQMRepairResultData::~SQMRepairResultData((NDFSQMSession::SQMRepairResultData *)v13, v5);
          goto LABEL_9;
        }
      }
    }
    NDFSQMSession::SQMRepairResultData::~SQMRepairResultData((NDFSQMSession::SQMRepairResultData *)v13, v5);
  }
}

```

## disassembly

```asm
0x1800248a4  push    rbx
0x1800248a6  push    rsi
0x1800248a7  push    rdi
0x1800248a8  push    r14
0x1800248aa  sub     rsp, 0F8h
0x1800248b1  mov     rax, cs:__security_cookie
0x1800248b8  xor     rax, rsp
0x1800248bb  mov     [rsp+118h+var_38], rax
0x1800248c3  mov     rsi, rcx
0x1800248c6  mov     rcx, [rcx+20h]
0x1800248ca  sub     rcx, [rsi+18h]
0x1800248ce  sar     rcx, 7
0x1800248d2  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x1800248d7  mov     r8d, eax
0x1800248da  mov     edx, 0E41h
0x1800248df  mov     rcx, [rsi+8]
0x1800248e3  call    cs:__imp_WinSqmSetDWORD
0x1800248e9  xor     r14d, r14d
0x1800248ec  or      edi, 0FFFFFFFFh
0x1800248ef  mov     rbx, [rsi+18h]
0x1800248f3  cmp     rbx, [rsi+20h]
0x1800248f7  jnz     short loc_180024900
0x1800248f9  cmp     edi, 0FFFFFFFFh
0x1800248fc  jz      short loc_180024955
0x1800248fe  jmp     short loc_180024942
0x180024900  mov     rdx, rbx; struct NDFSQMSession::SQMRepairResultData *
0x180024903  lea     rcx, [rsp+118h+var_B8]; this
0x180024908  call    ??0SQMRepairResultData@NDFSQMSession@@QEAA@AEBU01@@Z; NDFSQMSession::SQMRepairResultData::SQMRepairResultData(NDFSQMSession::SQMRepairResultData const &)
0x18002490d  cmp     [rsp+118h+var_48], 0
0x180024915  jz      loc_180024A1B
0x18002491b  cmp     [rsp+118h+var_40], edi
0x180024922  jle     loc_180024A1B
0x180024928  mov     edi, [rsp+118h+var_40]
0x18002492f  cmp     edi, 4
0x180024932  jnz     loc_180024A1B
0x180024938  lea     rcx, [rsp+118h+var_B8]; this
0x18002493d  call    ??1SQMRepairResultData@NDFSQMSession@@QEAA@XZ; NDFSQMSession::SQMRepairResultData::~SQMRepairResultData(void)
0x180024942  mov     r8d, edi
0x180024945  mov     edx, 0E43h
0x18002494a  mov     rcx, [rsi+8]
0x18002494e  call    cs:__imp_WinSqmSetDWORD
0x180024954  nop
0x180024955  cmp     qword ptr [rsi+10h], 0
0x18002495a  jz      loc_1800249F3
0x180024960  lea     rcx, [rsp+118h+var_F8]
0x180024965  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002496a  nop
0x18002496b  mov     rax, [rsi+10h]
0x18002496f  movups  xmm0, xmmword ptr [rax+4Ch]
0x180024973  movdqu  [rsp+118h+var_E8], xmm0
0x180024979  lea     rdx, [rsp+118h+var_F8]
0x18002497e  lea     rcx, [rsp+118h+var_E8]
0x180024983  call    ?GuidToString@AttributeConverter@@SAXU_GUID@@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; AttributeConverter::GuidToString(_GUID,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180024988  mov     rdi, qword ptr [rsp+118h+var_F8]
0x18002498d  mov     r8, rdi
0x180024990  mov     edx, 0E4Fh
0x180024995  mov     rcx, [rsi+8]
0x180024999  call    cs:__imp_WinSqmSetString
0x18002499f  lea     rcx, [rsp+118h+var_E8]
0x1800249a4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800249a9  nop
0x1800249aa  mov     rax, [rsi+10h]
0x1800249ae  movups  xmm0, xmmword ptr [rax+5Ch]
0x1800249b2  movdqu  [rsp+118h+var_C8], xmm0
0x1800249b8  lea     rdx, [rsp+118h+var_E8]
0x1800249bd  lea     rcx, [rsp+118h+var_C8]
0x1800249c2  call    ?GuidToString@AttributeConverter@@SAXU_GUID@@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; AttributeConverter::GuidToString(_GUID,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x1800249c7  mov     rbx, qword ptr [rsp+118h+var_E8]
0x1800249cc  mov     r8, rbx
0x1800249cf  mov     edx, 0E50h
0x1800249d4  mov     rcx, [rsi+8]
0x1800249d8  call    cs:__imp_WinSqmSetString
0x1800249de  nop
0x1800249df  lea     rcx, [rbx-18h]; this
0x1800249e3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800249e8  nop
0x1800249e9  lea     rcx, [rdi-18h]; this
0x1800249ed  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800249f2  nop
0x1800249f3  mov     [rsp+118h+var_F8], r14d
0x1800249f8  jmp     short $+2
0x1800249fa  mov     eax, [rsp+118h+var_F8]
0x1800249fe  mov     rcx, [rsp+118h+var_38]
0x180024a06  xor     rcx, rsp; StackCookie
0x180024a09  call    __security_check_cookie
0x180024a0e  add     rsp, 0F8h
0x180024a15  pop     r14
0x180024a17  pop     rdi
0x180024a18  pop     rsi
0x180024a19  pop     rbx
0x180024a1a  retn
0x180024a1b  lea     rcx, [rsp+118h+var_B8]; this
0x180024a20  call    ??1SQMRepairResultData@NDFSQMSession@@QEAA@XZ; NDFSQMSession::SQMRepairResultData::~SQMRepairResultData(void)
0x180024a25  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180024a29  jmp     loc_1800248F3
0x180024a2e  jmp     short loc_1800249FA
```
