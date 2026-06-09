# CSchedule::AddAtJobCommon(_AT_INFO const &,CJob * *,ushort * const,unsigned __int64,ushort * const)

- ea: `0x18000e7f8`
- end: `0x18000eeed`
- name: `?AddAtJobCommon@CSchedule@@AEAAJAEBU_AT_INFO@@PEAPEAVCJob@@QEAG_K2@Z`
- size: `1781`
- prototype: `__int64 __usercall@<rax>(CSchedule *__hidden this@<rcx>, const struct _AT_INFO *@<rdx>, struct CJob **@<r8>, unsigned __int16 *const@<r9>, unsigned __int64, unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e750`

## callees

- `0x180001840`
- `0x180004190`
- `0x180006f90`
- `0x18000865c`
- `0x18000d41c`
- `0x18000d780`
- `0x18000e578`
- `0x18000e7f8`
- `0x18000eef4`
- `0x18000f18c`
- `0x18000f3ac`
- `0x18000f3d0`
- `0x18000f510`
- `0x180019440`
- `0x180019554`
- `0x18001aac0`
- `0x18001b010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18000e8a0`
- `msvcrt!_itow_s` at `0x18000ee6a`
- `msvcrt!_itow_s` at `0x18000e8a0`
- `msvcrt!_itow_s` at `0x18000ee6a`
- `msvcrt!wcspbrk` at `0x18000e933`
- `msvcrt!wcspbrk` at `0x18000e933`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000ea0b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000ea0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000ea50`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000ea50`

## pseudocode

```c
__int64 __fastcall CSchedule::AddAtJobCommon(
        CSchedule *this,
        const struct _AT_INFO *a2,
        struct CJob **a3,
        unsigned __int16 *const a4,
        unsigned __int64 a5,
        unsigned __int16 *const Buffer)
{
  unsigned __int16 *v6; // r12
  CSchedule *v8; // r13
  CJob *v9; // rbx
  wchar_t *p_String; // r14
  unsigned __int64 i; // rdi
  __int16 v13; // ax
  int v14; // r14d
  int v15; // edi
  HINSTANCE v16; // rcx
  DWORD_PTR JobTime; // r8
  DWORD DaysOfMonth; // edi
  __int64 v19; // rdx
  DWORD_PTR v20; // r8
  bool v21; // zf
  char v22; // al
  CSchedule *v23; // rcx
  int v24; // r15d
  __int16 v25; // ax
  __int16 v26; // ax
  struct _SYSTEMTIME v27; // xmm6
  WORD v28; // si
  WORD v29; // r15
  unsigned __int16 v30; // di
  WORD v31; // r12
  int v32; // eax
  unsigned int v33; // [rsp+48h] [rbp-C0h] BYREF
  __int16 v34; // [rsp+50h] [rbp-B8h] BYREF
  __int16 v35; // [rsp+52h] [rbp-B6h]
  WORD wYear; // [rsp+54h] [rbp-B4h]
  WORD wMonth; // [rsp+56h] [rbp-B2h]
  WORD wDay; // [rsp+58h] [rbp-B0h]
  int v39; // [rsp+5Ah] [rbp-AEh]
  WORD v40; // [rsp+5Eh] [rbp-AAh]
  int v41; // [rsp+60h] [rbp-A8h]
  __int64 v42; // [rsp+64h] [rbp-A4h]
  int v43; // [rsp+6Ch] [rbp-9Ch]
  __int64 v44; // [rsp+70h] [rbp-98h]
  int v45; // [rsp+78h] [rbp-90h]
  int v46; // [rsp+7Ch] [rbp-8Ch]
  struct _SYSTEMTIME v47; // [rsp+88h] [rbp-80h] BYREF
  struct _SYSTEMTIME v48; // [rsp+98h] [rbp-70h] BYREF
  struct _SYSTEMTIME v49; // [rsp+A8h] [rbp-60h] BYREF
  struct _SYSTEMTIME v50; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int16 *v51; // [rsp+C8h] [rbp-40h]
  CSchedule *v52; // [rsp+D0h] [rbp-38h]
  wchar_t *v53; // [rsp+D8h] [rbp-30h]
  struct CJob **v54; // [rsp+E0h] [rbp-28h]
  struct _SYSTEMTIME v55; // [rsp+E8h] [rbp-20h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+F8h] [rbp-10h] BYREF
  wchar_t String; // [rsp+108h] [rbp+0h] BYREF
  __int16 v58; // [rsp+10Ah] [rbp+2h] BYREF
  char v59; // [rsp+10Ch] [rbp+4h] BYREF
  WCHAR v60[88]; // [rsp+318h] [rbp+210h] BYREF

  v6 = a4;
  v51 = a4;
  v54 = a3;
  v8 = this;
  v52 = this;
  v53 = Buffer;
  if ( *((_DWORD *)this + 12) > 1u && (unsigned int)CSchedule::_AtTaskExists(this) == 1 )
    CSchedule::ResetAtID(v8);
  StringCchCopyW(v6, 0x105u, *((const unsigned __int16 **)v8 + 8));
  StringCchCatW(v6, 0x105u, L"\\At");
  _itow_s(*((_DWORD *)v8 + 12), Buffer, 0x10u, 10);
  StringCchCatW(v6, 0x105u, Buffer);
  StringCchCatW(v6, 0x105u, L".job");
  v9 = CJob::Create();
  if ( !v9 )
    return 2147942414LL;
  StringCchCopyW(&String, 0x104u, a2->Command);
  if ( String == 34 )
  {
    p_String = (wchar_t *)&v58;
    if ( !v58 )
    {
      i = 0;
      goto LABEL_21;
    }
    for ( i = (unsigned __int64)&v59; *(_WORD *)i; i += 2LL )
    {
      if ( *(_WORD *)i == 34 )
        goto LABEL_15;
    }
    i = 0;
  }
  else
  {
    p_String = &String;
    i = (unsigned __int64)wcspbrk(&String, L" \t");
  }
LABEL_15:
  if ( i )
  {
    *(_WORD *)i = 0;
    do
    {
      i += 2LL;
      v13 = *(_WORD *)i;
    }
    while ( *(_WORD *)i && (v13 == 32 || v13 == 9) );
    i &= -(__int64)(*(_WORD *)i != 0);
  }
LABEL_21:
  v14 = (*(__int64 (__fastcall **)(CJob *, wchar_t *))(*(_QWORD *)v9 + 256LL))(v9, p_String);
  if ( v14 < 0 )
  {
    (*(void (__fastcall **)(CJob *))(*(_QWORD *)v9 + 16LL))(v9);
    return (unsigned int)v14;
  }
  if ( i )
  {
    v15 = (*(__int64 (__fastcall **)(CJob *, unsigned __int64))(*(_QWORD *)v9 + 272LL))(v9, i);
    if ( v15 < 0 )
      goto LABEL_25;
  }
  *((_DWORD *)v9 + 22) |= 0x200002u;
  if ( (a2->Flags & 0x10) == 0 )
    *((_DWORD *)v9 + 22) |= 1u;
  v16 = g_hInstance;
  *((_DWORD *)v9 + 21) = 267008;
  if ( LoadStringW(v16, 0x44Bu, v60, 80) > 0 )
    (*(void (__fastcall **)(CJob *, WCHAR *))(*(_QWORD *)v9 + 144LL))(v9, v60);
  SystemTime = 0;
  v55 = 0;
  v47 = 0;
  v49 = 0;
  v50 = 0;
  v48 = 0;
  GetLocalTime(&SystemTime);
  JobTime = a2->JobTime;
  DaysOfMonth = a2->DaysOfMonth;
  v19 = (a2->JobTime * (unsigned __int128)0x179EC9CBD821DC3BuLL) >> 64;
  v55 = SystemTime;
  *(_DWORD *)&v55.wSecond = 0;
  v33 = DaysOfMonth;
  v44 = 0;
  v20 = (v19 + ((JobTime - v19) >> 1)) >> 15;
  v45 = 0;
  v55.wHour = (unsigned int)v20 / 0x3C;
  v21 = (a2->Flags & 8) == 0;
  *(_DWORD *)&v55.wMinute = (unsigned int)v20 % 0x3C;
  if ( v21 )
  {
    if ( !DaysOfMonth && !a2->DaysOfWeek && !(unsigned int)IsFirstTimeEarlier(&SystemTime, &v55) )
      IncrementDay(&v55);
  }
  else
  {
    DaysOfMonth |= 1 << (LOBYTE(v55.wDay) - 1);
    v33 = DaysOfMonth;
  }
  v39 = 0;
  v34 = 48;
  v35 = *((_WORD *)v9 + 16);
  wYear = v55.wYear;
  wMonth = v55.wMonth;
  wDay = v55.wDay;
  v41 = *(_DWORD *)&v55.wHour;
  v22 = ~a2->Flags;
  v40 = 0;
  v23 = (CSchedule *)(v22 & 1);
  v46 = 0;
  v43 = v22 & 1;
  v42 = 0;
  if ( DaysOfMonth )
  {
    v21 = (a2->Flags & 1) == 0;
    HIWORD(v44) = HIWORD(v33);
    LOWORD(v45) = 4095;
    LODWORD(v44) = 3;
    WORD2(v44) = DaysOfMonth;
    if ( v21 )
    {
      CalcDomTriggerDates(DaysOfMonth, &SystemTime, &v55, &v47, &v49, &v50, &v48);
      wYear = v47.wYear;
      wMonth = v47.wMonth;
      wDay = v47.wDay;
      v39 = *(_DWORD *)&v49.wYear;
      v40 = v49.wDay;
    }
    v15 = CDynamicArray<_TASK_TRIGGER>::Add((char *)v9 + 24, &v34);
    if ( v15 < 0 )
      goto LABEL_25;
    v23 = (CSchedule *)v50.wDay;
    if ( v50.wDay )
    {
      wYear = v50.wYear;
      wMonth = v50.wMonth;
      v39 = *(_DWORD *)&v48.wYear;
      v40 = v48.wDay;
      v25 = *((_WORD *)v9 + 16);
      wDay = v50.wDay;
      v35 = v25;
      v15 = CDynamicArray<_TASK_TRIGGER>::Add((char *)v9 + 24, &v34);
      if ( v15 < 0 )
        goto LABEL_25;
    }
  }
  else if ( !a2->DaysOfWeek )
  {
    v43 = 0;
    v24 = CDynamicArray<_TASK_TRIGGER>::Add((char *)v9 + 24, &v34);
    if ( v24 < 0 )
    {
      (*(void (__fastcall **)(CJob *))(*(_QWORD *)v9 + 16LL))(v9);
      return (unsigned int)v24;
    }
  }
  if ( a2->DaysOfWeek )
  {
    v35 = *((_WORD *)v9 + 16);
    v26 = 2 * a2->DaysOfWeek;
    LODWORD(v44) = 2;
    WORD2(v44) = 1;
    HIWORD(v44) = v26;
    if ( (v26 & 0x80u) != 0 )
      HIWORD(v44) = v26 & 0xFF7E | 1;
    if ( (a2->Flags & 1) == 0 )
    {
      v27 = SystemTime;
      v48 = SystemTime;
      if ( (unsigned int)IsFirstTimeEarlier(&v55, &SystemTime) )
      {
        IncrementDay(&v48);
        v27 = v48;
      }
      v47 = v27;
      v28 = v27.wYear;
      LOWORD(v33) = 0;
      v29 = v27.wMonth;
      v30 = v27.wDay + 6;
      v31 = v27.wDay + 6;
      if ( (int)MonthDays(v27.wMonth, v27.wYear, (unsigned __int16 *)&v33) >= 0 && v30 > (unsigned __int16)v33 )
      {
        v47.wDay = v30 - v33;
        IncrementMonth(&v47);
        v31 = v47.wDay;
        v29 = v47.wMonth;
        v28 = v47.wYear;
      }
      wYear = v27.wYear;
      v8 = v52;
      HIWORD(v39) = v29;
      wMonth = _mm_extract_epi16((__m128i)v27, 1);
      v40 = v31;
      v6 = v51;
      LOWORD(v39) = v28;
      wDay = _mm_extract_epi16((__m128i)v27, 3);
    }
    v15 = CDynamicArray<_TASK_TRIGGER>::Add((char *)v9 + 24, &v34);
    if ( v15 < 0 )
      goto LABEL_25;
  }
  v33 = 0;
  if ( CSchedule::GetAtTaskMaxHours(v23, &v33) >= 0 )
    (*(void (__fastcall **)(CJob *, _QWORD))(*(_QWORD *)v9 + 336LL))(v9, v33);
  *((_DWORD *)v9 + 22) = *((_DWORD *)v9 + 22) & 0xFFFFFFF | 0xD0000000;
  v32 = CJob::SaveWithRetry(v9, v6, 1, 5u);
  v15 = v32;
  if ( v32 < 0 )
  {
    if ( v32 != -2147024816
      || (GetNextAtID((unsigned int *)v8 + 12),
          StringCchCopyW(v6, 0x105u, *((const unsigned __int16 **)v8 + 8)),
          StringCchCatW(v6, 0x105u, L"\\At"),
          _itow_s(*((_DWORD *)v8 + 12), v53, 0x10u, 10),
          StringCchCatW(v6, 0x105u, v53),
          StringCchCatW(v6, 0x105u, L".job"),
          v15 = CJob::SaveWithRetry(v9, v6, 1, 5u),
          v15 < 0) )
    {
LABEL_25:
      (*(void (__fastcall **)(CJob *))(*(_QWORD *)v9 + 16LL))(v9);
      return (unsigned int)v15;
    }
  }
  *v54 = v9;
  return 0;
}

```

## disassembly

```asm
0x18000e7f8  mov     rax, rsp
0x18000e7fb  push    rbp
0x18000e7fc  push    rbx
0x18000e7fd  push    rsi
0x18000e7fe  push    rdi
0x18000e7ff  push    r12
0x18000e801  push    r13
0x18000e803  push    r14
0x18000e805  push    r15
0x18000e807  lea     rbp, [rax-328h]
0x18000e80e  sub     rsp, 3E8h
0x18000e815  movaps  xmmword ptr [rax-58h], xmm6
0x18000e819  mov     rax, cs:__security_cookie
0x18000e820  xor     rax, rsp
0x18000e823  mov     [rbp+320h+var_60], rax
0x18000e82a  mov     rdi, [rbp+320h+Buffer]
0x18000e831  mov     r14d, 1
0x18000e837  mov     r12, r9
0x18000e83a  mov     [rbp+320h+var_360], r9
0x18000e83e  mov     rsi, rdx
0x18000e841  mov     [rbp+320h+var_348], r8
0x18000e845  mov     r13, rcx
0x18000e848  mov     [rbp+320h+var_358], rcx
0x18000e84c  mov     [rbp+320h+var_350], rdi
0x18000e850  cmp     [rcx+30h], r14d
0x18000e854  jbe     short loc_18000E868
0x18000e856  call    ?_AtTaskExists@CSchedule@@AEAAJXZ; CSchedule::_AtTaskExists(void)
0x18000e85b  cmp     eax, r14d
0x18000e85e  jnz     short loc_18000E868
0x18000e860  mov     rcx, r13; this
0x18000e863  call    ?ResetAtID@CSchedule@@QEAAJXZ; CSchedule::ResetAtID(void)
0x18000e868  mov     r8, [r13+40h]; unsigned __int16 *
0x18000e86c  mov     r14d, 105h
0x18000e872  mov     edx, r14d; unsigned __int64
0x18000e875  mov     rcx, r12; unsigned __int16 *
0x18000e878  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e87d  lea     r8, aAt; "\\At"
0x18000e884  mov     edx, r14d; unsigned __int64
0x18000e887  mov     rcx, r12; unsigned __int16 *
0x18000e88a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e88f  mov     ecx, [r13+30h]; Value
0x18000e893  mov     r9d, 0Ah; Radix
0x18000e899  mov     rdx, rdi; Buffer
0x18000e89c  lea     r8d, [r9+6]; BufferCount
0x18000e8a0  call    cs:__imp__itow_s
0x18000e8a6  mov     r8, rdi; unsigned __int16 *
0x18000e8a9  mov     edx, r14d; unsigned __int64
0x18000e8ac  mov     rcx, r12; unsigned __int16 *
0x18000e8af  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e8b4  lea     r8, aJob; ".job"
0x18000e8bb  mov     edx, r14d; unsigned __int64
0x18000e8be  mov     rcx, r12; unsigned __int16 *
0x18000e8c1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e8c6  call    ?Create@CJob@@SAPEAV1@XZ; CJob::Create(void)
0x18000e8cb  xor     r15d, r15d
0x18000e8ce  mov     rbx, rax
0x18000e8d1  test    rax, rax
0x18000e8d4  jnz     short loc_18000E8E0
0x18000e8d6  mov     eax, 8007000Eh
0x18000e8db  jmp     loc_18000EEB6
0x18000e8e0  mov     r8, [rsi+10h]; unsigned __int16 *
0x18000e8e4  lea     rcx, [rbp+320h+String]; unsigned __int16 *
0x18000e8e8  mov     edx, 104h; unsigned __int64
0x18000e8ed  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e8f2  cmp     [rbp+320h+String], 22h ; '"'
0x18000e8f7  jnz     short loc_18000E924
0x18000e8f9  lea     r14, [rbp+320h+var_31E]
0x18000e8fd  cmp     [rbp+320h+var_31E], r15w
0x18000e902  jnz     short loc_18000E909
0x18000e904  mov     rdi, r15
0x18000e907  jmp     short loc_18000E96B
0x18000e909  lea     rdi, [rbp+320h+var_31C]
0x18000e90d  cmp     [rdi], r15w
0x18000e911  jz      short loc_18000E91F
0x18000e913  cmp     word ptr [rdi], 22h ; '"'
0x18000e917  jz      short loc_18000E93C
0x18000e919  add     rdi, 2
0x18000e91d  jmp     short loc_18000E90D
0x18000e91f  mov     rdi, r15
0x18000e922  jmp     short loc_18000E93C
0x18000e924  lea     rdx, Control; " \t"
0x18000e92b  lea     rcx, [rbp+320h+String]; String
0x18000e92f  lea     r14, [rbp+320h+String]
0x18000e933  call    cs:__imp_wcspbrk
0x18000e939  mov     rdi, rax
0x18000e93c  test    rdi, rdi
0x18000e93f  jz      short loc_18000E96B
0x18000e941  mov     [rdi], r15w
0x18000e945  jmp     short loc_18000E953
0x18000e947  cmp     ax, 20h ; ' '
0x18000e94b  jz      short loc_18000E953
0x18000e94d  cmp     ax, 9
0x18000e951  jnz     short loc_18000E95F
0x18000e953  add     rdi, 2
0x18000e957  movzx   eax, word ptr [rdi]
0x18000e95a  test    ax, ax
0x18000e95d  jnz     short loc_18000E947
0x18000e95f  movzx   eax, word ptr [rdi]
0x18000e962  neg     ax
0x18000e965  sbb     rcx, rcx
0x18000e968  and     rdi, rcx
0x18000e96b  mov     rax, [rbx]
0x18000e96e  mov     rdx, r14
0x18000e971  mov     rcx, rbx
0x18000e974  mov     rax, [rax+100h]
0x18000e97b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e980  mov     r14d, eax
0x18000e983  test    eax, eax
0x18000e985  jns     short loc_18000E99E
0x18000e987  mov     rcx, [rbx]
0x18000e98a  mov     rax, [rcx+10h]
0x18000e98e  mov     rcx, rbx
0x18000e991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e996  mov     eax, r14d
0x18000e999  jmp     loc_18000EEB6
0x18000e99e  test    rdi, rdi
0x18000e9a1  jz      short loc_18000E9D4
0x18000e9a3  mov     rax, [rbx]
0x18000e9a6  mov     rdx, rdi
0x18000e9a9  mov     rcx, rbx
0x18000e9ac  mov     rax, [rax+110h]
0x18000e9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9b8  mov     edi, eax
0x18000e9ba  test    eax, eax
0x18000e9bc  jns     short loc_18000E9D4
0x18000e9be  mov     rcx, [rbx]
0x18000e9c1  mov     rax, [rcx+10h]
0x18000e9c5  mov     rcx, rbx
0x18000e9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9cd  mov     eax, edi
0x18000e9cf  jmp     loc_18000EEB6
0x18000e9d4  or      dword ptr [rbx+58h], 200002h
0x18000e9db  mov     r14d, 1
0x18000e9e1  test    byte ptr [rsi+0Dh], 10h
0x18000e9e5  jnz     short loc_18000E9EB
0x18000e9e7  or      [rbx+58h], r14d
0x18000e9eb  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000e9f2  lea     r8, [rbp+320h+var_110]; lpBuffer
0x18000e9f9  mov     r9d, 50h ; 'P'; cchBufferMax
0x18000e9ff  mov     dword ptr [rbx+54h], 41300h
0x18000ea06  mov     edx, 44Bh; uID
0x18000ea0b  call    cs:__imp_LoadStringW
0x18000ea11  test    eax, eax
0x18000ea13  jle     short loc_18000EA2E
0x18000ea15  mov     rax, [rbx]
0x18000ea18  lea     rdx, [rbp+320h+var_110]
0x18000ea1f  mov     rcx, rbx
0x18000ea22  mov     rax, [rax+90h]
0x18000ea29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea2e  xorps   xmm0, xmm0
0x18000ea31  lea     rcx, [rbp+320h+SystemTime]; lpSystemTime
0x18000ea35  xorps   xmm1, xmm1
0x18000ea38  movups  xmmword ptr [rbp+320h+SystemTime.wYear], xmm0
0x18000ea3c  movups  xmmword ptr [rbp+320h+var_340.wYear], xmm1
0x18000ea40  movups  xmmword ptr [rbp+320h+var_3A0.wYear], xmm0
0x18000ea44  movups  xmmword ptr [rbp+320h+var_380.wYear], xmm1
0x18000ea48  movups  xmmword ptr [rbp+320h+var_370.wYear], xmm0
0x18000ea4c  movups  xmmword ptr [rbp+320h+var_390.wYear], xmm1
0x18000ea50  call    cs:__imp_GetLocalTime
0x18000ea56  mov     r8, [rsi]
0x18000ea59  mov     rax, 179EC9CBD821DC3Bh
0x18000ea63  movaps  xmm0, xmmword ptr [rbp+320h+SystemTime.wYear]
0x18000ea67  mov     edi, [rsi+8]
0x18000ea6a  mul     r8
0x18000ea6d  movdqa  xmmword ptr [rbp+320h+var_340.wYear], xmm0
0x18000ea72  mov     eax, 88888889h
0x18000ea77  mov     dword ptr [rbp+320h+var_340.wSecond], r15d
0x18000ea7b  sub     r8, rdx
0x18000ea7e  mov     [rsp+420h+var_3E0], edi
0x18000ea82  shr     r8, 1
0x18000ea85  add     r8, rdx
0x18000ea88  mov     qword ptr [rsp+420h+var_3B8], r15
0x18000ea8d  shr     r8, 0Fh
0x18000ea91  mul     r8d
0x18000ea94  mov     [rsp+420h+var_3B0], r15d
0x18000ea99  shr     edx, 5
0x18000ea9c  movzx   eax, dx
0x18000ea9f  imul    ecx, eax, 3Ch ; '<'
0x18000eaa2  mov     [rbp+320h+var_340.wHour], dx
0x18000eaa6  sub     r8w, cx
0x18000eaaa  test    byte ptr [rsi+0Dh], 8
0x18000eaae  mov     [rbp+320h+var_340.wMinute], r8w
0x18000eab3  jz      short loc_18000EACF
0x18000eab5  mov     rcx, qword ptr [rbp+320h+var_340.wYear]
0x18000eab9  mov     eax, r14d
0x18000eabc  shr     rcx, 30h
0x18000eac0  sub     ecx, r14d
0x18000eac3  shl     eax, cl
0x18000eac5  or      eax, edi
0x18000eac7  mov     edi, eax
0x18000eac9  mov     [rsp+420h+var_3E0], eax
0x18000eacd  jmp     short loc_18000EAF3
0x18000eacf  test    edi, edi
0x18000ead1  jnz     short loc_18000EAF3
0x18000ead3  cmp     [rsi+0Ch], r15b
0x18000ead7  jnz     short loc_18000EAF3
0x18000ead9  lea     rdx, [rbp+320h+var_340]; struct _SYSTEMTIME *
0x18000eadd  lea     rcx, [rbp+320h+SystemTime]; struct _SYSTEMTIME *
0x18000eae1  call    ?IsFirstTimeEarlier@@YAHPEBU_SYSTEMTIME@@0@Z; IsFirstTimeEarlier(_SYSTEMTIME const *,_SYSTEMTIME const *)
0x18000eae6  test    eax, eax
0x18000eae8  jnz     short loc_18000EAF3
0x18000eaea  lea     rcx, [rbp+320h+var_340]; struct _SYSTEMTIME *
0x18000eaee  call    ?IncrementDay@@YAXPEAU_SYSTEMTIME@@@Z; IncrementDay(_SYSTEMTIME *)
0x18000eaf3  mov     eax, 30h ; '0'
0x18000eaf8  mov     dword ptr [rsp+420h+var_3CE], r15d
0x18000eafd  mov     [rsp+420h+var_3D8], ax
0x18000eb02  lea     r14, [rbx+18h]
0x18000eb06  movzx   eax, word ptr [r14+8]
0x18000eb0b  mov     word ptr [rsp+420h+var_3D6], ax
0x18000eb10  movzx   eax, [rbp+320h+var_340.wYear]
0x18000eb14  mov     word ptr [rsp+420h+var_3D6+2], ax
0x18000eb19  movzx   eax, [rbp+320h+var_340.wMonth]
0x18000eb1d  mov     [rsp+420h+var_3D2], ax
0x18000eb22  movzx   eax, [rbp+320h+var_340.wDay]
0x18000eb26  mov     [rsp+420h+var_3D0], ax
0x18000eb2b  movzx   eax, [rbp+320h+var_340.wHour]
0x18000eb2f  mov     word ptr [rsp+420h+var_3CC+4], ax
0x18000eb34  movzx   eax, [rbp+320h+var_340.wMinute]
0x18000eb38  mov     word ptr [rsp+420h+var_3CC+6], ax
0x18000eb3d  mov     al, [rsi+0Dh]
0x18000eb40  not     al
0x18000eb42  mov     word ptr [rsp+420h+var_3CC+2], r15w
0x18000eb48  movzx   ecx, al
0x18000eb4b  and     ecx, 1
0x18000eb4e  mov     [rsp+420h+var_3AC], r15d
0x18000eb53  mov     dword ptr [rsp+420h+var_3C0+4], ecx
0x18000eb57  mov     qword ptr [rsp+420h+var_3C4], r15
0x18000eb5c  test    edi, edi
0x18000eb5e  jnz     short loc_18000EBA1
0x18000eb60  cmp     [rsi+0Ch], r15b
0x18000eb64  jnz     short loc_18000EB99
0x18000eb66  lea     rdx, [rsp+420h+var_3D8]
0x18000eb6b  mov     dword ptr [rsp+420h+var_3C0+4], r15d
0x18000eb70  mov     rcx, r14
0x18000eb73  call    ?Add@?$CDynamicArray@U_TASK_TRIGGER@@@@QEAAJAEBU_TASK_TRIGGER@@@Z; CDynamicArray<_TASK_TRIGGER>::Add(_TASK_TRIGGER const &)
0x18000eb78  mov     r15d, eax
0x18000eb7b  test    eax, eax
0x18000eb7d  jns     short loc_18000EB96
0x18000eb7f  mov     rcx, [rbx]
0x18000eb82  mov     rax, [rcx+10h]
0x18000eb86  mov     rcx, rbx
0x18000eb89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb8e  mov     eax, r15d
0x18000eb91  jmp     loc_18000EEB6
0x18000eb96  xor     r15d, r15d
0x18000eb99  test    edi, edi
0x18000eb9b  jz      loc_18000EC9E
0x18000eba1  test    byte ptr [rsi+0Dh], 1
0x18000eba5  movzx   eax, word ptr [rsp+420h+var_3E0+2]
0x18000ebaa  mov     word ptr [rsp+420h+var_3B4+2], ax
0x18000ebaf  mov     eax, 0FFFh
0x18000ebb4  mov     word ptr [rsp+420h+var_3B0], ax
0x18000ebb9  mov     [rsp+420h+var_3B8], 3
0x18000ebc1  mov     word ptr [rsp+420h+var_3B4], di
0x18000ebc6  jnz     short loc_18000EC2C
0x18000ebc8  lea     rax, [rbp+320h+var_390]
0x18000ebcc  mov     ecx, edi; unsigned int
0x18000ebce  mov     [rsp+30h], rax; struct _SYSTEMTIME *
0x18000ebd3  lea     r9, [rbp+320h+var_3A0]; struct _SYSTEMTIME *
0x18000ebd7  lea     rax, [rbp+320h+var_370]
0x18000ebdb  mov     [rsp+420h+var_3F8], rax; struct _SYSTEMTIME *
0x18000ebe0  lea     r8, [rbp+320h+var_340]; struct _SYSTEMTIME *
0x18000ebe4  lea     rax, [rbp+320h+var_380]
0x18000ebe8  lea     rdx, [rbp+320h+SystemTime]; struct _SYSTEMTIME *
0x18000ebec  mov     [rsp+420h+var_400], rax; struct _SYSTEMTIME *
0x18000ebf1  call    ?CalcDomTriggerDates@@YAXKAEBU_SYSTEMTIME@@0PEAU1@111@Z; CalcDomTriggerDates(ulong,_SYSTEMTIME const &,_SYSTEMTIME const &,_SYSTEMTIME *,_SYSTEMTIME *,_SYSTEMTIME *,_SYSTEMTIME *)
0x18000ebf6  movzx   eax, [rbp+320h+var_3A0.wYear]
0x18000ebfa  mov     word ptr [rsp+420h+var_3D6+2], ax
0x18000ebff  movzx   eax, [rbp+320h+var_3A0.wMonth]
0x18000ec03  mov     [rsp+420h+var_3D2], ax
0x18000ec08  movzx   eax, [rbp+320h+var_3A0.wDay]
0x18000ec0c  mov     [rsp+420h+var_3D0], ax
0x18000ec11  movzx   eax, [rbp+320h+var_380.wYear]
0x18000ec15  mov     [rsp+420h+var_3CE], ax
0x18000ec1a  movzx   eax, [rbp+320h+var_380.wMonth]
0x18000ec1e  mov     word ptr [rsp+420h+var_3CC], ax
0x18000ec23  movzx   eax, [rbp+320h+var_380.wDay]
0x18000ec27  mov     word ptr [rsp+420h+var_3CC+2], ax
0x18000ec2c  lea     rdx, [rsp+420h+var_3D8]
0x18000ec31  mov     rcx, r14
0x18000ec34  call    ?Add@?$CDynamicArray@U_TASK_TRIGGER@@@@QEAAJAEBU_TASK_TRIGGER@@@Z; CDynamicArray<_TASK_TRIGGER>::Add(_TASK_TRIGGER const &)
0x18000ec39  mov     edi, eax
0x18000ec3b  test    eax, eax
0x18000ec3d  js      loc_18000E9BE
0x18000ec43  movzx   ecx, [rbp+320h+var_370.wDay]
0x18000ec47  test    cx, cx
0x18000ec4a  jz      short loc_18000EC9E
0x18000ec4c  movzx   eax, [rbp+320h+var_370.wYear]
0x18000ec50  lea     rdx, [rsp+420h+var_3D8]
0x18000ec55  mov     word ptr [rsp+420h+var_3D6+2], ax
0x18000ec5a  movzx   eax, [rbp+320h+var_370.wMonth]
0x18000ec5e  mov     [rsp+420h+var_3D2], ax
0x18000ec63  movzx   eax, [rbp+320h+var_390.wYear]
0x18000ec67  mov     [rsp+420h+var_3CE], ax
0x18000ec6c  movzx   eax, [rbp+320h+var_390.wMonth]
0x18000ec70  mov     word ptr [rsp+420h+var_3CC], ax
0x18000ec75  movzx   eax, [rbp+320h+var_390.wDay]
0x18000ec79  mov     word ptr [rsp+420h+var_3CC+2], ax
0x18000ec7e  movzx   eax, word ptr [rbx+20h]
0x18000ec82  mov     [rsp+420h+var_3D0], cx
  ... truncated ...
```
