# PrjfCreatePrjReparseBuffer

- ea: `0x14002f494`
- end: `0x14002f5e9`
- name: `PrjfCreatePrjReparseBuffer`
- size: `341`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, __int128 *, __int64, _OWORD *, WCHAR **, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x140035238`
- `0x1400368c4`

## callees

- `0x14002f494`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002f5cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f5cc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002f598`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002f598`
- `ntoskrnl!ExAllocatePool2` at `0x14002f4c9`
- `ntoskrnl!ExAllocatePool2` at `0x14002f4c9`

## pseudocode

```c
__int64 __fastcall PrjfCreatePrjReparseBuffer(
        PCUNICODE_STRING SourceString,
        __int128 *a2,
        __int64 a3,
        _OWORD *a4,
        WCHAR **a5,
        unsigned int *a6)
{
  unsigned int v8; // r14d
  __int64 Pool2; // rax
  WCHAR *v11; // rbx
  __int128 v13; // xmm0
  __int64 v14; // rcx
  _OWORD *v15; // rax
  __int128 v16; // xmm1
  WCHAR v17; // ax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF

  v8 = SourceString->Length + 290;
  DestinationString = 0;
  Pool2 = ExAllocatePool2(256, v8, 1769097808);
  v11 = (WCHAR *)Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  v13 = *a2;
  v14 = 2;
  *(_QWORD *)(Pool2 + 8) = 2;
  *(_OWORD *)(Pool2 + 16) = v13;
  v15 = (_OWORD *)(Pool2 + 32);
  do
  {
    *v15 = *a4;
    v15[1] = a4[1];
    v15[2] = a4[2];
    v15[3] = a4[3];
    v15[4] = a4[4];
    v15[5] = a4[5];
    v15[6] = a4[6];
    v16 = a4[7];
    a4 += 8;
    v15[7] = v16;
    v15 += 8;
    --v14;
  }
  while ( v14 );
  v11[144] = SourceString->Length;
  *(_DWORD *)v11 = -1879048164;
  v17 = v11[144] + 282;
  if ( v17 < 0x11Au )
  {
    v11[2] = -1;
    ExFreePoolWithTag(v11, 0x69724A50u);
    return 3221225621LL;
  }
  else
  {
    v11[2] = v17;
    DestinationString.MaximumLength = v11[144];
    DestinationString.Length = 0;
    DestinationString.Buffer = v11 + 145;
    RtlCopyUnicodeString(&DestinationString, SourceString);
    *a5 = v11;
    *a6 = v8;
    return 0;
  }
}

```

## disassembly

```asm
0x14002f494  push    rbx
0x14002f496  push    rbp
0x14002f497  push    rsi
0x14002f498  push    rdi
0x14002f499  push    r14
0x14002f49b  sub     rsp, 30h
0x14002f49f  movzx   r14d, word ptr [rcx]
0x14002f4a3  mov     rbp, rdx
0x14002f4a6  mov     rsi, rcx
0x14002f4a9  xorps   xmm0, xmm0
0x14002f4ac  add     r14d, 122h
0x14002f4b3  mov     ecx, 100h
0x14002f4b8  mov     edx, r14d
0x14002f4bb  mov     r8d, 69724A50h
0x14002f4c1  mov     rdi, r9
0x14002f4c4  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x14002f4c9  call    cs:__imp_ExAllocatePool2
0x14002f4d0  nop     dword ptr [rax+rax+00h]
0x14002f4d5  mov     rbx, rax
0x14002f4d8  test    rax, rax
0x14002f4db  jnz     short loc_14002F4E7
0x14002f4dd  mov     eax, 0C000009Ah
0x14002f4e2  jmp     loc_14002F5DD
0x14002f4e7  movaps  xmm0, xmmword ptr [rbp+0]
0x14002f4eb  mov     ecx, 2
0x14002f4f0  mov     [rax+8], rcx
0x14002f4f4  movdqu  xmmword ptr [rax+10h], xmm0
0x14002f4f9  add     rax, 20h ; ' '
0x14002f4fd  lea     edx, [rcx+7Eh]
0x14002f500  movups  xmm0, xmmword ptr [rdi]
0x14002f503  movups  xmmword ptr [rax], xmm0
0x14002f506  movups  xmm1, xmmword ptr [rdi+10h]
0x14002f50a  movups  xmmword ptr [rax+10h], xmm1
0x14002f50e  movups  xmm0, xmmword ptr [rdi+20h]
0x14002f512  movups  xmmword ptr [rax+20h], xmm0
0x14002f516  movups  xmm1, xmmword ptr [rdi+30h]
0x14002f51a  movups  xmmword ptr [rax+30h], xmm1
0x14002f51e  movups  xmm0, xmmword ptr [rdi+40h]
0x14002f522  movups  xmmword ptr [rax+40h], xmm0
0x14002f526  movups  xmm1, xmmword ptr [rdi+50h]
0x14002f52a  movups  xmmword ptr [rax+50h], xmm1
0x14002f52e  movups  xmm0, xmmword ptr [rdi+60h]
0x14002f532  movups  xmmword ptr [rax+60h], xmm0
0x14002f536  movups  xmm1, xmmword ptr [rdi+70h]
0x14002f53a  add     rdi, rdx
0x14002f53d  movups  xmmword ptr [rax+70h], xmm1
0x14002f541  add     rax, rdx
0x14002f544  sub     rcx, 1
0x14002f548  jnz     short loc_14002F500
0x14002f54a  movzx   eax, word ptr [rsi]
0x14002f54d  mov     ecx, 11Ah
0x14002f552  mov     [rbx+120h], ax
0x14002f559  mov     eax, ecx
0x14002f55b  mov     dword ptr [rbx], 9000001Ch
0x14002f561  add     ax, [rbx+120h]
0x14002f568  cmp     ax, cx
0x14002f56b  jb      short loc_14002F5BE
0x14002f56d  mov     [rbx+4], ax
0x14002f571  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x14002f576  movzx   eax, word ptr [rbx+120h]
0x14002f57d  mov     rdx, rsi; SourceString
0x14002f580  mov     [rsp+58h+DestinationString.MaximumLength], ax
0x14002f585  xor     eax, eax
0x14002f587  mov     [rsp+58h+DestinationString.Length], ax
0x14002f58c  lea     rax, [rbx+122h]
0x14002f593  mov     [rsp+58h+DestinationString.Buffer], rax
0x14002f598  call    cs:__imp_RtlCopyUnicodeString
0x14002f59f  nop     dword ptr [rax+rax+00h]
0x14002f5a4  mov     rax, [rsp+58h+arg_20]
0x14002f5ac  mov     [rax], rbx
0x14002f5af  mov     rax, [rsp+58h+arg_28]
0x14002f5b7  mov     [rax], r14d
0x14002f5ba  xor     eax, eax
0x14002f5bc  jmp     short loc_14002F5DD
0x14002f5be  mov     edx, 69724A50h; Tag
0x14002f5c3  mov     word ptr [rbx+4], 0FFFFh
0x14002f5c9  mov     rcx, rbx; P
0x14002f5cc  call    cs:__imp_ExFreePoolWithTag
0x14002f5d3  nop     dword ptr [rax+rax+00h]
0x14002f5d8  mov     eax, 0C0000095h
0x14002f5dd  add     rsp, 30h
0x14002f5e1  pop     r14
0x14002f5e3  pop     rdi
0x14002f5e4  pop     rsi
0x14002f5e5  pop     rbp
0x14002f5e6  pop     rbx
0x14002f5e7  retn
```
