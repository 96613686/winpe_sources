# WriteObject

- ea: `0x18003a054`
- end: `0x18003a11b`
- name: `WriteObject`
- size: `199`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `27`
- callee_count: `3`
- tags: ``

## callers

- `0x180030440`
- `0x1800306f0`
- `0x1800308a4`
- `0x180030ab8`
- `0x180031a00`
- `0x180031cd4`
- `0x1800325cc`
- `0x180032dd8`
- `0x1800333e4`
- `0x180033a1c`
- `0x180033a84`
- `0x1800346a4`
- `0x180034c80`
- `0x180034f88`
- `0x180035f30`
- `0x1800367f0`
- `0x180036f50`
- `0x180037340`
- `0x180038458`
- `0x1800387e4`
- `0x1800388e8`
- `0x180038b98`
- `0x180038cf8`
- `0x180038f0c`
- `0x1800390c8`
- `0x180039d74`
- `0x180039ff8`

## callees

- `0x18002b058`
- `0x1800391bc`
- `0x18003a054`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a106`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a106`

## pseudocode

```c
__int64 __fastcall WriteObject(_BYTE **a1, unsigned int *a2, const char *a3)
{
  unsigned int v3; // r11d
  const char *v4; // rsi
  unsigned __int64 v7; // r11
  _BYTE *v8; // rcx
  DWORD v9; // ecx
  __int64 v10; // rax
  unsigned int v11; // ebx
  _BYTE *v12; // rax
  __int64 v13; // rax
  ULONG pulResult; // [rsp+48h] [rbp+10h] BYREF
  ULONGLONG ullOperand; // [rsp+58h] [rbp+20h] BYREF

  v3 = *a2;
  v4 = a3;
  ullOperand = 0;
  pulResult = 0;
  if ( StringCchLengthA(a3, v3, &ullOperand) < 0 || ULongLongToULong(ullOperand, &pulResult) < 0 )
  {
    v9 = 87;
    goto LABEL_16;
  }
  if ( !v7 )
  {
LABEL_6:
    v9 = 122;
LABEL_16:
    v11 = 0;
    SetLastError(v9);
    return v11;
  }
  v8 = *a1;
  if ( v7 > 0x7FFFFFFF )
  {
    *v8 = 0;
    goto LABEL_6;
  }
  v10 = 2147483646;
  v11 = 1;
  do
  {
    if ( !v10 )
      break;
    if ( !*v4 )
      break;
    *v8++ = *v4++;
    --v10;
    --v7;
  }
  while ( v7 );
  v12 = v8 - 1;
  if ( v7 )
    v12 = v8;
  *v12 = 0;
  if ( !v7 )
    goto LABEL_6;
  v13 = pulResult;
  *a2 -= pulResult;
  *a1 += v13;
  return v11;
}

```

## disassembly

```asm
0x18003a054  mov     rax, rsp
0x18003a057  mov     [rax+8], rbx
0x18003a05b  push    rbp
0x18003a05c  push    rsi
0x18003a05d  push    rdi
0x18003a05e  sub     rsp, 20h
0x18003a062  mov     r11d, [rdx]
0x18003a065  mov     rsi, r8
0x18003a068  mov     rbp, rdx
0x18003a06b  mov     qword ptr [rax+20h], 0
0x18003a073  mov     rdi, rcx
0x18003a076  mov     dword ptr [rax+10h], 0
0x18003a07d  mov     edx, r11d; cchMax
0x18003a080  lea     r8, [rax+20h]; pcchLength
0x18003a084  mov     rcx, rsi; psz
0x18003a087  call    StringCchLengthA
0x18003a08c  test    eax, eax
0x18003a08e  js      short loc_18003A0FF
0x18003a090  mov     rcx, [rsp+38h+ullOperand]; ullOperand
0x18003a095  lea     rdx, [rsp+38h+pulResult]; pulResult
0x18003a09a  call    ULongLongToULong
0x18003a09f  test    eax, eax
0x18003a0a1  js      short loc_18003A0FF
0x18003a0a3  test    r11, r11
0x18003a0a6  jz      short loc_18003A0B7
0x18003a0a8  mov     rcx, [rdi]
0x18003a0ab  cmp     r11, 7FFFFFFFh
0x18003a0b2  jbe     short loc_18003A0BE
0x18003a0b4  mov     byte ptr [rcx], 0
0x18003a0b7  mov     ecx, 7Ah ; 'z'
0x18003a0bc  jmp     short loc_18003A104
0x18003a0be  mov     eax, 7FFFFFFEh
0x18003a0c3  mov     ebx, 1
0x18003a0c8  test    rax, rax
0x18003a0cb  jz      short loc_18003A0E3
0x18003a0cd  mov     dl, [rsi]
0x18003a0cf  test    dl, dl
0x18003a0d1  jz      short loc_18003A0E3
0x18003a0d3  mov     [rcx], dl
0x18003a0d5  add     rsi, rbx
0x18003a0d8  add     rcx, rbx
0x18003a0db  sub     rax, rbx
0x18003a0de  sub     r11, rbx
0x18003a0e1  jnz     short loc_18003A0C8
0x18003a0e3  test    r11, r11
0x18003a0e6  lea     rax, [rcx-1]
0x18003a0ea  cmovnz  rax, rcx
0x18003a0ee  mov     byte ptr [rax], 0
0x18003a0f1  jz      short loc_18003A0B7
0x18003a0f3  mov     eax, [rsp+38h+pulResult]
0x18003a0f7  sub     [rbp+0], eax
0x18003a0fa  add     [rdi], rax
0x18003a0fd  jmp     short loc_18003A10C
0x18003a0ff  mov     ecx, 57h ; 'W'; dwErrCode
0x18003a104  xor     ebx, ebx
0x18003a106  call    cs:__imp_SetLastError
0x18003a10c  mov     eax, ebx
0x18003a10e  mov     rbx, [rsp+38h+arg_0]
0x18003a113  add     rsp, 20h
0x18003a117  pop     rdi
0x18003a118  pop     rsi
0x18003a119  pop     rbp
0x18003a11a  retn
```
