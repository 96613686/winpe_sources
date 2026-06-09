# DfscCompareStringsIgnoreTrailingChars

- ea: `0x1400238c0`
- end: `0x1400239a6`
- name: `DfscCompareStringsIgnoreTrailingChars`
- size: `230`
- prototype: `__int64 __fastcall(UNICODE_STRING *, UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140028680`

## callees

- `0x1400238c0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14002396d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14002396d`

## pseudocode

```c
__int64 __fastcall DfscCompareStringsIgnoreTrailingChars(UNICODE_STRING *a1, UNICODE_STRING *a2)
{
  unsigned __int16 v2; // ax
  unsigned __int16 v4; // r8
  WCHAR v5; // dx
  WCHAR v6; // dx
  UNICODE_STRING String2; // [rsp+20h] [rbp-28h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-18h] BYREF

  v2 = a2->Length >> 1;
  v4 = a1->Length >> 1;
  String1 = 0;
  for ( String2 = 0; v4; --v4 )
  {
    v5 = a1->Buffer[v4 - 1];
    if ( v5 != 92 && v5 )
      break;
  }
  if ( v2 )
  {
    while ( 1 )
    {
      v6 = a2->Buffer[v2 - 1];
      if ( v6 != 92 )
      {
        if ( v6 )
          break;
      }
      if ( !--v2 )
        return !v4;
    }
    if ( v2 == v4 )
    {
      if ( v4 )
      {
        String1 = *a1;
        String1.Length = 2 * v4;
        String2 = *a2;
        String2.Length = 2 * v2;
        if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
          return 1;
      }
    }
    return 0;
  }
  return !v4;
}

```

## disassembly

```asm
0x1400238c0  push    rbx
0x1400238c2  sub     rsp, 40h
0x1400238c6  movzx   eax, word ptr [rdx]
0x1400238c9  xorps   xmm0, xmm0
0x1400238cc  movzx   r8d, word ptr [rcx]
0x1400238d0  xorps   xmm1, xmm1
0x1400238d3  shr     ax, 1
0x1400238d6  mov     r10, rdx
0x1400238d9  shr     r8w, 1
0x1400238dd  mov     r11, rcx
0x1400238e0  movups  xmmword ptr [rsp+48h+String1.Length], xmm0
0x1400238e5  mov     ebx, 0FFFFh
0x1400238ea  movups  xmmword ptr [rsp+48h+String2.Length], xmm1
0x1400238ef  jz      short loc_14002390A
0x1400238f1  mov     r9, [rcx+8]
0x1400238f5  movzx   ecx, r8w
0x1400238f9  movzx   edx, word ptr [r9+rcx*2-2]
0x1400238ff  cmp     dx, 5Ch ; '\'
0x140023903  jz      short loc_14002397F
0x140023905  test    dx, dx
0x140023908  jz      short loc_14002397F
0x14002390a  test    ax, ax
0x14002390d  jz      short loc_14002398E
0x14002390f  mov     r9, [r10+8]
0x140023913  movzx   ecx, ax
0x140023916  movzx   edx, word ptr [r9+rcx*2-2]
0x14002391c  cmp     dx, 5Ch ; '\'
0x140023920  jz      short loc_14002399B
0x140023922  test    dx, dx
0x140023925  jz      short loc_14002399B
0x140023927  cmp     ax, r8w
0x14002392b  jz      short loc_140023936
0x14002392d  xor     eax, eax
0x14002392f  add     rsp, 40h
0x140023933  pop     rbx
0x140023934  retn
0x140023936  test    r8w, r8w
0x14002393a  jz      short loc_14002392D
0x14002393c  movups  xmm0, xmmword ptr [r11]
0x140023940  add     r8w, r8w
0x140023944  lea     rdx, [rsp+48h+String2]; String2
0x140023949  add     ax, ax
0x14002394c  lea     rcx, [rsp+48h+String1]; String1
0x140023951  movups  xmmword ptr [rsp+48h+String1.Length], xmm0
0x140023956  mov     [rsp+48h+String1.Length], r8w
0x14002395c  mov     r8b, 1; CaseInSensitive
0x14002395f  movups  xmm0, xmmword ptr [r10]
0x140023963  movups  xmmword ptr [rsp+48h+String2.Length], xmm0
0x140023968  mov     [rsp+48h+String2.Length], ax
0x14002396d  call    cs:__imp_RtlCompareUnicodeString
0x140023974  nop     dword ptr [rax+rax+00h]
0x140023979  test    eax, eax
0x14002397b  jnz     short loc_14002392D
0x14002397d  jmp     short loc_140023994
0x14002397f  add     r8w, bx
0x140023983  jnz     loc_1400238F5
0x140023989  jmp     loc_14002390A
0x14002398e  test    r8w, r8w
0x140023992  jnz     short loc_14002392D
0x140023994  mov     eax, 1
0x140023999  jmp     short loc_14002392F
0x14002399b  add     ax, bx
0x14002399e  jnz     loc_140023913
0x1400239a4  jmp     short loc_14002398E
```
