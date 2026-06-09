# JSONPostParseWalk(CSession *,VAR *,VAR *,VAR *,VAR *,VAR *)

- ea: `0x180069e04`
- end: `0x18006a135`
- name: `?JSONPostParseWalk@@YAJPEAVCSession@@PEAVVAR@@1111@Z`
- size: `817`
- prototype: `int __fastcall(struct CSession *, struct VAR *, struct VAR *, struct VAR *, struct VAR *, struct VAR *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180069e04`
- `0x18006bdb0`

## callees

- `0x1800060b4`
- `0x18000a0c8`
- `0x18000ad40`
- `0x18000ff30`
- `0x180010430`
- `0x180033c30`
- `0x18003efe0`
- `0x180069e04`
- `0x1800767b0`
- `0x180096010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180069f48`
- `OLEAUT32!__imp_SysFreeString` at `0x180069f48`

## pseudocode

```c
int __fastcall JSONPostParseWalk(
        struct CSession *a1,
        struct VAR *a2,
        struct VAR *a3,
        struct VAR *a4,
        struct VAR *a5,
        struct VAR *a6)
{
  struct VAR *v6; // r14
  struct VAR *v7; // r15
  struct VAR *v8; // r13
  int v10; // ebx
  __m128i *v11; // r14
  unsigned int v12; // edx
  unsigned int v13; // edi
  NameTbl *v14; // r13
  __int64 v15; // r15
  int NextOwnIdSym; // eax
  OLECHAR *v17; // rdi
  int v18; // eax
  __int64 v19; // rax
  CIndexedNameList::IndexedEntry *v20; // rbx
  __int64 v21; // rdi
  VAR *v22; // rax
  int result; // eax
  int v24; // [rsp+40h] [rbp-E8h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-E0h] BYREF
  unsigned __int16 *v26[2]; // [rsp+60h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+70h] [rbp-B8h]
  VARIANTARG *p_pvarg; // [rsp+78h] [rbp-B0h] BYREF
  struct CSession *v29; // [rsp+80h] [rbp-A8h]
  __int64 v30; // [rsp+88h] [rbp-A0h]
  __m128i v31; // [rsp+90h] [rbp-98h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-88h]
  __int128 v33; // [rsp+A8h] [rbp-80h] BYREF
  __int64 v34; // [rsp+B8h] [rbp-70h]
  __int128 v35; // [rsp+C0h] [rbp-68h]
  __int64 v36; // [rsp+D0h] [rbp-58h]
  _WORD v37[40]; // [rsp+D8h] [rbp-50h] BYREF

  v6 = a4;
  v7 = a3;
  v8 = a2;
  v10 = 0;
  if ( (unsigned int)VAR::IsJsObj(a5) )
  {
    v31 = *(__m128i *)a5;
    v32 = *((_QWORD *)a5 + 2);
    v11 = &v31;
    v12 = 128;
    if ( (unsigned __int16)_mm_cvtsi128_si32(v31) == 128 )
      v11 = (__m128i *)*((_QWORD *)a5 + 1);
    v13 = -1;
    v24 = -1;
    v14 = (NameTbl *)v11->m128i_i64[1];
    pvarg.vt = 0;
    v29 = a1;
    p_pvarg = &pvarg;
    v30 = *((_QWORD *)a1 + 122);
    *((_QWORD *)a1 + 122) = &p_pvarg;
    v15 = v11->m128i_i64[1];
    *(_OWORD *)v26 = 0;
    v27 = 0;
    while ( 1 )
    {
      NextOwnIdSym = NameTbl::GetNextOwnIdSym(v14, v12, v13, &v24, (struct SYM *)v26);
      v10 = NextOwnIdSym;
      if ( NextOwnIdSym < 0 )
        break;
      if ( NextOwnIdSym > 0 )
      {
        v10 = 0;
        break;
      }
      v17 = _SysAllocStringLen(v26[0], (unsigned int)v26[1]);
      if ( !v17 )
      {
        v10 = -2147024882;
        break;
      }
      pvarg.vt = 8;
      pvarg.llVal = (LONGLONG)v17;
      v10 = VAR::MoveToHeap(&pvarg, a1);
      if ( v10 < 0 )
      {
        SysFreeString(v17);
        break;
      }
      v13 = v24;
      v10 = VAR::InvokeByDispID((VAR *)v11, a1, v24, 2u, (struct VAR *)&v33, 0, 0, 0);
      if ( v10 < 0 )
        break;
      if ( !(unsigned int)FStackAvailable(0x10000u) )
      {
        v10 = -2146828260;
        break;
      }
      v10 = JSONPostParseWalk(a1, (struct VAR *)v37, (struct VAR *)&v31, (struct VAR *)&pvarg, (struct VAR *)&v33, a6);
      if ( v10 >= 0 )
      {
        v18 = v37[0]
            ? VAR::InvokeByDispID((VAR *)v11, a1, v13, 4u, 0, 1, (struct VAR *)v37, 0)
            : (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 80LL))(v15, v13);
        v10 = v18;
        if ( v18 >= 0 )
          continue;
      }
      break;
    }
    v19 = *((_QWORD *)v29 + 122);
    v6 = a4;
    v7 = a3;
    v8 = a2;
    if ( v19 )
      *((_QWORD *)v29 + 122) = *(_QWORD *)(v19 + 16);
  }
  if ( v10 < 0 )
    return v10;
  v20 = (CIndexedNameList::IndexedEntry *)&v33;
  v21 = 2;
  do
  {
    CIndexedNameList::IndexedEntry::IndexedEntry(v20);
    v20 = (CIndexedNameList::IndexedEntry *)((char *)v20 + 24);
    --v21;
  }
  while ( v21 );
  v33 = *(_OWORD *)a5;
  v34 = *((_QWORD *)a5 + 2);
  v35 = *(_OWORD *)v6;
  v36 = *((_QWORD *)v6 + 2);
  v22 = VAR::PvarCutAll(a6);
  result = VAR::InvokeByDispID(v22, a1, 0, 1u, v8, 2, (struct VAR *)&v33, v7);
  v10 = result;
  if ( result >= 0 )
    return v10;
  return result;
}

```

## disassembly

```asm
0x180069e04  mov     [rsp+arg_18], r9
0x180069e09  mov     [rsp+arg_10], r8
0x180069e0e  mov     [rsp+arg_8], rdx
0x180069e13  push    rbx
0x180069e14  push    rsi
0x180069e15  push    rdi
0x180069e16  push    r12
0x180069e18  push    r13
0x180069e1a  push    r14
0x180069e1c  push    r15
0x180069e1e  sub     rsp, 0F0h
0x180069e25  mov     r14, r9
0x180069e28  mov     r15, r8
0x180069e2b  mov     r13, rdx
0x180069e2e  mov     rsi, rcx
0x180069e31  xor     ebx, ebx
0x180069e33  mov     r12, [rsp+128h+arg_20]
0x180069e3b  mov     rcx, r12; this
0x180069e3e  call    ?IsJsObj@VAR@@QEAAHXZ; VAR::IsJsObj(void)
0x180069e43  test    eax, eax
0x180069e45  jz      loc_18006A07D
0x180069e4b  movups  xmm2, xmmword ptr [r12]
0x180069e50  movups  [rsp+128h+var_98], xmm2
0x180069e58  movsd   xmm0, qword ptr [r12+10h]
0x180069e5f  movsd   [rsp+128h+var_88], xmm0
0x180069e68  lea     r14, [rsp+128h+var_98]
0x180069e70  mov     edx, 80h; unsigned int
0x180069e75  movd    eax, xmm2
0x180069e79  cmp     ax, dx
0x180069e7c  cmovz   r14, [r12+8]
0x180069e82  or      edi, 0FFFFFFFFh
0x180069e85  mov     [rsp+128h+var_E8], edi
0x180069e89  mov     r13, [r14+8]
0x180069e8d  xor     eax, eax
0x180069e8f  mov     word ptr [rsp+128h+pvarg], ax
0x180069e94  mov     [rsp+128h+var_A8], rsi
0x180069e9c  lea     rax, [rsp+128h+pvarg]
0x180069ea1  mov     [rsp+128h+var_B0], rax
0x180069ea6  mov     rax, [rsi+3D0h]
0x180069ead  mov     [rsp+128h+var_A0], rax
0x180069eb5  lea     rax, [rsp+128h+var_B0]
0x180069eba  mov     [rsi+3D0h], rax
0x180069ec1  mov     r15, [r14+8]
0x180069ec5  xorps   xmm0, xmm0
0x180069ec8  xor     eax, eax
0x180069eca  movups  xmmword ptr [rsp+128h+var_C8], xmm0
0x180069ecf  mov     [rsp+128h+var_B8], rax
0x180069ed4  lea     rax, [rsp+128h+var_C8]
0x180069ed9  mov     [rsp+128h+var_108], rax; struct SYM *
0x180069ede  lea     r9, [rsp+128h+var_E8]; int *
0x180069ee3  mov     r8d, edi; int
0x180069ee6  mov     rcx, r13; this
0x180069ee9  call    ?GetNextOwnIdSym@NameTbl@@QEAAJKJPEAJPEAUSYM@@@Z; NameTbl::GetNextOwnIdSym(ulong,long,long *,SYM *)
0x180069eee  mov     ebx, eax
0x180069ef0  test    eax, eax
0x180069ef2  js      loc_18006A046
0x180069ef8  jle     short loc_180069F01
0x180069efa  xor     ebx, ebx
0x180069efc  jmp     loc_18006A046
0x180069f01  mov     edx, dword ptr [rsp+128h+var_C8+8]; unsigned int
0x180069f05  mov     rcx, [rsp+128h+var_C8]; unsigned __int16 *
0x180069f0a  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x180069f0f  mov     rdi, rax
0x180069f12  test    rax, rax
0x180069f15  jnz     short loc_180069F21
0x180069f17  mov     ebx, 8007000Eh
0x180069f1c  jmp     loc_18006A046
0x180069f21  mov     eax, 8
0x180069f26  mov     word ptr [rsp+128h+pvarg], ax
0x180069f2b  mov     qword ptr [rsp+128h+pvarg+8], rdi
0x180069f30  mov     rdx, rsi; this
0x180069f33  lea     rcx, [rsp+128h+pvarg]; pvarg
0x180069f38  call    ?MoveToHeap@VAR@@QEAAJPEAVCSession@@@Z; VAR::MoveToHeap(CSession *)
0x180069f3d  mov     ebx, eax
0x180069f3f  xor     eax, eax
0x180069f41  test    ebx, ebx
0x180069f43  jns     short loc_180069F53
0x180069f45  mov     rcx, rdi; bstrString
0x180069f48  call    cs:__imp_SysFreeString
0x180069f4e  jmp     loc_18006A046
0x180069f53  mov     [rsp+128h+var_F0], rax; struct VAR *
0x180069f58  mov     [rsp+128h+var_F8], rax; struct VAR *
0x180069f5d  mov     dword ptr [rsp+128h+var_100], eax; int
0x180069f61  lea     rax, [rsp+128h+var_80]
0x180069f69  mov     [rsp+128h+var_108], rax; struct VAR *
0x180069f6e  mov     r9d, 2; unsigned int
0x180069f74  mov     edi, [rsp+128h+var_E8]
0x180069f78  mov     r8d, edi; int
0x180069f7b  mov     rdx, rsi; struct CSession *
0x180069f7e  mov     rcx, r14; this
0x180069f81  call    ?InvokeByDispID@VAR@@QEAAJPEAVCSession@@JKPEAV1@H11@Z; VAR::InvokeByDispID(CSession *,long,ulong,VAR *,int,VAR *,VAR *)
0x180069f86  mov     ebx, eax
0x180069f88  test    eax, eax
0x180069f8a  js      loc_18006A046
0x180069f90  mov     ecx, 10000h; unsigned int
0x180069f95  call    ?FStackAvailable@@YAHI@Z; FStackAvailable(uint)
0x180069f9a  test    eax, eax
0x180069f9c  jnz     short loc_180069FA8
0x180069f9e  mov     ebx, 800A001Ch
0x180069fa3  jmp     loc_18006A046
0x180069fa8  mov     rax, [rsp+128h+arg_28]
0x180069fb0  mov     [rsp+128h+var_100], rax; struct VAR *
0x180069fb5  lea     rax, [rsp+128h+var_80]
0x180069fbd  mov     [rsp+128h+var_108], rax; struct VAR *
0x180069fc2  lea     r9, [rsp+128h+pvarg]; struct VAR *
0x180069fc7  lea     r8, [rsp+128h+var_98]; struct VAR *
0x180069fcf  lea     rdx, [rsp+128h+var_50]; struct VAR *
0x180069fd7  mov     rcx, rsi; struct CSession *
0x180069fda  call    ?JSONPostParseWalk@@YAJPEAVCSession@@PEAVVAR@@1111@Z; JSONPostParseWalk(CSession *,VAR *,VAR *,VAR *,VAR *,VAR *)
0x180069fdf  mov     ebx, eax
0x180069fe1  test    eax, eax
0x180069fe3  js      short loc_18006A046
0x180069fe5  xor     eax, eax
0x180069fe7  cmp     ax, [rsp+128h+var_50]
0x180069fef  jnz     short loc_18006A004
0x180069ff1  mov     rax, [r15]
0x180069ff4  mov     edx, edi
0x180069ff6  mov     rcx, r15
0x180069ff9  mov     rax, [rax+50h]
0x180069ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a002  jmp     short loc_18006A03B
0x18006a004  mov     [rsp+128h+var_F0], rax; struct VAR *
0x18006a009  lea     rax, [rsp+128h+var_50]
0x18006a011  mov     [rsp+128h+var_F8], rax; struct VAR *
0x18006a016  mov     dword ptr [rsp+128h+var_100], 1; int
0x18006a01e  mov     [rsp+128h+var_108], 0; struct VAR *
0x18006a027  mov     r9d, 4; unsigned int
0x18006a02d  mov     r8d, edi; int
0x18006a030  mov     rdx, rsi; struct CSession *
0x18006a033  mov     rcx, r14; this
0x18006a036  call    ?InvokeByDispID@VAR@@QEAAJPEAVCSession@@JKPEAV1@H11@Z; VAR::InvokeByDispID(CSession *,long,ulong,VAR *,int,VAR *,VAR *)
0x18006a03b  test    eax, eax
0x18006a03d  mov     ebx, eax
0x18006a03f  js      short loc_18006A046
0x18006a041  jmp     loc_180069ED4
0x18006a046  mov     rcx, [rsp+128h+var_A8]
0x18006a04e  mov     rax, [rcx+3D0h]
0x18006a055  mov     r14, [rsp+128h+arg_18]
0x18006a05d  mov     r15, [rsp+128h+arg_10]
0x18006a065  mov     r13, [rsp+128h+arg_8]
0x18006a06d  test    rax, rax
0x18006a070  jz      short loc_18006A07D
0x18006a072  mov     rax, [rax+10h]
0x18006a076  mov     [rcx+3D0h], rax
0x18006a07d  test    ebx, ebx
0x18006a07f  js      loc_18006A120
0x18006a085  lea     rbx, [rsp+128h+var_80]
0x18006a08d  mov     edi, 2
0x18006a092  mov     rcx, rbx; this
0x18006a095  call    ??0IndexedEntry@CIndexedNameList@@QEAA@XZ; CIndexedNameList::IndexedEntry::IndexedEntry(void)
0x18006a09a  add     rbx, 18h
0x18006a09e  sub     rdi, 1
0x18006a0a2  jnz     short loc_18006A092
0x18006a0a4  movups  xmm0, xmmword ptr [r12]
0x18006a0a9  movups  [rsp+128h+var_80], xmm0
0x18006a0b1  movsd   xmm1, qword ptr [r12+10h]
0x18006a0b8  movsd   [rsp+128h+var_70], xmm1
0x18006a0c1  movups  xmm0, xmmword ptr [r14]
0x18006a0c5  movups  [rsp+128h+var_68], xmm0
0x18006a0cd  movsd   xmm1, qword ptr [r14+10h]
0x18006a0d3  movsd   [rsp+128h+var_58], xmm1
0x18006a0dc  mov     rcx, [rsp+128h+arg_28]; this
0x18006a0e4  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x18006a0e9  mov     [rsp+128h+var_F0], r15; struct VAR *
0x18006a0ee  lea     rcx, [rsp+128h+var_80]
0x18006a0f6  mov     [rsp+128h+var_F8], rcx; struct VAR *
0x18006a0fb  mov     dword ptr [rsp+128h+var_100], 2; int
0x18006a103  mov     [rsp+128h+var_108], r13; struct VAR *
0x18006a108  lea     r9d, [rdi+1]; unsigned int
0x18006a10c  xor     r8d, r8d; int
0x18006a10f  mov     rdx, rsi; struct CSession *
0x18006a112  mov     rcx, rax; this
0x18006a115  call    ?InvokeByDispID@VAR@@QEAAJPEAVCSession@@JKPEAV1@H11@Z; VAR::InvokeByDispID(CSession *,long,ulong,VAR *,int,VAR *,VAR *)
0x18006a11a  mov     ebx, eax
0x18006a11c  test    eax, eax
0x18006a11e  js      short loc_18006A122
0x18006a120  mov     eax, ebx
0x18006a122  add     rsp, 0F0h
0x18006a129  pop     r15
0x18006a12b  pop     r14
0x18006a12d  pop     r13
0x18006a12f  pop     r12
0x18006a131  pop     rdi
0x18006a132  pop     rsi
0x18006a133  pop     rbx
0x18006a134  retn
0x180094a0c  push    rbp
0x180094a0e  sub     rsp, 40h
0x180094a12  mov     rbp, rdx
0x180094a15  add     rsp, 40h
0x180094a19  pop     rbp
0x180094a1a  retn
```
