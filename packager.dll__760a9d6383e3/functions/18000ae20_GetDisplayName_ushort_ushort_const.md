# GetDisplayName(ushort *,ushort const *)

- ea: `0x18000ae20`
- end: `0x18000ae7e`
- name: `?GetDisplayName@@YAXPEAGPEBG@Z`
- size: `94`
- prototype: `void __fastcall(unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800089f8`
- `0x18000baa0`
- `0x18000c440`

## callees

- `0x18000ae20`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x18000ae35`
- `SHLWAPI!PathFindFileNameW` at `0x18000ae35`

## pseudocode

```c
void __fastcall GetDisplayName(unsigned __int16 *a1, const unsigned __int16 *a2)
{
  __int64 v3; // rdi
  LPWSTR FileNameW; // rax
  __int64 v5; // rdx
  unsigned __int16 *v6; // rcx

  v3 = 2147483646;
  FileNameW = PathFindFileNameW(a2);
  v5 = 260;
  do
  {
    if ( !v3 )
      break;
    if ( !*FileNameW )
      break;
    *a1++ = *FileNameW++;
    --v3;
    --v5;
  }
  while ( v5 );
  v6 = a1 - 1;
  if ( v5 )
    v6 = a1;
  *v6 = 0;
}

```

## disassembly

```asm
0x18000ae20  mov     [rsp+arg_0], rbx
0x18000ae25  push    rdi
0x18000ae26  sub     rsp, 20h
0x18000ae2a  mov     rbx, rcx
0x18000ae2d  mov     edi, 7FFFFFFEh
0x18000ae32  mov     rcx, rdx; pszPath
0x18000ae35  call    cs:__imp_PathFindFileNameW
0x18000ae3b  mov     edx, 104h
0x18000ae40  xor     r8d, r8d
0x18000ae43  test    rdi, rdi
0x18000ae46  jz      short loc_18000AE64
0x18000ae48  movzx   ecx, word ptr [rax]
0x18000ae4b  test    cx, cx
0x18000ae4e  jz      short loc_18000AE64
0x18000ae50  mov     [rbx], cx
0x18000ae53  add     rax, 2
0x18000ae57  add     rbx, 2
0x18000ae5b  dec     rdi
0x18000ae5e  sub     rdx, 1
0x18000ae62  jnz     short loc_18000AE43
0x18000ae64  lea     rcx, [rbx-2]
0x18000ae68  test    rdx, rdx
0x18000ae6b  cmovnz  rcx, rbx
0x18000ae6f  mov     rbx, [rsp+28h+arg_0]
0x18000ae74  mov     [rcx], r8w
0x18000ae78  add     rsp, 20h
0x18000ae7c  pop     rdi
0x18000ae7d  retn
```
