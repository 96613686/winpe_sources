# DsRolepEventWriteHelper(_EVENT_DESCRIPTOR const *,ushort *,ulong,char *)

- ea: `0x180019b34`
- end: `0x18001a162`
- name: `?DsRolepEventWriteHelper@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGKPEAD@Z`
- size: `1582`
- prototype: `__int64 __fastcall(const struct _EVENT_DESCRIPTOR *, unsigned __int16 *, __int64, char *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001e204`

## callees

- `0x180019b34`
- `0x18001dbdc`
- `0x18001e234`
- `0x180020dbc`
- `0x180027d44`
- `0x18002af90`
- `0x18002c01e`
- `0x18002c050`
- `0x18002c0e0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019f9d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019f9d`
- `ntdll!RtlLeaveCriticalSection` at `0x180019bd2`
- `ntdll!RtlLeaveCriticalSection` at `0x180019bd2`
- `ntdll!RtlEnterCriticalSection` at `0x180019bb2`
- `ntdll!RtlEnterCriticalSection` at `0x180019bb2`

## string_xrefs

- `0x18001a0a3`: `EventWrite( %u ) failed - %u\n`

## pseudocode

```c
__int64 __fastcall DsRolepEventWriteHelper(
        const struct _EVENT_DESCRIPTOR *a1,
        unsigned __int16 *a2,
        __int64 a3,
        char *a4)
{
  const struct _EVENT_DESCRIPTOR *v5; // r13
  char *v6; // r14
  __int64 v7; // rcx
  unsigned __int64 *v8; // rsi
  unsigned int v9; // ebx
  __int64 i; // rdx
  void **v11; // r8
  unsigned __int64 *v12; // rdi
  unsigned __int64 v13; // r13
  unsigned __int64 v14; // rbx
  __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  void *v17; // rsp
  void *v18; // rsp
  unsigned __int64 *v19; // rax
  unsigned int v20; // r12d
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rbx
  __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  void *v25; // rsp
  void *v26; // rsp
  unsigned __int64 *v27; // rax
  unsigned int v28; // r15d
  unsigned __int64 v29; // rax
  unsigned __int16 *v30; // r13
  unsigned __int64 *v31; // rbx
  unsigned __int64 v32; // r14
  unsigned __int64 v33; // rcx
  __int64 v34; // rcx
  unsigned __int64 v35; // rcx
  void *v36; // rsp
  void *v37; // rsp
  unsigned __int64 *v38; // rax
  unsigned __int64 v39; // r14
  unsigned __int64 v40; // r10
  _WORD *v41; // r9
  unsigned __int64 v42; // rax
  void **v43; // rcx
  unsigned __int64 v44; // rax
  unsigned __int64 v45; // rbx
  void *v46; // rcx
  DWORD LengthSid; // eax
  DWORD v48; // ecx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  unsigned int v52; // eax
  unsigned int j; // edi
  unsigned __int64 v54; // rcx
  _DWORD *v55; // rcx
  _BYTE v57[48]; // [rsp+0h] [rbp-30h] BYREF
  unsigned __int64 v58; // [rsp+30h] [rbp+0h] BYREF
  DWORD v59; // [rsp+38h] [rbp+8h] BYREF
  char *v60; // [rsp+40h] [rbp+10h]
  DWORD v61; // [rsp+48h] [rbp+18h] BYREF
  int v62; // [rsp+50h] [rbp+20h]
  unsigned __int64 v63; // [rsp+58h] [rbp+28h]
  unsigned __int16 *v64; // [rsp+60h] [rbp+30h]
  const struct _EVENT_DESCRIPTOR *v65; // [rsp+68h] [rbp+38h]
  wchar_t Buffer[264]; // [rsp+80h] [rbp+50h] BYREF

  v64 = a2;
  v65 = a1;
  v5 = a1;
  v61 = 0;
  v59 = 0;
  v60 = a4;
  v6 = a4;
  memset_0(Buffer, 0, 0x20Au);
  v8 = 0;
  v58 = 0;
  if ( !g_DsRoleRegistrationHandle )
  {
    v9 = 0;
    RtlEnterCriticalSection(&g_DsRoleRegistrationHandleCS);
    if ( !g_DsRoleRegistrationHandle )
      v9 = DsRolepInitializeEvents();
    RtlLeaveCriticalSection(&g_DsRoleRegistrationHandleCS);
    if ( v9 )
    {
      v39 = 0;
      goto LABEL_99;
    }
  }
  v12 = 0;
  if ( !a2 )
  {
    v20 = 0;
    goto LABEL_92;
  }
  v13 = -1;
  do
    ++v13;
  while ( a2[v13] );
  v14 = 8 * v13;
  v8 = 0;
  if ( !(8 * v13)
    || v14 > g_ulMaxStackAllocSize
    || v14 + g_ulAdditionalProbeSize + 8 < v14
    || !(unsigned int)((__int64 (*)(void))VerifyStackAvailable)() )
  {
    goto LABEL_110;
  }
  v15 = v14 + 23;
  if ( v14 + 23 <= v14 + 8 )
    v15 = 0xFFFFFFFFFFFFFF0LL;
  v16 = v15 & 0xFFFFFFFFFFFFFFF0uLL;
  v17 = alloca(v16);
  v18 = alloca(v16);
  v8 = &v58;
  if ( v57 == (_BYTE *)-48LL || (LODWORD(v58) = 1801679955, (v8 = (unsigned __int64 *)&v59) == 0) )
  {
LABEL_110:
    if ( v14 + 8 >= v14 )
    {
      v19 = (unsigned __int64 *)((__int64 (*)(void))g_pfnAllocate)();
      v8 = v19;
      if ( v19 )
      {
        *(_DWORD *)v19 = 1885431112;
        v8 = v19 + 1;
      }
    }
  }
  if ( !v8 )
    return 8;
  memset_0(v8, 0, 8 * v13);
  if ( v13 > 0x7F )
    v13 = 127;
  v20 = 0;
  v63 = v13;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v7 = (unsigned int)i;
    v21 = -1;
    do
      ++v21;
    while ( a2[v21] );
    if ( (unsigned int)i >= v21 )
      break;
    if ( a2[(unsigned int)i] == 98 )
    {
      v20 += 2;
    }
    else
    {
      if ( a2[(unsigned int)i] != 100 && a2[(unsigned int)i] != 101 && a2[(unsigned int)i] != 115 )
      {
        v7 = (unsigned int)a2[(unsigned int)i] - 116;
        if ( (unsigned int)v7 > 1 )
          break;
      }
      ++v20;
    }
  }
  if ( v20 )
  {
    v12 = 0;
    v22 = 16LL * v20;
    if ( !v22
      || v22 > g_ulMaxStackAllocSize
      || v22 + g_ulAdditionalProbeSize + 8 < v22
      || !(unsigned int)((__int64 (*)(void))VerifyStackAvailable)() )
    {
      goto LABEL_111;
    }
    v23 = v22 + 23;
    if ( v22 + 23 <= v22 + 8 )
      v23 = 0xFFFFFFFFFFFFFF0LL;
    v24 = v23 & 0xFFFFFFFFFFFFFFF0uLL;
    v25 = alloca(v24);
    v26 = alloca(v24);
    v12 = &v58;
    if ( v57 == (_BYTE *)-48LL || (LODWORD(v58) = 1801679955, (v12 = (unsigned __int64 *)&v59) == 0) )
    {
LABEL_111:
      if ( v22 + 8 >= v22 )
      {
        v27 = (unsigned __int64 *)((__int64 (*)(void))g_pfnAllocate)();
        v12 = v27;
        if ( v27 )
        {
          *(_DWORD *)v27 = 1885431112;
          v12 = v27 + 1;
        }
      }
    }
    if ( !v12 )
    {
      v9 = 8;
      goto LABEL_105;
    }
    memset_0(v12, 0, 16LL * v20);
  }
  v28 = 0;
  v29 = 0;
  while ( 1 )
  {
    v62 = v29;
    if ( v29 >= v13 )
      break;
    v11 = (void **)v6;
    switch ( v64[v29] )
    {
      case 'b':
        v59 = *(_DWORD *)v6;
        v51 = v28++;
        v51 *= 2;
        i = 2LL * v28;
        v12[v51] = (unsigned __int64)&v59;
        v12[v51 + 1] = 4;
        v44 = *((_QWORD *)v6 + 1);
        v6 += 16;
        v7 = v59;
LABEL_85:
        HIDWORD(v12[i + 1]) = 0;
        LODWORD(v12[i + 1]) = v7;
        v12[i] = v44;
        break;
      case 'd':
        v7 = (__int64)&v61;
        v61 = *(_DWORD *)v6;
        v6 += 8;
        v50 = 2LL * v28;
        v12[v50] = (unsigned __int64)&v61;
        v12[v50 + 1] = 4;
        break;
      case 'e':
        v48 = *(_DWORD *)v6;
        v6 += 8;
        v60 = v6;
        populateStatusString(v48, Buffer, (unsigned int)v11);
        v49 = -1;
        do
          ++v49;
        while ( Buffer[v49] );
        i = (__int64)Buffer;
        v7 = 2LL * v28;
        LengthSid = 2 * v49 + 2;
        v12[2 * v28] = (unsigned __int64)Buffer;
        goto LABEL_79;
      case 's':
        v45 = *(_QWORD *)v6;
        v6 += 8;
        v46 = *v11;
        v60 = v6;
        LengthSid = GetLengthSid(v46);
        v7 = 2LL * v28;
        v12[2 * v28] = v45;
LABEL_79:
        LODWORD(v12[v7 + 1]) = LengthSid;
        HIDWORD(v12[v7 + 1]) = 0;
        goto LABEL_87;
      case 't':
        v6 += 8;
        v7 = 2LL * v28;
        v12[v7] = (unsigned __int64)*v11;
        v12[v7 + 1] = 16;
        break;
      case 'u':
        v30 = *(unsigned __int16 **)v6;
        v31 = 0;
        v32 = **(unsigned __int16 **)v6 + 2LL;
        if ( v32 > g_ulMaxStackAllocSize )
          goto LABEL_112;
        v33 = v32 + g_ulAdditionalProbeSize + 8;
        if ( v33 < v32 || !(unsigned int)VerifyStackAvailable(v33, i, v11) )
          goto LABEL_112;
        v34 = v32 + 23;
        if ( v32 + 23 <= v32 + 8 )
          v34 = 0xFFFFFFFFFFFFFF0LL;
        v35 = v34 & 0xFFFFFFFFFFFFFFF0uLL;
        v36 = alloca(v35);
        v37 = alloca(v35);
        v31 = &v58;
        if ( v57 == (_BYTE *)-48LL || (LODWORD(v58) = 1801679955, (v31 = (unsigned __int64 *)&v59) == 0) )
        {
LABEL_112:
          if ( v32 + 8 >= v32 )
          {
            v38 = (unsigned __int64 *)((__int64 (__fastcall *)(unsigned __int64, __int64, void **))g_pfnAllocate)(
                                        v32 + 8,
                                        i,
                                        v11);
            v31 = v38;
            if ( v38 )
            {
              *(_DWORD *)v38 = 1885431112;
              v31 = v38 + 1;
            }
          }
        }
        v39 = v58;
        v8[v58] = (unsigned __int64)v31;
        if ( !v31 )
        {
          v9 = 8;
          goto LABEL_95;
        }
        memset_0(v31, 0, *v30 + 2LL);
        v40 = v39;
        v41 = (_WORD *)*((_QWORD *)v30 + 1);
        v11 = (void **)v8[v39];
        v42 = (unsigned __int64)*v30 >> 1;
        i = v42 + 1;
        do
        {
          if ( !v42 )
            break;
          if ( !*v41 )
            break;
          *(_WORD *)v11 = *v41++;
          v11 = (void **)((char *)v11 + 2);
          --v42;
          --i;
        }
        while ( i );
        v43 = (void **)((char *)v11 - 2);
        if ( i )
          v43 = v11;
        v9 = i == 0 ? 0x80000005 : 0;
        *(_WORD *)v43 = 0;
        if ( !i )
          goto LABEL_95;
        v7 = (unsigned int)*v30 + 2;
        v44 = v8[v39];
        v6 = v60 + 8;
        v13 = v63;
        i = 2LL * v28;
        v58 = v40 + 1;
        goto LABEL_85;
      default:
        v9 = 87;
        goto LABEL_94;
    }
    v60 = v6;
LABEL_87:
    v29 = (unsigned int)(v62 + 1);
    ++v28;
  }
  v5 = v65;
LABEL_92:
  v52 = CEventWrite(v7, v5, v20, v12);
  v9 = v52;
  if ( v52 )
    DsRolepLogPrintRoutine(1, "EventWrite( %u ) failed - %u\n", v5->Id, v52);
LABEL_94:
  v39 = v58;
LABEL_95:
  if ( v12 && *((_DWORD *)v12 - 2) == 1885431112 )
    ((void (__fastcall *)(unsigned __int64 *, __int64, void **, _QWORD))g_pfnFree)(v12 - 1, i, v11, 0);
LABEL_99:
  for ( j = 0; j < v39; ++j )
  {
    v54 = v8[j];
    if ( v54 )
    {
      v55 = (_DWORD *)(v54 - 8);
      if ( *v55 == 1885431112 )
        ((void (__fastcall *)(_DWORD *, __int64, void **, _QWORD))g_pfnFree)(v55, i, v11, 0);
    }
  }
  if ( v8 )
  {
LABEL_105:
    if ( *((_DWORD *)v8 - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  return v9;
}

```

## disassembly

```asm
0x180019b34  push    rbp
0x180019b36  push    rsi
0x180019b37  push    rdi
0x180019b38  push    r12
0x180019b3a  push    r13
0x180019b3c  push    r14
0x180019b3e  push    r15
0x180019b40  sub     rsp, 2A0h
0x180019b47  lea     rbp, [rsp+30h]
0x180019b4c  mov     [rbp+2A0h+arg_10], rbx
0x180019b53  mov     rax, cs:__security_cookie
0x180019b5a  xor     rax, rbp
0x180019b5d  mov     [rbp+2A0h+var_40], rax
0x180019b64  xor     r11d, r11d
0x180019b67  mov     [rbp+2A0h+var_270], rdx
0x180019b6b  mov     r15, rdx
0x180019b6e  mov     [rbp+2A0h+var_268], rcx
0x180019b72  mov     r13, rcx
0x180019b75  mov     [rbp+2A0h+var_288], r11d
0x180019b79  xor     edx, edx; Val
0x180019b7b  mov     [rbp+2A0h+var_298], r11d
0x180019b7f  lea     rcx, [rbp+2A0h+Buffer]; void *
0x180019b83  mov     [rbp+2A0h+var_290], r9
0x180019b87  mov     r8d, 20Ah; Size
0x180019b8d  mov     r14, r9
0x180019b90  call    memset_0
0x180019b95  xor     r9d, r9d
0x180019b98  cmp     cs:?g_DsRoleRegistrationHandle@@3_KA, r9; unsigned __int64 g_DsRoleRegistrationHandle
0x180019b9f  mov     esi, r9d
0x180019ba2  mov     [rbp+2A0h+var_2A0], r9
0x180019ba6  jnz     short loc_180019BE3
0x180019ba8  lea     rcx, ?g_DsRoleRegistrationHandleCS@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180019baf  mov     ebx, r9d
0x180019bb2  call    cs:__imp_RtlEnterCriticalSection
0x180019bb8  xor     r11d, r11d
0x180019bbb  cmp     cs:?g_DsRoleRegistrationHandle@@3_KA, r11; unsigned __int64 g_DsRoleRegistrationHandle
0x180019bc2  jnz     short loc_180019BCB
0x180019bc4  call    DsRolepInitializeEvents
0x180019bc9  mov     ebx, eax
0x180019bcb  lea     rcx, ?g_DsRoleRegistrationHandleCS@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180019bd2  call    cs:__imp_RtlLeaveCriticalSection
0x180019bd8  xor     r9d, r9d
0x180019bdb  test    ebx, ebx
0x180019bdd  jnz     loc_18001A0E0
0x180019be3  mov     rdi, r9
0x180019be6  test    r15, r15
0x180019be9  jz      loc_18001A07E
0x180019bef  or      r13, 0FFFFFFFFFFFFFFFFh
0x180019bf3  inc     r13
0x180019bf6  cmp     [r15+r13*2], r9w
0x180019bfb  jnz     short loc_180019BF3
0x180019bfd  lea     rbx, ds:0[r13*8]
0x180019c05  mov     rsi, r9
0x180019c08  mov     r12, 0FFFFFFFFFFFFFF0h
0x180019c12  test    rbx, rbx
0x180019c15  jz      short loc_180019C71
0x180019c17  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180019c1e  ja      short loc_180019C71
0x180019c20  mov     rcx, cs:g_ulAdditionalProbeSize
0x180019c27  add     rcx, 8
0x180019c2b  add     rcx, rbx
0x180019c2e  cmp     rcx, rbx
0x180019c31  jb      short loc_180019C71
0x180019c33  call    VerifyStackAvailable
0x180019c38  test    eax, eax
0x180019c3a  jz      short loc_180019C71
0x180019c3c  lea     rax, [rbx+8]
0x180019c40  lea     rcx, [rax+0Fh]
0x180019c44  cmp     rcx, rax
0x180019c47  ja      short loc_180019C4C
0x180019c49  mov     rcx, r12
0x180019c4c  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180019c50  mov     rax, rcx
0x180019c53  call    _alloca_probe
0x180019c58  sub     rsp, rcx
0x180019c5b  lea     rsi, [rsp+2D0h+var_2A0]
0x180019c60  test    rsi, rsi
0x180019c63  jz      short loc_180019C71
0x180019c65  mov     dword ptr [rsi], 6B637453h
0x180019c6b  add     rsi, 8
0x180019c6f  jnz     short loc_180019C98
0x180019c71  lea     rcx, [rbx+8]
0x180019c75  cmp     rcx, rbx
0x180019c78  jb      short loc_180019C98
0x180019c7a  mov     rax, cs:g_pfnAllocate
0x180019c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c86  mov     rsi, rax
0x180019c89  test    rax, rax
0x180019c8c  jz      short loc_180019C98
0x180019c8e  mov     dword ptr [rax], 70616548h
0x180019c94  add     rsi, 8
0x180019c98  test    rsi, rsi
0x180019c9b  jnz     short loc_180019CA5
0x180019c9d  lea     ebx, [rsi+8]
0x180019ca0  jmp     loc_18001A137
0x180019ca5  mov     r8, rbx; Size
0x180019ca8  xor     edx, edx; Val
0x180019caa  mov     rcx, rsi; void *
0x180019cad  call    memset_0
0x180019cb2  mov     eax, 7Fh
0x180019cb7  cmp     r13, rax
0x180019cba  cmova   r13, rax
0x180019cbe  xor     r9d, r9d
0x180019cc1  mov     r12d, r9d
0x180019cc4  mov     [rbp+2A0h+var_278], r13
0x180019cc8  mov     edx, r9d
0x180019ccb  mov     ecx, edx
0x180019ccd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019cd1  inc     rax
0x180019cd4  cmp     [r15+rax*2], r9w
0x180019cd9  jnz     short loc_180019CD1
0x180019cdb  cmp     rcx, rax
0x180019cde  jnb     short loc_180019D10
0x180019ce0  movzx   ecx, word ptr [r15+rcx*2]
0x180019ce5  sub     ecx, 62h ; 'b'
0x180019ce8  jz      short loc_180019D08
0x180019cea  sub     ecx, 2
0x180019ced  jz      short loc_180019D03
0x180019cef  sub     ecx, 1
0x180019cf2  jz      short loc_180019D03
0x180019cf4  sub     ecx, 0Eh
0x180019cf7  jz      short loc_180019D03
0x180019cf9  sub     ecx, 1
0x180019cfc  jz      short loc_180019D03
0x180019cfe  cmp     ecx, 1
0x180019d01  jnz     short loc_180019D10
0x180019d03  inc     r12d
0x180019d06  jmp     short loc_180019D0C
0x180019d08  add     r12d, 2
0x180019d0c  inc     edx
0x180019d0e  jmp     short loc_180019CCB
0x180019d10  test    r12d, r12d
0x180019d13  jz      loc_180019DCD
0x180019d19  mov     ebx, r12d
0x180019d1c  mov     rdi, r9
0x180019d1f  shl     rbx, 4
0x180019d23  test    rbx, rbx
0x180019d26  jz      short loc_180019D89
0x180019d28  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180019d2f  ja      short loc_180019D89
0x180019d31  mov     rcx, cs:g_ulAdditionalProbeSize
0x180019d38  add     rcx, 8
0x180019d3c  add     rcx, rbx
0x180019d3f  cmp     rcx, rbx
0x180019d42  jb      short loc_180019D89
0x180019d44  call    VerifyStackAvailable
0x180019d49  test    eax, eax
0x180019d4b  jz      short loc_180019D89
0x180019d4d  lea     rax, [rbx+8]
0x180019d51  lea     rcx, [rax+0Fh]
0x180019d55  cmp     rcx, rax
0x180019d58  ja      short loc_180019D64
0x180019d5a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180019d64  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180019d68  mov     rax, rcx
0x180019d6b  call    _alloca_probe
0x180019d70  sub     rsp, rcx
0x180019d73  lea     rdi, [rsp+2D0h+var_2A0]
0x180019d78  test    rdi, rdi
0x180019d7b  jz      short loc_180019D89
0x180019d7d  mov     dword ptr [rdi], 6B637453h
0x180019d83  add     rdi, 8
0x180019d87  jnz     short loc_180019DB0
0x180019d89  lea     rcx, [rbx+8]
0x180019d8d  cmp     rcx, rbx
0x180019d90  jb      short loc_180019DB0
0x180019d92  mov     rax, cs:g_pfnAllocate
0x180019d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d9e  mov     rdi, rax
0x180019da1  test    rax, rax
0x180019da4  jz      short loc_180019DB0
0x180019da6  mov     dword ptr [rax], 70616548h
0x180019dac  add     rdi, 8
0x180019db0  test    rdi, rdi
0x180019db3  jnz     short loc_180019DBD
0x180019db5  lea     ebx, [rdi+8]
0x180019db8  jmp     loc_18001A11F
0x180019dbd  mov     r8, rbx; Size
0x180019dc0  xor     edx, edx; Val
0x180019dc2  mov     rcx, rdi; void *
0x180019dc5  call    memset_0
0x180019dca  xor     r9d, r9d
0x180019dcd  mov     r15d, r9d
0x180019dd0  mov     eax, r9d
0x180019dd3  mov     [rbp+2A0h+var_280], eax
0x180019dd6  cmp     rax, r13
0x180019dd9  jnb     loc_18001A083
0x180019ddf  mov     rcx, [rbp+2A0h+var_270]
0x180019de3  mov     r8, r14; unsigned int
0x180019de6  movzx   ecx, word ptr [rcx+rax*2]
0x180019dea  sub     ecx, 62h ; 'b'
0x180019ded  jz      loc_18001A021
0x180019df3  sub     ecx, 2
0x180019df6  jz      loc_180019FFE
0x180019dfc  sub     ecx, 1
0x180019dff  jz      loc_180019FBE
0x180019e05  sub     ecx, 0Eh
0x180019e08  jz      loc_180019F8F
0x180019e0e  sub     ecx, 1
0x180019e11  jz      loc_180019F70
0x180019e17  cmp     ecx, 1
0x180019e1a  jnz     loc_18001A077
0x180019e20  mov     r13, [r14]
0x180019e23  mov     rbx, r9
0x180019e26  movzx   r14d, word ptr [r13+0]
0x180019e2b  add     r14, 2
0x180019e2f  cmp     r14, cs:g_ulMaxStackAllocSize
0x180019e36  ja      short loc_180019E93
0x180019e38  mov     rcx, cs:g_ulAdditionalProbeSize
0x180019e3f  add     rcx, 8
0x180019e43  add     rcx, r14
0x180019e46  cmp     rcx, r14
0x180019e49  jb      short loc_180019E93
0x180019e4b  call    VerifyStackAvailable
0x180019e50  xor     r9d, r9d
0x180019e53  test    eax, eax
0x180019e55  jz      short loc_180019E93
0x180019e57  lea     rax, [r14+8]
0x180019e5b  lea     rcx, [rax+0Fh]
0x180019e5f  cmp     rcx, rax
0x180019e62  ja      short loc_180019E6E
0x180019e64  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180019e6e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180019e72  mov     rax, rcx
0x180019e75  call    _alloca_probe
0x180019e7a  sub     rsp, rcx
0x180019e7d  lea     rbx, [rsp+2D0h+var_2A0]
0x180019e82  test    rbx, rbx
0x180019e85  jz      short loc_180019E93
0x180019e87  mov     dword ptr [rbx], 6B637453h
0x180019e8d  add     rbx, 8
0x180019e91  jnz     short loc_180019EBD
0x180019e93  lea     rcx, [r14+8]
0x180019e97  cmp     rcx, r14
0x180019e9a  jb      short loc_180019EBD
0x180019e9c  mov     rax, cs:g_pfnAllocate
0x180019ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ea8  xor     r9d, r9d
0x180019eab  mov     rbx, rax
0x180019eae  test    rax, rax
0x180019eb1  jz      short loc_180019EBD
0x180019eb3  mov     dword ptr [rax], 70616548h
0x180019eb9  add     rbx, 8
0x180019ebd  mov     r14, [rbp+2A0h+var_2A0]
0x180019ec1  mov     [rsi+r14*8], rbx
0x180019ec5  test    rbx, rbx
0x180019ec8  jz      loc_18001A070
0x180019ece  movzx   r8d, word ptr [r13+0]
0x180019ed3  xor     edx, edx; Val
0x180019ed5  add     r8, 2; Size
0x180019ed9  mov     rcx, rbx; void *
0x180019edc  call    memset_0
0x180019ee1  movzx   eax, word ptr [r13+0]
0x180019ee6  mov     r10, r14
0x180019ee9  mov     r9, [r13+8]
0x180019eed  mov     r8, [rsi+r14*8]
0x180019ef1  shr     rax, 1
0x180019ef4  lea     rdx, [rax+1]
0x180019ef8  test    rax, rax
0x180019efb  jz      short loc_180019F1B
0x180019efd  movzx   ecx, word ptr [r9]
0x180019f01  test    cx, cx
0x180019f04  jz      short loc_180019F1B
0x180019f06  mov     [r8], cx
0x180019f0a  add     r9, 2
0x180019f0e  add     r8, 2
0x180019f12  dec     rax
0x180019f15  sub     rdx, 1
0x180019f19  jnz     short loc_180019EF8
0x180019f1b  xor     r9d, r9d
0x180019f1e  lea     rcx, [r8-2]
0x180019f22  test    rdx, rdx
0x180019f25  mov     rax, rdx
0x180019f28  cmovnz  rcx, r8
0x180019f2c  neg     rax
0x180019f2f  sbb     ebx, ebx
0x180019f31  not     ebx
0x180019f33  and     ebx, 80000005h
0x180019f39  mov     [rcx], r9w
0x180019f3d  test    rdx, rdx
0x180019f40  jz      loc_18001A0BE
0x180019f46  movzx   ecx, word ptr [r13+0]
0x180019f4b  mov     r14, [rbp+2A0h+var_290]
0x180019f4f  add     ecx, 2
0x180019f52  mov     rax, [rsi+r10*8]
0x180019f56  add     r14, 8
0x180019f5a  mov     r13, [rbp+2A0h+var_278]
0x180019f5e  mov     edx, r15d
0x180019f61  add     rdx, rdx
0x180019f64  inc     r10
0x180019f67  mov     [rbp+2A0h+var_2A0], r10
0x180019f6b  jmp     loc_18001A052
0x180019f70  mov     rax, [r8]
0x180019f73  add     r14, 8
0x180019f77  mov     ecx, r15d
0x180019f7a  add     rcx, rcx
0x180019f7d  mov     [rdi+rcx*8], rax
0x180019f81  mov     qword ptr [rdi+rcx*8+8], 10h
0x180019f8a  jmp     loc_18001A05F
0x180019f8f  mov     rbx, [r8]
  ... truncated ...
```
