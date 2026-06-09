# RtlQueryActivationContextApplicationSettings

- ea: `0x180053180`
- end: `0x1800533c6`
- name: `RtlQueryActivationContextApplicationSettings`
- size: `582`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005306c`
- `0x180053e78`

## callees

- `0x180019d50`
- `0x18001a080`
- `0x18001a590`
- `0x180053180`
- `0x18012d320`
- `0x180164280`
- `0x18016f030`

## string_xrefs

- `0x1800531a4`: `http://schemas.microsoft.com/SMI/2005/WindowsSettings`

## pseudocode

```c
__int64 __fastcall RtlQueryActivationContextApplicationSettings(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const void *a4,
        void *a5,
        unsigned __int64 a6,
        _QWORD *a7)
{
  const wchar_t *v7; // rsi
  __int64 v9; // rcx
  char *v10; // rax
  char *v11; // rcx
  int UnicodeStringInSection; // ebx
  unsigned int v13; // edi
  int v14; // ebx
  size_t v15; // rax
  unsigned int *v16; // rdi
  char *v17; // rax
  signed __int64 v18; // rsi
  int v19; // edx
  int v20; // ecx
  int v22; // [rsp+40h] [rbp-61h] BYREF
  int v23; // [rsp+44h] [rbp-5Dh] BYREF
  const void *v24[3]; // [rsp+48h] [rbp-59h] BYREF
  int v25; // [rsp+60h] [rbp-41h] BYREF
  int v26; // [rsp+64h] [rbp-3Dh] BYREF
  unsigned int *v27; // [rsp+68h] [rbp-39h]
  unsigned int v28; // [rsp+100h] [rbp+5Fh] BYREF

  v28 = 0;
  v7 = L"http://schemas.microsoft.com/SMI/2005/WindowsSettings";
  v24[0] = 0;
  if ( a3 )
    v7 = a3;
  v23 = -1;
  v22 = 0;
  if ( !a5 && a6 )
    return 3221225485LL;
  switch ( a2 )
  {
    case 0LL:
      v9 = 760;
LABEL_6:
      v10 = *(char **)(&NtCurrentPeb()->InheritedAddressSpace + v9);
      goto LABEL_7;
    case -3LL:
      v11 = "Actx ";
      goto LABEL_9;
    case -4LL:
      v9 = 776;
      goto LABEL_6;
  }
  v10 = *(char **)(a2 + 24);
LABEL_7:
  v11 = "Actx ";
  if ( v10 )
    v11 = v10;
LABEL_9:
  UnicodeStringInSection = RtlpLocateActivationContextSection(v11, 0, 0xAu, v24, &v28);
  if ( UnicodeStringInSection >= 0 )
  {
    v13 = v28;
    v14 = (int)v24[0];
    if ( v28 < 0x2C || *(_DWORD *)v24[0] != 1682469715 )
    {
      DbgPrintEx(
        51,
        0,
        "RtlpLocateActivationContextSection() found section at %p (length %lu) which is not a string section\n",
        v24[0],
        v28);
      return 3222601731LL;
    }
    v24[0] = 0;
    v24[1] = a4;
    if ( a4 )
    {
      v15 = 2 * wcslen((const wchar_t *)a4);
      if ( v15 >= 0xFFFE )
        LOWORD(v15) = -4;
      LOWORD(v24[0]) = v15;
      WORD1(v24[0]) = v15 + 2;
    }
    memset_thunk_772440563353939046(&v26, 0, 0x6Cu);
    v25 = 112;
    UnicodeStringInSection = RtlpFindUnicodeStringInSection(
                               v14,
                               v13,
                               (unsigned int)v24,
                               (unsigned int)&v25,
                               (__int64)&v23,
                               (__int64)&v22);
    if ( UnicodeStringInSection >= 0 )
    {
      if ( v26 == 1 )
      {
        v16 = v27;
        v17 = (char *)v27 + v27[3];
        v18 = (char *)v7 - v17;
        do
        {
          v19 = *(unsigned __int16 *)&v17[v18];
          v20 = *(unsigned __int16 *)v17 - v19;
          if ( v20 )
            break;
          v17 += 2;
        }
        while ( v19 );
        if ( v20 )
          return 3222601736LL;
        if ( a6 < (unsigned __int64)v27[6] >> 1 )
          UnicodeStringInSection = -1073741789;
        else
          memmove(a5, (char *)v27 + v27[7], v27[6] + 2LL);
        if ( a7 )
          *a7 = ((unsigned __int64)v16[6] >> 1) + 1;
        goto LABEL_27;
      }
      return 3222601731LL;
    }
  }
LABEL_27:
  if ( UnicodeStringInSection == -1072365567 )
    return (unsigned int)-1072365560;
  return (unsigned int)UnicodeStringInSection;
}

```

## disassembly

```asm
0x180053180  mov     [rsp-8+arg_0], rbx
0x180053185  mov     [rsp-8+arg_8], rsi
0x18005318a  push    rbp
0x18005318b  push    rdi
0x18005318c  push    r14
0x18005318e  lea     rbp, [rsp-2Fh]
0x180053193  sub     rsp, 0D0h
0x18005319a  test    r8, r8
0x18005319d  mov     [rbp+3Fh+arg_10], 0
0x1800531a4  lea     rsi, aHttpSchemasMic_1; "http://schemas.microsoft.com/SMI/2005/W"...
0x1800531ab  mov     [rbp+3Fh+var_98], 0
0x1800531b3  cmovnz  rsi, r8
0x1800531b7  mov     [rbp+3Fh+var_9C], 0FFFFFFFFh
0x1800531be  cmp     [rbp+3Fh+arg_20], 0
0x1800531c3  mov     r14, r9
0x1800531c6  mov     [rbp+3Fh+var_A0], 0
0x1800531cd  jz      loc_180053355
0x1800531d3  test    rdx, rdx
0x1800531d6  jnz     loc_180053372
0x1800531dc  mov     ecx, 2F8h
0x1800531e1  mov     rax, gs:60h
0x1800531ea  mov     rax, [rax+rcx]
0x1800531ee  test    rax, rax
0x1800531f1  lea     rcx, RtlpTheEmptyActivationContextData; "Actx "
0x1800531f8  cmovnz  rcx, rax
0x1800531fc  xor     edx, edx
0x1800531fe  lea     rax, [rbp+3Fh+arg_10]
0x180053202  lea     r9, [rbp+3Fh+var_98]
0x180053206  mov     [rsp+0E0h+var_C0], rax
0x18005320b  lea     r8d, [rdx+0Ah]
0x18005320f  call    RtlpLocateActivationContextSection
0x180053214  mov     ebx, eax
0x180053216  test    eax, eax
0x180053218  js      loc_180053343
0x18005321e  mov     edi, [rbp+3Fh+arg_10]
0x180053221  mov     rbx, [rbp+3Fh+var_98]
0x180053225  cmp     edi, 2Ch ; ','
0x180053228  jb      loc_18005338B
0x18005322e  cmp     dword ptr [rbx], 64487353h
0x180053234  jnz     loc_18005338B
0x18005323a  mov     [rbp+3Fh+var_98], 0
0x180053242  mov     [rbp+3Fh+var_90], r14
0x180053246  test    r14, r14
0x180053249  jz      loc_180053367
0x18005324f  mov     rcx, r14; String
0x180053252  call    wcslen
0x180053257  add     rax, rax
0x18005325a  mov     ecx, 0FFFCh
0x18005325f  cmp     rax, 0FFFEh
0x180053265  mov     r14d, 2
0x18005326b  cmovnb  rax, rcx
0x18005326f  mov     word ptr [rbp+3Fh+var_98], ax
0x180053273  add     ax, r14w
0x180053277  mov     word ptr [rbp+3Fh+var_98+2], ax
0x18005327b  xor     edx, edx; Val
0x18005327d  lea     rcx, [rbp+3Fh+var_7C]; void *
0x180053281  lea     r8d, [rdx+6Ch]; Size
0x180053285  call    memset$thunk$772440563353939046
0x18005328a  lea     rax, [rbp+3Fh+var_A0]
0x18005328e  mov     [rbp+3Fh+var_80], 70h ; 'p'
0x180053295  mov     [rsp+0E0h+var_B8], rax
0x18005329a  lea     r9, [rbp+3Fh+var_80]
0x18005329e  lea     rax, [rbp+3Fh+var_9C]
0x1800532a2  mov     rdx, rdi
0x1800532a5  lea     r8, [rbp+3Fh+var_98]
0x1800532a9  mov     [rsp+0E0h+var_C0], rax
0x1800532ae  mov     rcx, rbx
0x1800532b1  call    RtlpFindUnicodeStringInSection
0x1800532b6  mov     ebx, eax
0x1800532b8  test    eax, eax
0x1800532ba  js      loc_180053343
0x1800532c0  cmp     [rbp+3Fh+var_7C], 1
0x1800532c4  jnz     loc_1800533A3
0x1800532ca  mov     rdi, [rbp+3Fh+var_78]
0x1800532ce  mov     eax, [rdi+0Ch]
0x1800532d1  add     rax, rdi
0x1800532d4  sub     rsi, rax
0x1800532d7  movzx   ecx, word ptr [rax]
0x1800532da  movzx   edx, word ptr [rax+rsi]
0x1800532de  sub     ecx, edx
0x1800532e0  jnz     short loc_1800532E9
0x1800532e2  add     rax, r14
0x1800532e5  test    edx, edx
0x1800532e7  jnz     short loc_1800532D7
0x1800532e9  test    ecx, ecx
0x1800532eb  jz      short loc_18005330B
0x1800532ed  mov     eax, 0C0150008h
0x1800532f2  lea     r11, [rsp+0E0h+var_10]
0x1800532fa  mov     rbx, [r11+20h]
0x1800532fe  mov     rsi, [r11+28h]
0x180053302  mov     rsp, r11
0x180053305  pop     r14
0x180053307  pop     rdi
0x180053308  pop     rbp
0x180053309  retn
0x18005330b  mov     r8d, [rdi+18h]
0x18005330f  mov     eax, r8d
0x180053312  shr     rax, 1
0x180053315  cmp     [rbp+3Fh+arg_28], rax
0x180053319  jb      short loc_180053384
0x18005331b  mov     edx, [rdi+1Ch]
0x18005331e  add     r8, 2; Size
0x180053322  mov     rcx, [rbp+3Fh+arg_20]; void *
0x180053326  add     rdx, rdi; Src
0x180053329  call    memmove
0x18005332e  mov     rcx, [rbp+3Fh+arg_30]
0x180053332  test    rcx, rcx
0x180053335  jz      short loc_180053343
0x180053337  mov     eax, [rdi+18h]
0x18005333a  shr     rax, 1
0x18005333d  inc     rax
0x180053340  mov     [rcx], rax
0x180053343  mov     eax, 0C0150008h
0x180053348  cmp     ebx, 0C0150001h
0x18005334e  cmovz   ebx, eax
0x180053351  mov     eax, ebx
0x180053353  jmp     short loc_1800532F2
0x180053355  cmp     [rbp+3Fh+arg_28], 0
0x18005335a  jz      loc_1800531D3
0x180053360  mov     eax, 0C000000Dh
0x180053365  jmp     short loc_1800532F2
0x180053367  mov     r14d, 2
0x18005336d  jmp     loc_18005327B
0x180053372  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180053376  jnz     short loc_1800533AD
0x180053378  lea     rcx, RtlpTheEmptyActivationContextData; "Actx "
0x18005337f  jmp     loc_1800531FC
0x180053384  mov     ebx, 0C0000023h
0x180053389  jmp     short loc_18005332E
0x18005338b  xor     edx, edx
0x18005338d  mov     dword ptr [rsp+0E0h+var_C0], edi
0x180053391  mov     r9, rbx
0x180053394  lea     r8, aRtlplocateacti; "RtlpLocateActivationContextSection() fo"...
0x18005339b  lea     ecx, [rdx+33h]
0x18005339e  call    DbgPrintEx
0x1800533a3  mov     eax, 0C0150003h
0x1800533a8  jmp     loc_1800532F2
0x1800533ad  cmp     rdx, 0FFFFFFFFFFFFFFFCh
0x1800533b1  jz      short loc_1800533BC
0x1800533b3  mov     rax, [rdx+18h]
0x1800533b7  jmp     loc_1800531EE
0x1800533bc  mov     ecx, 308h
0x1800533c1  jmp     loc_1800531E1
```
