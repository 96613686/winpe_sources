# WorkbookNameUpdate(x,x,x,x,x,x)

- ea: `0x1001d870`
- end: `0x1001d97a`
- name: `_WorkbookNameUpdate@24`
- size: `266`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10029730`
- `0x10029b60`

## callees

- `0x10016240`
- `0x1001c2b0`
- `0x1001d870`
- `0x1001d980`
- `0x1001fe30`
- `0x10035510`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1001d8e1`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1001d8e1`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1001d8e8`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1001d8e8`

## pseudocode

```c
int __fastcall WorkbookNameUpdate(int a1, wchar_t *a2, int a3, int a4, int a5, int a6)
{
  int v6; // esi
  int *v7; // ebx
  int v8; // ecx
  int i; // edi
  _DWORD *v10; // esi
  LCID UserDefaultLCID; // eax
  int updated; // eax
  __int16 v13; // ax
  __int16 v14; // dx
  int v16; // [esp-8h] [ebp-268h]
  int v17; // [esp-4h] [ebp-264h]
  wchar_t v19[256]; // [esp+18h] [ebp-248h] BYREF
  wchar_t v20[34]; // [esp+218h] [ebp-48h] BYREF

  v6 = a1;
  v7 = *(int **)(a1 + 804);
  WorkbookNameParse(a2, v20, v19, v16, v17);
  if ( v20[0] )
  {
    v10 = (_DWORD *)v7[20];
    for ( i = 1; v10; ++i )
    {
      UserDefaultLCID = GetUserDefaultLCID();
      if ( DBCompareStringW(UserDefaultLCID, 196609, (char *)v10 + 14, -1, v20, -1) == 2 )
        break;
      v10 = (_DWORD *)*v10;
    }
    v6 = a1;
  }
  else
  {
    i = 0;
  }
  if ( v7[3] )
  {
    updated = XLOLENameUpdate(*(_DWORD *)(v6 + 796) + 14, a5, a6, v8);
  }
  else
  {
    v13 = 0;
    v14 = -1;
    if ( a4 == 1 )
    {
      v14 = 0x7FFF;
    }
    else if ( a4 == 2 )
    {
      v13 = 0x8000;
    }
    updated = ExcelUpdateName(v7[2], i, v19, v14, v13, a5, a6);
  }
  return TranslateEXErrorToJETError(updated);
}

```

## disassembly

```asm
0x1001d870  mov     edi, edi
0x1001d872  push    ebp
0x1001d873  mov     ebp, esp
0x1001d875  sub     esp, 254h
0x1001d87b  mov     eax, ___security_cookie
0x1001d880  xor     eax, ebp
0x1001d882  mov     [ebp+var_4], eax
0x1001d885  push    ebx
0x1001d886  push    esi
0x1001d887  push    edi
0x1001d888  mov     esi, ecx
0x1001d88a  sub     esp, 8
0x1001d88d  mov     eax, edx
0x1001d88f  mov     [ebp+var_24C], esi
0x1001d895  lea     ecx, [ebp+var_248]
0x1001d89b  mov     [ebp+var_250], eax
0x1001d8a1  lea     edx, [ebp+var_48]
0x1001d8a4  mov     ebx, [esi+324h]
0x1001d8aa  push    ecx
0x1001d8ab  mov     ecx, eax
0x1001d8ad  call    _WorkbookNameParse@20; WorkbookNameParse(x,x,x,x,x)
0x1001d8b2  cmp     [ebp+var_48], 0
0x1001d8b7  jnz     short loc_1001D8BD
0x1001d8b9  xor     edi, edi
0x1001d8bb  jmp     short loc_1001D900
0x1001d8bd  mov     esi, [ebx+50h]
0x1001d8c0  mov     edi, 1
0x1001d8c5  test    esi, esi
0x1001d8c7  jz      short loc_1001D8FA
0x1001d8c9  nop     dword ptr [eax+00000000h]
0x1001d8d0  push    0FFFFFFFFh
0x1001d8d2  lea     eax, [ebp+var_48]
0x1001d8d5  push    eax
0x1001d8d6  push    0FFFFFFFFh
0x1001d8d8  lea     eax, [esi+0Eh]
0x1001d8db  push    eax
0x1001d8dc  push    30001h
0x1001d8e1  call    ds:__imp__GetUserDefaultLCID@0; GetUserDefaultLCID()
0x1001d8e7  push    eax
0x1001d8e8  call    ds:__imp__DBCompareStringW@24; DBCompareStringW(x,x,x,x,x,x)
0x1001d8ee  sub     eax, 2
0x1001d8f1  jz      short loc_1001D8FA
0x1001d8f3  mov     esi, [esi]
0x1001d8f5  inc     edi
0x1001d8f6  test    esi, esi
0x1001d8f8  jnz     short loc_1001D8D0
0x1001d8fa  mov     esi, [ebp+var_24C]
0x1001d900  cmp     dword ptr [ebx+0Ch], 0
0x1001d904  jz      short loc_1001D926
0x1001d906  mov     eax, [esi+31Ch]
0x1001d90c  mov     edx, [ebp+var_250]
0x1001d912  add     eax, 0Eh
0x1001d915  push    ecx
0x1001d916  push    [ebp+arg_C]
0x1001d919  mov     ecx, ebx
0x1001d91b  push    [ebp+arg_8]
0x1001d91e  push    eax
0x1001d91f  call    _XLOLENameUpdate@24; XLOLENameUpdate(x,x,x,x,x,x)
0x1001d924  jmp     short loc_1001D960
0x1001d926  mov     ecx, [ebp+arg_4]
0x1001d929  xor     eax, eax
0x1001d92b  mov     edx, 0FFFFh
0x1001d930  cmp     ecx, 1
0x1001d933  jnz     short loc_1001D93C
0x1001d935  mov     edx, 7FFFh
0x1001d93a  jmp     short loc_1001D947
0x1001d93c  cmp     ecx, 2
0x1001d93f  mov     esi, 8000h
0x1001d944  cmovz   eax, esi
0x1001d947  push    [ebp+arg_C]
0x1001d94a  mov     ecx, [ebx+8]
0x1001d94d  push    [ebp+arg_8]
0x1001d950  push    eax
0x1001d951  push    edx
0x1001d952  lea     eax, [ebp+var_248]
0x1001d958  mov     edx, edi
0x1001d95a  push    eax
0x1001d95b  call    _ExcelUpdateName@28; ExcelUpdateName(x,x,x,x,x,x,x)
0x1001d960  mov     ecx, eax
0x1001d962  call    _TranslateEXErrorToJETError@4; TranslateEXErrorToJETError(x)
0x1001d967  mov     ecx, [ebp+var_4]
0x1001d96a  pop     edi
0x1001d96b  pop     esi
0x1001d96c  xor     ecx, ebp; StackCookie
0x1001d96e  pop     ebx
0x1001d96f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001d974  mov     esp, ebp
0x1001d976  pop     ebp
0x1001d977  retn    10h
```
