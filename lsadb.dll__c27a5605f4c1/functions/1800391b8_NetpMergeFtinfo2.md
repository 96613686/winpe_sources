# NetpMergeFtinfo2

- ea: `0x1800391b8`
- end: `0x1800398b6`
- name: `NetpMergeFtinfo2`
- size: `1790`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800390c8`

## callees

- `0x180037688`
- `0x180037768`
- `0x180037e10`
- `0x1800384f0`
- `0x18003872c`
- `0x1800391b8`
- `0x1800398bc`
- `0x18003ad30`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180039246`
- `ntdll!RtlAllocateHeap` at `0x180039292`
- `ntdll!RtlAllocateHeap` at `0x1800392cb`
- `ntdll!RtlAllocateHeap` at `0x180039246`
- `ntdll!RtlAllocateHeap` at `0x180039292`
- `ntdll!RtlAllocateHeap` at `0x1800392cb`
- `ntdll!RtlFreeHeap` at `0x180039858`
- `ntdll!RtlFreeHeap` at `0x180039876`
- `ntdll!RtlFreeHeap` at `0x180039893`
- `ntdll!RtlFreeHeap` at `0x180039858`
- `ntdll!RtlFreeHeap` at `0x180039876`
- `ntdll!RtlFreeHeap` at `0x180039893`
- `ntdll!RtlEqualUnicodeString` at `0x1800397c6`
- `ntdll!RtlEqualUnicodeString` at `0x1800397c6`
- `ntdll!RtlEqualSid` at `0x1800395d5`
- `ntdll!RtlEqualSid` at `0x1800395d5`

## pseudocode

```c
__int64 __fastcall NetpMergeFtinfo2(__int64 a1, unsigned int *a2, unsigned int *a3, _QWORD *a4)
{
  __int64 v4; // r15
  unsigned int v7; // esi
  SIZE_T v8; // rbx
  unsigned int v9; // r12d
  PVOID Heap; // rax
  unsigned int v11; // r13d
  SIZE_T v12; // rbx
  PVOID v13; // rax
  PVOID v14; // rax
  PVOID v15; // rsi
  _WORD *v16; // r14
  __int64 v17; // rsi
  __int64 v18; // r8
  __int64 v19; // rdi
  __int64 v20; // rbx
  __int64 v21; // rax
  char v22; // di
  char IsSubordinate; // al
  int v24; // ecx
  char v25; // dl
  unsigned int v26; // ebx
  __int64 v27; // r14
  __int64 v28; // rsi
  unsigned int v29; // r15d
  __int64 v30; // rdi
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  char *v33; // rax
  char *v34; // rax
  int v35; // eax
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  unsigned int v38; // ebx
  __int64 v39; // rbx
  _QWORD *v40; // r15
  unsigned int *v41; // rdx
  _DWORD *v42; // rax
  _DWORD **v43; // r13
  _DWORD *v44; // rdx
  __int64 v45; // rbx
  _DWORD *v46; // rcx
  __int64 v47; // r8
  const UNICODE_STRING *v48; // r15
  __int64 v49; // rdi
  __int64 v50; // rsi
  int v52; // [rsp+48h] [rbp-89h] BYREF
  int v53; // [rsp+4Ch] [rbp-85h] BYREF
  int v54; // [rsp+50h] [rbp-81h]
  PVOID v55[2]; // [rsp+58h] [rbp-79h] BYREF
  __int64 v56; // [rsp+68h] [rbp-69h] BYREF
  __int64 v57; // [rsp+70h] [rbp-61h] BYREF
  __int128 v58; // [rsp+78h] [rbp-59h] BYREF
  PSID Sid1[2]; // [rsp+88h] [rbp-49h] BYREF
  __int128 v60; // [rsp+98h] [rbp-39h]
  __int64 v61; // [rsp+A8h] [rbp-29h]
  PVOID P[2]; // [rsp+B0h] [rbp-21h] BYREF
  _QWORD v63[2]; // [rsp+C0h] [rbp-11h] BYREF
  __int128 v64; // [rsp+D0h] [rbp-1h]
  PVOID v65[2]; // [rsp+E0h] [rbp+Fh] BYREF
  int v67; // [rsp+148h] [rbp+77h] BYREF
  _QWORD *v68; // [rsp+150h] [rbp+7Fh]

  v68 = a4;
  v4 = a1;
  v63[1] = v63;
  v63[0] = v63;
  v53 = 0;
  v57 = 0;
  v56 = 0;
  v7 = 0;
  *a4 = 0;
  v64 = 0;
  *(_OWORD *)P = 0;
  *(_OWORD *)v65 = 0;
  *(_OWORD *)v55 = 0;
  if ( a3 )
  {
    v7 = *a3;
    v8 = 8LL * *a3;
    v9 = *a3;
    LODWORD(P[0]) = *a3;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
    P[1] = Heap;
    if ( !Heap )
    {
LABEL_92:
      v15 = v55[1];
      goto LABEL_93;
    }
    memcpy_0(Heap, *((const void **)a3 + 1), v8);
    v4 = a1;
  }
  else
  {
    v9 = (unsigned int)P[0];
  }
  v11 = *a2;
  v12 = 8LL * *a2;
  LODWORD(v65[0]) = *a2;
  v13 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  v65[1] = v13;
  if ( !v13 )
    goto LABEL_92;
  memcpy_0(v13, *((const void **)a2 + 1), v12);
  v14 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 8LL * (v7 + v11));
  v55[1] = v14;
  v15 = v14;
  if ( !v14 )
    goto LABEL_93;
  LOBYTE(v14) = 0;
  v52 = 0;
  v16 = 0;
  v54 = (int)v14;
  v17 = 0;
  v67 = 0;
  while ( v52 < v11 || v67 < v9 )
  {
    NetpMergeFtinfoHelper(
      (int)v65,
      (int)P,
      (int)&v52,
      (int)&v67,
      (__int64)&v57,
      (__int64)&v56,
      (__int64)&v53,
      NetpCompareFtinfoEntryDns2);
    v19 = v56;
    if ( v56 )
    {
      if ( *(_DWORD *)(v56 + 4) )
      {
        if ( *(_DWORD *)(v56 + 4) == 1 && !NetpAllocFtinfoEntry2(v63, (unsigned int *)v56) )
        {
          v38 = -1073741801;
LABEL_91:
          v15 = v55[1];
          goto LABEL_94;
        }
      }
      else
      {
        v16 = (_WORD *)v56;
      }
    }
    v20 = v57;
    if ( v57 )
    {
      if ( !*(_DWORD *)(v57 + 4) )
      {
        v61 = 0;
        v58 = 0;
        *(_OWORD *)Sid1 = 0;
        v60 = 0;
        v58 = *(_OWORD *)v57;
        *(_OWORD *)Sid1 = *(_OWORD *)(v57 + 16);
        v60 = *(_OWORD *)(v57 + 32);
        v61 = *(_QWORD *)(v57 + 48);
        if ( !v17
          || *(_DWORD *)(v17 + 4)
          || (LOBYTE(v18) = 1, !(unsigned __int8)NetpIsSubordinate(v57 + 16, v17 + 16, v18)) )
        {
          if ( v19 )
          {
            LODWORD(v58) = v53;
            v21 = *(_QWORD *)(v19 + 8);
            v22 = 0;
            *((_QWORD *)&v58 + 1) = v21;
          }
          else
          {
            v22 = 1;
            LODWORD(v58) = 0;
            *((_QWORD *)&v58 + 1) = 0;
          }
          if ( v16 && (unsigned __int8)NetpIsSubordinate(Sid1, v16 + 8, 0) )
          {
            if ( (*(_BYTE *)v16 & 2) != 0 )
            {
              LODWORD(v58) = v58 | 2;
              v22 = 0;
            }
            else
            {
              v22 = *v16 != 0 ? v22 : 0;
            }
          }
          LOBYTE(v18) = 1;
          IsSubordinate = NetpIsSubordinate(v4, Sid1, v18);
          v24 = (unsigned __int8)v54;
          if ( IsSubordinate )
            v24 = 1;
          v25 = 0;
          v54 = v24;
          if ( !IsSubordinate )
            v25 = v22;
          if ( v25 )
            LODWORD(v58) = v58 | 1;
          if ( !NetpAllocFtinfoEntry2(v63, (unsigned int *)&v58) )
            goto LABEL_92;
          v17 = v20;
        }
      }
    }
  }
  v26 = (unsigned int)v55[0];
  v27 = 0;
  v52 = 0;
  v67 = 0;
LABEL_37:
  v15 = v55[1];
  while ( v52 < v11 || v67 < v9 )
  {
    NetpMergeFtinfoHelper(
      (int)v65,
      (int)P,
      (int)&v52,
      (int)&v67,
      (__int64)&v57,
      (__int64)&v56,
      (__int64)&v53,
      (_CoreCrtNonSecureSearchSortCompareFunction)NetpCompareFtinfoEntrySid2);
    v28 = v56;
    v29 = v53 & 0xFFFFFFF3;
    v30 = v57;
    v53 &= 0xFFFFFFF3;
    if ( v56 && *(_DWORD *)(v56 + 4) == 2 && (v29 & 1) != 0 )
    {
      if ( v57 )
        goto LABEL_47;
      v31 = *(_OWORD *)(v56 + 16);
      v58 = *(_OWORD *)v56;
      LODWORD(v58) = v29;
      v32 = *(_OWORD *)(v56 + 32);
      *(_OWORD *)Sid1 = v31;
      *(_QWORD *)&v31 = *(_QWORD *)(v56 + 48);
      v60 = v32;
      v61 = v31;
      v33 = NetpAllocFtinfoEntry2(v63, (unsigned int *)&v58);
      *((_QWORD *)v55[1] + v26) = v33;
      if ( !v33 )
        goto LABEL_92;
      LODWORD(v55[0]) = ++v26;
    }
    if ( !v30 )
      goto LABEL_37;
LABEL_47:
    if ( *(_DWORD *)(v30 + 4) != 2 )
      goto LABEL_37;
    v61 = 0;
    v58 = 0;
    *(_OWORD *)Sid1 = 0;
    v60 = 0;
    v58 = *(_OWORD *)v30;
    *(_OWORD *)Sid1 = *(_OWORD *)(v30 + 16);
    v60 = *(_OWORD *)(v30 + 32);
    v61 = *(_QWORD *)(v30 + 48);
    if ( v27 )
    {
      if ( *(_DWORD *)(v27 + 4) == 2 && RtlEqualSid(Sid1[0], *(PSID *)(v27 + 16)) )
        goto LABEL_37;
    }
    if ( v28 )
    {
      LODWORD(v58) = v29;
      *((_QWORD *)&v58 + 1) = *(_QWORD *)(v28 + 8);
    }
    else
    {
      LODWORD(v58) = 0;
      *((_QWORD *)&v58 + 1) = 0;
    }
    v34 = NetpAllocFtinfoEntry2(v63, (unsigned int *)&v58);
    v15 = v55[1];
    *((_QWORD *)v55[1] + v26) = v34;
    if ( !v34 )
      goto LABEL_93;
    LODWORD(v55[0]) = ++v26;
    if ( !(unsigned __int8)NetpAddTlnFtinfoEntry(v63, &Sid1[1]) )
      goto LABEL_93;
    v27 = v30;
  }
  v52 = 0;
  v67 = 0;
  while ( v52 < v26 || v67 < v9 )
  {
    NetpMergeFtinfoHelper(
      (int)v55,
      (int)P,
      (int)&v52,
      (int)&v67,
      (__int64)&v57,
      (__int64)&v56,
      (__int64)&v53,
      NetpCompareFtinfoEntryNetbios);
    v35 = v53 & 0xC;
    v53 = v35;
    if ( v56 )
    {
      if ( v57 )
      {
        *(_DWORD *)v57 |= v35;
      }
      else if ( *(_DWORD *)(v56 + 4) == 2 && (v35 & 4) != 0 )
      {
        v36 = *(_OWORD *)(v56 + 16);
        v58 = *(_OWORD *)v56;
        LODWORD(v58) = v35;
        v37 = *(_OWORD *)(v56 + 32);
        *(_OWORD *)Sid1 = v36;
        *(_QWORD *)&v36 = *(_QWORD *)(v56 + 48);
        v60 = v37;
        v61 = v36;
        if ( !NetpAllocFtinfoEntry2(v63, (unsigned int *)&v58) )
          goto LABEL_93;
      }
    }
  }
  if ( !(_BYTE)v54 )
  {
    v38 = -1073741811;
    goto LABEL_94;
  }
  v39 = 0;
  if ( !v9 )
  {
LABEL_74:
    v42 = (_DWORD *)NetpCopyFtinfoContext2(v63);
    v43 = (_DWORD **)v68;
    v44 = v42;
    *v68 = v42;
    if ( !v42 )
      goto LABEL_93;
    if ( *v42 )
    {
      v45 = 0;
      v46 = v42;
      do
      {
        v47 = *(_QWORD *)(*((_QWORD *)v44 + 1) + 8 * v45);
        if ( *(_DWORD *)(v47 + 4) == 1 )
        {
          if ( *v44 )
          {
            v48 = (const UNICODE_STRING *)(v47 + 16);
            v49 = 0;
            while ( 1 )
            {
              v50 = *(_QWORD *)(*((_QWORD *)v44 + 1) + 8 * v49);
              if ( !*(_DWORD *)(v50 + 4) )
              {
                if ( (unsigned __int8)NetpIsSubordinate(v48, v50 + 16, 0) )
                  goto LABEL_88;
                if ( RtlEqualUnicodeString(v48, (PCUNICODE_STRING)(v50 + 16), 1u) )
                  break;
              }
              v44 = *v43;
              v49 = (unsigned int)(v49 + 1);
              if ( (unsigned int)v49 >= **v43 )
                goto LABEL_84;
            }
            if ( !(unsigned __int16)*(_DWORD *)v50 )
              *(_DWORD *)v50 |= 1u;
LABEL_84:
            v46 = *v43;
          }
          *(_QWORD *)(*((_QWORD *)v46 + 1) + 8 * v45) = *(_QWORD *)(*((_QWORD *)v46 + 1) + 8LL * (unsigned int)--*v46);
          LODWORD(v45) = v45 - 1;
        }
LABEL_88:
        v44 = *v43;
        v45 = (unsigned int)(v45 + 1);
        v46 = *v43;
      }
      while ( (unsigned int)v45 < **v43 );
    }
    v38 = 0;
    goto LABEL_91;
  }
  v40 = P[1];
  while ( 1 )
  {
    v41 = (unsigned int *)v40[v39];
    if ( v41[1] - 3 <= 1 && !NetpAllocFtinfoEntry2(v63, v41) )
      break;
    v39 = (unsigned int)(v39 + 1);
    if ( (unsigned int)v39 >= v9 )
      goto LABEL_74;
  }
LABEL_93:
  v38 = -1073741801;
LABEL_94:
  NetpCleanFtinfoContext(v63);
  if ( P[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
  if ( v65[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v65[1]);
  if ( v15 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
  return v38;
}

```

## disassembly

```asm
0x1800391b8  mov     rax, rsp
0x1800391bb  mov     [rax+10h], rbx
0x1800391bf  mov     [rax+20h], r9
0x1800391c3  mov     [rax+8], rcx
0x1800391c7  push    rbp
0x1800391c8  push    rsi
0x1800391c9  push    rdi
0x1800391ca  push    r12
0x1800391cc  push    r13
0x1800391ce  push    r14
0x1800391d0  push    r15
0x1800391d2  lea     rbp, [rax-5Fh]
0x1800391d6  sub     rsp, 0F0h
0x1800391dd  xorps   xmm0, xmm0
0x1800391e0  lea     rax, [rbp+57h+var_68]
0x1800391e4  mov     r15, rcx
0x1800391e7  mov     [rbp+57h+var_60], rax
0x1800391eb  xor     ecx, ecx
0x1800391ed  lea     rax, [rbp+57h+var_68]
0x1800391f1  mov     [rbp+57h+var_68], rax
0x1800391f5  xorps   xmm1, xmm1
0x1800391f8  mov     dword ptr [rsp+120h+var_DC], ecx
0x1800391fc  mov     rdi, r8
0x1800391ff  mov     [rbp+57h+var_B8], rcx
0x180039203  mov     r14, rdx
0x180039206  mov     [rbp+57h+var_C0], rcx
0x18003920a  mov     esi, ecx
0x18003920c  mov     [r9], rcx
0x18003920f  movdqu  [rbp+57h+var_58], xmm0
0x180039214  movups  xmmword ptr [rbp+57h+P], xmm0
0x180039218  movups  xmmword ptr [rbp+57h+var_48], xmm1
0x18003921c  movups  xmmword ptr [rbp+57h+var_D0], xmm0
0x180039220  test    r8, r8
0x180039223  jz      short loc_18003926E
0x180039225  mov     esi, [r8]
0x180039228  xor     edx, edx; Flags
0x18003922a  mov     rcx, gs:60h
0x180039233  mov     ebx, esi
0x180039235  shl     rbx, 3
0x180039239  mov     r12d, esi
0x18003923c  mov     r8, rbx; Size
0x18003923f  mov     dword ptr [rbp+57h+P], esi
0x180039242  mov     rcx, [rcx+30h]; HeapHandle
0x180039246  call    cs:__imp_RtlAllocateHeap
0x18003924c  mov     [rbp+57h+P+8], rax
0x180039250  test    rax, rax
0x180039253  jz      loc_18003982E
0x180039259  mov     rdx, [rdi+8]; Src
0x18003925d  mov     r8, rbx; Size
0x180039260  mov     rcx, rax; void *
0x180039263  call    memcpy_0
0x180039268  mov     r15, [rbp+57h+arg_0]
0x18003926c  jmp     short loc_180039272
0x18003926e  mov     r12d, dword ptr [rbp+57h+P]
0x180039272  mov     r13d, [r14]
0x180039275  xor     edx, edx; Flags
0x180039277  mov     rcx, gs:60h
0x180039280  mov     ebx, r13d
0x180039283  shl     rbx, 3
0x180039287  mov     r8, rbx; Size
0x18003928a  mov     dword ptr [rbp+57h+var_48], r13d
0x18003928e  mov     rcx, [rcx+30h]; HeapHandle
0x180039292  call    cs:__imp_RtlAllocateHeap
0x180039298  mov     [rbp+57h+var_48+8], rax
0x18003929c  test    rax, rax
0x18003929f  jz      loc_18003982E
0x1800392a5  mov     rdx, [r14+8]; Src
0x1800392a9  mov     r8, rbx; Size
0x1800392ac  mov     rcx, rax; void *
0x1800392af  call    memcpy_0
0x1800392b4  mov     rcx, gs:60h
0x1800392bd  lea     r8d, [rsi+r13]
0x1800392c1  shl     r8, 3; Size
0x1800392c5  xor     edx, edx; Flags
0x1800392c7  mov     rcx, [rcx+30h]; HeapHandle
0x1800392cb  call    cs:__imp_RtlAllocateHeap
0x1800392d1  mov     [rbp+57h+var_D0+8], rax
0x1800392d5  mov     rsi, rax
0x1800392d8  test    rax, rax
0x1800392db  jz      loc_180039832
0x1800392e1  xor     al, al
0x1800392e3  mov     [rsp+120h+var_E0], 0
0x1800392eb  xor     r14d, r14d
0x1800392ee  mov     dword ptr [rsp+120h+var_DC+4], eax
0x1800392f2  xor     esi, esi
0x1800392f4  mov     [rbp+57h+arg_10], 0
0x1800392fb  cmp     [rsp+120h+var_E0], r13d
0x180039300  jb      short loc_18003930C
0x180039302  cmp     [rbp+57h+arg_10], r12d
0x180039306  jnb     loc_18003949A
0x18003930c  lea     rax, NetpCompareFtinfoEntryDns2
0x180039313  mov     [rsp+120h+CompareFunction], rax; CompareFunction
0x180039318  lea     r9, [rbp+57h+arg_10]; int
0x18003931c  lea     rax, [rsp+120h+var_DC]
0x180039321  mov     [rsp+120h+var_F0], rax; __int64
0x180039326  lea     r8, [rsp+120h+var_E0]; int
0x18003932b  lea     rax, [rbp+57h+var_C0]
0x18003932f  mov     [rsp+120h+var_F8], rax; __int64
0x180039334  lea     rdx, [rbp+57h+P]; int
0x180039338  lea     rax, [rbp+57h+var_B8]
0x18003933c  lea     rcx, [rbp+57h+var_48]; int
0x180039340  mov     [rsp+120h+var_100], rax; __int64
0x180039345  call    NetpMergeFtinfoHelper
0x18003934a  mov     rdi, [rbp+57h+var_C0]
0x18003934e  test    rdi, rdi
0x180039351  jz      short loc_180039379
0x180039353  cmp     dword ptr [rdi+4], 0
0x180039357  jnz     short loc_18003935E
0x180039359  mov     r14, rdi
0x18003935c  jmp     short loc_180039379
0x18003935e  cmp     dword ptr [rdi+4], 1
0x180039362  jnz     short loc_180039379
0x180039364  mov     rdx, rdi
0x180039367  lea     rcx, [rbp+57h+var_68]
0x18003936b  call    NetpAllocFtinfoEntry2
0x180039370  test    rax, rax
0x180039373  jz      loc_180039823
0x180039379  mov     rbx, [rbp+57h+var_B8]
0x18003937d  test    rbx, rbx
0x180039380  jz      loc_1800392FB
0x180039386  cmp     dword ptr [rbx+4], 0
0x18003938a  jnz     loc_1800392FB
0x180039390  xorps   xmm0, xmm0
0x180039393  xor     eax, eax
0x180039395  mov     [rbp+57h+var_80], rax
0x180039399  movups  [rbp+57h+var_B0], xmm0
0x18003939d  movups  xmmword ptr [rbp+57h+Sid1], xmm0
0x1800393a1  movups  [rbp+57h+var_90], xmm0
0x1800393a5  movups  xmm0, xmmword ptr [rbx]
0x1800393a8  movups  [rbp+57h+var_B0], xmm0
0x1800393ac  movups  xmm1, xmmword ptr [rbx+10h]
0x1800393b0  movups  xmmword ptr [rbp+57h+Sid1], xmm1
0x1800393b4  movups  xmm0, xmmword ptr [rbx+20h]
0x1800393b8  movups  [rbp+57h+var_90], xmm0
0x1800393bc  movsd   xmm1, qword ptr [rbx+30h]
0x1800393c1  movsd   [rbp+57h+var_80], xmm1
0x1800393c6  test    rsi, rsi
0x1800393c9  jz      short loc_1800393E8
0x1800393cb  cmp     [rsi+4], eax
0x1800393ce  jnz     short loc_1800393E8
0x1800393d0  lea     rdx, [rsi+10h]
0x1800393d4  mov     r8b, 1
0x1800393d7  lea     rcx, [rbx+10h]
0x1800393db  call    NetpIsSubordinate
0x1800393e0  test    al, al
0x1800393e2  jnz     loc_1800392FB
0x1800393e8  mov     esi, 1
0x1800393ed  test    rdi, rdi
0x1800393f0  jz      short loc_180039406
0x1800393f2  mov     eax, dword ptr [rsp+120h+var_DC]
0x1800393f6  mov     dword ptr [rbp+57h+var_B0], eax
0x1800393f9  mov     rax, [rdi+8]
0x1800393fd  xor     dil, dil
0x180039400  mov     qword ptr [rbp+57h+var_B0+8], rax
0x180039404  jmp     short loc_180039418
0x180039406  mov     dil, sil
0x180039409  mov     dword ptr [rbp+57h+var_B0], 0
0x180039410  mov     qword ptr [rbp+57h+var_B0+8], 0
0x180039418  test    r14, r14
0x18003941b  jz      short loc_18003944B
0x18003941d  lea     rdx, [r14+10h]
0x180039421  xor     r8d, r8d
0x180039424  lea     rcx, [rbp+57h+Sid1]
0x180039428  call    NetpIsSubordinate
0x18003942d  test    al, al
0x18003942f  jz      short loc_18003944B
0x180039431  test    byte ptr [r14], 2
0x180039435  jz      short loc_180039440
0x180039437  or      dword ptr [rbp+57h+var_B0], 2
0x18003943b  xor     dil, dil
0x18003943e  jmp     short loc_18003944B
0x180039440  movzx   eax, word ptr [r14]
0x180039444  neg     eax
0x180039446  sbb     cl, cl
0x180039448  and     dil, cl
0x18003944b  mov     r8b, sil
0x18003944e  lea     rdx, [rbp+57h+Sid1]
0x180039452  mov     rcx, r15
0x180039455  call    NetpIsSubordinate
0x18003945a  mov     ecx, dword ptr [rsp+120h+var_DC+4]
0x18003945e  test    al, al
0x180039460  movzx   ecx, cl
0x180039463  cmovnz  ecx, esi
0x180039466  xor     edx, edx
0x180039468  test    al, al
0x18003946a  mov     dword ptr [rsp+120h+var_DC+4], ecx
0x18003946e  movzx   ecx, dil
0x180039472  cmovz   edx, ecx
0x180039475  test    dl, dl
0x180039477  jz      short loc_18003947C
0x180039479  or      dword ptr [rbp+57h+var_B0], esi
0x18003947c  lea     rdx, [rbp+57h+var_B0]
0x180039480  lea     rcx, [rbp+57h+var_68]
0x180039484  call    NetpAllocFtinfoEntry2
0x180039489  test    rax, rax
0x18003948c  jz      loc_18003982E
0x180039492  mov     rsi, rbx
0x180039495  jmp     loc_1800392FB
0x18003949a  mov     ebx, dword ptr [rbp+57h+var_D0]
0x18003949d  xor     r14d, r14d
0x1800394a0  mov     [rsp+120h+var_E0], 0
0x1800394a8  mov     [rbp+57h+arg_10], 0
0x1800394af  mov     rsi, [rbp+57h+var_D0+8]
0x1800394b3  cmp     [rsp+120h+var_E0], r13d
0x1800394b8  jb      short loc_1800394C4
0x1800394ba  cmp     [rbp+57h+arg_10], r12d
0x1800394be  jnb     loc_180039647
0x1800394c4  lea     rax, NetpCompareFtinfoEntrySid2
0x1800394cb  mov     [rsp+120h+CompareFunction], rax; CompareFunction
0x1800394d0  lea     r9, [rbp+57h+arg_10]; int
0x1800394d4  lea     rax, [rsp+120h+var_DC]
0x1800394d9  mov     [rsp+120h+var_F0], rax; __int64
0x1800394de  lea     r8, [rsp+120h+var_E0]; int
0x1800394e3  lea     rax, [rbp+57h+var_C0]
0x1800394e7  mov     [rsp+120h+var_F8], rax; __int64
0x1800394ec  lea     rdx, [rbp+57h+P]; int
0x1800394f0  lea     rax, [rbp+57h+var_B8]
0x1800394f4  lea     rcx, [rbp+57h+var_48]; int
0x1800394f8  mov     [rsp+120h+var_100], rax; __int64
0x1800394fd  call    NetpMergeFtinfoHelper
0x180039502  mov     r15d, dword ptr [rsp+120h+var_DC]
0x180039507  mov     rsi, [rbp+57h+var_C0]
0x18003950b  and     r15d, 0FFFFFFF3h
0x18003950f  mov     rdi, [rbp+57h+var_B8]
0x180039513  mov     dword ptr [rsp+120h+var_DC], r15d
0x180039518  test    rsi, rsi
0x18003951b  jz      short loc_180039578
0x18003951d  cmp     dword ptr [rsi+4], 2
0x180039521  jnz     short loc_180039578
0x180039523  test    r15b, 1
0x180039527  jz      short loc_180039578
0x180039529  test    rdi, rdi
0x18003952c  jnz     short loc_180039581
0x18003952e  movups  xmm0, xmmword ptr [rsi]
0x180039531  lea     rdx, [rbp+57h+var_B0]
0x180039535  movups  xmm1, xmmword ptr [rsi+10h]
0x180039539  lea     rcx, [rbp+57h+var_68]
0x18003953d  movups  [rbp+57h+var_B0], xmm0
0x180039541  mov     dword ptr [rbp+57h+var_B0], r15d
0x180039545  movups  xmm0, xmmword ptr [rsi+20h]
0x180039549  movups  xmmword ptr [rbp+57h+Sid1], xmm1
0x18003954d  movsd   xmm1, qword ptr [rsi+30h]
0x180039552  movups  [rbp+57h+var_90], xmm0
0x180039556  movsd   [rbp+57h+var_80], xmm1
0x18003955b  call    NetpAllocFtinfoEntry2
0x180039560  mov     rdx, [rbp+57h+var_D0+8]
0x180039564  mov     ecx, ebx
0x180039566  mov     [rdx+rcx*8], rax
0x18003956a  test    rax, rax
0x18003956d  jz      loc_18003982E
0x180039573  inc     ebx
0x180039575  mov     dword ptr [rbp+57h+var_D0], ebx
0x180039578  test    rdi, rdi
0x18003957b  jz      loc_1800394AF
0x180039581  cmp     dword ptr [rdi+4], 2
0x180039585  jnz     loc_1800394AF
0x18003958b  xorps   xmm0, xmm0
0x18003958e  xor     eax, eax
0x180039590  mov     [rbp+57h+var_80], rax
0x180039594  movups  [rbp+57h+var_B0], xmm0
0x180039598  movups  xmmword ptr [rbp+57h+Sid1], xmm0
0x18003959c  movups  [rbp+57h+var_90], xmm0
0x1800395a0  movups  xmm0, xmmword ptr [rdi]
0x1800395a3  movups  [rbp+57h+var_B0], xmm0
0x1800395a7  movups  xmm1, xmmword ptr [rdi+10h]
0x1800395ab  movups  xmmword ptr [rbp+57h+Sid1], xmm1
0x1800395af  movups  xmm0, xmmword ptr [rdi+20h]
0x1800395b3  movups  [rbp+57h+var_90], xmm0
0x1800395b7  movsd   xmm1, qword ptr [rdi+30h]
0x1800395bc  movsd   [rbp+57h+var_80], xmm1
0x1800395c1  test    r14, r14
0x1800395c4  jz      short loc_1800395E3
0x1800395c6  cmp     dword ptr [r14+4], 2
0x1800395cb  jnz     short loc_1800395E3
0x1800395cd  mov     rdx, [r14+10h]; Sid2
0x1800395d1  mov     rcx, [rbp+57h+Sid1]; Sid1
0x1800395d5  call    cs:__imp_RtlEqualSid
0x1800395db  test    al, al
0x1800395dd  jnz     loc_1800394AF
0x1800395e3  test    rsi, rsi
0x1800395e6  jz      short loc_1800395F6
0x1800395e8  mov     dword ptr [rbp+57h+var_B0], r15d
0x1800395ec  mov     rax, [rsi+8]
0x1800395f0  mov     qword ptr [rbp+57h+var_B0+8], rax
0x1800395f4  jmp     short loc_180039605
0x1800395f6  mov     dword ptr [rbp+57h+var_B0], 0
0x1800395fd  mov     qword ptr [rbp+57h+var_B0+8], 0
0x180039605  lea     rdx, [rbp+57h+var_B0]
0x180039609  lea     rcx, [rbp+57h+var_68]
0x18003960d  call    NetpAllocFtinfoEntry2
0x180039612  mov     rsi, [rbp+57h+var_D0+8]
0x180039616  mov     ecx, ebx
0x180039618  mov     [rsi+rcx*8], rax
0x18003961c  test    rax, rax
0x18003961f  jz      loc_180039832
0x180039625  inc     ebx
0x180039627  lea     rdx, [rbp+57h+Sid1+8]
0x18003962b  lea     rcx, [rbp+57h+var_68]
0x18003962f  mov     dword ptr [rbp+57h+var_D0], ebx
0x180039632  call    NetpAddTlnFtinfoEntry
  ... truncated ...
```
