# HandleApplicationSend

- ea: `0x1800411a8`
- end: `0x180041b3e`
- name: `HandleApplicationSend`
- size: `2454`
- prototype: `__int64 __usercall@<rax>(PVOID CompletionContext@<rcx>, void *Src@<rdx>, int, __int64, __int64, __int64, char, __int64, int)`
- caller_count: `3`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180040d78`
- `0x1800453ec`
- `0x18004abd0`

## callees

- `0x1800052a0`
- `0x180023cc0`
- `0x180023fd4`
- `0x1800240a8`
- `0x180024dd4`
- `0x1800371a1`
- `0x180038104`
- `0x180038a20`
- `0x18003ae8c`
- `0x18003c7cc`
- `0x18003ef30`
- `0x18003f28c`
- `0x18003f2e0`
- `0x1800411a8`
- `0x1800462b0`
- `0x1800475c0`
- `0x180047b18`
- `0x18004b1d0`
- `0x18004c204`
- `0x18004c81c`
- `0x18004d924`
- `0x18004f514`

## import_xrefs

- `ntdll!NtClearEvent` at `0x18004130f`
- `ntdll!NtClearEvent` at `0x18004130f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041363`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041472`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004163d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800416cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041809`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800418c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041363`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041472`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004163d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800416cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041809`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800418c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041344`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800414a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041783`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004179f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004189a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041344`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800414a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041783`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004179f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004189a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180041483`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180041483`

## pseudocode

```c
__int64 __fastcall HandleApplicationSend(
        char *CompletionContext,
        void *Src,
        unsigned int a3,
        unsigned int *a4,
        int a5,
        _QWORD *a6,
        void *a7,
        void *a8,
        char a9,
        __int64 a10,
        int a11)
{
  __int64 v14; // rdx
  char v15; // al
  char v16; // cl
  unsigned int IoSize; // esi
  unsigned int v19; // eax
  __int64 v20; // r15
  unsigned __int64 v21; // rcx
  NTSTATUS v22; // eax
  __int64 ApplicationBuffer; // rdi
  void *WsaBufArray; // rax
  void *v25; // r14
  unsigned int v26; // esi
  _QWORD *v27; // r14
  struct _RTL_CRITICAL_SECTION *v28; // rcx
  __int64 v29; // rcx
  unsigned int v30; // ecx
  unsigned int v31; // r15d
  unsigned int v32; // r15d
  unsigned int v33; // r8d
  int v34; // ecx
  int v35; // ecx
  int v36; // r9d
  unsigned int *v37; // rdx
  __int64 v38; // r15
  _QWORD *v39; // r15
  _QWORD *v40; // rax
  bool v41; // si
  int v42; // r13d
  BOOL v43; // edi
  unsigned int v44; // eax
  __int64 v45; // rdx
  __int64 v46; // rax
  unsigned int v47; // eax
  unsigned int *v48; // rdx
  __int64 v49; // rax
  _QWORD *v50; // rcx
  char v51; // al
  unsigned int v52; // [rsp+30h] [rbp-48h] BYREF
  int v53; // [rsp+34h] [rbp-44h]
  __int64 v54; // [rsp+38h] [rbp-40h]
  unsigned int v55; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v56; // [rsp+90h] [rbp+18h]
  unsigned int *v57; // [rsp+98h] [rbp+20h]

  v57 = a4;
  v56 = a3;
  v52 = 0;
  v14 = *(_QWORD *)CompletionContext;
  v54 = *(_QWORD *)CompletionContext;
  v15 = xmmword_180063D60;
  if ( (xmmword_180063D60 & 0x80u) != 0LL )
  {
    WPP_SF_(1031, 138, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids);
    v15 = xmmword_180063D60;
    v14 = v54;
  }
  v16 = CompletionContext[800];
  if ( (v16 & 0x40) != 0 )
    return 10038;
  if ( *((_DWORD *)CompletionContext + 38) != 1 )
    return 10057;
  if ( (*(_BYTE *)(v14 + 69) & 2) != 0 && !*((_DWORD *)CompletionContext + 34) && (v16 & 4) == 0 )
    return 10058;
  if ( (a5 & 0xFFFF7FFA) != 0 )
    return 10045;
  if ( *((_DWORD *)CompletionContext + 34) || (v16 & 6) != 0 )
  {
    if ( v15 < 0 )
      WPP_SF_(1031, 139, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids);
    v51 = CompletionContext[800];
    if ( (v51 & 4) != 0 )
    {
      return 10053;
    }
    else if ( (v51 & 2) != 0 )
    {
      return 10058 - (unsigned int)((v51 & 0x10) != 0);
    }
    else
    {
      return 10054;
    }
  }
  if ( a10 )
  {
    IoSize = a11;
    v53 = a11;
  }
  else
  {
    if ( !Src )
      return 10022;
    IoSize = GetIoSize(Src, a3);
    v53 = IoSize;
    if ( IoSize == -2 )
      return 10022;
    v14 = v54;
  }
  if ( (IoSize & 0x80000000) != 0 )
    return 10055;
  v19 = *(_DWORD *)(v14 + 64);
  if ( v19 && *((_DWORD *)CompletionContext + 32) >= v19 )
    DrainSendCompleteQueue(CompletionContext);
  v20 = (__int64)a6;
  if ( a6 )
  {
    *a6 = 259;
    if ( !a7 )
    {
      v21 = *(_QWORD *)(v20 + 24);
      if ( (v21 & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      {
        v22 = NtClearEvent((HANDLE)v21);
        if ( v22 < 0 )
          return NtStatusToSocketError((unsigned int)v22);
        v52 = 0;
      }
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  ApplicationBuffer = GetApplicationBuffer(CompletionContext);
  if ( !ApplicationBuffer )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
    return 10055;
  }
  if ( Src )
  {
    WsaBufArray = (void *)GetWsaBufArray(CompletionContext, a3);
    v25 = WsaBufArray;
    if ( !WsaBufArray )
    {
      v26 = 10055;
LABEL_77:
      ReleaseApplicationBuffer(CompletionContext, ApplicationBuffer);
      LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
      return v26;
    }
    memmove_0(WsaBufArray, Src, 16LL * v56);
  }
  else
  {
    v25 = 0;
  }
  *(_DWORD *)(ApplicationBuffer + 40) = 0;
  *(_QWORD *)(ApplicationBuffer + 84) = 0;
  *(_DWORD *)(ApplicationBuffer + 92) = 0;
  *(_QWORD *)(ApplicationBuffer + 100) = 0;
  *(_QWORD *)(ApplicationBuffer + 120) = 0;
  *(_QWORD *)(ApplicationBuffer + 48) = v25;
  *(_DWORD *)(ApplicationBuffer + 56) = v56;
  *(_DWORD *)(ApplicationBuffer + 80) = IoSize;
  *(_DWORD *)(ApplicationBuffer + 60) = a5;
  *(_QWORD *)(ApplicationBuffer + 64) = a7;
  *(_QWORD *)(ApplicationBuffer + 72) = a8;
  *(_QWORD *)(ApplicationBuffer + 136) = a10;
  *(_DWORD *)(ApplicationBuffer + 144) = a11;
  *(_QWORD *)(ApplicationBuffer + 8) = v20;
  *(_BYTE *)(ApplicationBuffer + 128) = 0;
  *(_BYTE *)(ApplicationBuffer + 131) = 0;
  v27 = CompletionContext + 400;
  while ( 1 )
  {
    if ( (_QWORD *)*v27 == v27
      && *((char **)CompletionContext + 52) == CompletionContext + 416
      && (unsigned int)(*((_DWORD *)CompletionContext + 44) - 1) > 1 )
    {
      v29 = v54;
      if ( *((_DWORD *)CompletionContext + 32) >= *(_DWORD *)(v54 + 64) || a10 )
      {
LABEL_69:
        if ( !*(_BYTE *)(ApplicationBuffer + 129)
          && (*(_BYTE *)(v29 + 68) & 0x40) != 0
          && (!*((_DWORD *)CompletionContext + 8) || !a9) )
        {
          if ( *((_DWORD *)CompletionContext + 108) <= 2u )
          {
            if ( Src )
              ReleaseWsaBufArray(CompletionContext, *(_QWORD *)(ApplicationBuffer + 48));
            v26 = 10035;
            goto LABEL_77;
          }
          *(_BYTE *)(ApplicationBuffer + 128) = 1;
          *(_BYTE *)(ApplicationBuffer + 131) = 1;
        }
        v39 = (_QWORD *)(ApplicationBuffer + 16);
        v40 = (_QWORD *)*((_QWORD *)CompletionContext + 51);
        if ( (_QWORD *)*v40 != v27 )
          goto LABEL_171;
        *v39 = v27;
        *(_QWORD *)(ApplicationBuffer + 24) = v40;
        *v40 = v39;
        *((_QWORD *)CompletionContext + 51) = v39;
        v41 = (CompletionContext[801] & 8) != 0
           && (unsigned int)UseRdma(IoSize)
           && *((_DWORD *)CompletionContext + 117) == 2
           && !*((_DWORD *)CompletionContext + 146)
           && !*(_BYTE *)(ApplicationBuffer + 128);
        LOBYTE(v55) = *(_BYTE *)(ApplicationBuffer + 129);
        if ( !v41 )
          ++*(_DWORD *)(ApplicationBuffer + 96);
        LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
        if ( (xmmword_180063D60 & 0x80u) != 0LL )
          WPP_SF_d(
            1031,
            142,
            WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids,
            *((unsigned int *)CompletionContext + 108));
        v52 = 0;
        v42 = TrySend(CompletionContext, (__int64)&v52);
        if ( v42 == -1 && v52 == 997 )
        {
          if ( (xmmword_180063D60 & 0x80u) != 0LL )
            WPP_SF_qD(
              1031,
              143,
              WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids,
              ApplicationBuffer,
              *(_DWORD *)(ApplicationBuffer + 84));
          if ( (_BYTE)v55 )
            v52 = 0;
          if ( v41 )
          {
            v43 = 0;
            goto LABEL_112;
          }
          EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
          --*(_DWORD *)(ApplicationBuffer + 96);
          CheckBSQHeadForCompletion(CompletionContext);
        }
        else
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
          if ( v42 && a6 )
            *a6 = 0;
          *(_DWORD *)(ApplicationBuffer + 36) = 1;
          if ( !v41 )
            --*(_DWORD *)(ApplicationBuffer + 96);
          *(_DWORD *)(ApplicationBuffer + 92) = 0;
          CheckBSQHeadForCompletion(CompletionContext);
        }
        v43 = (_QWORD *)*v27 != v27 && ((_QWORD *)*v27 != v39 || *((_DWORD *)CompletionContext + 34));
        LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
LABEL_112:
        if ( v43 )
          RestartBlockedSends(CompletionContext);
        if ( (CompletionContext[800] & 1) != 0 )
        {
          v44 = ContinueGracefulDisconnect(CompletionContext);
          if ( !v44 || (xmmword_180063D60 & 2) == 0 )
            return v52;
          v45 = 144;
        }
        else
        {
          if ( (*(_BYTE *)(*(_QWORD *)CompletionContext + 69LL) & 2) == 0 )
            return v52;
          v44 = SendFIN(CompletionContext);
          if ( !v44 || (xmmword_180063D60 & 2) == 0 )
            return v52;
          v45 = 145;
        }
        WPP_SF_d(1025, v45, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v44);
        return v52;
      }
      v55 = 0;
      v30 = *((_DWORD *)CompletionContext + 108);
      v31 = v30 - 2;
      if ( v30 <= 1 )
        v31 = 0;
      v32 = *((unsigned __int16 *)CompletionContext + 419) * v31;
      if ( (unsigned int)UseRdma(IoSize) )
      {
        GetLargeRecvFCInfoNoPop(CompletionContext, &v55);
        v34 = *((_DWORD *)CompletionContext + 117);
        if ( !v34 || (v35 = v34 - 1) == 0 )
        {
          v36 = 1;
          goto LABEL_63;
        }
        if ( v35 == 1 )
        {
          if ( IoSize > v55 )
            goto LABEL_64;
          v36 = 0;
          goto LABEL_63;
        }
        if ( IoSize > v32 )
          goto LABEL_64;
        v33 = *((unsigned __int16 *)CompletionContext + 419);
      }
      else if ( IoSize > v32 )
      {
        goto LABEL_64;
      }
      v36 = 0;
      *((_DWORD *)CompletionContext + 115) = IoSize / v33;
      if ( v33 * (IoSize / v33) < IoSize )
        *((_DWORD *)CompletionContext + 115) = IoSize / v33 + 1;
LABEL_63:
      if ( !v36 )
      {
LABEL_68:
        v29 = v54;
        goto LABEL_69;
      }
LABEL_64:
      v52 = CopyNBSendData(CompletionContext, ApplicationBuffer);
      if ( v52 )
        goto LABEL_124;
      v37 = v57;
      *v57 = IoSize;
      v38 = (__int64)a6;
      if ( a6 )
      {
        a6[1] = IoSize;
        if ( a9 )
          CompleteOverlappedIO(*(_QWORD *)(*(_QWORD *)CompletionContext + 8LL), v38, a7, a8, 0, *v37);
      }
      goto LABEL_68;
    }
    if ( (unsigned int)(*((_DWORD *)CompletionContext + 44) - 1) > 1 )
      break;
    LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
    Sleep(1u);
    v52 = SockSanImportSocket(*(_QWORD *)CompletionContext);
    v28 = (struct _RTL_CRITICAL_SECTION *)(CompletionContext + 48);
    if ( v52 )
    {
      EnterCriticalSection(v28);
LABEL_124:
      if ( Src )
        ReleaseWsaBufArray(CompletionContext, *(_QWORD *)(ApplicationBuffer + 48));
      ReleaseApplicationBuffer(CompletionContext, ApplicationBuffer);
      goto LABEL_127;
    }
    EnterCriticalSection(v28);
  }
  if ( (_QWORD *)*v27 == v27 )
    v46 = 0;
  else
    v46 = *((_QWORD *)CompletionContext + 51) - 16LL;
  if ( !v46 || *(_BYTE *)(v46 + 129) || (*(_BYTE *)(v54 + 68) & 0x40) == 0 || a9 )
  {
    if ( a10 || v46 && !*(_BYTE *)(v46 + 129) )
      goto LABEL_156;
    v47 = CopyNBSendData(CompletionContext, ApplicationBuffer);
    v52 = v47;
    if ( (xmmword_180063D60 & 0x80u) != 0LL )
    {
      WPP_SF_d(1031, 140, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v47);
      v47 = v52;
    }
    if ( !v47 )
    {
      v48 = v57;
      *v57 = IoSize;
      goto LABEL_159;
    }
    if ( v47 == 10035 )
    {
      if ( *((_DWORD *)CompletionContext + 8) && v20 )
      {
        v49 = v54;
LABEL_151:
        if ( (*(_BYTE *)(v49 + 68) & 0x40) != 0 && !a9 )
          goto LABEL_153;
LABEL_156:
        v47 = 997;
        goto LABEL_157;
      }
      v49 = v54;
      if ( (*(_BYTE *)(v54 + 68) & 0x40) == 0 )
        goto LABEL_151;
    }
LABEL_153:
    if ( Src )
      ReleaseWsaBufArray(CompletionContext, *(_QWORD *)(ApplicationBuffer + 48));
    ReleaseApplicationBuffer(CompletionContext, ApplicationBuffer);
    ApplicationBuffer = 0;
    v47 = v52;
    goto LABEL_158;
  }
  if ( Src )
    ReleaseWsaBufArray(CompletionContext, *(_QWORD *)(ApplicationBuffer + 48));
  ReleaseApplicationBuffer(CompletionContext, ApplicationBuffer);
  ApplicationBuffer = 0;
  v47 = 10035;
LABEL_157:
  v52 = v47;
LABEL_158:
  v48 = v57;
LABEL_159:
  if ( v20 )
  {
    if ( !v47 )
    {
      if ( a9 )
      {
        v52 = CompleteOverlappedIO(*(_QWORD *)(*(_QWORD *)CompletionContext + 8LL), v20, a7, a8, 0, *v48);
        if ( v52 )
        {
          if ( !ApplicationBuffer )
            goto LABEL_127;
          if ( Src )
            ReleaseWsaBufArray(CompletionContext, *(_QWORD *)(ApplicationBuffer + 48));
          ReleaseApplicationBuffer(CompletionContext, ApplicationBuffer);
          ApplicationBuffer = 0;
        }
      }
    }
  }
  if ( ApplicationBuffer )
  {
    if ( (xmmword_180063D60 & 0x80u) != 0LL )
      WPP_SF_qD(
        1031,
        141,
        WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids,
        ApplicationBuffer,
        *((_DWORD *)CompletionContext + 108));
    *(_DWORD *)(ApplicationBuffer + 92) = 64;
    v50 = (_QWORD *)*((_QWORD *)CompletionContext + 51);
    if ( (_QWORD *)*v50 == v27 )
    {
      *(_QWORD *)(ApplicationBuffer + 16) = v27;
      *(_QWORD *)(ApplicationBuffer + 24) = v50;
      *v50 = ApplicationBuffer + 16;
      *((_QWORD *)CompletionContext + 51) = ApplicationBuffer + 16;
      goto LABEL_127;
    }
LABEL_171:
    __fastfail(3u);
  }
LABEL_127:
  LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  return v52;
}

```

## disassembly

```asm
0x1800411a8  mov     [rsp+arg_18], r9
0x1800411ad  mov     [rsp+arg_10], r8d
0x1800411b2  push    rbx
0x1800411b3  push    rsi
0x1800411b4  push    rdi
0x1800411b5  push    r12
0x1800411b7  push    r13
0x1800411b9  push    r14
0x1800411bb  push    r15
0x1800411bd  sub     rsp, 40h
0x1800411c1  mov     r14d, r8d
0x1800411c4  mov     r13, rdx
0x1800411c7  mov     rbx, rcx
0x1800411ca  xor     edi, edi
0x1800411cc  mov     dword ptr [rsp+78h+var_48], edi
0x1800411d0  mov     rdx, [rcx]
0x1800411d3  mov     [rsp+78h+var_40], rdx
0x1800411d8  mov     al, byte ptr cs:xmmword_180063D60
0x1800411de  test    al, al
0x1800411e0  jns     short loc_180041203
0x1800411e2  mov     edx, 8Ah
0x1800411e7  mov     ecx, 407h
0x1800411ec  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x1800411f3  call    WPP_SF_
0x1800411f8  mov     al, byte ptr cs:xmmword_180063D60
0x1800411fe  mov     rdx, [rsp+78h+var_40]
0x180041203  mov     cl, [rbx+320h]
0x180041209  test    cl, 40h
0x18004120c  jz      short loc_180041218
0x18004120e  mov     eax, 2736h
0x180041213  jmp     loc_180041B2D
0x180041218  cmp     dword ptr [rbx+98h], 1
0x18004121f  jz      short loc_18004122B
0x180041221  mov     eax, 2749h
0x180041226  jmp     loc_180041B2D
0x18004122b  test    byte ptr [rdx+45h], 2
0x18004122f  jz      short loc_180041248
0x180041231  cmp     [rbx+88h], edi
0x180041237  jnz     short loc_180041248
0x180041239  test    cl, 4
0x18004123c  jnz     short loc_180041248
0x18004123e  mov     eax, 274Ah
0x180041243  jmp     loc_180041B2D
0x180041248  test    [rsp+78h+arg_20], 0FFFF7FFAh
0x180041253  jz      short loc_18004125F
0x180041255  mov     eax, 273Dh
0x18004125a  jmp     loc_180041B2D
0x18004125f  cmp     [rbx+88h], edi
0x180041265  jnz     loc_180041ADE
0x18004126b  test    cl, 6
0x18004126e  jnz     loc_180041ADE
0x180041274  cmp     [rsp+78h+arg_48], rdi
0x18004127c  jz      short loc_18004128B
0x18004127e  mov     esi, [rsp+78h+arg_50]
0x180041285  mov     dword ptr [rsp+78h+var_48+4], esi
0x180041289  jmp     short loc_1800412BF
0x18004128b  test    r13, r13
0x18004128e  jnz     short loc_18004129A
0x180041290  mov     eax, 2726h
0x180041295  jmp     loc_180041B2D
0x18004129a  mov     edx, r14d
0x18004129d  mov     rcx, r13
0x1800412a0  call    GetIoSize
0x1800412a5  mov     esi, eax
0x1800412a7  mov     dword ptr [rsp+78h+var_48+4], eax
0x1800412ab  cmp     eax, 0FFFFFFFEh
0x1800412ae  jnz     short loc_1800412BA
0x1800412b0  mov     eax, 2726h
0x1800412b5  jmp     loc_180041B2D
0x1800412ba  mov     rdx, [rsp+78h+var_40]
0x1800412bf  test    esi, esi
0x1800412c1  jns     short loc_1800412CD
0x1800412c3  mov     eax, 2747h
0x1800412c8  jmp     loc_180041B2D
0x1800412cd  mov     eax, [rdx+40h]
0x1800412d0  test    eax, eax
0x1800412d2  jz      short loc_1800412E4
0x1800412d4  cmp     [rbx+80h], eax
0x1800412da  jb      short loc_1800412E4
0x1800412dc  mov     rcx, rbx
0x1800412df  call    DrainSendCompleteQueue
0x1800412e4  mov     r15, [rsp+78h+arg_28]
0x1800412ec  test    r15, r15
0x1800412ef  jz      short loc_18004133D
0x1800412f1  mov     qword ptr [r15], 103h
0x1800412f8  cmp     [rsp+78h+arg_30], rdi
0x180041300  jnz     short loc_180041331
0x180041302  mov     rcx, [r15+18h]; EventHandle
0x180041306  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18004130d  jz      short loc_180041331
0x18004130f  call    cs:__imp_NtClearEvent
0x180041316  nop     dword ptr [rax+rax+00h]
0x18004131b  test    eax, eax
0x18004131d  js      short loc_180041325
0x18004131f  mov     dword ptr [rsp+78h+var_48], edi
0x180041323  jmp     short loc_180041331
0x180041325  mov     ecx, eax
0x180041327  call    NtStatusToSocketError
0x18004132c  jmp     loc_180041B2D
0x180041331  jmp     short loc_18004133D
0x180041333  mov     eax, 271Eh
0x180041338  jmp     loc_180041B2D
0x18004133d  lea     r12, [rbx+30h]
0x180041341  mov     rcx, r12; lpCriticalSection
0x180041344  call    cs:__imp_EnterCriticalSection
0x18004134b  nop     dword ptr [rax+rax+00h]
0x180041350  mov     rcx, rbx
0x180041353  call    GetApplicationBuffer
0x180041358  mov     rdi, rax
0x18004135b  test    rax, rax
0x18004135e  jnz     short loc_180041374
0x180041360  mov     rcx, r12; lpCriticalSection
0x180041363  call    cs:__imp_LeaveCriticalSection
0x18004136a  nop     dword ptr [rax+rax+00h]
0x18004136f  jmp     loc_1800412C3
0x180041374  test    r13, r13
0x180041377  jz      short loc_1800413AF
0x180041379  mov     edx, r14d
0x18004137c  mov     rcx, rbx
0x18004137f  call    GetWsaBufArray
0x180041384  mov     r14, rax
0x180041387  test    rax, rax
0x18004138a  jnz     short loc_180041396
0x18004138c  mov     esi, 2747h
0x180041391  jmp     loc_18004162F
0x180041396  mov     r8d, [rsp+78h+arg_10]
0x18004139e  shl     r8, 4; Size
0x1800413a2  mov     rdx, r13; Src
0x1800413a5  mov     rcx, rax; void *
0x1800413a8  call    memmove_0
0x1800413ad  jmp     short loc_1800413B2
0x1800413af  xor     r14d, r14d
0x1800413b2  mov     dword ptr [rdi+28h], 0
0x1800413b9  mov     qword ptr [rdi+54h], 0
0x1800413c1  mov     dword ptr [rdi+5Ch], 0
0x1800413c8  mov     qword ptr [rdi+64h], 0
0x1800413d0  mov     qword ptr [rdi+78h], 0
0x1800413d8  mov     [rdi+30h], r14
0x1800413dc  mov     eax, [rsp+78h+arg_10]
0x1800413e3  mov     [rdi+38h], eax
0x1800413e6  mov     [rdi+50h], esi
0x1800413e9  mov     eax, [rsp+78h+arg_20]
0x1800413f0  mov     [rdi+3Ch], eax
0x1800413f3  mov     rax, [rsp+78h+arg_30]
0x1800413fb  mov     [rdi+40h], rax
0x1800413ff  mov     rdx, [rsp+78h+arg_38]
0x180041407  mov     [rdi+48h], rdx
0x18004140b  mov     rcx, [rsp+78h+arg_48]
0x180041413  mov     [rdi+88h], rcx
0x18004141a  mov     eax, [rsp+78h+arg_50]
0x180041421  mov     [rdi+90h], eax
0x180041427  mov     [rdi+8], r15
0x18004142b  mov     byte ptr [rdi+80h], 0
0x180041432  mov     byte ptr [rdi+83h], 0
0x180041439  lea     r14, [rbx+190h]
0x180041440  cmp     [r14], r14
0x180041443  jnz     short loc_18004145E
0x180041445  lea     rax, [rbx+1A0h]
0x18004144c  cmp     [rax], rax
0x18004144f  jnz     short loc_18004145E
0x180041451  mov     eax, [rbx+0B0h]
0x180041457  dec     eax
0x180041459  cmp     eax, 1
0x18004145c  ja      short loc_1800414B4
0x18004145e  mov     eax, [rbx+0B0h]
0x180041464  dec     eax
0x180041466  cmp     eax, 1
0x180041469  ja      loc_1800418D6
0x18004146f  mov     rcx, r12; lpCriticalSection
0x180041472  call    cs:__imp_LeaveCriticalSection
0x180041479  nop     dword ptr [rax+rax+00h]
0x18004147e  mov     ecx, 1; dwMilliseconds
0x180041483  call    cs:__imp_Sleep
0x18004148a  nop     dword ptr [rax+rax+00h]
0x18004148f  mov     rcx, [rbx]
0x180041492  call    SockSanImportSocket
0x180041497  mov     dword ptr [rsp+78h+var_48], eax
0x18004149b  mov     rcx, r12; lpCriticalSection
0x18004149e  test    eax, eax
0x1800414a0  jnz     loc_18004189A
0x1800414a6  call    cs:__imp_EnterCriticalSection
0x1800414ad  nop     dword ptr [rax+rax+00h]
0x1800414b2  jmp     short loc_180041440
0x1800414b4  mov     rcx, [rsp+78h+var_40]
0x1800414b9  mov     eax, [rcx+40h]
0x1800414bc  cmp     [rbx+80h], eax
0x1800414c2  jnb     loc_1800415F1
0x1800414c8  cmp     [rsp+78h+arg_48], 0
0x1800414d1  jnz     loc_1800415F1
0x1800414d7  mov     [rsp+78h+arg_0], 0
0x1800414e2  mov     ecx, [rbx+1B0h]
0x1800414e8  movzx   r8d, word ptr [rbx+346h]
0x1800414f0  lea     r15d, [rcx-2]
0x1800414f4  xor     eax, eax
0x1800414f6  cmp     ecx, 1
0x1800414f9  cmovbe  r15d, eax
0x1800414fd  imul    r15d, r8d
0x180041501  mov     ecx, esi
0x180041503  call    UseRdma
0x180041508  test    eax, eax
0x18004150a  jz      short loc_180041555
0x18004150c  lea     rdx, [rsp+78h+arg_0]
0x180041514  mov     rcx, rbx
0x180041517  call    GetLargeRecvFCInfoNoPop
0x18004151c  mov     ecx, [rbx+1D4h]
0x180041522  test    ecx, ecx
0x180041524  jz      short loc_18004154D
0x180041526  sub     ecx, 1
0x180041529  jz      short loc_18004154D
0x18004152b  cmp     ecx, 1
0x18004152e  jz      short loc_18004153F
0x180041530  cmp     esi, r15d
0x180041533  ja      short loc_180041581
0x180041535  movzx   r8d, word ptr [rbx+346h]
0x18004153d  jmp     short loc_18004155A
0x18004153f  cmp     esi, [rsp+78h+arg_0]
0x180041546  ja      short loc_180041581
0x180041548  xor     r9d, r9d
0x18004154b  jmp     short loc_18004157C
0x18004154d  mov     r9d, 1
0x180041553  jmp     short loc_18004157C
0x180041555  cmp     esi, r15d
0x180041558  ja      short loc_180041581
0x18004155a  mov     eax, esi
0x18004155c  xor     edx, edx
0x18004155e  div     r8d
0x180041561  mov     ecx, eax
0x180041563  xor     r9d, r9d
0x180041566  imul    ecx, r8d
0x18004156a  cmp     ecx, esi
0x18004156c  mov     [rbx+1CCh], eax
0x180041572  jnb     short loc_18004157C
0x180041574  inc     eax
0x180041576  mov     [rbx+1CCh], eax
0x18004157c  test    r9d, r9d
0x18004157f  jz      short loc_1800415EC
0x180041581  mov     rdx, rdi
0x180041584  mov     rcx, rbx
0x180041587  call    CopyNBSendData
0x18004158c  mov     dword ptr [rsp+78h+var_48], eax
0x180041590  test    eax, eax
0x180041592  jnz     loc_1800418A6
0x180041598  mov     rdx, [rsp+78h+arg_18]
0x1800415a0  mov     [rdx], esi
0x1800415a2  mov     r15, [rsp+78h+arg_28]
0x1800415aa  test    r15, r15
0x1800415ad  jz      short loc_1800415EC
0x1800415af  mov     eax, esi
0x1800415b1  mov     [r15+8], rax
0x1800415b5  cmp     [rsp+78h+arg_40], 0
0x1800415bd  jz      short loc_1800415EC
0x1800415bf  mov     rcx, [rbx]
0x1800415c2  mov     eax, [rdx]
0x1800415c4  mov     [rsp+78h+var_50], eax
0x1800415c8  mov     dword ptr [rsp+78h+var_58], 0
0x1800415d0  mov     r9, [rsp+78h+arg_38]
0x1800415d8  mov     r8, [rsp+78h+arg_30]
0x1800415e0  mov     rdx, r15
0x1800415e3  mov     rcx, [rcx+8]
0x1800415e7  call    CompleteOverlappedIO
0x1800415ec  mov     rcx, [rsp+78h+var_40]
0x1800415f1  cmp     byte ptr [rdi+81h], 0
0x1800415f8  jnz     short loc_18004165E
0x1800415fa  test    byte ptr [rcx+44h], 40h
0x1800415fe  jz      short loc_18004165E
0x180041600  cmp     dword ptr [rbx+20h], 0
0x180041604  jz      short loc_180041610
0x180041606  cmp     [rsp+78h+arg_40], 0
0x18004160e  jnz     short loc_18004165E
0x180041610  cmp     dword ptr [rbx+1B0h], 2
0x180041617  ja      short loc_180041650
0x180041619  test    r13, r13
0x18004161c  jz      short loc_18004162A
0x18004161e  mov     rdx, [rdi+30h]
0x180041622  mov     rcx, rbx
0x180041625  call    ReleaseWsaBufArray
0x18004162a  mov     esi, 2733h
0x18004162f  mov     rdx, rdi
0x180041632  mov     rcx, rbx
0x180041635  call    ReleaseApplicationBuffer
0x18004163a  mov     rcx, r12; lpCriticalSection
0x18004163d  call    cs:__imp_LeaveCriticalSection
0x180041644  nop     dword ptr [rax+rax+00h]
0x180041649  mov     eax, esi
0x18004164b  jmp     loc_180041B2D
0x180041650  mov     byte ptr [rdi+80h], 1
0x180041657  mov     byte ptr [rdi+83h], 1
0x18004165e  lea     r15, [rdi+10h]
0x180041662  mov     rax, [r14+8]
0x180041666  cmp     [rax], r14
0x180041669  jnz     loc_180041AB9
0x18004166f  mov     [r15], r14
0x180041672  mov     [r15+8], rax
0x180041676  mov     [rax], r15
0x180041679  mov     [r14+8], r15
0x18004167d  test    byte ptr [rbx+321h], 8
0x180041684  jz      short loc_1800416B1
0x180041686  mov     ecx, esi
0x180041688  call    UseRdma
0x18004168d  test    eax, eax
  ... truncated ...
```
