# InternetHost::CheckSafety(SAFETYOPERATION,_GUID const &,_GUID,IUnknown *)

- ea: `0x1801229dc`
- end: `0x180122bc0`
- name: `?CheckSafety@InternetHost@@IEAA_NW4SAFETYOPERATION@@AEBU_GUID@@U3@PEAUIUnknown@@@Z`
- size: `484`
- prototype: `bool __fastcall(InternetHost *this, SAFETYOPERATION sOperation, const _GUID *clsid, _GUID pUnk, IUnknown *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800cb440`

## callees

- `0x1800cc6c0`
- `0x1800d6c90`
- `0x1801229dc`
- `0x180122e1c`
- `0x18018c010`

## import_xrefs

- `urlmon!CompatFlagsFromClsid` at `0x180122a6e`
- `urlmon!CompatFlagsFromClsid` at `0x180122a6e`

## pseudocode

```c
char __fastcall InternetHost::CheckSafety(
        InternetHost *this,
        SAFETYOPERATION sOperation,
        const _GUID *clsid,
        _GUID *pUnk,
        IUnknown *a5)
{
  CLSID v5; // xmm0
  char v6; // bl
  GUID v9; // xmm6
  unsigned int v10; // edi
  ICatInformation **v11; // rcx
  unsigned int v12; // edx
  IObjectSafety *pOSafe; // [rsp+48h] [rbp-31h] BYREF
  ICatInformation **dwMiscStatus; // [rsp+50h] [rbp-29h] BYREF
  DWORD pdwMiscStatusFlags[4]; // [rsp+58h] [rbp-21h] BYREF
  CLSID pclsid; // [rsp+68h] [rbp-11h] BYREF
  GUID v18; // [rsp+78h] [rbp-1h] BYREF

  v5 = *pUnk;
  v6 = 0;
  LOBYTE(pOSafe) = 0;
  HIDWORD(pOSafe) = 0;
  pdwMiscStatusFlags[0] = 0;
  dwMiscStatus = 0;
  pclsid = v5;
  if ( sOperation )
  {
    if ( sOperation == SAFETY_SCRIPT )
    {
      v9 = CATID_SafeForScripting;
      v10 = 1;
    }
    else
    {
      v9 = GUID_NULL;
      v10 = 0;
    }
  }
  else
  {
    v9 = CATID_SafeForInitializing;
    v10 = 2;
  }
  if ( CompatFlagsFromClsid(&pclsid, (LPDWORD)&pOSafe + 1, pdwMiscStatusFlags) >= 0 && (WORD2(pOSafe) & 0x400) == 0 )
  {
    if ( (BYTE4(pOSafe) & 2) != 0 )
    {
$Confirm:
      v12 = 4612;
LABEL_16:
      InternetHost::IsAllowableAction(this, v12, (bool *)&pOSafe);
      v6 = (char)pOSafe;
      goto $Cleanup_18;
    }
    if ( a5->QueryInterface(a5, &IID_IObjectSafety, (void **)&dwMiscStatus) >= 0 && (v11 = dwMiscStatus) != 0 )
    {
      if ( sOperation == SAFETY_SCRIPT )
      {
        if ( ((int (__fastcall *)(ICatInformation **, GUID *, _QWORD, _QWORD))(*dwMiscStatus)[4].__vftable)(
               dwMiscStatus,
               &IID_IDispatchEx,
               v10,
               v10) >= 0 )
        {
LABEL_23:
          v12 = 5125;
          goto LABEL_16;
        }
        v11 = dwMiscStatus;
      }
      if ( ((int (__fastcall *)(ICatInformation **, GUID *, _QWORD, _QWORD))(*v11)[4].__vftable)(
             v11,
             &IID_IDispatch,
             v10,
             v10) < 0 )
        goto $Confirm;
    }
    else
    {
      if ( CreateCatalogInformation(v11) < 0 )
        goto $Cleanup_18;
      v18 = v9;
      if ( g_pCatInfo->IsClassOfCategories(g_pCatInfo, &pclsid, 1u, &v18, 0, 0) )
        goto $Confirm;
    }
    if ( sOperation == SAFETY_SCRIPT )
      goto LABEL_23;
    v6 = 1;
  }
$Cleanup_18:
  if ( dwMiscStatus )
    ((void (__fastcall *)(ICatInformation **))(*dwMiscStatus)[2].__vftable)(dwMiscStatus);
  return v6;
}

```

## disassembly

```asm
0x1801229dc  mov     rax, rsp
0x1801229df  mov     [rax+10h], rbx
0x1801229e3  push    rbp
0x1801229e4  push    rsi
0x1801229e5  push    rdi
0x1801229e6  push    r14
0x1801229e8  push    r15
0x1801229ea  lea     rbp, [rax-57h]
0x1801229ee  sub     rsp, 0A0h
0x1801229f5  movaps  xmmword ptr [rax-38h], xmm6
0x1801229f9  mov     rax, cs:__security_cookie
0x180122a00  xor     rax, rsp
0x180122a03  mov     [rbp+4Fh+var_40], rax
0x180122a07  movups  xmm0, xmmword ptr [clsid]
0x180122a0b  mov     r15, [rbp+4Fh+arg_20]
0x180122a0f  xor     bl, bl
0x180122a11  mov     byte ptr [rbp+4Fh+pOSafe], bl
0x180122a14  mov     esi, sOperation
0x180122a16  mov     dword ptr [rbp+4Fh+pOSafe+4], 0
0x180122a1d  mov     r14, this
0x180122a20  mov     [rbp+4Fh+pdwMiscStatusFlags], 0
0x180122a27  mov     [rbp+4Fh+dwMiscStatus], 0
0x180122a2f  movdqu  xmmword ptr [rbp+4Fh+pclsid.Data1], xmm0
0x180122a34  test    sOperation, sOperation
0x180122a36  jz      short loc_180122A56
0x180122a38  cmp     sOperation, 1
0x180122a3b  jz      short loc_180122A48
0x180122a3d  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x180122a44  xor     edi, edi
0x180122a46  jmp     short loc_180122A62
0x180122a48  movups  xmm6, xmmword ptr cs:CATID_SafeForScripting.Data1
0x180122a4f  mov     edi, 1
0x180122a54  jmp     short loc_180122A62
0x180122a56  movups  xmm6, xmmword ptr cs:CATID_SafeForInitializing.Data1
0x180122a5d  mov     edi, 2
0x180122a62  lea     r8, [rbp+4Fh+pdwMiscStatusFlags]; pdwMiscStatusFlags
0x180122a66  lea     rdx, [rbp+4Fh+pOSafe+4]; pdwCompatFlags
0x180122a6a  lea     this, [rbp+4Fh+pclsid]; pclsid
0x180122a6e  call    cs:__imp_CompatFlagsFromClsid
0x180122a75  nop     dword ptr [rax+rax+00h]
0x180122a7a  test    eax, eax
0x180122a7c  js      $Cleanup_18
0x180122a82  test    dword ptr [rbp+4Fh+pOSafe+4], 400h
0x180122a89  jnz     $Cleanup_18
0x180122a8f  test    byte ptr [rbp+4Fh+pOSafe+4], 2
0x180122a93  jnz     short $Confirm
0x180122a95  mov     rax, [r15]
0x180122a98  lea     r8, [rbp+4Fh+dwMiscStatus]
0x180122a9c  lea     rdx, IID_IObjectSafety
0x180122aa3  mov     this, r15
0x180122aa6  mov     rax, [rax]
0x180122aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122aae  test    eax, eax
0x180122ab0  js      loc_180122B62
0x180122ab6  mov     this, [rbp+4Fh+dwMiscStatus]
0x180122aba  test    this, this
0x180122abd  jz      loc_180122B62
0x180122ac3  cmp     esi, 1
0x180122ac6  jnz     short loc_180122AED
0x180122ac8  mov     rax, [this]
0x180122acb  lea     rdx, IID_IDispatchEx
0x180122ad2  mov     r9d, edi
0x180122ad5  mov     r8d, edi
0x180122ad8  mov     rax, [rax+20h]
0x180122adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122ae1  test    eax, eax
0x180122ae3  jns     loc_180122BAF
0x180122ae9  mov     this, [rbp+4Fh+dwMiscStatus]
0x180122aed  mov     rax, [this]
0x180122af0  lea     rdx, IID_IDispatch
0x180122af7  mov     r9d, edi
0x180122afa  mov     r8d, edi
0x180122afd  mov     rax, [rax+20h]
0x180122b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122b06  test    eax, eax
0x180122b08  jns     $EnsureSafeForScripting
0x180122b0e  mov     sOperation, 1204h; dwAction
0x180122b13  lea     r8, [rbp+4Fh+pOSafe]; pfAllow
0x180122b17  mov     this, r14; this
0x180122b1a  call    ?IsAllowableAction@InternetHost@@IEAAJKPEA_N@Z; InternetHost::IsAllowableAction(ulong,bool *)
0x180122b1f  mov     bl, byte ptr [rbp+4Fh+pOSafe]
0x180122b22  mov     this, [rbp+4Fh+dwMiscStatus]
0x180122b26  test    this, this
0x180122b29  jz      short loc_180122B37
0x180122b2b  mov     rdx, [this]
0x180122b2e  mov     rax, [rdx+10h]
0x180122b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122b37  mov     al, bl
0x180122b39  mov     this, [rbp+4Fh+var_40]
0x180122b3d  xor     this, rsp; StackCookie
0x180122b40  call    __security_check_cookie
0x180122b45  lea     r11, [rsp+0C0h+var_20]
0x180122b4d  mov     rbx, [r11+38h]
0x180122b51  movaps  xmm6, xmmword ptr [r11-10h]
0x180122b56  mov     rsp, r11
0x180122b59  pop     r15
0x180122b5b  pop     r14
0x180122b5d  pop     rdi
0x180122b5e  pop     rsi
0x180122b5f  pop     rbp
0x180122b60  retn
0x180122b62  call    ?CreateCatalogInformation@@YAJPEAPEAUICatInformation@@@Z; CreateCatalogInformation(ICatInformation * *)
0x180122b67  test    eax, eax
0x180122b69  js      short $Cleanup_18
0x180122b6b  mov     this, cs:?g_pCatInfo@@3PEAUICatInformation@@EA; ICatInformation * g_pCatInfo
0x180122b72  lea     clsid, [rbp+4Fh+var_50]
0x180122b76  movdqa  [rbp+4Fh+var_50], xmm6
0x180122b7b  lea     rdx, [rbp+4Fh+pclsid]
0x180122b7f  mov     [rsp+0C0h+var_98], 0
0x180122b88  mov     r8d, 1
0x180122b8e  mov     dword ptr [rsp+0C0h+var_A0], 0
0x180122b96  mov     rax, [this]
0x180122b99  mov     rax, [rax+30h]
0x180122b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180122ba2  test    eax, eax
0x180122ba4  jnz     $Confirm
0x180122baa  cmp     esi, 1
0x180122bad  jnz     short loc_180122BB9
0x180122baf  mov     sOperation, 1405h
0x180122bb4  jmp     loc_180122B13
0x180122bb9  mov     bl, 1
0x180122bbb  jmp     $Cleanup_18
```
