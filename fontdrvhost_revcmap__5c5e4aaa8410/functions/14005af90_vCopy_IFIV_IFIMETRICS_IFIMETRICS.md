# vCopy_IFIV(_IFIMETRICS *,_IFIMETRICS *)

- ea: `0x14005af90`
- end: `0x14005b051`
- name: `?vCopy_IFIV@@YAXPEAU_IFIMETRICS@@0@Z`
- size: `193`
- prototype: `void __fastcall(struct _IFIMETRICS *Src, struct _IFIMETRICS *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140007f98`
- `0x14000978c`

## callees

- `0x14005af90`
- `0x140076eea`

## pseudocode

```c
void __fastcall vCopy_IFIV(struct _IFIMETRICS *Src, struct _IFIMETRICS *a2)
{
  __int64 dpwszFaceName; // rax
  _WORD *v5; // r8
  _WORD *v6; // rdx
  __int64 dpwszFamilyName; // rax
  __int16 *v8; // rdx
  _WORD *v9; // rcx
  __int16 v10; // ax
  _WORD *v11; // rdx
  _WORD *v12; // rcx

  memcpy_0(a2, Src, Src->cjThis);
  dpwszFaceName = a2->dpwszFaceName;
  v5 = (_WORD *)((char *)Src + Src->dpwszFaceName);
  v6 = (_WORD *)((char *)&a2->cjThis + dpwszFaceName + 2);
  *(_WORD *)((char *)&a2->cjThis + dpwszFaceName) = 64;
  while ( *v5 )
    *v6++ = *v5++;
  *v6 = 0;
  dpwszFamilyName = a2->dpwszFamilyName;
  v8 = (__int16 *)((char *)Src + Src->dpwszFamilyName);
  v9 = (_WORD *)((char *)&a2->cjThis + dpwszFamilyName + 2);
  *(_WORD *)((char *)&a2->cjThis + dpwszFamilyName) = 64;
  while ( 1 )
  {
    v10 = *v8;
    if ( !*v8 )
      break;
    ++v8;
    *v9++ = v10;
  }
  *v9 = 0;
  if ( (a2->flInfo & 0x8000000) != 0 )
  {
    v11 = v8 + 1;
    v9[1] = 64;
    v12 = v9 + 2;
    while ( *v11 )
      *v12++ = *v11++;
    *(_DWORD *)v12 = 0;
  }
}

```

## disassembly

```asm
0x14005af90  mov     [rsp+arg_0], rbx
0x14005af95  push    rdi
0x14005af96  sub     rsp, 20h
0x14005af9a  mov     r8d, [rcx]; Size
0x14005af9d  mov     rbx, rdx
0x14005afa0  mov     rdx, rcx; Src
0x14005afa3  mov     rdi, rcx
0x14005afa6  mov     rcx, rbx; void *
0x14005afa9  call    memcpy_0
0x14005afae  movsxd  rax, dword ptr [rbx+10h]
0x14005afb2  lea     rdx, [rbx+2]
0x14005afb6  movsxd  r8, dword ptr [rdi+10h]
0x14005afba  mov     r10d, 40h ; '@'
0x14005afc0  add     r8, rdi
0x14005afc3  add     rdx, rax
0x14005afc6  xor     r9d, r9d
0x14005afc9  mov     [rax+rbx], r10w
0x14005afce  jmp     short loc_14005AFDB
0x14005afd0  mov     [rdx], ax
0x14005afd3  lea     r8, [r8+2]
0x14005afd7  add     rdx, 2
0x14005afdb  movzx   eax, word ptr [r8]
0x14005afdf  test    ax, ax
0x14005afe2  jnz     short loc_14005AFD0
0x14005afe4  mov     [rdx], r9w
0x14005afe8  lea     rcx, [rbx+2]
0x14005afec  movsxd  rax, dword ptr [rbx+8]
0x14005aff0  movsxd  rdx, dword ptr [rdi+8]
0x14005aff4  add     rdx, rdi
0x14005aff7  add     rcx, rax
0x14005affa  mov     [rax+rbx], r10w
0x14005afff  jmp     short loc_14005B00C
0x14005b001  add     rdx, 2
0x14005b005  mov     [rcx], ax
0x14005b008  add     rcx, 2
0x14005b00c  movzx   eax, word ptr [rdx]
0x14005b00f  test    ax, ax
0x14005b012  jnz     short loc_14005B001
0x14005b014  mov     [rcx], r9w
0x14005b018  test    dword ptr [rbx+30h], 8000000h
0x14005b01f  jz      short loc_14005B046
0x14005b021  add     rdx, 2
0x14005b025  mov     [rcx+2], r10w
0x14005b02a  add     rcx, 4
0x14005b02e  jmp     short loc_14005B03B
0x14005b030  mov     [rcx], ax
0x14005b033  lea     rdx, [rdx+2]
0x14005b037  add     rcx, 2
0x14005b03b  movzx   eax, word ptr [rdx]
0x14005b03e  test    ax, ax
0x14005b041  jnz     short loc_14005B030
0x14005b043  mov     [rcx], r9d
0x14005b046  mov     rbx, [rsp+28h+arg_0]
0x14005b04b  add     rsp, 20h
0x14005b04f  pop     rdi
0x14005b050  retn
```
