# CheckPendingAppRecvs

- ea: `0x18003cdc8`
- end: `0x18003d478`
- name: `CheckPendingAppRecvs`
- size: `1712`
- prototype: `__int64 __fastcall(PVOID CompletionContext)`
- caller_count: `8`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003b114`
- `0x18003b760`
- `0x180046240`
- `0x180047cb0`
- `0x1800485dc`
- `0x18004b890`
- `0x18004f6c4`
- `0x18004fd1c`

## callees

- `0x1800240e4`
- `0x180024814`
- `0x180024dd4`
- `0x180038104`
- `0x18003aefc`
- `0x18003cdc8`
- `0x18003d480`
- `0x18003dae8`
- `0x18003e1e0`
- `0x18004642c`
- `0x1800477a8`
- `0x1800479e4`
- `0x180047be4`
- `0x180049310`
- `0x18004a288`
- `0x18004fa0c`
- `0x180050544`
- `0x18005086c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d046`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d1c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d20d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d2b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d3c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d046`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d1c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d20d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d2b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d3c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d02f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d12d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d266`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d3a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d02f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d12d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d266`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d3a0`

## pseudocode

```c
__int64 __fastcall CheckPendingAppRecvs(char *CompletionContext)
{
  __int64 result; // rax
  int v3; // ecx
  _QWORD *v4; // rbx
  char *v5; // r14
  char *v6; // r14
  _DWORD *v7; // rbx
  __int64 NextMessage; // rax
  __int64 v9; // r8
  int v10; // edx
  _DWORD *v11; // r15
  _DWORD *v12; // rdi
  _DWORD *v13; // r12
  _DWORD *v14; // r13
  int v15; // eax
  __int64 v16; // rax
  int v17; // r15d
  char v18; // cl
  unsigned int v19; // edx
  char v20; // di
  __int64 RdmaData; // rax
  __int64 v22; // rbx
  bool v23; // zf
  int v24; // edi
  char **v25; // rdx
  PVOID *v26; // rdx
  __int64 v27; // rdi
  __int64 v28; // rdx
  __int64 v29; // r8
  char **v30; // rdx
  int v31; // ebx
  __int64 v32; // [rsp+28h] [rbp-41h]
  __int64 v33; // [rsp+30h] [rbp-39h]
  int v34; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v35; // [rsp+54h] [rbp-15h]
  int v36; // [rsp+58h] [rbp-11h]
  int v37; // [rsp+5Ch] [rbp-Dh] BYREF
  unsigned int v38; // [rsp+60h] [rbp-9h] BYREF
  int v39; // [rsp+64h] [rbp-5h]
  __int64 v40; // [rsp+68h] [rbp-1h]
  __int64 WsaBuf; // [rsp+70h] [rbp+7h]
  char v42; // [rsp+D8h] [rbp+6Fh] BYREF
  int v43; // [rsp+E0h] [rbp+77h]
  int v44; // [rsp+E8h] [rbp+7Fh]

  v37 = 0;
  v35 = 0;
  v34 = 0;
  result = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)CompletionContext + 60);
  if ( (_DWORD)result == 1 )
  {
    while ( 1 )
    {
      if ( *((_DWORD *)CompletionContext + 65) )
      {
        _InterlockedExchange((volatile __int32 *)CompletionContext + 65, 0);
        HandleModeChange(CompletionContext);
        goto LABEL_104;
      }
      v3 = 0;
LABEL_5:
      v44 = v3;
      while ( 1 )
      {
        while ( 1 )
        {
          if ( v3 )
            goto LABEL_104;
          v4 = CompletionContext + 320;
          v5 = (char *)*((_QWORD *)CompletionContext + 40);
          if ( v5 == CompletionContext + 320 || (v6 = v5 - 16) == 0 )
          {
            v3 = 1;
            goto LABEL_5;
          }
          if ( !*((_DWORD *)v6 + 27) )
            break;
          if ( *((_DWORD *)CompletionContext + 120) == 2 && ++*((_DWORD *)CompletionContext + 123) == 300 )
            *(_QWORD *)(CompletionContext + 492) = 0;
LABEL_91:
          CompletePendingAppRecv(CompletionContext);
          v3 = v44;
        }
        if ( (CompletionContext[801] & 8) != 0 && *((_QWORD *)v6 + 15) )
          goto LABEL_104;
        if ( !*((_DWORD *)v6 + 9) )
          break;
        ContinueCancelBlockingReceive(CompletionContext);
        v3 = v44;
        if ( (_QWORD *)*v4 != v4 && v6 == (char *)(*v4 - 16LL) && *((_DWORD *)v6 + 9) )
          goto LABEL_104;
      }
      v7 = v6 + 60;
      NextMessage = FindNextMessage(CompletionContext, *((_DWORD *)v6 + 15) & 1, 0);
      v9 = NextMessage;
      v40 = NextMessage;
      if ( (BYTE1(xmmword_180063D60) & 0x10) != 0 )
      {
        WPP_SF_qq(1036, 109, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v6, NextMessage, v32, v33);
        v9 = v40;
      }
      v10 = 0;
      v11 = v6 + 40;
      v43 = 0;
      v12 = v6 + 80;
      while ( 1 )
      {
        v13 = v11;
        v14 = v12;
        if ( !v9 )
          goto LABEL_41;
        v11 = v6 + 40;
        v12 = v6 + 80;
        v13 = v6 + 40;
        v14 = v6 + 80;
        if ( *((_DWORD *)v6 + 20) <= (unsigned int)(v10 + *((_DWORD *)v6 + 10)) )
          goto LABEL_41;
        v35 = *(_DWORD *)(*(_QWORD *)(v9 + 96) + 8LL);
        v15 = DataAvailableDoRecv(
                CompletionContext,
                (__int64)&v37,
                (__int64)(v6 + 60),
                *((_QWORD *)v6 + 17),
                *((_DWORD *)v6 + 36),
                v9);
        v34 = v15;
        if ( v15 && v15 != 10036 )
        {
          CompletePendingAppRecv(CompletionContext);
          goto LABEL_104;
        }
        v43 += v37;
        if ( !*((_QWORD *)v6 + 17) && (v37 || !*v12) )
          break;
        if ( v15 == 10036 )
          break;
        if ( (*v7 & 2) != 0 && (v37 || !*v12) )
          goto LABEL_41;
        v16 = FindNextMessage(CompletionContext, *v7 & 1, 0);
        v10 = v43;
        v9 = v16;
        v40 = v16;
      }
      if ( (CompletionContext[801] & 8) == 0 && *((_DWORD *)CompletionContext + 120) == 2 )
      {
        if ( *((_QWORD *)v6 + 15) )
        {
          if ( ++*((_DWORD *)CompletionContext + 124) == 100 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
            CompletionContext[142] = 1;
            LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
            HandleFlowControlUponSmallRecvOrSelect(CompletionContext);
            v7 = v6 + 60;
          }
        }
      }
LABEL_41:
      v17 = v43;
      v18 = 0;
      *v13 += v43;
      v19 = v35;
      if ( v35 && *((_DWORD *)CompletionContext + 61) > v35 )
      {
        v20 = 0;
      }
      else
      {
        v20 = 1;
        v14 = v6 + 80;
      }
      if ( *v14 <= *v13 )
        goto LABEL_85;
      if ( (CompletionContext[801] & 8) == 0 )
        break;
      if ( !*((_QWORD *)v6 + 17) && (unsigned int)UseRdma((unsigned int)*v14) && (*(_BYTE *)v7 & 2) == 0 )
      {
        v36 = 1;
        goto LABEL_53;
      }
      v36 = 0;
LABEL_82:
      if ( !v17 )
      {
        HandleFlowControlUponSmallRecvOrSelect(CompletionContext);
        goto LABEL_84;
      }
      if ( !v19
        || *((_DWORD *)CompletionContext + 61) != v19
        || (EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48)),
            v31 = PopLargeSendFCInfoExt(CompletionContext, 0, 0, 0),
            LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48)),
            v31 != 2) )
      {
LABEL_84:
        v18 = 0;
        goto LABEL_85;
      }
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_(1025, 110, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids);
      SendControlMessage(CompletionContext, 0, 0);
      v18 = 0;
LABEL_100:
      if ( !v36 )
      {
LABEL_85:
        if ( !*((_DWORD *)CompletionContext + 120) )
          *((_DWORD *)CompletionContext + 53) = 1;
      }
      if ( !v18 )
      {
LABEL_88:
        if ( v17 || !*v14 && v40 )
          goto LABEL_91;
      }
LABEL_104:
      result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)CompletionContext + 60, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
        return result;
    }
    v36 = OKForRdmaRecv(
            *((_QWORD *)v6 + 17),
            *((_QWORD *)v6 + 6),
            *((_DWORD *)v6 + 14),
            (_DWORD)v7,
            0,
            *((_DWORD *)CompletionContext + 120),
            (__int64)&v42);
    if ( !v36 )
    {
      v19 = v35;
      goto LABEL_82;
    }
LABEL_53:
    if ( *((_QWORD *)v6 + 15) )
      goto LABEL_88;
    v39 = *((_DWORD *)CompletionContext + 114);
    v38 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
    RdmaData = GetRdmaData(CompletionContext);
    v22 = RdmaData;
    if ( !RdmaData )
    {
LABEL_61:
      LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
      goto LABEL_91;
    }
    v23 = (CompletionContext[801] & 8) == 0;
    v42 = 0;
    WsaBuf = 0;
    if ( !v23 )
    {
      if ( v20 )
      {
        v24 = PopLargeSendFCInfoExt(CompletionContext, &v38, *(_QWORD *)(RdmaData + 96), 0);
        if ( v24 == 2 )
        {
          WsaBuf = GetWsaBufExArray(CompletionContext, *((unsigned int *)v6 + 14));
          if ( !WsaBuf )
          {
            *(_DWORD *)v22 = 1145324612;
            v25 = (char **)*((_QWORD *)CompletionContext + 97);
            if ( *v25 == CompletionContext + 768 )
            {
              *(_QWORD *)(v22 + 40) = CompletionContext + 768;
              *(_QWORD *)(v22 + 48) = v25;
              *v25 = (char *)(v22 + 40);
              *((_QWORD *)CompletionContext + 97) = v22 + 40;
              goto LABEL_61;
            }
LABEL_106:
            __fastfail(3u);
          }
LABEL_65:
          LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
          if ( (CompletionContext[801] & 8) != 0 )
          {
            if ( v24 == 2 )
            {
              v27 = WsaBuf;
              v28 = v38;
              v29 = WsaBuf;
              *(_QWORD *)(v22 + 64) = v6;
              *(_QWORD *)(v22 + 56) = CompletionContext;
              if ( (unsigned int)StartRdmaRead(v22, v28, v29, &v34) == -1 && v34 != 997 )
              {
                EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
                *(_DWORD *)v22 = 1145324612;
                v30 = (char **)*((_QWORD *)CompletionContext + 97);
                if ( *v30 == CompletionContext + 768 )
                {
                  *(_QWORD *)(v22 + 40) = CompletionContext + 768;
                  *(_QWORD *)(v22 + 48) = v30;
                  *v30 = (char *)(v22 + 40);
                  *((_QWORD *)CompletionContext + 97) = v22 + 40;
                  ReleaseWsaBufExArray(CompletionContext, v27);
                  *((_QWORD *)v6 + 15) = 0;
                  LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
                  goto LABEL_91;
                }
                goto LABEL_106;
              }
              goto LABEL_80;
            }
          }
          else if ( v42 )
          {
            SetupLargeReceive((_DWORD)CompletionContext, (_DWORD)v6, *v13, v39, v22);
LABEL_80:
            v18 = 1;
LABEL_99:
            v17 = v43;
            goto LABEL_100;
          }
          v18 = 0;
          goto LABEL_99;
        }
      }
      else
      {
        v24 = 0;
      }
LABEL_63:
      *(_DWORD *)v22 = 1145324612;
      v26 = (PVOID *)*((_QWORD *)CompletionContext + 97);
      if ( *v26 != CompletionContext + 768 )
        goto LABEL_106;
      *(_QWORD *)(v22 + 40) = CompletionContext + 768;
      *(_QWORD *)(v22 + 48) = v26;
      *v26 = (PVOID)(v22 + 40);
      *((_QWORD *)CompletionContext + 97) = v22 + 40;
      goto LABEL_65;
    }
    if ( v20 )
    {
      v24 = PopLargeSendFCInfoExt(CompletionContext, 0, 0, 0);
      if ( v24 == 2 )
        goto LABEL_77;
    }
    else
    {
      v24 = 0;
    }
    if ( *((_DWORD *)CompletionContext + 120) != 2 || v43 )
      goto LABEL_63;
LABEL_77:
    v42 = 1;
    goto LABEL_65;
  }
  return result;
}

```

## disassembly

```asm
0x18003cdc8  push    rbp
0x18003cdca  push    rbx
0x18003cdcb  push    rsi
0x18003cdcc  push    rdi
0x18003cdcd  push    r12
0x18003cdcf  push    r13
0x18003cdd1  push    r14
0x18003cdd3  push    r15
0x18003cdd5  lea     rbp, [rsp-1Fh]
0x18003cdda  sub     rsp, 88h
0x18003cde1  xor     eax, eax
0x18003cde3  mov     [rbp+57h+var_64], 0
0x18003cdea  mov     [rbp+57h+var_6C], eax
0x18003cded  mov     rsi, rcx
0x18003cdf0  mov     eax, 1
0x18003cdf5  mov     [rbp+57h+var_70], 0
0x18003cdfc  lock xadd [rcx+0F0h], eax
0x18003ce04  inc     eax
0x18003ce06  cmp     eax, 1
0x18003ce09  jnz     loc_18003D45C
0x18003ce0f  cmp     dword ptr [rsi+104h], 0
0x18003ce16  jz      short loc_18003CE35
0x18003ce18  xor     eax, eax
0x18003ce1a  mov     edx, 2
0x18003ce1f  xchg    eax, [rsi+104h]
0x18003ce25  mov     r8d, edx
0x18003ce28  mov     rcx, rsi
0x18003ce2b  call    HandleModeChange
0x18003ce30  jmp     loc_18003D448
0x18003ce35  xor     ecx, ecx
0x18003ce37  mov     [rbp+57h+arg_18], ecx
0x18003ce3a  test    ecx, ecx
0x18003ce3c  jnz     loc_18003D448
0x18003ce42  lea     rbx, [rsi+140h]
0x18003ce49  mov     r14, [rbx]
0x18003ce4c  cmp     r14, rbx
0x18003ce4f  jz      loc_18003D430
0x18003ce55  add     r14, 0FFFFFFFFFFFFFFF0h
0x18003ce59  jz      loc_18003D430
0x18003ce5f  cmp     [r14+6Ch], ecx
0x18003ce63  jz      short loc_18003CE94
0x18003ce65  cmp     dword ptr [rsi+1E0h], 2
0x18003ce6c  jnz     short loc_18003CE8B
0x18003ce6e  inc     dword ptr [rsi+1ECh]
0x18003ce74  cmp     dword ptr [rsi+1ECh], 12Ch
0x18003ce7e  jnz     short loc_18003CE8B
0x18003ce80  mov     qword ptr [rsi+1ECh], 0
0x18003ce8b  mov     r8d, [r14+20h]
0x18003ce8f  jmp     loc_18003D37D
0x18003ce94  test    byte ptr [rsi+321h], 8
0x18003ce9b  jz      short loc_18003CEA8
0x18003ce9d  cmp     qword ptr [r14+78h], 0
0x18003cea2  jnz     loc_18003D448
0x18003cea8  cmp     dword ptr [r14+24h], 0
0x18003cead  mov     rcx, rsi; CompletionContext
0x18003ceb0  jz      short loc_18003CEE6
0x18003ceb2  mov     rdx, r14
0x18003ceb5  call    ContinueCancelBlockingReceive
0x18003ceba  mov     rax, [rbx]
0x18003cebd  mov     ecx, [rbp+57h+arg_18]
0x18003cec0  cmp     rax, rbx
0x18003cec3  jz      loc_18003CE3A
0x18003cec9  add     rax, 0FFFFFFFFFFFFFFF0h
0x18003cecd  cmp     r14, rax
0x18003ced0  jnz     loc_18003CE3A
0x18003ced6  cmp     dword ptr [r14+24h], 0
0x18003cedb  jnz     loc_18003D448
0x18003cee1  jmp     loc_18003CE3A
0x18003cee6  lea     rbx, [r14+3Ch]
0x18003ceea  xor     r8d, r8d
0x18003ceed  mov     edx, [rbx]
0x18003ceef  and     edx, 1
0x18003cef2  call    FindNextMessage
0x18003cef7  mov     r8, rax
0x18003cefa  mov     [rbp+57h+var_58], rax
0x18003cefe  test    byte ptr cs:xmmword_180063D60+1, 10h
0x18003cf05  jz      short loc_18003CF29
0x18003cf07  mov     edx, 6Dh ; 'm'
0x18003cf0c  mov     [rsp+0C0h+var_A0], rax
0x18003cf11  mov     ecx, 40Ch
0x18003cf16  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18003cf1d  mov     r9, r14
0x18003cf20  call    WPP_SF_qq
0x18003cf25  mov     r8, [rbp+57h+var_58]
0x18003cf29  xor     edx, edx
0x18003cf2b  lea     r15, [r14+28h]
0x18003cf2f  mov     [rbp+57h+arg_10], edx
0x18003cf32  lea     rdi, [r14+50h]
0x18003cf36  mov     r12, r15
0x18003cf39  mov     r13, rdi
0x18003cf3c  test    r8, r8
0x18003cf3f  jz      loc_18003D05E
0x18003cf45  lea     r15, [r14+28h]
0x18003cf49  mov     r9d, [r15]
0x18003cf4c  lea     rdi, [r14+50h]
0x18003cf50  add     r9d, edx
0x18003cf53  mov     r12, r15
0x18003cf56  mov     r13, rdi
0x18003cf59  cmp     [rdi], r9d
0x18003cf5c  jbe     loc_18003D05E
0x18003cf62  mov     rax, [r8+60h]
0x18003cf66  mov     rcx, rsi
0x18003cf69  mov     rdx, [r14+30h]
0x18003cf6d  mov     [rsp+0C0h+var_80], r8
0x18003cf72  mov     r8d, [r14+38h]
0x18003cf76  mov     eax, [rax+8]
0x18003cf79  mov     [rbp+57h+var_6C], eax
0x18003cf7c  mov     eax, [r14+90h]
0x18003cf83  mov     [rsp+0C0h+var_88], eax
0x18003cf87  mov     rax, [r14+88h]
0x18003cf8e  mov     [rsp+0C0h+var_90], rax
0x18003cf93  lea     rax, [rbp+57h+var_64]
0x18003cf97  mov     [rsp+0C0h+var_98], rbx
0x18003cf9c  mov     [rsp+0C0h+var_A0], rax
0x18003cfa1  call    DataAvailableDoRecv
0x18003cfa6  mov     [rbp+57h+var_70], eax
0x18003cfa9  test    eax, eax
0x18003cfab  jz      short loc_18003CFB8
0x18003cfad  cmp     eax, 2734h
0x18003cfb2  jnz     loc_18003D43A
0x18003cfb8  mov     ecx, [rbp+57h+var_64]
0x18003cfbb  add     [rbp+57h+arg_10], ecx
0x18003cfbe  cmp     qword ptr [r14+88h], 0
0x18003cfc6  jnz     short loc_18003CFD0
0x18003cfc8  test    ecx, ecx
0x18003cfca  jnz     short loc_18003D003
0x18003cfcc  cmp     [rdi], ecx
0x18003cfce  jz      short loc_18003D003
0x18003cfd0  cmp     eax, 2734h
0x18003cfd5  jz      short loc_18003D003
0x18003cfd7  mov     edx, [rbx]
0x18003cfd9  test    dl, 2
0x18003cfdc  jz      short loc_18003CFE6
0x18003cfde  test    ecx, ecx
0x18003cfe0  jnz     short loc_18003D05E
0x18003cfe2  cmp     [rdi], ecx
0x18003cfe4  jz      short loc_18003D05E
0x18003cfe6  and     edx, 1
0x18003cfe9  xor     r8d, r8d
0x18003cfec  mov     rcx, rsi
0x18003cfef  call    FindNextMessage
0x18003cff4  mov     edx, [rbp+57h+arg_10]
0x18003cff7  mov     r8, rax
0x18003cffa  mov     [rbp+57h+var_58], rax
0x18003cffe  jmp     loc_18003CF36
0x18003d003  test    byte ptr [rsi+321h], 8
0x18003d00a  jnz     short loc_18003D05E
0x18003d00c  cmp     dword ptr [rsi+1E0h], 2
0x18003d013  jnz     short loc_18003D05E
0x18003d015  cmp     qword ptr [r14+78h], 0
0x18003d01a  jz      short loc_18003D05E
0x18003d01c  inc     dword ptr [rsi+1F0h]
0x18003d022  cmp     dword ptr [rsi+1F0h], 64h ; 'd'
0x18003d029  jnz     short loc_18003D05E
0x18003d02b  lea     rcx, [rsi+30h]; lpCriticalSection
0x18003d02f  call    cs:__imp_EnterCriticalSection
0x18003d036  nop     dword ptr [rax+rax+00h]
0x18003d03b  lea     rcx, [rsi+30h]; lpCriticalSection
0x18003d03f  mov     byte ptr [rsi+8Eh], 1
0x18003d046  call    cs:__imp_LeaveCriticalSection
0x18003d04d  nop     dword ptr [rax+rax+00h]
0x18003d052  mov     rcx, rsi
0x18003d055  call    HandleFlowControlUponSmallRecvOrSelect
0x18003d05a  lea     rbx, [r14+3Ch]
0x18003d05e  mov     r15d, [rbp+57h+arg_10]
0x18003d062  xor     cl, cl
0x18003d064  add     [r12], r15d
0x18003d068  mov     edx, [rbp+57h+var_6C]
0x18003d06b  mov     eax, [r12]
0x18003d06f  mov     [rbp+57h+arg_0], cl
0x18003d072  test    edx, edx
0x18003d074  jz      short loc_18003D083
0x18003d076  cmp     [rsi+0F4h], edx
0x18003d07c  jbe     short loc_18003D083
0x18003d07e  xor     dil, dil
0x18003d081  jmp     short loc_18003D08A
0x18003d083  mov     dil, 1
0x18003d086  lea     r13, [r14+50h]
0x18003d08a  cmp     [r13+0], eax
0x18003d08e  jle     loc_18003D345
0x18003d094  test    byte ptr [rsi+321h], 8
0x18003d09b  jz      short loc_18003D0CE
0x18003d09d  cmp     qword ptr [r14+88h], 0
0x18003d0a5  jnz     short loc_18003D0C2
0x18003d0a7  mov     ecx, [r13+0]
0x18003d0ab  call    UseRdma
0x18003d0b0  test    eax, eax
0x18003d0b2  jz      short loc_18003D0C2
0x18003d0b4  test    byte ptr [rbx], 2
0x18003d0b7  jnz     short loc_18003D0C2
0x18003d0b9  mov     [rbp+57h+var_68], 1
0x18003d0c0  jmp     short loc_18003D10B
0x18003d0c2  mov     [rbp+57h+var_68], 0
0x18003d0c9  jmp     loc_18003D335
0x18003d0ce  mov     r8d, [r14+38h]
0x18003d0d2  lea     rax, [rbp+57h+arg_8]
0x18003d0d6  mov     rdx, [r14+30h]
0x18003d0da  mov     r9, rbx
0x18003d0dd  mov     rcx, [r14+88h]
0x18003d0e4  mov     [rsp+0C0h+var_90], rax
0x18003d0e9  mov     eax, [rsi+1E0h]
0x18003d0ef  mov     dword ptr [rsp+0C0h+var_98], eax
0x18003d0f3  mov     dword ptr [rsp+0C0h+var_A0], 0
0x18003d0fb  call    OKForRdmaRecv
0x18003d100  mov     [rbp+57h+var_68], eax
0x18003d103  test    eax, eax
0x18003d105  jz      loc_18003D332
0x18003d10b  cmp     qword ptr [r14+78h], 0
0x18003d110  jnz     loc_18003D360
0x18003d116  mov     eax, [rsi+1C8h]
0x18003d11c  lea     r15, [rsi+30h]
0x18003d120  mov     rcx, r15; lpCriticalSection
0x18003d123  mov     [rbp+57h+var_5C], eax
0x18003d126  mov     [rbp+57h+var_60], 0
0x18003d12d  call    cs:__imp_EnterCriticalSection
0x18003d134  nop     dword ptr [rax+rax+00h]
0x18003d139  mov     rcx, rsi
0x18003d13c  call    GetRdmaData
0x18003d141  mov     rbx, rax
0x18003d144  test    rax, rax
0x18003d147  jz      short loc_18003D1C2
0x18003d149  test    byte ptr [rsi+321h], 8
0x18003d150  mov     [rbp+57h+arg_8], 0
0x18003d154  mov     [rbp+57h+var_50], 0
0x18003d15c  jz      loc_18003D2C9
0x18003d162  test    dil, dil
0x18003d165  jz      short loc_18003D1DC
0x18003d167  mov     r8, [rax+60h]
0x18003d16b  lea     rdx, [rbp+57h+var_60]
0x18003d16f  xor     r9d, r9d
0x18003d172  mov     rcx, rsi
0x18003d175  call    PopLargeSendFCInfoExt
0x18003d17a  mov     edi, eax
0x18003d17c  cmp     eax, 2
0x18003d17f  jnz     short loc_18003D1DE
0x18003d181  mov     edx, [r14+38h]
0x18003d185  mov     rcx, rsi
0x18003d188  call    GetWsaBufExArray
0x18003d18d  mov     [rbp+57h+var_50], rax
0x18003d191  test    rax, rax
0x18003d194  jnz     short loc_18003D20A
0x18003d196  lea     rcx, [rsi+300h]
0x18003d19d  mov     dword ptr [rbx], 44444444h
0x18003d1a3  mov     rdx, [rcx+8]
0x18003d1a7  cmp     [rdx], rcx
0x18003d1aa  jnz     loc_18003D471
0x18003d1b0  lea     rax, [rbx+28h]
0x18003d1b4  mov     [rax], rcx
0x18003d1b7  mov     [rax+8], rdx
0x18003d1bb  mov     [rdx], rax
0x18003d1be  mov     [rcx+8], rax
0x18003d1c2  mov     rcx, r15; lpCriticalSection
0x18003d1c5  call    cs:__imp_LeaveCriticalSection
0x18003d1cc  nop     dword ptr [rax+rax+00h]
0x18003d1d1  mov     r8d, 2747h
0x18003d1d7  jmp     loc_18003D37D
0x18003d1dc  xor     edi, edi
0x18003d1de  lea     rcx, [rsi+300h]
0x18003d1e5  mov     dword ptr [rbx], 44444444h
0x18003d1eb  mov     rdx, [rcx+8]
0x18003d1ef  cmp     [rdx], rcx
0x18003d1f2  jnz     loc_18003D471
0x18003d1f8  lea     rax, [rbx+28h]
0x18003d1fc  mov     [rax], rcx
0x18003d1ff  mov     [rax+8], rdx
0x18003d203  mov     [rdx], rax
0x18003d206  mov     [rcx+8], rax
0x18003d20a  mov     rcx, r15; lpCriticalSection
0x18003d20d  call    cs:__imp_LeaveCriticalSection
0x18003d214  nop     dword ptr [rax+rax+00h]
0x18003d219  test    byte ptr [rsi+321h], 8
0x18003d220  jz      loc_18003D309
0x18003d226  cmp     edi, 2
0x18003d229  jnz     loc_18003D41A
0x18003d22f  mov     rdi, [rbp+57h+var_50]
0x18003d233  lea     r9, [rbp+57h+var_70]
0x18003d237  mov     edx, [rbp+57h+var_60]
0x18003d23a  mov     r8, rdi
0x18003d23d  mov     rcx, rbx
0x18003d240  mov     [rbx+40h], r14
0x18003d244  mov     [rbx+38h], rsi
0x18003d248  call    StartRdmaRead
0x18003d24d  cmp     eax, 0FFFFFFFFh
0x18003d250  jnz     loc_18003D32B
0x18003d256  cmp     [rbp+57h+var_70], 3E5h
0x18003d25d  jz      loc_18003D32B
0x18003d263  mov     rcx, r15; lpCriticalSection
0x18003d266  call    cs:__imp_EnterCriticalSection
0x18003d26d  nop     dword ptr [rax+rax+00h]
0x18003d272  lea     rcx, [rsi+300h]
0x18003d279  mov     dword ptr [rbx], 44444444h
0x18003d27f  mov     rdx, [rcx+8]
0x18003d283  cmp     [rdx], rcx
0x18003d286  jnz     loc_18003D471
0x18003d28c  lea     rax, [rbx+28h]
0x18003d290  mov     [rax], rcx
0x18003d293  mov     [rax+8], rdx
0x18003d297  mov     [rdx], rax
0x18003d29a  mov     rdx, rdi
0x18003d29d  mov     [rcx+8], rax
  ... truncated ...
```
