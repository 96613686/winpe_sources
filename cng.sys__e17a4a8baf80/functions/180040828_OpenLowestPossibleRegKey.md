# OpenLowestPossibleRegKey

- ea: `0x180040828`
- end: `0x180040b09`
- name: `OpenLowestPossibleRegKey`
- size: `737`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004f310`
- `0x180051e24`

## callees

- `0x18000e090`
- `0x180010590`
- `0x180040828`
- `0x180040b10`
- `0x180050d34`
- `0x180051fa4`
- `0x1800a4260`

## import_xrefs

- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180040abc`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180040abc`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180040af3`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180040af3`
- `ntoskrnl!wcsrchr` at `0x180040a2b`
- `ntoskrnl!wcsrchr` at `0x180040a2b`

## string_xrefs

- `0x180040945`: `OpenLowestPossibleRegKey:: StringCchCopyW failed: %ld`
- `0x1800a7c3c`: `OpenLowestPossibleRegKey:: StringCchLengthW failed: %ld`
- `0x180040a9c`: `OpenLowestPossibleRegKey:: pRegKeyNotifyRoot == nullptr`
- `0x1800a7c73`: `OpenLowestPossibleRegKey:: StringCchLengthW failed`
- `0x180040ad0`: `OpenLowestPossibleRegKey:: wcsrchr returned NULL`
- `0x1800409be`: `OpenLowestPossibleRegKey:: StringCchCopyW failed`
- `0x1800a7c19`: `OpenLowestPossibleRegKey:: Reached notify limit`
- `0x1800a7be3`: `OpenLowestPossibleRegKey:: Reached notify limit: %s`

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
  v5 = off_1800ACDE0[2 * a2];
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
  v14 = off_1800ACDE0[v3];
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
      v27 = *(unsigned __int16 *)((char *)v26 + (char *)off_1800ACDE0[v3 + 1] - (char *)v11);
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
              off_1800ACDE0[v3 + 1]);
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
0x180040828  mov     [rsp+arg_10], rbx
0x18004082d  push    rbp
0x18004082e  push    rsi
0x18004082f  push    rdi
0x180040830  push    r12
0x180040832  push    r13
0x180040834  push    r14
0x180040836  push    r15
0x180040838  sub     rsp, 850h
0x18004083f  mov     rax, cs:__security_cookie
0x180040846  xor     rax, rsp
0x180040849  mov     [rsp+888h+var_48], rax
0x180040851  xor     ebp, ebp
0x180040853  mov     r14, rcx
0x180040856  test    rcx, rcx
0x180040859  jz      loc_180040A9C
0x18004085f  mov     r12d, edx
0x180040862  lea     rax, off_1800ACDE0; "Software\\Policies\\Microsoft\\Cryptogr"...
0x180040869  add     r12, r12
0x18004086c  mov     r15d, edx
0x18004086f  mov     rax, [rax+r12*8]
0x180040873  test    rax, rax
0x180040876  jz      loc_1800409CB
0x18004087c  mov     r13d, 7FFFFFFFh
0x180040882  mov     r8d, r13d
0x180040885  cmp     [rax], bp
0x180040888  jz      short loc_180040894
0x18004088a  add     rax, 2
0x18004088e  sub     r8, 1
0x180040892  jnz     short loc_180040885
0x180040894  mov     rax, r8
0x180040897  mov     ebx, 80070057h
0x18004089c  neg     rax
0x18004089f  mov     rcx, r13
0x1800408a2  mov     rax, r8
0x1800408a5  sbb     edx, edx
0x1800408a7  sub     rcx, r8
0x1800408aa  not     edx
0x1800408ac  and     edx, ebx
0x1800408ae  neg     rax
0x1800408b1  sbb     rsi, rsi
0x1800408b4  and     rsi, rcx
0x1800408b7  test    r8, r8
0x1800408ba  jz      loc_1800A7C38
0x1800408c0  lea     rcx, ds:2[rsi*2]
0x1800408c8  call    MSCryptAlloc
0x1800408cd  mov     rdi, rax
0x1800408d0  test    rax, rax
0x1800408d3  jz      loc_180040AB2
0x1800408d9  lea     rdx, [rsi+1]
0x1800408dd  lea     esi, [rbx+23h]
0x1800408e0  test    rdx, rdx
0x1800408e3  jz      short loc_180040945
0x1800408e5  cmp     rdx, r13
0x1800408e8  ja      loc_180040B01
0x1800408ee  lea     rcx, off_1800ACDE0; "Software\\Policies\\Microsoft\\Cryptogr"...
0x1800408f5  mov     eax, 7FFFFFFEh
0x1800408fa  mov     rcx, [rcx+r12*8]
0x1800408fe  mov     r8, rdi
0x180040901  test    rax, rax
0x180040904  jz      short loc_180040925
0x180040906  movzx   r9d, word ptr [rcx]
0x18004090a  test    r9w, r9w
0x18004090e  jz      short loc_180040925
0x180040910  mov     [r8], r9w
0x180040914  add     rcx, 2
0x180040918  add     r8, 2
0x18004091c  dec     rax
0x18004091f  sub     rdx, 1
0x180040923  jnz     short loc_180040901
0x180040925  mov     rax, rdx
0x180040928  lea     rcx, [r8-2]
0x18004092c  neg     rax
0x18004092f  sbb     ebx, ebx
0x180040931  not     ebx
0x180040933  and     ebx, esi
0x180040935  test    rdx, rdx
0x180040938  cmovnz  rcx, r8
0x18004093c  mov     [rcx], bp
0x18004093f  jnz     loc_1800409D5
0x180040945  lea     rax, aOpenlowestposs_1; "OpenLowestPossibleRegKey:: StringCchCop"...
0x18004094c  mov     dword ptr [rsp+888h+var_858], ebx
0x180040950  mov     [rsp+888h+var_860], rax; unsigned __int16 *
0x180040955  lea     rcx, [rsp+888h+pszDest]; pszDest
0x18004095a  xor     r9d, r9d; unsigned __int64 *
0x18004095d  mov     qword ptr [rsp+888h+var_868], rbp; unsigned int
0x180040962  xor     r8d, r8d; unsigned __int16 **
0x180040965  mov     edx, 400h; unsigned __int64
0x18004096a  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18004096f  mov     edx, 80000000h
0x180040974  lea     ecx, [rax+rdx]
0x180040977  test    edx, ecx
0x180040979  jz      short loc_1800409BE
0x18004097b  lea     rcx, [rsp+888h+pszDest]
0x180040980  call    SendTelemetry
0x180040985  mov     rcx, rdi; P
0x180040988  call    MSCryptFree
0x18004098d  mov     eax, 0Dh
0x180040992  mov     rcx, [rsp+888h+var_48]
0x18004099a  xor     rcx, rsp; StackCookie
0x18004099d  call    __security_check_cookie
0x1800409a2  mov     rbx, [rsp+888h+arg_10]
0x1800409aa  add     rsp, 850h
0x1800409b1  pop     r15
0x1800409b3  pop     r14
0x1800409b5  pop     r13
0x1800409b7  pop     r12
0x1800409b9  pop     rdi
0x1800409ba  pop     rsi
0x1800409bb  pop     rbp
0x1800409bc  retn
0x1800409be  lea     rcx, aOpenlowestposs_2; "OpenLowestPossibleRegKey:: StringCchCop"...
0x1800409c5  cmp     eax, esi
0x1800409c7  jz      short loc_18004097B
0x1800409c9  jmp     short loc_180040980
0x1800409cb  mov     edx, 80070057h
0x1800409d0  jmp     loc_1800A7C38
0x1800409d5  mov     rcx, [r14+58h]
0x1800409d9  mov     r13, rbp
0x1800409dc  test    rcx, rcx
0x1800409df  jnz     loc_180040ABC
0x1800409e5  mov     rcx, [r14]
0x1800409e8  shl     r15, 5
0x1800409ec  mov     rbp, r15
0x1800409ef  mov     dword ptr [rcx+r15+18h], 1
0x1800409f8  mov     r9, [r14]
0x1800409fb  mov     r8d, 10h
0x180040a01  add     r9, r15
0x180040a04  mov     rdx, rdi
0x180040a07  mov     rcx, 0FFFFFFFF80000002h
0x180040a0e  call    KeRegOpenKey
0x180040a13  mov     ebx, eax
0x180040a15  cmp     eax, 2
0x180040a18  jnz     short loc_180040A82
0x180040a1a  mov     rax, [r14]
0x180040a1d  lea     edx, [rbx+5Ah]; Ch
0x180040a20  mov     rcx, rdi; Str
0x180040a23  mov     dword ptr [rax+rbp+18h], 0
0x180040a2b  call    cs:__imp_wcsrchr
0x180040a32  nop     dword ptr [rax+rax+00h]
0x180040a37  mov     r9, rax
0x180040a3a  test    rax, rax
0x180040a3d  jz      loc_180040AD0
0x180040a43  lea     rax, off_1800ACDE0; "Software\\Policies\\Microsoft\\Cryptogr"...
0x180040a4a  mov     rcx, rdi
0x180040a4d  mov     r10, [rax+r12*8+8]
0x180040a52  mov     r8, r10
0x180040a55  sub     r8, rdi
0x180040a58  movzx   edx, word ptr [rcx]
0x180040a5b  movzx   eax, word ptr [rcx+r8]
0x180040a60  sub     edx, eax
0x180040a62  jnz     short loc_180040A6C
0x180040a64  add     rcx, 2
0x180040a68  test    eax, eax
0x180040a6a  jnz     short loc_180040A58
0x180040a6c  test    edx, edx
0x180040a6e  jz      loc_1800A7BDE
0x180040a74  xor     eax, eax
0x180040a76  mov     r15, rbp
0x180040a79  mov     [r9], ax
0x180040a7d  jmp     loc_1800409F8
0x180040a82  test    eax, eax
0x180040a84  jnz     short loc_180040AE3
0x180040a86  cmp     qword ptr [r14+58h], 0
0x180040a8b  jnz     short loc_180040AF0
0x180040a8d  mov     rcx, rdi; P
0x180040a90  call    MSCryptFree
0x180040a95  mov     eax, ebx
0x180040a97  jmp     loc_180040992
0x180040a9c  lea     rcx, aOpenlowestposs_0; "OpenLowestPossibleRegKey:: pRegKeyNotif"...
0x180040aa3  call    SendTelemetry
0x180040aa8  mov     eax, 6
0x180040aad  jmp     loc_180040992
0x180040ab2  mov     eax, 8
0x180040ab7  jmp     loc_180040992
0x180040abc  call    cs:__imp_PsAttachSiloToCurrentThread
0x180040ac3  nop     dword ptr [rax+rax+00h]
0x180040ac8  mov     r13, rax
0x180040acb  jmp     loc_1800409E5
0x180040ad0  lea     rcx, aOpenlowestposs_4; "OpenLowestPossibleRegKey:: wcsrchr retu"...
0x180040ad7  call    SendTelemetry
0x180040adc  mov     ebx, 0Dh
0x180040ae1  jmp     short loc_180040A86
0x180040ae3  mov     rax, [r14]
0x180040ae6  mov     dword ptr [rax+rbp+18h], 0
0x180040aee  jmp     short loc_180040A86
0x180040af0  mov     rcx, r13
0x180040af3  call    cs:__imp_PsDetachSiloFromCurrentThread
0x180040afa  nop     dword ptr [rax+rax+00h]
0x180040aff  jmp     short loc_180040A8D
0x180040b01  mov     [rax], bp
0x180040b04  jmp     loc_180040945
0x1800a7bde  mov     [rsp+888h+var_858], r10
0x1800a7be3  lea     rax, aOpenlowestposs_6; "OpenLowestPossibleRegKey:: Reached noti"...
0x1800a7bea  mov     [rsp+888h+var_860], rax; unsigned __int16 *
0x1800a7bef  lea     rcx, [rsp+888h+pszDest]; pszDest
0x1800a7bf4  xor     r9d, r9d; unsigned __int64 *
0x1800a7bf7  mov     qword ptr [rsp+888h+var_868], 0; unsigned int
0x1800a7c00  xor     r8d, r8d; unsigned __int16 **
0x1800a7c03  mov     edx, 400h; unsigned __int64
0x1800a7c08  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800a7c0d  mov     edx, 80000000h
0x1800a7c12  lea     ecx, [rax+rdx]
0x1800a7c15  test    edx, ecx
0x1800a7c17  jnz     short loc_1800A7C24
0x1800a7c19  lea     rcx, aOpenlowestposs_5; "OpenLowestPossibleRegKey:: Reached noti"...
0x1800a7c20  cmp     eax, esi
0x1800a7c22  jnz     short loc_1800A7C29
0x1800a7c24  lea     rcx, [rsp+888h+pszDest]
0x1800a7c29  call    SendTelemetry
0x1800a7c2e  mov     ebx, 12h
0x1800a7c33  jmp     loc_180040A86
0x1800a7c38  mov     dword ptr [rsp+888h+var_858], edx
0x1800a7c3c  lea     rax, aOpenlowestposs_3; "OpenLowestPossibleRegKey:: StringCchLen"...
0x1800a7c43  mov     [rsp+888h+var_860], rax; unsigned __int16 *
0x1800a7c48  lea     rcx, [rsp+888h+pszDest]; pszDest
0x1800a7c4d  xor     r9d, r9d; unsigned __int64 *
0x1800a7c50  mov     qword ptr [rsp+888h+var_868], rbp; unsigned int
0x1800a7c55  xor     r8d, r8d; unsigned __int16 **
0x1800a7c58  mov     edx, 400h; unsigned __int64
0x1800a7c5d  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800a7c62  mov     edx, 80000000h
0x1800a7c67  lea     ecx, [rax+rdx]
0x1800a7c6a  test    edx, ecx
0x1800a7c6c  jnz     short loc_1800A7C7E
0x1800a7c6e  mov     esi, 8007007Ah
0x1800a7c73  lea     rcx, aOpenlowestposs; "OpenLowestPossibleRegKey:: StringCchLen"...
0x1800a7c7a  cmp     eax, esi
0x1800a7c7c  jnz     short loc_1800A7C83
0x1800a7c7e  lea     rcx, [rsp+888h+pszDest]
0x1800a7c83  call    SendTelemetry
0x1800a7c88  nop
0x1800a7c89  jmp     loc_18004098D
```
