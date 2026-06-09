# GenImageNtHeader(void *,_IMAGE_NT_HEADERS64 *)

- ea: `0x180026cb4`
- end: `0x180026da5`
- name: `?GenImageNtHeader@@YAPEAU_IMAGE_NT_HEADERS64@@PEAXPEAU1@@Z`
- size: `241`
- prototype: `struct _IMAGE_NT_HEADERS *__fastcall(char *, struct _IMAGE_NT_HEADERS64 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180012e20`
- `0x180017b8c`
- `0x18001a990`
- `0x18001cdb0`
- `0x180026b18`

## callees

- `0x180026bbc`
- `0x180026cb4`

## pseudocode

```c
struct _IMAGE_NT_HEADERS *__fastcall GenImageNtHeader(char *a1, struct _IMAGE_NT_HEADERS64 *a2)
{
  struct _IMAGE_NT_HEADERS *v3; // rcx
  struct _IMAGE_NT_HEADERS *v4; // rax
  __int64 v5; // r8

  if ( (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return 0;
  if ( *(_WORD *)a1 != 23117 )
    return 0;
  v3 = (struct _IMAGE_NT_HEADERS *)&a1[*((int *)a1 + 15)];
  if ( v3->Signature != 17744 )
    return 0;
  if ( ((v3->OptionalHeader.Magic - 267) & 0xFEFF) != 0 )
    return 0;
  if ( a2 )
  {
    if ( v3->OptionalHeader.Magic == 267 )
    {
      GenImageNtHdr32To64(v3, a2);
    }
    else
    {
      v4 = v3;
      v5 = 2;
      do
      {
        *(_OWORD *)&a2->Signature = *(_OWORD *)&v4->Signature;
        *(_OWORD *)&a2->FileHeader.NumberOfSymbols = *(_OWORD *)&v4->FileHeader.NumberOfSymbols;
        *(_OWORD *)&a2->OptionalHeader.SizeOfInitializedData = *(_OWORD *)&v4->OptionalHeader.SizeOfInitializedData;
        *(_OWORD *)&a2->OptionalHeader.ImageBase = *(_OWORD *)&v4->OptionalHeader.BaseOfData;
        *(_OWORD *)&a2->OptionalHeader.MajorOperatingSystemVersion = *(_OWORD *)&v4->OptionalHeader.MajorOperatingSystemVersion;
        *(_OWORD *)&a2->OptionalHeader.SizeOfImage = *(_OWORD *)&v4->OptionalHeader.SizeOfImage;
        *(_OWORD *)&a2->OptionalHeader.SizeOfStackReserve = *(_OWORD *)&v4->OptionalHeader.SizeOfStackReserve;
        *(_OWORD *)&a2->OptionalHeader.SizeOfHeapReserve = *(_OWORD *)&v4->OptionalHeader.LoaderFlags;
        a2 = (struct _IMAGE_NT_HEADERS64 *)((char *)a2 + 128);
        v4 = (struct _IMAGE_NT_HEADERS *)((char *)v4 + 128);
        --v5;
      }
      while ( v5 );
      *(_QWORD *)&a2->Signature = *(_QWORD *)&v4->Signature;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180026cb4  mov     [rsp+arg_0], rcx
0x180026cb9  sub     rsp, 78h
0x180026cbd  mov     r8, rcx
0x180026cc0  mov     [rsp+78h+var_28], 0
0x180026cc9  lea     rax, [rcx-1]
0x180026ccd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026cd1  ja      loc_180026D9E
0x180026cd7  mov     eax, 5A4Dh
0x180026cdc  cmp     [rcx], ax
0x180026cdf  jz      short loc_180026CE8
0x180026ce1  xor     eax, eax
0x180026ce3  jmp     loc_180026DA0
0x180026ce8  movsxd  rcx, dword ptr [rcx+3Ch]
0x180026cec  add     rcx, r8; struct _IMAGE_NT_HEADERS *
0x180026cef  mov     [rsp+78h+var_28], rcx
0x180026cf4  cmp     dword ptr [rcx], 4550h
0x180026cfa  jz      short loc_180026D03
0x180026cfc  xor     eax, eax
0x180026cfe  jmp     loc_180026DA0
0x180026d03  mov     r9d, 10Bh
0x180026d09  movzx   eax, word ptr [rcx+18h]
0x180026d0d  sub     ax, r9w
0x180026d11  mov     r8d, 0FEFFh
0x180026d17  test    r8w, ax
0x180026d1b  jz      short loc_180026D21
0x180026d1d  xor     eax, eax
0x180026d1f  jmp     short loc_180026DA0
0x180026d21  test    rdx, rdx
0x180026d24  jz      short loc_180026D91
0x180026d26  cmp     [rcx+18h], r9w
0x180026d2b  jnz     short loc_180026D34
0x180026d2d  call    ?GenImageNtHdr32To64@@YAXPEAU_IMAGE_NT_HEADERS@@PEAU_IMAGE_NT_HEADERS64@@@Z; GenImageNtHdr32To64(_IMAGE_NT_HEADERS *,_IMAGE_NT_HEADERS64 *)
0x180026d32  jmp     short loc_180026D91
0x180026d34  mov     rax, rcx
0x180026d37  mov     r8d, 2
0x180026d3d  lea     r9d, [r8+7Eh]
0x180026d41  movups  xmm0, xmmword ptr [rax]
0x180026d44  movups  xmmword ptr [rdx], xmm0
0x180026d47  movups  xmm1, xmmword ptr [rax+10h]
0x180026d4b  movups  xmmword ptr [rdx+10h], xmm1
0x180026d4f  movups  xmm0, xmmword ptr [rax+20h]
0x180026d53  movups  xmmword ptr [rdx+20h], xmm0
0x180026d57  movups  xmm1, xmmword ptr [rax+30h]
0x180026d5b  movups  xmmword ptr [rdx+30h], xmm1
0x180026d5f  movups  xmm0, xmmword ptr [rax+40h]
0x180026d63  movups  xmmword ptr [rdx+40h], xmm0
0x180026d67  movups  xmm1, xmmword ptr [rax+50h]
0x180026d6b  movups  xmmword ptr [rdx+50h], xmm1
0x180026d6f  movups  xmm0, xmmword ptr [rax+60h]
0x180026d73  movups  xmmword ptr [rdx+60h], xmm0
0x180026d77  movups  xmm1, xmmword ptr [rax+70h]
0x180026d7b  movups  xmmword ptr [rdx+70h], xmm1
0x180026d7f  add     rdx, r9
0x180026d82  add     rax, r9
0x180026d85  sub     r8, 1
0x180026d89  jnz     short loc_180026D41
0x180026d8b  mov     rax, [rax]
0x180026d8e  mov     [rdx], rax
0x180026d91  mov     rax, rcx
0x180026d94  jmp     short loc_180026DA0
0x180026d96  xor     eax, eax
0x180026d98  jmp     short loc_180026DA0
0x180026d9a  xor     eax, eax
0x180026d9c  jmp     short loc_180026DA0
0x180026d9e  xor     eax, eax
0x180026da0  add     rsp, 78h
0x180026da4  retn
0x18002b63a  push    rbp
0x18002b63c  sub     rsp, 20h
0x18002b640  mov     rbp, rdx
0x18002b643  mov     rax, [rcx]
0x18002b646  mov     edx, [rax]
0x18002b648  mov     [rbp+60h], rcx
0x18002b64c  mov     [rbp+30h], edx
0x18002b64f  mov     rax, [rbp+60h]
0x18002b653  mov     rcx, [rax]
0x18002b656  mov     [rbp+48h], rcx
0x18002b65a  mov     eax, [rbp+30h]
0x18002b65d  cmp     eax, 0C0000006h
0x18002b662  jz      short loc_18002B66E
0x18002b664  mov     eax, [rbp+30h]
0x18002b667  cmp     eax, 0C0000005h
0x18002b66c  jnz     short loc_18002B6A1
0x18002b66e  mov     rax, [rbp+48h]
0x18002b672  cmp     qword ptr [rax+20h], 0
0x18002b677  jnz     short loc_18002B6A1
0x18002b679  mov     rax, [rbp+48h]
0x18002b67d  mov     rdx, [rbp+80h]
0x18002b684  cmp     [rax+28h], rdx
0x18002b688  jb      short loc_18002B6A1
0x18002b68a  mov     rcx, [rbp+48h]
0x18002b68e  lea     rax, [rdx+40h]
0x18002b692  cmp     [rcx+28h], rax
0x18002b696  jnb     short loc_18002B6A1
0x18002b698  mov     dword ptr [rbp+38h], 1
0x18002b69f  jmp     short loc_18002B6A8
0x18002b6a1  mov     dword ptr [rbp+38h], 0
0x18002b6a8  mov     eax, [rbp+38h]
0x18002b6ab  add     rsp, 20h
0x18002b6af  pop     rbp
0x18002b6b0  retn
0x18002b6b2  push    rbp
0x18002b6b4  sub     rsp, 20h
0x18002b6b8  mov     rbp, rdx
0x18002b6bb  mov     rax, [rcx]
0x18002b6be  mov     edx, [rax]
0x18002b6c0  mov     [rbp+58h], rcx
0x18002b6c4  mov     [rbp+20h], edx
0x18002b6c7  mov     rax, [rbp+58h]
0x18002b6cb  mov     rcx, [rax]
0x18002b6ce  mov     [rbp+40h], rcx
0x18002b6d2  mov     eax, [rbp+20h]
0x18002b6d5  cmp     eax, 0C0000006h
0x18002b6da  jz      short loc_18002B6E6
0x18002b6dc  mov     eax, [rbp+20h]
0x18002b6df  cmp     eax, 0C0000005h
0x18002b6e4  jnz     short loc_18002B719
0x18002b6e6  mov     rax, [rbp+40h]
0x18002b6ea  cmp     qword ptr [rax+20h], 0
0x18002b6ef  jnz     short loc_18002B719
0x18002b6f1  mov     rax, [rbp+40h]
0x18002b6f5  mov     rdx, [rbp+50h]
0x18002b6f9  cmp     [rax+28h], rdx
0x18002b6fd  jb      short loc_18002B719
0x18002b6ff  mov     rcx, [rbp+40h]
0x18002b703  lea     rax, [rdx+108h]
0x18002b70a  cmp     [rcx+28h], rax
0x18002b70e  jnb     short loc_18002B719
0x18002b710  mov     dword ptr [rbp+28h], 1
0x18002b717  jmp     short loc_18002B720
0x18002b719  mov     dword ptr [rbp+28h], 0
0x18002b720  mov     eax, [rbp+28h]
0x18002b723  add     rsp, 20h
0x18002b727  pop     rbp
0x18002b728  retn
```
