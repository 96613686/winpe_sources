# RtlStringCbCopyW

- ea: `0x140003ec0`
- end: `0x140003f18`
- name: `RtlStringCbCopyW`
- size: `88`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140013908`
- `0x140013cbc`

## callees

- `0x140003ec0`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCbCopyW(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszSrc)
{
  __int64 v3; // rax
  const wchar_t *v4; // rdx
  __int64 v5; // r8
  NTSTRSAFE_PWSTR v6; // rdx
  NTSTATUS result; // eax

  v3 = 2147483646;
  v4 = L"\\??\\X:";
  v5 = 25;
  do
  {
    if ( !v3 )
      break;
    if ( !*v4 )
      break;
    *pszDest++ = *v4++;
    --v3;
    --v5;
  }
  while ( v5 );
  v6 = pszDest - 1;
  result = v5 == 0 ? 0x80000005 : 0;
  if ( v5 )
    v6 = pszDest;
  *v6 = 0;
  return result;
}

```

## disassembly

```asm
0x140003ec0  mov     eax, 7FFFFFFEh
0x140003ec5  lea     rdx, asc_140008CF8; "\\??\\X:"
0x140003ecc  mov     r8d, 19h
0x140003ed2  xor     r10d, r10d
0x140003ed5  test    rax, rax
0x140003ed8  jz      short loc_140003EF9
0x140003eda  movzx   r9d, word ptr [rdx]
0x140003ede  test    r9w, r9w
0x140003ee2  jz      short loc_140003EF9
0x140003ee4  mov     [rcx], r9w
0x140003ee8  add     rdx, 2
0x140003eec  add     rcx, 2
0x140003ef0  dec     rax
0x140003ef3  sub     r8, 1
0x140003ef7  jnz     short loc_140003ED5
0x140003ef9  mov     rax, r8
0x140003efc  lea     rdx, [rcx-2]
0x140003f00  neg     rax
0x140003f03  sbb     eax, eax
0x140003f05  not     eax
0x140003f07  and     eax, 80000005h
0x140003f0c  test    r8, r8
0x140003f0f  cmovnz  rdx, rcx
0x140003f13  mov     [rdx], r10w
0x140003f17  retn
```
