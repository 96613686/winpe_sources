# ndisQueryDriverImageName(_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x14004e250`
- end: `0x14004e3ca`
- name: `?ndisQueryDriverImageName@@YAXPEAU_UNICODE_STRING@@0@Z`
- size: `378`
- prototype: `void(struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14004e0c0`
- `0x14007a070`
- `0x140096e40`
- `0x1401703a4`

## callees

- `0x14004e250`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14004e2da`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14004e2da`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004e356`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004e356`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e389`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e389`
- `ntoskrnl!ExAllocatePool2` at `0x14004e329`
- `ntoskrnl!ExAllocatePool2` at `0x14004e329`

## string_xrefs

- `0x14004e299`: `ImagePath`

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
0x14004e250  mov     rax, rsp
0x14004e253  sub     rsp, 0B8h
0x14004e25a  cmp     word ptr [rcx], 0
0x14004e25e  xorps   xmm0, xmm0
0x14004e261  mov     [rax+8], rbx
0x14004e265  mov     [rax+10h], rsi
0x14004e269  mov     [rax-8], rdi
0x14004e26d  mov     rdi, rdx
0x14004e270  movups  xmmword ptr [rsp+0B8h+P], xmm0
0x14004e275  jz      loc_14004E362
0x14004e27b  mov     rbx, [rcx+8]
0x14004e27f  test    rbx, rbx
0x14004e282  jz      loc_14004E362
0x14004e288  xor     edx, edx; Val
0x14004e28a  lea     rcx, [rax-78h]; void *
0x14004e28e  mov     r8d, 70h ; 'p'; Size
0x14004e294  call    memset
0x14004e299  lea     rax, aImagepath; "ImagePath"
0x14004e2a0  mov     [rsp+0B8h+var_70], 130h
0x14004e2a8  mov     rdx, rbx
0x14004e2ab  mov     [rsp+0B8h+var_68], rax
0x14004e2b0  lea     rax, [rsp+0B8h+P]
0x14004e2b5  mov     [rsp+0B8h+var_58], 2000000h
0x14004e2bd  mov     ebx, 1
0x14004e2c2  mov     [rsp+0B8h+var_60], rax
0x14004e2c7  xor     r9d, r9d
0x14004e2ca  mov     [rsp+0B8h+var_98], 0
0x14004e2d3  lea     r8, [rsp+0B8h+var_78]
0x14004e2d8  mov     ecx, ebx
0x14004e2da  call    cs:__imp_RtlQueryRegistryValuesEx
0x14004e2e1  nop     dword ptr [rax+rax+00h]
0x14004e2e6  test    eax, eax
0x14004e2e8  jnz     short loc_14004E362
0x14004e2ea  movzx   r9d, word ptr [rsp+0B8h+P]
0x14004e2f0  xor     esi, esi
0x14004e2f2  mov     r8, [rsp+0B8h+P+8]
0x14004e2f7  movzx   edx, r9w
0x14004e2fb  shr     dx, 1
0x14004e2fe  xor     r10d, r10d
0x14004e301  cmp     ax, dx
0x14004e304  jb      loc_14004E3A0
0x14004e30a  cmp     si, dx
0x14004e30d  jnb     short loc_14004E367
0x14004e30f  sub     bx, si
0x14004e312  mov     ecx, 40h ; '@'
0x14004e317  add     bx, bx
0x14004e31a  mov     r8d, 6E61444Eh
0x14004e320  add     bx, r9w
0x14004e324  movzx   ebx, bx
0x14004e327  mov     edx, ebx
0x14004e329  call    cs:__imp_ExAllocatePool2
0x14004e330  nop     dword ptr [rax+rax+00h]
0x14004e335  mov     [rdi+8], rax
0x14004e339  test    rax, rax
0x14004e33c  jz      short loc_14004E362
0x14004e33e  xor     eax, eax
0x14004e340  movzx   ecx, si
0x14004e343  mov     [rdi], ax
0x14004e346  mov     rax, [rsp+0B8h+P+8]
0x14004e34b  mov     [rdi+2], bx
0x14004e34f  lea     rdx, [rax+rcx*2]; Source
0x14004e353  mov     rcx, rdi; Destination
0x14004e356  call    cs:__imp_RtlAppendUnicodeToString
0x14004e35d  nop     dword ptr [rax+rax+00h]
0x14004e362  mov     r8, [rsp+0B8h+P+8]
0x14004e367  mov     rdi, [rsp+0B8h+var_8]
0x14004e36f  mov     rsi, [rsp+0B8h+arg_8]
0x14004e377  mov     rbx, [rsp+0B8h+arg_0]
0x14004e37f  test    r8, r8
0x14004e382  jz      short loc_14004E395
0x14004e384  xor     edx, edx; Tag
0x14004e386  mov     rcx, r8; P
0x14004e389  call    cs:__imp_ExFreePoolWithTag
0x14004e390  nop     dword ptr [rax+rax+00h]
0x14004e395  add     rsp, 0B8h
0x14004e39c  retn
0x14004e3a0  lea     ecx, [r10+1]
0x14004e3a4  movzx   eax, r10w
0x14004e3a8  movzx   r11d, cx
0x14004e3ac  movzx   r10d, cx
0x14004e3b0  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x14004e3b6  cmovnz  r11w, si
0x14004e3bb  movzx   esi, r11w
0x14004e3bf  cmp     cx, dx
0x14004e3c2  jnb     loc_14004E30A
0x14004e3c8  jmp     short loc_14004E3A0
```
