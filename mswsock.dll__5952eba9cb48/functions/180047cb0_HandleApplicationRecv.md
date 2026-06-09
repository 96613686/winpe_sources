# HandleApplicationRecv

- ea: `0x180047cb0`
- end: `0x1800485d6`
- name: `HandleApplicationRecv`
- size: `2342`
- prototype: `__int64 __usercall@<rax>(PVOID CompletionContext@<rcx>, __int64, __int64, __int64, __int64, char, __int64, int)`
- caller_count: `3`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d540`
- `0x18004abd0`
- `0x18004b890`

## callees

- `0x1800052a0`
- `0x180023fd4`
- `0x1800240a8`
- `0x1800240e4`
- `0x180024814`
- `0x180024dd4`
- `0x1800371a1`
- `0x180038104`
- `0x180038118`
- `0x18003cdc8`
- `0x18003e1e0`
- `0x180046240`
- `0x1800462b0`
- `0x1800477a8`
- `0x180047b18`
- `0x180047cb0`
- `0x1800496e4`
- `0x18004d924`

## import_xrefs

- `ntdll!NtClearEvent` at `0x1800482d8`
- `ntdll!NtClearEvent` at `0x1800482d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004847c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048518`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004847c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048518`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800482fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800482fb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180048287`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180048496`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180048287`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180048496`

## pseudocode

```c
__int64 __fastcall HandleApplicationRecv(
        char *CompletionContext,
        _DWORD *a2,
        unsigned int a3,
        unsigned int *a4,
        _DWORD *a5,
        _QWORD *a6,
        _DWORD *a7,
        void *a8,
        unsigned __int8 a9,
        __int64 a10,
        int a11)
{
  _DWORD *v13; // r11
  int v14; // edi
  char v15; // al
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 result; // rax
  __int64 v19; // rdx
  _BYTE *v20; // r9
  unsigned int v21; // r10d
  unsigned int IoSize; // r14d
  unsigned int v23; // r12d
  int *v24; // rdi
  __int64 v25; // rdx
  __int64 NextMessage; // rax
  unsigned int v27; // edi
  _BYTE *v28; // r9
  int v29; // r15d
  int v30; // eax
  int v31; // r14d
  unsigned int v32; // eax
  int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // ecx
  unsigned __int64 v36; // rcx
  NTSTATUS v37; // eax
  __int64 ApplicationBuffer; // rax
  __int64 v39; // rdi
  void *WsaBufArray; // rax
  void *v41; // r15
  int v42; // eax
  int v43; // r14d
  PVOID *v44; // rcx
  int v45; // edi
  int v46; // [rsp+50h] [rbp-68h]
  int v47; // [rsp+54h] [rbp-64h] BYREF
  unsigned int v48; // [rsp+58h] [rbp-60h] BYREF
  int v49; // [rsp+5Ch] [rbp-5Ch]
  unsigned int v50; // [rsp+60h] [rbp-58h]
  int v51; // [rsp+64h] [rbp-54h]
  unsigned int v52; // [rsp+68h] [rbp-50h]
  _DWORD *v53; // [rsp+70h] [rbp-48h]
  unsigned int v54; // [rsp+C0h] [rbp+8h]
  unsigned int v56; // [rsp+D0h] [rbp+18h]

  v56 = a3;
  v13 = 0;
  v47 = 0;
  v48 = 0;
  if ( (*(_BYTE *)(*(_QWORD *)CompletionContext + 68LL) & 0x40) != 0 || a9 )
  {
    v14 = 0;
    v49 = 0;
  }
  else
  {
    v14 = 1;
    v49 = 1;
  }
  if ( (xmmword_180063D60 & 0x80u) != 0LL )
  {
    WPP_SF_(1031, 125, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids);
    a3 = v56;
    v13 = 0;
  }
  v15 = CompletionContext[800];
  if ( (v15 & 0x40) != 0 )
  {
    v16 = a10;
    if ( a10 )
    {
      v17 = 3221225480LL;
LABEL_10:
      IndicateRedirError(CompletionContext, v16, v17);
      return 0;
    }
    return 10038;
  }
  if ( *((_DWORD *)CompletionContext + 38) == 1 )
  {
    if ( (v15 & 4) != 0 )
    {
      v16 = a10;
      if ( a10 )
      {
        v17 = 3221226049LL;
        goto LABEL_10;
      }
      return 10053;
    }
    v19 = *(_QWORD *)CompletionContext;
    if ( (*(_BYTE *)(*(_QWORD *)CompletionContext + 69LL) & 1) != 0 )
    {
      v16 = a10;
      if ( a10 )
      {
        v17 = 3221225648LL;
        goto LABEL_10;
      }
      return 10058;
    }
    v20 = a5;
    if ( a5 )
    {
      if ( (*a5 & 0xFFFFFFFC) != 0 )
        return 10045;
      if ( (((*(_BYTE *)a5 & 1) != 0) & (*(_BYTE *)(v19 + 68) >> 3)) != 0 )
        return 10022;
    }
    if ( a10 || (*(_BYTE *)(v19 + 68) & 0x40) != 0 )
      v46 = a9;
    else
      v46 = 1;
    if ( a3 != 1 || *a2 > 0x64u || (v21 = 1, !v14) )
      v21 = 0;
    v52 = v21;
    if ( a10 )
    {
      IoSize = a11;
      v54 = a11;
      v51 = a11;
    }
    else
    {
      if ( !a2 )
        return 10022;
      IoSize = GetIoSize(a2, a3);
      v54 = IoSize;
      v51 = IoSize;
      if ( IoSize == -2 )
        return 10022;
      v20 = a5;
      a3 = v56;
    }
    if ( (IoSize & 0x80000000) != 0 )
      return 10055;
    v23 = (unsigned int)v13;
    v50 = (unsigned int)v13;
    v24 = (int *)(CompletionContext + 804);
    if ( *((char **)CompletionContext + 40) != CompletionContext + 320
      || *v24 == (_DWORD)v13 && *((_DWORD *)CompletionContext + 34) != (_DWORD)v13 )
    {
      if ( (CompletionContext[801] & 8) != 0 )
      {
        if ( a10 || (v33 = UseRdma(IoSize), v31 = 1, !v33) )
          v31 = (int)v13;
        if ( v20 )
        {
          if ( !v31 || (*v20 & 2) != 0 )
            v31 = (int)v13;
          else
            v31 = 1;
        }
      }
      else
      {
        v31 = OKForRdmaRecv(
                a10,
                (_DWORD)a2,
                a3,
                (_DWORD)v20,
                (_DWORD)v13,
                *((_DWORD *)CompletionContext + 120),
                (__int64)&v48);
        v13 = 0;
      }
      v29 = (int)v13;
      v47 = (int)v13;
      goto LABEL_122;
    }
    if ( v20 )
      v25 = *(_DWORD *)v20 & 1;
    else
      v25 = (unsigned int)v13;
    NextMessage = FindNextMessage(CompletionContext, v25, v21);
    v13 = 0;
    v27 = 0;
    while ( 1 )
    {
      v53 = (_DWORD *)NextMessage;
      if ( !NextMessage || IoSize <= v23 )
        break;
      result = DataAvailableDoRecv(CompletionContext, (__int64)&v47, (__int64)a5, a10, a11, NextMessage);
      v27 = result;
      v13 = 0;
      if ( (_DWORD)result && (_DWORD)result != 10036 )
        return result;
      v23 += v47;
      v50 = v23;
      if ( a10 && (_DWORD)result == 10036 )
      {
        v27 = 0;
        break;
      }
      v28 = a5;
      if ( (*a5 & 2) != 0 && v47 )
        goto LABEL_65;
      NextMessage = FindNextMessage(CompletionContext, *a5 & 1, 0);
      v13 = 0;
    }
    v28 = a5;
LABEL_65:
    v29 = 0;
    v47 = 0;
    if ( (v23 || !IoSize) && a4 )
      *a4 = v23;
    if ( (CompletionContext[801] & 8) != 0 )
    {
      if ( a10 || (v30 = UseRdma(IoSize), v31 = 1, !v30) )
        v31 = (int)v13;
      if ( v28 )
      {
        if ( !v31 || (*v28 & 2) != 0 )
          v31 = (int)v13;
        else
          v31 = 1;
      }
    }
    else
    {
      v31 = OKForRdmaRecv(a10, (_DWORD)a2, v56, (_DWORD)v28, v23, *((_DWORD *)CompletionContext + 120), (__int64)&v48);
      v13 = 0;
    }
    if ( v31 )
    {
      if ( *((_DWORD *)CompletionContext + 120) == (_DWORD)v13 && v48 > (unsigned int)v13 )
        *((_DWORD *)CompletionContext + 53) = 1;
      if ( *((_DWORD **)CompletionContext + 63) == v13 )
      {
        v29 = *((_DWORD *)CompletionContext + 154) != 0 ? 2 : 0;
        v47 = v29;
        if ( (*v28 & 2) != 0 || *((char **)CompletionContext + 42) != CompletionContext + 336 )
        {
          v29 = (int)v13;
          v47 = (int)v13;
        }
      }
      v32 = v54;
      if ( v29 == 2 && v54 > v23 )
      {
        v24 = (int *)(CompletionContext + 804);
        goto LABEL_122;
      }
    }
    else
    {
      v32 = v54;
    }
    if ( !v31 && *((_DWORD *)CompletionContext + 120) == (_DWORD)v13 )
      *((_DWORD *)CompletionContext + 53) = 1;
    if ( !v23 && (v32 || v53 == v13 && (*(_BYTE *)(*(_QWORD *)CompletionContext + 68LL) & 0x40) == 0) )
    {
      v24 = (int *)(CompletionContext + 804);
      if ( !v31 && *((char **)CompletionContext + 40) == CompletionContext + 320 )
      {
        if ( *((_DWORD *)CompletionContext + 34) != (_DWORD)v13 )
          goto LABEL_168;
        if ( *v24 == (_DWORD)v13 )
        {
          HandleFlowControlUponSmallRecvOrSelect(CompletionContext);
          v13 = 0;
        }
      }
LABEL_122:
      if ( *((_DWORD *)CompletionContext + 34) == (_DWORD)v13 )
      {
        v24 = (int *)(CompletionContext + 804);
        v53 = CompletionContext + 804;
        if ( *((_DWORD *)CompletionContext + 201) == (_DWORD)v13 )
        {
          if ( (*(_BYTE *)(*(_QWORD *)CompletionContext + 68LL) & 0x40) != 0 && v46 == (_DWORD)v13 && !a10 && v29 != 2 )
          {
            if ( (unsigned int)(*((_DWORD *)CompletionContext + 44) - 1) > 1 )
              return 10035;
            Sleep(1u);
            v34 = SockSanImportSocket(*(_QWORD *)CompletionContext);
            v35 = 10035;
            if ( v34 )
              return v34;
            return v35;
          }
          if ( a6 )
          {
            *a6 = 259;
            if ( a7 == v13 )
            {
              v36 = a6[3];
              if ( (v36 & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
              {
                v37 = NtClearEvent((HANDLE)v36);
                if ( v37 < 0 )
                  return NtStatusToSocketError((unsigned int)v37);
              }
            }
          }
          EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
          ApplicationBuffer = GetApplicationBuffer(CompletionContext);
          v39 = ApplicationBuffer;
          if ( ApplicationBuffer )
          {
            if ( (xmmword_180063D60 & 0x80u) != 0LL )
              WPP_SF_q(1031, 126, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, ApplicationBuffer);
            if ( !a2 )
            {
              v41 = 0;
              goto LABEL_145;
            }
            WsaBufArray = (void *)GetWsaBufArray(CompletionContext, v56);
            v41 = WsaBufArray;
            if ( WsaBufArray )
            {
              memmove_0(WsaBufArray, a2, 16LL * v56);
LABEL_145:
              *(_QWORD *)(v39 + 48) = v41;
              *(_DWORD *)(v39 + 56) = v56;
              *(_QWORD *)(v39 + 8) = a6;
              *(_QWORD *)(v39 + 64) = a7;
              *(_QWORD *)(v39 + 72) = a8;
              *(_BYTE *)(v39 + 128) = 0;
              *(_BYTE *)(v39 + 131) = 0;
              if ( a5 )
                v42 = *a5;
              else
                v42 = 0;
              *(_DWORD *)(v39 + 60) = v42;
              *(_QWORD *)(v39 + 136) = a10;
              *(_DWORD *)(v39 + 144) = a11;
              *(_DWORD *)(v39 + 108) = 0;
              *(_BYTE *)(v39 + 92) = 0;
              *(_DWORD *)(v39 + 80) = v54;
              *(_DWORD *)(v39 + 40) = v50;
              *(_QWORD *)(v39 + 120) = 0;
              if ( !v31 )
                *((_QWORD *)CompletionContext + 63) = v39;
              v43 = v47;
              if ( (unsigned int)(*((_DWORD *)CompletionContext + 44) - 1) <= 1 )
                v43 = 0;
              v44 = (PVOID *)*((_QWORD *)CompletionContext + 41);
              if ( *v44 != CompletionContext + 320 )
                __fastfail(3u);
              *(_QWORD *)(v39 + 16) = CompletionContext + 320;
              *(_QWORD *)(v39 + 24) = v44;
              *v44 = (PVOID)(v39 + 16);
              *((_QWORD *)CompletionContext + 41) = v39 + 16;
              if ( (BYTE1(xmmword_180063D60) & 0x10) != 0 )
                WPP_SF_q(1036, 127, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v39);
              LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
              if ( (unsigned int)(*((_DWORD *)CompletionContext + 44) - 1) <= 1
                && (Sleep(1u), (unsigned int)SockSanImportSocket(*(_QWORD *)CompletionContext)) )
              {
                CompleteAppRecvsUponClose(CompletionContext);
              }
              else
              {
                CheckPendingAppRecvs(CompletionContext);
                if ( *v53 || *(_DWORD *)(*(_QWORD *)CompletionContext + 24LL) == 4 )
                  CompleteAppRecvsUponClose(CompletionContext);
                if ( !v46 && ((*(_BYTE *)(*(_QWORD *)CompletionContext + 68LL) & 0x40) == 0 || v43 != 2) )
                  return 0;
              }
              return 997;
            }
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
          return 10055;
        }
      }
LABEL_168:
      v45 = *v24;
      if ( a4 && v45 )
        *a4 = v23;
      if ( a10 )
      {
        v17 = v45 == 0 ? 0xC000020D : 0;
        v16 = a10;
        goto LABEL_10;
      }
      if ( v46 == (_DWORD)v13 )
        return v45 == 0 ? 0x2746 : 0;
      if ( !v45 )
        return v45 == 0 ? 0x2746 : 0;
      if ( v49 != (_DWORD)v13 )
        return v45 == 0 ? 0x2746 : 0;
      result = CompleteOverlappedIO(
                 *(_QWORD *)(*(_QWORD *)CompletionContext + 8LL),
                 (__int64)a6,
                 a7,
                 a8,
                 (unsigned int)v13,
                 v23);
      if ( !(_DWORD)result )
        return v45 == 0 ? 0x2746 : 0;
      return result;
    }
    if ( v46 != (_DWORD)v13 && !a10 )
    {
      if ( v27 )
        return v27;
      if ( v49 == (_DWORD)v13 )
      {
        CompleteOverlappedIO(
          *(_QWORD *)(*(_QWORD *)CompletionContext + 8LL),
          (__int64)a6,
          a7,
          a8,
          (unsigned int)v13,
          v23);
        return v27;
      }
    }
    if ( !v27 )
      *a4 = v23;
    return v27;
  }
  v16 = a10;
  if ( a10 )
  {
    v17 = 3221225792LL;
    goto LABEL_10;
  }
  return 10057;
}

```

## disassembly

```asm
0x180047cb0  mov     rax, rsp
0x180047cb3  mov     [rax+20h], r9
0x180047cb7  mov     [rax+18h], r8d
0x180047cbb  mov     [rax+10h], rdx
0x180047cbf  push    rbx
0x180047cc0  push    rsi
0x180047cc1  push    rdi
0x180047cc2  push    r12
0x180047cc4  push    r13
0x180047cc6  push    r14
0x180047cc8  push    r15
0x180047cca  sub     rsp, 80h
0x180047cd1  mov     r15, rdx
0x180047cd4  mov     rbx, rcx
0x180047cd7  xor     r11d, r11d
0x180047cda  mov     [rax-64h], r11d
0x180047cde  mov     [rax-60h], r11d
0x180047ce2  mov     rax, [rcx]
0x180047ce5  mov     r14b, 40h ; '@'
0x180047ce8  test    [rax+44h], r14b
0x180047cec  jnz     short loc_180047D04
0x180047cee  cmp     [rsp+0B8h+arg_40], r11b
0x180047cf6  jnz     short loc_180047D04
0x180047cf8  lea     esi, [r11+1]
0x180047cfc  mov     edi, esi
0x180047cfe  mov     [rsp+0B8h+var_5C], esi
0x180047d02  jmp     short loc_180047D11
0x180047d04  mov     edi, r11d
0x180047d07  mov     [rsp+0B8h+var_5C], r11d
0x180047d0c  mov     esi, 1
0x180047d11  cmp     byte ptr cs:xmmword_180063D60, r11b
0x180047d18  jge     short loc_180047D3B
0x180047d1a  mov     edx, 7Dh ; '}'
0x180047d1f  mov     ecx, 407h
0x180047d24  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x180047d2b  call    WPP_SF_
0x180047d30  mov     r8d, [rsp+0B8h+arg_10]
0x180047d38  xor     r11d, r11d
0x180047d3b  mov     al, [rbx+320h]
0x180047d41  test    r14b, al
0x180047d44  jz      short loc_180047D72
0x180047d46  mov     rdx, [rsp+0B8h+arg_48]
0x180047d4e  test    rdx, rdx
0x180047d51  jz      short loc_180047D68
0x180047d53  mov     r8d, 0C0000008h
0x180047d59  mov     rcx, rbx
0x180047d5c  call    IndicateRedirError
0x180047d61  xor     eax, eax
0x180047d63  jmp     loc_1800485C2
0x180047d68  mov     eax, 2736h
0x180047d6d  jmp     loc_1800485C2
0x180047d72  cmp     [rbx+98h], esi
0x180047d78  jz      short loc_180047D99
0x180047d7a  mov     rdx, [rsp+0B8h+arg_48]
0x180047d82  test    rdx, rdx
0x180047d85  jz      short loc_180047D8F
0x180047d87  mov     r8d, 0C0000140h
0x180047d8d  jmp     short loc_180047D59
0x180047d8f  mov     eax, 2749h
0x180047d94  jmp     loc_1800485C2
0x180047d99  test    al, 4
0x180047d9b  jz      short loc_180047DBC
0x180047d9d  mov     rdx, [rsp+0B8h+arg_48]
0x180047da5  test    rdx, rdx
0x180047da8  jz      short loc_180047DB2
0x180047daa  mov     r8d, 0C0000241h
0x180047db0  jmp     short loc_180047D59
0x180047db2  mov     eax, 2745h
0x180047db7  jmp     loc_1800485C2
0x180047dbc  mov     rdx, [rbx]
0x180047dbf  test    [rdx+45h], sil
0x180047dc3  jz      short loc_180047DE7
0x180047dc5  mov     rdx, [rsp+0B8h+arg_48]
0x180047dcd  test    rdx, rdx
0x180047dd0  jz      short loc_180047DDD
0x180047dd2  mov     r8d, 0C00000B0h
0x180047dd8  jmp     loc_180047D59
0x180047ddd  mov     eax, 274Ah
0x180047de2  jmp     loc_1800485C2
0x180047de7  mov     r9, [rsp+0B8h+arg_20]
0x180047def  test    r9, r9
0x180047df2  jz      short loc_180047E24
0x180047df4  test    dword ptr [r9], 0FFFFFFFCh
0x180047dfb  jz      short loc_180047E07
0x180047dfd  mov     eax, 273Dh
0x180047e02  jmp     loc_1800485C2
0x180047e07  mov     cl, [rdx+44h]
0x180047e0a  shr     cl, 3
0x180047e0d  test    [r9], sil
0x180047e10  setnz   al
0x180047e13  and     cl, al
0x180047e15  test    sil, cl
0x180047e18  jz      short loc_180047E24
0x180047e1a  mov     eax, 2726h
0x180047e1f  jmp     loc_1800485C2
0x180047e24  mov     r13, [rsp+0B8h+arg_48]
0x180047e2c  test    r13, r13
0x180047e2f  jnz     short loc_180047E3D
0x180047e31  test    [rdx+44h], r14b
0x180047e35  jnz     short loc_180047E3D
0x180047e37  mov     [rsp+0B8h+var_68], esi
0x180047e3b  jmp     short loc_180047E49
0x180047e3d  movzx   eax, [rsp+0B8h+arg_40]
0x180047e45  mov     [rsp+0B8h+var_68], eax
0x180047e49  cmp     r8d, esi
0x180047e4c  jnz     short loc_180047E5B
0x180047e4e  cmp     dword ptr [r15], 64h ; 'd'
0x180047e52  ja      short loc_180047E5B
0x180047e54  test    edi, edi
0x180047e56  mov     r10d, esi
0x180047e59  jnz     short loc_180047E5E
0x180047e5b  mov     r10d, r11d
0x180047e5e  mov     [rsp+0B8h+var_50], r10d
0x180047e63  test    r13, r13
0x180047e66  jz      short loc_180047E7F
0x180047e68  mov     r14d, [rsp+0B8h+arg_50]
0x180047e70  mov     [rsp+0B8h+arg_0], r14d
0x180047e78  mov     [rsp+0B8h+var_54], r14d
0x180047e7d  jmp     short loc_180047EC6
0x180047e7f  test    r15, r15
0x180047e82  jnz     short loc_180047E8E
0x180047e84  mov     eax, 2726h
0x180047e89  jmp     loc_1800485C2
0x180047e8e  mov     edx, r8d
0x180047e91  mov     rcx, r15
0x180047e94  call    GetIoSize
0x180047e99  mov     r14d, eax
0x180047e9c  mov     [rsp+0B8h+arg_0], eax
0x180047ea3  mov     [rsp+0B8h+var_54], eax
0x180047ea7  cmp     eax, 0FFFFFFFEh
0x180047eaa  jnz     short loc_180047EB6
0x180047eac  mov     eax, 2726h
0x180047eb1  jmp     loc_1800485C2
0x180047eb6  mov     r9, [rsp+0B8h+arg_20]
0x180047ebe  mov     r8d, [rsp+0B8h+arg_10]
0x180047ec6  test    r14d, r14d
0x180047ec9  jns     short loc_180047ED5
0x180047ecb  mov     eax, 2747h
0x180047ed0  jmp     loc_1800485C2
0x180047ed5  mov     r12d, r11d
0x180047ed8  mov     [rsp+0B8h+var_58], r11d
0x180047edd  lea     rax, [rbx+140h]
0x180047ee4  lea     rdi, [rbx+324h]
0x180047eeb  cmp     [rax], rax
0x180047eee  jnz     loc_1800481C6
0x180047ef4  cmp     [rdi], r11d
0x180047ef7  jnz     short loc_180047F06
0x180047ef9  cmp     [rbx+88h], r11d
0x180047f00  jnz     loc_1800481C6
0x180047f06  test    r9, r9
0x180047f09  jz      short loc_180047F12
0x180047f0b  mov     edx, [r9]
0x180047f0e  and     edx, esi
0x180047f10  jmp     short loc_180047F15
0x180047f12  mov     edx, r11d
0x180047f15  mov     r8d, r10d
0x180047f18  mov     rcx, rbx
0x180047f1b  call    FindNextMessage
0x180047f20  xor     r11d, r11d
0x180047f23  mov     edi, r11d
0x180047f26  mov     [rsp+0B8h+var_48], rax
0x180047f2b  test    rax, rax
0x180047f2e  jz      loc_180047FD8
0x180047f34  cmp     r14d, r12d
0x180047f37  jbe     loc_180047FD8
0x180047f3d  mov     [rsp+0B8h+var_78], rax
0x180047f42  mov     ecx, [rsp+0B8h+arg_50]
0x180047f49  mov     [rsp+0B8h+var_80], ecx
0x180047f4d  mov     [rsp+0B8h+var_88], r13
0x180047f52  mov     rax, [rsp+0B8h+arg_20]
0x180047f5a  mov     [rsp+0B8h+var_90], rax
0x180047f5f  lea     rax, [rsp+0B8h+var_64]
0x180047f64  mov     [rsp+0B8h+var_98], rax
0x180047f69  mov     r9d, r12d
0x180047f6c  mov     r8d, [rsp+0B8h+arg_10]
0x180047f74  mov     rdx, r15
0x180047f77  mov     rcx, rbx
0x180047f7a  call    DataAvailableDoRecv
0x180047f7f  mov     edi, eax
0x180047f81  xor     r11d, r11d
0x180047f84  test    eax, eax
0x180047f86  jz      short loc_180047F93
0x180047f88  cmp     eax, 2734h
0x180047f8d  jnz     loc_1800485C2
0x180047f93  mov     eax, [rsp+0B8h+var_64]
0x180047f97  add     r12d, eax
0x180047f9a  mov     [rsp+0B8h+var_58], r12d
0x180047f9f  test    r13, r13
0x180047fa2  jz      short loc_180047FAC
0x180047fa4  cmp     edi, 2734h
0x180047faa  jz      short loc_180047FD5
0x180047fac  mov     r9, [rsp+0B8h+arg_20]
0x180047fb4  mov     edx, [r9]
0x180047fb7  test    dl, 2
0x180047fba  jz      short loc_180047FC0
0x180047fbc  test    eax, eax
0x180047fbe  jnz     short loc_180047FE0
0x180047fc0  and     edx, esi
0x180047fc2  xor     r8d, r8d
0x180047fc5  mov     rcx, rbx
0x180047fc8  call    FindNextMessage
0x180047fcd  xor     r11d, r11d
0x180047fd0  jmp     loc_180047F26
0x180047fd5  mov     edi, r11d
0x180047fd8  mov     r9, [rsp+0B8h+arg_20]
0x180047fe0  mov     r15d, r11d
0x180047fe3  mov     [rsp+0B8h+var_64], r11d
0x180047fe8  test    r12d, r12d
0x180047feb  jnz     short loc_180047FF2
0x180047fed  test    r14d, r14d
0x180047ff0  jnz     short loc_180048002
0x180047ff2  mov     rax, [rsp+0B8h+arg_18]
0x180047ffa  test    rax, rax
0x180047ffd  jz      short loc_180048002
0x180047fff  mov     [rax], r12d
0x180048002  test    byte ptr [rbx+321h], 8
0x180048009  jz      short loc_18004803C
0x18004800b  test    r13, r13
0x18004800e  jnz     short loc_18004801F
0x180048010  mov     ecx, r14d
0x180048013  call    UseRdma
0x180048018  test    eax, eax
0x18004801a  mov     r14d, esi
0x18004801d  jnz     short loc_180048022
0x18004801f  mov     r14d, r11d
0x180048022  test    r9, r9
0x180048025  jz      short loc_180048073
0x180048027  test    r14d, r14d
0x18004802a  jz      short loc_180048037
0x18004802c  test    byte ptr [r9], 2
0x180048030  jnz     short loc_180048037
0x180048032  mov     r14d, esi
0x180048035  jmp     short loc_180048073
0x180048037  mov     r14d, r11d
0x18004803a  jmp     short loc_180048073
0x18004803c  lea     rax, [rsp+0B8h+var_60]
0x180048041  mov     [rsp+0B8h+var_88], rax
0x180048046  mov     eax, [rbx+1E0h]
0x18004804c  mov     dword ptr [rsp+0B8h+var_90], eax
0x180048050  mov     dword ptr [rsp+0B8h+var_98], r12d
0x180048055  mov     r8d, [rsp+0B8h+arg_10]
0x18004805d  mov     rdx, [rsp+0B8h+Src]
0x180048065  mov     rcx, r13
0x180048068  call    OKForRdmaRecv
0x18004806d  mov     r14d, eax
0x180048070  xor     r11d, r11d
0x180048073  test    r14d, r14d
0x180048076  jz      short loc_1800480E8
0x180048078  cmp     [rbx+1E0h], r11d
0x18004807f  jnz     short loc_18004808E
0x180048081  cmp     [rsp+0B8h+var_60], r11d
0x180048086  jbe     short loc_18004808E
0x180048088  mov     [rbx+0D4h], esi
0x18004808e  cmp     [rbx+1F8h], r11
0x180048095  jnz     short loc_1800480C5
0x180048097  mov     eax, [rbx+268h]
0x18004809d  neg     eax
0x18004809f  sbb     r15d, r15d
0x1800480a2  and     r15d, 2
0x1800480a6  mov     [rsp+0B8h+var_64], r15d
0x1800480ab  test    byte ptr [r9], 2
0x1800480af  jnz     short loc_1800480BD
0x1800480b1  lea     rax, [rbx+150h]
0x1800480b8  cmp     [rax], rax
0x1800480bb  jz      short loc_1800480C5
0x1800480bd  mov     r15d, r11d
0x1800480c0  mov     [rsp+0B8h+var_64], r11d
0x1800480c5  test    r14d, r14d
0x1800480c8  jz      short loc_1800480E8
0x1800480ca  mov     eax, [rsp+0B8h+arg_0]
0x1800480d1  cmp     r15d, 2
0x1800480d5  jnz     short loc_1800480EF
0x1800480d7  cmp     eax, r12d
0x1800480da  jbe     short loc_1800480EF
0x1800480dc  lea     rdi, [rbx+324h]
0x1800480e3  jmp     loc_180048232
0x1800480e8  mov     eax, [rsp+0B8h+arg_0]
0x1800480ef  test    r14d, r14d
0x1800480f2  jnz     short loc_180048103
0x1800480f4  cmp     [rbx+1E0h], r11d
0x1800480fb  jnz     short loc_180048103
0x1800480fd  mov     [rbx+0D4h], esi
0x180048103  test    r12d, r12d
0x180048106  jnz     short loc_180048162
0x180048108  test    eax, eax
0x18004810a  jnz     short loc_18004811C
0x18004810c  cmp     [rsp+0B8h+var_48], r11
0x180048111  jnz     short loc_180048162
0x180048113  mov     rax, [rbx]
0x180048116  test    byte ptr [rax+44h], 40h
0x18004811a  jnz     short loc_180048162
0x18004811c  lea     rdi, [rbx+324h]
0x180048123  test    r14d, r14d
0x180048126  jnz     loc_180048232
0x18004812c  lea     rax, [rbx+140h]
0x180048133  cmp     [rax], rax
0x180048136  jnz     loc_180048232
0x18004813c  cmp     [rbx+88h], r11d
0x180048143  jnz     loc_180048533
0x180048149  cmp     [rdi], r11d
  ... truncated ...
```
