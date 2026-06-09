# stringCmpI(wchar_t const *,wchar_t const *)

- ea: `0x180005d0c`
- end: `0x180005db8`
- name: `?stringCmpI@@YAHPEB_W0@Z`
- size: `172`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800064c4`

## callees

- `0x180005d0c`
- `0x180014860`
- `0x1800148c8`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180005d9e`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180005d9e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005d7e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005d7e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005d52`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005d52`

## pseudocode

```c
int __fastcall stringCmpI(PCNZWCH lpString1, PCNZWCH lpString2)
{
  if ( __TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                            + (unsigned int)tls_index)
                                                          + 4LL) )
  {
    Init_thread_header(&__TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA);
    if ( __TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA == -1 )
    {
      `stringCmpI'::`2'::lcidSystem = GetSystemDefaultLCID();
      Init_thread_footer(&__TSS0__1__stringCmpI__YAHPEB_W0_Z_4HA);
    }
  }
  if ( `stringCmpI'::`2'::lcidSystem == 1055 )
    return CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2, -1) - 2;
  else
    return lstrcmpiW(lpString1, lpString2);
}

```

## disassembly

```asm
0x180005d0c  mov     [rsp+arg_0], rbx
0x180005d11  push    rdi
0x180005d12  sub     rsp, 30h
0x180005d16  mov     r8d, cs:_tls_index
0x180005d1d  mov     rdi, rcx
0x180005d20  mov     rax, gs:58h
0x180005d29  mov     rbx, rdx
0x180005d2c  mov     ecx, 4
0x180005d31  mov     rax, [rax+r8*8]
0x180005d35  mov     eax, [rcx+rax]
0x180005d38  cmp     cs:?$TSS0@?1??stringCmpI@@YAHPEB_W0@Z@4HA, eax
0x180005d3e  jg      short loc_180005D89
0x180005d40  cmp     cs:?lcidSystem@?1??stringCmpI@@YAHPEB_W0@Z@4KA, 41Fh; ulong `stringCmpI(wchar_t const *,wchar_t const *)'::`2'::lcidSystem
0x180005d4a  jz      short loc_180005D63
0x180005d4c  mov     rdx, rbx; lpString2
0x180005d4f  mov     rcx, rdi; lpString1
0x180005d52  call    cs:__imp_lstrcmpiW
0x180005d58  mov     rbx, [rsp+38h+arg_0]
0x180005d5d  add     rsp, 30h
0x180005d61  pop     rdi
0x180005d62  retn
0x180005d63  or      r9d, 0FFFFFFFFh; cchCount1
0x180005d67  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x180005d6f  mov     r8, rdi; lpString1
0x180005d72  mov     [rsp+38h+lpString2], rbx; lpString2
0x180005d77  lea     edx, [r9+2]; dwCmpFlags
0x180005d7b  lea     ecx, [rdx+7Eh]; Locale
0x180005d7e  call    cs:__imp_CompareStringW
0x180005d84  sub     eax, 2
0x180005d87  jmp     short loc_180005D58
0x180005d89  lea     rcx, ?$TSS0@?1??stringCmpI@@YAHPEB_W0@Z@4HA
0x180005d90  call    _Init_thread_header
0x180005d95  cmp     cs:?$TSS0@?1??stringCmpI@@YAHPEB_W0@Z@4HA, 0FFFFFFFFh
0x180005d9c  jnz     short loc_180005D40
0x180005d9e  call    cs:__imp_GetSystemDefaultLCID
0x180005da4  lea     rcx, ?$TSS0@?1??stringCmpI@@YAHPEB_W0@Z@4HA
0x180005dab  mov     cs:?lcidSystem@?1??stringCmpI@@YAHPEB_W0@Z@4KA, eax; ulong `stringCmpI(wchar_t const *,wchar_t const *)'::`2'::lcidSystem
0x180005db1  call    _Init_thread_footer
0x180005db6  jmp     short loc_180005D40
```
