# ReadBOOLEANFromXMLNode(IXMLDOMNode *,int *)

- ea: `0x18002e060`
- end: `0x18002e10f`
- name: `?ReadBOOLEANFromXMLNode@@YAJPEAUIXMLDOMNode@@PEAH@Z`
- size: `175`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002e118`

## callees

- `0x18002e060`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002e0a4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002e0ba`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002e0d0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002e0e6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002e0a4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002e0ba`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002e0d0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002e0e6`

## pseudocode

```c
__int64 __fastcall ReadBOOLEANFromXMLNode(struct IXMLDOMNode *a1, int *a2)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v4; // ebx
  int v5; // eax
  LPCWSTR lpString1; // [rsp+30h] [rbp+8h] BYREF

  lpVtbl = a1->lpVtbl;
  lpString1 = 0;
  v4 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, LPCWSTR *))lpVtbl->get_text)(a1, &lpString1);
  if ( v4 >= 0 )
  {
    if ( lstrcmpiW(lpString1, L"true") && lstrcmpiW(lpString1, L"1") )
    {
      if ( lstrcmpiW(lpString1, L"false") && lstrcmpiW(lpString1, L"0") )
        return (unsigned int)-2147467259;
      v5 = 0;
    }
    else
    {
      v5 = 1;
    }
    *a2 = v5;
    return (unsigned int)v4;
  }
  *a2 = 0;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002e060  mov     [rsp+arg_8], rbx
0x18002e065  push    rdi
0x18002e066  sub     rsp, 20h
0x18002e06a  mov     rax, [rcx]
0x18002e06d  mov     rdi, rdx
0x18002e070  lea     rdx, [rsp+28h+lpString1]
0x18002e075  mov     [rsp+28h+lpString1], 0
0x18002e07e  mov     rax, [rax+0D0h]
0x18002e085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e08a  mov     ebx, eax
0x18002e08c  test    eax, eax
0x18002e08e  jns     short loc_18002E098
0x18002e090  mov     dword ptr [rdi], 0
0x18002e096  jmp     short loc_18002E102
0x18002e098  mov     rcx, [rsp+28h+lpString1]; lpString1
0x18002e09d  lea     rdx, aTrue; "true"
0x18002e0a4  call    cs:__imp_lstrcmpiW
0x18002e0aa  test    eax, eax
0x18002e0ac  jz      short loc_18002E0FB
0x18002e0ae  mov     rcx, [rsp+28h+lpString1]; lpString1
0x18002e0b3  lea     rdx, a1; "1"
0x18002e0ba  call    cs:__imp_lstrcmpiW
0x18002e0c0  test    eax, eax
0x18002e0c2  jz      short loc_18002E0FB
0x18002e0c4  mov     rcx, [rsp+28h+lpString1]; lpString1
0x18002e0c9  lea     rdx, aFalse; "false"
0x18002e0d0  call    cs:__imp_lstrcmpiW
0x18002e0d6  test    eax, eax
0x18002e0d8  jz      short loc_18002E0F7
0x18002e0da  mov     rcx, [rsp+28h+lpString1]; lpString1
0x18002e0df  lea     rdx, a0; "0"
0x18002e0e6  call    cs:__imp_lstrcmpiW
0x18002e0ec  test    eax, eax
0x18002e0ee  jz      short loc_18002E0F7
0x18002e0f0  mov     ebx, 80004005h
0x18002e0f5  jmp     short loc_18002E102
0x18002e0f7  xor     eax, eax
0x18002e0f9  jmp     short loc_18002E100
0x18002e0fb  mov     eax, 1
0x18002e100  mov     [rdi], eax
0x18002e102  mov     eax, ebx
0x18002e104  mov     rbx, [rsp+28h+arg_8]
0x18002e109  add     rsp, 20h
0x18002e10d  pop     rdi
0x18002e10e  retn
```
