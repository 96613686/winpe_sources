# SendLargeSendFirstMsg

- ea: `0x180050074`
- end: `0x18005053b`
- name: `SendLargeSendFirstMsg`
- size: `1223`
- prototype: `__int64 __fastcall(PVOID CompletionContext)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180045e74`
- `0x180049310`
- `0x18004b1d0`

## callees

- `0x180008250`
- `0x180022bd2`
- `0x1800289a0`
- `0x180038944`
- `0x18003ae8c`
- `0x18003dae8`
- `0x18003ff84`
- `0x1800462b0`
- `0x180050074`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050125`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800501aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800502fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800503d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005049d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050508`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050125`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800501aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800502fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800503d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005049d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050508`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800500bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050185`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800503c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050425`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800500bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050185`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800503c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050425`

## pseudocode

```c
__int64 __fastcall SendLargeSendFirstMsg(char *CompletionContext, __int64 a2, __int64 a3, unsigned int *a4)
{
  unsigned int v4; // r12d
  struct _RTL_CRITICAL_SECTION *v9; // r14
  int v10; // eax
  int v11; // ecx
  bool v12; // zf
  unsigned int v13; // eax
  int v14; // eax
  __int64 *v15; // rdx
  int v16; // r9d
  int v17; // ecx
  unsigned int v18; // r8d
  __int64 v19; // r12
  __int64 v20; // rax
  __int64 v21; // r9
  __int64 v22; // r9
  unsigned int v23; // eax
  int v24; // ecx
  __int64 *v25; // r12
  __int64 v26; // rdx
  __int64 v27; // r8
  bool v28; // cf
  __int64 result; // rax
  unsigned int v30; // eax
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r8
  unsigned int v36; // eax
  char *v37; // rdi
  char **v38; // rcx
  char *v39; // rdi
  char **v40; // rcx
  _BYTE v41[4]; // [rsp+40h] [rbp-29h] BYREF
  int v42; // [rsp+44h] [rbp-25h]
  char v43; // [rsp+58h] [rbp-11h]
  __int64 v44; // [rsp+60h] [rbp-9h]
  __int64 v45; // [rsp+68h] [rbp-1h]
  __int64 v46; // [rsp+D0h] [rbp+67h] BYREF
  int v47; // [rsp+D8h] [rbp+6Fh] BYREF

  v4 = 0;
  LODWORD(v46) = 0;
  v42 = 0;
  memset_0(v41, 0, 0x44u);
  v9 = (struct _RTL_CRITICAL_SECTION *)(CompletionContext + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  *((_DWORD *)CompletionContext + 63) = 1;
  if ( (*(_BYTE *)(a2 + 92) & 4) != 0 || *(_DWORD *)(a2 + 84) >= *(_DWORD *)(a2 + 80) || *(_DWORD *)(a2 + 36) )
  {
    if ( a3 )
    {
      v39 = CompletionContext + 768;
      *(_DWORD *)a3 = 1145324612;
      v40 = (char **)*((_QWORD *)v39 + 1);
      if ( *v40 != v39 )
        goto LABEL_55;
      *(_QWORD *)(a3 + 40) = v39;
      *(_QWORD *)(a3 + 48) = v40;
      *v40 = (char *)(a3 + 40);
      *((_QWORD *)v39 + 1) = a3 + 40;
    }
    LeaveCriticalSection(v9);
    result = 0xFFFFFFFFLL;
    *a4 = 997;
    return result;
  }
  *((_DWORD *)CompletionContext + 63) = 0;
  *(_DWORD *)(a2 + 92) |= 6u;
  v10 = *(_DWORD *)(a2 + 92);
  if ( (CompletionContext[801] & 8) != 0 )
    v10 |= 0x80u;
  *(_BYTE *)(a2 + 130) = 0;
  *(_DWORD *)(a2 + 92) = v10 & 0xFFFFF3FF | 0x800;
  LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  v11 = 1008;
  v12 = (CompletionContext[801] & 8) == 0;
  v47 = 1008;
  if ( v12 )
  {
    v30 = *(_DWORD *)(a2 + 80) - *(_DWORD *)(a2 + 84) - 1008;
    v45 = 0;
    v44 = v30;
    goto LABEL_37;
  }
  _InterlockedIncrement(*((volatile signed __int32 **)CompletionContext + 1));
  if ( *((_DWORD *)CompletionContext + 117) == 2 )
  {
    v47 = 0;
    *(_DWORD *)(a2 + 112) = 1;
LABEL_13:
    *(_QWORD *)(a3 + 56) = CompletionContext;
    *(_QWORD *)(a3 + 64) = a2;
    if ( !*((_DWORD *)CompletionContext + 8) || (v14 = 1, !*(_QWORD *)(a2 + 8)) )
      v14 = 0;
    *(_DWORD *)(a3 + 84) = v14;
    v15 = (__int64 *)(a2 + 48);
    v16 = *(_DWORD *)(a2 + 56);
    v17 = 0;
    if ( v16 > 0 )
    {
      v18 = *(_DWORD *)(a2 + 84);
      v19 = *v15;
      do
      {
        v20 = 16LL * (unsigned int)v17;
        if ( *(_DWORD *)(v20 + v19) > v18 )
          break;
        v18 -= *(_DWORD *)(v20 + v19);
        ++v17;
      }
      while ( v17 < v16 );
      if ( v17 < v16 )
      {
        v21 = v17;
        v4 = *(_DWORD *)(v19 + 16LL * v17) - v18;
        goto LABEL_24;
      }
      v4 = 0;
    }
    v21 = v17;
LABEL_24:
    if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _QWORD, __int64, unsigned int *))(*((_QWORD *)CompletionContext + 2) + 320LL))(
           *((_QWORD *)CompletionContext + 13),
           *(_QWORD *)(16 * v21 + *v15 + 8) + *(_DWORD *)(16 * v21 + *v15) - v4,
           v4,
           1,
           *(_QWORD *)(a3 + 96),
           *((_QWORD *)CompletionContext + 2) + 20LL,
           a4) == -1 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_dd(1025, 32, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids, 0xFFFFFFFFLL, *a4);
      goto LABEL_44;
    }
    v11 = v47;
    v22 = *(_QWORD *)(a3 + 96);
    *(_DWORD *)(a3 + 80) = v4 - v47;
    *(_QWORD *)(a2 + 120) = a3;
    v44 = v4;
    v45 = v22;
    if ( !v11 )
    {
      v23 = SendControlMessage(CompletionContext, 0, 0);
      v24 = 40;
      v25 = (__int64 *)(a3 + 96);
      LODWORD(v46) = 40;
LABEL_38:
      *a4 = v23;
      if ( !v23 )
      {
        if ( v24 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
          *(_DWORD *)(a2 + 92) &= ~0x800u;
          LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
          return 0;
        }
        *a4 = 997;
      }
      if ( (CompletionContext[801] & 8) != 0 )
      {
        v31 = *((_QWORD *)CompletionContext + 2);
        v32 = *v25;
        v33 = *((_QWORD *)CompletionContext + 13);
        v47 = 0;
        (*(void (__fastcall **)(__int64, __int64, _QWORD, int *))(v31 + 328))(
          v33,
          v32,
          *(unsigned int *)(v31 + 20),
          &v47);
      }
      goto LABEL_44;
    }
LABEL_37:
    v43 = 4;
    v25 = (__int64 *)(a3 + 96);
    v23 = SendUsingSmallMsg(CompletionContext, a2, v11, (__int64)v41, &v46);
    v24 = v46;
    goto LABEL_38;
  }
  *(_DWORD *)(a2 + 112) = 0;
  v13 = SendNonRdmaBuffers(CompletionContext);
  *a4 = v13;
  if ( v13 )
  {
LABEL_44:
    EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
    v36 = *(_DWORD *)(a2 + 92) & 0xFFFFF3D8 | 0x400;
    *(_DWORD *)(a2 + 92) = v36;
    if ( (CompletionContext[801] & 8) != 0 )
    {
      *(_DWORD *)(a2 + 92) = v36 & 0xFFFFFF7F;
      if ( _InterlockedExchangeAdd(*((volatile signed __int32 **)CompletionContext + 1), 0xFFFFFFFF) == 1 )
        SockDestroySocket(*((_QWORD *)CompletionContext + 1), v34, v35);
    }
    if ( !a3 )
      goto LABEL_50;
    v37 = CompletionContext + 768;
    *(_DWORD *)a3 = 1145324612;
    v38 = (char **)*((_QWORD *)v37 + 1);
    if ( *v38 == v37 )
    {
      *(_QWORD *)(a3 + 40) = v37;
      *(_QWORD *)(a3 + 48) = v38;
      *v38 = (char *)(a3 + 40);
      *((_QWORD *)v37 + 1) = a3 + 40;
      *(_QWORD *)(a2 + 120) = 0;
LABEL_50:
      LeaveCriticalSection(v9);
      if ( (BYTE1(xmmword_180063D60) & 0x10) != 0 )
        WPP_SF_d(1036, 33, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids, *a4);
      return 0xFFFFFFFFLL;
    }
LABEL_55:
    __fastfail(3u);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  if ( *(_DWORD *)(a2 + 84) < *(_DWORD *)(a2 + 80) && !*(_DWORD *)(a2 + 36) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
    goto LABEL_13;
  }
  *(_DWORD *)(a2 + 92) &= 0xFFFFF779;
  LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  if ( !*(_DWORD *)(a2 + 36) && !*(_BYTE *)(a2 + 129) && (*(_BYTE *)(a2 + 92) & 8) == 0 )
    CompleteOverlappedIO(
      *(_QWORD *)(*(_QWORD *)CompletionContext + 8LL),
      *(_QWORD *)(a2 + 8),
      *(void **)(a2 + 64),
      *(void **)(a2 + 72),
      0,
      *(_DWORD *)(a2 + 80));
  if ( _InterlockedExchangeAdd(*((volatile signed __int32 **)CompletionContext + 1), 0xFFFFFFFF) == 1 )
    SockDestroySocket(*((_QWORD *)CompletionContext + 1), v26, v27);
  v28 = *(_DWORD *)(a2 + 36) != 0;
  *a4 = v28 ? 0x3E5 : 0;
  return (unsigned int)-v28;
}

```

## disassembly

```asm
0x180050074  mov     [rsp-8+arg_10], rbx
0x180050079  push    rbp
0x18005007a  push    rsi
0x18005007b  push    rdi
0x18005007c  push    r12
0x18005007e  push    r13
0x180050080  push    r14
0x180050082  push    r15
0x180050084  lea     rbp, [rsp-27h]
0x180050089  sub     rsp, 90h
0x180050090  xor     r12d, r12d
0x180050093  mov     rsi, r8
0x180050096  mov     rbx, rdx
0x180050099  mov     dword ptr [rbp+57h+arg_0], r12d
0x18005009d  mov     rdi, rcx
0x1800500a0  xor     eax, eax
0x1800500a2  xor     edx, edx; Val
0x1800500a4  mov     [rbp+57h+var_7C], eax
0x1800500a7  lea     r8d, [r12+44h]; Size
0x1800500ac  mov     r13, r9
0x1800500af  lea     rcx, [rbp+57h+var_80]; void *
0x1800500b3  call    memset_0
0x1800500b8  lea     r14, [rdi+30h]
0x1800500bc  mov     rcx, r14; lpCriticalSection
0x1800500bf  call    cs:__imp_EnterCriticalSection
0x1800500c6  nop     dword ptr [rax+rax+00h]
0x1800500cb  mov     dword ptr [rdi+0FCh], 1
0x1800500d5  test    byte ptr [rbx+5Ch], 4
0x1800500d9  jnz     loc_1800504D1
0x1800500df  mov     eax, [rbx+50h]
0x1800500e2  cmp     [rbx+54h], eax
0x1800500e5  jge     loc_1800504D1
0x1800500eb  cmp     [rbx+24h], r12d
0x1800500ef  jnz     loc_1800504D1
0x1800500f5  mov     [rdi+0FCh], r12d
0x1800500fc  or      dword ptr [rbx+5Ch], 6
0x180050100  test    byte ptr [rdi+321h], 8
0x180050107  mov     eax, [rbx+5Ch]
0x18005010a  jz      short loc_180050110
0x18005010c  bts     eax, 7
0x180050110  btr     eax, 0Ah
0x180050114  mov     [rbx+82h], r12b
0x18005011b  bts     eax, 0Bh
0x18005011f  mov     rcx, r14; lpCriticalSection
0x180050122  mov     [rbx+5Ch], eax
0x180050125  call    cs:__imp_LeaveCriticalSection
0x18005012c  nop     dword ptr [rax+rax+00h]
0x180050131  or      r15d, 0FFFFFFFFh
0x180050135  mov     ecx, 3F0h
0x18005013a  test    byte ptr [rdi+321h], 8
0x180050141  mov     [rbp+57h+arg_8], ecx
0x180050144  jz      loc_180050375
0x18005014a  mov     rax, [rdi+8]
0x18005014e  lock inc dword ptr [rax]
0x180050151  cmp     dword ptr [rdi+1D4h], 2
0x180050158  jnz     short loc_180050167
0x18005015a  mov     [rbp+57h+arg_8], r12d
0x18005015e  mov     dword ptr [rbx+70h], 1
0x180050165  jmp     short loc_1800501B6
0x180050167  mov     rdx, rbx
0x18005016a  mov     [rbx+70h], r12d
0x18005016e  mov     rcx, rdi
0x180050171  call    SendNonRdmaBuffers
0x180050176  mov     [r13+0], eax
0x18005017a  test    eax, eax
0x18005017c  jnz     loc_180050422
0x180050182  mov     rcx, r14; lpCriticalSection
0x180050185  call    cs:__imp_EnterCriticalSection
0x18005018c  nop     dword ptr [rax+rax+00h]
0x180050191  mov     eax, [rbx+50h]
0x180050194  cmp     [rbx+54h], eax
0x180050197  jge     loc_1800502F1
0x18005019d  cmp     [rbx+24h], r12d
0x1800501a1  jnz     loc_1800502F1
0x1800501a7  mov     rcx, r14; lpCriticalSection
0x1800501aa  call    cs:__imp_LeaveCriticalSection
0x1800501b1  nop     dword ptr [rax+rax+00h]
0x1800501b6  mov     [rsi+38h], rdi
0x1800501ba  mov     [rsi+40h], rbx
0x1800501be  cmp     [rdi+20h], r12d
0x1800501c2  jz      short loc_1800501CF
0x1800501c4  mov     eax, 1
0x1800501c9  cmp     [rbx+8], r12
0x1800501cd  jnz     short loc_1800501D2
0x1800501cf  mov     eax, r12d
0x1800501d2  mov     [rsi+54h], eax
0x1800501d5  lea     rdx, [rbx+30h]
0x1800501d9  mov     r9d, [rbx+38h]
0x1800501dd  mov     ecx, r12d
0x1800501e0  test    r9d, r9d
0x1800501e3  jle     short loc_18005021D
0x1800501e5  mov     r8d, [rbx+54h]
0x1800501e9  mov     r12, [rdx]
0x1800501ec  mov     eax, ecx
0x1800501ee  shl     rax, 4
0x1800501f2  cmp     [rax+r12], r8d
0x1800501f6  ja      short loc_180050203
0x1800501f8  sub     r8d, [rax+r12]
0x1800501fc  inc     ecx
0x1800501fe  cmp     ecx, r9d
0x180050201  jl      short loc_1800501EC
0x180050203  cmp     ecx, r9d
0x180050206  jge     short loc_18005021A
0x180050208  movsxd  r9, ecx
0x18005020b  mov     rax, r9
0x18005020e  add     rax, rax
0x180050211  mov     r12d, [r12+rax*8]
0x180050215  sub     r12d, r8d
0x180050218  jmp     short loc_180050220
0x18005021a  xor     r12d, r12d
0x18005021d  movsxd  r9, ecx
0x180050220  mov     rcx, [rdx]
0x180050223  mov     r10, [rdi+10h]
0x180050227  mov     rax, [rsi+60h]
0x18005022b  shl     r9, 4
0x18005022f  mov     [rsp+0C0h+var_90], r13
0x180050234  lea     r8, [r10+14h]
0x180050238  mov     [rsp+0C0h+var_98], r8
0x18005023d  mov     r8d, r12d
0x180050240  mov     edx, [r9+rcx]
0x180050244  sub     edx, r12d
0x180050247  mov     [rsp+0C0h+var_A0], rax
0x18005024c  add     rdx, [r9+rcx+8]
0x180050251  mov     r9d, 1
0x180050257  mov     rcx, [rdi+68h]
0x18005025b  mov     rax, [r10+140h]
0x180050262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050267  cmp     eax, r15d
0x18005026a  jnz     short loc_18005029F
0x18005026c  test    byte ptr cs:xmmword_180063D60, 2
0x180050273  jz      loc_18005041F
0x180050279  mov     eax, [r13+0]
0x18005027d  lea     r8, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids
0x180050284  mov     edx, 20h ; ' '
0x180050289  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18005028d  mov     ecx, 401h
0x180050292  mov     r9d, r15d
0x180050295  call    WPP_SF_dd
0x18005029a  jmp     loc_18005041F
0x18005029f  mov     ecx, [rbp+57h+arg_8]
0x1800502a2  mov     r9, [rsi+60h]
0x1800502a6  mov     r8d, r12d
0x1800502a9  sub     r12d, ecx
0x1800502ac  mov     [rsi+50h], r12d
0x1800502b0  mov     [rbx+78h], rsi
0x1800502b4  mov     [rbp+57h+var_60], r8
0x1800502b8  mov     [rbp+57h+var_58], r9
0x1800502bc  test    ecx, ecx
0x1800502be  jnz     loc_180050385
0x1800502c4  mov     [rsp+0C0h+var_98], 0
0x1800502cd  mov     dl, 4
0x1800502cf  mov     rcx, rdi
0x1800502d2  mov     [rsp+0C0h+var_A0], 0
0x1800502db  call    SendControlMessage
0x1800502e0  mov     ecx, 28h ; '('
0x1800502e5  lea     r12, [rsi+60h]
0x1800502e9  mov     dword ptr [rbp+57h+arg_0], ecx
0x1800502ec  jmp     loc_1800503AB
0x1800502f1  and     dword ptr [rbx+5Ch], 0FFFFF779h
0x1800502f8  mov     rcx, r14; lpCriticalSection
0x1800502fb  call    cs:__imp_LeaveCriticalSection
0x180050302  nop     dword ptr [rax+rax+00h]
0x180050307  cmp     [rbx+24h], r12d
0x18005030b  jnz     short loc_180050340
0x18005030d  cmp     [rbx+81h], r12b
0x180050314  jnz     short loc_180050340
0x180050316  test    byte ptr [rbx+5Ch], 8
0x18005031a  jnz     short loc_180050340
0x18005031c  mov     rcx, [rdi]
0x18005031f  mov     eax, [rbx+50h]
0x180050322  mov     r9, [rbx+48h]
0x180050326  mov     r8, [rbx+40h]
0x18005032a  mov     rcx, [rcx+8]
0x18005032e  mov     rdx, [rbx+8]
0x180050332  mov     dword ptr [rsp+0C0h+var_98], eax
0x180050336  mov     dword ptr [rsp+0C0h+var_A0], r12d
0x18005033b  call    CompleteOverlappedIO
0x180050340  mov     rax, [rdi+8]
0x180050344  mov     ecx, r15d
0x180050347  lock xadd [rax], ecx
0x18005034b  add     ecx, r15d
0x18005034e  jnz     short loc_180050359
0x180050350  mov     rcx, [rdi+8]
0x180050354  call    SockDestroySocket
0x180050359  mov     edx, [rbx+24h]
0x18005035c  mov     eax, edx
0x18005035e  neg     eax
0x180050360  sbb     ecx, ecx
0x180050362  and     ecx, 3E5h
0x180050368  neg     edx
0x18005036a  mov     [r13+0], ecx
0x18005036e  sbb     eax, eax
0x180050370  jmp     loc_18005051F
0x180050375  mov     eax, [rbx+50h]
0x180050378  sub     eax, [rbx+54h]
0x18005037b  sub     eax, ecx
0x18005037d  mov     [rbp+57h+var_58], r12
0x180050381  mov     [rbp+57h+var_60], rax
0x180050385  lea     rax, [rbp+57h+arg_0]
0x180050389  mov     [rbp+57h+var_68], 4
0x18005038d  mov     r8d, ecx
0x180050390  mov     [rsp+0C0h+var_A0], rax; __int64
0x180050395  mov     rcx, rdi; CompletionContext
0x180050398  lea     r9, [rbp+57h+var_80]
0x18005039c  mov     rdx, rbx
0x18005039f  lea     r12, [rsi+60h]
0x1800503a3  call    SendUsingSmallMsg
0x1800503a8  mov     ecx, dword ptr [rbp+57h+arg_0]
0x1800503ab  mov     [r13+0], eax
0x1800503af  lea     r10, [rdi+68h]
0x1800503b3  lea     rdx, [rdi+10h]
0x1800503b7  test    eax, eax
0x1800503b9  jnz     short loc_1800503F1
0x1800503bb  test    ecx, ecx
0x1800503bd  jz      short loc_1800503E9
0x1800503bf  mov     rcx, r14; lpCriticalSection
0x1800503c2  call    cs:__imp_EnterCriticalSection
0x1800503c9  nop     dword ptr [rax+rax+00h]
0x1800503ce  btr     dword ptr [rbx+5Ch], 0Bh
0x1800503d3  mov     rcx, r14; lpCriticalSection
0x1800503d6  call    cs:__imp_LeaveCriticalSection
0x1800503dd  nop     dword ptr [rax+rax+00h]
0x1800503e2  xor     eax, eax
0x1800503e4  jmp     loc_18005051F
0x1800503e9  mov     dword ptr [r13+0], 3E5h
0x1800503f1  test    byte ptr [rdi+321h], 8
0x1800503f8  jz      short loc_18005041F
0x1800503fa  mov     r8, [rdx]
0x1800503fd  lea     r9, [rbp+57h+arg_8]
0x180050401  mov     rdx, [r12]
0x180050405  mov     rcx, [r10]
0x180050408  mov     [rbp+57h+arg_8], 0
0x18005040f  mov     rax, [r8+148h]
0x180050416  mov     r8d, [r8+14h]
0x18005041a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005041f  xor     r12d, r12d
0x180050422  mov     rcx, r14; lpCriticalSection
0x180050425  call    cs:__imp_EnterCriticalSection
0x18005042c  nop     dword ptr [rax+rax+00h]
0x180050431  mov     eax, [rbx+5Ch]
0x180050434  and     eax, 0FFFFF7D8h
0x180050439  bts     eax, 0Ah
0x18005043d  mov     [rbx+5Ch], eax
0x180050440  test    byte ptr [rdi+321h], 8
0x180050447  jz      short loc_180050469
0x180050449  btr     eax, 7
0x18005044d  mov     ecx, r15d
0x180050450  mov     [rbx+5Ch], eax
0x180050453  mov     rax, [rdi+8]
0x180050457  lock xadd [rax], ecx
0x18005045b  add     ecx, r15d
0x18005045e  jnz     short loc_180050469
0x180050460  mov     rcx, [rdi+8]
0x180050464  call    SockDestroySocket
0x180050469  test    rsi, rsi
0x18005046c  jz      short loc_18005049A
0x18005046e  add     rdi, 300h
0x180050475  mov     dword ptr [rsi], 44444444h
0x18005047b  mov     rcx, [rdi+8]
0x18005047f  cmp     [rcx], rdi
0x180050482  jnz     short loc_1800504EC
0x180050484  lea     rax, [rsi+28h]
0x180050488  mov     [rax], rdi
0x18005048b  mov     [rax+8], rcx
0x18005048f  mov     [rcx], rax
0x180050492  mov     [rdi+8], rax
0x180050496  mov     [rbx+78h], r12
0x18005049a  mov     rcx, r14; lpCriticalSection
0x18005049d  call    cs:__imp_LeaveCriticalSection
0x1800504a4  nop     dword ptr [rax+rax+00h]
0x1800504a9  test    byte ptr cs:xmmword_180063D60+1, 10h
0x1800504b0  jz      short loc_1800504CC
0x1800504b2  mov     r9d, [r13+0]
0x1800504b6  lea     r8, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids
0x1800504bd  mov     edx, 21h ; '!'
0x1800504c2  mov     ecx, 40Ch
0x1800504c7  call    WPP_SF_d
0x1800504cc  mov     eax, r15d
0x1800504cf  jmp     short loc_18005051F
0x1800504d1  test    rsi, rsi
0x1800504d4  jz      short loc_180050505
0x1800504d6  add     rdi, 300h
0x1800504dd  mov     dword ptr [rsi], 44444444h
0x1800504e3  mov     rcx, [rdi+8]
0x1800504e7  cmp     [rcx], rdi
0x1800504ea  jz      short loc_1800504F3
0x1800504ec  mov     ecx, 3
0x1800504f1  int     29h; Win8: RtlFailFast(ecx)
0x1800504f3  lea     rax, [rsi+28h]
0x1800504f7  mov     [rax], rdi
0x1800504fa  mov     [rax+8], rcx
0x1800504fe  mov     [rcx], rax
0x180050501  mov     [rdi+8], rax
0x180050505  mov     rcx, r14; lpCriticalSection
0x180050508  call    cs:__imp_LeaveCriticalSection
0x18005050f  nop     dword ptr [rax+rax+00h]
0x180050514  or      eax, 0FFFFFFFFh
0x180050517  mov     dword ptr [r13+0], 3E5h
0x18005051f  mov     rbx, [rsp+0C0h+arg_10]
0x180050527  add     rsp, 90h
  ... truncated ...
```
