# GenericBStrNode::AddStringNode(ConfigDataType,tagVARIANT,ICSPNode * *,ulong *,GenericBStrNode * *)

- ea: `0x180022e48`
- end: `0x180022fc6`
- name: `?AddStringNode@GenericBStrNode@@SAJW4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAKPEAPEAV1@@Z`
- size: `382`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800118a0`
- `0x180014870`
- `0x180024980`

## callees

- `0x180006974`
- `0x180010b00`
- `0x180022e48`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GenericBStrNode::AddStringNode(int a1, __int128 *a2, __int64 a3, _DWORD *a4, _QWORD *a5)
{
  __int64 v9; // rbx
  unsigned int v11; // edi
  int v12; // eax
  int v13; // eax
  __int64 v14; // [rsp+20h] [rbp-68h] BYREF
  __int128 v15; // [rsp+30h] [rbp-58h] BYREF
  __int64 v16; // [rsp+40h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  Microsoft::WRL::Details::Make<GenericBStrNode,>(&v14);
  v9 = v14;
  if ( !v14 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\genericbstrnode.cpp",
      (const char *)0x8007000ELL,
      0);
    return 2147942414LL;
  }
  if ( *(_WORD *)a2 )
  {
    if ( a1 != 1 )
    {
      v11 = -2046820335;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\genericbstrnode.cpp",
        (const char *)0x86000011LL,
        v14);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      return v11;
    }
    v15 = *a2;
    v16 = *((_QWORD *)a2 + 2);
    v12 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v14 + 88LL))(v14, &v15);
    v11 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\genericbstrnode.cpp",
        (const char *)(unsigned int)v12,
        v14);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      return v11;
    }
  }
  if ( a3 )
  {
    v13 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64))v9)(v9, &GUID_8a13633c_797d_46e9_b602_d982b8ec9847, a3);
    v11 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\genericbstrnode.cpp",
        (const char *)(unsigned int)v13,
        v14);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      return v11;
    }
  }
  *a5 = v9;
  *a4 = 0;
  return 0;
}

```

## disassembly

```asm
0x180022e48  push    rbx
0x180022e4a  push    rbp
0x180022e4b  push    rsi
0x180022e4c  push    rdi
0x180022e4d  push    r14
0x180022e4f  push    r15
0x180022e51  sub     rsp, 58h
0x180022e55  mov     r14, r9
0x180022e58  mov     rsi, r8
0x180022e5b  mov     rdi, rdx
0x180022e5e  mov     ebp, ecx
0x180022e60  lea     rcx, [rsp+88h+var_68]
0x180022e65  call    ??$Make@VGenericBStrNode@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VGenericBStrNode@@@12@XZ; Microsoft::WRL::Details::Make<GenericBStrNode,>(void)
0x180022e6a  nop
0x180022e6b  mov     rbx, [rsp+88h+var_68]
0x180022e70  xor     r15d, r15d
0x180022e73  test    rbx, rbx
0x180022e76  jnz     short loc_180022EA0
0x180022e78  mov     rcx, [rsp+88h]; this
0x180022e80  mov     ebx, 8007000Eh
0x180022e85  mov     r9d, ebx; char *
0x180022e88  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\provcsp\\gener"...
0x180022e8f  lea     edx, [r15+3Ch]; void *
0x180022e93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022e98  nop
0x180022e99  mov     eax, ebx
0x180022e9b  jmp     loc_180022FB8
0x180022ea0  cmp     [rdi], r15w
0x180022ea4  jz      loc_180022F4E
0x180022eaa  cmp     ebp, 1
0x180022ead  jz      short loc_180022EED
0x180022eaf  mov     rcx, [rsp+88h]; this
0x180022eb7  mov     edi, 86000011h
0x180022ebc  mov     r9d, edi; char *
0x180022ebf  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\provcsp\\gener"...
0x180022ec6  mov     edx, 3Fh ; '?'; void *
0x180022ecb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022ed0  nop
0x180022ed1  test    rbx, rbx
0x180022ed4  jz      short loc_180022EE6
0x180022ed6  mov     rcx, [rbx]
0x180022ed9  mov     rax, [rcx+10h]
0x180022edd  mov     rcx, rbx
0x180022ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ee5  nop
0x180022ee6  mov     eax, edi
0x180022ee8  jmp     loc_180022FB8
0x180022eed  movaps  xmm0, xmmword ptr [rdi]
0x180022ef0  movaps  [rsp+88h+var_58], xmm0
0x180022ef5  movsd   xmm1, qword ptr [rdi+10h]
0x180022efa  movsd   [rsp+88h+var_48], xmm1
0x180022f00  mov     rax, [rbx]
0x180022f03  lea     rdx, [rsp+88h+var_58]
0x180022f08  mov     rcx, rbx
0x180022f0b  mov     rax, [rax+58h]
0x180022f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f14  mov     edi, eax
0x180022f16  test    eax, eax
0x180022f18  jns     short loc_180022F4E
0x180022f1a  mov     rcx, [rsp+88h]; this
0x180022f22  mov     r9d, eax; char *
0x180022f25  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\provcsp\\gener"...
0x180022f2c  mov     edx, 40h ; '@'; void *
0x180022f31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022f36  nop
0x180022f37  test    rbx, rbx
0x180022f3a  jz      short loc_180022F4C
0x180022f3c  mov     rax, [rbx]
0x180022f3f  mov     rcx, rbx
0x180022f42  mov     rax, [rax+10h]
0x180022f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f4b  nop
0x180022f4c  jmp     short loc_180022EE6
0x180022f4e  test    rsi, rsi
0x180022f51  jz      short loc_180022FA8
0x180022f53  mov     rax, [rbx]
0x180022f56  mov     r8, rsi
0x180022f59  lea     rdx, _GUID_8a13633c_797d_46e9_b602_d982b8ec9847
0x180022f60  mov     rcx, rbx
0x180022f63  mov     rax, [rax]
0x180022f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f6b  mov     edi, eax
0x180022f6d  test    eax, eax
0x180022f6f  jns     short loc_180022FA8
0x180022f71  mov     rcx, [rsp+88h]; this
0x180022f79  mov     r9d, eax; char *
0x180022f7c  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\provcsp\\gener"...
0x180022f83  mov     edx, 44h ; 'D'; void *
0x180022f88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022f8d  nop
0x180022f8e  test    rbx, rbx
0x180022f91  jz      short loc_180022FA3
0x180022f93  mov     rax, [rbx]
0x180022f96  mov     rcx, rbx
0x180022f99  mov     rax, [rax+10h]
0x180022f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022fa2  nop
0x180022fa3  jmp     loc_180022EE6
0x180022fa8  mov     rax, [rsp+88h+arg_20]
0x180022fb0  mov     [rax], rbx
0x180022fb3  mov     [r14], r15d
0x180022fb6  xor     eax, eax
0x180022fb8  add     rsp, 58h
0x180022fbc  pop     r15
0x180022fbe  pop     r14
0x180022fc0  pop     rdi
0x180022fc1  pop     rsi
0x180022fc2  pop     rbp
0x180022fc3  pop     rbx
0x180022fc4  retn
```
