# CDescriptor::SetCategory(ushort *)

- ea: `0x18000c14c`
- end: `0x18000c289`
- name: `?SetCategory@CDescriptor@@QEAAXPEAG@Z`
- size: `317`
- prototype: `void __fastcall(CDescriptor *__hidden this, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000a484`
- `0x18000b358`
- `0x18000c018`

## callees

- `0x1800015d0`
- `0x1800019a0`
- `0x1800019ac`
- `0x180001ef0`
- `0x180009f58`
- `0x18000c14c`

## pseudocode

```c
void __fastcall CDescriptor::SetCategory(CDescriptor *this, unsigned __int16 *a2)
{
  unsigned __int16 *v2; // rdi
  void *v4; // rcx
  unsigned __int16 *v5; // r9
  __int64 v6; // rax
  __int64 v7; // rdx
  unsigned __int16 *v8; // rcx
  __int64 v9; // rcx
  unsigned __int64 v10; // rdi
  unsigned __int16 *v11; // rax
  int v12; // eax
  unsigned int v13; // eax
  unsigned __int16 v14; // [rsp+20h] [rbp-98h] BYREF
  _BYTE v15[126]; // [rsp+22h] [rbp-96h] BYREF

  if ( a2 )
  {
    v2 = a2;
    v14 = 0;
    memset_0(v15, 0, sizeof(v15));
    v4 = (void *)*((_QWORD *)this + 9);
    if ( v4 )
      operator delete(v4);
    *((_DWORD *)this + 2) &= ~8u;
    v5 = &v14;
    *((_QWORD *)this + 9) = 0;
    v6 = 2147483646;
    v7 = 64;
    do
    {
      if ( !v6 )
        break;
      if ( !*v2 )
        break;
      *v5++ = *v2++;
      --v6;
      --v7;
    }
    while ( v7 );
    v8 = v5 - 1;
    if ( v7 )
      v8 = v5;
    *v8 = 0;
    if ( v7 )
    {
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)&v15[2 * v9 - 2] );
      v10 = v9 + 1;
      v11 = (unsigned __int16 *)operator new[](saturated_mul(v9 + 1, 2u));
      *((_QWORD *)this + 9) = v11;
      if ( v11 )
      {
        StringCchCopyNW(v11, v10, &v14, v10);
        v13 = *((_DWORD *)this + 2) | 8;
        goto LABEL_16;
      }
      v12 = *((_DWORD *)this + 2);
    }
    else
    {
      v12 = *((_DWORD *)this + 2);
    }
    v13 = v12 & 0xFFFFFFF7;
LABEL_16:
    *((_DWORD *)this + 2) = v13;
  }
}

```

## disassembly

```asm
0x18000c14c  test    rdx, rdx
0x18000c14f  jz      locret_18000C263
0x18000c155  mov     [rsp+arg_8], rbx
0x18000c15a  mov     [rsp+arg_10], rsi
0x18000c15f  push    rdi
0x18000c160  sub     rsp, 0B0h
0x18000c167  mov     rax, cs:__security_cookie
0x18000c16e  xor     rax, rsp
0x18000c171  mov     [rsp+0B8h+var_18], rax
0x18000c179  xor     esi, esi
0x18000c17b  mov     rdi, rdx
0x18000c17e  mov     rbx, rcx
0x18000c181  mov     [rsp+0B8h+var_98], si
0x18000c186  xor     edx, edx; Val
0x18000c188  lea     rcx, [rsp+0B8h+var_96]; void *
0x18000c18d  lea     r8d, [rsi+7Eh]; Size
0x18000c191  call    memset_0
0x18000c196  mov     rcx, [rbx+48h]; void *
0x18000c19a  test    rcx, rcx
0x18000c19d  jz      short loc_18000C1A4
0x18000c19f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c1a4  and     dword ptr [rbx+8], 0FFFFFFF7h
0x18000c1a8  lea     r9, [rsp+0B8h+var_98]
0x18000c1ad  mov     [rbx+48h], rsi
0x18000c1b1  mov     eax, 7FFFFFFEh
0x18000c1b6  mov     edx, 40h ; '@'
0x18000c1bb  test    rax, rax
0x18000c1be  jz      short loc_18000C1DD
0x18000c1c0  movzx   ecx, word ptr [rdi]
0x18000c1c3  test    cx, cx
0x18000c1c6  jz      short loc_18000C1DD
0x18000c1c8  mov     [r9], cx
0x18000c1cc  add     rdi, 2
0x18000c1d0  add     r9, 2
0x18000c1d4  dec     rax
0x18000c1d7  sub     rdx, 1
0x18000c1db  jnz     short loc_18000C1BB
0x18000c1dd  mov     rax, rdx
0x18000c1e0  lea     rcx, [r9-2]
0x18000c1e4  neg     rax
0x18000c1e7  sbb     r8d, r8d
0x18000c1ea  not     r8d
0x18000c1ed  and     r8d, 8007007Ah
0x18000c1f4  test    rdx, rdx
0x18000c1f7  cmovnz  rcx, r9
0x18000c1fb  mov     [rcx], si
0x18000c1fe  jz      short loc_18000C27C
0x18000c200  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000c204  lea     rax, [rsp+0B8h+var_98]
0x18000c209  mov     rcx, r8
0x18000c20c  inc     rcx
0x18000c20f  cmp     [rax+rcx*2], si
0x18000c213  jnz     short loc_18000C20C
0x18000c215  lea     rdi, [rcx+1]
0x18000c219  mov     eax, 2
0x18000c21e  mul     rdi
0x18000c221  cmovb   rax, r8
0x18000c225  mov     rcx, rax; unsigned __int64
0x18000c228  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c22d  mov     [rbx+48h], rax
0x18000c231  test    rax, rax
0x18000c234  jnz     short loc_18000C264
0x18000c236  mov     eax, [rbx+8]
0x18000c239  and     eax, 0FFFFFFF7h
0x18000c23c  mov     [rbx+8], eax
0x18000c23f  mov     rcx, [rsp+0B8h+var_18]
0x18000c247  xor     rcx, rsp; StackCookie
0x18000c24a  call    __security_check_cookie
0x18000c24f  lea     r11, [rsp+0B8h+var_8]
0x18000c257  mov     rbx, [r11+18h]
0x18000c25b  mov     rsi, [r11+20h]
0x18000c25f  mov     rsp, r11
0x18000c262  pop     rdi
0x18000c263  retn
0x18000c264  mov     r9, rdi; unsigned __int64
0x18000c267  lea     r8, [rsp+0B8h+var_98]; unsigned __int16 *
0x18000c26c  mov     rdx, rdi; unsigned __int64
0x18000c26f  mov     rcx, rax; unsigned __int16 *
0x18000c272  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000c277  mov     eax, [rbx+8]
0x18000c27a  jmp     short loc_18000C284
0x18000c27c  mov     eax, [rbx+8]
0x18000c27f  test    r8d, r8d
0x18000c282  js      short loc_18000C239
0x18000c284  or      eax, 8
0x18000c287  jmp     short loc_18000C23C
```
