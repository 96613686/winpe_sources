# HTraceDataCollector::Start(void)

- ea: `0x1800e16b0`
- end: `0x1800e1d31`
- name: `?Start@HTraceDataCollector@@UEAAJXZ`
- size: `1665`
- prototype: `__int64 __fastcall(HTraceDataCollector *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800bb5f0`
- `0x1800e16b0`
- `0x180135668`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e182a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e182a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e1820`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e1820`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e1cf8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e1cf8`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800e180f`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800e180f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e16f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e16f5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800e1ac5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800e1ac5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e1d06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e1d06`

## pseudocode

```c
__int64 __fastcall HTraceDataCollector::Start(HTraceDataCollector *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // r13
  void *v3; // r12
  int v4; // eax
  unsigned int v5; // edi
  __int64 v6; // rbx
  int *v7; // r9
  __int64 v8; // rbx
  HANDLE v9; // rax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rax
  __int64 v16; // rax
  int i; // r14d
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v23; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+78h] [rbp-88h] BYREF
  _WORD v25[8]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v26[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v27[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v28[64]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v29[64]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 v30[64]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v31[64]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v32[64]; // [rsp+390h] [rbp+290h] BYREF
  unsigned __int16 v33[64]; // [rsp+410h] [rbp+310h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 144);
  v25[0] = 0;
  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  v4 = (*(__int64 (__fastcall **)(_QWORD, _WORD *))(**((_QWORD **)this + 37) + 400LL))(*((_QWORD *)this + 37), v25);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v8 = -1;
    if ( v25[0] == 0xFFFF )
    {
      v9 = OpenEventW(2u, 0, L"Global\\WDC.A29E4D2F-BEAB-4FD0-9FCC-1CD79DBFD975");
      v3 = v9;
      if ( v9 )
      {
        if ( !SetEvent(v9) )
          GetLastError();
      }
    }
    v10 = HDataCollector::Start(this);
    v5 = v10;
    if ( v10 < 0 )
    {
      v24 = 0;
      v23 = v10;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_80;
      }
      PlaiWhoAmI(v27, 0x4000000000000800uLL);
      do
        ++v8;
      while ( v27[v8] );
      goto LABEL_19;
    }
    if ( !*((_QWORD *)this + 38) )
    {
      v5 = -2147024882;
      v23 = -2147024882;
      v24 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_80;
      }
      PlaiWhoAmI(v28, 0x4000000000000800uLL);
      do
        ++v8;
      while ( v28[v8] );
      goto LABEL_19;
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 37) + 136LL))(
            *((_QWORD *)this + 37),
            *(_QWORD *)(*((_QWORD *)this + 9) + 40LL));
    v5 = v11;
    if ( v11 < 0 )
    {
      v24 = 0;
      v23 = v11;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_80;
      }
      PlaiWhoAmI(v29, 0x4000000000000800uLL);
      do
        ++v8;
      while ( v29[v8] );
      goto LABEL_19;
    }
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000100LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000100LL) )
    {
      v12 = *((_QWORD *)this + 9);
      v13 = *(_QWORD *)(v12 + 40);
      v14 = *(_QWORD *)(v12 + 24);
      if ( v13 )
      {
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)(v13 + 2 * v15) );
      }
      if ( v14 )
      {
        v16 = -1;
        do
          ++v16;
        while ( *(_WORD *)(v14 + 2 * v16) );
      }
      EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_DC_OPEN, 2, v14);
    }
    if ( v25[0] == 0xFFFF )
    {
      for ( i = 10; i >= 0; --i )
      {
        v18 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 38) + 496LL))(
                *((_QWORD *)this + 38),
                0xFFFFFFFFLL);
        v5 = v18;
        if ( v18 >= 0 )
          break;
        if ( !i || v18 != -2144337750 )
        {
          v23 = v18;
          v24 = 0;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v30, 0x4000000000000800uLL);
            do
              ++v8;
            while ( v30[v8] );
            goto LABEL_19;
          }
          goto LABEL_80;
        }
        Sleep(0xC8u);
      }
    }
    else
    {
      v19 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 38) + 496LL))(
              *((_QWORD *)this + 38),
              0xFFFFFFFFLL);
      v5 = v19;
      if ( v19 < 0 )
      {
        v24 = 0;
        v23 = v19;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_80;
        }
        PlaiWhoAmI(v31, 0x4000000000000800uLL);
        do
          ++v8;
        while ( v31[v8] );
        goto LABEL_19;
      }
    }
    v20 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 37) + 504LL))(
            *((_QWORD *)this + 37),
            *((_QWORD *)this + 9) + 72LL);
    v5 = v20;
    if ( v20 >= 0 )
    {
      _InterlockedExchange((volatile __int32 *)(*((_QWORD *)this + 9) + 64LL), 1);
      v21 = (*(__int64 (__fastcall **)(HTraceDataCollector *))(*(_QWORD *)this + 56LL))(this);
      v5 = v21;
      if ( v21 >= 0 )
      {
        if ( !*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 9) + 56LL) + 80LL) )
          HDataCollector::CompleteDataCollector(this);
        goto LABEL_80;
      }
      v24 = 0;
      v23 = v21;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_80;
      }
      PlaiWhoAmI(v33, 0x4000000000000800uLL);
      do
        ++v8;
      while ( v33[v8] );
    }
    else
    {
      v24 = 0;
      v23 = v20;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_80;
      }
      PlaiWhoAmI(v32, 0x4000000000000800uLL);
      do
        ++v8;
      while ( v32[v8] );
    }
LABEL_19:
    v7 = &v23;
LABEL_8:
    EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)v7);
    goto LABEL_80;
  }
  v23 = 0;
  v24 = v4;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v26, 0x4000000000000800uLL);
    v6 = -1;
    do
      ++v6;
    while ( v26[v6] );
    v7 = &v24;
    goto LABEL_8;
  }
LABEL_80:
  LeaveCriticalSection(v1);
  if ( v3 )
    CloseHandle(v3);
  return v5;
}

```

## disassembly

```asm
0x1800e16b0  push    rbp
0x1800e16b2  push    rbx
0x1800e16b3  push    rsi
0x1800e16b4  push    rdi
0x1800e16b5  push    r12
0x1800e16b7  push    r13
0x1800e16b9  push    r14
0x1800e16bb  push    r15
0x1800e16bd  lea     rbp, [rsp-3A8h]
0x1800e16c5  sub     rsp, 4A8h
0x1800e16cc  mov     rax, cs:__security_cookie
0x1800e16d3  xor     rax, rsp
0x1800e16d6  mov     [rbp+3E0h+var_50], rax
0x1800e16dd  lea     r13, [rcx+90h]
0x1800e16e4  mov     rsi, rcx
0x1800e16e7  xor     r14d, r14d
0x1800e16ea  mov     rcx, r13; lpCriticalSection
0x1800e16ed  mov     [rbp+3E0h+var_460], r14w
0x1800e16f2  mov     r12d, r14d
0x1800e16f5  call    cs:__imp_EnterCriticalSection
0x1800e16fb  mov     rcx, [rsi+128h]
0x1800e1702  lea     rdx, [rbp+3E0h+var_460]
0x1800e1706  mov     rax, [rcx]
0x1800e1709  mov     rax, [rax+190h]
0x1800e1710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1715  mov     edi, eax
0x1800e1717  test    eax, eax
0x1800e1719  jns     loc_1800E17F9
0x1800e171f  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800e1726  mov     [rsp+4E0h+var_470], r14d
0x1800e172b  mov     [rsp+4E0h+var_468], eax
0x1800e172f  jz      loc_1800E1CF5
0x1800e1735  mov     rdx, 4000000000000800h; unsigned __int64
0x1800e173f  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800e1746  jz      loc_1800E1CF5
0x1800e174c  mov     rax, cs:qword_180169748
0x1800e1753  and     rax, rdx
0x1800e1756  cmp     cs:qword_180169748, rax
0x1800e175d  jnz     loc_1800E1CF5
0x1800e1763  lea     rcx, [rbp+3E0h+var_450]; unsigned __int16 *
0x1800e1767  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800e176c  lea     rax, [rbp+3E0h+var_450]
0x1800e1770  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800e1774  inc     rbx
0x1800e1777  cmp     [rax+rbx*2], r14w
0x1800e177c  jnz     short loc_1800E1774
0x1800e177e  lea     ecx, [rbx+rbx]
0x1800e1781  mov     r15d, 1
0x1800e1787  add     rcx, 2
0x1800e178b  lea     rax, [rbp+3E0h+var_450]
0x1800e178f  mov     [rsp+4E0h+var_480], rcx
0x1800e1794  lea     r9, [rsp+4E0h+var_468]
0x1800e1799  lea     rcx, [rsp+4E0h+var_470]
0x1800e179e  mov     [rsp+4E0h+var_488], rax
0x1800e17a3  lea     rdx, PLA_EVENT_ERROR
0x1800e17aa  mov     [rsp+4E0h+var_490], 1Bh
0x1800e17b3  lea     rax, aHtracedatacoll_2; "HTraceDataCollector::Start"
0x1800e17ba  mov     [rsp+4E0h+var_498], rax
0x1800e17bf  mov     eax, 4
0x1800e17c4  mov     [rsp+4E0h+var_4A0], rax
0x1800e17c9  mov     [rsp+4E0h+var_4A8], rcx
0x1800e17ce  lea     rcx, byte_180147320
0x1800e17d5  mov     [rsp+4E0h+var_4B0], r15
0x1800e17da  mov     [rsp+4E0h+var_4B8], rcx
0x1800e17df  lea     r8d, [rax+1]
0x1800e17e3  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800e17ea  mov     [rsp+4E0h+var_4C0], rax
0x1800e17ef  call    EventingWriteEvent
0x1800e17f4  jmp     loc_1800E1CF5
0x1800e17f9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800e17fd  cmp     bx, [rbp+3E0h+var_460]
0x1800e1801  jnz     short loc_1800E1830
0x1800e1803  lea     r8, Name; "Global\\WDC.A29E4D2F-BEAB-4FD0-9FCC-1CD"...
0x1800e180a  xor     edx, edx; bInheritHandle
0x1800e180c  lea     ecx, [rbx+3]; dwDesiredAccess
0x1800e180f  call    cs:__imp_OpenEventW
0x1800e1815  mov     r12, rax
0x1800e1818  test    rax, rax
0x1800e181b  jz      short loc_1800E1830
0x1800e181d  mov     rcx, rax; hEvent
0x1800e1820  call    cs:__imp_SetEvent
0x1800e1826  test    eax, eax
0x1800e1828  jnz     short loc_1800E1830
0x1800e182a  call    cs:__imp_GetLastError
0x1800e1830  mov     rcx, rsi; this
0x1800e1833  call    ?Start@HDataCollector@@UEAAJXZ; HDataCollector::Start(void)
0x1800e1838  mov     edi, eax
0x1800e183a  test    eax, eax
0x1800e183c  jns     loc_1800E18C2
0x1800e1842  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800e1849  mov     [rsp+4E0h+var_468], r14d
0x1800e184e  mov     [rsp+4E0h+var_470], eax
0x1800e1852  jz      loc_1800E1CF5
0x1800e1858  mov     rdx, 4000000000000800h; unsigned __int64
0x1800e1862  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800e1869  jz      loc_1800E1CF5
0x1800e186f  mov     rax, cs:qword_180169748
0x1800e1876  and     rax, rdx
0x1800e1879  cmp     cs:qword_180169748, rax
0x1800e1880  jnz     loc_1800E1CF5
0x1800e1886  lea     rcx, [rbp+3E0h+var_3D0]; unsigned __int16 *
0x1800e188a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800e188f  lea     rax, [rbp+3E0h+var_3D0]
0x1800e1893  inc     rbx
0x1800e1896  cmp     [rax+rbx*2], r14w
0x1800e189b  jnz     short loc_1800E1893
0x1800e189d  lea     rax, [rbp+3E0h+var_3D0]
0x1800e18a1  mov     r15d, 1
0x1800e18a7  lea     ecx, [rbx+rbx]
0x1800e18aa  add     rcx, 2
0x1800e18ae  lea     r9, [rsp+4E0h+var_470]
0x1800e18b3  mov     [rsp+4E0h+var_480], rcx
0x1800e18b8  lea     rcx, [rsp+4E0h+var_468]
0x1800e18bd  jmp     loc_1800E179E
0x1800e18c2  cmp     [rsi+130h], r14
0x1800e18c9  jnz     short loc_1800E193D
0x1800e18cb  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800e18d2  mov     edi, 8007000Eh
0x1800e18d7  mov     [rsp+4E0h+var_470], edi
0x1800e18db  mov     [rsp+4E0h+var_468], r14d
0x1800e18e0  jz      loc_1800E1CF5
0x1800e18e6  mov     rdx, 4000000000000800h; unsigned __int64
0x1800e18f0  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800e18f7  jz      loc_1800E1CF5
0x1800e18fd  mov     rax, cs:qword_180169748
0x1800e1904  and     rax, rdx
0x1800e1907  cmp     cs:qword_180169748, rax
0x1800e190e  jnz     loc_1800E1CF5
0x1800e1914  lea     rcx, [rbp+3E0h+var_350]; unsigned __int16 *
0x1800e191b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800e1920  lea     rax, [rbp+3E0h+var_350]
0x1800e1927  inc     rbx
0x1800e192a  cmp     [rax+rbx*2], r14w
0x1800e192f  jnz     short loc_1800E1927
0x1800e1931  lea     rax, [rbp+3E0h+var_350]
0x1800e1938  jmp     loc_1800E18A1
0x1800e193d  mov     rcx, [rsi+128h]
0x1800e1944  mov     rdx, [rsi+48h]
0x1800e1948  mov     rax, [rcx]
0x1800e194b  mov     rdx, [rdx+28h]
0x1800e194f  mov     rax, [rax+88h]
0x1800e1956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e195b  mov     edi, eax
0x1800e195d  test    eax, eax
0x1800e195f  jns     short loc_1800E19CE
0x1800e1961  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800e1968  mov     [rsp+4E0h+var_468], r14d
0x1800e196d  mov     [rsp+4E0h+var_470], eax
0x1800e1971  jz      loc_1800E1CF5
0x1800e1977  mov     rdx, 4000000000000800h; unsigned __int64
0x1800e1981  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800e1988  jz      loc_1800E1CF5
0x1800e198e  mov     rax, cs:qword_180169748
0x1800e1995  and     rax, rdx
0x1800e1998  cmp     cs:qword_180169748, rax
0x1800e199f  jnz     loc_1800E1CF5
0x1800e19a5  lea     rcx, [rbp+3E0h+var_2D0]; unsigned __int16 *
0x1800e19ac  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800e19b1  lea     rax, [rbp+3E0h+var_2D0]
0x1800e19b8  inc     rbx
0x1800e19bb  cmp     [rax+rbx*2], r14w
0x1800e19c0  jnz     short loc_1800E19B8
0x1800e19c2  lea     rax, [rbp+3E0h+var_2D0]
0x1800e19c9  jmp     loc_1800E18A1
0x1800e19ce  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800e19d5  jz      loc_1800E1A75
0x1800e19db  mov     rdx, 4000000000000100h
0x1800e19e5  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800e19ec  jz      loc_1800E1A75
0x1800e19f2  mov     rax, cs:qword_180169748
0x1800e19f9  and     rax, rdx
0x1800e19fc  cmp     cs:qword_180169748, rax
0x1800e1a03  jnz     short loc_1800E1A75
0x1800e1a05  mov     rax, [rsi+48h]
0x1800e1a09  mov     r8, [rax+28h]
0x1800e1a0d  mov     r9, [rax+18h]
0x1800e1a11  test    r8, r8
0x1800e1a14  jz      short loc_1800E1A2C
0x1800e1a16  mov     rax, rbx
0x1800e1a19  inc     rax
0x1800e1a1c  cmp     [r8+rax*2], r14w
0x1800e1a21  jnz     short loc_1800E1A19
0x1800e1a23  lea     edx, [rax+rax]
0x1800e1a26  add     rdx, 2
0x1800e1a2a  jmp     short loc_1800E1A2F
0x1800e1a2c  mov     rdx, r14
0x1800e1a2f  test    r9, r9
0x1800e1a32  jz      short loc_1800E1A4A
0x1800e1a34  mov     rax, rbx
0x1800e1a37  inc     rax
0x1800e1a3a  cmp     [r9+rax*2], r14w
0x1800e1a3f  jnz     short loc_1800E1A37
0x1800e1a41  lea     ecx, [rax+rax]
0x1800e1a44  add     rcx, 2
0x1800e1a48  jmp     short loc_1800E1A4D
0x1800e1a4a  mov     rcx, r14
0x1800e1a4d  mov     [rsp+4E0h+var_4B0], rdx
0x1800e1a52  lea     rdx, PLA_EVENT_DC_OPEN
0x1800e1a59  mov     [rsp+4E0h+var_4B8], r8
0x1800e1a5e  mov     r8d, 2
0x1800e1a64  mov     [rsp+4E0h+var_4C0], rcx
0x1800e1a69  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800e1a70  call    EventingWriteEvent
0x1800e1a75  mov     r15d, 1
0x1800e1a7b  cmp     bx, [rbp+3E0h+var_460]
0x1800e1a7f  jnz     loc_1800E1B40
0x1800e1a85  lea     r14d, [r15+9]
0x1800e1a89  test    r14d, r14d
0x1800e1a8c  js      loc_1800E1BCB
0x1800e1a92  mov     rcx, [rsi+130h]
0x1800e1a99  mov     edx, ebx
0x1800e1a9b  mov     rax, [rcx]
0x1800e1a9e  mov     rax, [rax+1F0h]
0x1800e1aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1aaa  mov     edi, eax
0x1800e1aac  test    eax, eax
0x1800e1aae  jns     loc_1800E1BCB
0x1800e1ab4  test    r14d, r14d
0x1800e1ab7  jz      short loc_1800E1AD0
0x1800e1ab9  cmp     eax, 803000AAh
0x1800e1abe  jnz     short loc_1800E1AD0
0x1800e1ac0  mov     ecx, 0C8h; dwMilliseconds
0x1800e1ac5  call    cs:__imp_Sleep
0x1800e1acb  sub     r14d, r15d
0x1800e1ace  jmp     short loc_1800E1A89
0x1800e1ad0  xor     r14d, r14d
0x1800e1ad3  mov     [rsp+4E0h+var_470], eax
0x1800e1ad7  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800e1ade  mov     [rsp+4E0h+var_468], r14d
0x1800e1ae3  jz      loc_1800E1CF5
0x1800e1ae9  mov     rdx, 4000000000000800h; unsigned __int64
0x1800e1af3  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800e1afa  jz      loc_1800E1CF5
0x1800e1b00  mov     rax, cs:qword_180169748
0x1800e1b07  and     rax, rdx
0x1800e1b0a  cmp     cs:qword_180169748, rax
0x1800e1b11  jnz     loc_1800E1CF5
0x1800e1b17  lea     rcx, [rbp+3E0h+var_250]; unsigned __int16 *
0x1800e1b1e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800e1b23  lea     rax, [rbp+3E0h+var_250]
0x1800e1b2a  inc     rbx
0x1800e1b2d  cmp     [rax+rbx*2], r14w
0x1800e1b32  jnz     short loc_1800E1B2A
0x1800e1b34  lea     rax, [rbp+3E0h+var_250]
0x1800e1b3b  jmp     loc_1800E18A7
0x1800e1b40  mov     rcx, [rsi+130h]
0x1800e1b47  mov     edx, ebx
0x1800e1b49  mov     rax, [rcx]
0x1800e1b4c  mov     rax, [rax+1F0h]
0x1800e1b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1b58  mov     edi, eax
0x1800e1b5a  test    eax, eax
0x1800e1b5c  jns     short loc_1800E1BCE
0x1800e1b5e  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800e1b65  mov     [rsp+4E0h+var_468], r14d
0x1800e1b6a  mov     [rsp+4E0h+var_470], eax
0x1800e1b6e  jz      loc_1800E1CF5
0x1800e1b74  mov     rdx, 4000000000000800h; unsigned __int64
0x1800e1b7e  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800e1b85  jz      loc_1800E1CF5
0x1800e1b8b  mov     rax, cs:qword_180169748
0x1800e1b92  and     rax, rdx
0x1800e1b95  cmp     cs:qword_180169748, rax
0x1800e1b9c  jnz     loc_1800E1CF5
0x1800e1ba2  lea     rcx, [rbp+3E0h+var_1D0]; unsigned __int16 *
0x1800e1ba9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800e1bae  lea     rax, [rbp+3E0h+var_1D0]
0x1800e1bb5  inc     rbx
0x1800e1bb8  cmp     [rax+rbx*2], r14w
0x1800e1bbd  jnz     short loc_1800E1BB5
0x1800e1bbf  lea     rax, [rbp+3E0h+var_1D0]
0x1800e1bc6  jmp     loc_1800E18A7
0x1800e1bcb  xor     r14d, r14d
0x1800e1bce  mov     rcx, [rsi+128h]
0x1800e1bd5  mov     rdx, [rsi+48h]
0x1800e1bd9  add     rdx, 48h ; 'H'
0x1800e1bdd  mov     rax, [rcx]
0x1800e1be0  mov     rax, [rax+1F8h]
0x1800e1be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1bec  mov     edi, eax
0x1800e1bee  test    eax, eax
0x1800e1bf0  jns     short loc_1800E1C5F
0x1800e1bf2  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800e1bf9  mov     [rsp+4E0h+var_468], r14d
0x1800e1bfe  mov     [rsp+4E0h+var_470], eax
0x1800e1c02  jz      loc_1800E1CF5
0x1800e1c08  mov     rdx, 4000000000000800h; unsigned __int64
0x1800e1c12  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800e1c19  jz      loc_1800E1CF5
0x1800e1c1f  mov     rax, cs:qword_180169748
0x1800e1c26  and     rax, rdx
0x1800e1c29  cmp     cs:qword_180169748, rax
0x1800e1c30  jnz     loc_1800E1CF5
0x1800e1c36  lea     rcx, [rbp+3E0h+var_150]; unsigned __int16 *
0x1800e1c3d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800e1c42  lea     rax, [rbp+3E0h+var_150]
0x1800e1c49  inc     rbx
0x1800e1c4c  cmp     [rax+rbx*2], r14w
0x1800e1c51  jnz     short loc_1800E1C49
0x1800e1c53  lea     rax, [rbp+3E0h+var_150]
  ... truncated ...
```
