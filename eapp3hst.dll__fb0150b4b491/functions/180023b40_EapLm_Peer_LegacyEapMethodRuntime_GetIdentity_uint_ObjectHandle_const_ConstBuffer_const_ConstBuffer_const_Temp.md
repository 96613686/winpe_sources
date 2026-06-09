# EapLm::Peer::LegacyEapMethodRuntime::GetIdentity(uint,ObjectHandle const &,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &,bool &)

- ea: `0x180023b40`
- end: `0x180023dc3`
- name: `?GetIdentity@LegacyEapMethodRuntime@Peer@EapLm@@UEAAXIAEBVObjectHandle@@AEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@AEA_N@Z`
- size: `643`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, _QWORD *, __int64 *, __int64, void **, _BYTE *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x18000bf94`
- `0x180013d10`
- `0x18001549c`
- `0x180016400`
- `0x1800165a4`
- `0x18001b154`
- `0x180023b40`
- `0x180023dcc`
- `0x1800296fc`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180023ba5`
- `ntdll!EtwEventEnabled` at `0x180023cd0`
- `ntdll!EtwEventEnabled` at `0x180023ba5`
- `ntdll!EtwEventEnabled` at `0x180023cd0`

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
        void **a7,
        _BYTE *a8)
{
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  unsigned int IdentityHelper; // r10d
  __int64 result; // rax
  __int64 *v16; // rbx
  const wchar_t *v17; // r9
  void **v19; // [rsp+48h] [rbp-B8h] BYREF
  char v20; // [rsp+50h] [rbp-B0h]
  __int64 v21; // [rsp+54h] [rbp-ACh]
  int v22; // [rsp+60h] [rbp-A0h]
  char v23[2048]; // [rsp+70h] [rbp-90h] BYREF

  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v23, 0x800u, "RasEapGetIdentity Entry:\n flags(%d)", a2) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v23);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids, a2);
  *a8 = 0;
  BasicSimpleString<wchar_t>::Assign(a7, 0);
  if ( *(_BYTE *)(a1 + 137) )
  {
    EapLm::Peer::BaseEapMethodRuntime::GetGenericIdentity(v12, v11, v13, (__int64)a4, (__int64)a5, a6, a7, a8);
  }
  else
  {
    IdentityHelper = EapLm::Peer::LegacyEapMethodRuntime::GetIdentityHelper(a1, a3, a2, a4, a5, a6, (__int64)a7);
    if ( IdentityHelper == 703 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids, 703);
      *a8 = 1;
    }
    else if ( IdentityHelper )
    {
      v20 = *(_BYTE *)(a1 + 16);
      v21 = *(_QWORD *)(a1 + 20);
      if ( v20 != -2 )
        v21 = 0;
      v19 = &EapHost::EapMethodType::`vftable';
      v22 = *(_DWORD *)(a1 + 28);
      EapHost::EapException::Throw(IdentityHelper, (const struct EapHost::EapMethodType *)&v19, IdentityHelper);
    }
  }
  result = EtwEventEnabled(eaphost_Context, DebugInfoEvent);
  v16 = &`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
  if ( (_BYTE)result )
  {
    v17 = (const wchar_t *)&`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
    if ( *a7 )
      v17 = (const wchar_t *)*a7;
    result = StringCchPrintfA(v23, 0x800u, "RasEapGetIdentity Exit:\n returning identity(%ls)", v17);
    if ( (int)result >= 0 && Microsoft_Windows_EapHostEnableBits < 0 )
      result = McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v23);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    if ( *a7 )
      v16 = (__int64 *)*a7;
    return WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids, v16);
  }
  return result;
}

```

## disassembly

```asm
0x180023b40  push    rbp
0x180023b42  push    rbx
0x180023b43  push    rsi
0x180023b44  push    rdi
0x180023b45  push    r12
0x180023b47  push    r13
0x180023b49  push    r14
0x180023b4b  push    r15
0x180023b4d  lea     rbp, [rsp-788h]
0x180023b55  sub     rsp, 888h
0x180023b5c  mov     rax, cs:__security_cookie
0x180023b63  xor     rax, rsp
0x180023b66  mov     [rbp+7C0h+var_50], rax
0x180023b6d  mov     r15, r9
0x180023b70  mov     [rsp+8C0h+var_880], r8
0x180023b75  mov     r14d, edx
0x180023b78  mov     rbx, rcx
0x180023b7b  mov     rdi, [rbp+7C0h+arg_30]
0x180023b82  mov     r12, [rbp+7C0h+arg_20]
0x180023b89  mov     r13, [rbp+7C0h+arg_28]
0x180023b90  mov     rsi, [rbp+7C0h+arg_38]
0x180023b97  lea     rdx, DebugInfoEvent
0x180023b9e  mov     rcx, cs:eaphost_Context
0x180023ba5  call    cs:__imp_EtwEventEnabled
0x180023bab  test    al, al
0x180023bad  jz      short loc_180023BED
0x180023baf  mov     r9d, r14d
0x180023bb2  lea     r8, aRaseapgetident_0; "RasEapGetIdentity Entry:\n flags(%d)"
0x180023bb9  mov     edx, 800h; unsigned __int64
0x180023bbe  lea     rcx, [rsp+8C0h+var_850]; char *
0x180023bc3  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180023bc8  test    eax, eax
0x180023bca  js      short loc_180023BED
0x180023bcc  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180023bd3  jge     short loc_180023BED
0x180023bd5  lea     r8, [rsp+8C0h+var_850]
0x180023bda  lea     rdx, DebugInfoEvent
0x180023be1  lea     rcx, eaphost_Context
0x180023be8  call    McTemplateU0s_EtwEventWriteTransfer
0x180023bed  lea     rax, WPP_GLOBAL_Control
0x180023bf4  mov     rcx, cs:WPP_GLOBAL_Control
0x180023bfb  cmp     rcx, rax
0x180023bfe  jz      short loc_180023C1E
0x180023c00  test    byte ptr [rcx+1Ch], 4
0x180023c04  jz      short loc_180023C1E
0x180023c06  mov     edx, 11h
0x180023c0b  mov     r9d, r14d
0x180023c0e  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180023c15  mov     rcx, [rcx+10h]
0x180023c19  call    WPP_SF_d
0x180023c1e  mov     byte ptr [rsi], 0
0x180023c21  xor     edx, edx
0x180023c23  mov     rcx, rdi
0x180023c26  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x180023c2b  mov     r9, r15
0x180023c2e  cmp     byte ptr [rbx+89h], 0
0x180023c35  jz      short loc_180023C52
0x180023c37  mov     [rsp+8C0h+var_888], rsi
0x180023c3c  mov     [rsp+8C0h+var_890], rdi
0x180023c41  mov     [rsp+8C0h+var_898], r13
0x180023c46  mov     [rsp+8C0h+var_8A0], r12
0x180023c4b  call    ?GetGenericIdentity@BaseEapMethodRuntime@Peer@EapLm@@IEAAXIAEBVObjectHandle@@AEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@AEA_N@Z; EapLm::Peer::BaseEapMethodRuntime::GetGenericIdentity(uint,ObjectHandle const &,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &,bool &)
0x180023c50  jmp     short loc_180023CBB
0x180023c52  mov     [rsp+8C0h+var_890], rdi
0x180023c57  mov     [rsp+8C0h+var_898], r13
0x180023c5c  mov     [rsp+8C0h+var_8A0], r12
0x180023c61  mov     r8d, r14d
0x180023c64  mov     rdx, [rsp+8C0h+var_880]
0x180023c69  mov     rcx, rbx
0x180023c6c  call    ?GetIdentityHelper@LegacyEapMethodRuntime@Peer@EapLm@@AEAAKAEBVObjectHandle@@IAEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@@Z; EapLm::Peer::LegacyEapMethodRuntime::GetIdentityHelper(ObjectHandle const &,uint,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &)
0x180023c71  mov     r10d, eax
0x180023c74  mov     r9d, 2BFh
0x180023c7a  cmp     eax, r9d
0x180023c7d  jnz     short loc_180023CB2
0x180023c7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c86  lea     r14, WPP_GLOBAL_Control
0x180023c8d  cmp     rcx, r14
0x180023c90  jz      short loc_180023CAD
0x180023c92  test    byte ptr [rcx+1Ch], 4
0x180023c96  jz      short loc_180023CAD
0x180023c98  mov     edx, 12h
0x180023c9d  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180023ca4  mov     rcx, [rcx+10h]
0x180023ca8  call    WPP_SF_d
0x180023cad  mov     byte ptr [rsi], 1
0x180023cb0  jmp     short loc_180023CC2
0x180023cb2  test    r10d, r10d
0x180023cb5  jnz     loc_180023D7C
0x180023cbb  lea     r14, WPP_GLOBAL_Control
0x180023cc2  lea     rdx, DebugInfoEvent
0x180023cc9  mov     rcx, cs:eaphost_Context
0x180023cd0  call    cs:__imp_EtwEventEnabled
0x180023cd6  lea     rbx, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x180023cdd  test    al, al
0x180023cdf  jz      short loc_180023D27
0x180023ce1  mov     r9, rbx
0x180023ce4  cmp     qword ptr [rdi], 0
0x180023ce8  cmovnz  r9, [rdi]
0x180023cec  lea     r8, aRaseapgetident_5; "RasEapGetIdentity Exit:\n returning ide"...
0x180023cf3  mov     edx, 800h; unsigned __int64
0x180023cf8  lea     rcx, [rsp+8C0h+var_850]; char *
0x180023cfd  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180023d02  test    eax, eax
0x180023d04  js      short loc_180023D27
0x180023d06  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180023d0d  jge     short loc_180023D27
0x180023d0f  lea     r8, [rsp+8C0h+var_850]
0x180023d14  lea     rdx, DebugInfoEvent
0x180023d1b  lea     rcx, eaphost_Context
0x180023d22  call    McTemplateU0s_EtwEventWriteTransfer
0x180023d27  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d2e  cmp     rcx, r14
0x180023d31  jz      short loc_180023D59
0x180023d33  test    byte ptr [rcx+1Ch], 4
0x180023d37  jz      short loc_180023D59
0x180023d39  cmp     qword ptr [rdi], 0
0x180023d3d  cmovnz  rbx, [rdi]
0x180023d41  mov     edx, 13h
0x180023d46  mov     r9, rbx
0x180023d49  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180023d50  mov     rcx, [rcx+10h]
0x180023d54  call    WPP_SF_S
0x180023d59  mov     rcx, [rbp+7C0h+var_50]
0x180023d60  xor     rcx, rsp; StackCookie
0x180023d63  call    __security_check_cookie
0x180023d68  add     rsp, 888h
0x180023d6f  pop     r15
0x180023d71  pop     r14
0x180023d73  pop     r13
0x180023d75  pop     r12
0x180023d77  pop     rdi
0x180023d78  pop     rsi
0x180023d79  pop     rbx
0x180023d7a  pop     rbp
0x180023d7b  retn
0x180023d7c  mov     cl, [rbx+10h]
0x180023d7f  mov     [rsp+8C0h+var_870], cl
0x180023d83  mov     eax, [rbx+14h]
0x180023d86  mov     dword ptr [rsp+8C0h+var_86C], eax
0x180023d8a  mov     eax, [rbx+18h]
0x180023d8d  mov     dword ptr [rsp+8C0h+var_86C+4], eax
0x180023d91  cmp     cl, 0FEh
0x180023d94  jz      short loc_180023D9F
0x180023d96  mov     [rsp+8C0h+var_86C], 0
0x180023d9f  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180023da6  mov     [rsp+8C0h+var_878], rax
0x180023dab  mov     eax, [rbx+1Ch]
0x180023dae  mov     [rsp+8C0h+var_860], eax
0x180023db2  mov     r8d, r10d; unsigned int
0x180023db5  lea     rdx, [rsp+8C0h+var_878]; struct EapHost::EapMethodType *
0x180023dba  mov     ecx, r10d; unsigned int
0x180023dbd  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
```
