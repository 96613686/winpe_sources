# container::NetworkProvider::SetupCompartment(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *)

- ea: `0x1800263f4`
- end: `0x18002652d`
- name: `?SetupCompartment@NetworkProvider@container@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z`
- size: `313`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800063f0`

## callees

- `0x180002ad0`
- `0x18000362c`
- `0x180006e98`
- `0x180012b10`
- `0x18002627c`
- `0x1800263f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180026472`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180026472`
- `IPHLPAPI!SetJobCompartmentId` at `0x1800264b9`
- `IPHLPAPI!SetJobCompartmentId` at `0x1800264b9`
- `IPHLPAPI!InitializeCompartmentEntry` at `0x18002643c`
- `IPHLPAPI!InitializeCompartmentEntry` at `0x18002643c`
- `IPHLPAPI!CreateCompartment` at `0x18002648a`
- `IPHLPAPI!CreateCompartment` at `0x18002648a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall container::NetworkProvider::SetupCompartment(_QWORD *a1, container_runtime *a2)
{
  unsigned int Compartment; // eax
  unsigned int v5; // eax
  unsigned int v7[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int16 v8; // [rsp+28h] [rbp-D8h]
  unsigned int v9[5]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[516]; // [rsp+44h] [rbp-BCh] BYREF
  char v11; // [rsp+248h] [rbp+148h]
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  memset_0(v9, 0, 0x21Cu);
  InitializeCompartmentEntry(v9);
  container_runtime::GetContainerIdentifier(a2, v9, 0, 0, *(unsigned int **)v7);
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  _o_wcscpy_s(v10, 257, a1);
  v11 |= 1u;
  Compartment = CreateCompartment(v9);
  if ( Compartment )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\network_provider.cpp",
      (const char *)Compartment,
      v7[0]);
  *(_QWORD *)v7 = v9;
  v8 = 257;
  v5 = SetJobCompartmentId(a2, v9[4]);
  if ( v5 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\network_provider.cpp",
      (const char *)v5,
      v7[0]);
  HIBYTE(v8) = 0;
  return wil::details::ScopeExitFnGuard__lambda_47272fddd909adeb429bad6d42265b19___::operator()(v7);
}

```

## disassembly

```asm
0x1800263f4  mov     [rsp-8+arg_10], rbx
0x1800263f9  mov     [rsp-8+arg_18], rdi
0x1800263fe  push    rbp
0x1800263ff  lea     rbp, [rsp-160h]
0x180026407  sub     rsp, 260h
0x18002640e  mov     rax, cs:__security_cookie
0x180026415  xor     rax, rsp
0x180026418  mov     [rbp+160h+var_10], rax
0x18002641f  mov     rdi, rdx
0x180026422  mov     rbx, rcx
0x180026425  xor     edx, edx; Val
0x180026427  mov     r8d, 21Ch; Size
0x18002642d  lea     rcx, [rsp+260h+var_230]; void *
0x180026432  call    memset_0
0x180026437  lea     rcx, [rsp+260h+var_230]
0x18002643c  call    cs:__imp_InitializeCompartmentEntry
0x180026443  nop     dword ptr [rax+rax+00h]
0x180026448  xor     r9d, r9d; struct _GUID *
0x18002644b  xor     r8d, r8d; struct _GUID *
0x18002644e  lea     rdx, [rsp+260h+var_230]; void *
0x180026453  mov     rcx, rdi; this
0x180026456  call    ?GetContainerIdentifier@container_runtime@@YAXPEAXPEAU_GUID@@1PEAK@Z; container_runtime::GetContainerIdentifier(void *,_GUID *,_GUID *,ulong *)
0x18002645b  cmp     qword ptr [rbx+18h], 7
0x180026460  jbe     short loc_180026465
0x180026462  mov     rbx, [rbx]
0x180026465  mov     r8, rbx
0x180026468  mov     edx, 101h
0x18002646d  lea     rcx, [rsp+260h+var_21C]
0x180026472  call    cs:__imp__o_wcscpy_s
0x180026479  nop     dword ptr [rax+rax+00h]
0x18002647e  or      [rbp+160h+var_18], 1
0x180026485  lea     rcx, [rsp+260h+var_230]
0x18002648a  call    cs:__imp_CreateCompartment
0x180026491  nop     dword ptr [rax+rax+00h]
0x180026496  mov     rcx, [rbp+168h]; this
0x18002649d  test    eax, eax
0x18002649f  jnz     short loc_180026518
0x1800264a1  lea     rax, [rsp+260h+var_230]
0x1800264a6  mov     qword ptr [rsp+260h+var_240], rax; unsigned int
0x1800264ab  mov     [rsp+260h+var_238], 101h
0x1800264b2  mov     edx, [rsp+260h+CompartmentId]; CompartmentId
0x1800264b6  mov     rcx, rdi; JobHandle
0x1800264b9  call    cs:__imp_SetJobCompartmentId
0x1800264c0  nop     dword ptr [rax+rax+00h]
0x1800264c5  mov     rcx, [rbp+168h]; this
0x1800264cc  test    eax, eax
0x1800264ce  jnz     short loc_180026503
0x1800264d0  mov     byte ptr [rsp+260h+var_238+1], al
0x1800264d4  lea     rcx, [rsp+260h+var_240]
0x1800264d9  call    wil__details__ScopeExitFnGuard__lambda_47272fddd909adeb429bad6d42265b19_____operator__
0x1800264de  mov     rcx, [rbp+160h+var_10]
0x1800264e5  xor     rcx, rsp; StackCookie
0x1800264e8  call    __security_check_cookie
0x1800264ed  lea     r11, [rsp+260h+var_s0]
0x1800264f5  mov     rbx, [r11+20h]
0x1800264f9  mov     rdi, [r11+28h]
0x1800264fd  mov     rsp, r11
0x180026500  pop     rbp
0x180026501  retn
0x180026503  mov     r9d, eax; char *
0x180026506  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\container"...
0x18002650d  mov     edx, 61h ; 'a'; void *
0x180026512  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180026518  mov     r9d, eax; char *
0x18002651b  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\container"...
0x180026522  mov     edx, 55h ; 'U'; void *
0x180026527  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
