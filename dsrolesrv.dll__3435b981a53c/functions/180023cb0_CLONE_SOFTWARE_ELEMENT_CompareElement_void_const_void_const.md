# CLONE_SOFTWARE_ELEMENT::CompareElement(void const *,void const *)

- ea: `0x180023cb0`
- end: `0x180023cec`
- name: `?CompareElement@CLONE_SOFTWARE_ELEMENT@@SAHPEBX0@Z`
- size: `60`
- prototype: `__int64 __fastcall(PCNZWCH **, PCNZWCH **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180023cb0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180023cde`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180023cde`

## pseudocode

```c
__int64 __fastcall CLONE_SOFTWARE_ELEMENT::CompareElement(PCNZWCH **a1, PCNZWCH **a2)
{
  __int64 result; // rax

  result = (unsigned int)(*((_DWORD *)*a2 + 2) - *((_DWORD *)*a1 + 2));
  if ( !(_DWORD)result )
    return (unsigned int)(CompareStringW(0x7Fu, 1u, **a1, -1, **a2, -1) - 2);
  return result;
}

```

## disassembly

```asm
0x180023cb0  sub     rsp, 38h
0x180023cb4  mov     r8, [rcx]
0x180023cb7  mov     rcx, [rdx]
0x180023cba  mov     eax, [rcx+8]
0x180023cbd  sub     eax, [r8+8]
0x180023cc1  jnz     short loc_180023CE7
0x180023cc3  mov     rax, [rcx]
0x180023cc6  or      r9d, 0FFFFFFFFh; cchCount1
0x180023cca  mov     r8, [r8]; lpString1
0x180023ccd  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x180023cd2  mov     [rsp+38h+lpString2], rax; lpString2
0x180023cd7  lea     edx, [r9+2]; dwCmpFlags
0x180023cdb  lea     ecx, [rdx+7Eh]; Locale
0x180023cde  call    cs:__imp_CompareStringW
0x180023ce4  sub     eax, 2
0x180023ce7  add     rsp, 38h
0x180023ceb  retn
```
