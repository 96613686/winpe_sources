# LsaApCallPackageUntrusted

- ea: `0x180011090`
- end: `0x1800112ae`
- name: `LsaApCallPackageUntrusted`
- size: `542`
- prototype: `__int64 __fastcall(__int64, int *, __int64, unsigned int, _QWORD *, _DWORD *, __int64)`
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180007740`
- `0x1800078d0`
- `0x18000d4b0`
- `0x18000d7c0`
- `0x180011090`
- `0x180024c00`
- `0x180025c50`
- `0x18002fb50`
- `0x180034720`
- `0x180036960`
- `0x18003cf50`
- `0x18003d430`
- `0x18003d6a0`
- `0x18003da90`
- `0x18003db30`
- `0x18003dcf0`
- `0x18003e230`
- `0x18003e380`
- `0x18003e3a0`
- `0x18003e6a0`
- `0x18003eb40`
- `0x1800462b0`
- `0x180046700`
- `0x180055dc0`
- `0x180055e00`
- `0x18006d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180011175`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180011175`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180011168`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180011168`

## pseudocode

```c
__int64 __fastcall LsaApCallPackageUntrusted(
        __int64 a1,
        int *a2,
        __int64 a3,
        unsigned int a4,
        _QWORD *a5,
        _DWORD *a6,
        __int64 a7)
{
  __int64 v11; // rdi
  __int64 (*ImpersonateClient)(void); // rax
  __int64 result; // rax
  int v14; // eax
  int v15; // eax
  __int64 v16; // [rsp+30h] [rbp-71h]
  WINBOOL IsMember; // [rsp+40h] [rbp-61h] BYREF
  __int64 v18; // [rsp+48h] [rbp-59h]
  __int128 v19; // [rsp+50h] [rbp-51h] BYREF
  __int64 v20; // [rsp+60h] [rbp-41h]
  _OWORD v21[2]; // [rsp+68h] [rbp-39h] BYREF
  _DWORD SidToCheck[4]; // [rsp+88h] [rbp-19h] BYREF

  v18 = a7;
  v20 = 0;
  v19 = 0;
  if ( a4 < 4 )
    return 3221225485LL;
  v11 = *a2;
  if ( (_DWORD)v11 == 1026 )
    return 3221225506LL;
  if ( (unsigned int)v11 >= 0x19 )
    return 3221225485LL;
  if ( (_DWORD)v11 == 10 )
  {
    memset(v21, 0, sizeof(v21));
    result = ((__int64 (__fastcall *)(_OWORD *))LsaFunctions->GetClientInfo)(v21);
    if ( (int)result < 0 )
      return result;
    if ( a4 >= 0x18 )
    {
      if ( *(_QWORD *)&v21[0] != *(_QWORD *)(a2 + 1) || *(_QWORD *)&v21[0] == 999 )
        return 3221225506LL;
      goto LABEL_8;
    }
    return 3221225485LL;
  }
  if ( (_DWORD)v11 == 19 || (_DWORD)v11 == 12 )
  {
    if ( a4 >= 0xC )
    {
      if ( (a2[1] & 0xFFFFFFE3) == 0 )
      {
LABEL_8:
        IsMember = 0;
        SidToCheck[0] = 257;
        SidToCheck[1] = 83886080;
        ImpersonateClient = (__int64 (*)(void))LsaFunctions->ImpersonateClient;
        SidToCheck[2] = 6;
        result = ImpersonateClient();
        if ( (int)result < 0 )
          return result;
        if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
          IsMember = 0;
        RevertToSelf();
        if ( !IsMember )
          return 3221225506LL;
        goto LABEL_12;
      }
      return 3221225506LL;
    }
    return 3221225485LL;
  }
  if ( (unsigned int)v11 <= 0xD )
  {
    v14 = 8268;
    if ( _bittest(&v14, v11) )
      goto LABEL_8;
  }
  if ( (unsigned int)v11 > 0xF )
    return 3221225506LL;
  v15 = 32801;
  if ( !_bittest(&v15, v11) )
    return 3221225506LL;
LABEL_12:
  if ( !((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v19) )
    return 3221225701LL;
  if ( (BYTE8(v19) & 0x40) != 0 && (unsigned int)(v11 - 5) > 1 )
    return 3221225659LL;
  v16 = v18;
  *a5 = 0;
  *a6 = 0;
  return MspCallPackageDispatch[v11](a1, (int)a2, a3, a4, (__int64)a5, (__int64)a6, v16);
}

```

## disassembly

```asm
0x180011090  push    rbp
0x180011092  push    rbx
0x180011093  push    rsi
0x180011094  push    rdi
0x180011095  push    r12
0x180011097  push    r13
0x180011099  push    r14
0x18001109b  push    r15
0x18001109d  lea     rbp, [rsp-7]
0x1800110a2  sub     rsp, 0A8h
0x1800110a9  mov     rax, cs:__security_cookie
0x1800110b0  xor     rax, rsp
0x1800110b3  mov     [rbp+3Fh+var_48], rax
0x1800110b7  mov     rax, [rbp+3Fh+arg_30]
0x1800110bb  xorps   xmm0, xmm0
0x1800110be  mov     r14, [rbp+3Fh+arg_20]
0x1800110c2  mov     esi, r9d
0x1800110c5  mov     r15, [rbp+3Fh+arg_28]
0x1800110c9  mov     r13, r8
0x1800110cc  mov     [rbp+3Fh+var_98], rax
0x1800110d0  mov     rbx, rdx
0x1800110d3  xor     eax, eax
0x1800110d5  mov     r12, rcx
0x1800110d8  mov     [rbp+3Fh+var_80], rax
0x1800110dc  movups  [rbp+3Fh+var_90], xmm0
0x1800110e0  cmp     r9d, 4
0x1800110e4  jb      loc_1800112A4
0x1800110ea  movsxd  rdi, dword ptr [rdx]
0x1800110ed  cmp     edi, 402h
0x1800110f3  jz      loc_180011234
0x1800110f9  cmp     edi, 19h
0x1800110fc  jnb     loc_1800112A4
0x180011102  cmp     edi, 0Ah
0x180011105  jz      loc_180011242
0x18001110b  cmp     edi, 13h
0x18001110e  jnz     loc_180011205
0x180011114  cmp     esi, 0Ch
0x180011117  jb      loc_1800112A4
0x18001111d  test    dword ptr [rdx+4], 0FFFFFFE3h
0x180011124  jnz     loc_180011234
0x18001112a  mov     rax, cs:LsaFunctions
0x180011131  mov     [rbp+3Fh+IsMember], 0
0x180011138  mov     [rbp+3Fh+SidToCheck], 101h
0x18001113f  mov     [rbp+3Fh+var_54], 5000000h
0x180011146  mov     rax, [rax+58h]
0x18001114a  mov     [rbp+3Fh+var_50], 6
0x180011151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011156  test    eax, eax
0x180011158  js      loc_1800111E5
0x18001115e  lea     r8, [rbp+3Fh+IsMember]; IsMember
0x180011162  xor     ecx, ecx; TokenHandle
0x180011164  lea     rdx, [rbp+3Fh+SidToCheck]; SidToCheck
0x180011168  call    cs:__imp_CheckTokenMembership
0x18001116e  test    eax, eax
0x180011170  jnz     short loc_180011175
0x180011172  mov     [rbp+3Fh+IsMember], eax
0x180011175  call    cs:__imp_RevertToSelf
0x18001117b  cmp     [rbp+3Fh+IsMember], 0
0x18001117f  jz      loc_180011234
0x180011185  mov     rax, cs:LsaFunctions
0x18001118c  lea     rcx, [rbp+3Fh+var_90]
0x180011190  mov     rax, [rax+0C0h]
0x180011197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001119c  test    al, al
0x18001119e  jz      loc_18001123B
0x1800111a4  test    byte ptr [rbp+3Fh+var_90+8], 40h
0x1800111a8  jnz     loc_18001128E
0x1800111ae  mov     rcx, [rbp+3Fh+var_98]
0x1800111b2  lea     r10, MspCallPackageDispatch
0x1800111b9  xor     eax, eax
0x1800111bb  mov     [rsp+0E0h+var_B0], rcx
0x1800111c0  mov     [r14], rax
0x1800111c3  mov     r9d, esi
0x1800111c6  mov     [r15], eax
0x1800111c9  mov     r8, r13
0x1800111cc  mov     rax, ds:(MspCallPackageDispatch - 18006E220h)[r10+rdi*8]
0x1800111d0  mov     rdx, rbx
0x1800111d3  mov     [rsp+0E0h+var_B8], r15
0x1800111d8  mov     rcx, r12
0x1800111db  mov     [rsp+0E0h+var_C0], r14
0x1800111e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111e5  mov     rcx, [rbp+3Fh+var_48]
0x1800111e9  xor     rcx, rsp; StackCookie
0x1800111ec  call    __security_check_cookie
0x1800111f1  add     rsp, 0A8h
0x1800111f8  pop     r15
0x1800111fa  pop     r14
0x1800111fc  pop     r13
0x1800111fe  pop     r12
0x180011200  pop     rdi
0x180011201  pop     rsi
0x180011202  pop     rbx
0x180011203  pop     rbp
0x180011204  retn
0x180011205  cmp     edi, 0Ch
0x180011208  jz      loc_180011114
0x18001120e  cmp     edi, 0Dh
0x180011211  ja      short loc_180011221
0x180011213  mov     eax, 204Ch
0x180011218  bt      eax, edi
0x18001121b  jb      loc_18001112A
0x180011221  cmp     edi, 0Fh
0x180011224  ja      short loc_180011234
0x180011226  mov     eax, 8021h
0x18001122b  bt      eax, edi
0x18001122e  jb      loc_180011185
0x180011234  mov     eax, 0C0000022h
0x180011239  jmp     short loc_1800111E5
0x18001123b  mov     eax, 0C00000E5h
0x180011240  jmp     short loc_1800111E5
0x180011242  mov     rax, cs:LsaFunctions
0x180011249  lea     rcx, [rbp+3Fh+var_78]
0x18001124d  movups  [rbp+3Fh+var_78], xmm0
0x180011251  movups  [rbp+3Fh+var_68], xmm0
0x180011255  mov     rax, [rax+80h]
0x18001125c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011261  test    eax, eax
0x180011263  js      short loc_1800111E5
0x180011265  cmp     esi, 18h
0x180011268  jb      short loc_1800112A4
0x18001126a  mov     eax, dword ptr [rbp+3Fh+var_78]
0x18001126d  cmp     eax, [rbx+4]
0x180011270  jnz     short loc_180011234
0x180011272  mov     ecx, dword ptr [rbp+3Fh+var_78+4]
0x180011275  cmp     ecx, [rbx+8]
0x180011278  jnz     short loc_180011234
0x18001127a  cmp     eax, 3E7h
0x18001127f  jnz     loc_18001112A
0x180011285  test    ecx, ecx
0x180011287  jz      short loc_180011234
0x180011289  jmp     loc_18001112A
0x18001128e  lea     eax, [rdi-5]
0x180011291  cmp     eax, 1
0x180011294  jbe     loc_1800111AE
0x18001129a  mov     eax, 0C00000BBh
0x18001129f  jmp     loc_1800111E5
0x1800112a4  mov     eax, 0C000000Dh
0x1800112a9  jmp     loc_1800111E5
```
