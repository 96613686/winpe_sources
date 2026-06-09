# CDiffCrcInitializer::Initialize(void)

- ea: `0x18002040c`
- end: `0x18002056e`
- name: `?Initialize@CDiffCrcInitializer@@QEAAXXZ`
- size: `354`
- prototype: `void(CDiffCrcInitializer *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800201c4`
- `0x1800202bc`

## callees

- `0x18000e0b0`
- `0x18000e7fc`
- `0x18002037c`
- `0x18002040c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002042e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180020442`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180020451`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180020460`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002046f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002042e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180020442`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180020451`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180020460`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002046f`

## string_xrefs

- `0x180020556`: `onecoreuap\base\appmodel\search\common\utils\crchash.cxx`

## pseudocode

```c
void __fastcall CDiffCrcInitializer::Initialize(CDiffCrcInitializer *this)
{
  unsigned int *v1; // rax
  CDiffCrcInitializer *v2; // rcx
  _DWORD *v3; // r14
  unsigned int *v4; // rdi
  unsigned int *v5; // r10
  __int64 v6; // r9
  int v7; // edx
  int v8; // r11d
  int v9; // eax
  CDiffCrcInitializer *v10; // rcx
  CDiffCrcInitializer *v11; // rcx
  unsigned int v12; // r9d
  CDiffCrcInitializer *v13; // rcx
  unsigned int v14; // r9d
  CDiffCrcInitializer *v15; // rcx
  unsigned int v16; // r9d
  int v17; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !byte_180036488 )
  {
    g_rgdwPower = malloc(0x1000u);
    g_rgdwRes32 = (unsigned int *)malloc(0x400u);
    g_rgdwRes40 = (unsigned int *)malloc(0x400u);
    g_rgdwRes48 = (unsigned int *)malloc(0x400u);
    v1 = (unsigned int *)malloc(0x400u);
    v3 = g_rgdwPower;
    v4 = v1;
    g_rgdwRes56 = v1;
    if ( !g_rgdwPower || (v5 = g_rgdwRes32) == 0 || !g_rgdwRes40 || !g_rgdwRes48 || !v1 )
    {
      CDiffCrcInitializer::_Free(v2);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\utils\\crchash.cxx",
        (const char *)0x8007000ELL,
        v17);
    }
    v6 = 1;
    v7 = 79764919;
    do
    {
      v3[v6] = v7;
      v8 = 32;
      do
      {
        v9 = v7;
        v10 = (CDiffCrcInitializer *)(unsigned int)(2 * v7);
        v7 = (2 * v7) ^ 0x4C11DB7;
        if ( v9 >= 0 )
          v7 = (int)v10;
        --v8;
      }
      while ( v8 );
      ++v6;
    }
    while ( v6 != 1024 );
    CDiffCrcInitializer::InitResTable(v10, v5, 0x20u, 0x400u);
    CDiffCrcInitializer::InitResTable(v11, g_rgdwRes40, 0x28u, v12);
    CDiffCrcInitializer::InitResTable(v13, g_rgdwRes48, 0x30u, v14);
    CDiffCrcInitializer::InitResTable(v15, v4, 0x38u, v16);
    byte_180036488 = 1;
  }
}

```

## disassembly

```asm
0x18002040c  mov     [rsp+arg_0], rbp
0x180020411  mov     [rsp+arg_8], rdi
0x180020416  push    r14; int
0x180020418  sub     rsp, 20h
0x18002041c  cmp     cs:byte_180036488, 0
0x180020423  jnz     loc_18002053B
0x180020429  mov     ecx, 1000h; Size
0x18002042e  call    cs:__imp_malloc
0x180020434  mov     ebp, 400h
0x180020439  mov     cs:?g_rgdwPower@@3PEAKEA, rax; ulong * g_rgdwPower
0x180020440  mov     ecx, ebp; Size
0x180020442  call    cs:__imp_malloc
0x180020448  mov     ecx, ebp; Size
0x18002044a  mov     cs:?g_rgdwRes32@@3PEAKEA, rax; ulong * g_rgdwRes32
0x180020451  call    cs:__imp_malloc
0x180020457  mov     ecx, ebp; Size
0x180020459  mov     cs:?g_rgdwRes40@@3PEAKEA, rax; ulong * g_rgdwRes40
0x180020460  call    cs:__imp_malloc
0x180020466  mov     ecx, ebp; Size
0x180020468  mov     cs:?g_rgdwRes48@@3PEAKEA, rax; ulong * g_rgdwRes48
0x18002046f  call    cs:__imp_malloc
0x180020475  mov     r14, cs:?g_rgdwPower@@3PEAKEA; ulong * g_rgdwPower
0x18002047c  mov     rdi, rax
0x18002047f  mov     cs:?g_rgdwRes56@@3PEAKEA, rax; ulong * g_rgdwRes56
0x180020486  test    r14, r14
0x180020489  jz      loc_18002054C
0x18002048f  mov     r10, cs:?g_rgdwRes32@@3PEAKEA; ulong * g_rgdwRes32
0x180020496  test    r10, r10
0x180020499  jz      loc_18002054C
0x18002049f  cmp     cs:?g_rgdwRes40@@3PEAKEA, 0; ulong * g_rgdwRes40
0x1800204a7  jz      loc_18002054C
0x1800204ad  cmp     cs:?g_rgdwRes48@@3PEAKEA, 0; ulong * g_rgdwRes48
0x1800204b5  jz      loc_18002054C
0x1800204bb  test    rax, rax
0x1800204be  jz      loc_18002054C
0x1800204c4  mov     r9d, 1
0x1800204ca  mov     edx, 4C11DB7h
0x1800204cf  lea     r8d, [r9+1Fh]; unsigned int
0x1800204d3  mov     [r14+r9*4], edx
0x1800204d7  mov     r11d, r8d
0x1800204da  mov     eax, edx
0x1800204dc  lea     ecx, [rdx+rdx]; this
0x1800204df  mov     edx, ecx
0x1800204e1  xor     edx, 4C11DB7h
0x1800204e7  test    eax, eax
0x1800204e9  cmovns  edx, ecx
0x1800204ec  add     r11d, 0FFFFFFFFh
0x1800204f0  jnz     short loc_1800204DA
0x1800204f2  inc     r9; unsigned int
0x1800204f5  cmp     r9, rbp
0x1800204f8  jnz     short loc_1800204D3
0x1800204fa  mov     rdx, r10; unsigned int *
0x1800204fd  call    ?InitResTable@CDiffCrcInitializer@@AEAAXPEAKKK@Z; CDiffCrcInitializer::InitResTable(ulong *,ulong,ulong)
0x180020502  mov     rdx, cs:?g_rgdwRes40@@3PEAKEA; unsigned int *
0x180020509  mov     r8d, 28h ; '('; unsigned int
0x18002050f  call    ?InitResTable@CDiffCrcInitializer@@AEAAXPEAKKK@Z; CDiffCrcInitializer::InitResTable(ulong *,ulong,ulong)
0x180020514  mov     rdx, cs:?g_rgdwRes48@@3PEAKEA; unsigned int *
0x18002051b  mov     r8d, 30h ; '0'; unsigned int
0x180020521  call    ?InitResTable@CDiffCrcInitializer@@AEAAXPEAKKK@Z; CDiffCrcInitializer::InitResTable(ulong *,ulong,ulong)
0x180020526  mov     r8d, 38h ; '8'; unsigned int
0x18002052c  mov     rdx, rdi; unsigned int *
0x18002052f  call    ?InitResTable@CDiffCrcInitializer@@AEAAXPEAKKK@Z; CDiffCrcInitializer::InitResTable(ulong *,ulong,ulong)
0x180020534  mov     cs:byte_180036488, 1
0x18002053b  mov     rbp, [rsp+28h+arg_0]
0x180020540  mov     rdi, [rsp+28h+arg_8]
0x180020545  add     rsp, 20h
0x180020549  pop     r14
0x18002054b  retn
0x18002054c  call    ?_Free@CDiffCrcInitializer@@AEAAXXZ; CDiffCrcInitializer::_Free(void)
0x180020551  mov     rcx, [rsp+28h]; this
0x180020556  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\com"...
0x18002055d  mov     r9d, 8007000Eh; char *
0x180020563  mov     edx, 49h ; 'I'; void *
0x180020568  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
