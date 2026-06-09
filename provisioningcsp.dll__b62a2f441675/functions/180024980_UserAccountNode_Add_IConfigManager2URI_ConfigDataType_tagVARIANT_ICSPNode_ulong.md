# UserAccountNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x180024980`
- end: `0x180024b94`
- name: `?Add@UserAccountNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `532`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006974`
- `0x180022e48`
- `0x180024980`
- `0x180026248`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180024a25`
- `msvcrt!_wcsicmp` at `0x180024a9e`
- `msvcrt!_wcsicmp` at `0x180024b13`
- `msvcrt!_wcsicmp` at `0x180024a25`
- `msvcrt!_wcsicmp` at `0x180024a9e`
- `msvcrt!_wcsicmp` at `0x180024b13`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserAccountNode::Add(_QWORD *a1, __int64 a2, unsigned int a3, __int128 *a4, __int64 a5, __int64 a6)
{
  int v10; // ebx
  __int64 v11; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // [rsp+20h] [rbp-48h]
  wchar_t *String1; // [rsp+30h] [rbp-38h] BYREF
  __int128 v18; // [rsp+40h] [rbp-28h] BYREF
  __int64 v19; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  int v21; // [rsp+A8h] [rbp+40h] BYREF

  v21 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 136LL))(a2, &v21);
  if ( v10 < 0 )
  {
    v11 = 67;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\useraccount.cpp",
      (const char *)(unsigned int)v10,
      v16);
    return (unsigned int)v10;
  }
  if ( v21 != 1 )
  {
    v10 = -2147024809;
    v11 = 68;
    goto LABEL_3;
  }
  String1 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t **))(*(_QWORD *)a2 + 88LL))(a2, 0, &String1);
  if ( v10 < 0 )
  {
    v11 = 71;
    goto LABEL_3;
  }
  if ( !_wcsicmp(String1, L"Password") )
  {
    v13 = a1[8];
    if ( v13 )
    {
      a1[8] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v18 = *a4;
    v19 = *((_QWORD *)a4 + 2);
    v16 = (_DWORD)a1 + 64;
    v10 = GenericBStrNode::AddStringNode(a3, &v18, a5, a6);
    if ( v10 < 0 )
    {
      v11 = 75;
      goto LABEL_3;
    }
    return 0;
  }
  if ( !_wcsicmp(String1, L"LocalUserGroup") )
  {
    v14 = a1[9];
    if ( v14 )
    {
      a1[9] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v18 = *a4;
    v19 = *((_QWORD *)a4 + 2);
    v16 = (_DWORD)a1 + 72;
    v10 = GenericIntNode::AddNode(a3, &v18, a5, a6);
    if ( v10 < 0 )
    {
      v11 = 79;
      goto LABEL_3;
    }
    return 0;
  }
  if ( !_wcsicmp(String1, L"HomeDir") )
  {
    v15 = a1[10];
    if ( v15 )
    {
      a1[10] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v18 = *a4;
    v19 = *((_QWORD *)a4 + 2);
    v16 = (_DWORD)a1 + 80;
    v10 = GenericBStrNode::AddStringNode(a3, &v18, a5, a6);
    if ( v10 < 0 )
    {
      v11 = 83;
      goto LABEL_3;
    }
    return 0;
  }
  return 2248146946LL;
}

```

## disassembly

```asm
0x180024980  push    rbp
0x180024982  push    rbx
0x180024983  push    rsi
0x180024984  push    rdi
0x180024985  push    r14
0x180024987  push    r15
0x180024989  mov     rbp, rsp
0x18002498c  sub     rsp, 68h
0x180024990  mov     rsi, r9
0x180024993  mov     r15d, r8d
0x180024996  mov     r14, rdx
0x180024999  mov     rdi, rcx
0x18002499c  mov     [rbp+arg_8], 0
0x1800249a3  mov     rax, [rdx]
0x1800249a6  lea     rdx, [rbp+arg_8]
0x1800249aa  mov     rcx, r14
0x1800249ad  mov     rax, [rax+88h]
0x1800249b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249b9  mov     ebx, eax
0x1800249bb  test    eax, eax
0x1800249bd  jns     short loc_1800249DE
0x1800249bf  mov     edx, 43h ; 'C'; void *
0x1800249c4  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provcsp\\usera"...
0x1800249cb  mov     r9d, ebx; char *
0x1800249ce  mov     rcx, [rbp+30h]; this
0x1800249d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800249d7  mov     eax, ebx
0x1800249d9  jmp     loc_180024B86
0x1800249de  cmp     [rbp+arg_8], 1
0x1800249e2  jz      short loc_1800249F0
0x1800249e4  mov     ebx, 80070057h
0x1800249e9  mov     edx, 44h ; 'D'
0x1800249ee  jmp     short loc_1800249C4
0x1800249f0  mov     [rbp+String1], 0
0x1800249f8  mov     rax, [r14]
0x1800249fb  lea     r8, [rbp+String1]
0x1800249ff  xor     edx, edx
0x180024a01  mov     rcx, r14
0x180024a04  mov     rax, [rax+58h]
0x180024a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a0d  mov     ebx, eax
0x180024a0f  test    eax, eax
0x180024a11  jns     short loc_180024A1A
0x180024a13  mov     edx, 47h ; 'G'
0x180024a18  jmp     short loc_1800249C4
0x180024a1a  lea     rdx, ?gc_wszAccountsLocalUserPasswordNode@@3QBGB; "Password"
0x180024a21  mov     rcx, [rbp+String1]; String1
0x180024a25  call    cs:__imp__wcsicmp
0x180024a2c  nop     dword ptr [rax+rax+00h]
0x180024a31  test    eax, eax
0x180024a33  jnz     short loc_180024A93
0x180024a35  lea     rbx, [rdi+40h]
0x180024a39  mov     rcx, [rbx]
0x180024a3c  test    rcx, rcx
0x180024a3f  jz      short loc_180024A55
0x180024a41  mov     qword ptr [rbx], 0
0x180024a48  mov     rax, [rcx]
0x180024a4b  mov     rax, [rax+10h]
0x180024a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a54  nop
0x180024a55  movups  xmm0, xmmword ptr [rsi]
0x180024a58  movaps  [rbp+var_28], xmm0
0x180024a5c  movsd   xmm1, qword ptr [rsi+10h]
0x180024a61  movsd   [rbp+var_18], xmm1
0x180024a66  mov     qword ptr [rsp+68h+var_48], rbx
0x180024a6b  mov     r9, [rbp+arg_28]
0x180024a6f  mov     r8, [rbp+arg_20]
0x180024a73  lea     rdx, [rbp+var_28]
0x180024a77  mov     ecx, r15d
0x180024a7a  call    ?AddStringNode@GenericBStrNode@@SAJW4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAKPEAPEAV1@@Z; GenericBStrNode::AddStringNode(ConfigDataType,tagVARIANT,ICSPNode * *,ulong *,GenericBStrNode * *)
0x180024a7f  mov     ebx, eax
0x180024a81  test    eax, eax
0x180024a83  jns     loc_180024B7D
0x180024a89  mov     edx, 4Bh ; 'K'
0x180024a8e  jmp     loc_1800249C4
0x180024a93  lea     rdx, ?gc_wszAccountsLocalUserGroupNode@@3QBGB; "LocalUserGroup"
0x180024a9a  mov     rcx, [rbp+String1]; String1
0x180024a9e  call    cs:__imp__wcsicmp
0x180024aa5  nop     dword ptr [rax+rax+00h]
0x180024aaa  test    eax, eax
0x180024aac  jnz     short loc_180024B08
0x180024aae  lea     rbx, [rdi+48h]
0x180024ab2  mov     rcx, [rbx]
0x180024ab5  test    rcx, rcx
0x180024ab8  jz      short loc_180024ACE
0x180024aba  mov     qword ptr [rbx], 0
0x180024ac1  mov     rax, [rcx]
0x180024ac4  mov     rax, [rax+10h]
0x180024ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024acd  nop
0x180024ace  movups  xmm0, xmmword ptr [rsi]
0x180024ad1  movaps  [rbp+var_28], xmm0
0x180024ad5  movsd   xmm1, qword ptr [rsi+10h]
0x180024ada  movsd   [rbp+var_18], xmm1
0x180024adf  mov     qword ptr [rsp+68h+var_48], rbx
0x180024ae4  mov     r9, [rbp+arg_28]
0x180024ae8  mov     r8, [rbp+arg_20]
0x180024aec  lea     rdx, [rbp+var_28]
0x180024af0  mov     ecx, r15d
0x180024af3  call    ?AddNode@GenericIntNode@@SAJW4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAKPEAPEAV1@@Z; GenericIntNode::AddNode(ConfigDataType,tagVARIANT,ICSPNode * *,ulong *,GenericIntNode * *)
0x180024af8  mov     ebx, eax
0x180024afa  test    eax, eax
0x180024afc  jns     short loc_180024B7D
0x180024afe  mov     edx, 4Fh ; 'O'
0x180024b03  jmp     loc_1800249C4
0x180024b08  lea     rdx, ?gc_wszAccountsLocalUserHomeDirNode@@3QBGB; "HomeDir"
0x180024b0f  mov     rcx, [rbp+String1]; String1
0x180024b13  call    cs:__imp__wcsicmp
0x180024b1a  nop     dword ptr [rax+rax+00h]
0x180024b1f  test    eax, eax
0x180024b21  jnz     short loc_180024B81
0x180024b23  lea     rbx, [rdi+50h]
0x180024b27  mov     rcx, [rbx]
0x180024b2a  test    rcx, rcx
0x180024b2d  jz      short loc_180024B43
0x180024b2f  mov     qword ptr [rbx], 0
0x180024b36  mov     rax, [rcx]
0x180024b39  mov     rax, [rax+10h]
0x180024b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b42  nop
0x180024b43  movups  xmm0, xmmword ptr [rsi]
0x180024b46  movaps  [rbp+var_28], xmm0
0x180024b4a  movsd   xmm1, qword ptr [rsi+10h]
0x180024b4f  movsd   [rbp+var_18], xmm1
0x180024b54  mov     qword ptr [rsp+68h+var_48], rbx
0x180024b59  mov     r9, [rbp+arg_28]
0x180024b5d  mov     r8, [rbp+arg_20]
0x180024b61  lea     rdx, [rbp+var_28]
0x180024b65  mov     ecx, r15d
0x180024b68  call    ?AddStringNode@GenericBStrNode@@SAJW4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAKPEAPEAV1@@Z; GenericBStrNode::AddStringNode(ConfigDataType,tagVARIANT,ICSPNode * *,ulong *,GenericBStrNode * *)
0x180024b6d  mov     ebx, eax
0x180024b6f  test    eax, eax
0x180024b71  jns     short loc_180024B7D
0x180024b73  mov     edx, 53h ; 'S'
0x180024b78  jmp     loc_1800249C4
0x180024b7d  xor     eax, eax
0x180024b7f  jmp     short loc_180024B86
0x180024b81  mov     eax, 86000002h
0x180024b86  add     rsp, 68h
0x180024b8a  pop     r15
0x180024b8c  pop     r14
0x180024b8e  pop     rdi
0x180024b8f  pop     rsi
0x180024b90  pop     rbx
0x180024b91  pop     rbp
0x180024b92  retn
```
