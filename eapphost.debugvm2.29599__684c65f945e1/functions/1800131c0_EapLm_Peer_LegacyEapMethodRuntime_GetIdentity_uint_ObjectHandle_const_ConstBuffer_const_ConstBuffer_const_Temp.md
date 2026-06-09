# EapLm::Peer::LegacyEapMethodRuntime::GetIdentity(uint,ObjectHandle const &,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &,bool &)

- ea: `0x1800131c0`
- end: `0x180013427`
- name: `?GetIdentity@LegacyEapMethodRuntime@Peer@EapLm@@UEAAXIAEBVObjectHandle@@AEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@AEA_N@Z`
- size: `615`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002a90`
- `0x1800049d8`
- `0x1800052c0`
- `0x180009dec`
- `0x180009f70`
- `0x180011578`
- `0x180011958`
- `0x1800131c0`
- `0x180013430`
- `0x180018ffc`
- `0x18001dc24`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001321f`
- `ntdll!EtwEventEnabled` at `0x180013348`
- `ntdll!EtwEventEnabled` at `0x18001321f`
- `ntdll!EtwEventEnabled` at `0x180013348`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EapLm::Peer::LegacyEapMethodRuntime::GetIdentity(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        _QWORD *a4,
        __int64 *a5,
        __int64 a6,
        const wchar_t **a7,
        _BYTE *a8)
{
  int v12; // edx
  int v13; // ecx
  int v14; // r8d
  int IdentityHelper; // r10d
  __int64 result; // rax
  __int64 *v17; // rbx
  const wchar_t *v18; // r9
  __int64 v19; // rdx
  unsigned int v20; // r10d
  _QWORD v21[3]; // [rsp+40h] [rbp-878h] BYREF
  int v22; // [rsp+58h] [rbp-860h]
  char v23[2048]; // [rsp+60h] [rbp-858h] BYREF

  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v23, 0x800u, "RasEapGetIdentity Entry:\n flags(%d)", a2) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v23);
  }
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids, a2);
  }
  *a8 = 0;
  BasicSimpleString<wchar_t>::Assign(a7, 0);
  if ( *(_BYTE *)(a1 + 137) )
  {
    EapLm::Peer::BaseEapMethodRuntime::GetGenericIdentity(
      v13,
      v12,
      v14,
      (_DWORD)a4,
      (__int64)a5,
      a6,
      (__int64)a7,
      (__int64)a8);
  }
  else
  {
    IdentityHelper = EapLm::Peer::LegacyEapMethodRuntime::GetIdentityHelper(a1, a3, a2, a4, a5, a6, (__int64)a7);
    if ( IdentityHelper == 703 )
    {
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids, 703);
      }
      *a8 = 1;
    }
    else if ( IdentityHelper )
    {
      EapHost::EapType::EapType((EapHost::EapType *)v21, (const struct _EAP_TYPE *)(a1 + 16));
      v21[0] = &EapHost::EapMethodType::`vftable';
      v22 = *(_DWORD *)(v19 + 12);
      EapHost::EapException::Throw(v20, (const struct EapHost::EapMethodType *)v21, v20);
    }
  }
  result = EtwEventEnabled(eaphost_Context, DebugInfoEvent);
  v17 = &`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
  if ( (_BYTE)result )
  {
    v18 = (const wchar_t *)&`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
    if ( *a7 )
      v18 = *a7;
    result = StringCchPrintfA(v23, 0x800u, "RasEapGetIdentity Exit:\n returning identity(%ls)", v18);
    if ( (int)result >= 0 && Microsoft_Windows_EapHostEnableBits < 0 )
      result = McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v23);
  }
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    if ( *a7 )
      v17 = (__int64 *)*a7;
    return WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids, v17);
  }
  return result;
}

```

## disassembly

```asm
0x1800131c0  push    rbx
0x1800131c2  push    rbp
0x1800131c3  push    rsi
0x1800131c4  push    rdi
0x1800131c5  push    r12
0x1800131c7  push    r13
0x1800131c9  push    r14
0x1800131cb  push    r15
0x1800131cd  sub     rsp, 878h
0x1800131d4  mov     rax, cs:__security_cookie
0x1800131db  xor     rax, rsp
0x1800131de  mov     [rsp+8B8h+var_58], rax
0x1800131e6  mov     r14, r9
0x1800131e9  mov     r13, r8
0x1800131ec  mov     ebp, edx
0x1800131ee  mov     rsi, rcx
0x1800131f1  mov     rdi, [rsp+8B8h+arg_30]
0x1800131f9  mov     r15, [rsp+8B8h+arg_20]
0x180013201  mov     r12, [rsp+8B8h+arg_28]
0x180013209  mov     rbx, [rsp+8B8h+arg_38]
0x180013211  lea     rdx, DebugInfoEvent
0x180013218  mov     rcx, cs:eaphost_Context
0x18001321f  call    cs:__imp_EtwEventEnabled
0x180013225  test    al, al
0x180013227  jz      short loc_180013267
0x180013229  mov     r9d, ebp
0x18001322c  lea     r8, aRaseapgetident; "RasEapGetIdentity Entry:\n flags(%d)"
0x180013233  mov     edx, 800h; unsigned __int64
0x180013238  lea     rcx, [rsp+8B8h+var_858]; char *
0x18001323d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180013242  test    eax, eax
0x180013244  js      short loc_180013267
0x180013246  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001324d  jge     short loc_180013267
0x18001324f  lea     r8, [rsp+8B8h+var_858]
0x180013254  lea     rdx, DebugInfoEvent
0x18001325b  lea     rcx, eaphost_Context
0x180013262  call    McTemplateU0s_EtwEventWriteTransfer
0x180013267  lea     rax, WPP_GLOBAL_Control
0x18001326e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013275  cmp     rcx, rax
0x180013278  jz      short loc_180013298
0x18001327a  test    byte ptr [rcx+1Ch], 4
0x18001327e  jz      short loc_180013298
0x180013280  mov     edx, 11h
0x180013285  mov     r9d, ebp
0x180013288  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x18001328f  mov     rcx, [rcx+10h]
0x180013293  call    WPP_SF_d
0x180013298  mov     byte ptr [rbx], 0
0x18001329b  xor     edx, edx
0x18001329d  mov     rcx, rdi
0x1800132a0  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x1800132a5  mov     r9, r14
0x1800132a8  cmp     byte ptr [rsi+89h], 0
0x1800132af  jz      short loc_1800132CC
0x1800132b1  mov     [rsp+8B8h+var_880], rbx
0x1800132b6  mov     [rsp+8B8h+var_888], rdi
0x1800132bb  mov     [rsp+8B8h+var_890], r12
0x1800132c0  mov     [rsp+8B8h+var_898], r15
0x1800132c5  call    ?GetGenericIdentity@BaseEapMethodRuntime@Peer@EapLm@@IEAAXIAEBVObjectHandle@@AEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@AEA_N@Z; EapLm::Peer::BaseEapMethodRuntime::GetGenericIdentity(uint,ObjectHandle const &,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &,bool &)
0x1800132ca  jmp     short loc_180013333
0x1800132cc  mov     [rsp+8B8h+var_888], rdi
0x1800132d1  mov     [rsp+8B8h+var_890], r12
0x1800132d6  mov     [rsp+8B8h+var_898], r15
0x1800132db  mov     r8d, ebp
0x1800132de  mov     rdx, r13
0x1800132e1  mov     rcx, rsi
0x1800132e4  call    ?GetIdentityHelper@LegacyEapMethodRuntime@Peer@EapLm@@AEAAKAEBVObjectHandle@@IAEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@@Z; EapLm::Peer::LegacyEapMethodRuntime::GetIdentityHelper(ObjectHandle const &,uint,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &)
0x1800132e9  mov     r10d, eax
0x1800132ec  mov     r9d, 2BFh
0x1800132f2  cmp     eax, r9d
0x1800132f5  jnz     short loc_18001332A
0x1800132f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132fe  lea     rbp, WPP_GLOBAL_Control
0x180013305  cmp     rcx, rbp
0x180013308  jz      short loc_180013325
0x18001330a  test    byte ptr [rcx+1Ch], 4
0x18001330e  jz      short loc_180013325
0x180013310  mov     edx, 12h
0x180013315  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x18001331c  mov     rcx, [rcx+10h]
0x180013320  call    WPP_SF_d
0x180013325  mov     byte ptr [rbx], 1
0x180013328  jmp     short loc_18001333A
0x18001332a  test    r10d, r10d
0x18001332d  jnz     loc_1800133F5
0x180013333  lea     rbp, WPP_GLOBAL_Control
0x18001333a  lea     rdx, DebugInfoEvent
0x180013341  mov     rcx, cs:eaphost_Context
0x180013348  call    cs:__imp_EtwEventEnabled
0x18001334e  lea     rbx, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x180013355  xor     esi, esi
0x180013357  test    al, al
0x180013359  jz      short loc_1800133A0
0x18001335b  mov     r9, rbx
0x18001335e  cmp     [rdi], rsi
0x180013361  cmovnz  r9, [rdi]
0x180013365  lea     r8, aRaseapgetident_1; "RasEapGetIdentity Exit:\n returning ide"...
0x18001336c  mov     edx, 800h; unsigned __int64
0x180013371  lea     rcx, [rsp+8B8h+var_858]; char *
0x180013376  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001337b  test    eax, eax
0x18001337d  js      short loc_1800133A0
0x18001337f  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x180013386  jge     short loc_1800133A0
0x180013388  lea     r8, [rsp+8B8h+var_858]
0x18001338d  lea     rdx, DebugInfoEvent
0x180013394  lea     rcx, eaphost_Context
0x18001339b  call    McTemplateU0s_EtwEventWriteTransfer
0x1800133a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800133a7  cmp     rcx, rbp
0x1800133aa  jz      short loc_1800133D1
0x1800133ac  test    byte ptr [rcx+1Ch], 4
0x1800133b0  jz      short loc_1800133D1
0x1800133b2  cmp     [rdi], rsi
0x1800133b5  cmovnz  rbx, [rdi]
0x1800133b9  mov     edx, 13h
0x1800133be  mov     r9, rbx
0x1800133c1  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x1800133c8  mov     rcx, [rcx+10h]
0x1800133cc  call    WPP_SF_S
0x1800133d1  mov     rcx, [rsp+8B8h+var_58]
0x1800133d9  xor     rcx, rsp; StackCookie
0x1800133dc  call    __security_check_cookie
0x1800133e1  add     rsp, 878h
0x1800133e8  pop     r15
0x1800133ea  pop     r14
0x1800133ec  pop     r13
0x1800133ee  pop     r12
0x1800133f0  pop     rdi
0x1800133f1  pop     rsi
0x1800133f2  pop     rbp
0x1800133f3  pop     rbx
0x1800133f4  retn
0x1800133f5  lea     rdx, [rsi+10h]; struct _EAP_TYPE *
0x1800133f9  lea     rcx, [rsp+8B8h+var_878]; this
0x1800133fe  call    ??0EapType@EapHost@@QEAA@AEBU_EAP_TYPE@@@Z; EapHost::EapType::EapType(_EAP_TYPE const &)
0x180013403  lea     rcx, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001340a  mov     [rsp+8B8h+var_878], rcx
0x18001340f  mov     eax, [rdx+0Ch]
0x180013412  mov     [rsp+8B8h+var_860], eax
0x180013416  mov     r8d, r10d; unsigned int
0x180013419  lea     rdx, [rsp+8B8h+var_878]; struct EapHost::EapMethodType *
0x18001341e  mov     ecx, r10d; unsigned int
0x180013421  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
```
