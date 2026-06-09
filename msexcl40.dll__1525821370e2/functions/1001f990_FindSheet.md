# FindSheet

- ea: `0x1001f990`
- end: `0x1001fa15`
- name: `FindSheet`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1001fa20`

## callees

- `0x1001dad0`
- `0x1001f990`
- `0x10035510`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1001f9e6`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1001f9e6`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1001f9ed`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1001f9ed`

## pseudocode

```c
__int16 *__fastcall FindSheet(int a1, int a2, _DWORD *a3)
{
  __int16 *v3; // esi
  LCID UserDefaultLCID; // eax
  __int16 v7[256]; // [esp+Ch] [ebp-204h] BYREF

  v3 = *(__int16 **)(a1 + 80);
  for ( *a3 = 0; v3; ++*a3 )
  {
    ExcelSheetnameImage(v3 + 7, v7, 255, 0);
    UserDefaultLCID = GetUserDefaultLCID();
    if ( DBCompareStringW(UserDefaultLCID, 196609, v7, -1, a2, -1) == 2 )
      break;
    v3 = *(__int16 **)v3;
  }
  return v3;
}

```

## disassembly

```asm
0x1001f990  mov     edi, edi
0x1001f992  push    ebp
0x1001f993  mov     ebp, esp
0x1001f995  sub     esp, 204h
0x1001f99b  mov     eax, ___security_cookie
0x1001f9a0  xor     eax, ebp
0x1001f9a2  mov     [ebp+var_4], eax
0x1001f9a5  push    ebx
0x1001f9a6  push    esi
0x1001f9a7  mov     esi, [ecx+50h]
0x1001f9aa  mov     ebx, edx
0x1001f9ac  push    edi
0x1001f9ad  mov     edi, [ebp+arg_0]
0x1001f9b0  mov     dword ptr [edi], 0
0x1001f9b6  test    esi, esi
0x1001f9b8  jz      short loc_1001FA00
0x1001f9ba  nop     word ptr [eax+eax+00h]
0x1001f9c0  push    0
0x1001f9c2  push    0FFh
0x1001f9c7  lea     ecx, [esi+0Eh]
0x1001f9ca  lea     edx, [ebp+var_204]
0x1001f9d0  call    _ExcelSheetnameImage@16; ExcelSheetnameImage(x,x,x,x)
0x1001f9d5  push    0FFFFFFFFh
0x1001f9d7  push    ebx
0x1001f9d8  push    0FFFFFFFFh
0x1001f9da  lea     eax, [ebp+var_204]
0x1001f9e0  push    eax
0x1001f9e1  push    30001h
0x1001f9e6  call    ds:__imp__GetUserDefaultLCID@0; GetUserDefaultLCID()
0x1001f9ec  push    eax
0x1001f9ed  call    ds:__imp__DBCompareStringW@24; DBCompareStringW(x,x,x,x,x,x)
0x1001f9f3  sub     eax, 2
0x1001f9f6  jz      short loc_1001FA00
0x1001f9f8  mov     esi, [esi]
0x1001f9fa  inc     dword ptr [edi]
0x1001f9fc  test    esi, esi
0x1001f9fe  jnz     short loc_1001F9C0
0x1001fa00  mov     ecx, [ebp+var_4]
0x1001fa03  mov     eax, esi
0x1001fa05  pop     edi
0x1001fa06  pop     esi
0x1001fa07  xor     ecx, ebp; StackCookie
0x1001fa09  pop     ebx
0x1001fa0a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001fa0f  mov     esp, ebp
0x1001fa11  pop     ebp
0x1001fa12  retn    4
```
