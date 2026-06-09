# UnDecorator::getZName(bool,bool)

- ea: `0x18001f680`
- end: `0x18001f933`
- name: `?getZName@UnDecorator@@AEAA?AVDName@@_N0@Z`
- size: `691`
- prototype: ``
- caller_count: `10`
- callee_count: `13`
- tags: ``

## callers

- `0x18001c0e8`
- `0x18001e638`
- `0x18001f224`
- `0x18001f93c`
- `0x18001fcf8`
- `0x180020b5c`
- `0x18002246c`
- `0x1801d4968`
- `0x1801d5284`
- `0x1801d5be4`

## callees

- `0x1800106ac`
- `0x180010860`
- `0x180010e10`
- `0x180011010`
- `0x1800148d0`
- `0x18001aa78`
- `0x18001f680`
- `0x18001f93c`
- `0x18001fc40`
- `0x1801d46c0`
- `0x1801d54c0`
- `0x1801d6350`
- `0x180205010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_atol` at `0x18001f829`
- `api-ms-win-crt-private-l1-1-0!_o_atol` at `0x18001f829`

## string_xrefs

- `0x18001f74d`: `template-parameter-`
- `0x18001f777`: ``template-parameter-`

## pseudocode

```c
__int64 __fastcall UnDecorator::getZName(__int64 a1, __int64 a2, char a3, char a4)
{
  const char **v5; // r15
  _BYTE *v6; // r10
  __int64 v9; // rcx
  bool v10; // zf
  __int64 v11; // r12
  __int64 TemplateName; // rax
  const char *v13; // rcx
  __int64 v14; // rbx
  int v15; // edi
  char v16; // al
  const char *v17; // rax
  _BYTE *v18; // rcx
  int v19; // r8d
  const char *v20; // rax
  const char *v21; // rax
  const char *v22; // r10
  const char *v23; // rax
  _BYTE *v24; // rdx
  int v25; // r8d
  __int64 (__fastcall *v26)(_QWORD); // rbx
  unsigned int v27; // eax
  __int64 v28; // rax
  DName *v29; // rax
  __int64 v30; // rax
  __int64 v31; // r8
  char *v32; // rdx
  int *v33; // rsi
  _QWORD *v34; // rax
  __int64 v35; // rdx
  const char *v37; // [rsp+20h] [rbp-69h] BYREF
  __int64 v38; // [rsp+28h] [rbp-61h]
  _BYTE v39[24]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v40[24]; // [rsp+58h] [rbp-31h] BYREF
  char v41[24]; // [rsp+70h] [rbp-19h] BYREF
  char String[16]; // [rsp+88h] [rbp-1h] BYREF
  int v43; // [rsp+98h] [rbp+Fh]

  v5 = (const char **)(a1 + 256);
  v6 = *(_BYTE **)(a1 + 256);
  if ( (unsigned int)((char)*v6 - 48) <= 9 )
  {
    v9 = *(_QWORD *)(a1 + 200);
    *v5 = v6 + 1;
    Replicator::operator[](v9, a2);
    return a2;
  }
  v10 = *v6 == 63;
  v11 = a1;
  *(_QWORD *)&String[8] = a1;
  if ( v10 )
  {
    TemplateName = UnDecorator::getTemplateName(a1, v39, 0);
    v13 = *v5;
    v14 = *(_QWORD *)TemplateName;
    v15 = *(_DWORD *)(TemplateName + 16);
    v16 = **v5;
    *(_QWORD *)String = v14;
    v43 = v15;
    if ( v16 != 64 )
    {
      DName::operator=(String, (unsigned int)(v16 != 0) + 1);
      v15 = v43;
      v11 = *(_QWORD *)&String[8];
      v14 = *(_QWORD *)String;
      goto LABEL_32;
    }
    v17 = v13 + 1;
    goto LABEL_29;
  }
  v18 = v6;
  *(_DWORD *)&String[12] = 0;
  v19 = 18;
  v20 = "template-parameter-";
  do
  {
    if ( !*v18 )
      break;
    if ( *v18 != *v20 )
      break;
    ++v18;
    ++v20;
    --v19;
  }
  while ( v19 );
  if ( *v18 == *v20 )
  {
    v21 = "`template-parameter-";
    v38 = 20;
    v22 = v6 + 19;
LABEL_19:
    v37 = v21;
    *v5 = v22;
    UnDecorator::getSignedDimension(a1, v39);
    if ( (*(_DWORD *)(a1 + 272) & 0x4000) != 0 && *(_QWORD *)(a1 + 280) )
    {
      *(_OWORD *)String = 0;
      DName::getString((DName *)v39, String, 16);
      v26 = *(__int64 (__fastcall **)(_QWORD))(a1 + 280);
      v27 = atol(String);
      v28 = v26(v27);
      if ( v28 )
      {
        v29 = (DName *)DName::DName(&v37, a1, v28);
        goto LABEL_31;
      }
      v30 = operator+((DName *)v41);
      v32 = v40;
    }
    else
    {
      v30 = operator+((DName *)v40);
      v32 = v41;
    }
    LOBYTE(v31) = 39;
    v29 = (DName *)DName::operator+(v30, v32, v31);
    goto LABEL_31;
  }
  v23 = "generic-type-";
  v24 = v6;
  v25 = 12;
  do
  {
    if ( !*v24 )
      break;
    if ( *v24 != *v23 )
      break;
    ++v24;
    ++v23;
    --v25;
  }
  while ( v25 );
  if ( *v24 == *v23 )
  {
    v21 = "`generic-type-";
    v38 = 14;
    v22 = v6 + 13;
    goto LABEL_19;
  }
  if ( a4 && *v6 == 64 )
  {
    v14 = 0;
    v17 = v6 + 1;
    v15 = 0;
LABEL_29:
    *v5 = v17;
    goto LABEL_32;
  }
  v29 = DName::DName((DName *)v40, (struct UnDecorator *)a1, v5, a4);
LABEL_31:
  v15 = *((_DWORD *)v29 + 4);
  v14 = *(_QWORD *)v29;
LABEL_32:
  if ( a3 )
  {
    v33 = *(int **)(a1 + 200);
    if ( *v33 != 9 )
    {
      if ( v14 )
      {
        v34 = operator new(0x18u, (struct _HeapManager *)(*((_QWORD *)v33 + 11) + 216LL), 0);
        if ( v34 )
        {
          v34[1] = v11;
          *v34 = v14;
          *((_DWORD *)v34 + 4) = v15;
          v35 = *v33;
          *v33 = v35 + 1;
          *(_QWORD *)&v33[2 * v35 + 4] = v34;
        }
      }
    }
  }
  *(_QWORD *)(a2 + 8) = v11;
  *(_QWORD *)a2 = v14;
  *(_DWORD *)(a2 + 16) = v15;
  return a2;
}

```

## disassembly

```asm
0x18001f680  mov     [rsp-8+arg_10], rbx
0x18001f685  push    rbp
0x18001f686  push    rsi
0x18001f687  push    rdi
0x18001f688  push    r12
0x18001f68a  push    r13
0x18001f68c  push    r14
0x18001f68e  push    r15
0x18001f690  lea     rbp, [rsp-27h]
0x18001f695  sub     rsp, 0B0h
0x18001f69c  mov     rax, cs:__security_cookie
0x18001f6a3  xor     rax, rsp
0x18001f6a6  mov     [rbp+57h+var_40], rax
0x18001f6aa  mov     r13b, r8b
0x18001f6ad  lea     r15, [rcx+100h]
0x18001f6b4  mov     r10, [r15]
0x18001f6b7  mov     r14, rdx
0x18001f6ba  mov     rsi, rcx
0x18001f6bd  movsx   r8d, byte ptr [r10]
0x18001f6c1  add     r8d, 0FFFFFFD0h
0x18001f6c5  cmp     r8d, 9
0x18001f6c9  ja      short loc_18001F6E6
0x18001f6cb  mov     rcx, [rcx+0C8h]
0x18001f6d2  lea     rdx, [r10+1]
0x18001f6d6  mov     [r15], rdx
0x18001f6d9  mov     rdx, r14
0x18001f6dc  call    ??AReplicator@@QEBA?AVDName@@H@Z; Replicator::operator[](int)
0x18001f6e1  jmp     loc_18001F909
0x18001f6e6  cmp     byte ptr [r10], 3Fh ; '?'
0x18001f6ea  mov     r12, rsi
0x18001f6ed  mov     qword ptr [rbp+57h+String+8], rsi
0x18001f6f1  jnz     short loc_18001F73F
0x18001f6f3  xor     r8d, r8d
0x18001f6f6  lea     rdx, [rbp+57h+var_A0]
0x18001f6fa  call    ?getTemplateName@UnDecorator@@AEAA?AVDName@@_N@Z; UnDecorator::getTemplateName(bool)
0x18001f6ff  mov     rcx, [r15]
0x18001f702  mov     rbx, [rax]
0x18001f705  mov     edi, [rax+10h]
0x18001f708  mov     al, [rcx]
0x18001f70a  mov     qword ptr [rbp+57h+String], rbx
0x18001f70e  mov     [rbp+57h+var_48], edi
0x18001f711  cmp     al, 40h ; '@'
0x18001f713  jnz     short loc_18001F71E
0x18001f715  lea     rax, [rcx+1]
0x18001f719  jmp     loc_18001F89B
0x18001f71e  neg     al
0x18001f720  lea     rcx, [rbp+57h+String]
0x18001f724  sbb     edx, edx
0x18001f726  neg     edx
0x18001f728  inc     edx
0x18001f72a  call    ??4DName@@QEAAAEAV0@W4DNameStatus@@@Z; DName::operator=(DNameStatus)
0x18001f72f  mov     edi, [rbp+57h+var_48]
0x18001f732  mov     r12, qword ptr [rbp+57h+String+8]
0x18001f736  mov     rbx, qword ptr [rbp+57h+String]
0x18001f73a  jmp     loc_18001F8B5
0x18001f73f  xor     eax, eax
0x18001f741  mov     rcx, r10
0x18001f744  mov     dword ptr [rbp+57h+String+0Ch], eax
0x18001f747  mov     r8d, 12h
0x18001f74d  lea     rax, aTemplateParame_0; "template-parameter-"
0x18001f754  or      r11d, 0FFFFFFFFh
0x18001f758  mov     dl, [rcx]
0x18001f75a  test    dl, dl
0x18001f75c  jz      short loc_18001F76D
0x18001f75e  cmp     dl, [rax]
0x18001f760  jnz     short loc_18001F76D
0x18001f762  inc     rcx
0x18001f765  inc     rax
0x18001f768  add     r8d, r11d
0x18001f76b  jnz     short loc_18001F758
0x18001f76d  movzx   ecx, byte ptr [rcx]
0x18001f770  movzx   eax, byte ptr [rax]
0x18001f773  cmp     ecx, eax
0x18001f775  jnz     short loc_18001F78C
0x18001f777  lea     rax, aTemplateParame_1; "`template-parameter-"
0x18001f77e  mov     qword ptr [rbp+57h+var_C0+8], 14h
0x18001f786  add     r10, 13h
0x18001f78a  jmp     short loc_18001F7D2
0x18001f78c  lea     rax, aGenericType_0; "generic-type-"
0x18001f793  mov     rdx, r10
0x18001f796  mov     r8d, 0Ch
0x18001f79c  mov     cl, [rdx]
0x18001f79e  test    cl, cl
0x18001f7a0  jz      short loc_18001F7B1
0x18001f7a2  cmp     cl, [rax]
0x18001f7a4  jnz     short loc_18001F7B1
0x18001f7a6  inc     rdx
0x18001f7a9  inc     rax
0x18001f7ac  add     r8d, r11d
0x18001f7af  jnz     short loc_18001F79C
0x18001f7b1  movzx   ecx, byte ptr [rax]
0x18001f7b4  movzx   eax, byte ptr [rdx]
0x18001f7b7  cmp     eax, ecx
0x18001f7b9  jnz     loc_18001F888
0x18001f7bf  lea     rax, aGenericType; "`generic-type-"
0x18001f7c6  mov     qword ptr [rbp+57h+var_C0+8], 0Eh
0x18001f7ce  add     r10, 0Dh
0x18001f7d2  mov     qword ptr [rbp+57h+var_C0], rax
0x18001f7d6  lea     rdx, [rbp+57h+var_A0]
0x18001f7da  movaps  xmm0, [rbp+57h+var_C0]
0x18001f7de  mov     rcx, rsi
0x18001f7e1  movdqa  [rbp+57h+var_C0], xmm0
0x18001f7e6  mov     [r15], r10
0x18001f7e9  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x18001f7ee  test    dword ptr [rsi+110h], 4000h
0x18001f7f8  jz      short loc_18001F871
0x18001f7fa  cmp     qword ptr [rsi+118h], 0
0x18001f802  jz      short loc_18001F871
0x18001f804  xorps   xmm0, xmm0
0x18001f807  lea     rdx, [rbp+57h+String]; char *
0x18001f80b  mov     r8d, 10h; int
0x18001f811  lea     rcx, [rbp+57h+var_A0]; this
0x18001f815  movups  xmmword ptr [rbp+57h+String], xmm0
0x18001f819  call    ?getString@DName@@QEBAPEADPEADH@Z; DName::getString(char *,int)
0x18001f81e  mov     rbx, [rsi+118h]
0x18001f825  lea     rcx, [rbp+57h+String]; String
0x18001f829  call    cs:__imp_atol
0x18001f82f  mov     ecx, eax
0x18001f831  mov     rax, rbx
0x18001f834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f839  test    rax, rax
0x18001f83c  jz      short loc_18001F84F
0x18001f83e  mov     r8, rax
0x18001f841  lea     rcx, [rbp+57h+var_C0]
0x18001f845  mov     rdx, rsi
0x18001f848  call    ??$?0$01@DName@@QEAA@PEAVUnDecorator@@PEBDU?$StringLifeSelector@$01@@@Z; DName::DName(UnDecorator *,char const *,StringLifeSelector<2>)
0x18001f84d  jmp     short loc_18001F8AF
0x18001f84f  lea     r8, [rbp+57h+var_A0]
0x18001f853  lea     rdx, [rbp+57h+var_C0]
0x18001f857  lea     rcx, [rbp+57h+var_70]; this
0x18001f85b  call    ??H@YA?AVDName@@AEBUStringLiteral@@AEBV0@@Z; operator+(StringLiteral const &,DName const &)
0x18001f860  lea     rdx, [rbp+57h+var_88]
0x18001f864  mov     r8b, 27h ; '''
0x18001f867  mov     rcx, rax
0x18001f86a  call    ??HDName@@QEBA?AV0@D@Z; DName::operator+(char)
0x18001f86f  jmp     short loc_18001F8AF
0x18001f871  lea     r8, [rbp+57h+var_A0]
0x18001f875  lea     rdx, [rbp+57h+var_C0]
0x18001f879  lea     rcx, [rbp+57h+var_88]; this
0x18001f87d  call    ??H@YA?AVDName@@AEBUStringLiteral@@AEBV0@@Z; operator+(StringLiteral const &,DName const &)
0x18001f882  lea     rdx, [rbp+57h+var_70]
0x18001f886  jmp     short loc_18001F864
0x18001f888  test    r9b, r9b
0x18001f88b  jz      short loc_18001F8A0
0x18001f88d  cmp     byte ptr [r10], 40h ; '@'
0x18001f891  jnz     short loc_18001F8A0
0x18001f893  xor     ebx, ebx
0x18001f895  lea     rax, [r10+1]
0x18001f899  xor     edi, edi
0x18001f89b  mov     [r15], rax
0x18001f89e  jmp     short loc_18001F8B5
0x18001f8a0  mov     r8, r15; char **
0x18001f8a3  lea     rcx, [rbp+57h+var_88]; this
0x18001f8a7  mov     rdx, rsi; struct UnDecorator *
0x18001f8aa  call    ??0DName@@QEAA@PEAVUnDecorator@@AEAPEBDD@Z; DName::DName(UnDecorator *,char const * &,char)
0x18001f8af  mov     edi, [rax+10h]
0x18001f8b2  mov     rbx, [rax]
0x18001f8b5  test    r13b, r13b
0x18001f8b8  jz      short loc_18001F8FE
0x18001f8ba  mov     rsi, [rsi+0C8h]
0x18001f8c1  cmp     dword ptr [rsi], 9
0x18001f8c4  jz      short loc_18001F8FE
0x18001f8c6  test    rbx, rbx
0x18001f8c9  jz      short loc_18001F8FE
0x18001f8cb  mov     rdx, [rsi+58h]
0x18001f8cf  xor     r8d, r8d; int
0x18001f8d2  add     rdx, 0D8h; struct _HeapManager *
0x18001f8d9  lea     ecx, [r8+18h]; unsigned __int64
0x18001f8dd  call    ??2@YAPEAX_KAEAV_HeapManager@@H@Z; operator new(unsigned __int64,_HeapManager &,int)
0x18001f8e2  test    rax, rax
0x18001f8e5  jz      short loc_18001F8FE
0x18001f8e7  mov     [rax+8], r12
0x18001f8eb  mov     [rax], rbx
0x18001f8ee  mov     [rax+10h], edi
0x18001f8f1  movsxd  rdx, dword ptr [rsi]
0x18001f8f4  lea     ecx, [rdx+1]
0x18001f8f7  mov     [rsi], ecx
0x18001f8f9  mov     [rsi+rdx*8+10h], rax
0x18001f8fe  mov     [r14+8], r12
0x18001f902  mov     [r14], rbx
0x18001f905  mov     [r14+10h], edi
0x18001f909  mov     rax, r14
0x18001f90c  mov     rcx, [rbp+57h+var_40]
0x18001f910  xor     rcx, rsp; StackCookie
0x18001f913  call    __security_check_cookie
0x18001f918  mov     rbx, [rsp+0E0h+arg_10]
0x18001f920  add     rsp, 0B0h
0x18001f927  pop     r15
0x18001f929  pop     r14
0x18001f92b  pop     r13
0x18001f92d  pop     r12
0x18001f92f  pop     rdi
0x18001f930  pop     rsi
0x18001f931  pop     rbp
0x18001f932  retn
```
