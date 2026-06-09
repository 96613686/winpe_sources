# InternetHost::CheckSafety(SAFETYOPERATION,_GUID const &,_GUID,IUnknown *)

- ea: `0x18011ff54`
- end: `0x180120131`
- name: `?CheckSafety@InternetHost@@IEAA_NW4SAFETYOPERATION@@AEBU_GUID@@U3@PEAUIUnknown@@@Z`
- size: `477`
- prototype: `bool __fastcall(InternetHost *this, SAFETYOPERATION sOperation, const _GUID *clsid, _GUID pUnk, IUnknown *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800c9b40`

## callees

- `0x1800cada0`
- `0x1800d4ff0`
- `0x18011ff54`
- `0x18012037c`
- `0x180188010`

## import_xrefs

- `urlmon!CompatFlagsFromClsid` at `0x18011ffe6`
- `urlmon!CompatFlagsFromClsid` at `0x18011ffe6`

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
      goto $Cleanup_17;
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
        goto $Cleanup_17;
      v18 = v9;
      if ( g_pCatInfo->IsClassOfCategories(g_pCatInfo, &pclsid, 1u, &v18, 0, 0) )
        goto $Confirm;
    }
    if ( sOperation == SAFETY_SCRIPT )
      goto LABEL_23;
    v6 = 1;
  }
$Cleanup_17:
  if ( dwMiscStatus )
    ((void (__fastcall *)(ICatInformation **))(*dwMiscStatus)[2].__vftable)(dwMiscStatus);
  return v6;
}

```

## disassembly

```asm
0x18011ff54  mov     rax, rsp
0x18011ff57  mov     [rax+10h], rbx
0x18011ff5b  push    rbp
0x18011ff5c  push    rsi
0x18011ff5d  push    rdi
0x18011ff5e  push    r14
0x18011ff60  push    r15
0x18011ff62  lea     rbp, [rax-57h]
0x18011ff66  sub     rsp, 0A0h
0x18011ff6d  movaps  xmmword ptr [rax-38h], xmm6
0x18011ff71  mov     rax, cs:__security_cookie
0x18011ff78  xor     rax, rsp
0x18011ff7b  mov     [rbp+4Fh+var_40], rax
0x18011ff7f  movups  xmm0, xmmword ptr [clsid]
0x18011ff83  mov     r15, [rbp+4Fh+arg_20]
0x18011ff87  xor     bl, bl
0x18011ff89  mov     byte ptr [rbp+4Fh+pOSafe], bl
0x18011ff8c  mov     esi, sOperation
0x18011ff8e  mov     dword ptr [rbp+4Fh+pOSafe+4], 0
0x18011ff95  mov     r14, this
0x18011ff98  mov     [rbp+4Fh+pdwMiscStatusFlags], 0
0x18011ff9f  mov     [rbp+4Fh+dwMiscStatus], 0
0x18011ffa7  movdqu  xmmword ptr [rbp+4Fh+pclsid.Data1], xmm0
0x18011ffac  test    sOperation, sOperation
0x18011ffae  jz      short loc_18011FFCE
0x18011ffb0  cmp     sOperation, 1
0x18011ffb3  jz      short loc_18011FFC0
0x18011ffb5  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18011ffbc  xor     edi, edi
0x18011ffbe  jmp     short loc_18011FFDA
0x18011ffc0  movups  xmm6, xmmword ptr cs:CATID_SafeForScripting.Data1
0x18011ffc7  mov     edi, 1
0x18011ffcc  jmp     short loc_18011FFDA
0x18011ffce  movups  xmm6, xmmword ptr cs:CATID_SafeForInitializing.Data1
0x18011ffd5  mov     edi, 2
0x18011ffda  lea     r8, [rbp+4Fh+pdwMiscStatusFlags]; pdwMiscStatusFlags
0x18011ffde  lea     rdx, [rbp+4Fh+pOSafe+4]; pdwCompatFlags
0x18011ffe2  lea     this, [rbp+4Fh+pclsid]; pclsid
0x18011ffe6  call    cs:__imp_CompatFlagsFromClsid
0x18011ffec  test    eax, eax
0x18011ffee  js      $Cleanup_17
0x18011fff4  test    dword ptr [rbp+4Fh+pOSafe+4], 400h
0x18011fffb  jnz     $Cleanup_17
0x180120001  test    byte ptr [rbp+4Fh+pOSafe+4], 2
0x180120005  jnz     short $Confirm
0x180120007  mov     rax, [r15]
0x18012000a  lea     r8, [rbp+4Fh+dwMiscStatus]
0x18012000e  lea     rdx, IID_IObjectSafety
0x180120015  mov     this, r15
0x180120018  mov     rax, [rax]
0x18012001b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120020  test    eax, eax
0x180120022  js      loc_1801200D3
0x180120028  mov     this, [rbp+4Fh+dwMiscStatus]
0x18012002c  test    this, this
0x18012002f  jz      loc_1801200D3
0x180120035  cmp     esi, 1
0x180120038  jnz     short loc_18012005F
0x18012003a  mov     rax, [this]
0x18012003d  lea     rdx, IID_IDispatchEx
0x180120044  mov     r9d, edi
0x180120047  mov     r8d, edi
0x18012004a  mov     rax, [rax+20h]
0x18012004e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120053  test    eax, eax
0x180120055  jns     loc_180120120
0x18012005b  mov     this, [rbp+4Fh+dwMiscStatus]
0x18012005f  mov     rax, [this]
0x180120062  lea     rdx, IID_IDispatch
0x180120069  mov     r9d, edi
0x18012006c  mov     r8d, edi
0x18012006f  mov     rax, [rax+20h]
0x180120073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120078  test    eax, eax
0x18012007a  jns     $EnsureSafeForScripting
0x180120080  mov     sOperation, 1204h; dwAction
0x180120085  lea     r8, [rbp+4Fh+pOSafe]; pfAllow
0x180120089  mov     this, r14; this
0x18012008c  call    ?IsAllowableAction@InternetHost@@IEAAJKPEA_N@Z; InternetHost::IsAllowableAction(ulong,bool *)
0x180120091  mov     bl, byte ptr [rbp+4Fh+pOSafe]
0x180120094  mov     this, [rbp+4Fh+dwMiscStatus]
0x180120098  test    this, this
0x18012009b  jz      short loc_1801200A9
0x18012009d  mov     rdx, [this]
0x1801200a0  mov     rax, [rdx+10h]
0x1801200a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801200a9  mov     al, bl
0x1801200ab  mov     this, [rbp+4Fh+var_40]
0x1801200af  xor     this, rsp; StackCookie
0x1801200b2  call    __security_check_cookie
0x1801200b7  lea     r11, [rsp+0C0h+var_20]
0x1801200bf  mov     rbx, [r11+38h]
0x1801200c3  movaps  xmm6, xmmword ptr [r11-10h]
0x1801200c8  mov     rsp, r11
0x1801200cb  pop     r15
0x1801200cd  pop     r14
0x1801200cf  pop     rdi
0x1801200d0  pop     rsi
0x1801200d1  pop     rbp
0x1801200d2  retn
0x1801200d3  call    ?CreateCatalogInformation@@YAJPEAPEAUICatInformation@@@Z; CreateCatalogInformation(ICatInformation * *)
0x1801200d8  test    eax, eax
0x1801200da  js      short $Cleanup_17
0x1801200dc  mov     this, cs:?g_pCatInfo@@3PEAUICatInformation@@EA; ICatInformation * g_pCatInfo
0x1801200e3  lea     clsid, [rbp+4Fh+var_50]
0x1801200e7  movdqa  [rbp+4Fh+var_50], xmm6
0x1801200ec  lea     rdx, [rbp+4Fh+pclsid]
0x1801200f0  mov     [rsp+0C0h+var_98], 0
0x1801200f9  mov     r8d, 1
0x1801200ff  mov     dword ptr [rsp+0C0h+var_A0], 0
0x180120107  mov     rax, [this]
0x18012010a  mov     rax, [rax+30h]
0x18012010e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180120113  test    eax, eax
0x180120115  jnz     $Confirm
0x18012011b  cmp     esi, 1
0x18012011e  jnz     short loc_18012012A
0x180120120  mov     sOperation, 1405h
0x180120125  jmp     loc_180120085
0x18012012a  mov     bl, 1
0x18012012c  jmp     $Cleanup_17
```
