# TlmiRemoveCommandLineArgs

- ea: `0x18001ade0`
- end: `0x18001ae91`
- name: `TlmiRemoveCommandLineArgs`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018564`

## callees

- `0x18001ade0`

## import_xrefs

- `ntdll!RtlPrefixUnicodeString` at `0x18001ae30`
- `ntdll!RtlPrefixUnicodeString` at `0x18001ae30`

## pseudocode

```c
char __fastcall TlmiRemoveCommandLineArgs(__m128i *a1)
{
  WCHAR *v1; // rax
  int v3; // edi
  USHORT v4; // ax
  PWSTR Buffer; // rcx
  USHORT MaximumLength; // dx
  UNICODE_STRING String2; // [rsp+20h] [rbp-10h] BYREF

  v1 = (WCHAR *)(a1->m128i_i64[1] + 2);
  *(_QWORD *)&String2.Length = a1->m128i_i64[0];
  String2.Length -= 2;
  String2.MaximumLength -= 2;
  String2.Buffer = v1;
  v3 = 0;
  while ( 1 )
  {
    LOBYTE(v4) = RtlPrefixUnicodeString((PCUNICODE_STRING)&asc_18002A710[8 * v3], &String2, 1u);
    if ( (_BYTE)v4 )
      break;
    if ( (unsigned int)++v3 >= 2 )
    {
      v4 = _mm_cvtsi128_si32(*a1);
      String2 = (UNICODE_STRING)*a1;
      if ( v4 )
      {
        Buffer = String2.Buffer;
        MaximumLength = String2.MaximumLength;
        do
        {
          if ( *Buffer == 32 )
            break;
          ++Buffer;
          v4 -= 2;
          MaximumLength -= 2;
          String2.Buffer = Buffer;
          String2.Length = v4;
          String2.MaximumLength = MaximumLength;
        }
        while ( v4 );
      }
      a1->m128i_i16[0] -= v4;
      return v4;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001ade0  push    rbp
0x18001ade2  push    rbx
0x18001ade3  push    rsi
0x18001ade4  push    rdi
0x18001ade5  push    r14
0x18001ade7  mov     rbp, rsp
0x18001adea  sub     rsp, 30h
0x18001adee  movups  xmm0, xmmword ptr [rcx]
0x18001adf1  mov     rax, [rcx+8]
0x18001adf5  mov     r14d, 0FFFEh
0x18001adfb  add     rax, 2
0x18001adff  mov     rbx, rcx
0x18001ae02  movups  xmmword ptr [rbp+String2.Length], xmm0
0x18001ae06  add     [rbp+String2.Length], r14w
0x18001ae0b  add     [rbp+String2.MaximumLength], r14w
0x18001ae10  xor     esi, esi
0x18001ae12  mov     [rbp+String2.Buffer], rax
0x18001ae16  mov     edi, esi
0x18001ae18  lea     rax, asc_18002A710; "<>"
0x18001ae1f  movsxd  rcx, edi
0x18001ae22  shl     rcx, 4
0x18001ae26  lea     rdx, [rbp+String2]; String2
0x18001ae2a  add     rcx, rax; String1
0x18001ae2d  mov     r8b, 1; CaseInsensitive
0x18001ae30  call    cs:__imp_RtlPrefixUnicodeString
0x18001ae37  nop     dword ptr [rax+rax+00h]
0x18001ae3c  test    al, al
0x18001ae3e  jnz     short loc_18001AE85
0x18001ae40  inc     edi
0x18001ae42  cmp     edi, 2
0x18001ae45  jb      short loc_18001AE18
0x18001ae47  movups  xmm0, xmmword ptr [rbx]
0x18001ae4a  movd    eax, xmm0
0x18001ae4e  movups  xmmword ptr [rbp+String2.Length], xmm0
0x18001ae52  test    ax, ax
0x18001ae55  jz      short loc_18001AE82
0x18001ae57  mov     rcx, [rbp+String2.Buffer]
0x18001ae5b  movzx   edx, [rbp+String2.MaximumLength]
0x18001ae5f  cmp     word ptr [rcx], 20h ; ' '
0x18001ae63  jz      short loc_18001AE82
0x18001ae65  add     rcx, 2
0x18001ae69  add     ax, r14w
0x18001ae6d  add     dx, r14w
0x18001ae71  mov     [rbp+String2.Buffer], rcx
0x18001ae75  mov     [rbp+String2.Length], ax
0x18001ae79  mov     [rbp+String2.MaximumLength], dx
0x18001ae7d  test    ax, ax
0x18001ae80  jnz     short loc_18001AE5F
0x18001ae82  sub     [rbx], ax
0x18001ae85  add     rsp, 30h
0x18001ae89  pop     r14
0x18001ae8b  pop     rdi
0x18001ae8c  pop     rsi
0x18001ae8d  pop     rbx
0x18001ae8e  pop     rbp
0x18001ae8f  retn
```
