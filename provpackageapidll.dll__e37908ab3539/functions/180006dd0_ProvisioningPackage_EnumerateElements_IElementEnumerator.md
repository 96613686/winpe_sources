# ProvisioningPackage::EnumerateElements(IElementEnumerator * *)

- ea: `0x180006dd0`
- end: `0x180006efe`
- name: `?EnumerateElements@ProvisioningPackage@@EEAAJPEAPEAUIElementEnumerator@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(ProvisioningPackage *__hidden this, struct IElementEnumerator **)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180002084`
- `0x180006014`
- `0x180006dd0`
- `0x18000d010`
- `0x180019010`

## string_xrefs

- `0x180006e9e`: `    Failed to create element enumerator`

## pseudocode

```c
__int64 __fastcall ProvisioningPackage::EnumerateElements(ProvisioningPackage *this, struct IElementEnumerator **a2)
{
  _QWORD *v4; // rbx
  __int64 result; // rax
  unsigned int v6; // edi

  v4 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
  {
    *v4 = &ElementEnumerator::`vftable';
    v4[2] = 0;
    v4[3] = 0;
    v4[4] = 0;
    v4[5] = 0;
    v4[6] = 0;
    v4[7] = 0;
    *((_BYTE *)v4 + 64) = 1;
    result = ElementEnumerator::CreateElementEnumerator((ElementEnumerator *)v4, this);
    v6 = result;
    if ( (int)result >= 0 )
    {
      *a2 = (struct IElementEnumerator *)v4;
      return result;
    }
    (*(void (__fastcall **)(_QWORD *))(*v4 + 8LL))(v4);
    *a2 = 0;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::EnumerateElements",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      625,
      v6);
    ProvPackageLog(3, L"    Failed to create element enumerator");
  }
  else
  {
    v6 = -2147024882;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::EnumerateElements",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      614,
      -2147024882);
    ProvPackageLog(3, L"    Failed to allocate ptr");
  }
  return v6;
}

```

## disassembly

```asm
0x180006dd0  mov     [rsp+arg_0], rbx
0x180006dd5  mov     [rsp+arg_8], rsi
0x180006dda  push    rdi
0x180006ddb  sub     rsp, 30h
0x180006ddf  mov     rsi, rdx
0x180006de2  mov     rdi, rcx
0x180006de5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006dec  mov     ecx, 48h ; 'H'; unsigned __int64
0x180006df1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006df6  mov     [rsp+38h+arg_10], rax
0x180006dfb  mov     rbx, rax
0x180006dfe  test    rax, rax
0x180006e01  jz      loc_180006EAC
0x180006e07  lea     rax, ??_7ElementEnumerator@@6B@; const ElementEnumerator::`vftable'
0x180006e0e  mov     [rbx], rax
0x180006e11  mov     qword ptr [rbx+10h], 0
0x180006e19  mov     qword ptr [rbx+18h], 0
0x180006e21  mov     qword ptr [rbx+20h], 0
0x180006e29  mov     qword ptr [rbx+28h], 0
0x180006e31  mov     qword ptr [rbx+30h], 0
0x180006e39  mov     qword ptr [rbx+38h], 0
0x180006e41  mov     byte ptr [rbx+40h], 1
0x180006e45  test    rbx, rbx
0x180006e48  jz      short loc_180006EAC
0x180006e4a  mov     rdx, rdi; struct ProvisioningPackage *
0x180006e4d  mov     rcx, rbx; this
0x180006e50  call    ?CreateElementEnumerator@ElementEnumerator@@QEAAJPEAVProvisioningPackage@@@Z; ElementEnumerator::CreateElementEnumerator(ProvisioningPackage *)
0x180006e55  mov     edi, eax
0x180006e57  test    eax, eax
0x180006e59  jns     short loc_180006EA7
0x180006e5b  mov     rdx, [rbx]
0x180006e5e  mov     rcx, rbx
0x180006e61  mov     rax, [rdx+8]
0x180006e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e6a  mov     ebx, 3
0x180006e6f  mov     [rsp+38h+var_10], edi
0x180006e73  mov     ecx, ebx
0x180006e75  mov     qword ptr [rsi], 0
0x180006e7c  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180006e83  mov     [rsp+38h+var_18], 271h
0x180006e8b  lea     r8, aProvisioningpa_11; "ProvisioningPackage::EnumerateElements"
0x180006e92  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180006e99  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180006e9e  lea     rdx, aFailedToCreate_0; "    Failed to create element enumerator"
0x180006ea5  jmp     short loc_180006EE5
0x180006ea7  mov     [rsi], rbx
0x180006eaa  jmp     short loc_180006EEE
0x180006eac  mov     edi, 8007000Eh
0x180006eb1  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180006eb8  mov     ebx, 3
0x180006ebd  mov     [rsp+38h+var_10], edi
0x180006ec1  mov     ecx, ebx
0x180006ec3  mov     [rsp+38h+var_18], 266h
0x180006ecb  lea     r8, aProvisioningpa_11; "ProvisioningPackage::EnumerateElements"
0x180006ed2  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180006ed9  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180006ede  lea     rdx, aFailedToAlloca_0; "    Failed to allocate ptr"
0x180006ee5  mov     ecx, ebx
0x180006ee7  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180006eec  mov     eax, edi
0x180006eee  mov     rbx, [rsp+38h+arg_0]
0x180006ef3  mov     rsi, [rsp+38h+arg_8]
0x180006ef8  add     rsp, 30h
0x180006efc  pop     rdi
0x180006efd  retn
```
