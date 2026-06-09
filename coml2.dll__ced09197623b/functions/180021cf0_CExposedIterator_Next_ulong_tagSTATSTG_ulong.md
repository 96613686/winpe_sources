# CExposedIterator::Next(ulong,tagSTATSTG *,ulong *)

- ea: `0x180021cf0`
- end: `0x180021fa1`
- name: `?Next@CExposedIterator@@UEAAJKPEAUtagSTATSTG@@PEAK@Z`
- size: `689`
- prototype: `__int64 __fastcall(CExposedIterator *__hidden this, unsigned int, struct tagSTATSTG *, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000b904`
- `0x180015f30`
- `0x180016810`
- `0x180021cf0`
- `0x180021fb0`
- `0x18002200c`
- `0x1800222fc`
- `0x18002329c`
- `0x18002366c`
- `0x180042800`
- `0x180043100`
- `0x18006141c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021f7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021f7f`

## pseudocode

```c
__int64 __fastcall CExposedIterator::Next(
        CExposedIterator *this,
        unsigned int a2,
        struct tagSTATSTG *a3,
        unsigned int *a4)
{
  __int64 v4; // rax
  unsigned int v5; // r15d
  int v9; // ebx
  struct tagSTATSTG *v10; // rdi
  struct ILockBytes *v11; // r8
  _QWORD *v12; // rcx
  _QWORD *v13; // rdx
  unsigned __int64 v14; // rdi
  unsigned __int16 v16; // bx
  struct tagSTATSTG *v17; // r15
  __int64 v18; // rdx
  PDocFile *v19; // rcx
  int GreaterEntry; // eax
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  int v25; // eax
  __int64 v26; // rsi
  void *v27; // rcx
  int v29; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h]
  __int128 v31; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v32[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int128 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+90h] [rbp-70h]
  __int128 v36; // [rsp+A0h] [rbp-60h]
  _BYTE v37[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v38; // [rsp+F0h] [rbp-10h]

  v4 = *((_QWORD *)this + 8);
  v5 = a2;
  v29 = -2147286784;
  v30 = v4;
  v31 = 0;
  memset_0(v32, 0, 0x50u);
  v9 = CExpParameterValidate::Next(v5, a3, a4);
  if ( v9 >= 0 )
  {
    v10 = a3;
    v9 = CExposedIterator::Validate(this);
    if ( v9 >= 0 )
    {
      while ( 1 )
      {
        v9 = CSafeSem::Take((CSafeSem *)&v29);
        if ( v9 < 0 )
          break;
        v12 = (_QWORD *)*((_QWORD *)this + 8);
        v13 = (_QWORD *)*((_QWORD *)this + 7);
        v13[4] = v12[2];
        v13[5] = v12[3];
        v13[6] = v12[4];
        if ( (*(_BYTE *)(*((_QWORD *)this + 6) + 20LL) & 0x20) != 0 )
        {
          v9 = -2147286782;
          break;
        }
        v16 = *((_WORD *)this + 72);
        if ( v16 > 0x40u )
          v16 = 64;
        if ( this != (CExposedIterator *)-80LL )
          memcpy_0(v37, (char *)this + 80, v16);
        v38 = v16;
        v17 = (struct tagSTATSTG *)((char *)a3 + 80 * v5);
        v9 = 0;
        while ( 1 )
        {
          if ( v10 >= v17 )
            goto LABEL_7;
          memset_0(v10, 0, 0x50u);
          v18 = *(_QWORD *)(*((_QWORD *)this + 6) + 120LL);
          v19 = v18 ? (PDocFile *)(v18 + *(_QWORD *)NtCurrentTeb()->ReservedForOle) : 0LL;
          GreaterEntry = PDocFile::FindGreaterEntry(
                           v19,
                           (CExposedIterator *)((char *)this + 80),
                           0,
                           (struct tagSTATSTG *)v32);
          v9 = GreaterEntry;
          if ( GreaterEntry < 0 )
            break;
          CDfName::Set((CExposedIterator *)((char *)this + 80), v32[0]);
          v21 = v33;
          *(_OWORD *)v10 = *(_OWORD *)v32;
          *(_QWORD *)&v35 = 0;
          v22 = v34;
          *((_OWORD *)v10 + 1) = v21;
          HIDWORD(v36) = 0;
          v23 = v35;
          *((_OWORD *)v10 + 2) = v22;
          v24 = v36;
          *((_OWORD *)v10 + 3) = v23;
          *((_OWORD *)v10 + 4) = v24;
          v10 = (struct tagSTATSTG *)((char *)v10 + 80);
        }
        if ( GreaterEntry == -2147287022 )
        {
          v9 = 1;
LABEL_8:
          if ( v9 < 0 )
            CDfName::Set((CExposedIterator *)((char *)this + 80), (const struct CDfName *)v37);
          break;
        }
        if ( GreaterEntry != -2147483638 )
        {
LABEL_7:
          if ( v9 != -2147286524 )
            goto LABEL_8;
        }
        v25 = CAsyncConnection::Notify(
                (CExposedIterator *)((char *)this + 16),
                v9,
                v11,
                *((struct CPerContext **)this + 8),
                (struct CSafeSem *)&v29);
        if ( v25 )
        {
          v9 = v25;
          goto LABEL_13;
        }
        v5 = a2;
      }
    }
    v14 = 0xCCCCCCCCCCCCCCCDuLL * ((v10 - a3) >> 4);
    if ( v9 < 0 )
    {
      v26 = 0;
      do
      {
        v27 = (void *)*((_QWORD *)a3 + 10 * v26);
        if ( v27 )
        {
          CoTaskMemFree(v27);
          *((_QWORD *)a3 + 10 * v26) = 0;
        }
        v26 = (unsigned int)(v26 + 1);
      }
      while ( (unsigned int)v26 <= (unsigned int)v14 );
    }
    else if ( a4 )
    {
      *a4 = v14;
    }
  }
LABEL_13:
  CSafeSem::Release((CSafeSem *)&v29);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180021cf0  push    rbp
0x180021cf2  push    rbx
0x180021cf3  push    rsi
0x180021cf4  push    rdi
0x180021cf5  push    r12
0x180021cf7  push    r13
0x180021cf9  push    r14
0x180021cfb  push    r15
0x180021cfd  lea     rbp, [rsp-18h]
0x180021d02  sub     rsp, 118h
0x180021d09  mov     rax, cs:__security_cookie
0x180021d10  xor     rax, rsp
0x180021d13  mov     [rbp+50h+var_50], rax
0x180021d17  mov     rax, [rcx+40h]
0x180021d1b  mov     r15d, edx
0x180021d1e  mov     [rsp+150h+var_120], edx
0x180021d22  mov     r12, r8
0x180021d25  xor     edx, edx; Val
0x180021d27  mov     [rsp+150h+var_118], 80030100h
0x180021d2f  mov     r14, rcx
0x180021d32  mov     [rsp+150h+var_110], rax
0x180021d37  xorps   xmm0, xmm0
0x180021d3a  lea     rcx, [rsp+150h+var_F0]; void *
0x180021d3f  mov     r13, r9
0x180021d42  lea     r8d, [rdx+50h]; Size
0x180021d46  movdqu  [rsp+150h+var_108], xmm0
0x180021d4c  call    memset_0
0x180021d51  mov     r8, r13; unsigned int *
0x180021d54  mov     rdx, r12; struct tagSTATSTG *
0x180021d57  mov     ecx, r15d; unsigned int
0x180021d5a  call    ?Next@CExpParameterValidate@@SAJKPEAUtagSTATSTG@@PEAK@Z; CExpParameterValidate::Next(ulong,tagSTATSTG *,ulong *)
0x180021d5f  mov     ebx, eax
0x180021d61  test    eax, eax
0x180021d63  js      loc_180021E00
0x180021d69  mov     rcx, r14; this
0x180021d6c  mov     rdi, r12
0x180021d6f  call    ?Validate@CExposedIterator@@QEBAJXZ; CExposedIterator::Validate(void)
0x180021d74  mov     ebx, eax
0x180021d76  test    eax, eax
0x180021d78  js      short loc_180021DDA
0x180021d7a  lea     rcx, [rsp+150h+var_118]; this
0x180021d7f  call    ?Take@CSafeSem@@QEAAJXZ; CSafeSem::Take(void)
0x180021d84  mov     ebx, eax
0x180021d86  test    eax, eax
0x180021d88  js      short loc_180021DDA
0x180021d8a  mov     rcx, [r14+40h]
0x180021d8e  mov     rdx, [r14+38h]
0x180021d92  mov     rax, [rcx+10h]
0x180021d96  mov     [rdx+20h], rax
0x180021d9a  mov     rax, [rcx+18h]
0x180021d9e  mov     [rdx+28h], rax
0x180021da2  mov     rax, [rcx+20h]
0x180021da6  mov     [rdx+30h], rax
0x180021daa  mov     rax, [r14+30h]
0x180021dae  test    byte ptr [rax+14h], 20h
0x180021db2  jz      short loc_180021E2C
0x180021db4  mov     ebx, 80030102h
0x180021db9  jmp     short loc_180021DDA
0x180021dbb  cmp     eax, 8000000Ah
0x180021dc0  jz      loc_180021F19
0x180021dc6  cmp     ebx, 80030204h
0x180021dcc  jz      loc_180021F19
0x180021dd2  test    ebx, ebx
0x180021dd4  js      loc_180021F5C
0x180021dda  sub     rdi, r12
0x180021ddd  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180021de7  sar     rdi, 4
0x180021deb  imul    rdi, rax
0x180021def  test    ebx, ebx
0x180021df1  js      loc_180021F6D
0x180021df7  test    r13, r13
0x180021dfa  jnz     loc_180021F98
0x180021e00  lea     rcx, [rsp+150h+var_118]; this
0x180021e05  call    ?Release@CSafeSem@@QEAAXXZ; CSafeSem::Release(void)
0x180021e0a  mov     eax, ebx
0x180021e0c  mov     rcx, [rbp+50h+var_50]
0x180021e10  xor     rcx, rsp; StackCookie
0x180021e13  call    __security_check_cookie
0x180021e18  add     rsp, 118h
0x180021e1f  pop     r15
0x180021e21  pop     r14
0x180021e23  pop     r13
0x180021e25  pop     r12
0x180021e27  pop     rdi
0x180021e28  pop     rsi
0x180021e29  pop     rbx
0x180021e2a  pop     rbp
0x180021e2b  retn
0x180021e2c  lea     rsi, [r14+50h]
0x180021e30  mov     eax, 40h ; '@'
0x180021e35  movzx   ebx, word ptr [rsi+40h]
0x180021e39  cmp     bx, ax
0x180021e3c  ja      loc_180021F0D
0x180021e42  test    rsi, rsi
0x180021e45  jz      short loc_180021E57
0x180021e47  movzx   r8d, bx; Size
0x180021e4b  lea     rcx, [rbp+50h+var_A0]; void *
0x180021e4f  mov     rdx, rsi; Src
0x180021e52  call    memcpy_0
0x180021e57  mov     eax, r15d
0x180021e5a  mov     [rbp+50h+var_60], bx
0x180021e5e  lea     r15, [rax+rax*4]
0x180021e62  shl     r15, 4
0x180021e66  add     r15, r12
0x180021e69  xor     ebx, ebx
0x180021e6b  cmp     rdi, r15
0x180021e6e  jnb     loc_180021DC6
0x180021e74  xor     edx, edx; Val
0x180021e76  mov     rcx, rdi; void *
0x180021e79  lea     r8d, [rdx+50h]; Size
0x180021e7d  call    memset_0
0x180021e82  mov     rax, [r14+30h]
0x180021e86  mov     rdx, [rax+78h]
0x180021e8a  test    rdx, rdx
0x180021e8d  jz      loc_180021F15
0x180021e93  mov     rax, gs:30h
0x180021e9c  mov     rcx, [rax+1758h]
0x180021ea3  mov     rcx, [rcx]
0x180021ea6  add     rcx, rdx; this
0x180021ea9  lea     r9, [rsp+150h+var_F0]; struct tagSTATSTG *
0x180021eae  xor     r8d, r8d; struct SIterBuffer *
0x180021eb1  mov     rdx, rsi; struct CDfName *
0x180021eb4  call    ?FindGreaterEntry@PDocFile@@QEAAJPEBVCDfName@@PEAUSIterBuffer@@PEAUtagSTATSTG@@@Z; PDocFile::FindGreaterEntry(CDfName const *,SIterBuffer *,tagSTATSTG *)
0x180021eb9  mov     ebx, eax
0x180021ebb  test    eax, eax
0x180021ebd  js      short loc_180021F3D
0x180021ebf  mov     rdx, [rsp+150h+var_F0]; unsigned __int16 *
0x180021ec4  mov     rcx, rsi; this
0x180021ec7  call    ?Set@CDfName@@QEAAXPEBG@Z; CDfName::Set(ushort const *)
0x180021ecc  movaps  xmm0, xmmword ptr [rsp+150h+var_F0]
0x180021ed1  movaps  xmm1, [rsp+150h+var_E0]
0x180021ed6  movups  xmmword ptr [rdi], xmm0
0x180021ed9  mov     qword ptr [rbp+50h+var_C0], 0
0x180021ee1  movaps  xmm0, [rbp+50h+var_D0]
0x180021ee5  movups  xmmword ptr [rdi+10h], xmm1
0x180021ee9  mov     [rbp+50h+var_A4], 0
0x180021ef0  movaps  xmm1, [rbp+50h+var_C0]
0x180021ef4  movups  xmmword ptr [rdi+20h], xmm0
0x180021ef8  movaps  xmm0, xmmword ptr [rbp-60h]
0x180021efc  movups  xmmword ptr [rdi+30h], xmm1
0x180021f00  movups  xmmword ptr [rdi+40h], xmm0
0x180021f04  add     rdi, 50h ; 'P'
0x180021f08  jmp     loc_180021E6B
0x180021f0d  movzx   ebx, ax
0x180021f10  jmp     loc_180021E42
0x180021f15  xor     ecx, ecx
0x180021f17  jmp     short loc_180021EA9
0x180021f19  mov     r9, [r14+40h]; struct CPerContext *
0x180021f1d  lea     rax, [rsp+150h+var_118]
0x180021f22  lea     rcx, [r14+10h]; this
0x180021f26  mov     [rsp+150h+var_130], rax; struct CSafeSem *
0x180021f2b  mov     edx, ebx; int
0x180021f2d  call    ?Notify@CAsyncConnection@@QEAAJJPEAUILockBytes@@PEAVCPerContext@@PEAVCSafeSem@@@Z; CAsyncConnection::Notify(long,ILockBytes *,CPerContext *,CSafeSem *)
0x180021f32  test    eax, eax
0x180021f34  jz      short loc_180021F52
0x180021f36  mov     ebx, eax
0x180021f38  jmp     loc_180021E00
0x180021f3d  cmp     eax, 80030012h
0x180021f42  jnz     loc_180021DBB
0x180021f48  mov     ebx, 1
0x180021f4d  jmp     loc_180021DD2
0x180021f52  mov     r15d, [rsp+150h+var_120]
0x180021f57  jmp     loc_180021D7A
0x180021f5c  lea     rdx, [rbp+50h+var_A0]; struct CDfName *
0x180021f60  mov     rcx, rsi; this
0x180021f63  call    ?Set@CDfName@@QEAAXPEBV1@@Z; CDfName::Set(CDfName const *)
0x180021f68  jmp     loc_180021DDA
0x180021f6d  xor     esi, esi
0x180021f6f  lea     r14, [rsi+rsi*4]
0x180021f73  add     r14, r14
0x180021f76  mov     rcx, [r12+r14*8]; pv
0x180021f7a  test    rcx, rcx
0x180021f7d  jz      short loc_180021F8D
0x180021f7f  call    cs:__imp_CoTaskMemFree
0x180021f85  mov     qword ptr [r12+r14*8], 0
0x180021f8d  inc     esi
0x180021f8f  cmp     esi, edi
0x180021f91  jbe     short loc_180021F6F
0x180021f93  jmp     loc_180021E00
0x180021f98  mov     [r13+0], edi
0x180021f9c  jmp     loc_180021E00
```
