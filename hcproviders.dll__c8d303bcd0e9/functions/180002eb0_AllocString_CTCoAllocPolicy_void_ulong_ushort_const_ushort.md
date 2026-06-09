# _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)

- ea: `0x180002eb0`
- end: `0x180003001`
- name: `??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z`
- size: `337`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180001490`
- `0x180001ea0`
- `0x180002300`
- `0x180002770`
- `0x180009150`
- `0x180009180`
- `0x180009330`
- `0x180009520`
- `0x1800095d0`
- `0x180009670`
- `0x180009840`
- `0x180009870`
- `0x1800098a0`
- `0x180009990`

## callees

- `0x180002eb0`
- `0x180009e16`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002f14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002f14`

## pseudocode

```c
__int64 __fastcall _AllocString<CTCoAllocPolicy>(__int64 a1, __int64 a2, char *a3, _QWORD *a4)
{
  char *v5; // rdi
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // r14
  unsigned int v8; // esi
  _WORD *v10; // rax
  unsigned __int64 v11; // rcx
  _WORD *v12; // rdx
  __int64 v13; // r9
  unsigned __int64 v14; // r14

  v5 = a3;
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)&a3[2 * v6] );
  v7 = v6 + 1;
  *a4 = 0;
  if ( v6 + 1 < v6 || !is_mul_ok(v7, 2u) )
    return (unsigned int)-2147024362;
  v10 = CoTaskMemAlloc(2 * v7);
  *a4 = v10;
  v8 = -2147024882;
  if ( v10 )
    v8 = 0;
  if ( (v8 & 0x80000000) == 0 )
  {
    if ( (v10 || v6 == -1) && v7 <= 0x7FFFFFFF )
    {
      if ( v6 < 0x7FFFFFFF )
      {
        if ( !v5 )
        {
          v5 = byte_18000DBA8;
          v6 = 0;
        }
        if ( v7 )
        {
          v11 = v7;
          v12 = v10;
          v13 = 0;
          while ( v6 && *(_WORD *)v5 )
          {
            *v12 = *(_WORD *)v5;
            v5 += 2;
            ++v12;
            --v6;
            ++v13;
            if ( !--v11 )
            {
              *(v12 - 1) = 0;
              return v8;
            }
          }
          v14 = v7 - v13;
          *v12 = 0;
          if ( v14 > 1 && 2 * v14 > 2 )
            memset_0(&v10[v13 + 1], 0, 2 * v14 - 2);
        }
        return v8;
      }
      if ( v6 == -1 )
        return v8;
    }
    *v10 = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x180002eb0  mov     [rsp+arg_8], rbx
0x180002eb5  mov     [rsp+arg_10], rbp
0x180002eba  push    rsi
0x180002ebb  push    rdi
0x180002ebc  push    r14
0x180002ebe  sub     rsp, 20h
0x180002ec2  mov     rsi, r9
0x180002ec5  mov     rdi, r8
0x180002ec8  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180002ecf  nop
0x180002ed0  inc     rbx
0x180002ed3  cmp     word ptr [r8+rbx*2], 0
0x180002ed9  jnz     short loc_180002ED0
0x180002edb  xor     ebp, ebp
0x180002edd  lea     r14, [rbx+1]
0x180002ee1  mov     [r9], rbp
0x180002ee4  cmp     r14, rbx
0x180002ee7  jb      short loc_180002EF6
0x180002ee9  mov     eax, 2
0x180002eee  mul     r14
0x180002ef1  test    rdx, rdx
0x180002ef4  jz      short loc_180002F11
0x180002ef6  mov     esi, 80070216h
0x180002efb  mov     rbx, [rsp+38h+arg_8]
0x180002f00  mov     eax, esi
0x180002f02  mov     rbp, [rsp+38h+arg_10]
0x180002f07  add     rsp, 20h
0x180002f0b  pop     r14
0x180002f0d  pop     rdi
0x180002f0e  pop     rsi
0x180002f0f  retn
0x180002f11  mov     rcx, rax; cb
0x180002f14  call    cs:__imp_CoTaskMemAlloc
0x180002f1b  nop     dword ptr [rax+rax+00h]
0x180002f20  mov     [rsi], rax
0x180002f23  test    rax, rax
0x180002f26  mov     esi, 8007000Eh
0x180002f2b  mov     r10, rax
0x180002f2e  cmovnz  esi, ebp
0x180002f31  test    esi, esi
0x180002f33  js      short loc_180002EFB
0x180002f35  test    rax, rax
0x180002f38  jz      loc_180002FD7
0x180002f3e  cmp     r14, 7FFFFFFFh
0x180002f45  ja      loc_180002FEA
0x180002f4b  cmp     rbx, 7FFFFFFFh
0x180002f52  jnb     loc_180002FE1
0x180002f58  test    rdi, rdi
0x180002f5b  jz      loc_180002FF2
0x180002f61  test    r14, r14
0x180002f64  jz      short loc_180002EFB
0x180002f66  mov     rcx, r14
0x180002f69  mov     rdx, r10
0x180002f6c  mov     r9, rbp
0x180002f6f  nop
0x180002f70  test    rbx, rbx
0x180002f73  jz      short loc_180002FA2
0x180002f75  movzx   eax, word ptr [rdi]
0x180002f78  test    ax, ax
0x180002f7b  jz      short loc_180002F9D
0x180002f7d  mov     [rdx], ax
0x180002f80  add     rdi, 2
0x180002f84  add     rdx, 2
0x180002f88  dec     rbx
0x180002f8b  inc     r9
0x180002f8e  sub     rcx, 1
0x180002f92  jnz     short loc_180002F70
0x180002f94  mov     [rdx-2], bp
0x180002f98  jmp     loc_180002EFB
0x180002f9d  test    rcx, rcx
0x180002fa0  jz      short loc_180002F94
0x180002fa2  sub     r14, r9
0x180002fa5  mov     [rdx], bp
0x180002fa8  cmp     r14, 1
0x180002fac  jbe     loc_180002EFB
0x180002fb2  lea     r8, [r14+r14]
0x180002fb6  cmp     r8, 2
0x180002fba  jbe     loc_180002EFB
0x180002fc0  inc     r9
0x180002fc3  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180002fc7  xor     edx, edx; Val
0x180002fc9  lea     rcx, [r10+r9*2]; void *
0x180002fcd  call    memset_0
0x180002fd2  jmp     loc_180002EFB
0x180002fd7  test    r14, r14
0x180002fda  jnz     short loc_180002FEA
0x180002fdc  jmp     loc_180002F3E
0x180002fe1  test    r14, r14
0x180002fe4  jz      loc_180002EFB
0x180002fea  mov     [rax], bp
0x180002fed  jmp     loc_180002EFB
0x180002ff2  lea     rdi, byte_18000DBA8
0x180002ff9  mov     rbx, rbp
0x180002ffc  jmp     loc_180002F61
```
