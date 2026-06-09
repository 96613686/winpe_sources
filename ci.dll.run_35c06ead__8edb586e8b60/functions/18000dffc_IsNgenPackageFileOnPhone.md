# IsNgenPackageFileOnPhone

- ea: `0x18000dffc`
- end: `0x18000e089`
- name: `IsNgenPackageFileOnPhone`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800a73a0`

## callees

- `0x18000aa40`
- `0x18000dffc`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeStrings` at `0x18000e036`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x18000e036`

## string_xrefs

- `0x18000e02f`: `\ProgramData\Microsoft\Windows\AppRepository\Packages\`

## pseudocode

```c
bool __fastcall IsNgenPackageFileOnPhone(__int64 a1, unsigned int a2)
{
  __int64 v4; // rdi
  unsigned int v5; // ebp
  const WCHAR *v6; // rsi

  if ( a2 >= 0x36 )
  {
    v4 = 0;
    v5 = a2 - 54;
    while ( (unsigned int)v4 <= v5 )
    {
      v6 = (const WCHAR *)(a1 + 2 * v4);
      if ( !RtlCompareUnicodeStrings(
              v6,
              0x36u,
              L"\\ProgramData\\Microsoft\\Windows\\AppRepository\\Packages\\",
              0x36u,
              1u) )
      {
        if ( !v6 )
          return 0;
        return KappxpFindSubString(v6 + 54, a2 - (unsigned int)((2 * v4) >> 1) - 54, L"\\NI\\", 4) != 0;
      }
      v4 = (unsigned int)(v4 + 1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000dffc  push    rbx
0x18000dffe  push    rbp
0x18000dfff  push    rsi
0x18000e000  push    rdi
0x18000e001  push    r14
0x18000e003  sub     rsp, 30h
0x18000e007  mov     ebx, edx
0x18000e009  mov     r14, rcx
0x18000e00c  cmp     edx, 36h ; '6'
0x18000e00f  jb      short loc_18000E04F
0x18000e011  xor     edi, edi
0x18000e013  lea     ebp, [rdx-36h]
0x18000e016  cmp     edi, ebp
0x18000e018  ja      short loc_18000E04F
0x18000e01a  mov     r9d, 36h ; '6'; String2Length
0x18000e020  mov     [rsp+58h+CaseInSensitive], 1; CaseInSensitive
0x18000e025  lea     rsi, [r14+rdi*2]
0x18000e029  mov     edx, r9d; String1Length
0x18000e02c  mov     rcx, rsi; String1
0x18000e02f  lea     r8, aProgramdataMic; "\\ProgramData\\Microsoft\\Windows\\AppR"...
0x18000e036  call    cs:__imp_RtlCompareUnicodeStrings
0x18000e03d  nop     dword ptr [rax+rax+00h]
0x18000e042  test    eax, eax
0x18000e044  jz      short loc_18000E04A
0x18000e046  inc     edi
0x18000e048  jmp     short loc_18000E016
0x18000e04a  test    rsi, rsi
0x18000e04d  jnz     short loc_18000E05D
0x18000e04f  xor     al, al
0x18000e051  add     rsp, 30h
0x18000e055  pop     r14
0x18000e057  pop     rdi
0x18000e058  pop     rsi
0x18000e059  pop     rbp
0x18000e05a  pop     rbx
0x18000e05b  retn
0x18000e05d  mov     rax, rsi
0x18000e060  lea     rcx, [rsi+6Ch]
0x18000e064  sub     rax, r14
0x18000e067  lea     r8, aNi; "\\NI\\"
0x18000e06e  sar     rax, 1
0x18000e071  mov     r9d, 4
0x18000e077  sub     ebx, eax
0x18000e079  lea     edx, [rbx-36h]
0x18000e07c  call    KappxpFindSubString
0x18000e081  test    rax, rax
0x18000e084  setnz   al
0x18000e087  jmp     short loc_18000E051
```
