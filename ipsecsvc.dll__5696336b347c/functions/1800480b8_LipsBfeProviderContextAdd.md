# LipsBfeProviderContextAdd

- ea: `0x1800480b8`
- end: `0x1800482d3`
- name: `LipsBfeProviderContextAdd`
- size: `539`
- prototype: `__int64 __fastcall(FWPM_PROVIDER_CONTEXT_TYPE, IPSEC_KEYING_POLICY0 *, GUID *, UINT64 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180045b44`
- `0x180046f60`

## callees

- `0x180009d44`
- `0x18000c4d0`
- `0x18000e510`
- `0x1800480b8`
- `0x180048bd0`
- `0x180048ca4`
- `0x18004d05e`
- `0x18004d090`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800481e6`
- `ntdll!EtwEventWrite` at `0x18004821f`
- `ntdll!EtwEventWrite` at `0x1800481e6`
- `ntdll!EtwEventWrite` at `0x18004821f`
- `RPCRT4!UuidCreate` at `0x180048187`
- `RPCRT4!UuidCreate` at `0x180048187`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x1800481fe`
- `fwpuclnt!FwpmProviderContextAdd0` at `0x1800481fe`

## pseudocode

```c
__int64 __fastcall LipsBfeProviderContextAdd(
        FWPM_PROVIDER_CONTEXT_TYPE a1,
        IPSEC_KEYING_POLICY0 *a2,
        GUID *a3,
        UINT64 *a4)
{
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // r8d
  FWPM_PROVIDER_CONTEXT0 Uuid; // [rsp+30h] [rbp-88h] BYREF

  memset_0(&Uuid, 0, sizeof(Uuid));
  *a3 = 0;
  *a4 = 0;
  v8 = LipsBfeBind();
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_25;
    v10 = 27;
    goto LABEL_5;
  }
  memset_0(&Uuid, 0, sizeof(Uuid));
  Uuid.displayData.name = L"LIPS";
  if ( a1 == FWPM_IPSEC_IKE_QM_TRANSPORT_CONTEXT || a1 == FWPM_IPSEC_IKE_MM_CONTEXT )
    Uuid.keyingPolicy = a2;
  Uuid.type = a1;
  if ( UuidCreate(&Uuid.providerContextKey) )
  {
    v8 = 1003;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_25;
    v10 = 28;
    goto LABEL_5;
  }
  Uuid.providerKey = (GUID *)LipsProviderGuid;
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_BFE_ProviderContextAdd_Begin, 0, 0);
  v8 = FwpmProviderContextAdd0(gLipsBfeEngineHandle, &Uuid, 0, a4);
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_BFE_ProviderContextAdd_End, 0, 0);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_25;
    v10 = 29;
LABEL_5:
    WPP_SF_d(v9[2], v10, WPP_47af9f0627fa340f85c21449576885fa_Traceguids, v8);
    goto LABEL_25;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s_guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      v11,
      (unsigned int)"FwpmProviderContextAdd0",
      (__int64)&Uuid);
  *a3 = Uuid.providerContextKey;
LABEL_25:
  LipsBfeUnbindOnFailure(v8);
  if ( v8 )
    return LipsReportError(v8, "LipsBfeProviderContextAdd");
  else
    return 0;
}

```

## disassembly

```asm
0x1800480b8  mov     [rsp+arg_0], rbx
0x1800480bd  mov     [rsp+arg_8], rbp
0x1800480c2  push    rsi
0x1800480c3  push    rdi
0x1800480c4  push    r14
0x1800480c6  sub     rsp, 0A0h
0x1800480cd  mov     rax, cs:__security_cookie
0x1800480d4  xor     rax, rsp
0x1800480d7  mov     [rsp+0B8h+var_28], rax
0x1800480df  mov     rsi, rdx
0x1800480e2  mov     rbp, r8
0x1800480e5  xor     edx, edx; Val
0x1800480e7  mov     edi, ecx
0x1800480e9  lea     rcx, [rsp+0B8h+Uuid]; void *
0x1800480ee  mov     r14, r9
0x1800480f1  lea     r8d, [rdx+58h]; Size
0x1800480f5  call    memset_0
0x1800480fa  xorps   xmm0, xmm0
0x1800480fd  movups  xmmword ptr [rbp+0], xmm0
0x180048101  mov     qword ptr [r14], 0
0x180048108  call    LipsBfeBind
0x18004810d  mov     ebx, eax
0x18004810f  test    eax, eax
0x180048111  jz      short loc_180048151
0x180048113  mov     rcx, cs:WPP_GLOBAL_Control
0x18004811a  lea     rax, WPP_GLOBAL_Control
0x180048121  cmp     rcx, rax
0x180048124  jz      loc_18004828E
0x18004812a  test    byte ptr [rcx+1Ch], 10h
0x18004812e  jz      loc_18004828E
0x180048134  mov     edx, 1Bh
0x180048139  mov     rcx, [rcx+10h]
0x18004813d  lea     r8, WPP_47af9f0627fa340f85c21449576885fa_Traceguids
0x180048144  mov     r9d, ebx
0x180048147  call    WPP_SF_d
0x18004814c  jmp     loc_18004828E
0x180048151  xor     edx, edx; Val
0x180048153  lea     rcx, [rsp+0B8h+Uuid]; void *
0x180048158  lea     r8d, [rdx+58h]; Size
0x18004815c  call    memset_0
0x180048161  mov     ecx, edi
0x180048163  lea     rax, aLips; "LIPS"
0x18004816a  mov     [rsp+0B8h+var_78], rax
0x18004816f  sub     ecx, 1
0x180048172  jz      short loc_180048179
0x180048174  cmp     ecx, 4
0x180048177  jnz     short loc_18004817E
0x180048179  mov     [rsp+0B8h+var_40], rsi
0x18004817e  lea     rcx, [rsp+0B8h+Uuid]; Uuid
0x180048183  mov     [rsp+0B8h+var_48], edi
0x180048187  call    cs:__imp_UuidCreate
0x18004818d  test    eax, eax
0x18004818f  jz      short loc_1800481C1
0x180048191  mov     ebx, 3EBh
0x180048196  mov     rcx, cs:WPP_GLOBAL_Control
0x18004819d  lea     rax, WPP_GLOBAL_Control
0x1800481a4  cmp     rcx, rax
0x1800481a7  jz      loc_18004828E
0x1800481ad  test    byte ptr [rcx+1Ch], 10h
0x1800481b1  jz      loc_18004828E
0x1800481b7  mov     edx, 1Ch
0x1800481bc  jmp     loc_180048139
0x1800481c1  mov     rcx, cs:g_Provider
0x1800481c8  lea     rax, LipsProviderGuid
0x1800481cf  mov     [rsp+0B8h+var_60], rax
0x1800481d4  test    rcx, rcx
0x1800481d7  jz      short loc_1800481EC
0x1800481d9  xor     r9d, r9d
0x1800481dc  lea     rdx, IPSEC_BFE_ProviderContextAdd_Begin
0x1800481e3  xor     r8d, r8d
0x1800481e6  call    cs:__imp_EtwEventWrite
0x1800481ec  mov     rcx, cs:gLipsBfeEngineHandle; engineHandle
0x1800481f3  lea     rdx, [rsp+0B8h+Uuid]; providerContext
0x1800481f8  mov     r9, r14; id
0x1800481fb  xor     r8d, r8d; sd
0x1800481fe  call    cs:__imp_FwpmProviderContextAdd0
0x180048204  mov     rcx, cs:g_Provider
0x18004820b  mov     ebx, eax
0x18004820d  test    rcx, rcx
0x180048210  jz      short loc_180048225
0x180048212  xor     r9d, r9d
0x180048215  lea     rdx, IPSEC_BFE_ProviderContextAdd_End
0x18004821c  xor     r8d, r8d
0x18004821f  call    cs:__imp_EtwEventWrite
0x180048225  test    ebx, ebx
0x180048227  jz      short loc_18004824C
0x180048229  mov     rcx, cs:WPP_GLOBAL_Control
0x180048230  lea     rax, WPP_GLOBAL_Control
0x180048237  cmp     rcx, rax
0x18004823a  jz      short loc_18004828E
0x18004823c  test    byte ptr [rcx+1Ch], 10h
0x180048240  jz      short loc_18004828E
0x180048242  mov     edx, 1Dh
0x180048247  jmp     loc_180048139
0x18004824c  mov     rcx, cs:WPP_GLOBAL_Control
0x180048253  lea     rax, WPP_GLOBAL_Control
0x18004825a  cmp     rcx, rax
0x18004825d  jz      short loc_180048284
0x18004825f  test    byte ptr [rcx+1Ch], 4
0x180048263  jz      short loc_180048284
0x180048265  mov     rcx, [rcx+10h]
0x180048269  lea     rax, [rsp+0B8h+Uuid]
0x18004826e  mov     edx, 1Eh
0x180048273  mov     [rsp+0B8h+var_98], rax
0x180048278  lea     r9, aFwpmproviderco_0; "FwpmProviderContextAdd0"
0x18004827f  call    WPP_SF_s_guid_
0x180048284  movaps  xmm0, xmmword ptr [rsp+0B8h+Uuid.Data1]
0x180048289  movdqu  xmmword ptr [rbp+0], xmm0
0x18004828e  mov     ecx, ebx
0x180048290  call    LipsBfeUnbindOnFailure
0x180048295  test    ebx, ebx
0x180048297  jnz     short loc_18004829D
0x180048299  xor     eax, eax
0x18004829b  jmp     short loc_1800482AB
0x18004829d  lea     rdx, aLipsbfeprovide; "LipsBfeProviderContextAdd"
0x1800482a4  mov     ecx, ebx
0x1800482a6  call    LipsReportError
0x1800482ab  mov     rcx, [rsp+0B8h+var_28]
0x1800482b3  xor     rcx, rsp; StackCookie
0x1800482b6  call    __security_check_cookie
0x1800482bb  lea     r11, [rsp+0B8h+var_18]
0x1800482c3  mov     rbx, [r11+20h]
0x1800482c7  mov     rbp, [r11+28h]
0x1800482cb  mov     rsp, r11
0x1800482ce  pop     r14
0x1800482d0  pop     rdi
0x1800482d1  pop     rsi
0x1800482d2  retn
```
