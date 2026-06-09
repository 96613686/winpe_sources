# InvokeCreateFilter

- ea: `0x1800419a0`
- end: `0x180041bba`
- name: `InvokeCreateFilter`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800426a0`

## callees

- `0x1800077a0`
- `0x180007800`
- `0x180007ad0`
- `0x180041220`
- `0x180041540`
- `0x1800419a0`
- `0x180044698`
- `0x1800446dc`
- `0x18004472c`
- `0x180044842`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!free` at `0x180041a9c`
- `msvcrt!free` at `0x180041b94`
- `msvcrt!free` at `0x180041a9c`
- `msvcrt!free` at `0x180041b94`
- `msvcrt!_wcsdup` at `0x180041a15`
- `msvcrt!_wcsdup` at `0x180041a15`

## pseudocode

```c
void __fastcall InvokeCreateFilter(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        wchar_t *a5,
        int a6,
        __int64 a7)
{
  __int64 v11; // rdi
  wchar_t *v12; // rax
  wchar_t *v13; // r14
  unsigned int v14; // eax
  __int64 v15; // rsi
  __int64 v16; // rsi
  wchar_t *v17; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+58h] [rbp-A8h]
  _QWORD v20[18]; // [rsp+60h] [rbp-A0h] BYREF

  v17 = a5;
  v19 = a7;
  v18 = 0;
  memset_0(v20, 0, sizeof(v20));
  v11 = EnableErrorDetails();
  v12 = _wcsdup(a3);
  v13 = v12;
  if ( !v12 )
  {
    RevertErrorDetails(v11);
    v14 = 27;
    goto LABEL_18;
  }
  v15 = CimBaseCache_Find(a2, v12);
  if ( v15 )
  {
    RevertErrorDetails(v11);
    v16 = *(_QWORD *)(v15 + 56);
    (**(void (__fastcall ***)(__int64))(v16 + 16))(v16);
  }
  else
  {
    v16 = Filter_New(a1, a2, a3, a4, v17, a6, v19);
    if ( !v16 )
    {
      free(v13);
      CatchErrorDetails(v11, &v18);
      PostCimErrorOrAbortOnFailure(a1, v18);
      return;
    }
    RevertErrorDetails(v11);
  }
  if ( !a1 || !*(_QWORD *)a1 )
    goto LABEL_17;
  v14 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD *))(*(_QWORD *)a1 + 32LL))(
          a1,
          &OMF_IndicationFilter_CreateIndicationFilter_rtti,
          v20);
  if ( v14
    || (v17 = (wchar_t *)(v16 + 208),
        (v14 = (*(__int64 (__fastcall **)(_QWORD *, __int64, wchar_t **))(v20[0] + 80LL))(v20, 5, &v17)) != 0) )
  {
LABEL_18:
    PostErrorOrAbortOnFailure(a1, v14);
    if ( !v13 )
      return;
    goto LABEL_19;
  }
  if ( !*(_QWORD *)a1 )
    goto LABEL_17;
  v14 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a1 + 8LL))(a1, v20);
  if ( v14 )
    goto LABEL_18;
  if ( !v20[0] )
  {
LABEL_17:
    v14 = 4;
    goto LABEL_18;
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD *))(v20[0] + 8LL))(v20);
  if ( v14 )
    goto LABEL_18;
  PostResultOrAbortOnFailure(a1, 0);
LABEL_19:
  free(v13);
}

```

## disassembly

```asm
0x1800419a0  push    rbp
0x1800419a2  push    rbx
0x1800419a3  push    rsi
0x1800419a4  push    rdi
0x1800419a5  push    r12
0x1800419a7  push    r13
0x1800419a9  push    r14
0x1800419ab  push    r15
0x1800419ad  lea     rbp, [rsp-8]
0x1800419b2  sub     rsp, 108h
0x1800419b9  mov     rax, cs:__security_cookie
0x1800419c0  xor     rax, rsp
0x1800419c3  mov     [rbp+40h+var_50], rax
0x1800419c7  mov     rax, [rbp+40h+arg_20]
0x1800419cb  mov     r12, r8
0x1800419ce  mov     [rsp+140h+var_F8], rax
0x1800419d3  mov     r15, rdx
0x1800419d6  mov     eax, [rbp+40h+arg_28]
0x1800419d9  mov     rbx, rcx
0x1800419dc  mov     [rsp+140h+var_100], eax
0x1800419e0  lea     rcx, [rsp+140h+var_E0]; void *
0x1800419e5  mov     rax, [rbp+40h+arg_30]
0x1800419ec  xor     edx, edx; Val
0x1800419ee  mov     r8d, 90h; Size
0x1800419f4  mov     [rsp+140h+var_E8], rax
0x1800419f9  mov     r13, r9
0x1800419fc  mov     [rsp+140h+var_F0], 0
0x180041a05  call    memset_0
0x180041a0a  call    EnableErrorDetails
0x180041a0f  mov     rcx, r12; String
0x180041a12  mov     rdi, rax
0x180041a15  call    cs:__imp__wcsdup
0x180041a1b  mov     r14, rax
0x180041a1e  test    rax, rax
0x180041a21  jnz     short loc_180041A34
0x180041a23  mov     rcx, rdi
0x180041a26  call    RevertErrorDetails
0x180041a2b  lea     eax, [r14+1Bh]
0x180041a2f  jmp     loc_180041B82
0x180041a34  mov     rdx, r14
0x180041a37  mov     rcx, r15
0x180041a3a  call    CimBaseCache_Find
0x180041a3f  mov     rsi, rax
0x180041a42  test    rax, rax
0x180041a45  jz      short loc_180041A64
0x180041a47  mov     rcx, rdi
0x180041a4a  call    RevertErrorDetails
0x180041a4f  mov     rsi, [rsi+38h]
0x180041a53  mov     rcx, rsi
0x180041a56  mov     rax, [rsi+10h]
0x180041a5a  mov     rax, [rax]
0x180041a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041a62  jmp     short loc_180041AC9
0x180041a64  mov     rax, [rsp+140h+var_E8]
0x180041a69  mov     r9, r13
0x180041a6c  mov     [rsp+140h+var_110], rax
0x180041a71  mov     r8, r12
0x180041a74  mov     eax, [rsp+140h+var_100]
0x180041a78  mov     rdx, r15
0x180041a7b  mov     [rsp+140h+var_118], eax
0x180041a7f  mov     rcx, rbx
0x180041a82  mov     rax, [rsp+140h+var_F8]
0x180041a87  mov     [rsp+140h+var_120], rax
0x180041a8c  call    Filter_New
0x180041a91  mov     rsi, rax
0x180041a94  test    rax, rax
0x180041a97  jnz     short loc_180041AC1
0x180041a99  mov     rcx, r14; Block
0x180041a9c  call    cs:__imp_free
0x180041aa2  lea     rdx, [rsp+140h+var_F0]
0x180041aa7  mov     rcx, rdi
0x180041aaa  call    CatchErrorDetails
0x180041aaf  mov     rdx, [rsp+140h+var_F0]
0x180041ab4  mov     rcx, rbx
0x180041ab7  call    PostCimErrorOrAbortOnFailure
0x180041abc  jmp     loc_180041B9A
0x180041ac1  mov     rcx, rdi
0x180041ac4  call    RevertErrorDetails
0x180041ac9  test    rbx, rbx
0x180041acc  jz      loc_180041B7D
0x180041ad2  mov     rax, [rbx]
0x180041ad5  test    rax, rax
0x180041ad8  jz      loc_180041B7D
0x180041ade  mov     rax, [rax+20h]
0x180041ae2  lea     r8, [rsp+140h+var_E0]
0x180041ae7  lea     rdx, OMF_IndicationFilter_CreateIndicationFilter_rtti
0x180041aee  mov     rcx, rbx
0x180041af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041af6  test    eax, eax
0x180041af8  jnz     loc_180041B82
0x180041afe  lea     rax, [rsi+0D0h]
0x180041b05  mov     dword ptr [rsp+140h+var_120], 0
0x180041b0d  mov     [rsp+140h+var_F8], rax
0x180041b12  lea     r8, [rsp+140h+var_F8]
0x180041b17  mov     rax, [rsp+140h+var_E0]
0x180041b1c  lea     rcx, [rsp+140h+var_E0]
0x180041b21  mov     r9d, 0Eh
0x180041b27  mov     rax, [rax+50h]
0x180041b2b  lea     edx, [r9-9]
0x180041b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b34  test    eax, eax
0x180041b36  jnz     short loc_180041B82
0x180041b38  mov     rax, [rbx]
0x180041b3b  test    rax, rax
0x180041b3e  jz      short loc_180041B7D
0x180041b40  mov     rax, [rax+8]
0x180041b44  lea     rdx, [rsp+140h+var_E0]
0x180041b49  mov     rcx, rbx
0x180041b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b51  test    eax, eax
0x180041b53  jnz     short loc_180041B82
0x180041b55  mov     rax, [rsp+140h+var_E0]
0x180041b5a  test    rax, rax
0x180041b5d  jz      short loc_180041B7D
0x180041b5f  mov     rax, [rax+8]
0x180041b63  lea     rcx, [rsp+140h+var_E0]
0x180041b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b6d  test    eax, eax
0x180041b6f  jnz     short loc_180041B82
0x180041b71  xor     edx, edx
0x180041b73  mov     rcx, rbx
0x180041b76  call    PostResultOrAbortOnFailure
0x180041b7b  jmp     short loc_180041B91
0x180041b7d  mov     eax, 4
0x180041b82  mov     edx, eax
0x180041b84  mov     rcx, rbx
0x180041b87  call    PostErrorOrAbortOnFailure
0x180041b8c  test    r14, r14
0x180041b8f  jz      short loc_180041B9A
0x180041b91  mov     rcx, r14; Block
0x180041b94  call    cs:__imp_free
0x180041b9a  mov     rcx, [rbp+40h+var_50]
0x180041b9e  xor     rcx, rsp; StackCookie
0x180041ba1  call    __security_check_cookie
0x180041ba6  add     rsp, 108h
0x180041bad  pop     r15
0x180041baf  pop     r14
0x180041bb1  pop     r13
0x180041bb3  pop     r12
0x180041bb5  pop     rdi
0x180041bb6  pop     rsi
0x180041bb7  pop     rbx
0x180041bb8  pop     rbp
0x180041bb9  retn
```
