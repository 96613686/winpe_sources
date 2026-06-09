# MakeTokenInformationV2(_APPLUGIN_USER_INFO *,_LSA_TOKEN_INFORMATION_V1 * *)

- ea: `0x18002c3f0`
- end: `0x18002c68f`
- name: `?MakeTokenInformationV2@@YAJPEAU_APPLUGIN_USER_INFO@@PEAPEAU_LSA_TOKEN_INFORMATION_V1@@@Z`
- size: `671`
- prototype: `__int64 __fastcall(struct _APPLUGIN_USER_INFO *, struct _LSA_TOKEN_INFORMATION_V1 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180011960`
- `0x180056d60`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18002c3f0`
- `0x18004317c`
- `0x180081010`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002c421`
- `ntdll!RtlLengthSid` at `0x18002c4a7`
- `ntdll!RtlLengthSid` at `0x18002c4c9`
- `ntdll!RtlLengthSid` at `0x18002c5a1`
- `ntdll!RtlLengthSid` at `0x18002c5ea`
- `ntdll!RtlLengthSid` at `0x18002c421`
- `ntdll!RtlLengthSid` at `0x18002c4a7`
- `ntdll!RtlLengthSid` at `0x18002c4c9`
- `ntdll!RtlLengthSid` at `0x18002c5a1`
- `ntdll!RtlLengthSid` at `0x18002c5ea`
- `ntdll!RtlCopySid` at `0x18002c4b8`
- `ntdll!RtlCopySid` at `0x18002c4da`
- `ntdll!RtlCopySid` at `0x18002c5ff`
- `ntdll!RtlCopySid` at `0x18002c4b8`
- `ntdll!RtlCopySid` at `0x18002c4da`
- `ntdll!RtlCopySid` at `0x18002c5ff`

## string_xrefs

- `0x18002c52f`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18002c62f`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`

## pseudocode

```c
__int64 __fastcall MakeTokenInformationV2(struct _APPLUGIN_USER_INFO *a1, struct _LSA_TOKEN_INFORMATION_V1 **a2)
{
  __int64 v2; // rdi
  struct _LSA_TOKEN_INFORMATION_V1 **v3; // r12
  int i; // ebx
  ULONG v6; // ebx
  union _LARGE_INTEGER *v7; // r14
  union _LARGE_INTEGER *v8; // r13
  ULONG v9; // eax
  __int64 v10; // rbx
  char *v11; // r13
  ULONG v12; // eax
  __int64 v13; // rbx
  __int64 result; // rax
  const char *v15; // r9
  char v16; // cl
  const char *v17; // rdx
  bool v18; // zf
  unsigned int v19; // r12d
  __int64 v20; // rsi
  __int64 v21; // rbx
  ULONG v22; // eax
  __int64 v23; // rdi
  const char *v24; // rax
  __int64 v26; // [rsp+90h] [rbp+18h]

  v2 = 0;
  v3 = a2;
  for ( i = 16 * *((_DWORD *)a1 + 6) + 72; (unsigned int)v2 < *((_DWORD *)a1 + 6); v2 = (unsigned int)(v2 + 1) )
    i += RtlLengthSid(*(PSID *)(*((_QWORD *)a1 + 4) + 8 * v2));
  v6 = i + 2 * RtlLengthSid(*((PSID *)a1 + 2));
  v7 = (union _LARGE_INTEGER *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(v6);
  if ( v7 )
  {
    v26 = v6;
    memset_0(v7, 0, v6);
    *v7 = g_TimeForever;
    v7[3].QuadPart = (LONGLONG)&v7[8];
    v7[8].LowPart = *((_DWORD *)a1 + 6);
    v8 = &v7[2 * *((unsigned int *)a1 + 6) + 9];
    if ( *((_DWORD *)a1 + 6) )
    {
      v19 = 0;
      do
      {
        v20 = 2LL * v19;
        v21 = 8LL * v19;
        *(_DWORD *)(v7[3].QuadPart + 16LL * v19 + 16) = 7;
        v22 = RtlLengthSid(*(PSID *)(*((_QWORD *)a1 + 4) + v21));
        v23 = v22;
        RtlCopySid(v22, v8, *(PSID *)(v21 + *((_QWORD *)a1 + 4)));
        ++v19;
        *(_QWORD *)(v7[3].QuadPart + 8 * v20 + 8) = v8;
        v8 = (union _LARGE_INTEGER *)((char *)v8 + v23);
      }
      while ( v19 < *((_DWORD *)a1 + 6) );
      v3 = a2;
    }
    v7[1].QuadPart = (LONGLONG)v8;
    v9 = RtlLengthSid(*((PSID *)a1 + 2));
    v10 = v9;
    RtlCopySid(v9, v8, *((PSID *)a1 + 2));
    v11 = (char *)v8 + v10;
    v7[4].QuadPart = (LONGLONG)v11;
    v12 = RtlLengthSid(*((PSID *)a1 + 2));
    v13 = v12;
    RtlCopySid(v12, v11, *((PSID *)a1 + 2));
    if ( (char *)v7 + v26 < &v11[v13] )
    {
      v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225701LL, v24, 4643, "Programming error", &Class);
      ((void (__fastcall *)(union _LARGE_INTEGER *))g_pLsaFunctionTable->FreeLsaHeap)(v7);
      return 3221225701LL;
    }
    else
    {
      v7[5].QuadPart = 0;
      result = 0;
      v7[6].QuadPart = 0;
      v7[7].QuadPart = 0;
      *v3 = (struct _LSA_TOKEN_INFORMATION_V1 *)v7;
    }
  }
  else
  {
    v15 = "";
    while ( 1 )
    {
      v16 = *(v15 - 1);
      v17 = v15--;
      v18 = v16 == 92;
      if ( v16 == 92 )
        break;
      if ( v15 <= "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" )
      {
        v18 = v16 == 92;
        break;
      }
    }
    if ( v18 )
      v15 = v17;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v15, 4590, "AllocateLsaHeap", &Class);
    return 3221225495LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002c3f0  mov     [rsp+arg_8], rdx
0x18002c3f5  push    rbx
0x18002c3f6  push    rbp
0x18002c3f7  push    rdi
0x18002c3f8  push    r12
0x18002c3fa  push    r14
0x18002c3fc  push    r15
0x18002c3fe  sub     rsp, 48h
0x18002c402  mov     eax, [rcx+18h]
0x18002c405  xor     edi, edi
0x18002c407  mov     ebx, eax
0x18002c409  mov     r12, rdx
0x18002c40c  shl     ebx, 4
0x18002c40f  mov     rbp, rcx
0x18002c412  add     ebx, 48h ; 'H'
0x18002c415  test    eax, eax
0x18002c417  jnz     loc_18002C599
0x18002c41d  mov     rcx, [rbp+10h]; Sid
0x18002c421  call    cs:__imp_RtlLengthSid
0x18002c427  lea     ebx, [rbx+rax*2]
0x18002c42a  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18002c431  mov     ecx, ebx
0x18002c433  mov     rax, [rax+28h]
0x18002c437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c43c  mov     r14, rax
0x18002c43f  test    rax, rax
0x18002c442  jz      loc_18002C528
0x18002c448  mov     eax, ebx
0x18002c44a  xor     edx, edx; Val
0x18002c44c  mov     r8d, ebx; Size
0x18002c44f  mov     rcx, r14; void *
0x18002c452  mov     [rsp+78h+arg_10], rax
0x18002c45a  mov     [rsp+78h+var_38], r13
0x18002c45f  call    memset_0
0x18002c464  mov     rax, cs:?g_TimeForever@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER g_TimeForever
0x18002c46b  lea     rdx, [r14+40h]
0x18002c46f  mov     [r14], rax
0x18002c472  mov     [r14+18h], rdx
0x18002c476  mov     eax, [rbp+18h]
0x18002c479  mov     [rdx], eax
0x18002c47b  mov     ecx, [rbp+18h]
0x18002c47e  mov     r13d, ecx
0x18002c481  mov     [rsp+78h+arg_0], 0
0x18002c48c  shl     r13, 4
0x18002c490  add     r13, 8
0x18002c494  add     r13, rdx
0x18002c497  test    ecx, ecx
0x18002c499  jnz     loc_18002C5B5
0x18002c49f  mov     [r14+8], r13
0x18002c4a3  mov     rcx, [rbp+10h]; Sid
0x18002c4a7  call    cs:__imp_RtlLengthSid
0x18002c4ad  mov     r8, [rbp+10h]; SourceSid
0x18002c4b1  mov     rdx, r13; DestinationSid
0x18002c4b4  mov     ecx, eax; DestinationSidLength
0x18002c4b6  mov     ebx, eax
0x18002c4b8  call    cs:__imp_RtlCopySid
0x18002c4be  add     r13, rbx
0x18002c4c1  mov     [r14+20h], r13
0x18002c4c5  mov     rcx, [rbp+10h]; Sid
0x18002c4c9  call    cs:__imp_RtlLengthSid
0x18002c4cf  mov     r8, [rbp+10h]; SourceSid
0x18002c4d3  mov     rdx, r13; DestinationSid
0x18002c4d6  mov     ecx, eax; DestinationSidLength
0x18002c4d8  mov     ebx, eax
0x18002c4da  call    cs:__imp_RtlCopySid
0x18002c4e0  mov     rax, [rsp+78h+arg_10]
0x18002c4e8  add     rbx, r13
0x18002c4eb  mov     r13, [rsp+78h+var_38]
0x18002c4f0  add     rax, r14
0x18002c4f3  cmp     rax, rbx
0x18002c4f6  jb      loc_18002C62F
0x18002c4fc  mov     qword ptr [r14+28h], 0
0x18002c504  xor     eax, eax
0x18002c506  mov     qword ptr [r14+30h], 0
0x18002c50e  mov     qword ptr [r14+38h], 0
0x18002c516  mov     [r12], r14
0x18002c51a  add     rsp, 48h
0x18002c51e  pop     r15
0x18002c520  pop     r14
0x18002c522  pop     r12
0x18002c524  pop     rdi
0x18002c525  pop     rbp
0x18002c526  pop     rbx
0x18002c527  retn
0x18002c528  lea     r9, aOnecoreDsExtCl_6+27h; ""
0x18002c52f  lea     rax, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18002c536  movzx   ecx, byte ptr [r9-1]
0x18002c53b  mov     rdx, r9
0x18002c53e  dec     r9
0x18002c541  cmp     cl, 5Ch ; '\'
0x18002c544  jz      short loc_18002C54E
0x18002c546  cmp     r9, rax
0x18002c549  ja      short loc_18002C536
0x18002c54b  cmp     cl, 5Ch ; '\'
0x18002c54e  cmovz   r9, rdx
0x18002c552  lea     rcx, Class
0x18002c559  mov     [rsp+78h+var_48], rcx
0x18002c55e  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002c565  lea     rcx, aAllocatelsahea_3; "AllocateLsaHeap"
0x18002c56c  mov     r8d, 0C0000017h
0x18002c572  mov     [rsp+78h+var_50], rcx
0x18002c577  xor     ecx, ecx
0x18002c579  mov     [rsp+78h+var_58], 11EEh
0x18002c581  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002c586  mov     eax, 0C0000017h
0x18002c58b  add     rsp, 48h
0x18002c58f  pop     r15
0x18002c591  pop     r14
0x18002c593  pop     r12
0x18002c595  pop     rdi
0x18002c596  pop     rbp
0x18002c597  pop     rbx
0x18002c598  retn
0x18002c599  mov     rcx, [rbp+20h]
0x18002c59d  mov     rcx, [rcx+rdi*8]; Sid
0x18002c5a1  call    cs:__imp_RtlLengthSid
0x18002c5a7  add     ebx, eax
0x18002c5a9  inc     edi
0x18002c5ab  cmp     edi, [rbp+18h]
0x18002c5ae  jb      short loc_18002C599
0x18002c5b0  jmp     loc_18002C41D
0x18002c5b5  mov     r12d, [rsp+78h+arg_0]
0x18002c5bd  mov     [rsp+78h+arg_18], rsi
0x18002c5c5  mov     rax, [r14+18h]
0x18002c5c9  mov     ecx, r12d
0x18002c5cc  mov     esi, r12d
0x18002c5cf  add     rsi, rsi
0x18002c5d2  lea     rbx, ds:0[rcx*8]
0x18002c5da  mov     dword ptr [rax+rsi*8+10h], 7
0x18002c5e2  mov     rcx, [rbp+20h]
0x18002c5e6  mov     rcx, [rcx+rbx]; Sid
0x18002c5ea  call    cs:__imp_RtlLengthSid
0x18002c5f0  mov     r8, [rbp+20h]
0x18002c5f4  mov     rdx, r13; DestinationSid
0x18002c5f7  mov     ecx, eax; DestinationSidLength
0x18002c5f9  mov     edi, eax
0x18002c5fb  mov     r8, [rbx+r8]; SourceSid
0x18002c5ff  call    cs:__imp_RtlCopySid
0x18002c605  mov     rcx, [r14+18h]
0x18002c609  inc     r12d
0x18002c60c  mov     [rcx+rsi*8+8], r13
0x18002c611  add     r13, rdi
0x18002c614  cmp     r12d, [rbp+18h]
0x18002c618  jb      short loc_18002C5C5
0x18002c61a  mov     rsi, [rsp+78h+arg_18]
0x18002c622  mov     r12, [rsp+78h+arg_8]
0x18002c62a  jmp     loc_18002C49F
0x18002c62f  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18002c636  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002c63b  lea     rcx, Class
0x18002c642  mov     r9, rax
0x18002c645  mov     [rsp+78h+var_48], rcx
0x18002c64a  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002c651  lea     rcx, aProgrammingErr; "Programming error"
0x18002c658  mov     r8d, 0C00000E5h
0x18002c65e  mov     [rsp+78h+var_50], rcx
0x18002c663  xor     ecx, ecx
0x18002c665  mov     [rsp+78h+var_58], 1223h
0x18002c66d  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002c672  mov     rdx, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18002c679  mov     rcx, r14
0x18002c67c  mov     rax, [rdx+30h]
0x18002c680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c685  mov     eax, 0C00000E5h
0x18002c68a  jmp     loc_18002C51A
```
