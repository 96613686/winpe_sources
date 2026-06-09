# StartRdmaWrite

- ea: `0x180050c40`
- end: `0x18005115f`
- name: `StartRdmaWrite`
- size: `1311`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18004b1d0`

## callees

- `0x180008250`
- `0x1800380b0`
- `0x180039410`
- `0x18003ae8c`
- `0x18003dae8`
- `0x18004a288`
- `0x18004a520`
- `0x180050c40`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050ec1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050f2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800510c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050ec1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050f2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800510c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050e72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050eec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051070`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050e72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050eec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051070`

## pseudocode

```c
__int64 __fastcall StartRdmaWrite(__int64 a1, unsigned int a2, __int64 a3, _DWORD *a4)
{
  unsigned int v5; // r8d
  __int64 v8; // rsi
  unsigned int v9; // r13d
  __int64 v10; // rdi
  signed int v11; // r14d
  unsigned int v12; // edx
  __int64 v13; // r9
  __int64 v14; // rax
  unsigned int v15; // r9d
  __int64 v16; // rcx
  signed int v17; // edx
  unsigned int v18; // r10d
  unsigned int v19; // r15d
  int v20; // eax
  int v21; // ecx
  __int64 v22; // rdx
  __int64 v23; // r11
  __int64 v24; // r9
  __int64 v25; // rax
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // r9
  _DWORD *v31; // r8
  _QWORD *v32; // r8
  int v33; // eax
  BOOL v34; // eax
  _QWORD *v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // r8
  int v38; // [rsp+70h] [rbp-48h] BYREF
  __int64 v39; // [rsp+78h] [rbp-40h]
  int v40; // [rsp+C0h] [rbp+8h] BYREF
  unsigned int v41; // [rsp+C8h] [rbp+10h]
  unsigned int v42; // [rsp+D0h] [rbp+18h]
  _DWORD *v43; // [rsp+D8h] [rbp+20h]

  v43 = a4;
  v38 = 0;
  v40 = 0;
  v5 = a2;
  if ( !a3 )
  {
    *a4 = 10055;
    return 0xFFFFFFFFLL;
  }
  v8 = *(_QWORD *)(a1 + 56);
  v9 = 0;
  v10 = *(_QWORD *)(a1 + 64);
  if ( *(_DWORD *)(*(_QWORD *)(v8 + 16) + 360LL) < a2 )
    v5 = *(_DWORD *)(*(_QWORD *)(v8 + 16) + 360LL);
  v11 = 0;
  v41 = v5;
  if ( *(int *)(v10 + 56) <= 0 )
  {
LABEL_10:
    v15 = 0;
    v16 = v11;
  }
  else
  {
    v12 = *(_DWORD *)(v10 + 84);
    v13 = *(_QWORD *)(v10 + 48);
    while ( 1 )
    {
      v14 = 16LL * (unsigned int)v11;
      if ( *(_DWORD *)(v14 + v13) > v12 )
        break;
      v12 -= *(_DWORD *)(v14 + v13);
      if ( ++v11 >= *(_DWORD *)(v10 + 56) )
        goto LABEL_10;
    }
    v16 = v11;
    v15 = *(_DWORD *)(v13 + 16LL * v11) - v12;
  }
  v17 = v11;
  v18 = *(_DWORD *)(*(_QWORD *)(v10 + 48) + 16 * v16) - v15;
  v19 = 0;
  while ( 1 )
  {
    v20 = 4;
    v21 = *(_DWORD *)(v10 + 56) - v11;
    v42 = v17;
    if ( v21 < 4 )
      v20 = v21;
    if ( v17 >= v11 + v20 )
    {
LABEL_31:
      *(_QWORD *)(a1 + 32) = 0;
      *(_QWORD *)(a1 + 72) = a3;
      *(_DWORD *)(a1 + 80) = v19;
      *(_DWORD *)a1 = 1145333350;
      EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 48));
      v33 = *(_DWORD *)(v10 + 92);
      *(_DWORD *)(v10 + 84) += v9;
      *(_DWORD *)(v10 + 92) = v33 & 0xFFFFFF79 | 0x82;
      v34 = *(_DWORD *)(v10 + 84) == *(_DWORD *)(v10 + 80) || v9 == v41;
      *(_DWORD *)(a1 + 88) = v34;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 48));
      _InterlockedIncrement(*(volatile signed __int32 **)(v8 + 8));
      v42 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD, _DWORD, int *, _DWORD, __int64, _QWORD, __int64, _DWORD *))(*(_QWORD *)(v8 + 16) + 336LL))(
              *(_QWORD *)(v8 + 104),
              a3,
              v19,
              *(_QWORD *)(a1 + 96),
              *(_DWORD *)(*(_QWORD *)(v8 + 16) + 20LL),
              0,
              &v38,
              0,
              a1 + 8,
              0,
              v10 + 72,
              v43);
      if ( !v42 )
      {
        v42 = -1;
        *v43 = 997;
      }
      if ( (BYTE1(xmmword_180063D60) & 0x10) != 0 )
        WPP_SF_qdd(1036, 12, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids, a1, v9, v19);
      if ( v42 != -1 || *v43 == 997 )
      {
        if ( *(_DWORD *)(a1 + 88) )
        {
          SendControlMessage((PVOID)v8, 0, 0);
          if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 88)) == 3 )
            SanOverlappedCompletionAux(a1 + 8, *(unsigned int *)(a1 + 28), *(unsigned int *)(a1 + 16), &v40);
        }
        return v42;
      }
      if ( (xmmword_180063D60 & 2) != 0 )
      {
        WPP_SF_qdd(1025, 13, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids, a1, v9, v19);
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_d(1025, 14, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids, (unsigned int)*v43);
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 48));
      *(_DWORD *)(v10 + 92) &= 0xFFFFFF7D;
      ReleaseWsaBufExArray(v8, a3);
      *(_DWORD *)a1 = 1145324612;
      v35 = *(_QWORD **)(v8 + 776);
      if ( *v35 == v8 + 768 )
      {
        *(_QWORD *)(a1 + 40) = v8 + 768;
        *(_QWORD *)(a1 + 48) = v35;
        *v35 = a1 + 40;
        *(_QWORD *)(v8 + 776) = a1 + 40;
        *(_QWORD *)(v10 + 120) = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 48));
        if ( _InterlockedExchangeAdd(*(volatile signed __int32 **)(v8 + 8), 0xFFFFFFFF) == 1 )
          SockDestroySocket(*(_QWORD *)(v8 + 8), v36, v37);
        return 0xFFFFFFFFLL;
      }
LABEL_45:
      __fastfail(3u);
    }
    v22 = 2LL * v17;
    v23 = v18 + *(_QWORD *)(*(_QWORD *)(v10 + 48) + 8 * v22 + 8);
    v24 = 3LL * (int)v19;
    *(_QWORD *)(a3 + 8 * v24 + 8) = v23;
    v25 = *(_QWORD *)(v10 + 48);
    v39 = v24;
    v26 = *(_DWORD *)(v25 + 8 * v22) - v18;
    v9 += v26;
    *(_DWORD *)(a3 + 8 * v24) = v26;
    if ( v9 > v5 )
    {
      v27 = v26 - v9;
      v9 = v5;
      v26 = v5 + v27;
      *(_DWORD *)(a3 + 24LL * (int)v19) = v26;
    }
    v28 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, int *))(*(_QWORD *)(v8 + 16) + 304LL))(
            *(_QWORD *)(v8 + 104),
            v23,
            v26,
            1,
            &v40);
    v30 = v39;
    *(_QWORD *)(a3 + 8 * v39 + 16) = v28;
    if ( !v28 )
      break;
    v5 = v41;
    ++v19;
    if ( v9 == v41 )
      goto LABEL_31;
    v18 = 0;
    v17 = v42 + 1;
  }
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_qdd(
      1025,
      10,
      WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids,
      *(_QWORD *)(a3 + 8 * v30 + 8),
      *(_DWORD *)(a3 + 8 * v30),
      v40);
  v31 = v43;
  *v43 = v40;
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_qdq(v29, 11, v31, v10, *(_DWORD *)(v10 + 56), v8);
  if ( v19 )
  {
    while ( (--v19 & 0x80000000) == 0 )
      (*(void (__fastcall **)(_QWORD, _QWORD, int *))(*(_QWORD *)(v8 + 16) + 312LL))(
        *(_QWORD *)(v8 + 104),
        *(_QWORD *)(a3 + 24LL * v19 + 16),
        &v40);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 48));
  *(_DWORD *)a1 = 1145324612;
  v32 = *(_QWORD **)(v8 + 776);
  if ( *v32 != v8 + 768 )
    goto LABEL_45;
  *(_QWORD *)(a1 + 40) = v8 + 768;
  *(_QWORD *)(a1 + 48) = v32;
  *v32 = a1 + 40;
  *(_QWORD *)(v8 + 776) = a1 + 40;
  *(_QWORD *)(v10 + 120) = 0;
  ReleaseWsaBufExArray(v8, a3);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 48));
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180050c40  mov     rax, rsp
0x180050c43  mov     [rax+20h], r9
0x180050c47  push    rbx
0x180050c48  push    rsi
0x180050c49  push    rdi
0x180050c4a  push    r12
0x180050c4c  push    r13
0x180050c4e  push    r14
0x180050c50  push    r15
0x180050c52  sub     rsp, 80h
0x180050c59  mov     r12, r8
0x180050c5c  mov     dword ptr [rax-48h], 0
0x180050c63  mov     dword ptr [rax+8], 0
0x180050c6a  mov     r8d, edx
0x180050c6d  mov     rbx, rcx
0x180050c70  test    r12, r12
0x180050c73  jnz     short loc_180050C84
0x180050c75  mov     dword ptr [r9], 2747h
0x180050c7c  or      eax, 0FFFFFFFFh
0x180050c7f  jmp     loc_18005114B
0x180050c84  mov     rsi, [rcx+38h]
0x180050c88  xor     r13d, r13d
0x180050c8b  mov     rdi, [rcx+40h]
0x180050c8f  mov     rax, [rsi+10h]
0x180050c93  mov     ecx, [rax+168h]
0x180050c99  cmp     ecx, r8d
0x180050c9c  cmovb   r8d, ecx
0x180050ca0  xor     r14d, r14d
0x180050ca3  mov     [rsp+0B8h+arg_8], r8d
0x180050cab  cmp     [rdi+38h], r13d
0x180050caf  jle     short loc_180050CD6
0x180050cb1  mov     edx, [rdi+54h]
0x180050cb4  mov     r9, [rdi+30h]
0x180050cb8  mov     eax, r14d
0x180050cbb  shl     rax, 4
0x180050cbf  cmp     [rax+r9], edx
0x180050cc3  ja      loc_180050DBC
0x180050cc9  sub     edx, [rax+r9]
0x180050ccd  inc     r14d
0x180050cd0  cmp     r14d, [rdi+38h]
0x180050cd4  jl      short loc_180050CB8
0x180050cd6  xor     r9d, r9d
0x180050cd9  movsxd  rcx, r14d
0x180050cdc  mov     rax, [rdi+30h]
0x180050ce0  add     rcx, rcx
0x180050ce3  mov     edx, r14d
0x180050ce6  mov     r10d, [rax+rcx*8]
0x180050cea  sub     r10d, r9d
0x180050ced  xor     r15d, r15d
0x180050cf0  mov     ecx, [rdi+38h]
0x180050cf3  mov     eax, 4
0x180050cf8  sub     ecx, r14d
0x180050cfb  mov     [rsp+0B8h+arg_10], edx
0x180050d02  cmp     ecx, eax
0x180050d04  cmovl   eax, ecx
0x180050d07  add     eax, r14d
0x180050d0a  cmp     edx, eax
0x180050d0c  jge     loc_180050ED2
0x180050d12  mov     rax, [rdi+30h]
0x180050d16  mov     ecx, r10d
0x180050d19  movsxd  rdx, edx
0x180050d1c  add     rdx, rdx
0x180050d1f  mov     r11, [rax+rdx*8+8]
0x180050d24  add     r11, rcx
0x180050d27  movsxd  rax, r15d
0x180050d2a  lea     r9, [rax+rax*2]
0x180050d2e  mov     [r12+r9*8+8], r11
0x180050d33  mov     rax, [rdi+30h]
0x180050d37  mov     [rsp+0B8h+var_40], r9
0x180050d3c  mov     ecx, [rax+rdx*8]
0x180050d3f  sub     ecx, r10d
0x180050d42  add     r13d, ecx
0x180050d45  mov     [r12+r9*8], ecx
0x180050d49  cmp     r13d, r8d
0x180050d4c  jbe     short loc_180050D5B
0x180050d4e  sub     ecx, r13d
0x180050d51  mov     r13d, r8d
0x180050d54  add     ecx, r8d
0x180050d57  mov     [r12+r9*8], ecx
0x180050d5b  mov     rax, [rsi+10h]
0x180050d5f  lea     rdx, [rsp+0B8h+arg_0]
0x180050d67  mov     [rsp+0B8h+var_98], rdx
0x180050d6c  mov     r8d, ecx
0x180050d6f  mov     rcx, [rsi+68h]
0x180050d73  mov     r9d, 1
0x180050d79  mov     rdx, r11
0x180050d7c  mov     rax, [rax+130h]
0x180050d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d88  mov     r9, [rsp+0B8h+var_40]
0x180050d8d  mov     [r12+r9*8+10h], rax
0x180050d92  test    rax, rax
0x180050d95  jz      short loc_180050DD1
0x180050d97  mov     r8d, [rsp+0B8h+arg_8]
0x180050d9f  inc     r15d
0x180050da2  cmp     r13d, r8d
0x180050da5  jz      loc_180050ED2
0x180050dab  mov     edx, [rsp+0B8h+arg_10]
0x180050db2  xor     r10d, r10d
0x180050db5  inc     edx
0x180050db7  jmp     loc_180050CF0
0x180050dbc  movsxd  rcx, r14d
0x180050dbf  mov     rax, rcx
0x180050dc2  add     rax, rax
0x180050dc5  mov     r9d, [r9+rax*8]
0x180050dc9  sub     r9d, edx
0x180050dcc  jmp     loc_180050CDC
0x180050dd1  test    byte ptr cs:xmmword_180063D60, 2
0x180050dd8  jz      short loc_180050E08
0x180050dda  mov     eax, [rsp+0B8h+arg_0]
0x180050de1  lea     r8, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids
0x180050de8  mov     dword ptr [rsp+0B8h+var_90], eax
0x180050dec  mov     edx, 0Ah
0x180050df1  mov     eax, [r12+r9*8]
0x180050df5  mov     ecx, 401h
0x180050dfa  mov     r9, [r12+r9*8+8]
0x180050dff  mov     dword ptr [rsp+0B8h+var_98], eax
0x180050e03  call    WPP_SF_qdd
0x180050e08  mov     r8, [rsp+0B8h+arg_18]
0x180050e10  mov     eax, [rsp+0B8h+arg_0]
0x180050e17  mov     [r8], eax
0x180050e1a  test    byte ptr cs:xmmword_180063D60, 2
0x180050e21  jz      short loc_180050E3C
0x180050e23  mov     eax, [rdi+38h]
0x180050e26  mov     edx, 0Bh
0x180050e2b  mov     [rsp+0B8h+var_90], rsi
0x180050e30  mov     r9, rdi
0x180050e33  mov     dword ptr [rsp+0B8h+var_98], eax
0x180050e37  call    WPP_SF_qdq
0x180050e3c  test    r15d, r15d
0x180050e3f  jz      short loc_180050E6E
0x180050e41  jmp     short loc_180050E68
0x180050e43  mov     rcx, [rsi+10h]
0x180050e47  lea     rdx, [r15+r15*2]
0x180050e4b  mov     rdx, [r12+rdx*8+10h]
0x180050e50  lea     r8, [rsp+0B8h+arg_0]
0x180050e58  mov     rax, [rcx+138h]
0x180050e5f  mov     rcx, [rsi+68h]
0x180050e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e68  sub     r15d, 1
0x180050e6c  jns     short loc_180050E43
0x180050e6e  lea     rcx, [rsi+30h]; lpCriticalSection
0x180050e72  call    cs:__imp_EnterCriticalSection
0x180050e79  nop     dword ptr [rax+rax+00h]
0x180050e7e  lea     rdx, [rsi+300h]
0x180050e85  mov     dword ptr [rbx], 44444444h
0x180050e8b  mov     r8, [rdx+8]
0x180050e8f  cmp     [r8], rdx
0x180050e92  jnz     loc_1800510A4
0x180050e98  lea     rax, [rbx+28h]
0x180050e9c  mov     rcx, rsi
0x180050e9f  mov     [rax], rdx
0x180050ea2  mov     [rax+8], r8
0x180050ea6  mov     [r8], rax
0x180050ea9  mov     [rdx+8], rax
0x180050ead  mov     rdx, r12
0x180050eb0  mov     qword ptr [rdi+78h], 0
0x180050eb8  call    ReleaseWsaBufExArray
0x180050ebd  lea     rcx, [rsi+30h]; lpCriticalSection
0x180050ec1  call    cs:__imp_LeaveCriticalSection
0x180050ec8  nop     dword ptr [rax+rax+00h]
0x180050ecd  jmp     loc_180050C7C
0x180050ed2  lea     rcx, [rsi+30h]; lpCriticalSection
0x180050ed6  mov     qword ptr [rbx+20h], 0
0x180050ede  mov     [rbx+48h], r12
0x180050ee2  mov     [rbx+50h], r15d
0x180050ee6  mov     dword ptr [rbx], 44446666h
0x180050eec  call    cs:__imp_EnterCriticalSection
0x180050ef3  nop     dword ptr [rax+rax+00h]
0x180050ef8  mov     eax, [rdi+5Ch]
0x180050efb  add     [rdi+54h], r13d
0x180050eff  and     eax, 0FFFFFFFBh
0x180050f02  or      eax, 82h
0x180050f07  mov     [rdi+5Ch], eax
0x180050f0a  mov     eax, [rdi+54h]
0x180050f0d  cmp     eax, [rdi+50h]
0x180050f10  jz      short loc_180050F20
0x180050f12  cmp     r13d, [rsp+0B8h+arg_8]
0x180050f1a  jz      short loc_180050F20
0x180050f1c  xor     eax, eax
0x180050f1e  jmp     short loc_180050F25
0x180050f20  mov     eax, 1
0x180050f25  lea     rcx, [rsi+30h]; lpCriticalSection
0x180050f29  mov     [rbx+58h], eax
0x180050f2c  call    cs:__imp_LeaveCriticalSection
0x180050f33  nop     dword ptr [rax+rax+00h]
0x180050f38  mov     rax, [rsi+8]
0x180050f3c  lock inc dword ptr [rax]
0x180050f3f  mov     rdx, [rsi+10h]
0x180050f43  lea     rcx, [rdi+48h]
0x180050f47  mov     r8, [rsp+0B8h+arg_18]
0x180050f4f  lea     r9, [rbx+8]
0x180050f53  mov     [rsp+0B8h+var_60], r8
0x180050f58  xor     r8d, r8d
0x180050f5b  mov     [rsp+0B8h+var_68], rcx
0x180050f60  lea     rcx, [rsp+0B8h+var_48]
0x180050f65  mov     rax, [rdx+150h]
0x180050f6c  mov     [rsp+0B8h+var_70], r8
0x180050f71  mov     [rsp+0B8h+var_78], r9
0x180050f76  mov     r9, [rbx+60h]
0x180050f7a  mov     [rsp+0B8h+var_80], r8d
0x180050f7f  mov     [rsp+0B8h+var_88], rcx
0x180050f84  mov     ecx, [rdx+14h]
0x180050f87  mov     rdx, r12
0x180050f8a  mov     dword ptr [rsp+0B8h+var_90], r8d
0x180050f8f  mov     r8d, r15d
0x180050f92  mov     dword ptr [rsp+0B8h+var_98], ecx
0x180050f96  mov     rcx, [rsi+68h]
0x180050f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f9f  or      r14d, 0FFFFFFFFh
0x180050fa3  mov     [rsp+0B8h+arg_10], eax
0x180050faa  test    eax, eax
0x180050fac  jnz     short loc_180050FC4
0x180050fae  mov     rax, [rsp+0B8h+arg_18]
0x180050fb6  mov     [rsp+0B8h+arg_10], r14d
0x180050fbe  mov     dword ptr [rax], 3E5h
0x180050fc4  test    byte ptr cs:xmmword_180063D60+1, 10h
0x180050fcb  jz      short loc_180050FF0
0x180050fcd  mov     edx, 0Ch
0x180050fd2  mov     dword ptr [rsp+0B8h+var_90], r15d
0x180050fd7  mov     ecx, 40Ch
0x180050fdc  mov     dword ptr [rsp+0B8h+var_98], r13d
0x180050fe1  mov     r9, rbx
0x180050fe4  lea     r8, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids
0x180050feb  call    WPP_SF_qdd
0x180050ff0  cmp     [rsp+0B8h+arg_10], r14d
0x180050ff8  jnz     loc_1800510F3
0x180050ffe  mov     rax, [rsp+0B8h+arg_18]
0x180051006  cmp     dword ptr [rax], 3E5h
0x18005100c  jz      loc_1800510F3
0x180051012  mov     cl, byte ptr cs:xmmword_180063D60
0x180051018  test    cl, 2
0x18005101b  jz      short loc_18005106C
0x18005101d  mov     edx, 0Dh
0x180051022  mov     dword ptr [rsp+0B8h+var_90], r15d
0x180051027  mov     ecx, 401h
0x18005102c  mov     dword ptr [rsp+0B8h+var_98], r13d
0x180051031  mov     r9, rbx
0x180051034  lea     r8, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids
0x18005103b  call    WPP_SF_qdd
0x180051040  mov     cl, byte ptr cs:xmmword_180063D60
0x180051046  mov     rax, [rsp+0B8h+arg_18]
0x18005104e  test    cl, 2
0x180051051  jz      short loc_18005106C
0x180051053  mov     r9d, [rax]
0x180051056  lea     r8, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids
0x18005105d  mov     edx, 0Eh
0x180051062  mov     ecx, 401h
0x180051067  call    WPP_SF_d
0x18005106c  lea     rcx, [rsi+30h]; lpCriticalSection
0x180051070  call    cs:__imp_EnterCriticalSection
0x180051077  nop     dword ptr [rax+rax+00h]
0x18005107c  and     dword ptr [rdi+5Ch], 0FFFFFF7Dh
0x180051083  mov     rdx, r12
0x180051086  mov     rcx, rsi
0x180051089  call    ReleaseWsaBufExArray
0x18005108e  lea     rcx, [rsi+300h]
0x180051095  mov     dword ptr [rbx], 44444444h
0x18005109b  mov     rdx, [rcx+8]
0x18005109f  cmp     [rdx], rcx
0x1800510a2  jz      short loc_1800510AB
0x1800510a4  mov     ecx, 3
0x1800510a9  int     29h; Win8: RtlFailFast(ecx)
0x1800510ab  lea     rax, [rbx+28h]
0x1800510af  mov     [rax], rcx
0x1800510b2  mov     [rax+8], rdx
0x1800510b6  mov     [rdx], rax
0x1800510b9  mov     [rcx+8], rax
0x1800510bd  lea     rcx, [rsi+30h]; lpCriticalSection
0x1800510c1  mov     qword ptr [rdi+78h], 0
0x1800510c9  call    cs:__imp_LeaveCriticalSection
0x1800510d0  nop     dword ptr [rax+rax+00h]
0x1800510d5  mov     rax, [rsi+8]
0x1800510d9  mov     ecx, r14d
0x1800510dc  lock xadd [rax], ecx
0x1800510e0  add     ecx, r14d
0x1800510e3  jnz     short loc_1800510EE
0x1800510e5  mov     rcx, [rsi+8]
0x1800510e9  call    SockDestroySocket
0x1800510ee  mov     eax, r14d
0x1800510f1  jmp     short loc_18005114B
0x1800510f3  cmp     dword ptr [rbx+58h], 0
0x1800510f7  jz      short loc_180051144
0x1800510f9  mov     r8d, r13d
0x1800510fc  xor     r9d, r9d
0x1800510ff  mov     [rsp+0B8h+var_90], 0
0x180051108  mov     dl, 5
0x18005110a  mov     rcx, rsi
0x18005110d  mov     [rsp+0B8h+var_98], 0
0x180051116  call    SendControlMessage
0x18005111b  mov     eax, 1
0x180051120  lock xadd [rbx+58h], eax
0x180051125  inc     eax
0x180051127  cmp     eax, 3
0x18005112a  jnz     short loc_180051144
0x18005112c  mov     r8d, [rbx+10h]
0x180051130  lea     r9, [rsp+0B8h+arg_0]
0x180051138  mov     edx, [rbx+1Ch]
0x18005113b  lea     rcx, [rbx+8]
0x18005113f  call    SanOverlappedCompletionAux
0x180051144  mov     eax, [rsp+0B8h+arg_10]
  ... truncated ...
```
