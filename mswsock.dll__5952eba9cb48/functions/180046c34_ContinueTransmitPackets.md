# ContinueTransmitPackets

- ea: `0x180046c34`
- end: `0x18004747c`
- name: `ContinueTransmitPackets`
- size: `2120`
- prototype: `__int64 __fastcall(PVOID CompletionContext)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180029144`
- `0x18003c7cc`
- `0x180051ff0`

## callees

- `0x180023cc0`
- `0x1800240a8`
- `0x180024dd4`
- `0x180038a20`
- `0x18003ae8c`
- `0x1800462b0`
- `0x180046c34`
- `0x18004b1d0`
- `0x18004e7b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046cb8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180046cb8`
- `ntdll!NtClearEvent` at `0x180046f1d`
- `ntdll!NtClearEvent` at `0x180046f1d`
- `ntdll!RtlNtStatusToDosError` at `0x180046fd1`
- `ntdll!RtlNtStatusToDosError` at `0x180046fd1`
- `ntdll!NtWaitForSingleObject` at `0x180046eab`
- `ntdll!NtWaitForSingleObject` at `0x180046eab`
- `ntdll!NtReadFile` at `0x180046e87`
- `ntdll!NtReadFile` at `0x180046e87`
- `ntdll!RtlFreeHeap` at `0x180047347`
- `ntdll!RtlFreeHeap` at `0x180047347`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004718b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800473a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047457`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004718b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800473a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047457`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047047`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800471fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004728b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004742f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047047`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800471fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004728b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004742f`

## pseudocode

```c
__int64 __fastcall ContinueTransmitPackets(char *CompletionContext, __int64 a2)
{
  int v4; // r13d
  HANDLE *Value; // r11
  unsigned int i; // r8d
  __int64 v7; // rax
  int v8; // edx
  ULONG Length; // r15d
  __int64 v10; // r14
  void *v11; // r10
  __int64 v12; // rcx
  int v13; // r9d
  union _LARGE_INTEGER *v14; // rax
  unsigned int v15; // ecx
  int Status; // r14d
  int v17; // edx
  __int64 v18; // rdx
  struct _RTL_CRITICAL_SECTION *v19; // r15
  _QWORD *v20; // r14
  _QWORD *v21; // rax
  _QWORD *v22; // r8
  struct _RTL_CRITICAL_SECTION *v23; // rcx
  _QWORD *v24; // rax
  PVOID *v25; // r8
  int IoSize; // eax
  __int64 v27; // r10
  unsigned int v28; // eax
  int v29; // ecx
  bool v30; // zf
  int v31; // eax
  int v32; // r14d
  char v33; // r13
  __int64 v34; // rcx
  void *v35; // r8
  __int64 v36; // r14
  __int64 v37; // r12
  unsigned int started; // eax
  unsigned int v40; // [rsp+50h] [rbp-B8h]
  int v41; // [rsp+54h] [rbp-B4h]
  unsigned int v42; // [rsp+58h] [rbp-B0h]
  int v43; // [rsp+5Ch] [rbp-ACh]
  int v44; // [rsp+60h] [rbp-A8h]
  LONGLONG *v45; // [rsp+68h] [rbp-A0h]
  union _LARGE_INTEGER ByteOffset; // [rsp+70h] [rbp-98h] BYREF
  HANDLE *v47; // [rsp+78h] [rbp-90h]
  int v48; // [rsp+80h] [rbp-88h]
  int v49; // [rsp+84h] [rbp-84h]
  int *v50; // [rsp+88h] [rbp-80h]
  void *v51; // [rsp+90h] [rbp-78h]
  __int64 v52; // [rsp+98h] [rbp-70h]
  _DWORD *v53; // [rsp+A0h] [rbp-68h]
  unsigned int *v54; // [rsp+A8h] [rbp-60h]
  union _LARGE_INTEGER *v55; // [rsp+B0h] [rbp-58h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v57; // [rsp+120h] [rbp+18h] BYREF
  int v58; // [rsp+128h] [rbp+20h]

  v55 = (union _LARGE_INTEGER *)a2;
  v52 = a2;
  IoStatusBlock = 0;
  ByteOffset.QuadPart = 0;
  v49 = 0;
  LODWORD(v57) = 0;
  v4 = 0;
  v41 = 0;
  while ( 2 )
  {
    if ( *(_DWORD *)(a2 + 84) < *(_DWORD *)(a2 + 80) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
      *(_DWORD *)(a2 + 92) &= ~0x200u;
      if ( v4 )
      {
        v30 = (*(_DWORD *)(a2 + 96))-- == 1;
        if ( v30 )
          CheckBSQHeadForCompletion(CompletionContext);
      }
      v23 = (struct _RTL_CRITICAL_SECTION *)(CompletionContext + 48);
LABEL_111:
      LeaveCriticalSection(v23);
      return 997;
    }
    v40 = 0;
    v43 = 1;
    v58 = 0;
    v48 = 0;
    Value = (HANDLE *)TlsGetValue(MSAFD_SockTlsSlot);
    v47 = Value;
    v54 = (unsigned int *)(a2 + 40);
    v44 = *(_DWORD *)(a2 + 40);
    v50 = (int *)(a2 + 168);
    for ( i = *(_DWORD *)(a2 + 168); ; ++i )
    {
      v53 = (_DWORD *)(a2 + 160);
      if ( i >= *(_DWORD *)(a2 + 160) )
      {
        v13 = v40;
        goto LABEL_42;
      }
      v7 = *(_QWORD *)(a2 + 152);
      v8 = *(_DWORD *)(v7 + 24LL * i);
      Length = *(_DWORD *)(v7 + 24LL * i + 4);
      v10 = *(_QWORD *)(v7 + 24LL * i + 8);
      v11 = *(void **)(v7 + 24LL * i + 16);
      v51 = v11;
      if ( (v8 & 3) == 0 )
      {
        LODWORD(v57) = 10022;
        goto LABEL_73;
      }
      if ( (v8 & 1) == 0 )
        break;
      v12 = 2LL * (int)v40;
      *(_QWORD *)(*(_QWORD *)(a2 + 48) + 8 * v12 + 8) = v10;
      *(_DWORD *)(*(_QWORD *)(a2 + 48) + 8 * v12) = Length;
      v13 = ++v40;
      ++*v50;
      if ( (v8 & 4) != 0 )
        goto LABEL_9;
LABEL_40:
      ;
    }
    if ( (v8 & 2) == 0 )
      goto LABEL_40;
    if ( (xmmword_180063D60 & 0x80u) != 0LL )
    {
      WPP_SF_qD(1031, 116, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, a2, *v54);
      v11 = v51;
      Value = v47;
    }
    if ( *(_DWORD *)(a2 + 172) )
    {
      Length = *(_DWORD *)(a2 + 172);
      v14 = v55 + 22;
    }
    else
    {
      *(_DWORD *)(a2 + 172) = Length;
      if ( !Length )
      {
        *(_DWORD *)(a2 + 172) = -1;
        Length = -1;
      }
      v14 = (union _LARGE_INTEGER *)(a2 + 176);
      *(_QWORD *)(a2 + 176) = v10;
    }
    v45 = (LONGLONG *)v14;
    ByteOffset = *v14;
    v15 = 0;
    v42 = 0;
    if ( Length > 0x10000 )
      Length = 0x10000;
    while ( 1 )
    {
      Status = NtReadFile(
                 v11,
                 Value[2],
                 0,
                 0,
                 &IoStatusBlock,
                 (PVOID)(*(_QWORD *)(v52 + 184) + v15),
                 Length,
                 &ByteOffset,
                 0);
      if ( Status == 259 )
      {
        NtWaitForSingleObject(v47[2], 0, 0);
        Status = IoStatusBlock.Status;
      }
      if ( Status < 0 )
        break;
      v42 += LODWORD(IoStatusBlock.Information);
      ByteOffset.QuadPart += IoStatusBlock.Information;
      if ( (unsigned int)UseRdma() )
        goto LABEL_29;
      Length -= v17;
      v11 = v51;
      if ( !Length )
        goto LABEL_29;
      Value = v47;
    }
    if ( Status == -1073741807 )
    {
LABEL_29:
      if ( ((unsigned __int64)v47[2] | 1) == *(_QWORD *)(*(_QWORD *)(a2 + 8) + 24LL) )
        NtClearEvent(v47[2]);
      if ( v42 )
      {
        v18 = 2LL * (int)v40;
        *(_QWORD *)(*(_QWORD *)(a2 + 48) + 8 * v18 + 8) = *(_QWORD *)(v52 + 184);
        *(_DWORD *)(*(_QWORD *)(a2 + 48) + 8 * v18) = v42;
        v13 = ++v40;
        _InterlockedAdd((volatile signed __int32 *)(a2 + 172), -v42);
        *v45 += v42;
      }
      else
      {
        v13 = v40;
      }
      if ( Status == -1073741807 || !*(_DWORD *)(a2 + 172) )
      {
        *(_DWORD *)(a2 + 172) = 0;
        ++*v50;
      }
LABEL_9:
      v58 = 1;
LABEL_42:
      if ( v13 )
      {
        *(_DWORD *)(a2 + 56) = v13;
        v19 = (struct _RTL_CRITICAL_SECTION *)(CompletionContext + 48);
        EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
        if ( !v44 )
        {
          v20 = CompletionContext + 400;
          if ( (_QWORD *)*v20 != v20 )
          {
            if ( (xmmword_180063D60 & 0x80u) != 0LL )
              WPP_SF_qD(
                1031,
                (unsigned int)(v44 + 118),
                WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids,
                a2,
                *((_DWORD *)CompletionContext + 108));
            v21 = *(_QWORD **)(a2 + 8);
            if ( v21 )
              *v21 = 259;
            *(_DWORD *)(a2 + 80) = GetIoSize(*(_QWORD *)(a2 + 48), v40);
            *(_DWORD *)(a2 + 92) = *(_DWORD *)(a2 + 92) & 0xFFFFFDBF | 0x40;
            if ( v4 )
              --*(_DWORD *)(a2 + 96);
            v22 = (_QWORD *)*((_QWORD *)CompletionContext + 51);
            if ( (_QWORD *)*v22 == v20 )
            {
              *(_QWORD *)(a2 + 16) = v20;
              *(_QWORD *)(a2 + 24) = v22;
              *v22 = a2 + 16;
              *((_QWORD *)CompletionContext + 51) = a2 + 16;
              goto LABEL_53;
            }
LABEL_57:
            __fastfail(3u);
          }
          v24 = *(_QWORD **)(a2 + 8);
          if ( v24 )
            *v24 = 259;
          v25 = (PVOID *)*((_QWORD *)CompletionContext + 51);
          if ( *v25 != CompletionContext + 400 )
            goto LABEL_57;
          *(_QWORD *)(a2 + 16) = CompletionContext + 400;
          *(_QWORD *)(a2 + 24) = v25;
          *v25 = (PVOID)(a2 + 16);
          *((_QWORD *)CompletionContext + 51) = a2 + 16;
          v43 = 0;
        }
        IoSize = GetIoSize(*(_QWORD *)(a2 + 48), v40);
        *(_QWORD *)(v27 + 8) -= *(unsigned int *)(a2 + 80);
        **(_DWORD **)(a2 + 48) += *(_DWORD *)(a2 + 80);
        *(_DWORD *)(a2 + 80) += IoSize;
        v28 = *(_DWORD *)(a2 + 92) & 0xFFFFFDEF;
        v29 = v28 | 0x200;
        if ( !v58 )
          v29 = v28;
        *(_DWORD *)(a2 + 92) = v29;
        if ( !v4 )
        {
          ++*(_DWORD *)(a2 + 96);
          v4 = 1;
          v41 = 1;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
        if ( (unsigned int)TrySend(CompletionContext, (__int64)&v57) == -1 )
        {
          if ( (_DWORD)v57 == 997 )
          {
            if ( (xmmword_180063D60 & 0x80u) != 0LL )
              WPP_SF_qD(1031, 119, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, a2, *(_DWORD *)(a2 + 84));
            EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
            *(_DWORD *)(a2 + 92) &= ~0x200u;
            v30 = v4 == 0;
LABEL_68:
            if ( !v30 )
            {
              v30 = (*(_DWORD *)(a2 + 96))-- == 1;
              if ( v30 )
                CheckBSQHeadForCompletion(CompletionContext);
            }
LABEL_53:
            v23 = v19;
            goto LABEL_111;
          }
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_d(1025, 120, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, (unsigned int)v57);
        }
      }
    }
    else
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_d(1025, 117, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, (unsigned int)Status);
      LODWORD(v57) = RtlNtStatusToDosError(Status);
    }
LABEL_73:
    v31 = v58;
    v32 = 0;
    v58 = 0;
    if ( !(_DWORD)v57 )
    {
      v4 = v41;
      if ( v31 )
        continue;
    }
    break;
  }
  v19 = (struct _RTL_CRITICAL_SECTION *)(CompletionContext + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  *(_DWORD *)(a2 + 92) &= ~0x200u;
  if ( !(_DWORD)v57 )
  {
    if ( !v43 && *((_QWORD *)CompletionContext + 50) != a2 + 16 )
      goto LABEL_78;
    v32 = *v50;
  }
  if ( v32 != *v53 && !(_DWORD)v57 )
  {
    *(_DWORD *)(a2 + 92) &= ~0x10u;
LABEL_78:
    v30 = v41 == 0;
    goto LABEL_68;
  }
  v33 = 0;
  if ( !(_DWORD)v57 && (*(_BYTE *)(a2 + 148) & 3) != 0 )
  {
    CompletionContext[800] |= 0x20u;
    if ( (*(_BYTE *)(a2 + 148) & 2) != 0 )
    {
      v58 = 1;
      v34 = *(_QWORD *)(a2 + 8);
      CompletionContext[800] |= 0x10u;
    }
    else
    {
      v34 = 0;
    }
    *((_QWORD *)CompletionContext + 103) = v34;
    *(_WORD *)(*(_QWORD *)CompletionContext + 48LL) = 0;
    v33 = 1;
  }
  v35 = *(void **)(a2 + 184);
  if ( v35 )
    RtlFreeHeap(SockPrivateHeap, 0, v35);
  *(_QWORD *)(a2 + 184) = 0;
  *v53 = 0;
  v36 = *(_QWORD *)(a2 + 8);
  v37 = *v54;
  if ( v36 )
    *(_QWORD *)(v36 + 8) = v37;
  *(_DWORD *)(a2 + 92) &= 0xFFFFFFE7;
  if ( v41 )
    --*(_DWORD *)(a2 + 96);
  if ( !v43 || v44 )
    CheckBSQHeadForCompletion(CompletionContext);
  LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  if ( v33 )
  {
    started = StartGracefulDisconnect(CompletionContext);
    LODWORD(v57) = started;
    if ( started )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_d(1025, 121, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, started);
    }
  }
  if ( !v58 || (_DWORD)v57 )
  {
    if ( v36 )
      CompleteOverlappedIO(*(_QWORD *)(*(_QWORD *)CompletionContext + 8LL), v36, 0, 0, v57, v37);
    return (unsigned int)v57;
  }
  return 997;
}

```

## disassembly

```asm
0x180046c34  mov     rax, rsp
0x180046c37  mov     [rax+10h], rdx
0x180046c3b  mov     [rax+8], rcx
0x180046c3f  push    rbx
0x180046c40  push    rsi
0x180046c41  push    rdi
0x180046c42  push    r12
0x180046c44  push    r13
0x180046c46  push    r14
0x180046c48  push    r15
0x180046c4a  sub     rsp, 0D0h
0x180046c51  mov     rbx, rdx
0x180046c54  mov     rsi, rcx
0x180046c57  mov     [rsp+108h+var_58], rdx
0x180046c5f  mov     [rsp+108h+var_70], rdx
0x180046c67  xorps   xmm0, xmm0
0x180046c6a  movups  xmmword ptr [rax-50h], xmm0
0x180046c6e  xor     edi, edi
0x180046c70  mov     qword ptr [rsp+108h+var_98], rdi
0x180046c75  mov     [rax-84h], edi
0x180046c7b  mov     [rax+18h], edi
0x180046c7e  mov     r13d, edi
0x180046c81  mov     [rsp+108h+var_B4], edi
0x180046c85  lea     r12d, [rdi+1]
0x180046c89  mov     eax, [rbx+50h]
0x180046c8c  cmp     [rbx+54h], eax
0x180046c8f  jl      loc_18004742B
0x180046c95  mov     [rsp+108h+var_B8], edi
0x180046c99  mov     eax, r12d
0x180046c9c  mov     [rsp+108h+var_AC], eax
0x180046ca0  mov     [rsp+108h+var_B0], eax
0x180046ca4  mov     [rsp+108h+arg_18], edi
0x180046cab  mov     [rsp+108h+var_88], edi
0x180046cb2  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180046cb8  call    cs:__imp_TlsGetValue
0x180046cbf  nop     dword ptr [rax+rax+00h]
0x180046cc4  mov     r11, rax
0x180046cc7  mov     [rsp+108h+var_90], rax
0x180046ccc  lea     rax, [rbx+28h]
0x180046cd0  mov     [rsp+108h+var_60], rax
0x180046cd8  mov     r9d, [rax]
0x180046cdb  mov     [rsp+108h+var_A8], r9d
0x180046ce0  mov     dword ptr [rsp+108h+var_A0], r9d
0x180046ce5  lea     rax, [rbx+0A8h]
0x180046cec  mov     [rsp+108h+var_80], rax
0x180046cf4  mov     r8d, [rax]
0x180046cf7  lea     rax, [rbx+0A0h]
0x180046cfe  mov     [rsp+108h+var_68], rax
0x180046d06  cmp     r8d, [rax]
0x180046d09  jnb     loc_18004702E
0x180046d0f  mov     eax, r8d
0x180046d12  lea     rcx, [rax+rax*2]
0x180046d16  mov     rax, [rbx+98h]
0x180046d1d  mov     edx, [rax+rcx*8]
0x180046d20  mov     r15d, [rax+rcx*8+4]
0x180046d25  mov     r14, [rax+rcx*8+8]
0x180046d2a  mov     r10, [rax+rcx*8+10h]
0x180046d2f  mov     [rsp+108h+var_78], r10
0x180046d37  test    dl, 3
0x180046d3a  jnz     short loc_180046D4C
0x180046d3c  mov     dword ptr [rsp+108h+arg_10], 2726h
0x180046d47  jmp     loc_18004725D
0x180046d4c  test    r12b, dl
0x180046d4f  jz      short loc_180046D96
0x180046d51  movsxd  r9, [rsp+108h+var_B8]
0x180046d56  mov     rcx, r9
0x180046d59  add     rcx, rcx
0x180046d5c  mov     rax, [rbx+30h]
0x180046d60  mov     [rax+rcx*8+8], r14
0x180046d65  mov     rax, [rbx+30h]
0x180046d69  mov     [rax+rcx*8], r15d
0x180046d6d  add     r9d, r12d
0x180046d70  mov     [rsp+108h+var_B8], r9d
0x180046d75  mov     rax, [rsp+108h+var_80]
0x180046d7d  add     [rax], r12d
0x180046d80  test    dl, 4
0x180046d83  jz      loc_180046FE9
0x180046d89  mov     [rsp+108h+arg_18], r12d
0x180046d91  jmp     loc_180047033
0x180046d96  test    dl, 2
0x180046d99  jz      loc_180046FE9
0x180046d9f  cmp     byte ptr cs:xmmword_180063D60, dil
0x180046da6  jge     short loc_180046DDC
0x180046da8  mov     edx, 74h ; 't'
0x180046dad  mov     ecx, 407h
0x180046db2  mov     rax, [rsp+108h+var_60]
0x180046dba  mov     eax, [rax]
0x180046dbc  mov     dword ptr [rsp+108h+IoStatusBlock], eax
0x180046dc0  mov     r9, rbx
0x180046dc3  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x180046dca  call    WPP_SF_qD
0x180046dcf  mov     r10, [rsp+108h+var_78]
0x180046dd7  mov     r11, [rsp+108h+var_90]
0x180046ddc  mov     eax, [rbx+0ACh]
0x180046de2  test    eax, eax
0x180046de4  jnz     short loc_180046E0C
0x180046de6  mov     [rbx+0ACh], r15d
0x180046ded  test    r15d, r15d
0x180046df0  jnz     short loc_180046E00
0x180046df2  mov     dword ptr [rbx+0ACh], 0FFFFFFFFh
0x180046dfc  or      r15d, 0FFFFFFFFh
0x180046e00  lea     rax, [rbx+0B0h]
0x180046e07  mov     [rax], r14
0x180046e0a  jmp     short loc_180046E1D
0x180046e0c  mov     r15d, eax
0x180046e0f  mov     rax, [rsp+108h+var_58]
0x180046e17  add     rax, 0B0h
0x180046e1d  mov     [rsp+108h+var_A0], rax
0x180046e22  mov     rax, [rax]
0x180046e25  mov     qword ptr [rsp+108h+var_98], rax
0x180046e2a  mov     ecx, edi
0x180046e2c  mov     [rsp+108h+var_B0], ecx
0x180046e30  mov     eax, 10000h
0x180046e35  cmp     r15d, eax
0x180046e38  cmova   r15d, eax
0x180046e3c  jmp     short loc_180046E43
0x180046e3e  mov     r11, [rsp+108h+var_90]
0x180046e43  mov     eax, ecx
0x180046e45  mov     rcx, [rsp+108h+var_70]
0x180046e4d  add     rax, [rcx+0B8h]
0x180046e54  mov     [rsp+108h+Key], rdi; Key
0x180046e59  lea     rcx, [rsp+108h+var_98]
0x180046e5e  mov     [rsp+108h+ByteOffset], rcx; ByteOffset
0x180046e63  mov     [rsp+108h+Length], r15d; Length
0x180046e68  mov     [rsp+108h+Buffer], rax; Buffer
0x180046e6d  lea     rax, [rsp+108h+var_50]
0x180046e75  mov     [rsp+108h+IoStatusBlock], rax; IoStatusBlock
0x180046e7a  xor     r9d, r9d; ApcContext
0x180046e7d  xor     r8d, r8d; ApcRoutine
0x180046e80  mov     rdx, [r11+10h]; Event
0x180046e84  mov     rcx, r10; FileHandle
0x180046e87  call    cs:__imp_NtReadFile
0x180046e8e  nop     dword ptr [rax+rax+00h]
0x180046e93  mov     r14d, eax
0x180046e96  cmp     eax, 103h
0x180046e9b  jnz     short loc_180046EBF
0x180046e9d  xor     r8d, r8d; Timeout
0x180046ea0  xor     edx, edx; Alertable
0x180046ea2  mov     rcx, [rsp+108h+var_90]
0x180046ea7  mov     rcx, [rcx+10h]; Handle
0x180046eab  call    cs:__imp_NtWaitForSingleObject
0x180046eb2  nop     dword ptr [rax+rax+00h]
0x180046eb7  mov     r14d, dword ptr [rsp+108h+var_50]
0x180046ebf  test    r14d, r14d
0x180046ec2  js      short loc_180046EF7
0x180046ec4  mov     rdx, [rsp+108h+var_50.Information]
0x180046ecc  mov     ecx, [rsp+108h+var_B0]
0x180046ed0  add     ecx, edx
0x180046ed2  mov     [rsp+108h+var_B0], ecx
0x180046ed6  add     qword ptr [rsp+108h+var_98], rdx
0x180046edb  call    UseRdma
0x180046ee0  test    eax, eax
0x180046ee2  jnz     short loc_180046F04
0x180046ee4  sub     r15d, edx
0x180046ee7  mov     r10, [rsp+108h+var_78]
0x180046eef  jnz     loc_180046E3E
0x180046ef5  jmp     short loc_180046F04
0x180046ef7  cmp     r14d, 0C0000011h
0x180046efe  jnz     loc_180046FAC
0x180046f04  mov     rax, [rsp+108h+var_90]
0x180046f09  mov     rcx, [rax+10h]; EventHandle
0x180046f0d  mov     rdx, [rbx+8]
0x180046f11  mov     rax, rcx
0x180046f14  or      rax, r12
0x180046f17  cmp     rax, [rdx+18h]
0x180046f1b  jnz     short loc_180046F29
0x180046f1d  call    cs:__imp_NtClearEvent
0x180046f24  nop     dword ptr [rax+rax+00h]
0x180046f29  mov     r8d, [rsp+108h+var_B0]
0x180046f2e  test    r8d, r8d
0x180046f31  jz      short loc_180046F7C
0x180046f33  movsxd  r9, [rsp+108h+var_B8]
0x180046f38  mov     rdx, r9
0x180046f3b  add     rdx, rdx
0x180046f3e  mov     rcx, [rbx+30h]
0x180046f42  mov     rax, [rsp+108h+var_70]
0x180046f4a  mov     rax, [rax+0B8h]
0x180046f51  mov     [rcx+rdx*8+8], rax
0x180046f56  mov     rax, [rbx+30h]
0x180046f5a  mov     [rax+rdx*8], r8d
0x180046f5e  add     r9d, r12d
0x180046f61  mov     [rsp+108h+var_B8], r9d
0x180046f66  mov     eax, r8d
0x180046f69  neg     eax
0x180046f6b  lock add [rbx+0ACh], eax
0x180046f72  mov     rcx, [rsp+108h+var_A0]
0x180046f77  add     [rcx], r8
0x180046f7a  jmp     short loc_180046F81
0x180046f7c  mov     r9d, [rsp+108h+var_B8]
0x180046f81  cmp     r14d, 0C0000011h
0x180046f88  jz      short loc_180046F96
0x180046f8a  cmp     [rbx+0ACh], edi
0x180046f90  jnz     loc_180046D89
0x180046f96  mov     [rbx+0ACh], edi
0x180046f9c  mov     rax, [rsp+108h+var_80]
0x180046fa4  add     [rax], r12d
0x180046fa7  jmp     loc_180046D89
0x180046fac  test    byte ptr cs:xmmword_180063D60, 2
0x180046fb3  jz      short loc_180046FCE
0x180046fb5  mov     edx, 75h ; 'u'
0x180046fba  mov     ecx, 401h
0x180046fbf  mov     r9d, r14d
0x180046fc2  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x180046fc9  call    WPP_SF_d
0x180046fce  mov     ecx, r14d; Status
0x180046fd1  call    cs:__imp_RtlNtStatusToDosError
0x180046fd8  nop     dword ptr [rax+rax+00h]
0x180046fdd  mov     dword ptr [rsp+108h+arg_10], eax
0x180046fe4  jmp     loc_18004725D
0x180046fe9  add     r8d, r12d
0x180046fec  jmp     loc_180046CF7
0x180046ff1  mov     dword ptr [rsp+108h+arg_10], 271Eh
0x180046ffc  xor     edi, edi
0x180046ffe  lea     r12d, [rdi+1]
0x180047002  mov     rbx, [rsp+108h+arg_8]
0x18004700a  mov     rsi, [rsp+108h+CompletionContext]
0x180047012  mov     eax, [rsp+108h+var_B0]
0x180047016  mov     [rsp+108h+var_AC], eax
0x18004701a  mov     eax, [rsp+108h+var_88]
0x180047021  mov     ecx, dword ptr [rsp+108h+var_A0]
0x180047025  mov     [rsp+108h+var_A8], ecx
0x180047029  jmp     loc_180047264
0x18004702e  mov     r9d, [rsp+108h+var_B8]
0x180047033  test    r9d, r9d
0x180047036  jz      loc_18004725D
0x18004703c  mov     [rbx+38h], r9d
0x180047040  lea     r15, [rsi+30h]
0x180047044  mov     rcx, r15; lpCriticalSection
0x180047047  call    cs:__imp_EnterCriticalSection
0x18004704e  nop     dword ptr [rax+rax+00h]
0x180047053  mov     eax, [rsp+108h+var_A8]
0x180047057  test    eax, eax
0x180047059  jnz     loc_180047132
0x18004705f  lea     r14, [rsi+190h]
0x180047066  cmp     [r14], r14
0x180047069  jz      loc_1800470F1
0x18004706f  cmp     byte ptr cs:xmmword_180063D60, dil
0x180047076  jge     short loc_180047099
0x180047078  lea     edx, [rax+76h]
0x18004707b  mov     ecx, 407h
0x180047080  mov     eax, [rsi+1B0h]
0x180047086  mov     dword ptr [rsp+108h+IoStatusBlock], eax
0x18004708a  mov     r9, rbx
0x18004708d  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x180047094  call    WPP_SF_qD
0x180047099  mov     rax, [rbx+8]
0x18004709d  test    rax, rax
0x1800470a0  jz      short loc_1800470A9
0x1800470a2  mov     qword ptr [rax], 103h
0x1800470a9  mov     edx, [rsp+108h+var_B8]
0x1800470ad  mov     rcx, [rbx+30h]
0x1800470b1  call    GetIoSize
0x1800470b6  mov     [rbx+50h], eax
0x1800470b9  mov     eax, [rbx+5Ch]
0x1800470bc  btr     eax, 9
0x1800470c0  or      eax, 40h
0x1800470c3  mov     [rbx+5Ch], eax
0x1800470c6  test    r13d, r13d
0x1800470c9  jz      short loc_1800470CE
0x1800470cb  dec     dword ptr [rbx+60h]
0x1800470ce  mov     r8, [r14+8]
0x1800470d2  cmp     [r8], r14
0x1800470d5  jnz     short loc_180047115
0x1800470d7  lea     rdx, [rbx+10h]
0x1800470db  mov     [rdx], r14
0x1800470de  mov     [rdx+8], r8
0x1800470e2  mov     [r8], rdx
0x1800470e5  mov     [r14+8], rdx
0x1800470e9  mov     rcx, r15
0x1800470ec  jmp     loc_180047457
0x1800470f1  test    eax, eax
0x1800470f3  jnz     short loc_180047132
0x1800470f5  mov     rax, [rbx+8]
0x1800470f9  test    rax, rax
0x1800470fc  jz      short loc_180047105
0x1800470fe  mov     qword ptr [rax], 103h
0x180047105  lea     rdx, [rsi+190h]
0x18004710c  mov     r8, [rdx+8]
0x180047110  cmp     [r8], rdx
0x180047113  jz      short loc_18004711C
0x180047115  mov     ecx, 3
0x18004711a  int     29h; Win8: RtlFailFast(ecx)
0x18004711c  lea     rax, [rbx+10h]
0x180047120  mov     [rax], rdx
0x180047123  mov     [rax+8], r8
0x180047127  mov     [r8], rax
0x18004712a  mov     [rdx+8], rax
0x18004712e  mov     [rsp+108h+var_AC], edi
0x180047132  mov     r10, [rbx+30h]
0x180047136  mov     edx, [rsp+108h+var_B8]
0x18004713a  mov     rcx, r10
0x18004713d  call    GetIoSize
0x180047142  mov     ecx, [rbx+50h]
0x180047145  sub     [r10+8], rcx
0x180047149  mov     rdx, [rbx+30h]
0x18004714d  mov     ecx, [rbx+50h]
0x180047150  add     [rdx], ecx
0x180047152  add     [rbx+50h], eax
0x180047155  mov     ecx, [rbx+5Ch]
0x180047158  and     ecx, 0FFFFFFEFh
  ... truncated ...
```
