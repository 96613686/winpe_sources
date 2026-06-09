# CNetworkDiagnostics::get_Progress(ushort * *)

- ea: `0x180016a10`
- end: `0x180016b58`
- name: `?get_Progress@CNetworkDiagnostics@@UEAAJPEAPEAG@Z`
- size: `328`
- prototype: `__int64 __fastcall(CNetworkDiagnostics *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180016a10`
- `0x18001f652`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180016a4f`
- `ole32!CoTaskMemAlloc` at `0x180016a4f`
- `ole32!CoTaskMemRealloc` at `0x180016abd`
- `ole32!CoTaskMemRealloc` at `0x180016abd`
- `ole32!CoTaskMemFree` at `0x180016afa`
- `ole32!CoTaskMemFree` at `0x180016afa`
- `wdi!WdiGetProgress` at `0x180016aa8`
- `wdi!WdiGetProgress` at `0x180016b24`
- `wdi!WdiGetProgress` at `0x180016aa8`
- `wdi!WdiGetProgress` at `0x180016b24`
- `OLEAUT32!__imp_SysAllocString` at `0x180016aee`
- `OLEAUT32!__imp_SysAllocString` at `0x180016aee`

## pseudocode

```c
__int64 __fastcall CNetworkDiagnostics::get_Progress(CNetworkDiagnostics *this, unsigned __int16 **a2)
{
  int v2; // r8d
  __int64 v4; // r14
  void *v5; // rax
  void *v6; // rdi
  __int64 v8; // rcx
  int Progress; // ebx
  void *v10; // rax
  __int64 v11; // rcx
  size_t Size; // [rsp+60h] [rbp+30h] BYREF
  int v13; // [rsp+70h] [rbp+40h] BYREF
  int v14; // [rsp+78h] [rbp+48h] BYREF

  v2 = *((_DWORD *)this + 30);
  if ( ((v2 - 2) & 0xFFFFFFF9) == 0 && v2 != 8 )
  {
    v4 = *((_QWORD *)this + 2);
    LODWORD(Size) = 256;
    v5 = CoTaskMemAlloc(0x100u);
    v6 = v5;
    if ( !v5 )
      return 2147942414LL;
    memset_0(v5, 0, (unsigned int)Size);
    v8 = *(_QWORD *)(v4 + 128);
    if ( !v8 )
      goto LABEL_9;
    v14 = 0;
    v13 = 0;
    Progress = WdiGetProgress(v8, &v14, &v13, v6, &Size);
    if ( Progress != -2147024662 )
      goto LABEL_10;
    v10 = CoTaskMemRealloc(v6, (unsigned int)Size);
    v6 = v10;
    if ( !v10 )
      return (unsigned int)-2147024882;
    memset_0(v10, 0, (unsigned int)Size);
    v11 = *(_QWORD *)(v4 + 128);
    if ( v11 )
    {
      v14 = 0;
      v13 = 0;
      Progress = WdiGetProgress(v11, &v14, &v13, v6, &Size);
    }
    else
    {
LABEL_9:
      Progress = -2147024875;
    }
LABEL_10:
    if ( Progress < 0 )
    {
      if ( Progress == -2147020579 )
        return (unsigned int)-2147024875;
    }
    else
    {
      *a2 = SysAllocString((const OLECHAR *)v6);
      CoTaskMemFree(v6);
    }
    return (unsigned int)Progress;
  }
  return 2147943176LL;
}

```

## disassembly

```asm
0x180016a10  mov     [rsp-28h+arg_8], rbx
0x180016a15  push    rbp
0x180016a16  push    rsi
0x180016a17  push    rdi
0x180016a18  push    r14
0x180016a1a  push    r15
0x180016a1c  mov     rbp, rsp
0x180016a1f  sub     rsp, 30h
0x180016a23  mov     r8d, [rcx+78h]
0x180016a27  mov     r15, rdx
0x180016a2a  lea     eax, [r8-2]
0x180016a2e  test    eax, 0FFFFFFF9h
0x180016a33  jnz     loc_180016B42
0x180016a39  cmp     r8d, 8
0x180016a3d  jz      loc_180016B42
0x180016a43  mov     r14, [rcx+10h]
0x180016a47  mov     ecx, 100h; cb
0x180016a4c  mov     dword ptr [rbp+Size], ecx
0x180016a4f  call    cs:__imp_CoTaskMemAlloc
0x180016a55  mov     rdi, rax
0x180016a58  test    rax, rax
0x180016a5b  jnz     short loc_180016A67
0x180016a5d  mov     eax, 8007000Eh
0x180016a62  jmp     loc_180016B47
0x180016a67  mov     r8d, dword ptr [rbp+Size]; Size
0x180016a6b  xor     edx, edx; Val
0x180016a6d  mov     rcx, rdi; void *
0x180016a70  call    memset_0
0x180016a75  mov     rcx, [r14+80h]
0x180016a7c  mov     esi, 80070015h
0x180016a81  test    rcx, rcx
0x180016a84  jz      short loc_180016AE5
0x180016a86  lea     rax, [rbp+Size]
0x180016a8a  mov     [rbp+arg_18], 0
0x180016a91  mov     r9, rdi
0x180016a94  mov     [rsp+30h+var_10], rax
0x180016a99  lea     r8, [rbp+arg_10]
0x180016a9d  mov     [rbp+arg_10], 0
0x180016aa4  lea     rdx, [rbp+arg_18]
0x180016aa8  call    cs:__imp_WdiGetProgress
0x180016aae  mov     ebx, eax
0x180016ab0  cmp     eax, 800700EAh
0x180016ab5  jnz     short loc_180016AE7
0x180016ab7  mov     edx, dword ptr [rbp+Size]; cb
0x180016aba  mov     rcx, rdi; pv
0x180016abd  call    cs:__imp_CoTaskMemRealloc
0x180016ac3  mov     rdi, rax
0x180016ac6  test    rax, rax
0x180016ac9  jz      short loc_180016B2E
0x180016acb  mov     r8d, dword ptr [rbp+Size]; Size
0x180016acf  xor     edx, edx; Val
0x180016ad1  mov     rcx, rax; void *
0x180016ad4  call    memset_0
0x180016ad9  mov     rcx, [r14+80h]
0x180016ae0  test    rcx, rcx
0x180016ae3  jnz     short loc_180016B02
0x180016ae5  mov     ebx, esi
0x180016ae7  test    ebx, ebx
0x180016ae9  js      short loc_180016B35
0x180016aeb  mov     rcx, rdi; psz
0x180016aee  call    cs:__imp_SysAllocString
0x180016af4  mov     rcx, rdi; pv
0x180016af7  mov     [r15], rax
0x180016afa  call    cs:__imp_CoTaskMemFree
0x180016b00  jmp     short loc_180016B3E
0x180016b02  lea     rax, [rbp+Size]
0x180016b06  mov     [rbp+arg_18], 0
0x180016b0d  mov     r9, rdi
0x180016b10  mov     [rsp+30h+var_10], rax
0x180016b15  lea     r8, [rbp+arg_10]
0x180016b19  mov     [rbp+arg_10], 0
0x180016b20  lea     rdx, [rbp+arg_18]
0x180016b24  call    cs:__imp_WdiGetProgress
0x180016b2a  mov     ebx, eax
0x180016b2c  jmp     short loc_180016AE7
0x180016b2e  mov     ebx, 8007000Eh
0x180016b33  jmp     short loc_180016B3E
0x180016b35  cmp     ebx, 800710DDh
0x180016b3b  cmovz   ebx, esi
0x180016b3e  mov     eax, ebx
0x180016b40  jmp     short loc_180016B47
0x180016b42  mov     eax, 80070308h
0x180016b47  mov     rbx, [rsp+30h+arg_8]
0x180016b4c  add     rsp, 30h
0x180016b50  pop     r15
0x180016b52  pop     r14
0x180016b54  pop     rdi
0x180016b55  pop     rsi
0x180016b56  pop     rbp
0x180016b57  retn
```
