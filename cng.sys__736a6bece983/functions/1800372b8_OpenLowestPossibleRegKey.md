# OpenLowestPossibleRegKey

- ea: `0x1800372b8`
- end: `0x180037599`
- name: `OpenLowestPossibleRegKey`
- size: `737`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180045cb0`
- `0x1800487c4`

## callees

- `0x180003f70`
- `0x180006470`
- `0x1800372b8`
- `0x1800375a0`
- `0x1800476d4`
- `0x180048944`
- `0x18009f650`

## import_xrefs

- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18003754c`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18003754c`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180037583`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180037583`
- `ntoskrnl!wcsrchr` at `0x1800374bb`
- `ntoskrnl!wcsrchr` at `0x1800374bb`

## string_xrefs

- `0x1800373d5`: `OpenLowestPossibleRegKey:: StringCchCopyW failed: %ld`
- `0x18003752c`: `OpenLowestPossibleRegKey:: pRegKeyNotifyRoot == nullptr`
- `0x1800a2d05`: `OpenLowestPossibleRegKey:: StringCchLengthW failed`
- `0x1800a2cce`: `OpenLowestPossibleRegKey:: StringCchLengthW failed: %ld`
- `0x18003744e`: `OpenLowestPossibleRegKey:: StringCchCopyW failed`
- `0x1800a2c75`: `OpenLowestPossibleRegKey:: Reached notify limit: %s`
- `0x180037560`: `OpenLowestPossibleRegKey:: wcsrchr returned NULL`
- `0x1800a2cab`: `OpenLowestPossibleRegKey:: Reached notify limit`

## pseudocode

```c
__int64 __fastcall OpenLowestPossibleRegKey(_QWORD *a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 v5; // r12
  __int64 v6; // r15
  wchar_t *v7; // rax
  __int64 v8; // r8
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rsi
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rdi
  unsigned __int64 v14; // rdx
  __int64 v15; // rax
  wchar_t *v16; // rcx
  _WORD *v17; // r8
  _WORD *v18; // rcx
  int v19; // eax
  wchar_t *v20; // rcx
  __int64 v22; // r13
  __int64 v23; // r15
  __int64 v24; // rbp
  ULONG v25; // eax
  unsigned int v26; // ebx
  wchar_t *v27; // r9
  unsigned __int16 *v28; // rcx
  int v29; // eax
  int v30; // edx
  int v31; // eax
  wchar_t *v32; // rcx
  int v33; // eax
  wchar_t *v34; // rcx
  wchar_t pszDest[1024]; // [rsp+40h] [rbp-848h] BYREF

  if ( !a1 )
  {
    SendTelemetry(L"OpenLowestPossibleRegKey:: pRegKeyNotifyRoot == nullptr");
    return 6;
  }
  v5 = 2LL * a2;
  v6 = a2;
  v7 = off_1800A7DE0[2 * a2];
  if ( !v7 )
  {
    LODWORD(v10) = -2147024809;
LABEL_47:
    v33 = StringCchPrintfExW(pszDest, 0x400u, 0, 0, 0, L"OpenLowestPossibleRegKey:: StringCchLengthW failed: %ld", v10);
    if ( (int)(v33 + 0x80000000) < 0
      || (v34 = L"OpenLowestPossibleRegKey:: StringCchLengthW failed", v33 == -2147024774) )
    {
      v34 = pszDest;
    }
    SendTelemetry(v34);
    return 13;
  }
  v8 = 0x7FFFFFFF;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v8;
  }
  while ( v8 );
  v9 = -2147024809;
  v10 = v8 == 0 ? 0x80070057 : 0;
  v11 = (0x7FFFFFFF - v8) & -(__int64)(v8 != 0);
  if ( !v8 )
    goto LABEL_47;
  v12 = (unsigned __int16 *)MSCryptAlloc(2 * v11 + 2, v10, v8, a4);
  v13 = v12;
  if ( !v12 )
    return 8;
  v14 = v11 + 1;
  if ( v11 == -1 )
  {
LABEL_17:
    v19 = StringCchPrintfExW(pszDest, 0x400u, 0, 0, 0, L"OpenLowestPossibleRegKey:: StringCchCopyW failed: %ld", v9);
    if ( (int)(v19 + 0x80000000) < 0 || (v20 = L"OpenLowestPossibleRegKey:: StringCchCopyW failed", v19 == -2147024774) )
      v20 = pszDest;
    SendTelemetry(v20);
    MSCryptFree(v13);
    return 13;
  }
  if ( v14 > 0x7FFFFFFF )
  {
    *v12 = 0;
    goto LABEL_17;
  }
  v15 = 2147483646;
  v16 = off_1800A7DE0[v5];
  v17 = v13;
  do
  {
    if ( !v15 )
      break;
    if ( !*v16 )
      break;
    *v17++ = *v16++;
    --v15;
    --v14;
  }
  while ( v14 );
  v18 = v17 - 1;
  v9 = v14 == 0 ? 0x8007007A : 0;
  if ( v14 )
    v18 = v17;
  *v18 = 0;
  if ( !v14 )
    goto LABEL_17;
  v22 = 0;
  if ( a1[11] )
    v22 = PsAttachSiloToCurrentThread();
  v23 = 32 * v6;
  v24 = v23;
  *(_DWORD *)(*a1 + v23 + 24) = 1;
  while ( 1 )
  {
    v25 = KeRegOpenKey((void *)0xFFFFFFFF80000002LL, v13, 0x10u, (void **)(v23 + *a1));
    v26 = v25;
    if ( v25 != 2 )
      break;
    *(_DWORD *)(*a1 + v24 + 24) = 0;
    v27 = wcsrchr(v13, 0x5Cu);
    if ( !v27 )
    {
      SendTelemetry(L"OpenLowestPossibleRegKey:: wcsrchr returned NULL");
      v26 = 13;
      goto LABEL_36;
    }
    v28 = v13;
    do
    {
      v29 = *(unsigned __int16 *)((char *)v28 + (char *)off_1800A7DE0[v5 + 1] - (char *)v13);
      v30 = *v28 - v29;
      if ( v30 )
        break;
      ++v28;
    }
    while ( v29 );
    if ( !v30 )
    {
      v31 = StringCchPrintfExW(
              pszDest,
              0x400u,
              0,
              0,
              0,
              L"OpenLowestPossibleRegKey:: Reached notify limit: %s",
              off_1800A7DE0[v5 + 1]);
      if ( (int)(v31 + 0x80000000) < 0 || (v32 = L"OpenLowestPossibleRegKey:: Reached notify limit", v31 == -2147024774) )
        v32 = pszDest;
      SendTelemetry(v32);
      v26 = 18;
      goto LABEL_36;
    }
    v23 = v24;
    *v27 = 0;
  }
  if ( v25 )
    *(_DWORD *)(*a1 + v24 + 24) = 0;
LABEL_36:
  if ( a1[11] )
    PsDetachSiloFromCurrentThread(v22);
  MSCryptFree(v13);
  return v26;
}

```

## disassembly

```asm
0x1800372b8  mov     [rsp+arg_10], rbx
0x1800372bd  push    rbp
0x1800372be  push    rsi
0x1800372bf  push    rdi
0x1800372c0  push    r12
0x1800372c2  push    r13
0x1800372c4  push    r14
0x1800372c6  push    r15
0x1800372c8  sub     rsp, 850h
0x1800372cf  mov     rax, cs:__security_cookie
0x1800372d6  xor     rax, rsp
0x1800372d9  mov     [rsp+888h+var_48], rax
0x1800372e1  xor     ebp, ebp
0x1800372e3  mov     r14, rcx
0x1800372e6  test    rcx, rcx
0x1800372e9  jz      loc_18003752C
0x1800372ef  mov     r12d, edx
0x1800372f2  lea     rax, off_1800A7DE0; "Software\\Policies\\Microsoft\\Cryptogr"...
0x1800372f9  add     r12, r12
0x1800372fc  mov     r15d, edx
0x1800372ff  mov     rax, [rax+r12*8]
0x180037303  test    rax, rax
0x180037306  jz      loc_18003745B
0x18003730c  mov     r13d, 7FFFFFFFh
0x180037312  mov     r8d, r13d
0x180037315  cmp     [rax], bp
0x180037318  jz      short loc_180037324
0x18003731a  add     rax, 2
0x18003731e  sub     r8, 1
0x180037322  jnz     short loc_180037315
0x180037324  mov     rax, r8
0x180037327  mov     ebx, 80070057h
0x18003732c  neg     rax
0x18003732f  mov     rcx, r13
0x180037332  mov     rax, r8
0x180037335  sbb     edx, edx
0x180037337  sub     rcx, r8
0x18003733a  not     edx
0x18003733c  and     edx, ebx
0x18003733e  neg     rax
0x180037341  sbb     rsi, rsi
0x180037344  and     rsi, rcx
0x180037347  test    r8, r8
0x18003734a  jz      loc_1800A2CCA
0x180037350  lea     rcx, ds:2[rsi*2]
0x180037358  call    MSCryptAlloc
0x18003735d  mov     rdi, rax
0x180037360  test    rax, rax
0x180037363  jz      loc_180037542
0x180037369  lea     rdx, [rsi+1]
0x18003736d  lea     esi, [rbx+23h]
0x180037370  test    rdx, rdx
0x180037373  jz      short loc_1800373D5
0x180037375  cmp     rdx, r13
0x180037378  ja      loc_180037591
0x18003737e  lea     rcx, off_1800A7DE0; "Software\\Policies\\Microsoft\\Cryptogr"...
0x180037385  mov     eax, 7FFFFFFEh
0x18003738a  mov     rcx, [rcx+r12*8]
0x18003738e  mov     r8, rdi
0x180037391  test    rax, rax
0x180037394  jz      short loc_1800373B5
0x180037396  movzx   r9d, word ptr [rcx]
0x18003739a  test    r9w, r9w
0x18003739e  jz      short loc_1800373B5
0x1800373a0  mov     [r8], r9w
0x1800373a4  add     rcx, 2
0x1800373a8  add     r8, 2
0x1800373ac  dec     rax
0x1800373af  sub     rdx, 1
0x1800373b3  jnz     short loc_180037391
0x1800373b5  mov     rax, rdx
0x1800373b8  lea     rcx, [r8-2]
0x1800373bc  neg     rax
0x1800373bf  sbb     ebx, ebx
0x1800373c1  not     ebx
0x1800373c3  and     ebx, esi
0x1800373c5  test    rdx, rdx
0x1800373c8  cmovnz  rcx, r8
0x1800373cc  mov     [rcx], bp
0x1800373cf  jnz     loc_180037465
0x1800373d5  lea     rax, aOpenlowestposs_1; "OpenLowestPossibleRegKey:: StringCchCop"...
0x1800373dc  mov     dword ptr [rsp+888h+var_858], ebx
0x1800373e0  mov     [rsp+888h+var_860], rax; unsigned __int16 *
0x1800373e5  lea     rcx, [rsp+888h+pszDest]; pszDest
0x1800373ea  xor     r9d, r9d; unsigned __int64 *
0x1800373ed  mov     qword ptr [rsp+888h+var_868], rbp; unsigned int
0x1800373f2  xor     r8d, r8d; unsigned __int16 **
0x1800373f5  mov     edx, 400h; unsigned __int64
0x1800373fa  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800373ff  mov     edx, 80000000h
0x180037404  lea     ecx, [rax+rdx]
0x180037407  test    edx, ecx
0x180037409  jz      short loc_18003744E
0x18003740b  lea     rcx, [rsp+888h+pszDest]
0x180037410  call    SendTelemetry
0x180037415  mov     rcx, rdi; P
0x180037418  call    MSCryptFree
0x18003741d  mov     eax, 0Dh
0x180037422  mov     rcx, [rsp+888h+var_48]
0x18003742a  xor     rcx, rsp; StackCookie
0x18003742d  call    __security_check_cookie
0x180037432  mov     rbx, [rsp+888h+arg_10]
0x18003743a  add     rsp, 850h
0x180037441  pop     r15
0x180037443  pop     r14
0x180037445  pop     r13
0x180037447  pop     r12
0x180037449  pop     rdi
0x18003744a  pop     rsi
0x18003744b  pop     rbp
0x18003744c  retn
0x18003744e  lea     rcx, aOpenlowestposs_2; "OpenLowestPossibleRegKey:: StringCchCop"...
0x180037455  cmp     eax, esi
0x180037457  jz      short loc_18003740B
0x180037459  jmp     short loc_180037410
0x18003745b  mov     edx, 80070057h
0x180037460  jmp     loc_1800A2CCA
0x180037465  mov     rcx, [r14+58h]
0x180037469  mov     r13, rbp
0x18003746c  test    rcx, rcx
0x18003746f  jnz     loc_18003754C
0x180037475  mov     rcx, [r14]
0x180037478  shl     r15, 5
0x18003747c  mov     rbp, r15
0x18003747f  mov     dword ptr [rcx+r15+18h], 1
0x180037488  mov     r9, [r14]
0x18003748b  mov     r8d, 10h
0x180037491  add     r9, r15
0x180037494  mov     rdx, rdi
0x180037497  mov     rcx, 0FFFFFFFF80000002h
0x18003749e  call    KeRegOpenKey
0x1800374a3  mov     ebx, eax
0x1800374a5  cmp     eax, 2
0x1800374a8  jnz     short loc_180037512
0x1800374aa  mov     rax, [r14]
0x1800374ad  lea     edx, [rbx+5Ah]; Ch
0x1800374b0  mov     rcx, rdi; Str
0x1800374b3  mov     dword ptr [rax+rbp+18h], 0
0x1800374bb  call    cs:__imp_wcsrchr
0x1800374c2  nop     dword ptr [rax+rax+00h]
0x1800374c7  mov     r9, rax
0x1800374ca  test    rax, rax
0x1800374cd  jz      loc_180037560
0x1800374d3  lea     rax, off_1800A7DE0; "Software\\Policies\\Microsoft\\Cryptogr"...
0x1800374da  mov     rcx, rdi
0x1800374dd  mov     r10, [rax+r12*8+8]
0x1800374e2  mov     r8, r10
0x1800374e5  sub     r8, rdi
0x1800374e8  movzx   edx, word ptr [rcx]
0x1800374eb  movzx   eax, word ptr [rcx+r8]
0x1800374f0  sub     edx, eax
0x1800374f2  jnz     short loc_1800374FC
0x1800374f4  add     rcx, 2
0x1800374f8  test    eax, eax
0x1800374fa  jnz     short loc_1800374E8
0x1800374fc  test    edx, edx
0x1800374fe  jz      loc_1800A2C70
0x180037504  xor     eax, eax
0x180037506  mov     r15, rbp
0x180037509  mov     [r9], ax
0x18003750d  jmp     loc_180037488
0x180037512  test    eax, eax
0x180037514  jnz     short loc_180037573
0x180037516  cmp     qword ptr [r14+58h], 0
0x18003751b  jnz     short loc_180037580
0x18003751d  mov     rcx, rdi; P
0x180037520  call    MSCryptFree
0x180037525  mov     eax, ebx
0x180037527  jmp     loc_180037422
0x18003752c  lea     rcx, aOpenlowestposs_0; "OpenLowestPossibleRegKey:: pRegKeyNotif"...
0x180037533  call    SendTelemetry
0x180037538  mov     eax, 6
0x18003753d  jmp     loc_180037422
0x180037542  mov     eax, 8
0x180037547  jmp     loc_180037422
0x18003754c  call    cs:__imp_PsAttachSiloToCurrentThread
0x180037553  nop     dword ptr [rax+rax+00h]
0x180037558  mov     r13, rax
0x18003755b  jmp     loc_180037475
0x180037560  lea     rcx, aOpenlowestposs_4; "OpenLowestPossibleRegKey:: wcsrchr retu"...
0x180037567  call    SendTelemetry
0x18003756c  mov     ebx, 0Dh
0x180037571  jmp     short loc_180037516
0x180037573  mov     rax, [r14]
0x180037576  mov     dword ptr [rax+rbp+18h], 0
0x18003757e  jmp     short loc_180037516
0x180037580  mov     rcx, r13
0x180037583  call    cs:__imp_PsDetachSiloFromCurrentThread
0x18003758a  nop     dword ptr [rax+rax+00h]
0x18003758f  jmp     short loc_18003751D
0x180037591  mov     [rax], bp
0x180037594  jmp     loc_1800373D5
0x1800a2c70  mov     [rsp+888h+var_858], r10
0x1800a2c75  lea     rax, aOpenlowestposs_6; "OpenLowestPossibleRegKey:: Reached noti"...
0x1800a2c7c  mov     [rsp+888h+var_860], rax; unsigned __int16 *
0x1800a2c81  lea     rcx, [rsp+888h+pszDest]; pszDest
0x1800a2c86  xor     r9d, r9d; unsigned __int64 *
0x1800a2c89  mov     qword ptr [rsp+888h+var_868], 0; unsigned int
0x1800a2c92  xor     r8d, r8d; unsigned __int16 **
0x1800a2c95  mov     edx, 400h; unsigned __int64
0x1800a2c9a  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800a2c9f  mov     edx, 80000000h
0x1800a2ca4  lea     ecx, [rax+rdx]
0x1800a2ca7  test    edx, ecx
0x1800a2ca9  jnz     short loc_1800A2CB6
0x1800a2cab  lea     rcx, aOpenlowestposs_5; "OpenLowestPossibleRegKey:: Reached noti"...
0x1800a2cb2  cmp     eax, esi
0x1800a2cb4  jnz     short loc_1800A2CBB
0x1800a2cb6  lea     rcx, [rsp+888h+pszDest]
0x1800a2cbb  call    SendTelemetry
0x1800a2cc0  mov     ebx, 12h
0x1800a2cc5  jmp     loc_180037516
0x1800a2cca  mov     dword ptr [rsp+888h+var_858], edx
0x1800a2cce  lea     rax, aOpenlowestposs_3; "OpenLowestPossibleRegKey:: StringCchLen"...
0x1800a2cd5  mov     [rsp+888h+var_860], rax; unsigned __int16 *
0x1800a2cda  lea     rcx, [rsp+888h+pszDest]; pszDest
0x1800a2cdf  xor     r9d, r9d; unsigned __int64 *
0x1800a2ce2  mov     qword ptr [rsp+888h+var_868], rbp; unsigned int
0x1800a2ce7  xor     r8d, r8d; unsigned __int16 **
0x1800a2cea  mov     edx, 400h; unsigned __int64
0x1800a2cef  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800a2cf4  mov     edx, 80000000h
0x1800a2cf9  lea     ecx, [rax+rdx]
0x1800a2cfc  test    edx, ecx
0x1800a2cfe  jnz     short loc_1800A2D10
0x1800a2d00  mov     esi, 8007007Ah
0x1800a2d05  lea     rcx, aOpenlowestposs; "OpenLowestPossibleRegKey:: StringCchLen"...
0x1800a2d0c  cmp     eax, esi
0x1800a2d0e  jnz     short loc_1800A2D15
0x1800a2d10  lea     rcx, [rsp+888h+pszDest]
0x1800a2d15  call    SendTelemetry
0x1800a2d1a  nop
0x1800a2d1b  jmp     loc_18003741D
```
