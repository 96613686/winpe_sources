# ProvisioningPackage::EnumerateElements(_PROVISIONINGELEMENTTYPE,IElementEnumerator * *)

- ea: `0x180006f10`
- end: `0x180007036`
- name: `?EnumerateElements@ProvisioningPackage@@EEAAJW4_PROVISIONINGELEMENTTYPE@@PEAPEAUIElementEnumerator@@@Z`
- size: `294`
- prototype: `__int64 __fastcall(__int64, int, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180002084`
- `0x180006014`
- `0x180006f10`
- `0x18000d0c4`
- `0x180019010`

## string_xrefs

- `0x180006fdd`: `    Failed to create element enumerator`

## pseudocode

```c
__int64 __fastcall ProvisioningPackage::EnumerateElements(__int64 a1, int a2, _QWORD *a3)
{
  _QWORD *v6; // rbx
  __int64 result; // rax
  unsigned int v8; // edi

  v6 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v6 )
  {
    *v6 = &ElementEnumerator::`vftable';
    v6[2] = 0;
    v6[3] = 0;
    v6[4] = 0;
    v6[5] = 0;
    v6[6] = 0;
    v6[7] = 0;
    *((_BYTE *)v6 + 64) = 1;
    result = ElementEnumerator::CreateElementEnumerator((__int64)v6, a1, a2);
    v8 = result;
    if ( (int)result >= 0 )
    {
      *a3 = v6;
      return result;
    }
    (*(void (__fastcall **)(_QWORD *))(*v6 + 8LL))(v6);
    *a3 = 0;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::EnumerateElements",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      648,
      v8);
    ProvPackageLog(3, L"    Failed to create element enumerator");
  }
  else
  {
    v8 = -2147024882;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ProvisioningPackage::EnumerateElements",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\provisioningpackage.cpp",
      637,
      -2147024882);
    ProvPackageLog(3, L"    Failed to allocate ptr");
  }
  return v8;
}

```

## disassembly

```asm
0x180006f10  push    rbx
0x180006f12  push    rbp
0x180006f13  push    rsi
0x180006f14  push    rdi
0x180006f15  sub     rsp, 38h
0x180006f19  mov     edi, edx
0x180006f1b  mov     rbp, rcx
0x180006f1e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006f25  mov     ecx, 48h ; 'H'; unsigned __int64
0x180006f2a  mov     rsi, r8
0x180006f2d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006f32  mov     [rsp+58h+arg_18], rax
0x180006f37  mov     rbx, rax
0x180006f3a  test    rax, rax
0x180006f3d  jz      loc_180006FEB
0x180006f43  lea     rax, ??_7ElementEnumerator@@6B@; const ElementEnumerator::`vftable'
0x180006f4a  mov     [rbx], rax
0x180006f4d  mov     qword ptr [rbx+10h], 0
0x180006f55  mov     qword ptr [rbx+18h], 0
0x180006f5d  mov     qword ptr [rbx+20h], 0
0x180006f65  mov     qword ptr [rbx+28h], 0
0x180006f6d  mov     qword ptr [rbx+30h], 0
0x180006f75  mov     qword ptr [rbx+38h], 0
0x180006f7d  mov     byte ptr [rbx+40h], 1
0x180006f81  test    rbx, rbx
0x180006f84  jz      short loc_180006FEB
0x180006f86  mov     r8d, edi
0x180006f89  mov     rdx, rbp
0x180006f8c  mov     rcx, rbx
0x180006f8f  call    ?CreateElementEnumerator@ElementEnumerator@@QEAAJPEAVProvisioningPackage@@W4_PROVISIONINGELEMENTTYPE@@@Z; ElementEnumerator::CreateElementEnumerator(ProvisioningPackage *,_PROVISIONINGELEMENTTYPE)
0x180006f94  mov     edi, eax
0x180006f96  test    eax, eax
0x180006f98  jns     short loc_180006FE6
0x180006f9a  mov     rdx, [rbx]
0x180006f9d  mov     rcx, rbx
0x180006fa0  mov     rax, [rdx+8]
0x180006fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fa9  mov     ebx, 3
0x180006fae  mov     [rsp+58h+var_30], edi
0x180006fb2  mov     ecx, ebx
0x180006fb4  mov     qword ptr [rsi], 0
0x180006fbb  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180006fc2  mov     [rsp+58h+var_38], 288h
0x180006fca  lea     r8, aProvisioningpa_11; "ProvisioningPackage::EnumerateElements"
0x180006fd1  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180006fd8  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180006fdd  lea     rdx, aFailedToCreate_0; "    Failed to create element enumerator"
0x180006fe4  jmp     short loc_180007024
0x180006fe6  mov     [rsi], rbx
0x180006fe9  jmp     short loc_18000702D
0x180006feb  mov     edi, 8007000Eh
0x180006ff0  lea     r9, aOnecoreBaseNts_7; "onecore\\base\\ntsetup\\provpackageapi"...
0x180006ff7  mov     ebx, 3
0x180006ffc  mov     [rsp+58h+var_30], edi
0x180007000  mov     ecx, ebx
0x180007002  mov     [rsp+58h+var_38], 27Dh
0x18000700a  lea     r8, aProvisioningpa_11; "ProvisioningPackage::EnumerateElements"
0x180007011  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180007018  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000701d  lea     rdx, aFailedToAlloca_0; "    Failed to allocate ptr"
0x180007024  mov     ecx, ebx
0x180007026  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000702b  mov     eax, edi
0x18000702d  add     rsp, 38h
0x180007031  pop     rdi
0x180007032  pop     rsi
0x180007033  pop     rbp
0x180007034  pop     rbx
0x180007035  retn
```
