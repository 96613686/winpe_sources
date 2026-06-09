# NpSetAttributeInList

- ea: `0x140013ec0`
- end: `0x1400140ed`
- name: `NpSetAttributeInList`
- size: `557`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, _BYTE *, const void *, size_t Size)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000b84c`
- `0x1400127f0`
- `0x14001399c`

## callees

- `0x140001f40`
- `0x140013ec0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140014032`
- `ntoskrnl!ExAllocatePool2` at `0x140014032`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400140a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400140a3`

## string_xrefs

- `0x140013f7b`: `ServerProcessId`
- `0x140013f8d`: `ClientComputerName`
- `0x140013f96`: `ClientProcessId`
- `0x140013fa8`: `RestrictedAccess`

## pseudocode

```c
__int64 __fastcall NpSetAttributeInList(_QWORD *a1, _QWORD *a2, _BYTE *a3, const void *a4, size_t Size)
{
  _QWORD *i; // rdi
  unsigned __int64 v10; // rdx
  size_t v11; // r14
  _QWORD *Pool2; // rbx
  const char *v13; // rdx
  signed __int64 v14; // r8
  int v15; // eax
  int v16; // ecx
  __int64 v17; // rax
  __int64 result; // rax
  char *v20; // rcx
  _QWORD *v21; // rax
  _QWORD *v22; // rcx
  _QWORD *v23; // rax

  for ( i = (_QWORD *)*a1; i != a1; i = (_QWORD *)*i )
  {
    if ( (unsigned __int64)a3 >= 8 )
    {
      v13 = (const char *)i[2];
      switch ( (int)v13 )
      {
        case 1:
          v13 = "ServerProcessId";
          break;
        case 2:
          v13 = "ServerSessionId";
          break;
        case 3:
          v13 = "ClientProcessId";
          break;
        case 4:
          v13 = "ClientSessionId";
          break;
        case 6:
          v13 = "ClientComputerName";
          break;
        case 7:
          v13 = "RestrictedAccess";
          break;
        default:
          break;
      }
      v14 = a3 - v13;
      do
      {
        v15 = (unsigned __int8)v13[v14];
        v16 = *(unsigned __int8 *)v13 - v15;
        if ( v16 )
          break;
        ++v13;
      }
      while ( v15 );
      if ( !v16 )
        goto LABEL_25;
    }
    else if ( (_BYTE *)i[2] == a3 )
    {
      goto LABEL_4;
    }
  }
  i = 0;
LABEL_25:
  if ( (unsigned __int64)a3 <= 8 )
  {
LABEL_4:
    v10 = 40;
    v11 = 0;
  }
  else
  {
    v17 = -1;
    while ( a3[++v17] != 0 )
      ;
    v11 = v17 + 1;
    v10 = v17 + 41;
    if ( (unsigned __int64)(v17 + 41) < 0x28 )
      return 3221225621LL;
  }
  if ( Size > 8 )
  {
    if ( v10 + Size < v10 )
      return 3221225621LL;
    v10 += Size;
  }
  if ( a2 )
  {
    Pool2 = a2;
  }
  else
  {
    Pool2 = (_QWORD *)ExAllocatePool2(256, v10, 1950445646);
    if ( !Pool2 )
      return 3221225626LL;
  }
  if ( (unsigned __int64)a3 <= 8 )
  {
    Pool2[2] = a3;
  }
  else
  {
    Pool2[2] = Pool2 + 5;
    memmove(Pool2 + 5, a3, v11);
  }
  if ( Size <= 8 )
  {
    v20 = (char *)(Pool2 + 4);
  }
  else
  {
    v20 = (char *)Pool2 + v11 + 40;
    Pool2[4] = v20;
  }
  memmove(v20, a4, Size);
  Pool2[3] = Size;
  if ( i )
  {
    v21 = (_QWORD *)*i;
    if ( *(_QWORD **)(*i + 8LL) != i || (v22 = (_QWORD *)i[1], (_QWORD *)*v22 != i) )
LABEL_42:
      __fastfail(3u);
    *v22 = v21;
    v21[1] = v22;
    if ( i != a2 )
      ExFreePoolWithTag(i, 0);
  }
  v23 = (_QWORD *)a1[1];
  if ( (_QWORD *)*v23 != a1 )
    goto LABEL_42;
  Pool2[1] = v23;
  *Pool2 = a1;
  *v23 = Pool2;
  result = 0;
  a1[1] = Pool2;
  return result;
}

```

## disassembly

```asm
0x140013ec0  mov     [rsp+arg_8], rbp
0x140013ec5  mov     [rsp+arg_10], rsi
0x140013eca  push    rdi
0x140013ecb  push    r12
0x140013ecd  push    r13
0x140013ecf  push    r14
0x140013ed1  push    r15
0x140013ed3  sub     rsp, 20h
0x140013ed7  mov     rdi, [rcx]
0x140013eda  mov     r13, r9
0x140013edd  mov     rbp, r8
0x140013ee0  mov     r12, rdx
0x140013ee3  mov     r15, rcx
0x140013ee6  cmp     rdi, rcx
0x140013ee9  jz      loc_140013FE3
0x140013eef  lea     r9, cs:140000000h
0x140013ef6  cmp     rbp, 8
0x140013efa  jnb     short loc_140013F5C
0x140013efc  cmp     [rdi+10h], rbp
0x140013f00  jnz     loc_140013FD7
0x140013f06  mov     edx, 28h ; '('
0x140013f0b  xor     r14d, r14d
0x140013f0e  mov     rsi, [rsp+48h+Size]
0x140013f13  cmp     rsi, 8
0x140013f17  jbe     short loc_140013F29
0x140013f19  lea     rax, [rdx+rsi]
0x140013f1d  cmp     rax, rdx
0x140013f20  jb      loc_14001401D
0x140013f26  mov     rdx, rax
0x140013f29  mov     [rsp+48h+arg_0], rbx
0x140013f2e  test    r12, r12
0x140013f31  jz      loc_140014027
0x140013f37  mov     rbx, r12
0x140013f3a  cmp     rbp, 8
0x140013f3e  jbe     loc_140014051
0x140013f44  lea     rcx, [rbx+28h]; void *
0x140013f48  mov     r8, r14; Size
0x140013f4b  mov     rdx, rbp; Src
0x140013f4e  mov     [rbx+10h], rcx
0x140013f52  call    memmove
0x140013f57  jmp     loc_140014055
0x140013f5c  mov     rdx, [rdi+10h]
0x140013f60  lea     eax, [rdx-1]; switch 7 cases
0x140013f63  cmp     eax, 6
0x140013f66  ja      short def_140013F75; jumptable 0000000140013F75 default case, case 5
0x140013f68  cdqe
0x140013f6a  mov     ecx, ds:(jpt_140013F75 - 140000000h)[r9+rax*4]
0x140013f72  add     rcx, r9
0x140013f75  jmp     rcx; switch jump
0x140013f7b  lea     rdx, aServerprocessi; jumptable 0000000140013F75 case 1
0x140013f82  jmp     short def_140013F75; jumptable 0000000140013F75 default case, case 5
0x140013f84  lea     rdx, aServersessioni; jumptable 0000000140013F75 case 2
0x140013f8b  jmp     short def_140013F75; jumptable 0000000140013F75 default case, case 5
0x140013f8d  lea     rdx, Str2; jumptable 0000000140013F75 case 6
0x140013f94  jmp     short def_140013F75; jumptable 0000000140013F75 default case, case 5
0x140013f96  lea     rdx, aClientprocessi; jumptable 0000000140013F75 case 3
0x140013f9d  jmp     short def_140013F75; jumptable 0000000140013F75 default case, case 5
0x140013f9f  lea     rdx, aClientsessioni; jumptable 0000000140013F75 case 4
0x140013fa6  jmp     short def_140013F75; jumptable 0000000140013F75 default case, case 5
0x140013fa8  lea     rdx, aRestrictedacce; jumptable 0000000140013F75 case 7
0x140013faf  mov     r8, rbp; jumptable 0000000140013F75 default case, case 5
0x140013fb2  sub     r8, rdx
0x140013fb5  nop     word ptr [rax+rax+00000000h]
0x140013fc0  movzx   ecx, byte ptr [rdx]
0x140013fc3  movzx   eax, byte ptr [rdx+r8]
0x140013fc8  sub     ecx, eax
0x140013fca  jnz     short loc_140013FD3
0x140013fcc  inc     rdx
0x140013fcf  test    eax, eax
0x140013fd1  jnz     short loc_140013FC0
0x140013fd3  test    ecx, ecx
0x140013fd5  jz      short loc_140013FE5
0x140013fd7  mov     rdi, [rdi]
0x140013fda  cmp     rdi, r15
0x140013fdd  jnz     loc_140013EF6
0x140013fe3  xor     edi, edi
0x140013fe5  cmp     rbp, 8
0x140013fe9  jbe     loc_140013F06
0x140013fef  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140013ff6  nop     word ptr [rax+rax+00000000h]
0x140014000  cmp     byte ptr [rax+rbp+1], 0
0x140014005  lea     rax, [rax+1]
0x140014009  jnz     short loc_140014000
0x14001400b  lea     r14, [rax+1]
0x14001400f  lea     rdx, [r14+28h]
0x140014013  cmp     rdx, 28h ; '('
0x140014017  jnb     loc_140013F0E
0x14001401d  mov     eax, 0C0000095h
0x140014022  jmp     loc_1400140D4
0x140014027  mov     ecx, 100h
0x14001402c  mov     r8d, 7441704Eh
0x140014032  call    cs:__imp_ExAllocatePool2
0x140014039  nop     dword ptr [rax+rax+00h]
0x14001403e  mov     rbx, rax
0x140014041  test    rax, rax
0x140014044  jnz     loc_140013F3A
0x14001404a  mov     eax, 0C000009Ah
0x14001404f  jmp     short loc_1400140CF
0x140014051  mov     [rbx+10h], rbp
0x140014055  mov     r8, rsi; Size
0x140014058  mov     rdx, r13; Src
0x14001405b  cmp     rsi, 8
0x14001405f  jbe     short loc_14001406E
0x140014061  lea     rcx, [r14+28h]
0x140014065  add     rcx, rbx
0x140014068  mov     [rbx+20h], rcx
0x14001406c  jmp     short loc_140014072
0x14001406e  lea     rcx, [rbx+20h]; void *
0x140014072  call    memmove
0x140014077  mov     [rbx+18h], rsi
0x14001407b  test    rdi, rdi
0x14001407e  jz      short loc_1400140AF
0x140014080  mov     rax, [rdi]
0x140014083  cmp     [rax+8], rdi
0x140014087  jnz     short loc_1400140B8
0x140014089  mov     rcx, [rdi+8]
0x14001408d  cmp     [rcx], rdi
0x140014090  jnz     short loc_1400140B8
0x140014092  mov     [rcx], rax
0x140014095  mov     [rax+8], rcx
0x140014099  cmp     rdi, r12
0x14001409c  jz      short loc_1400140AF
0x14001409e  xor     edx, edx; Tag
0x1400140a0  mov     rcx, rdi; P
0x1400140a3  call    cs:__imp_ExFreePoolWithTag
0x1400140aa  nop     dword ptr [rax+rax+00h]
0x1400140af  mov     rax, [r15+8]
0x1400140b3  cmp     [rax], r15
0x1400140b6  jz      short loc_1400140BF
0x1400140b8  mov     ecx, 3
0x1400140bd  int     29h; Win8: RtlFailFast(ecx)
0x1400140bf  mov     [rbx+8], rax
0x1400140c3  mov     [rbx], r15
0x1400140c6  mov     [rax], rbx
0x1400140c9  xor     eax, eax
0x1400140cb  mov     [r15+8], rbx
0x1400140cf  mov     rbx, [rsp+48h+arg_0]
0x1400140d4  mov     rbp, [rsp+48h+arg_8]
0x1400140d9  mov     rsi, [rsp+48h+arg_10]
0x1400140de  add     rsp, 20h
0x1400140e2  pop     r15
0x1400140e4  pop     r14
0x1400140e6  pop     r13
0x1400140e8  pop     r12
0x1400140ea  pop     rdi
0x1400140eb  retn
```
