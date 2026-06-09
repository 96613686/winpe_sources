# UlpDeleteIpAddressFromList

- ea: `0x1c012d104`
- end: `0x1c012d2d8`
- name: `UlpDeleteIpAddressFromList`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1c012bf50`

## callees

- `0x1c00022d0`
- `0x1c001b640`
- `0x1c009f008`
- `0x1c00d8440`
- `0x1c012096c`
- `0x1c012d104`

## import_xrefs

- `ntoskrnl!ZwDeleteValueKey` at `0x1c012d285`
- `ntoskrnl!ZwDeleteValueKey` at `0x1c012d285`
- `ntoskrnl!wcsncmp` at `0x1c012d1e6`
- `ntoskrnl!wcsncmp` at `0x1c012d1e6`
- `ntoskrnl!ZwClose` at `0x1c012d29b`
- `ntoskrnl!ZwClose` at `0x1c012d29b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c012d2b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c012d2b1`

## string_xrefs

- `0x1c012d134`: `\Registry\Machine\System\CurrentControlSet\Services\Http\Parameters`

## pseudocode

```c
__int64 __fastcall UlpDeleteIpAddressFromList(__int64 a1, const wchar_t *a2, unsigned int a3)
{
  __int64 v3; // r13
  unsigned int v4; // r14d
  int v5; // eax
  HANDLE v6; // rbp
  int GenericParameter; // ebx
  __int64 v8; // rsi
  int v9; // r15d
  size_t v10; // r12
  __int64 v11; // r14
  const void *v12; // rdx
  ULONG v13; // r15d
  NTSTATUS v14; // eax
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-48h] BYREF
  HANDLE KeyHandle; // [rsp+98h] [rbp+20h] BYREF

  v3 = a3;
  KeyHandle = 0;
  v4 = a3 - 1;
  v5 = UxOpenKey(
         0,
         (__int64)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Http\\Parameters",
         134,
         0xF003Fu,
         0,
         &KeyHandle);
  v6 = KeyHandle;
  GenericParameter = v5;
  if ( v5 >= 0 )
  {
    GenericParameter = UlReadGenericParameter(KeyHandle);
    if ( GenericParameter >= 0 )
    {
      if ( MEMORY[4] != 7 )
      {
LABEL_4:
        GenericParameter = -1073741492;
        goto LABEL_22;
      }
      v8 = 12;
      v9 = MEMORY[8];
      GenericParameter = -1073741275;
      if ( MEMORY[0xC] )
      {
        v10 = v4;
        while ( 1 )
        {
          v11 = -1;
          do
            ++v11;
          while ( *(_WORD *)(v8 + 2 * v11) );
          if ( v11 == v10 && !wcsncmp((const wchar_t *)v8, a2, v10) )
            break;
          v8 += 2 * v11 + 2;
          if ( !*(_WORD *)v8 )
            goto LABEL_22;
        }
        v12 = (const void *)(v8 + 2 * v3);
        if ( (unsigned int)(v8 + 2 * v3 - 12) > MEMORY[8] )
          goto LABEL_4;
        v13 = -2 * v3 + v9;
        if ( MEMORY[8] - (_DWORD)v12 == -12 )
          *(_WORD *)v8 = 0;
        else
          memmove((void *)v8, v12, (unsigned int)(MEMORY[8] - (_DWORD)v12 + 12));
        if ( v13 <= 2 )
        {
          ValueName = 0;
          GenericParameter = UlInitUnicodeStringEx(&ValueName, L"ListenOnlyList");
          if ( GenericParameter < 0 )
            goto LABEL_22;
          v14 = ZwDeleteValueKey(v6, &ValueName);
        }
        else
        {
          v14 = UlSetRegistryValue(v6, v13);
        }
        GenericParameter = v14;
      }
    }
  }
LABEL_22:
  if ( v6 )
    ZwClose(v6);
  return (unsigned int)GenericParameter;
}

```

## disassembly

```asm
0x1c012d104  mov     r11, rsp
0x1c012d107  mov     [r11+18h], rbx
0x1c012d10b  mov     [r11+10h], rdx
0x1c012d10f  mov     [r11+8], rcx
0x1c012d113  push    rbp
0x1c012d114  push    rsi
0x1c012d115  push    rdi
0x1c012d116  push    r12
0x1c012d118  push    r13
0x1c012d11a  push    r14
0x1c012d11c  push    r15
0x1c012d11e  sub     rsp, 40h
0x1c012d122  xor     r12d, r12d
0x1c012d125  mov     r13d, r8d
0x1c012d128  lea     rax, [r11+20h]
0x1c012d12c  mov     [r11+8], r12
0x1c012d130  mov     [r11-50h], rax
0x1c012d134  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x1c012d13b  mov     r8d, 86h
0x1c012d141  mov     [r11+20h], r12
0x1c012d145  mov     r9d, 0F003Fh
0x1c012d14b  mov     [r11-58h], r12b
0x1c012d14f  xor     ecx, ecx
0x1c012d151  lea     r14d, [r13-1]
0x1c012d155  mov     edi, r12d
0x1c012d158  call    UxOpenKey
0x1c012d15d  mov     rbp, [rsp+78h+KeyHandle]
0x1c012d165  mov     ebx, eax
0x1c012d167  test    eax, eax
0x1c012d169  js      loc_1C012D293
0x1c012d16f  lea     r8, [rsp+78h+arg_0]
0x1c012d177  mov     rcx, rbp; KeyHandle
0x1c012d17a  lea     rdx, aListenonlylist; "ListenOnlyList"
0x1c012d181  call    UlReadGenericParameter
0x1c012d186  mov     rdi, [rsp+78h+arg_0]
0x1c012d18e  mov     ebx, eax
0x1c012d190  test    eax, eax
0x1c012d192  js      loc_1C012D293
0x1c012d198  cmp     dword ptr [rdi+4], 7
0x1c012d19c  jz      short loc_1C012D1A8
0x1c012d19e  mov     ebx, 0C000014Ch
0x1c012d1a3  jmp     loc_1C012D293
0x1c012d1a8  lea     rsi, [rdi+0Ch]
0x1c012d1ac  mov     r15d, [rdi+8]
0x1c012d1b0  mov     ebx, 0C0000225h
0x1c012d1b5  cmp     [rdi+0Ch], r12w
0x1c012d1ba  jz      loc_1C012D293
0x1c012d1c0  mov     r12d, r14d
0x1c012d1c3  xor     eax, eax
0x1c012d1c5  or      r14, 0FFFFFFFFFFFFFFFFh
0x1c012d1c9  inc     r14
0x1c012d1cc  cmp     [rsi+r14*2], ax
0x1c012d1d1  jnz     short loc_1C012D1C9
0x1c012d1d3  cmp     r14, r12
0x1c012d1d6  jnz     short loc_1C012D1F8
0x1c012d1d8  mov     rdx, [rsp+78h+Str2]; Str2
0x1c012d1e0  mov     r8, r12; MaxCount
0x1c012d1e3  mov     rcx, rsi; Str1
0x1c012d1e6  call    cs:__imp_wcsncmp
0x1c012d1ed  nop     dword ptr [rax+rax+00h]
0x1c012d1f2  test    eax, eax
0x1c012d1f4  jz      short loc_1C012D20A
0x1c012d1f6  xor     eax, eax
0x1c012d1f8  lea     rsi, [rsi+r14*2]
0x1c012d1fc  add     rsi, 2
0x1c012d200  cmp     [rsi], ax
0x1c012d203  jnz     short loc_1C012D1C5
0x1c012d205  jmp     loc_1C012D293
0x1c012d20a  mov     ecx, [rdi+8]
0x1c012d20d  lea     rdx, [rsi+r13*2]; Src
0x1c012d211  mov     eax, edx
0x1c012d213  sub     eax, edi
0x1c012d215  sub     eax, 0Ch
0x1c012d218  cmp     eax, ecx
0x1c012d21a  ja      short loc_1C012D19E
0x1c012d21c  imul    eax, r13d, -2
0x1c012d220  lea     r8d, [rdi+0Ch]
0x1c012d224  sub     ecx, edx
0x1c012d226  xor     r12d, r12d
0x1c012d229  add     r15d, eax
0x1c012d22c  add     r8d, ecx; Size
0x1c012d22f  jz      short loc_1C012D23B
0x1c012d231  mov     rcx, rsi; void *
0x1c012d234  call    memmove
0x1c012d239  jmp     short loc_1C012D23F
0x1c012d23b  mov     [rsi], r12w
0x1c012d23f  lea     rdx, aListenonlylist; "ListenOnlyList"
0x1c012d246  cmp     r15d, 2
0x1c012d24a  jbe     short loc_1C012D265
0x1c012d24c  lea     r9, [rdi+0Ch]
0x1c012d250  mov     [rsp+78h+var_58], r15d; ULONG
0x1c012d255  mov     r8d, 7
0x1c012d25b  mov     rcx, rbp; KeyHandle
0x1c012d25e  call    UlSetRegistryValue
0x1c012d263  jmp     short loc_1C012D291
0x1c012d265  xorps   xmm0, xmm0
0x1c012d268  lea     rcx, [rsp+78h+ValueName]
0x1c012d26d  movups  xmmword ptr [rsp+78h+ValueName.Length], xmm0
0x1c012d272  call    UlInitUnicodeStringEx
0x1c012d277  mov     ebx, eax
0x1c012d279  test    eax, eax
0x1c012d27b  js      short loc_1C012D293
0x1c012d27d  lea     rdx, [rsp+78h+ValueName]; ValueName
0x1c012d282  mov     rcx, rbp; KeyHandle
0x1c012d285  call    cs:__imp_ZwDeleteValueKey
0x1c012d28c  nop     dword ptr [rax+rax+00h]
0x1c012d291  mov     ebx, eax
0x1c012d293  test    rbp, rbp
0x1c012d296  jz      short loc_1C012D2A7
0x1c012d298  mov     rcx, rbp; Handle
0x1c012d29b  call    cs:__imp_ZwClose
0x1c012d2a2  nop     dword ptr [rax+rax+00h]
0x1c012d2a7  test    rdi, rdi
0x1c012d2aa  jz      short loc_1C012D2BD
0x1c012d2ac  xor     edx, edx; Tag
0x1c012d2ae  mov     rcx, rdi; P
0x1c012d2b1  call    cs:__imp_ExFreePoolWithTag
0x1c012d2b8  nop     dword ptr [rax+rax+00h]
0x1c012d2bd  mov     eax, ebx
0x1c012d2bf  mov     rbx, [rsp+78h+arg_10]
0x1c012d2c7  add     rsp, 40h
0x1c012d2cb  pop     r15
0x1c012d2cd  pop     r14
0x1c012d2cf  pop     r13
0x1c012d2d1  pop     r12
0x1c012d2d3  pop     rdi
0x1c012d2d4  pop     rsi
0x1c012d2d5  pop     rbp
0x1c012d2d6  retn
```
