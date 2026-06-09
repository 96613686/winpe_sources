# CCheckBase::GetCanonicalName(ushort * *)

- ea: `0x1800011c0`
- end: `0x180001311`
- name: `?GetCanonicalName@CCheckBase@@UEAAJPEAPEAG@Z`
- size: `337`
- prototype: `__int64 __fastcall(CCheckBase *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800011c0`
- `0x180009e16`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001223`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001223`

## pseudocode

```c
__int64 __fastcall CCheckBase::GetCanonicalName(CCheckBase *this, unsigned __int16 **a2)
{
  char *v3; // rdi
  unsigned __int64 v4; // rbx
  unsigned __int64 v5; // r14
  unsigned int v6; // esi
  unsigned __int16 *v8; // rax
  unsigned __int64 v9; // rcx
  unsigned __int16 *v10; // rdx
  __int64 v11; // r9
  unsigned __int64 v12; // r14

  v3 = (char *)this + 24;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)&v3[2 * v4] );
  v5 = v4 + 1;
  *a2 = 0;
  if ( v4 + 1 < v4 || !is_mul_ok(v5, 2u) )
    return (unsigned int)-2147024362;
  v8 = (unsigned __int16 *)CoTaskMemAlloc(2 * v5);
  *a2 = v8;
  v6 = -2147024882;
  if ( v8 )
    v6 = 0;
  if ( (v6 & 0x80000000) == 0 )
  {
    if ( (v8 || v4 == -1) && v5 <= 0x7FFFFFFF )
    {
      if ( v4 < 0x7FFFFFFF )
      {
        if ( !v3 )
        {
          v3 = byte_18000DBA8;
          v4 = 0;
        }
        if ( v5 )
        {
          v9 = v5;
          v10 = v8;
          v11 = 0;
          while ( v4 && *(_WORD *)v3 )
          {
            *v10 = *(_WORD *)v3;
            v3 += 2;
            ++v10;
            --v4;
            ++v11;
            if ( !--v9 )
            {
              *(v10 - 1) = 0;
              return v6;
            }
          }
          v12 = v5 - v11;
          *v10 = 0;
          if ( v12 > 1 && 2 * v12 > 2 )
            memset_0(&v8[v11 + 1], 0, 2 * v12 - 2);
        }
        return v6;
      }
      if ( v4 == -1 )
        return v6;
    }
    *v8 = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x1800011c0  mov     [rsp+arg_8], rbx
0x1800011c5  mov     [rsp+arg_10], rbp
0x1800011ca  push    rsi
0x1800011cb  push    rdi
0x1800011cc  push    r14
0x1800011ce  sub     rsp, 20h
0x1800011d2  mov     rsi, rdx
0x1800011d5  lea     rdi, [rcx+18h]
0x1800011d9  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800011e0  inc     rbx
0x1800011e3  cmp     word ptr [rdi+rbx*2], 0
0x1800011e8  jnz     short loc_1800011E0
0x1800011ea  xor     ebp, ebp
0x1800011ec  lea     r14, [rbx+1]
0x1800011f0  mov     [rdx], rbp
0x1800011f3  cmp     r14, rbx
0x1800011f6  jb      short loc_180001205
0x1800011f8  mov     eax, 2
0x1800011fd  mul     r14
0x180001200  test    rdx, rdx
0x180001203  jz      short loc_180001220
0x180001205  mov     esi, 80070216h
0x18000120a  mov     rbx, [rsp+38h+arg_8]
0x18000120f  mov     eax, esi
0x180001211  mov     rbp, [rsp+38h+arg_10]
0x180001216  add     rsp, 20h
0x18000121a  pop     r14
0x18000121c  pop     rdi
0x18000121d  pop     rsi
0x18000121e  retn
0x180001220  mov     rcx, rax; cb
0x180001223  call    cs:__imp_CoTaskMemAlloc
0x18000122a  nop     dword ptr [rax+rax+00h]
0x18000122f  mov     [rsi], rax
0x180001232  test    rax, rax
0x180001235  mov     esi, 8007000Eh
0x18000123a  mov     r10, rax
0x18000123d  cmovnz  esi, ebp
0x180001240  test    esi, esi
0x180001242  js      short loc_18000120A
0x180001244  test    rax, rax
0x180001247  jz      loc_1800012E7
0x18000124d  cmp     r14, 7FFFFFFFh
0x180001254  ja      loc_1800012FA
0x18000125a  cmp     rbx, 7FFFFFFFh
0x180001261  jnb     loc_1800012F1
0x180001267  test    rdi, rdi
0x18000126a  jz      loc_180001302
0x180001270  test    r14, r14
0x180001273  jz      short loc_18000120A
0x180001275  mov     rcx, r14
0x180001278  mov     rdx, r10
0x18000127b  mov     r9, rbp
0x18000127e  xchg    ax, ax
0x180001280  test    rbx, rbx
0x180001283  jz      short loc_1800012B2
0x180001285  movzx   eax, word ptr [rdi]
0x180001288  test    ax, ax
0x18000128b  jz      short loc_1800012AD
0x18000128d  mov     [rdx], ax
0x180001290  add     rdi, 2
0x180001294  add     rdx, 2
0x180001298  dec     rbx
0x18000129b  inc     r9
0x18000129e  sub     rcx, 1
0x1800012a2  jnz     short loc_180001280
0x1800012a4  mov     [rdx-2], bp
0x1800012a8  jmp     loc_18000120A
0x1800012ad  test    rcx, rcx
0x1800012b0  jz      short loc_1800012A4
0x1800012b2  sub     r14, r9
0x1800012b5  mov     [rdx], bp
0x1800012b8  cmp     r14, 1
0x1800012bc  jbe     loc_18000120A
0x1800012c2  lea     r8, [r14+r14]
0x1800012c6  cmp     r8, 2
0x1800012ca  jbe     loc_18000120A
0x1800012d0  inc     r9
0x1800012d3  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x1800012d7  xor     edx, edx; Val
0x1800012d9  lea     rcx, [r10+r9*2]; void *
0x1800012dd  call    memset_0
0x1800012e2  jmp     loc_18000120A
0x1800012e7  test    r14, r14
0x1800012ea  jnz     short loc_1800012FA
0x1800012ec  jmp     loc_18000124D
0x1800012f1  test    r14, r14
0x1800012f4  jz      loc_18000120A
0x1800012fa  mov     [rax], bp
0x1800012fd  jmp     loc_18000120A
0x180001302  lea     rdi, byte_18000DBA8
0x180001309  mov     rbx, rbp
0x18000130c  jmp     loc_180001270
```
