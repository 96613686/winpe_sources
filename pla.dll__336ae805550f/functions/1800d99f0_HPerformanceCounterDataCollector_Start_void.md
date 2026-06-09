# HPerformanceCounterDataCollector::Start(void)

- ea: `0x1800d99f0`
- end: `0x1800d9dd4`
- name: `?Start@HPerformanceCounterDataCollector@@UEAAJXZ`
- size: `996`
- prototype: `__int64 __fastcall(HPerformanceCounterDataCollector *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x1800bb5f0`
- `0x1800d99f0`
- `0x180135668`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d9dad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800d9dad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d9a26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d9a26`
- `pdh!PdhOpenLogW` at `0x1800d9c06`
- `pdh!PdhOpenLogW` at `0x1800d9c06`

## pseudocode

```c
__int64 __fastcall HPerformanceCounterDataCollector::Start(HPerformanceCounterDataCollector *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // r15
  int v3; // eax
  unsigned int v4; // esi
  __int64 v5; // rbx
  int *v6; // r9
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // r10
  void *v14; // r9
  DWORD v15; // edx
  PDH_STATUS v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  DWORD dwMaxSize; // [rsp+20h] [rbp-E0h]
  const WCHAR *szUserCaption; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v25[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v26[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v27[64]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v28[64]; // [rsp+200h] [rbp+100h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 144);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  v3 = HDataCollector::Start(this);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v7 = -1;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000100LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000100LL) )
    {
      v8 = *((_QWORD *)this + 9);
      v9 = *(_QWORD *)(v8 + 40);
      v10 = *(_QWORD *)(v8 + 24);
      if ( v9 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)(v9 + 2 * v11) );
      }
      if ( v10 )
      {
        v12 = -1;
        do
          ++v12;
        while ( *(_WORD *)(v10 + 2 * v12) );
      }
      EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_DC_OPEN, 2, v10);
    }
    v13 = *((_QWORD *)this + 9);
    v14 = (void *)*((_QWORD *)this + 29);
    v15 = *((_DWORD *)this + 65);
    szUserCaption = (const WCHAR *)*((_QWORD *)this + 11);
    dwMaxSize = *((_DWORD *)this + 29) << 20;
    *((_DWORD *)this + 66) = 0;
    v16 = PdhOpenLogW(
            *(LPCWSTR *)(v13 + 40),
            v15,
            (LPDWORD)this + 64,
            v14,
            dwMaxSize,
            szUserCaption,
            (PDH_HLOG *)this + 30);
    v17 = PlaiHResultFromWin32(v16);
    v4 = v17;
    if ( v17 >= 0 )
    {
      v18 = (*(__int64 (__fastcall **)(HPerformanceCounterDataCollector *))(*(_QWORD *)this + 40LL))(this);
      v4 = v18;
      if ( v18 >= 0 )
      {
        v19 = (*(__int64 (__fastcall **)(HPerformanceCounterDataCollector *))(*(_QWORD *)this + 56LL))(this);
        v4 = v19;
        if ( v19 >= 0 )
        {
          if ( !*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 9) + 56LL) + 80LL) && !*((_DWORD *)this + 52) )
            HDataCollector::CompleteDataCollector(this);
          goto LABEL_43;
        }
        v24 = 0;
        v23 = v19;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_43;
        }
        PlaiWhoAmI(v28, 0x4000000000000800uLL);
        do
          ++v7;
        while ( v28[v7] );
      }
      else
      {
        v24 = 0;
        v23 = v18;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_43;
        }
        PlaiWhoAmI(v27, 0x4000000000000800uLL);
        do
          ++v7;
        while ( v27[v7] );
      }
    }
    else
    {
      v24 = 0;
      v23 = v17;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_43;
      }
      PlaiWhoAmI(v26, 0x4000000000000800uLL);
      do
        ++v7;
      while ( v26[v7] );
    }
    v6 = &v23;
LABEL_8:
    EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)v6);
    goto LABEL_43;
  }
  v23 = 0;
  v24 = v3;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v25, 0x4000000000000800uLL);
    v5 = -1;
    do
      ++v5;
    while ( v25[v5] );
    v6 = &v24;
    goto LABEL_8;
  }
LABEL_43:
  LeaveCriticalSection(v1);
  return v4;
}

```

## disassembly

```asm
0x1800d99f0  push    rbp
0x1800d99f2  push    rbx
0x1800d99f3  push    rsi
0x1800d99f4  push    rdi
0x1800d99f5  push    r12
0x1800d99f7  push    r15
0x1800d99f9  lea     rbp, [rsp-198h]
0x1800d9a01  sub     rsp, 298h
0x1800d9a08  mov     rax, cs:__security_cookie
0x1800d9a0f  xor     rax, rsp
0x1800d9a12  mov     [rbp+1C0h+var_40], rax
0x1800d9a19  lea     r15, [rcx+90h]
0x1800d9a20  mov     rdi, rcx
0x1800d9a23  mov     rcx, r15; lpCriticalSection
0x1800d9a26  call    cs:__imp_EnterCriticalSection
0x1800d9a2c  mov     rcx, rdi; this
0x1800d9a2f  call    ?Start@HDataCollector@@UEAAJXZ; HDataCollector::Start(void)
0x1800d9a34  xor     r12d, r12d
0x1800d9a37  mov     esi, eax
0x1800d9a39  test    eax, eax
0x1800d9a3b  jns     loc_1800D9B19
0x1800d9a41  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800d9a48  mov     [rsp+2C0h+var_250], r12d
0x1800d9a4d  mov     [rsp+2C0h+var_248], eax
0x1800d9a51  jz      loc_1800D9DAA
0x1800d9a57  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d9a61  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d9a68  jz      loc_1800D9DAA
0x1800d9a6e  mov     rax, cs:qword_180169748
0x1800d9a75  and     rax, rdx
0x1800d9a78  cmp     cs:qword_180169748, rax
0x1800d9a7f  jnz     loc_1800D9DAA
0x1800d9a85  lea     rcx, [rbp+1C0h+var_240]; unsigned __int16 *
0x1800d9a89  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d9a8e  lea     rax, [rbp+1C0h+var_240]
0x1800d9a92  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800d9a96  inc     rbx
0x1800d9a99  cmp     [rax+rbx*2], r12w
0x1800d9a9e  jnz     short loc_1800D9A96
0x1800d9aa0  lea     ecx, [rbx+rbx]
0x1800d9aa3  add     rcx, 2
0x1800d9aa7  lea     rax, [rbp+1C0h+var_240]
0x1800d9aab  mov     [rsp+2C0h+var_260], rcx
0x1800d9ab0  lea     r9, [rsp+2C0h+var_248]
0x1800d9ab5  lea     rcx, [rsp+2C0h+var_250]
0x1800d9aba  mov     [rsp+2C0h+var_268], rax
0x1800d9abf  lea     rdx, PLA_EVENT_ERROR
0x1800d9ac6  mov     [rsp+2C0h+var_270], 28h ; '('
0x1800d9acf  lea     rax, aHperformanceco_4; "HPerformanceCounterDataCollector::Start"
0x1800d9ad6  mov     [rsp+2C0h+var_278], rax
0x1800d9adb  mov     eax, 4
0x1800d9ae0  mov     [rsp+2C0h+var_280], rax
0x1800d9ae5  mov     [rsp+2C0h+var_288], rcx
0x1800d9aea  lea     rcx, byte_180147320
0x1800d9af1  mov     [rsp+2C0h+phLog], 1
0x1800d9afa  mov     [rsp+2C0h+szUserCaption], rcx
0x1800d9aff  lea     r8d, [rax+1]
0x1800d9b03  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800d9b0a  mov     qword ptr [rsp+2C0h+dwMaxSize], rax
0x1800d9b0f  call    EventingWriteEvent
0x1800d9b14  jmp     loc_1800D9DAA
0x1800d9b19  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800d9b1d  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800d9b24  jz      loc_1800D9BC4
0x1800d9b2a  mov     rdx, 4000000000000100h
0x1800d9b34  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d9b3b  jz      loc_1800D9BC4
0x1800d9b41  mov     rax, cs:qword_180169748
0x1800d9b48  and     rax, rdx
0x1800d9b4b  cmp     cs:qword_180169748, rax
0x1800d9b52  jnz     short loc_1800D9BC4
0x1800d9b54  mov     rax, [rdi+48h]
0x1800d9b58  mov     r8, [rax+28h]
0x1800d9b5c  mov     r9, [rax+18h]
0x1800d9b60  test    r8, r8
0x1800d9b63  jz      short loc_1800D9B7B
0x1800d9b65  mov     rax, rbx
0x1800d9b68  inc     rax
0x1800d9b6b  cmp     [r8+rax*2], r12w
0x1800d9b70  jnz     short loc_1800D9B68
0x1800d9b72  lea     edx, [rax+rax]
0x1800d9b75  add     rdx, 2
0x1800d9b79  jmp     short loc_1800D9B7E
0x1800d9b7b  mov     rdx, r12
0x1800d9b7e  test    r9, r9
0x1800d9b81  jz      short loc_1800D9B99
0x1800d9b83  mov     rax, rbx
0x1800d9b86  inc     rax
0x1800d9b89  cmp     [r9+rax*2], r12w
0x1800d9b8e  jnz     short loc_1800D9B86
0x1800d9b90  lea     ecx, [rax+rax]
0x1800d9b93  add     rcx, 2
0x1800d9b97  jmp     short loc_1800D9B9C
0x1800d9b99  mov     rcx, r12
0x1800d9b9c  mov     [rsp+2C0h+phLog], rdx
0x1800d9ba1  lea     rdx, PLA_EVENT_DC_OPEN
0x1800d9ba8  mov     [rsp+2C0h+szUserCaption], r8
0x1800d9bad  mov     r8d, 2
0x1800d9bb3  mov     qword ptr [rsp+2C0h+dwMaxSize], rcx
0x1800d9bb8  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800d9bbf  call    EventingWriteEvent
0x1800d9bc4  mov     ecx, [rdi+74h]
0x1800d9bc7  lea     rax, [rdi+0F0h]
0x1800d9bce  mov     r10, [rdi+48h]
0x1800d9bd2  lea     r8, [rdi+100h]; lpdwLogType
0x1800d9bd9  mov     r9, [rdi+0E8h]; hQuery
0x1800d9be0  mov     edx, [rdi+104h]; dwAccessFlags
0x1800d9be6  mov     [rsp+2C0h+phLog], rax; phLog
0x1800d9beb  mov     rax, [rdi+58h]
0x1800d9bef  shl     ecx, 14h
0x1800d9bf2  mov     [rsp+2C0h+szUserCaption], rax; szUserCaption
0x1800d9bf7  mov     [rsp+2C0h+dwMaxSize], ecx; dwMaxSize
0x1800d9bfb  mov     [rdi+108h], r12d
0x1800d9c02  mov     rcx, [r10+28h]; szLogFileName
0x1800d9c06  call    cs:__imp_PdhOpenLogW
0x1800d9c0c  mov     ecx, eax; unsigned int
0x1800d9c0e  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800d9c13  mov     esi, eax
0x1800d9c15  test    eax, eax
0x1800d9c17  jns     short loc_1800D9C93
0x1800d9c19  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800d9c20  mov     [rsp+2C0h+var_248], r12d
0x1800d9c25  mov     [rsp+2C0h+var_250], eax
0x1800d9c29  jz      loc_1800D9DAA
0x1800d9c2f  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d9c39  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d9c40  jz      loc_1800D9DAA
0x1800d9c46  mov     rax, cs:qword_180169748
0x1800d9c4d  and     rax, rdx
0x1800d9c50  cmp     cs:qword_180169748, rax
0x1800d9c57  jnz     loc_1800D9DAA
0x1800d9c5d  lea     rcx, [rbp+1C0h+var_1C0]; unsigned __int16 *
0x1800d9c61  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d9c66  lea     rax, [rbp+1C0h+var_1C0]
0x1800d9c6a  inc     rbx
0x1800d9c6d  cmp     [rax+rbx*2], r12w
0x1800d9c72  jnz     short loc_1800D9C6A
0x1800d9c74  lea     rax, [rbp+1C0h+var_1C0]
0x1800d9c78  lea     ecx, [rbx+rbx]
0x1800d9c7b  add     rcx, 2
0x1800d9c7f  lea     r9, [rsp+2C0h+var_250]
0x1800d9c84  mov     [rsp+2C0h+var_260], rcx
0x1800d9c89  lea     rcx, [rsp+2C0h+var_248]
0x1800d9c8e  jmp     loc_1800D9ABA
0x1800d9c93  mov     rax, [rdi]
0x1800d9c96  mov     rcx, rdi
0x1800d9c99  mov     rax, [rax+28h]
0x1800d9c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9ca2  mov     esi, eax
0x1800d9ca4  test    eax, eax
0x1800d9ca6  jns     short loc_1800D9D15
0x1800d9ca8  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800d9caf  mov     [rsp+2C0h+var_248], r12d
0x1800d9cb4  mov     [rsp+2C0h+var_250], eax
0x1800d9cb8  jz      loc_1800D9DAA
0x1800d9cbe  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d9cc8  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d9ccf  jz      loc_1800D9DAA
0x1800d9cd5  mov     rax, cs:qword_180169748
0x1800d9cdc  and     rax, rdx
0x1800d9cdf  cmp     cs:qword_180169748, rax
0x1800d9ce6  jnz     loc_1800D9DAA
0x1800d9cec  lea     rcx, [rbp+1C0h+var_140]; unsigned __int16 *
0x1800d9cf3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d9cf8  lea     rax, [rbp+1C0h+var_140]
0x1800d9cff  inc     rbx
0x1800d9d02  cmp     [rax+rbx*2], r12w
0x1800d9d07  jnz     short loc_1800D9CFF
0x1800d9d09  lea     rax, [rbp+1C0h+var_140]
0x1800d9d10  jmp     loc_1800D9C78
0x1800d9d15  mov     rax, [rdi]
0x1800d9d18  mov     rcx, rdi
0x1800d9d1b  mov     rax, [rax+38h]
0x1800d9d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9d24  mov     esi, eax
0x1800d9d26  test    eax, eax
0x1800d9d28  jns     short loc_1800D9D8B
0x1800d9d2a  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800d9d31  mov     [rsp+2C0h+var_248], r12d
0x1800d9d36  mov     [rsp+2C0h+var_250], eax
0x1800d9d3a  jz      short loc_1800D9DAA
0x1800d9d3c  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d9d46  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d9d4d  jz      short loc_1800D9DAA
0x1800d9d4f  mov     rax, cs:qword_180169748
0x1800d9d56  and     rax, rdx
0x1800d9d59  cmp     cs:qword_180169748, rax
0x1800d9d60  jnz     short loc_1800D9DAA
0x1800d9d62  lea     rcx, [rbp+1C0h+var_C0]; unsigned __int16 *
0x1800d9d69  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d9d6e  lea     rax, [rbp+1C0h+var_C0]
0x1800d9d75  inc     rbx
0x1800d9d78  cmp     [rax+rbx*2], r12w
0x1800d9d7d  jnz     short loc_1800D9D75
0x1800d9d7f  lea     rax, [rbp+1C0h+var_C0]
0x1800d9d86  jmp     loc_1800D9C78
0x1800d9d8b  mov     rax, [rdi+48h]
0x1800d9d8f  mov     rdx, [rax+38h]
0x1800d9d93  cmp     [rdx+50h], r12d
0x1800d9d97  jnz     short loc_1800D9DAA
0x1800d9d99  cmp     [rdi+0D0h], r12d
0x1800d9da0  jnz     short loc_1800D9DAA
0x1800d9da2  mov     rcx, rdi; this
0x1800d9da5  call    ?CompleteDataCollector@HDataCollector@@QEAAXXZ; HDataCollector::CompleteDataCollector(void)
0x1800d9daa  mov     rcx, r15; lpCriticalSection
0x1800d9dad  call    cs:__imp_LeaveCriticalSection
0x1800d9db3  mov     eax, esi
0x1800d9db5  mov     rcx, [rbp+1C0h+var_40]
0x1800d9dbc  xor     rcx, rsp; StackCookie
0x1800d9dbf  call    __security_check_cookie
0x1800d9dc4  add     rsp, 298h
0x1800d9dcb  pop     r15
0x1800d9dcd  pop     r12
0x1800d9dcf  pop     rdi
0x1800d9dd0  pop     rsi
0x1800d9dd1  pop     rbx
0x1800d9dd2  pop     rbp
0x1800d9dd3  retn
```
