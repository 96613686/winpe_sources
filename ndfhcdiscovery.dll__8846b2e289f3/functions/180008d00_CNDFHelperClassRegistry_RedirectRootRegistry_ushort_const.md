# CNDFHelperClassRegistry::RedirectRootRegistry(ushort const *)

- ea: `0x180008d00`
- end: `0x180008d55`
- name: `?RedirectRootRegistry@CNDFHelperClassRegistry@@UEAAJPEBG@Z`
- size: `85`
- prototype: `__int64 __fastcall(CNDFHelperClassRegistry *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180008d00`

## pseudocode

```c
__int64 __fastcall CNDFHelperClassRegistry::RedirectRootRegistry(
        CNDFHelperClassRegistry *this,
        const unsigned __int16 *a2)
{
  _WORD *v2; // rcx
  __int64 v3; // rax
  __int64 v4; // r8
  _WORD *v5; // rdx
  __int64 result; // rax

  v2 = (_WORD *)((char *)this + 64);
  v3 = 2147483646;
  v4 = 260;
  do
  {
    if ( !v3 )
      break;
    if ( !*a2 )
      break;
    *v2++ = *a2++;
    --v3;
    --v4;
  }
  while ( v4 );
  v5 = v2 - 1;
  result = v4 == 0 ? 0x8007007A : 0;
  if ( v4 )
    v5 = v2;
  *v5 = 0;
  return result;
}

```

## disassembly

```asm
0x180008d00  add     rcx, 40h ; '@'
0x180008d04  mov     eax, 7FFFFFFEh
0x180008d09  xor     r10d, r10d
0x180008d0c  mov     r8d, 104h
0x180008d12  test    rax, rax
0x180008d15  jz      short loc_180008D36
0x180008d17  movzx   r9d, word ptr [rdx]
0x180008d1b  test    r9w, r9w
0x180008d1f  jz      short loc_180008D36
0x180008d21  mov     [rcx], r9w
0x180008d25  add     rdx, 2
0x180008d29  add     rcx, 2
0x180008d2d  dec     rax
0x180008d30  sub     r8, 1
0x180008d34  jnz     short loc_180008D12
0x180008d36  mov     rax, r8
0x180008d39  lea     rdx, [rcx-2]
0x180008d3d  neg     rax
0x180008d40  sbb     eax, eax
0x180008d42  not     eax
0x180008d44  and     eax, 8007007Ah
0x180008d49  test    r8, r8
0x180008d4c  cmovnz  rdx, rcx
0x180008d50  mov     [rdx], r10w
0x180008d54  retn
```
