# IP_RESTRICTION_LIST::ReverseDNSLookupThreadDoWork(ulong,ulong,_OVERLAPPED *)

- ea: `0x180004290`
- end: `0x180004601`
- name: `?ReverseDNSLookupThreadDoWork@IP_RESTRICTION_LIST@@CAXKKPEAU_OVERLAPPED@@@Z`
- size: `881`
- prototype: `void __fastcall(unsigned int, unsigned int, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004110`

## callees

- `0x180001088`
- `0x1800010c8`
- `0x180004290`
- `0x180004aa6`
- `0x180004ad0`
- `0x180005010`

## import_xrefs

- `WS2_32!GetNameInfoW` at `0x18000432b`
- `WS2_32!GetNameInfoW` at `0x18000432b`
- `WS2_32!GetAddrInfoW` at `0x180004393`
- `WS2_32!GetAddrInfoW` at `0x180004393`
- `WS2_32!FreeAddrInfoW` at `0x1800045dc`
- `WS2_32!FreeAddrInfoW` at `0x1800045dc`
- `WS2_32!__imp_WSAGetLastError` at `0x18000439d`
- `WS2_32!__imp_WSAGetLastError` at `0x18000439d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004524`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000456d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004524`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000456d`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000453d`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180004586`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x18000453d`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180004586`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004420`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800044c1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004420`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800044c1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000434e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800043f5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004438`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800044d5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000434e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800043f5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004438`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800044d5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004455`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000459c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004455`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000459c`

## pseudocode

```c
void __fastcall IP_RESTRICTION_LIST::ReverseDNSLookupThreadDoWork(__int64 a1, __int64 a2, struct _OVERLAPPED *a3)
{
  unsigned __int16 *Internal; // rsi
  socklen_t v5; // edx
  signed int v6; // ebx
  int Error; // eax
  PADDRINFOW v8; // rdx
  __int16 v9; // r8
  struct sockaddr *ai_addr; // rcx
  _DWORD *v11; // rax
  _DWORD *v12; // rbx
  _DWORD *v14; // rax
  _DWORD *v15; // rdi
  _DWORD *hEvent; // rax
  PADDRINFOW ppResult; // [rsp+40h] [rbp-C0h] BYREF
  ADDRINFOW pHints; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pNodeBuffer[1032]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(pNodeBuffer, 0, 0x802u);
  Internal = (unsigned __int16 *)a3[-1].Internal;
  memset(&pHints, 0, sizeof(pHints));
  ppResult = 0;
  if ( *Internal == 2 )
  {
    v5 = 16;
  }
  else
  {
    v5 = 0;
    if ( *Internal == 23 )
      v5 = 28;
  }
  if ( GetNameInfoW((const SOCKADDR *)Internal, v5, pNodeBuffer, 0x401u, 0, 0, 4) )
    goto LABEL_9;
  if ( !a3[-1].Offset )
  {
    v6 = STRU::Copy((STRU *)a3[-1].InternalHigh, pNodeBuffer);
    goto LABEL_11;
  }
  memset(&pHints, 0, sizeof(pHints));
  pHints.ai_family = *Internal;
  pHints.ai_socktype = 1;
  pHints.ai_protocol = 6;
  if ( GetAddrInfoW(pNodeBuffer, L"80", &pHints, &ppResult) )
  {
LABEL_9:
    Error = WSAGetLastError();
    v6 = Error;
    if ( Error > 0 )
      v6 = (unsigned __int16)Error | 0x80070000;
LABEL_11:
    if ( v6 >= 0 )
      goto LABEL_46;
    goto LABEL_31;
  }
  v8 = ppResult;
  v9 = *Internal;
  while ( 1 )
  {
    ai_addr = v8->ai_addr;
    if ( v9 != ai_addr->sa_family )
      goto LABEL_29;
    if ( v9 != 2 )
      break;
    if ( *((_DWORD *)Internal + 1) == *(_DWORD *)&ai_addr->sa_data[2] )
      goto LABEL_17;
LABEL_29:
    v8 = v8->ai_next;
    if ( !v8 )
    {
      v6 = -2147023728;
      goto LABEL_31;
    }
  }
  if ( v9 != 23 )
    goto LABEL_29;
  if ( *((_QWORD *)Internal + 2) != *(_QWORD *)&ai_addr[1].sa_family
    || *((_QWORD *)Internal + 1) != *(_QWORD *)&ai_addr->sa_data[6] )
  {
    goto LABEL_29;
  }
LABEL_17:
  v6 = STRU::Copy((STRU *)a3[-1].InternalHigh, pNodeBuffer);
  if ( v6 < 0 )
    goto LABEL_31;
  v11 = operator new(0xE0u);
  v12 = v11;
  if ( !v11 )
  {
    v6 = -2147024882;
LABEL_31:
    v14 = operator new(0xE0u);
    v15 = v14;
    if ( v14 )
    {
      *v14 = 1;
      STRU::STRU((STRU *)(v14 + 2));
      v15[1] = v6;
      if ( (int)STRU::Copy((STRU *)(v15 + 2), (const unsigned __int16 *)&qword_180006FE8) >= 0 )
      {
        if ( *Internal == 2 )
        {
          *((_OWORD *)v15 + 12) = *(_OWORD *)Internal;
        }
        else if ( *Internal == 23 )
        {
          *((_OWORD *)v15 + 12) = *(_OWORD *)Internal;
          *(_OWORD *)(v15 + 51) = *(_OWORD *)(Internal + 6);
        }
        v15[55] = GetTickCount();
      }
      CLKRHashTable::InsertRecord(&IP_RESTRICTION_LIST::sm_FastDNSLookupTable, v15, 0);
      if ( _InterlockedExchangeAdd(v15, 0xFFFFFFFF) == 1 )
      {
        STRU::~STRU((STRU *)(v15 + 2));
        operator delete(v15);
      }
    }
    goto LABEL_46;
  }
  *v11 = 1;
  STRU::STRU((STRU *)(v11 + 2));
  v12[1] = 0;
  if ( (int)STRU::Copy((STRU *)(v12 + 2), pNodeBuffer) >= 0 )
  {
    if ( *Internal == 2 )
    {
      *((_OWORD *)v12 + 12) = *(_OWORD *)Internal;
    }
    else if ( *Internal == 23 )
    {
      *((_OWORD *)v12 + 12) = *(_OWORD *)Internal;
      *(_OWORD *)(v12 + 51) = *(_OWORD *)(Internal + 6);
    }
    v12[55] = GetTickCount();
    CLKRHashTable::InsertRecord(&IP_RESTRICTION_LIST::sm_FastDNSLookupTable, v12, 0);
  }
  if ( _InterlockedExchangeAdd(v12, 0xFFFFFFFF) == 1 )
  {
    STRU::~STRU((STRU *)(v12 + 2));
    operator delete(v12);
  }
  v6 = 0;
LABEL_46:
  hEvent = a3[-1].hEvent;
  if ( hEvent )
    *hEvent = v6;
  if ( LODWORD(a3[-2].hEvent) )
  {
    ((void (__fastcall *)(ULONG_PTR))a3[1].Internal)(a3[1].InternalHigh);
    operator delete(&a3[-2].hEvent);
  }
  if ( ppResult )
    FreeAddrInfoW(ppResult);
}

```

## disassembly

```asm
0x180004290  push    rbp
0x180004292  push    rbx
0x180004293  push    rsi
0x180004294  push    rdi
0x180004295  push    r14
0x180004297  push    r15
0x180004299  lea     rbp, [rsp-7A8h]
0x1800042a1  sub     rsp, 8A8h
0x1800042a8  mov     rax, cs:__security_cookie
0x1800042af  xor     rax, rsp
0x1800042b2  mov     [rbp+7D0h+var_40], rax
0x1800042b9  mov     r14, r8
0x1800042bc  lea     rcx, [rbp+7D0h+pNodeBuffer]; void *
0x1800042c0  mov     r8d, 802h; Size
0x1800042c6  xor     edx, edx; Val
0x1800042c8  call    memset_0
0x1800042cd  mov     rsi, [r14-20h]
0x1800042d1  xorps   xmm0, xmm0
0x1800042d4  movups  xmmword ptr [rsp+8D0h+pHints.ai_flags], xmm0
0x1800042d9  mov     [rsp+8D0h+ppResult], 0
0x1800042e2  movups  xmmword ptr [rsp+8D0h+pHints.ai_addrlen], xmm0
0x1800042e7  movups  xmmword ptr [rsp+8D0h+pHints.ai_addr], xmm0
0x1800042ec  cmp     word ptr [rsi], 2
0x1800042f0  jnz     short loc_1800042F9
0x1800042f2  mov     edx, 10h
0x1800042f7  jmp     short loc_180004305
0x1800042f9  xor     edx, edx
0x1800042fb  cmp     word ptr [rsi], 17h
0x1800042ff  lea     eax, [rdx+1Ch]
0x180004302  cmovz   edx, eax; SockaddrLength
0x180004305  mov     [rsp+8D0h+Flags], 4; Flags
0x18000430d  lea     r8, [rbp+7D0h+pNodeBuffer]; pNodeBuffer
0x180004311  mov     [rsp+8D0h+ServiceBufferSize], 0; ServiceBufferSize
0x180004319  mov     r9d, 401h; NodeBufferSize
0x18000431f  mov     rcx, rsi; pSockaddr
0x180004322  mov     [rsp+8D0h+pServiceBuffer], 0; pServiceBuffer
0x18000432b  call    cs:__imp_GetNameInfoW
0x180004331  mov     edi, 0E0h
0x180004336  mov     r15d, 1
0x18000433c  test    eax, eax
0x18000433e  jnz     short loc_18000439D
0x180004340  cmp     [r14-10h], eax
0x180004344  jnz     short loc_180004358
0x180004346  mov     rcx, [r14-18h]
0x18000434a  lea     rdx, [rbp+7D0h+pNodeBuffer]
0x18000434e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004354  mov     ebx, eax
0x180004356  jmp     short loc_1800043B2
0x180004358  xorps   xmm0, xmm0
0x18000435b  lea     r9, [rsp+8D0h+ppResult]; ppResult
0x180004360  movups  xmmword ptr [rsp+8D0h+pHints.ai_flags], xmm0
0x180004365  lea     r8, [rsp+8D0h+pHints]; pHints
0x18000436a  movups  xmmword ptr [rsp+8D0h+pHints.ai_addrlen], xmm0
0x18000436f  lea     rdx, pServiceName; "80"
0x180004376  movups  xmmword ptr [rsp+8D0h+pHints.ai_addr], xmm0
0x18000437b  movzx   eax, word ptr [rsi]
0x18000437e  lea     rcx, [rbp+7D0h+pNodeBuffer]; pNodeName
0x180004382  mov     [rsp+8D0h+pHints.ai_family], eax
0x180004386  mov     [rsp+8D0h+pHints.ai_socktype], r15d
0x18000438b  mov     [rsp+8D0h+pHints.ai_protocol], 6
0x180004393  call    cs:__imp_GetAddrInfoW
0x180004399  test    eax, eax
0x18000439b  jz      short loc_1800043BF
0x18000439d  call    cs:__imp_WSAGetLastError
0x1800043a3  mov     ebx, eax
0x1800043a5  test    eax, eax
0x1800043a7  jle     short loc_1800043B2
0x1800043a9  movzx   ebx, ax
0x1800043ac  or      ebx, 80070000h
0x1800043b2  test    ebx, ebx
0x1800043b4  jns     loc_1800045AA
0x1800043ba  jmp     loc_1800044A6
0x1800043bf  mov     rdx, [rsp+8D0h+ppResult]
0x1800043c4  movzx   r8d, word ptr [rsi]
0x1800043c8  mov     rcx, [rdx+20h]
0x1800043cc  cmp     r8w, [rcx]
0x1800043d0  jnz     loc_180004494
0x1800043d6  cmp     r8w, 2
0x1800043db  jnz     loc_18000446A
0x1800043e1  mov     eax, [rsi+4]
0x1800043e4  cmp     eax, [rcx+4]
0x1800043e7  jnz     loc_180004494
0x1800043ed  mov     rcx, [r14-18h]
0x1800043f1  lea     rdx, [rbp+7D0h+pNodeBuffer]
0x1800043f5  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800043fb  mov     ebx, eax
0x1800043fd  test    eax, eax
0x1800043ff  js      loc_1800044A6
0x180004405  mov     rcx, rdi; Size
0x180004408  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000440d  mov     rbx, rax
0x180004410  test    rax, rax
0x180004413  jz      loc_180004548
0x180004419  lea     rcx, [rax+8]
0x18000441d  mov     [rax], r15d
0x180004420  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004426  lea     rdi, [rbx+8]
0x18000442a  mov     dword ptr [rbx+4], 0
0x180004431  mov     rcx, rdi
0x180004434  lea     rdx, [rbp+7D0h+pNodeBuffer]
0x180004438  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000443e  test    eax, eax
0x180004440  jns     loc_1800044F6
0x180004446  or      eax, 0FFFFFFFFh
0x180004449  lock xadd [rbx], eax
0x18000444d  cmp     eax, r15d
0x180004450  jnz     short loc_180004463
0x180004452  mov     rcx, rdi
0x180004455  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000445b  mov     rcx, rbx; Block
0x18000445e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004463  xor     ebx, ebx
0x180004465  jmp     loc_1800045AA
0x18000446a  cmp     r8w, 17h
0x18000446f  jnz     short loc_180004494
0x180004471  mov     rax, [rcx+10h]
0x180004475  cmp     [rsi+10h], rax
0x180004479  jnz     short loc_18000448A
0x18000447b  mov     rax, [rcx+8]
0x18000447f  cmp     [rsi+8], rax
0x180004483  jnz     short loc_18000448A
0x180004485  mov     al, r15b
0x180004488  jmp     short loc_18000448C
0x18000448a  xor     al, al
0x18000448c  test    al, al
0x18000448e  jnz     loc_1800043ED
0x180004494  mov     rdx, [rdx+28h]
0x180004498  test    rdx, rdx
0x18000449b  jnz     loc_1800043C8
0x1800044a1  mov     ebx, 80070490h
0x1800044a6  mov     rcx, rdi; Size
0x1800044a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800044ae  mov     rdi, rax
0x1800044b1  test    rax, rax
0x1800044b4  jz      loc_1800045AA
0x1800044ba  lea     rcx, [rax+8]
0x1800044be  mov     [rax], r15d
0x1800044c1  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800044c7  lea     rdx, qword_180006FE8
0x1800044ce  mov     [rdi+4], ebx
0x1800044d1  lea     rcx, [rdi+8]
0x1800044d5  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800044db  test    eax, eax
0x1800044dd  js      loc_180004579
0x1800044e3  cmp     word ptr [rsi], 2
0x1800044e7  jnz     short loc_180004552
0x1800044e9  movups  xmm0, xmmword ptr [rsi]
0x1800044ec  movdqu  xmmword ptr [rdi+0C0h], xmm0
0x1800044f4  jmp     short loc_18000456D
0x1800044f6  cmp     word ptr [rsi], 2
0x1800044fa  jnz     short loc_180004509
0x1800044fc  movups  xmm0, xmmword ptr [rsi]
0x1800044ff  movdqu  xmmword ptr [rbx+0C0h], xmm0
0x180004507  jmp     short loc_180004524
0x180004509  cmp     word ptr [rsi], 17h
0x18000450d  jnz     short loc_180004524
0x18000450f  movups  xmm0, xmmword ptr [rsi]
0x180004512  movups  xmmword ptr [rbx+0C0h], xmm0
0x180004519  movups  xmm1, xmmword ptr [rsi+0Ch]
0x18000451d  movups  xmmword ptr [rbx+0CCh], xmm1
0x180004524  call    cs:__imp_GetTickCount
0x18000452a  xor     r8d, r8d
0x18000452d  lea     rcx, ?sm_FastDNSLookupTable@IP_RESTRICTION_LIST@@0VFAST_DNS_LOOKUP_HASH@@A; FAST_DNS_LOOKUP_HASH IP_RESTRICTION_LIST::sm_FastDNSLookupTable
0x180004534  mov     rdx, rbx
0x180004537  mov     [rbx+0DCh], eax
0x18000453d  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180004543  jmp     loc_180004446
0x180004548  mov     ebx, 8007000Eh
0x18000454d  jmp     loc_1800044A6
0x180004552  cmp     word ptr [rsi], 17h
0x180004556  jnz     short loc_18000456D
0x180004558  movups  xmm0, xmmword ptr [rsi]
0x18000455b  movups  xmmword ptr [rdi+0C0h], xmm0
0x180004562  movups  xmm1, xmmword ptr [rsi+0Ch]
0x180004566  movups  xmmword ptr [rdi+0CCh], xmm1
0x18000456d  call    cs:__imp_GetTickCount
0x180004573  mov     [rdi+0DCh], eax
0x180004579  xor     r8d, r8d
0x18000457c  lea     rcx, ?sm_FastDNSLookupTable@IP_RESTRICTION_LIST@@0VFAST_DNS_LOOKUP_HASH@@A; FAST_DNS_LOOKUP_HASH IP_RESTRICTION_LIST::sm_FastDNSLookupTable
0x180004583  mov     rdx, rdi
0x180004586  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18000458c  or      eax, 0FFFFFFFFh
0x18000458f  lock xadd [rdi], eax
0x180004593  cmp     eax, r15d
0x180004596  jnz     short loc_1800045AA
0x180004598  lea     rcx, [rdi+8]
0x18000459c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800045a2  mov     rcx, rdi; Block
0x1800045a5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800045aa  mov     rax, [r14-8]
0x1800045ae  test    rax, rax
0x1800045b1  jz      short loc_1800045B5
0x1800045b3  mov     [rax], ebx
0x1800045b5  cmp     dword ptr [r14-28h], 0
0x1800045ba  jz      short loc_1800045D2
0x1800045bc  mov     rcx, [r14+28h]
0x1800045c0  mov     rax, [r14+20h]
0x1800045c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045c9  lea     rcx, [r14-28h]; Block
0x1800045cd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800045d2  mov     rcx, [rsp+8D0h+ppResult]; pAddrInfo
0x1800045d7  test    rcx, rcx
0x1800045da  jz      short loc_1800045E2
0x1800045dc  call    cs:__imp_FreeAddrInfoW
0x1800045e2  mov     rcx, [rbp+7D0h+var_40]
0x1800045e9  xor     rcx, rsp; StackCookie
0x1800045ec  call    __security_check_cookie
0x1800045f1  add     rsp, 8A8h
0x1800045f8  pop     r15
0x1800045fa  pop     r14
0x1800045fc  pop     rdi
0x1800045fd  pop     rsi
0x1800045fe  pop     rbx
0x1800045ff  pop     rbp
0x180004600  retn
```
