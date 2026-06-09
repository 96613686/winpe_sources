# OmaDmDeleteSessionPolicy

- ea: `0x180016a10`
- end: `0x180016a70`
- name: `OmaDmDeleteSessionPolicy`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180015bb0`

## callees

- `0x180009bc0`
- `0x18000b26c`
- `0x180016a10`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016a5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016a5b`

## string_xrefs

- `0x180016a3b`: `policy:/REGISTRY/HKLM`

## pseudocode

```c
__int64 __fastcall OmaDmDeleteSessionPolicy(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  _QWORD *v3; // rax
  int v4; // eax
  HLOCAL hMem; // [rsp+30h] [rbp+8h] BYREF

  hMem = 0;
  if ( a1 )
  {
    v3 = (_QWORD *)ipx::replace<ipx::detail::_HandleTraits<unsigned short *,void * (*)(void *),&void * LocalFree(void *),0>>(&hMem);
    v4 = BuildCanonicalFileOrRegPolicyName((__int64)L"policy:/REGISTRY/HKLM", a1, v3);
    v2 = 0;
    if ( v4 < 0 )
      v2 = v4;
    if ( hMem )
      LocalFree(hMem);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v2;
}

```

## disassembly

```asm
0x180016a10  push    rbx
0x180016a12  sub     rsp, 20h
0x180016a16  mov     [rsp+28h+hMem], 0
0x180016a1f  mov     rbx, rcx
0x180016a22  test    rcx, rcx
0x180016a25  jnz     short loc_180016A2E
0x180016a27  mov     ebx, 80070057h
0x180016a2c  jmp     short loc_180016A67
0x180016a2e  lea     rcx, [rsp+28h+hMem]
0x180016a33  call    ??$replace@U?$_HandleTraits@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAGAEAV?$unique_any@U?$_HandleTraits@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<ushort *,void * (*)(void *),&LocalFree(void *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<ushort *,void * (*)(void *),&LocalFree(void *),0>> &)
0x180016a38  mov     r8, rax
0x180016a3b  lea     rcx, aPolicyRegistry_0; "policy:/REGISTRY/HKLM"
0x180016a42  mov     rdx, rbx
0x180016a45  call    BuildCanonicalFileOrRegPolicyName
0x180016a4a  mov     rcx, [rsp+28h+hMem]; hMem
0x180016a4f  xor     ebx, ebx
0x180016a51  test    eax, eax
0x180016a53  cmovs   ebx, eax
0x180016a56  test    rcx, rcx
0x180016a59  jz      short loc_180016A67
0x180016a5b  call    cs:__imp_LocalFree
0x180016a62  nop     dword ptr [rax+rax+00h]
0x180016a67  mov     eax, ebx
0x180016a69  add     rsp, 20h
0x180016a6d  pop     rbx
0x180016a6e  retn
```
