# EapHost::Peer::Host::GetIdentity(EapHost::Peer::PeerSession &)

- ea: `0x180026488`
- end: `0x180026847`
- name: `?GetIdentity@Host@Peer@EapHost@@AEAA?AW4tagEapHostPeerResponseAction@@AEAVPeerSession@23@@Z`
- size: `959`
- prototype: `enum tagEapHostPeerResponseAction(EapHost::Peer::Host *__hidden this, struct EapHost::Peer::PeerSession *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027708`

## callees

- `0x180002af0`
- `0x180005410`
- `0x180007564`
- `0x180009fe4`
- `0x18000a21c`
- `0x18000a3e4`
- `0x180011cb8`
- `0x1800120c4`
- `0x180026488`
- `0x18002b9c0`
- `0x180030b08`
- `0x180030f54`
- `0x180039010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180026560`
- `ntdll!EtwEventEnabled` at `0x1800266f1`
- `ntdll!EtwEventEnabled` at `0x180026560`
- `ntdll!EtwEventEnabled` at `0x1800266f1`

## string_xrefs

- `0x180026570`: `Returning NULL identity for Guest access`

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
  __int64 v17; // [rsp+68h] [rbp-98h]
  _QWORD v18[2]; // [rsp+70h] [rbp-90h] BYREF
  char v19[2048]; // [rsp+80h] [rbp-80h] BYREF

  LOBYTE(a3) = 0;
  v14[0] = 0;
  if ( !*((_BYTE *)a2 + 132) )
  {
    *(_QWORD *)((char *)a2 + 260) = 2;
    if ( (byte_18004F981 & 4) != 0 )
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
    BasicSimpleString<wchar_t>::Assign((char *)a2 + 312, 0);
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
    if ( (byte_18004F981 & 4) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(&eaphost_Context, (__int64)PeerUserEntersCredentials, v8, 1, (__int64)v18);
    *(_QWORD *)((char *)a2 + 260) = 2;
    v5 = EapHostPeerResponseInvokeUi;
  }
  else
  {
    if ( (byte_18004F981 & 4) != 0 )
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
    BasicSimpleString<wchar_t>::Assign((char *)a2 + 312, v10);
    TempBuffer<0>::Assign(v7, v17);
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
0x180026488  mov     [rsp-8+arg_0], rbx
0x18002648d  mov     [rsp-8+arg_10], rsi
0x180026492  push    rbp
0x180026493  push    rdi
0x180026494  push    r12
0x180026496  push    r14
0x180026498  push    r15
0x18002649a  lea     rbp, [rsp-790h]
0x1800264a2  sub     rsp, 890h
0x1800264a9  mov     rax, cs:__security_cookie
0x1800264b0  xor     rax, rsp
0x1800264b3  mov     [rbp+7B0h+var_30], rax
0x1800264ba  mov     rdi, rdx
0x1800264bd  xor     r12d, r12d
0x1800264c0  mov     r8b, r12b
0x1800264c3  mov     [rsp+8B0h+var_860], r12b
0x1800264c8  cmp     [rdx+84h], r12b
0x1800264cf  jnz     short loc_180026522
0x1800264d1  mov     qword ptr [rdx+104h], 2
0x1800264dc  test    cs:byte_18004F981, 4
0x1800264e3  jz      short loc_18002650C
0x1800264e5  lea     rax, [rsp+8B0h+var_850]
0x1800264ea  mov     [rsp+8B0h+var_890], rax
0x1800264ef  lea     r9d, [r12+1]
0x1800264f4  lea     rdx, PeerUserEntersCredentials
0x1800264fb  lea     rcx, eaphost_Context
0x180026502  call    McGenEventWrite_EtwEventWriteTransfer
0x180026507  mov     r8b, [rsp+8B0h+var_860]; bool
0x18002650c  xor     r9d, r9d; bool
0x18002650f  lea     ebx, [r9+3]
0x180026513  mov     edx, ebx; enum tagEapHostPeerResponseAction
0x180026515  mov     rcx, rdi; struct EapHost::Peer::PeerSession *
0x180026518  call    ?WriteEapGetIdentityTelemetry@@YAXAEAVPeerSession@Peer@EapHost@@W4tagEapHostPeerResponseAction@@_N2@Z; WriteEapGetIdentityTelemetry(EapHost::Peer::PeerSession &,tagEapHostPeerResponseAction,bool,bool)
0x18002651d  jmp     loc_180026819
0x180026522  test    byte ptr [rdx+80h], 40h
0x180026529  jz      loc_1800265E4
0x18002652f  lea     rcx, [rdx+138h]
0x180026536  xor     edx, edx
0x180026538  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x18002653d  mov     dword ptr [rdi+108h], 6
0x180026547  mov     ebx, 1
0x18002654c  mov     [rdi+104h], ebx
0x180026552  lea     rdx, DebugInfoEvent
0x180026559  mov     rcx, cs:eaphost_Context
0x180026560  call    cs:__imp_EtwEventEnabled
0x180026567  nop     dword ptr [rax+rax+00h]
0x18002656c  test    al, al
0x18002656e  jz      short loc_1800265A9
0x180026570  lea     r8, aReturningNullI; "Returning NULL identity for Guest acces"...
0x180026577  mov     edx, 800h; unsigned __int64
0x18002657c  lea     rcx, [rbp+7B0h+var_830]; char *
0x180026580  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180026585  test    eax, eax
0x180026587  js      short loc_1800265A9
0x180026589  cmp     cs:Microsoft_Windows_EapHostEnableBits, r12b
0x180026590  jge     short loc_1800265A9
0x180026592  lea     r8, [rbp+7B0h+var_830]
0x180026596  lea     rdx, DebugInfoEvent
0x18002659d  lea     rcx, eaphost_Context
0x1800265a4  call    McTemplateU0s_EtwEventWriteTransfer
0x1800265a9  lea     rax, WPP_GLOBAL_Control
0x1800265b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800265b7  cmp     rcx, rax
0x1800265ba  jz      short loc_1800265D7
0x1800265bc  test    byte ptr [rcx+1Ch], 4
0x1800265c0  jz      short loc_1800265D7
0x1800265c2  mov     edx, 2Ch ; ','
0x1800265c7  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x1800265ce  mov     rcx, [rcx+10h]
0x1800265d2  call    WPP_SF_
0x1800265d7  mov     r9b, bl
0x1800265da  mov     r8b, [rsp+8B0h+var_860]
0x1800265df  jmp     loc_180026513
0x1800265e4  mov     [rsp+8B0h+var_850], r12
0x1800265e9  mov     [rsp+8B0h+var_848], r12
0x1800265ee  mov     [rsp+8B0h+var_858], r12
0x1800265f3  mov     rsi, [rdx+120h]
0x1800265fa  mov     [rsp+8B0h+var_840], rsi
0x1800265ff  mov     ebx, 1
0x180026604  test    rsi, rsi
0x180026607  jz      short loc_18002660D
0x180026609  lock add [rsi+8], ebx
0x18002660d  lea     r15, [rdx+0E0h]
0x180026614  mov     rax, [rsi]
0x180026617  lea     r9, [rdx+0D0h]
0x18002661e  lea     r8, [rdx+0C0h]
0x180026625  lea     rcx, [rsp+8B0h+var_860]
0x18002662a  mov     [rsp+8B0h+var_878], rcx
0x18002662f  lea     rcx, [rsp+8B0h+var_858]
0x180026634  mov     [rsp+8B0h+var_880], rcx
0x180026639  lea     rcx, [rsp+8B0h+var_850]
0x18002663e  mov     [rsp+8B0h+var_888], rcx
0x180026643  mov     [rsp+8B0h+var_890], r15
0x180026648  mov     edx, [rdx+80h]
0x18002664e  mov     rcx, rsi
0x180026651  mov     rax, [rax+20h]
0x180026655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002665a  nop
0x18002665b  test    rsi, rsi
0x18002665e  jz      short loc_180026668
0x180026660  mov     rcx, rsi; this
0x180026663  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x180026668  cmp     [rsp+8B0h+var_860], r12b
0x18002666d  jnz     loc_180026786
0x180026673  test    cs:byte_18004F981, 4
0x18002667a  jz      short loc_18002669C
0x18002667c  lea     rax, [rsp+8B0h+var_840]
0x180026681  mov     [rsp+8B0h+var_890], rax
0x180026686  mov     r9d, ebx
0x180026689  lea     rdx, PeerUserUsesSavedCredentials
0x180026690  lea     rcx, eaphost_Context
0x180026697  call    McGenEventWrite_EtwEventWriteTransfer
0x18002669c  mov     rax, [rsp+8B0h+var_858]
0x1800266a1  lea     rsi, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x1800266a8  mov     rdx, rsi
0x1800266ab  test    rax, rax
0x1800266ae  cmovnz  rdx, rax
0x1800266b2  lea     r14, [rdi+138h]
0x1800266b9  mov     rcx, r14
0x1800266bc  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x1800266c1  mov     r8, [rsp+8B0h+var_850]
0x1800266c6  mov     rdx, [rsp+8B0h+var_848]
0x1800266cb  mov     rcx, r15
0x1800266ce  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x1800266d3  mov     dword ptr [rdi+108h], 6
0x1800266dd  mov     [rdi+104h], ebx
0x1800266e3  lea     rdx, DebugInfoEvent
0x1800266ea  mov     rcx, cs:eaphost_Context
0x1800266f1  call    cs:__imp_EtwEventEnabled
0x1800266f8  nop     dword ptr [rax+rax+00h]
0x1800266fd  test    al, al
0x1800266ff  jz      short loc_180026744
0x180026701  mov     r9, rsi
0x180026704  cmp     [r14], r12
0x180026707  cmovnz  r9, [r14]
0x18002670b  lea     r8, aGetidentityRet; "GetIdentity returning %S"
0x180026712  mov     edx, 800h; unsigned __int64
0x180026717  lea     rcx, [rbp+7B0h+var_830]; char *
0x18002671b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180026720  test    eax, eax
0x180026722  js      short loc_180026744
0x180026724  cmp     cs:Microsoft_Windows_EapHostEnableBits, r12b
0x18002672b  jge     short loc_180026744
0x18002672d  lea     r8, [rbp+7B0h+var_830]
0x180026731  lea     rdx, DebugInfoEvent
0x180026738  lea     rcx, eaphost_Context
0x18002673f  call    McTemplateU0s_EtwEventWriteTransfer
0x180026744  lea     rax, WPP_GLOBAL_Control
0x18002674b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026752  cmp     rcx, rax
0x180026755  jz      loc_1800267ED
0x18002675b  test    byte ptr [rcx+1Ch], 4
0x18002675f  jz      loc_1800267ED
0x180026765  cmp     [r14], r12
0x180026768  cmovnz  rsi, [r14]
0x18002676c  mov     edx, 2Dh ; '-'
0x180026771  mov     r9, rsi
0x180026774  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x18002677b  mov     rcx, [rcx+10h]
0x18002677f  call    WPP_SF_S
0x180026784  jmp     short loc_1800267ED
0x180026786  lea     rax, WPP_GLOBAL_Control
0x18002678d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026794  cmp     rcx, rax
0x180026797  jz      short loc_1800267B4
0x180026799  test    byte ptr [rcx+1Ch], 4
0x18002679d  jz      short loc_1800267B4
0x18002679f  mov     edx, 2Eh ; '.'
0x1800267a4  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x1800267ab  mov     rcx, [rcx+10h]
0x1800267af  call    WPP_SF_
0x1800267b4  test    cs:byte_18004F981, 4
0x1800267bb  jz      short loc_1800267DD
0x1800267bd  lea     rax, [rsp+8B0h+var_840]
0x1800267c2  mov     [rsp+8B0h+var_890], rax
0x1800267c7  mov     r9d, ebx
0x1800267ca  lea     rdx, PeerUserEntersCredentials
0x1800267d1  lea     rcx, eaphost_Context
0x1800267d8  call    McGenEventWrite_EtwEventWriteTransfer
0x1800267dd  mov     qword ptr [rdi+104h], 2
0x1800267e8  mov     ebx, 3
0x1800267ed  xor     r9d, r9d; bool
0x1800267f0  mov     r8b, [rsp+8B0h+var_860]; bool
0x1800267f5  mov     edx, ebx; enum tagEapHostPeerResponseAction
0x1800267f7  mov     rcx, rdi; struct EapHost::Peer::PeerSession *
0x1800267fa  call    ?WriteEapGetIdentityTelemetry@@YAXAEAVPeerSession@Peer@EapHost@@W4tagEapHostPeerResponseAction@@_N2@Z; WriteEapGetIdentityTelemetry(EapHost::Peer::PeerSession &,tagEapHostPeerResponseAction,bool,bool)
0x1800267ff  nop
0x180026800  mov     rcx, [rsp+8B0h+var_858]; void *
0x180026805  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002680a  mov     [rsp+8B0h+var_858], r12
0x18002680f  mov     rcx, [rsp+8B0h+var_850]; void *
0x180026814  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180026819  mov     eax, ebx
0x18002681b  mov     rcx, [rbp+7B0h+var_30]
0x180026822  xor     rcx, rsp; StackCookie
0x180026825  call    __security_check_cookie
0x18002682a  lea     r11, [rsp+8B0h+var_20]
0x180026832  mov     rbx, [r11+30h]
0x180026836  mov     rsi, [r11+40h]
0x18002683a  mov     rsp, r11
0x18002683d  pop     r15
0x18002683f  pop     r14
0x180026841  pop     r12
0x180026843  pop     rdi
0x180026844  pop     rbp
0x180026845  retn
```
