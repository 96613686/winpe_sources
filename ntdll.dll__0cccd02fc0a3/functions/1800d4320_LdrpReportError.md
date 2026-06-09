# LdrpReportError

- ea: `0x1800d4320`
- end: `0x1800d45cc`
- name: `LdrpReportError`
- size: `684`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180025698`
- `0x180052930`
- `0x1800ac3d0`

## callees

- `0x18001eb80`
- `0x180021c80`
- `0x1800369d4`
- `0x180053990`
- `0x1800d4320`
- `0x18012c830`
- `0x180161160`
- `0x180162000`
- `0x180164360`

## string_xrefs

- `0x1800d4444`: `Locating export "%wZ" for DLL "%wZ" failed with status: 0x%08lx.\n`
- `0x1800d452c`: `Locating export at ordinal %d for DLL "%wZ" failed with status: 0x%08lx.\n`

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
0x1800d4320  mov     [rsp-8+arg_18], rbx
0x1800d4325  push    rbp
0x1800d4326  push    rsi
0x1800d4327  push    rdi
0x1800d4328  push    r12
0x1800d432a  push    r13
0x1800d432c  push    r14
0x1800d432e  push    r15
0x1800d4330  lea     rbp, [rsp-0B0h]
0x1800d4338  sub     rsp, 1B0h
0x1800d433f  mov     rax, cs:__security_cookie
0x1800d4346  xor     rax, rsp
0x1800d4349  mov     [rbp+0E0h+var_40], rax
0x1800d4350  xor     esi, esi
0x1800d4352  xorps   xmm0, xmm0
0x1800d4355  mov     [rsp+1E0h+var_190], esi
0x1800d4359  mov     r15d, r8d
0x1800d435c  mov     rdi, rdx
0x1800d435f  mov     rbx, rcx
0x1800d4362  mov     r13d, 0FFFCh
0x1800d4368  mov     r12d, 0FFFEh
0x1800d436e  movups  xmmword ptr [rsp+1E0h+DestinationString.Length], xmm0
0x1800d4373  movups  [rsp+1E0h+var_188], xmm0
0x1800d4378  test    rcx, rcx
0x1800d437b  jnz     loc_1800D455D
0x1800d4381  lea     rcx, aUnknown_1; "Unknown"
0x1800d4388  mov     qword ptr [rsp+1E0h+var_188+8], rcx
0x1800d438d  call    wcslen
0x1800d4392  add     rax, rax
0x1800d4395  lea     rbx, [rsp+1E0h+var_188]
0x1800d439a  cmp     rax, r12
0x1800d439d  cmovnb  rax, r13
0x1800d43a1  mov     word ptr [rsp+1E0h+var_188], ax
0x1800d43a6  add     ax, 2
0x1800d43aa  mov     word ptr [rsp+1E0h+var_188+2], ax
0x1800d43af  xor     r14b, r14b
0x1800d43b2  cmp     r15d, 0C0000139h
0x1800d43b9  jnz     loc_1800D44B0
0x1800d43bf  mov     qword ptr [rsp+1E0h+SourceString.Length], rsi
0x1800d43c4  mov     [rsp+1E0h+SourceString.Buffer], rdi
0x1800d43c9  test    rdi, rdi
0x1800d43cc  jz      short loc_1800D43ED
0x1800d43ce  mov     rcx, rdi; Str
0x1800d43d1  call    strlen
0x1800d43d6  cmp     rax, 0FFFFh
0x1800d43dc  cmovnb  rax, r12
0x1800d43e0  mov     [rsp+1E0h+SourceString.Length], ax
0x1800d43e5  inc     ax
0x1800d43e8  mov     [rsp+1E0h+SourceString.MaximumLength], ax
0x1800d43ed  lea     rax, [rbp+0E0h+var_140]
0x1800d43f1  xor     r8d, r8d; AllocateDestinationString
0x1800d43f4  mov     [rsp+1E0h+DestinationString.Buffer], rax
0x1800d43f9  lea     rdx, [rsp+1E0h+SourceString]; SourceString
0x1800d43fe  mov     eax, 100h
0x1800d4403  lea     rcx, [rsp+1E0h+DestinationString]; DestinationString
0x1800d4408  mov     [rsp+1E0h+DestinationString.MaximumLength], ax
0x1800d440d  call    RtlAnsiStringToUnicodeString
0x1800d4412  test    eax, eax
0x1800d4414  jns     short loc_1800D441B
0x1800d4416  mov     [rsp+1E0h+DestinationString.Length], si
0x1800d441b  lea     rax, [rsp+1E0h+DestinationString]
0x1800d4420  mov     [rsp+1E0h+var_1A8], 0C0000139h
0x1800d4428  mov     [rsp+1E0h+var_168], rax
0x1800d442d  mov     esi, 3
0x1800d4432  lea     rax, [rsp+1E0h+DestinationString]
0x1800d4437  mov     [rsp+1E0h+var_1B0], rbx
0x1800d443c  mov     qword ptr [rsp+1E0h+ArgList], rax; ArgList
0x1800d4441  mov     r12d, esi
0x1800d4444  lea     rax, aLocatingExport; "Locating export \"%wZ\" for DLL \"%wZ\""...
0x1800d444b  mov     [rbp+0E0h+var_158], 0FFFFFFFFC0000139h
0x1800d4453  mov     edx, 37Ah; int
0x1800d4458  movzx   r9d, r14b
0x1800d445c  lea     r8, aLdrpreporterro; "LdrpReportError"
0x1800d4463  xor     r9d, 1; int
0x1800d4467  mov     [rsp+1E0h+Format], rax; Format
0x1800d446c  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x1800d4473  mov     [rbp+0E0h+var_160], rbx
0x1800d4477  call    LdrpLogInternal
0x1800d447c  test    r14b, r14b
0x1800d447f  jnz     loc_1800D4565
0x1800d4485  mov     rcx, [rbp+0E0h+var_40]
0x1800d448c  xor     rcx, rsp; StackCookie
0x1800d448f  call    __security_check_cookie
0x1800d4494  mov     rbx, [rsp+1E0h+arg_18]
0x1800d449c  add     rsp, 1B0h
0x1800d44a3  pop     r15
0x1800d44a5  pop     r14
0x1800d44a7  pop     r13
0x1800d44a9  pop     r12
0x1800d44ab  pop     rdi
0x1800d44ac  pop     rsi
0x1800d44ad  pop     rbp
0x1800d44ae  retn
0x1800d44b0  cmp     r15d, 0C0000138h
0x1800d44b7  jnz     short loc_1800D4538
0x1800d44b9  movzx   r9d, di
0x1800d44bd  lea     r8, aD_1; "#%d"
0x1800d44c4  mov     edx, 0Eh; cbDest
0x1800d44c9  lea     rcx, [rbp+0E0h+pszDest]; pszDest
0x1800d44cd  call    StringCbPrintfW
0x1800d44d2  lea     rax, [rbp+0E0h+pszDest]
0x1800d44d6  mov     qword ptr [rsp+1E0h+DestinationString.Length], rsi
0x1800d44db  lea     rcx, [rbp+0E0h+pszDest]; String
0x1800d44df  mov     [rsp+1E0h+DestinationString.Buffer], rax
0x1800d44e4  call    wcslen
0x1800d44e9  add     rax, rax
0x1800d44ec  mov     [rsp+1E0h+var_1A8], r15d
0x1800d44f1  cmp     rax, r12
0x1800d44f4  mov     [rsp+1E0h+var_1B0], rbx
0x1800d44f9  mov     [rsp+1E0h+var_168], rdi
0x1800d44fe  mov     esi, 3
0x1800d4503  cmovnb  rax, r13
0x1800d4507  mov     [rbp+0E0h+var_158], 0FFFFFFFFC0000138h
0x1800d450f  mov     [rsp+1E0h+DestinationString.Length], ax
0x1800d4514  mov     r12d, 2
0x1800d451a  add     ax, 2
0x1800d451e  mov     dword ptr [rsp+1E0h+ArgList], edi
0x1800d4522  mov     [rsp+1E0h+DestinationString.MaximumLength], ax
0x1800d4527  mov     edx, 360h
0x1800d452c  lea     rax, aLocatingExport_0; "Locating export at ordinal %d for DLL "...
0x1800d4533  jmp     loc_1800D4458
0x1800d4538  cmp     r15d, 0C0000135h
0x1800d453f  jnz     short loc_1800D45B5
0x1800d4541  mov     qword ptr [rsp+1E0h+DestinationString.Length], rsi
0x1800d4546  mov     [rsp+1E0h+DestinationString.Buffer], rsi
0x1800d454b  mov     esi, 1
0x1800d4550  mov     r12d, esi
0x1800d4553  mov     [rsp+1E0h+var_168], rbx
0x1800d4558  jmp     loc_1800D447C
0x1800d455d  mov     r14b, 1
0x1800d4560  jmp     loc_1800D43B2
0x1800d4565  lea     rax, [rsp+1E0h+var_190]
0x1800d456a  mov     r8d, r12d
0x1800d456d  mov     qword ptr [rsp+1E0h+ArgList], rax
0x1800d4572  lea     r9, [rsp+1E0h+var_168]
0x1800d4577  mov     edx, esi
0x1800d4579  mov     dword ptr [rsp+1E0h+Format], 1
0x1800d4581  mov     ecx, r15d
0x1800d4584  call    NtRaiseHardError
0x1800d4589  test    eax, eax
0x1800d458b  js      short loc_1800D459C
0x1800d458d  cmp     cs:LdrInitState, 3
0x1800d4594  jz      short loc_1800D459C
0x1800d4596  inc     cs:LdrpFatalHardErrorCount
0x1800d459c  lea     eax, [r15+3FFFFEC8h]
0x1800d45a3  cmp     eax, 1
0x1800d45a6  ja      loc_1800D4485
0x1800d45ac  mov     ecx, r15d
0x1800d45af  call    RtlRaiseStatus
0x1800d45b5  mov     qword ptr [rsp+1E0h+DestinationString.Length], rsi
0x1800d45ba  mov     [rsp+1E0h+DestinationString.Buffer], rsi
0x1800d45bf  mov     esi, 3
0x1800d45c4  mov     r12d, esi
0x1800d45c7  jmp     loc_1800D447C
```
