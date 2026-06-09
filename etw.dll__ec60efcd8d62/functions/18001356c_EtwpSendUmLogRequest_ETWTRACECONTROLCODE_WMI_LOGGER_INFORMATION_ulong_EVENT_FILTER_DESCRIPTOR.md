# EtwpSendUmLogRequest(ETWTRACECONTROLCODE,_WMI_LOGGER_INFORMATION *,ulong,_EVENT_FILTER_DESCRIPTOR *)

- ea: `0x18001356c`
- end: `0x1800137db`
- name: `?EtwpSendUmLogRequest@@YAKW4ETWTRACECONTROLCODE@@PEAU_WMI_LOGGER_INFORMATION@@KPEAU_EVENT_FILTER_DESCRIPTOR@@@Z`
- size: `623`
- prototype: `unsigned int __high(enum ETWTRACECONTROLCODE, struct _WMI_LOGGER_INFORMATION *, unsigned int, struct _EVENT_FILTER_DESCRIPTOR *)`
- caller_count: `6`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180013284`
- `0x18001349c`
- `0x180013504`
- `0x1800137e4`
- `0x1800138d0`
- `0x180013bc8`

## callees

- `0x180001eb2`
- `0x180001ff0`
- `0x180002014`
- `0x18001356c`
- `0x180015834`

## import_xrefs

- `ntdll!EtwSendNotification` at `0x180013756`
- `ntdll!EtwSendNotification` at `0x180013756`
- `ntdll!EtwProcessPrivateLoggerRequest` at `0x180013734`
- `ntdll!EtwProcessPrivateLoggerRequest` at `0x180013734`

## pseudocode

```c
__int64 __fastcall EtwpSendUmLogRequest(int a1, __int64 a2, unsigned int a3, __int64 a4)
{
  unsigned int v4; // ebx
  __int64 v5; // rbp
  int v6; // r14d
  _DWORD *v7; // rdi
  int v9; // ecx
  unsigned int i; // edx
  __int64 v11; // rax
  char *v12; // rax
  char *v13; // rsi
  unsigned int v14; // eax
  _DWORD *v15; // r14
  __int128 v16; // xmm0
  int v17; // eax
  __int64 v18; // rax
  char *v19; // r12
  char *v20; // r15
  __int64 v21; // r14
  __int64 v22; // r13
  unsigned int v23; // edi
  __int64 v24; // rbx
  unsigned int v25; // eax
  unsigned int v26; // ebx
  int v28[17]; // [rsp+34h] [rbp-44h] BYREF
  int v30; // [rsp+90h] [rbp+18h] BYREF
  __int64 v31; // [rsp+98h] [rbp+20h]

  v31 = a4;
  v4 = 0;
  v5 = a3;
  v6 = *(_DWORD *)a2 + 72;
  v30 = 0;
  v7 = (_DWORD *)a2;
  v28[0] = 0;
  if ( a3
    && ((*(_BYTE *)(a2 + 11) & 1) == 0
     || (unsigned __int16)(*(_WORD *)(a2 + 8) - 8) > 0x37u
     || (*(_DWORD *)(a2 + 64) & 0x20000) == 0) )
  {
    v9 = 16 * a3 + 4;
    for ( i = 0; i < a3; ++i )
    {
      v11 = i;
      v9 += *(_DWORD *)(16 * v11 + a4 + 8);
    }
    v4 = (v9 + 7) & 0xFFFFFFF8;
    v6 += v4;
  }
  v12 = (char *)operator new(0x10000u, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v12;
  if ( !v12 )
    return 8;
  memset_0(v12, 0, 0x10000u);
  v14 = (v6 + 7) & 0xFFFFFFF8;
  v15 = v13 + 72;
  *((_DWORD *)v13 + 1) = v14;
  v16 = *(_OWORD *)(v7 + 6);
  v13[12] = 1;
  v17 = 11;
  *(_OWORD *)(v13 + 40) = v16;
  if ( !v4 )
    v17 = 4;
  *(_OWORD *)(v13 + 56) = *(_OWORD *)(v7 + 6);
  *(_DWORD *)v13 = v17;
  memcpy_0(v13 + 72, v7, (unsigned int)*v7);
  *((_DWORD *)v13 + 19) = a1;
  if ( v4 )
  {
    v18 = (*v7 + 7) & 0xFFFFFFF8;
    *(_DWORD *)&v13[v18 + 72] = v5;
    v19 = &v13[v18 + 76];
    v20 = &v19[16 * v5];
    if ( (_DWORD)v5 )
    {
      v21 = v31;
      v22 = 0;
      v23 = 0;
      do
      {
        v24 = 2 * v22;
        *(_DWORD *)&v19[8 * v24 + 12] = *(_DWORD *)(v21 + 16 * v22 + 12);
        *(_DWORD *)&v19[8 * v24 + 8] = *(_DWORD *)(v21 + 16 * v22 + 8);
        *(_QWORD *)&v19[8 * v24] = v20 - v19;
        memcpy_0(v20, *(const void **)(v21 + 16 * v22), *(unsigned int *)(v21 + 16 * v22 + 8));
        ++v23;
        v20 += *(unsigned int *)&v19[16 * v22++ + 8];
      }
      while ( v23 < (unsigned int)v5 );
      v7 = (_DWORD *)a2;
      v15 = v13 + 72;
    }
  }
  if ( (*((_BYTE *)v7 + 11) & 1) != 0 && (unsigned __int16)(*((_WORD *)v7 + 4) - 8) <= 0x37u )
    v7[16] |= 0x20000u;
  if ( (v7[16] & 0x20000) != 0 )
  {
    *((_DWORD *)v13 + 5) = 1;
    v25 = EtwProcessPrivateLoggerRequest(v13);
  }
  else
  {
    v25 = EtwSendNotification(v13, 0x10000, v13, &v30, v28);
  }
  v26 = v25;
  if ( !v25 && (v30 || (v7[16] & 0x20000) != 0) )
  {
    if ( *((_DWORD *)v13 + 1) >= 0xF8u )
    {
      if ( *(_DWORD *)v13 == 1 )
      {
        v26 = 4209;
      }
      else if ( *v7 < *v15 )
      {
        v26 = 13;
      }
      else
      {
        memcpy_0(v7, v15, (unsigned int)*v15);
      }
    }
    else if ( *((_DWORD *)v13 + 1) == 76 )
    {
      v26 = *v15;
    }
    else
    {
      v26 = 87;
    }
  }
  operator delete(v13);
  return v26;
}

```

## disassembly

```asm
0x18001356c  mov     rax, rsp
0x18001356f  mov     [rax+8], rbx
0x180013573  mov     [rax+20h], r9
0x180013577  mov     [rax+10h], rdx
0x18001357b  push    rbp
0x18001357c  push    rsi
0x18001357d  push    rdi
0x18001357e  push    r12
0x180013580  push    r13
0x180013582  push    r14
0x180013584  push    r15
0x180013586  sub     rsp, 40h
0x18001358a  mov     r14d, [rdx]
0x18001358d  xor     ebx, ebx
0x18001358f  mov     ebp, r8d
0x180013592  add     r14d, 48h ; 'H'
0x180013596  mov     dword ptr [rax+18h], 0
0x18001359d  mov     rdi, rdx
0x1800135a0  mov     dword ptr [rax-44h], 0
0x1800135a7  mov     r15d, ecx
0x1800135aa  lea     r13d, [rbx+8]
0x1800135ae  mov     r12d, 20000h
0x1800135b4  mov     r8d, 0FFFFFFF8h
0x1800135ba  test    ebp, ebp
0x1800135bc  jz      short loc_1800135FC
0x1800135be  test    byte ptr [rdx+0Bh], 1
0x1800135c2  jz      short loc_1800135D8
0x1800135c4  movzx   eax, word ptr [rdx+8]
0x1800135c8  sub     ax, r13w
0x1800135cc  cmp     ax, 37h ; '7'
0x1800135d0  ja      short loc_1800135D8
0x1800135d2  test    [rdx+40h], r12d
0x1800135d6  jnz     short loc_1800135FC
0x1800135d8  mov     ecx, ebp
0x1800135da  shl     ecx, 4
0x1800135dd  add     ecx, 4
0x1800135e0  xor     edx, edx
0x1800135e2  mov     eax, edx
0x1800135e4  inc     edx
0x1800135e6  shl     rax, 4
0x1800135ea  add     ecx, [rax+r9+8]
0x1800135ef  cmp     edx, ebp
0x1800135f1  jb      short loc_1800135E2
0x1800135f3  lea     ebx, [rcx+7]
0x1800135f6  and     ebx, r8d
0x1800135f9  add     r14d, ebx
0x1800135fc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013603  mov     ecx, 10000h; unsigned __int64
0x180013608  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001360d  mov     rsi, rax
0x180013610  test    rax, rax
0x180013613  jz      loc_1800137C0
0x180013619  xor     edx, edx; Val
0x18001361b  mov     r8d, 10000h; Size
0x180013621  mov     rcx, rax; void *
0x180013624  call    memset_0
0x180013629  lea     eax, [r14+7]
0x18001362d  mov     ecx, 0FFFFFFF8h
0x180013632  and     eax, ecx
0x180013634  lea     r14, [rsi+48h]
0x180013638  mov     [rsi+4], eax
0x18001363b  test    ebx, ebx
0x18001363d  movups  xmm0, xmmword ptr [rdi+18h]
0x180013641  mov     byte ptr [rsi+0Ch], 1
0x180013645  mov     eax, 0Bh
0x18001364a  mov     rdx, rdi; Src
0x18001364d  movdqu  xmmword ptr [rsi+28h], xmm0
0x180013652  movups  xmm1, xmmword ptr [rdi+18h]
0x180013656  lea     ecx, [rax-7]
0x180013659  cmovz   eax, ecx
0x18001365c  mov     rcx, r14; void *
0x18001365f  movdqu  xmmword ptr [rsi+38h], xmm1
0x180013664  mov     [rsi], eax
0x180013666  mov     r8d, [rdi]; Size
0x180013669  call    memcpy_0
0x18001366e  mov     [r14+4], r15d
0x180013672  test    ebx, ebx
0x180013674  jz      loc_18001370C
0x18001367a  mov     eax, [rdi]
0x18001367c  mov     ecx, 0FFFFFFF8h
0x180013681  add     eax, 7
0x180013684  mov     r15, rbp
0x180013687  and     rax, rcx
0x18001368a  shl     r15, 4
0x18001368e  lea     r12, [rax+4Ch]
0x180013692  mov     [rax+rsi+48h], ebp
0x180013696  add     r12, rsi
0x180013699  add     r15, r12
0x18001369c  test    ebp, ebp
0x18001369e  jz      short loc_180013706
0x1800136a0  mov     r14, [rsp+78h+arg_18]
0x1800136a8  xor     r13d, r13d
0x1800136ab  mov     edi, r13d
0x1800136ae  mov     rbx, r13
0x1800136b1  mov     rcx, r15; void *
0x1800136b4  add     rbx, rbx
0x1800136b7  mov     eax, [r14+rbx*8+0Ch]
0x1800136bc  mov     [r12+rbx*8+0Ch], eax
0x1800136c1  mov     eax, [r14+rbx*8+8]
0x1800136c6  mov     [r12+rbx*8+8], eax
0x1800136cb  mov     rax, r15
0x1800136ce  sub     rax, r12
0x1800136d1  mov     [r12+rbx*8], rax
0x1800136d5  mov     r8d, [r14+rbx*8+8]; Size
0x1800136da  mov     rdx, [r14+rbx*8]; Src
0x1800136de  call    memcpy_0
0x1800136e3  mov     eax, [r12+rbx*8+8]
0x1800136e8  inc     edi
0x1800136ea  add     r15, rax
0x1800136ed  inc     r13
0x1800136f0  cmp     edi, ebp
0x1800136f2  jb      short loc_1800136AE
0x1800136f4  mov     rdi, [rsp+78h+arg_8]
0x1800136fc  lea     r14, [rsi+48h]
0x180013700  mov     r13d, 8
0x180013706  mov     r12d, 20000h
0x18001370c  test    byte ptr [rdi+0Bh], 1
0x180013710  jz      short loc_180013724
0x180013712  movzx   eax, word ptr [rdi+8]
0x180013716  sub     ax, r13w
0x18001371a  cmp     ax, 37h ; '7'
0x18001371e  ja      short loc_180013724
0x180013720  or      [rdi+40h], r12d
0x180013724  mov     rcx, rsi
0x180013727  test    [rdi+40h], r12d
0x18001372b  jz      short loc_18001373C
0x18001372d  mov     dword ptr [rsi+14h], 1
0x180013734  call    cs:__imp_EtwProcessPrivateLoggerRequest
0x18001373a  jmp     short loc_18001375C
0x18001373c  lea     rax, [rsp+78h+var_44]
0x180013741  mov     r8, rsi
0x180013744  lea     r9, [rsp+78h+arg_10]
0x18001374c  mov     [rsp+78h+var_58], rax
0x180013751  mov     edx, 10000h
0x180013756  call    cs:__imp_EtwSendNotification
0x18001375c  mov     ebx, eax
0x18001375e  test    eax, eax
0x180013760  jnz     short loc_1800137B4
0x180013762  cmp     [rsp+78h+arg_10], eax
0x180013769  ja      short loc_180013771
0x18001376b  test    [rdi+40h], r12d
0x18001376f  jz      short loc_1800137B4
0x180013771  cmp     dword ptr [rsi+4], 0F8h
0x180013778  jnb     short loc_18001378C
0x18001377a  cmp     dword ptr [rsi+4], 4Ch ; 'L'
0x18001377e  jnz     short loc_180013785
0x180013780  mov     ebx, [r14]
0x180013783  jmp     short loc_1800137B4
0x180013785  mov     ebx, 57h ; 'W'
0x18001378a  jmp     short loc_1800137B4
0x18001378c  cmp     dword ptr [rsi], 1
0x18001378f  jnz     short loc_180013798
0x180013791  mov     ebx, 1071h
0x180013796  jmp     short loc_1800137B4
0x180013798  mov     eax, [r14]
0x18001379b  cmp     [rdi], eax
0x18001379d  jb      short loc_1800137AF
0x18001379f  mov     r8d, eax; Size
0x1800137a2  mov     rdx, r14; Src
0x1800137a5  mov     rcx, rdi; void *
0x1800137a8  call    memcpy_0
0x1800137ad  jmp     short loc_1800137B4
0x1800137af  mov     ebx, 0Dh
0x1800137b4  mov     rcx, rsi; Block
0x1800137b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800137bc  mov     eax, ebx
0x1800137be  jmp     short loc_1800137C3
0x1800137c0  mov     eax, r13d
0x1800137c3  mov     rbx, [rsp+78h+arg_0]
0x1800137cb  add     rsp, 40h
0x1800137cf  pop     r15
0x1800137d1  pop     r14
0x1800137d3  pop     r13
0x1800137d5  pop     r12
0x1800137d7  pop     rdi
0x1800137d8  pop     rsi
0x1800137d9  pop     rbp
0x1800137da  retn
```
