# SymbolicLinkNamesFromUniqueIdQuery

- ea: `0x140019780`
- end: `0x1400198aa`
- name: `SymbolicLinkNamesFromUniqueIdQuery`
- size: `298`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x140001b30`
- `0x140002f80`
- `0x140019780`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400197f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400197f2`
- `ntoskrnl!ExAllocatePool2` at `0x14001980e`
- `ntoskrnl!ExAllocatePool2` at `0x14001980e`
- `ntoskrnl!RtlCompareMemory` at `0x1400197d0`
- `ntoskrnl!RtlCompareMemory` at `0x1400197d0`

## pseudocode

```c
__int64 __fastcall SymbolicLinkNamesFromUniqueIdQuery(
        const WCHAR *Src,
        int a2,
        const void *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        struct _UNICODE_STRING *a6)
{
  bool v6; // zf
  WCHAR *Pool2; // rax
  struct _UNICODE_STRING *i; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  v6 = *Src == 35;
  DestinationString = 0;
  if ( v6 || a2 != 3 || *a5 != a4 || RtlCompareMemory(a5 + 1, a3, a4) != a4 )
    return 0;
  RtlInitUnicodeString(&DestinationString, Src);
  Pool2 = (WCHAR *)ExAllocatePool2(258, DestinationString.MaximumLength, 1098149453);
  DestinationString.Buffer = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, Src, DestinationString.Length);
    DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1] = 0;
    for ( i = a6; i->Length; ++i )
      ;
    *i = DestinationString;
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20);
  return 3221225626LL;
}

```

## disassembly

```asm
0x140019780  mov     [rsp+arg_8], rsi
0x140019785  push    rdi
0x140019786  sub     rsp, 30h
0x14001978a  xor     esi, esi
0x14001978c  xorps   xmm0, xmm0
0x14001978f  cmp     word ptr [rcx], 23h ; '#'
0x140019793  mov     r10, r8
0x140019796  mov     rdi, rcx
0x140019799  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x14001979e  jz      loc_14001989C
0x1400197a4  cmp     edx, 3
0x1400197a7  jnz     loc_14001989C
0x1400197ad  mov     rcx, [rsp+38h+arg_20]
0x1400197b2  movzx   eax, word ptr [rcx]
0x1400197b5  cmp     eax, r9d
0x1400197b8  jnz     loc_14001989C
0x1400197be  mov     [rsp+38h+arg_0], rbx
0x1400197c3  add     rcx, 2; Source1
0x1400197c7  mov     r8d, r9d; Length
0x1400197ca  mov     rdx, r10; Source2
0x1400197cd  mov     ebx, r9d
0x1400197d0  call    cs:__imp_RtlCompareMemory
0x1400197d7  nop     dword ptr [rax+rax+00h]
0x1400197dc  cmp     rax, rbx
0x1400197df  mov     rbx, [rsp+38h+arg_0]
0x1400197e4  jnz     loc_14001989C
0x1400197ea  mov     rdx, rdi; SourceString
0x1400197ed  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400197f2  call    cs:__imp_RtlInitUnicodeString
0x1400197f9  nop     dword ptr [rax+rax+00h]
0x1400197fe  movzx   edx, [rsp+38h+DestinationString.MaximumLength]
0x140019803  mov     ecx, 102h
0x140019808  mov     r8d, 41746E4Dh
0x14001980e  call    cs:__imp_ExAllocatePool2
0x140019815  nop     dword ptr [rax+rax+00h]
0x14001981a  mov     [rsp+38h+DestinationString.Buffer], rax
0x14001981f  test    rax, rax
0x140019822  jnz     short loc_14001985D
0x140019824  mov     rcx, cs:WPP_GLOBAL_Control
0x14001982b  lea     rax, WPP_GLOBAL_Control
0x140019832  cmp     rcx, rax
0x140019835  jz      short loc_14001984C
0x140019837  mov     eax, [rcx+2Ch]
0x14001983a  test    al, 4
0x14001983c  jz      short loc_14001984C
0x14001983e  mov     rcx, [rcx+18h]
0x140019842  mov     edx, 14h
0x140019847  call    WPP_SF_
0x14001984c  mov     eax, 0C000009Ah
0x140019851  mov     rsi, [rsp+38h+arg_8]
0x140019856  add     rsp, 30h
0x14001985a  pop     rdi
0x14001985b  retn
0x14001985d  movzx   r8d, [rsp+38h+DestinationString.Length]; Size
0x140019863  mov     rdx, rdi; Src
0x140019866  mov     rcx, rax; void *
0x140019869  call    memmove
0x14001986e  movzx   edx, [rsp+38h+DestinationString.Length]
0x140019873  xor     ecx, ecx
0x140019875  mov     rax, [rsp+38h+DestinationString.Buffer]
0x14001987a  shr     rdx, 1
0x14001987d  mov     [rax+rdx*2], cx
0x140019881  mov     rax, [rsp+38h+arg_28]
0x140019886  cmp     [rax], cx
0x140019889  jz      short loc_140019894
0x14001988b  add     rax, 10h
0x14001988f  cmp     [rax], cx
0x140019892  jnz     short loc_14001988B
0x140019894  movups  xmm0, xmmword ptr [rsp+38h+DestinationString.Length]
0x140019899  movups  xmmword ptr [rax], xmm0
0x14001989c  mov     eax, esi
0x14001989e  mov     rsi, [rsp+38h+arg_8]
0x1400198a3  add     rsp, 30h
0x1400198a7  pop     rdi
0x1400198a8  retn
```
