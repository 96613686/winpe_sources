# InvokeCreateListener

- ea: `0x180041dc0`
- end: `0x180041faa`
- name: `InvokeCreateListener`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800425a0`

## callees

- `0x1800077a0`
- `0x180007800`
- `0x180007ad0`
- `0x180041220`
- `0x180041dc0`
- `0x180041fec`
- `0x180044698`
- `0x1800446dc`
- `0x18004472c`
- `0x180044842`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!free` at `0x180041e90`
- `msvcrt!free` at `0x180041f84`
- `msvcrt!free` at `0x180041e90`
- `msvcrt!free` at `0x180041f84`
- `msvcrt!_wcsdup` at `0x180041e15`
- `msvcrt!_wcsdup` at `0x180041e15`

## pseudocode

```c
void __fastcall InvokeCreateListener(__int64 a1, __int64 a2, const wchar_t *a3, __int16 a4)
{
  __int64 v8; // rsi
  wchar_t *v9; // rax
  wchar_t *v10; // r14
  unsigned int v11; // eax
  __int64 v12; // rdi
  __int64 v13; // rdi
  __int64 v14; // [rsp+30h] [rbp-79h] BYREF
  __int64 v15; // [rsp+38h] [rbp-71h] BYREF
  _QWORD v16[14]; // [rsp+40h] [rbp-69h] BYREF

  v14 = 0;
  memset_0(v16, 0, sizeof(v16));
  v8 = EnableErrorDetails();
  v9 = _wcsdup(a3);
  v10 = v9;
  if ( !v9 )
  {
    CatchErrorDetails(v8, &v14);
    PostCimErrorOrAbortOnFailure(a1, v14);
    v11 = 1;
    goto LABEL_18;
  }
  v12 = CimBaseCache_Find(a2, v9);
  if ( v12 )
  {
    RevertErrorDetails(v8);
    v13 = *(_QWORD *)(v12 + 56);
    (**(void (__fastcall ***)(__int64))(v13 + 16))(v13);
  }
  else
  {
    v13 = Listener_New(a1, a2, a3, a4);
    if ( !v13 )
    {
      free(v10);
      CatchErrorDetails(v8, &v14);
      PostCimErrorOrAbortOnFailure(a1, v14);
      PostErrorOrAbortOnFailure(a1, 0);
      return;
    }
    RevertErrorDetails(v8);
  }
  if ( !a1 || !*(_QWORD *)a1 )
    goto LABEL_17;
  v11 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD *))(*(_QWORD *)a1 + 32LL))(
          a1,
          &OMF_ListenerDestination_CreateListener_rtti,
          v16);
  if ( v11
    || (v15 = v13 + 168,
        (v11 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(v16[0] + 80LL))(v16, 3, &v15)) != 0) )
  {
LABEL_18:
    PostErrorOrAbortOnFailure(a1, v11);
    if ( !v10 )
      return;
    goto LABEL_19;
  }
  if ( !*(_QWORD *)a1 )
    goto LABEL_17;
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a1 + 8LL))(a1, v16);
  if ( v11 )
    goto LABEL_18;
  if ( !v16[0] )
  {
LABEL_17:
    v11 = 4;
    goto LABEL_18;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD *))(v16[0] + 8LL))(v16);
  if ( v11 )
    goto LABEL_18;
  PostResultOrAbortOnFailure(a1, 0);
LABEL_19:
  free(v10);
}

```

## disassembly

```asm
0x180041dc0  push    rbp
0x180041dc2  push    rbx
0x180041dc3  push    rsi
0x180041dc4  push    rdi
0x180041dc5  push    r12
0x180041dc7  push    r13
0x180041dc9  push    r14
0x180041dcb  push    r15
0x180041dcd  lea     rbp, [rsp-1Fh]
0x180041dd2  sub     rsp, 0C8h
0x180041dd9  mov     rax, cs:__security_cookie
0x180041de0  xor     rax, rsp
0x180041de3  mov     [rbp+57h+var_50], rax
0x180041de7  mov     r15, rdx
0x180041dea  mov     [rbp+57h+var_D0], 0
0x180041df2  xor     edx, edx; Val
0x180041df4  mov     r12, r8
0x180041df7  mov     rbx, rcx
0x180041dfa  mov     r13d, r9d
0x180041dfd  lea     rcx, [rbp+57h+var_C0]; void *
0x180041e01  lea     r8d, [rdx+70h]; Size
0x180041e05  call    memset_0
0x180041e0a  call    EnableErrorDetails
0x180041e0f  mov     rcx, r12; String
0x180041e12  mov     rsi, rax
0x180041e15  call    cs:__imp__wcsdup
0x180041e1b  mov     r14, rax
0x180041e1e  test    rax, rax
0x180041e21  jnz     short loc_180041E44
0x180041e23  lea     rdx, [rbp+57h+var_D0]
0x180041e27  mov     rcx, rsi
0x180041e2a  call    CatchErrorDetails
0x180041e2f  mov     rdx, [rbp+57h+var_D0]
0x180041e33  mov     rcx, rbx
0x180041e36  call    PostCimErrorOrAbortOnFailure
0x180041e3b  lea     eax, [r14+1]
0x180041e3f  jmp     loc_180041F72
0x180041e44  mov     rdx, r14
0x180041e47  mov     rcx, r15
0x180041e4a  call    CimBaseCache_Find
0x180041e4f  mov     rdi, rax
0x180041e52  test    rax, rax
0x180041e55  jz      short loc_180041E74
0x180041e57  mov     rcx, rsi
0x180041e5a  call    RevertErrorDetails
0x180041e5f  mov     rdi, [rdi+38h]
0x180041e63  mov     rcx, rdi
0x180041e66  mov     rax, [rdi+10h]
0x180041e6a  mov     rax, [rax]
0x180041e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e72  jmp     short loc_180041EC5
0x180041e74  mov     r9d, r13d
0x180041e77  mov     r8, r12
0x180041e7a  mov     rdx, r15
0x180041e7d  mov     rcx, rbx
0x180041e80  call    Listener_New
0x180041e85  mov     rdi, rax
0x180041e88  test    rax, rax
0x180041e8b  jnz     short loc_180041EBD
0x180041e8d  mov     rcx, r14; Block
0x180041e90  call    cs:__imp_free
0x180041e96  lea     rdx, [rbp+57h+var_D0]
0x180041e9a  mov     rcx, rsi
0x180041e9d  call    CatchErrorDetails
0x180041ea2  mov     rdx, [rbp+57h+var_D0]
0x180041ea6  mov     rcx, rbx
0x180041ea9  call    PostCimErrorOrAbortOnFailure
0x180041eae  xor     edx, edx
0x180041eb0  mov     rcx, rbx
0x180041eb3  call    PostErrorOrAbortOnFailure
0x180041eb8  jmp     loc_180041F8A
0x180041ebd  mov     rcx, rsi
0x180041ec0  call    RevertErrorDetails
0x180041ec5  test    rbx, rbx
0x180041ec8  jz      loc_180041F6D
0x180041ece  mov     rax, [rbx]
0x180041ed1  test    rax, rax
0x180041ed4  jz      loc_180041F6D
0x180041eda  mov     rax, [rax+20h]
0x180041ede  lea     r8, [rbp+57h+var_C0]
0x180041ee2  lea     rdx, OMF_ListenerDestination_CreateListener_rtti
0x180041ee9  mov     rcx, rbx
0x180041eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ef1  test    eax, eax
0x180041ef3  jnz     short loc_180041F72
0x180041ef5  lea     rax, [rdi+0A8h]
0x180041efc  mov     [rsp+100h+var_E0], 0
0x180041f04  mov     [rbp+57h+var_C8], rax
0x180041f08  lea     r8, [rbp+57h+var_C8]
0x180041f0c  mov     rax, [rbp+57h+var_C0]
0x180041f10  lea     rcx, [rbp+57h+var_C0]
0x180041f14  mov     r9d, 0Eh
0x180041f1a  mov     rax, [rax+50h]
0x180041f1e  lea     edx, [r9-0Bh]
0x180041f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f27  test    eax, eax
0x180041f29  jnz     short loc_180041F72
0x180041f2b  mov     rax, [rbx]
0x180041f2e  test    rax, rax
0x180041f31  jz      short loc_180041F6D
0x180041f33  mov     rax, [rax+8]
0x180041f37  lea     rdx, [rbp+57h+var_C0]
0x180041f3b  mov     rcx, rbx
0x180041f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f43  test    eax, eax
0x180041f45  jnz     short loc_180041F72
0x180041f47  mov     rax, [rbp+57h+var_C0]
0x180041f4b  test    rax, rax
0x180041f4e  jz      short loc_180041F6D
0x180041f50  mov     rax, [rax+8]
0x180041f54  lea     rcx, [rbp+57h+var_C0]
0x180041f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f5d  test    eax, eax
0x180041f5f  jnz     short loc_180041F72
0x180041f61  xor     edx, edx
0x180041f63  mov     rcx, rbx
0x180041f66  call    PostResultOrAbortOnFailure
0x180041f6b  jmp     short loc_180041F81
0x180041f6d  mov     eax, 4
0x180041f72  mov     edx, eax
0x180041f74  mov     rcx, rbx
0x180041f77  call    PostErrorOrAbortOnFailure
0x180041f7c  test    r14, r14
0x180041f7f  jz      short loc_180041F8A
0x180041f81  mov     rcx, r14; Block
0x180041f84  call    cs:__imp_free
0x180041f8a  mov     rcx, [rbp+57h+var_50]
0x180041f8e  xor     rcx, rsp; StackCookie
0x180041f91  call    __security_check_cookie
0x180041f96  add     rsp, 0C8h
0x180041f9d  pop     r15
0x180041f9f  pop     r14
0x180041fa1  pop     r13
0x180041fa3  pop     r12
0x180041fa5  pop     rdi
0x180041fa6  pop     rsi
0x180041fa7  pop     rbx
0x180041fa8  pop     rbp
0x180041fa9  retn
```
