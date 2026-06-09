# OpenLowestPossibleRegKey

- ea: `0x1800367b8`
- end: `0x180036a99`
- name: `OpenLowestPossibleRegKey`
- size: `737`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180045220`
- `0x180047d34`

## callees

- `0x180003f70`
- `0x180006470`
- `0x1800367b8`
- `0x180036aa0`
- `0x180046c44`
- `0x180047eb4`
- `0x18009d820`

## import_xrefs

- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180036a4c`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180036a4c`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180036a83`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180036a83`
- `ntoskrnl!wcsrchr` at `0x1800369bb`
- `ntoskrnl!wcsrchr` at `0x1800369bb`

## string_xrefs

- `0x1800368d5`: `OpenLowestPossibleRegKey:: StringCchCopyW failed: %ld`
- `0x180036a2c`: `OpenLowestPossibleRegKey:: pRegKeyNotifyRoot == nullptr`
- `0x1800a0ed5`: `OpenLowestPossibleRegKey:: StringCchLengthW failed`
- `0x1800a0e9e`: `OpenLowestPossibleRegKey:: StringCchLengthW failed: %ld`
- `0x18003694e`: `OpenLowestPossibleRegKey:: StringCchCopyW failed`
- `0x1800a0e45`: `OpenLowestPossibleRegKey:: Reached notify limit: %s`
- `0x180036a60`: `OpenLowestPossibleRegKey:: wcsrchr returned NULL`
- `0x1800a0e7b`: `OpenLowestPossibleRegKey:: Reached notify limit`

## pseudocode

```c
__int64 __fastcall OpenLowestPossibleRegKey(_QWORD *a1, unsigned int a2)
{
  __int64 v3; // r12
  __int64 v4; // r15
  wchar_t *v5; // rax
  __int64 v6; // r8
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rsi
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rdi
  unsigned __int64 v12; // rdx
  __int64 v13; // rax
  wchar_t *v14; // rcx
  _WORD *v15; // r8
  _WORD *v16; // rcx
  int v17; // eax
  wchar_t *v18; // rcx
  __int64 v20; // r13
  __int64 v21; // r15
  __int64 v22; // rbp
  unsigned int v23; // eax
  unsigned int v24; // ebx
  wchar_t *v25; // r9
  unsigned __int16 *v26; // rcx
  int v27; // eax
  int v28; // edx
  int v29; // eax
  wchar_t *v30; // rcx
  int v31; // eax
  wchar_t *v32; // rcx
  wchar_t pszDest[1024]; // [rsp+40h] [rbp-848h] BYREF

  if ( !a1 )
  {
    SendTelemetry(L"OpenLowestPossibleRegKey:: pRegKeyNotifyRoot == nullptr");
    return 6;
  }
  v3 = 2LL * a2;
  v4 = a2;
  v5 = off_1800A5DE0[2 * a2];
  if ( !v5 )
  {
    LODWORD(v8) = -2147024809;
LABEL_47:
    v31 = StringCchPrintfExW(pszDest, 0x400u, 0, 0, 0, L"OpenLowestPossibleRegKey:: StringCchLengthW failed: %ld", v8);
    if ( (int)(v31 + 0x80000000) < 0
      || (v32 = L"OpenLowestPossibleRegKey:: StringCchLengthW failed", v31 == -2147024774) )
    {
      v32 = pszDest;
    }
    SendTelemetry(v32);
    return 13;
  }
  v6 = 0x7FFFFFFF;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  v7 = -2147024809;
  v8 = v6 == 0 ? 0x80070057 : 0;
  v9 = (0x7FFFFFFF - v6) & -(__int64)(v6 != 0);
  if ( !v6 )
    goto LABEL_47;
  v10 = (unsigned __int16 *)MSCryptAlloc(2 * v9 + 2, v8);
  v11 = v10;
  if ( !v10 )
    return 8;
  v12 = v9 + 1;
  if ( v9 == -1 )
  {
LABEL_17:
    v17 = StringCchPrintfExW(pszDest, 0x400u, 0, 0, 0, L"OpenLowestPossibleRegKey:: StringCchCopyW failed: %ld", v7);
    if ( (int)(v17 + 0x80000000) < 0 || (v18 = L"OpenLowestPossibleRegKey:: StringCchCopyW failed", v17 == -2147024774) )
      v18 = pszDest;
    SendTelemetry(v18);
    MSCryptFree(v11);
    return 13;
  }
  if ( v12 > 0x7FFFFFFF )
  {
    *v10 = 0;
    goto LABEL_17;
  }
  v13 = 2147483646;
  v14 = off_1800A5DE0[v3];
  v15 = v11;
  do
  {
    if ( !v13 )
      break;
    if ( !*v14 )
      break;
    *v15++ = *v14++;
    --v13;
    --v12;
  }
  while ( v12 );
  v16 = v15 - 1;
  v7 = v12 == 0 ? 0x8007007A : 0;
  if ( v12 )
    v16 = v15;
  *v16 = 0;
  if ( !v12 )
    goto LABEL_17;
  v20 = 0;
  if ( a1[11] )
    v20 = PsAttachSiloToCurrentThread();
  v21 = 32 * v4;
  v22 = v21;
  *(_DWORD *)(*a1 + v21 + 24) = 1;
  while ( 1 )
  {
    v23 = KeRegOpenKey(-2147483646, v11, 16, v21 + *a1);
    v24 = v23;
    if ( v23 != 2 )
      break;
    *(_DWORD *)(*a1 + v22 + 24) = 0;
    v25 = wcsrchr(v11, 0x5Cu);
    if ( !v25 )
    {
      SendTelemetry(L"OpenLowestPossibleRegKey:: wcsrchr returned NULL");
      v24 = 13;
      goto LABEL_36;
    }
    v26 = v11;
    do
    {
      v27 = *(unsigned __int16 *)((char *)v26 + (char *)off_1800A5DE0[v3 + 1] - (char *)v11);
      v28 = *v26 - v27;
      if ( v28 )
        break;
      ++v26;
    }
    while ( v27 );
    if ( !v28 )
    {
      v29 = StringCchPrintfExW(
              pszDest,
              0x400u,
              0,
              0,
              0,
              L"OpenLowestPossibleRegKey:: Reached notify limit: %s",
              off_1800A5DE0[v3 + 1]);
      if ( (int)(v29 + 0x80000000) < 0 || (v30 = L"OpenLowestPossibleRegKey:: Reached notify limit", v29 == -2147024774) )
        v30 = pszDest;
      SendTelemetry(v30);
      v24 = 18;
      goto LABEL_36;
    }
    v21 = v22;
    *v25 = 0;
  }
  if ( v23 )
    *(_DWORD *)(*a1 + v22 + 24) = 0;
LABEL_36:
  if ( a1[11] )
    PsDetachSiloFromCurrentThread(v20);
  MSCryptFree(v11);
  return v24;
}

```

## disassembly

```asm
0x1800367b8  mov     [rsp+arg_10], rbx
0x1800367bd  push    rbp
0x1800367be  push    rsi
0x1800367bf  push    rdi
0x1800367c0  push    r12
0x1800367c2  push    r13
0x1800367c4  push    r14
0x1800367c6  push    r15
0x1800367c8  sub     rsp, 850h
0x1800367cf  mov     rax, cs:__security_cookie
0x1800367d6  xor     rax, rsp
0x1800367d9  mov     [rsp+888h+var_48], rax
0x1800367e1  xor     ebp, ebp
0x1800367e3  mov     r14, rcx
0x1800367e6  test    rcx, rcx
0x1800367e9  jz      loc_180036A2C
0x1800367ef  mov     r12d, edx
0x1800367f2  lea     rax, off_1800A5DE0; "Software\\Policies\\Microsoft\\Cryptogr"...
0x1800367f9  add     r12, r12
0x1800367fc  mov     r15d, edx
0x1800367ff  mov     rax, [rax+r12*8]
0x180036803  test    rax, rax
0x180036806  jz      loc_18003695B
0x18003680c  mov     r13d, 7FFFFFFFh
0x180036812  mov     r8d, r13d
0x180036815  cmp     [rax], bp
0x180036818  jz      short loc_180036824
0x18003681a  add     rax, 2
0x18003681e  sub     r8, 1
0x180036822  jnz     short loc_180036815
0x180036824  mov     rax, r8
0x180036827  mov     ebx, 80070057h
0x18003682c  neg     rax
0x18003682f  mov     rcx, r13
0x180036832  mov     rax, r8
0x180036835  sbb     edx, edx
0x180036837  sub     rcx, r8
0x18003683a  not     edx
0x18003683c  and     edx, ebx
0x18003683e  neg     rax
0x180036841  sbb     rsi, rsi
0x180036844  and     rsi, rcx
0x180036847  test    r8, r8
0x18003684a  jz      loc_1800A0E9A
0x180036850  lea     rcx, ds:2[rsi*2]
0x180036858  call    MSCryptAlloc
0x18003685d  mov     rdi, rax
0x180036860  test    rax, rax
0x180036863  jz      loc_180036A42
0x180036869  lea     rdx, [rsi+1]
0x18003686d  lea     esi, [rbx+23h]
0x180036870  test    rdx, rdx
0x180036873  jz      short loc_1800368D5
0x180036875  cmp     rdx, r13
0x180036878  ja      loc_180036A91
0x18003687e  lea     rcx, off_1800A5DE0; "Software\\Policies\\Microsoft\\Cryptogr"...
0x180036885  mov     eax, 7FFFFFFEh
0x18003688a  mov     rcx, [rcx+r12*8]
0x18003688e  mov     r8, rdi
0x180036891  test    rax, rax
0x180036894  jz      short loc_1800368B5
0x180036896  movzx   r9d, word ptr [rcx]
0x18003689a  test    r9w, r9w
0x18003689e  jz      short loc_1800368B5
0x1800368a0  mov     [r8], r9w
0x1800368a4  add     rcx, 2
0x1800368a8  add     r8, 2
0x1800368ac  dec     rax
0x1800368af  sub     rdx, 1
0x1800368b3  jnz     short loc_180036891
0x1800368b5  mov     rax, rdx
0x1800368b8  lea     rcx, [r8-2]
0x1800368bc  neg     rax
0x1800368bf  sbb     ebx, ebx
0x1800368c1  not     ebx
0x1800368c3  and     ebx, esi
0x1800368c5  test    rdx, rdx
0x1800368c8  cmovnz  rcx, r8
0x1800368cc  mov     [rcx], bp
0x1800368cf  jnz     loc_180036965
0x1800368d5  lea     rax, aOpenlowestposs_1; "OpenLowestPossibleRegKey:: StringCchCop"...
0x1800368dc  mov     dword ptr [rsp+888h+var_858], ebx
0x1800368e0  mov     [rsp+888h+var_860], rax; unsigned __int16 *
0x1800368e5  lea     rcx, [rsp+888h+pszDest]; pszDest
0x1800368ea  xor     r9d, r9d; unsigned __int64 *
0x1800368ed  mov     qword ptr [rsp+888h+var_868], rbp; unsigned int
0x1800368f2  xor     r8d, r8d; unsigned __int16 **
0x1800368f5  mov     edx, 400h; unsigned __int64
0x1800368fa  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800368ff  mov     edx, 80000000h
0x180036904  lea     ecx, [rax+rdx]
0x180036907  test    edx, ecx
0x180036909  jz      short loc_18003694E
0x18003690b  lea     rcx, [rsp+888h+pszDest]
0x180036910  call    SendTelemetry
0x180036915  mov     rcx, rdi; P
0x180036918  call    MSCryptFree
0x18003691d  mov     eax, 0Dh
0x180036922  mov     rcx, [rsp+888h+var_48]
0x18003692a  xor     rcx, rsp; StackCookie
0x18003692d  call    __security_check_cookie
0x180036932  mov     rbx, [rsp+888h+arg_10]
0x18003693a  add     rsp, 850h
0x180036941  pop     r15
0x180036943  pop     r14
0x180036945  pop     r13
0x180036947  pop     r12
0x180036949  pop     rdi
0x18003694a  pop     rsi
0x18003694b  pop     rbp
0x18003694c  retn
0x18003694e  lea     rcx, aOpenlowestposs_2; "OpenLowestPossibleRegKey:: StringCchCop"...
0x180036955  cmp     eax, esi
0x180036957  jz      short loc_18003690B
0x180036959  jmp     short loc_180036910
0x18003695b  mov     edx, 80070057h
0x180036960  jmp     loc_1800A0E9A
0x180036965  mov     rcx, [r14+58h]
0x180036969  mov     r13, rbp
0x18003696c  test    rcx, rcx
0x18003696f  jnz     loc_180036A4C
0x180036975  mov     rcx, [r14]
0x180036978  shl     r15, 5
0x18003697c  mov     rbp, r15
0x18003697f  mov     dword ptr [rcx+r15+18h], 1
0x180036988  mov     r9, [r14]
0x18003698b  mov     r8d, 10h
0x180036991  add     r9, r15
0x180036994  mov     rdx, rdi
0x180036997  mov     rcx, 0FFFFFFFF80000002h
0x18003699e  call    KeRegOpenKey
0x1800369a3  mov     ebx, eax
0x1800369a5  cmp     eax, 2
0x1800369a8  jnz     short loc_180036A12
0x1800369aa  mov     rax, [r14]
0x1800369ad  lea     edx, [rbx+5Ah]; Ch
0x1800369b0  mov     rcx, rdi; Str
0x1800369b3  mov     dword ptr [rax+rbp+18h], 0
0x1800369bb  call    cs:__imp_wcsrchr
0x1800369c2  nop     dword ptr [rax+rax+00h]
0x1800369c7  mov     r9, rax
0x1800369ca  test    rax, rax
0x1800369cd  jz      loc_180036A60
0x1800369d3  lea     rax, off_1800A5DE0; "Software\\Policies\\Microsoft\\Cryptogr"...
0x1800369da  mov     rcx, rdi
0x1800369dd  mov     r10, [rax+r12*8+8]
0x1800369e2  mov     r8, r10
0x1800369e5  sub     r8, rdi
0x1800369e8  movzx   edx, word ptr [rcx]
0x1800369eb  movzx   eax, word ptr [rcx+r8]
0x1800369f0  sub     edx, eax
0x1800369f2  jnz     short loc_1800369FC
0x1800369f4  add     rcx, 2
0x1800369f8  test    eax, eax
0x1800369fa  jnz     short loc_1800369E8
0x1800369fc  test    edx, edx
0x1800369fe  jz      loc_1800A0E40
0x180036a04  xor     eax, eax
0x180036a06  mov     r15, rbp
0x180036a09  mov     [r9], ax
0x180036a0d  jmp     loc_180036988
0x180036a12  test    eax, eax
0x180036a14  jnz     short loc_180036A73
0x180036a16  cmp     qword ptr [r14+58h], 0
0x180036a1b  jnz     short loc_180036A80
0x180036a1d  mov     rcx, rdi; P
0x180036a20  call    MSCryptFree
0x180036a25  mov     eax, ebx
0x180036a27  jmp     loc_180036922
0x180036a2c  lea     rcx, aOpenlowestposs_0; "OpenLowestPossibleRegKey:: pRegKeyNotif"...
0x180036a33  call    SendTelemetry
0x180036a38  mov     eax, 6
0x180036a3d  jmp     loc_180036922
0x180036a42  mov     eax, 8
0x180036a47  jmp     loc_180036922
0x180036a4c  call    cs:__imp_PsAttachSiloToCurrentThread
0x180036a53  nop     dword ptr [rax+rax+00h]
0x180036a58  mov     r13, rax
0x180036a5b  jmp     loc_180036975
0x180036a60  lea     rcx, aOpenlowestposs_4; "OpenLowestPossibleRegKey:: wcsrchr retu"...
0x180036a67  call    SendTelemetry
0x180036a6c  mov     ebx, 0Dh
0x180036a71  jmp     short loc_180036A16
0x180036a73  mov     rax, [r14]
0x180036a76  mov     dword ptr [rax+rbp+18h], 0
0x180036a7e  jmp     short loc_180036A16
0x180036a80  mov     rcx, r13
0x180036a83  call    cs:__imp_PsDetachSiloFromCurrentThread
0x180036a8a  nop     dword ptr [rax+rax+00h]
0x180036a8f  jmp     short loc_180036A1D
0x180036a91  mov     [rax], bp
0x180036a94  jmp     loc_1800368D5
0x1800a0e40  mov     [rsp+888h+var_858], r10
0x1800a0e45  lea     rax, aOpenlowestposs_6; "OpenLowestPossibleRegKey:: Reached noti"...
0x1800a0e4c  mov     [rsp+888h+var_860], rax; unsigned __int16 *
0x1800a0e51  lea     rcx, [rsp+888h+pszDest]; pszDest
0x1800a0e56  xor     r9d, r9d; unsigned __int64 *
0x1800a0e59  mov     qword ptr [rsp+888h+var_868], 0; unsigned int
0x1800a0e62  xor     r8d, r8d; unsigned __int16 **
0x1800a0e65  mov     edx, 400h; unsigned __int64
0x1800a0e6a  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800a0e6f  mov     edx, 80000000h
0x1800a0e74  lea     ecx, [rax+rdx]
0x1800a0e77  test    edx, ecx
0x1800a0e79  jnz     short loc_1800A0E86
0x1800a0e7b  lea     rcx, aOpenlowestposs_5; "OpenLowestPossibleRegKey:: Reached noti"...
0x1800a0e82  cmp     eax, esi
0x1800a0e84  jnz     short loc_1800A0E8B
0x1800a0e86  lea     rcx, [rsp+888h+pszDest]
0x1800a0e8b  call    SendTelemetry
0x1800a0e90  mov     ebx, 12h
0x1800a0e95  jmp     loc_180036A16
0x1800a0e9a  mov     dword ptr [rsp+888h+var_858], edx
0x1800a0e9e  lea     rax, aOpenlowestposs_3; "OpenLowestPossibleRegKey:: StringCchLen"...
0x1800a0ea5  mov     [rsp+888h+var_860], rax; unsigned __int16 *
0x1800a0eaa  lea     rcx, [rsp+888h+pszDest]; pszDest
0x1800a0eaf  xor     r9d, r9d; unsigned __int64 *
0x1800a0eb2  mov     qword ptr [rsp+888h+var_868], rbp; unsigned int
0x1800a0eb7  xor     r8d, r8d; unsigned __int16 **
0x1800a0eba  mov     edx, 400h; unsigned __int64
0x1800a0ebf  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800a0ec4  mov     edx, 80000000h
0x1800a0ec9  lea     ecx, [rax+rdx]
0x1800a0ecc  test    edx, ecx
0x1800a0ece  jnz     short loc_1800A0EE0
0x1800a0ed0  mov     esi, 8007007Ah
0x1800a0ed5  lea     rcx, aOpenlowestposs; "OpenLowestPossibleRegKey:: StringCchLen"...
0x1800a0edc  cmp     eax, esi
0x1800a0ede  jnz     short loc_1800A0EE5
0x1800a0ee0  lea     rcx, [rsp+888h+pszDest]
0x1800a0ee5  call    SendTelemetry
0x1800a0eea  nop
0x1800a0eeb  jmp     loc_18003691D
```
