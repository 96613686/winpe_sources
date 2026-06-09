# CLogState::_AllocateFromCurrent(CWriteMap &,ulong *,_RANGEENTRY *,int)

- ea: `0x180009600`
- end: `0x18000974d`
- name: `?_AllocateFromCurrent@CLogState@@AEAAHAEAVCWriteMap@@PEAKPEAU_RANGEENTRY@@H@Z`
- size: `333`
- prototype: `__int64 __fastcall(CLogState *this, struct CWriteMap *, unsigned int *, struct _RANGEENTRY *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009298`

## callees

- `0x180009600`
- `0x180009934`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009625`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009625`

## pseudocode

```c
__int64 __fastcall CLogState::_AllocateFromCurrent(
        CLogState *this,
        struct CWriteMap *a2,
        unsigned int *a3,
        struct _RANGEENTRY *a4,
        int a5)
{
  unsigned int v7; // r9d
  int v10; // edx
  int v11; // ecx
  int v12; // r10d
  unsigned int v13; // edx
  BOOL v14; // ecx
  unsigned int v15; // r8d
  __int64 v16; // rax
  __int128 v17; // xmm1
  int v18; // r9d
  int v19; // edx
  bool v21; // zf
  unsigned int v22; // eax
  int v23; // eax

  v7 = *((_DWORD *)this + 29);
  if ( v7 )
  {
    v12 = *((_DWORD *)this + 28);
  }
  else
  {
    if ( !*((_DWORD *)this + 31) )
    {
      GetCurrentThreadId();
      CLogState::_DoWrapAround(this);
    }
    v10 = *((_DWORD *)this + 30);
    v7 = 8160;
    v11 = *((_DWORD *)this + 20);
    --*((_DWORD *)this + 31);
    *((_DWORD *)this + 27) = v10;
    v12 = 0;
    *((_DWORD *)this + 28) = 0;
    *((_DWORD *)this + 29) = 8160;
    *((_DWORD *)this + 30) = v11 + v10;
    *((_DWORD *)a4 + 2) = v10;
    *((_DWORD *)a4 + 3) = v11;
  }
  v13 = *a3;
  if ( *a3 < v7 )
  {
    v14 = 0;
    v15 = *a3;
  }
  else
  {
    v14 = 1;
    v15 = v7;
  }
  *((_DWORD *)a4 + 1) = v15;
  if ( !v14 )
    v14 = (unsigned __int64)(v15 + *((_DWORD *)a2 + 18)) + 24 >= v7 || a5;
  *(_DWORD *)a4 = v12;
  *((_DWORD *)a4 + 7) = v14;
  if ( v15 )
  {
    v16 = 32LL * *((unsigned int *)a2 + 20);
    v17 = *((_OWORD *)a4 + 1);
    *(_OWORD *)((char *)a2 + v16 + 84) = *(_OWORD *)a4;
    *(_OWORD *)((char *)a2 + v16 + 100) = v17;
    ++*((_DWORD *)a2 + 20);
  }
  v18 = v14 ? v13 - v15 : 0;
  *a3 = v18;
  if ( v14 )
  {
    *((_DWORD *)this + 4) -= *((_DWORD *)this + 29);
    *((_QWORD *)this + 14) = 0;
    if ( !v18 )
    {
      *((_DWORD *)a2 + 19) = 0;
      return 1;
    }
  }
  else
  {
    v19 = *((_DWORD *)a2 + 18);
    *((_DWORD *)this + 4) -= v19 + v15;
    *((_DWORD *)this + 29) -= v19 + v15;
    *((_DWORD *)this + 28) += v19 + v15;
    if ( !v18 )
      return 1;
  }
  *((_DWORD *)a4 + 2) += *((_DWORD *)a4 + 3);
  v21 = *((_DWORD *)this + 26) == 0;
  v22 = *((_DWORD *)a4 + 2);
  *(_DWORD *)a4 = 0;
  if ( !v21 && v22 >= *((_DWORD *)this + 14) )
  {
    v23 = *(_DWORD *)this;
    ++*((_DWORD *)a4 + 4);
    *((_DWORD *)a4 + 2) = v23;
  }
  return 0;
}

```

## disassembly

```asm
0x180009600  push    rbx
0x180009602  push    rsi
0x180009603  push    rdi
0x180009604  push    r14
0x180009606  sub     rsp, 28h
0x18000960a  mov     rdi, r9
0x18000960d  mov     r14, r8
0x180009610  mov     r9d, [rcx+74h]
0x180009614  mov     rsi, rdx
0x180009617  mov     rbx, rcx
0x18000961a  test    r9d, r9d
0x18000961d  jnz     short loc_180009661
0x18000961f  cmp     [rcx+7Ch], r9d
0x180009623  jnz     short loc_180009633
0x180009625  call    cs:__imp_GetCurrentThreadId
0x18000962b  mov     rcx, rbx; this
0x18000962e  call    ?_DoWrapAround@CLogState@@AEAAXXZ; CLogState::_DoWrapAround(void)
0x180009633  mov     edx, [rbx+78h]
0x180009636  mov     r9d, 1FE0h
0x18000963c  mov     ecx, [rbx+50h]
0x18000963f  dec     dword ptr [rbx+7Ch]
0x180009642  mov     [rbx+6Ch], edx
0x180009645  xor     r10d, r10d
0x180009648  mov     dword ptr [rbx+70h], 0
0x18000964f  lea     eax, [rcx+rdx]
0x180009652  mov     [rbx+74h], r9d
0x180009656  mov     [rbx+78h], eax
0x180009659  mov     [rdi+8], edx
0x18000965c  mov     [rdi+0Ch], ecx
0x18000965f  jmp     short loc_180009665
0x180009661  mov     r10d, [rcx+70h]
0x180009665  mov     edx, [r14]
0x180009668  mov     r11d, 1
0x18000966e  cmp     edx, r9d
0x180009671  jb      short loc_18000967B
0x180009673  mov     ecx, r11d
0x180009676  mov     r8d, r9d
0x180009679  jmp     short loc_180009680
0x18000967b  xor     ecx, ecx
0x18000967d  mov     r8d, edx
0x180009680  mov     [rdi+4], r8d
0x180009684  test    ecx, ecx
0x180009686  jnz     short loc_1800096A8
0x180009688  mov     ecx, [rsi+48h]
0x18000968b  add     ecx, r8d
0x18000968e  mov     eax, r9d
0x180009691  add     rcx, 18h
0x180009695  cmp     rcx, rax
0x180009698  jnb     short loc_1800096A5
0x18000969a  cmp     [rsp+48h+arg_20], 0
0x18000969f  jnz     short loc_1800096A5
0x1800096a1  xor     ecx, ecx
0x1800096a3  jmp     short loc_1800096A8
0x1800096a5  mov     ecx, r11d
0x1800096a8  mov     [rdi], r10d
0x1800096ab  mov     [rdi+1Ch], ecx
0x1800096ae  test    r8d, r8d
0x1800096b1  jz      short loc_1800096CF
0x1800096b3  mov     eax, [rsi+50h]
0x1800096b6  movups  xmm0, xmmword ptr [rdi]
0x1800096b9  shl     rax, 5
0x1800096bd  movups  xmm1, xmmword ptr [rdi+10h]
0x1800096c1  movups  xmmword ptr [rax+rsi+54h], xmm0
0x1800096c6  movups  xmmword ptr [rax+rsi+64h], xmm1
0x1800096cb  add     [rsi+50h], r11d
0x1800096cf  sub     edx, r8d
0x1800096d2  mov     eax, ecx
0x1800096d4  neg     eax
0x1800096d6  sbb     r9d, r9d
0x1800096d9  and     r9d, edx
0x1800096dc  mov     [r14], r9d
0x1800096df  test    ecx, ecx
0x1800096e1  jz      short loc_1800096FC
0x1800096e3  mov     eax, [rbx+74h]
0x1800096e6  sub     [rbx+10h], eax
0x1800096e9  mov     qword ptr [rbx+70h], 0
0x1800096f1  test    r9d, r9d
0x1800096f4  jnz     short loc_18000971E
0x1800096f6  mov     [rsi+4Ch], r9d
0x1800096fa  jmp     short loc_180009719
0x1800096fc  mov     edx, [rsi+48h]
0x1800096ff  lea     ecx, [rdx+r8]
0x180009703  sub     [rbx+10h], ecx
0x180009706  lea     ecx, [rdx+r8]
0x18000970a  sub     [rbx+74h], ecx
0x18000970d  lea     ecx, [rdx+r8]
0x180009711  add     [rbx+70h], ecx
0x180009714  test    r9d, r9d
0x180009717  jnz     short loc_18000971E
0x180009719  mov     eax, r11d
0x18000971c  jmp     short loc_180009743
0x18000971e  mov     eax, [rdi+0Ch]
0x180009721  add     [rdi+8], eax
0x180009724  cmp     dword ptr [rbx+68h], 0
0x180009728  mov     eax, [rdi+8]
0x18000972b  mov     dword ptr [rdi], 0
0x180009731  jz      short loc_180009741
0x180009733  cmp     eax, [rbx+38h]
0x180009736  jb      short loc_180009741
0x180009738  mov     eax, [rbx]
0x18000973a  add     [rdi+10h], r11d
0x18000973e  mov     [rdi+8], eax
0x180009741  xor     eax, eax
0x180009743  add     rsp, 28h
0x180009747  pop     r14
0x180009749  pop     rdi
0x18000974a  pop     rsi
0x18000974b  pop     rbx
0x18000974c  retn
```
