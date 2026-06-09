# ComputerNameNode::AddStringNode(ConfigDataType,tagVARIANT,ICSPNode * *,ulong *,ComputerNameNode * *)

- ea: `0x1800260a0`
- end: `0x180026242`
- name: `?AddStringNode@ComputerNameNode@@SAJW4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAKPEAPEAV1@@Z`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800118a0`

## callees

- `0x1800030e8`
- `0x180006974`
- `0x18000fffc`
- `0x1800260a0`
- `0x180038010`

## string_xrefs

- `0x1800260cb`: `onecoreuap\admin\prov\provcsp\computernamenode.cpp`
- `0x180026156`: `onecoreuap\admin\prov\provcsp\computernamenode.cpp`
- `0x1800261a9`: `onecoreuap\admin\prov\provcsp\computernamenode.cpp`
- `0x1800261fd`: `onecoreuap\admin\prov\provcsp\computernamenode.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ComputerNameNode::AddStringNode(int a1, __int128 *a2, __int64 a3, _DWORD *a4, GenericBStrNode **a5)
{
  unsigned int v8; // ebx
  GenericBStrNode *v10; // rbx
  GenericBStrNode *v11; // rax
  GenericBStrNode *v12; // rdi
  int v13; // eax
  unsigned int v14; // esi
  int v15; // eax
  int v16; // [rsp+20h] [rbp-68h]
  int v17; // [rsp+20h] [rbp-68h]
  __int128 v18; // [rsp+30h] [rbp-58h] BYREF
  __int64 v19; // [rsp+40h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( a1 != 1 )
  {
    v8 = -2046820335;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\computernamenode.cpp",
      (const char *)0x86000011LL,
      v16);
    return v8;
  }
  v10 = 0;
  v17 = 0;
  v11 = (GenericBStrNode *)operator new(0x58u, (const struct std::nothrow_t *)std::nothrow);
  v12 = v11;
  if ( v11 )
  {
    GenericBStrNode::GenericBStrNode(v11);
    *(_QWORD *)v12 = &ComputerNameNode::`vftable'{for `ICSPNode'};
    *((_QWORD *)v12 + 1) = &GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
    *((_QWORD *)v12 + 10) = 7;
    *((_QWORD *)v12 + 9) = 0;
    *((_WORD *)v12 + 28) = 0;
    v10 = v12;
    v17 = (int)v12;
  }
  else
  {
    v12 = 0;
  }
  if ( !v12 )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\computernamenode.cpp",
      (const char *)0x8007000ELL,
      v17);
    return v8;
  }
  if ( *(_WORD *)a2
    && (v18 = *a2,
        v19 = *((_QWORD *)a2 + 2),
        v13 = (*(__int64 (__fastcall **)(GenericBStrNode *, __int128 *))(*(_QWORD *)v12 + 88LL))(v12, &v18),
        v14 = v13,
        v13 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\computernamenode.cpp",
      (const char *)(unsigned int)v13,
      v17);
    (*(void (__fastcall **)(GenericBStrNode *))(*(_QWORD *)v12 + 16LL))(v12);
    return v14;
  }
  else
  {
    if ( a3 )
    {
      v15 = (**(__int64 (__fastcall ***)(GenericBStrNode *, GUID *, __int64))v10)(
              v10,
              &GUID_8a13633c_797d_46e9_b602_d982b8ec9847,
              a3);
      v8 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x31,
          (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\computernamenode.cpp",
          (const char *)(unsigned int)v15,
          v17);
        (*(void (__fastcall **)(GenericBStrNode *))(*(_QWORD *)v12 + 16LL))(v12);
        return v8;
      }
    }
    *a5 = v12;
    *a4 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x1800260a0  push    rbx
0x1800260a2  push    rbp
0x1800260a3  push    rsi
0x1800260a4  push    rdi
0x1800260a5  push    r14
0x1800260a7  push    r15
0x1800260a9  sub     rsp, 58h
0x1800260ad  mov     r14, r9
0x1800260b0  mov     rbp, r8
0x1800260b3  mov     rsi, rdx
0x1800260b6  cmp     ecx, 1
0x1800260b9  jz      short loc_1800260E3
0x1800260bb  mov     rcx, [rsp+88h]; this
0x1800260c3  mov     ebx, 86000011h
0x1800260c8  mov     r9d, ebx; char *
0x1800260cb  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\provcsp\\compu"...
0x1800260d2  mov     edx, 28h ; '('; void *
0x1800260d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800260dc  mov     eax, ebx
0x1800260de  jmp     loc_180026234
0x1800260e3  xor     r15d, r15d
0x1800260e6  mov     ebx, r15d
0x1800260e9  mov     qword ptr [rsp+88h+var_68], rbx; int
0x1800260ee  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800260f5  lea     ecx, [r15+58h]; unsigned __int64
0x1800260f9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800260fe  mov     rdi, rax
0x180026101  test    rax, rax
0x180026104  jz      short loc_18002613E
0x180026106  mov     rcx, rax; this
0x180026109  call    ??0GenericBStrNode@@QEAA@XZ; GenericBStrNode::GenericBStrNode(void)
0x18002610e  lea     rax, ??_7ComputerNameNode@@6BICSPNode@@@; const ComputerNameNode::`vftable'{for `ICSPNode'}
0x180026115  mov     [rdi], rax
0x180026118  lea     rax, ??_7GenericIntNode@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@WRL@Microsoft@@@; const GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x18002611f  mov     [rdi+8], rax
0x180026123  mov     qword ptr [rdi+50h], 7
0x18002612b  mov     [rdi+48h], r15
0x18002612f  mov     [rdi+38h], r15w
0x180026134  mov     rbx, rdi
0x180026137  mov     qword ptr [rsp+88h+var_68], rbx
0x18002613c  jmp     short loc_180026141
0x18002613e  mov     rdi, r15
0x180026141  test    rdi, rdi
0x180026144  jnz     short loc_18002616B
0x180026146  mov     rcx, [rsp+88h]; this
0x18002614e  mov     ebx, 8007000Eh
0x180026153  mov     r9d, ebx; char *
0x180026156  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\provcsp\\compu"...
0x18002615d  lea     edx, [rdi+2Ah]; void *
0x180026160  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026165  nop
0x180026166  jmp     loc_1800260DC
0x18002616b  cmp     [rsi], r15w
0x18002616f  jz      short loc_1800261CF
0x180026171  movaps  xmm0, xmmword ptr [rsi]
0x180026174  movaps  [rsp+88h+var_58], xmm0
0x180026179  movsd   xmm1, qword ptr [rsi+10h]
0x18002617e  movsd   [rsp+88h+var_48], xmm1
0x180026184  mov     rax, [rdi]
0x180026187  lea     rdx, [rsp+88h+var_58]
0x18002618c  mov     rcx, rdi
0x18002618f  mov     rax, [rax+58h]
0x180026193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026198  mov     esi, eax
0x18002619a  test    eax, eax
0x18002619c  jns     short loc_1800261CF
0x18002619e  mov     rcx, [rsp+88h]; this
0x1800261a6  mov     r9d, eax; char *
0x1800261a9  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\provcsp\\compu"...
0x1800261b0  mov     edx, 2Dh ; '-'; void *
0x1800261b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800261ba  nop
0x1800261bb  mov     rdx, [rdi]
0x1800261be  mov     rcx, rdi
0x1800261c1  mov     rax, [rdx+10h]
0x1800261c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261ca  nop
0x1800261cb  mov     eax, esi
0x1800261cd  jmp     short loc_180026234
0x1800261cf  test    rbp, rbp
0x1800261d2  jz      short loc_180026224
0x1800261d4  mov     rax, [rbx]
0x1800261d7  mov     r8, rbp
0x1800261da  lea     rdx, _GUID_8a13633c_797d_46e9_b602_d982b8ec9847
0x1800261e1  mov     rcx, rbx
0x1800261e4  mov     rax, [rax]
0x1800261e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261ec  mov     ebx, eax
0x1800261ee  test    eax, eax
0x1800261f0  jns     short loc_180026224
0x1800261f2  mov     rcx, [rsp+88h]; this
0x1800261fa  mov     r9d, eax; char *
0x1800261fd  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\provcsp\\compu"...
0x180026204  mov     edx, 31h ; '1'; void *
0x180026209  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002620e  nop
0x18002620f  mov     rcx, [rdi]
0x180026212  mov     rax, [rcx+10h]
0x180026216  mov     rcx, rdi
0x180026219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002621e  nop
0x18002621f  jmp     loc_1800260DC
0x180026224  mov     rax, [rsp+88h+arg_20]
0x18002622c  mov     [rax], rdi
0x18002622f  mov     [r14], r15d
0x180026232  xor     eax, eax
0x180026234  add     rsp, 58h
0x180026238  pop     r15
0x18002623a  pop     r14
0x18002623c  pop     rdi
0x18002623d  pop     rsi
0x18002623e  pop     rbp
0x18002623f  pop     rbx
0x180026240  retn
```
