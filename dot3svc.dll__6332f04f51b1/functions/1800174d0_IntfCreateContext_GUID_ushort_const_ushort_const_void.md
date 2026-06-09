# IntfCreateContext(_GUID *,ushort const *,ushort const *,void * *)

- ea: `0x1800174d0`
- end: `0x1800177ad`
- name: `?IntfCreateContext@@YAKPEAU_GUID@@PEBG1PEAPEAX@Z`
- size: `733`
- prototype: `__int64 __fastcall(struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000f4a0`

## callees

- `0x180002a10`
- `0x180003114`
- `0x180008c38`
- `0x18000a7ec`
- `0x18000a87c`
- `0x18000a9c0`
- `0x18000aa58`
- `0x18000c230`
- `0x180016be4`
- `0x1800174d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800175fe`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800175fe`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800176c8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800176c8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017713`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017713`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017659`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017659`
- `MobileNetworking!HtNewHandle` at `0x1800176f2`
- `MobileNetworking!HtNewHandle` at `0x1800176f2`

## pseudocode

```c
__int64 __fastcall IntfCreateContext(
        struct _GUID *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void **a4)
{
  struct _LIST_ENTRY *v8; // rcx
  __int64 v9; // rdx
  DWORD LastError; // ebx
  char *v11; // rax
  char *v12; // rdi
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rbx
  __int64 v16; // rcx
  unsigned __int16 *v17; // rax
  char v18; // bp
  unsigned int v19; // edx
  struct _RTL_CRITICAL_SECTION *v20; // rsi
  void *v21; // rcx

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 31, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v8 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || !BYTE1(v8[1].Blink) || (BYTE4(v8[1].Blink) & 1) == 0 )
      goto LABEL_11;
    v9 = 32;
LABEL_10:
    WPP_SF_(v8[1].Flink, v9, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids);
    v8 = WPP_GLOBAL_Control;
LABEL_11:
    LastError = 87;
    goto LABEL_50;
  }
  if ( !a4 )
  {
    if ( v8 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || !BYTE1(v8[1].Blink) || (BYTE4(v8[1].Blink) & 1) == 0 )
      goto LABEL_11;
    v9 = 33;
    goto LABEL_10;
  }
  if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v8[1].Blink) >= 4u && (BYTE4(v8[1].Blink) & 1) != 0 )
    WPP_SF_S(v8[1].Flink, 34, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, a3);
  v11 = (char *)operator new(0x1E8u, (const struct std::nothrow_t *)std::nothrow);
  v12 = v11;
  if ( v11 )
  {
    memset_0(v11, 0, 0x1D8u);
    *((_QWORD *)v12 + 59) = 0;
    *((_QWORD *)v12 + 60) = 0;
    *(struct _GUID *)(v12 + 8) = *a1;
    _o_wcscpy_s(v12 + 24, 46, a2);
    v15 = -1;
    v16 = -1;
    do
      ++v16;
    while ( a3[v16] );
    v17 = (unsigned __int16 *)Dot3Alloc(2 * v16 + 2, v13, v14);
    *((_QWORD *)v12 + 15) = v17;
    if ( v17 )
    {
      do
        ++v15;
      while ( a3[v15] );
      if ( StringCchCopyW(v17, v15 + 1, a3) < 0 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control[1].Blink)
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 37, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids);
        }
        LastError = 13;
        goto LABEL_41;
      }
      v20 = (struct _RTL_CRITICAL_SECTION *)(v12 + 128);
      InitializeCriticalSection((LPCRITICAL_SECTION)(v12 + 128));
      v18 = 1;
      LastError = HtNewHandle(g_hHandleTable, v12, 1448036676, IntfDestroyContext, 1, v12);
      *a4 = *(void **)v12;
      *((_QWORD *)v12 + 37) = 0;
    }
    else
    {
      v18 = 0;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 36, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids);
      }
      LastError = GetLastError();
      v20 = (struct _RTL_CRITICAL_SECTION *)(v12 + 128);
    }
    if ( !LastError )
    {
LABEL_44:
      v8 = WPP_GLOBAL_Control;
      goto LABEL_50;
    }
    if ( v18 )
      DeleteCriticalSection(v20);
LABEL_41:
    v21 = (void *)*((_QWORD *)v12 + 15);
    if ( v21 )
      Dot3Free(v21);
    _LAN_INTERFACE_CONTEXT::`scalar deleting destructor'((_LAN_INTERFACE_CONTEXT *)v12, v19);
    goto LABEL_44;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink)
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 35, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  LastError = 14;
LABEL_50:
  if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v8[1].Blink) >= 4u && (BYTE4(v8[1].Blink) & 1) != 0 )
    WPP_SF_d(v8[1].Flink, 38, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x1800174d0  push    rbx
0x1800174d2  push    rbp
0x1800174d3  push    rsi
0x1800174d4  push    rdi
0x1800174d5  push    r12
0x1800174d7  push    r13
0x1800174d9  push    r14
0x1800174db  push    r15
0x1800174dd  sub     rsp, 38h
0x1800174e1  mov     r14, r9
0x1800174e4  mov     rsi, r8
0x1800174e7  mov     rbp, rdx
0x1800174ea  mov     rbx, rcx
0x1800174ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800174f4  lea     r13, WPP_GLOBAL_Control
0x1800174fb  mov     r15d, 1
0x180017501  cmp     rcx, r13
0x180017504  jz      short loc_18001752D
0x180017506  cmp     byte ptr [rcx+19h], 4
0x18001750a  jb      short loc_18001752D
0x18001750c  test    [rcx+1Ch], r15b
0x180017510  jz      short loc_18001752D
0x180017512  mov     rcx, [rcx+10h]
0x180017516  lea     edx, [r15+1Eh]
0x18001751a  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x180017521  call    WPP_SF_
0x180017526  mov     rcx, cs:WPP_GLOBAL_Control
0x18001752d  xor     r12d, r12d
0x180017530  test    rbx, rbx
0x180017533  jnz     short loc_18001756A
0x180017535  cmp     rcx, r13
0x180017538  jz      short loc_180017560
0x18001753a  cmp     [rcx+19h], r15b
0x18001753e  jb      short loc_180017560
0x180017540  test    [rcx+1Ch], r15b
0x180017544  jz      short loc_180017560
0x180017546  lea     edx, [rbx+20h]
0x180017549  mov     rcx, [rcx+10h]
0x18001754d  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x180017554  call    WPP_SF_
0x180017559  mov     rcx, cs:WPP_GLOBAL_Control
0x180017560  mov     ebx, 57h ; 'W'
0x180017565  jmp     loc_180017771
0x18001756a  test    r14, r14
0x18001756d  jnz     short loc_180017586
0x18001756f  cmp     rcx, r13
0x180017572  jz      short loc_180017560
0x180017574  cmp     [rcx+19h], r15b
0x180017578  jb      short loc_180017560
0x18001757a  test    [rcx+1Ch], r15b
0x18001757e  jz      short loc_180017560
0x180017580  lea     edx, [r14+21h]
0x180017584  jmp     short loc_180017549
0x180017586  cmp     rcx, r13
0x180017589  jz      short loc_1800175AF
0x18001758b  cmp     byte ptr [rcx+19h], 4
0x18001758f  jb      short loc_1800175AF
0x180017591  test    [rcx+1Ch], r15b
0x180017595  jz      short loc_1800175AF
0x180017597  mov     rcx, [rcx+10h]
0x18001759b  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x1800175a2  mov     edx, 22h ; '"'
0x1800175a7  mov     r9, rsi
0x1800175aa  call    WPP_SF_S
0x1800175af  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800175b6  mov     ecx, 1E8h; unsigned __int64
0x1800175bb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800175c0  mov     rdi, rax
0x1800175c3  test    rax, rax
0x1800175c6  jz      loc_180017738
0x1800175cc  xor     edx, edx; Val
0x1800175ce  mov     r8d, 1D8h; Size
0x1800175d4  mov     rcx, rax; void *
0x1800175d7  call    memset_0
0x1800175dc  mov     [rdi+1D8h], r12
0x1800175e3  lea     rcx, [rdi+18h]
0x1800175e7  mov     [rdi+1E0h], r12
0x1800175ee  mov     r8, rbp
0x1800175f1  movups  xmm0, xmmword ptr [rbx]
0x1800175f4  mov     edx, 2Eh ; '.'
0x1800175f9  movdqu  xmmword ptr [rdi+8], xmm0
0x1800175fe  call    cs:__imp__o_wcscpy_s
0x180017604  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180017608  mov     rcx, rbx
0x18001760b  inc     rcx
0x18001760e  cmp     [rsi+rcx*2], r12w
0x180017613  jnz     short loc_18001760B
0x180017615  lea     rcx, ds:2[rcx*2]; dwBytes
0x18001761d  call    ?Dot3Alloc@@YAPEAX_K@Z; Dot3Alloc(unsigned __int64)
0x180017622  mov     [rdi+78h], rax
0x180017626  test    rax, rax
0x180017629  jnz     short loc_18001766D
0x18001762b  mov     bpl, r12b
0x18001762e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017635  cmp     rcx, r13
0x180017638  jz      short loc_180017659
0x18001763a  cmp     [rcx+19h], r15b
0x18001763e  jb      short loc_180017659
0x180017640  test    [rcx+1Ch], r15b
0x180017644  jz      short loc_180017659
0x180017646  mov     rcx, [rcx+10h]
0x18001764a  lea     edx, [rax+24h]
0x18001764d  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x180017654  call    WPP_SF_
0x180017659  call    cs:__imp_GetLastError
0x18001765f  mov     ebx, eax
0x180017661  lea     rsi, [rdi+80h]
0x180017668  jmp     loc_180017707
0x18001766d  inc     rbx
0x180017670  cmp     [rsi+rbx*2], r12w
0x180017675  jnz     short loc_18001766D
0x180017677  lea     rdx, [rbx+1]; unsigned __int64
0x18001767b  mov     r8, rsi; unsigned __int16 *
0x18001767e  mov     rcx, rax; unsigned __int16 *
0x180017681  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017686  test    eax, eax
0x180017688  jns     short loc_1800176BE
0x18001768a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017691  cmp     rcx, r13
0x180017694  jz      short loc_1800176B7
0x180017696  cmp     [rcx+19h], r15b
0x18001769a  jb      short loc_1800176B7
0x18001769c  test    [rcx+1Ch], r15b
0x1800176a0  jz      short loc_1800176B7
0x1800176a2  mov     rcx, [rcx+10h]
0x1800176a6  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x1800176ad  mov     edx, 25h ; '%'
0x1800176b2  call    WPP_SF_
0x1800176b7  mov     ebx, 0Dh
0x1800176bc  jmp     short loc_180017719
0x1800176be  lea     rsi, [rdi+80h]
0x1800176c5  mov     rcx, rsi; lpCriticalSection
0x1800176c8  call    cs:__imp_InitializeCriticalSection
0x1800176ce  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x1800176d5  lea     r9, IntfDestroyContext
0x1800176dc  mov     r8d, 564F4944h
0x1800176e2  mov     [rsp+78h+var_50], rdi
0x1800176e7  mov     rdx, rdi
0x1800176ea  mov     [rsp+78h+var_58], r15d
0x1800176ef  mov     bpl, r15b
0x1800176f2  call    cs:__imp_HtNewHandle
0x1800176f8  mov     ebx, eax
0x1800176fa  mov     rax, [rdi]
0x1800176fd  mov     [r14], rax
0x180017700  mov     [rdi+128h], r12
0x180017707  test    ebx, ebx
0x180017709  jz      short loc_18001772F
0x18001770b  test    bpl, bpl
0x18001770e  jz      short loc_180017719
0x180017710  mov     rcx, rsi; lpCriticalSection
0x180017713  call    cs:__imp_DeleteCriticalSection
0x180017719  mov     rcx, [rdi+78h]; lpMem
0x18001771d  test    rcx, rcx
0x180017720  jz      short loc_180017727
0x180017722  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x180017727  mov     rcx, rdi; this
0x18001772a  call    ??_G_LAN_INTERFACE_CONTEXT@@QEAAPEAXI@Z; _LAN_INTERFACE_CONTEXT::`scalar deleting destructor'(uint)
0x18001772f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017736  jmp     short loc_180017771
0x180017738  mov     rcx, cs:WPP_GLOBAL_Control
0x18001773f  cmp     rcx, r13
0x180017742  jz      short loc_18001776C
0x180017744  cmp     [rcx+19h], r15b
0x180017748  jb      short loc_18001776C
0x18001774a  test    [rcx+1Ch], r15b
0x18001774e  jz      short loc_18001776C
0x180017750  mov     rcx, [rcx+10h]
0x180017754  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x18001775b  mov     edx, 23h ; '#'
0x180017760  call    WPP_SF_
0x180017765  mov     rcx, cs:WPP_GLOBAL_Control
0x18001776c  mov     ebx, 0Eh
0x180017771  cmp     rcx, r13
0x180017774  jz      short loc_18001779A
0x180017776  cmp     byte ptr [rcx+19h], 4
0x18001777a  jb      short loc_18001779A
0x18001777c  test    [rcx+1Ch], r15b
0x180017780  jz      short loc_18001779A
0x180017782  mov     rcx, [rcx+10h]
0x180017786  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x18001778d  mov     edx, 26h ; '&'
0x180017792  mov     r9d, ebx
0x180017795  call    WPP_SF_d
0x18001779a  mov     eax, ebx
0x18001779c  add     rsp, 38h
0x1800177a0  pop     r15
0x1800177a2  pop     r14
0x1800177a4  pop     r13
0x1800177a6  pop     r12
0x1800177a8  pop     rdi
0x1800177a9  pop     rsi
0x1800177aa  pop     rbp
0x1800177ab  pop     rbx
0x1800177ac  retn
```
