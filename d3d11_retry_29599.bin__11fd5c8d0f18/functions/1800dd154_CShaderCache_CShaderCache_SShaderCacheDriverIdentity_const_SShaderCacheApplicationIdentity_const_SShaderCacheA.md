# CShaderCache::CShaderCache(SShaderCacheDriverIdentity const &,SShaderCacheApplicationIdentity const &,SShaderCacheApplicationIdentity const &,SessionUniqueness const &,SShaderCacheDesc const &,ushort const *,SShaderCacheProperties *)

- ea: `0x1800dd154`
- end: `0x1800dd301`
- name: `??0CShaderCache@@QEAA@AEBUSShaderCacheDriverIdentity@@AEBUSShaderCacheApplicationIdentity@@1AEBUSessionUniqueness@@AEBUSShaderCacheDesc@@PEBGPEAUSShaderCacheProperties@@@Z`
- size: `429`
- prototype: `CShaderCache *__fastcall(CShaderCache *__hidden this, const struct SShaderCacheDriverIdentity *, const struct SShaderCacheApplicationIdentity *, const struct SShaderCacheApplicationIdentity *, const struct SessionUniqueness *, const struct SShaderCacheDesc *, const unsigned __int16 *, struct SShaderCacheProperties *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800dc2e8`

## callees

- `0x180022400`
- `0x18009ec74`
- `0x1800dce94`
- `0x1800dd154`

## import_xrefs

- `D3DSCache!ShaderCache_Clear` at `0x1800dd259`
- `D3DSCache!ShaderCache_Clear` at `0x1800dd259`
- `D3DSCache!ShaderCache_GetCompilerIdentity` at `0x1800dd204`
- `D3DSCache!ShaderCache_GetCompilerIdentity` at `0x1800dd204`
- `D3DSCache!ShaderCache_GetApplicationIdentity` at `0x1800dd218`
- `D3DSCache!ShaderCache_GetApplicationIdentity` at `0x1800dd218`
- `D3DSCache!ShaderCache_SetCompilerIdentity` at `0x1800dd282`
- `D3DSCache!ShaderCache_SetCompilerIdentity` at `0x1800dd282`
- `D3DSCache!ShaderCache_SetApplicationIdentity` at `0x1800dd2d4`
- `D3DSCache!ShaderCache_SetApplicationIdentity` at `0x1800dd2d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CShaderCache *__fastcall CShaderCache::CShaderCache(
        CShaderCache *this,
        const struct SShaderCacheDriverIdentity *a2,
        const struct SShaderCacheApplicationIdentity *a3,
        const struct SShaderCacheApplicationIdentity *a4,
        const struct SessionUniqueness *a5,
        const struct SShaderCacheDesc *a6,
        unsigned __int16 *a7,
        struct SShaderCacheProperties *a8)
{
  int v12; // eax
  char v13; // cl
  char v14; // al
  int v15; // ecx
  int v16; // eax
  const struct SShaderCacheDriverIdentity *v18; // [rsp+28h] [rbp-79h] BYREF
  int v19; // [rsp+30h] [rbp-71h]
  int v20; // [rsp+34h] [rbp-6Dh]
  struct SShaderCacheProperties *v21; // [rsp+38h] [rbp-69h]
  char v22; // [rsp+40h] [rbp-61h]
  int v23; // [rsp+41h] [rbp-60h]
  __int16 v24; // [rsp+45h] [rbp-5Ch]
  char v25; // [rsp+47h] [rbp-5Ah]
  _QWORD v26[2]; // [rsp+48h] [rbp-59h] BYREF
  int v27; // [rsp+58h] [rbp-49h]
  int v28; // [rsp+5Ch] [rbp-45h]
  struct SShaderCacheProperties *v29; // [rsp+60h] [rbp-41h]
  char v30; // [rsp+68h] [rbp-39h]
  int v31; // [rsp+69h] [rbp-38h]
  __int16 v32; // [rsp+6Dh] [rbp-34h]
  char v33; // [rsp+6Fh] [rbp-32h]
  _QWORD v34[3]; // [rsp+70h] [rbp-31h] BYREF
  _QWORD v35[6]; // [rsp+88h] [rbp-19h] BYREF

  CShaderCache::CShaderCache(this, a5, a6, a7);
  if ( a8 )
    *(_BYTE *)a8 = 1;
  v12 = *((_DWORD *)a6 + 4);
  if ( v12 && (*((_BYTE *)a6 + 64) & 4) == 0 )
  {
    v18 = a2;
    v19 = v12;
    v20 = 0;
    v21 = a8;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26[0] = a3;
    v26[1] = a4;
    v27 = v12;
    v28 = 0;
    v29 = a8;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    ShaderCache_GetCompilerIdentity(
      *(_QWORD *)this,
      lambda_0d74c186d0cf49bca22ca087075eea2d_::_lambda_invoker_cdecl_,
      &v18);
    ShaderCache_GetApplicationIdentity(
      *(_QWORD *)this,
      lambda_905eb0cc9c2c22f07e9876e56f26c6a7_::_lambda_invoker_cdecl_,
      v26);
    v13 = v22;
    v14 = v30;
    if ( a8 )
    {
      *((_BYTE *)a8 + 1) = v22;
      *((_BYTE *)a8 + 2) = v14;
    }
    if ( *((_DWORD *)a6 + 4) == 3 )
    {
      if ( v13 && v14 )
        v15 = 0;
      else
        v15 = -2005270477;
    }
    else
    {
      if ( !v13 || !v14 )
        ShaderCache_Clear(*(_QWORD *)this);
      v34[0] = *((_QWORD *)a2 + 5);
      v34[1] = *((_QWORD *)a2 + 6);
      v34[2] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      v16 = ShaderCache_SetCompilerIdentity(*(_QWORD *)this, v34);
      ThrowFailure(v16);
      v35[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
      v35[1] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)a3 + 32);
      v35[2] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)a3 + 72);
      v35[3] = *((_QWORD *)a3 + 8);
      v35[4] = *((_QWORD *)a3 + 13);
      v35[5] = *((_QWORD *)a3 + 14);
      v15 = ShaderCache_SetApplicationIdentity(*(_QWORD *)this, v35);
    }
    ThrowFailure(v15);
  }
  return this;
}

```

## disassembly

```asm
0x1800dd154  mov     rax, rsp
0x1800dd157  mov     [rax+10h], rbx
0x1800dd15b  mov     [rax+18h], rsi
0x1800dd15f  mov     [rax+8], rcx
0x1800dd163  push    rbp
0x1800dd164  push    rdi
0x1800dd165  push    r12
0x1800dd167  push    r14
0x1800dd169  push    r15
0x1800dd16b  lea     rbp, [rax-3Fh]
0x1800dd16f  sub     rsp, 0B0h
0x1800dd176  mov     r12, r9
0x1800dd179  mov     r14, r8
0x1800dd17c  mov     r15, rdx
0x1800dd17f  mov     rdi, rcx
0x1800dd182  mov     r9, [rbp+37h+arg_30]; unsigned __int16 *
0x1800dd186  mov     rsi, [rbp+37h+arg_28]
0x1800dd18a  mov     r8, rsi; struct SShaderCacheDesc *
0x1800dd18d  mov     rdx, [rbp+37h+arg_20]; struct SessionUniqueness *
0x1800dd191  call    ??0CShaderCache@@AEAA@AEBUSessionUniqueness@@AEBUSShaderCacheDesc@@PEBG@Z; CShaderCache::CShaderCache(SessionUniqueness const &,SShaderCacheDesc const &,ushort const *)
0x1800dd196  nop
0x1800dd197  mov     rbx, [rbp+37h+arg_38]
0x1800dd19b  test    rbx, rbx
0x1800dd19e  jz      short loc_1800DD1A3
0x1800dd1a0  mov     byte ptr [rbx], 1
0x1800dd1a3  mov     eax, [rsi+10h]
0x1800dd1a6  test    eax, eax
0x1800dd1a8  jz      loc_1800DD2E2
0x1800dd1ae  test    byte ptr [rsi+40h], 4
0x1800dd1b2  jnz     loc_1800DD2E2
0x1800dd1b8  mov     [rbp+37h+var_B0], r15
0x1800dd1bc  mov     [rbp+37h+var_A8], eax
0x1800dd1bf  xor     ecx, ecx
0x1800dd1c1  mov     [rbp+37h+var_A4], ecx
0x1800dd1c4  mov     [rbp+37h+var_A0], rbx
0x1800dd1c8  mov     [rbp+37h+var_98], cl
0x1800dd1cb  mov     [rbp+37h+var_97], ecx
0x1800dd1ce  mov     [rbp+37h+var_93], cx
0x1800dd1d2  mov     [rbp+37h+var_91], cl
0x1800dd1d5  mov     [rbp+37h+var_90], r14
0x1800dd1d9  mov     [rbp+37h+var_88], r12
0x1800dd1dd  mov     [rbp+37h+var_80], eax
0x1800dd1e0  xor     eax, eax
0x1800dd1e2  mov     [rbp+37h+var_7C], eax
0x1800dd1e5  mov     [rbp+37h+var_78], rbx
0x1800dd1e9  mov     [rbp+37h+var_70], al
0x1800dd1ec  mov     [rbp+37h+var_6F], eax
0x1800dd1ef  mov     [rbp+37h+var_6B], ax
0x1800dd1f3  mov     [rbp+37h+var_69], al
0x1800dd1f6  lea     r8, [rbp+37h+var_B0]
0x1800dd1fa  lea     rdx, _lambda_0d74c186d0cf49bca22ca087075eea2d____lambda_invoker_cdecl_
0x1800dd201  mov     rcx, [rdi]
0x1800dd204  call    cs:__imp_ShaderCache_GetCompilerIdentity
0x1800dd20a  lea     r8, [rbp+37h+var_90]
0x1800dd20e  lea     rdx, _lambda_905eb0cc9c2c22f07e9876e56f26c6a7____lambda_invoker_cdecl_
0x1800dd215  mov     rcx, [rdi]
0x1800dd218  call    cs:__imp_ShaderCache_GetApplicationIdentity
0x1800dd21e  mov     cl, [rbp+37h+var_98]
0x1800dd221  mov     al, [rbp+37h+var_70]
0x1800dd224  test    rbx, rbx
0x1800dd227  jz      short loc_1800DD22F
0x1800dd229  mov     [rbx+1], cl
0x1800dd22c  mov     [rbx+2], al
0x1800dd22f  cmp     dword ptr [rsi+10h], 3
0x1800dd233  jnz     short loc_1800DD24E
0x1800dd235  test    cl, cl
0x1800dd237  jz      short loc_1800DD244
0x1800dd239  test    al, al
0x1800dd23b  jz      short loc_1800DD244
0x1800dd23d  xor     ecx, ecx
0x1800dd23f  jmp     loc_1800DD2DC
0x1800dd244  mov     ecx, 887A0033h
0x1800dd249  jmp     loc_1800DD2DC
0x1800dd24e  test    cl, cl
0x1800dd250  jz      short loc_1800DD256
0x1800dd252  test    al, al
0x1800dd254  jnz     short loc_1800DD25F
0x1800dd256  mov     rcx, [rdi]
0x1800dd259  call    cs:__imp_ShaderCache_Clear
0x1800dd25f  mov     rax, [r15+28h]
0x1800dd263  mov     [rbp+37h+var_68], rax
0x1800dd267  mov     rax, [r15+30h]
0x1800dd26b  mov     [rbp+37h+var_60], rax
0x1800dd26f  mov     rcx, r15
0x1800dd272  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800dd277  mov     [rbp+37h+var_58], rax
0x1800dd27b  lea     rdx, [rbp+37h+var_68]
0x1800dd27f  mov     rcx, [rdi]
0x1800dd282  call    cs:__imp_ShaderCache_SetCompilerIdentity
0x1800dd288  mov     ecx, eax; int
0x1800dd28a  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800dd28f  mov     rcx, r14
0x1800dd292  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800dd297  mov     [rbp+37h+var_50], rax
0x1800dd29b  lea     rcx, [r14+20h]
0x1800dd29f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800dd2a4  mov     [rbp+37h+var_48], rax
0x1800dd2a8  lea     rcx, [r14+48h]
0x1800dd2ac  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800dd2b1  mov     [rbp+37h+var_40], rax
0x1800dd2b5  mov     rax, [r14+40h]
0x1800dd2b9  mov     [rbp+37h+var_38], rax
0x1800dd2bd  mov     rax, [r14+68h]
0x1800dd2c1  mov     [rbp+37h+var_30], rax
0x1800dd2c5  mov     rax, [r14+70h]
0x1800dd2c9  mov     [rbp+37h+var_28], rax
0x1800dd2cd  lea     rdx, [rbp+37h+var_50]
0x1800dd2d1  mov     rcx, [rdi]
0x1800dd2d4  call    cs:__imp_ShaderCache_SetApplicationIdentity
0x1800dd2da  mov     ecx, eax; int
0x1800dd2dc  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800dd2e1  nop
0x1800dd2e2  mov     rax, rdi
0x1800dd2e5  lea     r11, [rsp+0D0h+var_20]
0x1800dd2ed  mov     rbx, [r11+38h]
0x1800dd2f1  mov     rsi, [r11+40h]
0x1800dd2f5  mov     rsp, r11
0x1800dd2f8  pop     r15
0x1800dd2fa  pop     r14
0x1800dd2fc  pop     r12
0x1800dd2fe  pop     rdi
0x1800dd2ff  pop     rbp
0x1800dd300  retn
```
