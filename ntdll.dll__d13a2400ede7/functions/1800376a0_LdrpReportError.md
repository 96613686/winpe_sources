# LdrpReportError

- ea: `0x1800376a0`
- end: `0x18003794c`
- name: `LdrpReportError`
- size: `684`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180025688`
- `0x18006f310`
- `0x1800b6f08`

## callees

- `0x18001eb80`
- `0x180021c70`
- `0x180035b34`
- `0x1800376a0`
- `0x180070370`
- `0x18012d320`
- `0x180161970`
- `0x180162810`
- `0x180164b60`

## string_xrefs

- `0x1800377c4`: `Locating export "%wZ" for DLL "%wZ" failed with status: 0x%08lx.\n`
- `0x1800378ac`: `Locating export at ordinal %d for DLL "%wZ" failed with status: 0x%08lx.\n`

## pseudocode

```c
void __fastcall LdrpReportError(__int128 *a1, char *a2, unsigned int a3)
{
  __int128 *v5; // rbx
  size_t v6; // rax
  unsigned __int8 v7; // r14
  size_t v8; // rax
  unsigned int v9; // esi
  unsigned int v10; // r12d
  char *Format; // rax
  int v12; // edx
  size_t v13; // rax
  UNICODE_STRING *ArgList; // [rsp+28h] [rbp-D8h]
  __int128 *v15; // [rsp+30h] [rbp-D0h]
  int v16; // [rsp+38h] [rbp-C8h]
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v19; // [rsp+58h] [rbp-A8h] BYREF
  STRING SourceString; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v21[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v22; // [rsp+88h] [rbp-78h]
  wchar_t pszDest[8]; // [rsp+90h] [rbp-70h] BYREF
  char v24; // [rsp+A0h] [rbp-60h] BYREF

  v18 = 0;
  v5 = a1;
  DestinationString = 0;
  v19 = 0;
  if ( a1 )
  {
    v7 = 1;
  }
  else
  {
    *((_QWORD *)&v19 + 1) = L"Unknown";
    v6 = 2 * wcslen(L"Unknown");
    v5 = &v19;
    if ( v6 >= 0xFFFE )
      LOWORD(v6) = -4;
    LOWORD(v19) = v6;
    WORD1(v19) = v6 + 2;
    v7 = 0;
  }
  if ( a3 == -1073741511 )
  {
    *(_QWORD *)&SourceString.Length = 0;
    SourceString.Buffer = a2;
    if ( a2 )
    {
      v8 = strlen(a2);
      if ( v8 >= 0xFFFF )
        LOWORD(v8) = -2;
      SourceString.Length = v8;
      SourceString.MaximumLength = v8 + 1;
    }
    DestinationString.Buffer = (wchar_t *)&v24;
    DestinationString.MaximumLength = 256;
    if ( RtlAnsiStringToUnicodeString(&DestinationString, &SourceString, 0) < 0 )
      DestinationString.Length = 0;
    v16 = -1073741511;
    v21[0] = &DestinationString;
    v9 = 3;
    v15 = v5;
    ArgList = &DestinationString;
    v10 = 3;
    Format = "Locating export \"%wZ\" for DLL \"%wZ\" failed with status: 0x%08lx.\n";
    v22 = -1073741511;
    v12 = 890;
LABEL_13:
    v21[1] = v5;
    LdrpLogInternal((int)"minkernel\\ldr\\ldrutil.c", v12, (int)"LdrpReportError", v7 ^ 1, Format, (char)ArgList);
    goto LABEL_14;
  }
  if ( a3 == -1073741512 )
  {
    StringCbPrintfW(pszDest, 0xEu, L"#%d", (unsigned __int16)a2);
    *(_QWORD *)&DestinationString.Length = 0;
    DestinationString.Buffer = pszDest;
    v13 = 2 * wcslen(pszDest);
    v16 = -1073741512;
    v15 = v5;
    v21[0] = a2;
    v9 = 3;
    if ( v13 >= 0xFFFE )
      LOWORD(v13) = -4;
    v22 = -1073741512;
    DestinationString.Length = v13;
    v10 = 2;
    LOBYTE(ArgList) = (_BYTE)a2;
    DestinationString.MaximumLength = v13 + 2;
    v12 = 864;
    Format = "Locating export at ordinal %d for DLL \"%wZ\" failed with status: 0x%08lx.\n";
    goto LABEL_13;
  }
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  if ( a3 == -1073741515 )
  {
    v9 = 1;
    v10 = 1;
    v21[0] = v5;
  }
  else
  {
    v9 = 3;
    v10 = 3;
  }
LABEL_14:
  if ( v7 )
  {
    if ( (int)NtRaiseHardError(a3, v9, v10, v21, 1, &v18, v15, v16, *(_QWORD *)&DestinationString.Length) >= 0
      && LdrInitState != 3 )
    {
      ++LdrpFatalHardErrorCount;
    }
    if ( a3 + 1073741512 <= 1 )
      RtlRaiseStatus(a3);
  }
}

```

## disassembly

```asm
0x1800376a0  mov     [rsp-8+arg_18], rbx
0x1800376a5  push    rbp
0x1800376a6  push    rsi
0x1800376a7  push    rdi
0x1800376a8  push    r12
0x1800376aa  push    r13
0x1800376ac  push    r14
0x1800376ae  push    r15
0x1800376b0  lea     rbp, [rsp-0B0h]
0x1800376b8  sub     rsp, 1B0h
0x1800376bf  mov     rax, cs:__security_cookie
0x1800376c6  xor     rax, rsp
0x1800376c9  mov     [rbp+0E0h+var_40], rax
0x1800376d0  xor     esi, esi
0x1800376d2  xorps   xmm0, xmm0
0x1800376d5  mov     [rsp+1E0h+var_190], esi
0x1800376d9  mov     r15d, r8d
0x1800376dc  mov     rdi, rdx
0x1800376df  mov     rbx, rcx
0x1800376e2  mov     r13d, 0FFFCh
0x1800376e8  mov     r12d, 0FFFEh
0x1800376ee  movups  xmmword ptr [rsp+1E0h+DestinationString.Length], xmm0
0x1800376f3  movups  [rsp+1E0h+var_188], xmm0
0x1800376f8  test    rcx, rcx
0x1800376fb  jnz     loc_1800378DD
0x180037701  lea     rcx, aUnknown_1; "Unknown"
0x180037708  mov     qword ptr [rsp+1E0h+var_188+8], rcx
0x18003770d  call    wcslen
0x180037712  add     rax, rax
0x180037715  lea     rbx, [rsp+1E0h+var_188]
0x18003771a  cmp     rax, r12
0x18003771d  cmovnb  rax, r13
0x180037721  mov     word ptr [rsp+1E0h+var_188], ax
0x180037726  add     ax, 2
0x18003772a  mov     word ptr [rsp+1E0h+var_188+2], ax
0x18003772f  xor     r14b, r14b
0x180037732  cmp     r15d, 0C0000139h
0x180037739  jnz     loc_180037830
0x18003773f  mov     qword ptr [rsp+1E0h+SourceString.Length], rsi
0x180037744  mov     [rsp+1E0h+SourceString.Buffer], rdi
0x180037749  test    rdi, rdi
0x18003774c  jz      short loc_18003776D
0x18003774e  mov     rcx, rdi; Str
0x180037751  call    strlen
0x180037756  cmp     rax, 0FFFFh
0x18003775c  cmovnb  rax, r12
0x180037760  mov     [rsp+1E0h+SourceString.Length], ax
0x180037765  inc     ax
0x180037768  mov     [rsp+1E0h+SourceString.MaximumLength], ax
0x18003776d  lea     rax, [rbp+0E0h+var_140]
0x180037771  xor     r8d, r8d; AllocateDestinationString
0x180037774  mov     [rsp+1E0h+DestinationString.Buffer], rax
0x180037779  lea     rdx, [rsp+1E0h+SourceString]; SourceString
0x18003777e  mov     eax, 100h
0x180037783  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x180037788  mov     [rsp+1E0h+DestinationString.MaximumLength], ax
0x18003778d  call    RtlAnsiStringToUnicodeString
0x180037792  test    eax, eax
0x180037794  jns     short loc_18003779B
0x180037796  mov     [rsp+1E0h+DestinationString.Length], si
0x18003779b  lea     rax, [rsp+1E0h+DestinationString]
0x1800377a0  mov     [rsp+1E0h+var_1A8], 0C0000139h
0x1800377a8  mov     [rsp+1E0h+var_168], rax
0x1800377ad  mov     esi, 3
0x1800377b2  lea     rax, [rsp+1E0h+DestinationString]
0x1800377b7  mov     [rsp+1E0h+var_1B0], rbx
0x1800377bc  mov     qword ptr [rsp+1E0h+ArgList], rax; ArgList
0x1800377c1  mov     r12d, esi
0x1800377c4  lea     rax, aLocatingExport; "Locating export \"%wZ\" for DLL \"%wZ\""...
0x1800377cb  mov     [rbp+0E0h+var_158], 0FFFFFFFFC0000139h
0x1800377d3  mov     edx, 37Ah; int
0x1800377d8  movzx   r9d, r14b
0x1800377dc  lea     r8, aLdrpreporterro; "LdrpReportError"
0x1800377e3  xor     r9d, 1; int
0x1800377e7  mov     [rsp+1E0h+Format], rax; Format
0x1800377ec  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x1800377f3  mov     [rbp+0E0h+var_160], rbx
0x1800377f7  call    LdrpLogInternal
0x1800377fc  test    r14b, r14b
0x1800377ff  jnz     loc_1800378E5
0x180037805  mov     rcx, [rbp+0E0h+var_40]
0x18003780c  xor     rcx, rsp; StackCookie
0x18003780f  call    __security_check_cookie
0x180037814  mov     rbx, [rsp+1E0h+arg_18]
0x18003781c  add     rsp, 1B0h
0x180037823  pop     r15
0x180037825  pop     r14
0x180037827  pop     r13
0x180037829  pop     r12
0x18003782b  pop     rdi
0x18003782c  pop     rsi
0x18003782d  pop     rbp
0x18003782e  retn
0x180037830  cmp     r15d, 0C0000138h
0x180037837  jnz     short loc_1800378B8
0x180037839  movzx   r9d, di
0x18003783d  lea     r8, aD_2; "#%d"
0x180037844  mov     edx, 0Eh; cbDest
0x180037849  lea     rcx, [rbp+0E0h+pszDest]; pszDest
0x18003784d  call    StringCbPrintfW
0x180037852  lea     rax, [rbp+0E0h+pszDest]
0x180037856  mov     qword ptr [rsp+1E0h+DestinationString.Length], rsi
0x18003785b  lea     rcx, [rbp+0E0h+pszDest]; String
0x18003785f  mov     [rsp+1E0h+DestinationString.Buffer], rax
0x180037864  call    wcslen
0x180037869  add     rax, rax
0x18003786c  mov     [rsp+1E0h+var_1A8], r15d
0x180037871  cmp     rax, r12
0x180037874  mov     [rsp+1E0h+var_1B0], rbx
0x180037879  mov     [rsp+1E0h+var_168], rdi
0x18003787e  mov     esi, 3
0x180037883  cmovnb  rax, r13
0x180037887  mov     [rbp+0E0h+var_158], 0FFFFFFFFC0000138h
0x18003788f  mov     [rsp+1E0h+DestinationString.Length], ax
0x180037894  mov     r12d, 2
0x18003789a  add     ax, 2
0x18003789e  mov     dword ptr [rsp+1E0h+ArgList], edi
0x1800378a2  mov     [rsp+1E0h+DestinationString.MaximumLength], ax
0x1800378a7  mov     edx, 360h
0x1800378ac  lea     rax, aLocatingExport_0; "Locating export at ordinal %d for DLL "...
0x1800378b3  jmp     loc_1800377D8
0x1800378b8  cmp     r15d, 0C0000135h
0x1800378bf  jnz     short loc_180037935
0x1800378c1  mov     qword ptr [rsp+1E0h+DestinationString.Length], rsi
0x1800378c6  mov     [rsp+1E0h+DestinationString.Buffer], rsi
0x1800378cb  mov     esi, 1
0x1800378d0  mov     r12d, esi
0x1800378d3  mov     [rsp+1E0h+var_168], rbx
0x1800378d8  jmp     loc_1800377FC
0x1800378dd  mov     r14b, 1
0x1800378e0  jmp     loc_180037732
0x1800378e5  lea     rax, [rsp+1E0h+var_190]
0x1800378ea  mov     r8d, r12d
0x1800378ed  mov     qword ptr [rsp+1E0h+ArgList], rax
0x1800378f2  lea     r9, [rsp+1E0h+var_168]
0x1800378f7  mov     edx, esi
0x1800378f9  mov     dword ptr [rsp+1E0h+Format], 1
0x180037901  mov     ecx, r15d
0x180037904  call    NtRaiseHardError
0x180037909  test    eax, eax
0x18003790b  js      short loc_18003791C
0x18003790d  cmp     cs:LdrInitState, 3
0x180037914  jz      short loc_18003791C
0x180037916  inc     cs:LdrpFatalHardErrorCount
0x18003791c  lea     eax, [r15+3FFFFEC8h]
0x180037923  cmp     eax, 1
0x180037926  ja      loc_180037805
0x18003792c  mov     ecx, r15d
0x18003792f  call    RtlRaiseStatus
0x180037935  mov     qword ptr [rsp+1E0h+DestinationString.Length], rsi
0x18003793a  mov     [rsp+1E0h+DestinationString.Buffer], rsi
0x18003793f  mov     esi, 3
0x180037944  mov     r12d, esi
0x180037947  jmp     loc_1800377FC
```
