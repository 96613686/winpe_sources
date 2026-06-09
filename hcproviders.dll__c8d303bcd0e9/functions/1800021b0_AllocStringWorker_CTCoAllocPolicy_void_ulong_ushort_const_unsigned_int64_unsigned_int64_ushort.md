# _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)

- ea: `0x1800021b0`
- end: `0x1800022f3`
- name: `??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180001490`

## callees

- `0x1800021b0`
- `0x180009e16`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002206`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002206`

## pseudocode

```c
__int64 __fastcall _AllocStringWorker<CTCoAllocPolicy>(
        __int64 a1,
        __int64 a2,
        char *a3,
        unsigned __int64 a4,
        int a5,
        _QWORD *a6)
{
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rbx
  unsigned int v9; // esi
  _WORD *v11; // rax
  unsigned __int64 v12; // rcx
  _WORD *v13; // rdx
  __int64 v14; // r9
  unsigned __int64 v15; // r14

  v6 = a4 + 1;
  v7 = a4;
  *a6 = 0;
  if ( a4 + 1 < a4 || !is_mul_ok(v6, 2u) )
    return (unsigned int)-2147024362;
  v11 = CoTaskMemAlloc(2 * v6);
  *a6 = v11;
  v9 = -2147024882;
  if ( v11 )
    v9 = 0;
  if ( (v9 & 0x80000000) == 0 )
  {
    if ( (v11 || !v6) && v6 <= 0x7FFFFFFF )
    {
      if ( v7 < 0x7FFFFFFF )
      {
        if ( !a3 )
        {
          a3 = byte_18000DBA8;
          v7 = 0;
        }
        if ( v6 )
        {
          v12 = v6;
          v13 = v11;
          v14 = 0;
          while ( v7 && *(_WORD *)a3 )
          {
            *v13 = *(_WORD *)a3;
            a3 += 2;
            ++v13;
            --v7;
            ++v14;
            if ( !--v12 )
            {
              *(v13 - 1) = 0;
              return v9;
            }
          }
          v15 = v6 - v14;
          *v13 = 0;
          if ( v15 > 1 && 2 * v15 > 2 )
            memset_0(&v11[v14 + 1], 0, 2 * v15 - 2);
        }
        return v9;
      }
      if ( !v6 )
        return v9;
    }
    *v11 = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x1800021b0  mov     [rsp+arg_8], rbx
0x1800021b5  mov     [rsp+arg_10], rbp
0x1800021ba  push    rsi
0x1800021bb  push    rdi
0x1800021bc  push    r14
0x1800021be  sub     rsp, 20h
0x1800021c2  mov     rsi, [rsp+38h+arg_28]
0x1800021c7  lea     r14, [r9+1]
0x1800021cb  xor     ebp, ebp
0x1800021cd  mov     rbx, r9
0x1800021d0  mov     rdi, r8
0x1800021d3  mov     [rsi], rbp
0x1800021d6  cmp     r14, r9
0x1800021d9  jb      short loc_1800021E8
0x1800021db  mov     eax, 2
0x1800021e0  mul     r14
0x1800021e3  test    rdx, rdx
0x1800021e6  jz      short loc_180002203
0x1800021e8  mov     esi, 80070216h
0x1800021ed  mov     rbx, [rsp+38h+arg_8]
0x1800021f2  mov     eax, esi
0x1800021f4  mov     rbp, [rsp+38h+arg_10]
0x1800021f9  add     rsp, 20h
0x1800021fd  pop     r14
0x1800021ff  pop     rdi
0x180002200  pop     rsi
0x180002201  retn
0x180002203  mov     rcx, rax; cb
0x180002206  call    cs:__imp_CoTaskMemAlloc
0x18000220d  nop     dword ptr [rax+rax+00h]
0x180002212  mov     [rsi], rax
0x180002215  test    rax, rax
0x180002218  mov     esi, 8007000Eh
0x18000221d  mov     r10, rax
0x180002220  cmovnz  esi, ebp
0x180002223  test    esi, esi
0x180002225  js      short loc_1800021ED
0x180002227  test    rax, rax
0x18000222a  jz      loc_1800022C9
0x180002230  cmp     r14, 7FFFFFFFh
0x180002237  ja      loc_1800022DC
0x18000223d  cmp     rbx, 7FFFFFFFh
0x180002244  jnb     loc_1800022D3
0x18000224a  test    rdi, rdi
0x18000224d  jz      loc_1800022E4
0x180002253  test    r14, r14
0x180002256  jz      short loc_1800021ED
0x180002258  mov     rcx, r14
0x18000225b  mov     rdx, r10
0x18000225e  mov     r9, rbp
0x180002261  test    rbx, rbx
0x180002264  jz      short loc_180002293
0x180002266  movzx   eax, word ptr [rdi]
0x180002269  test    ax, ax
0x18000226c  jz      short loc_18000228E
0x18000226e  mov     [rdx], ax
0x180002271  add     rdi, 2
0x180002275  add     rdx, 2
0x180002279  dec     rbx
0x18000227c  inc     r9
0x18000227f  sub     rcx, 1
0x180002283  jnz     short loc_180002261
0x180002285  mov     [rdx-2], bp
0x180002289  jmp     loc_1800021ED
0x18000228e  test    rcx, rcx
0x180002291  jz      short loc_180002285
0x180002293  sub     r14, r9
0x180002296  mov     [rdx], bp
0x180002299  cmp     r14, 1
0x18000229d  jbe     loc_1800021ED
0x1800022a3  lea     r8, [r14+r14]
0x1800022a7  cmp     r8, 2
0x1800022ab  jbe     loc_1800021ED
0x1800022b1  add     r10, 2
0x1800022b5  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x1800022b9  xor     edx, edx; Val
0x1800022bb  lea     rcx, [r10+r9*2]; void *
0x1800022bf  call    memset_0
0x1800022c4  jmp     loc_1800021ED
0x1800022c9  test    r14, r14
0x1800022cc  jnz     short loc_1800022DC
0x1800022ce  jmp     loc_180002230
0x1800022d3  test    r14, r14
0x1800022d6  jz      loc_1800021ED
0x1800022dc  mov     [rax], bp
0x1800022df  jmp     loc_1800021ED
0x1800022e4  lea     rdi, byte_18000DBA8
0x1800022eb  mov     rbx, rbp
0x1800022ee  jmp     loc_180002253
```
