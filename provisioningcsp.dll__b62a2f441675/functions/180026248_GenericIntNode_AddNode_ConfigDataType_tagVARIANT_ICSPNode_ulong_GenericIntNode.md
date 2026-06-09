# GenericIntNode::AddNode(ConfigDataType,tagVARIANT,ICSPNode * *,ulong *,GenericIntNode * *)

- ea: `0x180026248`
- end: `0x1800263c5`
- name: `?AddNode@GenericIntNode@@SAJW4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAKPEAPEAV1@@Z`
- size: `381`
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
- `0x180024764`
- `0x180026248`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GenericIntNode::AddNode(int a1, __int128 *a2, __int64 a3, _DWORD *a4, _QWORD *a5)
{
  __int64 v9; // rbx
  unsigned int v11; // edi
  int v12; // eax
  int v13; // eax
  __int64 v14; // [rsp+20h] [rbp-68h] BYREF
  __int128 v15; // [rsp+30h] [rbp-58h] BYREF
  __int64 v16; // [rsp+40h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  Microsoft::WRL::Details::Make<GenericIntNode,>(&v14);
  v9 = v14;
  if ( !v14 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\genericintnode.cpp",
      (const char *)0x8007000ELL,
      0);
    return 2147942414LL;
  }
  if ( *(_WORD *)a2 )
  {
    if ( a1 )
    {
      v11 = -2046820335;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\genericintnode.cpp",
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
        (void *)0x36,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\genericintnode.cpp",
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
        (void *)0x3A,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\genericintnode.cpp",
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
0x180026248  push    rbx
0x18002624a  push    rbp
0x18002624b  push    rsi
0x18002624c  push    rdi
0x18002624d  push    r14
0x18002624f  push    r15
0x180026251  sub     rsp, 58h
0x180026255  mov     r14, r9
0x180026258  mov     rsi, r8
0x18002625b  mov     rdi, rdx
0x18002625e  mov     ebp, ecx
0x180026260  lea     rcx, [rsp+88h+var_68]
0x180026265  call    ??$Make@VGenericIntNode@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VGenericIntNode@@@12@XZ; Microsoft::WRL::Details::Make<GenericIntNode,>(void)
0x18002626a  nop
0x18002626b  mov     rbx, [rsp+88h+var_68]
0x180026270  xor     r15d, r15d
0x180026273  test    rbx, rbx
0x180026276  jnz     short loc_1800262A0
0x180026278  mov     rcx, [rsp+88h]; this
0x180026280  mov     ebx, 8007000Eh
0x180026285  mov     r9d, ebx; char *
0x180026288  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\provcsp\\gener"...
0x18002628f  lea     edx, [r15+32h]; void *
0x180026293  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026298  nop
0x180026299  mov     eax, ebx
0x18002629b  jmp     loc_1800263B7
0x1800262a0  cmp     [rdi], r15w
0x1800262a4  jz      loc_18002634D
0x1800262aa  test    ebp, ebp
0x1800262ac  jz      short loc_1800262EC
0x1800262ae  mov     rcx, [rsp+88h]; this
0x1800262b6  mov     edi, 86000011h
0x1800262bb  mov     r9d, edi; char *
0x1800262be  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\provcsp\\gener"...
0x1800262c5  mov     edx, 35h ; '5'; void *
0x1800262ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800262cf  nop
0x1800262d0  test    rbx, rbx
0x1800262d3  jz      short loc_1800262E5
0x1800262d5  mov     rcx, [rbx]
0x1800262d8  mov     rax, [rcx+10h]
0x1800262dc  mov     rcx, rbx
0x1800262df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262e4  nop
0x1800262e5  mov     eax, edi
0x1800262e7  jmp     loc_1800263B7
0x1800262ec  movaps  xmm0, xmmword ptr [rdi]
0x1800262ef  movaps  [rsp+88h+var_58], xmm0
0x1800262f4  movsd   xmm1, qword ptr [rdi+10h]
0x1800262f9  movsd   [rsp+88h+var_48], xmm1
0x1800262ff  mov     rax, [rbx]
0x180026302  lea     rdx, [rsp+88h+var_58]
0x180026307  mov     rcx, rbx
0x18002630a  mov     rax, [rax+58h]
0x18002630e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026313  mov     edi, eax
0x180026315  test    eax, eax
0x180026317  jns     short loc_18002634D
0x180026319  mov     rcx, [rsp+88h]; this
0x180026321  mov     r9d, eax; char *
0x180026324  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\provcsp\\gener"...
0x18002632b  mov     edx, 36h ; '6'; void *
0x180026330  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026335  nop
0x180026336  test    rbx, rbx
0x180026339  jz      short loc_18002634B
0x18002633b  mov     rax, [rbx]
0x18002633e  mov     rcx, rbx
0x180026341  mov     rax, [rax+10h]
0x180026345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002634a  nop
0x18002634b  jmp     short loc_1800262E5
0x18002634d  test    rsi, rsi
0x180026350  jz      short loc_1800263A7
0x180026352  mov     rax, [rbx]
0x180026355  mov     r8, rsi
0x180026358  lea     rdx, _GUID_8a13633c_797d_46e9_b602_d982b8ec9847
0x18002635f  mov     rcx, rbx
0x180026362  mov     rax, [rax]
0x180026365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002636a  mov     edi, eax
0x18002636c  test    eax, eax
0x18002636e  jns     short loc_1800263A7
0x180026370  mov     rcx, [rsp+88h]; this
0x180026378  mov     r9d, eax; char *
0x18002637b  lea     r8, aOnecoreuapAdmi_30; "onecoreuap\\admin\\prov\\provcsp\\gener"...
0x180026382  mov     edx, 3Ah ; ':'; void *
0x180026387  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002638c  nop
0x18002638d  test    rbx, rbx
0x180026390  jz      short loc_1800263A2
0x180026392  mov     rax, [rbx]
0x180026395  mov     rcx, rbx
0x180026398  mov     rax, [rax+10h]
0x18002639c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263a1  nop
0x1800263a2  jmp     loc_1800262E5
0x1800263a7  mov     rax, [rsp+88h+arg_20]
0x1800263af  mov     [rax], rbx
0x1800263b2  mov     [r14], r15d
0x1800263b5  xor     eax, eax
0x1800263b7  add     rsp, 58h
0x1800263bb  pop     r15
0x1800263bd  pop     r14
0x1800263bf  pop     rdi
0x1800263c0  pop     rsi
0x1800263c1  pop     rbp
0x1800263c2  pop     rbx
0x1800263c3  retn
```
