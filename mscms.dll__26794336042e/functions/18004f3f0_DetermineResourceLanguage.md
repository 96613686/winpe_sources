# DetermineResourceLanguage

- ea: `0x18004f3f0`
- end: `0x18004f49b`
- name: `DetermineResourceLanguage`
- size: `171`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18004ee44`

## callees

- `0x18002e670`
- `0x18002f2dc`
- `0x18004f3f0`

## import_xrefs

- `ntdll!RtlLcidToLocaleName` at `0x18004f41f`
- `ntdll!RtlLcidToLocaleName` at `0x18004f41f`
- `ntdll!RtlFreeUnicodeString` at `0x18004f489`
- `ntdll!RtlFreeUnicodeString` at `0x18004f489`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18004f404`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18004f404`

## pseudocode

```c
__int64 __fastcall DetermineResourceLanguage(_QWORD *a1)
{
  LCID ThreadLocale; // eax
  __int64 v3; // r9
  int v4; // esi
  unsigned int v5; // esi
  __int64 v6; // rdi
  _WORD *v7; // rax
  size_t Length; // r8
  PWSTR Buffer; // rdx
  _WORD *v10; // rbx
  struct _UNICODE_STRING Src; // [rsp+20h] [rbp-38h] BYREF

  *a1 = 0;
  ThreadLocale = GetThreadLocale();
  LOBYTE(v3) = 1;
  Src = 0;
  v4 = RtlLcidToLocaleName(ThreadLocale, &Src, 0, v3);
  if ( v4 >= 0 )
  {
    v5 = 0;
    v6 = Src.Length >> 1;
    v7 = operator new(saturated_mul((unsigned int)(v6 + 1), 2u));
    Length = Src.Length;
    Buffer = Src.Buffer;
    v10 = v7;
    *a1 = v7;
    memcpy_0(v7, Buffer, Length);
    v10[v6] = 0;
  }
  else
  {
    v5 = v4 & 0x8000FFFF | 0x70000;
  }
  if ( Src.Buffer )
    RtlFreeUnicodeString(&Src);
  return v5;
}

```

## disassembly

```asm
0x18004f3f0  push    rbx
0x18004f3f2  push    rsi
0x18004f3f3  push    rdi
0x18004f3f4  push    r14
0x18004f3f6  sub     rsp, 38h
0x18004f3fa  mov     r14, rcx
0x18004f3fd  mov     qword ptr [rcx], 0
0x18004f404  call    cs:__imp_GetThreadLocale
0x18004f40a  xorps   xmm0, xmm0
0x18004f40d  lea     rdx, [rsp+58h+Src]
0x18004f412  mov     ecx, eax
0x18004f414  mov     r9b, 1
0x18004f417  xor     r8d, r8d
0x18004f41a  movups  xmmword ptr [rsp+58h+Src.Length], xmm0
0x18004f41f  call    cs:__imp_RtlLcidToLocaleName
0x18004f425  mov     esi, eax
0x18004f427  test    eax, eax
0x18004f429  jns     short loc_18004F439
0x18004f42b  and     esi, 8007FFFFh
0x18004f431  or      esi, 70000h
0x18004f437  jmp     short loc_18004F47C
0x18004f439  movzx   eax, [rsp+58h+Src.Length]
0x18004f43e  xor     esi, esi
0x18004f440  shr     eax, 1
0x18004f442  mov     edi, eax
0x18004f444  lea     ecx, [rax+1]
0x18004f447  lea     eax, [rsi+2]
0x18004f44a  mul     rcx
0x18004f44d  lea     rcx, [rsi-1]
0x18004f451  cmovb   rax, rcx
0x18004f455  mov     rcx, rax; Size
0x18004f458  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f45d  movzx   r8d, [rsp+58h+Src.Length]; Size
0x18004f463  mov     rcx, rax; void *
0x18004f466  mov     rdx, [rsp+58h+Src.Buffer]; Src
0x18004f46b  mov     rbx, rax
0x18004f46e  mov     [r14], rax
0x18004f471  call    memcpy_0
0x18004f476  xor     ecx, ecx
0x18004f478  mov     [rbx+rdi*2], cx
0x18004f47c  cmp     [rsp+58h+Src.Buffer], 0
0x18004f482  jz      short loc_18004F48F
0x18004f484  lea     rcx, [rsp+58h+Src]; UnicodeString
0x18004f489  call    cs:__imp_RtlFreeUnicodeString
0x18004f48f  mov     eax, esi
0x18004f491  add     rsp, 38h
0x18004f495  pop     r14
0x18004f497  pop     rdi
0x18004f498  pop     rsi
0x18004f499  pop     rbx
0x18004f49a  retn
```
