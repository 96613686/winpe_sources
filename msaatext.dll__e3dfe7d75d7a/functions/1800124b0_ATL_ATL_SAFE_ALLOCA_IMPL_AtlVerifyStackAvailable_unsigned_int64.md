# ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)

- ea: `0x1800124b0`
- end: `0x180012520`
- name: `?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z`
- size: `112`
- prototype: `bool __fastcall(ATL::_ATL_SAFE_ALLOCA_IMPL *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e3f4`
- `0x180010dd4`
- `0x180011038`

## callees

- `0x1800124b0`
- `0x180012528`
- `0x180012b40`
- `0x180012c00`

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
0x1800124b0  push    rbp
0x1800124b2  sub     rsp, 30h
0x1800124b6  lea     rbp, [rsp+20h]
0x1800124bb  mov     [rbp+10h+arg_0], rbx
0x1800124bf  mov     rax, cs:__security_cookie
0x1800124c6  xor     rax, rbp
0x1800124c9  mov     [rbp+10h+var_10], rax
0x1800124cd  mov     bl, 1
0x1800124cf  lea     rdx, [rcx+2000h]
0x1800124d6  cmp     rdx, rcx
0x1800124d9  jnb     short loc_1800124DF
0x1800124db  xor     al, al
0x1800124dd  jmp     short loc_18001250A
0x1800124df  lea     rax, [rdx+0Fh]
0x1800124e3  cmp     rax, rdx
0x1800124e6  ja      short loc_1800124F2
0x1800124e8  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800124f2  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800124f6  call    _alloca_probe
0x1800124fb  sub     rsp, rax
0x1800124fe  jmp     short loc_180012508
0x180012500  xor     bl, bl
0x180012502  call    ?_Atlresetstkoflw@_ATL_SAFE_ALLOCA_IMPL@ATL@@YAHXZ; ATL::_ATL_SAFE_ALLOCA_IMPL::_Atlresetstkoflw(void)
0x180012507  nop
0x180012508  mov     al, bl
0x18001250a  mov     rcx, [rbp+10h+var_10]
0x18001250e  xor     rcx, rbp; StackCookie
0x180012511  call    __security_check_cookie
0x180012516  mov     rbx, [rbp+10h+arg_0]
0x18001251a  lea     rsp, [rbp+10h]
0x18001251e  pop     rbp
0x18001251f  retn
0x180013a9b  push    rbp
0x180013a9d  sub     rsp, 20h
0x180013aa1  lea     rbp, [rdx+20h]
0x180013aa5  mov     rax, [rcx]
0x180013aa8  xor     ecx, ecx
0x180013aaa  cmp     dword ptr [rax], 0C00000FDh
0x180013ab0  setz    cl
0x180013ab3  mov     eax, ecx
0x180013ab5  add     rsp, 20h
0x180013ab9  pop     rbp
0x180013aba  retn
```
