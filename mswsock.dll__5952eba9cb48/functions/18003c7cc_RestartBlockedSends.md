# RestartBlockedSends

- ea: `0x18003c7cc`
- end: `0x18003cdc0`
- name: `RestartBlockedSends`
- size: `1524`
- prototype: `__int64 __fastcall(PVOID CompletionContext)`
- caller_count: `8`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18003b054`
- `0x18003b344`
- `0x18003b760`
- `0x1800411a8`
- `0x18004958c`
- `0x180049ba8`
- `0x18004a2dc`
- `0x18005284c`

## callees

- `0x180023cc0`
- `0x180024674`
- `0x180024dd4`
- `0x180038104`
- `0x180038118`
- `0x180038944`
- `0x180038c40`
- `0x18003ae8c`
- `0x18003c7cc`
- `0x18003dae8`
- `0x18003ec84`
- `0x1800462b0`
- `0x180046c34`
- `0x1800496e4`
- `0x18004b1d0`
- `0x18004c204`
- `0x18004c81c`
- `0x18004f27c`
- `0x18004f514`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c8ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c97b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c9ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cb2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cbd5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cd07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c8ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c97b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c9ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cb2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cbd5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cd07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c84b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c8ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c98a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ca0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cbb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cbf3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c84b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c8ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c98a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ca0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cbb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cbf3`

## pseudocode

```c
__int64 __fastcall RestartBlockedSends(volatile signed __int32 *CompletionContext, __int64 a2)
{
  __int64 result; // rax
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  struct _RTL_CRITICAL_SECTION *v5; // r15
  _QWORD **v6; // r13
  _QWORD *v7; // rax
  _QWORD *v8; // rcx
  PVOID *v9; // rdx
  _QWORD *v10; // rsi
  int v11; // eax
  char v12; // r12
  bool v13; // zf
  _QWORD *v14; // r14
  __int64 v15; // rdi
  char v16; // cl
  int v17; // eax
  int v18; // edx
  int v19; // eax
  BOOL v20; // ecx
  int v21; // r8d
  char v22; // cl
  unsigned int v23; // eax
  unsigned int v24; // r14d
  __int64 v25; // r9
  unsigned int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rdx
  unsigned int v29; // r14d
  bool v30; // di
  __int64 v31; // [rsp+70h] [rbp+8h] BYREF
  int v32; // [rsp+78h] [rbp+10h]

  v32 = 0;
  LODWORD(v31) = 0;
  result = (unsigned int)_InterlockedIncrement(CompletionContext + 62);
  if ( (_DWORD)result != 1 )
    return result;
  v4 = (struct _RTL_CRITICAL_SECTION *)(CompletionContext + 12);
  v5 = (struct _RTL_CRITICAL_SECTION *)(CompletionContext + 12);
  v6 = (_QWORD **)(CompletionContext + 104);
  while ( 2 )
  {
    while ( *v6 != v6 )
    {
      v5 = v4;
      LODWORD(v31) = SendControlMessage((PVOID)CompletionContext, 0, 0);
      EnterCriticalSection(v4);
      if ( (_DWORD)v31 )
      {
        v10 = CompletionContext + 100;
        goto LABEL_88;
      }
      v7 = *v6;
      if ( *v6 != v6 )
      {
        if ( (_QWORD **)v7[1] != v6
          || (v8 = (_QWORD *)*v7, *(_QWORD **)(*v7 + 8LL) != v7)
          || (*v6 = v8, v8[1] = v6, v9 = (PVOID *)*((_QWORD *)CompletionContext + 99), *v9 != CompletionContext + 196) )
        {
          __fastfail(3u);
        }
        *v7 = CompletionContext + 196;
        v7[1] = v9;
        *v9 = v7;
        *((_QWORD *)CompletionContext + 99) = v7;
      }
      LeaveCriticalSection(v4);
    }
    v11 = *((_DWORD *)CompletionContext + 34);
    v12 = 0;
    v13 = v11 == 0;
    if ( v11 )
      goto LABEL_15;
    if ( (CompletionContext[200] & 0x40) != 0 )
    {
      v13 = 1;
LABEL_15:
      LOBYTE(a2) = v13;
      CompleteAppSendsUponClose(CompletionContext, a2);
    }
    EnterCriticalSection(v5);
    v10 = CompletionContext + 100;
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          v14 = (_QWORD *)*v10;
          if ( (_QWORD *)*v10 == v10 || *((_DWORD *)CompletionContext + 44) > 1u )
            goto LABEL_88;
          v15 = (__int64)(v14 - 2);
          v16 = xmmword_180063D60;
          if ( (xmmword_180063D60 & 0x80u) != 0LL )
          {
            WPP_SF_(1031, 149, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids);
            v16 = xmmword_180063D60;
          }
          v17 = *(_DWORD *)(v15 + 92);
          if ( !v17 )
          {
            if ( v16 >= 0 )
              goto LABEL_88;
            v28 = 150;
            goto LABEL_87;
          }
          if ( *(_BYTE *)(v15 + 131) )
          {
            if ( v16 >= 0 )
              goto LABEL_88;
            v28 = 151;
LABEL_87:
            WPP_SF_q(1031, v28, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v14 - 2);
            goto LABEL_88;
          }
          if ( !*(_DWORD *)(v15 + 36) )
            break;
          *((_DWORD *)v14 + 19) = 0;
          CheckBSQHeadForCompletion((PVOID)CompletionContext);
          LeaveCriticalSection(v5);
          EnterCriticalSection(v5);
        }
        if ( (v17 & 0x80u) != 0 )
        {
          if ( (((v17 & 4) != 0) & (*((_BYTE *)CompletionContext + 801) >> 3)) == 0
            || (unsigned int)GetLargeRecvFCInfoNoPop(CompletionContext, 0) != 1 )
          {
            goto LABEL_88;
          }
          v16 = xmmword_180063D60;
        }
        v18 = *(_DWORD *)(v15 + 92);
        if ( (v18 & 8) == 0 || *(_DWORD *)(v15 + 40) < *(_DWORD *)(v15 + 80) )
          break;
        if ( (v18 & 0x10) == 0 )
        {
          LeaveCriticalSection(v5);
          LODWORD(v31) = ContinueTransmitPackets((char *)CompletionContext, (__int64)(v14 - 2));
          EnterCriticalSection(v5);
          if ( !(_DWORD)v31 )
            continue;
        }
        goto LABEL_88;
      }
      v19 = *(_DWORD *)(v15 + 80);
      if ( *(_DWORD *)(v15 + 84) >= v19 || (v18 & 0x443) == 0 && (*(_DWORD *)(v15 + 92) & 0x120) != 0x120 )
      {
        if ( v19 )
          break;
      }
      if ( v16 < 0 )
        WPP_SF_q(1031, 152, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v14 - 2);
      *(_DWORD *)(v15 + 92) &= 0xFFFFFEBF;
      v20 = (unsigned int)UseRdma(*(unsigned int *)(v15 + 80))
         && !*(_QWORD *)(v15 + 136)
         && (*(_BYTE *)(v15 + 92) & 0x21) == 0
         && *((_DWORD *)CompletionContext + 117) != 3
         && (unsigned int)GetLargeRecvFCInfoNoPop(CompletionContext, 0) != 3;
      v21 = *(_DWORD *)(v15 + 84);
      if ( (unsigned int)(*(_DWORD *)(v15 + 80) - v21) <= 0x3F0 && v20 && (*(_BYTE *)(v15 + 92) & 4) == 0 )
      {
        v22 = BYTE1(xmmword_180063D60);
        if ( (BYTE1(xmmword_180063D60) & 0x10) != 0 )
        {
          WPP_SF_dd(1036, 153, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, *(unsigned int *)(v15 + 40), v21);
          v22 = BYTE1(xmmword_180063D60);
        }
        if ( *(_DWORD *)(v15 + 40) != *(_DWORD *)(v15 + 84) )
          goto LABEL_88;
        if ( (v22 & 0x10) != 0 )
          WPP_SF_(1036, 154, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids);
        *(_DWORD *)(v15 + 92) &= ~2u;
      }
      ++*(_DWORD *)(v15 + 96);
      *(_DWORD *)(v15 + 92) &= ~0x400u;
      LeaveCriticalSection(v5);
      v23 = TrySend((PVOID)CompletionContext, (__int64)&v31);
      v24 = v23;
      if ( (xmmword_180063D60 & 0x80u) != 0LL )
        WPP_SF_ddq(1031, 155, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v23, v31, v15);
      if ( (*(_BYTE *)(*((_QWORD *)CompletionContext + 27) + 24LL) & 4) == 0
        && !v24
        && *((_DWORD *)CompletionContext + 32) < *(_DWORD *)(*(_QWORD *)CompletionContext + 64LL) )
      {
        NotifyAfdOfSendAvail(CompletionContext);
      }
      EnterCriticalSection(v5);
      if ( v24 )
      {
        if ( (_DWORD)v31 != 997 )
        {
          if ( !*(_DWORD *)(v15 + 36) )
          {
            v25 = *(_QWORD *)(v15 + 136);
            if ( v25 )
            {
              if ( (_DWORD)v31 )
                v26 = SocketErrorToNtStatus((unsigned int)v31);
              else
                v26 = 0;
              IndicateRedirError(CompletionContext, v25, v26);
            }
            else if ( *(_QWORD *)(v15 + 8) )
            {
              CompleteOverlappedIO(
                *(_QWORD *)(*(_QWORD *)CompletionContext + 8LL),
                *(_QWORD *)(v15 + 8),
                *(void **)(v15 + 64),
                *(void **)(v15 + 72),
                v31,
                *(_DWORD *)(v15 + 40));
            }
          }
          *(_DWORD *)(v15 + 36) = 1;
          *(_DWORD *)(v15 + 92) = 0;
          goto LABEL_77;
        }
      }
      else
      {
        if ( (*(_BYTE *)(v15 + 92) & 8) == 0 )
          goto LABEL_77;
        LeaveCriticalSection(v5);
        LODWORD(v31) = ContinueTransmitPackets((char *)CompletionContext, v15);
        EnterCriticalSection(v5);
        if ( !(_DWORD)v31 )
          goto LABEL_77;
      }
      v12 = 1;
LABEL_77:
      --*(_DWORD *)(v15 + 96);
      CheckBSQHeadForCompletion((PVOID)CompletionContext);
      if ( v12 )
      {
        if ( (xmmword_180063D60 & 0x80u) == 0LL )
          goto LABEL_88;
        v27 = 156;
        goto LABEL_80;
      }
    }
    if ( v16 < 0 )
    {
      v27 = 157;
LABEL_80:
      WPP_SF_(1031, v27, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids);
    }
LABEL_88:
    v29 = *((_DWORD *)CompletionContext + 108);
    v30 = (_QWORD *)*v10 == v10 && *v6 == v6;
    LeaveCriticalSection(v5);
    if ( (*(_BYTE *)(*((_QWORD *)CompletionContext + 27) + 24LL) & 4) == 0
      && (*((_DWORD *)CompletionContext + 32) < *(_DWORD *)(*(_QWORD *)CompletionContext + 64LL) || v29 > 2 && v30) )
    {
      NotifyAfdOfSendAvail(CompletionContext);
    }
    if ( _InterlockedExchangeAdd(CompletionContext + 62, 0xFFFFFFFF) != 1 )
    {
      v4 = (struct _RTL_CRITICAL_SECTION *)(CompletionContext + 12);
      continue;
    }
    break;
  }
  if ( (CompletionContext[200] & 1) != 0 )
  {
    result = ContinueGracefulDisconnect(CompletionContext);
    LODWORD(v31) = result;
    if ( (_DWORD)result && (xmmword_180063D60 & 2) != 0 )
      return WPP_SF_d(1025, 158, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, (unsigned int)result);
  }
  else
  {
    result = *(_QWORD *)CompletionContext;
    if ( (*(_BYTE *)(*(_QWORD *)CompletionContext + 69LL) & 2) != 0 )
      return SendFIN(CompletionContext);
  }
  return result;
}

```

## disassembly

```asm
0x18003c7cc  push    rbx
0x18003c7ce  push    rsi
0x18003c7cf  push    rdi
0x18003c7d0  push    r12
0x18003c7d2  push    r13
0x18003c7d4  push    r14
0x18003c7d6  push    r15
0x18003c7d8  sub     rsp, 30h
0x18003c7dc  mov     rbx, rcx
0x18003c7df  mov     [rsp+68h+arg_8], 0
0x18003c7e7  mov     dword ptr [rsp+68h+arg_0], 0
0x18003c7ef  mov     eax, 1
0x18003c7f4  lock xadd [rcx+0F8h], eax
0x18003c7fc  inc     eax
0x18003c7fe  cmp     eax, 1
0x18003c801  jnz     loc_18003CDAF
0x18003c807  lea     rdi, [rcx+30h]
0x18003c80b  mov     r15, rdi
0x18003c80e  lea     r13, [rcx+1A0h]
0x18003c815  cmp     [r13+0], r13
0x18003c819  jz      loc_18003C8C8
0x18003c81f  mov     [rsp+68h+var_40], 0
0x18003c828  xor     r9d, r9d
0x18003c82b  xor     r8d, r8d
0x18003c82e  mov     [rsp+68h+var_48], 0
0x18003c837  mov     dl, 14h
0x18003c839  mov     rcx, rbx
0x18003c83c  mov     r15, rdi
0x18003c83f  call    SendControlMessage
0x18003c844  mov     rcx, rdi; lpCriticalSection
0x18003c847  mov     dword ptr [rsp+68h+arg_0], eax
0x18003c84b  call    cs:__imp_EnterCriticalSection
0x18003c852  nop     dword ptr [rax+rax+00h]
0x18003c857  cmp     dword ptr [rsp+68h+arg_0], 0
0x18003c85c  jnz     short loc_18003C8BC
0x18003c85e  mov     rax, [r13+0]
0x18003c862  cmp     rax, r13
0x18003c865  jz      short loc_18003C8A8
0x18003c867  cmp     [rax+8], r13
0x18003c86b  jnz     loc_18003CD5A
0x18003c871  mov     rcx, [rax]
0x18003c874  cmp     [rcx+8], rax
0x18003c878  jnz     loc_18003CD5A
0x18003c87e  mov     [r13+0], rcx
0x18003c882  mov     [rcx+8], r13
0x18003c886  lea     rcx, [rbx+310h]
0x18003c88d  mov     rdx, [rcx+8]
0x18003c891  cmp     [rdx], rcx
0x18003c894  jnz     loc_18003CD5A
0x18003c89a  mov     [rax], rcx
0x18003c89d  mov     [rax+8], rdx
0x18003c8a1  mov     [rdx], rax
0x18003c8a4  mov     [rcx+8], rax
0x18003c8a8  mov     rcx, rdi; lpCriticalSection
0x18003c8ab  call    cs:__imp_LeaveCriticalSection
0x18003c8b2  nop     dword ptr [rax+rax+00h]
0x18003c8b7  jmp     loc_18003C815
0x18003c8bc  lea     rsi, [rbx+190h]
0x18003c8c3  jmp     loc_18003CCEA
0x18003c8c8  mov     eax, [rbx+88h]
0x18003c8ce  xor     r12b, r12b
0x18003c8d1  test    eax, eax
0x18003c8d3  jnz     short loc_18003C8E0
0x18003c8d5  test    byte ptr [rbx+320h], 40h
0x18003c8dc  jz      short loc_18003C8EB
0x18003c8de  test    eax, eax
0x18003c8e0  setz    dl
0x18003c8e3  mov     rcx, rbx
0x18003c8e6  call    CompleteAppSendsUponClose
0x18003c8eb  mov     rcx, r15; lpCriticalSection
0x18003c8ee  call    cs:__imp_EnterCriticalSection
0x18003c8f5  nop     dword ptr [rax+rax+00h]
0x18003c8fa  lea     rsi, [rbx+190h]
0x18003c901  mov     r14, [rsi]
0x18003c904  cmp     r14, rsi
0x18003c907  jz      loc_18003CCEA
0x18003c90d  mov     eax, [rbx+0B0h]
0x18003c913  test    eax, eax
0x18003c915  jz      short loc_18003C920
0x18003c917  cmp     eax, 1
0x18003c91a  jnz     loc_18003CCEA
0x18003c920  lea     rdi, [r14-10h]
0x18003c924  mov     cl, byte ptr cs:xmmword_180063D60
0x18003c92a  test    cl, cl
0x18003c92c  jns     short loc_18003C94A
0x18003c92e  mov     edx, 95h
0x18003c933  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18003c93a  mov     ecx, 407h
0x18003c93f  call    WPP_SF_
0x18003c944  mov     cl, byte ptr cs:xmmword_180063D60
0x18003c94a  mov     eax, [rdi+5Ch]
0x18003c94d  test    eax, eax
0x18003c94f  jz      loc_18003CCCD
0x18003c955  cmp     byte ptr [rdi+83h], 0
0x18003c95c  jnz     loc_18003CCC2
0x18003c962  cmp     dword ptr [rdi+24h], 0
0x18003c966  jz      short loc_18003C99B
0x18003c968  mov     rcx, rbx; CompletionContext
0x18003c96b  mov     dword ptr [r14+4Ch], 0
0x18003c973  call    CheckBSQHeadForCompletion
0x18003c978  mov     rcx, r15; lpCriticalSection
0x18003c97b  call    cs:__imp_LeaveCriticalSection
0x18003c982  nop     dword ptr [rax+rax+00h]
0x18003c987  mov     rcx, r15; lpCriticalSection
0x18003c98a  call    cs:__imp_EnterCriticalSection
0x18003c991  nop     dword ptr [rax+rax+00h]
0x18003c996  jmp     loc_18003C901
0x18003c99b  test    al, al
0x18003c99d  jns     short loc_18003C9D1
0x18003c99f  mov     cl, [rbx+321h]
0x18003c9a5  shr     cl, 3
0x18003c9a8  test    al, 4
0x18003c9aa  setnz   al
0x18003c9ad  and     cl, al
0x18003c9af  test    cl, 1
0x18003c9b2  jz      loc_18003CCEA
0x18003c9b8  xor     edx, edx
0x18003c9ba  mov     rcx, rbx
0x18003c9bd  call    GetLargeRecvFCInfoNoPop
0x18003c9c2  cmp     eax, 1
0x18003c9c5  jnz     loc_18003CCEA
0x18003c9cb  mov     cl, byte ptr cs:xmmword_180063D60
0x18003c9d1  mov     edx, [rdi+5Ch]
0x18003c9d4  test    dl, 8
0x18003c9d7  jz      short loc_18003CA27
0x18003c9d9  mov     eax, [rdi+50h]
0x18003c9dc  cmp     [rdi+28h], eax
0x18003c9df  jb      short loc_18003CA27
0x18003c9e1  test    dl, 10h
0x18003c9e4  jnz     loc_18003CCEA
0x18003c9ea  mov     rcx, r15; lpCriticalSection
0x18003c9ed  call    cs:__imp_LeaveCriticalSection
0x18003c9f4  nop     dword ptr [rax+rax+00h]
0x18003c9f9  mov     rdx, rdi
0x18003c9fc  mov     rcx, rbx; CompletionContext
0x18003c9ff  call    ContinueTransmitPackets
0x18003ca04  mov     rcx, r15; lpCriticalSection
0x18003ca07  mov     dword ptr [rsp+68h+arg_0], eax
0x18003ca0b  call    cs:__imp_EnterCriticalSection
0x18003ca12  nop     dword ptr [rax+rax+00h]
0x18003ca17  cmp     dword ptr [rsp+68h+arg_0], 0
0x18003ca1c  jz      loc_18003C901
0x18003ca22  jmp     loc_18003CCEA
0x18003ca27  mov     eax, [rdi+50h]
0x18003ca2a  cmp     [rdi+54h], eax
0x18003ca2d  jge     short loc_18003CA45
0x18003ca2f  test    edx, 443h
0x18003ca35  jnz     short loc_18003CA4D
0x18003ca37  mov     r8d, 120h
0x18003ca3d  and     edx, r8d
0x18003ca40  cmp     edx, r8d
0x18003ca43  jz      short loc_18003CA4D
0x18003ca45  test    eax, eax
0x18003ca47  jnz     loc_18003CCB7
0x18003ca4d  test    cl, cl
0x18003ca4f  jns     short loc_18003CA6A
0x18003ca51  mov     edx, 98h
0x18003ca56  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18003ca5d  mov     ecx, 407h
0x18003ca62  mov     r9, rdi
0x18003ca65  call    WPP_SF_q
0x18003ca6a  and     dword ptr [rdi+5Ch], 0FFFFFEBFh
0x18003ca71  mov     ecx, [rdi+50h]
0x18003ca74  call    UseRdma
0x18003ca79  test    eax, eax
0x18003ca7b  jz      short loc_18003CAAC
0x18003ca7d  cmp     qword ptr [rdi+88h], 0
0x18003ca85  jnz     short loc_18003CAAC
0x18003ca87  test    byte ptr [rdi+5Ch], 21h
0x18003ca8b  jnz     short loc_18003CAAC
0x18003ca8d  cmp     dword ptr [rbx+1D4h], 3
0x18003ca94  jz      short loc_18003CAAC
0x18003ca96  xor     edx, edx
0x18003ca98  mov     rcx, rbx
0x18003ca9b  call    GetLargeRecvFCInfoNoPop
0x18003caa0  cmp     eax, 3
0x18003caa3  jz      short loc_18003CAAC
0x18003caa5  mov     ecx, 1
0x18003caaa  jmp     short loc_18003CAAE
0x18003caac  xor     ecx, ecx
0x18003caae  mov     eax, [rdi+50h]
0x18003cab1  mov     r8d, [rdi+54h]
0x18003cab5  sub     eax, r8d
0x18003cab8  cmp     eax, 3F0h
0x18003cabd  ja      short loc_18003CB24
0x18003cabf  test    ecx, ecx
0x18003cac1  jz      short loc_18003CB24
0x18003cac3  test    byte ptr [rdi+5Ch], 4
0x18003cac7  jnz     short loc_18003CB24
0x18003cac9  mov     cl, byte ptr cs:xmmword_180063D60+1
0x18003cacf  test    cl, 10h
0x18003cad2  jz      short loc_18003CAF9
0x18003cad4  mov     r9d, [rdi+28h]
0x18003cad8  mov     edx, 99h
0x18003cadd  mov     dword ptr [rsp+68h+var_48], r8d
0x18003cae2  mov     ecx, 40Ch
0x18003cae7  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18003caee  call    WPP_SF_dd
0x18003caf3  mov     cl, byte ptr cs:xmmword_180063D60+1
0x18003caf9  mov     eax, [rdi+54h]
0x18003cafc  cmp     [rdi+28h], eax
0x18003caff  jnz     loc_18003CCEA
0x18003cb05  test    cl, 10h
0x18003cb08  jz      short loc_18003CB20
0x18003cb0a  mov     edx, 9Ah
0x18003cb0f  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18003cb16  mov     ecx, 40Ch
0x18003cb1b  call    WPP_SF_
0x18003cb20  and     dword ptr [rdi+5Ch], 0FFFFFFFDh
0x18003cb24  inc     dword ptr [rdi+60h]
0x18003cb27  mov     rcx, r15; lpCriticalSection
0x18003cb2a  btr     dword ptr [rdi+5Ch], 0Ah
0x18003cb2f  call    cs:__imp_LeaveCriticalSection
0x18003cb36  nop     dword ptr [rax+rax+00h]
0x18003cb3b  lea     rax, [rsp+68h+arg_0]
0x18003cb40  mov     r8b, 1
0x18003cb43  lea     r9, [rsp+68h+arg_8]
0x18003cb48  mov     [rsp+68h+var_48], rax; __int64
0x18003cb4d  mov     rdx, rdi
0x18003cb50  mov     rcx, rbx; CompletionContext
0x18003cb53  call    TrySend
0x18003cb58  mov     r14d, eax
0x18003cb5b  cmp     byte ptr cs:xmmword_180063D60, 0
0x18003cb62  jge     short loc_18003CB8C
0x18003cb64  mov     r8d, dword ptr [rsp+68h+arg_0]
0x18003cb69  mov     edx, 9Bh
0x18003cb6e  mov     [rsp+68h+var_40], rdi
0x18003cb73  mov     ecx, 407h
0x18003cb78  mov     dword ptr [rsp+68h+var_48], r8d
0x18003cb7d  mov     r9d, eax
0x18003cb80  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18003cb87  call    WPP_SF_ddq
0x18003cb8c  mov     rax, [rbx+0D8h]
0x18003cb93  test    byte ptr [rax+18h], 4
0x18003cb97  jnz     short loc_18003CBB4
0x18003cb99  test    r14d, r14d
0x18003cb9c  jnz     short loc_18003CBB4
0x18003cb9e  mov     rax, [rbx]
0x18003cba1  mov     ecx, [rax+40h]
0x18003cba4  cmp     [rbx+80h], ecx
0x18003cbaa  jnb     short loc_18003CBB4
0x18003cbac  mov     rcx, rbx
0x18003cbaf  call    NotifyAfdOfSendAvail
0x18003cbb4  mov     rcx, r15; lpCriticalSection
0x18003cbb7  call    cs:__imp_EnterCriticalSection
0x18003cbbe  nop     dword ptr [rax+rax+00h]
0x18003cbc3  test    r14d, r14d
0x18003cbc6  jnz     short loc_18003CC08
0x18003cbc8  test    byte ptr [rdi+5Ch], 8
0x18003cbcc  jz      loc_18003CC82
0x18003cbd2  mov     rcx, r15; lpCriticalSection
0x18003cbd5  call    cs:__imp_LeaveCriticalSection
0x18003cbdc  nop     dword ptr [rax+rax+00h]
0x18003cbe1  mov     rdx, rdi
0x18003cbe4  mov     rcx, rbx; CompletionContext
0x18003cbe7  call    ContinueTransmitPackets
0x18003cbec  mov     rcx, r15; lpCriticalSection
0x18003cbef  mov     dword ptr [rsp+68h+arg_0], eax
0x18003cbf3  call    cs:__imp_EnterCriticalSection
0x18003cbfa  nop     dword ptr [rax+rax+00h]
0x18003cbff  cmp     dword ptr [rsp+68h+arg_0], r14d
0x18003cc04  jz      short loc_18003CC82
0x18003cc06  jmp     short loc_18003CC14
0x18003cc08  mov     edx, dword ptr [rsp+68h+arg_0]
0x18003cc0c  cmp     edx, 3E5h
0x18003cc12  jnz     short loc_18003CC19
0x18003cc14  mov     r12b, 1
0x18003cc17  jmp     short loc_18003CC82
0x18003cc19  xor     r14d, r14d
0x18003cc1c  cmp     [rdi+24h], r14d
0x18003cc20  jnz     short loc_18003CC77
0x18003cc22  mov     r9, [rdi+88h]
0x18003cc29  test    r9, r9
0x18003cc2c  jz      short loc_18003CC4E
0x18003cc2e  test    edx, edx
0x18003cc30  jnz     short loc_18003CC37
0x18003cc32  mov     eax, r14d
0x18003cc35  jmp     short loc_18003CC3E
0x18003cc37  mov     ecx, edx
0x18003cc39  call    SocketErrorToNtStatus
0x18003cc3e  mov     r8d, eax
0x18003cc41  mov     rdx, r9
0x18003cc44  mov     rcx, rbx
0x18003cc47  call    IndicateRedirError
0x18003cc4c  jmp     short loc_18003CC77
0x18003cc4e  cmp     [rdi+8], r14
0x18003cc52  jz      short loc_18003CC77
0x18003cc54  mov     rcx, [rbx]
0x18003cc57  mov     eax, [rdi+28h]
0x18003cc5a  mov     r9, [rdi+48h]
0x18003cc5e  mov     r8, [rdi+40h]
0x18003cc62  mov     rcx, [rcx+8]
0x18003cc66  mov     dword ptr [rsp+68h+var_40], eax
0x18003cc6a  mov     dword ptr [rsp+68h+var_48], edx
0x18003cc6e  mov     rdx, [rdi+8]
0x18003cc72  call    CompleteOverlappedIO
0x18003cc77  mov     dword ptr [rdi+24h], 1
0x18003cc7e  mov     [rdi+5Ch], r14d
0x18003cc82  dec     dword ptr [rdi+60h]
0x18003cc85  mov     rcx, rbx; CompletionContext
  ... truncated ...
```
