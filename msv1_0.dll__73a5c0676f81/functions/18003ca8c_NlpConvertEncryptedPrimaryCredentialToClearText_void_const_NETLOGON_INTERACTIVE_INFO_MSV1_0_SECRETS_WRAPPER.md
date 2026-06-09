# NlpConvertEncryptedPrimaryCredentialToClearText(void * const &,_NETLOGON_INTERACTIVE_INFO &,_MSV1_0_SECRETS_WRAPPER &)

- ea: `0x18003ca8c`
- end: `0x18003cd29`
- name: `?NlpConvertEncryptedPrimaryCredentialToClearText@@YAJAEBQEAXAEAU_NETLOGON_INTERACTIVE_INFO@@AEAU_MSV1_0_SECRETS_WRAPPER@@@Z`
- size: `669`
- prototype: `__int64 __fastcall(void *const *, struct _NETLOGON_INTERACTIVE_INFO *, struct _MSV1_0_SECRETS_WRAPPER *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a470`

## callees

- `0x18002f014`
- `0x18003ca8c`
- `0x18005c19c`
- `0x18006d010`

## import_xrefs

- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18003cba8`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18003cc49`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18003cc84`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18003ccc4`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18003ccf5`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18003cba8`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18003cc49`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18003cc84`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18003ccc4`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18003ccf5`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18003cb98`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18003cc39`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18003cc74`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18003ccb4`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18003cce5`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18003cb98`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18003cc39`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18003cc74`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18003ccb4`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18003cce5`
- `SAMSRV!SamrCloseHandle` at `0x18003cbb8`
- `SAMSRV!SamrCloseHandle` at `0x18003cc59`
- `SAMSRV!SamrCloseHandle` at `0x18003cc94`
- `SAMSRV!SamrCloseHandle` at `0x18003ccd4`
- `SAMSRV!SamrCloseHandle` at `0x18003cd05`
- `SAMSRV!SamrCloseHandle` at `0x18003cbb8`
- `SAMSRV!SamrCloseHandle` at `0x18003cc59`
- `SAMSRV!SamrCloseHandle` at `0x18003cc94`
- `SAMSRV!SamrCloseHandle` at `0x18003ccd4`
- `SAMSRV!SamrCloseHandle` at `0x18003cd05`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x18003cb83`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x18003cb83`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NlpConvertEncryptedPrimaryCredentialToClearText(
        void *const *a1,
        struct _NETLOGON_INTERACTIVE_INFO *a2,
        struct _MSV1_0_SECRETS_WRAPPER *a3)
{
  __int64 v5; // rdx
  int v6; // edi
  __int64 v8; // rdx
  __int64 v9; // [rsp+50h] [rbp-9h] BYREF
  __int128 v10; // [rsp+58h] [rbp-1h] BYREF
  __int128 v11; // [rsp+68h] [rbp+Fh] BYREF
  __int64 *v12; // [rsp+78h] [rbp+1Fh]
  __int128 *v13; // [rsp+80h] [rbp+27h]
  __int64 *v14; // [rsp+88h] [rbp+2Fh]
  char v15; // [rsp+90h] [rbp+37h]
  __int64 v16; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( (dword_180087A84 & 0x20) == 0 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids);
    return 3221225659LL;
  }
  if ( !*((_BYTE *)a3 + 8) || !*((_BYTE *)a3 + 9) )
    return 3221225659LL;
  v9 = 0;
  v10 = 0;
  v16 = 0;
  v12 = &v9;
  v13 = &v10;
  v14 = &v16;
  v15 = 1;
  v6 = SamIGetUserLogonInformation2(
         *a1,
         0,
         &a2->Identity.UserName,
         557838287,
         NlpWorkstation != 0 ? 0x100000 : 0x2000000,
         0,
         &v9,
         &v10,
         &v16);
  if ( v6 < 0 )
  {
    if ( v9 )
      SamIFree_UserInternal6Information(v9);
    if ( *((_QWORD *)&v10 + 1) )
      SamIFreeSidAndAttributesList(&v10, v5);
    if ( v16 )
      SamrCloseHandle(&v16);
    return (unsigned int)v6;
  }
  if ( !*(_BYTE *)(v9 + 313) || *(_WORD *)(v9 + 224) != 16 )
  {
    if ( v9 )
      SamIFree_UserInternal6Information(v9);
    if ( *((_QWORD *)&v10 + 1) )
      SamIFreeSidAndAttributesList(&v10, v5);
    if ( v16 )
      SamrCloseHandle(&v16);
    return 3221225659LL;
  }
  v11 = 0;
  *((_QWORD *)&v11 + 1) = *(_QWORD *)(v9 + 232);
  LODWORD(v11) = *(_DWORD *)(v9 + 224);
  v6 = (*(__int64 (__fastcall **)(struct NtlmCredIsoApi *, __int128 *, struct _MSV1_0_SECRETS_WRAPPER *))(*(_QWORD *)LocalhostNtLmCredIsoObj::IsoObj + 168LL))(
         LocalhostNtLmCredIsoObj::IsoObj,
         &v11,
         a3);
  if ( v6 < 0 )
  {
    if ( v9 )
      SamIFree_UserInternal6Information(v9);
    if ( *((_QWORD *)&v10 + 1) )
      SamIFreeSidAndAttributesList(&v10, v8);
    if ( v16 )
      SamrCloseHandle(&v16);
    return (unsigned int)v6;
  }
  if ( !*((_BYTE *)a3 + 8) )
  {
    a2->NtOwfPassword = *(NT_OWF_PASSWORD *)((char *)a3 + 38);
    if ( v9 )
      SamIFree_UserInternal6Information(v9);
    if ( *((_QWORD *)&v10 + 1) )
      SamIFreeSidAndAttributesList(&v10, v8);
    if ( v16 )
      SamrCloseHandle(&v16);
    return (unsigned int)v6;
  }
  if ( v9 )
    SamIFree_UserInternal6Information(v9);
  if ( *((_QWORD *)&v10 + 1) )
    SamIFreeSidAndAttributesList(&v10, v8);
  if ( v16 )
    SamrCloseHandle(&v16);
  return 3221225701LL;
}

```

## disassembly

```asm
0x18003ca8c  mov     [rsp-8+arg_0], rbx
0x18003ca91  mov     [rsp-8+arg_8], rsi
0x18003ca96  push    rbp
0x18003ca97  push    rdi
0x18003ca98  push    r14
0x18003ca9a  lea     rbp, [rsp-47h]
0x18003ca9f  sub     rsp, 0A0h
0x18003caa6  mov     rbx, r8
0x18003caa9  mov     rsi, rdx
0x18003caac  mov     r10, rcx
0x18003caaf  test    byte ptr cs:dword_180087A84, 20h
0x18003cab6  jnz     short loc_18003CAF8
0x18003cab8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003cabd  lea     rax, WPP_GLOBAL_Control
0x18003cac4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cacb  cmp     rcx, rax
0x18003cace  jz      loc_18003CD0C
0x18003cad4  test    byte ptr [rcx+1Ch], 1
0x18003cad8  jz      loc_18003CD0C
0x18003cade  mov     edx, 48h ; 'H'
0x18003cae3  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x18003caea  mov     rcx, [rcx+10h]
0x18003caee  call    WPP_SF_
0x18003caf3  jmp     loc_18003CD0C
0x18003caf8  xor     r14d, r14d
0x18003cafb  cmp     [r8+8], r14b
0x18003caff  jz      loc_18003CD0C
0x18003cb05  cmp     [r8+9], r14b
0x18003cb09  jz      loc_18003CD0C
0x18003cb0f  mov     [rbp+57h+var_60], r14
0x18003cb13  xorps   xmm0, xmm0
0x18003cb16  movups  [rbp+57h+var_58], xmm0
0x18003cb1a  mov     [rbp+57h+arg_18], r14
0x18003cb1e  lea     rax, [rbp+57h+var_60]
0x18003cb22  mov     [rbp+57h+var_38], rax
0x18003cb26  lea     rax, [rbp+57h+var_58]
0x18003cb2a  mov     [rbp+57h+var_30], rax
0x18003cb2e  lea     rax, [rbp+57h+arg_18]
0x18003cb32  mov     [rbp+57h+var_28], rax
0x18003cb36  mov     [rbp+57h+var_20], 1
0x18003cb3a  mov     al, cs:NlpWorkstation
0x18003cb40  neg     al
0x18003cb42  sbb     ecx, ecx
0x18003cb44  and     ecx, 0FE100000h
0x18003cb4a  add     ecx, 2000000h
0x18003cb50  lea     r8, [rdx+20h]
0x18003cb54  lea     rax, [rbp+57h+arg_18]
0x18003cb58  mov     [rsp+0B0h+var_70], rax
0x18003cb5d  lea     rax, [rbp+57h+var_58]
0x18003cb61  mov     [rsp+0B0h+var_78], rax
0x18003cb66  lea     rax, [rbp+57h+var_60]
0x18003cb6a  mov     [rsp+0B0h+var_80], rax
0x18003cb6f  mov     [rsp+0B0h+var_88], r14
0x18003cb74  mov     [rsp+0B0h+var_90], ecx
0x18003cb78  xor     edx, edx
0x18003cb7a  mov     r9d, 213FEFCFh
0x18003cb80  mov     rcx, [r10]
0x18003cb83  call    cs:__imp_SamIGetUserLogonInformation2
0x18003cb89  mov     edi, eax
0x18003cb8b  test    eax, eax
0x18003cb8d  jns     short loc_18003CBC6
0x18003cb8f  mov     rcx, [rbp+57h+var_60]
0x18003cb93  test    rcx, rcx
0x18003cb96  jz      short loc_18003CB9E
0x18003cb98  call    cs:__imp_SamIFree_UserInternal6Information
0x18003cb9e  cmp     qword ptr [rbp+57h+var_58+8], r14
0x18003cba2  jz      short loc_18003CBAE
0x18003cba4  lea     rcx, [rbp+57h+var_58]
0x18003cba8  call    cs:__imp_SamIFreeSidAndAttributesList
0x18003cbae  cmp     [rbp+57h+arg_18], r14
0x18003cbb2  jz      short loc_18003CBBF
0x18003cbb4  lea     rcx, [rbp+57h+arg_18]
0x18003cbb8  call    cs:__imp_SamrCloseHandle
0x18003cbbe  nop
0x18003cbbf  mov     eax, edi
0x18003cbc1  jmp     loc_18003CD11
0x18003cbc6  mov     rcx, [rbp+57h+var_60]
0x18003cbca  cmp     [rcx+139h], r14b
0x18003cbd1  jz      loc_18003CCE0
0x18003cbd7  cmp     word ptr [rcx+0E0h], 10h
0x18003cbdf  jnz     loc_18003CCE0
0x18003cbe5  xorps   xmm0, xmm0
0x18003cbe8  movups  [rbp+57h+var_48], xmm0
0x18003cbec  mov     rax, [rcx+0E8h]
0x18003cbf3  mov     qword ptr [rbp+57h+var_48+8], rax
0x18003cbf7  movzx   eax, word ptr [rcx+0E0h]
0x18003cbfe  mov     word ptr [rbp+57h+var_48], ax
0x18003cc02  movzx   eax, word ptr [rcx+0E2h]
0x18003cc09  mov     word ptr [rbp+57h+var_48+2], ax
0x18003cc0d  mov     rcx, cs:?IsoObj@LocalhostNtLmCredIsoObj@@0PEAVNtlmCredIsoApi@@EA; NtlmCredIsoApi * LocalhostNtLmCredIsoObj::IsoObj
0x18003cc14  mov     rax, [rcx]
0x18003cc17  mov     r8, rbx
0x18003cc1a  lea     rdx, [rbp+57h+var_48]
0x18003cc1e  mov     rax, [rax+0A8h]
0x18003cc25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc2a  mov     edi, eax
0x18003cc2c  test    eax, eax
0x18003cc2e  jns     short loc_18003CC65
0x18003cc30  mov     rcx, [rbp+57h+var_60]
0x18003cc34  test    rcx, rcx
0x18003cc37  jz      short loc_18003CC3F
0x18003cc39  call    cs:__imp_SamIFree_UserInternal6Information
0x18003cc3f  cmp     qword ptr [rbp+57h+var_58+8], r14
0x18003cc43  jz      short loc_18003CC4F
0x18003cc45  lea     rcx, [rbp+57h+var_58]
0x18003cc49  call    cs:__imp_SamIFreeSidAndAttributesList
0x18003cc4f  cmp     [rbp+57h+arg_18], r14
0x18003cc53  jz      short loc_18003CC60
0x18003cc55  lea     rcx, [rbp+57h+arg_18]
0x18003cc59  call    cs:__imp_SamrCloseHandle
0x18003cc5f  nop
0x18003cc60  jmp     loc_18003CBBF
0x18003cc65  cmp     [rbx+8], r14b
0x18003cc69  jz      short loc_18003CCA2
0x18003cc6b  mov     rcx, [rbp+57h+var_60]
0x18003cc6f  test    rcx, rcx
0x18003cc72  jz      short loc_18003CC7A
0x18003cc74  call    cs:__imp_SamIFree_UserInternal6Information
0x18003cc7a  cmp     qword ptr [rbp+57h+var_58+8], r14
0x18003cc7e  jz      short loc_18003CC8A
0x18003cc80  lea     rcx, [rbp+57h+var_58]
0x18003cc84  call    cs:__imp_SamIFreeSidAndAttributesList
0x18003cc8a  cmp     [rbp+57h+arg_18], r14
0x18003cc8e  jz      short loc_18003CC9B
0x18003cc90  lea     rcx, [rbp+57h+arg_18]
0x18003cc94  call    cs:__imp_SamrCloseHandle
0x18003cc9a  nop
0x18003cc9b  mov     eax, 0C00000E5h
0x18003cca0  jmp     short loc_18003CD11
0x18003cca2  movups  xmm0, xmmword ptr [rbx+26h]
0x18003cca6  movdqu  xmmword ptr [rsi+50h], xmm0
0x18003ccab  mov     rcx, [rbp+57h+var_60]
0x18003ccaf  test    rcx, rcx
0x18003ccb2  jz      short loc_18003CCBA
0x18003ccb4  call    cs:__imp_SamIFree_UserInternal6Information
0x18003ccba  cmp     qword ptr [rbp+57h+var_58+8], r14
0x18003ccbe  jz      short loc_18003CCCA
0x18003ccc0  lea     rcx, [rbp+57h+var_58]
0x18003ccc4  call    cs:__imp_SamIFreeSidAndAttributesList
0x18003ccca  cmp     [rbp+57h+arg_18], r14
0x18003ccce  jz      short loc_18003CCDB
0x18003ccd0  lea     rcx, [rbp+57h+arg_18]
0x18003ccd4  call    cs:__imp_SamrCloseHandle
0x18003ccda  nop
0x18003ccdb  jmp     loc_18003CBBF
0x18003cce0  test    rcx, rcx
0x18003cce3  jz      short loc_18003CCEB
0x18003cce5  call    cs:__imp_SamIFree_UserInternal6Information
0x18003cceb  cmp     qword ptr [rbp+57h+var_58+8], r14
0x18003ccef  jz      short loc_18003CCFB
0x18003ccf1  lea     rcx, [rbp+57h+var_58]
0x18003ccf5  call    cs:__imp_SamIFreeSidAndAttributesList
0x18003ccfb  cmp     [rbp+57h+arg_18], r14
0x18003ccff  jz      short loc_18003CD0C
0x18003cd01  lea     rcx, [rbp+57h+arg_18]
0x18003cd05  call    cs:__imp_SamrCloseHandle
0x18003cd0b  nop
0x18003cd0c  mov     eax, 0C00000BBh
0x18003cd11  lea     r11, [rsp+0B0h+var_10]
0x18003cd19  mov     rbx, [r11+20h]
0x18003cd1d  mov     rsi, [r11+28h]
0x18003cd21  mov     rsp, r11
0x18003cd24  pop     r14
0x18003cd26  pop     rdi
0x18003cd27  pop     rbp
0x18003cd28  retn
```
