# CWaveObj::Write(void *)

- ea: `0x180014ed8`
- end: `0x18001514a`
- name: `?Write@CWaveObj@@AEAAJPEAX@Z`
- size: `626`
- prototype: `__int64 __fastcall(CWaveObj *this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ed58`

## callees

- `0x1800021a8`
- `0x180014724`
- `0x180014d48`
- `0x180014ed8`
- `0x1800217bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001512a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001512a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014f21`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014f21`

## pseudocode

```c
__int64 __fastcall CWaveObj::Write(CWaveObj *this, unsigned __int8 *a2)
{
  CWaveObj *v3; // rbp
  __int64 result; // rax
  size_t v5; // r13
  unsigned int v6; // r15d
  int v7; // eax
  __int64 v8; // rax
  __int64 v9; // r12
  __int64 v10; // r14
  unsigned int v11; // r8d
  int Data; // edi
  unsigned int v13; // eax
  int v14; // r14d
  unsigned int v15; // r14d
  __int64 *v16; // r13
  int v17; // r12d
  unsigned int v18; // edi
  unsigned __int8 *v19; // rbx
  unsigned int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // [rsp+30h] [rbp-48h]
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+38h] [rbp-40h]
  size_t Size; // [rsp+90h] [rbp+18h] BYREF
  unsigned int v29; // [rsp+98h] [rbp+20h] BYREF

  LODWORD(Size) = 0;
  v3 = this;
  v29 = 0;
  result = CWaveObj::Size(this, (unsigned int *)&Size, &v29);
  if ( (int)result >= 0 )
  {
    lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)((char *)v3 + 8);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 8));
    v5 = (unsigned int)Size;
    v6 = 2;
    *(_DWORD *)a2 = 2;
    *((_DWORD *)a2 + 1) = *((_DWORD *)v3 + 38);
    *((_DWORD *)a2 + 2) = *((_DWORD *)v3 + 42) >> 2;
    *((_DWORD *)a2 + 3) = v5;
    v7 = *((_DWORD *)v3 + 42) + 7;
    v29 = 0;
    LODWORD(Size) = 0;
    v8 = (v7 & 0xFFFFFFF8) + 16;
    *((_DWORD *)a2 + 4) = v8;
    v9 = (unsigned int)v8;
    v25 = (unsigned int)v8;
    *(_DWORD *)&a2[v8 + 8] = 1;
    v10 = (unsigned int)(v8 + 32);
    *((_DWORD *)a2 + 5) = v10;
    v11 = *((_DWORD *)v3 + 35);
    *((_DWORD *)v3 + 36) = v11;
    Data = CWaveObj::GetData(v3, &a2[(unsigned int)v10 + 4], v11, &v29, (unsigned int *)&Size);
    *(_DWORD *)&a2[v10] = *((_DWORD *)v3 + 36);
    if ( Data < 0 )
    {
      memset_0(a2, 0, v5);
      goto LABEL_22;
    }
    v13 = *((_DWORD *)v3 + 35);
    if ( v13 >= 4 )
      v14 = v13 + v10 + 11;
    else
      v14 = v10 + 15;
    v15 = v14 & 0xFFFFFFF8;
    *(_OWORD *)&a2[v9 + 12] = *(_OWORD *)((char *)v3 + 74);
    *(_WORD *)&a2[v9 + 28] = *((_WORD *)v3 + 45);
    v16 = (__int64 *)*((_QWORD *)v3 + 15);
    *(_DWORD *)&a2[v9] = v16 != 0 ? 2 : 0;
    if ( v16 )
    {
      v17 = *((_DWORD *)v3 + 43);
      do
      {
        v18 = v6 + 1;
        v19 = &a2[v15];
        *(_DWORD *)&a2[4 * v6 + 16] = v15;
        memcpy_0(v19, (const void *)v16[1], (*((_DWORD *)v16 + 4) + 23) & 0xFFFFFFF8);
        ++v6;
        v15 += (*((_DWORD *)v16 + 4) + 23) & 0xFFFFFFF8;
        v20 = 0;
        if ( v17 != 1 )
          v20 = v18;
        --v17;
        *((_DWORD *)v19 + 1) = v20;
        v16 = (__int64 *)*v16;
      }
      while ( v16 );
      v3 = this;
      Data = 0;
      v9 = v25;
    }
    v21 = *((_QWORD *)v3 + 16);
    if ( v21 && *(_QWORD *)(v21 + 16) )
    {
      *(_DWORD *)&a2[4 * v6 + 16] = v15;
      *(_DWORD *)&a2[v9 + 4] = v6;
      v22 = *((_QWORD *)v3 + 16);
    }
    else
    {
      v23 = *((_QWORD *)v3 + 20);
      if ( !v23 || (v24 = *(_QWORD *)(v23 + 80)) == 0 || !*(_QWORD *)(v24 + 16) )
      {
        *(_DWORD *)&a2[v9 + 4] = 0;
        goto LABEL_22;
      }
      *(_DWORD *)&a2[4 * v6 + 16] = v15;
      *(_DWORD *)&a2[v9 + 4] = v6;
      v22 = *(_QWORD *)(*((_QWORD *)v3 + 20) + 80LL);
    }
    memcpy_0(&a2[v15], *(const void **)(v22 + 16), (*(_DWORD *)(v22 + 24) + 15) & 0xFFFFFFF8);
    Data = 0;
LABEL_22:
    LeaveCriticalSection(lpCriticalSection);
    return (unsigned int)Data;
  }
  return result;
}

```

## disassembly

```asm
0x180014ed8  mov     rax, rsp
0x180014edb  mov     [rax+10h], rbx
0x180014edf  mov     [rax+8], rcx
0x180014ee3  push    rbp
0x180014ee4  push    rsi
0x180014ee5  push    rdi
0x180014ee6  push    r12
0x180014ee8  push    r13
0x180014eea  push    r14
0x180014eec  push    r15
0x180014eee  sub     rsp, 40h
0x180014ef2  mov     rsi, rdx
0x180014ef5  lea     r8, [rax+20h]; unsigned int *
0x180014ef9  xor     edi, edi
0x180014efb  lea     rdx, [rax+18h]; unsigned int *
0x180014eff  mov     [rax+18h], edi
0x180014f02  mov     rbp, rcx
0x180014f05  mov     [rax+20h], edi
0x180014f08  call    ?Size@CWaveObj@@AEAAJPEAK0@Z; CWaveObj::Size(ulong *,ulong *)
0x180014f0d  test    eax, eax
0x180014f0f  js      loc_180015132
0x180014f15  lea     rax, [rbp+8]
0x180014f19  mov     rcx, rax; lpCriticalSection
0x180014f1c  mov     [rsp+78h+lpCriticalSection], rax
0x180014f21  call    cs:__imp_EnterCriticalSection
0x180014f27  mov     r13d, dword ptr [rsp+78h+Size]
0x180014f2f  lea     r15d, [rdi+2]
0x180014f33  mov     [rsi], r15d
0x180014f36  lea     rdx, [rsi+4]
0x180014f3a  mov     eax, [rbp+98h]
0x180014f40  lea     r9, [rsp+78h+arg_18]; unsigned int *
0x180014f48  mov     [rsi+4], eax
0x180014f4b  mov     ecx, 0FFFFFFF8h
0x180014f50  mov     eax, [rbp+0A8h]
0x180014f56  shr     eax, 2
0x180014f59  mov     [rsi+8], eax
0x180014f5c  mov     [rsi+0Ch], r13d
0x180014f60  mov     eax, [rbp+0A8h]
0x180014f66  add     eax, 7
0x180014f69  mov     [rsp+78h+arg_18], edi
0x180014f70  and     eax, ecx
0x180014f72  mov     dword ptr [rsp+78h+Size], edi
0x180014f79  add     eax, 10h
0x180014f7c  mov     rcx, rbp; this
0x180014f7f  mov     [rsi+10h], eax
0x180014f82  mov     r12d, eax
0x180014f85  mov     [rsp+78h+var_48], r12
0x180014f8a  mov     dword ptr [rax+rsi+8], 1
0x180014f92  lea     r14d, [rax+20h]
0x180014f96  mov     [rsi+14h], r14d
0x180014f9a  lea     rax, [rsp+78h+Size]
0x180014fa2  mov     r8d, [rbp+8Ch]; unsigned int
0x180014fa9  mov     ebx, r14d
0x180014fac  add     rdx, rbx; unsigned __int8 *
0x180014faf  mov     [rbp+90h], r8d
0x180014fb6  mov     [rsp+78h+var_58], rax; unsigned int *
0x180014fbb  call    ?GetData@CWaveObj@@AEAAJPEAEKPEAK1@Z; CWaveObj::GetData(uchar *,ulong,ulong *,ulong *)
0x180014fc0  mov     ecx, [rbp+90h]
0x180014fc6  mov     edi, eax
0x180014fc8  mov     [r14+rsi], ecx
0x180014fcc  test    eax, eax
0x180014fce  js      loc_180015118
0x180014fd4  mov     eax, [rbp+8Ch]
0x180014fda  cmp     eax, 4
0x180014fdd  jnb     short loc_180014FE5
0x180014fdf  add     r14d, 0Fh
0x180014fe3  jmp     short loc_180014FEC
0x180014fe5  add     r14d, 0Bh
0x180014fe9  add     r14d, eax
0x180014fec  movups  xmm0, xmmword ptr [rbp+4Ah]
0x180014ff0  mov     r9d, 0FFFFFFF8h
0x180014ff6  and     r14d, r9d
0x180014ff9  movups  xmmword ptr [r12+rsi+0Ch], xmm0
0x180014fff  movzx   eax, word ptr [rbp+5Ah]
0x180015003  mov     [r12+rsi+1Ch], ax
0x180015009  mov     r13, [rbp+78h]
0x18001500d  mov     rax, r13
0x180015010  neg     rax
0x180015013  sbb     ecx, ecx
0x180015015  and     ecx, r15d
0x180015018  mov     [r12+rsi], ecx
0x18001501c  mov     eax, [rbp+0ACh]
0x180015022  test    r13, r13
0x180015025  jz      short loc_180015092
0x180015027  mov     r12d, eax
0x18001502a  mov     ebp, r9d
0x18001502d  mov     eax, r15d
0x180015030  lea     edi, [r15+1]
0x180015034  mov     ebx, r14d
0x180015037  add     rbx, rsi
0x18001503a  mov     rcx, rbx; void *
0x18001503d  mov     [rsi+rax*4+10h], r14d
0x180015042  mov     r8d, [r13+10h]
0x180015046  mov     rdx, [r13+8]; Src
0x18001504a  add     r8d, 17h
0x18001504e  and     r8, rbp; Size
0x180015051  call    memcpy_0
0x180015056  mov     eax, [r13+10h]
0x18001505a  mov     r15d, edi
0x18001505d  add     eax, 17h
0x180015060  and     eax, ebp
0x180015062  add     r14d, eax
0x180015065  xor     eax, eax
0x180015067  cmp     r12d, 1
0x18001506b  cmovnz  eax, edi
0x18001506e  dec     r12d
0x180015071  mov     [rbx+4], eax
0x180015074  mov     r13, [r13+0]
0x180015078  test    r13, r13
0x18001507b  jnz     short loc_18001502D
0x18001507d  mov     rbp, [rsp+78h+arg_0]
0x180015085  xor     edi, edi
0x180015087  mov     r12, [rsp+78h+var_48]
0x18001508c  mov     r9d, 0FFFFFFF8h
0x180015092  mov     rax, [rbp+80h]
0x180015099  test    rax, rax
0x18001509c  jz      short loc_1800150D7
0x18001509e  cmp     qword ptr [rax+10h], 0
0x1800150a3  jz      short loc_1800150D7
0x1800150a5  mov     eax, r15d
0x1800150a8  mov     [rsi+rax*4+10h], r14d
0x1800150ad  mov     [r12+rsi+4], r15d
0x1800150b2  mov     rdx, [rbp+80h]
0x1800150b9  mov     r8d, [rdx+18h]
0x1800150bd  mov     rdx, [rdx+10h]; Src
0x1800150c1  add     r8d, 0Fh
0x1800150c5  mov     ecx, r14d
0x1800150c8  and     r8, r9; Size
0x1800150cb  add     rcx, rsi; void *
0x1800150ce  call    memcpy_0
0x1800150d3  xor     edi, edi
0x1800150d5  jmp     short loc_180015125
0x1800150d7  mov     rax, [rbp+0A0h]
0x1800150de  test    rax, rax
0x1800150e1  jz      short loc_18001510D
0x1800150e3  mov     rax, [rax+50h]
0x1800150e7  test    rax, rax
0x1800150ea  jz      short loc_18001510D
0x1800150ec  cmp     qword ptr [rax+10h], 0
0x1800150f1  jz      short loc_18001510D
0x1800150f3  mov     eax, r15d
0x1800150f6  mov     [rsi+rax*4+10h], r14d
0x1800150fb  mov     [r12+rsi+4], r15d
0x180015100  mov     rax, [rbp+0A0h]
0x180015107  mov     rdx, [rax+50h]
0x18001510b  jmp     short loc_1800150B9
0x18001510d  mov     dword ptr [r12+rsi+4], 0
0x180015116  jmp     short loc_180015125
0x180015118  mov     r8, r13; Size
0x18001511b  xor     edx, edx; Val
0x18001511d  mov     rcx, rsi; void *
0x180015120  call    memset_0
0x180015125  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x18001512a  call    cs:__imp_LeaveCriticalSection
0x180015130  mov     eax, edi
0x180015132  mov     rbx, [rsp+78h+arg_8]
0x18001513a  add     rsp, 40h
0x18001513e  pop     r15
0x180015140  pop     r14
0x180015142  pop     r13
0x180015144  pop     r12
0x180015146  pop     rdi
0x180015147  pop     rsi
0x180015148  pop     rbp
0x180015149  retn
```
