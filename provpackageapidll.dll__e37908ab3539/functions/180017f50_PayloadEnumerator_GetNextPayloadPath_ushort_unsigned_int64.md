# PayloadEnumerator::GetNextPayloadPath(ushort *,unsigned __int64)

- ea: `0x180017f50`
- end: `0x18001806b`
- name: `?GetNextPayloadPath@PayloadEnumerator@@EEAAJPEAG_K@Z`
- size: `283`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callees

- `0x1800020a8`
- `0x180005424`
- `0x180006014`
- `0x180017898`
- `0x180017f50`

## string_xrefs

- `0x180017fa2`: `PayloadEnumerator::GetNextPayloadPath`
- `0x180017fda`: `PayloadEnumerator::GetNextPayloadPath`
- `0x18001802e`: `PayloadEnumerator::GetNextPayloadPath`
- `0x180018041`: `    Failed to copy payload path`

## pseudocode

```c
__int64 __fastcall PayloadEnumerator::GetNextPayloadPath(
        const unsigned __int16 **this,
        unsigned __int16 *a2,
        unsigned __int64 a3)
{
  int NextPayload; // eax
  unsigned int v7; // edi
  int v9; // eax
  const struct std::nothrow_t *v10; // rdx
  unsigned __int16 *v11; // rcx

  if ( a3 )
    *a2 = 0;
  if ( !this[6] )
  {
    NextPayload = PayloadEnumerator::GetNextPayload((PayloadEnumerator *)this);
    v7 = NextPayload;
    if ( NextPayload == -2147024637 )
    {
      ProvPackageLog(
        0,
        L"%hs (%hs:%d): %s",
        "PayloadEnumerator::GetNextPayloadPath",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
        165,
        L"No more payloads to enumerate");
      return 2147942659LL;
    }
    if ( NextPayload < 0 )
    {
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "PayloadEnumerator::GetNextPayloadPath",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
        168,
        NextPayload);
      ProvPackageLog(3, L"    Failed to get next payload");
      return v7;
    }
  }
  v9 = StringCchCopyW(a2, a3, this[6]);
  v7 = v9;
  if ( v9 < 0 )
  {
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "PayloadEnumerator::GetNextPayloadPath",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\payloadenumerator.cpp",
      172,
      v9);
    ProvPackageLog(3, L"    Failed to copy payload path");
    return v7;
  }
  v11 = (unsigned __int16 *)this[6];
  this[6] = 0;
  if ( v11 )
    operator delete(v11, v10);
  return 0;
}

```

## disassembly

```asm
0x180017f50  push    rbx
0x180017f52  push    rbp
0x180017f53  push    rsi
0x180017f54  push    rdi
0x180017f55  sub     rsp, 38h
0x180017f59  mov     rbp, r8
0x180017f5c  mov     rsi, rdx
0x180017f5f  mov     rbx, rcx
0x180017f62  test    r8, r8
0x180017f65  jz      short loc_180017F6C
0x180017f67  xor     eax, eax
0x180017f69  mov     [rdx], ax
0x180017f6c  cmp     qword ptr [rcx+30h], 0
0x180017f71  jnz     loc_180017FFF
0x180017f77  call    ?GetNextPayload@PayloadEnumerator@@AEAAJXZ; PayloadEnumerator::GetNextPayload(void)
0x180017f7c  mov     edi, eax
0x180017f7e  cmp     eax, 80070103h
0x180017f83  jnz     short loc_180017FBC
0x180017f85  lea     rcx, aNoMorePayloads; "No more payloads to enumerate"
0x180017f8c  mov     [rsp+58h+var_30], rcx
0x180017f91  lea     r9, aOnecoreBaseNts_4; "onecore\\base\\ntsetup\\provpackageapi"...
0x180017f98  xor     ecx, ecx
0x180017f9a  mov     [rsp+58h+var_38], 0A5h
0x180017fa2  lea     r8, aPayloadenumera_0; "PayloadEnumerator::GetNextPayloadPath"
0x180017fa9  lea     rdx, aHsHsDS; "%hs (%hs:%d): %s"
0x180017fb0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180017fb5  mov     eax, edi
0x180017fb7  jmp     loc_180018062
0x180017fbc  test    edi, edi
0x180017fbe  jns     short loc_180017FFF
0x180017fc0  mov     ebx, 3
0x180017fc5  mov     dword ptr [rsp+58h+var_30], edi
0x180017fc9  mov     ecx, ebx
0x180017fcb  mov     [rsp+58h+var_38], 0A8h
0x180017fd3  lea     r9, aOnecoreBaseNts_4; "onecore\\base\\ntsetup\\provpackageapi"...
0x180017fda  lea     r8, aPayloadenumera_0; "PayloadEnumerator::GetNextPayloadPath"
0x180017fe1  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x180017fe8  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180017fed  lea     rdx, aFailedToGetNex_2; "    Failed to get next payload"
0x180017ff4  mov     ecx, ebx
0x180017ff6  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180017ffb  mov     eax, edi
0x180017ffd  jmp     short loc_180018062
0x180017fff  mov     r8, [rbx+30h]; unsigned __int16 *
0x180018003  mov     rdx, rbp; unsigned __int64
0x180018006  mov     rcx, rsi; unsigned __int16 *
0x180018009  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001800e  mov     edi, eax
0x180018010  test    eax, eax
0x180018012  jns     short loc_18001804A
0x180018014  mov     dword ptr [rsp+58h+var_30], eax
0x180018018  lea     r9, aOnecoreBaseNts_4; "onecore\\base\\ntsetup\\provpackageapi"...
0x18001801f  mov     ebx, 3
0x180018024  mov     [rsp+58h+var_38], 0ACh
0x18001802c  mov     ecx, ebx
0x18001802e  lea     r8, aPayloadenumera_0; "PayloadEnumerator::GetNextPayloadPath"
0x180018035  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18001803c  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180018041  lea     rdx, aFailedToCopyPa_3; "    Failed to copy payload path"
0x180018048  jmp     short loc_180017FF4
0x18001804a  mov     rcx, [rbx+30h]; void *
0x18001804e  mov     qword ptr [rbx+30h], 0
0x180018056  test    rcx, rcx
0x180018059  jz      short loc_180018060
0x18001805b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180018060  xor     eax, eax
0x180018062  add     rsp, 38h
0x180018066  pop     rdi
0x180018067  pop     rsi
0x180018068  pop     rbp
0x180018069  pop     rbx
0x18001806a  retn
```
