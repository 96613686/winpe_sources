# CElementWithIUnknown::GetUnknownFromElement(DirectUI::Element *)

- ea: `0x18002f130`
- end: `0x18002f1b5`
- name: `?GetUnknownFromElement@CElementWithIUnknown@@SAPEAUIUnknown@@PEAVElement@DirectUI@@@Z`
- size: `133`
- prototype: `struct IUnknown *__fastcall(struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002e230`

## callees

- `0x18002f130`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002f18b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002f18b`

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
0x18002f130  push    rbx
0x18002f132  push    rbp
0x18002f133  push    rsi
0x18002f134  push    rdi
0x18002f135  sub     rsp, 38h
0x18002f139  mov     rax, [rcx]
0x18002f13c  mov     rsi, rcx
0x18002f13f  xor     ebp, ebp
0x18002f141  mov     rax, [rax+118h]
0x18002f148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f14d  mov     rdi, rax
0x18002f150  test    rax, rax
0x18002f153  jz      short loc_18002F1A9
0x18002f155  mov     rcx, cs:?Class@CElementWithIUnknown@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * CElementWithIUnknown::Class
0x18002f15c  mov     rax, [rcx]
0x18002f15f  mov     rax, [rax+40h]
0x18002f163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f168  mov     rbx, rax
0x18002f16b  mov     rcx, rdi
0x18002f16e  mov     rax, [rdi]
0x18002f171  mov     rax, [rax+40h]
0x18002f175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f17a  or      r9d, 0FFFFFFFFh; cchCount2
0x18002f17e  mov     [rsp+58h+bIgnoreCase], ebp; bIgnoreCase
0x18002f182  or      edx, r9d; cchCount1
0x18002f185  mov     r8, rbx; lpString2
0x18002f188  mov     rcx, rax; lpString1
0x18002f18b  call    cs:__imp_CompareStringOrdinal
0x18002f191  cmp     eax, 2
0x18002f194  jz      short loc_18002F1A2
0x18002f196  mov     rax, [rdi]
0x18002f199  mov     rcx, rdi
0x18002f19c  mov     rax, [rax+38h]
0x18002f1a0  jmp     short loc_18002F148
0x18002f1a2  lea     rbp, [rsi+0C8h]
0x18002f1a9  mov     rax, rbp
0x18002f1ac  add     rsp, 38h
0x18002f1b0  pop     rdi
0x18002f1b1  pop     rsi
0x18002f1b2  pop     rbp
0x18002f1b3  pop     rbx
0x18002f1b4  retn
```
