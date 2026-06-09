# EapHost::Peer::Host::GetIdentity(EapHost::Peer::PeerSession &)

- ea: `0x180025760`
- end: `0x180025b12`
- name: `?GetIdentity@Host@Peer@EapHost@@AEAA?AW4tagEapHostPeerResponseAction@@AEAVPeerSession@23@@Z`
- size: `946`
- prototype: `enum tagEapHostPeerResponseAction(EapHost::Peer::Host *__hidden this, struct EapHost::Peer::PeerSession *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800269ac`

## callees

- `0x180002a90`
- `0x1800052c0`
- `0x1800072cc`
- `0x180009b98`
- `0x180009dc4`
- `0x180009f70`
- `0x180011578`
- `0x180011958`
- `0x180025760`
- `0x18002ab8c`
- `0x18002f93c`
- `0x18002fd44`
- `0x180038010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180025838`
- `ntdll!EtwEventEnabled` at `0x1800259c3`
- `ntdll!EtwEventEnabled` at `0x180025838`
- `ntdll!EtwEventEnabled` at `0x1800259c3`

## string_xrefs

- `0x180025842`: `Returning NULL identity for Guest access`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EapHost::Peer::Host::GetIdentity(
        EapHost::Peer::Host *this,
        struct EapHost::Peer::PeerSession *a2,
        __int64 a3)
{
  bool v4; // r9
  enum tagEapHostPeerResponseAction v5; // ebx
  volatile signed __int32 *v6; // rsi
  char *v7; // r15
  __int64 v8; // r8
  __int64 *v9; // rsi
  __int64 *v10; // rdx
  const wchar_t **v11; // r14
  const wchar_t *v12; // r9
  bool v14[8]; // [rsp+50h] [rbp-B0h] BYREF
  void *v15; // [rsp+58h] [rbp-A8h] BYREF
  void *v16; // [rsp+60h] [rbp-A0h] BYREF
  size_t v17; // [rsp+68h] [rbp-98h]
  _QWORD v18[2]; // [rsp+70h] [rbp-90h] BYREF
  char v19[2048]; // [rsp+80h] [rbp-80h] BYREF

  LOBYTE(a3) = 0;
  v14[0] = 0;
  if ( !*((_BYTE *)a2 + 132) )
  {
    *(_QWORD *)((char *)a2 + 260) = 2;
    if ( (byte_18004E841 & 4) != 0 )
    {
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)PeerUserEntersCredentials, a3, 1, (__int64)&v16);
      LOBYTE(a3) = v14[0];
    }
    v4 = 0;
    v5 = EapHostPeerResponseInvokeUi;
LABEL_5:
    WriteEapGetIdentityTelemetry(a2, v5, a3, v4);
    return (unsigned int)v5;
  }
  if ( (*((_BYTE *)a2 + 128) & 0x40) != 0 )
  {
    BasicSimpleString<wchar_t>::Assign((void **)a2 + 39, 0);
    *((_DWORD *)a2 + 66) = 6;
    v5 = EapHostPeerResponseSend;
    *((_DWORD *)a2 + 65) = 1;
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v19, 0x800u, "Returning NULL identity for Guest access") >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v19);
    }
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids);
    }
    v4 = 1;
    LOBYTE(a3) = v14[0];
    goto LABEL_5;
  }
  v16 = 0;
  v17 = 0;
  v15 = 0;
  v6 = (volatile signed __int32 *)*((_QWORD *)a2 + 36);
  v18[0] = v6;
  v5 = EapHostPeerResponseSend;
  if ( v6 )
    _InterlockedAdd(v6 + 2, 1u);
  v7 = (char *)a2 + 224;
  (*(void (__fastcall **)(volatile signed __int32 *, _QWORD, char *, char *, char *, void **, void **, bool *))(*(_QWORD *)v6 + 32LL))(
    v6,
    *((unsigned int *)a2 + 32),
    (char *)a2 + 192,
    (char *)a2 + 208,
    (char *)a2 + 224,
    &v16,
    &v15,
    v14);
  if ( v6 )
    ReferenceCounted::Release((ReferenceCounted *)v6);
  if ( v14[0] )
  {
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids);
    }
    if ( (byte_18004E841 & 4) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)PeerUserEntersCredentials, v8, 1, (__int64)v18);
    *(_QWORD *)((char *)a2 + 260) = 2;
    v5 = EapHostPeerResponseInvokeUi;
  }
  else
  {
    if ( (byte_18004E841 & 4) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        &eaphost_Context,
        (__int64)PeerUserUsesSavedCredentials,
        v8,
        1,
        (__int64)v18);
    v9 = &`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
    v10 = &`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
    if ( v15 )
      v10 = (__int64 *)v15;
    v11 = (const wchar_t **)((char *)a2 + 312);
    BasicSimpleString<wchar_t>::Assign((void **)a2 + 39, (__int64)v10);
    TempBuffer<0>::Assign((__int64)v7, v17, v16);
    *((_DWORD *)a2 + 66) = 6;
    *((_DWORD *)a2 + 65) = 1;
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
    {
      v12 = (const wchar_t *)&`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
      if ( *v11 )
        v12 = *v11;
      if ( (int)StringCchPrintfA(v19, 0x800u, "GetIdentity returning %S", v12) >= 0
        && Microsoft_Windows_EapHostEnableBits < 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v19);
      }
    }
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      if ( *v11 )
        v9 = (__int64 *)*v11;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids, v9);
    }
  }
  WriteEapGetIdentityTelemetry(a2, v5, v14[0], 0);
  HeapAllocator::Free(v15);
  v15 = 0;
  HeapAllocator::Free(v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180025760  mov     [rsp-8+arg_0], rbx
0x180025765  mov     [rsp-8+arg_10], rsi
0x18002576a  push    rbp
0x18002576b  push    rdi
0x18002576c  push    r12
0x18002576e  push    r14
0x180025770  push    r15
0x180025772  lea     rbp, [rsp-790h]
0x18002577a  sub     rsp, 890h
0x180025781  mov     rax, cs:__security_cookie
0x180025788  xor     rax, rsp
0x18002578b  mov     [rbp+7B0h+var_30], rax
0x180025792  mov     rdi, rdx
0x180025795  xor     r12d, r12d
0x180025798  mov     r8b, r12b
0x18002579b  mov     [rsp+8B0h+var_860], r12b
0x1800257a0  cmp     [rdx+84h], r12b
0x1800257a7  jnz     short loc_1800257FA
0x1800257a9  mov     qword ptr [rdx+104h], 2
0x1800257b4  test    cs:byte_18004E841, 4
0x1800257bb  jz      short loc_1800257E4
0x1800257bd  lea     rax, [rsp+8B0h+var_850]
0x1800257c2  mov     [rsp+8B0h+var_890], rax
0x1800257c7  lea     r9d, [r12+1]
0x1800257cc  lea     rdx, PeerUserEntersCredentials
0x1800257d3  lea     rcx, eaphost_Context
0x1800257da  call    McGenEventWrite_EtwEventWriteTransfer
0x1800257df  mov     r8b, [rsp+8B0h+var_860]; bool
0x1800257e4  xor     r9d, r9d; bool
0x1800257e7  lea     ebx, [r9+3]
0x1800257eb  mov     edx, ebx; enum tagEapHostPeerResponseAction
0x1800257ed  mov     rcx, rdi; struct EapHost::Peer::PeerSession *
0x1800257f0  call    ?WriteEapGetIdentityTelemetry@@YAXAEAVPeerSession@Peer@EapHost@@W4tagEapHostPeerResponseAction@@_N2@Z; WriteEapGetIdentityTelemetry(EapHost::Peer::PeerSession &,tagEapHostPeerResponseAction,bool,bool)
0x1800257f5  jmp     loc_180025AE5
0x1800257fa  test    byte ptr [rdx+80h], 40h
0x180025801  jz      loc_1800258B6
0x180025807  lea     rcx, [rdx+138h]
0x18002580e  xor     edx, edx
0x180025810  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x180025815  mov     dword ptr [rdi+108h], 6
0x18002581f  mov     ebx, 1
0x180025824  mov     [rdi+104h], ebx
0x18002582a  lea     rdx, DebugInfoEvent
0x180025831  mov     rcx, cs:eaphost_Context
0x180025838  call    cs:__imp_EtwEventEnabled
0x18002583e  test    al, al
0x180025840  jz      short loc_18002587B
0x180025842  lea     r8, aReturningNullI; "Returning NULL identity for Guest acces"...
0x180025849  mov     edx, 800h; unsigned __int64
0x18002584e  lea     rcx, [rbp+7B0h+var_830]; char *
0x180025852  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180025857  test    eax, eax
0x180025859  js      short loc_18002587B
0x18002585b  cmp     cs:Microsoft_Windows_EapHostEnableBits, r12b
0x180025862  jge     short loc_18002587B
0x180025864  lea     r8, [rbp+7B0h+var_830]
0x180025868  lea     rdx, DebugInfoEvent
0x18002586f  lea     rcx, eaphost_Context
0x180025876  call    McTemplateU0s_EtwEventWriteTransfer
0x18002587b  lea     rax, WPP_GLOBAL_Control
0x180025882  mov     rcx, cs:WPP_GLOBAL_Control
0x180025889  cmp     rcx, rax
0x18002588c  jz      short loc_1800258A9
0x18002588e  test    byte ptr [rcx+1Ch], 4
0x180025892  jz      short loc_1800258A9
0x180025894  mov     edx, 2Ch ; ','
0x180025899  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x1800258a0  mov     rcx, [rcx+10h]
0x1800258a4  call    WPP_SF_
0x1800258a9  mov     r9b, bl
0x1800258ac  mov     r8b, [rsp+8B0h+var_860]
0x1800258b1  jmp     loc_1800257EB
0x1800258b6  mov     [rsp+8B0h+var_850], r12
0x1800258bb  mov     [rsp+8B0h+var_848], r12
0x1800258c0  mov     [rsp+8B0h+var_858], r12
0x1800258c5  mov     rsi, [rdx+120h]
0x1800258cc  mov     [rsp+8B0h+var_840], rsi
0x1800258d1  mov     ebx, 1
0x1800258d6  test    rsi, rsi
0x1800258d9  jz      short loc_1800258DF
0x1800258db  lock add [rsi+8], ebx
0x1800258df  lea     r15, [rdx+0E0h]
0x1800258e6  mov     rax, [rsi]
0x1800258e9  lea     r9, [rdx+0D0h]
0x1800258f0  lea     r8, [rdx+0C0h]
0x1800258f7  lea     rcx, [rsp+8B0h+var_860]
0x1800258fc  mov     [rsp+8B0h+var_878], rcx
0x180025901  lea     rcx, [rsp+8B0h+var_858]
0x180025906  mov     [rsp+8B0h+var_880], rcx
0x18002590b  lea     rcx, [rsp+8B0h+var_850]
0x180025910  mov     [rsp+8B0h+var_888], rcx
0x180025915  mov     [rsp+8B0h+var_890], r15
0x18002591a  mov     edx, [rdx+80h]
0x180025920  mov     rcx, rsi
0x180025923  mov     rax, [rax+20h]
0x180025927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002592c  nop
0x18002592d  test    rsi, rsi
0x180025930  jz      short loc_18002593A
0x180025932  mov     rcx, rsi; this
0x180025935  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18002593a  cmp     [rsp+8B0h+var_860], r12b
0x18002593f  jnz     loc_180025A52
0x180025945  test    cs:byte_18004E841, 4
0x18002594c  jz      short loc_18002596E
0x18002594e  lea     rax, [rsp+8B0h+var_840]
0x180025953  mov     [rsp+8B0h+var_890], rax
0x180025958  mov     r9d, ebx
0x18002595b  lea     rdx, PeerUserUsesSavedCredentials
0x180025962  lea     rcx, eaphost_Context
0x180025969  call    McGenEventWrite_EtwEventWriteTransfer
0x18002596e  mov     rax, [rsp+8B0h+var_858]
0x180025973  lea     rsi, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x18002597a  mov     rdx, rsi
0x18002597d  test    rax, rax
0x180025980  cmovnz  rdx, rax
0x180025984  lea     r14, [rdi+138h]
0x18002598b  mov     rcx, r14
0x18002598e  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x180025993  mov     r8, [rsp+8B0h+var_850]
0x180025998  mov     rdx, [rsp+8B0h+var_848]
0x18002599d  mov     rcx, r15
0x1800259a0  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x1800259a5  mov     dword ptr [rdi+108h], 6
0x1800259af  mov     [rdi+104h], ebx
0x1800259b5  lea     rdx, DebugInfoEvent
0x1800259bc  mov     rcx, cs:eaphost_Context
0x1800259c3  call    cs:__imp_EtwEventEnabled
0x1800259c9  test    al, al
0x1800259cb  jz      short loc_180025A10
0x1800259cd  mov     r9, rsi
0x1800259d0  cmp     [r14], r12
0x1800259d3  cmovnz  r9, [r14]
0x1800259d7  lea     r8, aGetidentityRet; "GetIdentity returning %S"
0x1800259de  mov     edx, 800h; unsigned __int64
0x1800259e3  lea     rcx, [rbp+7B0h+var_830]; char *
0x1800259e7  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800259ec  test    eax, eax
0x1800259ee  js      short loc_180025A10
0x1800259f0  cmp     cs:Microsoft_Windows_EapHostEnableBits, r12b
0x1800259f7  jge     short loc_180025A10
0x1800259f9  lea     r8, [rbp+7B0h+var_830]
0x1800259fd  lea     rdx, DebugInfoEvent
0x180025a04  lea     rcx, eaphost_Context
0x180025a0b  call    McTemplateU0s_EtwEventWriteTransfer
0x180025a10  lea     rax, WPP_GLOBAL_Control
0x180025a17  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a1e  cmp     rcx, rax
0x180025a21  jz      loc_180025AB9
0x180025a27  test    byte ptr [rcx+1Ch], 4
0x180025a2b  jz      loc_180025AB9
0x180025a31  cmp     [r14], r12
0x180025a34  cmovnz  rsi, [r14]
0x180025a38  mov     edx, 2Dh ; '-'
0x180025a3d  mov     r9, rsi
0x180025a40  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180025a47  mov     rcx, [rcx+10h]
0x180025a4b  call    WPP_SF_S
0x180025a50  jmp     short loc_180025AB9
0x180025a52  lea     rax, WPP_GLOBAL_Control
0x180025a59  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a60  cmp     rcx, rax
0x180025a63  jz      short loc_180025A80
0x180025a65  test    byte ptr [rcx+1Ch], 4
0x180025a69  jz      short loc_180025A80
0x180025a6b  mov     edx, 2Eh ; '.'
0x180025a70  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180025a77  mov     rcx, [rcx+10h]
0x180025a7b  call    WPP_SF_
0x180025a80  test    cs:byte_18004E841, 4
0x180025a87  jz      short loc_180025AA9
0x180025a89  lea     rax, [rsp+8B0h+var_840]
0x180025a8e  mov     [rsp+8B0h+var_890], rax
0x180025a93  mov     r9d, ebx
0x180025a96  lea     rdx, PeerUserEntersCredentials
0x180025a9d  lea     rcx, eaphost_Context
0x180025aa4  call    McGenEventWrite_EtwEventWriteTransfer
0x180025aa9  mov     qword ptr [rdi+104h], 2
0x180025ab4  mov     ebx, 3
0x180025ab9  xor     r9d, r9d; bool
0x180025abc  mov     r8b, [rsp+8B0h+var_860]; bool
0x180025ac1  mov     edx, ebx; enum tagEapHostPeerResponseAction
0x180025ac3  mov     rcx, rdi; struct EapHost::Peer::PeerSession *
0x180025ac6  call    ?WriteEapGetIdentityTelemetry@@YAXAEAVPeerSession@Peer@EapHost@@W4tagEapHostPeerResponseAction@@_N2@Z; WriteEapGetIdentityTelemetry(EapHost::Peer::PeerSession &,tagEapHostPeerResponseAction,bool,bool)
0x180025acb  nop
0x180025acc  mov     rcx, [rsp+8B0h+var_858]; void *
0x180025ad1  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180025ad6  mov     [rsp+8B0h+var_858], r12
0x180025adb  mov     rcx, [rsp+8B0h+var_850]; void *
0x180025ae0  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180025ae5  mov     eax, ebx
0x180025ae7  mov     rcx, [rbp+7B0h+var_30]
0x180025aee  xor     rcx, rsp; StackCookie
0x180025af1  call    __security_check_cookie
0x180025af6  lea     r11, [rsp+8B0h+var_20]
0x180025afe  mov     rbx, [r11+30h]
0x180025b02  mov     rsi, [r11+40h]
0x180025b06  mov     rsp, r11
0x180025b09  pop     r15
0x180025b0b  pop     r14
0x180025b0d  pop     r12
0x180025b0f  pop     rdi
0x180025b10  pop     rbp
0x180025b11  retn
```
