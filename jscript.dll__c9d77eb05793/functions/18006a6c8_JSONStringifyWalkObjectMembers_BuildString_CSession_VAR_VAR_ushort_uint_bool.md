# JSONStringifyWalkObjectMembers(BuildString &,CSession *,VAR *,VAR *,ushort *,uint &,bool &)

- ea: `0x18006a6c8`
- end: `0x18006a9b3`
- name: `?JSONStringifyWalkObjectMembers@@YAJAEAVBuildString@@PEAVCSession@@PEAVVAR@@2PEAGAEAIAEA_N@Z`
- size: `747`
- prototype: `__int64 __fastcall(struct BuildString *, struct CSession *, struct VAR *, struct VAR *, unsigned __int16 *, unsigned int *, struct NameTbl *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18006a304`

## callees

- `0x18000ad40`
- `0x18000ff30`
- `0x180033c30`
- `0x180038180`
- `0x18006a13c`
- `0x18006a47c`
- `0x18006a6c8`
- `0x1800767b0`
- `0x180096010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006a8e5`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a987`
- `OLEAUT32!__imp_SysFreeString` at `0x180094fc7`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a8e5`
- `OLEAUT32!__imp_SysFreeString` at `0x18006a987`
- `OLEAUT32!__imp_SysFreeString` at `0x180094fc7`

## pseudocode

```c
__int64 __fastcall JSONStringifyWalkObjectMembers(
        struct BuildString *a1,
        struct CSession *a2,
        struct VAR *a3,
        struct VAR *a4,
        unsigned __int16 *a5,
        unsigned int *a6,
        struct NameTbl *a7)
{
  __m128i *v11; // rdi
  VAR *v12; // r9
  bool *v13; // r15
  __m128i *v15; // rdx
  unsigned __int64 v16; // xmm1_8
  NameTbl *v17; // rcx
  int v18; // r13d
  OLECHAR *v19; // rdi
  int NextOwnIdSym; // eax
  int v21; // ebx
  int v22; // eax
  unsigned __int16 *v23; // rax
  __int64 v24; // rax
  VAR *v25; // [rsp+58h] [rbp-B0h]
  NameTbl *v26; // [rsp+60h] [rbp-A8h]
  unsigned __int16 *v27[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+78h] [rbp-90h]
  __int16 *v29; // [rsp+80h] [rbp-88h] BYREF
  struct CSession *v30; // [rsp+88h] [rbp-80h]
  __int64 v31; // [rsp+90h] [rbp-78h]
  __int16 v32; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int16 *v33; // [rsp+A0h] [rbp-68h]
  __m128i v34; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v35; // [rsp+C0h] [rbp-48h]
  _BYTE v36[24]; // [rsp+C8h] [rbp-40h] BYREF
  int v38; // [rsp+128h] [rbp+20h] BYREF

  v11 = (__m128i *)VAR::PvarCutAll(a3);
  v13 = (bool *)a7;
  *(_BYTE *)a7 = 1;
  a7 = 0;
  if ( v12
    && (unsigned int)VAR::IsJsObj(v12, &a7)
    && (*(unsigned int (__fastcall **)(struct NameTbl *))(*(_QWORD *)a7 + 240LL))(a7) )
  {
    return JSONStringifyObjectMembersByArrayReplacer(a1, a2, a3, a4, a5, a6, v13);
  }
  v34 = *v11;
  v35 = v11[1].m128i_i64[0];
  v15 = &v34;
  v16 = _mm_srli_si128(v34, 8).m128i_u64[0];
  if ( (unsigned __int16)_mm_cvtsi128_si32(v34) == 128 )
    v15 = (__m128i *)v16;
  v25 = (VAR *)v15;
  v17 = (NameTbl *)v15->m128i_i64[1];
  v26 = v17;
  v18 = -1;
  v38 = -1;
  v19 = 0;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  v32 = 8;
  v30 = a2;
  v29 = &v32;
  v31 = *((_QWORD *)a2 + 122);
  *((_QWORD *)a2 + 122) = &v29;
  LOBYTE(a7) = 1;
  while ( 1 )
  {
    NextOwnIdSym = NameTbl::GetNextOwnIdSym(v17, (unsigned int)v15, v18, &v38, (struct SYM *)v27);
    v21 = NextOwnIdSym;
    if ( NextOwnIdSym < 0 )
      break;
    if ( NextOwnIdSym > 0 )
    {
      v21 = 0;
      *v13 = (char)a7;
      break;
    }
    v18 = v38;
    v22 = VAR::InvokeByDispID(v25, a2, v38, 2u, (struct VAR *)v36, 0, 0, 0);
    v21 = v22;
    if ( v22 < 0 )
      break;
    if ( !v22 )
    {
      if ( v19 )
        SysFreeString(v19);
      v23 = _SysAllocStringLen(v27[0], (unsigned int)v27[1]);
      v19 = v23;
      if ( !v23 )
      {
        v21 = -2147024882;
        break;
      }
      v33 = v23;
      v21 = JSONStringifyObjectMember(a1, a2, (struct VAR *)&v32, (struct VAR *)v36, a4, a5, a6, (bool *)&a7, a3);
      if ( v21 < 0 )
        break;
    }
    v17 = v26;
  }
  if ( v19 )
    SysFreeString(v19);
  v24 = *((_QWORD *)v30 + 122);
  if ( v24 )
    *((_QWORD *)v30 + 122) = *(_QWORD *)(v24 + 16);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18006a6c8  mov     [rsp+arg_8], rbx
0x18006a6cd  mov     [rsp+arg_10], rsi
0x18006a6d2  mov     [rsp+arg_0], rcx
0x18006a6d7  push    rdi
0x18006a6d8  push    r12
0x18006a6da  push    r13
0x18006a6dc  push    r14
0x18006a6de  push    r15
0x18006a6e0  sub     rsp, 0E0h
0x18006a6e7  mov     rsi, r9
0x18006a6ea  mov     r12, r8
0x18006a6ed  mov     r14, rdx
0x18006a6f0  mov     rbx, rcx
0x18006a6f3  mov     rcx, r8; this
0x18006a6f6  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x18006a6fb  mov     rdi, rax
0x18006a6fe  mov     r15, [rsp+108h+arg_30]
0x18006a706  mov     byte ptr [r15], 1
0x18006a70a  mov     [rsp+108h+arg_30], 0
0x18006a716  test    r9, r9
0x18006a719  jz      short loc_18006A797
0x18006a71b  lea     rdx, [rsp+108h+arg_30]; struct NameTbl **
0x18006a723  mov     rcx, r9; this
0x18006a726  call    ?IsJsObj@VAR@@QEAAHPEAPEAVNameTbl@@@Z; VAR::IsJsObj(NameTbl * *)
0x18006a72b  test    eax, eax
0x18006a72d  jz      short loc_18006A797
0x18006a72f  mov     rcx, [rsp+108h+arg_30]
0x18006a737  mov     rax, [rcx]
0x18006a73a  mov     rax, [rax+0F0h]
0x18006a741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a746  test    eax, eax
0x18006a748  jz      short loc_18006A797
0x18006a74a  mov     [rsp+108h+var_D8], r15; bool *
0x18006a74f  mov     rax, [rsp+108h+arg_28]
0x18006a757  mov     [rsp+108h+var_E0], rax; unsigned int *
0x18006a75c  mov     rax, [rsp+108h+arg_20]
0x18006a764  mov     [rsp+108h+var_E8], rax; unsigned __int16 *
0x18006a769  mov     r9, rsi; struct VAR *
0x18006a76c  mov     r8, r12; struct VAR *
0x18006a76f  mov     rdx, r14; struct CSession *
0x18006a772  mov     rcx, rbx; struct BuildString *
0x18006a775  call    ?JSONStringifyObjectMembersByArrayReplacer@@YAJAEAVBuildString@@PEAVCSession@@PEAVVAR@@2PEAGAEAIAEA_N@Z; JSONStringifyObjectMembersByArrayReplacer(BuildString &,CSession *,VAR *,VAR *,ushort *,uint &,bool &)
0x18006a77a  lea     r11, [rsp+108h+var_28]
0x18006a782  mov     rbx, [r11+38h]
0x18006a786  mov     rsi, [r11+40h]
0x18006a78a  mov     rsp, r11
0x18006a78d  pop     r15
0x18006a78f  pop     r14
0x18006a791  pop     r13
0x18006a793  pop     r12
0x18006a795  pop     rdi
0x18006a796  retn
0x18006a797  movups  xmm2, xmmword ptr [rdi]
0x18006a79a  movups  [rsp+108h+var_58], xmm2
0x18006a7a2  movsd   xmm0, qword ptr [rdi+10h]
0x18006a7a7  movsd   [rsp+108h+var_48], xmm0
0x18006a7b0  lea     rdx, [rsp+108h+var_58]
0x18006a7b8  movdqa  xmm1, xmm2
0x18006a7bc  psrldq  xmm1, 8
0x18006a7c1  movq    rcx, xmm1
0x18006a7c6  mov     r8d, 80h
0x18006a7cc  movd    eax, xmm2
0x18006a7d0  cmp     ax, r8w
0x18006a7d4  cmovz   rdx, rcx; unsigned int
0x18006a7d8  mov     [rsp+108h+var_B0], rdx
0x18006a7dd  mov     rcx, [rdx+8]; this
0x18006a7e1  mov     [rsp+108h+var_A8], rcx
0x18006a7e6  or      r13d, 0FFFFFFFFh
0x18006a7ea  mov     [rsp+108h+arg_18], r13d
0x18006a7f2  xor     edi, edi
0x18006a7f4  mov     [rsp+108h+var_B8], rdi
0x18006a7f9  xorps   xmm0, xmm0
0x18006a7fc  xor     eax, eax
0x18006a7fe  movups  xmmword ptr [rsp+108h+var_A0], xmm0
0x18006a803  mov     [rsp+108h+var_90], rax
0x18006a808  lea     eax, [rdi+8]
0x18006a80b  mov     [rsp+108h+var_70], ax
0x18006a813  mov     [rsp+108h+var_80], r14
0x18006a81b  lea     rax, [rsp+108h+var_70]
0x18006a823  mov     [rsp+108h+var_88], rax
0x18006a82b  mov     rax, [r14+3D0h]
0x18006a832  mov     [rsp+108h+var_78], rax
0x18006a83a  lea     rax, [rsp+108h+var_88]
0x18006a842  mov     [r14+3D0h], rax
0x18006a849  mov     byte ptr [rsp+108h+arg_30], 1
0x18006a851  lea     rax, [rsp+108h+var_A0]
0x18006a856  mov     [rsp+108h+var_E8], rax; struct SYM *
0x18006a85b  lea     r9, [rsp+108h+arg_18]; int *
0x18006a863  mov     r8d, r13d; int
0x18006a866  call    ?GetNextOwnIdSym@NameTbl@@QEAAJKJPEAJPEAUSYM@@@Z; NameTbl::GetNextOwnIdSym(ulong,long,long *,SYM *)
0x18006a86b  mov     ebx, eax
0x18006a86d  test    eax, eax
0x18006a86f  js      loc_18006A97F
0x18006a875  jle     short loc_18006A888
0x18006a877  xor     ebx, ebx
0x18006a879  mov     al, byte ptr [rsp+108h+arg_30]
0x18006a880  mov     [r15], al
0x18006a883  jmp     loc_18006A97F
0x18006a888  mov     [rsp+108h+var_D0], 0; struct VAR *
0x18006a891  mov     [rsp+108h+var_D8], 0; struct VAR *
0x18006a89a  mov     dword ptr [rsp+108h+var_E0], 0; int
0x18006a8a2  lea     rax, [rsp+108h+var_40]
0x18006a8aa  mov     [rsp+108h+var_E8], rax; struct VAR *
0x18006a8af  mov     r9d, 2; unsigned int
0x18006a8b5  mov     r13d, [rsp+108h+arg_18]
0x18006a8bd  mov     r8d, r13d; int
0x18006a8c0  mov     rdx, r14; struct CSession *
0x18006a8c3  mov     rcx, [rsp+108h+var_B0]; this
0x18006a8c8  call    ?InvokeByDispID@VAR@@QEAAJPEAVCSession@@JKPEAV1@H11@Z; VAR::InvokeByDispID(CSession *,long,ulong,VAR *,int,VAR *,VAR *)
0x18006a8cd  mov     ebx, eax
0x18006a8cf  test    eax, eax
0x18006a8d1  js      loc_18006A97F
0x18006a8d7  jnz     loc_18006A975
0x18006a8dd  test    rdi, rdi
0x18006a8e0  jz      short loc_18006A8F4
0x18006a8e2  mov     rcx, rdi; bstrString
0x18006a8e5  call    cs:__imp_SysFreeString
0x18006a8eb  mov     [rsp+108h+var_B8], 0
0x18006a8f4  mov     edx, dword ptr [rsp+108h+var_A0+8]; unsigned int
0x18006a8f8  mov     rcx, [rsp+108h+var_A0]; unsigned __int16 *
0x18006a8fd  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x18006a902  mov     rdi, rax
0x18006a905  mov     [rsp+108h+var_B8], rax
0x18006a90a  test    rax, rax
0x18006a90d  jnz     short loc_18006A916
0x18006a90f  mov     ebx, 8007000Eh
0x18006a914  jmp     short loc_18006A97F
0x18006a916  mov     [rsp+108h+var_68], rax
0x18006a91e  mov     [rsp+108h+var_C8], r12; struct VAR *
0x18006a923  lea     rax, [rsp+108h+arg_30]
0x18006a92b  mov     [rsp+108h+var_D0], rax; bool *
0x18006a930  mov     rax, [rsp+108h+arg_28]
0x18006a938  mov     [rsp+108h+var_D8], rax; unsigned int *
0x18006a93d  mov     rax, [rsp+108h+arg_20]
0x18006a945  mov     [rsp+108h+var_E0], rax; unsigned __int16 *
0x18006a94a  mov     [rsp+108h+var_E8], rsi; struct VAR *
0x18006a94f  lea     r9, [rsp+108h+var_40]; struct VAR *
0x18006a957  lea     r8, [rsp+108h+var_70]; struct VAR *
0x18006a95f  mov     rdx, r14; struct CSession *
0x18006a962  mov     rcx, [rsp+108h+arg_0]; this
0x18006a96a  call    ?JSONStringifyObjectMember@@YAJAEAVBuildString@@PEAVCSession@@PEAVVAR@@22PEAGAEAIAEA_N2@Z; JSONStringifyObjectMember(BuildString &,CSession *,VAR *,VAR *,VAR *,ushort *,uint &,bool &,VAR *)
0x18006a96f  mov     ebx, eax
0x18006a971  test    eax, eax
0x18006a973  js      short loc_18006A97F
0x18006a975  mov     rcx, [rsp+108h+var_A8]
0x18006a97a  jmp     loc_18006A851
0x18006a97f  test    rdi, rdi
0x18006a982  jz      short loc_18006A98D
0x18006a984  mov     rcx, rdi; bstrString
0x18006a987  call    cs:__imp_SysFreeString
0x18006a98d  mov     rcx, [rsp+108h+var_80]
0x18006a995  mov     rax, [rcx+3D0h]
0x18006a99c  test    rax, rax
0x18006a99f  jz      short loc_18006A9AC
0x18006a9a1  mov     rax, [rax+10h]
0x18006a9a5  mov     [rcx+3D0h], rax
0x18006a9ac  mov     eax, ebx
0x18006a9ae  jmp     loc_18006A77A
0x180094fb5  push    rbp
0x180094fb7  sub     rsp, 50h
0x180094fbb  mov     rbp, rdx
0x180094fbe  mov     rcx, [rbp+50h]; bstrString
0x180094fc2  test    rcx, rcx
0x180094fc5  jz      short loc_180094FCE
0x180094fc7  call    cs:__imp_SysFreeString
0x180094fcd  nop
0x180094fce  add     rsp, 50h
0x180094fd2  pop     rbp
0x180094fd3  retn
```
