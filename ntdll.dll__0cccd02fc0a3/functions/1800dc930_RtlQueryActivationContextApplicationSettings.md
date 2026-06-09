# RtlQueryActivationContextApplicationSettings

- ea: `0x1800dc930`
- end: `0x1800dcb76`
- name: `RtlQueryActivationContextApplicationSettings`
- size: `582`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180074ff8`
- `0x1800dc81c`

## callees

- `0x180019d50`
- `0x18001a080`
- `0x18001a590`
- `0x1800dc930`
- `0x18012c830`
- `0x180163a80`
- `0x18016f030`

## string_xrefs

- `0x1800dc954`: `http://schemas.microsoft.com/SMI/2005/WindowsSettings`

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
0x1800dc930  mov     [rsp-8+arg_0], rbx
0x1800dc935  mov     [rsp-8+arg_8], rsi
0x1800dc93a  push    rbp
0x1800dc93b  push    rdi
0x1800dc93c  push    r14
0x1800dc93e  lea     rbp, [rsp-2Fh]
0x1800dc943  sub     rsp, 0D0h
0x1800dc94a  test    r8, r8
0x1800dc94d  mov     [rbp+3Fh+arg_10], 0
0x1800dc954  lea     rsi, aHttpSchemasMic_1; "http://schemas.microsoft.com/SMI/2005/W"...
0x1800dc95b  mov     [rbp+3Fh+var_98], 0
0x1800dc963  cmovnz  rsi, r8
0x1800dc967  mov     [rbp+3Fh+var_9C], 0FFFFFFFFh
0x1800dc96e  cmp     [rbp+3Fh+arg_20], 0
0x1800dc973  mov     r14, r9
0x1800dc976  mov     [rbp+3Fh+var_A0], 0
0x1800dc97d  jz      loc_1800DCB05
0x1800dc983  test    rdx, rdx
0x1800dc986  jnz     loc_1800DCB22
0x1800dc98c  mov     ecx, 2F8h
0x1800dc991  mov     rax, gs:60h
0x1800dc99a  mov     rax, [rax+rcx]
0x1800dc99e  test    rax, rax
0x1800dc9a1  lea     rcx, RtlpTheEmptyActivationContextData; "Actx "
0x1800dc9a8  cmovnz  rcx, rax
0x1800dc9ac  xor     edx, edx
0x1800dc9ae  lea     rax, [rbp+3Fh+arg_10]
0x1800dc9b2  lea     r9, [rbp+3Fh+var_98]
0x1800dc9b6  mov     [rsp+0E0h+var_C0], rax
0x1800dc9bb  lea     r8d, [rdx+0Ah]
0x1800dc9bf  call    RtlpLocateActivationContextSection
0x1800dc9c4  mov     ebx, eax
0x1800dc9c6  test    eax, eax
0x1800dc9c8  js      loc_1800DCAF3
0x1800dc9ce  mov     edi, [rbp+3Fh+arg_10]
0x1800dc9d1  mov     rbx, [rbp+3Fh+var_98]
0x1800dc9d5  cmp     edi, 2Ch ; ','
0x1800dc9d8  jb      loc_1800DCB3B
0x1800dc9de  cmp     dword ptr [rbx], 64487353h
0x1800dc9e4  jnz     loc_1800DCB3B
0x1800dc9ea  mov     [rbp+3Fh+var_98], 0
0x1800dc9f2  mov     [rbp+3Fh+var_90], r14
0x1800dc9f6  test    r14, r14
0x1800dc9f9  jz      loc_1800DCB17
0x1800dc9ff  mov     rcx, r14; String
0x1800dca02  call    wcslen
0x1800dca07  add     rax, rax
0x1800dca0a  mov     ecx, 0FFFCh
0x1800dca0f  cmp     rax, 0FFFEh
0x1800dca15  mov     r14d, 2
0x1800dca1b  cmovnb  rax, rcx
0x1800dca1f  mov     word ptr [rbp+3Fh+var_98], ax
0x1800dca23  add     ax, r14w
0x1800dca27  mov     word ptr [rbp+3Fh+var_98+2], ax
0x1800dca2b  xor     edx, edx; Val
0x1800dca2d  lea     rcx, [rbp+3Fh+var_7C]; void *
0x1800dca31  lea     r8d, [rdx+6Ch]; Size
0x1800dca35  call    memset$thunk$772440563353939046
0x1800dca3a  lea     rax, [rbp+3Fh+var_A0]
0x1800dca3e  mov     [rbp+3Fh+var_80], 70h ; 'p'
0x1800dca45  mov     [rsp+0E0h+var_B8], rax
0x1800dca4a  lea     r9, [rbp+3Fh+var_80]
0x1800dca4e  lea     rax, [rbp+3Fh+var_9C]
0x1800dca52  mov     rdx, rdi
0x1800dca55  lea     r8, [rbp+3Fh+var_98]
0x1800dca59  mov     [rsp+0E0h+var_C0], rax
0x1800dca5e  mov     rcx, rbx
0x1800dca61  call    RtlpFindUnicodeStringInSection
0x1800dca66  mov     ebx, eax
0x1800dca68  test    eax, eax
0x1800dca6a  js      loc_1800DCAF3
0x1800dca70  cmp     [rbp+3Fh+var_7C], 1
0x1800dca74  jnz     loc_1800DCB53
0x1800dca7a  mov     rdi, [rbp+3Fh+var_78]
0x1800dca7e  mov     eax, [rdi+0Ch]
0x1800dca81  add     rax, rdi
0x1800dca84  sub     rsi, rax
0x1800dca87  movzx   ecx, word ptr [rax]
0x1800dca8a  movzx   edx, word ptr [rax+rsi]
0x1800dca8e  sub     ecx, edx
0x1800dca90  jnz     short loc_1800DCA99
0x1800dca92  add     rax, r14
0x1800dca95  test    edx, edx
0x1800dca97  jnz     short loc_1800DCA87
0x1800dca99  test    ecx, ecx
0x1800dca9b  jz      short loc_1800DCABB
0x1800dca9d  mov     eax, 0C0150008h
0x1800dcaa2  lea     r11, [rsp+0E0h+var_10]
0x1800dcaaa  mov     rbx, [r11+20h]
0x1800dcaae  mov     rsi, [r11+28h]
0x1800dcab2  mov     rsp, r11
0x1800dcab5  pop     r14
0x1800dcab7  pop     rdi
0x1800dcab8  pop     rbp
0x1800dcab9  retn
0x1800dcabb  mov     r8d, [rdi+18h]
0x1800dcabf  mov     eax, r8d
0x1800dcac2  shr     rax, 1
0x1800dcac5  cmp     [rbp+3Fh+arg_28], rax
0x1800dcac9  jb      short loc_1800DCB34
0x1800dcacb  mov     edx, [rdi+1Ch]
0x1800dcace  add     r8, 2; Size
0x1800dcad2  mov     rcx, [rbp+3Fh+arg_20]; void *
0x1800dcad6  add     rdx, rdi; Src
0x1800dcad9  call    memmove
0x1800dcade  mov     rcx, [rbp+3Fh+arg_30]
0x1800dcae2  test    rcx, rcx
0x1800dcae5  jz      short loc_1800DCAF3
0x1800dcae7  mov     eax, [rdi+18h]
0x1800dcaea  shr     rax, 1
0x1800dcaed  inc     rax
0x1800dcaf0  mov     [rcx], rax
0x1800dcaf3  mov     eax, 0C0150008h
0x1800dcaf8  cmp     ebx, 0C0150001h
0x1800dcafe  cmovz   ebx, eax
0x1800dcb01  mov     eax, ebx
0x1800dcb03  jmp     short loc_1800DCAA2
0x1800dcb05  cmp     [rbp+3Fh+arg_28], 0
0x1800dcb0a  jz      loc_1800DC983
0x1800dcb10  mov     eax, 0C000000Dh
0x1800dcb15  jmp     short loc_1800DCAA2
0x1800dcb17  mov     r14d, 2
0x1800dcb1d  jmp     loc_1800DCA2B
0x1800dcb22  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800dcb26  jnz     short loc_1800DCB5D
0x1800dcb28  lea     rcx, RtlpTheEmptyActivationContextData; "Actx "
0x1800dcb2f  jmp     loc_1800DC9AC
0x1800dcb34  mov     ebx, 0C0000023h
0x1800dcb39  jmp     short loc_1800DCADE
0x1800dcb3b  xor     edx, edx
0x1800dcb3d  mov     dword ptr [rsp+0E0h+var_C0], edi
0x1800dcb41  mov     r9, rbx
0x1800dcb44  lea     r8, aRtlplocateacti; "RtlpLocateActivationContextSection() fo"...
0x1800dcb4b  lea     ecx, [rdx+33h]
0x1800dcb4e  call    DbgPrintEx
0x1800dcb53  mov     eax, 0C0150003h
0x1800dcb58  jmp     loc_1800DCAA2
0x1800dcb5d  cmp     rdx, 0FFFFFFFFFFFFFFFCh
0x1800dcb61  jz      short loc_1800DCB6C
0x1800dcb63  mov     rax, [rdx+18h]
0x1800dcb67  jmp     loc_1800DC99E
0x1800dcb6c  mov     ecx, 308h
0x1800dcb71  jmp     loc_1800DC991
```
