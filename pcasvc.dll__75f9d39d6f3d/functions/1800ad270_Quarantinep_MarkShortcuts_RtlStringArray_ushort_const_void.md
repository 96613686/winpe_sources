# Quarantinep_MarkShortcuts(RtlStringArray *,ushort const *,void *)

- ea: `0x1800ad270`
- end: `0x1800ad5f8`
- name: `?Quarantinep_MarkShortcuts@@YAKPEAVRtlStringArray@@PEBGPEAX@Z`
- size: `904`
- prototype: `unsigned int(struct RtlStringArray *, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017de0`

## callees

- `0x180008e14`
- `0x180012920`
- `0x18001b320`
- `0x1800212b0`
- `0x1800ad270`
- `0x1800f1f10`
- `0x1800f7010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800ad405`
- `msvcrt!_wcsicmp` at `0x1800ad405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad2d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad2d5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800ad5c6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800ad5c6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800ad2c8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800ad2c8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800ad3f5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800ad3f5`
- `apphelp!__imp_SdbGetPermLayerPath` at `0x1800ad4d1`
- `apphelp!__imp_SdbGetPermLayerPath` at `0x1800ad4d1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ad34e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800ad34e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800ad5bb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800ad5bb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800ad310`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800ad310`

## string_xrefs

- `0x1800ad2e1`: `Failed to impersonate user [%d]`
- `0x1800ad35b`: `Failed to create link object [%d]`
- `0x1800ad4ad`: `Failed to get path for link [%d]`
- `0x1800ad4e4`: `Failed to get perm layers path for %S [%d]`
- `0x1800ad42e`: `Failed to get load link with persist file interface [%d]`
- `0x1800ad31d`: `Failed to initialize COM [%d]`
- `0x1800ad541`: `Failed to set a quarantined exe path to the store [%d]`

## pseudocode

```c
__int64 __fastcall Quarantinep_MarkShortcuts(struct RtlStringArray *a1, const unsigned __int16 *a2, void *a3)
{
  int v4; // r13d
  int v5; // r12d
  DWORD LastError; // edi
  const char *v7; // r9
  int v8; // r8d
  HRESULT v9; // eax
  HRESULT v10; // eax
  int v11; // eax
  ULONGLONG v12; // rax
  ULONGLONG v13; // r12
  int v14; // edi
  ULONGLONG i; // rsi
  LPCWSTR *v16; // rdx
  ULONGLONG v17; // rcx
  LPCWSTR v18; // r15
  const wchar_t *ExtensionW; // rax
  int v20; // eax
  const char *v21; // r9
  int v22; // r8d
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+28h] [rbp-D8h]
  LPVOID v26; // [rsp+30h] [rbp-D0h] BYREF
  ULONGLONG pullResult[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v29; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t v30[264]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v31[528]; // [rsp+270h] [rbp+170h] BYREF

  pullResult[0] = (ULONGLONG)a2;
  v26 = 0;
  v28 = 0;
  v29 = 0;
  v4 = 0;
  if ( !ImpersonateLoggedOnUser(a3) )
  {
    v5 = 0;
    LastError = GetLastError();
    v7 = "Failed to impersonate user [%d]";
    v8 = 104;
LABEL_3:
    AslLogCallPrintf(1, (unsigned int)"Quarantinep_MarkShortcuts", v8, (_DWORD)v7);
    goto LABEL_33;
  }
  v5 = 1;
  v9 = CoInitializeEx(0, 2u);
  if ( v9 < 0 )
  {
    LastError = (unsigned __int16)v9;
    v7 = "Failed to initialize COM [%d]";
    v8 = 117;
    goto LABEL_3;
  }
  v4 = 1;
  v10 = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &IID_IShellLinkW, &v26);
  if ( v10 < 0 )
  {
    LastError = (unsigned __int16)v10;
    v7 = "Failed to create link object [%d]";
    v8 = 130;
    goto LABEL_3;
  }
  v11 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v26)(v26, &IID_IPersistFile, &v28);
  if ( v11 < 0 )
  {
    LastError = (unsigned __int16)v11;
    v7 = "Failed to get persist file interface [%d]";
    v8 = 137;
    goto LABEL_3;
  }
  v12 = *((_QWORD *)a1 + 2);
  if ( !v12 )
    goto LABEL_32;
  v13 = pullResult[0];
  v14 = 0;
  for ( i = 0; i < v12; ++i )
  {
    v16 = 0;
    if ( i < v12 )
    {
      v17 = *((_QWORD *)a1 + 1);
      pullResult[0] = 0;
      if ( ULongLongMult(v17, i, pullResult) < 0
        || (v16 = (LPCWSTR *)(*((_QWORD *)a1 + 5) + pullResult[0]), (unsigned __int64)v16 < *((_QWORD *)a1 + 5)) )
      {
        v16 = 0;
      }
    }
    v18 = *v16;
    ExtensionW = PathFindExtensionW(*v16);
    if ( !_wcsicmp(ExtensionW, L".LNK") )
    {
      v20 = (*(__int64 (__fastcall **)(__int64, LPCWSTR, _QWORD))(*(_QWORD *)v28 + 40LL))(v28, v18, 0);
      if ( v20 < 0 )
      {
        v21 = "Failed to get load link with persist file interface [%d]";
        v22 = 155;
LABEL_19:
        v14 = (unsigned __int16)v20;
LABEL_20:
        AslLogCallPrintf(1, (unsigned int)"Quarantinep_MarkShortcuts", v22, (_DWORD)v21);
        goto LABEL_30;
      }
      v20 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)v26 + 152LL))(v26, 0, 105);
      if ( v20 < 0 )
      {
        v21 = "Failed to resolve [%d]";
        v22 = 162;
        goto LABEL_19;
      }
      LODWORD(ppv) = 0;
      v20 = (*(__int64 (__fastcall **)(LPVOID, wchar_t *, __int64, _QWORD, LPVOID *, int))(*(_QWORD *)v26 + 24LL))(
              v26,
              v30,
              260,
              0,
              ppv,
              v25);
      if ( v20 < 0 )
      {
        v21 = "Failed to get path for link [%d]";
        v22 = 169;
        goto LABEL_19;
      }
      if ( (unsigned int)SdbGetPermLayerPath(v30, v31, 260) )
      {
        v29 = 1u;
        v14 = PcaStoreSetValueEx(v13, v31, 5, &v29, 16);
        if ( v14 )
        {
          v21 = "Failed to set a quarantined exe path to the store [%d]";
          v22 = 190;
          goto LABEL_20;
        }
        PcaTracePrintf("Quarantine", 0, 0, "Quarantine,%S", v30);
      }
      else
      {
        v25 = v14;
        ppv = (LPVOID *)v30;
        AslLogCallPrintf(
          1,
          (unsigned int)"Quarantinep_MarkShortcuts",
          176,
          (unsigned int)"Failed to get perm layers path for %S [%d]");
      }
    }
LABEL_30:
    v12 = *((_QWORD *)a1 + 2);
  }
  v5 = 1;
LABEL_32:
  LastError = 0;
LABEL_33:
  if ( v26 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v4 == 1 )
    CoUninitialize();
  if ( v5 == 1 )
    RevertToSelf();
  return LastError;
}

```

## disassembly

```asm
0x1800ad270  mov     [rsp-8+arg_18], rbx
0x1800ad275  push    rbp
0x1800ad276  push    rsi
0x1800ad277  push    rdi
0x1800ad278  push    r12
0x1800ad27a  push    r13
0x1800ad27c  push    r14
0x1800ad27e  push    r15
0x1800ad280  lea     rbp, [rsp-390h]
0x1800ad288  sub     rsp, 490h
0x1800ad28f  mov     rax, cs:__security_cookie
0x1800ad296  xor     rax, rsp
0x1800ad299  mov     [rbp+3C0h+var_40], rax
0x1800ad2a0  mov     r14, rcx
0x1800ad2a3  mov     [rsp+4C0h+pullResult], rdx
0x1800ad2a8  xorps   xmm0, xmm0
0x1800ad2ab  mov     [rsp+4C0h+var_490], 0
0x1800ad2b4  mov     rcx, r8; hToken
0x1800ad2b7  mov     [rsp+4C0h+var_478], 0
0x1800ad2c0  movups  [rsp+4C0h+var_470], xmm0
0x1800ad2c5  xor     r13d, r13d
0x1800ad2c8  call    cs:__imp_ImpersonateLoggedOnUser
0x1800ad2ce  test    eax, eax
0x1800ad2d0  jnz     short loc_1800AD303
0x1800ad2d2  xor     r12d, r12d
0x1800ad2d5  call    cs:__imp_GetLastError
0x1800ad2db  mov     edi, eax
0x1800ad2dd  mov     dword ptr [rsp+4C0h+ppv], eax
0x1800ad2e1  lea     r9, aFailedToImpers_0; "Failed to impersonate user [%d]"
0x1800ad2e8  lea     r8d, [r13+68h]
0x1800ad2ec  lea     ebx, [r13+1]
0x1800ad2f0  lea     rdx, aQuarantinepMar; "Quarantinep_MarkShortcuts"
0x1800ad2f7  mov     ecx, ebx
0x1800ad2f9  call    AslLogCallPrintf
0x1800ad2fe  jmp     loc_1800AD58A
0x1800ad303  mov     ebx, 1
0x1800ad308  xor     ecx, ecx; pvReserved
0x1800ad30a  mov     r12d, ebx
0x1800ad30d  lea     edx, [rbx+1]; dwCoInit
0x1800ad310  call    cs:__imp_CoInitializeEx
0x1800ad316  test    eax, eax
0x1800ad318  jns     short loc_1800AD32E
0x1800ad31a  movzx   edi, ax
0x1800ad31d  lea     r9, aFailedToInitia_22; "Failed to initialize COM [%d]"
0x1800ad324  mov     dword ptr [rsp+4C0h+ppv], edi
0x1800ad328  lea     r8d, [rbx+74h]
0x1800ad32c  jmp     short loc_1800AD2F0
0x1800ad32e  lea     rax, [rsp+4C0h+var_490]
0x1800ad333  mov     r8d, ebx; dwClsContext
0x1800ad336  lea     r9, IID_IShellLinkW; riid
0x1800ad33d  mov     [rsp+4C0h+ppv], rax; ppv
0x1800ad342  xor     edx, edx; pUnkOuter
0x1800ad344  lea     rcx, CLSID_ShellLink; rclsid
0x1800ad34b  mov     r13d, ebx
0x1800ad34e  call    cs:__imp_CoCreateInstance
0x1800ad354  test    eax, eax
0x1800ad356  jns     short loc_1800AD36E
0x1800ad358  movzx   edi, ax
0x1800ad35b  lea     r9, aFailedToCreate_32; "Failed to create link object [%d]"
0x1800ad362  mov     dword ptr [rsp+4C0h+ppv], edi
0x1800ad366  mov     r8d, 82h
0x1800ad36c  jmp     short loc_1800AD2F0
0x1800ad36e  mov     rcx, [rsp+4C0h+var_490]
0x1800ad373  lea     r8, [rsp+4C0h+var_478]
0x1800ad378  lea     rdx, IID_IPersistFile
0x1800ad37f  mov     rax, [rcx]
0x1800ad382  mov     rax, [rax]
0x1800ad385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad38a  test    eax, eax
0x1800ad38c  jns     short loc_1800AD3A7
0x1800ad38e  movzx   edi, ax
0x1800ad391  lea     r9, aFailedToGetPer_2; "Failed to get persist file interface [%"...
0x1800ad398  mov     dword ptr [rsp+4C0h+ppv], edi
0x1800ad39c  mov     r8d, 89h
0x1800ad3a2  jmp     loc_1800AD2F0
0x1800ad3a7  mov     rax, [r14+10h]
0x1800ad3ab  test    rax, rax
0x1800ad3ae  jz      loc_1800AD588
0x1800ad3b4  mov     r12, [rsp+4C0h+pullResult]
0x1800ad3b9  xor     edi, edi
0x1800ad3bb  xor     esi, esi
0x1800ad3bd  xor     edx, edx
0x1800ad3bf  cmp     rsi, rax
0x1800ad3c2  jnb     short loc_1800AD3EF
0x1800ad3c4  mov     rcx, [r14+8]; ullMultiplicand
0x1800ad3c8  lea     r8, [rsp+4C0h+pullResult]; pullResult
0x1800ad3cd  mov     [rsp+4C0h+pullResult], rdx
0x1800ad3d2  mov     rdx, rsi; ullMultiplier
0x1800ad3d5  call    ULongLongMult
0x1800ad3da  test    eax, eax
0x1800ad3dc  js      short loc_1800AD3ED
0x1800ad3de  mov     rdx, [rsp+4C0h+pullResult]
0x1800ad3e3  add     rdx, [r14+28h]
0x1800ad3e7  cmp     rdx, [r14+28h]
0x1800ad3eb  jnb     short loc_1800AD3EF
0x1800ad3ed  xor     edx, edx
0x1800ad3ef  mov     r15, [rdx]
0x1800ad3f2  mov     rcx, r15; pszPath
0x1800ad3f5  call    cs:__imp_PathFindExtensionW
0x1800ad3fb  mov     rcx, rax; String1
0x1800ad3fe  lea     rdx, aLnk_0; ".LNK"
0x1800ad405  call    cs:__imp__wcsicmp
0x1800ad40b  test    eax, eax
0x1800ad40d  jnz     loc_1800AD575
0x1800ad413  mov     rcx, [rsp+4C0h+var_478]
0x1800ad418  xor     r8d, r8d
0x1800ad41b  mov     rdx, r15
0x1800ad41e  mov     rax, [rcx]
0x1800ad421  mov     rax, [rax+28h]
0x1800ad425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad42a  test    eax, eax
0x1800ad42c  jns     short loc_1800AD455
0x1800ad42e  lea     r9, aFailedToGetLoa; "Failed to get load link with persist fi"...
0x1800ad435  mov     r8d, 9Bh
0x1800ad43b  movzx   edi, ax
0x1800ad43e  mov     dword ptr [rsp+4C0h+ppv], edi
0x1800ad442  lea     rdx, aQuarantinepMar; "Quarantinep_MarkShortcuts"
0x1800ad449  mov     ecx, ebx
0x1800ad44b  call    AslLogCallPrintf
0x1800ad450  jmp     loc_1800AD575
0x1800ad455  mov     rcx, [rsp+4C0h+var_490]
0x1800ad45a  xor     edx, edx
0x1800ad45c  mov     rax, [rcx]
0x1800ad45f  lea     r8d, [rdx+69h]
0x1800ad463  mov     rax, [rax+98h]
0x1800ad46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad46f  test    eax, eax
0x1800ad471  jns     short loc_1800AD482
0x1800ad473  lea     r9, aFailedToResolv_4; "Failed to resolve [%d]"
0x1800ad47a  mov     r8d, 0A2h
0x1800ad480  jmp     short loc_1800AD43B
0x1800ad482  mov     rcx, [rsp+4C0h+var_490]
0x1800ad487  lea     rdx, [rsp+4C0h+var_460]
0x1800ad48c  xor     r9d, r9d
0x1800ad48f  mov     dword ptr [rsp+4C0h+ppv], 0
0x1800ad497  mov     r8d, 104h
0x1800ad49d  mov     rax, [rcx]
0x1800ad4a0  mov     rax, [rax+18h]
0x1800ad4a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad4a9  test    eax, eax
0x1800ad4ab  jns     short loc_1800AD4BF
0x1800ad4ad  lea     r9, aFailedToGetPat_1; "Failed to get path for link [%d]"
0x1800ad4b4  mov     r8d, 0A9h
0x1800ad4ba  jmp     loc_1800AD43B
0x1800ad4bf  mov     r8d, 104h
0x1800ad4c5  lea     rdx, [rbp+3C0h+var_250]
0x1800ad4cc  lea     rcx, [rsp+4C0h+var_460]
0x1800ad4d1  call    cs:__imp_SdbGetPermLayerPath
0x1800ad4d7  test    eax, eax
0x1800ad4d9  jnz     short loc_1800AD506
0x1800ad4db  lea     rax, [rsp+4C0h+var_460]
0x1800ad4e0  mov     [rsp+4C0h+var_498], edi
0x1800ad4e4  lea     r9, aFailedToGetPer; "Failed to get perm layers path for %S ["...
0x1800ad4eb  mov     [rsp+4C0h+ppv], rax
0x1800ad4f0  mov     r8d, 0B0h
0x1800ad4f6  lea     rdx, aQuarantinepMar; "Quarantinep_MarkShortcuts"
0x1800ad4fd  mov     ecx, ebx
0x1800ad4ff  call    AslLogCallPrintf
0x1800ad504  jmp     short loc_1800AD575
0x1800ad506  lea     r9, [rsp+4C0h+var_470]
0x1800ad50b  mov     qword ptr [rsp+4C0h+var_470], rbx
0x1800ad510  mov     r8d, 5
0x1800ad516  mov     qword ptr [rsp+4C0h+var_470+8], 0
0x1800ad51f  lea     rdx, [rbp+3C0h+var_250]
0x1800ad526  mov     [rsp+4C0h+ppv], 10h
0x1800ad52f  mov     rcx, r12
0x1800ad532  call    ?PcaStoreSetValueEx@@YAKPEBG0W4_PCA_SLOT_ID@@PEAX_K@Z; PcaStoreSetValueEx(ushort const *,ushort const *,_PCA_SLOT_ID,void *,unsigned __int64)
0x1800ad537  mov     edi, eax
0x1800ad539  test    eax, eax
0x1800ad53b  jz      short loc_1800AD553
0x1800ad53d  mov     dword ptr [rsp+4C0h+ppv], eax
0x1800ad541  lea     r9, aFailedToSetAQu; "Failed to set a quarantined exe path to"...
0x1800ad548  mov     r8d, 0BEh
0x1800ad54e  jmp     loc_1800AD442
0x1800ad553  lea     rax, [rsp+4C0h+var_460]
0x1800ad558  xor     r8d, r8d; unsigned int
0x1800ad55b  lea     r9, aQuarantineS; "Quarantine,%S"
0x1800ad562  mov     [rsp+4C0h+ppv], rax
0x1800ad567  xor     edx, edx; unsigned int
0x1800ad569  lea     rcx, aQuarantine; "Quarantine"
0x1800ad570  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800ad575  mov     rax, [r14+10h]
0x1800ad579  add     rsi, rbx
0x1800ad57c  cmp     rsi, rax
0x1800ad57f  jb      loc_1800AD3BD
0x1800ad585  mov     r12d, ebx
0x1800ad588  xor     edi, edi
0x1800ad58a  mov     rcx, [rsp+4C0h+var_490]
0x1800ad58f  test    rcx, rcx
0x1800ad592  jz      short loc_1800AD5A0
0x1800ad594  mov     rax, [rcx]
0x1800ad597  mov     rax, [rax+10h]
0x1800ad59b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad5a0  mov     rcx, [rsp+4C0h+var_478]
0x1800ad5a5  test    rcx, rcx
0x1800ad5a8  jz      short loc_1800AD5B6
0x1800ad5aa  mov     rax, [rcx]
0x1800ad5ad  mov     rax, [rax+10h]
0x1800ad5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad5b6  cmp     r13d, ebx
0x1800ad5b9  jnz     short loc_1800AD5C1
0x1800ad5bb  call    cs:__imp_CoUninitialize
0x1800ad5c1  cmp     r12d, ebx
0x1800ad5c4  jnz     short loc_1800AD5CC
0x1800ad5c6  call    cs:__imp_RevertToSelf
0x1800ad5cc  mov     eax, edi
0x1800ad5ce  mov     rcx, [rbp+3C0h+var_40]
0x1800ad5d5  xor     rcx, rsp; StackCookie
0x1800ad5d8  call    __security_check_cookie
0x1800ad5dd  mov     rbx, [rsp+4C0h+arg_18]
0x1800ad5e5  add     rsp, 490h
0x1800ad5ec  pop     r15
0x1800ad5ee  pop     r14
0x1800ad5f0  pop     r13
0x1800ad5f2  pop     r12
0x1800ad5f4  pop     rdi
0x1800ad5f5  pop     rsi
0x1800ad5f6  pop     rbp
0x1800ad5f7  retn
```
