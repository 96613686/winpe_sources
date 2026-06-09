# DirCacheShortNameKeyCompare

- ea: `0x1400194b0`
- end: `0x14001964e`
- name: `DirCacheShortNameKeyCompare`
- size: `414`
- prototype: `int __cdecl(void *, const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400194b0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1400195e8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400195e8`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400194ca`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400194ca`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001956e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140019591`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400195ae`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400195cd`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001956e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140019591`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400195ae`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400195cd`

## pseudocode

```c
LONG __fastcall DirCacheShortNameKeyCompare(_QWORD *a1, const UNICODE_STRING *a2, unsigned int *a3)
{
  unsigned int v3; // ebx
  CCHAR MostSignificantBit; // al
  __int64 v7; // r8
  unsigned int v8; // r9d
  unsigned int v9; // eax
  __int64 v10; // rdx
  UNICODE_STRING String1; // [rsp+20h] [rbp-18h] BYREF

  v3 = *a3;
  MostSignificantBit = RtlFindMostSignificantBit(*a3);
  v7 = 0;
  if ( MostSignificantBit <= 4 )
  {
    v8 = 0;
  }
  else
  {
    v8 = (unsigned int)(MostSignificantBit - 3) >> 1;
    if ( v8 >= 8 )
      goto LABEL_16;
  }
  _mm_lfence();
  v9 = v3;
  if ( v8 )
    v9 = v3 - (32 << (2 * v8 - 2));
  v10 = a1[v8 + 19];
  if ( v10 && v3 < *((_DWORD *)a1 + 54) )
  {
    v7 = v10 + (v9 << 7);
    goto LABEL_8;
  }
LABEL_16:
  __int2c();
LABEL_8:
  String1 = 0;
  String1.MaximumLength = 2 * (*(_WORD *)(v7 + 86) & 0xF);
  String1.Length = String1.MaximumLength;
  String1.Buffer = (PWSTR)(v7 + 88);
  if ( !RtlEqualUnicodeString(a2, &String2, 0) )
  {
    if ( RtlEqualUnicodeString(&String1, &String2, 0) )
      return 1;
    if ( !RtlEqualUnicodeString(a2, &stru_14003E010, 0) )
    {
      if ( !RtlEqualUnicodeString(&String1, &stru_14003E010, 0) )
        return RtlCompareUnicodeString(a2, &String1, 1u);
      return 1;
    }
  }
  return -1;
}

```

## disassembly

```asm
0x1400194b0  mov     [rsp+arg_0], rbx
0x1400194b5  mov     [rsp+arg_8], rsi
0x1400194ba  push    rdi
0x1400194bb  sub     rsp, 30h
0x1400194bf  mov     ebx, [r8]
0x1400194c2  mov     rdi, rcx
0x1400194c5  mov     ecx, ebx; Set
0x1400194c7  mov     rsi, rdx
0x1400194ca  call    cs:__imp_RtlFindMostSignificantBit
0x1400194d1  nop     dword ptr [rax+rax+00h]
0x1400194d6  xor     r8d, r8d
0x1400194d9  cmp     al, 4
0x1400194db  jle     loc_140019605
0x1400194e1  movsx   r9d, al
0x1400194e5  sub     r9d, 3
0x1400194e9  shr     r9d, 1
0x1400194ec  cmp     r9d, 8
0x1400194f0  jnb     loc_140019647
0x1400194f6  lfence
0x1400194f9  mov     eax, ebx
0x1400194fb  test    r9d, r9d
0x1400194fe  jz      short loc_140019511
0x140019500  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[r9*2]
0x140019508  mov     edx, 20h ; ' '
0x14001950d  shl     edx, cl
0x14001950f  sub     eax, edx
0x140019511  mov     ecx, r9d
0x140019514  mov     rdx, [rdi+rcx*8+98h]
0x14001951c  test    rdx, rdx
0x14001951f  jz      loc_140019639
0x140019525  cmp     ebx, [rdi+0D8h]
0x14001952b  jnb     loc_140019640
0x140019531  shl     eax, 7
0x140019534  mov     r8d, eax
0x140019537  add     r8, rdx
0x14001953a  xorps   xmm0, xmm0
0x14001953d  lea     rdx, String2; String2
0x140019544  movups  xmmword ptr [rsp+38h+String1.Length], xmm0
0x140019549  movzx   eax, word ptr [r8+56h]
0x14001954e  mov     rcx, rsi; String1
0x140019551  and     ax, 0Fh
0x140019555  add     ax, ax
0x140019558  mov     [rsp+38h+String1.MaximumLength], ax
0x14001955d  mov     [rsp+38h+String1.Length], ax
0x140019562  lea     rax, [r8+58h]
0x140019566  xor     r8d, r8d; CaseInSensitive
0x140019569  mov     [rsp+38h+String1.Buffer], rax
0x14001956e  call    cs:__imp_RtlEqualUnicodeString
0x140019575  nop     dword ptr [rax+rax+00h]
0x14001957a  test    al, al
0x14001957c  jnz     loc_140019623
0x140019582  xor     r8d, r8d; CaseInSensitive
0x140019585  lea     rdx, String2; String2
0x14001958c  lea     rcx, [rsp+38h+String1]; String1
0x140019591  call    cs:__imp_RtlEqualUnicodeString
0x140019598  nop     dword ptr [rax+rax+00h]
0x14001959d  test    al, al
0x14001959f  jnz     short loc_14001960D
0x1400195a1  xor     r8d, r8d; CaseInSensitive
0x1400195a4  lea     rdx, stru_14003E010; String2
0x1400195ab  mov     rcx, rsi; String1
0x1400195ae  call    cs:__imp_RtlEqualUnicodeString
0x1400195b5  nop     dword ptr [rax+rax+00h]
0x1400195ba  test    al, al
0x1400195bc  jnz     short loc_140019623
0x1400195be  xor     r8d, r8d; CaseInSensitive
0x1400195c1  lea     rdx, stru_14003E010; String2
0x1400195c8  lea     rcx, [rsp+38h+String1]; String1
0x1400195cd  call    cs:__imp_RtlEqualUnicodeString
0x1400195d4  nop     dword ptr [rax+rax+00h]
0x1400195d9  test    al, al
0x1400195db  jnz     short loc_14001960D
0x1400195dd  mov     r8b, 1; CaseInSensitive
0x1400195e0  lea     rdx, [rsp+38h+String1]; String2
0x1400195e5  mov     rcx, rsi; String1
0x1400195e8  call    cs:__imp_RtlCompareUnicodeString
0x1400195ef  nop     dword ptr [rax+rax+00h]
0x1400195f4  mov     rbx, [rsp+38h+arg_0]
0x1400195f9  mov     rsi, [rsp+38h+arg_8]
0x1400195fe  add     rsp, 30h
0x140019602  pop     rdi
0x140019603  retn
0x140019605  mov     r9d, r8d
0x140019608  jmp     loc_1400194F6
0x14001960d  mov     eax, 1
0x140019612  mov     rbx, [rsp+38h+arg_0]
0x140019617  mov     rsi, [rsp+38h+arg_8]
0x14001961c  add     rsp, 30h
0x140019620  pop     rdi
0x140019621  retn
0x140019623  mov     rbx, [rsp+38h+arg_0]
0x140019628  mov     eax, 0FFFFFFFFh
0x14001962d  mov     rsi, [rsp+38h+arg_8]
0x140019632  add     rsp, 30h
0x140019636  pop     rdi
0x140019637  retn
0x140019639  int     2Ch; Windows NT - assertion failure
0x14001963b  jmp     loc_14001953A
0x140019640  int     2Ch; Windows NT - assertion failure
0x140019642  jmp     loc_14001953A
0x140019647  int     2Ch; Windows NT - assertion failure
0x140019649  jmp     loc_14001953A
```
