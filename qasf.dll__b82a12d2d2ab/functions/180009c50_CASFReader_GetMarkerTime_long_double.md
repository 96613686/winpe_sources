# CASFReader::GetMarkerTime(long,double *)

- ea: `0x180009c50`
- end: `0x180009d22`
- name: `?GetMarkerTime@CASFReader@@EEAAJJPEAN@Z`
- size: `210`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, int, double *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001460`
- `0x180009c50`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::GetMarkerTime(CASFReader *this, unsigned __int16 a2, double *a3)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rcx
  int v7; // ebx
  __int64 v8; // [rsp+30h] [rbp-38h] BYREF
  __int16 v9; // [rsp+38h] [rbp-30h] BYREF
  __int64 v10; // [rsp+40h] [rbp-28h] BYREF

  v3 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 27);
  if ( !v3 )
    return 2147500037LL;
  v8 = 0;
  v7 = (**v3)(v3, &IID_IWMHeaderInfo, &v8);
  if ( v7 >= 0 )
  {
    v10 = 0;
    v9 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int16 *, __int64 *))(*(_QWORD *)v8 + 64LL))(
           v8,
           a2,
           0,
           &v9,
           &v10);
    if ( v7 >= 0 )
      *a3 = (double)(int)v10 / 10000000.0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009c50  push    rbx
0x180009c52  push    rsi
0x180009c53  push    rdi
0x180009c54  sub     rsp, 50h
0x180009c58  mov     rax, cs:__security_cookie
0x180009c5f  xor     rax, rsp
0x180009c62  mov     [rsp+68h+var_20], rax
0x180009c67  mov     rcx, [rcx+0D8h]
0x180009c6e  mov     rdi, r8
0x180009c71  mov     esi, edx
0x180009c73  test    rcx, rcx
0x180009c76  jnz     short loc_180009C82
0x180009c78  mov     eax, 80004005h
0x180009c7d  jmp     loc_180009D0D
0x180009c82  mov     [rsp+68h+var_38], 0
0x180009c8b  lea     r8, [rsp+68h+var_38]
0x180009c90  mov     rax, [rcx]
0x180009c93  lea     rdx, IID_IWMHeaderInfo
0x180009c9a  mov     rax, [rax]
0x180009c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ca2  mov     ebx, eax
0x180009ca4  test    eax, eax
0x180009ca6  js      short loc_180009D0B
0x180009ca8  mov     rcx, [rsp+68h+var_38]
0x180009cad  lea     r8, [rsp+68h+var_28]
0x180009cb2  xor     eax, eax
0x180009cb4  mov     [rsp+68h+var_28], 0
0x180009cbd  mov     [rsp+68h+var_30], ax
0x180009cc2  lea     r9, [rsp+68h+var_30]
0x180009cc7  mov     [rsp+68h+var_48], r8
0x180009ccc  movzx   edx, si
0x180009ccf  mov     rax, [rcx]
0x180009cd2  xor     r8d, r8d
0x180009cd5  mov     rax, [rax+40h]
0x180009cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cde  mov     ebx, eax
0x180009ce0  test    eax, eax
0x180009ce2  js      short loc_180009CFA
0x180009ce4  xorps   xmm0, xmm0
0x180009ce7  cvtsi2sd xmm0, [rsp+68h+var_28]
0x180009cee  divsd   xmm0, cs:__real@416312d000000000
0x180009cf6  movsd   qword ptr [rdi], xmm0
0x180009cfa  mov     rcx, [rsp+68h+var_38]
0x180009cff  mov     rax, [rcx]
0x180009d02  mov     rax, [rax+10h]
0x180009d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d0b  mov     eax, ebx
0x180009d0d  mov     rcx, [rsp+68h+var_20]
0x180009d12  xor     rcx, rsp; StackCookie
0x180009d15  call    __security_check_cookie
0x180009d1a  add     rsp, 50h
0x180009d1e  pop     rdi
0x180009d1f  pop     rsi
0x180009d20  pop     rbx
0x180009d21  retn
```
