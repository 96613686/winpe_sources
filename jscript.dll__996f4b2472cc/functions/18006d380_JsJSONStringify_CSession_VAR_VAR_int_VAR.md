# JsJSONStringify(CSession *,VAR *,VAR *,int,VAR *)

- ea: `0x18006d380`
- end: `0x18006d79f`
- name: `?JsJSONStringify@@YAJPEAVCSession@@PEAVVAR@@1H1@Z`
- size: `1055`
- prototype: `int __fastcall(struct CSession *, struct VAR *, struct VAR *, int, struct VAR *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callees

- `0x1800029e4`
- `0x180005070`
- `0x180007e68`
- `0x180007e9c`
- `0x1800080c8`
- `0x18000826c`
- `0x180008794`
- `0x180008df4`
- `0x1800325f8`
- `0x1800326c0`
- `0x180039f20`
- `0x18003d070`
- `0x18005460c`
- `0x18006b008`
- `0x18006d380`
- `0x180098010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006d730`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d755`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d77a`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d730`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d755`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d77a`
- `OLEAUT32!__imp_SysStringLen` at `0x18006d5ea`
- `OLEAUT32!__imp_SysStringLen` at `0x18006d5ea`

## pseudocode

```c
int __fastcall JsJSONStringify(struct CSession *a1, struct VAR *a2, struct VAR *a3, int a4, struct VAR *a5)
{
  struct VAR *v6; // r12
  VAR *v7; // r14
  VAR *v8; // rdi
  struct NameTbl *v9; // rbx
  char v10; // r15
  unsigned __int16 *bstrVal; // rbx
  VARIANTARG *v12; // rdi
  int v13; // r9d
  int result; // eax
  double v15; // xmm0_8
  __int64 Lo; // rsi
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
  VARIANTARG v30; // [rsp+98h] [rbp-40h] BYREF
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
  bstrVal = 0;
  v32 = 0;
  if ( !v8 )
    goto LABEL_56;
  v12 = (VARIANTARG *)VAR::PvarCutAll(v8);
  v22 = (struct NameTbl *)v12;
  if ( v12->vt != 129 )
  {
LABEL_32:
    if ( ((v12->vt - 3) & 0xFFFD) != 0 )
    {
      if ( !(unsigned int)VAR::FStr((VAR *)v12) )
        goto LABEL_56;
      if ( (unsigned int)VAR::IsAStringObj(v19) )
      {
        result = VAR::ConvertASTRtoBSTR((VAR *)v12);
        if ( result < 0 )
          return result;
        v12 = (VARIANTARG *)v22;
      }
      bstrVal = v12->bstrVal;
      if ( !*bstrVal )
      {
        bstrVal = 0;
        goto LABEL_56;
      }
      if ( SysStringLen(v12->bstrVal) > 0xA )
      {
        bstrVal = _SysAllocStringLen(bstrVal, 0xAu);
        if ( bstrVal )
        {
          v10 = 1;
          goto LABEL_56;
        }
        return -2147024882;
      }
    }
    else
    {
      if ( v12->vt == 5 )
      {
        v15 = ConvertToInteger(v12->dblVal);
        Lo = (unsigned int)LwFromDblNearest(v15);
      }
      else
      {
        Lo = v12->cyVal.Lo;
      }
      if ( (int)Lo >= 1 )
      {
        if ( (unsigned int)Lo > 0xA )
          Lo = 10;
        bstrVal = _SysAllocStringLen(0, Lo);
        if ( bstrVal )
        {
          v10 = 1;
          v17 = (unsigned int)Lo;
          v18 = bstrVal;
          while ( v17 )
          {
            *v18++ = 32;
            --v17;
          }
          bstrVal[Lo] = 0;
          goto LABEL_56;
        }
        return -2147024882;
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
                         bstrVal,
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
          SysFreeString(bstrVal);
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
        SysFreeString(bstrVal);
      BuildString::Reset((BuildString *)v24);
      return 0;
    }
    if ( v10 )
      SysFreeString(bstrVal);
LABEL_69:
    BuildString::Reset((BuildString *)v24);
    return JSONRootWrap;
  }
  (*(void (__fastcall **)(LONGLONG, _WORD *))(*v12->pllVal + 328))(v12->llVal, v26);
  v13 = *(unsigned __int16 *)VAR::PvarCutAll((VAR *)v26);
  if ( v13 == 3 || v13 == 5 )
  {
    result = ConvertToScalar(a1, v22, (struct VAR *)&v30, v13, 1);
    if ( result < 0 )
      return result;
    v12 = &v30;
    v22 = (struct NameTbl *)&v30;
    goto LABEL_32;
  }
  if ( v13 != 8 && v13 != 130 && v13 != 143
    || (result = ConvertToString(a1, (struct IDispatch ***)&v22, &v30, 1), result >= 0) )
  {
    v12 = (VARIANTARG *)v22;
    goto LABEL_32;
  }
  return result;
}

```

## disassembly

```asm
0x18006d380  mov     [rsp+arg_0], rbx
0x18006d385  mov     [rsp+arg_8], rsi
0x18006d38a  mov     [rsp+arg_10], r8
0x18006d38f  push    rdi
0x18006d390  push    r12
0x18006d392  push    r13
0x18006d394  push    r14
0x18006d396  push    r15
0x18006d398  sub     rsp, 0B0h
0x18006d39f  mov     r13, rcx
0x18006d3a2  mov     rdi, [rsp+0D8h+arg_20]
0x18006d3aa  test    r9d, r9d
0x18006d3ad  jle     short loc_18006D3BF
0x18006d3af  movsxd  r12, r9d
0x18006d3b2  dec     r12
0x18006d3b5  lea     r12, [r12+r12*2]
0x18006d3b9  lea     r12, [rdi+r12*8]
0x18006d3bd  jmp     short loc_18006D3C2
0x18006d3bf  xor     r12d, r12d
0x18006d3c2  mov     ecx, 1
0x18006d3c7  cmp     r9d, ecx
0x18006d3ca  jle     short loc_18006D3DD
0x18006d3cc  movsxd  rax, r9d
0x18006d3cf  sub     rax, 2
0x18006d3d3  lea     rax, [rax+rax*2]
0x18006d3d7  lea     r14, [rdi+rax*8]
0x18006d3db  jmp     short loc_18006D3E0
0x18006d3dd  xor     r14d, r14d
0x18006d3e0  mov     esi, 3
0x18006d3e5  cmp     r9d, 2
0x18006d3e9  jle     short loc_18006D3FB
0x18006d3eb  movsxd  rax, r9d
0x18006d3ee  sub     rax, rsi
0x18006d3f1  lea     rax, [rax+rax*2]
0x18006d3f5  lea     rdi, [rdi+rax*8]
0x18006d3f9  jmp     short loc_18006D3FD
0x18006d3fb  xor     edi, edi
0x18006d3fd  test    r14, r14
0x18006d400  jz      short loc_18006D40C
0x18006d402  xor     eax, eax
0x18006d404  cmp     [r14], cx
0x18006d408  cmovbe  r14, rax
0x18006d40c  test    rdi, rdi
0x18006d40f  jz      short loc_18006D41A
0x18006d411  xor     eax, eax
0x18006d413  cmp     [rdi], cx
0x18006d416  cmovbe  rdi, rax
0x18006d41a  test    r14, r14
0x18006d41d  jz      short loc_18006D46D
0x18006d41f  mov     [rsp+0D8h+var_98], 0
0x18006d428  lea     rdx, [rsp+0D8h+var_98]; struct NameTbl **
0x18006d42d  mov     rcx, r14; this
0x18006d430  call    ?IsJsObj@VAR@@QEAAHPEAPEAVNameTbl@@@Z; VAR::IsJsObj(NameTbl * *)
0x18006d435  test    eax, eax
0x18006d437  jz      short loc_18006D46A
0x18006d439  mov     rbx, [rsp+0D8h+var_98]
0x18006d43e  mov     rax, [rbx]
0x18006d441  mov     rcx, rbx
0x18006d444  mov     rax, [rax+0F0h]
0x18006d44b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d450  test    eax, eax
0x18006d452  jnz     short loc_18006D46D
0x18006d454  mov     rax, [rbx]
0x18006d457  mov     rcx, rbx
0x18006d45a  mov     rax, [rax+138h]
0x18006d461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d466  test    eax, eax
0x18006d468  jnz     short loc_18006D46D
0x18006d46a  xor     r14d, r14d
0x18006d46d  xor     r15b, r15b
0x18006d470  xor     ebx, ebx
0x18006d472  mov     [rsp+0D8h+arg_18], ebx
0x18006d479  test    rdi, rdi
0x18006d47c  jz      loc_18006D635
0x18006d482  mov     rcx, rdi; this
0x18006d485  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x18006d48a  mov     rdi, rax
0x18006d48d  mov     [rsp+0D8h+var_98], rax
0x18006d492  mov     eax, 81h
0x18006d497  cmp     [rdi], ax
0x18006d49a  jnz     loc_18006D53C
0x18006d4a0  mov     rcx, [rdi+8]
0x18006d4a4  mov     rax, [rcx]
0x18006d4a7  lea     rdx, [rsp+0D8h+var_70]
0x18006d4ac  mov     rax, [rax+148h]
0x18006d4b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d4b8  lea     rcx, [rsp+0D8h+var_70]; this
0x18006d4bd  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x18006d4c2  movzx   r9d, word ptr [rax]; int
0x18006d4c6  mov     ecx, r9d
0x18006d4c9  sub     ecx, esi
0x18006d4cb  jz      short loc_18006D50A
0x18006d4cd  sub     ecx, 2
0x18006d4d0  jz      short loc_18006D50A
0x18006d4d2  sub     ecx, esi
0x18006d4d4  jz      short loc_18006D4E0
0x18006d4d6  sub     ecx, 7Ah ; 'z'
0x18006d4d9  jz      short loc_18006D4E0
0x18006d4db  cmp     ecx, 0Dh
0x18006d4de  jnz     short loc_18006D503
0x18006d4e0  mov     r9d, 1; int
0x18006d4e6  lea     r8, [rsp+0D8h+var_40]; struct VAR *
0x18006d4ee  lea     rdx, [rsp+0D8h+var_98]; struct VAR **
0x18006d4f3  mov     rcx, r13; struct CSession *
0x18006d4f6  call    ?ConvertToString@@YAJPEAVCSession@@PEAPEAVVAR@@PEAV2@H@Z; ConvertToString(CSession *,VAR * *,VAR *,int)
0x18006d4fb  test    eax, eax
0x18006d4fd  js      loc_18006D614
0x18006d503  mov     rdi, [rsp+0D8h+var_98]
0x18006d508  jmp     short loc_18006D53C
0x18006d50a  mov     dword ptr [rsp+0D8h+var_B8], 1; int
0x18006d512  lea     r8, [rsp+0D8h+var_40]; struct VAR *
0x18006d51a  mov     rdx, [rsp+0D8h+var_98]; this
0x18006d51f  mov     rcx, r13; struct CSession *
0x18006d522  call    ?ConvertToScalar@@YAJPEAVCSession@@PEAVVAR@@1HH@Z; ConvertToScalar(CSession *,VAR *,VAR *,int,int)
0x18006d527  test    eax, eax
0x18006d529  js      loc_18006D614
0x18006d52f  lea     rdi, [rsp+0D8h+var_40]
0x18006d537  mov     [rsp+0D8h+var_98], rdi
0x18006d53c  movzx   eax, word ptr [rdi]
0x18006d53f  sub     ax, si
0x18006d542  mov     ecx, 0FFFDh
0x18006d547  test    cx, ax
0x18006d54a  jnz     short loc_18006D5B2
0x18006d54c  mov     eax, 5
0x18006d551  cmp     ax, [rdi]
0x18006d554  jnz     short loc_18006D569
0x18006d556  movsd   xmm0, qword ptr [rdi+8]; double
0x18006d55b  call    ?ConvertToInteger@@YANN@Z; ConvertToInteger(double)
0x18006d560  call    ?LwFromDblNearest@@YAJN@Z; LwFromDblNearest(double)
0x18006d565  mov     esi, eax
0x18006d567  jmp     short loc_18006D56C
0x18006d569  mov     esi, [rdi+8]
0x18006d56c  cmp     esi, 1
0x18006d56f  jl      loc_18006D635
0x18006d575  mov     edx, 0Ah
0x18006d57a  cmp     esi, edx
0x18006d57c  cmova   esi, edx
0x18006d57f  mov     edx, esi; unsigned int
0x18006d581  xor     ecx, ecx; unsigned __int16 *
0x18006d583  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x18006d588  mov     rbx, rax
0x18006d58b  test    rax, rax
0x18006d58e  jz      short loc_18006D60F
0x18006d590  mov     r15b, 1
0x18006d593  test    esi, esi
0x18006d595  jz      short loc_18006D5A7
0x18006d597  mov     ecx, esi
0x18006d599  mov     eax, 20h ; ' '
0x18006d59e  movzx   eax, ax
0x18006d5a1  mov     rdi, rbx
0x18006d5a4  rep stosw
0x18006d5a7  xor     eax, eax
0x18006d5a9  mov     [rbx+rsi*2], ax
0x18006d5ad  jmp     loc_18006D635
0x18006d5b2  mov     rcx, rdi; this
0x18006d5b5  call    ?FStr@VAR@@QEAAHXZ; VAR::FStr(void)
0x18006d5ba  test    eax, eax
0x18006d5bc  jz      short loc_18006D635
0x18006d5be  call    ?IsAStringObj@VAR@@QEAAHXZ; VAR::IsAStringObj(void)
0x18006d5c3  test    eax, eax
0x18006d5c5  jz      short loc_18006D5D8
0x18006d5c7  mov     rcx, rdi; this
0x18006d5ca  call    ?ConvertASTRtoBSTR@VAR@@QEAAJXZ; VAR::ConvertASTRtoBSTR(void)
0x18006d5cf  test    eax, eax
0x18006d5d1  js      short loc_18006D614
0x18006d5d3  mov     rdi, [rsp+0D8h+var_98]
0x18006d5d8  mov     rbx, [rdi+8]
0x18006d5dc  xor     eax, eax
0x18006d5de  cmp     ax, [rbx]
0x18006d5e1  jnz     short loc_18006D5E7
0x18006d5e3  xor     ebx, ebx
0x18006d5e5  jmp     short loc_18006D635
0x18006d5e7  mov     rcx, rbx; pbstr
0x18006d5ea  call    cs:__imp_SysStringLen
0x18006d5f1  nop     dword ptr [rax+rax+00h]
0x18006d5f6  mov     edx, 0Ah; unsigned int
0x18006d5fb  cmp     eax, edx
0x18006d5fd  jbe     short loc_18006D635
0x18006d5ff  mov     rcx, rbx; unsigned __int16 *
0x18006d602  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x18006d607  mov     rbx, rax
0x18006d60a  test    rax, rax
0x18006d60d  jnz     short loc_18006D632
0x18006d60f  mov     eax, 8007000Eh
0x18006d614  lea     r11, [rsp+0D8h+var_28]
0x18006d61c  mov     rbx, [r11+30h]
0x18006d620  mov     rsi, [r11+38h]
0x18006d624  mov     rsp, r11
0x18006d627  pop     r15
0x18006d629  pop     r14
0x18006d62b  pop     r13
0x18006d62d  pop     r12
0x18006d62f  pop     rdi
0x18006d630  retn
0x18006d632  mov     r15b, 1
0x18006d635  mov     [rsp+0D8h+var_88], 0
0x18006d63e  mov     [rsp+0D8h+var_80], 0
0x18006d647  mov     [rsp+0D8h+var_78], 0
0x18006d64f  test    r12, r12
0x18006d652  jnz     short loc_18006D65E
0x18006d654  mov     edi, 80004001h
0x18006d659  jmp     loc_18006D713
0x18006d65e  xor     eax, eax
0x18006d660  mov     [rsp+0D8h+var_70], ax
0x18006d665  mov     [rsp+0D8h+var_50], r13
0x18006d66d  lea     rax, [rsp+0D8h+var_70]
0x18006d672  mov     [rsp+0D8h+var_58], rax
0x18006d67a  mov     rax, [r13+3D0h]
0x18006d681  mov     [rsp+0D8h+var_48], rax
0x18006d689  lea     rax, [rsp+0D8h+var_58]
0x18006d691  mov     [r13+3D0h], rax
0x18006d698  mov     r8, r12; struct VAR *
0x18006d69b  lea     rdx, [rsp+0D8h+var_70]; struct VAR *
0x18006d6a0  mov     rcx, r13; struct CSession *
0x18006d6a3  call    ?GetJSONRootWrap@@YAJPEAVCSession@@PEAVVAR@@1@Z; GetJSONRootWrap(CSession *,VAR *,VAR *)
0x18006d6a8  mov     edi, eax
0x18006d6aa  mov     [rsp+0D8h+var_90], eax
0x18006d6ae  test    eax, eax
0x18006d6b0  js      short loc_18006D6F0
0x18006d6b2  lea     rax, [rsp+0D8h+var_70]
0x18006d6b7  mov     [rsp+0D8h+var_A0], rax; struct VAR *
0x18006d6bc  lea     rax, [rsp+0D8h+arg_18]
0x18006d6c4  mov     [rsp+0D8h+var_A8], rax; unsigned int *
0x18006d6c9  mov     [rsp+0D8h+var_B0], rbx; unsigned __int16 *
0x18006d6ce  mov     [rsp+0D8h+var_B8], r14; struct VAR *
0x18006d6d3  mov     r9, r12; struct VAR *
0x18006d6d6  lea     r8, ?cbstrEmpty@@3UConstBstr@@A; struct VAR *
0x18006d6dd  mov     rdx, r13; struct CSession *
0x18006d6e0  lea     rcx, [rsp+0D8h+var_88]; this
0x18006d6e5  call    ?JSONStringifyObject@@YAJAEAVBuildString@@PEAVCSession@@PEAVVAR@@22PEAGAEAI2@Z; JSONStringifyObject(BuildString &,CSession *,VAR *,VAR *,VAR *,ushort *,uint &,VAR *)
0x18006d6ea  mov     edi, eax
0x18006d6ec  mov     [rsp+0D8h+var_90], eax
0x18006d6f0  mov     rcx, [rsp+0D8h+var_50]
0x18006d6f8  mov     rax, [rcx+3D0h]
0x18006d6ff  test    rax, rax
0x18006d702  jz      short loc_18006D70F
0x18006d704  mov     rax, [rax+10h]
0x18006d708  mov     [rcx+3D0h], rax
0x18006d70f  test    edi, edi
0x18006d711  jns     short loc_18006D772
0x18006d713  cmp     edi, 80004001h
0x18006d719  jnz     short loc_18006D74D
0x18006d71b  xor     eax, eax
0x18006d71d  mov     rdx, [rsp+0D8h+arg_10]
0x18006d725  mov     [rdx], ax
0x18006d728  test    r15b, r15b
0x18006d72b  jz      short loc_18006D73C
0x18006d72d  mov     rcx, rbx; bstrString
0x18006d730  call    cs:__imp_SysFreeString
0x18006d737  nop     dword ptr [rax+rax+00h]
0x18006d73c  lea     rcx, [rsp+0D8h+var_88]; this
0x18006d741  call    ?Reset@BuildString@@QEAAXXZ; BuildString::Reset(void)
0x18006d746  xor     eax, eax
0x18006d748  jmp     loc_18006D614
0x18006d74d  test    r15b, r15b
0x18006d750  jz      short loc_18006D761
0x18006d752  mov     rcx, rbx; bstrString
0x18006d755  call    cs:__imp_SysFreeString
0x18006d75c  nop     dword ptr [rax+rax+00h]
0x18006d761  lea     rcx, [rsp+0D8h+var_88]; this
0x18006d766  call    ?Reset@BuildString@@QEAAXXZ; BuildString::Reset(void)
0x18006d76b  mov     eax, edi
0x18006d76d  jmp     loc_18006D614
0x18006d772  test    r15b, r15b
0x18006d775  jz      short loc_18006D786
0x18006d777  mov     rcx, rbx; bstrString
0x18006d77a  call    cs:__imp_SysFreeString
0x18006d781  nop     dword ptr [rax+rax+00h]
0x18006d786  mov     r8, r13; struct CSession *
0x18006d789  mov     rdx, [rsp+0D8h+arg_10]; struct VAR *
0x18006d791  lea     rcx, [rsp+0D8h+var_88]; this
0x18006d796  call    ?ResetVar@BuildString@@QEAAJPEAVVAR@@PEAVCSession@@@Z; BuildString::ResetVar(VAR *,CSession *)
0x18006d79b  mov     edi, eax
0x18006d79d  jmp     short loc_18006D761
0x180096e21  push    rbp
0x180096e23  sub     rsp, 40h
0x180096e27  mov     rbp, rdx
0x180096e2a  add     rsp, 40h
0x180096e2e  pop     rbp
0x180096e2f  retn
```
