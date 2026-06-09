# IsPublicPhonebook

- ea: `0x180009dd0`
- end: `0x18000a0a2`
- name: `IsPublicPhonebook`
- size: `722`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `13`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000975c`
- `0x1800103d0`
- `0x180012640`
- `0x180029cd0`
- `0x18002c244`
- `0x1800357e8`
- `0x180076bd0`
- `0x180079500`
- `0x1800993e8`
- `0x1800c5760`
- `0x1800c8b44`
- `0x1800c9580`
- `0x1800de184`

## callees

- `0x180009dd0`
- `0x18000a0a8`
- `0x18003e0a8`
- `0x18007e5f0`
- `0x18007efdc`
- `0x1800ded06`
- `0x1800ded50`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180009e36`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180009e36`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180009f61`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180009f61`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180009efe`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180009f33`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180009efe`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180009f33`
- `rtutils!TracePrintfExA` at `0x180009f81`
- `rtutils!TracePrintfExA` at `0x18000a04a`
- `rtutils!TracePrintfExA` at `0x18000a097`
- `rtutils!TracePrintfExA` at `0x180009f81`
- `rtutils!TracePrintfExA` at `0x18000a04a`
- `rtutils!TracePrintfExA` at `0x18000a097`

## string_xrefs

- `0x18000a08b`: `StringCchCopy failed due to error 0x%x`
- `0x18000a03e`: `IsPublicPhonebook: Unable to load pbk path info %x`

## pseudocode

```c
__int64 __fastcall IsPublicPhonebook(wchar_t *a1)
{
  wchar_t *v1; // rbx
  unsigned int v2; // edi
  WCHAR *v3; // rsi
  __int64 v4; // r9
  int v5; // eax
  __int64 v6; // rax
  wchar_t *v7; // r9
  __int64 v8; // r8
  wchar_t *v9; // rcx
  unsigned int v10; // ebx
  int v11; // ebx
  int v12; // edx
  int v13; // ecx
  int v14; // ecx
  const char *v16; // r9
  size_t pcchRemaining; // [rsp+30h] [rbp-268h] BYREF
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+38h] [rbp-260h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-258h] BYREF

  v1 = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v16 = (const char *)a1;
    if ( !a1 )
      v16 = L"<NULL>";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_38cda081c674317ed40163d707084d83_Traceguids, v16);
  }
  memset_0(pszDest, 0, 0x20Au);
  if ( !v1 )
    return 0;
  v2 = 0;
  v3 = (WCHAR *)GlobalAlloc(0x40u, 0x20Au);
  if ( v3 )
  {
    v5 = PbkPathInfoLoad(&g_PbkPathInfo);
    if ( v5 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "IsPublicPhonebook: Unable to load pbk path info %x", v5);
    }
    else
    {
      v6 = 2147483646;
      v7 = pszDest;
      v8 = 261;
      do
      {
        if ( !v6 )
          break;
        if ( !*v1 )
          break;
        *v7++ = *v1++;
        --v6;
        --v8;
      }
      while ( v8 );
      v9 = v7 - 1;
      v10 = v8 == 0 ? 0x8007007A : 0;
      if ( v8 )
        v9 = v7;
      *v9 = 0;
      if ( v8 )
        goto LABEL_12;
      StringExHandleOtherFlagsW(pszDest, 0x20Au, 0, &ppszDestEnd, &pcchRemaining, 0x900u);
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "StringCchCopy failed due to error 0x%x", v10);
      if ( !(_WORD)v10 )
      {
LABEL_12:
        ((void (__fastcall *)(WCHAR *, wchar_t *))qword_1800FF978)(v3, pszDest);
        ((void (__fastcall *)(WCHAR *))qword_1800FF980)(v3);
        v11 = -1;
        v12 = CompareStringW(0x7Fu, 1u, v3, -1, lpString2, -1);
        v13 = -1;
        if ( v12 )
          v13 = v12 - 2;
        if ( v13 )
        {
          v14 = CompareStringW(0x7Fu, 1u, v3, -1, qword_1800FF998, -1);
          v2 = 0;
          if ( v14 )
            v11 = v14 - 2;
          LOBYTE(v2) = v11 == 0;
        }
        else
        {
          v2 = 1;
        }
      }
    }
    GlobalFree(v3);
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "IsPublicPhonebook=%u", v2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(v4) = v2;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_38cda081c674317ed40163d707084d83_Traceguids, v4);
  }
  return v2;
}

```

## disassembly

```asm
0x180009dd0  push    rbx
0x180009dd2  push    rbp
0x180009dd3  push    rsi
0x180009dd4  push    rdi
0x180009dd5  push    r14
0x180009dd7  push    r15
0x180009dd9  sub     rsp, 268h
0x180009de0  mov     rax, cs:__security_cookie
0x180009de7  xor     rax, rsp
0x180009dea  mov     [rsp+298h+var_48], rax
0x180009df2  mov     rbx, rcx
0x180009df5  mov     rcx, cs:WPP_GLOBAL_Control
0x180009dfc  lea     r15, WPP_GLOBAL_Control
0x180009e03  xor     r14d, r14d
0x180009e06  cmp     rcx, r15
0x180009e09  jnz     loc_180009FB5
0x180009e0f  mov     ebp, 20Ah
0x180009e14  lea     rcx, [rsp+298h+pszDest]; void *
0x180009e19  mov     r8d, ebp; Size
0x180009e1c  xor     edx, edx; Val
0x180009e1e  call    memset_0
0x180009e23  test    rbx, rbx
0x180009e26  jz      loc_18000A025
0x180009e2c  mov     edx, ebp; dwBytes
0x180009e2e  mov     ecx, 40h ; '@'; uFlags
0x180009e33  mov     edi, r14d
0x180009e36  call    cs:__imp_GlobalAlloc
0x180009e3c  mov     rsi, rax
0x180009e3f  test    rax, rax
0x180009e42  jz      loc_180009F67
0x180009e48  lea     rcx, g_PbkPathInfo; lpCriticalSection
0x180009e4f  call    PbkPathInfoLoad
0x180009e54  test    eax, eax
0x180009e56  jnz     loc_18000A02C
0x180009e5c  mov     eax, 7FFFFFFEh
0x180009e61  lea     r9, [rsp+298h+pszDest]
0x180009e66  mov     r8d, 105h
0x180009e6c  mov     r15d, 1
0x180009e72  test    rax, rax
0x180009e75  jz      short loc_180009E93
0x180009e77  movzx   ecx, word ptr [rbx]
0x180009e7a  test    cx, cx
0x180009e7d  jz      short loc_180009E93
0x180009e7f  mov     [r9], cx
0x180009e83  add     rbx, 2
0x180009e87  add     r9, 2
0x180009e8b  sub     rax, r15
0x180009e8e  sub     r8, r15; cchOriginalDestLength
0x180009e91  jnz     short loc_180009E72
0x180009e93  mov     rax, r8
0x180009e96  lea     rcx, [r9-2]
0x180009e9a  neg     rax
0x180009e9d  sbb     ebx, ebx
0x180009e9f  not     ebx
0x180009ea1  and     ebx, 8007007Ah
0x180009ea7  test    r8, r8
0x180009eaa  cmovnz  rcx, r9
0x180009eae  mov     [rcx], r14w
0x180009eb2  jz      loc_18000A055
0x180009eb8  mov     rax, cs:qword_1800FF978
0x180009ebf  lea     rdx, [rsp+298h+pszDest]
0x180009ec4  mov     rcx, rsi
0x180009ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ecc  mov     rax, cs:qword_1800FF980
0x180009ed3  mov     rcx, rsi
0x180009ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009edb  mov     rax, cs:lpString2
0x180009ee2  or      ebx, 0FFFFFFFFh
0x180009ee5  mov     edi, 7Fh
0x180009eea  mov     [rsp+298h+cchCount2], ebx; cchCount2
0x180009eee  mov     r9d, ebx; cchCount1
0x180009ef1  mov     [rsp+298h+lpString2], rax; lpString2
0x180009ef6  mov     ecx, edi; Locale
0x180009ef8  mov     r8, rsi; lpString1
0x180009efb  mov     edx, r15d; dwCmpFlags
0x180009efe  call    cs:__imp_CompareStringW
0x180009f04  mov     edx, eax
0x180009f06  mov     ecx, ebx
0x180009f08  add     eax, 0FFFFFFFEh
0x180009f0b  test    edx, edx
0x180009f0d  cmovnz  ecx, eax
0x180009f10  test    ecx, ecx
0x180009f12  jz      loc_18000A01D
0x180009f18  mov     rax, cs:qword_1800FF998
0x180009f1f  mov     r9d, ebx; cchCount1
0x180009f22  mov     [rsp+298h+cchCount2], ebx; cchCount2
0x180009f26  mov     r8, rsi; lpString1
0x180009f29  mov     edx, r15d; dwCmpFlags
0x180009f2c  mov     [rsp+298h+lpString2], rax; lpString2
0x180009f31  mov     ecx, edi; Locale
0x180009f33  call    cs:__imp_CompareStringW
0x180009f39  mov     ecx, eax
0x180009f3b  mov     edi, r14d
0x180009f3e  add     eax, 0FFFFFFFEh
0x180009f41  test    ecx, ecx
0x180009f43  cmovnz  ebx, eax
0x180009f46  test    ebx, ebx
0x180009f48  setz    dil
0x180009f4c  jmp     short loc_180009F57
0x180009f4e  test    bx, bx
0x180009f51  jz      loc_180009EB8
0x180009f57  lea     r15, WPP_GLOBAL_Control
0x180009f5e  mov     rcx, rsi; hMem
0x180009f61  call    cs:__imp_GlobalFree
0x180009f67  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180009f6d  cmp     ecx, 0FFFFFFFFh
0x180009f70  jz      short loc_180009F87
0x180009f72  mov     r9d, edi
0x180009f75  lea     r8, aIspublicphoneb_1; "IsPublicPhonebook=%u"
0x180009f7c  mov     edx, 0Ch; dwFlags
0x180009f81  call    cs:__imp_TracePrintfExA
0x180009f87  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f8e  cmp     rcx, r15
0x180009f91  jnz     short loc_180009FF4
0x180009f93  mov     eax, edi
0x180009f95  mov     rcx, [rsp+298h+var_48]
0x180009f9d  xor     rcx, rsp; StackCookie
0x180009fa0  call    __security_check_cookie
0x180009fa5  add     rsp, 268h
0x180009fac  pop     r15
0x180009fae  pop     r14
0x180009fb0  pop     rdi
0x180009fb1  pop     rsi
0x180009fb2  pop     rbp
0x180009fb3  pop     rbx
0x180009fb4  retn
0x180009fb5  test    byte ptr [rcx+1Ch], 80h
0x180009fb9  jz      loc_180009E0F
0x180009fbf  cmp     byte ptr [rcx+19h], 6
0x180009fc3  jb      loc_180009E0F
0x180009fc9  mov     rcx, [rcx+10h]
0x180009fcd  lea     rax, aNull_3; "<NULL>"
0x180009fd4  test    rbx, rbx
0x180009fd7  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x180009fde  mov     r9, rbx
0x180009fe1  mov     edx, 56h ; 'V'
0x180009fe6  cmovz   r9, rax
0x180009fea  call    WPP_SF_S
0x180009fef  jmp     loc_180009E0F
0x180009ff4  test    byte ptr [rcx+1Ch], 80h
0x180009ff8  jz      short loc_180009F93
0x180009ffa  cmp     byte ptr [rcx+19h], 6
0x180009ffe  jb      short loc_180009F93
0x18000a000  mov     rcx, [rcx+10h]
0x18000a004  lea     r8, WPP_38cda081c674317ed40163d707084d83_Traceguids
0x18000a00b  mov     r9b, dil
0x18000a00e  mov     edx, 57h ; 'W'
0x18000a013  call    WPP_SF_c
0x18000a018  jmp     loc_180009F93
0x18000a01d  mov     edi, r15d
0x18000a020  jmp     loc_180009F57
0x18000a025  xor     eax, eax
0x18000a027  jmp     loc_180009F95
0x18000a02c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000a032  cmp     ecx, 0FFFFFFFFh
0x18000a035  jz      loc_180009F5E
0x18000a03b  mov     r9d, eax
0x18000a03e  lea     r8, aIspublicphoneb_0; "IsPublicPhonebook: Unable to load pbk p"...
0x18000a045  mov     edx, 0Ch; dwFlags
0x18000a04a  call    cs:__imp_TracePrintfExA
0x18000a050  jmp     loc_180009F5E
0x18000a055  lea     rax, [rsp+298h+pcchRemaining]
0x18000a05a  mov     [rsp+298h+cchCount2], 900h; dwFlags
0x18000a062  lea     r9, [rsp+298h+ppszDestEnd]; ppszDestEnd
0x18000a067  mov     [rsp+298h+lpString2], rax; pcchRemaining
0x18000a06c  mov     rdx, rbp; cbDest
0x18000a06f  lea     rcx, [rsp+298h+pszDest]; pszDest
0x18000a074  call    StringExHandleOtherFlagsW
0x18000a079  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000a07f  cmp     ecx, 0FFFFFFFFh
0x18000a082  jz      loc_180009F4E
0x18000a088  mov     r9d, ebx
0x18000a08b  lea     r8, aStringcchcopyF; "StringCchCopy failed due to error 0x%x"
0x18000a092  mov     edx, 0Ch; dwFlags
0x18000a097  call    cs:__imp_TracePrintfExA
0x18000a09d  jmp     loc_180009F4E
```
