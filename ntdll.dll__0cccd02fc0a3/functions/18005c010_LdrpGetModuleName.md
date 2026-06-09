# LdrpGetModuleName

- ea: `0x18005c010`
- end: `0x18005c247`
- name: `LdrpGetModuleName`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800f7a00`

## callees

- `0x180023350`
- `0x18005b470`
- `0x18005c010`
- `0x18005c250`
- `0x18005c5c0`
- `0x180127e50`
- `0x180162000`
- `0x18016f020`

## string_xrefs

- `0x18005c1ab`: `\system32`

## pseudocode

```c
NTSTATUS __fastcall LdrpGetModuleName(__int64 *a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v5; // rcx
  unsigned __int16 v6; // bx
  bool v7; // cf
  __int64 v10; // rdx
  __int64 (__fastcall *v11)(__int64, __int64, wchar_t *, _QWORD, _QWORD *); // rax
  NTSTATUS result; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  char *v16; // rax
  __int16 v17; // dx
  const wchar_t *NtSystemRoot; // rax
  __int64 v19; // rcx
  size_t v20; // rdi
  __int64 v21; // rcx
  _WORD v22[8]; // [rsp+30h] [rbp-D0h] BYREF
  UNICODE_STRING SourceString; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v24[2]; // [rsp+50h] [rbp-B0h] BYREF
  STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t String1[264]; // [rsp+70h] [rbp-90h] BYREF

  v5 = *a1;
  v6 = 512;
  v7 = *(_WORD *)a2 < 0x200u;
  *(_DWORD *)(&DestinationString.MaximumLength + 1) = 0;
  if ( v7 )
    v6 = *(_WORD *)a2;
  v10 = *(_QWORD *)(a2 + 8);
  v11 = (__int64 (__fastcall *)(__int64, __int64, wchar_t *, _QWORD, _QWORD *))a1[1];
  *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
  v22[0] = 0;
  v24[0] = 0;
  result = v11(v5, v10, String1, v6, v24);
  if ( result >= 0 )
  {
    if ( v24[0] == v6 )
    {
      String1[256] = 0;
      if ( !a4 )
        goto LABEL_6;
      NtSystemRoot = (const wchar_t *)RtlGetNtSystemRoot(v14, v13, v15);
      v19 = -1;
      do
        ++v19;
      while ( NtSystemRoot[v19] );
      if ( !v19 )
        return -1073741595;
      v20 = v19 - 1;
      if ( NtSystemRoot[v19 - 1] != 92 )
        v20 = v19;
      if ( wcsnicmp(String1, NtSystemRoot, v20) || wcsnicmp(&String1[v20], L"\\system32", 9u) )
        goto LABEL_6;
      if ( v20 + 16 >= 0x101 )
        return -1073741595;
      v21 = *a1;
      if ( !*a1 )
        v21 = -1;
      if ( (int)RtlWow64GetProcessMachines(v21, v22, 0) >= 0
        && (SourceString.Buffer = String1,
            SourceString.MaximumLength = v6,
            SourceString.Length = v6,
            HIDWORD(v24[0]) = *(_DWORD *)(&SourceString.MaximumLength + 1),
            LOWORD(v24[0]) = v6 - 2 * v20,
            WORD1(v24[0]) = v24[0],
            v24[1] = &String1[v20],
            (int)RtlReplaceSystemDirectoryInPath(v24, 1, v22[0], 0) >= 0) )
      {
LABEL_6:
        SourceString.MaximumLength = v6;
        SourceString.Buffer = String1;
        SourceString.Length = v6;
        DestinationString.Buffer = (char *)(a3 + 40);
        *(_DWORD *)&DestinationString.Length = 0x1000000;
        result = RtlUnicodeStringToAnsiString(&DestinationString, &SourceString, 0);
        if ( result >= 0 )
        {
          v16 = &DestinationString.Buffer[DestinationString.Length];
          do
          {
            v17 = (__int16)v16;
            if ( v16 <= DestinationString.Buffer )
              break;
            --v16;
          }
          while ( *v16 != 92 );
          *(_WORD *)(a3 + 38) = v17 - LOWORD(DestinationString.Buffer);
          return 0;
        }
      }
      else
      {
        return -1073741595;
      }
    }
    else
    {
      return -2147483635;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005c010  push    rbp
0x18005c012  push    rbx
0x18005c013  push    rsi
0x18005c014  push    rdi
0x18005c015  push    r12
0x18005c017  push    r14
0x18005c019  push    r15
0x18005c01b  lea     rbp, [rsp-190h]
0x18005c023  sub     rsp, 290h
0x18005c02a  mov     rax, cs:__security_cookie
0x18005c031  xor     rax, rsp
0x18005c034  mov     [rbp+1C0h+var_40], rax
0x18005c03b  xor     r12d, r12d
0x18005c03e  lea     rax, [rsp+2C0h+var_270]
0x18005c043  mov     r15, rcx
0x18005c046  mov     [rsp+2C0h+var_2A0], rax
0x18005c04b  mov     rcx, [rcx]
0x18005c04e  mov     ebx, 200h
0x18005c053  cmp     [rdx], bx
0x18005c056  mov     r14d, r9d
0x18005c059  mov     rsi, r8
0x18005c05c  mov     dword ptr [rsp+2C0h+DestinationString+4], r12d
0x18005c061  cmovb   bx, [rdx]
0x18005c065  lea     r8, [rsp+2C0h+String1]
0x18005c06a  mov     rdx, [rdx+8]
0x18005c06e  mov     rax, [r15+8]
0x18005c072  movzx   edi, bx
0x18005c075  mov     r9d, edi
0x18005c078  mov     dword ptr [rsp+2C0h+SourceString+4], r12d
0x18005c07d  mov     [rsp+2C0h+var_290], r12w
0x18005c083  mov     qword ptr [rsp+2C0h+var_270], r12
0x18005c088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c08d  test    eax, eax
0x18005c08f  js      loc_18005C122
0x18005c095  cmp     qword ptr [rsp+2C0h+var_270], rdi
0x18005c09a  jnz     loc_18005C144
0x18005c0a0  mov     [rsp+2C0h+arg_18], r13
0x18005c0a8  mov     [rbp+1C0h+var_50], r12w
0x18005c0b0  test    r14d, r14d
0x18005c0b3  jnz     loc_18005C14B
0x18005c0b9  lea     rax, [rsp+2C0h+String1]
0x18005c0be  mov     [rsp+2C0h+SourceString.MaximumLength], bx
0x18005c0c3  mov     [rsp+2C0h+SourceString.Buffer], rax
0x18005c0c8  lea     rdx, [rsp+2C0h+SourceString]; SourceString
0x18005c0cd  lea     rax, [rsi+28h]
0x18005c0d1  mov     [rsp+2C0h+SourceString.Length], bx
0x18005c0d6  xor     r8d, r8d; AllocateDestinationString
0x18005c0d9  mov     [rsp+2C0h+DestinationString.Buffer], rax
0x18005c0de  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x18005c0e3  mov     dword ptr [rsp+2C0h+DestinationString.Length], 1000000h
0x18005c0eb  call    RtlUnicodeStringToAnsiString
0x18005c0f0  test    eax, eax
0x18005c0f2  js      short loc_18005C11A
0x18005c0f4  movzx   eax, [rsp+2C0h+DestinationString.Length]
0x18005c0f9  mov     rcx, [rsp+2C0h+DestinationString.Buffer]
0x18005c0fe  add     rax, rcx
0x18005c101  movzx   edx, ax
0x18005c104  cmp     rax, rcx
0x18005c107  jbe     short loc_18005C111
0x18005c109  dec     rax
0x18005c10c  cmp     byte ptr [rax], 5Ch ; '\'
0x18005c10f  jnz     short loc_18005C101
0x18005c111  sub     dx, cx
0x18005c114  mov     [rsi+26h], dx
0x18005c118  xor     eax, eax
0x18005c11a  mov     r13, [rsp+2C0h+arg_18]
0x18005c122  mov     rcx, [rbp+1C0h+var_40]
0x18005c129  xor     rcx, rsp; StackCookie
0x18005c12c  call    __security_check_cookie
0x18005c131  add     rsp, 290h
0x18005c138  pop     r15
0x18005c13a  pop     r14
0x18005c13c  pop     r12
0x18005c13e  pop     rdi
0x18005c13f  pop     rsi
0x18005c140  pop     rbx
0x18005c141  pop     rbp
0x18005c142  retn
0x18005c144  mov     eax, 8000000Dh
0x18005c149  jmp     short loc_18005C122
0x18005c14b  call    RtlGetNtSystemRoot
0x18005c150  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18005c157  mov     rcx, r13
0x18005c15a  nop     word ptr [rax+rax+00h]
0x18005c160  inc     rcx
0x18005c163  cmp     [rax+rcx*2], r12w
0x18005c168  jnz     short loc_18005C160
0x18005c16a  test    rcx, rcx
0x18005c16d  jz      loc_18005C23D
0x18005c173  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18005c179  lea     rdi, [rcx-1]
0x18005c17d  mov     rdx, rax; String2
0x18005c180  cmovnz  rdi, rcx
0x18005c184  lea     rcx, [rsp+2C0h+String1]; String1
0x18005c189  mov     r8, rdi; MaxCount
0x18005c18c  call    _wcsnicmp
0x18005c191  test    eax, eax
0x18005c193  jnz     loc_18005C0B9
0x18005c199  lea     r14, [rsp+2C0h+String1]
0x18005c19e  mov     r8d, 9; MaxCount
0x18005c1a4  lea     r14, [r14+rdi*2]
0x18005c1a8  mov     rcx, r14; String1
0x18005c1ab  lea     rdx, aSystem32_1; "\\system32"
0x18005c1b2  call    _wcsnicmp
0x18005c1b7  test    eax, eax
0x18005c1b9  jnz     loc_18005C0B9
0x18005c1bf  lea     rax, [rdi+10h]
0x18005c1c3  cmp     rax, 101h
0x18005c1c9  jnb     short loc_18005C23D
0x18005c1cb  mov     rcx, [r15]
0x18005c1ce  lea     rdx, [rsp+2C0h+var_290]
0x18005c1d3  test    rcx, rcx
0x18005c1d6  cmovz   rcx, r13
0x18005c1da  xor     r8d, r8d
0x18005c1dd  call    RtlWow64GetProcessMachines
0x18005c1e2  test    eax, eax
0x18005c1e4  js      short loc_18005C23D
0x18005c1e6  movzx   r8d, [rsp+2C0h+var_290]
0x18005c1ec  lea     rax, [rsp+2C0h+String1]
0x18005c1f1  mov     [rsp+2C0h+SourceString.Buffer], rax
0x18005c1f6  lea     rcx, [rsp+2C0h+var_270]
0x18005c1fb  movzx   eax, bx
0x18005c1fe  mov     [rsp+2C0h+SourceString.MaximumLength], bx
0x18005c203  mov     [rsp+2C0h+SourceString.Length], bx
0x18005c208  add     di, di
0x18005c20b  movaps  xmm0, xmmword ptr [rsp+2C0h+SourceString.Length]
0x18005c210  sub     ax, di
0x18005c213  movdqa  [rsp+2C0h+var_270], xmm0
0x18005c219  mov     edx, 1
0x18005c21e  xor     r9d, r9d
0x18005c221  mov     word ptr [rsp+2C0h+var_270], ax
0x18005c226  mov     word ptr [rsp+2C0h+var_270+2], ax
0x18005c22b  mov     qword ptr [rsp+2C0h+var_270+8], r14
0x18005c230  call    RtlReplaceSystemDirectoryInPath
0x18005c235  test    eax, eax
0x18005c237  jns     loc_18005C0B9
0x18005c23d  mov     eax, 0C00000E5h
0x18005c242  jmp     loc_18005C11A
```
