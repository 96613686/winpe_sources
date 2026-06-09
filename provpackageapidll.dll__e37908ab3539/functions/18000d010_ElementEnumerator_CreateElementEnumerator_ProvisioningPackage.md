# ElementEnumerator::CreateElementEnumerator(ProvisioningPackage *)

- ea: `0x18000d010`
- end: `0x18000d0bb`
- name: `?CreateElementEnumerator@ElementEnumerator@@QEAAJPEAVProvisioningPackage@@@Z`
- size: `171`
- prototype: `__int64 __fastcall(ElementEnumerator *__hidden this, struct ProvisioningPackage *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180006dd0`

## callees

- `0x180006014`
- `0x18000d010`
- `0x18000d708`

## string_xrefs

- `0x18000d02b`: `ElementEnumerator::CreateElementEnumerator`
- `0x18000d08a`: `ElementEnumerator::CreateElementEnumerator`

## pseudocode

```c
__int64 __fastcall ElementEnumerator::CreateElementEnumerator(ElementEnumerator *this, struct ProvisioningPackage *a2)
{
  unsigned int NextElementType; // ebx
  int v4; // [rsp+20h] [rbp-18h]
  int v5; // [rsp+20h] [rbp-18h]
  int v6; // [rsp+28h] [rbp-10h]
  unsigned int v7; // [rsp+28h] [rbp-10h]

  if ( !a2 )
  {
    NextElementType = -2147024809;
    v6 = -2147024809;
    v4 = 19;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ElementEnumerator::CreateElementEnumerator",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
      v4,
      v6);
    ProvPackageLog(3, L"    pkg: Argument cannot be NULL");
    return NextElementType;
  }
  *((_QWORD *)this + 1) = a2;
  NextElementType = ElementEnumerator::GetNextElementType(this);
  if ( (int)(NextElementType + 0x80000000) >= 0 && NextElementType != -2147024637 )
  {
    v7 = NextElementType;
    v5 = 31;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ElementEnumerator::CreateElementEnumerator",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\elementenumerator.cpp",
      v5,
      v7);
    ProvPackageLog(3, L"    Failed to get next element type");
    return NextElementType;
  }
  return 0;
}

```

## disassembly

```asm
0x18000d010  push    rbx
0x18000d012  sub     rsp, 30h
0x18000d016  test    rdx, rdx
0x18000d019  jnz     short loc_18000D060
0x18000d01b  mov     ebx, 80070057h
0x18000d020  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d027  mov     [rsp+38h+var_10], ebx
0x18000d02b  lea     r8, aElementenumera_1; "ElementEnumerator::CreateElementEnumera"...
0x18000d032  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d039  mov     [rsp+38h+var_18], 13h
0x18000d041  mov     ecx, 3
0x18000d046  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d04b  lea     rdx, aPkgArgumentCan; "    pkg: Argument cannot be NULL"
0x18000d052  mov     ecx, 3
0x18000d057  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d05c  mov     eax, ebx
0x18000d05e  jmp     short loc_18000D0B5
0x18000d060  mov     [rcx+8], rdx
0x18000d064  call    ?GetNextElementType@ElementEnumerator@@AEAAJXZ; ElementEnumerator::GetNextElementType(void)
0x18000d069  mov     ebx, eax
0x18000d06b  mov     eax, 80000000h
0x18000d070  lea     ecx, [rbx+rax]
0x18000d073  test    eax, ecx
0x18000d075  jnz     short loc_18000D0B3
0x18000d077  cmp     ebx, 80070103h
0x18000d07d  jz      short loc_18000D0B3
0x18000d07f  mov     [rsp+38h+var_10], ebx
0x18000d083  lea     r9, aOnecoreBaseNts; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000d08a  lea     r8, aElementenumera_1; "ElementEnumerator::CreateElementEnumera"...
0x18000d091  mov     [rsp+38h+var_18], 1Fh
0x18000d099  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000d0a0  mov     ecx, 3
0x18000d0a5  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000d0aa  lea     rdx, aFailedToGetNex_4; "    Failed to get next element type"
0x18000d0b1  jmp     short loc_18000D052
0x18000d0b3  xor     eax, eax
0x18000d0b5  add     rsp, 30h
0x18000d0b9  pop     rbx
0x18000d0ba  retn
```
