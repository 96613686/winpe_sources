# ndisQueryDriverImageName(_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x140053480`
- end: `0x1400535fa`
- name: `?ndisQueryDriverImageName@@YAXPEAU_UNICODE_STRING@@0@Z`
- size: `378`
- prototype: `void(struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400532f0`
- `0x14007f810`
- `0x14009c0c0`
- `0x1401763a4`

## callees

- `0x140053480`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14005350a`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14005350a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140053586`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140053586`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400535b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400535b9`
- `ntoskrnl!ExAllocatePool2` at `0x140053559`
- `ntoskrnl!ExAllocatePool2` at `0x140053559`

## string_xrefs

- `0x1400534c9`: `ImagePath`

## pseudocode

```c
void __fastcall ndisQueryDriverImageName(struct _UNICODE_STRING *a1, struct _UNICODE_STRING *a2)
{
  bool v2; // zf
  wchar_t *Buffer; // rbx
  unsigned __int16 v5; // si
  PVOID v6; // r8
  unsigned __int16 v7; // dx
  unsigned __int16 v8; // r10
  unsigned __int16 v9; // bx
  wchar_t *Pool2; // rax
  const WCHAR *v11; // rax
  unsigned __int16 v12; // cx
  __int64 v13; // rax
  __int16 v14; // r11
  PVOID P[2]; // [rsp+30h] [rbp-88h] BYREF
  _QWORD v16[14]; // [rsp+40h] [rbp-78h] BYREF

  v2 = a1->Length == 0;
  *(_OWORD *)P = 0;
  if ( v2
    || (Buffer = a1->Buffer) == 0
    || (memset(v16, 0, sizeof(v16)),
        LODWORD(v16[1]) = 304,
        v16[2] = L"ImagePath",
        LODWORD(v16[4]) = 0x2000000,
        v16[3] = P,
        (unsigned int)RtlQueryRegistryValuesEx(1, Buffer, v16, 0, 0)) )
  {
LABEL_8:
    v6 = P[1];
    goto LABEL_9;
  }
  v5 = 0;
  v6 = P[1];
  v7 = LOWORD(P[0]) >> 1;
  v8 = 0;
  if ( LOWORD(P[0]) >> 1 )
  {
    do
    {
      v12 = v8 + 1;
      v13 = v8;
      v14 = ++v8;
      if ( *((_WORD *)P[1] + v13) != 92 )
        v14 = v5;
      v5 = v14;
    }
    while ( v12 < v7 );
  }
  if ( v5 < v7 )
  {
    v9 = LOWORD(P[0]) + 2 * (1 - v5);
    Pool2 = (wchar_t *)ExAllocatePool2(64, v9, 1851868238);
    a2->Buffer = Pool2;
    if ( Pool2 )
    {
      a2->Length = 0;
      v11 = (const WCHAR *)P[1];
      a2->MaximumLength = v9;
      RtlAppendUnicodeToString(a2, &v11[v5]);
    }
    goto LABEL_8;
  }
LABEL_9:
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
}

```

## disassembly

```asm
0x140053480  mov     rax, rsp
0x140053483  sub     rsp, 0B8h
0x14005348a  cmp     word ptr [rcx], 0
0x14005348e  xorps   xmm0, xmm0
0x140053491  mov     [rax+8], rbx
0x140053495  mov     [rax+10h], rsi
0x140053499  mov     [rax-8], rdi
0x14005349d  mov     rdi, rdx
0x1400534a0  movups  xmmword ptr [rsp+0B8h+P], xmm0
0x1400534a5  jz      loc_140053592
0x1400534ab  mov     rbx, [rcx+8]
0x1400534af  test    rbx, rbx
0x1400534b2  jz      loc_140053592
0x1400534b8  xor     edx, edx; Val
0x1400534ba  lea     rcx, [rax-78h]; void *
0x1400534be  mov     r8d, 70h ; 'p'; Size
0x1400534c4  call    memset
0x1400534c9  lea     rax, aImagepath; "ImagePath"
0x1400534d0  mov     [rsp+0B8h+var_70], 130h
0x1400534d8  mov     rdx, rbx
0x1400534db  mov     [rsp+0B8h+var_68], rax
0x1400534e0  lea     rax, [rsp+0B8h+P]
0x1400534e5  mov     [rsp+0B8h+var_58], 2000000h
0x1400534ed  mov     ebx, 1
0x1400534f2  mov     [rsp+0B8h+var_60], rax
0x1400534f7  xor     r9d, r9d
0x1400534fa  mov     [rsp+0B8h+var_98], 0
0x140053503  lea     r8, [rsp+0B8h+var_78]
0x140053508  mov     ecx, ebx
0x14005350a  call    cs:__imp_RtlQueryRegistryValuesEx
0x140053511  nop     dword ptr [rax+rax+00h]
0x140053516  test    eax, eax
0x140053518  jnz     short loc_140053592
0x14005351a  movzx   r9d, word ptr [rsp+0B8h+P]
0x140053520  xor     esi, esi
0x140053522  mov     r8, [rsp+0B8h+P+8]
0x140053527  movzx   edx, r9w
0x14005352b  shr     dx, 1
0x14005352e  xor     r10d, r10d
0x140053531  cmp     ax, dx
0x140053534  jb      loc_1400535D0
0x14005353a  cmp     si, dx
0x14005353d  jnb     short loc_140053597
0x14005353f  sub     bx, si
0x140053542  mov     ecx, 40h ; '@'
0x140053547  add     bx, bx
0x14005354a  mov     r8d, 6E61444Eh
0x140053550  add     bx, r9w
0x140053554  movzx   ebx, bx
0x140053557  mov     edx, ebx
0x140053559  call    cs:__imp_ExAllocatePool2
0x140053560  nop     dword ptr [rax+rax+00h]
0x140053565  mov     [rdi+8], rax
0x140053569  test    rax, rax
0x14005356c  jz      short loc_140053592
0x14005356e  xor     eax, eax
0x140053570  movzx   ecx, si
0x140053573  mov     [rdi], ax
0x140053576  mov     rax, [rsp+0B8h+P+8]
0x14005357b  mov     [rdi+2], bx
0x14005357f  lea     rdx, [rax+rcx*2]; Source
0x140053583  mov     rcx, rdi; Destination
0x140053586  call    cs:__imp_RtlAppendUnicodeToString
0x14005358d  nop     dword ptr [rax+rax+00h]
0x140053592  mov     r8, [rsp+0B8h+P+8]
0x140053597  mov     rdi, [rsp+0B8h+var_8]
0x14005359f  mov     rsi, [rsp+0B8h+arg_8]
0x1400535a7  mov     rbx, [rsp+0B8h+arg_0]
0x1400535af  test    r8, r8
0x1400535b2  jz      short loc_1400535C5
0x1400535b4  xor     edx, edx; Tag
0x1400535b6  mov     rcx, r8; P
0x1400535b9  call    cs:__imp_ExFreePoolWithTag
0x1400535c0  nop     dword ptr [rax+rax+00h]
0x1400535c5  add     rsp, 0B8h
0x1400535cc  retn
0x1400535d0  lea     ecx, [r10+1]
0x1400535d4  movzx   eax, r10w
0x1400535d8  movzx   r11d, cx
0x1400535dc  movzx   r10d, cx
0x1400535e0  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x1400535e6  cmovnz  r11w, si
0x1400535eb  movzx   esi, r11w
0x1400535ef  cmp     cx, dx
0x1400535f2  jnb     loc_14005353A
0x1400535f8  jmp     short loc_1400535D0
```
