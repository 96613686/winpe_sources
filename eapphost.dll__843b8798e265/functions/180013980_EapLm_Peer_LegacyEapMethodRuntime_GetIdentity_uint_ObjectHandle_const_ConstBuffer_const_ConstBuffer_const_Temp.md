# EapLm::Peer::LegacyEapMethodRuntime::GetIdentity(uint,ObjectHandle const &,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &,bool &)

- ea: `0x180013980`
- end: `0x180013bf4`
- name: `?GetIdentity@LegacyEapMethodRuntime@Peer@EapLm@@UEAAXIAEBVObjectHandle@@AEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@AEA_N@Z`
- size: `628`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002af0`
- `0x180004b4c`
- `0x180005410`
- `0x18000a24c`
- `0x18000a3e4`
- `0x180011cb8`
- `0x1800120c4`
- `0x180013980`
- `0x180013bfc`
- `0x1800199bc`
- `0x18001e728`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800139df`
- `ntdll!EtwEventEnabled` at `0x180013b0e`
- `ntdll!EtwEventEnabled` at `0x1800139df`
- `ntdll!EtwEventEnabled` at `0x180013b0e`

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
0x180013980  push    rbx
0x180013982  push    rbp
0x180013983  push    rsi
0x180013984  push    rdi
0x180013985  push    r12
0x180013987  push    r13
0x180013989  push    r14
0x18001398b  push    r15
0x18001398d  sub     rsp, 878h
0x180013994  mov     rax, cs:__security_cookie
0x18001399b  xor     rax, rsp
0x18001399e  mov     [rsp+8B8h+var_58], rax
0x1800139a6  mov     r14, r9
0x1800139a9  mov     r13, r8
0x1800139ac  mov     ebp, edx
0x1800139ae  mov     rsi, rcx
0x1800139b1  mov     rdi, [rsp+8B8h+arg_30]
0x1800139b9  mov     r15, [rsp+8B8h+arg_20]
0x1800139c1  mov     r12, [rsp+8B8h+arg_28]
0x1800139c9  mov     rbx, [rsp+8B8h+arg_38]
0x1800139d1  lea     rdx, DebugInfoEvent
0x1800139d8  mov     rcx, cs:eaphost_Context
0x1800139df  call    cs:__imp_EtwEventEnabled
0x1800139e6  nop     dword ptr [rax+rax+00h]
0x1800139eb  test    al, al
0x1800139ed  jz      short loc_180013A2D
0x1800139ef  mov     r9d, ebp
0x1800139f2  lea     r8, aRaseapgetident; "RasEapGetIdentity Entry:\n flags(%d)"
0x1800139f9  mov     edx, 800h; unsigned __int64
0x1800139fe  lea     rcx, [rsp+8B8h+var_858]; char *
0x180013a03  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180013a08  test    eax, eax
0x180013a0a  js      short loc_180013A2D
0x180013a0c  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180013a13  jge     short loc_180013A2D
0x180013a15  lea     r8, [rsp+8B8h+var_858]
0x180013a1a  lea     rdx, DebugInfoEvent
0x180013a21  lea     rcx, eaphost_Context
0x180013a28  call    McTemplateU0s_EtwEventWriteTransfer
0x180013a2d  lea     rax, WPP_GLOBAL_Control
0x180013a34  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a3b  cmp     rcx, rax
0x180013a3e  jz      short loc_180013A5E
0x180013a40  test    byte ptr [rcx+1Ch], 4
0x180013a44  jz      short loc_180013A5E
0x180013a46  mov     edx, 11h
0x180013a4b  mov     r9d, ebp
0x180013a4e  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180013a55  mov     rcx, [rcx+10h]
0x180013a59  call    WPP_SF_d
0x180013a5e  mov     byte ptr [rbx], 0
0x180013a61  xor     edx, edx
0x180013a63  mov     rcx, rdi
0x180013a66  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x180013a6b  mov     r9, r14
0x180013a6e  cmp     byte ptr [rsi+89h], 0
0x180013a75  jz      short loc_180013A92
0x180013a77  mov     [rsp+8B8h+var_880], rbx
0x180013a7c  mov     [rsp+8B8h+var_888], rdi
0x180013a81  mov     [rsp+8B8h+var_890], r12
0x180013a86  mov     [rsp+8B8h+var_898], r15
0x180013a8b  call    ?GetGenericIdentity@BaseEapMethodRuntime@Peer@EapLm@@IEAAXIAEBVObjectHandle@@AEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@AEA_N@Z; EapLm::Peer::BaseEapMethodRuntime::GetGenericIdentity(uint,ObjectHandle const &,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &,bool &)
0x180013a90  jmp     short loc_180013AF9
0x180013a92  mov     [rsp+8B8h+var_888], rdi
0x180013a97  mov     [rsp+8B8h+var_890], r12
0x180013a9c  mov     [rsp+8B8h+var_898], r15
0x180013aa1  mov     r8d, ebp
0x180013aa4  mov     rdx, r13
0x180013aa7  mov     rcx, rsi
0x180013aaa  call    ?GetIdentityHelper@LegacyEapMethodRuntime@Peer@EapLm@@AEAAKAEBVObjectHandle@@IAEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@@Z; EapLm::Peer::LegacyEapMethodRuntime::GetIdentityHelper(ObjectHandle const &,uint,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &)
0x180013aaf  mov     r10d, eax
0x180013ab2  mov     r9d, 2BFh
0x180013ab8  cmp     eax, r9d
0x180013abb  jnz     short loc_180013AF0
0x180013abd  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ac4  lea     rbp, WPP_GLOBAL_Control
0x180013acb  cmp     rcx, rbp
0x180013ace  jz      short loc_180013AEB
0x180013ad0  test    byte ptr [rcx+1Ch], 4
0x180013ad4  jz      short loc_180013AEB
0x180013ad6  mov     edx, 12h
0x180013adb  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180013ae2  mov     rcx, [rcx+10h]
0x180013ae6  call    WPP_SF_d
0x180013aeb  mov     byte ptr [rbx], 1
0x180013aee  jmp     short loc_180013B00
0x180013af0  test    r10d, r10d
0x180013af3  jnz     loc_180013BC2
0x180013af9  lea     rbp, WPP_GLOBAL_Control
0x180013b00  lea     rdx, DebugInfoEvent
0x180013b07  mov     rcx, cs:eaphost_Context
0x180013b0e  call    cs:__imp_EtwEventEnabled
0x180013b15  nop     dword ptr [rax+rax+00h]
0x180013b1a  lea     rbx, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x180013b21  xor     esi, esi
0x180013b23  test    al, al
0x180013b25  jz      short loc_180013B6C
0x180013b27  mov     r9, rbx
0x180013b2a  cmp     [rdi], rsi
0x180013b2d  cmovnz  r9, [rdi]
0x180013b31  lea     r8, aRaseapgetident_1; "RasEapGetIdentity Exit:\n returning ide"...
0x180013b38  mov     edx, 800h; unsigned __int64
0x180013b3d  lea     rcx, [rsp+8B8h+var_858]; char *
0x180013b42  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180013b47  test    eax, eax
0x180013b49  js      short loc_180013B6C
0x180013b4b  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x180013b52  jge     short loc_180013B6C
0x180013b54  lea     r8, [rsp+8B8h+var_858]
0x180013b59  lea     rdx, DebugInfoEvent
0x180013b60  lea     rcx, eaphost_Context
0x180013b67  call    McTemplateU0s_EtwEventWriteTransfer
0x180013b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b73  cmp     rcx, rbp
0x180013b76  jz      short loc_180013B9D
0x180013b78  test    byte ptr [rcx+1Ch], 4
0x180013b7c  jz      short loc_180013B9D
0x180013b7e  cmp     [rdi], rsi
0x180013b81  cmovnz  rbx, [rdi]
0x180013b85  mov     edx, 13h
0x180013b8a  mov     r9, rbx
0x180013b8d  lea     r8, WPP_85dc5ab8f9f63ed64ebe80d18a1b8cc2_Traceguids
0x180013b94  mov     rcx, [rcx+10h]
0x180013b98  call    WPP_SF_S
0x180013b9d  mov     rcx, [rsp+8B8h+var_58]
0x180013ba5  xor     rcx, rsp; StackCookie
0x180013ba8  call    __security_check_cookie
0x180013bad  add     rsp, 878h
0x180013bb4  pop     r15
0x180013bb6  pop     r14
0x180013bb8  pop     r13
0x180013bba  pop     r12
0x180013bbc  pop     rdi
0x180013bbd  pop     rsi
0x180013bbe  pop     rbp
0x180013bbf  pop     rbx
0x180013bc0  retn
0x180013bc2  lea     rdx, [rsi+10h]; struct _EAP_TYPE *
0x180013bc6  lea     rcx, [rsp+8B8h+var_878]; this
0x180013bcb  call    ??0EapType@EapHost@@QEAA@AEBU_EAP_TYPE@@@Z; EapHost::EapType::EapType(_EAP_TYPE const &)
0x180013bd0  lea     rcx, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180013bd7  mov     [rsp+8B8h+var_878], rcx
0x180013bdc  mov     eax, [rdx+0Ch]
0x180013bdf  mov     [rsp+8B8h+var_860], eax
0x180013be3  mov     r8d, r10d; unsigned int
0x180013be6  lea     rdx, [rsp+8B8h+var_878]; struct EapHost::EapMethodType *
0x180013beb  mov     ecx, r10d; unsigned int
0x180013bee  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
```
