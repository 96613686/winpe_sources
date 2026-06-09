# XPerfAddIn::CProcessInfoSource::ProcessEvent(XPerfCore::ICursor const &,unsigned __int64,_EVENT_TRACE const *)

- ea: `0x1800089b0`
- end: `0x180008ea5`
- name: `?ProcessEvent@CProcessInfoSource@XPerfAddIn@@AEAAJAEBUICursor@XPerfCore@@_KPEBU_EVENT_TRACE@@@Z`
- size: `1269`
- prototype: `int(XPerfAddIn::CProcessInfoSource *__hidden this, const struct XPerfCore::ICursor *, unsigned __int64, const struct _EVENT_TRACE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009de0`

## callees

- `0x1800065e4`
- `0x180008290`
- `0x180008594`
- `0x1800089b0`
- `0x180008eac`
- `0x1800091cc`
- `0x18000bbf0`
- `0x18000cc50`
- `0x180011e00`
- `0x180057836`
- `0x1800d6010`

## import_xrefs

- `msvcrt!malloc` at `0x180008c9c`
- `msvcrt!malloc` at `0x180008c9c`
- `msvcrt!_wcsicmp` at `0x180008d13`
- `msvcrt!_wcsicmp` at `0x180008d13`
- `msvcrt!free` at `0x180008e5f`
- `msvcrt!free` at `0x180008e6a`
- `msvcrt!free` at `0x180008e5f`
- `msvcrt!free` at `0x180008e6a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180008c24`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180008c24`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall XPerfAddIn::CProcessInfoSource::ProcessEvent(
        XPerfAddIn::CProcessInfoSource *this,
        const struct XPerfCore::ICursor *a2,
        __int64 a3,
        struct _EVENT_TRACE *a4)
{
  unsigned int *v8; // rdi
  unsigned int *v9; // rbx
  BOOL v10; // r12d
  unsigned int v11; // eax
  int v12; // r13d
  __int64 *v13; // rax
  __int64 *v14; // rcx
  unsigned int *v15; // r11
  unsigned int *v16; // r8
  __int64 v17; // rdx
  unsigned int *v18; // r10
  unsigned int **v19; // r14
  __int64 v20; // r15
  __int64 v21; // r15
  PSID v23; // rsi
  __int64 v24; // r8
  void *v25; // r12
  unsigned int *v26; // rcx
  __int64 v27; // rsi
  unsigned int *v28; // rax
  unsigned int *v29; // r15
  size_t v30; // rsi
  __int64 v31; // rax
  const wchar_t *v32; // rcx
  __int64 v33; // r15
  unsigned int v34; // eax
  int v35; // r12d
  unsigned int *v36[2]; // [rsp+30h] [rbp-D8h] BYREF
  void *Block; // [rsp+40h] [rbp-C8h] BYREF
  char v38; // [rsp+48h] [rbp-C0h]
  void *Src; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v41[4]; // [rsp+60h] [rbp-A8h] BYREF
  _DWORD v42[4]; // [rsp+80h] [rbp-88h] BYREF
  __int64 v43; // [rsp+90h] [rbp-78h]
  __int64 v44; // [rsp+98h] [rbp-70h]
  _OWORD v45[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v46; // [rsp+C0h] [rbp-48h]
  unsigned __int16 *v48; // [rsp+118h] [rbp+10h] BYREF
  PSID pSid; // [rsp+120h] [rbp+18h] BYREF
  struct XPerfAddIn::IProcessInfoSource::ProcessData *v50; // [rsp+128h] [rbp+20h]

  v50 = (struct XPerfAddIn::IProcessInfoSource::ProcessData *)a4;
  v8 = (unsigned int *)XPerfCore::TimeStamp::Min;
  v9 = (unsigned int *)XPerfCore::TimeStamp::Max;
  v10 = (unsigned __int64)(a3 - 3) <= 1;
  v41[0] = XPerfCore::TimeStamp::Min;
  v41[1] = XPerfCore::TimeStamp::Max;
  v44 = 0;
  std::_Tree_comp<0,std::_Tset_traits<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats,XPerfAddIn::CTraceStatsSource<XPerfAddIn::CClassicEtwEventPolicy>::lessEventStats,std::allocator<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats>,0>>::_Tree_comp<0,std::_Tset_traits<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats,XPerfAddIn::CTraceStatsSource<XPerfAddIn::CClassicEtwEventPolicy>::lessEventStats,std::allocator<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats>,0>>(v45);
  v45[1] = 0;
  v46 = 0;
  v41[2] = 0;
  v41[3] = 0;
  v42[0] = -1;
  v42[1] = -1;
  v42[2] = -1;
  v43 = 0;
  pSid = 0;
  Src = 0;
  LODWORD(v48) = 0;
  v11 = (*(__int64 (__fastcall **)(const struct XPerfCore::ICursor *))(*(_QWORD *)a2 + 80LL))(a2);
  v12 = XPerfAddIn::ParseEvent(
          (XPerfAddIn *)v41,
          (struct XPerfAddIn::IProcessInfoSource::ProcessData *)a4,
          (const struct _EVENT_TRACE *)v11,
          (unsigned int)&pSid,
          (const struct _SID **)&Src,
          (const unsigned __int16 **)&v48,
          v36[0]);
  if ( v12 < 0 )
    goto LABEL_22;
  Block = (char *)this + 40;
  (*(void (__fastcall **)(const struct XPerfCore::ICursor *, __int64 *))(*(_QWORD *)a2 + 72LL))(a2, &v40);
  v13 = *(__int64 **)(*((_QWORD *)this + 5) + 8LL);
  v14 = (__int64 *)*((_QWORD *)this + 5);
  if ( *((_BYTE *)v13 + 25) )
    goto LABEL_15;
  do
  {
    if ( *((_DWORD *)v13 + 8) <= v42[0] )
    {
      v14 = v13;
      v13 = (__int64 *)*v13;
    }
    else
    {
      v13 = (__int64 *)v13[2];
    }
  }
  while ( !*((_BYTE *)v13 + 25) );
  if ( v14 == *((__int64 **)this + 5) )
    goto LABEL_15;
  if ( v42[0] > *((_DWORD *)v14 + 8) )
    goto LABEL_15;
  v36[0] = (unsigned int *)v14[6];
  v15 = (unsigned int *)v14[5];
  v16 = v15;
  v17 = ((char *)v36[0] - (char *)v15) >> 3;
  if ( v17 <= 0 )
    goto LABEL_15;
  do
  {
    v18 = &v16[2 * ((unsigned __int64)v17 >> 1)];
    if ( v40 < **(_QWORD **)v18 )
    {
      v17 = (unsigned __int64)v17 >> 1;
    }
    else
    {
      v16 = v18 + 2;
      v17 += -1LL - ((unsigned __int64)v17 >> 1);
    }
  }
  while ( v17 > 0 );
  if ( v16 == v15 )
    goto LABEL_15;
  v19 = (unsigned int **)*((_QWORD *)v16 - 1);
  if ( (__int64)v19[1] >= v40 )
    goto LABEL_16;
  if ( !v10 )
    goto LABEL_15;
  v35 = v10 - 1;
  if ( v35 )
  {
    if ( v16 == v36[0] || v35 != 1 )
    {
LABEL_15:
      v19 = 0;
      goto LABEL_16;
    }
    v19 = *(unsigned int ***)v16;
  }
LABEL_16:
  v20 = a3 - 1;
  if ( !v20 )
  {
    (*(void (__fastcall **)(const struct XPerfCore::ICursor *, unsigned int **))(*(_QWORD *)a2 + 72LL))(a2, v36);
    v8 = v36[0];
    if ( v19 && v19[3] )
    {
      if ( *v19 != (unsigned int *)XPerfCore::TimeStamp::Min || v19[1] != (unsigned int *)XPerfCore::TimeStamp::End )
      {
        XPerfCore::ICursor::operator XPerfCore::TimeStamp const(a2, v36);
        v19[1] = v36[0];
      }
      v19 = 0;
    }
    goto LABEL_25;
  }
  v21 = v20 - 1;
  if ( !v21 )
  {
    (*(void (__fastcall **)(const struct XPerfCore::ICursor *, unsigned int **))(*(_QWORD *)a2 + 72LL))(a2, v36);
    v9 = v36[0];
    goto LABEL_19;
  }
  v33 = v21 - 1;
  if ( v33 )
  {
    if ( v33 != 1 )
    {
      v12 = 262400;
      goto LABEL_22;
    }
LABEL_19:
    if ( v19 && v19[3] )
    {
      v19[1] = v9;
LABEL_22:
      XPerfAddIn::CProcessInfoSource::CProcessData::~CProcessData((XPerfAddIn::CProcessInfoSource::CProcessData *)v41);
      return (unsigned int)v12;
    }
    goto LABEL_25;
  }
  if ( v19 && v19[3] )
  {
    if ( v19[1] == (unsigned int *)XPerfCore::TimeStamp::Max )
      goto LABEL_22;
    v19 = 0;
    (*(void (__fastcall **)(const struct XPerfCore::ICursor *, unsigned int **))(*(_QWORD *)a2 + 72LL))(a2, v36);
    v8 = v36[0];
  }
  v9 = (unsigned int *)XPerfCore::TimeStamp::End;
LABEL_25:
  if ( v19 )
  {
    v34 = (*(__int64 (__fastcall **)(const struct XPerfCore::ICursor *))(*(_QWORD *)a2 + 80LL))(a2);
    v12 = XPerfAddIn::ParseEvent(
            (XPerfAddIn *)v19,
            v50,
            (const struct _EVENT_TRACE *)v34,
            (unsigned int)&pSid,
            0,
            0,
            v36[0]);
    if ( v12 < 0 )
      goto LABEL_22;
  }
  else
  {
    v19 = (unsigned int **)XPerfAddIn::KeyedTimelines<unsigned long,XPerfAddIn::CProcessInfoSource::CProcessData,XPerfAddIn::IProcessInfoSource::ProcessData>::Add(
                             Block,
                             v42,
                             v41);
  }
  v23 = pSid;
  if ( pSid )
  {
    if ( IsValidSid(pSid) )
    {
      v38 = 0;
      Block = v23;
      std::_Tree<std::_Tset_traits<XPerfAddIn::CSidBlob,std::less<XPerfAddIn::CSidBlob>,std::allocator<XPerfAddIn::CSidBlob>,0>>::_Insert_nohint<XPerfAddIn::CSidBlob,std::_Nil>(
        (__int64 **)this + 20,
        (__int64)v36,
        v24,
        &Block);
      v19[6] = (unsigned int *)*((_QWORD *)v36[0] + 4);
      if ( v38 )
      {
        if ( Block )
          free(Block);
      }
    }
  }
  v25 = Src;
  if ( !Src )
  {
LABEL_35:
    v31 = std::map<unsigned __int64,XPerfAddIn::Timeline,std::greater<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,XPerfAddIn::Timeline>>>::operator[](
            (char *)this + 120,
            v19 + 2);
    v48 = (unsigned __int16 *)v19;
    std::vector<XPerfAddIn::Temporal *>::push_back(v31, &v48);
    *v19 = v8;
    v19[1] = v9;
    v32 = (const wchar_t *)v19[3];
    if ( v32 )
    {
      if ( !_wcsicmp(v32, L"System") )
        *((_QWORD *)this + 22) = v19;
    }
    goto LABEL_22;
  }
  v26 = v19[7];
  if ( v26 )
  {
    free(v26);
    v19[7] = 0;
  }
  v27 = (unsigned int)v48;
  v28 = (unsigned int *)malloc(2LL * (unsigned int)((_DWORD)v48 + 1));
  v29 = v28;
  if ( v28 )
  {
    v30 = 2 * v27;
    memcpy_0(v28, v25, v30);
    *(_WORD *)((char *)v29 + v30) = 0;
    v19[7] = v29;
    goto LABEL_35;
  }
  XPerfAddIn::CProcessInfoSource::CProcessData::~CProcessData((XPerfAddIn::CProcessInfoSource::CProcessData *)v41);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800089b0  mov     r11, rsp
0x1800089b3  mov     [r11+20h], r9
0x1800089b7  mov     [r11+8], rcx
0x1800089bb  push    rbx
0x1800089bc  push    rsi
0x1800089bd  push    rdi
0x1800089be  push    r12
0x1800089c0  push    r13
0x1800089c2  push    r14
0x1800089c4  push    r15
0x1800089c6  sub     rsp, 0D0h
0x1800089cd  mov     r13, r9
0x1800089d0  mov     r15, r8
0x1800089d3  mov     rsi, rdx
0x1800089d6  mov     r14, rcx
0x1800089d9  mov     rdi, cs:?Min@TimeStamp@XPerfCore@@2V12@B; XPerfCore::TimeStamp const XPerfCore::TimeStamp::Min
0x1800089e0  mov     rbx, cs:?Max@TimeStamp@XPerfCore@@2V12@B; XPerfCore::TimeStamp const XPerfCore::TimeStamp::Max
0x1800089e7  lea     rax, [r8-3]
0x1800089eb  xor     r12d, r12d
0x1800089ee  cmp     rax, 1
0x1800089f2  setbe   r12b
0x1800089f6  mov     [rsp+108h+var_A8], rdi
0x1800089fb  mov     [rsp+108h+var_A0], rbx
0x180008a00  mov     qword ptr [r11-70h], 0
0x180008a08  lea     rcx, [r11-68h]
0x180008a0c  call    ??0?$_Tree_comp@$0A@V?$_Tset_traits@UClassicEventStats@ITraceStatsInfoSource@XPerfAddIn@@UlessEventStats@?$CTraceStatsSource@UCClassicEtwEventPolicy@XPerfAddIn@@@3@V?$allocator@UClassicEventStats@ITraceStatsInfoSource@XPerfAddIn@@@std@@$0A@@std@@@std@@QEAA@AEBUlessEventStats@?$CTraceStatsSource@UCClassicEtwEventPolicy@XPerfAddIn@@@XPerfAddIn@@AEBV?$allocator@UClassicEventStats@ITraceStatsInfoSource@XPerfAddIn@@@1@@Z; std::_Tree_comp<0,std::_Tset_traits<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats,XPerfAddIn::CTraceStatsSource<XPerfAddIn::CClassicEtwEventPolicy>::lessEventStats,std::allocator<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats>,0>>::_Tree_comp<0,std::_Tset_traits<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats,XPerfAddIn::CTraceStatsSource<XPerfAddIn::CClassicEtwEventPolicy>::lessEventStats,std::allocator<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats>,0>>(XPerfAddIn::CTraceStatsSource<XPerfAddIn::CClassicEtwEventPolicy>::lessEventStats const &,std::allocator<XPerfAddIn::ITraceStatsInfoSource::ClassicEventStats> const &)
0x180008a11  xorps   xmm0, xmm0
0x180008a14  movdqa  [rsp+108h+var_58], xmm0
0x180008a1d  xor     ecx, ecx
0x180008a1f  mov     [rsp+108h+var_48], rcx
0x180008a27  mov     [rsp+108h+var_98], rcx
0x180008a2c  mov     [rsp+108h+var_90], rcx
0x180008a31  or      eax, 0FFFFFFFFh
0x180008a34  mov     [rsp+108h+var_88], eax
0x180008a3b  mov     [rsp+108h+var_84], eax
0x180008a42  mov     [rsp+108h+var_80], eax
0x180008a49  mov     [rsp+108h+var_78], rcx
0x180008a51  mov     [rsp+108h+pSid], rcx
0x180008a59  mov     [rsp+108h+Src], rcx
0x180008a5e  mov     dword ptr [rsp+108h+arg_8], ecx
0x180008a65  mov     rax, [rsi]
0x180008a68  mov     rcx, rsi
0x180008a6b  mov     rax, [rax+50h]
0x180008a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a74  mov     r8d, eax; struct _EVENT_TRACE *
0x180008a77  lea     rax, [rsp+108h+arg_8]
0x180008a7f  mov     [rsp+108h+var_E0], rax; unsigned __int16 **
0x180008a84  lea     rax, [rsp+108h+Src]
0x180008a89  mov     [rsp+108h+var_E8], rax; struct _SID **
0x180008a8e  lea     r9, [rsp+108h+pSid]; unsigned int
0x180008a96  mov     rdx, r13; struct XPerfAddIn::IProcessInfoSource::ProcessData *
0x180008a99  lea     rcx, [rsp+108h+var_A8]; this
0x180008a9e  call    ?ParseEvent@XPerfAddIn@@YAJAEAUProcessData@IProcessInfoSource@1@PEBU_EVENT_TRACE@@KPEAPEBU_SID@@PEAPEBGPEAK@Z; XPerfAddIn::ParseEvent(XPerfAddIn::IProcessInfoSource::ProcessData &,_EVENT_TRACE const *,ulong,_SID const * *,ushort const * *,ulong *)
0x180008aa3  mov     r13d, eax
0x180008aa6  test    eax, eax
0x180008aa8  js      loc_180008BA4
0x180008aae  add     r14, 28h ; '('
0x180008ab2  mov     [rsp+108h+Block], r14
0x180008ab7  mov     rax, [rsi]
0x180008aba  lea     rdx, [rsp+108h+var_B0]
0x180008abf  mov     rcx, rsi
0x180008ac2  mov     rax, [rax+48h]
0x180008ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008acb  mov     r8, [r14]
0x180008ace  mov     rax, [r8+8]
0x180008ad2  mov     rcx, r8
0x180008ad5  cmp     byte ptr [rax+19h], 0
0x180008ad9  jnz     loc_180008B68
0x180008adf  mov     edx, [rsp+108h+var_88]
0x180008ae6  cmp     [rax+20h], edx
0x180008ae9  jbe     loc_180008BC4
0x180008aef  mov     rax, [rax+10h]
0x180008af3  cmp     byte ptr [rax+19h], 0
0x180008af7  jz      short loc_180008AE6
0x180008af9  cmp     rcx, r8
0x180008afc  jz      short loc_180008B68
0x180008afe  cmp     edx, [rcx+20h]
0x180008b01  ja      short loc_180008B68
0x180008b03  mov     rax, [rcx+30h]
0x180008b07  mov     [rsp+108h+var_D8], rax; unsigned int *
0x180008b0c  mov     r11, [rcx+28h]
0x180008b10  mov     r8, r11
0x180008b13  mov     rdx, rax
0x180008b16  sub     rdx, r11
0x180008b19  sar     rdx, 3
0x180008b1d  test    rdx, rdx
0x180008b20  jle     short loc_180008B68
0x180008b22  mov     rax, [rsp+108h+var_B0]
0x180008b27  mov     r9, rdx
0x180008b2a  shr     r9, 1
0x180008b2d  lea     r10, [r8+r9*8]
0x180008b31  mov     rcx, [r10]
0x180008b34  cmp     rax, [rcx]
0x180008b37  jl      loc_180008D7B
0x180008b3d  lea     r8, [r10+8]
0x180008b41  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008b45  sub     rcx, r9
0x180008b48  add     rdx, rcx
0x180008b4b  test    rdx, rdx
0x180008b4e  jg      short loc_180008B27
0x180008b50  cmp     r8, r11
0x180008b53  jz      short loc_180008B68
0x180008b55  mov     r14, [r8-8]
0x180008b59  cmp     [r14+8], rax
0x180008b5d  jge     short loc_180008B6B
0x180008b5f  test    r12d, r12d
0x180008b62  jnz     loc_180008DCF
0x180008b68  xor     r14d, r14d
0x180008b6b  sub     r15, 1
0x180008b6f  jz      short loc_180008BCF
0x180008b71  sub     r15, 1
0x180008b75  jnz     loc_180008D2D
0x180008b7b  mov     rax, [rsi]
0x180008b7e  lea     rdx, [rsp+108h+var_D8]
0x180008b83  mov     rcx, rsi
0x180008b86  mov     rax, [rax+48h]
0x180008b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b8f  mov     rbx, [rsp+108h+var_D8]
0x180008b94  test    r14, r14
0x180008b97  jz      short loc_180008BF1
0x180008b99  cmp     qword ptr [r14+18h], 0
0x180008b9e  jz      short loc_180008BF1
0x180008ba0  mov     [r14+8], rbx
0x180008ba4  lea     rcx, [rsp+108h+var_A8]; this
0x180008ba9  call    ??1CProcessData@CProcessInfoSource@XPerfAddIn@@QEAA@XZ; XPerfAddIn::CProcessInfoSource::CProcessData::~CProcessData(void)
0x180008bae  mov     eax, r13d
0x180008bb1  add     rsp, 0D0h
0x180008bb8  pop     r15
0x180008bba  pop     r14
0x180008bbc  pop     r13
0x180008bbe  pop     r12
0x180008bc0  pop     rdi
0x180008bc1  pop     rsi
0x180008bc2  pop     rbx
0x180008bc3  retn
0x180008bc4  mov     rcx, rax
0x180008bc7  mov     rax, [rax]
0x180008bca  jmp     loc_180008AF3
0x180008bcf  mov     rax, [rsi]
0x180008bd2  lea     rdx, [rsp+108h+var_D8]
0x180008bd7  mov     rcx, rsi
0x180008bda  mov     rax, [rax+48h]
0x180008bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008be3  mov     rdi, [rsp+108h+var_D8]
0x180008be8  test    r14, r14
0x180008beb  jnz     loc_180008E2C
0x180008bf1  test    r14, r14
0x180008bf4  jnz     loc_180008D83
0x180008bfa  lea     r8, [rsp+108h+var_A8]
0x180008bff  lea     rdx, [rsp+108h+var_88]
0x180008c07  mov     rcx, [rsp+108h+Block]
0x180008c0c  call    ?Add@?$KeyedTimelines@KUCProcessData@CProcessInfoSource@XPerfAddIn@@UProcessData@IProcessInfoSource@3@@XPerfAddIn@@QEAAPEAUCProcessData@CProcessInfoSource@2@AEBKAEBU342@@Z; XPerfAddIn::KeyedTimelines<ulong,XPerfAddIn::CProcessInfoSource::CProcessData,XPerfAddIn::IProcessInfoSource::ProcessData>::Add(ulong const &,XPerfAddIn::CProcessInfoSource::CProcessData const &)
0x180008c11  mov     r14, rax
0x180008c14  mov     rsi, [rsp+108h+pSid]
0x180008c1c  test    rsi, rsi
0x180008c1f  jz      short loc_180008C78
0x180008c21  mov     rcx, rsi; pSid
0x180008c24  call    cs:__imp_IsValidSid
0x180008c2a  test    eax, eax
0x180008c2c  jz      short loc_180008C78
0x180008c2e  mov     [rsp+108h+var_C0], 0
0x180008c33  mov     [rsp+108h+Block], rsi
0x180008c38  mov     al, cs:byte_180101E6F
0x180008c3e  mov     rcx, [rsp+108h+arg_0]
0x180008c46  add     rcx, 0A0h
0x180008c4d  mov     byte ptr [rsp+108h+var_E8], al
0x180008c51  lea     r9, [rsp+108h+Block]
0x180008c56  lea     rdx, [rsp+108h+var_D8]
0x180008c5b  call    ??$_Insert_nohint@VCSidBlob@XPerfAddIn@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@VCSidBlob@XPerfAddIn@@U?$less@VCSidBlob@XPerfAddIn@@@std@@V?$allocator@VCSidBlob@XPerfAddIn@@@4@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VCSidBlob@XPerfAddIn@@@std@@@std@@@std@@_N@1@_N$$QEAVCSidBlob@XPerfAddIn@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<XPerfAddIn::CSidBlob,std::less<XPerfAddIn::CSidBlob>,std::allocator<XPerfAddIn::CSidBlob>,0>>::_Insert_nohint<XPerfAddIn::CSidBlob,std::_Nil>(bool,XPerfAddIn::CSidBlob &&,std::_Nil)
0x180008c60  mov     rax, [rsp+108h+var_D8]
0x180008c65  mov     rcx, [rax+20h]
0x180008c69  mov     [r14+30h], rcx
0x180008c6d  cmp     [rsp+108h+var_C0], 0
0x180008c72  jnz     loc_180008E51
0x180008c78  mov     r12, [rsp+108h+Src]
0x180008c7d  test    r12, r12
0x180008c80  jz      short loc_180008CCA
0x180008c82  mov     rcx, [r14+38h]; Block
0x180008c86  test    rcx, rcx
0x180008c89  jnz     loc_180008E6A
0x180008c8f  mov     esi, dword ptr [rsp+108h+arg_8]
0x180008c96  lea     ecx, [rsi+1]
0x180008c99  add     rcx, rcx; Size
0x180008c9c  call    cs:__imp_malloc
0x180008ca2  mov     r15, rax
0x180008ca5  test    rax, rax
0x180008ca8  jz      loc_180008E7D
0x180008cae  add     rsi, rsi
0x180008cb1  mov     r8, rsi; Size
0x180008cb4  mov     rdx, r12; Src
0x180008cb7  mov     rcx, rax; void *
0x180008cba  call    memcpy_0
0x180008cbf  xor     eax, eax
0x180008cc1  mov     [rsi+r15], ax
0x180008cc6  mov     [r14+38h], r15
0x180008cca  lea     rdx, [r14+10h]
0x180008cce  mov     rsi, [rsp+108h+arg_0]
0x180008cd6  lea     rcx, [rsi+78h]
0x180008cda  call    ??A?$map@_KVTimeline@XPerfAddIn@@U?$greater@_K@std@@V?$allocator@U?$pair@$$CB_KVTimeline@XPerfAddIn@@@std@@@4@@std@@QEAAAEAVTimeline@XPerfAddIn@@AEB_K@Z; std::map<unsigned __int64,XPerfAddIn::Timeline,std::greater<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,XPerfAddIn::Timeline>>>::operator[](unsigned __int64 const &)
0x180008cdf  mov     [rsp+108h+arg_8], r14
0x180008ce7  lea     rdx, [rsp+108h+arg_8]
0x180008cef  mov     rcx, rax
0x180008cf2  call    ?push_back@?$vector@PEAUTemporal@XPerfAddIn@@V?$allocator@PEAUTemporal@XPerfAddIn@@@std@@@std@@QEAAX$$QEAPEAUTemporal@XPerfAddIn@@@Z; std::vector<XPerfAddIn::Temporal *>::push_back(XPerfAddIn::Temporal * &&)
0x180008cf7  nop
0x180008cf8  mov     [r14], rdi
0x180008cfb  mov     [r14+8], rbx
0x180008cff  mov     rcx, [r14+18h]; String1
0x180008d03  test    rcx, rcx
0x180008d06  jz      loc_180008BA4
0x180008d0c  lea     rdx, aSystem; "System"
0x180008d13  call    cs:__imp__wcsicmp
0x180008d19  test    eax, eax
0x180008d1b  jnz     loc_180008BA4
0x180008d21  mov     [rsi+0B0h], r14
0x180008d28  jmp     loc_180008BA4
0x180008d2d  sub     r15, 1
0x180008d31  jnz     loc_180008E17
0x180008d37  test    r14, r14
0x180008d3a  jz      short loc_180008D6F
0x180008d3c  cmp     [r14+18h], r15
0x180008d40  jz      short loc_180008D6F
0x180008d42  mov     rax, cs:?Max@TimeStamp@XPerfCore@@2V12@B; XPerfCore::TimeStamp const XPerfCore::TimeStamp::Max
0x180008d49  cmp     [r14+8], rax
0x180008d4d  jz      loc_180008BA4
0x180008d53  xor     r14d, r14d
0x180008d56  mov     rax, [rsi]
0x180008d59  lea     rdx, [rsp+108h+var_D8]
0x180008d5e  mov     rcx, rsi
0x180008d61  mov     rax, [rax+48h]
0x180008d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d6a  mov     rdi, [rsp+108h+var_D8]
0x180008d6f  mov     rbx, cs:?End@TimeStamp@XPerfCore@@2V12@B; XPerfCore::TimeStamp const XPerfCore::TimeStamp::End
0x180008d76  jmp     loc_180008BF1
0x180008d7b  mov     rdx, r9
0x180008d7e  jmp     loc_180008B4B
0x180008d83  mov     rax, [rsi]
0x180008d86  mov     rcx, rsi
0x180008d89  mov     rax, [rax+50h]
0x180008d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d92  mov     [rsp+108h+var_E0], 0; unsigned __int16 **
0x180008d9b  mov     [rsp+108h+var_E8], 0; struct _SID **
0x180008da4  lea     r9, [rsp+108h+pSid]; unsigned int
0x180008dac  mov     r8d, eax; struct _EVENT_TRACE *
0x180008daf  mov     rdx, [rsp+108h+arg_18]; struct XPerfAddIn::IProcessInfoSource::ProcessData *
0x180008db7  mov     rcx, r14; this
0x180008dba  call    ?ParseEvent@XPerfAddIn@@YAJAEAUProcessData@IProcessInfoSource@1@PEBU_EVENT_TRACE@@KPEAPEBU_SID@@PEAPEBGPEAK@Z; XPerfAddIn::ParseEvent(XPerfAddIn::IProcessInfoSource::ProcessData &,_EVENT_TRACE const *,ulong,_SID const * *,ushort const * *,ulong *)
0x180008dbf  mov     r13d, eax
0x180008dc2  test    eax, eax
0x180008dc4  jns     loc_180008C14
0x180008dca  jmp     loc_180008BA4
0x180008dcf  sub     r12d, 1
0x180008dd3  jz      loc_180008B6B
0x180008dd9  cmp     r8, [rsp+108h+var_D8]
0x180008dde  jz      loc_180008B68
0x180008de4  cmp     r12d, 1
0x180008de8  jnz     loc_180008B68
0x180008dee  mov     r14, [r8]
0x180008df1  jmp     loc_180008B6B
0x180008df6  mov     rax, cs:?Min@TimeStamp@XPerfCore@@2V12@B; XPerfCore::TimeStamp const XPerfCore::TimeStamp::Min
0x180008dfd  cmp     [r14], rax
0x180008e00  jnz     short loc_180008E39
0x180008e02  mov     rax, cs:?End@TimeStamp@XPerfCore@@2V12@B; XPerfCore::TimeStamp const XPerfCore::TimeStamp::End
0x180008e09  cmp     [r14+8], rax
0x180008e0d  jnz     short loc_180008E39
0x180008e0f  xor     r14d, r14d
0x180008e12  jmp     loc_180008BF1
0x180008e17  cmp     r15, 1
0x180008e1b  jz      loc_180008B94
0x180008e21  mov     r13d, 40100h
0x180008e27  jmp     loc_180008BA4
0x180008e2c  cmp     qword ptr [r14+18h], 0
0x180008e31  jz      loc_180008BF1
0x180008e37  jmp     short loc_180008DF6
0x180008e39  lea     rdx, [rsp+108h+var_D8]
0x180008e3e  mov     rcx, rsi
0x180008e41  call    ??BICursor@XPerfCore@@QEBA?BVTimeStamp@1@XZ; XPerfCore::ICursor::operator XPerfCore::TimeStamp const(void)
0x180008e46  mov     rax, [rsp+108h+var_D8]
0x180008e4b  mov     [r14+8], rax
0x180008e4f  jmp     short loc_180008E0F
0x180008e51  mov     rcx, [rsp+108h+Block]; Block
0x180008e56  test    rcx, rcx
0x180008e59  jz      loc_180008C78
0x180008e5f  call    cs:__imp_free
0x180008e65  jmp     loc_180008C78
0x180008e6a  call    cs:__imp_free
0x180008e70  mov     qword ptr [r14+38h], 0
0x180008e78  jmp     loc_180008C8F
0x180008e7d  lea     rcx, [rsp+108h+var_A8]; this
0x180008e82  call    ??1CProcessData@CProcessInfoSource@XPerfAddIn@@QEAA@XZ; XPerfAddIn::CProcessInfoSource::CProcessData::~CProcessData(void)
0x180008e87  mov     eax, 8007000Eh
0x180008e8c  jmp     loc_180008BB1
0x180008e91  lea     rcx, [rsp+108h+var_A8]; this
0x180008e96  call    ??1CProcessData@CProcessInfoSource@XPerfAddIn@@QEAA@XZ; XPerfAddIn::CProcessInfoSource::CProcessData::~CProcessData(void)
0x180008e9b  mov     eax, 8007000Eh
0x180008ea0  jmp     loc_180008BB1
```
