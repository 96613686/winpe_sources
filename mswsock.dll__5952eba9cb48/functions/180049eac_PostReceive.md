# PostReceive

- ea: `0x180049eac`
- end: `0x18004a282`
- name: `PostReceive`
- size: `982`
- prototype: `__int64 __fastcall(PVOID CompletionContext)`
- caller_count: `4`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003b760`
- `0x18003e1e0`
- `0x1800497d4`
- `0x180049b2c`

## callees

- `0x180008250`
- `0x180038118`
- `0x180038a20`
- `0x18003b054`
- `0x1800466a8`
- `0x18004958c`
- `0x180049eac`
- `0x18004c4b8`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049f38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049fa8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a0d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a183`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a23e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049f38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049fa8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a0d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a183`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a23e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049ee9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049f74`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a0a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a162`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a217`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049ee9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049f74`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a0a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a162`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a217`

## pseudocode

```c
__int64 __fastcall PostReceive(char *CompletionContext, __int64 a2, unsigned int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r14
  __int64 v6; // rdi
  PVOID *v7; // rdx
  char v8; // r15
  signed __int32 v9; // esi
  char v11; // r13
  __int64 v12; // rdx
  _QWORD *v13; // rcx
  _QWORD *v14; // rsi
  volatile signed __int32 *v15; // rax
  int v16; // eax
  bool v17; // zf
  int v18; // eax
  __int64 v19; // rdx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  volatile signed __int32 *v23; // rcx
  __int64 v24; // r15
  int v25; // eax
  __int64 v26; // rdi
  __int64 v27; // [rsp+58h] [rbp-18h] BYREF
  __int64 v28; // [rsp+60h] [rbp-10h]
  unsigned int v29; // [rsp+B0h] [rbp+40h] BYREF
  int v30; // [rsp+B8h] [rbp+48h] BYREF
  int v31; // [rsp+C8h] [rbp+58h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)(CompletionContext + 48);
  LODWORD(v28) = 0;
  v27 = 0;
  v31 = 0;
  v6 = a2;
  v30 = 0;
  v29 = 0;
  *(_BYTE *)(a2 + 85) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  v7 = (PVOID *)*((_QWORD *)CompletionContext + 39);
  if ( *v7 != CompletionContext + 304 )
LABEL_55:
    __fastfail(3u);
  v8 = 1;
  *(_QWORD *)(v6 + 40) = CompletionContext + 304;
  *(_QWORD *)(v6 + 48) = v7;
  *v7 = (PVOID)(v6 + 40);
  *((_QWORD *)CompletionContext + 39) = v6 + 40;
  v9 = _InterlockedIncrement((volatile signed __int32 *)CompletionContext + 9);
  if ( v9 != 1 )
    *(_DWORD *)(v6 + 80) = a3;
  LeaveCriticalSection(v3);
  if ( v9 != 1 )
    return 0;
  v11 = 0;
  while ( 1 )
  {
    if ( !*(_BYTE *)(v6 + 72) )
    {
      v15 = (volatile signed __int32 *)*((_QWORD *)CompletionContext + 1);
      if ( v15 )
        _InterlockedAdd(v15, 1u);
      v16 = *(unsigned __int16 *)(v6 + 74);
      v14 = CompletionContext + 104;
      *(_DWORD *)(v6 + 80) = 0;
      v17 = *((_QWORD *)CompletionContext + 13) == -1;
      LODWORD(v27) = v16;
      v28 = *(_QWORD *)(v6 + 96);
      if ( v17 || (CompletionContext[800] & 0x40) != 0 )
      {
        v18 = 10038;
        v29 = 10038;
      }
      else
      {
        v8 = 0;
        if ( (*(unsigned int (__fastcall **)(_QWORD, __int64 *, __int64, int *, int *, __int64, _QWORD, _QWORD, unsigned int *))(*((_QWORD *)CompletionContext + 2) + 216LL))(
               *v14,
               &v27,
               1,
               &v31,
               &v30,
               v6 + 8,
               0,
               0,
               &v29) != -1 )
          goto LABEL_38;
        v18 = v29;
      }
      if ( v18 != 997 )
      {
        EnterCriticalSection(v3);
        v19 = *(_QWORD *)(v6 + 40);
        if ( *(_QWORD *)(v19 + 8) != v6 + 40 )
          goto LABEL_55;
        v20 = *(_QWORD **)(v6 + 48);
        if ( *v20 != v6 + 40 )
          goto LABEL_55;
        *v20 = v19;
        *(_QWORD *)(v19 + 8) = v20;
        LeaveCriticalSection(v3);
        v23 = (volatile signed __int32 *)*((_QWORD *)CompletionContext + 1);
        if ( v23 && _InterlockedExchangeAdd(v23, 0xFFFFFFFF) == 1 )
          SockDestroySocket(*((_QWORD *)CompletionContext + 1), v21, v22);
        if ( v29 == 10054 || v29 == 10057 )
        {
          if ( !*((_DWORD *)CompletionContext + 34) && !*((_DWORD *)CompletionContext + 112) )
          {
            HandleRemoteClose(CompletionContext);
            v8 = 1;
            if ( _InterlockedIncrement((volatile signed __int32 *)CompletionContext + 222) != 3 )
              goto LABEL_39;
            EnterCriticalSection(v3);
            v24 = *((_QWORD *)CompletionContext + 103);
            *((_QWORD *)CompletionContext + 103) = 0;
            LeaveCriticalSection(v3);
            if ( v24 )
              DoTPReuse(CompletionContext, v24);
          }
        }
        else if ( !v8 )
        {
          HandleRemoteClose(CompletionContext);
        }
        v8 = 1;
LABEL_39:
        if ( (xmmword_180063D60 & 0x80u) != 0LL )
          WPP_SF_qD(1031, 63, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v6, *((_DWORD *)CompletionContext + 112));
        goto LABEL_41;
      }
LABEL_38:
      v8 = 1;
      _InterlockedAdd((volatile signed __int32 *)CompletionContext + 112, 1u);
      v29 = 0;
      goto LABEL_39;
    }
    EnterCriticalSection(v3);
    v12 = *(_QWORD *)(v6 + 40);
    if ( *(_QWORD *)(v12 + 8) != v6 + 40 )
      goto LABEL_55;
    v13 = *(_QWORD **)(v6 + 48);
    if ( *v13 != v6 + 40 )
      goto LABEL_55;
    *v13 = v12;
    *(_QWORD *)(v12 + 8) = v13;
    LeaveCriticalSection(v3);
    if ( (unsigned __int16)++*((_WORD *)CompletionContext + 426) == *(_DWORD *)(*((_QWORD *)CompletionContext + 2)
                                                                              + 372LL) )
    {
      if ( (BYTE3(xmmword_180063D60) & 1) != 0 )
        WPP_SF_q(1048, 60, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, CompletionContext);
      v11 = 1;
    }
    v14 = CompletionContext + 104;
LABEL_41:
    if ( a3 && *v14 != -1 && (CompletionContext[800] & 0x40) == 0 )
      UpdateSendCredit(CompletionContext, a3);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)CompletionContext + 9, 0xFFFFFFFF) == 1 )
      break;
    EnterCriticalSection(v3);
    v25 = *((_DWORD *)CompletionContext + 9);
    v26 = *((_QWORD *)CompletionContext + 39);
    while ( v25 > 1 )
    {
      v26 = *(_QWORD *)(v26 + 8);
      --v25;
    }
    LeaveCriticalSection(v3);
    a3 = *(_DWORD *)(v26 + 40);
    v6 = v26 - 40;
  }
  if ( v11 && *v14 != -1 && (CompletionContext[800] & 0x40) == 0 )
    CompleteResizeRecvBuffers(CompletionContext);
  return v29;
}

```

## disassembly

```asm
0x180049eac  mov     [rsp-38h+arg_10], rbx
0x180049eb1  push    rbp
0x180049eb2  push    rsi
0x180049eb3  push    rdi
0x180049eb4  push    r12
0x180049eb6  push    r13
0x180049eb8  push    r14
0x180049eba  push    r15
0x180049ebc  mov     rbp, rsp
0x180049ebf  sub     rsp, 70h
0x180049ec3  xor     eax, eax
0x180049ec5  lea     r14, [rcx+30h]
0x180049ec9  mov     rbx, rcx
0x180049ecc  mov     qword ptr [rbp+var_14], rax
0x180049ed0  mov     rcx, r14; lpCriticalSection
0x180049ed3  mov     [rbp-18h], rax
0x180049ed7  mov     r12d, r8d
0x180049eda  mov     [rbp+arg_18], eax
0x180049edd  mov     rdi, rdx
0x180049ee0  mov     [rbp+arg_8], eax
0x180049ee3  mov     [rbp+arg_0], eax
0x180049ee6  mov     [rdx+55h], al
0x180049ee9  call    cs:__imp_EnterCriticalSection
0x180049ef0  nop     dword ptr [rax+rax+00h]
0x180049ef5  lea     rcx, [rbx+130h]
0x180049efc  mov     rdx, [rcx+8]
0x180049f00  cmp     [rdx], rcx
0x180049f03  jnz     loc_18004A27B
0x180049f09  lea     rax, [rdi+28h]
0x180049f0d  mov     r15d, 1
0x180049f13  mov     [rax], rcx
0x180049f16  mov     esi, r15d
0x180049f19  mov     [rax+8], rdx
0x180049f1d  mov     [rdx], rax
0x180049f20  mov     [rcx+8], rax
0x180049f24  lock xadd [rbx+24h], esi
0x180049f29  add     esi, r15d
0x180049f2c  cmp     esi, r15d
0x180049f2f  jz      short loc_180049F35
0x180049f31  mov     [rdi+50h], r12d
0x180049f35  mov     rcx, r14; lpCriticalSection
0x180049f38  call    cs:__imp_LeaveCriticalSection
0x180049f3f  nop     dword ptr [rax+rax+00h]
0x180049f44  cmp     esi, r15d
0x180049f47  jz      short loc_180049F64
0x180049f49  xor     eax, eax
0x180049f4b  mov     rbx, [rsp+70h+arg_10]
0x180049f53  add     rsp, 70h
0x180049f57  pop     r15
0x180049f59  pop     r14
0x180049f5b  pop     r13
0x180049f5d  pop     r12
0x180049f5f  pop     rdi
0x180049f60  pop     rsi
0x180049f61  pop     rbp
0x180049f62  retn
0x180049f64  xor     r13b, r13b
0x180049f67  cmp     byte ptr [rdi+48h], 0
0x180049f6b  jz      loc_180049FFD
0x180049f71  mov     rcx, r14; lpCriticalSection
0x180049f74  call    cs:__imp_EnterCriticalSection
0x180049f7b  nop     dword ptr [rax+rax+00h]
0x180049f80  lea     rax, [rdi+28h]
0x180049f84  mov     rdx, [rax]
0x180049f87  cmp     [rdx+8], rax
0x180049f8b  jnz     loc_18004A27B
0x180049f91  mov     rcx, [rdi+30h]
0x180049f95  cmp     [rcx], rax
0x180049f98  jnz     loc_18004A27B
0x180049f9e  mov     [rcx], rdx
0x180049fa1  mov     [rdx+8], rcx
0x180049fa5  mov     rcx, r14; lpCriticalSection
0x180049fa8  call    cs:__imp_LeaveCriticalSection
0x180049faf  nop     dword ptr [rax+rax+00h]
0x180049fb4  add     [rbx+354h], r15w
0x180049fbc  mov     rax, [rbx+10h]
0x180049fc0  movzx   ecx, word ptr [rbx+354h]
0x180049fc7  cmp     ecx, [rax+174h]
0x180049fcd  jnz     short loc_180049FF4
0x180049fcf  test    byte ptr cs:xmmword_180063D60+3, r15b
0x180049fd6  jz      short loc_180049FF1
0x180049fd8  mov     edx, 3Ch ; '<'
0x180049fdd  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x180049fe4  mov     ecx, 418h
0x180049fe9  mov     r9, rbx
0x180049fec  call    WPP_SF_q
0x180049ff1  mov     r13b, r15b
0x180049ff4  lea     rsi, [rbx+68h]
0x180049ff8  jmp     loc_18004A1E8
0x180049ffd  mov     rax, [rbx+8]
0x18004a001  test    rax, rax
0x18004a004  jz      short loc_18004A00A
0x18004a006  lock add [rax], r15d
0x18004a00a  movzx   eax, word ptr [rdi+4Ah]
0x18004a00e  lea     rsi, [rbx+68h]
0x18004a012  mov     dword ptr [rdi+50h], 0
0x18004a019  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18004a01d  mov     [rbp+var_18], eax
0x18004a020  mov     rax, [rdi+60h]
0x18004a024  mov     qword ptr [rbp+var_14+4], rax
0x18004a028  jz      short loc_18004A08F
0x18004a02a  test    byte ptr [rbx+320h], 40h
0x18004a031  jnz     short loc_18004A08F
0x18004a033  mov     rax, [rbx+10h]
0x18004a037  lea     rcx, [rbp+arg_0]
0x18004a03b  mov     [rsp+70h+var_30], rcx
0x18004a040  lea     rdx, [rdi+8]
0x18004a044  mov     [rsp+70h+var_38], 0
0x18004a04d  lea     rcx, [rbp+arg_8]
0x18004a051  mov     [rsp+70h+var_40], 0
0x18004a05a  lea     r9, [rbp+arg_18]
0x18004a05e  mov     rax, [rax+0D8h]
0x18004a065  mov     r8d, r15d
0x18004a068  mov     [rsp+70h+var_48], rdx
0x18004a06d  lea     rdx, [rbp+var_18]
0x18004a071  mov     [rsp+70h+var_50], rcx
0x18004a076  mov     rcx, [rsi]
0x18004a079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a07e  xor     r15b, r15b
0x18004a081  cmp     eax, 0FFFFFFFFh
0x18004a084  jnz     loc_18004A1A7
0x18004a08a  mov     eax, [rbp+arg_0]
0x18004a08d  jmp     short loc_18004A097
0x18004a08f  mov     eax, 2736h
0x18004a094  mov     [rbp+arg_0], eax
0x18004a097  cmp     eax, 3E5h
0x18004a09c  jz      loc_18004A1A7
0x18004a0a2  mov     rcx, r14; lpCriticalSection
0x18004a0a5  call    cs:__imp_EnterCriticalSection
0x18004a0ac  nop     dword ptr [rax+rax+00h]
0x18004a0b1  lea     rax, [rdi+28h]
0x18004a0b5  mov     rdx, [rax]
0x18004a0b8  cmp     [rdx+8], rax
0x18004a0bc  jnz     loc_18004A27B
0x18004a0c2  mov     rcx, [rdi+30h]
0x18004a0c6  cmp     [rcx], rax
0x18004a0c9  jnz     loc_18004A27B
0x18004a0cf  mov     [rcx], rdx
0x18004a0d2  mov     [rdx+8], rcx
0x18004a0d6  mov     rcx, r14; lpCriticalSection
0x18004a0d9  call    cs:__imp_LeaveCriticalSection
0x18004a0e0  nop     dword ptr [rax+rax+00h]
0x18004a0e5  mov     rcx, [rbx+8]
0x18004a0e9  test    rcx, rcx
0x18004a0ec  jz      short loc_18004A103
0x18004a0ee  or      eax, 0FFFFFFFFh
0x18004a0f1  lock xadd [rcx], eax
0x18004a0f5  cmp     eax, 1
0x18004a0f8  jnz     short loc_18004A103
0x18004a0fa  mov     rcx, [rbx+8]
0x18004a0fe  call    SockDestroySocket
0x18004a103  cmp     [rbp+arg_0], 2746h
0x18004a10a  jz      short loc_18004A12A
0x18004a10c  cmp     [rbp+arg_0], 2749h
0x18004a113  jz      short loc_18004A12A
0x18004a115  test    r15b, r15b
0x18004a118  jnz     loc_18004A19F
0x18004a11e  xor     edx, edx
0x18004a120  mov     rcx, rbx; CompletionContext
0x18004a123  call    HandleRemoteClose
0x18004a128  jmp     short loc_18004A19F
0x18004a12a  cmp     dword ptr [rbx+88h], 0
0x18004a131  jnz     short loc_18004A19F
0x18004a133  cmp     dword ptr [rbx+1C0h], 0
0x18004a13a  jnz     short loc_18004A19F
0x18004a13c  xor     edx, edx
0x18004a13e  mov     rcx, rbx; CompletionContext
0x18004a141  call    HandleRemoteClose
0x18004a146  mov     r15d, 1
0x18004a14c  mov     eax, r15d
0x18004a14f  lock xadd [rbx+378h], eax
0x18004a157  add     eax, r15d
0x18004a15a  cmp     eax, 3
0x18004a15d  jnz     short loc_18004A1BC
0x18004a15f  mov     rcx, r14; lpCriticalSection
0x18004a162  call    cs:__imp_EnterCriticalSection
0x18004a169  nop     dword ptr [rax+rax+00h]
0x18004a16e  mov     r15, [rbx+338h]
0x18004a175  mov     rcx, r14; lpCriticalSection
0x18004a178  mov     qword ptr [rbx+338h], 0
0x18004a183  call    cs:__imp_LeaveCriticalSection
0x18004a18a  nop     dword ptr [rax+rax+00h]
0x18004a18f  test    r15, r15
0x18004a192  jz      short loc_18004A19F
0x18004a194  mov     rdx, r15
0x18004a197  mov     rcx, rbx
0x18004a19a  call    DoTPReuse
0x18004a19f  mov     r15d, 1
0x18004a1a5  jmp     short loc_18004A1BC
0x18004a1a7  mov     r15d, 1
0x18004a1ad  lock add [rbx+1C0h], r15d
0x18004a1b5  mov     [rbp+arg_0], 0
0x18004a1bc  cmp     byte ptr cs:xmmword_180063D60, 0
0x18004a1c3  jge     short loc_18004A1E8
0x18004a1c5  mov     eax, [rbx+1C0h]
0x18004a1cb  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18004a1d2  mov     edx, 3Fh ; '?'
0x18004a1d7  mov     dword ptr [rsp+70h+var_50], eax
0x18004a1db  mov     ecx, 407h
0x18004a1e0  mov     r9, rdi
0x18004a1e3  call    WPP_SF_qD
0x18004a1e8  test    r12d, r12d
0x18004a1eb  jz      short loc_18004A207
0x18004a1ed  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18004a1f1  jz      short loc_18004A207
0x18004a1f3  test    byte ptr [rbx+320h], 40h
0x18004a1fa  jnz     short loc_18004A207
0x18004a1fc  mov     edx, r12d
0x18004a1ff  mov     rcx, rbx
0x18004a202  call    UpdateSendCredit
0x18004a207  or      eax, 0FFFFFFFFh
0x18004a20a  lock xadd [rbx+24h], eax
0x18004a20f  cmp     eax, 1
0x18004a212  jz      short loc_18004A257
0x18004a214  mov     rcx, r14; lpCriticalSection
0x18004a217  call    cs:__imp_EnterCriticalSection
0x18004a21e  nop     dword ptr [rax+rax+00h]
0x18004a223  mov     eax, [rbx+24h]
0x18004a226  mov     rdi, [rbx+138h]
0x18004a22d  jmp     short loc_18004A236
0x18004a22f  mov     rdi, [rdi+8]
0x18004a233  sub     eax, r15d
0x18004a236  cmp     eax, r15d
0x18004a239  jg      short loc_18004A22F
0x18004a23b  mov     rcx, r14; lpCriticalSection
0x18004a23e  call    cs:__imp_LeaveCriticalSection
0x18004a245  nop     dword ptr [rax+rax+00h]
0x18004a24a  mov     r12d, [rdi+28h]
0x18004a24e  add     rdi, 0FFFFFFFFFFFFFFD8h
0x18004a252  jmp     loc_180049F67
0x18004a257  test    r13b, r13b
0x18004a25a  jz      short loc_18004A273
0x18004a25c  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18004a260  jz      short loc_18004A273
0x18004a262  test    byte ptr [rbx+320h], 40h
0x18004a269  jnz     short loc_18004A273
0x18004a26b  mov     rcx, rbx
0x18004a26e  call    CompleteResizeRecvBuffers
0x18004a273  mov     eax, [rbp+arg_0]
0x18004a276  jmp     loc_180049F4B
0x18004a27b  mov     ecx, 3
0x18004a280  int     29h; Win8: RtlFailFast(ecx)
```
