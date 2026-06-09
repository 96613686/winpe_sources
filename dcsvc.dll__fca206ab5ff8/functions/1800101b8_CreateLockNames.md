# CreateLockNames

- ea: `0x1800101b8`
- end: `0x1800103fe`
- name: `CreateLockNames`
- size: `582`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010404`
- `0x180010db4`

## callees

- `0x180008fe8`
- `0x1800101b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010226`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001022f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010226`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001022f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010253`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010311`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010253`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010311`

## string_xrefs

- `0x180010342`: `Global\CspReadyEvent`
- `0x18001028d`: `Global\ConfigManagerMutex`

## pseudocode

```c
__int64 __fastcall CreateLockNames(const unsigned __int16 *a1, unsigned __int16 **a2, unsigned __int16 **a3)
{
  unsigned __int16 *v4; // rsi
  unsigned __int16 *v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rcx
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rcx
  unsigned int v10; // r15d
  unsigned __int64 v11; // rbp
  signed int v12; // ebx
  unsigned __int16 *v14; // rax
  __int64 v15; // r13
  const wchar_t *v16; // rcx
  __int64 v17; // rax
  unsigned __int64 v18; // rdx
  unsigned __int16 *v19; // r8
  unsigned __int16 *v20; // rcx
  unsigned __int16 *v21; // rax
  const wchar_t *v22; // rax
  __int64 v23; // r8
  unsigned __int16 *v24; // r9
  unsigned __int16 *v25; // rcx

  v4 = 0;
  v5 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a1[v6] );
  v7 = (unsigned int)(v6 + 26);
  if ( (unsigned int)v6 >= 0xFFFFFFE6 )
    goto LABEL_8;
  v8 = (unsigned int)v7;
  v9 = 2 * v7;
  if ( v9 > 0xFFFFFFFF )
    goto LABEL_8;
  if ( a3 )
  {
    v10 = v6 + 21;
    v11 = 2LL * v10;
    if ( v11 > 0xFFFFFFFF )
    {
LABEL_8:
      v12 = -2147024362;
      goto LABEL_9;
    }
  }
  else
  {
    v10 = 0;
    LODWORD(v11) = 0;
  }
  v14 = (unsigned __int16 *)malloc((unsigned int)v9);
  v4 = v14;
  if ( !v14 )
  {
LABEL_12:
    v12 = -2147024882;
    goto LABEL_9;
  }
  if ( !v8 )
  {
    v12 = -2147024809;
    goto LABEL_9;
  }
  if ( v8 > 0x7FFFFFFF )
  {
    v12 = -2147024809;
    *v14 = 0;
    goto LABEL_9;
  }
  v15 = 2147483646;
  v16 = L"Global\\ConfigManagerMutex";
  v17 = 2147483646;
  v18 = v8;
  v19 = v4;
  do
  {
    if ( !v17 )
      break;
    if ( !*v16 )
      break;
    *v19++ = *v16++;
    --v17;
    --v18;
  }
  while ( v18 );
  v20 = v19 - 1;
  v12 = v18 == 0 ? 0x8007007A : 0;
  if ( v18 )
    v20 = v19;
  *v20 = 0;
  if ( v18 )
  {
    v12 = StringCchCatW(v4, v8, a1);
    if ( v12 >= 0 )
    {
      if ( !a3 )
        goto LABEL_37;
      v21 = (unsigned __int16 *)malloc((unsigned int)v11);
      v5 = v21;
      if ( !v21 )
        goto LABEL_12;
      if ( !v10 )
      {
        v12 = -2147024809;
        goto LABEL_9;
      }
      if ( v10 > 0x7FFFFFFFuLL )
      {
        v12 = -2147024809;
        *v21 = 0;
        goto LABEL_9;
      }
      v22 = L"Global\\CspReadyEvent";
      v23 = v10;
      v24 = v5;
      do
      {
        if ( !v15 )
          break;
        if ( !*v22 )
          break;
        *v24++ = *v22++;
        --v15;
        --v23;
      }
      while ( v23 );
      v25 = v24 - 1;
      v12 = v23 == 0 ? 0x8007007A : 0;
      if ( v23 )
        v25 = v24;
      *v25 = 0;
      if ( v23 )
      {
        v12 = StringCchCatW(v5, v10, a1);
        if ( v12 >= 0 )
        {
LABEL_37:
          *a2 = v4;
          v4 = 0;
          if ( a3 )
          {
            *a3 = v5;
            v5 = 0;
          }
        }
      }
    }
  }
LABEL_9:
  free(v5);
  free(v4);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800101b8  mov     [rsp+arg_10], rbx
0x1800101bd  mov     [rsp+arg_8], rdx
0x1800101c2  mov     [rsp+arg_0], rcx
0x1800101c7  push    rbp
0x1800101c8  push    rsi
0x1800101c9  push    rdi
0x1800101ca  push    r12
0x1800101cc  push    r13
0x1800101ce  push    r14
0x1800101d0  push    r15
0x1800101d2  sub     rsp, 20h
0x1800101d6  xor     ebx, ebx
0x1800101d8  mov     r12, r8
0x1800101db  mov     esi, ebx
0x1800101dd  mov     edi, ebx
0x1800101df  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800101e3  inc     rax
0x1800101e6  cmp     [rcx+rax*2], bx
0x1800101ea  jnz     short loc_1800101E3
0x1800101ec  lea     ecx, [rax+1Ah]
0x1800101ef  cmp     ecx, 1Ah
0x1800101f2  jb      short loc_18001021E
0x1800101f4  mov     r14d, ecx
0x1800101f7  mov     edx, 0FFFFFFFFh
0x1800101fc  add     rcx, rcx
0x1800101ff  cmp     rcx, rdx
0x180010202  ja      short loc_18001021E
0x180010204  test    r12, r12
0x180010207  jz      short loc_18001024C
0x180010209  lea     r15d, [rax+15h]
0x18001020d  cmp     r15d, 15h
0x180010211  jb      short loc_18001021E
0x180010213  mov     ebp, r15d
0x180010216  add     rbp, rbp
0x180010219  cmp     rbp, rdx
0x18001021c  jbe     short loc_180010251
0x18001021e  mov     ebx, 80070216h
0x180010223  mov     rcx, rdi; Block
0x180010226  call    cs:__imp_free
0x18001022c  mov     rcx, rsi; Block
0x18001022f  call    cs:__imp_free
0x180010235  mov     eax, ebx
0x180010237  mov     rbx, [rsp+58h+arg_10]
0x18001023c  add     rsp, 20h
0x180010240  pop     r15
0x180010242  pop     r14
0x180010244  pop     r13
0x180010246  pop     r12
0x180010248  pop     rdi
0x180010249  pop     rsi
0x18001024a  pop     rbp
0x18001024b  retn
0x18001024c  mov     r15d, ebx
0x18001024f  mov     ebp, ebx
0x180010251  mov     ecx, ecx; Size
0x180010253  call    cs:__imp_malloc
0x180010259  mov     rsi, rax
0x18001025c  test    rax, rax
0x18001025f  jnz     short loc_180010268
0x180010261  mov     ebx, 8007000Eh
0x180010266  jmp     short loc_180010223
0x180010268  test    r14, r14
0x18001026b  jz      loc_1800103E4
0x180010271  cmp     r14, 7FFFFFFFh
0x180010278  jbe     short loc_180010287
0x18001027a  mov     ebx, 80070057h
0x18001027f  xor     r9d, r9d
0x180010282  jmp     loc_1800103F5
0x180010287  mov     r13d, 7FFFFFFEh
0x18001028d  lea     rcx, aGlobalConfigma_0; "Global\\ConfigManagerMutex"
0x180010294  mov     eax, r13d
0x180010297  mov     rdx, r14
0x18001029a  mov     r8, rsi
0x18001029d  test    rax, rax
0x1800102a0  jz      short loc_1800102C1
0x1800102a2  movzx   r9d, word ptr [rcx]
0x1800102a6  test    r9w, r9w
0x1800102aa  jz      short loc_1800102C1
0x1800102ac  mov     [r8], r9w
0x1800102b0  add     rcx, 2
0x1800102b4  add     r8, 2
0x1800102b8  dec     rax
0x1800102bb  sub     rdx, 1
0x1800102bf  jnz     short loc_18001029D
0x1800102c1  mov     rax, rdx
0x1800102c4  lea     rcx, [r8-2]
0x1800102c8  neg     rax
0x1800102cb  sbb     ebx, ebx
0x1800102cd  xor     r9d, r9d
0x1800102d0  not     ebx
0x1800102d2  and     ebx, 8007007Ah
0x1800102d8  test    rdx, rdx
0x1800102db  cmovnz  rcx, r8
0x1800102df  mov     [rcx], r9w
0x1800102e3  jz      loc_180010223
0x1800102e9  mov     r8, [rsp+58h+arg_0]; unsigned __int16 *
0x1800102ee  mov     rdx, r14; unsigned __int64
0x1800102f1  mov     rcx, rsi; unsigned __int16 *
0x1800102f4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800102f9  xor     r14d, r14d
0x1800102fc  mov     ebx, eax
0x1800102fe  test    eax, eax
0x180010300  js      loc_180010223
0x180010306  test    r12, r12
0x180010309  jz      loc_1800103AD
0x18001030f  mov     ecx, ebp; Size
0x180010311  call    cs:__imp_malloc
0x180010317  mov     rdi, rax
0x18001031a  test    rax, rax
0x18001031d  jz      loc_180010261
0x180010323  mov     edx, r15d; unsigned __int64
0x180010326  test    r15d, r15d
0x180010329  jz      loc_1800103CD
0x18001032f  cmp     rdx, 7FFFFFFFh
0x180010336  jbe     short loc_180010342
0x180010338  mov     ebx, 80070057h
0x18001033d  jmp     loc_1800103DB
0x180010342  lea     rax, aGlobalCspready; "Global\\CspReadyEvent"
0x180010349  mov     r8, rdx
0x18001034c  mov     r9, rdi
0x18001034f  test    r13, r13
0x180010352  jz      short loc_180010371
0x180010354  movzx   ecx, word ptr [rax]
0x180010357  test    cx, cx
0x18001035a  jz      short loc_180010371
0x18001035c  mov     [r9], cx
0x180010360  add     rax, 2
0x180010364  add     r9, 2
0x180010368  dec     r13
0x18001036b  sub     r8, 1
0x18001036f  jnz     short loc_18001034F
0x180010371  mov     rax, r8
0x180010374  lea     rcx, [r9-2]
0x180010378  neg     rax
0x18001037b  sbb     ebx, ebx
0x18001037d  not     ebx
0x18001037f  and     ebx, 8007007Ah
0x180010385  test    r8, r8
0x180010388  cmovnz  rcx, r9
0x18001038c  mov     [rcx], r14w
0x180010390  jz      loc_180010223
0x180010396  mov     r8, [rsp+58h+arg_0]; unsigned __int16 *
0x18001039b  mov     rcx, rdi; unsigned __int16 *
0x18001039e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800103a3  mov     ebx, eax
0x1800103a5  test    eax, eax
0x1800103a7  js      loc_180010223
0x1800103ad  mov     rax, [rsp+58h+arg_8]
0x1800103b2  mov     [rax], rsi
0x1800103b5  mov     rsi, r14
0x1800103b8  test    r12, r12
0x1800103bb  jz      loc_180010223
0x1800103c1  mov     [r12], rdi
0x1800103c5  mov     rdi, r14
0x1800103c8  jmp     loc_180010223
0x1800103cd  mov     ebx, 80070057h
0x1800103d2  test    r15d, r15d
0x1800103d5  jz      loc_180010223
0x1800103db  mov     [rax], r14w
0x1800103df  jmp     loc_180010223
0x1800103e4  xor     r9d, r9d
0x1800103e7  mov     ebx, 80070057h
0x1800103ec  test    r14, r14
0x1800103ef  jz      loc_180010223
0x1800103f5  mov     [rax], r9w
0x1800103f9  jmp     loc_180010223
```
