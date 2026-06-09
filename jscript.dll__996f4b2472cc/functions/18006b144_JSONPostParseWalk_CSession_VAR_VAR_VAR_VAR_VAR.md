# JSONPostParseWalk(CSession *,VAR *,VAR *,VAR *,VAR *,VAR *)

- ea: `0x18006b144`
- end: `0x18006b472`
- name: `?JSONPostParseWalk@@YAJPEAVCSession@@PEAVVAR@@1111@Z`
- size: `814`
- prototype: `__int64 __usercall@<rax>(struct CSession *@<rcx>, struct VAR *@<rdx>, struct VAR *@<r8>, struct VAR *@<r9>, struct VAR *, struct VAR *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18006b144`
- `0x18006d0e0`

## callees

- `0x180005070`
- `0x180006e54`
- `0x1800076e0`
- `0x180007e68`
- `0x18000d190`
- `0x18000d6a0`
- `0x18002d9d0`
- `0x180033c3c`
- `0x18006b144`
- `0x180077cf4`
- `0x180098010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006b27e`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b27e`

## pseudocode

```c
int __fastcall JSONPostParseWalk(
        struct CSession *a1,
        VARIANTARG *a2,
        struct VAR *a3,
        struct VAR *a4,
        struct VAR *a5,
        struct VAR *a6)
{
  struct VAR *v6; // r14
  struct VAR *v7; // r15
  VARIANTARG *v8; // r13
  int v10; // ebx
  unsigned int v11; // edx
  struct VAR *v12; // r14
  unsigned int v13; // edi
  NameTbl *v14; // r13
  __int64 v15; // r15
  int NextOwnIdSym; // eax
  OLECHAR *v17; // rdi
  int v18; // eax
  __int64 v19; // rax
  VARIANTARG *v20; // rbx
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
  __int128 v31; // [rsp+90h] [rbp-98h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-88h]
  VARIANTARG v33; // [rsp+A8h] [rbp-80h] BYREF
  __int128 v34; // [rsp+C0h] [rbp-68h]
  __int64 v35; // [rsp+D0h] [rbp-58h]
  VARIANTARG v36; // [rsp+D8h] [rbp-50h] BYREF

  v6 = a4;
  v7 = a3;
  v8 = a2;
  v10 = 0;
  if ( (unsigned int)VAR::IsJsObj(a5) )
  {
    v31 = *(_OWORD *)a5;
    v32 = *((_QWORD *)a5 + 2);
    v12 = VAR::PvarCutHeap((VAR *)&v31);
    v13 = -1;
    v24 = -1;
    v14 = (NameTbl *)*((_QWORD *)v12 + 1);
    pvarg.vt = 0;
    v29 = a1;
    p_pvarg = &pvarg;
    v30 = *((_QWORD *)a1 + 122);
    *((_QWORD *)a1 + 122) = &p_pvarg;
    v15 = *((_QWORD *)v12 + 1);
    *(_OWORD *)v26 = 0;
    v27 = 0;
    while ( 1 )
    {
      NextOwnIdSym = NameTbl::GetNextOwnIdSym(v14, v11, v13, &v24, (struct SYM *)v26);
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
      v10 = VAR::InvokeByDispID(v12, a1, v24, 2u, &v33, 0, 0, 0);
      if ( v10 < 0 )
        break;
      if ( !(unsigned int)FStackAvailable(0x10000u) )
      {
        v10 = -2146828260;
        break;
      }
      v10 = JSONPostParseWalk(a1, (struct VAR *)&v36, (struct VAR *)&v31, (struct VAR *)&pvarg, (struct VAR *)&v33, a6);
      if ( v10 >= 0 )
      {
        v18 = v36.vt
            ? VAR::InvokeByDispID(v12, a1, v13, 4u, 0, 1, (struct VAR *)&v36, 0)
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
  v20 = &v33;
  v21 = 2;
  do
  {
    CIndexedNameList::IndexedEntry::IndexedEntry((CIndexedNameList::IndexedEntry *)v20++);
    --v21;
  }
  while ( v21 );
  *(_OWORD *)&v33.vt = *(_OWORD *)a5;
  v33.pRecInfo = (IRecordInfo *)*((_QWORD *)a5 + 2);
  v34 = *(_OWORD *)v6;
  v35 = *((_QWORD *)v6 + 2);
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
0x18006b144  mov     [rsp+arg_18], r9
0x18006b149  mov     [rsp+arg_10], r8
0x18006b14e  mov     [rsp+arg_8], rdx
0x18006b153  push    rbx
0x18006b154  push    rsi
0x18006b155  push    rdi
0x18006b156  push    r12
0x18006b158  push    r13
0x18006b15a  push    r14
0x18006b15c  push    r15
0x18006b15e  sub     rsp, 0F0h
0x18006b165  mov     r14, r9
0x18006b168  mov     r15, r8
0x18006b16b  mov     r13, rdx
0x18006b16e  mov     rsi, rcx
0x18006b171  xor     ebx, ebx
0x18006b173  mov     r12, [rsp+128h+arg_20]
0x18006b17b  mov     rcx, r12; this
0x18006b17e  call    ?IsJsObj@VAR@@QEAAHXZ; VAR::IsJsObj(void)
0x18006b183  test    eax, eax
0x18006b185  jz      loc_18006B3B9
0x18006b18b  movups  xmm0, xmmword ptr [r12]
0x18006b190  movups  [rsp+128h+var_98], xmm0
0x18006b198  movsd   xmm1, qword ptr [r12+10h]
0x18006b19f  movsd   [rsp+128h+var_88], xmm1
0x18006b1a8  lea     rcx, [rsp+128h+var_98]; this
0x18006b1b0  call    ?PvarCutHeap@VAR@@QEAAPEAV1@XZ; VAR::PvarCutHeap(void)
0x18006b1b5  mov     r14, rax
0x18006b1b8  or      edi, 0FFFFFFFFh
0x18006b1bb  mov     [rsp+128h+var_E8], edi
0x18006b1bf  mov     r13, [rax+8]
0x18006b1c3  xor     ecx, ecx
0x18006b1c5  mov     word ptr [rsp+128h+pvarg], cx
0x18006b1ca  mov     [rsp+128h+var_A8], rsi
0x18006b1d2  lea     rax, [rsp+128h+pvarg]
0x18006b1d7  mov     [rsp+128h+var_B0], rax
0x18006b1dc  mov     rcx, [rsi+3D0h]
0x18006b1e3  mov     [rsp+128h+var_A0], rcx
0x18006b1eb  lea     rax, [rsp+128h+var_B0]
0x18006b1f0  mov     [rsi+3D0h], rax
0x18006b1f7  mov     r15, [r14+8]
0x18006b1fb  xorps   xmm0, xmm0
0x18006b1fe  xor     eax, eax
0x18006b200  movups  xmmword ptr [rsp+128h+var_C8], xmm0
0x18006b205  mov     [rsp+128h+var_B8], rax
0x18006b20a  lea     rax, [rsp+128h+var_C8]
0x18006b20f  mov     [rsp+128h+var_108], rax; struct SYM *
0x18006b214  lea     r9, [rsp+128h+var_E8]; int *
0x18006b219  mov     r8d, edi; int
0x18006b21c  mov     rcx, r13; this
0x18006b21f  call    ?GetNextOwnIdSym@NameTbl@@QEAAJKJPEAJPEAUSYM@@@Z; NameTbl::GetNextOwnIdSym(ulong,long,long *,SYM *)
0x18006b224  mov     ebx, eax
0x18006b226  test    eax, eax
0x18006b228  js      loc_18006B382
0x18006b22e  jle     short loc_18006B237
0x18006b230  xor     ebx, ebx
0x18006b232  jmp     loc_18006B382
0x18006b237  mov     edx, dword ptr [rsp+128h+var_C8+8]; unsigned int
0x18006b23b  mov     rcx, [rsp+128h+var_C8]; unsigned __int16 *
0x18006b240  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x18006b245  mov     rdi, rax
0x18006b248  test    rax, rax
0x18006b24b  jnz     short loc_18006B257
0x18006b24d  mov     ebx, 8007000Eh
0x18006b252  jmp     loc_18006B382
0x18006b257  mov     eax, 8
0x18006b25c  mov     word ptr [rsp+128h+pvarg], ax
0x18006b261  mov     qword ptr [rsp+128h+pvarg+8], rdi
0x18006b266  mov     rdx, rsi; this
0x18006b269  lea     rcx, [rsp+128h+pvarg]; pvarg
0x18006b26e  call    ?MoveToHeap@VAR@@QEAAJPEAVCSession@@@Z; VAR::MoveToHeap(CSession *)
0x18006b273  mov     ebx, eax
0x18006b275  xor     eax, eax
0x18006b277  test    ebx, ebx
0x18006b279  jns     short loc_18006B28F
0x18006b27b  mov     rcx, rdi; bstrString
0x18006b27e  call    cs:__imp_SysFreeString
0x18006b285  nop     dword ptr [rax+rax+00h]
0x18006b28a  jmp     loc_18006B382
0x18006b28f  mov     [rsp+128h+var_F0], rax; struct VAR *
0x18006b294  mov     [rsp+128h+var_F8], rax; struct VAR *
0x18006b299  mov     dword ptr [rsp+128h+var_100], eax; int
0x18006b29d  lea     rax, [rsp+128h+var_80]
0x18006b2a5  mov     [rsp+128h+var_108], rax; pvarg
0x18006b2aa  mov     r9d, 2; unsigned int
0x18006b2b0  mov     edi, [rsp+128h+var_E8]
0x18006b2b4  mov     r8d, edi; int
0x18006b2b7  mov     rdx, rsi; struct CSession *
0x18006b2ba  mov     rcx, r14; this
0x18006b2bd  call    ?InvokeByDispID@VAR@@QEAAJPEAVCSession@@JKPEAV1@H11@Z; VAR::InvokeByDispID(CSession *,long,ulong,VAR *,int,VAR *,VAR *)
0x18006b2c2  mov     ebx, eax
0x18006b2c4  test    eax, eax
0x18006b2c6  js      loc_18006B382
0x18006b2cc  mov     ecx, 10000h; unsigned int
0x18006b2d1  call    ?FStackAvailable@@YAHI@Z; FStackAvailable(uint)
0x18006b2d6  test    eax, eax
0x18006b2d8  jnz     short loc_18006B2E4
0x18006b2da  mov     ebx, 800A001Ch
0x18006b2df  jmp     loc_18006B382
0x18006b2e4  mov     rax, [rsp+128h+arg_28]
0x18006b2ec  mov     [rsp+128h+var_100], rax; struct VAR *
0x18006b2f1  lea     rax, [rsp+128h+var_80]
0x18006b2f9  mov     [rsp+128h+var_108], rax; struct VAR *
0x18006b2fe  lea     r9, [rsp+128h+pvarg]; struct VAR *
0x18006b303  lea     r8, [rsp+128h+var_98]; struct VAR *
0x18006b30b  lea     rdx, [rsp+128h+var_50]; struct VAR *
0x18006b313  mov     rcx, rsi; struct CSession *
0x18006b316  call    ?JSONPostParseWalk@@YAJPEAVCSession@@PEAVVAR@@1111@Z; JSONPostParseWalk(CSession *,VAR *,VAR *,VAR *,VAR *,VAR *)
0x18006b31b  mov     ebx, eax
0x18006b31d  test    eax, eax
0x18006b31f  js      short loc_18006B382
0x18006b321  xor     eax, eax
0x18006b323  cmp     ax, word ptr [rsp+128h+var_50]
0x18006b32b  jnz     short loc_18006B340
0x18006b32d  mov     rax, [r15]
0x18006b330  mov     edx, edi
0x18006b332  mov     rcx, r15
0x18006b335  mov     rax, [rax+50h]
0x18006b339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b33e  jmp     short loc_18006B377
0x18006b340  mov     [rsp+128h+var_F0], rax; struct VAR *
0x18006b345  lea     rax, [rsp+128h+var_50]
0x18006b34d  mov     [rsp+128h+var_F8], rax; struct VAR *
0x18006b352  mov     dword ptr [rsp+128h+var_100], 1; int
0x18006b35a  mov     [rsp+128h+var_108], 0; pvarg
0x18006b363  mov     r9d, 4; unsigned int
0x18006b369  mov     r8d, edi; int
0x18006b36c  mov     rdx, rsi; struct CSession *
0x18006b36f  mov     rcx, r14; this
0x18006b372  call    ?InvokeByDispID@VAR@@QEAAJPEAVCSession@@JKPEAV1@H11@Z; VAR::InvokeByDispID(CSession *,long,ulong,VAR *,int,VAR *,VAR *)
0x18006b377  test    eax, eax
0x18006b379  mov     ebx, eax
0x18006b37b  js      short loc_18006B382
0x18006b37d  jmp     loc_18006B20A
0x18006b382  mov     rcx, [rsp+128h+var_A8]
0x18006b38a  mov     rax, [rcx+3D0h]
0x18006b391  mov     r14, [rsp+128h+arg_18]
0x18006b399  mov     r15, [rsp+128h+arg_10]
0x18006b3a1  mov     r13, [rsp+128h+arg_8]
0x18006b3a9  test    rax, rax
0x18006b3ac  jz      short loc_18006B3B9
0x18006b3ae  mov     rax, [rax+10h]
0x18006b3b2  mov     [rcx+3D0h], rax
0x18006b3b9  test    ebx, ebx
0x18006b3bb  js      loc_18006B45C
0x18006b3c1  lea     rbx, [rsp+128h+var_80]
0x18006b3c9  mov     edi, 2
0x18006b3ce  mov     rcx, rbx; this
0x18006b3d1  call    ??0IndexedEntry@CIndexedNameList@@QEAA@XZ; CIndexedNameList::IndexedEntry::IndexedEntry(void)
0x18006b3d6  add     rbx, 18h
0x18006b3da  sub     rdi, 1
0x18006b3de  jnz     short loc_18006B3CE
0x18006b3e0  movups  xmm0, xmmword ptr [r12]
0x18006b3e5  movups  xmmword ptr [rsp+128h+var_80], xmm0
0x18006b3ed  movsd   xmm1, qword ptr [r12+10h]
0x18006b3f4  movsd   qword ptr [rsp+128h+var_80+10h], xmm1
0x18006b3fd  movups  xmm0, xmmword ptr [r14]
0x18006b401  movups  [rsp+128h+var_68], xmm0
0x18006b409  movsd   xmm1, qword ptr [r14+10h]
0x18006b40f  movsd   [rsp+128h+var_58], xmm1
0x18006b418  mov     rcx, [rsp+128h+arg_28]; this
0x18006b420  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x18006b425  mov     [rsp+128h+var_F0], r15; struct VAR *
0x18006b42a  lea     rcx, [rsp+128h+var_80]
0x18006b432  mov     [rsp+128h+var_F8], rcx; struct VAR *
0x18006b437  mov     dword ptr [rsp+128h+var_100], 2; int
0x18006b43f  mov     [rsp+128h+var_108], r13; pvarg
0x18006b444  lea     r9d, [rdi+1]; unsigned int
0x18006b448  xor     r8d, r8d; int
0x18006b44b  mov     rdx, rsi; struct CSession *
0x18006b44e  mov     rcx, rax; this
0x18006b451  call    ?InvokeByDispID@VAR@@QEAAJPEAVCSession@@JKPEAV1@H11@Z; VAR::InvokeByDispID(CSession *,long,ulong,VAR *,int,VAR *,VAR *)
0x18006b456  mov     ebx, eax
0x18006b458  test    eax, eax
0x18006b45a  js      short loc_18006B45E
0x18006b45c  mov     eax, ebx
0x18006b45e  add     rsp, 0F0h
0x18006b465  pop     r15
0x18006b467  pop     r14
0x18006b469  pop     r13
0x18006b46b  pop     r12
0x18006b46d  pop     rdi
0x18006b46e  pop     rsi
0x18006b46f  pop     rbx
0x18006b470  retn
0x180096e21  push    rbp
0x180096e23  sub     rsp, 40h
0x180096e27  mov     rbp, rdx
0x180096e2a  add     rsp, 40h
0x180096e2e  pop     rbp
0x180096e2f  retn
```
