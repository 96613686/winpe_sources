# NgcUtils::GetNgcEnabledModifiers

- ea: `0x180009fd4`
- end: `0x18000a172`
- name: `NgcUtils::GetNgcEnabledModifiers`
- size: `414`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a240`
- `0x18002cb98`

## callees

- `0x180006538`
- `0x180006560`
- `0x180006780`
- `0x180008108`
- `0x180008ab4`
- `0x180009fd4`
- `0x1800159a0`
- `0x180018790`
- `0x18001c65c`
- `0x18001df90`
- `0x1800247ec`
- `0x180028360`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a09b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a09b`

## string_xrefs

- `0x18000a012`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x18000a05e`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x18000a0a9`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`
- `0x18000a0fa`: `onecore\ds\security\ngc\utils\common\lib\policyutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcUtils::GetNgcEnabledModifiers(int *a1)
{
  int v2; // eax
  int JoinInfo; // eax
  unsigned int LastError; // ebx
  _QWORD *v5; // rbx
  __int64 v6; // rcx
  int UserSidFromToken; // eax
  int v8; // edi
  const char *v9; // r9
  int Enabled; // eax
  int v12; // [rsp+20h] [rbp-40h]
  int v13; // [rsp+20h] [rbp-40h]
  LPWSTR StringSid; // [rsp+30h] [rbp-30h] BYREF
  void *Block; // [rsp+38h] [rbp-28h] BYREF
  PSID Sid[4]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  char v18; // [rsp+88h] [rbp+28h] BYREF
  char v19; // [rsp+90h] [rbp+30h] BYREF
  char v20; // [rsp+98h] [rbp+38h] BYREF

  v2 = dword_18006EEA4;
  if ( !dword_18006EEA4 )
  {
    Block = 0;
    JoinInfo = DsrGetJoinInfo(a1, &Block);
    LastError = JoinInfo;
    if ( JoinInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
        (const char *)(unsigned int)JoinInfo,
        v12);
LABEL_13:
      wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&Block);
      return LastError;
    }
    v5 = Block;
    if ( !Block || !*(_DWORD *)Block )
    {
      if ( Block )
        DsrFreeJoinInfo(Block);
      return 0;
    }
    std::vector<unsigned char>::vector<unsigned char>(Sid);
    UserSidFromToken = NgcUtils::GetUserSidFromToken(v6, Sid);
    v8 = UserSidFromToken;
    if ( UserSidFromToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
        (const char *)(unsigned int)UserSidFromToken,
        v12);
      std::vector<unsigned char>::_Tidy(Sid);
      LastError = v8;
      goto LABEL_13;
    }
    StringSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    if ( !ConvertSidToStringSidW(Sid[0], &StringSid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x6E,
                    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
                    v9);
LABEL_12:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
      std::vector<unsigned char>::_Tidy(Sid);
      goto LABEL_13;
    }
    dword_18006EEA4 |= 0x20u;
    Enabled = NgcQueryEnabled(
                (_DWORD)StringSid,
                v5[4],
                (unsigned int)&v20,
                (unsigned int)&v19,
                (__int64)&dword_18006EEA4,
                (__int64)&v18);
    LastError = Enabled;
    if ( Enabled < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\policyutils.cpp",
        (const char *)(unsigned int)Enabled,
        v13);
      goto LABEL_12;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
    std::vector<unsigned char>::_Tidy(Sid);
    wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&Block);
    v2 = dword_18006EEA4;
  }
  *a1 = v2;
  return 0;
}

```

## disassembly

```asm
0x180009fd4  mov     [rsp-18h+arg_0], rbx
0x180009fd9  push    rbp
0x180009fda  push    rsi
0x180009fdb  push    rdi
0x180009fdc  mov     rbp, rsp
0x180009fdf  sub     rsp, 60h
0x180009fe3  mov     rsi, rcx
0x180009fe6  mov     eax, cs:dword_18006EEA4
0x180009fec  test    eax, eax
0x180009fee  jnz     loc_18000A14F
0x180009ff4  mov     [rbp+Block], 0
0x180009ffc  lea     rdx, [rbp+Block]
0x18000a000  call    DsrGetJoinInfo
0x18000a005  mov     ebx, eax
0x18000a007  test    eax, eax
0x18000a009  jns     short loc_18000A028
0x18000a00b  mov     rcx, [rbp+18h]; this
0x18000a00f  mov     r9d, eax; char *
0x18000a012  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000a019  mov     edx, 63h ; 'c'; void *
0x18000a01e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a023  jmp     loc_18000A11F
0x18000a028  mov     rbx, [rbp+Block]
0x18000a02c  test    rbx, rbx
0x18000a02f  jz      loc_18000A163
0x18000a035  cmp     dword ptr [rbx], 0
0x18000a038  jz      loc_18000A163
0x18000a03e  lea     rcx, [rbp+Sid]
0x18000a042  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::vector<uchar>(void)
0x18000a047  nop
0x18000a048  lea     rdx, [rbp+Sid]
0x18000a04c  call    NgcUtils__GetUserSidFromToken
0x18000a051  mov     edi, eax
0x18000a053  test    eax, eax
0x18000a055  jns     short loc_18000A080
0x18000a057  mov     rcx, [rbp+18h]; this
0x18000a05b  mov     r9d, eax; char *
0x18000a05e  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000a065  mov     edx, 6Bh ; 'k'; void *
0x18000a06a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a06f  nop
0x18000a070  lea     rcx, [rbp+Sid]
0x18000a074  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000a079  mov     ebx, edi
0x18000a07b  jmp     loc_18000A11F
0x18000a080  mov     [rbp+StringSid], 0
0x18000a088  xor     edx, edx
0x18000a08a  lea     rcx, [rbp+StringSid]
0x18000a08e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000a093  lea     rdx, [rbp+StringSid]; StringSid
0x18000a097  mov     rcx, [rbp+Sid]; Sid
0x18000a09b  call    cs:__imp_ConvertSidToStringSidW
0x18000a0a1  test    eax, eax
0x18000a0a3  jnz     short loc_18000A0BC
0x18000a0a5  mov     rcx, [rbp+18h]; this
0x18000a0a9  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000a0b0  lea     edx, [rax+6Eh]; void *
0x18000a0b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a0b8  mov     ebx, eax
0x18000a0ba  jmp     short loc_18000A10B
0x18000a0bc  or      cs:dword_18006EEA4, 20h
0x18000a0c3  lea     rax, [rbp+arg_8]
0x18000a0c7  mov     [rsp+60h+var_38], rax
0x18000a0cc  lea     rax, dword_18006EEA4
0x18000a0d3  mov     qword ptr [rsp+60h+var_40], rax; int
0x18000a0d8  lea     r9, [rbp+arg_10]
0x18000a0dc  lea     r8, [rbp+arg_18]
0x18000a0e0  mov     rdx, [rbx+20h]
0x18000a0e4  mov     rcx, [rbp+StringSid]
0x18000a0e8  call    NgcQueryEnabled
0x18000a0ed  mov     ebx, eax
0x18000a0ef  test    eax, eax
0x18000a0f1  jns     short loc_18000A12C
0x18000a0f3  mov     rcx, [rbp+18h]; this
0x18000a0f7  mov     r9d, eax; char *
0x18000a0fa  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000a101  mov     edx, 7Ah ; 'z'; void *
0x18000a106  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a10b  lea     rcx, [rbp+StringSid]; void *
0x18000a10f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000a114  nop
0x18000a115  lea     rcx, [rbp+Sid]
0x18000a119  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000a11e  nop
0x18000a11f  lea     rcx, [rbp+Block]
0x18000a123  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x18000a128  mov     eax, ebx
0x18000a12a  jmp     short loc_18000A153
0x18000a12c  lea     rcx, [rbp+StringSid]; void *
0x18000a130  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000a135  nop
0x18000a136  lea     rcx, [rbp+Sid]
0x18000a13a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000a13f  nop
0x18000a140  lea     rcx, [rbp+Block]
0x18000a144  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x18000a149  mov     eax, cs:dword_18006EEA4
0x18000a14f  mov     [rsi], eax
0x18000a151  xor     eax, eax
0x18000a153  mov     rbx, [rsp+60h+arg_0]
0x18000a15b  add     rsp, 60h
0x18000a15f  pop     rdi
0x18000a160  pop     rsi
0x18000a161  pop     rbp
0x18000a162  retn
0x18000a163  test    rbx, rbx
0x18000a166  jz      short loc_18000A151
0x18000a168  mov     rcx, rbx; Block
0x18000a16b  call    DsrFreeJoinInfo
0x18000a170  jmp     short loc_18000A151
```
