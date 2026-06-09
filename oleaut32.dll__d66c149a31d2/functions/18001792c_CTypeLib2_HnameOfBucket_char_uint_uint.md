# CTypeLib2::HnameOfBucket(char *,uint,uint)

- ea: `0x18001792c`
- end: `0x1800179b3`
- name: `?HnameOfBucket@CTypeLib2@@AEBAKPEADII@Z`
- size: `135`
- prototype: `unsigned int(CTypeLib2 *__hidden this, char *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180017220`

## callees

- `0x18001792c`

## import_xrefs

- `KERNELBASE!CompareStringA` at `0x180017997`
- `KERNELBASE!CompareStringA` at `0x180017997`

## pseudocode

```c
__int64 __fastcall CTypeLib2::HnameOfBucket(CTypeLib2 *this, char *a2, unsigned int a3, __int16 a4)
{
  unsigned int i; // edi
  __int64 v8; // rbx

  for ( i = *(_DWORD *)(*((_QWORD *)this + 24) + 4LL * a3); i != -1; i = *(_DWORD *)(v8 + 4) )
  {
    v8 = i >= *((_DWORD *)this + 51) ? 0LL : *((_QWORD *)this + 27) + i;
    if ( *(_WORD *)(v8 + 10) == a4
      && CompareStringA(*((_DWORD *)this + 99), 0x30001u, (PCNZCH)(v8 + 12), *(_WORD *)(v8 + 8) & 0x3FF, a2, -1) == 2 )
    {
      break;
    }
  }
  return i;
}

```

## disassembly

```asm
0x18001792c  push    rbx
0x18001792e  push    rbp
0x18001792f  push    rsi
0x180017930  push    rdi
0x180017931  push    r14
0x180017933  sub     rsp, 30h
0x180017937  mov     rax, [rcx+0C0h]
0x18001793e  mov     ebp, r9d
0x180017941  mov     r8d, r8d
0x180017944  mov     r14, rdx
0x180017947  mov     rsi, rcx
0x18001794a  mov     edi, [rax+r8*4]
0x18001794e  cmp     edi, 0FFFFFFFFh
0x180017951  jz      short loc_1800179A2
0x180017953  cmp     edi, [rsi+0CCh]
0x180017959  jnb     short loc_1800179AF
0x18001795b  mov     ebx, edi
0x18001795d  add     rbx, [rsi+0D8h]
0x180017964  cmp     [rbx+0Ah], bp
0x180017968  jz      short loc_18001796F
0x18001796a  mov     edi, [rbx+4]
0x18001796d  jmp     short loc_18001794E
0x18001796f  movzx   r9d, word ptr [rbx+8]
0x180017974  lea     r8, [rbx+0Ch]; lpString1
0x180017978  mov     ecx, [rsi+18Ch]; Locale
0x18001797e  and     r9d, 3FFh; cchCount1
0x180017985  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001798d  mov     edx, 30001h; dwCmpFlags
0x180017992  mov     [rsp+58h+lpString2], r14; lpString2
0x180017997  call    cs:__imp_CompareStringA
0x18001799d  cmp     eax, 2
0x1800179a0  jnz     short loc_18001796A
0x1800179a2  mov     eax, edi
0x1800179a4  add     rsp, 30h
0x1800179a8  pop     r14
0x1800179aa  pop     rdi
0x1800179ab  pop     rsi
0x1800179ac  pop     rbp
0x1800179ad  pop     rbx
0x1800179ae  retn
0x1800179af  xor     ebx, ebx
0x1800179b1  jmp     short loc_180017964
```
