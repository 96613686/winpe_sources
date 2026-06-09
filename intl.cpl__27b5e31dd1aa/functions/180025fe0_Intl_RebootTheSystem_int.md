# Intl_RebootTheSystem(int)

- ea: `0x180025fe0`
- end: `0x180026032`
- name: `?Intl_RebootTheSystem@@YAXH@Z`
- size: `82`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180025eb8`
- `0x180025f40`

## callees

- `0x180025fe0`
- `0x180026874`

## import_xrefs

- `USER32!ExitWindowsEx` at `0x180026011`
- `USER32!ExitWindowsEx` at `0x180026011`

## string_xrefs

- `0x180025fed`: `SeShutdownPrivilege`
- `0x180026020`: `SeShutdownPrivilege`

## pseudocode

```c
void __fastcall Intl_RebootTheSystem(int a1)
{
  UINT v2; // ecx
  unsigned __int8 v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  if ( (int)Intl_SetPrivilegeAccessToken(L"SeShutdownPrivilege", 1, (bool *)&v3) >= 0 )
  {
    if ( a1 )
      v2 = 2;
    else
      v2 = 0;
    ExitWindowsEx(v2, 0);
    Intl_SetPrivilegeAccessToken(L"SeShutdownPrivilege", v3, (bool *)&v3);
  }
}

```

## disassembly

```asm
0x180025fe0  push    rbx
0x180025fe2  sub     rsp, 20h
0x180025fe6  mov     ebx, ecx
0x180025fe8  mov     [rsp+28h+arg_8], 0
0x180025fed  lea     rcx, aSeshutdownpriv; "SeShutdownPrivilege"
0x180025ff4  mov     dl, 1; unsigned __int8
0x180025ff6  lea     r8, [rsp+28h+arg_8]; unsigned __int8 *
0x180025ffb  call    ?Intl_SetPrivilegeAccessToken@@YAKPEBGEPEAE@Z; Intl_SetPrivilegeAccessToken(ushort const *,uchar,uchar *)
0x180026000  test    eax, eax
0x180026002  js      short loc_18002602C
0x180026004  xor     edx, edx; dwReason
0x180026006  test    ebx, ebx
0x180026008  jz      short loc_18002600F
0x18002600a  lea     ecx, [rdx+2]
0x18002600d  jmp     short loc_180026011
0x18002600f  xor     ecx, ecx; uFlags
0x180026011  call    cs:__imp_ExitWindowsEx
0x180026017  mov     dl, [rsp+28h+arg_8]; unsigned __int8
0x18002601b  lea     r8, [rsp+28h+arg_8]; unsigned __int8 *
0x180026020  lea     rcx, aSeshutdownpriv; "SeShutdownPrivilege"
0x180026027  call    ?Intl_SetPrivilegeAccessToken@@YAKPEBGEPEAE@Z; Intl_SetPrivilegeAccessToken(ushort const *,uchar,uchar *)
0x18002602c  add     rsp, 20h
0x180026030  pop     rbx
0x180026031  retn
```
