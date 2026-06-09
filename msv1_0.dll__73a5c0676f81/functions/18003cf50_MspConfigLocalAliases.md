# MspConfigLocalAliases

- ea: `0x18003cf50`
- end: `0x18003d427`
- name: `MspConfigLocalAliases`
- size: `1239`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int64, unsigned int, _QWORD *, _DWORD *, int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x180011090`
- `0x180012d10`

## callees

- `0x18000cba0`
- `0x18000dab4`
- `0x18000db30`
- `0x18000dc18`
- `0x1800189c0`
- `0x180030844`
- `0x18003cf50`
- `0x18004ce00`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18003d030`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003d030`
- `ntdll!RtlReleaseResource` at `0x18003d1b6`
- `ntdll!RtlReleaseResource` at `0x18003d1f6`
- `ntdll!RtlReleaseResource` at `0x18003d414`
- `ntdll!RtlReleaseResource` at `0x18003d1b6`
- `ntdll!RtlReleaseResource` at `0x18003d1f6`
- `ntdll!RtlReleaseResource` at `0x18003d414`
- `ntdll!RtlAcquireResourceShared` at `0x18003d305`
- `ntdll!RtlAcquireResourceShared` at `0x18003d305`
- `ntdll!RtlEqualUnicodeString` at `0x18003d05b`
- `ntdll!RtlEqualUnicodeString` at `0x18003d24f`
- `ntdll!RtlEqualUnicodeString` at `0x18003d05b`
- `ntdll!RtlEqualUnicodeString` at `0x18003d24f`

## pseudocode

```c
__int64 __fastcall MspConfigLocalAliases(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        unsigned int a4,
        _QWORD *a5,
        _DWORD *a6,
        int *a7)
{
  unsigned int v7; // r12d
  const UNICODE_STRING *v9; // r13
  unsigned __int64 v10; // rcx
  __int64 v11; // rdx
  int ClientBuffer; // ebx
  int v14; // eax
  int v15; // r15d
  unsigned int j; // r14d
  _DWORD *v17; // rcx
  int v18; // eax
  __int64 v19; // rsi
  int v20; // eax
  __int64 v21; // rcx
  void *v22; // rax
  unsigned int *v23; // rbx
  __int64 v24; // rcx
  struct _LSA_SECPKG_FUNCTION_TABLE *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // r8
  unsigned int v29; // r15d
  __int64 v30; // r14
  __int64 v31; // rdx
  unsigned int v32; // esi
  unsigned int i; // r8d
  unsigned int v34; // ecx
  __int64 v35; // r15
  unsigned int v36; // r14d
  __int64 v37; // rsi
  char *v38; // r12
  __int128 v39; // [rsp+20h] [rbp-38h] BYREF
  __int64 v40; // [rsp+30h] [rbp-28h] BYREF
  __int128 v41; // [rsp+38h] [rbp-20h]
  __int64 v42; // [rsp+48h] [rbp-10h]

  v7 = 0;
  v40 = a1;
  v42 = 0;
  *a5 = 0;
  *a6 = 0;
  v41 = 0;
  if ( a4 < 0x18 )
    goto LABEL_4;
  v9 = (const UNICODE_STRING *)(a2 + 8);
  v10 = *(_QWORD *)(a2 + 16);
  v11 = *(unsigned __int16 *)(a2 + 8);
  if ( v10 )
  {
    if ( (_WORD)v11 )
    {
      if ( v10 >= a3 )
      {
        v10 -= a3;
        if ( !v10 )
          goto LABEL_4;
      }
      if ( v10 > a4 )
        goto LABEL_4;
      if ( v10 + v11 > a4 )
        goto LABEL_4;
      if ( v10 < 0x18 )
        goto LABEL_4;
      if ( (v10 & 1) != 0 )
        goto LABEL_4;
      *(_WORD *)(a2 + 10) = v11;
      *(_QWORD *)(a2 + 16) = v10 + a2;
      if ( (v11 & 1) != 0 )
        goto LABEL_4;
    }
    else
    {
      *(_QWORD *)(a2 + 16) = 0;
    }
LABEL_16:
    v14 = *(_DWORD *)(a2 + 4);
    ClientBuffer = 0;
    if ( (v14 & 3) == 0 )
    {
      if ( (v14 & 4) == 0 )
        goto LABEL_6;
      v39 = 0;
      RtlAcquireResourceShared(&NtLmGlobalHostTableLock, 1u);
      if ( !NtLmGlobalEphemeralHostTable || (v32 = 2, !*(_DWORD *)NtLmGlobalEphemeralHostTable) )
        v32 = 4;
      for ( i = 0; NtLmGlobalEphemeralHostTable && i < *(_DWORD *)NtLmGlobalEphemeralHostTable; ++i )
      {
        v34 = *(unsigned __int16 *)(*(_QWORD *)(NtLmGlobalEphemeralHostTable + 8) + 16LL * i) + 2;
        v32 += v34;
        if ( v32 < v34 )
        {
          ClientBuffer = -1073741675;
          goto LABEL_41;
        }
      }
      if ( v32 > 0x7FFF )
      {
        ClientBuffer = -1073741595;
        goto LABEL_5;
      }
      *a6 = v32 + 24;
      ClientBuffer = NlpAllocateClientBuffer((__int64)&v40, 24, v32 + 24);
      if ( ClientBuffer >= 0 )
      {
        v35 = *((_QWORD *)&v41 + 1);
        LOWORD(v39) = v32 - 2;
        v36 = 0;
        WORD1(v39) = v32 - 2;
        v37 = NtLmGlobalEphemeralHostTable;
        **((_DWORD **)&v41 + 1) = 13;
        v38 = (char *)(v35 + 24);
        *((_QWORD *)&v39 + 1) = v35 + 24;
        if ( v37 )
        {
          while ( v36 < *(_DWORD *)v37 )
          {
            memcpy_0(
              v38,
              *(const void **)(*(_QWORD *)(v37 + 8) + 16LL * v36 + 8),
              *(unsigned __int16 *)(*(_QWORD *)(v37 + 8) + 16LL * v36));
            v38 += *(unsigned __int16 *)(*(_QWORD *)(v37 + 8) + 16LL * v36++) + 2;
          }
        }
        NlpPutClientString(&v40, v35 + 8, &v39);
        ClientBuffer = NlpFlushClientBuffer((__int64)&v40, a5);
        goto LABEL_70;
      }
LABEL_41:
      RtlReleaseResource(&NtLmGlobalHostTableLock);
      goto LABEL_5;
    }
    if ( !(_WORD)v11 )
      goto LABEL_6;
    v15 = 0;
    RtlAcquireResourceExclusive(&NtLmGlobalHostTableLock, 1u);
    for ( j = 0; ; ++j )
    {
      v17 = (_DWORD *)NtLmGlobalEphemeralHostTable;
      if ( !NtLmGlobalEphemeralHostTable || j >= *(_DWORD *)NtLmGlobalEphemeralHostTable )
        break;
      if ( RtlEqualUnicodeString(v9, (PCUNICODE_STRING)(*(_QWORD *)(NtLmGlobalEphemeralHostTable + 8) + 16LL * j), 1u) )
      {
        v17 = (_DWORD *)NtLmGlobalEphemeralHostTable;
        v15 = 1;
        break;
      }
    }
    v18 = *(_DWORD *)(a2 + 4);
    if ( (v18 & 1) != 0 )
    {
      if ( !v15 )
      {
        v19 = ((__int64 (__fastcall *)(__int64))LsaFunctions->AllocatePrivateHeap)(16);
        if ( v19 )
        {
          if ( NtLmGlobalEphemeralHostTable )
            v20 = *(_DWORD *)NtLmGlobalEphemeralHostTable;
          else
            v20 = 0;
          v21 = (unsigned int)(v20 + 1);
          *(_DWORD *)v19 = v21;
          v22 = (void *)((__int64 (__fastcall *)(__int64))LsaFunctions->AllocatePrivateHeap)(16 * v21);
          *(_QWORD *)(v19 + 8) = v22;
          if ( v22 )
          {
            v23 = (unsigned int *)NtLmGlobalEphemeralHostTable;
            if ( NtLmGlobalEphemeralHostTable )
            {
              memcpy_0(
                v22,
                *(const void **)(NtLmGlobalEphemeralHostTable + 8),
                16LL * *(unsigned int *)NtLmGlobalEphemeralHostTable);
              memset_0(*((void **)v23 + 1), 0, 16LL * *v23);
            }
            ClientBuffer = NtLmDuplicateUnicodeString(
                             *(_QWORD *)(v19 + 8) + 16LL * (unsigned int)(*(_DWORD *)v19 - 1),
                             v9);
            if ( ClientBuffer >= 0 )
            {
              v24 = NtLmGlobalEphemeralHostTable;
LABEL_52:
              SspFreeStringTable(v24);
              ((void (__fastcall *)(__int64))LsaFunctions->FreePrivateHeap)(NtLmGlobalEphemeralHostTable);
              NtLmGlobalEphemeralHostTable = v19;
              goto LABEL_70;
            }
LABEL_44:
            RtlReleaseResource(&NtLmGlobalHostTableLock);
            SspFreeStringTable(v19);
            ((void (__fastcall *)(__int64))LsaFunctions->FreePrivateHeap)(v19);
            goto LABEL_71;
          }
LABEL_43:
          ClientBuffer = -1073741801;
          goto LABEL_44;
        }
LABEL_40:
        ClientBuffer = -1073741801;
        goto LABEL_41;
      }
    }
    else
    {
      if ( (v18 & 2) == 0 || !v15 )
        goto LABEL_70;
      if ( *v17 != 1 )
      {
        v19 = ((__int64 (__fastcall *)(__int64))LsaFunctions->AllocatePrivateHeap)(16);
        if ( v19 )
        {
          v25 = LsaFunctions;
          v26 = (unsigned int)(*(_DWORD *)NtLmGlobalEphemeralHostTable - 1);
          *(_DWORD *)v19 = v26;
          v27 = ((__int64 (__fastcall *)(__int64))v25->AllocatePrivateHeap)(16 * v26);
          *(_QWORD *)(v19 + 8) = v27;
          if ( v27 )
          {
            v28 = NtLmGlobalEphemeralHostTable;
            v29 = 0;
            if ( *(_DWORD *)NtLmGlobalEphemeralHostTable )
            {
              do
              {
                if ( v29 >= *(_DWORD *)v19 )
                  break;
                v30 = 16LL * v7;
                if ( RtlEqualUnicodeString(v9, (PCUNICODE_STRING)(v30 + *(_QWORD *)(v28 + 8)), 1u) )
                {
                  ((void (__fastcall *)(_QWORD))LsaFunctions->FreePrivateHeap)(*(_QWORD *)(*(_QWORD *)(NtLmGlobalEphemeralHostTable + 8)
                                                                                         + v30
                                                                                         + 8));
                  v28 = NtLmGlobalEphemeralHostTable;
                }
                else
                {
                  v28 = NtLmGlobalEphemeralHostTable;
                  v31 = 2LL * v29++;
                  *(_OWORD *)(*(_QWORD *)(v19 + 8) + 8 * v31) = *(_OWORD *)(*(_QWORD *)(NtLmGlobalEphemeralHostTable + 8)
                                                                          + 16LL * v7);
                }
                ++v7;
                *(_OWORD *)(v30 + *(_QWORD *)(v28 + 8)) = 0;
              }
              while ( v7 < *(_DWORD *)v28 );
            }
            v24 = v28;
            goto LABEL_52;
          }
          goto LABEL_43;
        }
        goto LABEL_40;
      }
      ((void (*)(void))SspFreeStringTable)();
      ((void (__fastcall *)(__int64))LsaFunctions->FreePrivateHeap)(NtLmGlobalEphemeralHostTable);
      NtLmGlobalEphemeralHostTable = 0;
    }
LABEL_70:
    RtlReleaseResource(&NtLmGlobalHostTableLock);
LABEL_71:
    if ( ClientBuffer >= 0 )
      goto LABEL_6;
    goto LABEL_5;
  }
  if ( !(_WORD)v11 )
    goto LABEL_16;
LABEL_4:
  ClientBuffer = -1073741811;
LABEL_5:
  NlpFreeClientBuffer(&v40);
LABEL_6:
  *a7 = ClientBuffer;
  return 0;
}

```

## disassembly

```asm
0x18003cf50  push    rbp
0x18003cf52  push    rbx
0x18003cf53  push    rsi
0x18003cf54  push    rdi
0x18003cf55  push    r12
0x18003cf57  push    r13
0x18003cf59  push    r14
0x18003cf5b  push    r15
0x18003cf5d  mov     rbp, rsp
0x18003cf60  sub     rsp, 58h
0x18003cf64  mov     rax, [rbp+arg_20]
0x18003cf68  xor     r12d, r12d
0x18003cf6b  mov     r15, [rbp+arg_28]
0x18003cf6f  xorps   xmm0, xmm0
0x18003cf72  mov     [rbp+var_28], rcx
0x18003cf76  mov     rsi, rdx
0x18003cf79  mov     [rbp+var_10], r12
0x18003cf7d  mov     [rax], r12
0x18003cf80  mov     [r15], r12d
0x18003cf83  movdqu  [rbp+var_20], xmm0
0x18003cf88  cmp     r9d, 18h
0x18003cf8c  jb      short loc_18003CFA5
0x18003cf8e  lea     r13, [rdx+8]
0x18003cf92  mov     rcx, [r13+8]
0x18003cf96  movzx   edx, word ptr [r13+0]
0x18003cf9b  test    rcx, rcx
0x18003cf9e  jnz     short loc_18003CFCC
0x18003cfa0  test    dx, dx
0x18003cfa3  jz      short loc_18003D00E
0x18003cfa5  mov     ebx, 0C000000Dh
0x18003cfaa  lea     rcx, [rbp+var_28]
0x18003cfae  call    NlpFreeClientBuffer
0x18003cfb3  mov     rax, [rbp+arg_30]
0x18003cfb7  mov     [rax], ebx
0x18003cfb9  xor     eax, eax
0x18003cfbb  add     rsp, 58h
0x18003cfbf  pop     r15
0x18003cfc1  pop     r14
0x18003cfc3  pop     r13
0x18003cfc5  pop     r12
0x18003cfc7  pop     rdi
0x18003cfc8  pop     rsi
0x18003cfc9  pop     rbx
0x18003cfca  pop     rbp
0x18003cfcb  retn
0x18003cfcc  test    dx, dx
0x18003cfcf  jnz     short loc_18003CFD7
0x18003cfd1  mov     [rsi+10h], r12
0x18003cfd5  jmp     short loc_18003D00E
0x18003cfd7  cmp     rcx, r8
0x18003cfda  jb      short loc_18003CFE1
0x18003cfdc  sub     rcx, r8
0x18003cfdf  jz      short loc_18003CFA5
0x18003cfe1  mov     r8d, r9d
0x18003cfe4  cmp     rcx, r8
0x18003cfe7  ja      short loc_18003CFA5
0x18003cfe9  lea     rax, [rcx+rdx]
0x18003cfed  cmp     rax, r8
0x18003cff0  ja      short loc_18003CFA5
0x18003cff2  cmp     rcx, 18h
0x18003cff6  jb      short loc_18003CFA5
0x18003cff8  test    cl, 1
0x18003cffb  jnz     short loc_18003CFA5
0x18003cffd  mov     [rsi+0Ah], dx
0x18003d001  lea     rax, [rcx+rsi]
0x18003d005  mov     [rsi+10h], rax
0x18003d009  test    dl, 1
0x18003d00c  jnz     short loc_18003CFA5
0x18003d00e  mov     eax, [rsi+4]
0x18003d011  mov     ebx, r12d
0x18003d014  test    al, 3
0x18003d016  jz      loc_18003D2ED
0x18003d01c  test    dx, dx
0x18003d01f  jz      short loc_18003CFB3
0x18003d021  lea     rdi, NtLmGlobalHostTableLock
0x18003d028  mov     dl, 1; Wait
0x18003d02a  mov     rcx, rdi; Resource
0x18003d02d  mov     r15d, r12d
0x18003d030  call    cs:__imp_RtlAcquireResourceExclusive
0x18003d036  mov     r14d, r12d
0x18003d039  mov     rcx, cs:NtLmGlobalEphemeralHostTable
0x18003d040  test    rcx, rcx
0x18003d043  jz      short loc_18003D077
0x18003d045  cmp     r14d, [rcx]
0x18003d048  jnb     short loc_18003D077
0x18003d04a  mov     edx, r14d
0x18003d04d  mov     r8b, 1; CaseInsensitive
0x18003d050  shl     rdx, 4
0x18003d054  add     rdx, [rcx+8]; String2
0x18003d058  mov     rcx, r13; String1
0x18003d05b  call    cs:__imp_RtlEqualUnicodeString
0x18003d061  test    al, al
0x18003d063  jnz     short loc_18003D06A
0x18003d065  inc     r14d
0x18003d068  jmp     short loc_18003D039
0x18003d06a  mov     rcx, cs:NtLmGlobalEphemeralHostTable
0x18003d071  mov     r15d, 1
0x18003d077  mov     eax, [rsi+4]
0x18003d07a  test    al, 1
0x18003d07c  jz      loc_18003D146
0x18003d082  test    r15d, r15d
0x18003d085  jnz     loc_18003D411
0x18003d08b  mov     rax, cs:LsaFunctions
0x18003d092  lea     ecx, [r15+10h]
0x18003d096  mov     rax, [rax+180h]
0x18003d09d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0a2  mov     rsi, rax
0x18003d0a5  test    rax, rax
0x18003d0a8  jz      loc_18003D1AE
0x18003d0ae  mov     rax, cs:NtLmGlobalEphemeralHostTable
0x18003d0b5  test    rax, rax
0x18003d0b8  jz      short loc_18003D0BE
0x18003d0ba  mov     eax, [rax]
0x18003d0bc  jmp     short loc_18003D0C1
0x18003d0be  mov     eax, r12d
0x18003d0c1  inc     eax
0x18003d0c3  mov     ecx, eax
0x18003d0c5  mov     [rsi], eax
0x18003d0c7  mov     rax, cs:LsaFunctions
0x18003d0ce  shl     rcx, 4
0x18003d0d2  mov     rax, [rax+180h]
0x18003d0d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0de  mov     [rsi+8], rax
0x18003d0e2  test    rax, rax
0x18003d0e5  jz      loc_18003D1EE
0x18003d0eb  mov     rbx, cs:NtLmGlobalEphemeralHostTable
0x18003d0f2  test    rbx, rbx
0x18003d0f5  jz      short loc_18003D11C
0x18003d0f7  mov     r8d, [rbx]
0x18003d0fa  mov     rcx, rax; void *
0x18003d0fd  mov     rdx, [rbx+8]; Src
0x18003d101  shl     r8, 4; Size
0x18003d105  call    memcpy_0
0x18003d10a  mov     r8d, [rbx]
0x18003d10d  xor     edx, edx; Val
0x18003d10f  mov     rcx, [rbx+8]; void *
0x18003d113  shl     r8, 4; Size
0x18003d117  call    memset_0
0x18003d11c  mov     ecx, [rsi]
0x18003d11e  mov     rdx, r13
0x18003d121  dec     ecx
0x18003d123  shl     rcx, 4
0x18003d127  add     rcx, [rsi+8]
0x18003d12b  call    NtLmDuplicateUnicodeString
0x18003d130  mov     ebx, eax
0x18003d132  test    eax, eax
0x18003d134  js      loc_18003D1F3
0x18003d13a  mov     rcx, cs:NtLmGlobalEphemeralHostTable
0x18003d141  jmp     loc_18003D2C2
0x18003d146  mov     r14d, 2
0x18003d14c  test    r14b, al
0x18003d14f  jz      loc_18003D411
0x18003d155  test    r15d, r15d
0x18003d158  jz      loc_18003D411
0x18003d15e  cmp     dword ptr [rcx], 1
0x18003d161  jnz     short loc_18003D18E
0x18003d163  call    SspFreeStringTable
0x18003d168  mov     rax, cs:LsaFunctions
0x18003d16f  mov     rcx, cs:NtLmGlobalEphemeralHostTable
0x18003d176  mov     rax, [rax+188h]
0x18003d17d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d182  mov     cs:NtLmGlobalEphemeralHostTable, r12
0x18003d189  jmp     loc_18003D411
0x18003d18e  mov     rax, cs:LsaFunctions
0x18003d195  mov     ecx, 10h
0x18003d19a  mov     rax, [rax+180h]
0x18003d1a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1a6  mov     rsi, rax
0x18003d1a9  test    rax, rax
0x18003d1ac  jnz     short loc_18003D1C1
0x18003d1ae  mov     ebx, 0C0000017h
0x18003d1b3  mov     rcx, rdi; Resource
0x18003d1b6  call    cs:__imp_RtlReleaseResource
0x18003d1bc  jmp     loc_18003CFAA
0x18003d1c1  mov     rax, cs:NtLmGlobalEphemeralHostTable
0x18003d1c8  mov     ecx, [rax]
0x18003d1ca  mov     rax, cs:LsaFunctions
0x18003d1d1  dec     ecx
0x18003d1d3  mov     [rsi], ecx
0x18003d1d5  shl     rcx, 4
0x18003d1d9  mov     rax, [rax+180h]
0x18003d1e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1e5  mov     [rsi+8], rax
0x18003d1e9  test    rax, rax
0x18003d1ec  jnz     short loc_18003D21F
0x18003d1ee  mov     ebx, 0C0000017h
0x18003d1f3  mov     rcx, rdi; Resource
0x18003d1f6  call    cs:__imp_RtlReleaseResource
0x18003d1fc  mov     rcx, rsi
0x18003d1ff  call    SspFreeStringTable
0x18003d204  mov     rax, cs:LsaFunctions
0x18003d20b  mov     rcx, rsi
0x18003d20e  mov     rax, [rax+188h]
0x18003d215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d21a  jmp     loc_18003D41A
0x18003d21f  mov     r8, cs:NtLmGlobalEphemeralHostTable
0x18003d226  mov     r15d, r12d
0x18003d229  cmp     [r8], ebx
0x18003d22c  jbe     loc_18003D2BF
0x18003d232  cmp     r15d, [rsi]
0x18003d235  jnb     loc_18003D2BF
0x18003d23b  mov     rdx, [r8+8]
0x18003d23f  mov     rcx, r13; String1
0x18003d242  mov     r14d, r12d
0x18003d245  mov     r8b, 1; CaseInsensitive
0x18003d248  shl     r14, 4
0x18003d24c  add     rdx, r14; String2
0x18003d24f  call    cs:__imp_RtlEqualUnicodeString
0x18003d255  test    al, al
0x18003d257  jz      short loc_18003D285
0x18003d259  mov     rax, cs:NtLmGlobalEphemeralHostTable
0x18003d260  mov     rcx, [rax+8]
0x18003d264  mov     rax, cs:LsaFunctions
0x18003d26b  mov     rcx, [rcx+r14+8]
0x18003d270  mov     rax, [rax+188h]
0x18003d277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d27c  mov     r8, cs:NtLmGlobalEphemeralHostTable
0x18003d283  jmp     short loc_18003D2A7
0x18003d285  mov     r8, cs:NtLmGlobalEphemeralHostTable
0x18003d28c  mov     rax, [rsi+8]
0x18003d290  mov     edx, r15d
0x18003d293  add     rdx, rdx
0x18003d296  mov     rcx, [r8+8]
0x18003d29a  inc     r15d
0x18003d29d  movups  xmm0, xmmword ptr [rcx+r14]
0x18003d2a2  movdqu  xmmword ptr [rax+rdx*8], xmm0
0x18003d2a7  mov     rax, [r8+8]
0x18003d2ab  xorps   xmm0, xmm0
0x18003d2ae  inc     r12d
0x18003d2b1  movups  xmmword ptr [r14+rax], xmm0
0x18003d2b6  cmp     r12d, [r8]
0x18003d2b9  jb      loc_18003D232
0x18003d2bf  mov     rcx, r8
0x18003d2c2  call    SspFreeStringTable
0x18003d2c7  mov     rax, cs:LsaFunctions
0x18003d2ce  mov     rcx, cs:NtLmGlobalEphemeralHostTable
0x18003d2d5  mov     rax, [rax+188h]
0x18003d2dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2e1  mov     cs:NtLmGlobalEphemeralHostTable, rsi
0x18003d2e8  jmp     loc_18003D411
0x18003d2ed  test    al, 4
0x18003d2ef  jz      loc_18003CFB3
0x18003d2f5  lea     rdi, NtLmGlobalHostTableLock
0x18003d2fc  mov     dl, 1; Wait
0x18003d2fe  mov     rcx, rdi; Resource
0x18003d301  movups  [rbp+var_38], xmm0
0x18003d305  call    cs:__imp_RtlAcquireResourceShared
0x18003d30b  mov     rdx, cs:NtLmGlobalEphemeralHostTable
0x18003d312  mov     r14d, 2
0x18003d318  test    rdx, rdx
0x18003d31b  jz      short loc_18003D325
0x18003d31d  mov     esi, r14d
0x18003d320  cmp     [rdx], r12d
0x18003d323  jnz     short loc_18003D32A
0x18003d325  mov     esi, 4
0x18003d32a  mov     r8d, r12d
0x18003d32d  test    rdx, rdx
0x18003d330  jz      short loc_18003D35D
0x18003d332  cmp     r8d, [rdx]
0x18003d335  jnb     short loc_18003D35D
0x18003d337  mov     rax, [rdx+8]
0x18003d33b  mov     ecx, r8d
0x18003d33e  add     rcx, rcx
0x18003d341  movzx   ecx, word ptr [rax+rcx*8]
0x18003d345  add     ecx, r14d
0x18003d348  add     esi, ecx
0x18003d34a  cmp     esi, ecx
0x18003d34c  jb      short loc_18003D353
0x18003d34e  inc     r8d
0x18003d351  jmp     short loc_18003D32D
0x18003d353  mov     ebx, 0C0000095h
0x18003d358  jmp     loc_18003D1B3
0x18003d35d  cmp     esi, 7FFFh
0x18003d363  jbe     short loc_18003D36F
0x18003d365  mov     ebx, 0C00000E5h
0x18003d36a  jmp     loc_18003CFAA
0x18003d36f  lea     r8d, [rsi+18h]
0x18003d373  mov     edx, 18h
0x18003d378  lea     rcx, [rbp+var_28]
0x18003d37c  mov     [r15], r8d
0x18003d37f  call    NlpAllocateClientBuffer
0x18003d384  mov     ebx, eax
0x18003d386  test    eax, eax
0x18003d388  js      loc_18003D1B3
0x18003d38e  mov     r15, qword ptr [rbp+var_20+8]
0x18003d392  sub     si, r14w
0x18003d396  mov     word ptr [rbp+var_38], si
0x18003d39a  xor     r14d, r14d
0x18003d39d  mov     word ptr [rbp+var_38+2], si
0x18003d3a1  mov     rsi, cs:NtLmGlobalEphemeralHostTable
0x18003d3a8  mov     dword ptr [r15], 0Dh
0x18003d3af  lea     r12, [r15+18h]
0x18003d3b3  mov     qword ptr [rbp+var_38+8], r12
0x18003d3b7  test    rsi, rsi
0x18003d3ba  jz      short loc_18003D3F1
0x18003d3bc  cmp     r14d, [rsi]
0x18003d3bf  jnb     short loc_18003D3F1
0x18003d3c1  mov     rdx, [rsi+8]
0x18003d3c5  mov     rcx, r12; void *
0x18003d3c8  mov     ebx, r14d
  ... truncated ...
```
