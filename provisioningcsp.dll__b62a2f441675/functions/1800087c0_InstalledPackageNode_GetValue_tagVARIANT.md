# InstalledPackageNode::GetValue(tagVARIANT *)

- ea: `0x1800087c0`
- end: `0x180008825`
- name: `?GetValue@InstalledPackageNode@@UEAAJPEAUtagVARIANT@@@Z`
- size: `101`
- prototype: `int(InstalledPackageNode *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180006974`
- `0x1800087c0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800087df`
- `OLEAUT32!__imp_SysAllocString` at `0x1800087df`

## string_xrefs

- `0x1800087f5`: `onecoreuap\admin\prov\provcsp\installedpackagenode.cpp`

## pseudocode

```c
__int64 __fastcall InstalledPackageNode::GetValue(InstalledPackageNode *this, struct tagVARIANT *a2)
{
  char *v2; // rcx
  BSTR v4; // rax
  __int64 result; // rax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (char *)this + 56;
  if ( *((_QWORD *)v2 + 3) >= 8u )
    v2 = *(char **)v2;
  v4 = SysAllocString((const OLECHAR *)v2);
  if ( v4 )
  {
    a2->llVal = (LONGLONG)v4;
    result = 0;
    a2->vt = 8;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\installedpackagenode.cpp",
      (const char *)0x8007000ELL,
      v6);
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800087c0  mov     [rsp+arg_0], rbx
0x1800087c5  push    rdi; int
0x1800087c6  sub     rsp, 20h
0x1800087ca  add     rcx, 38h ; '8'
0x1800087ce  mov     edi, 8
0x1800087d3  mov     rbx, rdx
0x1800087d6  cmp     [rcx+18h], rdi
0x1800087da  jb      short loc_1800087DF
0x1800087dc  mov     rcx, [rcx]; psz
0x1800087df  call    cs:__imp_SysAllocString
0x1800087e6  nop     dword ptr [rax+rax+00h]
0x1800087eb  test    rax, rax
0x1800087ee  jnz     short loc_180008810
0x1800087f0  mov     rcx, [rsp+28h]; this
0x1800087f5  lea     r8, aOnecoreuapAdmi_26; "onecoreuap\\admin\\prov\\provcsp\\insta"...
0x1800087fc  mov     ebx, 8007000Eh
0x180008801  lea     edx, [rax+67h]; void *
0x180008804  mov     r9d, ebx; char *
0x180008807  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000880c  mov     eax, ebx
0x18000880e  jmp     short loc_180008819
0x180008810  mov     [rbx+8], rax
0x180008814  xor     eax, eax
0x180008816  mov     [rbx], di
0x180008819  mov     rbx, [rsp+28h+arg_0]
0x18000881e  add     rsp, 20h
0x180008822  pop     rdi
0x180008823  retn
```
