# PortReceive

- ea: `0x180023f00`
- end: `0x1800244f6`
- name: `PortReceive`
- size: `1526`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024500`
- `0x180028a0c`

## callees

- `0x180005a20`
- `0x180005ad8`
- `0x180005bcc`
- `0x180005bfc`
- `0x180005cf8`
- `0x18000c3c0`
- `0x180014f0c`
- `0x180023f00`
- `0x18002b290`
- `0x180038b8c`
- `0x180049944`
- `0x1800499f0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023fd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800241bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023fd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800241bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002400d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002400d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002438d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002438d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023ff2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023ff2`

## pseudocode

```c
struct _LIST_ENTRY **__fastcall PortReceive(__int64 a1, _DWORD *a2, DWORD *a3, int a4)
{
  DWORD *v5; // r14
  struct _LIST_ENTRY *v8; // rcx
  DWORD v9; // esi
  DWORD LastError; // edi
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  char *v14; // rax
  char *v15; // rbp
  unsigned __int16 v16; // r12
  DWORD v17; // eax
  unsigned __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  struct _LIST_ENTRY *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // r9
  char *v24; // rsi
  int v25; // ecx
  struct _LIST_ENTRY *v26; // rcx
  __int64 v27; // r8
  struct _LIST_ENTRY **result; // rax

  v5 = a3;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 398, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( a2 && *a2 )
    v9 = a2[2];
  else
    v9 = v5[4];
  if ( !a1 )
  {
    if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v8[1].Blink) & 0x2000) != 0
      && BYTE1(v8[1].Blink) >= 2u )
    {
      WPP_SF_(v8[1].Flink, 400, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      goto LABEL_95;
    }
LABEL_96:
    LastError = 618;
    if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v8[1].Blink) & 0x2000) != 0
      && BYTE1(v8[1].Blink) >= 2u )
    {
      WPP_SF_(v8[1].Flink, 401, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
    }
    goto LABEL_100;
  }
  if ( *(_DWORD *)(a1 + 24) == 2 )
  {
    if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v8[1].Blink) & 0x2000) != 0
      && BYTE1(v8[1].Blink) >= 2u )
    {
      WPP_SF_q(v8[1].Flink, 399, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, *(_QWORD *)a1);
LABEL_95:
      v8 = WPP_GLOBAL_Control;
      goto LABEL_96;
    }
    goto LABEL_96;
  }
  if ( *(_DWORD *)(a1 + 24) )
  {
    LastError = 618;
    goto LABEL_100;
  }
  if ( *(_DWORD *)(a1 + 472) && *(_DWORD *)(a1 + 28) != 2
    || (v11 = *(_DWORD *)(a1 + 1224), (v11 & 2) != 0)
    || !a4 && (v11 & 4) != 0 )
  {
    if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v8[1].Blink) & 0x2000) != 0
      && BYTE1(v8[1].Blink) >= 4u )
    {
      WPP_SF_s(v8[1].Flink, 402, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, a1 + 8);
    }
    LastError = 616;
  }
  else
  {
    if ( v9 == GetCurrentProcessId() || a4 )
    {
      v15 = (char *)*((_QWORD *)v5 + 3);
      if ( !a4 )
        *(_DWORD *)(a1 + 1224) = 0;
    }
    else
    {
      v14 = (char *)LocalAlloc(0x40u, 0x608u);
      *(_QWORD *)(a1 + 528) = v14;
      v15 = v14;
      if ( !v14 )
      {
        LastError = GetLastError();
        goto LABEL_100;
      }
      *(_DWORD *)(a1 + 1224) = 1;
    }
    if ( *(_DWORD *)(a1 + 28) == 2 )
    {
      v16 = 26;
      v17 = CompleteReceiveIfPending(a1, v15, 7);
    }
    else
    {
      if ( *(_DWORD *)(a1 + 28) == 4 )
      {
        SetPortConnState(v13, v12, a1, 0);
        LastError = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(a1 + 48) + 136LL))(*(_QWORD *)(a1 + 216));
        if ( LastError )
          goto LABEL_100;
      }
      if ( v5[1] != -1 )
      {
        v18 = 1000LL * v5[1];
        if ( v18 > 0xFFFFFFFF )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 403, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, 2147942934LL);
          }
          goto LABEL_56;
        }
        v5[1] = v18;
      }
      v19 = *(_QWORD *)(a1 + 48);
      v20 = *(_QWORD *)(a1 + 216);
      v16 = 7;
      *(_DWORD *)(a1 + 536) = 0;
      v17 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, _QWORD))(v19 + 128))(v20, v15 + 32, *v5, v5[1]);
    }
    LastError = v17;
    if ( v17 == 997 )
      LastError = 600;
    *(_DWORD *)(a1 + 264) = LastError;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 404, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, LastError);
      v21 = WPP_GLOBAL_Control;
    }
    if ( LastError )
    {
      if ( LastError != 600 )
        goto LABEL_100;
      if ( v21 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v21[1].Blink) & 0x2000) != 0
        && BYTE1(v21[1].Blink) >= 5u )
      {
        WPP_SF_(v21[1].Flink, 405, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      }
      v22 = ValidateHandleForRasman(*((HANDLE *)v5 + 1), v9);
      *(_QWORD *)(a1 + 464) = v22;
      if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        SetPortAsyncReqType("onecoreuap\\net\\rras\\ras\\rasman\\rasman\\request.c", 6237, a1, v16);
        if ( !a4 && v9 == GetCurrentProcessId() )
          *(_QWORD *)(a1 + 528) = v15;
        if ( v16 == 26 )
        {
          v23 = v5[1];
          if ( (unsigned int)(v23 - 1) <= 0xFFFFFFFD )
            *(_QWORD *)(a1 + 480) = AddTimeoutElement(HubReceiveTimeout, a1, 0, v23);
        }
        goto LABEL_100;
      }
LABEL_56:
      LastError = -2147024809;
      goto LABEL_100;
    }
    if ( v21 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v21[1].Blink) & 0x2000) != 0
      && BYTE1(v21[1].Blink) >= 5u )
    {
      WPP_SF_(v21[1].Flink, 406, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
    }
    if ( v16 == 7 )
      *(_DWORD *)(a1 + 536) = 0;
    v24 = (char *)ValidateHandleForRasman(*((HANDLE *)v5 + 1), v9);
    if ( (unsigned __int64)(v24 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_56;
    v25 = *(_DWORD *)(a1 + 1224);
    if ( (v25 & 1) != 0 )
    {
      *(_DWORD *)(a1 + 1224) = v25 | 2;
      *(_QWORD *)(a1 + 480) = AddTimeoutElement(OutOfProcessReceiveTimeout, a1, 0, 15000);
    }
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
    {
      WPP_SF_s(WPP_GLOBAL_Control[1].Flink, 407, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, a1 + 8);
      v26 = WPP_GLOBAL_Control;
    }
    if ( (*(_BYTE *)(a1 + 1224) & 4) != 0 )
    {
      while ( 1 )
      {
        if ( v26 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v26[1].Blink) & 0x2000) != 0
          && BYTE1(v26[1].Blink) >= 4u )
        {
          WPP_SF_s(v26[1].Flink, 408, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, a1 + 8);
        }
        SendReceivedPacketToProtocolEngine(a1, v15 + 8);
        LastError = CompleteReceiveIfPending(a1, v15, v27);
        if ( LastError )
          break;
        v26 = WPP_GLOBAL_Control;
      }
      v5 = a3;
    }
    SetEvent(v24);
    if ( !a4 )
    {
      if ( (*(_DWORD *)(a1 + 1224) & 1) != 0 )
      {
        SetPortAsyncReqType("onecoreuap\\net\\rras\\ras\\rasman\\rasman\\request.c", 6315, a1, v16);
        *(_QWORD *)(a1 + 464) = v24;
      }
      else
      {
        FreeNotifierHandle(v24);
      }
    }
  }
LABEL_100:
  *v5 = LastError;
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    return (struct _LIST_ENTRY **)WPP_SF_d(
                                    WPP_GLOBAL_Control[1].Flink,
                                    409,
                                    WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                                    LastError);
  }
  return result;
}

```

## disassembly

```asm
0x180023f00  mov     [rsp+arg_10], r8
0x180023f05  push    rbx
0x180023f06  push    rbp
0x180023f07  push    rsi
0x180023f08  push    rdi
0x180023f09  push    r12
0x180023f0b  push    r13
0x180023f0d  push    r14
0x180023f0f  push    r15
0x180023f11  sub     rsp, 38h
0x180023f15  mov     r13d, r9d
0x180023f18  mov     r14, r8
0x180023f1b  mov     rdi, rdx
0x180023f1e  mov     rbx, rcx
0x180023f21  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f28  lea     rdx, WPP_GLOBAL_Control
0x180023f2f  cmp     rcx, rdx
0x180023f32  jz      short loc_180023F66
0x180023f34  test    dword ptr [rcx+1Ch], 2000h
0x180023f3b  jz      short loc_180023F66
0x180023f3d  cmp     byte ptr [rcx+19h], 6
0x180023f41  jb      short loc_180023F66
0x180023f43  mov     rcx, [rcx+10h]
0x180023f47  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180023f4e  mov     edx, 18Eh
0x180023f53  call    WPP_SF_
0x180023f58  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f5f  lea     rdx, WPP_GLOBAL_Control
0x180023f66  xor     r15d, r15d
0x180023f69  test    rdi, rdi
0x180023f6c  jz      short loc_180023F78
0x180023f6e  cmp     [rdi], r15d
0x180023f71  jz      short loc_180023F78
0x180023f73  mov     esi, [rdi+8]
0x180023f76  jmp     short loc_180023F7C
0x180023f78  mov     esi, [r14+10h]
0x180023f7c  mov     r12d, 2
0x180023f82  test    rbx, rbx
0x180023f85  jz      loc_180024442
0x180023f8b  cmp     [rbx+18h], r12d
0x180023f8f  jz      loc_180024414
0x180023f95  cmp     [rbx+18h], r15d
0x180023f99  jz      short loc_180023FA5
0x180023f9b  mov     edi, 26Ah
0x180023fa0  jmp     loc_1800244A7
0x180023fa5  cmp     [rbx+1D8h], r15d
0x180023fac  jz      short loc_180023FB8
0x180023fae  cmp     [rbx+1Ch], r12d
0x180023fb2  jnz     loc_1800243DD
0x180023fb8  mov     eax, [rbx+4C8h]
0x180023fbe  test    r12b, al
0x180023fc1  jnz     loc_1800243DD
0x180023fc7  test    r13d, r13d
0x180023fca  jnz     short loc_180023FD4
0x180023fcc  test    al, 4
0x180023fce  jnz     loc_1800243DD
0x180023fd4  call    cs:__imp_GetCurrentProcessId
0x180023fdb  nop     dword ptr [rax+rax+00h]
0x180023fe0  cmp     esi, eax
0x180023fe2  jz      short loc_18002402C
0x180023fe4  test    r13d, r13d
0x180023fe7  jnz     short loc_18002402C
0x180023fe9  mov     edx, 608h; uBytes
0x180023fee  lea     ecx, [r13+40h]; uFlags
0x180023ff2  call    cs:__imp_LocalAlloc
0x180023ff9  nop     dword ptr [rax+rax+00h]
0x180023ffe  mov     [rbx+210h], rax
0x180024005  mov     rbp, rax
0x180024008  test    rax, rax
0x18002400b  jnz     short loc_180024020
0x18002400d  call    cs:__imp_GetLastError
0x180024014  nop     dword ptr [rax+rax+00h]
0x180024019  mov     edi, eax
0x18002401b  jmp     loc_1800244A7
0x180024020  mov     dword ptr [rbx+4C8h], 1
0x18002402a  jmp     short loc_18002403C
0x18002402c  mov     rbp, [r14+18h]
0x180024030  test    r13d, r13d
0x180024033  jnz     short loc_18002403C
0x180024035  mov     [rbx+4C8h], r15d
0x18002403c  mov     eax, 1Ah
0x180024041  lea     r8d, [rax-13h]
0x180024045  cmp     [rbx+1Ch], r12d
0x180024049  jnz     short loc_18002405F
0x18002404b  mov     rdx, rbp
0x18002404e  mov     rcx, rbx
0x180024051  movzx   r12d, ax
0x180024055  call    CompleteReceiveIfPending
0x18002405a  jmp     loc_1800240E4
0x18002405f  cmp     dword ptr [rbx+1Ch], 4
0x180024063  jnz     short loc_180024095
0x180024065  xor     r9d, r9d
0x180024068  mov     r8, rbx
0x18002406b  call    SetPortConnState
0x180024070  mov     rax, [rbx+30h]
0x180024074  mov     rcx, [rbx+0D8h]
0x18002407b  mov     rax, [rax+88h]
0x180024082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024087  mov     edi, eax
0x180024089  test    eax, eax
0x18002408b  jnz     loc_1800244A7
0x180024091  lea     r8d, [rax+7]
0x180024095  mov     edx, 0FFFFFFFFh
0x18002409a  cmp     [r14+4], edx
0x18002409e  jz      short loc_1800240B8
0x1800240a0  mov     eax, [r14+4]
0x1800240a4  imul    rcx, rax, 3E8h
0x1800240ab  cmp     rcx, rdx
0x1800240ae  ja      loc_180024210
0x1800240b4  mov     [r14+4], ecx
0x1800240b8  mov     rax, [rbx+30h]
0x1800240bc  lea     rdx, [rbp+20h]
0x1800240c0  mov     rcx, [rbx+0D8h]
0x1800240c7  mov     r12d, r8d
0x1800240ca  mov     [rbx+218h], r15d
0x1800240d1  mov     r9d, [r14+4]
0x1800240d5  mov     rax, [rax+80h]
0x1800240dc  mov     r8d, [r14]
0x1800240df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240e4  cmp     eax, 3E5h
0x1800240e9  mov     edi, eax
0x1800240eb  mov     edx, 258h
0x1800240f0  cmovz   edi, edx
0x1800240f3  mov     [rbx+108h], edi
0x1800240f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180024100  lea     rax, WPP_GLOBAL_Control
0x180024107  cmp     rcx, rax
0x18002410a  jz      short loc_180024146
0x18002410c  test    dword ptr [rcx+1Ch], 2000h
0x180024113  jz      short loc_180024146
0x180024115  cmp     byte ptr [rcx+19h], 5
0x180024119  jb      short loc_180024146
0x18002411b  mov     rcx, [rcx+10h]
0x18002411f  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180024126  mov     edx, 194h
0x18002412b  mov     r9d, edi
0x18002412e  call    WPP_SF_d
0x180024133  mov     rcx, cs:WPP_GLOBAL_Control
0x18002413a  lea     rax, WPP_GLOBAL_Control
0x180024141  mov     edx, 258h
0x180024146  test    edi, edi
0x180024148  jz      loc_180024257
0x18002414e  cmp     edi, edx
0x180024150  jnz     loc_1800244A7
0x180024156  cmp     rcx, rax
0x180024159  jz      short loc_18002417F
0x18002415b  test    dword ptr [rcx+1Ch], 2000h
0x180024162  jz      short loc_18002417F
0x180024164  cmp     byte ptr [rcx+19h], 5
0x180024168  jb      short loc_18002417F
0x18002416a  mov     rcx, [rcx+10h]
0x18002416e  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180024175  mov     edx, 195h
0x18002417a  call    WPP_SF_
0x18002417f  mov     rcx, [r14+8]; hSourceHandle
0x180024183  mov     edx, esi; dwProcessId
0x180024185  call    ValidateHandleForRasman
0x18002418a  mov     [rbx+1D0h], rax
0x180024191  dec     rax
0x180024194  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024198  ja      loc_18002424D
0x18002419e  movzx   r9d, r12w
0x1800241a2  lea     rcx, aOnecoreuapNetR_2; "onecoreuap\\net\\rras\\ras\\rasman\\ras"...
0x1800241a9  mov     r8, rbx
0x1800241ac  mov     edx, 185Dh
0x1800241b1  call    SetPortAsyncReqType
0x1800241b6  test    r13d, r13d
0x1800241b9  jnz     short loc_1800241D2
0x1800241bb  call    cs:__imp_GetCurrentProcessId
0x1800241c2  nop     dword ptr [rax+rax+00h]
0x1800241c7  cmp     esi, eax
0x1800241c9  jnz     short loc_1800241D2
0x1800241cb  mov     [rbx+210h], rbp
0x1800241d2  mov     eax, 1Ah
0x1800241d7  cmp     r12w, ax
0x1800241db  jnz     loc_1800244A7
0x1800241e1  mov     r9d, [r14+4]
0x1800241e5  lea     eax, [r9-1]
0x1800241e9  cmp     eax, 0FFFFFFFDh
0x1800241ec  ja      loc_1800244A7
0x1800241f2  xor     r8d, r8d
0x1800241f5  lea     rcx, HubReceiveTimeout
0x1800241fc  mov     rdx, rbx
0x1800241ff  call    AddTimeoutElement
0x180024204  mov     [rbx+1E0h], rax
0x18002420b  jmp     loc_1800244A7
0x180024210  mov     rcx, cs:WPP_GLOBAL_Control
0x180024217  lea     rax, WPP_GLOBAL_Control
0x18002421e  cmp     rcx, rax
0x180024221  jz      short loc_18002424D
0x180024223  test    dword ptr [rcx+1Ch], 2000h
0x18002422a  jz      short loc_18002424D
0x18002422c  cmp     [rcx+19h], r12b
0x180024230  jb      short loc_18002424D
0x180024232  mov     rcx, [rcx+10h]
0x180024236  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x18002423d  mov     edx, 193h
0x180024242  mov     r9d, 80070216h
0x180024248  call    WPP_SF_d
0x18002424d  mov     edi, 80070057h
0x180024252  jmp     loc_1800244A7
0x180024257  cmp     rcx, rax
0x18002425a  jz      short loc_180024280
0x18002425c  test    dword ptr [rcx+1Ch], 2000h
0x180024263  jz      short loc_180024280
0x180024265  cmp     byte ptr [rcx+19h], 5
0x180024269  jb      short loc_180024280
0x18002426b  mov     rcx, [rcx+10h]
0x18002426f  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180024276  mov     edx, 196h
0x18002427b  call    WPP_SF_
0x180024280  mov     eax, 7
0x180024285  cmp     r12w, ax
0x180024289  jnz     short loc_180024292
0x18002428b  mov     [rbx+218h], r15d
0x180024292  mov     rcx, [r14+8]; hSourceHandle
0x180024296  mov     edx, esi; dwProcessId
0x180024298  call    ValidateHandleForRasman
0x18002429d  mov     rsi, rax
0x1800242a0  lea     rcx, [rax-1]
0x1800242a4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800242a8  ja      short loc_18002424D
0x1800242aa  mov     ecx, [rbx+4C8h]
0x1800242b0  test    cl, 1
0x1800242b3  jz      short loc_1800242DD
0x1800242b5  or      ecx, 2
0x1800242b8  mov     r9d, 3A98h
0x1800242be  mov     [rbx+4C8h], ecx
0x1800242c4  xor     r8d, r8d
0x1800242c7  lea     rcx, OutOfProcessReceiveTimeout
0x1800242ce  mov     rdx, rbx
0x1800242d1  call    AddTimeoutElement
0x1800242d6  mov     [rbx+1E0h], rax
0x1800242dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800242e4  lea     rax, WPP_GLOBAL_Control
0x1800242eb  cmp     rcx, rax
0x1800242ee  jz      short loc_18002431F
0x1800242f0  test    dword ptr [rcx+1Ch], 2000h
0x1800242f7  jz      short loc_18002431F
0x1800242f9  cmp     byte ptr [rcx+19h], 4
0x1800242fd  jb      short loc_18002431F
0x1800242ff  mov     rcx, [rcx+10h]
0x180024303  lea     r9, [rbx+8]
0x180024307  mov     edx, 197h
0x18002430c  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180024313  call    WPP_SF_s
0x180024318  mov     rcx, cs:WPP_GLOBAL_Control
0x18002431f  test    byte ptr [rbx+4C8h], 4
0x180024326  jz      short loc_18002438A
0x180024328  lea     r14, WPP_GLOBAL_Control
0x18002432f  cmp     rcx, r14
0x180024332  jz      short loc_18002435C
0x180024334  test    dword ptr [rcx+1Ch], 2000h
0x18002433b  jz      short loc_18002435C
0x18002433d  cmp     byte ptr [rcx+19h], 4
0x180024341  jb      short loc_18002435C
0x180024343  mov     rcx, [rcx+10h]
0x180024347  lea     r9, [rbx+8]
0x18002434b  mov     edx, 198h
0x180024350  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180024357  call    WPP_SF_s
0x18002435c  lea     rdx, [rbp+8]
0x180024360  mov     rcx, rbx
0x180024363  call    SendReceivedPacketToProtocolEngine
0x180024368  mov     rdx, rbp
0x18002436b  mov     rcx, rbx
0x18002436e  call    CompleteReceiveIfPending
0x180024373  mov     edi, eax
0x180024375  test    eax, eax
0x180024377  jnz     short loc_180024382
0x180024379  mov     rcx, cs:WPP_GLOBAL_Control
0x180024380  jmp     short loc_18002432F
0x180024382  mov     r14, [rsp+78h+arg_10]
0x18002438a  mov     rcx, rsi; hEvent
0x18002438d  call    cs:__imp_SetEvent
0x180024394  nop     dword ptr [rax+rax+00h]
0x180024399  test    r13d, r13d
0x18002439c  jnz     loc_1800244A7
0x1800243a2  mov     eax, [rbx+4C8h]
0x1800243a8  test    al, 1
0x1800243aa  jnz     short loc_1800243B9
0x1800243ac  mov     rcx, rsi; hObject
0x1800243af  call    FreeNotifierHandle
0x1800243b4  jmp     loc_1800244A7
0x1800243b9  movzx   r9d, r12w
0x1800243bd  lea     rcx, aOnecoreuapNetR_2; "onecoreuap\\net\\rras\\ras\\rasman\\ras"...
0x1800243c4  mov     r8, rbx
0x1800243c7  mov     edx, 18ABh
0x1800243cc  call    SetPortAsyncReqType
0x1800243d1  mov     [rbx+1D0h], rsi
0x1800243d8  jmp     loc_1800244A7
0x1800243dd  cmp     rcx, rdx
0x1800243e0  jz      short loc_18002440A
0x1800243e2  test    dword ptr [rcx+1Ch], 2000h
0x1800243e9  jz      short loc_18002440A
0x1800243eb  cmp     byte ptr [rcx+19h], 4
0x1800243ef  jb      short loc_18002440A
0x1800243f1  mov     rcx, [rcx+10h]
0x1800243f5  lea     r9, [rbx+8]
0x1800243f9  mov     edx, 192h
  ... truncated ...
```
