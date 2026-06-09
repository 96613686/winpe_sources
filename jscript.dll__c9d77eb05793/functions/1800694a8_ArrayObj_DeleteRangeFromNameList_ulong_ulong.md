# ArrayObj::DeleteRangeFromNameList(ulong,ulong)

- ea: `0x1800694a8`
- end: `0x1800695c3`
- name: `?DeleteRangeFromNameList@ArrayObj@@IEAAXKK@Z`
- size: `283`
- prototype: `void(ArrayObj *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18004b548`

## callees

- `0x180016498`
- `0x180030d40`
- `0x180039a10`
- `0x18003a350`
- `0x1800694a8`
- `0x1800765c8`
- `0x180076648`
- `0x1800942d0`

## import_xrefs

- `msvcrt!_ltow` at `0x18006956c`
- `msvcrt!_ltow` at `0x18006956c`

## pseudocode

```c
void __fastcall ArrayObj::DeleteRangeFromNameList(ArrayObj *this, unsigned int a2, unsigned int a3)
{
  NameList *v3; // rsi
  int v6; // edx
  struct SYM *v7; // rax
  int v8; // r8d
  int i; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v10; // [rsp+34h] [rbp-CCh] BYREF
  struct VVAL *v11; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v12; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+50h] [rbp-B0h]
  __int128 v14; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v15; // [rsp+68h] [rbp-98h]
  wchar_t Buffer[256]; // [rsp+70h] [rbp-90h] BYREF

  v3 = (NameList *)*((_QWORD *)this + 2);
  v13 = 0;
  v12 = 0;
  v10 = 0;
  v11 = 0;
  if ( (unsigned int)ArrayObj::FSparseArray(this) )
  {
    v6 = -1;
    for ( i = -1; (unsigned int)CIndexedNameList::FGetNextId(v3, v6, &i, &v11, (struct SYM *)&v12); v6 = i )
    {
      if ( (unsigned int)FGetIndex((struct SYM *)&v12, &v10) && v10 >= a2 && v10 <= a3 )
        NameList::DeleteVvalById(v3, i, 0);
    }
  }
  else
  {
    while ( a2 <= a3 )
    {
      _ltow(a2, Buffer, 10);
      v15 = 0;
      v14 = 0;
      v7 = SYM::InitFromPsz((SYM *)&v14, Buffer);
      NameList::DeleteVval(v3, v7, v8);
      ++a2;
    }
  }
}

```

## disassembly

```asm
0x1800694a8  mov     [rsp-8+arg_10], rbx
0x1800694ad  push    rbp
0x1800694ae  push    rsi
0x1800694af  push    rdi
0x1800694b0  lea     rbp, [rsp-180h]
0x1800694b8  sub     rsp, 280h
0x1800694bf  mov     rax, cs:__security_cookie
0x1800694c6  xor     rax, rsp
0x1800694c9  mov     [rbp+190h+var_20], rax
0x1800694d0  mov     rsi, [rcx+10h]
0x1800694d4  xor     eax, eax
0x1800694d6  xorps   xmm0, xmm0
0x1800694d9  mov     [rsp+290h+var_240], rax
0x1800694de  movups  [rsp+290h+var_250], xmm0
0x1800694e3  mov     [rsp+290h+var_25C], eax
0x1800694e7  mov     edi, r8d
0x1800694ea  mov     ebx, edx
0x1800694ec  mov     [rsp+290h+var_258], 0
0x1800694f5  call    ?FSparseArray@ArrayObj@@QEAAHXZ; ArrayObj::FSparseArray(void)
0x1800694fa  test    eax, eax
0x1800694fc  jz      loc_18006959D
0x180069502  or      edx, 0FFFFFFFFh
0x180069505  mov     [rsp+290h+var_260], edx
0x180069509  jmp     short loc_18006953D
0x18006950b  lea     rdx, [rsp+290h+var_25C]; unsigned int *
0x180069510  lea     rcx, [rsp+290h+var_250]; struct SYM *
0x180069515  call    ?FGetIndex@@YAHPEAUSYM@@PEAK@Z; FGetIndex(SYM *,ulong *)
0x18006951a  test    eax, eax
0x18006951c  jz      short loc_180069539
0x18006951e  cmp     [rsp+290h+var_25C], ebx
0x180069522  jb      short loc_180069539
0x180069524  cmp     [rsp+290h+var_25C], edi
0x180069528  ja      short loc_180069539
0x18006952a  mov     edx, [rsp+290h+var_260]; int
0x18006952e  xor     r8d, r8d; int
0x180069531  mov     rcx, rsi; this
0x180069534  call    ?DeleteVvalById@NameList@@QEAAJJH@Z; NameList::DeleteVvalById(long,int)
0x180069539  mov     edx, [rsp+290h+var_260]; int
0x18006953d  lea     rax, [rsp+290h+var_250]
0x180069542  mov     rcx, rsi; this
0x180069545  lea     r9, [rsp+290h+var_258]; struct VVAL **
0x18006954a  mov     [rsp+290h+var_270], rax; struct SYM *
0x18006954f  lea     r8, [rsp+290h+var_260]; int *
0x180069554  call    ?FGetNextId@CIndexedNameList@@UEAAHJPEAJPEAPEAUVVAL@@PEAUSYM@@@Z; CIndexedNameList::FGetNextId(long,long *,VVAL * *,SYM *)
0x180069559  test    eax, eax
0x18006955b  jnz     short loc_18006950B
0x18006955d  jmp     short loc_1800695A1
0x18006955f  mov     r8d, 0Ah; Radix
0x180069565  lea     rdx, [rsp+290h+Buffer]; Buffer
0x18006956a  mov     ecx, ebx; Value
0x18006956c  call    cs:__imp__ltow
0x180069572  xor     eax, eax
0x180069574  lea     rdx, [rsp+290h+Buffer]; unsigned __int16 *
0x180069579  xorps   xmm0, xmm0
0x18006957c  mov     [rsp+290h+var_228], rax
0x180069581  lea     rcx, [rsp+290h+var_238]; this
0x180069586  movups  [rsp+290h+var_238], xmm0
0x18006958b  call    ?InitFromPsz@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromPsz(ushort const *)
0x180069590  mov     rdx, rax; struct SYM *
0x180069593  mov     rcx, rsi; this
0x180069596  call    ?DeleteVval@NameList@@QEAAJPEAUSYM@@H@Z; NameList::DeleteVval(SYM *,int)
0x18006959b  inc     ebx
0x18006959d  cmp     ebx, edi
0x18006959f  jbe     short loc_18006955F
0x1800695a1  mov     rcx, [rbp+190h+var_20]
0x1800695a8  xor     rcx, rsp; StackCookie
0x1800695ab  call    __security_check_cookie
0x1800695b0  mov     rbx, [rsp+290h+arg_10]
0x1800695b8  add     rsp, 280h
0x1800695bf  pop     rdi
0x1800695c0  pop     rsi
0x1800695c1  pop     rbp
0x1800695c2  retn
```
