# GetPropertyGuidFromPropQuery(ushort const *,_GUID *)

- ea: `0x18005abd4`
- end: `0x18005adda`
- name: `?GetPropertyGuidFromPropQuery@@YAJPEBGPEAU_GUID@@@Z`
- size: `518`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18005a724`

## callees

- `0x180008de0`
- `0x18005a298`
- `0x18005abd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18005ac48`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18005ac48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005acb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005acb6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005aca6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005ad74`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005aca6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005ad74`

## pseudocode

```c
__int64 __fastcall GetPropertyGuidFromPropQuery(const unsigned __int16 *a1, struct _GUID *a2)
{
  int v3; // ebx
  wchar_t *lpString2; // rbx
  unsigned __int64 v5; // rax
  int v6; // eax
  signed int LastError; // eax
  const WCHAR *v8; // rbp
  unsigned int i; // esi
  wchar_t *v10; // r10
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  const WCHAR *v13; // r10
  int v14; // eax
  int cchCount2; // [rsp+30h] [rbp-48h] BYREF
  int cchCount1; // [rsp+34h] [rbp-44h] BYREF
  WCHAR String1[8]; // [rsp+38h] [rbp-40h] BYREF

  wcscpy(String1, L"?prop=");
  cchCount1 = 0;
  cchCount2 = 0;
  if ( a1 && a2 )
  {
    lpString2 = wcsstr(a1, L"?");
    if ( !lpString2 )
      return 1;
    v5 = -1;
    do
      ++v5;
    while ( lpString2[v5] );
    if ( v5 <= 6 )
      return (unsigned int)-2147467259;
    v6 = CompareStringW(0x7Fu, 1u, String1, 6, lpString2, 6);
    if ( v6 )
    {
      if ( v6 != 2 )
        return 1;
      v8 = lpString2 + 6;
      if ( lpString2 == (wchar_t *)-12LL )
      {
        return (unsigned int)-2147024882;
      }
      else
      {
        v3 = -2046820333;
        for ( i = 0; i < 9; ++i )
        {
          v10 = (&off_1801563F0)[3 * (int)i];
          if ( !v10 )
            return (unsigned int)-2147024882;
          v11 = -1;
          do
            ++v11;
          while ( v10[v11] );
          v3 = UIntPtrToInt(v11, &cchCount1);
          if ( v3 < 0 )
            break;
          v12 = -1;
          do
            ++v12;
          while ( v8[v12] );
          v3 = UIntPtrToInt(v12, &cchCount2);
          if ( v3 < 0 )
            break;
          v14 = CompareStringW(0x7Fu, 1u, v13, cchCount1, v8, cchCount2);
          if ( !v14 )
            goto LABEL_11;
          if ( v14 == 2 )
          {
            v3 = 0;
            *a2 = *(struct _GUID *)(&off_1801563F0 + 3 * (int)i + 1);
            return (unsigned int)v3;
          }
        }
      }
    }
    else
    {
LABEL_11:
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18005abd4  mov     r11, rsp
0x18005abd7  mov     [r11+18h], rbx
0x18005abdb  mov     [r11+20h], rbp
0x18005abdf  push    rsi
0x18005abe0  push    r12
0x18005abe2  push    r13
0x18005abe4  push    r14
0x18005abe6  push    r15
0x18005abe8  sub     rsp, 50h
0x18005abec  mov     rax, cs:__security_cookie
0x18005abf3  xor     rax, rsp
0x18005abf6  mov     [rsp+78h+var_30], rax
0x18005abfb  mov     eax, dword ptr cs:aProp+8; "p="
0x18005ac01  xor     r12d, r12d
0x18005ac04  movsd   xmm0, qword ptr cs:aProp; "?prop="
0x18005ac0c  mov     r15, rdx
0x18005ac0f  mov     [rsp+78h+var_38], eax
0x18005ac13  movzx   eax, word ptr cs:aProp+0Ch; ""
0x18005ac1a  mov     [rsp+78h+var_34], ax
0x18005ac1f  movsd   qword ptr [rsp+78h+String1], xmm0
0x18005ac25  mov     [r11-44h], r12d
0x18005ac29  mov     [r11-48h], r12d
0x18005ac2d  test    rcx, rcx
0x18005ac30  jnz     short loc_18005AC3C
0x18005ac32  mov     ebx, 80070057h
0x18005ac37  jmp     loc_18005ADB0
0x18005ac3c  test    r15, r15
0x18005ac3f  jz      short loc_18005AC32
0x18005ac41  lea     rdx, SubStr; "?"
0x18005ac48  call    cs:__imp_wcsstr
0x18005ac4f  nop     dword ptr [rax+rax+00h]
0x18005ac54  mov     rbx, rax
0x18005ac57  test    rax, rax
0x18005ac5a  jnz     short loc_18005AC66
0x18005ac5c  mov     ebx, 1
0x18005ac61  jmp     loc_18005ADB0
0x18005ac66  or      r13, 0FFFFFFFFFFFFFFFFh
0x18005ac6a  mov     rax, r13
0x18005ac6d  inc     rax
0x18005ac70  cmp     [rbx+rax*2], r12w
0x18005ac75  jnz     short loc_18005AC6D
0x18005ac77  cmp     rax, 6
0x18005ac7b  ja      short loc_18005AC87
0x18005ac7d  mov     ebx, 80004005h
0x18005ac82  jmp     loc_18005ADB0
0x18005ac87  mov     r9d, 6; cchCount1
0x18005ac8d  mov     [rsp+78h+cchCount2], 6; cchCount2
0x18005ac95  lea     r8, [rsp+78h+String1]; lpString1
0x18005ac9a  mov     [rsp+78h+lpString2], rbx; lpString2
0x18005ac9f  lea     edx, [r9-5]; dwCmpFlags
0x18005aca3  lea     ecx, [rdx+7Eh]; Locale
0x18005aca6  call    cs:__imp_CompareStringW
0x18005acad  nop     dword ptr [rax+rax+00h]
0x18005acb2  test    eax, eax
0x18005acb4  jnz     short loc_18005ACDA
0x18005acb6  call    cs:__imp_GetLastError
0x18005acbd  nop     dword ptr [rax+rax+00h]
0x18005acc2  mov     ebx, eax
0x18005acc4  test    eax, eax
0x18005acc6  jle     loc_18005ADB0
0x18005accc  movzx   ebx, ax
0x18005accf  or      ebx, 80070000h
0x18005acd5  jmp     loc_18005ADB0
0x18005acda  cmp     eax, 2
0x18005acdd  jnz     loc_18005AC5C
0x18005ace3  lea     rbp, [rbx+0Ch]
0x18005ace7  test    rbp, rbp
0x18005acea  jz      loc_18005ADAB
0x18005acf0  mov     ebx, 86000013h
0x18005acf5  mov     esi, r12d
0x18005acf8  lea     rcx, off_1801563F0; "Format"
0x18005acff  cmp     esi, 9
0x18005ad02  jnb     loc_18005ADB0
0x18005ad08  movsxd  rax, esi
0x18005ad0b  lea     r14, [rax+rax*2]
0x18005ad0f  mov     r10, [rcx+r14*8]
0x18005ad13  test    r10, r10
0x18005ad16  jz      loc_18005ADAB
0x18005ad1c  mov     rcx, r13
0x18005ad1f  inc     rcx; unsigned __int64
0x18005ad22  cmp     [r10+rcx*2], r12w
0x18005ad27  jnz     short loc_18005AD1F
0x18005ad29  lea     rdx, [rsp+78h+cchCount1]; int *
0x18005ad2e  call    ?UIntPtrToInt@@YAJ_KPEAH@Z; UIntPtrToInt(unsigned __int64,int *)
0x18005ad33  mov     ebx, eax
0x18005ad35  test    eax, eax
0x18005ad37  js      short loc_18005ADB0
0x18005ad39  mov     rcx, r13
0x18005ad3c  inc     rcx; unsigned __int64
0x18005ad3f  cmp     [rbp+rcx*2+0], r12w
0x18005ad45  jnz     short loc_18005AD3C
0x18005ad47  lea     rdx, [rsp+78h+var_48]; int *
0x18005ad4c  call    ?UIntPtrToInt@@YAJ_KPEAH@Z; UIntPtrToInt(unsigned __int64,int *)
0x18005ad51  mov     ebx, eax
0x18005ad53  test    eax, eax
0x18005ad55  js      short loc_18005ADB0
0x18005ad57  mov     eax, [rsp+78h+var_48]
0x18005ad5b  mov     edx, 1; dwCmpFlags
0x18005ad60  mov     r9d, [rsp+78h+cchCount1]; cchCount1
0x18005ad65  mov     r8, r10; lpString1
0x18005ad68  mov     [rsp+78h+cchCount2], eax; cchCount2
0x18005ad6c  mov     [rsp+78h+lpString2], rbp; lpString2
0x18005ad71  lea     ecx, [rdx+7Eh]; Locale
0x18005ad74  call    cs:__imp_CompareStringW
0x18005ad7b  nop     dword ptr [rax+rax+00h]
0x18005ad80  test    eax, eax
0x18005ad82  jz      loc_18005ACB6
0x18005ad88  cmp     eax, 2
0x18005ad8b  jz      short loc_18005AD94
0x18005ad8d  inc     esi
0x18005ad8f  jmp     loc_18005ACF8
0x18005ad94  lea     rax, off_1801563F0; "Format"
0x18005ad9b  mov     ebx, r12d
0x18005ad9e  movups  xmm0, xmmword ptr [rax+r14*8+8]
0x18005ada4  movdqu  xmmword ptr [r15], xmm0
0x18005ada9  jmp     short loc_18005ADB0
0x18005adab  mov     ebx, 8007000Eh
0x18005adb0  mov     eax, ebx
0x18005adb2  mov     rcx, [rsp+78h+var_30]
0x18005adb7  xor     rcx, rsp; StackCookie
0x18005adba  call    __security_check_cookie
0x18005adbf  lea     r11, [rsp+78h+var_28]
0x18005adc4  mov     rbx, [r11+40h]
0x18005adc8  mov     rbp, [r11+48h]
0x18005adcc  mov     rsp, r11
0x18005adcf  pop     r15
0x18005add1  pop     r14
0x18005add3  pop     r13
0x18005add5  pop     r12
0x18005add7  pop     rsi
0x18005add8  retn
```
