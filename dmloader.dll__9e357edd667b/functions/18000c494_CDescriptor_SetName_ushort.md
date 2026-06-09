# CDescriptor::SetName(ushort *)

- ea: `0x18000c494`
- end: `0x18000c5d1`
- name: `?SetName@CDescriptor@@QEAAXPEAG@Z`
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
- `0x18000c494`

## pseudocode

```c
void __fastcall CDescriptor::SetName(CDescriptor *this, unsigned __int16 *a2)
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
    v4 = (void *)*((_QWORD *)this + 8);
    if ( v4 )
      operator delete(v4);
    *((_DWORD *)this + 2) &= ~4u;
    v5 = &v14;
    *((_QWORD *)this + 8) = 0;
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
      *((_QWORD *)this + 8) = v11;
      if ( v11 )
      {
        StringCchCopyNW(v11, v10, &v14, v10);
        v13 = *((_DWORD *)this + 2) | 4;
        goto LABEL_16;
      }
      v12 = *((_DWORD *)this + 2);
    }
    else
    {
      v12 = *((_DWORD *)this + 2);
    }
    v13 = v12 & 0xFFFFFFFB;
LABEL_16:
    *((_DWORD *)this + 2) = v13;
  }
}

```

## disassembly

```asm
0x18000c494  test    rdx, rdx
0x18000c497  jz      locret_18000C5AB
0x18000c49d  mov     [rsp+arg_8], rbx
0x18000c4a2  mov     [rsp+arg_10], rsi
0x18000c4a7  push    rdi
0x18000c4a8  sub     rsp, 0B0h
0x18000c4af  mov     rax, cs:__security_cookie
0x18000c4b6  xor     rax, rsp
0x18000c4b9  mov     [rsp+0B8h+var_18], rax
0x18000c4c1  xor     esi, esi
0x18000c4c3  mov     rdi, rdx
0x18000c4c6  mov     rbx, rcx
0x18000c4c9  mov     [rsp+0B8h+var_98], si
0x18000c4ce  xor     edx, edx; Val
0x18000c4d0  lea     rcx, [rsp+0B8h+var_96]; void *
0x18000c4d5  lea     r8d, [rsi+7Eh]; Size
0x18000c4d9  call    memset_0
0x18000c4de  mov     rcx, [rbx+40h]; void *
0x18000c4e2  test    rcx, rcx
0x18000c4e5  jz      short loc_18000C4EC
0x18000c4e7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c4ec  and     dword ptr [rbx+8], 0FFFFFFFBh
0x18000c4f0  lea     r9, [rsp+0B8h+var_98]
0x18000c4f5  mov     [rbx+40h], rsi
0x18000c4f9  mov     eax, 7FFFFFFEh
0x18000c4fe  mov     edx, 40h ; '@'
0x18000c503  test    rax, rax
0x18000c506  jz      short loc_18000C525
0x18000c508  movzx   ecx, word ptr [rdi]
0x18000c50b  test    cx, cx
0x18000c50e  jz      short loc_18000C525
0x18000c510  mov     [r9], cx
0x18000c514  add     rdi, 2
0x18000c518  add     r9, 2
0x18000c51c  dec     rax
0x18000c51f  sub     rdx, 1
0x18000c523  jnz     short loc_18000C503
0x18000c525  mov     rax, rdx
0x18000c528  lea     rcx, [r9-2]
0x18000c52c  neg     rax
0x18000c52f  sbb     r8d, r8d
0x18000c532  not     r8d
0x18000c535  and     r8d, 8007007Ah
0x18000c53c  test    rdx, rdx
0x18000c53f  cmovnz  rcx, r9
0x18000c543  mov     [rcx], si
0x18000c546  jz      short loc_18000C5C4
0x18000c548  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000c54c  lea     rax, [rsp+0B8h+var_98]
0x18000c551  mov     rcx, r8
0x18000c554  inc     rcx
0x18000c557  cmp     [rax+rcx*2], si
0x18000c55b  jnz     short loc_18000C554
0x18000c55d  lea     rdi, [rcx+1]
0x18000c561  mov     eax, 2
0x18000c566  mul     rdi
0x18000c569  cmovb   rax, r8
0x18000c56d  mov     rcx, rax; unsigned __int64
0x18000c570  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c575  mov     [rbx+40h], rax
0x18000c579  test    rax, rax
0x18000c57c  jnz     short loc_18000C5AC
0x18000c57e  mov     eax, [rbx+8]
0x18000c581  and     eax, 0FFFFFFFBh
0x18000c584  mov     [rbx+8], eax
0x18000c587  mov     rcx, [rsp+0B8h+var_18]
0x18000c58f  xor     rcx, rsp; StackCookie
0x18000c592  call    __security_check_cookie
0x18000c597  lea     r11, [rsp+0B8h+var_8]
0x18000c59f  mov     rbx, [r11+18h]
0x18000c5a3  mov     rsi, [r11+20h]
0x18000c5a7  mov     rsp, r11
0x18000c5aa  pop     rdi
0x18000c5ab  retn
0x18000c5ac  mov     r9, rdi; unsigned __int64
0x18000c5af  lea     r8, [rsp+0B8h+var_98]; unsigned __int16 *
0x18000c5b4  mov     rdx, rdi; unsigned __int64
0x18000c5b7  mov     rcx, rax; unsigned __int16 *
0x18000c5ba  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000c5bf  mov     eax, [rbx+8]
0x18000c5c2  jmp     short loc_18000C5CC
0x18000c5c4  mov     eax, [rbx+8]
0x18000c5c7  test    r8d, r8d
0x18000c5ca  js      short loc_18000C581
0x18000c5cc  or      eax, 4
0x18000c5cf  jmp     short loc_18000C584
```
