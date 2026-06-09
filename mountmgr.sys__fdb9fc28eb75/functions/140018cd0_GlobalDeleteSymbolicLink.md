# GlobalDeleteSymbolicLink

- ea: `0x140018cd0`
- end: `0x140018d99`
- name: `GlobalDeleteSymbolicLink`
- size: `201`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x14000a050`
- `0x14000be4c`
- `0x14000c7d8`
- `0x14000c954`
- `0x14000d7a0`
- `0x14000ff00`
- `0x140014fc0`
- `0x140018560`
- `0x140018af0`

## callees

- `0x140001ae0`
- `0x1400021c8`
- `0x140018cd0`
- `0x140018e80`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x140018cfa`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140018cfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018d7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018d7f`

## pseudocode

```c
__int64 __fastcall GlobalDeleteSymbolicLink(__int64 a1)
{
  int v2; // ebx
  __int64 v3; // r8
  __int64 v4; // rdx
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+30h] [rbp-18h] BYREF

  SymbolicLinkName = 0;
  v2 = CreateStringWithGlobal((PCUNICODE_STRING)a1, &SymbolicLinkName);
  if ( v2 < 0 || (v2 = IoDeleteSymbolicLink(&SymbolicLinkName), v2 < 0) )
  {
    v4 = *(_QWORD *)(a1 + 8);
    if ( v4 && *(_WORD *)a1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_LS(WPP_GLOBAL_Control->AttachedDevice, v4, v3, v2, *(_QWORD *)(a1 + 8));
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 16, v3, (unsigned int)v2);
    }
  }
  if ( SymbolicLinkName.Buffer )
    ExFreePoolWithTag(SymbolicLinkName.Buffer, 0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140018cd0  mov     [rsp+arg_0], rbx
0x140018cd5  push    rdi
0x140018cd6  sub     rsp, 40h
0x140018cda  xorps   xmm0, xmm0
0x140018cdd  lea     rdx, [rsp+48h+SymbolicLinkName]
0x140018ce2  movups  xmmword ptr [rsp+48h+SymbolicLinkName.Length], xmm0
0x140018ce7  mov     rdi, rcx
0x140018cea  call    CreateStringWithGlobal
0x140018cef  mov     ebx, eax
0x140018cf1  test    eax, eax
0x140018cf3  js      short loc_140018D0C
0x140018cf5  lea     rcx, [rsp+48h+SymbolicLinkName]; SymbolicLinkName
0x140018cfa  call    cs:__imp_IoDeleteSymbolicLink
0x140018d01  nop     dword ptr [rax+rax+00h]
0x140018d06  mov     ebx, eax
0x140018d08  test    eax, eax
0x140018d0a  jns     short loc_140018D73
0x140018d0c  mov     rdx, [rdi+8]
0x140018d10  test    rdx, rdx
0x140018d13  jz      short loc_140018D48
0x140018d15  cmp     word ptr [rdi], 0
0x140018d19  jz      short loc_140018D48
0x140018d1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140018d22  lea     rax, WPP_GLOBAL_Control
0x140018d29  cmp     rcx, rax
0x140018d2c  jz      short loc_140018D73
0x140018d2e  mov     eax, [rcx+2Ch]
0x140018d31  test    al, 1
0x140018d33  jz      short loc_140018D73
0x140018d35  mov     rcx, [rcx+18h]
0x140018d39  mov     r9d, ebx
0x140018d3c  mov     [rsp+48h+var_28], rdx
0x140018d41  call    WPP_SF_LS
0x140018d46  jmp     short loc_140018D73
0x140018d48  mov     rcx, cs:WPP_GLOBAL_Control
0x140018d4f  lea     rax, WPP_GLOBAL_Control
0x140018d56  cmp     rcx, rax
0x140018d59  jz      short loc_140018D73
0x140018d5b  mov     eax, [rcx+2Ch]
0x140018d5e  test    al, 1
0x140018d60  jz      short loc_140018D73
0x140018d62  mov     rcx, [rcx+18h]
0x140018d66  mov     edx, 10h
0x140018d6b  mov     r9d, ebx
0x140018d6e  call    WPP_SF_L
0x140018d73  mov     rcx, [rsp+48h+SymbolicLinkName.Buffer]; P
0x140018d78  test    rcx, rcx
0x140018d7b  jz      short loc_140018D8B
0x140018d7d  xor     edx, edx; Tag
0x140018d7f  call    cs:__imp_ExFreePoolWithTag
0x140018d86  nop     dword ptr [rax+rax+00h]
0x140018d8b  mov     eax, ebx
0x140018d8d  mov     rbx, [rsp+48h+arg_0]
0x140018d92  add     rsp, 40h
0x140018d96  pop     rdi
0x140018d97  retn
```
