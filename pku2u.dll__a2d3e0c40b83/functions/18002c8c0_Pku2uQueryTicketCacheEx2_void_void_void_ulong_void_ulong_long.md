# Pku2uQueryTicketCacheEx2(void * *,void *,void *,ulong,void * *,ulong *,long *)

- ea: `0x18002c8c0`
- end: `0x18002cbf8`
- name: `?Pku2uQueryTicketCacheEx2@@YAJPEAPEAXPEAX1K0PEAKPEAJ@Z`
- size: `824`
- prototype: `__int64 __fastcall(void **, char *, void *, unsigned int, void **, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000af80`
- `0x18000d160`
- `0x180018c80`
- `0x1800210f0`
- `0x180021a54`
- `0x18002bf78`
- `0x18002c168`
- `0x18002c8c0`
- `0x180044f20`
- `0x180046010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002caa3`
- `ntdll!RtlLeaveCriticalSection` at `0x18002caac`
- `ntdll!RtlLeaveCriticalSection` at `0x18002cba0`
- `ntdll!RtlLeaveCriticalSection` at `0x18002cba9`
- `ntdll!RtlLeaveCriticalSection` at `0x18002caa3`
- `ntdll!RtlLeaveCriticalSection` at `0x18002caac`
- `ntdll!RtlLeaveCriticalSection` at `0x18002cba0`
- `ntdll!RtlLeaveCriticalSection` at `0x18002cba9`
- `ntdll!RtlEnterCriticalSection` at `0x18002c9b6`
- `ntdll!RtlEnterCriticalSection` at `0x18002c9c3`
- `ntdll!RtlEnterCriticalSection` at `0x18002c9b6`
- `ntdll!RtlEnterCriticalSection` at `0x18002c9c3`

## pseudocode

```c
__int64 __fastcall Pku2uQueryTicketCacheEx2(
        void **a1,
        char *a2,
        void *a3,
        unsigned int a4,
        void **a5,
        unsigned int *a6,
        int *a7)
{
  unsigned int v7; // r12d
  unsigned int v8; // esi
  int v10; // edi
  struct _LUID *v11; // rcx
  struct _PKU2U_LOGON_SESSION *LogonSession; // r15
  struct _KERB_QUERY_TKT_CACHE_EX2_RESPONSE *v13; // rbx
  struct _RTL_CRITICAL_SECTION **v14; // r14
  struct _RTL_CRITICAL_SECTION *v15; // rbx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  void *v18; // rsp
  void *v19; // rsp
  _DWORD *v20; // rax
  signed __int64 v22; // rax
  struct _RTL_CRITICAL_SECTION *v23; // rdi
  void *v24; // rax
  __int64 v25; // [rsp+0h] [rbp-30h] BYREF
  _BYTE *v26; // [rsp+30h] [rbp+0h] BYREF
  unsigned int v27; // [rsp+38h] [rbp+8h] BYREF
  unsigned int v28[2]; // [rsp+40h] [rbp+10h] BYREF
  unsigned int v29; // [rsp+48h] [rbp+18h] BYREF
  unsigned __int8 *v30; // [rsp+50h] [rbp+20h] BYREF
  __int128 v31; // [rsp+58h] [rbp+28h] BYREF
  __int64 v32; // [rsp+68h] [rbp+38h]
  struct _LUID v33[2]; // [rsp+70h] [rbp+40h] BYREF
  __int128 v34; // [rsp+80h] [rbp+50h]

  v7 = 0;
  v26 = 0;
  v28[0] = 0;
  v30 = 0;
  v8 = 8;
  v27 = 8;
  v29 = 0;
  *(_OWORD *)&v33[0].LowPart = 0;
  v34 = 0;
  if ( a4 < 0xC )
  {
    v10 = -1073741811;
    goto LABEL_34;
  }
  v10 = ((__int64 (__fastcall *)(struct _LUID *, char *, void *))Pku2uGlobalLsaFunctions->GetClientInfo)(v33, a2, a3);
  if ( v10 >= 0 )
  {
    v11 = (struct _LUID *)(a2 + 4);
    if ( !*(_QWORD *)(a2 + 4) )
    {
      v11 = v33;
      goto LABEL_6;
    }
    if ( (_BYTE)v34 )
    {
LABEL_6:
      LogonSession = Pku2uLocateLogonSession(v11);
      if ( !LogonSession )
      {
        v10 = -1073741729;
        goto LABEL_32;
      }
      v32 = 0;
      v31 = 0;
      if ( ((unsigned __int8 (__fastcall *)(__int128 *))Pku2uGlobalLsaFunctions->GetCallInfo)(&v31) )
      {
        RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)LogonSession + 1);
        RtlEnterCriticalSection(&Pku2uGlobalTicketListLock);
        v14 = (struct _RTL_CRITICAL_SECTION **)((char *)LogonSession + 24);
        v15 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)LogonSession + 3);
        if ( v15 != (struct _RTL_CRITICAL_SECTION *)((char *)LogonSession + 24) )
        {
          do
          {
            KerbComputeTicketCacheSizeEx2(
              (struct _PKU2U_PRIMARY_CREDENTIAL *)&v15[1],
              (BYTE8(v31) & 0x40) != 0,
              &v27,
              v28);
            v15 = (struct _RTL_CRITICAL_SECTION *)v15->DebugInfo;
          }
          while ( v15 != (struct _RTL_CRITICAL_SECTION *)v14 );
          v8 = v27;
          v7 = v28[0];
        }
        v13 = 0;
        if ( !v8
          || v8 > (unsigned __int64)g_ulMaxStackAllocSize
          || (unsigned __int64)v8 + g_ulAdditionalProbeSize + 8 < v8
          || !(unsigned int)VerifyStackAvailable() )
        {
          goto LABEL_43;
        }
        v16 = v8 + 23LL;
        if ( v16 <= (unsigned __int64)v8 + 8 )
          v16 = 0xFFFFFFFFFFFFFF0LL;
        v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
        v18 = alloca(v17);
        v19 = alloca(v17);
        v13 = (struct _KERB_QUERY_TKT_CACHE_EX2_RESPONSE *)&v26;
        if ( &v25 == (__int64 *)-48LL
          || (LODWORD(v26) = 1801679955, (v13 = (struct _KERB_QUERY_TKT_CACHE_EX2_RESPONSE *)&v27) == 0) )
        {
LABEL_43:
          if ( (unsigned __int64)v8 + 8 >= v8 )
          {
            v20 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
            v13 = (struct _KERB_QUERY_TKT_CACHE_EX2_RESPONSE *)v20;
            if ( v20 )
            {
              *v20 = 1885431112;
              v13 = (struct _KERB_QUERY_TKT_CACHE_EX2_RESPONSE *)(v20 + 2);
            }
          }
        }
        if ( v13 )
        {
          memset_0(v13, 0, v8);
          v10 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _BYTE **))Pku2uGlobalLsaFunctions->AllocateClientBuffer)(
                  0,
                  v8,
                  &v26);
          if ( v10 >= 0 )
          {
            v22 = v26 - (_BYTE *)v13;
            v13->MessageType = KerbQueryTicketCacheEx2Message;
            v13->CountOfTickets = v7;
            v23 = *v14;
            *(_QWORD *)v28 = v22;
            while ( v23 != (struct _RTL_CRITICAL_SECTION *)v14 )
            {
              KerbBuildQueryTicketCacheResponseEx2(v23 + 1, v13, (BYTE8(v31) & 0x40) != 0, (__int64 *)v28, &v30, &v29);
              v23 = (struct _RTL_CRITICAL_SECTION *)v23->DebugInfo;
            }
            RtlLeaveCriticalSection(&Pku2uGlobalTicketListLock);
            RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)LogonSession + 1);
            v10 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _BYTE *, struct _KERB_QUERY_TKT_CACHE_EX2_RESPONSE *))Pku2uGlobalLsaFunctions->CopyToClientBuffer)(
                    0,
                    v8,
                    v26,
                    v13);
            if ( v10 >= 0 )
            {
              v24 = v26;
              v26 = 0;
              *a5 = v24;
              *a6 = v8;
            }
            goto LABEL_29;
          }
        }
        else
        {
          v10 = -1073741670;
        }
        RtlLeaveCriticalSection(&Pku2uGlobalTicketListLock);
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)LogonSession + 1);
      }
      else
      {
        v13 = 0;
        v10 = -1073741595;
      }
LABEL_29:
      Pku2uDereferenceLogonSession(LogonSession);
      if ( v13 && v13[-1].Tickets[0].SessionKeyType == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      goto LABEL_32;
    }
    v10 = -1073741727;
  }
LABEL_32:
  if ( v26 )
    ((void (__fastcall *)(_QWORD))Pku2uGlobalLsaFunctions->FreeClientBuffer)(0);
LABEL_34:
  *a7 = v10;
  return 0;
}

```

## disassembly

```asm
0x18002c8c0  push    rbp
0x18002c8c2  push    rbx
0x18002c8c3  push    rsi
0x18002c8c4  push    rdi
0x18002c8c5  push    r12
0x18002c8c7  push    r13
0x18002c8c9  push    r14
0x18002c8cb  push    r15
0x18002c8cd  sub     rsp, 0A8h
0x18002c8d4  lea     rbp, [rsp+30h]
0x18002c8d9  mov     rax, cs:__security_cookie
0x18002c8e0  xor     rax, rbp
0x18002c8e3  mov     [rbp+0B0h+var_50], rax
0x18002c8e7  xor     r12d, r12d
0x18002c8ea  mov     [rbp+0B0h+var_B0], 0
0x18002c8f2  mov     [rbp+0B0h+var_A0], r12d
0x18002c8f6  xorps   xmm0, xmm0
0x18002c8f9  mov     [rbp+0B0h+var_90], r12
0x18002c8fd  mov     esi, 8
0x18002c902  mov     [rbp+0B0h+var_A8], esi
0x18002c905  mov     rbx, rdx
0x18002c908  mov     [rbp+0B0h+var_98], r12d
0x18002c90c  movups  xmmword ptr [rbp+0B0h+var_70.LowPart], xmm0
0x18002c910  movups  [rbp+0B0h+var_60], xmm0
0x18002c914  cmp     r9d, 0Ch
0x18002c918  jnb     short loc_18002C924
0x18002c91a  mov     edi, 0C000000Dh
0x18002c91f  jmp     loc_18002CAF2
0x18002c924  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002c92b  lea     rcx, [rbp+0B0h+var_70]
0x18002c92f  mov     rax, [rax+80h]
0x18002c936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c93b  mov     edi, eax
0x18002c93d  test    eax, eax
0x18002c93f  js      loc_18002CAD7
0x18002c945  mov     eax, [rbx+8]
0x18002c948  lea     rcx, [rbx+4]
0x18002c94c  or      eax, [rcx]
0x18002c94e  jnz     short loc_18002C96B
0x18002c950  lea     rcx, [rbp+0B0h+var_70]; struct _LUID *
0x18002c954  call    ?Pku2uLocateLogonSession@@YAPEAU_PKU2U_LOGON_SESSION@@PEAU_LUID@@@Z; Pku2uLocateLogonSession(_LUID *)
0x18002c959  mov     r15, rax
0x18002c95c  test    rax, rax
0x18002c95f  jnz     short loc_18002C97B
0x18002c961  mov     edi, 0C000005Fh
0x18002c966  jmp     loc_18002CAD7
0x18002c96b  cmp     byte ptr [rbp+0B0h+var_60], r12b
0x18002c96f  jnz     short loc_18002C954
0x18002c971  mov     edi, 0C0000061h
0x18002c976  jmp     loc_18002CAD7
0x18002c97b  xor     eax, eax
0x18002c97d  lea     rcx, [rbp+0B0h+var_88]
0x18002c981  mov     [rbp+0B0h+var_78], rax
0x18002c985  xorps   xmm0, xmm0
0x18002c988  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002c98f  movups  [rbp+0B0h+var_88], xmm0
0x18002c993  mov     rax, [rax+0C0h]
0x18002c99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c99f  test    al, al
0x18002c9a1  jnz     short loc_18002C9AF
0x18002c9a3  xor     ebx, ebx
0x18002c9a5  mov     edi, 0C00000E5h
0x18002c9aa  jmp     loc_18002CAB2
0x18002c9af  lea     r13, [r15+28h]
0x18002c9b3  mov     rcx, r13; CriticalSection
0x18002c9b6  call    cs:__imp_RtlEnterCriticalSection
0x18002c9bc  lea     rcx, ?Pku2uGlobalTicketListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002c9c3  call    cs:__imp_RtlEnterCriticalSection
0x18002c9c9  lea     r14, [r15+18h]
0x18002c9cd  mov     rbx, [r14]
0x18002c9d0  cmp     rbx, r14
0x18002c9d3  jz      short loc_18002C9FE
0x18002c9d5  mov     edx, dword ptr [rbp+0B0h+var_88+8]
0x18002c9d8  lea     rcx, [rbx+28h]; struct _PKU2U_PRIMARY_CREDENTIAL *
0x18002c9dc  shr     edx, 6
0x18002c9df  lea     r9, [rbp+0B0h+var_A0]; unsigned int *
0x18002c9e3  and     dl, 1; unsigned __int8
0x18002c9e6  lea     r8, [rbp+0B0h+var_A8]; unsigned int *
0x18002c9ea  call    ?KerbComputeTicketCacheSizeEx2@@YAXPEAU_PKU2U_PRIMARY_CREDENTIAL@@EPEAK1@Z; KerbComputeTicketCacheSizeEx2(_PKU2U_PRIMARY_CREDENTIAL *,uchar,ulong *,ulong *)
0x18002c9ef  mov     rbx, [rbx]
0x18002c9f2  cmp     rbx, r14
0x18002c9f5  jnz     short loc_18002C9D5
0x18002c9f7  mov     esi, [rbp+0B0h+var_A8]
0x18002c9fa  mov     r12d, [rbp+0B0h+var_A0]
0x18002c9fe  xor     ebx, ebx
0x18002ca00  mov     edi, esi
0x18002ca02  test    esi, esi
0x18002ca04  jz      short loc_18002CA67
0x18002ca06  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18002ca0d  ja      short loc_18002CA67
0x18002ca0f  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002ca16  add     rcx, 8
0x18002ca1a  add     rcx, rdi
0x18002ca1d  cmp     rcx, rdi
0x18002ca20  jb      short loc_18002CA67
0x18002ca22  call    VerifyStackAvailable
0x18002ca27  test    eax, eax
0x18002ca29  jz      short loc_18002CA67
0x18002ca2b  lea     rax, [rdi+8]
0x18002ca2f  lea     rcx, [rax+0Fh]
0x18002ca33  cmp     rcx, rax
0x18002ca36  ja      short loc_18002CA42
0x18002ca38  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002ca42  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002ca46  mov     rax, rcx
0x18002ca49  call    _alloca_probe
0x18002ca4e  sub     rsp, rcx
0x18002ca51  lea     rbx, [rsp+0E0h+var_B0]
0x18002ca56  test    rbx, rbx
0x18002ca59  jz      short loc_18002CA67
0x18002ca5b  mov     dword ptr [rbx], 6B637453h
0x18002ca61  add     rbx, 8
0x18002ca65  jnz     short loc_18002CA8E
0x18002ca67  lea     rcx, [rdi+8]
0x18002ca6b  cmp     rcx, rdi
0x18002ca6e  jb      short loc_18002CA8E
0x18002ca70  mov     rax, cs:g_pfnAllocate
0x18002ca77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca7c  mov     rbx, rax
0x18002ca7f  test    rax, rax
0x18002ca82  jz      short loc_18002CA8E
0x18002ca84  mov     dword ptr [rax], 70616548h
0x18002ca8a  add     rbx, 8
0x18002ca8e  test    rbx, rbx
0x18002ca91  jnz     loc_18002CB1A
0x18002ca97  mov     edi, 0C000009Ah
0x18002ca9c  lea     rcx, ?Pku2uGlobalTicketListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002caa3  call    cs:__imp_RtlLeaveCriticalSection
0x18002caa9  mov     rcx, r13; CriticalSection
0x18002caac  call    cs:__imp_RtlLeaveCriticalSection
0x18002cab2  mov     rcx, r15; struct _PKU2U_LOGON_SESSION *
0x18002cab5  call    ?Pku2uDereferenceLogonSession@@YAXPEAU_PKU2U_LOGON_SESSION@@@Z; Pku2uDereferenceLogonSession(_PKU2U_LOGON_SESSION *)
0x18002caba  test    rbx, rbx
0x18002cabd  jz      short loc_18002CAD7
0x18002cabf  lea     rcx, [rbx-8]
0x18002cac3  cmp     dword ptr [rcx], 70616548h
0x18002cac9  jnz     short loc_18002CAD7
0x18002cacb  mov     rax, cs:g_pfnFree
0x18002cad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cad7  mov     rdx, [rbp+0B0h+var_B0]
0x18002cadb  test    rdx, rdx
0x18002cade  jz      short loc_18002CAF2
0x18002cae0  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002cae7  xor     ecx, ecx
0x18002cae9  mov     rax, [rax+40h]
0x18002caed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002caf2  mov     rax, [rbp+0B0h+arg_30]
0x18002caf9  mov     [rax], edi
0x18002cafb  xor     eax, eax
0x18002cafd  mov     rcx, [rbp+0B0h+var_50]
0x18002cb01  xor     rcx, rbp; StackCookie
0x18002cb04  call    __security_check_cookie
0x18002cb09  lea     rsp, [rbp+78h]
0x18002cb0d  pop     r15
0x18002cb0f  pop     r14
0x18002cb11  pop     r13
0x18002cb13  pop     r12
0x18002cb15  pop     rdi
0x18002cb16  pop     rsi
0x18002cb17  pop     rbx
0x18002cb18  pop     rbp
0x18002cb19  retn
0x18002cb1a  mov     r8, rdi; Size
0x18002cb1d  xor     edx, edx; Val
0x18002cb1f  mov     rcx, rbx; void *
0x18002cb22  call    memset_0
0x18002cb27  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002cb2e  lea     r8, [rbp+0B0h+var_B0]
0x18002cb32  mov     edx, esi
0x18002cb34  xor     ecx, ecx
0x18002cb36  mov     rax, [rax+38h]
0x18002cb3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb3f  mov     edi, eax
0x18002cb41  test    eax, eax
0x18002cb43  js      loc_18002CA9C
0x18002cb49  mov     rax, [rbp+0B0h+var_B0]
0x18002cb4d  sub     rax, rbx
0x18002cb50  mov     dword ptr [rbx], 14h
0x18002cb56  mov     [rbx+4], r12d
0x18002cb5a  mov     rdi, [r14]
0x18002cb5d  mov     qword ptr [rbp+0B0h+var_A0], rax
0x18002cb61  jmp     short loc_18002CB94
0x18002cb63  mov     r8d, dword ptr [rbp+0B0h+var_88+8]
0x18002cb67  lea     rax, [rbp+0B0h+var_98]
0x18002cb6b  mov     [rsp+0E0h+var_B8], rax; unsigned int *
0x18002cb70  lea     rcx, [rdi+28h]; CriticalSection
0x18002cb74  shr     r8d, 6
0x18002cb78  lea     rax, [rbp+0B0h+var_90]
0x18002cb7c  and     r8b, 1; unsigned __int8
0x18002cb80  mov     [rsp+0E0h+var_C0], rax; unsigned __int8 **
0x18002cb85  lea     r9, [rbp+0B0h+var_A0]; __int64 *
0x18002cb89  mov     rdx, rbx; struct _KERB_QUERY_TKT_CACHE_EX2_RESPONSE *
0x18002cb8c  call    ?KerbBuildQueryTicketCacheResponseEx2@@YAXPEAU_PKU2U_PRIMARY_CREDENTIAL@@PEAU_KERB_QUERY_TKT_CACHE_EX2_RESPONSE@@EPEA_JPEAPEAEPEAK@Z; KerbBuildQueryTicketCacheResponseEx2(_PKU2U_PRIMARY_CREDENTIAL *,_KERB_QUERY_TKT_CACHE_EX2_RESPONSE *,uchar,__int64 *,uchar * *,ulong *)
0x18002cb91  mov     rdi, [rdi]
0x18002cb94  cmp     rdi, r14
0x18002cb97  jnz     short loc_18002CB63
0x18002cb99  lea     rcx, ?Pku2uGlobalTicketListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002cba0  call    cs:__imp_RtlLeaveCriticalSection
0x18002cba6  mov     rcx, r13; CriticalSection
0x18002cba9  call    cs:__imp_RtlLeaveCriticalSection
0x18002cbaf  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002cbb6  mov     r9, rbx
0x18002cbb9  mov     r8, [rbp+0B0h+var_B0]
0x18002cbbd  mov     edx, esi
0x18002cbbf  xor     ecx, ecx
0x18002cbc1  mov     rax, [rax+48h]
0x18002cbc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbca  mov     edi, eax
0x18002cbcc  test    eax, eax
0x18002cbce  js      loc_18002CAB2
0x18002cbd4  mov     rax, [rbp+0B0h+var_B0]
0x18002cbd8  mov     rcx, [rbp+0B0h+arg_20]
0x18002cbdf  mov     [rbp+0B0h+var_B0], 0
0x18002cbe7  mov     [rcx], rax
0x18002cbea  mov     rax, [rbp+0B0h+arg_28]
0x18002cbf1  mov     [rax], esi
0x18002cbf3  jmp     loc_18002CAB2
```
