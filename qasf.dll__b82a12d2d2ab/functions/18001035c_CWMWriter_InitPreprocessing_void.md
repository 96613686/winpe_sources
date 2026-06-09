# CWMWriter::InitPreprocessing(void)

- ea: `0x18001035c`
- end: `0x180010431`
- name: `?InitPreprocessing@CWMWriter@@QEAAJXZ`
- size: `213`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800119ec`

## callees

- `0x180001460`
- `0x18001035c`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMWriter::InitPreprocessing(CWMWriter *this)
{
  __int64 v3; // rbx
  int v4; // ecx
  __int64 v5; // rdi
  __int64 v6; // rcx
  unsigned int v7; // [rsp+30h] [rbp-18h] BYREF

  if ( !*((_DWORD *)this + 99) )
    return 0;
  v3 = *((_QWORD *)this + 51);
  v4 = 0;
  while ( v3 && v4 >= 0 )
  {
    v5 = *(_QWORD *)(v3 + 16);
    v3 = *(_QWORD *)(v3 + 8);
    v6 = *((_QWORD *)this + 44);
    v7 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v6 + 24LL))(
           v6,
           *(unsigned int *)(v5 + 396),
           0,
           &v7);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 44) + 32LL))(
             *((_QWORD *)this + 44),
             *(unsigned int *)(v5 + 396),
             0,
             v7);
      if ( v4 >= 0 )
        *(_DWORD *)(v5 + 464) = v7;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001035c  mov     [rsp+arg_8], rbx
0x180010361  mov     [rsp+arg_10], rsi
0x180010366  push    rdi
0x180010367  sub     rsp, 40h
0x18001036b  mov     rax, cs:__security_cookie
0x180010372  xor     rax, rsp
0x180010375  mov     [rsp+48h+var_10], rax
0x18001037a  cmp     dword ptr [rcx+18Ch], 0
0x180010381  mov     rsi, rcx
0x180010384  jnz     short loc_18001038D
0x180010386  xor     eax, eax
0x180010388  jmp     loc_180010414
0x18001038d  mov     rbx, [rsi+198h]
0x180010394  xor     ecx, ecx
0x180010396  jmp     short loc_18001040D
0x180010398  test    ecx, ecx
0x18001039a  js      short loc_180010412
0x18001039c  test    rbx, rbx
0x18001039f  jnz     short loc_1800103A5
0x1800103a1  xor     edi, edi
0x1800103a3  jmp     short loc_1800103AD
0x1800103a5  mov     rdi, [rbx+10h]
0x1800103a9  mov     rbx, [rbx+8]
0x1800103ad  mov     rcx, [rsi+160h]
0x1800103b4  lea     r9, [rsp+48h+var_18]
0x1800103b9  mov     [rsp+48h+var_18], 0
0x1800103c1  xor     r8d, r8d
0x1800103c4  mov     edx, [rdi+18Ch]
0x1800103ca  mov     rax, [rcx]
0x1800103cd  mov     rax, [rax+18h]
0x1800103d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103d6  mov     ecx, eax
0x1800103d8  test    eax, eax
0x1800103da  js      short loc_18001040D
0x1800103dc  mov     rcx, [rsi+160h]
0x1800103e3  xor     r8d, r8d
0x1800103e6  mov     r9d, [rsp+48h+var_18]
0x1800103eb  mov     edx, [rdi+18Ch]
0x1800103f1  mov     rax, [rcx]
0x1800103f4  mov     rax, [rax+20h]
0x1800103f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103fd  mov     ecx, eax
0x1800103ff  test    eax, eax
0x180010401  js      short loc_18001040D
0x180010403  mov     eax, [rsp+48h+var_18]
0x180010407  mov     [rdi+1D0h], eax
0x18001040d  test    rbx, rbx
0x180010410  jnz     short loc_180010398
0x180010412  mov     eax, ecx
0x180010414  mov     rcx, [rsp+48h+var_10]
0x180010419  xor     rcx, rsp; StackCookie
0x18001041c  call    __security_check_cookie
0x180010421  mov     rbx, [rsp+48h+arg_8]
0x180010426  mov     rsi, [rsp+48h+arg_10]
0x18001042b  add     rsp, 40h
0x18001042f  pop     rdi
0x180010430  retn
```
