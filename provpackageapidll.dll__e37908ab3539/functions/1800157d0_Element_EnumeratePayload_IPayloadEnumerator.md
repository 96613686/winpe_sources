# Element::EnumeratePayload(IPayloadEnumerator * *)

- ea: `0x1800157d0`
- end: `0x180015925`
- name: `?EnumeratePayload@Element@@EEAAJPEAPEAUIPayloadEnumerator@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(Element *__hidden this, struct IPayloadEnumerator **)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180002084`
- `0x180002110`
- `0x180006014`
- `0x1800157d0`
- `0x180017608`
- `0x180019010`

## string_xrefs

- `0x1800158fb`: `    Failed to create payload enumerator`

## pseudocode

```c
__int64 __fastcall Element::EnumeratePayload(Element *this, struct IPayloadEnumerator **a2)
{
  PayloadEnumerator *v4; // rdi
  _QWORD *v5; // rax
  int PayloadEnumerator; // ebp

  *a2 = 0;
  v4 = (PayloadEnumerator *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
  {
    *(_QWORD *)v4 = &PayloadEnumerator::`vftable';
    *((_QWORD *)v4 + 1) = 0;
    *((_QWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 3) = 0;
    *((_QWORD *)v4 + 4) = 0;
    *((_QWORD *)v4 + 5) = 0;
    *((_QWORD *)v4 + 6) = 0;
    *((_QWORD *)v4 + 7) = 0;
    *((_QWORD *)v4 + 8) = 0;
    *((_QWORD *)v4 + 9) = 0;
    *((_QWORD *)v4 + 10) = 0;
    *((_QWORD *)v4 + 11) = 0;
    v5 = operator new(0x10u);
    v5[1] = 0;
    *((_QWORD *)v4 + 7) = v5;
    *v5 = (char *)v4 + 56;
  }
  else
  {
    v4 = 0;
  }
  if ( v4 )
  {
    PayloadEnumerator = PayloadEnumerator::CreatePayloadEnumerator(
                          v4,
                          *(void **)(*((_QWORD *)this + 1) + 16LL),
                          *((const unsigned __int16 **)this + 2));
    if ( PayloadEnumerator >= 0 )
    {
      *a2 = v4;
      return 0;
    }
    else
    {
      (*(void (__fastcall **)(PayloadEnumerator *))(*(_QWORD *)v4 + 16LL))(v4);
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "Element::EnumeratePayload",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
        456,
        PayloadEnumerator);
      ProvPackageLog(3, L"    Failed to create payload enumerator");
      return (unsigned int)PayloadEnumerator;
    }
  }
  else
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "Element::EnumeratePayload",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\element.cpp",
      449,
      -2147024882);
    ProvPackageLog(3, L"    Failed to allocate ptr");
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800157d0  mov     [rsp+arg_0], rbx
0x1800157d5  mov     [rsp+arg_18], rbp
0x1800157da  push    rsi
0x1800157db  push    rdi
0x1800157dc  push    r14
0x1800157de  sub     rsp, 30h
0x1800157e2  mov     rsi, rdx
0x1800157e5  mov     rbp, rcx
0x1800157e8  xor     r14d, r14d
0x1800157eb  mov     [rdx], r14
0x1800157ee  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800157f5  lea     ecx, [r14+60h]; unsigned __int64
0x1800157f9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800157fe  mov     rdi, rax
0x180015801  mov     [rsp+48h+arg_8], rax
0x180015806  test    rax, rax
0x180015809  jz      short loc_180015859
0x18001580b  lea     rax, ??_7PayloadEnumerator@@6B@; const PayloadEnumerator::`vftable'
0x180015812  mov     [rdi], rax
0x180015815  mov     [rdi+8], r14
0x180015819  mov     [rdi+10h], r14
0x18001581d  mov     [rdi+18h], r14
0x180015821  mov     [rdi+20h], r14
0x180015825  mov     [rdi+28h], r14
0x180015829  mov     [rdi+30h], r14
0x18001582d  lea     rbx, [rdi+38h]
0x180015831  mov     [rbx], r14
0x180015834  mov     [rbx+8], r14
0x180015838  mov     [rbx+10h], r14
0x18001583c  mov     [rbx+18h], r14
0x180015840  mov     [rbx+20h], r14
0x180015844  lea     ecx, [r14+10h]; Size
0x180015848  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001584d  mov     [rax+8], r14
0x180015851  mov     [rbx], rax
0x180015854  mov     [rax], rbx
0x180015857  jmp     short loc_18001585C
0x180015859  mov     rdi, r14
0x18001585c  test    rdi, rdi
0x18001585f  jnz     short loc_1800158A5
0x180015861  mov     edi, 8007000Eh
0x180015866  mov     [rsp+48h+var_20], edi
0x18001586a  mov     [rsp+48h+var_28], 1C1h
0x180015872  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x180015879  lea     r8, aElementEnumera_0; "Element::EnumeratePayload"
0x180015880  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180015887  mov     ebx, 3
0x18001588c  mov     ecx, ebx
0x18001588e  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180015893  lea     rdx, aFailedToAlloca_0; "    Failed to allocate ptr"
0x18001589a  mov     ecx, ebx
0x18001589c  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800158a1  mov     eax, edi
0x1800158a3  jmp     short loc_180015912
0x1800158a5  mov     rdx, [rbp+8]
0x1800158a9  mov     r8, [rbp+10h]; unsigned __int16 *
0x1800158ad  mov     rdx, [rdx+10h]; void *
0x1800158b1  mov     rcx, rdi; this
0x1800158b4  call    ?CreatePayloadEnumerator@PayloadEnumerator@@QEAAJPEAXPEBG@Z; PayloadEnumerator::CreatePayloadEnumerator(void *,ushort const *)
0x1800158b9  mov     ebp, eax
0x1800158bb  test    eax, eax
0x1800158bd  jns     short loc_18001590D
0x1800158bf  mov     rdx, [rdi]
0x1800158c2  mov     rcx, rdi
0x1800158c5  mov     rax, [rdx+10h]
0x1800158c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158ce  mov     [rsp+48h+var_20], ebp
0x1800158d2  mov     [rsp+48h+var_28], 1C8h
0x1800158da  lea     r9, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800158e1  lea     r8, aElementEnumera_0; "Element::EnumeratePayload"
0x1800158e8  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x1800158ef  mov     ebx, 3
0x1800158f4  mov     ecx, ebx
0x1800158f6  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x1800158fb  lea     rdx, aFailedToCreate_4; "    Failed to create payload enumerator"
0x180015902  mov     ecx, ebx
0x180015904  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180015909  mov     eax, ebp
0x18001590b  jmp     short loc_180015912
0x18001590d  mov     [rsi], rdi
0x180015910  xor     eax, eax
0x180015912  mov     rbx, [rsp+48h+arg_0]
0x180015917  mov     rbp, [rsp+48h+arg_18]
0x18001591c  add     rsp, 30h
0x180015920  pop     r14
0x180015922  pop     rdi
0x180015923  pop     rsi
0x180015924  retn
```
