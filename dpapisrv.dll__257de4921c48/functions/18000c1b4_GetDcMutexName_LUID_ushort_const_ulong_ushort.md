# GetDcMutexName(_LUID *,ushort const *,ulong,ushort *)

- ea: `0x18000c1b4`
- end: `0x18000c449`
- name: `?GetDcMutexName@@YAKPEAU_LUID@@PEBGKPEAG@Z`
- size: `661`
- prototype: `__int64 __fastcall(struct _LUID *, const unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c010`
- `0x180026434`

## callees

- `0x18000c1b4`
- `0x18000c450`
- `0x18000c4a0`
- `0x18001d810`
- `0x18001eb8c`
- `0x18002317c`
- `0x180023228`
- `0x180023258`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18000c341`
- `ntdll!RtlFreeUnicodeString` at `0x18000c341`
- `ntdll!RtlUpcaseUnicodeString` at `0x18000c22c`
- `ntdll!RtlUpcaseUnicodeString` at `0x18000c22c`
- `ntdll!RtlInitUnicodeString` at `0x18000c213`
- `ntdll!RtlInitUnicodeString` at `0x18000c213`

## string_xrefs

- `0x18000c397`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x18000c3d1`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`

## pseudocode

```c
__int64 __fastcall GetDcMutexName(struct _LUID *a1, const unsigned __int16 *a2, __int64 a3, unsigned __int16 *a4)
{
  __int64 HighPart; // r9
  NTSTATUS v7; // eax
  int v8; // edx
  int v9; // edx
  __int64 v10; // r9
  __int64 v11; // rdx
  const wchar_t *v12; // rcx
  __int64 v13; // rax
  size_t v14; // r8
  size_t v15; // rdx
  size_t *v16; // r8
  size_t v17; // r9
  size_t v18; // r11
  size_t *v19; // r8
  size_t v20; // r9
  size_t v21; // r11
  size_t *v22; // r8
  __int64 v23; // r11
  unsigned int v24; // esi
  __int64 v26; // rcx
  DWORD cchToCopya; // [rsp+20h] [rbp-E0h]
  size_t cchToCopy; // [rsp+20h] [rbp-E0h]
  size_t pcchDestLength; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t v32[48]; // [rsp+70h] [rbp-90h] BYREF
  UCHAR v33[24]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t pszSrc[20]; // [rsp+E8h] [rbp-18h] BYREF

  cchToCopya = a1->LowPart;
  HighPart = (unsigned int)a1->HighPart;
  DestinationString = 0;
  UnicodeString = 0;
  StringCchPrintfW(pszSrc, 0x12u, L"%08x%08x_", HighPart, cchToCopya);
  RtlInitUnicodeString(&DestinationString, a2);
  v7 = RtlUpcaseUnicodeString(&UnicodeString, &DestinationString, 1u);
  if ( v7 < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v8,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"status",
        v7,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp",
        114);
      v26 = WPP_GLOBAL_Control;
    }
    v24 = 13;
    if ( (_UNKNOWN *)v26 != &WPP_GLOBAL_Control && (*(_BYTE *)(v26 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v26 + 16),
        v8,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRetVal",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp",
        116);
  }
  else if ( (unsigned int)FMyPrimitiveSHA((PUCHAR)UnicodeString.Buffer, UnicodeString.Length, v33) )
  {
    v10 = 0;
    do
    {
      v11 = (unsigned int)(2 * v10);
      v12 = (const wchar_t *)(unsigned int)(v11 + 1);
      v13 = v33[v10] & 0xF;
      v14 = (unsigned __int64)v33[v10] >> 4;
      v10 = (unsigned int)(v10 + 1);
      v32[v11] = a0123456789abcd[v13];
      v32[(_QWORD)v12] = a0123456789abcd[v14];
    }
    while ( (unsigned int)v10 < 0x14 );
    v32[40] = 0;
    if ( StringValidateDestW(v12, 0x46u, v14) < 0 )
      *a4 = 0;
    else
      StringCopyWorkerW(a4, v15, v16, L"Local\\DPAPI_", cchToCopy);
    pcchDestLength = 0;
    if ( StringValidateDestAndLengthW(a4, v18, &pcchDestLength, v17) >= 0 )
      StringCopyWorkerW(&a4[pcchDestLength], v21 - pcchDestLength, v19, pszSrc, cchToCopy);
    pcchDestLength = 0;
    if ( StringValidateDestAndLengthW(a4, v21, &pcchDestLength, v20) >= 0 )
      StringCopyWorkerW(&a4[pcchDestLength], v23 - pcchDestLength, v22, v32, cchToCopy);
    v24 = 0;
  }
  else
  {
    v24 = 13;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v9,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"ERROR_INVALID_DATA",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp",
        125);
  }
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  return v24;
}

```

## disassembly

```asm
0x18000c1b4  mov     [rsp-8+arg_10], rbx
0x18000c1b9  push    rbp
0x18000c1ba  push    rsi
0x18000c1bb  push    rdi
0x18000c1bc  lea     rbp, [rsp-20h]
0x18000c1c1  sub     rsp, 120h
0x18000c1c8  mov     rax, cs:__security_cookie
0x18000c1cf  xor     rax, rsp
0x18000c1d2  mov     [rbp+30h+var_20], rax
0x18000c1d6  mov     eax, [rcx]
0x18000c1d8  lea     r8, a08x08x; "%08x%08x_"
0x18000c1df  mov     rdi, r9
0x18000c1e2  mov     dword ptr [rsp+130h+cchToCopy], eax
0x18000c1e6  mov     r9d, [rcx+4]
0x18000c1ea  mov     rbx, rdx
0x18000c1ed  xorps   xmm0, xmm0
0x18000c1f0  lea     rcx, [rbp+30h+pszSrc]; unsigned __int16 *
0x18000c1f4  xorps   xmm1, xmm1
0x18000c1f7  mov     edx, 12h; unsigned __int64
0x18000c1fc  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x18000c201  movups  xmmword ptr [rsp+130h+UnicodeString.Length], xmm1
0x18000c206  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c20b  mov     rdx, rbx; SourceString
0x18000c20e  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x18000c213  call    cs:__imp_RtlInitUnicodeString
0x18000c21a  nop     dword ptr [rax+rax+00h]
0x18000c21f  mov     r8b, 1; AllocateDestinationString
0x18000c222  lea     rdx, [rsp+130h+DestinationString]; SourceString
0x18000c227  lea     rcx, [rsp+130h+UnicodeString]; DestinationString
0x18000c22c  call    cs:__imp_RtlUpcaseUnicodeString
0x18000c233  nop     dword ptr [rax+rax+00h]
0x18000c238  test    eax, eax
0x18000c23a  js      loc_18000C3C3
0x18000c240  movzx   edx, [rsp+130h+UnicodeString.Length]; cbInput
0x18000c245  lea     rax, [rbp+30h+var_60]
0x18000c249  mov     rcx, [rsp+130h+UnicodeString.Buffer]; pbInput
0x18000c24e  mov     [rsp+130h+cchToCopy], rax; PUCHAR
0x18000c253  call    FMyPrimitiveSHA
0x18000c258  test    eax, eax
0x18000c25a  jz      loc_18000C36F
0x18000c260  xor     r9d, r9d
0x18000c263  lea     r10, a0123456789abcd; "0123456789abcdef"
0x18000c26a  movzx   r8d, [rbp+r9+30h+var_60]
0x18000c270  lea     edx, [r9+r9]
0x18000c274  mov     eax, r8d
0x18000c277  lea     ecx, [rdx+1]; pszDest
0x18000c27a  and     eax, 0Fh
0x18000c27d  shr     r8, 4; cchMax
0x18000c281  inc     r9d
0x18000c284  movzx   eax, word ptr [r10+rax*2]
0x18000c289  mov     [rsp+rdx*2+130h+var_C0], ax
0x18000c28e  movzx   eax, word ptr [r10+r8*2]
0x18000c293  mov     [rsp+rcx*2+130h+var_C0], ax
0x18000c298  cmp     r9d, 14h
0x18000c29c  jb      short loc_18000C26A
0x18000c29e  xor     eax, eax
0x18000c2a0  mov     [rbp+30h+var_70], ax
0x18000c2a4  lea     r11d, [rax+46h]
0x18000c2a8  mov     edx, r11d; cchDest
0x18000c2ab  call    StringValidateDestW
0x18000c2b0  test    eax, eax
0x18000c2b2  js      loc_18000C43F
0x18000c2b8  lea     r9, aLocalDpapi; "Local\\DPAPI_"
0x18000c2bf  mov     rcx, rdi; pszDest
0x18000c2c2  call    StringCopyWorkerW
0x18000c2c7  lea     r8, [rsp+130h+pcchDestLength]; pcchDestLength
0x18000c2cc  mov     [rsp+130h+pcchDestLength], 0
0x18000c2d5  mov     rdx, r11; cchDest
0x18000c2d8  mov     rcx, rdi; pszDest
0x18000c2db  call    StringValidateDestAndLengthW
0x18000c2e0  test    eax, eax
0x18000c2e2  js      short loc_18000C2FC
0x18000c2e4  mov     rax, [rsp+130h+pcchDestLength]
0x18000c2e9  lea     r9, [rbp+30h+pszSrc]; pszSrc
0x18000c2ed  mov     rdx, r11
0x18000c2f0  sub     rdx, rax; cchDest
0x18000c2f3  lea     rcx, [rdi+rax*2]; pszDest
0x18000c2f7  call    StringCopyWorkerW
0x18000c2fc  lea     r8, [rsp+130h+pcchDestLength]; pcchDestLength
0x18000c301  mov     [rsp+130h+pcchDestLength], 0
0x18000c30a  mov     rdx, r11; cchDest
0x18000c30d  mov     rcx, rdi; pszDest
0x18000c310  call    StringValidateDestAndLengthW
0x18000c315  test    eax, eax
0x18000c317  js      short loc_18000C332
0x18000c319  mov     rax, [rsp+130h+pcchDestLength]
0x18000c31e  lea     r9, [rsp+130h+var_C0]; pszSrc
0x18000c323  sub     r11, rax
0x18000c326  mov     rdx, r11; cchDest
0x18000c329  lea     rcx, [rdi+rax*2]; pszDest
0x18000c32d  call    StringCopyWorkerW
0x18000c332  xor     esi, esi
0x18000c334  cmp     [rsp+130h+UnicodeString.Buffer], 0
0x18000c33a  jz      short loc_18000C34D
0x18000c33c  lea     rcx, [rsp+130h+UnicodeString]; UnicodeString
0x18000c341  call    cs:__imp_RtlFreeUnicodeString
0x18000c348  nop     dword ptr [rax+rax+00h]
0x18000c34d  mov     eax, esi
0x18000c34f  mov     rcx, [rbp+30h+var_20]
0x18000c353  xor     rcx, rsp; StackCookie
0x18000c356  call    __security_check_cookie
0x18000c35b  mov     rbx, [rsp+130h+arg_10]
0x18000c363  add     rsp, 120h
0x18000c36a  pop     rdi
0x18000c36b  pop     rsi
0x18000c36c  pop     rbp
0x18000c36d  retn
0x18000c36f  mov     eax, 0Dh
0x18000c374  mov     esi, eax
0x18000c376  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c37d  lea     rbx, WPP_GLOBAL_Control
0x18000c384  cmp     rcx, rbx
0x18000c387  jz      short loc_18000C334
0x18000c389  test    byte ptr [rcx+1Ch], 1
0x18000c38d  jz      short loc_18000C334
0x18000c38f  mov     [rsp+130h+var_100], 97Dh
0x18000c397  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000c39e  lea     r9, aErrorInvalidDa; "ERROR_INVALID_DATA"
0x18000c3a5  mov     rcx, [rcx+10h]
0x18000c3a9  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000c3b0  mov     [rsp+130h+var_108], rdi
0x18000c3b5  mov     dword ptr [rsp+130h+cchToCopy], eax
0x18000c3b9  call    WPP_SF_sDsd
0x18000c3be  jmp     loc_18000C334
0x18000c3c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3ca  lea     rbx, WPP_GLOBAL_Control
0x18000c3d1  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000c3d8  cmp     rcx, rbx
0x18000c3db  jz      short loc_18000C3E3
0x18000c3dd  test    byte ptr [rcx+1Ch], 1
0x18000c3e1  jnz     short loc_18000C40E
0x18000c3e3  mov     eax, 0Dh
0x18000c3e8  mov     esi, eax
0x18000c3ea  cmp     rcx, rbx
0x18000c3ed  jz      loc_18000C334
0x18000c3f3  test    byte ptr [rcx+1Ch], 1
0x18000c3f7  jz      loc_18000C334
0x18000c3fd  mov     [rsp+130h+var_100], 974h
0x18000c405  lea     r9, aDwretval; "dwRetVal"
0x18000c40c  jmp     short loc_18000C3A5
0x18000c40e  mov     rcx, [rcx+10h]
0x18000c412  lea     r9, aStatus_0; "status"
0x18000c419  mov     [rsp+130h+var_100], 972h
0x18000c421  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000c428  mov     [rsp+130h+var_108], rdi
0x18000c42d  mov     dword ptr [rsp+130h+cchToCopy], eax
0x18000c431  call    WPP_SF_sDsd
0x18000c436  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c43d  jmp     short loc_18000C3E3
0x18000c43f  xor     eax, eax
0x18000c441  mov     [rdi], ax
0x18000c444  jmp     loc_18000C2C7
```
