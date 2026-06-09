# RtlpQueryNlsSystemCodePages

- ea: `0x1800533cc`
- end: `0x180053633`
- name: `RtlpQueryNlsSystemCodePages`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180052ce4`

## callees

- `0x18000aab0`
- `0x1800533cc`
- `0x18012d320`
- `0x18015ecc0`
- `0x18015ed20`
- `0x18015edc0`
- `0x180162810`

## string_xrefs

- `0x180053409`: `\Registry\Machine\System\CurrentControlSet\Control\Nls\CodePage`

## pseudocode

```c
__int64 __fastcall RtlpQueryNlsSystemCodePages(_DWORD *a1, _DWORD *a2)
{
  size_t v4; // rax
  size_t v5; // rax
  int v6; // ebx
  size_t v7; // rax
  size_t v8; // rax
  size_t v9; // rax
  int v11; // [rsp+30h] [rbp-69h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-61h] BYREF
  __int64 v13; // [rsp+40h] [rbp-59h] BYREF
  const wchar_t *v14; // [rsp+48h] [rbp-51h]
  __int16 v15; // [rsp+50h] [rbp-49h] BYREF
  __int16 v16; // [rsp+52h] [rbp-47h]
  int v17; // [rsp+54h] [rbp-45h]
  wchar_t *v18; // [rsp+58h] [rbp-41h]
  _QWORD v19[2]; // [rsp+60h] [rbp-39h] BYREF
  _DWORD v20[2]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v21; // [rsp+78h] [rbp-21h]
  _QWORD *v22; // [rsp+80h] [rbp-19h]
  int v23; // [rsp+88h] [rbp-11h]
  int v24; // [rsp+8Ch] [rbp-Dh]
  __int128 v25; // [rsp+90h] [rbp-9h]
  _BYTE v26[4]; // [rsp+A0h] [rbp+7h] BYREF
  int v27; // [rsp+A4h] [rbp+Bh]
  wchar_t String[11]; // [rsp+ACh] [rbp+13h] BYREF
  __int16 v29; // [rsp+C2h] [rbp+29h]

  *a1 = 65001;
  *a2 = 65001;
  v11 = 0;
  Handle = 0;
  v22 = 0;
  v19[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Nls\\CodePage";
  v24 = 0;
  v19[0] = 0;
  v20[1] = 0;
  v4 = 2 * wcslen(L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Nls\\CodePage");
  v20[0] = 48;
  v21 = 0;
  v23 = 576;
  v25 = 0;
  if ( v4 >= 0xFFFE )
    LOWORD(v4) = -4;
  LOWORD(v19[0]) = v4;
  WORD1(v19[0]) = v4 + 2;
  v22 = v19;
  if ( (int)NtOpenKey(&Handle, 0x80000000LL, v20) < 0 )
    goto LABEL_20;
  v13 = 0;
  v14 = L"ACP";
  v5 = 2 * wcslen(L"ACP");
  if ( v5 >= 0xFFFE )
    LOWORD(v5) = -4;
  LOWORD(v13) = v5;
  WORD1(v13) = v5 + 2;
  v6 = NtQueryValueKey(Handle, &v13, 2, v26, 36, &v11);
  if ( v6 >= 0 )
  {
    if ( v27 != 1 )
      goto LABEL_11;
    v29 = 0;
    v17 = 0;
    v18 = String;
    v7 = 2 * wcslen(String);
    if ( v7 >= 0xFFFE )
      LOWORD(v7) = -4;
    v15 = v7;
    v16 = v7 + 2;
    v6 = RtlUnicodeStringToInteger(&v15, 10, a1);
    if ( v6 >= 0 )
    {
LABEL_11:
      v13 = 0;
      v14 = L"OEMCP";
      v8 = 2 * wcslen(L"OEMCP");
      if ( v8 >= 0xFFFE )
        LOWORD(v8) = -4;
      LOWORD(v13) = v8;
      WORD1(v13) = v8 + 2;
      v6 = NtQueryValueKey(Handle, &v13, 2, v26, 36, &v11);
      if ( v6 >= 0 && v27 == 1 )
      {
        v29 = 0;
        v17 = 0;
        v18 = String;
        v9 = 2 * wcslen(String);
        if ( v9 >= 0xFFFE )
          LOWORD(v9) = -4;
        v15 = v9;
        v16 = v9 + 2;
        v6 = RtlUnicodeStringToInteger(&v15, 10, a2);
      }
    }
  }
  NtClose(Handle);
  if ( v6 < 0 )
  {
LABEL_20:
    *a1 = 65001;
    *a2 = 65001;
  }
  return 0;
}

```

## disassembly

```asm
0x1800533cc  mov     [rsp-8+arg_10], rbx
0x1800533d1  push    rbp
0x1800533d2  push    rsi
0x1800533d3  push    rdi
0x1800533d4  push    r13
0x1800533d6  push    r15
0x1800533d8  lea     rbp, [rsp-37h]
0x1800533dd  sub     rsp, 0D0h
0x1800533e4  mov     rax, cs:__security_cookie
0x1800533eb  xor     rax, rsp
0x1800533ee  mov     [rbp+57h+var_28], rax
0x1800533f2  xorps   xmm0, xmm0
0x1800533f5  mov     dword ptr [rcx], 0FDE9h
0x1800533fb  xor     eax, eax
0x1800533fd  mov     dword ptr [rdx], 0FDE9h
0x180053403  mov     rsi, rcx
0x180053406  mov     [rbp+57h+var_C0], eax
0x180053409  lea     rcx, aRegistryMachin_13; "\\Registry\\Machine\\System\\CurrentCon"...
0x180053410  mov     [rbp+57h+Handle], rax
0x180053414  movups  [rbp+57h+var_70], xmm0
0x180053418  mov     [rbp+57h+var_88], rcx
0x18005341c  mov     rdi, rdx
0x18005341f  movups  [rbp+57h+var_70+0Ch], xmm0
0x180053423  mov     [rbp+57h+var_90], rax
0x180053427  movups  [rbp+57h+var_80], xmm0
0x18005342b  call    wcslen
0x180053430  add     rax, rax
0x180053433  mov     dword ptr [rbp+57h+var_80], 30h ; '0'
0x18005343a  mov     ebx, 0FFFCh
0x18005343f  mov     qword ptr [rbp+57h+var_80+8], 0
0x180053447  xorps   xmm0, xmm0
0x18005344a  mov     dword ptr [rbp+57h+var_70+8], 240h
0x180053451  mov     r15d, 2
0x180053457  lea     r8, [rbp+57h+var_80]
0x18005345b  mov     edx, 80000000h
0x180053460  lea     rcx, [rbp+57h+Handle]
0x180053464  lea     r13d, [rbx+2]
0x180053468  cmp     rax, r13
0x18005346b  movdqu  [rbp+57h+var_60], xmm0
0x180053470  cmovnb  rax, rbx
0x180053474  mov     word ptr [rbp+57h+var_90], ax
0x180053478  add     ax, r15w
0x18005347c  mov     word ptr [rbp+57h+var_90+2], ax
0x180053480  lea     rax, [rbp+57h+var_90]
0x180053484  mov     qword ptr [rbp+57h+var_70], rax
0x180053488  call    NtOpenKey
0x18005348d  test    eax, eax
0x18005348f  js      loc_180053625
0x180053495  lea     rcx, aAcp; "ACP"
0x18005349c  mov     [rbp+57h+var_B0], 0
0x1800534a4  mov     [rbp+57h+var_A8], rcx
0x1800534a8  call    wcslen
0x1800534ad  mov     rcx, [rbp+57h+Handle]
0x1800534b1  lea     r9, [rbp+57h+var_50]
0x1800534b5  add     rax, rax
0x1800534b8  lea     rdx, [rbp+57h+var_B0]
0x1800534bc  cmp     rax, r13
0x1800534bf  mov     r8d, r15d
0x1800534c2  cmovnb  rax, rbx
0x1800534c6  mov     word ptr [rbp+57h+var_B0], ax
0x1800534ca  add     ax, r15w
0x1800534ce  mov     word ptr [rbp+57h+var_B0+2], ax
0x1800534d2  lea     rax, [rbp+57h+var_C0]
0x1800534d6  mov     [rsp+0F0h+var_C8], rax
0x1800534db  mov     [rsp+0F0h+var_D0], 24h ; '$'
0x1800534e3  call    NtQueryValueKey
0x1800534e8  mov     ebx, eax
0x1800534ea  test    eax, eax
0x1800534ec  js      loc_1800535F2
0x1800534f2  cmp     [rbp+57h+var_4C], 1
0x1800534f6  jnz     short loc_180053546
0x1800534f8  xor     eax, eax
0x1800534fa  lea     rcx, [rbp+57h+String]; String
0x1800534fe  mov     [rbp+57h+var_2E], ax
0x180053502  mov     [rbp+57h+var_9C], eax
0x180053505  lea     rax, [rbp+57h+String]
0x180053509  mov     [rbp+57h+var_98], rax
0x18005350d  call    wcslen
0x180053512  add     rax, rax
0x180053515  lea     ecx, [r13-2]
0x180053519  cmp     rax, r13
0x18005351c  lea     edx, [r15+8]
0x180053520  mov     r8, rsi
0x180053523  cmovnb  rax, rcx
0x180053527  lea     rcx, [rbp+57h+var_A0]
0x18005352b  mov     [rbp+57h+var_A0], ax
0x18005352f  add     ax, r15w
0x180053533  mov     [rbp+57h+var_9E], ax
0x180053537  call    RtlUnicodeStringToInteger
0x18005353c  mov     ebx, eax
0x18005353e  test    eax, eax
0x180053540  js      loc_1800535F2
0x180053546  lea     rcx, aOemcp; "OEMCP"
0x18005354d  mov     [rbp+57h+var_B0], 0
0x180053555  mov     [rbp+57h+var_A8], rcx
0x180053559  call    wcslen
0x18005355e  add     rax, rax
0x180053561  lea     r9, [rbp+57h+var_50]
0x180053565  cmp     rax, r13
0x180053568  lea     rdx, [rbp+57h+var_B0]
0x18005356c  mov     ecx, 0FFFCh
0x180053571  mov     r8d, r15d
0x180053574  cmovnb  rax, rcx
0x180053578  mov     rcx, [rbp+57h+Handle]
0x18005357c  mov     word ptr [rbp+57h+var_B0], ax
0x180053580  add     ax, r15w
0x180053584  mov     word ptr [rbp+57h+var_B0+2], ax
0x180053588  lea     rax, [rbp+57h+var_C0]
0x18005358c  mov     [rsp+0F0h+var_C8], rax
0x180053591  mov     [rsp+0F0h+var_D0], 24h ; '$'
0x180053599  call    NtQueryValueKey
0x18005359e  mov     ebx, eax
0x1800535a0  test    eax, eax
0x1800535a2  js      short loc_1800535F2
0x1800535a4  cmp     [rbp+57h+var_4C], 1
0x1800535a8  jnz     short loc_1800535F2
0x1800535aa  xor     eax, eax
0x1800535ac  lea     rcx, [rbp+57h+String]; String
0x1800535b0  mov     [rbp+57h+var_2E], ax
0x1800535b4  mov     [rbp+57h+var_9C], eax
0x1800535b7  lea     rax, [rbp+57h+String]
0x1800535bb  mov     [rbp+57h+var_98], rax
0x1800535bf  call    wcslen
0x1800535c4  add     rax, rax
0x1800535c7  mov     ecx, 0FFFCh
0x1800535cc  cmp     rax, r13
0x1800535cf  mov     r8, rdi
0x1800535d2  mov     edx, 0Ah
0x1800535d7  cmovnb  rax, rcx
0x1800535db  lea     rcx, [rbp+57h+var_A0]
0x1800535df  mov     [rbp+57h+var_A0], ax
0x1800535e3  add     ax, r15w
0x1800535e7  mov     [rbp+57h+var_9E], ax
0x1800535eb  call    RtlUnicodeStringToInteger
0x1800535f0  mov     ebx, eax
0x1800535f2  mov     rcx, [rbp+57h+Handle]; Handle
0x1800535f6  call    NtClose
0x1800535fb  test    ebx, ebx
0x1800535fd  js      short loc_180053625
0x1800535ff  xor     eax, eax
0x180053601  mov     rcx, [rbp+57h+var_28]
0x180053605  xor     rcx, rsp; StackCookie
0x180053608  call    __security_check_cookie
0x18005360d  mov     rbx, [rsp+0F0h+arg_10]
0x180053615  add     rsp, 0D0h
0x18005361c  pop     r15
0x18005361e  pop     r13
0x180053620  pop     rdi
0x180053621  pop     rsi
0x180053622  pop     rbp
0x180053623  retn
0x180053625  mov     dword ptr [rsi], 0FDE9h
0x18005362b  mov     dword ptr [rdi], 0FDE9h
0x180053631  jmp     short loc_1800535FF
```
