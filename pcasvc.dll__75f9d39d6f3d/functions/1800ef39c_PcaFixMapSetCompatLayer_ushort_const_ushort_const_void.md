# PcaFixMapSetCompatLayer(ushort const *,ushort const *,void *)

- ea: `0x1800ef39c`
- end: `0x1800ef5be`
- name: `?PcaFixMapSetCompatLayer@@YAKPEBG0PEAX@Z`
- size: `546`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800b6330`
- `0x1800b7d20`

## callees

- `0x180012920`
- `0x18001658c`
- `0x1800333e8`
- `0x18007a9cf`
- `0x1800ea570`
- `0x1800ef39c`
- `0x1800f1f10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef416`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef416`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800ef590`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800ef590`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800ef40c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800ef40c`
- `apphelp!SetPermLayerState` at `0x1800ef471`
- `apphelp!SetPermLayerState` at `0x1800ef531`
- `apphelp!SetPermLayerState` at `0x1800ef566`
- `apphelp!SetPermLayerState` at `0x1800ef471`
- `apphelp!SetPermLayerState` at `0x1800ef531`
- `apphelp!SetPermLayerState` at `0x1800ef566`

## string_xrefs

- `0x1800ef41c`: `Failed to impersonate user [%d]`
- `0x1800ef429`: `PcaFixMapSetCompatLayer`
- `0x1800ef4ae`: `PcaFixMapSetCompatLayer`
- `0x1800ef540`: `Failed to remove layer [%d]`

## pseudocode

```c
__int64 __fastcall PcaFixMapSetCompatLayer(const unsigned __int16 *a1, const unsigned __int16 *a2, void *a3)
{
  int v6; // r14d
  DWORD LastError; // ebx
  const char *v8; // r9
  int v9; // r8d
  int v11; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v13; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v14[256]; // [rsp+50h] [rbp-B0h] BYREF

  v12 = 0;
  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  v6 = 0;
  v11 = 0;
  if ( a3 )
  {
    if ( !ImpersonateLoggedOnUser(a3) )
    {
      LastError = GetLastError();
      AslLogCallPrintf(1, (unsigned int)"PcaFixMapSetCompatLayer", 641, (unsigned int)"Failed to impersonate user [%d]");
      return LastError;
    }
    v6 = 1;
  }
  if ( !(unsigned int)SdbGetPermLayerKeys(a1, v14, &v11, 1) )
  {
    if ( !(unsigned int)SetPermLayerState(a1, a2, 4, 0, 1) )
    {
      v8 = "Failed to set layers [%d]";
      v9 = 669;
LABEL_21:
      LastError = 5;
      goto LABEL_10;
    }
    goto LABEL_22;
  }
  LastError = PcaFixMapFromString(&v12, a2);
  if ( LastError )
  {
    v8 = "Failed to generate map for fix to apply [%d]";
    v9 = 683;
LABEL_10:
    AslLogCallPrintf(1, (unsigned int)"PcaFixMapSetCompatLayer", v9, (_DWORD)v8);
    goto LABEL_23;
  }
  LastError = PcaFixMapFromString(&v13, v14);
  if ( LastError )
  {
    v8 = "Failed to generate map for existing layers [%d]";
    v9 = 689;
    goto LABEL_10;
  }
  if ( (_DWORD)v12 && (_DWORD)v13 )
  {
    LastError = PcaFixMapToString(v14, (unsigned int)v13);
    if ( LastError )
    {
      v8 = "Failed to generate layer string from fix map [%d]";
      v9 = 699;
      goto LABEL_10;
    }
    if ( !(unsigned int)SetPermLayerState(a1, v14, 0, 0, 0) )
    {
      v8 = "Failed to remove layer [%d]";
      LastError = 5;
      v9 = 709;
      goto LABEL_10;
    }
  }
  if ( !(unsigned int)SetPermLayerState(a1, a2, 4, 0, 1) )
  {
    v8 = "Failed to set layer [%d]";
    v9 = 724;
    goto LABEL_21;
  }
LABEL_22:
  LastError = 0;
LABEL_23:
  if ( v6 )
    RevertToSelf();
  return LastError;
}

```

## disassembly

```asm
0x1800ef39c  mov     [rsp-8+arg_18], rbx
0x1800ef3a1  push    rbp
0x1800ef3a2  push    rsi
0x1800ef3a3  push    rdi
0x1800ef3a4  push    r12
0x1800ef3a6  push    r14
0x1800ef3a8  lea     rbp, [rsp-160h]
0x1800ef3b0  sub     rsp, 260h
0x1800ef3b7  mov     rax, cs:__security_cookie
0x1800ef3be  xor     rax, rsp
0x1800ef3c1  mov     [rbp+180h+var_30], rax
0x1800ef3c8  mov     rbx, r8
0x1800ef3cb  mov     [rsp+280h+var_248], 0
0x1800ef3d4  mov     rsi, rdx
0x1800ef3d7  mov     [rsp+280h+var_240], 0
0x1800ef3e0  mov     rdi, rcx
0x1800ef3e3  xor     edx, edx; Val
0x1800ef3e5  mov     r8d, 200h; Size
0x1800ef3eb  lea     rcx, [rsp+280h+var_230]; void *
0x1800ef3f0  call    memset_0
0x1800ef3f5  xor     r14d, r14d
0x1800ef3f8  mov     [rsp+280h+var_250], 0
0x1800ef400  lea     r12d, [r14+1]
0x1800ef404  test    rbx, rbx
0x1800ef407  jz      short loc_1800EF446
0x1800ef409  mov     rcx, rbx; hToken
0x1800ef40c  call    cs:__imp_ImpersonateLoggedOnUser
0x1800ef412  test    eax, eax
0x1800ef414  jnz     short loc_1800EF443
0x1800ef416  call    cs:__imp_GetLastError
0x1800ef41c  lea     r9, aFailedToImpers_0; "Failed to impersonate user [%d]"
0x1800ef423  mov     r8d, 281h
0x1800ef429  lea     rdx, aPcafixmapsetco; "PcaFixMapSetCompatLayer"
0x1800ef430  mov     [rsp+280h+var_260], eax
0x1800ef434  mov     ecx, r12d
0x1800ef437  mov     ebx, eax
0x1800ef439  call    AslLogCallPrintf
0x1800ef43e  jmp     loc_1800EF596
0x1800ef443  mov     r14d, r12d
0x1800ef446  mov     r9d, r12d
0x1800ef449  lea     r8, [rsp+280h+var_250]
0x1800ef44e  lea     rdx, [rsp+280h+var_230]
0x1800ef453  mov     rcx, rdi
0x1800ef456  call    SdbGetPermLayerKeys
0x1800ef45b  mov     rdx, rsi; unsigned __int16 *
0x1800ef45e  test    eax, eax
0x1800ef460  jnz     short loc_1800EF491
0x1800ef462  xor     r9d, r9d
0x1800ef465  mov     [rsp+280h+var_260], r12d
0x1800ef46a  lea     r8d, [rax+4]
0x1800ef46e  mov     rcx, rdi
0x1800ef471  call    cs:__imp_SetPermLayerState
0x1800ef477  test    eax, eax
0x1800ef479  jnz     loc_1800EF589
0x1800ef47f  lea     r9, aFailedToSetLay; "Failed to set layers [%d]"
0x1800ef486  mov     r8d, 29Dh
0x1800ef48c  jmp     loc_1800EF57D
0x1800ef491  lea     rcx, [rsp+280h+var_248]; unsigned __int64 *
0x1800ef496  call    ?PcaFixMapFromString@@YAKPEA_KPEBG@Z; PcaFixMapFromString(unsigned __int64 *,ushort const *)
0x1800ef49b  mov     ebx, eax
0x1800ef49d  test    eax, eax
0x1800ef49f  jz      short loc_1800EF4C6
0x1800ef4a1  lea     r9, aFailedToGenera_2; "Failed to generate map for fix to apply"...
0x1800ef4a8  mov     r8d, 2ABh
0x1800ef4ae  lea     rdx, aPcafixmapsetco; "PcaFixMapSetCompatLayer"
0x1800ef4b5  mov     [rsp+280h+var_260], eax
0x1800ef4b9  mov     ecx, r12d
0x1800ef4bc  call    AslLogCallPrintf
0x1800ef4c1  jmp     loc_1800EF58B
0x1800ef4c6  lea     rdx, [rsp+280h+var_230]; unsigned __int16 *
0x1800ef4cb  lea     rcx, [rsp+280h+var_240]; unsigned __int64 *
0x1800ef4d0  call    ?PcaFixMapFromString@@YAKPEA_KPEBG@Z; PcaFixMapFromString(unsigned __int64 *,ushort const *)
0x1800ef4d5  mov     ebx, eax
0x1800ef4d7  test    eax, eax
0x1800ef4d9  jz      short loc_1800EF4EA
0x1800ef4db  lea     r9, aFailedToGenera; "Failed to generate map for existing lay"...
0x1800ef4e2  mov     r8d, 2B1h
0x1800ef4e8  jmp     short loc_1800EF4AE
0x1800ef4ea  cmp     dword ptr [rsp+280h+var_248], 0
0x1800ef4ef  jz      short loc_1800EF554
0x1800ef4f1  mov     rax, [rsp+280h+var_240]
0x1800ef4f6  test    eax, eax
0x1800ef4f8  jz      short loc_1800EF554
0x1800ef4fa  mov     edx, eax; unsigned __int64
0x1800ef4fc  lea     rcx, [rsp+280h+var_230]; unsigned __int16 *
0x1800ef501  call    ?PcaFixMapToString@@YAKPEAG_K@Z; PcaFixMapToString(ushort *,unsigned __int64)
0x1800ef506  mov     ebx, eax
0x1800ef508  test    eax, eax
0x1800ef50a  jz      short loc_1800EF51B
0x1800ef50c  lea     r9, aFailedToGenera_3; "Failed to generate layer string from fi"...
0x1800ef513  mov     r8d, 2BBh
0x1800ef519  jmp     short loc_1800EF4AE
0x1800ef51b  xor     r9d, r9d
0x1800ef51e  mov     [rsp+280h+var_260], 0
0x1800ef526  xor     r8d, r8d
0x1800ef529  lea     rdx, [rsp+280h+var_230]
0x1800ef52e  mov     rcx, rdi
0x1800ef531  call    cs:__imp_SetPermLayerState
0x1800ef537  test    eax, eax
0x1800ef539  jnz     short loc_1800EF554
0x1800ef53b  mov     eax, 5
0x1800ef540  lea     r9, aFailedToRemove_0; "Failed to remove layer [%d]"
0x1800ef547  mov     ebx, eax
0x1800ef549  mov     r8d, 2C5h
0x1800ef54f  jmp     loc_1800EF4AE
0x1800ef554  xor     r9d, r9d
0x1800ef557  mov     [rsp+280h+var_260], r12d
0x1800ef55c  mov     rdx, rsi
0x1800ef55f  mov     rcx, rdi
0x1800ef562  lea     r8d, [r9+4]
0x1800ef566  call    cs:__imp_SetPermLayerState
0x1800ef56c  test    eax, eax
0x1800ef56e  jnz     short loc_1800EF589
0x1800ef570  lea     r9, aFailedToSetLay_0; "Failed to set layer [%d]"
0x1800ef577  mov     r8d, 2D4h
0x1800ef57d  mov     eax, 5
0x1800ef582  mov     ebx, eax
0x1800ef584  jmp     loc_1800EF4AE
0x1800ef589  xor     ebx, ebx
0x1800ef58b  test    r14d, r14d
0x1800ef58e  jz      short loc_1800EF596
0x1800ef590  call    cs:__imp_RevertToSelf
0x1800ef596  mov     eax, ebx
0x1800ef598  mov     rcx, [rbp+180h+var_30]
0x1800ef59f  xor     rcx, rsp; StackCookie
0x1800ef5a2  call    __security_check_cookie
0x1800ef5a7  mov     rbx, [rsp+280h+arg_18]
0x1800ef5af  add     rsp, 260h
0x1800ef5b6  pop     r14
0x1800ef5b8  pop     r12
0x1800ef5ba  pop     rdi
0x1800ef5bb  pop     rsi
0x1800ef5bc  pop     rbp
0x1800ef5bd  retn
```
