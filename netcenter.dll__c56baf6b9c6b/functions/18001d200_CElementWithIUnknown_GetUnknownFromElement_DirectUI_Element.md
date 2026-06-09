# CElementWithIUnknown::GetUnknownFromElement(DirectUI::Element *)

- ea: `0x18001d200`
- end: `0x18001d285`
- name: `?GetUnknownFromElement@CElementWithIUnknown@@SAPEAUIUnknown@@PEAVElement@DirectUI@@@Z`
- size: `133`
- prototype: `struct IUnknown *__fastcall(struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001bec0`

## callees

- `0x18001d200`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d25b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d25b`

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
0x18001d200  push    rbx
0x18001d202  push    rbp
0x18001d203  push    rsi
0x18001d204  push    rdi
0x18001d205  sub     rsp, 38h
0x18001d209  mov     rax, [rcx]
0x18001d20c  mov     rsi, rcx
0x18001d20f  xor     ebp, ebp
0x18001d211  mov     rax, [rax+118h]
0x18001d218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d21d  mov     rdi, rax
0x18001d220  test    rax, rax
0x18001d223  jz      short loc_18001D279
0x18001d225  mov     rcx, cs:?Class@CElementWithIUnknown@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * CElementWithIUnknown::Class
0x18001d22c  mov     rax, [rcx]
0x18001d22f  mov     rax, [rax+40h]
0x18001d233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d238  mov     rbx, rax
0x18001d23b  mov     rcx, rdi
0x18001d23e  mov     rax, [rdi]
0x18001d241  mov     rax, [rax+40h]
0x18001d245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d24a  or      r9d, 0FFFFFFFFh; cchCount2
0x18001d24e  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x18001d252  or      edx, r9d; cchCount1
0x18001d255  mov     r8, rbx; lpString2
0x18001d258  mov     rcx, rax; lpString1
0x18001d25b  call    cs:__imp_CompareStringOrdinal
0x18001d261  cmp     eax, 2
0x18001d264  jz      short loc_18001D272
0x18001d266  mov     rax, [rdi]
0x18001d269  mov     rcx, rdi
0x18001d26c  mov     rax, [rax+38h]
0x18001d270  jmp     short loc_18001D218
0x18001d272  lea     rbp, [rsi+0C8h]
0x18001d279  mov     rax, rbp
0x18001d27c  add     rsp, 38h
0x18001d280  pop     rdi
0x18001d281  pop     rsi
0x18001d282  pop     rbp
0x18001d283  pop     rbx
0x18001d284  retn
```
