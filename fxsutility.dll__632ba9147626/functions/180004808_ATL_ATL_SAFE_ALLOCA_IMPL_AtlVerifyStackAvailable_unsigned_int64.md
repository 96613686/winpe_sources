# ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)

- ea: `0x180004808`
- end: `0x180004878`
- name: `?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z`
- size: `112`
- prototype: `bool __fastcall(ATL::_ATL_SAFE_ALLOCA_IMPL *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002274`
- `0x180003794`
- `0x1800039f4`

## callees

- `0x180004808`
- `0x180004880`
- `0x180015cf0`
- `0x180015db0`

## pseudocode

```c
char __fastcall ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(ATL::_ATL_SAFE_ALLOCA_IMPL *this)
{
  __int64 v2; // rax
  void *v3; // rsp

  if ( (ATL::_ATL_SAFE_ALLOCA_IMPL *)((char *)this + 0x2000) < this )
    return 0;
  v2 = (__int64)this + 8207;
  if ( (char *)this + 8207 < (char *)this + 0x2000 )
    v2 = 0xFFFFFFFFFFFFFF0LL;
  v3 = alloca(v2 & 0xFFFFFFFFFFFFFFF0uLL);
  return 1;
}

```

## disassembly

```asm
0x180004808  push    rbp
0x18000480a  sub     rsp, 30h
0x18000480e  lea     rbp, [rsp+20h]
0x180004813  mov     [rbp+10h+arg_0], rbx
0x180004817  mov     rax, cs:__security_cookie
0x18000481e  xor     rax, rbp
0x180004821  mov     [rbp+10h+var_10], rax
0x180004825  mov     bl, 1
0x180004827  lea     rdx, [rcx+2000h]
0x18000482e  cmp     rdx, rcx
0x180004831  jnb     short loc_180004837
0x180004833  xor     al, al
0x180004835  jmp     short loc_180004862
0x180004837  lea     rax, [rdx+0Fh]
0x18000483b  cmp     rax, rdx
0x18000483e  ja      short loc_18000484A
0x180004840  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000484a  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000484e  call    _alloca_probe
0x180004853  sub     rsp, rax
0x180004856  jmp     short loc_180004860
0x180004858  xor     bl, bl
0x18000485a  call    ?_Atlresetstkoflw@_ATL_SAFE_ALLOCA_IMPL@ATL@@YAHXZ; ATL::_ATL_SAFE_ALLOCA_IMPL::_Atlresetstkoflw(void)
0x18000485f  nop
0x180004860  mov     al, bl
0x180004862  mov     rcx, [rbp+10h+var_10]
0x180004866  xor     rcx, rbp; StackCookie
0x180004869  call    __security_check_cookie
0x18000486e  mov     rbx, [rbp+10h+arg_0]
0x180004872  lea     rsp, [rbp+10h]
0x180004876  pop     rbp
0x180004877  retn
0x180016229  push    rbp
0x18001622b  sub     rsp, 20h
0x18001622f  lea     rbp, [rdx+20h]
0x180016233  mov     rax, [rcx]
0x180016236  xor     ecx, ecx
0x180016238  cmp     dword ptr [rax], 0C00000FDh
0x18001623e  setz    cl
0x180016241  mov     eax, ecx
0x180016243  add     rsp, 20h
0x180016247  pop     rbp
0x180016248  retn
```
