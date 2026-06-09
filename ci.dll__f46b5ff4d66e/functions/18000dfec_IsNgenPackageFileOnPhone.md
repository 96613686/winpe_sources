# IsNgenPackageFileOnPhone

- ea: `0x18000dfec`
- end: `0x18000e079`
- name: `IsNgenPackageFileOnPhone`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800a6380`

## callees

- `0x18000aa30`
- `0x18000dfec`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeStrings` at `0x18000e026`
- `ntoskrnl!RtlCompareUnicodeStrings` at `0x18000e026`

## string_xrefs

- `0x18000e01f`: `\ProgramData\Microsoft\Windows\AppRepository\Packages\`

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
0x18000dfec  push    rbx
0x18000dfee  push    rbp
0x18000dfef  push    rsi
0x18000dff0  push    rdi
0x18000dff1  push    r14
0x18000dff3  sub     rsp, 30h
0x18000dff7  mov     ebx, edx
0x18000dff9  mov     r14, rcx
0x18000dffc  cmp     edx, 36h ; '6'
0x18000dfff  jb      short loc_18000E03F
0x18000e001  xor     edi, edi
0x18000e003  lea     ebp, [rdx-36h]
0x18000e006  cmp     edi, ebp
0x18000e008  ja      short loc_18000E03F
0x18000e00a  mov     r9d, 36h ; '6'; String2Length
0x18000e010  mov     [rsp+58h+CaseInSensitive], 1; CaseInSensitive
0x18000e015  lea     rsi, [r14+rdi*2]
0x18000e019  mov     edx, r9d; String1Length
0x18000e01c  mov     rcx, rsi; String1
0x18000e01f  lea     r8, aProgramdataMic; "\\ProgramData\\Microsoft\\Windows\\AppR"...
0x18000e026  call    cs:__imp_RtlCompareUnicodeStrings
0x18000e02d  nop     dword ptr [rax+rax+00h]
0x18000e032  test    eax, eax
0x18000e034  jz      short loc_18000E03A
0x18000e036  inc     edi
0x18000e038  jmp     short loc_18000E006
0x18000e03a  test    rsi, rsi
0x18000e03d  jnz     short loc_18000E04D
0x18000e03f  xor     al, al
0x18000e041  add     rsp, 30h
0x18000e045  pop     r14
0x18000e047  pop     rdi
0x18000e048  pop     rsi
0x18000e049  pop     rbp
0x18000e04a  pop     rbx
0x18000e04b  retn
0x18000e04d  mov     rax, rsi
0x18000e050  lea     rcx, [rsi+6Ch]
0x18000e054  sub     rax, r14
0x18000e057  lea     r8, aNi; "\\NI\\"
0x18000e05e  sar     rax, 1
0x18000e061  mov     r9d, 4
0x18000e067  sub     ebx, eax
0x18000e069  lea     edx, [rbx-36h]
0x18000e06c  call    KappxpFindSubString
0x18000e071  test    rax, rax
0x18000e074  setnz   al
0x18000e077  jmp     short loc_18000E041
```
