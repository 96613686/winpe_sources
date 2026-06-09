# CSpacePoolContext::CSpacePoolContext(_SCRUB_ENVIRONMENT const *,ulong,ulong)

- ea: `0x180012fc0`
- end: `0x180013235`
- name: `??0CSpacePoolContext@@QEAA@PEBU_SCRUB_ENVIRONMENT@@KK@Z`
- size: `629`
- prototype: `CSpacePoolContext *__fastcall(CSpacePoolContext *this, const struct _SCRUB_ENVIRONMENT *, int, DWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180014ee8`

## callees

- `0x1800032f8`
- `0x180003640`
- `0x180006688`
- `0x1800068b4`
- `0x180012fc0`

## import_xrefs

- `KERNEL32!SetThreadpoolThreadMaximum` at `0x180013195`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x180013195`
- `KERNEL32!CreateThreadpool` at `0x180013179`
- `KERNEL32!CreateThreadpool` at `0x180013179`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x1800130fc`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x1800130fc`
- `KERNEL32!GetLastError` at `0x18001310b`
- `KERNEL32!GetLastError` at `0x1800131d0`
- `KERNEL32!GetLastError` at `0x18001310b`
- `KERNEL32!GetLastError` at `0x1800131d0`

## string_xrefs

- `0x180013150`: `Hr = BOOL_HR( m_TpCleanupGroup.AttachEx( CreateThreadpoolCleanupGroup() ) )`
- `0x180013216`: `Hr = BOOL_HR( m_TpPool.AttachEx( CreateThreadpool( nullptr ) ) )`

## pseudocode

```c
CSpacePoolContext *__fastcall CSpacePoolContext::CSpacePoolContext(
        CSpacePoolContext *this,
        const struct _SCRUB_ENVIRONMENT *a2,
        int a3,
        DWORD a4)
{
  __int64 v6; // rdx
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  signed int LastError; // eax
  signed int v9; // ebx
  struct _TP_POOL *Threadpool; // rax
  signed int v12; // eax
  signed int v13; // ebx
  const char *v14; // [rsp+40h] [rbp-28h] BYREF
  signed int v15; // [rsp+48h] [rbp-20h]

  *(_DWORD *)this = 3;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_DWORD *)this + 15) = 1;
  *((_DWORD *)this + 16) = 72;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_BYTE *)this + 84) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_BYTE *)this + 100) = 0;
  *((_DWORD *)this + 26) = a3;
  *((_DWORD *)this + 27) = a4;
  *((_OWORD *)this + 7) = *(_OWORD *)a2;
  *((_OWORD *)this + 8) = *((_OWORD *)a2 + 1);
  *((_OWORD *)this + 9) = *((_OWORD *)a2 + 2);
  *((_OWORD *)this + 10) = *((_OWORD *)a2 + 3);
  *((_OWORD *)this + 11) = *((_OWORD *)a2 + 4);
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v6 + 16) = "CSpacePoolContext::CSpacePoolContext";
  v14 = "CSpacePoolContext::CSpacePoolContext";
  ++*(_WORD *)(v6 + 8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CSpacePoolContext::CSpacePoolContext");
  }
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)this + 9) = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 >= 0 )
      v9 = -2147467259;
    v15 = v9;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        (unsigned int)&WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids,
        (unsigned int)"Hr = BOOL_HR( m_TpCleanupGroup.AttachEx( CreateThreadpoolCleanupGroup() ) )",
        v9);
    }
    ATL::AtlThrowImpl(v9);
  }
  *((_QWORD *)this + 2) = ThreadpoolCleanupGroup;
  *((_QWORD *)this + 3) = 0;
  Threadpool = CreateThreadpool(0);
  *((_QWORD *)this + 11) = Threadpool;
  if ( !Threadpool )
  {
    v12 = GetLastError();
    v13 = v12;
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
    if ( v13 >= 0 )
      v13 = -2147467259;
    v15 = v13;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        76,
        (unsigned int)&WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids,
        (unsigned int)"Hr = BOOL_HR( m_TpPool.AttachEx( CreateThreadpool( nullptr ) ) )",
        v13);
    }
    ATL::AtlThrowImpl(v13);
  }
  v15 = 0;
  if ( a4 )
    SetThreadpoolThreadMaximum(Threadpool, a4);
  *((_DWORD *)this + 14) |= 1u;
  *((_QWORD *)this + 1) = *((_QWORD *)this + 11);
  *((_QWORD *)this + 23) = this;
  CHResultImp::~CHResultImp((CHResultImp *)&v14);
  return this;
}

```

## disassembly

```asm
0x180012fc0  mov     r11, rsp
0x180012fc3  mov     [r11+10h], rbx
0x180012fc7  mov     [r11+18h], rbp
0x180012fcb  mov     [r11+8], rcx
0x180012fcf  push    rsi
0x180012fd0  push    rdi
0x180012fd1  push    r14
0x180012fd3  sub     rsp, 50h
0x180012fd7  mov     edi, r9d
0x180012fda  mov     rbx, rcx
0x180012fdd  mov     dword ptr [rcx], 3
0x180012fe3  xor     esi, esi
0x180012fe5  mov     [rcx+8], rsi
0x180012fe9  mov     [rcx+10h], rsi
0x180012fed  mov     [rcx+18h], rsi
0x180012ff1  mov     [rcx+20h], rsi
0x180012ff5  mov     [rcx+28h], rsi
0x180012ff9  mov     [rcx+30h], rsi
0x180012ffd  mov     [rcx+38h], esi
0x180013000  lea     ebp, [rsi+1]
0x180013003  mov     [rcx+3Ch], ebp
0x180013006  mov     dword ptr [rcx+40h], 48h ; 'H'
0x18001300d  mov     [rcx+48h], rsi
0x180013011  mov     [rcx+50h], esi
0x180013014  mov     [rcx+54h], sil
0x180013018  mov     [rcx+58h], rsi
0x18001301c  mov     [rcx+60h], esi
0x18001301f  mov     [rcx+64h], sil
0x180013023  mov     [rcx+68h], r8d
0x180013027  mov     [rcx+6Ch], r9d
0x18001302b  movups  xmm0, xmmword ptr [rdx]
0x18001302e  movups  xmmword ptr [rcx+70h], xmm0
0x180013032  movups  xmm1, xmmword ptr [rdx+10h]
0x180013036  movups  xmmword ptr [rcx+80h], xmm1
0x18001303d  movups  xmm0, xmmword ptr [rdx+20h]
0x180013041  movups  xmmword ptr [rcx+90h], xmm0
0x180013048  movups  xmm1, xmmword ptr [rdx+30h]
0x18001304c  movups  xmmword ptr [rcx+0A0h], xmm1
0x180013053  movups  xmm0, xmmword ptr [rdx+40h]
0x180013057  movups  xmmword ptr [rcx+0B0h], xmm0
0x18001305e  mov     ecx, cs:_tls_index
0x180013064  mov     rax, gs:58h
0x18001306d  mov     rdx, [rax+rcx*8]
0x180013071  mov     eax, 10h
0x180013076  lea     r9, aCspacepoolcont; "CSpacePoolContext::CSpacePoolContext"
0x18001307d  mov     [rax+rdx], r9
0x180013081  mov     [r11-28h], r9
0x180013085  mov     r8d, 8
0x18001308b  add     [r8+rdx], bp
0x180013090  movzx   r8d, word ptr [r8+rdx]
0x180013095  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18001309c  movzx   eax, cx
0x18001309f  cmp     r8w, cx
0x1800130a3  cmovb   ax, r8w
0x1800130a8  mov     [rsp+68h+var_38], ax
0x1800130ad  cmovb   cx, r8w
0x1800130b2  mov     [rsp+68h+var_36], cx
0x1800130b7  xor     eax, eax
0x1800130b9  mov     [rsp+68h+var_34], eax
0x1800130bd  mov     rax, cs:off_180047060; "                                       "...
0x1800130c4  mov     [r11-30h], rax
0x1800130c8  lea     r14, WPP_GLOBAL_Control
0x1800130cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130d6  cmp     rcx, r14
0x1800130d9  jz      short loc_1800130FC
0x1800130db  test    [rcx+1Ch], bpl
0x1800130df  jz      short loc_1800130FC
0x1800130e1  cmp     byte ptr [rcx+19h], 5
0x1800130e5  jb      short loc_1800130FC
0x1800130e7  lea     edx, [rsi+0Dh]
0x1800130ea  mov     [r11-48h], r9
0x1800130ee  lea     r9, [r11-38h]
0x1800130f2  mov     rcx, [rcx+10h]; LoggerHandle
0x1800130f6  call    WPP_SF_aZs
0x1800130fb  nop
0x1800130fc  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180013102  mov     [rbx+48h], rax
0x180013106  test    rax, rax
0x180013109  jnz     short loc_18001316F
0x18001310b  call    cs:__imp_GetLastError
0x180013111  mov     ebx, eax
0x180013113  test    eax, eax
0x180013115  jle     short loc_180013120
0x180013117  movzx   ebx, ax
0x18001311a  or      ebx, 80070000h
0x180013120  test    ebx, ebx
0x180013122  js      short loc_180013129
0x180013124  mov     ebx, 80004005h
0x180013129  mov     eax, ebx
0x18001312b  mov     [rsp+68h+var_20], ebx
0x18001312f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013136  cmp     rcx, r14
0x180013139  jz      short loc_180013167
0x18001313b  test    [rcx+1Ch], bpl
0x18001313f  jz      short loc_180013167
0x180013141  cmp     byte ptr [rcx+19h], 2
0x180013145  jb      short loc_180013167
0x180013147  mov     edx, 4Bh ; 'K'
0x18001314c  mov     [rsp+68h+var_48], ebx
0x180013150  lea     r9, aHrBoolHrMTpcle; "Hr = BOOL_HR( m_TpCleanupGroup.AttachEx"...
0x180013157  lea     r8, WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids
0x18001315e  mov     rcx, [rcx+10h]
0x180013162  call    WPP_SF_sd
0x180013167  mov     ecx, ebx; int
0x180013169  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001316f  mov     [rbx+10h], rax
0x180013173  mov     [rbx+18h], rsi
0x180013177  xor     ecx, ecx; reserved
0x180013179  call    cs:__imp_CreateThreadpool
0x18001317f  mov     [rbx+58h], rax
0x180013183  test    rax, rax
0x180013186  jz      short loc_1800131D0
0x180013188  mov     [rsp+68h+var_20], esi
0x18001318c  test    edi, edi
0x18001318e  jz      short loc_18001319B
0x180013190  mov     edx, edi; cthrdMost
0x180013192  mov     rcx, rax; ptpp
0x180013195  call    cs:__imp_SetThreadpoolThreadMaximum
0x18001319b  or      [rbx+38h], ebp
0x18001319e  mov     rax, [rbx+58h]
0x1800131a2  mov     [rbx+8], rax
0x1800131a6  mov     [rbx+0B8h], rbx
0x1800131ad  lea     rcx, [rsp+68h+var_28]; this
0x1800131b2  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1800131b7  nop
0x1800131b8  mov     rax, rbx
0x1800131bb  lea     r11, [rsp+68h+var_18]
0x1800131c0  mov     rbx, [r11+28h]
0x1800131c4  mov     rbp, [r11+30h]
0x1800131c8  mov     rsp, r11
0x1800131cb  pop     r14
0x1800131cd  pop     rdi
0x1800131ce  pop     rsi
0x1800131cf  retn
0x1800131d0  call    cs:__imp_GetLastError
0x1800131d6  nop
0x1800131d7  mov     ebx, eax
0x1800131d9  test    eax, eax
0x1800131db  jle     short loc_1800131E6
0x1800131dd  movzx   ebx, ax
0x1800131e0  or      ebx, 80070000h
0x1800131e6  test    ebx, ebx
0x1800131e8  js      short loc_1800131EF
0x1800131ea  mov     ebx, 80004005h
0x1800131ef  mov     eax, ebx
0x1800131f1  mov     [rsp+68h+var_20], ebx
0x1800131f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131fc  cmp     rcx, r14
0x1800131ff  jz      short loc_18001322D
0x180013201  test    [rcx+1Ch], bpl
0x180013205  jz      short loc_18001322D
0x180013207  cmp     byte ptr [rcx+19h], 2
0x18001320b  jb      short loc_18001322D
0x18001320d  mov     edx, 4Ch ; 'L'
0x180013212  mov     [rsp+68h+var_48], ebx
0x180013216  lea     r9, aHrBoolHrMTppoo; "Hr = BOOL_HR( m_TpPool.AttachEx( Create"...
0x18001321d  lea     r8, WPP_926703ea09ae31764064aa4fcd6b3f92_Traceguids
0x180013224  mov     rcx, [rcx+10h]
0x180013228  call    WPP_SF_sd
0x18001322d  mov     ecx, ebx; int
0x18001322f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
