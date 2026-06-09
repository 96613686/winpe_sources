# CElementWithIUnknown::GetUnknownFromElement(DirectUI::Element *)

- ea: `0x180017480`
- end: `0x180017505`
- name: `?GetUnknownFromElement@CElementWithIUnknown@@SAPEAUIUnknown@@PEAVElement@DirectUI@@@Z`
- size: `133`
- prototype: `struct IUnknown *__fastcall(struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016b70`

## callees

- `0x180017480`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800174db`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800174db`

## pseudocode

```c
struct IUnknown *__fastcall CElementWithIUnknown::GetUnknownFromElement(struct DirectUI::Element *a1)
{
  __int64 v2; // rbp
  __int64 (*i)(void); // rax
  __int64 v4; // rdi
  const WCHAR *v5; // rbx
  const WCHAR *v6; // rax

  v2 = 0;
  for ( i = *(__int64 (**)(void))(*(_QWORD *)a1 + 280LL); ; i = *(__int64 (**)(void))(*(_QWORD *)v4 + 56LL) )
  {
    v4 = i();
    if ( !v4 )
      break;
    v5 = (const WCHAR *)(*(__int64 (__fastcall **)(struct DirectUI::IClassInfo *))(*(_QWORD *)CElementWithIUnknown::Class
                                                                                 + 64LL))(CElementWithIUnknown::Class);
    v6 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 64LL))(v4);
    if ( CompareStringOrdinal(v6, -1, v5, -1, 0) == 2 )
      return (struct IUnknown *)((char *)a1 + 200);
  }
  return (struct IUnknown *)v2;
}

```

## disassembly

```asm
0x180017480  push    rbx
0x180017482  push    rbp
0x180017483  push    rsi
0x180017484  push    rdi
0x180017485  sub     rsp, 38h
0x180017489  mov     rax, [rcx]
0x18001748c  mov     rsi, rcx
0x18001748f  xor     ebp, ebp
0x180017491  mov     rax, [rax+118h]
0x180017498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001749d  mov     rdi, rax
0x1800174a0  test    rax, rax
0x1800174a3  jz      short loc_1800174F9
0x1800174a5  mov     rcx, cs:?Class@CElementWithIUnknown@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * CElementWithIUnknown::Class
0x1800174ac  mov     rax, [rcx]
0x1800174af  mov     rax, [rax+40h]
0x1800174b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174b8  mov     rbx, rax
0x1800174bb  mov     rcx, rdi
0x1800174be  mov     rax, [rdi]
0x1800174c1  mov     rax, [rax+40h]
0x1800174c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174ca  or      r9d, 0FFFFFFFFh; cchCount2
0x1800174ce  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x1800174d2  or      edx, r9d; cchCount1
0x1800174d5  mov     r8, rbx; lpString2
0x1800174d8  mov     rcx, rax; lpString1
0x1800174db  call    cs:__imp_CompareStringOrdinal
0x1800174e1  cmp     eax, 2
0x1800174e4  jz      short loc_1800174F2
0x1800174e6  mov     rax, [rdi]
0x1800174e9  mov     rcx, rdi
0x1800174ec  mov     rax, [rax+38h]
0x1800174f0  jmp     short loc_180017498
0x1800174f2  lea     rbp, [rsi+0C8h]
0x1800174f9  mov     rax, rbp
0x1800174fc  add     rsp, 38h
0x180017500  pop     rdi
0x180017501  pop     rsi
0x180017502  pop     rbp
0x180017503  pop     rbx
0x180017504  retn
```
