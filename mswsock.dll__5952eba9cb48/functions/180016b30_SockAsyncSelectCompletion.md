# SockAsyncSelectCompletion

- ea: `0x180016b30`
- end: `0x1800172a7`
- name: `SockAsyncSelectCompletion`
- size: `1911`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800173f0`

## callees

- `0x1800052a0`
- `0x180008250`
- `0x180016b30`
- `0x1800173f0`
- `0x1800381a0`
- `0x1800382b8`
- `0x180038318`
- `0x1800383fc`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180016d39`
- `ntdll!RtlFreeHeap` at `0x180016d39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016cf1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016d13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016cf1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016d13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016b5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016b5d`

## string_xrefs

- `0x180016e53`: `FD_READ`
- `0x180016f22`: `FD_WRITE`

## pseudocode

```c
void __fastcall SockAsyncSelectCompletion(_DWORD *P, unsigned int *a2, __int64 a3)
{
  __int64 v3; // rbx
  int v6; // edx
  int v7; // r8d
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // r8
  int v11; // r8d
  unsigned int *v12; // r15
  int v13; // edi
  int v14; // edx
  _QWORD *v15; // r12
  int v16; // ecx
  int v17; // r8d
  int v18; // ecx
  int v19; // r8d
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  const char *v23; // rax
  unsigned __int16 v24; // ax
  char v25; // di
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  __int64 v29; // r9
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx

  v3 = *(_QWORD *)P;
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_qqLL(P, a2, a3, *(_QWORD *)P, *(_QWORD *)(v3 + 8), *a2, P[14]);
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 224));
  v8 = *a2;
  if ( (_DWORD)v8 == -1073741536 || *(_DWORD *)(v3 + 24) == 4 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
    {
      v23 = "closed";
      if ( *(_DWORD *)(v3 + 24) != 4 )
        v23 = "cancelled";
      WPP_SF_qs((unsigned int)"cancelled", v6, v7, *(_QWORD *)(v3 + 8), (__int64)v23);
    }
  }
  else
  {
    v9 = *(_DWORD *)(v3 + 112);
    v10 = (unsigned int)P[2];
    if ( (_DWORD)v10 == v9 )
    {
      if ( (int)v8 < 0 )
      {
        v24 = NtStatusToSocketError(v8);
        v25 = v24;
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(SockUpcallTable + 56))(
          *(_QWORD *)(v3 + 104),
          *(unsigned int *)(v3 + 116),
          *(_QWORD *)(v3 + 8),
          v24 << 16);
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_Lqisl(
            v26,
            28,
            (unsigned int)WPP_6558a8cfbcde30925840af8972a4178a_Traceguids,
            *(_DWORD *)(v3 + 116),
            *(_QWORD *)(v3 + 104),
            *(_QWORD *)(v3 + 8),
            (__int64)"0",
            v25);
      }
      else
      {
        v11 = *(_DWORD *)(v3 + 120);
        v12 = (unsigned int *)(v3 + 116);
        v13 = P[14];
        v14 = *(_DWORD *)(v3 + 124);
        v15 = (_QWORD *)(v3 + 104);
        if ( ((unsigned __int8)v13 & *(_BYTE *)(v3 + 120) & 1) != 0 && (v14 & 1) == 0 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(SockUpcallTable + 56))(
            *v15,
            *v12,
            *(_QWORD *)(v3 + 8),
            1);
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_Lqisl(
              v16,
              29,
              (unsigned int)WPP_6558a8cfbcde30925840af8972a4178a_Traceguids,
              *v12,
              *v15,
              *(_QWORD *)(v3 + 8),
              (__int64)"FD_READ",
              0);
          *(_DWORD *)(v3 + 124) |= 1u;
          v14 = *(_DWORD *)(v3 + 124);
          v11 = *(_DWORD *)(v3 + 120);
        }
        if ( (v14 & 4) == 0 && (v11 & 4) != 0 && (v13 & 2) != 0 )
        {
          v12 = (unsigned int *)(v3 + 116);
          v15 = (_QWORD *)(v3 + 104);
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(SockUpcallTable + 56))(
            *(_QWORD *)(v3 + 104),
            *(unsigned int *)(v3 + 116),
            *(_QWORD *)(v3 + 8),
            4);
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_Lqisl(
              v27,
              30,
              (unsigned int)WPP_6558a8cfbcde30925840af8972a4178a_Traceguids,
              *v12,
              *v15,
              *(_QWORD *)(v3 + 8),
              (__int64)"FD_OOB",
              0);
          v14 = *(_DWORD *)(v3 + 124) | 4;
          *(_DWORD *)(v3 + 124) = v14;
        }
        v17 = *(_DWORD *)(v3 + 120);
        if ( (v17 & 2) != 0 && (v14 & 2) == 0 && (v13 & 4) != 0 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(SockUpcallTable + 56))(
            *v15,
            *v12,
            *(_QWORD *)(v3 + 8),
            2);
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_Lqisl(
              v18,
              31,
              (unsigned int)WPP_6558a8cfbcde30925840af8972a4178a_Traceguids,
              *v12,
              *v15,
              *(_QWORD *)(v3 + 8),
              (__int64)"FD_WRITE",
              0);
          *(_DWORD *)(v3 + 124) |= 2u;
          v14 = *(_DWORD *)(v3 + 124);
          v17 = *(_DWORD *)(v3 + 120);
        }
        if ( (v14 & 8) == 0 && (v17 & 8) != 0 && (v13 & 0x80u) != 0 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(SockUpcallTable + 56))(
            *v15,
            *v12,
            *(_QWORD *)(v3 + 8),
            8);
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_Lqisl(
              v28,
              32,
              (unsigned int)WPP_6558a8cfbcde30925840af8972a4178a_Traceguids,
              *v12,
              *v15,
              *(_QWORD *)(v3 + 8),
              (__int64)"FD_ACCEPT",
              0);
          *(_DWORD *)(v3 + 124) |= 8u;
          v14 = *(_DWORD *)(v3 + 124);
        }
        v19 = *(_DWORD *)(v3 + 120);
        if ( (v14 & 0x20) == 0 && (v19 & 0x20) != 0 && ((v13 & 0x18) != 0 || (v13 & 0x20) != 0) )
        {
          v29 = 658833440;
          if ( (v13 & 0x10) == 0 )
            v29 = 32;
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(SockUpcallTable + 56))(
            *v15,
            *v12,
            *(_QWORD *)(v3 + 8),
            v29);
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_Lqisl(
              v30,
              33,
              (unsigned int)WPP_6558a8cfbcde30925840af8972a4178a_Traceguids,
              *v12,
              *v15,
              *(_QWORD *)(v3 + 8),
              (__int64)"FD_CLOSE",
              0);
          *(_DWORD *)(v3 + 124) |= 0x20u;
          v14 = *(_DWORD *)(v3 + 124);
          v19 = *(_DWORD *)(v3 + 120);
        }
        if ( (v14 & 0x40) == 0 && (v19 & 0x40) != 0 && (v13 & 0x200) != 0 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(SockUpcallTable + 56))(
            *v15,
            *v12,
            *(_QWORD *)(v3 + 8),
            64);
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_Lqisl(
              v31,
              34,
              (unsigned int)WPP_6558a8cfbcde30925840af8972a4178a_Traceguids,
              *v12,
              *v15,
              *(_QWORD *)(v3 + 8),
              (__int64)"FD_QOS",
              0);
          *(_DWORD *)(v3 + 124) |= 0x40u;
          v14 = *(_DWORD *)(v3 + 124);
          v19 = *(_DWORD *)(v3 + 120);
        }
        if ( (v14 & 0x80u) == 0 && (v19 & 0x80u) != 0 && (v13 & 0x400) != 0 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(SockUpcallTable + 56))(
            *v15,
            *v12,
            *(_QWORD *)(v3 + 8),
            128);
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_Lqisl(
              v32,
              35,
              (unsigned int)WPP_6558a8cfbcde30925840af8972a4178a_Traceguids,
              *v12,
              *v15,
              *(_QWORD *)(v3 + 8),
              (__int64)"FD_GROUP_QOS",
              0);
          *(_DWORD *)(v3 + 124) |= 0x80u;
          v14 = *(_DWORD *)(v3 + 124);
          v19 = *(_DWORD *)(v3 + 120);
        }
        if ( (v14 & 0x100) == 0 && (v19 & 0x100) != 0 && (v13 & 0x800) != 0 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(SockUpcallTable + 56))(
            *v15,
            *v12,
            *(_QWORD *)(v3 + 8),
            256);
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_Lqisl(
              v33,
              36,
              (unsigned int)WPP_6558a8cfbcde30925840af8972a4178a_Traceguids,
              *v12,
              *v15,
              *(_QWORD *)(v3 + 8),
              (__int64)"FD_ROUTING_INTERFACE_CHANGE",
              0);
        }
        if ( (*(_DWORD *)(v3 + 124) & 0x200) == 0 && (*(_DWORD *)(v3 + 120) & 0x200) != 0 && (v13 & 0x1000) != 0 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(SockUpcallTable + 56))(
            *v15,
            *v12,
            *(_QWORD *)(v3 + 8),
            512);
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_Lqisl(
              v34,
              37,
              (unsigned int)WPP_6558a8cfbcde30925840af8972a4178a_Traceguids,
              *v12,
              *v15,
              *(_QWORD *)(v3 + 8),
              (__int64)"FD_ADDRESS_LIST_CHANGE",
              0);
        }
        v20 = *(unsigned int *)(v3 + 120);
        if ( (~*(_DWORD *)(v3 + 124) & (unsigned int)v20) != 0 )
        {
          SockProcessAsyncSelect(v3, P);
          LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 224));
          return;
        }
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_qll(v20, 38, *(unsigned int *)(v3 + 124), v3, v20, *(_DWORD *)(v3 + 124));
      }
    }
    else if ( (xmmword_180063D60 & 2) != 0 )
    {
      WPP_SF_qll(v8, 27, v10, *(_QWORD *)(v3 + 8), v9, P[2]);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 224));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3, 0xFFFFFFFF) == 1 )
    SockDestroySocket(v3, v21, v22);
  RtlFreeHeap(SockPrivateHeap, 0, P);
  _InterlockedDecrement(&SockAsyncThreadReferenceCount);
}

```

## disassembly

```asm
0x180016b30  mov     [rsp+arg_10], rbx
0x180016b35  push    rbp
0x180016b36  push    rsi
0x180016b37  push    rdi
0x180016b38  push    r14
0x180016b3a  push    r15
0x180016b3c  sub     rsp, 40h
0x180016b40  mov     rbx, [rcx]
0x180016b43  mov     r15, rdx
0x180016b46  mov     rsi, rcx
0x180016b49  test    byte ptr cs:xmmword_180063D60, 2
0x180016b50  jnz     loc_180016D9D
0x180016b56  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x180016b5d  call    cs:__imp_EnterCriticalSection
0x180016b64  nop     dword ptr [rax+rax+00h]
0x180016b69  mov     ecx, [r15]
0x180016b6c  cmp     ecx, 0C0000120h
0x180016b72  jz      loc_180016D61
0x180016b78  cmp     dword ptr [rbx+18h], 4
0x180016b7c  jz      loc_180016D61
0x180016b82  mov     eax, [rbx+70h]
0x180016b85  mov     r8d, [rsi+8]
0x180016b89  cmp     r8d, eax
0x180016b8c  jnz     loc_180016CFF
0x180016b92  test    ecx, ecx
0x180016b94  js      loc_180016DDC
0x180016b9a  mov     r8d, [rbx+78h]
0x180016b9e  lea     r15, [rbx+74h]
0x180016ba2  mov     edi, [rsi+38h]
0x180016ba5  mov     eax, r8d
0x180016ba8  mov     edx, [rbx+7Ch]
0x180016bab  and     eax, edi
0x180016bad  test    al, 1
0x180016baf  mov     [rsp+68h+arg_0], r12
0x180016bb4  mov     [rsp+68h+arg_8], r13
0x180016bb9  lea     r12, [rbx+68h]
0x180016bbd  setnz   cl
0x180016bc0  test    dl, 1
0x180016bc3  setz    al
0x180016bc6  test    al, cl
0x180016bc8  jz      short loc_180016C03
0x180016bca  mov     rax, cs:SockUpcallTable
0x180016bd1  mov     r9d, 1
0x180016bd7  mov     r8, [rbx+8]
0x180016bdb  mov     edx, [r15]
0x180016bde  mov     rcx, [r12]
0x180016be2  mov     rax, [rax+38h]
0x180016be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016beb  test    byte ptr cs:xmmword_180063D60, 2
0x180016bf2  jnz     loc_180016E50
0x180016bf8  or      dword ptr [rbx+7Ch], 1
0x180016bfc  mov     edx, [rbx+7Ch]
0x180016bff  mov     r8d, [rbx+78h]
0x180016c03  test    dl, 4
0x180016c06  jz      loc_180016E8F
0x180016c0c  mov     r8d, [rbx+78h]
0x180016c10  test    dl, 2
0x180016c13  setz    cl
0x180016c16  test    r8b, 2
0x180016c1a  setnz   al
0x180016c1d  and     cl, al
0x180016c1f  test    dil, 4
0x180016c23  setnz   al
0x180016c26  test    al, cl
0x180016c28  jz      short loc_180016C63
0x180016c2a  mov     rax, cs:SockUpcallTable
0x180016c31  mov     r9d, 2
0x180016c37  mov     r8, [rbx+8]
0x180016c3b  mov     edx, [r15]
0x180016c3e  mov     rcx, [r12]
0x180016c42  mov     rax, [rax+38h]
0x180016c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c4b  test    byte ptr cs:xmmword_180063D60, 2
0x180016c52  jnz     loc_180016F1F
0x180016c58  or      dword ptr [rbx+7Ch], 2
0x180016c5c  mov     edx, [rbx+7Ch]
0x180016c5f  mov     r8d, [rbx+78h]
0x180016c63  mov     r13d, 20h ; ' '
0x180016c69  test    dl, 8
0x180016c6c  jz      loc_180016F5E
0x180016c72  mov     r8d, [rbx+78h]
0x180016c76  test    r13b, dl
0x180016c79  setz    cl
0x180016c7c  test    r13b, r8b
0x180016c7f  setnz   al
0x180016c82  test    al, cl
0x180016c84  jz      short loc_180016C99
0x180016c86  test    dil, 18h
0x180016c8a  jnz     loc_180016FE2
0x180016c90  test    r13b, dil
0x180016c93  jnz     loc_180016FE2
0x180016c99  mov     r13, [rsp+68h+arg_8]
0x180016c9e  test    dl, 40h
0x180016ca1  jz      loc_18001705E
0x180016ca7  test    dl, dl
0x180016ca9  jns     loc_1800170E8
0x180016caf  bt      edx, 8
0x180016cb3  jnb     loc_180017175
0x180016cb9  test    dword ptr [rbx+7Ch], 200h
0x180016cc0  jz      loc_1800171F9
0x180016cc6  mov     r8d, [rbx+7Ch]
0x180016cca  mov     eax, r8d
0x180016ccd  mov     ecx, [rbx+78h]
0x180016cd0  not     eax
0x180016cd2  mov     r12, [rsp+68h+arg_0]
0x180016cd7  test    ecx, eax
0x180016cd9  jz      loc_18001727F
0x180016cdf  mov     rdx, rsi
0x180016ce2  mov     rcx, rbx
0x180016ce5  call    SockProcessAsyncSelect
0x180016cea  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x180016cf1  call    cs:__imp_LeaveCriticalSection
0x180016cf8  nop     dword ptr [rax+rax+00h]
0x180016cfd  jmp     short loc_180016D4C
0x180016cff  test    byte ptr cs:xmmword_180063D60, 2
0x180016d06  jnz     loc_180016DC0
0x180016d0c  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x180016d13  call    cs:__imp_LeaveCriticalSection
0x180016d1a  nop     dword ptr [rax+rax+00h]
0x180016d1f  mov     eax, 0FFFFFFFFh
0x180016d24  lock xadd [rbx], eax
0x180016d28  cmp     eax, 1
0x180016d2b  jz      short loc_180016D93
0x180016d2d  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180016d34  mov     r8, rsi; P
0x180016d37  xor     edx, edx; Flags
0x180016d39  call    cs:__imp_RtlFreeHeap
0x180016d40  nop     dword ptr [rax+rax+00h]
0x180016d45  lock dec cs:SockAsyncThreadReferenceCount
0x180016d4c  mov     rbx, [rsp+68h+arg_10]
0x180016d54  add     rsp, 40h
0x180016d58  pop     r15
0x180016d5a  pop     r14
0x180016d5c  pop     rdi
0x180016d5d  pop     rsi
0x180016d5e  pop     rbp
0x180016d5f  retn
0x180016d61  test    byte ptr cs:xmmword_180063D60, 2
0x180016d68  jz      short loc_180016D0C
0x180016d6a  cmp     dword ptr [rbx+18h], 4
0x180016d6e  lea     rcx, aCancelled; "cancelled"
0x180016d75  mov     r9, [rbx+8]
0x180016d79  lea     rax, aClosed; "closed"
0x180016d80  cmovnz  rax, rcx
0x180016d84  mov     [rsp+68h+var_48], rax
0x180016d89  call    WPP_SF_qs
0x180016d8e  jmp     loc_180016D0C
0x180016d93  mov     rcx, rbx
0x180016d96  call    SockDestroySocket
0x180016d9b  jmp     short loc_180016D2D
0x180016d9d  mov     eax, [rcx+38h]
0x180016da0  mov     r9, rbx
0x180016da3  mov     dword ptr [rsp+68h+var_38], eax
0x180016da7  mov     eax, [rdx]
0x180016da9  mov     dword ptr [rsp+68h+var_40], eax
0x180016dad  mov     rax, [rbx+8]
0x180016db1  mov     [rsp+68h+var_48], rax
0x180016db6  call    WPP_SF_qqLL
0x180016dbb  jmp     loc_180016B56
0x180016dc0  mov     r9, [rbx+8]
0x180016dc4  mov     edx, 1Bh
0x180016dc9  mov     dword ptr [rsp+68h+var_40], r8d
0x180016dce  mov     dword ptr [rsp+68h+var_48], eax
0x180016dd2  call    WPP_SF_qll
0x180016dd7  jmp     loc_180016D0C
0x180016ddc  call    NtStatusToSocketError
0x180016de1  mov     r8, [rbx+8]
0x180016de5  mov     edi, eax
0x180016de7  mov     edx, [rbx+74h]
0x180016dea  movzx   ecx, ax
0x180016ded  shl     ecx, 10h
0x180016df0  movsxd  r9, ecx
0x180016df3  mov     rcx, cs:SockUpcallTable
0x180016dfa  mov     rax, [rcx+38h]
0x180016dfe  mov     rcx, [rbx+68h]
0x180016e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e07  test    byte ptr cs:xmmword_180063D60, 2
0x180016e0e  jz      loc_180016D0C
0x180016e14  mov     r9d, [rbx+74h]
0x180016e18  lea     rax, a0; "0"
0x180016e1f  mov     [rsp+68h+var_30], edi
0x180016e23  lea     r8, WPP_6558a8cfbcde30925840af8972a4178a_Traceguids
0x180016e2a  mov     [rsp+68h+var_38], rax
0x180016e2f  mov     edx, 1Ch
0x180016e34  mov     rax, [rbx+8]
0x180016e38  mov     [rsp+68h+var_40], rax
0x180016e3d  mov     rax, [rbx+68h]
0x180016e41  mov     [rsp+68h+var_48], rax
0x180016e46  call    WPP_SF_Lqisl
0x180016e4b  jmp     loc_180016D0C
0x180016e50  mov     r9d, [r15]
0x180016e53  lea     rax, aFdRead; "FD_READ"
0x180016e5a  mov     [rsp+68h+var_30], 0
0x180016e62  lea     r8, WPP_6558a8cfbcde30925840af8972a4178a_Traceguids
0x180016e69  mov     [rsp+68h+var_38], rax
0x180016e6e  mov     edx, 1Dh
0x180016e73  mov     rax, [rbx+8]
0x180016e77  mov     [rsp+68h+var_40], rax
0x180016e7c  mov     rax, [r12]
0x180016e80  mov     [rsp+68h+var_48], rax
0x180016e85  call    WPP_SF_Lqisl
0x180016e8a  jmp     loc_180016BF8
0x180016e8f  test    r8b, 4
0x180016e93  setnz   cl
0x180016e96  test    dil, 2
0x180016e9a  setnz   al
0x180016e9d  test    al, cl
0x180016e9f  jz      loc_180016C0C
0x180016ea5  mov     rax, cs:SockUpcallTable
0x180016eac  lea     r15, [rbx+74h]
0x180016eb0  mov     r8, [rbx+8]
0x180016eb4  lea     r12, [rbx+68h]
0x180016eb8  mov     edx, [r15]
0x180016ebb  mov     r9d, 4
0x180016ec1  mov     rcx, [r12]
0x180016ec5  mov     rax, [rax+38h]
0x180016ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ece  test    byte ptr cs:xmmword_180063D60, 2
0x180016ed5  jz      short loc_180016F11
0x180016ed7  mov     r9d, [r15]
0x180016eda  lea     rax, aFdOob; "FD_OOB"
0x180016ee1  mov     [rsp+68h+var_30], 0
0x180016ee9  lea     r8, WPP_6558a8cfbcde30925840af8972a4178a_Traceguids
0x180016ef0  mov     [rsp+68h+var_38], rax
0x180016ef5  mov     edx, 1Eh
0x180016efa  mov     rax, [rbx+8]
0x180016efe  mov     [rsp+68h+var_40], rax
0x180016f03  mov     rax, [r12]
0x180016f07  mov     [rsp+68h+var_48], rax
0x180016f0c  call    WPP_SF_Lqisl
0x180016f11  mov     edx, [rbx+7Ch]
0x180016f14  or      edx, 4
0x180016f17  mov     [rbx+7Ch], edx
0x180016f1a  jmp     loc_180016C0C
0x180016f1f  mov     r9d, [r15]
0x180016f22  lea     rax, aFdWrite; "FD_WRITE"
0x180016f29  mov     [rsp+68h+var_30], 0
0x180016f31  lea     r8, WPP_6558a8cfbcde30925840af8972a4178a_Traceguids
0x180016f38  mov     [rsp+68h+var_38], rax
0x180016f3d  mov     edx, 1Fh
0x180016f42  mov     rax, [rbx+8]
0x180016f46  mov     [rsp+68h+var_40], rax
0x180016f4b  mov     rax, [r12]
0x180016f4f  mov     [rsp+68h+var_48], rax
0x180016f54  call    WPP_SF_Lqisl
0x180016f59  jmp     loc_180016C58
0x180016f5e  test    r8b, 8
0x180016f62  setnz   cl
0x180016f65  test    dil, 80h
0x180016f69  setnz   al
0x180016f6c  test    al, cl
0x180016f6e  jz      loc_180016C72
0x180016f74  mov     rax, cs:SockUpcallTable
0x180016f7b  mov     r9d, 8
0x180016f81  mov     r8, [rbx+8]
0x180016f85  mov     edx, [r15]
0x180016f88  mov     rcx, [r12]
0x180016f8c  mov     rax, [rax+38h]
0x180016f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f95  test    byte ptr cs:xmmword_180063D60, 2
0x180016f9c  jz      short loc_180016FD6
0x180016f9e  mov     r9d, [r15]
0x180016fa1  lea     rax, aFdAccept; "FD_ACCEPT"
0x180016fa8  mov     [rsp+68h+var_30], 0
0x180016fb0  lea     r8, WPP_6558a8cfbcde30925840af8972a4178a_Traceguids
0x180016fb7  mov     [rsp+68h+var_38], rax
0x180016fbc  mov     edx, r13d
0x180016fbf  mov     rax, [rbx+8]
0x180016fc3  mov     [rsp+68h+var_40], rax
0x180016fc8  mov     rax, [r12]
0x180016fcc  mov     [rsp+68h+var_48], rax
0x180016fd1  call    WPP_SF_Lqisl
0x180016fd6  or      dword ptr [rbx+7Ch], 8
0x180016fda  mov     edx, [rbx+7Ch]
0x180016fdd  jmp     loc_180016C72
0x180016fe2  mov     rax, cs:SockUpcallTable
0x180016fe9  test    dil, 10h
0x180016fed  mov     r8, [rbx+8]
0x180016ff1  mov     r9d, 27450020h
0x180016ff7  mov     edx, [r15]
0x180016ffa  cmovz   r9, r13
0x180016ffe  mov     rcx, [r12]
0x180017002  mov     rax, [rax+38h]
0x180017006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001700b  test    byte ptr cs:xmmword_180063D60, 2
0x180017012  jz      short loc_18001704E
0x180017014  mov     r9d, [r15]
0x180017017  lea     rax, aFdClose; "FD_CLOSE"
0x18001701e  mov     [rsp+68h+var_30], 0
0x180017026  lea     r8, WPP_6558a8cfbcde30925840af8972a4178a_Traceguids
0x18001702d  mov     [rsp+68h+var_38], rax
0x180017032  mov     edx, 21h ; '!'
0x180017037  mov     rax, [rbx+8]
0x18001703b  mov     [rsp+68h+var_40], rax
0x180017040  mov     rax, [r12]
0x180017044  mov     [rsp+68h+var_48], rax
0x180017049  call    WPP_SF_Lqisl
0x18001704e  or      [rbx+7Ch], r13d
0x180017052  mov     edx, [rbx+7Ch]
0x180017055  mov     r8d, [rbx+78h]
  ... truncated ...
```
