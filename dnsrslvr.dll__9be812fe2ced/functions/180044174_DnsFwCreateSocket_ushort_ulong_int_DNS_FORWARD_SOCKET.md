# DnsFwCreateSocket(ushort,ulong,int,_DNS_FORWARD_SOCKET * *)

- ea: `0x180044174`
- end: `0x1800444c9`
- name: `?DnsFwCreateSocket@@YAKGKHPEAPEAU_DNS_FORWARD_SOCKET@@@Z`
- size: `853`
- prototype: `__int64 __fastcall(unsigned __int16, int, int, RTL_SRWLOCK **)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004345c`
- `0x180043eb8`

## callees

- `0x180008b00`
- `0x180044174`
- `0x1800444d0`
- `0x180046ec0`
- `0x180047818`
- `0x1800832b4`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004435e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004435e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044245`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180044245`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044257`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180044257`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18004428d`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18004428d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004445f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004445f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004440a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004440a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18004434f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18004434f`
- `WS2_32!WSASocketA` at `0x18004430d`
- `WS2_32!WSASocketA` at `0x18004430d`
- `WS2_32!__imp_bind` at `0x18004439d`
- `WS2_32!__imp_bind` at `0x18004439d`
- `WS2_32!__imp_htonl` at `0x1800442c1`
- `WS2_32!__imp_htonl` at `0x1800442c1`
- `WS2_32!__imp_htons` at `0x1800442e4`
- `WS2_32!__imp_htons` at `0x1800442e4`
- `WS2_32!__imp_listen` at `0x1800443d9`
- `WS2_32!__imp_listen` at `0x1800443d9`
- `WS2_32!__imp_WSAGetLastError` at `0x18004431d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800443a8`
- `WS2_32!__imp_WSAGetLastError` at `0x1800443e4`
- `WS2_32!__imp_WSAGetLastError` at `0x18004431d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800443a8`
- `WS2_32!__imp_WSAGetLastError` at `0x1800443e4`

## pseudocode

```c
__int64 __fastcall DnsFwCreateSocket(unsigned __int16 a1, int a2, int a3, RTL_SRWLOCK **a4)
{
  int v5; // ebx
  int v8; // ecx
  unsigned int v9; // ebx
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v11; // rax
  RTL_SRWLOCK *v12; // rdi
  RTL_SRWLOCK *v13; // rcx
  RTL_SRWLOCK *v14; // rax
  void *v15; // rax
  int Error; // eax
  PTP_IO ThreadpoolIo; // rax
  signed int LastError; // eax
  int v19; // eax
  int v20; // eax
  struct _LIST_ENTRY *v21; // rax
  unsigned int v22; // eax
  struct sockaddr name[8]; // [rsp+40h] [rbp-B8h] BYREF

  v5 = a1;
  memset_0(name, 0, sizeof(name));
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_ddq(v8, 14, (unsigned int)WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids, v5, a2, 0);
  if ( (_WORD)v5 != 2 && v5 != 23 )
  {
    v9 = -2147024809;
    goto LABEL_45;
  }
  if ( a2 != 17 && a2 != 6 )
  {
    v9 = -2147024809;
    goto LABEL_45;
  }
  if ( !a4 )
  {
    v9 = -2147024809;
    goto LABEL_45;
  }
  *a4 = 0;
  ProcessHeap = GetProcessHeap();
  v11 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 8u, 0x50u);
  v12 = v11;
  if ( !v11 )
  {
    v9 = -2147024882;
    goto LABEL_45;
  }
  v11[1].Ptr = v11;
  v13 = v11 + 4;
  v11->Ptr = v11;
  v14 = v11 + 2;
  v14[1].Ptr = v14;
  v14->Ptr = v14;
  InitializeSRWLock(v13);
  LODWORD(v12[5].Ptr) = 1;
  LOWORD(v12[7].Ptr) = v5;
  LODWORD(v12[8].Ptr) = a2;
  HIDWORD(v12[7].Ptr) = 2;
  if ( a2 == 6 )
    HIDWORD(v12[7].Ptr) = 1;
  name[0].sa_family = v5;
  if ( (_WORD)v5 == 2 )
  {
    *(_DWORD *)&name[0].sa_data[2] = htonl(0x7F000001u);
  }
  else
  {
    *(_OWORD *)&name[0].sa_data[6] = 0;
    name[1].sa_data[5] = 1;
  }
  *(_WORD *)name[0].sa_data = htons(0x35u);
  v15 = (void *)WSASocketA(LOWORD(v12[7].Ptr), HIDWORD(v12[7].Ptr), (int)v12[8].Ptr, 0, 0, 1u);
  v12[6].Ptr = v15;
  if ( v15 == (void *)-1LL )
  {
    Error = WSAGetLastError();
    v9 = Error;
    if ( Error > 0 )
      v9 = (unsigned __int16)Error | 0x80070000;
LABEL_44:
    DnsFwDerefSocket((struct _DNS_FORWARD_SOCKET *)v12);
    goto LABEL_45;
  }
  ThreadpoolIo = CreateThreadpoolIo(v15, DnsFwIoCompletionCallback, 0, 0);
  v12[9].Ptr = ThreadpoolIo;
  if ( !ThreadpoolIo )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (v9 & 0x80000000) == 0 )
      v9 = -2147418113;
    goto LABEL_44;
  }
  if ( a3 )
  {
    if ( bind((SOCKET)v12[6].Ptr, name, 128) == -1 )
    {
      v19 = WSAGetLastError();
      v9 = v19;
      if ( v19 > 0 )
        v9 = (unsigned __int16)v19 | 0x80070000;
      goto LABEL_44;
    }
    if ( LODWORD(v12[8].Ptr) == 6 && listen((SOCKET)v12[6].Ptr, 0x7FFFFFFF) == -1 )
    {
      v20 = WSAGetLastError();
      v9 = v20;
      if ( v20 > 0 )
        v9 = (unsigned __int16)v20 | 0x80070000;
      goto LABEL_44;
    }
  }
  EnterCriticalSection(&g_SocketListLock);
  if ( g_fForwarderRunning )
  {
    v21 = off_1800AB260;
    v9 = 0;
    if ( off_1800AB260->Flink != &g_SocketList )
      __fastfail(3u);
    v12->Ptr = &g_SocketList;
    v12[1].Ptr = v21;
    v21->Flink = (struct _LIST_ENTRY *)v12;
    off_1800AB260 = (struct _LIST_ENTRY *)v12;
    *a4 = v12;
    v12 = 0;
  }
  else
  {
    v9 = 995;
  }
  LeaveCriticalSection(&g_SocketListLock);
  if ( v12 )
    goto LABEL_44;
LABEL_45:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    v22 = WX_WIN32_FROM_HR(v9);
    WPP_SF_d(1035, 15, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids, v22);
  }
  return WX_WIN32_FROM_HR(v9);
}

```

## disassembly

```asm
0x180044174  mov     [rsp+arg_8], rbx
0x180044179  push    rbp
0x18004417a  push    rsi
0x18004417b  push    rdi
0x18004417c  push    r12
0x18004417e  push    r14
0x180044180  sub     rsp, 0D0h
0x180044187  mov     rax, cs:__security_cookie
0x18004418e  xor     rax, rsp
0x180044191  mov     [rsp+0F8h+var_38], rax
0x180044199  mov     ebp, r8d
0x18004419c  movzx   ebx, cx
0x18004419f  mov     esi, edx
0x1800441a1  mov     [rsp+0F8h+var_C4], 0
0x1800441a9  xor     edx, edx; Val
0x1800441ab  lea     rcx, [rsp+0F8h+name]; void *
0x1800441b0  mov     r8d, 80h; Size
0x1800441b6  mov     r14, r9
0x1800441b9  call    memset_0
0x1800441be  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800441c5  jz      short loc_1800441E8
0x1800441c7  mov     r9d, ebx
0x1800441ca  mov     qword ptr [rsp+0F8h+dwFlags], 0
0x1800441d3  mov     edx, 0Eh
0x1800441d8  mov     [rsp+0F8h+g], esi
0x1800441dc  lea     r8, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids
0x1800441e3  call    WPP_SF_ddq
0x1800441e8  mov     r12d, 2
0x1800441ee  cmp     bx, r12w
0x1800441f2  jz      short loc_18004420B
0x1800441f4  cmp     ebx, 17h
0x1800441f7  jz      short loc_18004420B
0x1800441f9  mov     ebx, 80070057h
0x1800441fe  mov     [rsp+0F8h+var_C4], 0BAh
0x180044206  jmp     loc_180044472
0x18004420b  cmp     esi, 11h
0x18004420e  jz      short loc_180044227
0x180044210  cmp     esi, 6
0x180044213  jz      short loc_180044227
0x180044215  mov     ebx, 80070057h
0x18004421a  mov     [rsp+0F8h+var_C4], 0BBh
0x180044222  jmp     loc_180044472
0x180044227  test    r14, r14
0x18004422a  jnz     short loc_18004423E
0x18004422c  mov     ebx, 80070057h
0x180044231  mov     [rsp+0F8h+var_C4], 0BCh
0x180044239  jmp     loc_180044472
0x18004423e  mov     qword ptr [r14], 0
0x180044245  call    cs:__imp_GetProcessHeap
0x18004424b  mov     edx, 8; dwFlags
0x180044250  mov     rcx, rax; hHeap
0x180044253  lea     r8d, [rdx+48h]; dwBytes
0x180044257  call    cs:__imp_HeapAlloc
0x18004425d  mov     rdi, rax
0x180044260  test    rax, rax
0x180044263  jnz     short loc_180044277
0x180044265  mov     ebx, 8007000Eh
0x18004426a  mov     [rsp+0F8h+var_C4], 0C3h
0x180044272  jmp     loc_180044472
0x180044277  mov     [rax+8], rdi
0x18004427b  lea     rcx, [rdi+20h]; SRWLock
0x18004427f  mov     [rax], rdi
0x180044282  add     rax, 10h
0x180044286  mov     [rax+8], rax
0x18004428a  mov     [rax], rax
0x18004428d  call    cs:__imp_InitializeSRWLock
0x180044293  mov     dword ptr [rdi+28h], 1
0x18004429a  mov     [rdi+38h], bx
0x18004429e  mov     [rdi+40h], esi
0x1800442a1  mov     [rdi+3Ch], r12d
0x1800442a5  cmp     esi, 6
0x1800442a8  jnz     short loc_1800442B1
0x1800442aa  mov     dword ptr [rdi+3Ch], 1
0x1800442b1  mov     word ptr [rsp+0F8h+name], bx
0x1800442b6  cmp     bx, r12w
0x1800442ba  jnz     short loc_1800442CD
0x1800442bc  mov     ecx, 7F000001h; hostlong
0x1800442c1  call    cs:__imp_htonl
0x1800442c7  mov     dword ptr [rsp+0F8h+name+4], eax
0x1800442cb  jmp     short loc_1800442DF
0x1800442cd  cmp     ebx, 17h
0x1800442d0  jnz     short loc_1800442EF
0x1800442d2  xorps   xmm0, xmm0
0x1800442d5  movups  xmmword ptr [rsp+0F8h+name+8], xmm0
0x1800442da  mov     [rsp+0F8h+name+17h], 1
0x1800442df  mov     ecx, 35h ; '5'; hostshort
0x1800442e4  call    cs:__imp_htons
0x1800442ea  mov     word ptr [rsp+0F8h+name+2], ax
0x1800442ef  movzx   ecx, word ptr [rdi+38h]; af
0x1800442f3  xor     r9d, r9d; lpProtocolInfo
0x1800442f6  mov     r8d, [rdi+40h]; protocol
0x1800442fa  mov     edx, [rdi+3Ch]; type
0x1800442fd  mov     [rsp+0F8h+dwFlags], 1; dwFlags
0x180044305  mov     [rsp+0F8h+g], 0; g
0x18004430d  call    cs:__imp_WSASocketA
0x180044313  mov     [rdi+30h], rax
0x180044317  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004431b  jnz     short loc_18004433F
0x18004431d  call    cs:__imp_WSAGetLastError
0x180044323  mov     ebx, eax
0x180044325  test    eax, eax
0x180044327  jle     short loc_180044332
0x180044329  movzx   ebx, ax
0x18004432c  or      ebx, 80070000h
0x180044332  mov     [rsp+0F8h+var_C4], 0EEh
0x18004433a  jmp     loc_18004446A
0x18004433f  xor     r9d, r9d; pcbe
0x180044342  lea     rdx, ?DnsFwIoCompletionCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x180044349  xor     r8d, r8d; pv
0x18004434c  mov     rcx, rax; fl
0x18004434f  call    cs:__imp_CreateThreadpoolIo
0x180044355  mov     [rdi+48h], rax
0x180044359  test    rax, rax
0x18004435c  jnz     short loc_18004438A
0x18004435e  call    cs:__imp_GetLastError
0x180044364  mov     ebx, eax
0x180044366  test    eax, eax
0x180044368  jle     short loc_180044373
0x18004436a  movzx   ebx, ax
0x18004436d  or      ebx, 80070000h
0x180044373  test    ebx, ebx
0x180044375  mov     [rsp+0F8h+var_C4], 0F4h
0x18004437d  mov     eax, 8000FFFFh
0x180044382  cmovns  ebx, eax
0x180044385  jmp     loc_18004446A
0x18004438a  test    ebp, ebp
0x18004438c  jz      short loc_180044403
0x18004438e  mov     rcx, [rdi+30h]; s
0x180044392  lea     rdx, [rsp+0F8h+name]; name
0x180044397  mov     r8d, 80h; namelen
0x18004439d  call    cs:__imp_bind
0x1800443a3  cmp     eax, 0FFFFFFFFh
0x1800443a6  jnz     short loc_1800443CA
0x1800443a8  call    cs:__imp_WSAGetLastError
0x1800443ae  mov     ebx, eax
0x1800443b0  test    eax, eax
0x1800443b2  jle     short loc_1800443BD
0x1800443b4  movzx   ebx, ax
0x1800443b7  or      ebx, 80070000h
0x1800443bd  mov     [rsp+0F8h+var_C4], 0FFh
0x1800443c5  jmp     loc_18004446A
0x1800443ca  cmp     dword ptr [rdi+40h], 6
0x1800443ce  jnz     short loc_180044403
0x1800443d0  mov     rcx, [rdi+30h]; s
0x1800443d4  mov     edx, 7FFFFFFFh; backlog
0x1800443d9  call    cs:__imp_listen
0x1800443df  cmp     eax, 0FFFFFFFFh
0x1800443e2  jnz     short loc_180044403
0x1800443e4  call    cs:__imp_WSAGetLastError
0x1800443ea  mov     ebx, eax
0x1800443ec  test    eax, eax
0x1800443ee  jle     short loc_1800443F9
0x1800443f0  movzx   ebx, ax
0x1800443f3  or      ebx, 80070000h
0x1800443f9  mov     [rsp+0F8h+var_C4], 105h
0x180044401  jmp     short loc_18004446A
0x180044403  lea     rcx, ?g_SocketListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004440a  call    cs:__imp_EnterCriticalSection
0x180044410  cmp     cs:?g_fForwarderRunning@@3HA, 0; int g_fForwarderRunning
0x180044417  jnz     short loc_180044428
0x180044419  mov     ebx, 3E3h
0x18004441e  mov     [rsp+0F8h+var_C4], 110h
0x180044426  jmp     short loc_180044458
0x180044428  mov     rax, cs:off_1800AB260
0x18004442f  lea     rcx, ?g_SocketList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_SocketList
0x180044436  xor     ebx, ebx
0x180044438  cmp     [rax], rcx
0x18004443b  jz      short loc_180044442
0x18004443d  lea     ecx, [rbx+3]
0x180044440  int     29h; Win8: RtlFailFast(ecx)
0x180044442  mov     [rdi], rcx
0x180044445  mov     [rdi+8], rax
0x180044449  mov     [rax], rdi
0x18004444c  mov     cs:off_1800AB260, rdi
0x180044453  mov     [r14], rdi
0x180044456  xor     edi, edi
0x180044458  lea     rcx, ?g_SocketListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004445f  call    cs:__imp_LeaveCriticalSection
0x180044465  test    rdi, rdi
0x180044468  jz      short loc_180044472
0x18004446a  mov     rcx, rdi; lpMem
0x18004446d  call    ?DnsFwDerefSocket@@YAXPEAU_DNS_FORWARD_SOCKET@@@Z; DnsFwDerefSocket(_DNS_FORWARD_SOCKET *)
0x180044472  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180044479  jz      short loc_18004449B
0x18004447b  mov     ecx, ebx
0x18004447d  call    WX_WIN32_FROM_HR
0x180044482  mov     r9d, eax
0x180044485  lea     r8, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids
0x18004448c  mov     edx, 0Fh
0x180044491  mov     ecx, 40Bh
0x180044496  call    WPP_SF_d
0x18004449b  mov     ecx, ebx
0x18004449d  call    WX_WIN32_FROM_HR
0x1800444a2  mov     rcx, [rsp+0F8h+var_38]
0x1800444aa  xor     rcx, rsp; StackCookie
0x1800444ad  call    __security_check_cookie
0x1800444b2  mov     rbx, [rsp+0F8h+arg_8]
0x1800444ba  add     rsp, 0D0h
0x1800444c1  pop     r14
0x1800444c3  pop     r12
0x1800444c5  pop     rdi
0x1800444c6  pop     rsi
0x1800444c7  pop     rbp
0x1800444c8  retn
```
