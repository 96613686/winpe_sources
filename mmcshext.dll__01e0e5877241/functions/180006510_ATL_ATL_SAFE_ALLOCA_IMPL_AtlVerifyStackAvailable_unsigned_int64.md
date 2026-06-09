# ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)

- ea: `0x180006510`
- end: `0x180006580`
- name: `?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z`
- size: `112`
- prototype: `bool __fastcall(ATL::_ATL_SAFE_ALLOCA_IMPL *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002fe8`
- `0x180004ed4`
- `0x180005130`

## callees

- `0x180006510`
- `0x180006588`
- `0x18000a5b0`
- `0x18000a670`

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
0x180006510  push    rbp
0x180006512  sub     rsp, 30h
0x180006516  lea     rbp, [rsp+20h]
0x18000651b  mov     [rbp+10h+arg_0], rbx
0x18000651f  mov     rax, cs:__security_cookie
0x180006526  xor     rax, rbp
0x180006529  mov     [rbp+10h+var_10], rax
0x18000652d  mov     bl, 1
0x18000652f  lea     rdx, [rcx+2000h]
0x180006536  cmp     rdx, rcx
0x180006539  jnb     short loc_18000653F
0x18000653b  xor     al, al
0x18000653d  jmp     short loc_18000656A
0x18000653f  lea     rax, [rdx+0Fh]
0x180006543  cmp     rax, rdx
0x180006546  ja      short loc_180006552
0x180006548  mov     rax, 0FFFFFFFFFFFFFF0h
0x180006552  and     rax, 0FFFFFFFFFFFFFFF0h
0x180006556  call    _alloca_probe
0x18000655b  sub     rsp, rax
0x18000655e  jmp     short loc_180006568
0x180006560  xor     bl, bl
0x180006562  call    ?_Atlresetstkoflw@_ATL_SAFE_ALLOCA_IMPL@ATL@@YAHXZ; ATL::_ATL_SAFE_ALLOCA_IMPL::_Atlresetstkoflw(void)
0x180006567  nop
0x180006568  mov     al, bl
0x18000656a  mov     rcx, [rbp+10h+var_10]
0x18000656e  xor     rcx, rbp; StackCookie
0x180006571  call    __security_check_cookie
0x180006576  mov     rbx, [rbp+10h+arg_0]
0x18000657a  lea     rsp, [rbp+10h]
0x18000657e  pop     rbp
0x18000657f  retn
0x18000ab9a  push    rbp
0x18000ab9c  sub     rsp, 20h
0x18000aba0  lea     rbp, [rdx+20h]
0x18000aba4  mov     rax, [rcx]
0x18000aba7  xor     ecx, ecx
0x18000aba9  cmp     dword ptr [rax], 0C00000FDh
0x18000abaf  setz    cl
0x18000abb2  mov     eax, ecx
0x18000abb4  add     rsp, 20h
0x18000abb8  pop     rbp
0x18000abb9  retn
```
