# CAnchorTag::GetValue(tagPROPVARIANT * *)

- ea: `0x180011230`
- end: `0x180011296`
- name: `?GetValue@CAnchorTag@@UEAAJPEAPEAUtagPROPVARIANT@@@Z`
- size: `102`
- prototype: `__int64 __fastcall(CAnchorTag *this, struct tagPROPVARIANT **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180011230`
- `0x1800138ec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011251`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011251`

## pseudocode

```c
__int64 __fastcall CAnchorTag::GetValue(CAnchorTag *this, struct tagPROPVARIANT **a2)
{
  struct tagPROPVARIANT *v3; // rcx
  __int64 result; // rax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 62) )
    return 2147751682LL;
  *((_DWORD *)this + 62) = 1;
  v3 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
  if ( v3 )
  {
    result = 0;
    v3->vt = 0;
    *a2 = v3;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\anchor.cxx",
      (const char *)0x8007000ELL,
      v5);
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180011230  push    rbx; int
0x180011232  sub     rsp, 20h
0x180011236  cmp     dword ptr [rcx+0F8h], 0
0x18001123d  mov     rbx, rdx
0x180011240  jnz     short loc_18001126D
0x180011242  mov     dword ptr [rcx+0F8h], 1
0x18001124c  mov     ecx, 18h; cb
0x180011251  call    cs:__imp_CoTaskMemAlloc
0x180011257  mov     rcx, rax
0x18001125a  test    rax, rax
0x18001125d  jz      short loc_180011274
0x18001125f  xor     eax, eax
0x180011261  mov     [rcx], ax
0x180011264  mov     [rbx], rcx
0x180011267  add     rsp, 20h
0x18001126b  pop     rbx
0x18001126c  retn
0x18001126d  mov     eax, 80041702h
0x180011272  jmp     short loc_180011267
0x180011274  mov     rcx, [rsp+28h]; this
0x180011279  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180011280  mov     ebx, 8007000Eh
0x180011285  mov     edx, 9Eh; void *
0x18001128a  mov     r9d, ebx; char *
0x18001128d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011292  mov     eax, ebx
0x180011294  jmp     short loc_180011267
```
