# FhePathOperations::IsSourcePathSupported(ushort const *)

- ea: `0x18002acd4`
- end: `0x18002ad40`
- name: `?IsSourcePathSupported@FhePathOperations@@YAHPEBG@Z`
- size: `108`
- prototype: `_BOOL8 __fastcall(LPCWSTR lpString, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001cb74`
- `0x18001eaf0`
- `0x1800236d0`

## callees

- `0x18002acd4`
- `0x18002e2a4`

## import_xrefs

- `KERNEL32!IsNLSDefinedString` at `0x18002ad1b`
- `KERNEL32!IsNLSDefinedString` at `0x18002ad1b`

## pseudocode

```c
_BOOL8 __fastcall FhePathOperations::IsSourcePathSupported(LPCWSTR lpString, const unsigned __int16 *a2)
{
  unsigned __int64 v2; // rax

  v2 = -1;
  do
    ++v2;
  while ( lpString[v2] );
  if ( v2 >= 0x104 )
    return 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowPUAStringsInFileHistory>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_AllowPUAStringsInFileHistory>::GetImpl'::`2'::impl,
                          a2) )
    return 1;
  return IsNLSDefinedString(1u, 0, 0, lpString, -1);
}

```

## disassembly

```asm
0x18002acd4  mov     [rsp+arg_0], rbx
0x18002acd9  push    rdi
0x18002acda  sub     rsp, 30h
0x18002acde  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ace2  mov     rbx, rcx
0x18002ace5  xor     edi, edi
0x18002ace7  inc     rax
0x18002acea  cmp     [rcx+rax*2], di
0x18002acee  jnz     short loc_18002ACE7
0x18002acf0  cmp     rax, 104h
0x18002acf6  jnb     short loc_18002AD33
0x18002acf8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AllowPUAStringsInFileHistory@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AllowPUAStringsInFileHistory@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowPUAStringsInFileHistory> `wil::Feature<__WilFeatureTraits_Feature_AllowPUAStringsInFileHistory>::GetImpl(void)'::`2'::impl
0x18002acff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowPUAStringsInFileHistory@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowPUAStringsInFileHistory>::__private_IsEnabled(void)
0x18002ad04  test    al, al
0x18002ad06  jnz     short loc_18002AD2C
0x18002ad08  xor     edx, edx; dwFlags
0x18002ad0a  mov     [rsp+38h+cchStr], 0FFFFFFFFh; cchStr
0x18002ad12  mov     r9, rbx; lpString
0x18002ad15  xor     r8d, r8d; lpVersionInformation
0x18002ad18  lea     ecx, [rdx+1]; Function
0x18002ad1b  call    cs:__imp_IsNLSDefinedString
0x18002ad21  test    eax, eax
0x18002ad23  mov     ecx, edi
0x18002ad25  setnz   cl
0x18002ad28  mov     eax, ecx
0x18002ad2a  jmp     short loc_18002AD35
0x18002ad2c  mov     eax, 1
0x18002ad31  jmp     short loc_18002AD35
0x18002ad33  xor     eax, eax
0x18002ad35  mov     rbx, [rsp+38h+arg_0]
0x18002ad3a  add     rsp, 30h
0x18002ad3e  pop     rdi
0x18002ad3f  retn
```
