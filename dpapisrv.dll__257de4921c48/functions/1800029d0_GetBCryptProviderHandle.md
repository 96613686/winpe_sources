# GetBCryptProviderHandle

- ea: `0x1800029d0`
- end: `0x180002d05`
- name: `GetBCryptProviderHandle`
- size: `821`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `25`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001e60`
- `0x180002310`
- `0x180002480`
- `0x18000ad44`
- `0x180011014`
- `0x180011710`
- `0x18001199c`
- `0x1800146ac`
- `0x180014c80`
- `0x180016370`
- `0x180024f38`
- `0x180028b1c`
- `0x18002fab8`
- `0x18002ffac`
- `0x18003048c`
- `0x1800310e0`
- `0x1800313c8`
- `0x180032084`
- `0x180032218`
- `0x18003325c`
- `0x180033b04`
- `0x18003442c`
- `0x1800349e4`
- `0x180036ac8`
- `0x18003b41c`

## callees

- `0x1800029d0`
- `0x180002d0c`
- `0x18001d810`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002aa7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002cf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002aa7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002cf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002cdb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002cdb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002b01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002b01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002c45`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002bb2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002bb2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180002b2a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180002b2a`
- `bcrypt!BCryptGetProperty` at `0x180002b75`
- `bcrypt!BCryptGetProperty` at `0x180002c1e`
- `bcrypt!BCryptGetProperty` at `0x180002b75`
- `bcrypt!BCryptGetProperty` at `0x180002c1e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180002c34`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180002cc1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180002c34`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180002cc1`

## pseudocode

```c
BCRYPT_ALG_HANDLE __fastcall GetBCryptProviderHandle(unsigned int a1, int *a2, ULONG a3)
{
  char *v3; // rdi
  int *v6; // rsi
  _DWORD *i; // rbx
  const WCHAR *v9; // rax
  NTSTATUS v10; // eax
  BCRYPT_ALG_HANDLE v11; // rbx
  unsigned int v12; // eax
  _DWORD *v13; // rax
  BCRYPT_ALG_HANDLE v14; // rcx
  _DWORD *v15; // rdi
  int v16; // eax
  char *v17; // rsi
  DWORD v18; // ecx
  int v19; // eax
  int v20; // eax
  ULONG pcbResult; // [rsp+30h] [rbp-29h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+38h] [rbp-21h] BYREF
  UCHAR v23[4]; // [rsp+40h] [rbp-19h] BYREF
  int v24; // [rsp+44h] [rbp-15h] BYREF
  __int64 v25; // [rsp+48h] [rbp-11h] BYREF
  unsigned int v26; // [rsp+50h] [rbp-9h]
  int v27; // [rsp+54h] [rbp-5h]
  __int64 v28; // [rsp+58h] [rbp-1h]
  ULONG v29; // [rsp+60h] [rbp+7h]
  int v30; // [rsp+64h] [rbp+Bh]
  UCHAR pbOutput[8]; // [rsp+68h] [rbp+Fh] BYREF
  int v32; // [rsp+70h] [rbp+17h]

  v3 = (char *)g_pBCProvList;
  v30 = 0;
  phAlgorithm = 0;
  v24 = -1;
  if ( !g_pBCProvList )
  {
    SetLastError(0x800C0001);
    return 0;
  }
  v6 = &v24;
  if ( a2 )
    v6 = a2;
  if ( ((a1 - 26113) & 0xFFFFFFFD) == 0 )
    *v6 = -1;
  v27 = *v6;
  v25 = 0;
  v26 = a1;
  v28 = 0;
  v29 = a3;
  if ( *((_DWORD *)v3 + 2) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 16));
    for ( i = *(_DWORD **)v3; i; i = *(_DWORD **)i )
    {
      if ( (*((unsigned int (__fastcall **)(_DWORD *, __int64 *))v3 + 7))(i, &v25) )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 16));
        *v6 = i[3];
        return (BCRYPT_ALG_HANDLE)*((_QWORD *)i + 2);
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 16));
  }
  v9 = TranslateALGIDtoBCrypt(a1);
  v10 = BCryptOpenAlgorithmProvider(&phAlgorithm, v9, L"Microsoft Primitive Provider", a3);
  if ( v10 < 0 )
  {
    v18 = v10 | 0x10000000;
    goto LABEL_25;
  }
  v11 = phAlgorithm;
  *(_QWORD *)pbOutput = 0;
  v32 = 0;
  *(_DWORD *)v23 = 0;
  pcbResult = 0;
  if ( BCryptGetProperty(phAlgorithm, L"KeyLengths", pbOutput, 0xCu, &pcbResult, 0) < 0 || pcbResult < 0xC )
  {
    if ( BCryptGetProperty(v11, L"HashDigestLength", v23, 4u, &pcbResult, 0) < 0 || pcbResult < 4 )
      goto LABEL_24;
    v20 = 8 * *(_DWORD *)v23;
    if ( *v6 == -1 )
    {
      *v6 = v20;
      goto LABEL_19;
    }
    if ( v20 != *v6 )
    {
LABEL_24:
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
      v18 = 50;
LABEL_25:
      SetLastError(v18);
      return 0;
    }
  }
  else
  {
    v12 = *v6;
    if ( *v6 != -1 )
    {
      if ( *(_DWORD *)pbOutput <= v12 && *(_DWORD *)&pbOutput[4] >= v12 )
        goto LABEL_19;
      goto LABEL_24;
    }
    v19 = *(_DWORD *)&pbOutput[4];
    if ( a1 == 26625 && *(_DWORD *)&pbOutput[4] > 0x80u )
      v19 = 128;
    *v6 = v19;
  }
LABEL_19:
  v13 = LocalAlloc(0x40u, 0x20u);
  v14 = phAlgorithm;
  v15 = v13;
  if ( !v13 )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    v18 = 8;
    goto LABEL_25;
  }
  v16 = *v6;
  v17 = (char *)g_pBCProvList;
  *(_QWORD *)v15 = 0;
  v15[2] = a1;
  v15[3] = v16;
  *((_QWORD *)v15 + 2) = v14;
  v15[6] = a3;
  if ( *((_DWORD *)v17 + 2) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 16));
    *(_QWORD *)v15 = *(_QWORD *)v17;
    *(_QWORD *)v17 = v15;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 16));
  }
  return phAlgorithm;
}

```

## disassembly

```asm
0x1800029d0  push    rbp
0x1800029d2  push    rdi
0x1800029d3  push    r12
0x1800029d5  push    r13
0x1800029d7  push    r15
0x1800029d9  lea     rbp, [rsp-37h]
0x1800029de  sub     rsp, 90h
0x1800029e5  mov     rax, cs:__security_cookie
0x1800029ec  xor     rax, rsp
0x1800029ef  mov     [rbp+57h+var_38], rax
0x1800029f3  mov     rdi, cs:?g_pBCProvList@@3PEAVCBCryptProvList@@EA; CBCryptProvList * g_pBCProvList
0x1800029fa  xor     r13d, r13d
0x1800029fd  mov     [rbp+57h+var_4C], r13d
0x180002a01  mov     r12d, r8d
0x180002a04  mov     [rbp+57h+phAlgorithm], r13
0x180002a08  mov     r15d, ecx
0x180002a0b  mov     [rbp+57h+var_6C], 0FFFFFFFFh
0x180002a12  test    rdi, rdi
0x180002a15  jz      loc_180002AFC
0x180002a1b  mov     [rsp+0B0h+var_28], rsi
0x180002a23  lea     eax, [rcx-6601h]
0x180002a29  test    rdx, rdx
0x180002a2c  lea     rsi, [rbp+57h+var_6C]
0x180002a30  cmovnz  rsi, rdx
0x180002a34  test    eax, 0FFFFFFFDh
0x180002a39  jz      loc_180002AF1
0x180002a3f  mov     eax, [rsi]
0x180002a41  mov     [rsp+0B0h+arg_18], rbx
0x180002a49  mov     [rsp+0B0h+var_30], r14
0x180002a51  mov     [rbp+57h+var_5C], eax
0x180002a54  mov     [rbp+57h+var_68], r13
0x180002a58  mov     [rbp+57h+var_60], r15d
0x180002a5c  mov     [rbp+57h+var_58], r13
0x180002a60  mov     [rbp+57h+var_50], r12d
0x180002a64  cmp     [rdi+8], r13d
0x180002a68  jz      loc_180002B11
0x180002a6e  lea     rcx, [rdi+10h]; lpCriticalSection
0x180002a72  call    cs:__imp_EnterCriticalSection
0x180002a79  nop     dword ptr [rax+rax+00h]
0x180002a7e  mov     rbx, [rdi]
0x180002a81  test    rbx, rbx
0x180002a84  jz      loc_180002C89
0x180002a8a  mov     rax, [rdi+38h]
0x180002a8e  lea     rdx, [rbp+57h+var_68]
0x180002a92  mov     rcx, rbx
0x180002a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a9a  test    eax, eax
0x180002a9c  jnz     short loc_180002AA3
0x180002a9e  mov     rbx, [rbx]
0x180002aa1  jmp     short loc_180002A81
0x180002aa3  lea     rcx, [rdi+10h]; lpCriticalSection
0x180002aa7  call    cs:__imp_LeaveCriticalSection
0x180002aae  nop     dword ptr [rax+rax+00h]
0x180002ab3  mov     ecx, [rbx+0Ch]
0x180002ab6  mov     [rsi], ecx
0x180002ab8  mov     rax, [rbx+10h]
0x180002abc  mov     rbx, [rsp+0B0h+arg_18]
0x180002ac4  mov     r14, [rsp+0B0h+var_30]
0x180002acc  mov     rsi, [rsp+0B0h+var_28]
0x180002ad4  mov     rcx, [rbp+57h+var_38]
0x180002ad8  xor     rcx, rsp; StackCookie
0x180002adb  call    __security_check_cookie
0x180002ae0  add     rsp, 90h
0x180002ae7  pop     r15
0x180002ae9  pop     r13
0x180002aeb  pop     r12
0x180002aed  pop     rdi
0x180002aee  pop     rbp
0x180002aef  retn
0x180002af1  mov     dword ptr [rsi], 0FFFFFFFFh
0x180002af7  jmp     loc_180002A3F
0x180002afc  mov     ecx, 800C0001h; dwErrCode
0x180002b01  call    cs:__imp_SetLastError
0x180002b08  nop     dword ptr [rax+rax+00h]
0x180002b0d  xor     eax, eax
0x180002b0f  jmp     short loc_180002AD4
0x180002b11  mov     ecx, r15d; unsigned int
0x180002b14  call    ?TranslateALGIDtoBCrypt@@YAPEBGI@Z; TranslateALGIDtoBCrypt(uint)
0x180002b19  mov     rdx, rax; pszAlgId
0x180002b1c  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x180002b20  mov     r9d, r12d; dwFlags
0x180002b23  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180002b2a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180002b31  nop     dword ptr [rax+rax+00h]
0x180002b36  test    eax, eax
0x180002b38  js      loc_180002C9E
0x180002b3e  mov     rbx, [rbp+57h+phAlgorithm]
0x180002b42  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x180002b46  xor     eax, eax
0x180002b48  mov     [rsp+0B0h+dwFlags], r13d; dwFlags
0x180002b4d  mov     qword ptr [rbp+57h+pbOutput], rax
0x180002b51  lea     rdx, aKeylengths; "KeyLengths"
0x180002b58  mov     [rbp+57h+var_40], eax
0x180002b5b  mov     r9d, 0Ch; cbOutput
0x180002b61  lea     rax, [rbp+57h+var_80]
0x180002b65  mov     dword ptr [rbp+57h+var_70], r13d
0x180002b69  mov     rcx, rbx; hObject
0x180002b6c  mov     [rsp+0B0h+pcbResult], rax; pcbResult
0x180002b71  mov     [rbp+57h+var_80], r13d
0x180002b75  call    cs:__imp_BCryptGetProperty
0x180002b7c  nop     dword ptr [rax+rax+00h]
0x180002b81  test    eax, eax
0x180002b83  js      short loc_180002BFC
0x180002b85  cmp     [rbp+57h+var_80], 0Ch
0x180002b89  jb      short loc_180002BFC
0x180002b8b  mov     eax, [rsi]
0x180002b8d  cmp     eax, 0FFFFFFFFh
0x180002b90  jz      loc_180002C58
0x180002b96  cmp     dword ptr [rbp+57h+pbOutput], eax
0x180002b99  ja      loc_180002C2E
0x180002b9f  cmp     dword ptr [rbp+57h+pbOutput+4], eax
0x180002ba2  jb      loc_180002C2E
0x180002ba8  mov     edx, 20h ; ' '; uBytes
0x180002bad  mov     ecx, 40h ; '@'; uFlags
0x180002bb2  call    cs:__imp_LocalAlloc
0x180002bb9  nop     dword ptr [rax+rax+00h]
0x180002bbe  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180002bc2  mov     rdi, rax
0x180002bc5  test    rax, rax
0x180002bc8  jz      loc_180002CBF
0x180002bce  mov     eax, [rsi]
0x180002bd0  mov     rsi, cs:?g_pBCProvList@@3PEAVCBCryptProvList@@EA; CBCryptProvList * g_pBCProvList
0x180002bd7  mov     [rdi], r13
0x180002bda  mov     [rdi+8], r15d
0x180002bde  mov     [rdi+0Ch], eax
0x180002be1  mov     [rdi+10h], rcx
0x180002be5  mov     [rdi+18h], r12d
0x180002be9  cmp     [rsi+8], r13d
0x180002bed  jnz     loc_180002CD7
0x180002bf3  mov     rax, [rbp+57h+phAlgorithm]
0x180002bf7  jmp     loc_180002ABC
0x180002bfc  lea     rax, [rbp+57h+var_80]
0x180002c00  mov     [rsp+0B0h+dwFlags], r13d; dwFlags
0x180002c05  mov     r9d, 4; cbOutput
0x180002c0b  mov     [rsp+0B0h+pcbResult], rax; pcbResult
0x180002c10  lea     r8, [rbp+57h+var_70]; pbOutput
0x180002c14  mov     rcx, rbx; hObject
0x180002c17  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180002c1e  call    cs:__imp_BCryptGetProperty
0x180002c25  nop     dword ptr [rax+rax+00h]
0x180002c2a  test    eax, eax
0x180002c2c  jns     short loc_180002C6B
0x180002c2e  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180002c32  xor     edx, edx; dwFlags
0x180002c34  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180002c3b  nop     dword ptr [rax+rax+00h]
0x180002c40  mov     ecx, 32h ; '2'; dwErrCode
0x180002c45  call    cs:__imp_SetLastError
0x180002c4c  nop     dword ptr [rax+rax+00h]
0x180002c51  xor     eax, eax
0x180002c53  jmp     loc_180002ABC
0x180002c58  mov     eax, dword ptr [rbp+57h+pbOutput+4]
0x180002c5b  cmp     r15d, 6801h
0x180002c62  jz      short loc_180002CA6
0x180002c64  mov     [rsi], eax
0x180002c66  jmp     loc_180002BA8
0x180002c6b  cmp     [rbp+57h+var_80], 4
0x180002c6f  jb      short loc_180002C2E
0x180002c71  mov     eax, dword ptr [rbp+57h+var_70]
0x180002c74  mov     ecx, [rsi]
0x180002c76  lea     eax, ds:0[rax*8]
0x180002c7d  cmp     ecx, 0FFFFFFFFh
0x180002c80  jnz     short loc_180002CB2
0x180002c82  mov     [rsi], eax
0x180002c84  jmp     loc_180002BA8
0x180002c89  lea     rcx, [rdi+10h]; lpCriticalSection
0x180002c8d  call    cs:__imp_LeaveCriticalSection
0x180002c94  nop     dword ptr [rax+rax+00h]
0x180002c99  jmp     loc_180002B11
0x180002c9e  bts     eax, 1Ch
0x180002ca2  mov     ecx, eax
0x180002ca4  jmp     short loc_180002C45
0x180002ca6  mov     ecx, 80h
0x180002cab  cmp     eax, ecx
0x180002cad  cmova   eax, ecx
0x180002cb0  jmp     short loc_180002C64
0x180002cb2  cmp     eax, ecx
0x180002cb4  jnz     loc_180002C2E
0x180002cba  jmp     loc_180002BA8
0x180002cbf  xor     edx, edx; dwFlags
0x180002cc1  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180002cc8  nop     dword ptr [rax+rax+00h]
0x180002ccd  mov     ecx, 8
0x180002cd2  jmp     loc_180002C45
0x180002cd7  lea     rcx, [rsi+10h]; lpCriticalSection
0x180002cdb  call    cs:__imp_EnterCriticalSection
0x180002ce2  nop     dword ptr [rax+rax+00h]
0x180002ce7  mov     rax, [rsi]
0x180002cea  lea     rcx, [rsi+10h]; lpCriticalSection
0x180002cee  mov     [rdi], rax
0x180002cf1  mov     [rsi], rdi
0x180002cf4  call    cs:__imp_LeaveCriticalSection
0x180002cfb  nop     dword ptr [rax+rax+00h]
0x180002d00  jmp     loc_180002BF3
```
