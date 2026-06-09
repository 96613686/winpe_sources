# EapLm::Peer::LegacyEapMethodConfig::GetMethodProperties(uint,uint,void *,ConstBuffer const &,ConstBuffer const &,_EAP_METHOD_PROPERTY_ARRAY *)

- ea: `0x180019320`
- end: `0x180019691`
- name: `?GetMethodProperties@LegacyEapMethodConfig@Peer@EapLm@@UEAAXIIPEAXAEBUConstBuffer@@1PEAU_EAP_METHOD_PROPERTY_ARRAY@@@Z`
- size: `881`
- prototype: `void __fastcall(EapLm::Peer::LegacyEapMethodConfig *__hidden this, unsigned int, unsigned int, void *, const struct ConstBuffer *, const struct ConstBuffer *, struct _EAP_METHOD_PROPERTY_ARRAY *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180005894`
- `0x18000bf94`
- `0x18000ce00`
- `0x18000ec84`
- `0x18001549c`
- `0x180016400`
- `0x180017e54`
- `0x180019320`
- `0x18001b154`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001938d`
- `ntdll!EtwEventEnabled` at `0x180019576`
- `ntdll!EtwEventEnabled` at `0x18001938d`
- `ntdll!EtwEventEnabled` at `0x180019576`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall EapLm::Peer::LegacyEapMethodConfig::GetMethodProperties(
        EapLm::Peer::LegacyEapMethodConfig *this,
        unsigned int a2,
        unsigned int a3,
        void *a4,
        const struct ConstBuffer *a5,
        const struct ConstBuffer *a6,
        struct _EAP_METHOD_PROPERTY_ARRAY *a7)
{
  __int64 v10; // r15
  void (*v11)(void); // r15
  __int64 v12; // rsi
  int v13; // ebx
  __int64 v14; // rdi
  int v15; // eax
  unsigned int v16; // eax
  __int64 v17; // r8
  struct _EAP_METHOD_PROPERTY_ARRAY v18; // xmm1
  unsigned int v19; // edx
  __int64 v20; // rcx
  unsigned int v21; // ebx
  _BYTE v22[20]; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+68h] [rbp-98h]
  __int128 v24; // [rsp+70h] [rbp-90h] BYREF
  const struct ConstBuffer *v25; // [rsp+80h] [rbp-80h]
  void *v26; // [rsp+88h] [rbp-78h]
  struct _EAP_METHOD_PROPERTY_ARRAY *v27; // [rsp+90h] [rbp-70h]
  char v28[2048]; // [rsp+A0h] [rbp-60h] BYREF

  v26 = a4;
  v25 = a5;
  v27 = a7;
  v24 = 0;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v28, 0x800u, "RasEapGetMethodProperties Entry:\n version(%d), flags(%d)", a2, a3) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v28);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, a2, a3);
  if ( EapLm::DelayLoadModule::LoadIfNeeded(*((EapLm::DelayLoadModule **)this + 26), 1) != 1
    || (v10 = *((_QWORD *)this + 26), (*(_QWORD *)v22 = *(_QWORD *)(v10 + 216)) == 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids,
        *((unsigned __int8 *)this + 16));
    v22[8] = *((_BYTE *)this + 16);
    *(_DWORD *)&v22[12] = *((_DWORD *)this + 5);
    *(_DWORD *)&v22[16] = *((_DWORD *)this + 6);
    if ( v22[8] != 0xFE )
      *(_QWORD *)&v22[12] = 0;
    *(_QWORD *)v22 = &EapHost::EapMethodType::`vftable';
    v23 = *((_DWORD *)this + 7);
    EapHost::EapException::Throw(0x80420020, (const struct EapHost::EapMethodType *)v22, 0x80420020);
  }
  v11 = *(void (**)(void))(v10 + 232);
  v12 = *(_QWORD *)a6;
  v13 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(*((_QWORD *)a6 + 1));
  v14 = *(_QWORD *)a5;
  v15 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(*((_QWORD *)v25 + 1));
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, void *, int, __int64, int, __int64, __int128 *))v22)(
          a2,
          a3,
          *((unsigned __int8 *)this + 16),
          v26,
          v15,
          v14,
          v13,
          v12,
          &v24);
  if ( v16 )
  {
    v22[8] = *((_BYTE *)this + 16);
    *(_DWORD *)&v22[12] = *((_DWORD *)this + 5);
    *(_DWORD *)&v22[16] = *((_DWORD *)this + 6);
    if ( v22[8] != 0xFE )
      *(_QWORD *)&v22[12] = 0;
    *(_QWORD *)v22 = &EapHost::EapMethodType::`vftable';
    v23 = *((_DWORD *)this + 7);
    EapHost::EapException::Throw(v16, (const struct EapHost::EapMethodType *)v22, v16);
  }
  *(_OWORD *)v22 = 0;
  crt_ref<_EAP_METHOD_PROPERTY_ARRAY>::Assign(v22, &v24, v17, 0);
  v18 = *(struct _EAP_METHOD_PROPERTY_ARRAY *)v22;
  *(_OWORD *)v22 = 0;
  *v27 = v18;
  if ( v11 )
  {
    v19 = v24;
    if ( (_DWORD)v24 )
    {
      v20 = *((_QWORD *)&v24 + 1);
      if ( *((_QWORD *)&v24 + 1) )
      {
        v21 = 0;
        do
        {
          if ( *(_DWORD *)(v20 + 24LL * v21 + 4) == 2 )
          {
            ((void (__fastcall *)(_QWORD))v11)(*(_QWORD *)(v20 + 24LL * v21 + 16));
            v20 = *((_QWORD *)&v24 + 1);
            v19 = v24;
          }
          ++v21;
        }
        while ( v21 < v19 );
        v11();
      }
    }
  }
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v28, 0x800u, "RasEapGetMethodProperties Exit:\n properties") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v28);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids);
  Free<HeapAllocator>(v22);
}

```

## disassembly

```asm
0x180019320  push    rbp
0x180019322  push    rbx
0x180019323  push    rsi
0x180019324  push    rdi
0x180019325  push    r12
0x180019327  push    r13
0x180019329  push    r14
0x18001932b  push    r15
0x18001932d  lea     rbp, [rsp-7B8h]
0x180019335  sub     rsp, 8B8h
0x18001933c  mov     rax, cs:__security_cookie
0x180019343  xor     rax, rsp
0x180019346  mov     [rbp+7F0h+var_50], rax
0x18001934d  mov     [rbp+7F0h+var_868], r9
0x180019351  mov     r13d, r8d
0x180019354  mov     r12d, edx
0x180019357  mov     r14, rcx
0x18001935a  mov     rdi, [rbp+7F0h+arg_20]
0x180019361  mov     [rbp+7F0h+var_870], rdi
0x180019365  mov     rbx, [rbp+7F0h+arg_28]
0x18001936c  mov     rax, [rbp+7F0h+arg_30]
0x180019373  mov     [rbp+7F0h+var_860], rax
0x180019377  xorps   xmm0, xmm0
0x18001937a  movups  [rsp+8F0h+var_880], xmm0
0x18001937f  lea     rdx, DebugInfoEvent
0x180019386  mov     rcx, cs:eaphost_Context
0x18001938d  call    cs:__imp_EtwEventEnabled
0x180019393  xor     esi, esi
0x180019395  test    al, al
0x180019397  jz      short loc_1800193DA
0x180019399  mov     [rsp+8F0h+var_8D0], r13d
0x18001939e  mov     r9d, r12d
0x1800193a1  lea     r8, aRaseapgetmetho_1; "RasEapGetMethodProperties Entry:\n vers"...
0x1800193a8  mov     edx, 800h; unsigned __int64
0x1800193ad  lea     rcx, [rbp+7F0h+var_850]; char *
0x1800193b1  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800193b6  test    eax, eax
0x1800193b8  js      short loc_1800193DA
0x1800193ba  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x1800193c1  jge     short loc_1800193DA
0x1800193c3  lea     r8, [rbp+7F0h+var_850]
0x1800193c7  lea     rdx, DebugInfoEvent
0x1800193ce  lea     rcx, eaphost_Context
0x1800193d5  call    McTemplateU0s_EtwEventWriteTransfer
0x1800193da  lea     rax, WPP_GLOBAL_Control
0x1800193e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193e8  cmp     rcx, rax
0x1800193eb  jz      short loc_180019410
0x1800193ed  test    byte ptr [rcx+1Ch], 4
0x1800193f1  jz      short loc_180019410
0x1800193f3  mov     edx, 36h ; '6'
0x1800193f8  mov     [rsp+8F0h+var_8D0], r13d
0x1800193fd  mov     r9d, r12d
0x180019400  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x180019407  mov     rcx, [rcx+10h]
0x18001940b  call    WPP_SF_dd
0x180019410  mov     dl, 1; bool
0x180019412  mov     rcx, [r14+0D0h]; this
0x180019419  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001941e  cmp     al, 1
0x180019420  jnz     loc_180019615
0x180019426  mov     r15, [r14+0D0h]
0x18001942d  mov     rax, [r15+0D8h]
0x180019434  mov     qword ptr [rsp+8F0h+var_8A0], rax
0x180019439  test    rax, rax
0x18001943c  jz      loc_180019615
0x180019442  mov     r15, [r15+0E8h]
0x180019449  mov     rsi, [rbx]
0x18001944c  mov     rcx, [rbx+8]
0x180019450  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180019455  mov     ebx, eax
0x180019457  mov     rdi, [rdi]
0x18001945a  mov     rcx, [rbp+7F0h+var_870]
0x18001945e  mov     rcx, [rcx+8]
0x180019462  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180019467  movzx   r8d, byte ptr [r14+10h]
0x18001946c  lea     rcx, [rsp+8F0h+var_880]
0x180019471  mov     [rsp+8F0h+var_8B0], rcx
0x180019476  mov     [rsp+8F0h+var_8B8], rsi
0x18001947b  mov     [rsp+8F0h+var_8C0], ebx
0x18001947f  mov     [rsp+8F0h+var_8C8], rdi
0x180019484  mov     [rsp+8F0h+var_8D0], eax
0x180019488  mov     r9, [rbp+7F0h+var_868]
0x18001948c  mov     edx, r13d
0x18001948f  mov     ecx, r12d
0x180019492  mov     rax, qword ptr [rsp+8F0h+var_8A0]
0x180019497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001949c  mov     r9d, eax
0x18001949f  xor     edi, edi
0x1800194a1  test    eax, eax
0x1800194a3  jz      short loc_1800194EC
0x1800194a5  mov     dl, [r14+10h]
0x1800194a9  mov     byte ptr [rsp+8F0h+var_8A0+8], dl
0x1800194ad  mov     ecx, [r14+14h]
0x1800194b1  mov     dword ptr [rsp+8F0h+var_8A0+0Ch], ecx
0x1800194b5  mov     ecx, [r14+18h]
0x1800194b9  mov     [rsp+8F0h+var_890], ecx
0x1800194bd  cmp     dl, 0FEh
0x1800194c0  jz      short loc_1800194C7
0x1800194c2  mov     qword ptr [rsp+8F0h+var_8A0+0Ch], rdi
0x1800194c7  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x1800194ce  mov     qword ptr [rsp+8F0h+var_8A0], rax
0x1800194d3  mov     eax, [r14+1Ch]
0x1800194d7  mov     [rsp+8F0h+var_888], eax
0x1800194db  mov     r8d, r9d; unsigned int
0x1800194de  lea     rdx, [rsp+8F0h+var_8A0]; struct EapHost::EapMethodType *
0x1800194e3  mov     ecx, r9d; unsigned int
0x1800194e6  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x1800194ec  xorps   xmm0, xmm0
0x1800194ef  movups  [rsp+8F0h+var_8A0], xmm0
0x1800194f4  lea     rdx, [rsp+8F0h+var_880]
0x1800194f9  lea     rcx, [rsp+8F0h+var_8A0]
0x1800194fe  call    ?Assign@?$crt_ref@U_EAP_METHOD_PROPERTY_ARRAY@@@@QEAAXAEBU_EAP_METHOD_PROPERTY_ARRAY@@@Z; crt_ref<_EAP_METHOD_PROPERTY_ARRAY>::Assign(_EAP_METHOD_PROPERTY_ARRAY const &)
0x180019503  nop
0x180019504  movaps  xmm1, [rsp+8F0h+var_8A0]
0x180019509  xorps   xmm0, xmm0
0x18001950c  movups  [rsp+8F0h+var_8A0], xmm0
0x180019511  mov     rax, [rbp+7F0h+var_860]
0x180019515  movdqu  xmmword ptr [rax], xmm1
0x180019519  test    r15, r15
0x18001951c  jz      short loc_180019568
0x18001951e  mov     edx, dword ptr [rsp+8F0h+var_880]
0x180019522  test    edx, edx
0x180019524  jz      short loc_180019568
0x180019526  mov     rcx, qword ptr [rsp+8F0h+var_880+8]
0x18001952b  test    rcx, rcx
0x18001952e  jz      short loc_180019568
0x180019530  mov     ebx, edi
0x180019532  test    edx, edx
0x180019534  jz      short loc_180019560
0x180019536  mov     eax, ebx
0x180019538  lea     r8, [rax+rax*2]
0x18001953c  cmp     dword ptr [rcx+r8*8+4], 2
0x180019542  jnz     short loc_18001955A
0x180019544  mov     rcx, [rcx+r8*8+10h]
0x180019549  mov     rax, r15
0x18001954c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019551  mov     rcx, qword ptr [rsp+8F0h+var_880+8]
0x180019556  mov     edx, dword ptr [rsp+8F0h+var_880]
0x18001955a  inc     ebx
0x18001955c  cmp     ebx, edx
0x18001955e  jb      short loc_180019536
0x180019560  mov     rax, r15
0x180019563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019568  lea     rdx, DebugInfoEvent
0x18001956f  mov     rcx, cs:eaphost_Context
0x180019576  call    cs:__imp_EtwEventEnabled
0x18001957c  test    al, al
0x18001957e  jz      short loc_1800195B9
0x180019580  lea     r8, aRaseapgetmetho_0; "RasEapGetMethodProperties Exit:\n prope"...
0x180019587  mov     edx, 800h; unsigned __int64
0x18001958c  lea     rcx, [rbp+7F0h+var_850]; char *
0x180019590  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180019595  test    eax, eax
0x180019597  js      short loc_1800195B9
0x180019599  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x1800195a0  jge     short loc_1800195B9
0x1800195a2  lea     r8, [rbp+7F0h+var_850]
0x1800195a6  lea     rdx, DebugInfoEvent
0x1800195ad  lea     rcx, eaphost_Context
0x1800195b4  call    McTemplateU0s_EtwEventWriteTransfer
0x1800195b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195c0  lea     rax, WPP_GLOBAL_Control
0x1800195c7  cmp     rcx, rax
0x1800195ca  jz      short loc_1800195E8
0x1800195cc  test    byte ptr [rcx+1Ch], 4
0x1800195d0  jz      short loc_1800195E8
0x1800195d2  mov     edx, 38h ; '8'
0x1800195d7  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x1800195de  mov     rcx, [rcx+10h]
0x1800195e2  call    WPP_SF_
0x1800195e7  nop
0x1800195e8  lea     rcx, [rsp+8F0h+var_8A0]
0x1800195ed  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_PROPERTY_ARRAY@@@Z; Free<HeapAllocator>(_EAP_METHOD_PROPERTY_ARRAY &)
0x1800195f2  mov     rcx, [rbp+7F0h+var_50]
0x1800195f9  xor     rcx, rsp; StackCookie
0x1800195fc  call    __security_check_cookie
0x180019601  add     rsp, 8B8h
0x180019608  pop     r15
0x18001960a  pop     r14
0x18001960c  pop     r13
0x18001960e  pop     r12
0x180019610  pop     rdi
0x180019611  pop     rsi
0x180019612  pop     rbx
0x180019613  pop     rbp
0x180019614  retn
0x180019615  mov     rcx, cs:WPP_GLOBAL_Control
0x18001961c  lea     rax, WPP_GLOBAL_Control
0x180019623  cmp     rcx, rax
0x180019626  jz      short loc_180019648
0x180019628  test    byte ptr [rcx+1Ch], 1
0x18001962c  jz      short loc_180019648
0x18001962e  movzx   r9d, byte ptr [r14+10h]
0x180019633  mov     edx, 37h ; '7'
0x180019638  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001963f  mov     rcx, [rcx+10h]
0x180019643  call    WPP_SF_d
0x180019648  mov     cl, [r14+10h]
0x18001964c  mov     byte ptr [rsp+8F0h+var_8A0+8], cl
0x180019650  mov     eax, [r14+14h]
0x180019654  mov     dword ptr [rsp+8F0h+var_8A0+0Ch], eax
0x180019658  mov     eax, [r14+18h]
0x18001965c  mov     [rsp+8F0h+var_890], eax
0x180019660  cmp     cl, 0FEh
0x180019663  jz      short loc_18001966A
0x180019665  mov     qword ptr [rsp+8F0h+var_8A0+0Ch], rsi
0x18001966a  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180019671  mov     qword ptr [rsp+8F0h+var_8A0], rax
0x180019676  mov     eax, [r14+1Ch]
0x18001967a  mov     [rsp+8F0h+var_888], eax
0x18001967e  mov     ecx, 80420020h; unsigned int
0x180019683  mov     r8d, ecx; unsigned int
0x180019686  lea     rdx, [rsp+8F0h+var_8A0]; struct EapHost::EapMethodType *
0x18001968b  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
```
