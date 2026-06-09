# AcquireEnrollmentCert(ulong,uint,long (*)(_DRM_STATUS_MSG,long,void *,void *),uint,ushort *,ushort *,void *)

- ea: `0x180033398`
- end: `0x180033899`
- name: `?AcquireEnrollmentCert@@YAJKIP6AJW4_DRM_STATUS_MSG@@JPEAX1@ZIPEAG31@Z`
- size: `1281`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, int (*)(enum _DRM_STATUS_MSG, int, void *, void *), unsigned int, unsigned __int16 *, unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x18001a680`

## callees

- `0x180001244`
- `0x180001284`
- `0x180004654`
- `0x180015438`
- `0x180019e28`
- `0x18001a1fc`
- `0x180033398`
- `0x1800385a0`
- `0x18005f010`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x180033774`
- `msvcrt!_beginthreadex` at `0x180033774`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180033511`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180033511`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003351c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003351c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800334e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003377f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800334e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003377f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800337d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003382d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800337d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003382d`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=3
__int64 __fastcall AcquireEnrollmentCert(
        unsigned int a1,
        int a2,
        int (*a3)(enum _DRM_STATUS_MSG, int, void *, void *),
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        void *a7)
{
  char v8; // r14
  void *v9; // r15
  __int64 v10; // rdx
  const unsigned __int16 *v11; // rax
  signed int ThreadTermEvent; // ebx
  unsigned __int64 v13; // r8
  signed __int64 v14; // rsi
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rax
  DRMOS *v17; // rcx
  void *v18; // rax
  HANDLE v19; // rax
  signed int LastError; // eax
  void **v21; // rax
  void **v22; // r14
  HANDLE *v23; // rsi
  __int64 v24; // rdx
  unsigned __int16 *v25; // rax
  unsigned __int64 v26; // r8
  signed __int64 v27; // rbx
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // rcx
  unsigned __int16 *v31; // rax
  __int64 v32; // rcx
  unsigned __int16 *v33; // rax
  unsigned __int64 v34; // rdx
  signed __int64 v35; // rbx
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // rax
  unsigned __int64 v38; // rcx
  unsigned __int16 *v39; // rax
  void *v40; // rax
  signed int v41; // eax
  unsigned int ThrdAddr[4]; // [rsp+30h] [rbp-68h] BYREF
  void *Block; // [rsp+40h] [rbp-58h]
  char *v45; // [rsp+48h] [rbp-50h]
  void **v46; // [rsp+50h] [rbp-48h]
  __int64 v47; // [rsp+58h] [rbp-40h]

  v47 = -2;
  v8 = a2;
  ThrdAddr[0] = 0;
  v9 = 0;
  Block = 0;
  if ( !a3 || !a5 || !a6 )
  {
    ThreadTermEvent = -2147024809;
    goto LABEL_57;
  }
  v10 = 0x7FFFFFFF;
  v11 = L"UDRMPublishingEnrollment";
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  ThreadTermEvent = v10 == 0 ? 0x80070057 : 0;
  v13 = (0x7FFFFFFF - v10) & -(__int64)(v10 != 0);
  if ( v10 )
  {
    v14 = v13 + 1;
    if ( v13 + 1 < v13 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(0x7FFFFFFF - v10);
    v15 = HIDWORD(v14);
    if ( v14 < 0 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v15);
    v16 = 2LL * (unsigned int)v14;
    v17 = (DRMOS *)(v15 << 33);
    if ( (unsigned __int64)v17 + v16 < v16 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v17);
    if ( !(DRMOS *)((char *)v17 + v16) )
      goto LABEL_15;
    v18 = operator new(saturated_mul(v14, 2u));
    Block = v18;
    if ( !v18 )
    {
      ThreadTermEvent = -2147024882;
      goto LABEL_57;
    }
    ThreadTermEvent = StringCchCopyW((unsigned __int16 *)v18, v14, L"UDRMPublishingEnrollment");
    if ( ThreadTermEvent >= 0 )
    {
LABEL_15:
      v19 = DRMOS::OpenEventA(v17, 1, (DRMOS *)Block, a4);
      v9 = v19;
      if ( !v19 )
      {
        LastError = GetLastError();
        ThreadTermEvent = LastError;
        if ( LastError > 0 )
          ThreadTermEvent = (unsigned __int16)LastError | 0x80070000;
        if ( ThreadTermEvent >= 0 )
          ThreadTermEvent = -2147467259;
        goto LABEL_57;
      }
      if ( (v8 & 4) != 0 )
      {
        SetEvent(v19);
        goto LABEL_57;
      }
      ResetEvent(v19);
      v21 = (void **)operator new(0x40u);
      v22 = v21;
      v46 = v21;
      if ( !v21 )
      {
        ThreadTermEvent = -2147024882;
        goto LABEL_57;
      }
      *v21 = 0;
      v21[1] = 0;
      *((_DWORD *)v21 + 4) = 0;
      v21[3] = 0;
      v21[4] = 0;
      v21[5] = 0;
      *((_DWORD *)v21 + 12) = 0;
      v21[7] = 0;
      v21[3] = a3;
      v21[4] = a7;
      *((_DWORD *)v21 + 4) = a1;
      v23 = v21 + 5;
      v45 = (char *)(v21 + 5);
      v21[5] = v9;
      v9 = 0;
      *((_DWORD *)v21 + 12) = a2;
      v24 = 0x7FFFFFFF;
      v25 = a5;
      v46 = v22;
      do
      {
        if ( !*v25 )
          break;
        ++v25;
        --v24;
      }
      while ( v24 );
      ThreadTermEvent = v24 == 0 ? 0x80070057 : 0;
      v26 = (0x7FFFFFFF - v24) & -(__int64)(v24 != 0);
      if ( !v24 )
        goto LABEL_52;
      v27 = v26 + 1;
      if ( v26 + 1 < v26 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(0x7FFFFFFF - v24);
      v28 = HIDWORD(v27);
      if ( v27 < 0 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v28);
      v29 = 2LL * (unsigned int)v27;
      v30 = v28 << 33;
      if ( v30 + v29 < v29 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v30);
      if ( v30 + v29 )
      {
        v31 = (unsigned __int16 *)operator new(saturated_mul(v27, 2u));
        *v22 = v31;
        if ( !v31 )
        {
          ThreadTermEvent = -2147024882;
LABEL_52:
          if ( *v23 )
            CloseHandle(*v23);
          operator delete(*v22);
          operator delete(v22[1]);
          operator delete(v22);
          goto LABEL_57;
        }
        ThreadTermEvent = StringCchCopyW(v31, v27, a5);
        if ( ThreadTermEvent < 0 )
          goto LABEL_52;
      }
      v32 = 0x7FFFFFFF;
      v33 = a6;
      do
      {
        if ( !*v33 )
          break;
        ++v33;
        --v32;
      }
      while ( v32 );
      ThreadTermEvent = v32 == 0 ? 0x80070057 : 0;
      v34 = (0x7FFFFFFF - v32) & ((unsigned __int128)-(__int128)(unsigned __int64)v32 >> 64);
      if ( !v32 )
        goto LABEL_52;
      v35 = v34 + 1;
      if ( v34 + 1 < v34 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v32);
      v36 = HIDWORD(v35);
      if ( v35 < 0 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v36);
      v37 = 2LL * (unsigned int)v35;
      v38 = v36 << 33;
      if ( v38 + v37 < v37 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v38);
      if ( v38 + v37 )
      {
        v39 = (unsigned __int16 *)operator new(saturated_mul(v35, 2u));
        v22[1] = v39;
        if ( !v39 )
        {
          ThreadTermEvent = -2147024882;
          goto LABEL_52;
        }
        ThreadTermEvent = StringCchCopyW(v39, v35, a6);
        if ( ThreadTermEvent < 0 )
          goto LABEL_52;
      }
      ThreadTermEvent = GetThreadTermEvent(a1, 1u, v22 + 7);
      if ( ThreadTermEvent >= 0 )
      {
        v40 = (void *)_beginthreadex(0, 0, EnrollmentProc, v22, 0, ThrdAddr);
        if ( v40 )
        {
          SetThreadInfo(a1, 1u, v40);
          goto LABEL_57;
        }
        v41 = GetLastError();
        ThreadTermEvent = v41;
        if ( v41 > 0 )
          ThreadTermEvent = (unsigned __int16)v41 | 0x80070000;
        if ( ThreadTermEvent >= 0 )
          ThreadTermEvent = -2147467259;
      }
      goto LABEL_52;
    }
  }
LABEL_57:
  operator delete(Block);
  if ( v9 )
    CloseHandle(v9);
  if ( ThreadTermEvent < 0 && a3 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, void *))a3)(5, (unsigned int)ThreadTermEvent, 0, a7);
  return (unsigned int)ThreadTermEvent;
}

```

## disassembly

```asm
0x180033398  mov     rax, rsp
0x18003339b  mov     [rax+20h], r9d
0x18003339f  mov     [rax+18h], r8
0x1800333a3  mov     [rax+10h], edx
0x1800333a6  mov     [rax+8], ecx
0x1800333a9  push    rbx
0x1800333aa  push    rsi
0x1800333ab  push    rdi
0x1800333ac  push    r12
0x1800333ae  push    r13
0x1800333b0  push    r14
0x1800333b2  push    r15
0x1800333b4  sub     rsp, 60h
0x1800333b8  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x1800333c0  mov     r12, r8
0x1800333c3  mov     r14d, edx
0x1800333c6  xor     edi, edi
0x1800333c8  mov     [rax-68h], edi
0x1800333cb  mov     r15d, edi
0x1800333ce  mov     [rsp+98h+Block], rdi
0x1800333d3  test    r8, r8
0x1800333d6  jz      loc_180033816
0x1800333dc  cmp     [rsp+98h+arg_20], rdi
0x1800333e4  jz      loc_180033816
0x1800333ea  cmp     [rsp+98h+arg_28], rdi
0x1800333f2  jz      loc_180033816
0x1800333f8  mov     r13d, 7FFFFFFFh
0x1800333fe  mov     edx, r13d
0x180033401  lea     rax, ?g_wszPUB_EnrollCancelEventName@@3QBGB; "UDRMPublishingEnrollment"
0x180033408  cmp     [rax], di
0x18003340b  jz      short loc_180033417
0x18003340d  add     rax, 2
0x180033411  sub     rdx, 1
0x180033415  jnz     short loc_180033408
0x180033417  mov     rax, rdx
0x18003341a  neg     rax
0x18003341d  sbb     ebx, ebx
0x18003341f  not     ebx
0x180033421  and     ebx, 80070057h
0x180033427  mov     rax, rdx
0x18003342a  mov     rcx, r13
0x18003342d  sub     rcx, rdx
0x180033430  neg     rax
0x180033433  sbb     r8, r8
0x180033436  and     r8, rcx
0x180033439  test    rdx, rdx
0x18003343c  jnz     short loc_180033443
0x18003343e  jmp     loc_18003381B
0x180033443  lea     rsi, [r8+1]
0x180033447  cmp     rsi, r8
0x18003344a  jb      loc_180033867
0x180033450  mov     rcx, rsi
0x180033453  shr     rcx, 20h
0x180033457  mov     rax, rcx
0x18003345a  shr     rax, 1Fh
0x18003345e  test    eax, eax
0x180033460  jnz     loc_18003386D
0x180033466  mov     eax, esi
0x180033468  add     rax, rax
0x18003346b  shl     rcx, 21h; this
0x18003346f  lea     rdx, [rcx+rax]
0x180033473  cmp     rdx, rax
0x180033476  jb      loc_180033872
0x18003347c  test    rdx, rdx
0x18003347f  jz      short loc_1800334CD
0x180033481  mov     eax, 2
0x180033486  mul     rsi
0x180033489  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180033490  cmovb   rax, rcx
0x180033494  mov     rcx, rax; Size
0x180033497  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003349c  mov     [rsp+98h+Block], rax
0x1800334a1  test    rax, rax
0x1800334a4  jnz     short loc_1800334B0
0x1800334a6  mov     ebx, 8007000Eh
0x1800334ab  jmp     loc_18003381B
0x1800334b0  lea     r8, ?g_wszPUB_EnrollCancelEventName@@3QBGB; "UDRMPublishingEnrollment"
0x1800334b7  mov     rdx, rsi; unsigned __int64
0x1800334ba  mov     rcx, rax; unsigned __int16 *
0x1800334bd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800334c2  mov     ebx, eax
0x1800334c4  test    eax, eax
0x1800334c6  jns     short loc_1800334CD
0x1800334c8  jmp     loc_18003381B
0x1800334cd  mov     r8, [rsp+98h+Block]; int
0x1800334d2  mov     edx, 1; unsigned int
0x1800334d7  call    ?OpenEventA@DRMOS@@YAPEAXKHPEBG@Z; DRMOS::OpenEventA(ulong,int,ushort const *)
0x1800334dc  mov     r15, rax
0x1800334df  test    rax, rax
0x1800334e2  jnz     short loc_180033508
0x1800334e4  call    cs:__imp_GetLastError
0x1800334ea  mov     ebx, eax
0x1800334ec  test    eax, eax
0x1800334ee  jle     short loc_1800334F9
0x1800334f0  movzx   ebx, ax
0x1800334f3  or      ebx, 80070000h
0x1800334f9  mov     eax, 80004005h
0x1800334fe  test    ebx, ebx
0x180033500  cmovns  ebx, eax
0x180033503  jmp     loc_18003381B
0x180033508  mov     rcx, r15; hEvent
0x18003350b  test    r14b, 4
0x18003350f  jz      short loc_18003351C
0x180033511  call    cs:__imp_SetEvent
0x180033517  jmp     loc_18003381B
0x18003351c  call    cs:__imp_ResetEvent
0x180033522  mov     ecx, 40h ; '@'; Size
0x180033527  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003352c  mov     r14, rax
0x18003352f  mov     [rsp+98h+var_48], rax
0x180033534  test    rax, rax
0x180033537  jz      loc_1800337F9
0x18003353d  mov     [rax], rdi
0x180033540  mov     [rax+8], rdi
0x180033544  mov     [rax+10h], edi
0x180033547  mov     [rax+18h], rdi
0x18003354b  mov     [rax+20h], rdi
0x18003354f  mov     [rax+28h], rdi
0x180033553  mov     [rax+30h], edi
0x180033556  mov     [rax+38h], rdi
0x18003355a  test    rax, rax
0x18003355d  jz      loc_1800337F9
0x180033563  mov     [rax+18h], r12
0x180033567  mov     rax, [rsp+98h+arg_30]
0x18003356f  mov     [r14+20h], rax
0x180033573  mov     eax, [rsp+98h+arg_0]
0x18003357a  mov     [r14+10h], eax
0x18003357e  lea     rsi, [r14+28h]
0x180033582  mov     [rsp+98h+var_50], rsi
0x180033587  mov     [rsi], r15
0x18003358a  mov     r15, rdi
0x18003358d  mov     eax, [rsp+98h+arg_8]
0x180033594  mov     [r14+30h], eax
0x180033598  mov     rdx, r13
0x18003359b  mov     rax, [rsp+98h+arg_20]
0x1800335a3  mov     [rsp+98h+var_48], r14
0x1800335a8  cmp     [rax], di
0x1800335ab  jz      short loc_1800335B7
0x1800335ad  add     rax, 2
0x1800335b1  sub     rdx, 1
0x1800335b5  jnz     short loc_1800335A8
0x1800335b7  mov     rax, rdx
0x1800335ba  neg     rax
0x1800335bd  sbb     ebx, ebx
0x1800335bf  not     ebx
0x1800335c1  and     ebx, 80070057h
0x1800335c7  mov     rax, rdx
0x1800335ca  mov     rcx, r13
0x1800335cd  sub     rcx, rdx
0x1800335d0  neg     rax
0x1800335d3  sbb     r8, r8
0x1800335d6  and     r8, rcx
0x1800335d9  test    rdx, rdx
0x1800335dc  jnz     short loc_1800335E3
0x1800335de  jmp     loc_1800337D0
0x1800335e3  lea     rbx, [r8+1]
0x1800335e7  cmp     rbx, r8
0x1800335ea  jb      loc_180033878
0x1800335f0  mov     rcx, rbx
0x1800335f3  shr     rcx, 20h
0x1800335f7  mov     rax, rcx
0x1800335fa  shr     rax, 1Fh
0x1800335fe  test    eax, eax
0x180033600  jnz     loc_18003387D
0x180033606  mov     eax, ebx
0x180033608  add     rax, rax
0x18003360b  shl     rcx, 21h
0x18003360f  lea     rdx, [rcx+rax]
0x180033613  cmp     rdx, rax
0x180033616  jb      loc_180033882
0x18003361c  test    rdx, rdx
0x18003361f  jz      short loc_18003366C
0x180033621  mov     eax, 2
0x180033626  mul     rbx
0x180033629  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180033630  cmovb   rax, rcx
0x180033634  mov     rcx, rax; Size
0x180033637  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003363c  mov     [r14], rax
0x18003363f  test    rax, rax
0x180033642  jnz     short loc_18003364E
0x180033644  mov     ebx, 8007000Eh
0x180033649  jmp     loc_1800337D0
0x18003364e  mov     r8, [rsp+98h+arg_20]; unsigned __int16 *
0x180033656  mov     rdx, rbx; unsigned __int64
0x180033659  mov     rcx, rax; unsigned __int16 *
0x18003365c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033661  mov     ebx, eax
0x180033663  test    eax, eax
0x180033665  jns     short loc_18003366C
0x180033667  jmp     loc_1800337D0
0x18003366c  mov     rcx, r13
0x18003366f  mov     rax, [rsp+98h+arg_28]
0x180033677  cmp     [rax], di
0x18003367a  jz      short loc_180033686
0x18003367c  add     rax, 2
0x180033680  sub     rcx, 1
0x180033684  jnz     short loc_180033677
0x180033686  mov     rax, rcx
0x180033689  neg     rax
0x18003368c  sbb     ebx, ebx
0x18003368e  not     ebx
0x180033690  and     ebx, 80070057h
0x180033696  mov     rax, rcx
0x180033699  sub     r13, rcx
0x18003369c  neg     rax
0x18003369f  sbb     rdx, rdx
0x1800336a2  and     rdx, r13
0x1800336a5  test    rcx, rcx
0x1800336a8  jnz     short loc_1800336AF
0x1800336aa  jmp     loc_1800337D0
0x1800336af  lea     rbx, [rdx+1]
0x1800336b3  cmp     rbx, rdx
0x1800336b6  jb      loc_180033888
0x1800336bc  mov     rcx, rbx
0x1800336bf  shr     rcx, 20h
0x1800336c3  mov     rax, rcx
0x1800336c6  shr     rax, 1Fh
0x1800336ca  test    eax, eax
0x1800336cc  jnz     loc_18003388D
0x1800336d2  mov     eax, ebx
0x1800336d4  add     rax, rax
0x1800336d7  shl     rcx, 21h
0x1800336db  lea     rdx, [rcx+rax]
0x1800336df  cmp     rdx, rax
0x1800336e2  jb      loc_180033892
0x1800336e8  test    rdx, rdx
0x1800336eb  jz      short loc_180033739
0x1800336ed  mov     eax, 2
0x1800336f2  mul     rbx
0x1800336f5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800336fc  cmovb   rax, rcx
0x180033700  mov     rcx, rax; Size
0x180033703  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033708  mov     [r14+8], rax
0x18003370c  test    rax, rax
0x18003370f  jnz     short loc_18003371B
0x180033711  mov     ebx, 8007000Eh
0x180033716  jmp     loc_1800337D0
0x18003371b  mov     r8, [rsp+98h+arg_28]; unsigned __int16 *
0x180033723  mov     rdx, rbx; unsigned __int64
0x180033726  mov     rcx, rax; unsigned __int16 *
0x180033729  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003372e  mov     ebx, eax
0x180033730  test    eax, eax
0x180033732  jns     short loc_180033739
0x180033734  jmp     loc_1800337D0
0x180033739  lea     r8, [r14+38h]; void **
0x18003373d  mov     edx, 1; unsigned int
0x180033742  mov     r13d, [rsp+98h+arg_0]
0x18003374a  mov     ecx, r13d; unsigned int
0x18003374d  call    ?GetThreadTermEvent@@YAJKIPEAPEAX@Z; GetThreadTermEvent(ulong,uint,void * *)
0x180033752  mov     ebx, eax
0x180033754  test    eax, eax
0x180033756  js      short loc_1800337D0
0x180033758  lea     rax, [rsp+98h+var_68]
0x18003375d  mov     [rsp+98h+ThrdAddr], rax; ThrdAddr
0x180033762  mov     [rsp+98h+InitFlag], edi; InitFlag
0x180033766  mov     r9, r14; ArgList
0x180033769  lea     r8, ?EnrollmentProc@@YAIPEAX@Z; StartAddress
0x180033770  xor     edx, edx; StackSize
0x180033772  xor     ecx, ecx; Security
0x180033774  call    cs:__imp__beginthreadex
0x18003377a  test    rax, rax
0x18003377d  jnz     short loc_1800337A0
0x18003377f  call    cs:__imp_GetLastError
0x180033785  mov     ebx, eax
0x180033787  test    eax, eax
0x180033789  jle     short loc_180033794
0x18003378b  movzx   ebx, ax
0x18003378e  or      ebx, 80070000h
0x180033794  mov     eax, 80004005h
0x180033799  test    ebx, ebx
0x18003379b  cmovns  ebx, eax
0x18003379e  jmp     short loc_1800337D0
0x1800337a0  mov     r8, rax; void *
0x1800337a3  mov     edx, 1; unsigned int
0x1800337a8  mov     ecx, r13d; unsigned int
0x1800337ab  call    ?SetThreadInfo@@YAJKIPEAX@Z; SetThreadInfo(ulong,uint,void *)
0x1800337b0  jmp     short loc_18003381B
0x1800337b2  xor     edi, edi
0x1800337b4  mov     r14, [rsp+98h+var_48]
0x1800337b9  mov     r15d, edi
0x1800337bc  mov     ebx, [rsp+98h+arg_18]
0x1800337c3  mov     r12, [rsp+98h+arg_10]
0x1800337cb  mov     rsi, [rsp+98h+var_50]
0x1800337d0  cmp     [rsi], rdi
0x1800337d3  jz      short loc_1800337DE
0x1800337d5  mov     rcx, [rsi]; hObject
0x1800337d8  call    cs:__imp_CloseHandle
0x1800337de  mov     rcx, [r14]; Block
0x1800337e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800337e6  mov     rcx, [r14+8]; Block
0x1800337ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800337ef  mov     rcx, r14; Block
0x1800337f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800337f7  jmp     short loc_18003381B
0x1800337f9  mov     ebx, 8007000Eh
0x1800337fe  jmp     short loc_18003381B
0x180033800  xor     edi, edi
  ... truncated ...
```
