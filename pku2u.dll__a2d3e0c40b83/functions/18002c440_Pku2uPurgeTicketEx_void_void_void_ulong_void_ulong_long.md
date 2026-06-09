# Pku2uPurgeTicketEx(void * *,void *,void *,ulong,void * *,ulong *,long *)

- ea: `0x18002c440`
- end: `0x18002c8b6`
- name: `?Pku2uPurgeTicketEx@@YAJPEAPEAXPEAX1K0PEAKPEAJ@Z`
- size: `1142`
- prototype: `__int64 __fastcall(void **, char *, unsigned __int64, unsigned int, void **, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000af80`
- `0x18000d160`
- `0x180020a94`
- `0x180021a54`
- `0x180023cb8`
- `0x180023ce0`
- `0x18002c440`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c833`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002c810`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002c810`
- `ntdll!RtlLeaveCriticalSection` at `0x18002c89c`
- `ntdll!RtlLeaveCriticalSection` at `0x18002c89c`
- `ntdll!RtlEnterCriticalSection` at `0x18002c878`
- `ntdll!RtlEnterCriticalSection` at `0x18002c878`

## pseudocode

```c
__int64 __fastcall Pku2uPurgeTicketEx(
        void **a1,
        char *a2,
        unsigned __int64 a3,
        unsigned int a4,
        void **a5,
        unsigned int *a6,
        int *a7)
{
  unsigned __int64 v7; // r15
  int v10; // ebx
  int v11; // edi
  unsigned int v12; // ebx
  int *v13; // rdi
  unsigned __int64 v14; // rcx
  __int64 v15; // rdx
  unsigned __int64 v17; // rcx
  __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  __int64 v20; // rdx
  unsigned __int64 v21; // rcx
  __int64 v22; // rdx
  struct _LUID *v23; // rsi
  struct _RTL_CRITICAL_SECTION *LogonSession; // rax
  struct _RTL_CRITICAL_SECTION *v25; // rsi
  DWORD LastError; // eax
  struct _RTL_CRITICAL_SECTION *i; // rdi
  struct _LUID v28[2]; // [rsp+20h] [rbp-91h] BYREF
  HANDLE TokenHandle[2]; // [rsp+30h] [rbp-81h]
  int v30; // [rsp+40h] [rbp-71h] BYREF
  __int64 v31; // [rsp+44h] [rbp-6Dh]
  __int16 v32; // [rsp+50h] [rbp-61h]
  __int16 v33; // [rsp+52h] [rbp-5Fh]
  __int64 v34; // [rsp+58h] [rbp-59h]
  __int16 v35; // [rsp+60h] [rbp-51h]
  __int16 v36; // [rsp+62h] [rbp-4Fh]
  __int64 v37; // [rsp+68h] [rbp-49h]
  __int16 v38; // [rsp+70h] [rbp-41h]
  __int16 v39; // [rsp+72h] [rbp-3Fh]
  __int64 v40; // [rsp+78h] [rbp-39h]
  __int16 v41; // [rsp+80h] [rbp-31h]
  __int16 v42; // [rsp+82h] [rbp-2Fh]
  __int64 v43; // [rsp+88h] [rbp-29h]
  __int64 v44; // [rsp+90h] [rbp-21h]
  __int64 v45; // [rsp+98h] [rbp-19h]
  __int64 v46; // [rsp+A0h] [rbp-11h]
  int v47; // [rsp+A8h] [rbp-9h]
  int v48; // [rsp+ACh] [rbp-5h]
  __int128 v49; // [rsp+B0h] [rbp-1h] BYREF
  __int64 v50; // [rsp+C0h] [rbp+Fh]
  WINBOOL IsMember; // [rsp+108h] [rbp+57h] BYREF

  v7 = a4;
  *(_OWORD *)&v28[0].LowPart = 0;
  *(_OWORD *)TokenHandle = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_2ec2da8647393888de06a165c0eee983_Traceguids);
  v50 = 0;
  v49 = 0;
  if ( !((unsigned __int8 (__fastcall *)(__int128 *))Pku2uGlobalLsaFunctions->GetCallInfo)(&v49) )
  {
    v10 = -1073741595;
    goto LABEL_13;
  }
  v11 = BYTE8(v49) & 0x40;
  v12 = v11 != 0 ? 80 : 112;
  if ( (unsigned int)v7 < v12 )
  {
LABEL_12:
    v10 = -1073741811;
    goto LABEL_13;
  }
  memset_0(&v30, 0, 0x70u);
  if ( v11 )
  {
    v13 = &v30;
    v30 = *(_DWORD *)a2;
    v31 = *(_QWORD *)(a2 + 4);
    v32 = *((_WORD *)a2 + 8);
    v33 = *((_WORD *)a2 + 9);
    v34 = *((unsigned int *)a2 + 5);
    v35 = *((_WORD *)a2 + 12);
    v36 = *((_WORD *)a2 + 13);
    v37 = *((unsigned int *)a2 + 7);
    v38 = *((_WORD *)a2 + 16);
    v39 = *((_WORD *)a2 + 17);
    v40 = *((unsigned int *)a2 + 9);
    v41 = *((_WORD *)a2 + 20);
    v42 = *((_WORD *)a2 + 21);
    v43 = *((unsigned int *)a2 + 11);
    v44 = *((_QWORD *)a2 + 6);
    v45 = *((_QWORD *)a2 + 7);
    v46 = *((_QWORD *)a2 + 8);
    v47 = *((_DWORD *)a2 + 18);
    v48 = *((_DWORD *)a2 + 19);
  }
  else
  {
    v13 = (int *)a2;
  }
  v14 = *((_QWORD *)v13 + 3);
  v15 = *((unsigned __int16 *)v13 + 8);
  if ( v14 )
  {
    if ( (_WORD)v15 )
    {
      if ( v14 >= a3 )
        v14 -= a3;
      if ( !v14 )
        goto LABEL_12;
      if ( v14 > v7 )
        goto LABEL_12;
      if ( v14 + v15 > v7 )
        goto LABEL_12;
      if ( v14 < v12 )
        goto LABEL_12;
      if ( (v14 & 1) != 0 )
        goto LABEL_12;
      *((_WORD *)v13 + 9) = v15;
      *((_QWORD *)v13 + 3) = &a2[v14];
      if ( (v15 & 1) != 0 )
        goto LABEL_12;
    }
    else
    {
      *((_QWORD *)v13 + 3) = 0;
    }
  }
  else if ( (_WORD)v15 )
  {
    goto LABEL_12;
  }
  v17 = *((_QWORD *)v13 + 5);
  v18 = *((unsigned __int16 *)v13 + 16);
  if ( v17 )
  {
    if ( (_WORD)v18 )
    {
      if ( v17 >= a3 )
        v17 -= a3;
      if ( !v17 )
        goto LABEL_12;
      if ( v17 > v7 )
        goto LABEL_12;
      if ( v17 + v18 > v7 )
        goto LABEL_12;
      if ( v17 < v12 )
        goto LABEL_12;
      if ( (v17 & 1) != 0 )
        goto LABEL_12;
      *((_WORD *)v13 + 17) = v18;
      *((_QWORD *)v13 + 5) = &a2[v17];
      if ( (v18 & 1) != 0 )
        goto LABEL_12;
    }
    else
    {
      *((_QWORD *)v13 + 5) = 0;
    }
  }
  else if ( (_WORD)v18 )
  {
    goto LABEL_12;
  }
  v19 = *((_QWORD *)v13 + 7);
  v20 = *((unsigned __int16 *)v13 + 24);
  if ( v19 )
  {
    if ( (_WORD)v20 )
    {
      if ( v19 >= a3 )
        v19 -= a3;
      if ( !v19 )
        goto LABEL_12;
      if ( v19 > v7 )
        goto LABEL_12;
      if ( v19 + v20 > v7 )
        goto LABEL_12;
      if ( v19 < v12 )
        goto LABEL_12;
      if ( (v19 & 1) != 0 )
        goto LABEL_12;
      *((_WORD *)v13 + 25) = v20;
      *((_QWORD *)v13 + 7) = &a2[v19];
      if ( (v20 & 1) != 0 )
        goto LABEL_12;
    }
    else
    {
      *((_QWORD *)v13 + 7) = 0;
    }
  }
  else if ( (_WORD)v20 )
  {
    goto LABEL_12;
  }
  v21 = *((_QWORD *)v13 + 9);
  v22 = *((unsigned __int16 *)v13 + 32);
  if ( v21 )
  {
    if ( (_WORD)v22 )
    {
      if ( v21 >= a3 )
        v21 -= a3;
      if ( !v21 )
        goto LABEL_12;
      if ( v21 > v7 )
        goto LABEL_12;
      if ( v21 + v22 > v7 )
        goto LABEL_12;
      if ( v21 < v12 )
        goto LABEL_12;
      if ( (v21 & 1) != 0 )
        goto LABEL_12;
      *((_WORD *)v13 + 33) = v22;
      *((_QWORD *)v13 + 9) = &a2[v21];
      if ( (v22 & 1) != 0 )
        goto LABEL_12;
    }
    else
    {
      *((_QWORD *)v13 + 9) = 0;
    }
  }
  else if ( (_WORD)v22 )
  {
    goto LABEL_12;
  }
  v10 = ((__int64 (__fastcall *)(struct _LUID *))Pku2uGlobalLsaFunctions->GetClientInfo)(v28);
  if ( v10 < 0 )
    goto LABEL_13;
  v23 = (struct _LUID *)(v13 + 1);
  if ( *(_QWORD *)(v13 + 1) )
  {
    if ( !LOBYTE(TokenHandle[0]) )
    {
      IsMember = 0;
      if ( TokenHandle[1] )
      {
        if ( CheckTokenMembership(TokenHandle[1], Pku2uGlobalAliasAdminsSid, &IsMember) )
        {
          if ( !IsMember )
          {
            v10 = -1073741727;
            goto LABEL_13;
          }
          goto LABEL_66;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_2ec2da8647393888de06a165c0eee983_Traceguids, LastError);
        }
      }
      v10 = -1073741670;
      goto LABEL_13;
    }
  }
  else
  {
    v23 = v28;
  }
LABEL_66:
  LogonSession = (struct _RTL_CRITICAL_SECTION *)Pku2uLocateLogonSession(v23);
  v25 = LogonSession;
  if ( LogonSession )
  {
    if ( (v13[3] & 1) != 0 )
    {
      RtlEnterCriticalSection(LogonSession + 1);
      for ( i = (struct _RTL_CRITICAL_SECTION *)v25->LockSemaphore;
            i != (struct _RTL_CRITICAL_SECTION *)&v25->LockSemaphore;
            i = (struct _RTL_CRITICAL_SECTION *)i->DebugInfo )
      {
        Pku2uPurgeTicketCache(i + 1);
      }
      RtlLeaveCriticalSection(v25 + 1);
    }
    else
    {
      v10 = -1073741637;
    }
    Pku2uDereferenceLogonSession((struct _PKU2U_LOGON_SESSION *)v25);
  }
  else
  {
    v10 = -1073741729;
  }
LABEL_13:
  *a5 = 0;
  *a6 = 0;
  *a7 = v10;
  return 0;
}

```

## disassembly

```asm
0x18002c440  mov     [rsp-8+arg_0], rbx
0x18002c445  mov     [rsp-8+arg_10], rsi
0x18002c44a  push    rbp
0x18002c44b  push    rdi
0x18002c44c  push    r12
0x18002c44e  push    r14
0x18002c450  push    r15
0x18002c452  lea     rbp, [rsp-1Fh]
0x18002c457  sub     rsp, 0D0h
0x18002c45e  xorps   xmm0, xmm0
0x18002c461  mov     r15d, r9d
0x18002c464  movups  xmmword ptr [rsp+0F0h+var_D0.LowPart], xmm0
0x18002c469  mov     r14, r8
0x18002c46c  mov     rsi, rdx
0x18002c46f  movups  xmmword ptr [rsp+0F0h+TokenHandle], xmm0
0x18002c474  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c47b  lea     rax, WPP_GLOBAL_Control
0x18002c482  cmp     rcx, rax
0x18002c485  jz      short loc_18002C4A2
0x18002c487  test    byte ptr [rcx+1Ch], 4
0x18002c48b  jz      short loc_18002C4A2
0x18002c48d  mov     rcx, [rcx+10h]
0x18002c491  lea     r8, WPP_2ec2da8647393888de06a165c0eee983_Traceguids
0x18002c498  mov     edx, 0Ah
0x18002c49d  call    WPP_SF_
0x18002c4a2  xor     eax, eax
0x18002c4a4  lea     rcx, [rbp+3Fh+var_40]
0x18002c4a8  mov     [rbp+3Fh+var_30], rax
0x18002c4ac  xorps   xmm0, xmm0
0x18002c4af  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002c4b6  movups  [rbp+3Fh+var_40], xmm0
0x18002c4ba  mov     rax, [rax+0C0h]
0x18002c4c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4c6  xor     r12d, r12d
0x18002c4c9  test    al, al
0x18002c4cb  jnz     short loc_18002C4D7
0x18002c4cd  mov     ebx, 0C00000E5h
0x18002c4d2  jmp     loc_18002C5B8
0x18002c4d7  mov     edi, dword ptr [rbp+3Fh+var_40+8]
0x18002c4da  mov     r8d, 70h ; 'p'; Size
0x18002c4e0  and     edi, 40h
0x18002c4e3  mov     eax, edi
0x18002c4e5  neg     eax
0x18002c4e7  sbb     ebx, ebx
0x18002c4e9  and     ebx, 0FFFFFFE0h
0x18002c4ec  add     ebx, r8d
0x18002c4ef  cmp     r15d, ebx
0x18002c4f2  jb      loc_18002C5B3
0x18002c4f8  xor     edx, edx; Val
0x18002c4fa  lea     rcx, [rbp+3Fh+var_B0]; void *
0x18002c4fe  call    memset_0
0x18002c503  test    edi, edi
0x18002c505  jz      loc_18002C59E
0x18002c50b  mov     eax, [rsi]
0x18002c50d  lea     rdi, [rbp+3Fh+var_B0]
0x18002c511  mov     [rbp+3Fh+var_B0], eax
0x18002c514  mov     rax, [rsi+4]
0x18002c518  mov     [rbp+3Fh+var_AC], rax
0x18002c51c  movzx   eax, word ptr [rsi+10h]
0x18002c520  mov     [rbp+3Fh+var_A0], ax
0x18002c524  movzx   eax, word ptr [rsi+12h]
0x18002c528  mov     [rbp+3Fh+var_9E], ax
0x18002c52c  mov     eax, [rsi+14h]
0x18002c52f  mov     [rbp+3Fh+var_98], rax
0x18002c533  movzx   eax, word ptr [rsi+18h]
0x18002c537  mov     [rbp+3Fh+var_90], ax
0x18002c53b  movzx   eax, word ptr [rsi+1Ah]
0x18002c53f  mov     [rbp+3Fh+var_8E], ax
0x18002c543  mov     eax, [rsi+1Ch]
0x18002c546  mov     [rbp+3Fh+var_88], rax
0x18002c54a  movzx   eax, word ptr [rsi+20h]
0x18002c54e  mov     [rbp+3Fh+var_80], ax
0x18002c552  movzx   eax, word ptr [rsi+22h]
0x18002c556  mov     [rbp+3Fh+var_7E], ax
0x18002c55a  mov     eax, [rsi+24h]
0x18002c55d  mov     [rbp+3Fh+var_78], rax
0x18002c561  movzx   eax, word ptr [rsi+28h]
0x18002c565  mov     [rbp+3Fh+var_70], ax
0x18002c569  movzx   eax, word ptr [rsi+2Ah]
0x18002c56d  mov     [rbp+3Fh+var_6E], ax
0x18002c571  mov     eax, [rsi+2Ch]
0x18002c574  mov     [rbp+3Fh+var_68], rax
0x18002c578  mov     rax, [rsi+30h]
0x18002c57c  mov     [rbp+3Fh+var_60], rax
0x18002c580  mov     rax, [rsi+38h]
0x18002c584  mov     [rbp+3Fh+var_58], rax
0x18002c588  mov     rax, [rsi+40h]
0x18002c58c  mov     [rbp+3Fh+var_50], rax
0x18002c590  mov     eax, [rsi+48h]
0x18002c593  mov     [rbp+3Fh+var_48], eax
0x18002c596  mov     eax, [rsi+4Ch]
0x18002c599  mov     [rbp+3Fh+var_44], eax
0x18002c59c  jmp     short loc_18002C5A1
0x18002c59e  mov     rdi, rsi
0x18002c5a1  mov     rcx, [rdi+18h]
0x18002c5a5  movzx   edx, word ptr [rdi+10h]
0x18002c5a9  test    rcx, rcx
0x18002c5ac  jnz     short loc_18002C5EA
0x18002c5ae  test    dx, dx
0x18002c5b1  jz      short loc_18002C632
0x18002c5b3  mov     ebx, 0C000000Dh
0x18002c5b8  mov     rax, [rbp+3Fh+arg_20]
0x18002c5bc  lea     r11, [rsp+0F0h+var_20]
0x18002c5c4  mov     rsi, [r11+40h]
0x18002c5c8  mov     [rax], r12
0x18002c5cb  mov     rax, [rbp+3Fh+arg_28]
0x18002c5cf  mov     [rax], r12d
0x18002c5d2  mov     rax, [rbp+3Fh+arg_30]
0x18002c5d6  mov     [rax], ebx
0x18002c5d8  xor     eax, eax
0x18002c5da  mov     rbx, [r11+30h]
0x18002c5de  mov     rsp, r11
0x18002c5e1  pop     r15
0x18002c5e3  pop     r14
0x18002c5e5  pop     r12
0x18002c5e7  pop     rdi
0x18002c5e8  pop     rbp
0x18002c5e9  retn
0x18002c5ea  test    dx, dx
0x18002c5ed  jnz     short loc_18002C5F5
0x18002c5ef  mov     [rdi+18h], r12
0x18002c5f3  jmp     short loc_18002C632
0x18002c5f5  mov     rax, rcx
0x18002c5f8  sub     rax, r14
0x18002c5fb  cmp     rcx, r14
0x18002c5fe  cmovnb  rcx, rax
0x18002c602  test    rcx, rcx
0x18002c605  jz      short loc_18002C5B3
0x18002c607  cmp     rcx, r15
0x18002c60a  ja      short loc_18002C5B3
0x18002c60c  lea     rax, [rcx+rdx]
0x18002c610  cmp     rax, r15
0x18002c613  ja      short loc_18002C5B3
0x18002c615  mov     eax, ebx
0x18002c617  cmp     rcx, rax
0x18002c61a  jb      short loc_18002C5B3
0x18002c61c  test    cl, 1
0x18002c61f  jnz     short loc_18002C5B3
0x18002c621  mov     [rdi+12h], dx
0x18002c625  lea     rax, [rcx+rsi]
0x18002c629  mov     [rdi+18h], rax
0x18002c62d  test    dl, 1
0x18002c630  jnz     short loc_18002C5B3
0x18002c632  mov     rcx, [rdi+28h]
0x18002c636  movzx   edx, word ptr [rdi+20h]
0x18002c63a  test    rcx, rcx
0x18002c63d  jnz     short loc_18002C649
0x18002c63f  test    dx, dx
0x18002c642  jz      short loc_18002C6A9
0x18002c644  jmp     loc_18002C5B3
0x18002c649  test    dx, dx
0x18002c64c  jnz     short loc_18002C654
0x18002c64e  mov     [rdi+28h], r12
0x18002c652  jmp     short loc_18002C6A9
0x18002c654  mov     rax, rcx
0x18002c657  sub     rax, r14
0x18002c65a  cmp     rcx, r14
0x18002c65d  cmovnb  rcx, rax
0x18002c661  test    rcx, rcx
0x18002c664  jz      loc_18002C5B3
0x18002c66a  cmp     rcx, r15
0x18002c66d  ja      loc_18002C5B3
0x18002c673  lea     rax, [rcx+rdx]
0x18002c677  cmp     rax, r15
0x18002c67a  ja      loc_18002C5B3
0x18002c680  mov     eax, ebx
0x18002c682  cmp     rcx, rax
0x18002c685  jb      loc_18002C5B3
0x18002c68b  test    cl, 1
0x18002c68e  jnz     loc_18002C5B3
0x18002c694  mov     [rdi+22h], dx
0x18002c698  lea     rax, [rcx+rsi]
0x18002c69c  mov     [rdi+28h], rax
0x18002c6a0  test    dl, 1
0x18002c6a3  jnz     loc_18002C5B3
0x18002c6a9  mov     rcx, [rdi+38h]
0x18002c6ad  movzx   edx, word ptr [rdi+30h]
0x18002c6b1  test    rcx, rcx
0x18002c6b4  jnz     short loc_18002C6C0
0x18002c6b6  test    dx, dx
0x18002c6b9  jz      short loc_18002C720
0x18002c6bb  jmp     loc_18002C5B3
0x18002c6c0  test    dx, dx
0x18002c6c3  jnz     short loc_18002C6CB
0x18002c6c5  mov     [rdi+38h], r12
0x18002c6c9  jmp     short loc_18002C720
0x18002c6cb  mov     rax, rcx
0x18002c6ce  sub     rax, r14
0x18002c6d1  cmp     rcx, r14
0x18002c6d4  cmovnb  rcx, rax
0x18002c6d8  test    rcx, rcx
0x18002c6db  jz      loc_18002C5B3
0x18002c6e1  cmp     rcx, r15
0x18002c6e4  ja      loc_18002C5B3
0x18002c6ea  lea     rax, [rcx+rdx]
0x18002c6ee  cmp     rax, r15
0x18002c6f1  ja      loc_18002C5B3
0x18002c6f7  mov     eax, ebx
0x18002c6f9  cmp     rcx, rax
0x18002c6fc  jb      loc_18002C5B3
0x18002c702  test    cl, 1
0x18002c705  jnz     loc_18002C5B3
0x18002c70b  mov     [rdi+32h], dx
0x18002c70f  lea     rax, [rcx+rsi]
0x18002c713  mov     [rdi+38h], rax
0x18002c717  test    dl, 1
0x18002c71a  jnz     loc_18002C5B3
0x18002c720  mov     rcx, [rdi+48h]
0x18002c724  movzx   edx, word ptr [rdi+40h]
0x18002c728  test    rcx, rcx
0x18002c72b  jnz     short loc_18002C737
0x18002c72d  test    dx, dx
0x18002c730  jz      short loc_18002C797
0x18002c732  jmp     loc_18002C5B3
0x18002c737  test    dx, dx
0x18002c73a  jnz     short loc_18002C742
0x18002c73c  mov     [rdi+48h], r12
0x18002c740  jmp     short loc_18002C797
0x18002c742  mov     rax, rcx
0x18002c745  sub     rax, r14
0x18002c748  cmp     rcx, r14
0x18002c74b  cmovnb  rcx, rax
0x18002c74f  test    rcx, rcx
0x18002c752  jz      loc_18002C5B3
0x18002c758  cmp     rcx, r15
0x18002c75b  ja      loc_18002C5B3
0x18002c761  lea     rax, [rcx+rdx]
0x18002c765  cmp     rax, r15
0x18002c768  ja      loc_18002C5B3
0x18002c76e  mov     eax, ebx
0x18002c770  cmp     rcx, rax
0x18002c773  jb      loc_18002C5B3
0x18002c779  test    cl, 1
0x18002c77c  jnz     loc_18002C5B3
0x18002c782  mov     [rdi+42h], dx
0x18002c786  lea     rax, [rcx+rsi]
0x18002c78a  mov     [rdi+48h], rax
0x18002c78e  test    dl, 1
0x18002c791  jnz     loc_18002C5B3
0x18002c797  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18002c79e  lea     rcx, [rsp+0F0h+var_D0]
0x18002c7a3  mov     rax, [rax+80h]
0x18002c7aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7af  mov     ebx, eax
0x18002c7b1  test    eax, eax
0x18002c7b3  js      loc_18002C5B8
0x18002c7b9  mov     ecx, [rdi+8]
0x18002c7bc  lea     rsi, [rdi+4]
0x18002c7c0  or      ecx, [rsi]
0x18002c7c2  jnz     short loc_18002C7E7
0x18002c7c4  lea     rsi, [rsp+0F0h+var_D0]
0x18002c7c9  mov     rcx, rsi; struct _LUID *
0x18002c7cc  call    ?Pku2uLocateLogonSession@@YAPEAU_PKU2U_LOGON_SESSION@@PEAU_LUID@@@Z; Pku2uLocateLogonSession(_LUID *)
0x18002c7d1  mov     rsi, rax
0x18002c7d4  test    rax, rax
0x18002c7d7  jnz     loc_18002C86E
0x18002c7dd  mov     ebx, 0C000005Fh
0x18002c7e2  jmp     loc_18002C5B8
0x18002c7e7  cmp     byte ptr [rsp+0F0h+TokenHandle], r12b
0x18002c7ec  jnz     short loc_18002C7C9
0x18002c7ee  mov     rcx, [rbp+3Fh+TokenHandle+8]; TokenHandle
0x18002c7f2  mov     [rbp+3Fh+IsMember], r12d
0x18002c7f6  test    rcx, rcx
0x18002c7f9  jnz     short loc_18002C805
0x18002c7fb  mov     ebx, 0C000009Ah
0x18002c800  jmp     loc_18002C5B8
0x18002c805  mov     rdx, cs:?Pku2uGlobalAliasAdminsSid@@3PEAXEA; SidToCheck
0x18002c80c  lea     r8, [rbp+3Fh+IsMember]; IsMember
0x18002c810  call    cs:__imp_CheckTokenMembership
0x18002c816  test    eax, eax
0x18002c818  jnz     short loc_18002C85A
0x18002c81a  mov     rax, cs:WPP_GLOBAL_Control
0x18002c821  lea     rcx, WPP_GLOBAL_Control
0x18002c828  cmp     rax, rcx
0x18002c82b  jz      short loc_18002C7FB
0x18002c82d  test    byte ptr [rax+1Ch], 1
0x18002c831  jz      short loc_18002C7FB
0x18002c833  call    cs:__imp_GetLastError
0x18002c839  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c840  lea     r8, WPP_2ec2da8647393888de06a165c0eee983_Traceguids
0x18002c847  mov     edx, 0Bh
0x18002c84c  mov     r9d, eax
0x18002c84f  mov     rcx, [rcx+10h]
0x18002c853  call    WPP_SF_d
0x18002c858  jmp     short loc_18002C7FB
0x18002c85a  cmp     [rbp+3Fh+IsMember], r12d
0x18002c85e  jnz     loc_18002C7C9
0x18002c864  mov     ebx, 0C0000061h
0x18002c869  jmp     loc_18002C5B8
0x18002c86e  test    byte ptr [rdi+0Ch], 1
0x18002c872  jz      short loc_18002C8A4
0x18002c874  lea     rcx, [rax+28h]; CriticalSection
0x18002c878  call    cs:__imp_RtlEnterCriticalSection
0x18002c87e  lea     r14, [rsi+18h]
0x18002c882  mov     rdi, [r14]
0x18002c885  jmp     short loc_18002C893
0x18002c887  lea     rcx, [rdi+28h]; CriticalSection
0x18002c88b  call    ?Pku2uPurgeTicketCache@@YAXPEAU_PKU2U_PRIMARY_CREDENTIAL@@@Z; Pku2uPurgeTicketCache(_PKU2U_PRIMARY_CREDENTIAL *)
0x18002c890  mov     rdi, [rdi]
0x18002c893  cmp     rdi, r14
  ... truncated ...
```
