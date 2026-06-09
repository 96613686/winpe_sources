# NetworkQuery_ProcessComplete

- ea: `0x180032348`
- end: `0x1800327b5`
- name: `NetworkQuery_ProcessComplete`
- size: `1133`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `5`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180030ea8`
- `0x180033414`
- `0x1800489cc`
- `0x1800493e0`
- `0x180062338`

## callees

- `0x18000f1b8`
- `0x18002e894`
- `0x1800317e0`
- `0x180032348`
- `0x180033890`
- `0x180034170`
- `0x180034cd4`
- `0x180047b80`
- `0x18004f9bc`
- `0x180059b84`
- `0x1800669f8`
- `0x18007d72c`
- `0x1800dc9e0`
- `0x1800ddfa8`
- `0x1800de650`
- `0x1800dfdc8`
- `0x1800e32b4`
- `0x1800e4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800323e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800323e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800324fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800324fa`

## string_xrefs

- `0x18003252a`: `NetworkQuery_ProcessComplete`
- `0x1800325f3`: `NetworkQuery_ProcessComplete`

## pseudocode

```c
__int64 __fastcall NetworkQuery_ProcessComplete(unsigned int *lpMem)
{
  unsigned int v2; // edi
  __int64 v3; // rsi
  __int64 v4; // rbp
  __int64 v5; // rdi
  __int64 *v6; // rcx
  __int64 *v7; // rax
  void *v8; // rcx
  __int64 v9; // rax
  _QWORD **v10; // rdi
  _QWORD *v11; // rax
  _QWORD *v13; // rcx
  char *v14; // r14
  void *v15; // rcx
  void *v16; // rcx

  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_qq(
      1035,
      160,
      (unsigned int)WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids,
      (_DWORD)lpMem,
      *((_QWORD *)lpMem + 128));
  if ( !lpMem[119] )
    return 0;
  v2 = 0;
  v3 = *((_QWORD *)lpMem + 62);
  if ( (lpMem[196] & 0x100) == 0 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_q(1035, 161, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, lpMem);
    goto LABEL_41;
  }
  NetworkQuery_ProcessEffectiveQuery(lpMem);
  if ( (*(_BYTE *)(v3 + 16) & 0x20) != 0 )
  {
    NetworkQuery_IsAllQueriesCompleted(lpMem);
  }
  else if ( !(unsigned int)Query_IsSuccessResponse(lpMem[179]) )
  {
    goto LABEL_12;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 162, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, lpMem[126]);
  Query_Cancel(lpMem);
LABEL_12:
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 24));
  v4 = *(_QWORD *)(v3 + 120);
  if ( (*(_DWORD *)(v3 + 16) & 0x240) == 0x40 )
  {
    v5 = *(_QWORD *)(v3 + 88);
    if ( v3 )
    {
      v6 = *(__int64 **)(v3 + 112);
      if ( v6 )
      {
        v7 = *(__int64 **)(v3 + 112);
        while ( (*((_DWORD *)v7 + 15) & 0x1000000) == 0 )
        {
          v7 = (__int64 *)*v7;
          if ( v7 == v6 )
            goto LABEL_22;
        }
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_(1035, 163, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids);
        *(_DWORD *)(v3 + 104) = 1;
      }
    }
LABEL_22:
    if ( (*(_DWORD *)(v3 + 64) & 0x400LL) == 0 )
      NetworkQuery_CacheEffectiveQueryResults(v3, 1);
    if ( (*(_DWORD *)(v3 + 64) & 0x800LL) == 0 )
      NetworkQuery_CacheEffectiveQueryResults(v3, 0);
    if ( *(_QWORD *)(v5 + 960) )
      goto LABEL_30;
    v8 = *(void **)(v5 + 816);
    if ( v8 || *(_QWORD *)(v5 + 824) )
    {
      v9 = Dns_RecordListBuildCombinedAAAAInPlace(v8, *(LPVOID *)(v5 + 824));
      *(_QWORD *)(v5 + 816) = 0;
      *(_QWORD *)(v5 + 824) = 0;
    }
    else
    {
      v15 = *(void **)(v5 + 856);
      if ( !v15 && !*(_QWORD *)(v5 + 864) )
        goto LABEL_30;
      v9 = Dns_RecordListBuildCombinedAAAAInPlace(v15, *(LPVOID *)(v5 + 864));
      *(_QWORD *)(v5 + 856) = 0;
      *(_QWORD *)(v5 + 864) = 0;
    }
    *(_QWORD *)(v5 + 960) = v9;
LABEL_30:
    NetworkQuery_HandleAllServerTimeout(v5);
    if ( v5 != v4 )
    {
      v16 = *(void **)(v4 + 960);
      *(_DWORD *)(v4 + 508) = *(_DWORD *)(v5 + 508);
      *(_QWORD *)(v4 + 264) = *(_QWORD *)(v5 + 264);
      Dns_RecordListFree(v16);
      *(_QWORD *)(v4 + 960) = *(_QWORD *)(v5 + 960);
      *(_QWORD *)(v4 + 3444) = *(_QWORD *)(v5 + 3444);
      *(_QWORD *)(v4 + 3436) = *(_QWORD *)(v5 + 3436);
      *(_QWORD *)(v5 + 960) = 0;
      Packet_FreeMsgBuf(*(char **)(v4 + 1152));
      *(_QWORD *)(v4 + 1152) = 0;
      *(_QWORD *)(v4 + 1152) = *(_QWORD *)(v5 + 1152);
      *(_QWORD *)(v5 + 1152) = 0;
      Dns_FreeMsgBufRpc(*(LPVOID *)(v4 + 1160));
      *(_QWORD *)(v4 + 1160) = 0;
      *(_QWORD *)(v4 + 1160) = *(_QWORD *)(v5 + 1160);
      *(_QWORD *)(v5 + 1160) = 0;
    }
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_q(1035, 164, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, v4);
    v10 = (_QWORD **)(v4 + 136);
    while ( 1 )
    {
      v11 = *v10;
      if ( *v10 == v10 )
        break;
      if ( (_QWORD **)v11[1] != v10 || (v13 = (_QWORD *)*v11, *(_QWORD **)(*v11 + 8LL) != v11) )
        __fastfail(3u);
      *v10 = v13;
      v14 = (char *)(v11 - 17);
      v13[1] = v10;
      v11[1] = v11;
      *v11 = v11;
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_dqqq(
          (_DWORD)v13,
          165,
          (unsigned int)WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids,
          0,
          (__int64)v14,
          (__int64)(*v10 - 17),
          *(_QWORD *)(v4 + 144) - 136LL);
      DeRefQueryBlobEx(v14, (__int64)"NetworkQuery_ProcessComplete", 234, 15);
    }
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_q(1035, 166, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, v4);
    *(_DWORD *)(v3 + 16) |= 0x200u;
    v2 = 1;
    *(_QWORD *)(v3 + 120) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 24));
  if ( v2 )
  {
    _InterlockedOr((volatile signed __int32 *)lpMem + 196, 0x200u);
    (*(void (__fastcall **)(__int64))(v4 + 1128))(v4);
  }
LABEL_41:
  DeRefQueryBlobEx((char *)lpMem, (__int64)"NetworkQuery_ProcessComplete", 6, 13);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 167, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180032348  push    rbx
0x18003234a  push    rbp
0x18003234b  push    rsi
0x18003234c  push    rdi
0x18003234d  push    r12
0x18003234f  push    r14
0x180032351  push    r15
0x180032353  sub     rsp, 40h
0x180032357  mov     rbx, rcx
0x18003235a  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180032361  lea     r14, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids
0x180032368  jnz     loc_180032659
0x18003236e  xor     r12d, r12d
0x180032371  cmp     [rbx+1DCh], r12d
0x180032378  jz      loc_180032699
0x18003237e  mov     eax, [rbx+310h]
0x180032384  mov     edi, r12d
0x180032387  mov     rsi, [rbx+1F0h]
0x18003238e  bt      eax, 8
0x180032392  jnb     loc_18003255E
0x180032398  mov     rcx, rbx
0x18003239b  call    NetworkQuery_ProcessEffectiveQuery
0x1800323a0  test    byte ptr [rsi+10h], 20h
0x1800323a4  lea     r15d, [r12+1]
0x1800323a9  jnz     short loc_1800323BF
0x1800323ab  mov     ecx, [rbx+2CCh]
0x1800323b1  mov     ebp, r12d
0x1800323b4  call    Query_IsSuccessResponse
0x1800323b9  test    eax, eax
0x1800323bb  jnz     short loc_1800323CA
0x1800323bd  jmp     short loc_1800323E4
0x1800323bf  mov     rcx, rbx
0x1800323c2  mov     ebp, r15d
0x1800323c5  call    NetworkQuery_IsAllQueriesCompleted
0x1800323ca  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800323d1  jnz     loc_1800326A0
0x1800323d7  mov     r8d, r15d
0x1800323da  mov     edx, ebp
0x1800323dc  mov     rcx, rbx; lpMem
0x1800323df  call    Query_Cancel
0x1800323e4  lea     rcx, [rsi+18h]; lpCriticalSection
0x1800323e8  call    cs:__imp_EnterCriticalSection
0x1800323ef  nop     dword ptr [rax+rax+00h]
0x1800323f4  mov     eax, [rsi+10h]
0x1800323f7  mov     rbp, [rsi+78h]
0x1800323fb  and     eax, 240h
0x180032400  cmp     eax, 40h ; '@'
0x180032403  jnz     loc_1800324F6
0x180032409  mov     rdi, [rsi+58h]
0x18003240d  test    rsi, rsi
0x180032410  jz      short loc_180032442
0x180032412  mov     rcx, [rsi+70h]
0x180032416  test    rcx, rcx
0x180032419  jz      short loc_180032442
0x18003241b  mov     rax, rcx
0x18003241e  test    dword ptr [rax+3Ch], 1000000h
0x180032425  jnz     short loc_180032431
0x180032427  mov     rax, [rax]
0x18003242a  cmp     rax, rcx
0x18003242d  jnz     short loc_18003241E
0x18003242f  jmp     short loc_180032442
0x180032431  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180032438  jnz     loc_1800326BE
0x18003243e  mov     [rsi+68h], r15d
0x180032442  mov     eax, [rsi+40h]
0x180032445  bt      rax, 0Ah
0x18003244a  jb      short loc_180032457
0x18003244c  mov     edx, r15d
0x18003244f  mov     rcx, rsi
0x180032452  call    NetworkQuery_CacheEffectiveQueryResults
0x180032457  mov     eax, [rsi+40h]
0x18003245a  bt      rax, 0Bh
0x18003245f  jb      short loc_18003246B
0x180032461  xor     edx, edx
0x180032463  mov     rcx, rsi
0x180032466  call    NetworkQuery_CacheEffectiveQueryResults
0x18003246b  cmp     [rdi+3C0h], r12
0x180032472  jnz     short loc_1800324A5
0x180032474  mov     rcx, [rdi+330h]
0x18003247b  test    rcx, rcx
0x18003247e  jz      loc_18003260D
0x180032484  mov     rdx, [rdi+338h]
0x18003248b  call    Dns_RecordListBuildCombinedAAAAInPlace
0x180032490  mov     [rdi+330h], r12
0x180032497  mov     [rdi+338h], r12
0x18003249e  mov     [rdi+3C0h], rax
0x1800324a5  mov     rcx, rdi
0x1800324a8  call    NetworkQuery_HandleAllServerTimeout
0x1800324ad  cmp     rdi, rbp
0x1800324b0  jnz     loc_1800326D5
0x1800324b6  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800324bd  jnz     loc_180032781
0x1800324c3  lea     rdi, [rbp+88h]
0x1800324ca  mov     rax, [rdi]
0x1800324cd  cmp     rax, rdi
0x1800324d0  jnz     loc_18003257E
0x1800324d6  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800324dd  lea     r14, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids
0x1800324e4  jnz     loc_18003279B
0x1800324ea  bts     dword ptr [rsi+10h], 9
0x1800324ef  mov     edi, r15d
0x1800324f2  mov     [rsi+78h], r12
0x1800324f6  lea     rcx, [rsi+18h]; lpCriticalSection
0x1800324fa  call    cs:__imp_LeaveCriticalSection
0x180032501  nop     dword ptr [rax+rax+00h]
0x180032506  test    edi, edi
0x180032508  jz      short loc_180032524
0x18003250a  lock or dword ptr [rbx+310h], 200h
0x180032515  mov     rax, [rbp+468h]
0x18003251c  mov     rcx, rbp
0x18003251f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032524  mov     r9d, 0Dh
0x18003252a  lea     rdx, aNetworkqueryPr; "NetworkQuery_ProcessComplete"
0x180032531  mov     r8d, 1B06h
0x180032537  mov     rcx, rbx; lpMem
0x18003253a  call    DeRefQueryBlobEx
0x18003253f  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180032546  jnz     loc_18003267F
0x18003254c  mov     eax, edi
0x18003254e  add     rsp, 40h
0x180032552  pop     r15
0x180032554  pop     r14
0x180032556  pop     r12
0x180032558  pop     rdi
0x180032559  pop     rsi
0x18003255a  pop     rbp
0x18003255b  pop     rbx
0x18003255c  retn
0x18003255e  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180032565  jz      short loc_180032524
0x180032567  mov     edx, 0A1h
0x18003256c  mov     ecx, 40Bh
0x180032571  mov     r9, rbx
0x180032574  mov     r8, r14
0x180032577  call    WPP_SF_q
0x18003257c  jmp     short loc_180032524
0x18003257e  cmp     [rax+8], rdi
0x180032582  jnz     loc_180032652
0x180032588  mov     rcx, [rax]
0x18003258b  cmp     [rcx+8], rax
0x18003258f  jnz     loc_180032652
0x180032595  mov     [rdi], rcx
0x180032598  lea     r14, [rax-88h]
0x18003259f  mov     [rcx+8], rdi
0x1800325a3  mov     [rax+8], rax
0x1800325a7  mov     [rax], rax
0x1800325aa  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800325b1  jz      short loc_1800325ED
0x1800325b3  mov     r8, [rbp+90h]
0x1800325ba  mov     edx, 0A5h
0x1800325bf  mov     rax, [rdi]
0x1800325c2  sub     r8, 88h
0x1800325c9  mov     [rsp+78h+var_48], r8
0x1800325ce  sub     rax, 88h
0x1800325d4  mov     [rsp+78h+var_50], rax
0x1800325d9  lea     r8, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids
0x1800325e0  xor     r9d, r9d
0x1800325e3  mov     [rsp+78h+var_58], r14
0x1800325e8  call    WPP_SF_dqqq
0x1800325ed  mov     r9d, 0Fh
0x1800325f3  lea     rdx, aNetworkqueryPr; "NetworkQuery_ProcessComplete"
0x1800325fa  mov     r8d, 1AEAh
0x180032600  mov     rcx, r14; lpMem
0x180032603  call    DeRefQueryBlobEx
0x180032608  jmp     loc_1800324CA
0x18003260d  cmp     [rdi+338h], r12
0x180032614  jnz     loc_180032484
0x18003261a  mov     rcx, [rdi+358h]
0x180032621  test    rcx, rcx
0x180032624  jnz     short loc_180032633
0x180032626  cmp     [rdi+360h], r12
0x18003262d  jz      loc_1800324A5
0x180032633  mov     rdx, [rdi+360h]
0x18003263a  call    Dns_RecordListBuildCombinedAAAAInPlace
0x18003263f  mov     [rdi+358h], r12
0x180032646  mov     [rdi+360h], r12
0x18003264d  jmp     loc_18003249E
0x180032652  mov     ecx, 3
0x180032657  int     29h; Win8: RtlFailFast(ecx)
0x180032659  mov     rax, [rbx+400h]
0x180032660  mov     edx, 0A0h
0x180032665  mov     ecx, 40Bh
0x18003266a  mov     [rsp+78h+var_58], rax
0x18003266f  mov     r9, rbx
0x180032672  mov     r8, r14
0x180032675  call    WPP_SF_qq
0x18003267a  jmp     loc_18003236E
0x18003267f  mov     edx, 0A7h
0x180032684  mov     ecx, 40Bh
0x180032689  mov     r9d, edi
0x18003268c  mov     r8, r14
0x18003268f  call    WPP_SF_d
0x180032694  jmp     loc_18003254C
0x180032699  xor     eax, eax
0x18003269b  jmp     loc_18003254E
0x1800326a0  mov     r9d, [rbx+1F8h]
0x1800326a7  mov     edx, 0A2h
0x1800326ac  mov     ecx, 40Bh
0x1800326b1  mov     r8, r14
0x1800326b4  call    WPP_SF_d
0x1800326b9  jmp     loc_1800323D7
0x1800326be  mov     edx, 0A3h
0x1800326c3  mov     ecx, 40Bh
0x1800326c8  mov     r8, r14
0x1800326cb  call    WPP_SF_
0x1800326d0  jmp     loc_18003243E
0x1800326d5  mov     eax, [rdi+1FCh]
0x1800326db  mov     rcx, [rbp+3C0h]; lpMem
0x1800326e2  mov     [rbp+1FCh], eax
0x1800326e8  mov     rax, [rdi+108h]
0x1800326ef  mov     [rbp+108h], rax
0x1800326f6  call    Dns_RecordListFree
0x1800326fb  mov     rax, [rdi+3C0h]
0x180032702  mov     [rbp+3C0h], rax
0x180032709  mov     rax, [rdi+0D74h]
0x180032710  mov     [rbp+0D74h], rax
0x180032717  mov     rax, [rdi+0D6Ch]
0x18003271e  mov     [rbp+0D6Ch], rax
0x180032725  mov     [rdi+3C0h], r12
0x18003272c  mov     rcx, [rbp+480h]; lpMem
0x180032733  call    Packet_FreeMsgBuf
0x180032738  mov     [rbp+480h], r12
0x18003273f  mov     rax, [rdi+480h]
0x180032746  mov     [rbp+480h], rax
0x18003274d  mov     [rdi+480h], r12
0x180032754  mov     rcx, [rbp+488h]; lpMem
0x18003275b  call    Dns_FreeMsgBufRpc
0x180032760  mov     [rbp+488h], r12
0x180032767  mov     rax, [rdi+488h]
0x18003276e  mov     [rbp+488h], rax
0x180032775  mov     [rdi+488h], r12
0x18003277c  jmp     loc_1800324B6
0x180032781  mov     edx, 0A4h
0x180032786  mov     ecx, 40Bh
0x18003278b  mov     r9, rbp
0x18003278e  mov     r8, r14
0x180032791  call    WPP_SF_q
0x180032796  jmp     loc_1800324C3
0x18003279b  mov     edx, 0A6h
0x1800327a0  mov     ecx, 40Bh
0x1800327a5  mov     r9, rbp
0x1800327a8  mov     r8, r14
0x1800327ab  call    WPP_SF_q
0x1800327b0  jmp     loc_1800324EA
```
