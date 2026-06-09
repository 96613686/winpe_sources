# WSTCreateUserModeContext(unsigned __int64,_SecBuffer *,_NEGOEXTS_UMODE_CONTEXT * *)

- ea: `0x18000e7a4`
- end: `0x18000e8e9`
- name: `?WSTCreateUserModeContext@@YAJ_KPEAU_SecBuffer@@PEAPEAU_NEGOEXTS_UMODE_CONTEXT@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(unsigned __int64, struct _SecBuffer *, struct _NEGOEXTS_UMODE_CONTEXT **)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d234`
- `0x180019200`

## callees

- `0x18000dbbc`
- `0x18000e710`
- `0x18000e7a4`
- `0x180019080`
- `0x1800193d4`
- `0x180019470`
- `0x180020010`

## string_xrefs

- `0x18000e87a`: `onecore\ds\security\protocols\negoexts\umctxt.cxx`

## pseudocode

```c
__int64 __fastcall WSTCreateUserModeContext(
        struct _NEGOEXTS_UMODE_CONTEXT *a1,
        struct _SecBuffer *a2,
        struct _NEGOEXTS_UMODE_CONTEXT **a3)
{
  bool v3; // cf
  _DWORD *pvBuffer; // rbp
  int v8; // eax
  struct _NEGOEXTS_UMODE_CONTEXT *v9; // rbx
  int v10; // edi
  struct _SECPKG_DLL_FUNCTIONS *v11; // rax
  __int64 v12; // rax
  struct _NEGOEXTS_UMODE_CONTEXT *v13; // rax
  struct _NEGOEXTS_UMODE_CONTEXT *v14; // [rsp+58h] [rbp+10h] BYREF

  v3 = a2->cbBuffer < 0x14;
  v14 = 0;
  if ( !v3 )
  {
    pvBuffer = a2->pvBuffer;
    v8 = WSTAllocateUserModeContext(&v14);
    v9 = v14;
    v10 = v8;
    if ( v8 >= 0 )
    {
      *((_QWORD *)v14 + 3) = 0x4F47454E54585455LL;
      *((_DWORD *)v9 + 10) = pvBuffer[2];
      v11 = NegoExtsGlobaDllFunctions;
      *((_DWORD *)v9 + 4) = 1;
      *((_QWORD *)v9 + 1) = 0;
      *(_QWORD *)v9 = 0;
      v12 = ((__int64 (__fastcall *)(_QWORD))v11->LocatePackageById)(*((unsigned int *)v9 + 10));
      *((_QWORD *)v9 + 6) = v12;
      if ( v12 )
      {
        v13 = v9;
        if ( a1 )
          v13 = a1;
        *((_QWORD *)v9 + 4) = v13;
        v10 = WSTInsertUserModeContext(v9);
        if ( v10 >= 0 )
        {
          *a3 = v9;
          return (unsigned int)v10;
        }
      }
      else
      {
        v10 = -1073741570;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)&WPP_8c1b4c250a203849e2737bc3a5ce992e_Traceguids,
        v10,
        (__int64)"onecore\\ds\\security\\protocols\\negoexts\\umctxt.cxx",
        97);
    if ( v9 )
      WSTFreeUserModeContext(v9);
    return (unsigned int)v10;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a2->cbBuffer);
  return 3221225485LL;
}

```

## disassembly

```asm
0x18000e7a4  mov     [rsp+arg_0], rbx
0x18000e7a9  mov     [rsp+arg_10], rbp
0x18000e7ae  push    rsi
0x18000e7af  push    rdi
0x18000e7b0  push    r14
0x18000e7b2  sub     rsp, 30h
0x18000e7b6  cmp     dword ptr [rdx], 14h
0x18000e7b9  mov     r14, r8
0x18000e7bc  mov     rsi, rcx
0x18000e7bf  mov     [rsp+48h+arg_8], 0
0x18000e7c8  jnb     short loc_18000E7F9
0x18000e7ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7d1  lea     rax, WPP_GLOBAL_Control
0x18000e7d8  cmp     rcx, rax
0x18000e7db  jz      short loc_18000E7EF
0x18000e7dd  test    byte ptr [rcx+1Ch], 1
0x18000e7e1  jz      short loc_18000E7EF
0x18000e7e3  mov     r9d, [rdx]
0x18000e7e6  mov     rcx, [rcx+10h]
0x18000e7ea  call    WPP_SF_DD
0x18000e7ef  mov     eax, 0C000000Dh
0x18000e7f4  jmp     loc_18000E8B1
0x18000e7f9  mov     rbp, [rdx+8]
0x18000e7fd  lea     rcx, [rsp+48h+arg_8]; struct _NEGOEXTS_UMODE_CONTEXT **
0x18000e802  call    ?WSTAllocateUserModeContext@@YAJPEAPEAU_NEGOEXTS_UMODE_CONTEXT@@@Z; WSTAllocateUserModeContext(_NEGOEXTS_UMODE_CONTEXT * *)
0x18000e807  mov     rbx, [rsp+48h+arg_8]
0x18000e80c  mov     edi, eax
0x18000e80e  test    eax, eax
0x18000e810  js      short loc_18000E85D
0x18000e812  mov     rax, 4F47454E54585455h
0x18000e81c  mov     [rbx+18h], rax
0x18000e820  mov     eax, [rbp+8]
0x18000e823  mov     [rbx+28h], eax
0x18000e826  mov     rax, cs:?NegoExtsGlobaDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * NegoExtsGlobaDllFunctions
0x18000e82d  mov     dword ptr [rbx+10h], 1
0x18000e834  mov     qword ptr [rbx+8], 0
0x18000e83c  mov     qword ptr [rbx], 0
0x18000e843  mov     rax, [rax+18h]
0x18000e847  mov     ecx, [rbx+28h]
0x18000e84a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e84f  mov     [rbx+30h], rax
0x18000e853  test    rax, rax
0x18000e856  jnz     short loc_18000E8C4
0x18000e858  mov     edi, 0C00000FEh
0x18000e85d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e864  lea     rax, WPP_GLOBAL_Control
0x18000e86b  cmp     rcx, rax
0x18000e86e  jz      short loc_18000E8A2
0x18000e870  test    byte ptr [rcx+1Ch], 1
0x18000e874  jz      short loc_18000E8A2
0x18000e876  mov     rcx, [rcx+10h]
0x18000e87a  lea     rax, aOnecoreDsSecur_1; "onecore\\ds\\security\\protocols\\negoe"...
0x18000e881  mov     edx, 0Bh
0x18000e886  mov     [rsp+48h+var_20], 261h
0x18000e88e  mov     r9d, edi
0x18000e891  mov     [rsp+48h+var_28], rax
0x18000e896  lea     r8, WPP_8c1b4c250a203849e2737bc3a5ce992e_Traceguids
0x18000e89d  call    WPP_SF_Dsd
0x18000e8a2  test    rbx, rbx
0x18000e8a5  jz      short loc_18000E8AF
0x18000e8a7  mov     rcx, rbx; struct _NEGOEXTS_UMODE_CONTEXT *
0x18000e8aa  call    ?WSTFreeUserModeContext@@YAXPEAU_NEGOEXTS_UMODE_CONTEXT@@@Z; WSTFreeUserModeContext(_NEGOEXTS_UMODE_CONTEXT *)
0x18000e8af  mov     eax, edi
0x18000e8b1  mov     rbx, [rsp+48h+arg_0]
0x18000e8b6  mov     rbp, [rsp+48h+arg_10]
0x18000e8bb  add     rsp, 30h
0x18000e8bf  pop     r14
0x18000e8c1  pop     rdi
0x18000e8c2  pop     rsi
0x18000e8c3  retn
0x18000e8c4  test    rsi, rsi
0x18000e8c7  mov     rax, rbx
0x18000e8ca  mov     rcx, rbx; struct _NEGOEXTS_UMODE_CONTEXT *
0x18000e8cd  cmovnz  rax, rsi
0x18000e8d1  mov     [rbx+20h], rax
0x18000e8d5  call    ?WSTInsertUserModeContext@@YAJPEAU_NEGOEXTS_UMODE_CONTEXT@@@Z; WSTInsertUserModeContext(_NEGOEXTS_UMODE_CONTEXT *)
0x18000e8da  mov     edi, eax
0x18000e8dc  test    eax, eax
0x18000e8de  js      loc_18000E85D
0x18000e8e4  mov     [r14], rbx
0x18000e8e7  jmp     short loc_18000E8AF
```
