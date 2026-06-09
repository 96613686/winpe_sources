# std::basic_stringbuf<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Tidy(void)

- ea: `0x18000eba8`
- end: `0x18000ec7f`
- name: `?_Tidy@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IEAAXXZ`
- size: `215`
- prototype: `_DWORD *__fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000dd1c`
- `0x18000de50`
- `0x18000f750`

## callees

- `0x180002c8c`
- `0x18000eba8`

## pseudocode

```c
_DWORD *__fastcall std::basic_stringbuf<unsigned short>::_Tidy(__int64 a1)
{
  __int64 v2; // rdx
  __int64 v3; // rdx
  char **v4; // rax
  char *v5; // rcx
  char *v6; // rax
  _DWORD *result; // rax

  if ( (*(_BYTE *)(a1 + 112) & 1) != 0 )
  {
    v2 = **(_QWORD **)(a1 + 64);
    if ( v2 )
      v3 = v2 + 2LL * **(int **)(a1 + 88);
    else
      v3 = **(_QWORD **)(a1 + 56) + 2LL * **(int **)(a1 + 80);
    v4 = *(char ***)(a1 + 24);
    v5 = *v4;
    if ( (unsigned __int64)(2 * ((v3 - (__int64)*v4) >> 1)) < 0x1000 )
    {
      v6 = *v4;
    }
    else
    {
      v6 = (char *)*((_QWORD *)v5 - 1);
      if ( (unsigned __int64)(v5 - v6 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v6);
  }
  **(_QWORD **)(a1 + 24) = 0;
  **(_QWORD **)(a1 + 56) = 0;
  **(_DWORD **)(a1 + 80) = 0;
  **(_QWORD **)(a1 + 32) = 0;
  **(_QWORD **)(a1 + 64) = 0;
  result = *(_DWORD **)(a1 + 88);
  *result = 0;
  *(_DWORD *)(a1 + 112) &= ~1u;
  *(_QWORD *)(a1 + 104) = 0;
  return result;
}

```

## disassembly

```asm
0x18000eba8  mov     [rsp+arg_0], rbx
0x18000ebad  push    rdi
0x18000ebae  sub     rsp, 20h
0x18000ebb2  test    byte ptr [rcx+70h], 1
0x18000ebb6  mov     rbx, rcx
0x18000ebb9  jz      short loc_18000EC28
0x18000ebbb  mov     rax, [rcx+40h]
0x18000ebbf  mov     rdx, [rax]
0x18000ebc2  test    rdx, rdx
0x18000ebc5  jz      short loc_18000EBD4
0x18000ebc7  mov     rax, [rcx+58h]
0x18000ebcb  movsxd  rcx, dword ptr [rax]
0x18000ebce  lea     rdx, [rdx+rcx*2]
0x18000ebd2  jmp     short loc_18000EBE6
0x18000ebd4  mov     rax, [rcx+50h]
0x18000ebd8  movsxd  rdx, dword ptr [rax]
0x18000ebdb  mov     rax, [rcx+38h]
0x18000ebdf  mov     rcx, [rax]
0x18000ebe2  lea     rdx, [rcx+rdx*2]
0x18000ebe6  mov     rax, [rbx+18h]
0x18000ebea  mov     rcx, [rax]
0x18000ebed  sub     rdx, rcx
0x18000ebf0  sar     rdx, 1
0x18000ebf3  add     rdx, rdx; unsigned __int64
0x18000ebf6  cmp     rdx, 1000h
0x18000ebfd  jb      short loc_18000EC1D
0x18000ebff  mov     rax, [rcx-8]
0x18000ec03  sub     rcx, rax
0x18000ec06  sub     rcx, 8
0x18000ec0a  cmp     rcx, 1Fh
0x18000ec0e  ja      short loc_18000EC16
0x18000ec10  add     rdx, 27h ; '''
0x18000ec14  jmp     short loc_18000EC20
0x18000ec16  mov     ecx, 5
0x18000ec1b  int     29h; Win8: RtlFailFast(ecx)
0x18000ec1d  mov     rax, rcx
0x18000ec20  mov     rcx, rax; void *
0x18000ec23  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ec28  mov     rax, [rbx+18h]
0x18000ec2c  mov     qword ptr [rax], 0
0x18000ec33  mov     rax, [rbx+38h]
0x18000ec37  mov     qword ptr [rax], 0
0x18000ec3e  mov     rax, [rbx+50h]
0x18000ec42  mov     dword ptr [rax], 0
0x18000ec48  mov     rax, [rbx+20h]
0x18000ec4c  mov     qword ptr [rax], 0
0x18000ec53  mov     rax, [rbx+40h]
0x18000ec57  mov     qword ptr [rax], 0
0x18000ec5e  mov     rax, [rbx+58h]
0x18000ec62  mov     dword ptr [rax], 0
0x18000ec68  and     dword ptr [rbx+70h], 0FFFFFFFEh
0x18000ec6c  mov     qword ptr [rbx+68h], 0
0x18000ec74  mov     rbx, [rsp+28h+arg_0]
0x18000ec79  add     rsp, 20h
0x18000ec7d  pop     rdi
0x18000ec7e  retn
```
