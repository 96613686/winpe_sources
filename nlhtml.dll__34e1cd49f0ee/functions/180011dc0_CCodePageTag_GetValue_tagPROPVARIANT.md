# CCodePageTag::GetValue(tagPROPVARIANT * *)

- ea: `0x180011dc0`
- end: `0x180011e3c`
- name: `?GetValue@CCodePageTag@@UEAAJPEAPEAUtagPROPVARIANT@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(CCodePageTag *__hidden this, struct tagPROPVARIANT **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180011dc0`
- `0x180013500`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011de8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011de8`

## pseudocode

```c
__int64 __fastcall CCodePageTag::GetValue(CCodePageTag *this, struct tagPROPVARIANT **a2)
{
  struct tagPROPVARIANT *v4; // rax
  struct tagPROPVARIANT *v5; // rdx
  __int64 result; // rax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 62) )
    return 2147751682LL;
  *((_DWORD *)this + 62) = 1;
  v4 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
  v5 = v4;
  if ( !v4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\deferred.cxx",
      (const char *)0x8007000ELL,
      v7);
  v4->vt = 19;
  result = 0;
  v5->lVal = *(_DWORD *)(*((_QWORD *)this + 1) + 5064LL);
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x180011dc0  mov     [rsp+arg_0], rbx
0x180011dc5  push    rdi; int
0x180011dc6  sub     rsp, 20h
0x180011dca  cmp     dword ptr [rcx+0F8h], 0
0x180011dd1  mov     rdi, rdx
0x180011dd4  mov     rbx, rcx
0x180011dd7  jnz     short loc_180011E18
0x180011dd9  mov     dword ptr [rcx+0F8h], 1
0x180011de3  mov     ecx, 18h; cb
0x180011de8  call    cs:__imp_CoTaskMemAlloc
0x180011dee  mov     rdx, rax
0x180011df1  test    rax, rax
0x180011df4  jz      short loc_180011E1F
0x180011df6  mov     word ptr [rax], 13h
0x180011dfb  mov     rax, [rbx+8]
0x180011dff  mov     ecx, [rax+13C8h]
0x180011e05  xor     eax, eax
0x180011e07  mov     [rdx+8], ecx
0x180011e0a  mov     [rdi], rdx
0x180011e0d  mov     rbx, [rsp+28h+arg_0]
0x180011e12  add     rsp, 20h
0x180011e16  pop     rdi
0x180011e17  retn
0x180011e18  mov     eax, 80041702h
0x180011e1d  jmp     short loc_180011E0D
0x180011e1f  mov     rcx, [rsp+28h]; this
0x180011e24  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180011e2b  mov     r9d, 8007000Eh; char *
0x180011e31  mov     edx, 0EBh; void *
0x180011e36  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
