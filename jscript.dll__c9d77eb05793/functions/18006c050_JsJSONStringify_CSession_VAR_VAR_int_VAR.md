# JsJSONStringify(CSession *,VAR *,VAR *,int,VAR *)

- ea: `0x18006c050`
- end: `0x18006c453`
- name: `?JsJSONStringify@@YAJPEAVCSession@@PEAVVAR@@1H1@Z`
- size: `1027`
- prototype: `__int64 __usercall@<rax>(struct CSession *@<rcx>, struct VAR *@<rdx>, struct VAR *@<r8>, int@<r9d>, struct VAR *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x1800043b4`
- `0x180004470`
- `0x18000ad40`
- `0x18000ad6c`
- `0x18000afa4`
- `0x18000b130`
- `0x18000bc94`
- `0x180033c30`
- `0x180038180`
- `0x1800384b0`
- `0x180039478`
- `0x18003ffcc`
- `0x1800537e4`
- `0x180069cc8`
- `0x18006c050`
- `0x180096010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006c3f6`
- `OLEAUT32!__imp_SysFreeString` at `0x18006c415`
- `OLEAUT32!__imp_SysFreeString` at `0x18006c434`
- `OLEAUT32!__imp_SysFreeString` at `0x18006c3f6`
- `OLEAUT32!__imp_SysFreeString` at `0x18006c415`
- `OLEAUT32!__imp_SysFreeString` at `0x18006c434`
- `OLEAUT32!__imp_SysStringLen` at `0x18006c2b7`
- `OLEAUT32!__imp_SysStringLen` at `0x18006c2b7`

## pseudocode

```c
__int64 __fastcall JsJSONStringify(struct CSession *a1, struct VAR *a2, struct VAR *a3, int a4, struct VAR *a5)
{
  struct VAR *v6; // r12
  VAR *v7; // r14
  VAR *v8; // rdi
  struct NameTbl *v9; // rbx
  char v10; // r15
  unsigned __int16 *v11; // rbx
  BSTR *v12; // rdi
  int v13; // r9d
  __int64 result; // rax
  double v15; // xmm0_8
  __int64 v16; // rsi
  __int64 v17; // rcx
  unsigned __int16 *v18; // rdi
  VAR *v19; // rcx
  int JSONRootWrap; // edi
  __int64 v21; // rax
  struct NameTbl *v22; // [rsp+40h] [rbp-98h] BYREF
  int v23; // [rsp+48h] [rbp-90h]
  _QWORD v24[2]; // [rsp+50h] [rbp-88h] BYREF
  int v25; // [rsp+60h] [rbp-78h]
  _WORD v26[12]; // [rsp+68h] [rbp-70h] BYREF
  _WORD *v27; // [rsp+80h] [rbp-58h] BYREF
  struct CSession *v28; // [rsp+88h] [rbp-50h]
  __int64 v29; // [rsp+90h] [rbp-48h]
  _BYTE v30[24]; // [rsp+98h] [rbp-40h] BYREF
  unsigned int v32; // [rsp+F8h] [rbp+20h] BYREF

  if ( a4 <= 0 )
    v6 = 0;
  else
    v6 = (struct VAR *)((char *)a5 + 24 * a4 - 24);
  if ( a4 <= 1 )
    v7 = 0;
  else
    v7 = (struct VAR *)((char *)a5 + 24 * a4 - 48);
  if ( a4 <= 2 )
    v8 = 0;
  else
    v8 = (struct VAR *)((char *)a5 + 24 * a4 - 72);
  if ( v7 && *(_WORD *)v7 <= 1u )
    v7 = 0;
  if ( v8 && *(_WORD *)v8 <= 1u )
    v8 = 0;
  if ( v7 )
  {
    v22 = 0;
    if ( !(unsigned int)VAR::IsJsObj(v7, &v22)
      || (v9 = v22, !(*(unsigned int (__fastcall **)(struct NameTbl *))(*(_QWORD *)v22 + 240LL))(v22))
      && !(*(unsigned int (__fastcall **)(struct NameTbl *))(*(_QWORD *)v9 + 312LL))(v9) )
    {
      v7 = 0;
    }
  }
  v10 = 0;
  v11 = 0;
  v32 = 0;
  if ( !v8 )
    goto LABEL_56;
  v12 = (BSTR *)VAR::PvarCutAll(v8);
  v22 = (struct NameTbl *)v12;
  if ( *(_WORD *)v12 != 129 )
  {
LABEL_32:
    if ( ((*(_WORD *)v12 - 3) & 0xFFFD) != 0 )
    {
      if ( !(unsigned int)VAR::FStr((VAR *)v12) )
        goto LABEL_56;
      if ( (unsigned int)VAR::IsAStringObj(v19) )
      {
        result = VAR::ConvertASTRtoBSTR((VAR *)v12);
        if ( (int)result < 0 )
          return result;
        v12 = (BSTR *)v22;
      }
      v11 = v12[1];
      if ( !*v11 )
      {
        v11 = 0;
        goto LABEL_56;
      }
      if ( SysStringLen(v12[1]) > 0xA )
      {
        v11 = _SysAllocStringLen(v11, 0xAu);
        if ( v11 )
        {
          v10 = 1;
          goto LABEL_56;
        }
        return 2147942414LL;
      }
    }
    else
    {
      if ( *(_WORD *)v12 == 5 )
      {
        v15 = ConvertToInteger(*((double *)v12 + 1));
        v16 = (unsigned int)LwFromDblNearest(v15);
      }
      else
      {
        v16 = *((unsigned int *)v12 + 2);
      }
      if ( (int)v16 >= 1 )
      {
        if ( (unsigned int)v16 > 0xA )
          v16 = 10;
        v11 = _SysAllocStringLen(0, v16);
        if ( v11 )
        {
          v10 = 1;
          v17 = (unsigned int)v16;
          v18 = v11;
          while ( v17 )
          {
            *v18++ = 32;
            --v17;
          }
          v11[v16] = 0;
          goto LABEL_56;
        }
        return 2147942414LL;
      }
    }
LABEL_56:
    v24[0] = 0;
    v24[1] = 0;
    v25 = 0;
    if ( v6 )
    {
      v26[0] = 0;
      v28 = a1;
      v27 = v26;
      v29 = *((_QWORD *)a1 + 122);
      *((_QWORD *)a1 + 122) = &v27;
      JSONRootWrap = GetJSONRootWrap(a1, (struct VAR *)v26, v6);
      v23 = JSONRootWrap;
      if ( JSONRootWrap >= 0 )
      {
        JSONRootWrap = JSONStringifyObject(
                         (struct BuildString *)v24,
                         a1,
                         (struct VAR *)&cbstrEmpty,
                         v6,
                         v7,
                         v11,
                         &v32,
                         (struct VAR *)v26);
        v23 = JSONRootWrap;
      }
      v21 = *((_QWORD *)v28 + 122);
      if ( v21 )
        *((_QWORD *)v28 + 122) = *(_QWORD *)(v21 + 16);
      if ( JSONRootWrap >= 0 )
      {
        if ( v10 )
          SysFreeString(v11);
        JSONRootWrap = BuildString::ResetVar((BuildString *)v24, a3, a1);
        goto LABEL_69;
      }
    }
    else
    {
      JSONRootWrap = -2147467263;
    }
    if ( JSONRootWrap == -2147467263 )
    {
      *(_WORD *)a3 = 0;
      if ( v10 )
        SysFreeString(v11);
      BuildString::Reset((BuildString *)v24);
      return 0;
    }
    if ( v10 )
      SysFreeString(v11);
LABEL_69:
    BuildString::Reset((BuildString *)v24);
    return (unsigned int)JSONRootWrap;
  }
  (*(void (__fastcall **)(BSTR, _WORD *))(*(_QWORD *)v12[1] + 328LL))(v12[1], v26);
  v13 = *(unsigned __int16 *)VAR::PvarCutAll((VAR *)v26);
  if ( v13 == 3 || v13 == 5 )
  {
    result = ConvertToScalar(a1, v22, (struct VAR *)v30, v13, 1);
    if ( (int)result < 0 )
      return result;
    v12 = (BSTR *)v30;
    v22 = (struct NameTbl *)v30;
    goto LABEL_32;
  }
  if ( v13 != 8 && v13 != 130 && v13 != 143
    || (result = ConvertToString(a1, &v22, (struct VAR *)v30, 1), (int)result >= 0) )
  {
    v12 = (BSTR *)v22;
    goto LABEL_32;
  }
  return result;
}

```

## disassembly

```asm
0x18006c050  mov     [rsp+arg_0], rbx
0x18006c055  mov     [rsp+arg_8], rsi
0x18006c05a  mov     [rsp+arg_10], r8
0x18006c05f  push    rdi
0x18006c060  push    r12
0x18006c062  push    r13
0x18006c064  push    r14
0x18006c066  push    r15
0x18006c068  sub     rsp, 0B0h
0x18006c06f  mov     r13, rcx
0x18006c072  mov     rdi, [rsp+0D8h+arg_20]
0x18006c07a  test    r9d, r9d
0x18006c07d  jle     short loc_18006C08F
0x18006c07f  movsxd  r12, r9d
0x18006c082  dec     r12
0x18006c085  lea     r12, [r12+r12*2]
0x18006c089  lea     r12, [rdi+r12*8]
0x18006c08d  jmp     short loc_18006C092
0x18006c08f  xor     r12d, r12d
0x18006c092  mov     ecx, 1
0x18006c097  cmp     r9d, ecx
0x18006c09a  jle     short loc_18006C0AD
0x18006c09c  movsxd  rax, r9d
0x18006c09f  sub     rax, 2
0x18006c0a3  lea     rax, [rax+rax*2]
0x18006c0a7  lea     r14, [rdi+rax*8]
0x18006c0ab  jmp     short loc_18006C0B0
0x18006c0ad  xor     r14d, r14d
0x18006c0b0  mov     esi, 3
0x18006c0b5  cmp     r9d, 2
0x18006c0b9  jle     short loc_18006C0CB
0x18006c0bb  movsxd  rax, r9d
0x18006c0be  sub     rax, rsi
0x18006c0c1  lea     rax, [rax+rax*2]
0x18006c0c5  lea     rdi, [rdi+rax*8]
0x18006c0c9  jmp     short loc_18006C0CD
0x18006c0cb  xor     edi, edi
0x18006c0cd  test    r14, r14
0x18006c0d0  jz      short loc_18006C0DC
0x18006c0d2  xor     eax, eax
0x18006c0d4  cmp     [r14], cx
0x18006c0d8  cmovbe  r14, rax
0x18006c0dc  test    rdi, rdi
0x18006c0df  jz      short loc_18006C0EA
0x18006c0e1  xor     eax, eax
0x18006c0e3  cmp     [rdi], cx
0x18006c0e6  cmovbe  rdi, rax
0x18006c0ea  test    r14, r14
0x18006c0ed  jz      short loc_18006C13D
0x18006c0ef  mov     [rsp+0D8h+var_98], 0
0x18006c0f8  lea     rdx, [rsp+0D8h+var_98]; struct NameTbl **
0x18006c0fd  mov     rcx, r14; this
0x18006c100  call    ?IsJsObj@VAR@@QEAAHPEAPEAVNameTbl@@@Z; VAR::IsJsObj(NameTbl * *)
0x18006c105  test    eax, eax
0x18006c107  jz      short loc_18006C13A
0x18006c109  mov     rbx, [rsp+0D8h+var_98]
0x18006c10e  mov     rax, [rbx]
0x18006c111  mov     rcx, rbx
0x18006c114  mov     rax, [rax+0F0h]
0x18006c11b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c120  test    eax, eax
0x18006c122  jnz     short loc_18006C13D
0x18006c124  mov     rax, [rbx]
0x18006c127  mov     rcx, rbx
0x18006c12a  mov     rax, [rax+138h]
0x18006c131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c136  test    eax, eax
0x18006c138  jnz     short loc_18006C13D
0x18006c13a  xor     r14d, r14d
0x18006c13d  xor     r15b, r15b
0x18006c140  xor     ebx, ebx
0x18006c142  mov     [rsp+0D8h+arg_18], ebx
0x18006c149  test    rdi, rdi
0x18006c14c  jz      loc_18006C2FB
0x18006c152  mov     rcx, rdi; this
0x18006c155  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x18006c15a  mov     rdi, rax
0x18006c15d  mov     [rsp+0D8h+var_98], rax
0x18006c162  mov     eax, 81h
0x18006c167  cmp     [rdi], ax
0x18006c16a  jnz     loc_18006C20C
0x18006c170  mov     rcx, [rdi+8]
0x18006c174  mov     rax, [rcx]
0x18006c177  lea     rdx, [rsp+0D8h+var_70]
0x18006c17c  mov     rax, [rax+148h]
0x18006c183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c188  lea     rcx, [rsp+0D8h+var_70]; this
0x18006c18d  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x18006c192  movzx   r9d, word ptr [rax]; int
0x18006c196  mov     ecx, r9d
0x18006c199  sub     ecx, esi
0x18006c19b  jz      short loc_18006C1DA
0x18006c19d  sub     ecx, 2
0x18006c1a0  jz      short loc_18006C1DA
0x18006c1a2  sub     ecx, esi
0x18006c1a4  jz      short loc_18006C1B0
0x18006c1a6  sub     ecx, 7Ah ; 'z'
0x18006c1a9  jz      short loc_18006C1B0
0x18006c1ab  cmp     ecx, 0Dh
0x18006c1ae  jnz     short loc_18006C1D3
0x18006c1b0  mov     r9d, 1; int
0x18006c1b6  lea     r8, [rsp+0D8h+var_40]; struct VAR *
0x18006c1be  lea     rdx, [rsp+0D8h+var_98]; struct VAR **
0x18006c1c3  mov     rcx, r13; struct CSession *
0x18006c1c6  call    ?ConvertToString@@YAJPEAVCSession@@PEAPEAVVAR@@PEAV2@H@Z; ConvertToString(CSession *,VAR * *,VAR *,int)
0x18006c1cb  test    eax, eax
0x18006c1cd  js      loc_18006C2DB
0x18006c1d3  mov     rdi, [rsp+0D8h+var_98]
0x18006c1d8  jmp     short loc_18006C20C
0x18006c1da  mov     dword ptr [rsp+0D8h+var_B8], 1; int
0x18006c1e2  lea     r8, [rsp+0D8h+var_40]; struct VAR *
0x18006c1ea  mov     rdx, [rsp+0D8h+var_98]; this
0x18006c1ef  mov     rcx, r13; struct CSession *
0x18006c1f2  call    ?ConvertToScalar@@YAJPEAVCSession@@PEAVVAR@@1HH@Z; ConvertToScalar(CSession *,VAR *,VAR *,int,int)
0x18006c1f7  test    eax, eax
0x18006c1f9  js      loc_18006C2DB
0x18006c1ff  lea     rdi, [rsp+0D8h+var_40]
0x18006c207  mov     [rsp+0D8h+var_98], rdi
0x18006c20c  movzx   eax, word ptr [rdi]
0x18006c20f  sub     ax, si
0x18006c212  mov     ecx, 0FFFDh
0x18006c217  test    cx, ax
0x18006c21a  jnz     short loc_18006C27F
0x18006c21c  mov     eax, 5
0x18006c221  cmp     ax, [rdi]
0x18006c224  jnz     short loc_18006C239
0x18006c226  movsd   xmm0, qword ptr [rdi+8]; double
0x18006c22b  call    ?ConvertToInteger@@YANN@Z; ConvertToInteger(double)
0x18006c230  call    ?LwFromDblNearest@@YAJN@Z; LwFromDblNearest(double)
0x18006c235  mov     esi, eax
0x18006c237  jmp     short loc_18006C23C
0x18006c239  mov     esi, [rdi+8]
0x18006c23c  cmp     esi, 1
0x18006c23f  jl      loc_18006C2FB
0x18006c245  mov     edx, 0Ah
0x18006c24a  cmp     esi, edx
0x18006c24c  cmova   esi, edx
0x18006c24f  mov     edx, esi; unsigned int
0x18006c251  xor     ecx, ecx; unsigned __int16 *
0x18006c253  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x18006c258  mov     rbx, rax
0x18006c25b  test    rax, rax
0x18006c25e  jz      short loc_18006C2D6
0x18006c260  mov     r15b, 1
0x18006c263  test    esi, esi
0x18006c265  jz      short loc_18006C277
0x18006c267  mov     ecx, esi
0x18006c269  mov     eax, 20h ; ' '
0x18006c26e  movzx   eax, ax
0x18006c271  mov     rdi, rbx
0x18006c274  rep stosw
0x18006c277  xor     eax, eax
0x18006c279  mov     [rbx+rsi*2], ax
0x18006c27d  jmp     short loc_18006C2FB
0x18006c27f  mov     rcx, rdi; this
0x18006c282  call    ?FStr@VAR@@QEAAHXZ; VAR::FStr(void)
0x18006c287  test    eax, eax
0x18006c289  jz      short loc_18006C2FB
0x18006c28b  call    ?IsAStringObj@VAR@@QEAAHXZ; VAR::IsAStringObj(void)
0x18006c290  test    eax, eax
0x18006c292  jz      short loc_18006C2A5
0x18006c294  mov     rcx, rdi; this
0x18006c297  call    ?ConvertASTRtoBSTR@VAR@@QEAAJXZ; VAR::ConvertASTRtoBSTR(void)
0x18006c29c  test    eax, eax
0x18006c29e  js      short loc_18006C2DB
0x18006c2a0  mov     rdi, [rsp+0D8h+var_98]
0x18006c2a5  mov     rbx, [rdi+8]
0x18006c2a9  xor     eax, eax
0x18006c2ab  cmp     ax, [rbx]
0x18006c2ae  jnz     short loc_18006C2B4
0x18006c2b0  xor     ebx, ebx
0x18006c2b2  jmp     short loc_18006C2FB
0x18006c2b4  mov     rcx, rbx; pbstr
0x18006c2b7  call    cs:__imp_SysStringLen
0x18006c2bd  mov     edx, 0Ah; unsigned int
0x18006c2c2  cmp     eax, edx
0x18006c2c4  jbe     short loc_18006C2FB
0x18006c2c6  mov     rcx, rbx; unsigned __int16 *
0x18006c2c9  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x18006c2ce  mov     rbx, rax
0x18006c2d1  test    rax, rax
0x18006c2d4  jnz     short loc_18006C2F8
0x18006c2d6  mov     eax, 8007000Eh
0x18006c2db  lea     r11, [rsp+0D8h+var_28]
0x18006c2e3  mov     rbx, [r11+30h]
0x18006c2e7  mov     rsi, [r11+38h]
0x18006c2eb  mov     rsp, r11
0x18006c2ee  pop     r15
0x18006c2f0  pop     r14
0x18006c2f2  pop     r13
0x18006c2f4  pop     r12
0x18006c2f6  pop     rdi
0x18006c2f7  retn
0x18006c2f8  mov     r15b, 1
0x18006c2fb  mov     [rsp+0D8h+var_88], 0
0x18006c304  mov     [rsp+0D8h+var_80], 0
0x18006c30d  mov     [rsp+0D8h+var_78], 0
0x18006c315  test    r12, r12
0x18006c318  jnz     short loc_18006C324
0x18006c31a  mov     edi, 80004001h
0x18006c31f  jmp     loc_18006C3D9
0x18006c324  xor     eax, eax
0x18006c326  mov     [rsp+0D8h+var_70], ax
0x18006c32b  mov     [rsp+0D8h+var_50], r13
0x18006c333  lea     rax, [rsp+0D8h+var_70]
0x18006c338  mov     [rsp+0D8h+var_58], rax
0x18006c340  mov     rax, [r13+3D0h]
0x18006c347  mov     [rsp+0D8h+var_48], rax
0x18006c34f  lea     rax, [rsp+0D8h+var_58]
0x18006c357  mov     [r13+3D0h], rax
0x18006c35e  mov     r8, r12; struct VAR *
0x18006c361  lea     rdx, [rsp+0D8h+var_70]; struct VAR *
0x18006c366  mov     rcx, r13; struct CSession *
0x18006c369  call    ?GetJSONRootWrap@@YAJPEAVCSession@@PEAVVAR@@1@Z; GetJSONRootWrap(CSession *,VAR *,VAR *)
0x18006c36e  mov     edi, eax
0x18006c370  mov     [rsp+0D8h+var_90], eax
0x18006c374  test    eax, eax
0x18006c376  js      short loc_18006C3B6
0x18006c378  lea     rax, [rsp+0D8h+var_70]
0x18006c37d  mov     [rsp+0D8h+var_A0], rax; struct VAR *
0x18006c382  lea     rax, [rsp+0D8h+arg_18]
0x18006c38a  mov     [rsp+0D8h+var_A8], rax; unsigned int *
0x18006c38f  mov     [rsp+0D8h+var_B0], rbx; unsigned __int16 *
0x18006c394  mov     [rsp+0D8h+var_B8], r14; struct VAR *
0x18006c399  mov     r9, r12; struct VAR *
0x18006c39c  lea     r8, ?cbstrEmpty@@3UConstBstr@@A; struct VAR *
0x18006c3a3  mov     rdx, r13; struct CSession *
0x18006c3a6  lea     rcx, [rsp+0D8h+var_88]; this
0x18006c3ab  call    ?JSONStringifyObject@@YAJAEAVBuildString@@PEAVCSession@@PEAVVAR@@22PEAGAEAI2@Z; JSONStringifyObject(BuildString &,CSession *,VAR *,VAR *,VAR *,ushort *,uint &,VAR *)
0x18006c3b0  mov     edi, eax
0x18006c3b2  mov     [rsp+0D8h+var_90], eax
0x18006c3b6  mov     rcx, [rsp+0D8h+var_50]
0x18006c3be  mov     rax, [rcx+3D0h]
0x18006c3c5  test    rax, rax
0x18006c3c8  jz      short loc_18006C3D5
0x18006c3ca  mov     rax, [rax+10h]
0x18006c3ce  mov     [rcx+3D0h], rax
0x18006c3d5  test    edi, edi
0x18006c3d7  jns     short loc_18006C42C
0x18006c3d9  cmp     edi, 80004001h
0x18006c3df  jnz     short loc_18006C40D
0x18006c3e1  xor     eax, eax
0x18006c3e3  mov     rdx, [rsp+0D8h+arg_10]
0x18006c3eb  mov     [rdx], ax
0x18006c3ee  test    r15b, r15b
0x18006c3f1  jz      short loc_18006C3FC
0x18006c3f3  mov     rcx, rbx; bstrString
0x18006c3f6  call    cs:__imp_SysFreeString
0x18006c3fc  lea     rcx, [rsp+0D8h+var_88]; this
0x18006c401  call    ?Reset@BuildString@@QEAAXXZ; BuildString::Reset(void)
0x18006c406  xor     eax, eax
0x18006c408  jmp     loc_18006C2DB
0x18006c40d  test    r15b, r15b
0x18006c410  jz      short loc_18006C41B
0x18006c412  mov     rcx, rbx; bstrString
0x18006c415  call    cs:__imp_SysFreeString
0x18006c41b  lea     rcx, [rsp+0D8h+var_88]; this
0x18006c420  call    ?Reset@BuildString@@QEAAXXZ; BuildString::Reset(void)
0x18006c425  mov     eax, edi
0x18006c427  jmp     loc_18006C2DB
0x18006c42c  test    r15b, r15b
0x18006c42f  jz      short loc_18006C43A
0x18006c431  mov     rcx, rbx; bstrString
0x18006c434  call    cs:__imp_SysFreeString
0x18006c43a  mov     r8, r13; struct CSession *
0x18006c43d  mov     rdx, [rsp+0D8h+arg_10]; struct VAR *
0x18006c445  lea     rcx, [rsp+0D8h+var_88]; this
0x18006c44a  call    ?ResetVar@BuildString@@QEAAJPEAVVAR@@PEAVCSession@@@Z; BuildString::ResetVar(VAR *,CSession *)
0x18006c44f  mov     edi, eax
0x18006c451  jmp     short loc_18006C41B
0x180094a0c  push    rbp
0x180094a0e  sub     rsp, 40h
0x180094a12  mov     rbp, rdx
0x180094a15  add     rsp, 40h
0x180094a19  pop     rbp
0x180094a1a  retn
```
