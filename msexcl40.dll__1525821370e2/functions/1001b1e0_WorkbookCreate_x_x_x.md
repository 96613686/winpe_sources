# WorkbookCreate(x,x,x)

- ea: `0x1001b1e0`
- end: `0x1001b2e9`
- name: `_WorkbookCreate@12`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x10026c60`

## callees

- `0x100158d0`
- `0x1001b1e0`
- `0x1001c2b0`
- `0x1002580a`
- `0x10025ab7`
- `0x10032cb3`
- `0x10035510`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1001b268`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1001b268`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x1001b246`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x1001b246`

## pseudocode

```c
int __fastcall WorkbookCreate(const WCHAR *a1, int a2, int *a3)
{
  unsigned int v3; // edi
  int v4; // esi
  int result; // eax
  UINT ACP; // eax
  __int16 v7; // ax
  int v8; // eax
  int v9; // [esp+Ch] [ebp-18h] BYREF
  LPCWSTR lpFileName; // [esp+10h] [ebp-14h]
  WCHAR LCData[6]; // [esp+14h] [ebp-10h] BYREF

  lpFileName = a1;
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      v3 = 4;
    }
    else
    {
      v3 = 8;
      if ( a2 == 2 )
        v3 = 5;
    }
  }
  else
  {
    v3 = 3;
  }
  v4 = MemAllocate(92);
  if ( !v4 )
    return -1011;
  ACP = GetACP();
  *(_DWORD *)(v4 + 36) = ACP;
  *(_DWORD *)(v4 + 32) = ACP;
  JetGetLocaleInfoW(0x400u, 5u, LCData, 6);
  v7 = __o__wtoi(LCData);
  *(_WORD *)(v4 + 44) = v7;
  lpFileName = (LPCWSTR)ExcelCreateFile(lpFileName, v3, v3 < 5 ? 0 : 2048, *(_DWORD *)(v4 + 36), v7, &v9);
  if ( lpFileName )
  {
    MemFree((_DWORD *)v4);
    return TranslateEXErrorToJETError((void *)lpFileName);
  }
  else
  {
    v8 = v9;
    *(_DWORD *)(v4 + 4) = v3;
    *(_DWORD *)(v4 + 8) = v8;
    result = 0;
    *(_DWORD *)v4 = 0;
    *a3 = v4;
  }
  return result;
}

```

## disassembly

```asm
0x1001b1e0  mov     edi, edi
0x1001b1e2  push    ebp
0x1001b1e3  mov     ebp, esp
0x1001b1e5  sub     esp, 18h
0x1001b1e8  mov     eax, ___security_cookie
0x1001b1ed  xor     eax, ebp
0x1001b1ef  mov     [ebp+var_4], eax
0x1001b1f2  mov     [ebp+lpFileName], ecx
0x1001b1f5  push    ebx
0x1001b1f6  mov     ebx, [ebp+arg_0]
0x1001b1f9  push    esi
0x1001b1fa  push    edi
0x1001b1fb  test    edx, edx
0x1001b1fd  jnz     short loc_1001B204
0x1001b1ff  lea     edi, [edx+3]
0x1001b202  jmp     short loc_1001B21E
0x1001b204  cmp     edx, 1
0x1001b207  jnz     short loc_1001B20E
0x1001b209  lea     edi, [edx+3]
0x1001b20c  jmp     short loc_1001B21E
0x1001b20e  cmp     edx, 2
0x1001b211  mov     edi, 8
0x1001b216  mov     eax, 5
0x1001b21b  cmovz   edi, eax
0x1001b21e  mov     ecx, 5Ch ; '\'
0x1001b223  call    _MemAllocate@4; MemAllocate(x)
0x1001b228  mov     esi, eax
0x1001b22a  test    esi, esi
0x1001b22c  jnz     short loc_1001B246
0x1001b22e  mov     eax, 0FFFFFC0Dh
0x1001b233  pop     edi
0x1001b234  pop     esi
0x1001b235  pop     ebx
0x1001b236  mov     ecx, [ebp+var_4]
0x1001b239  xor     ecx, ebp; StackCookie
0x1001b23b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001b240  mov     esp, ebp
0x1001b242  pop     ebp
0x1001b243  retn    4
0x1001b246  call    ds:__imp__GetACP@0; GetACP()
0x1001b24c  push    6; cchData
0x1001b24e  mov     [esi+24h], eax
0x1001b251  mov     [esi+20h], eax
0x1001b254  lea     eax, [ebp+LCData]
0x1001b257  push    eax; lpLCData
0x1001b258  push    5; LCType
0x1001b25a  push    400h; Locale
0x1001b25f  call    _JetGetLocaleInfoW@16; JetGetLocaleInfoW(x,x,x,x)
0x1001b264  lea     eax, [ebp+LCData]
0x1001b267  push    eax
0x1001b268  call    ds:__imp___o__wtoi
0x1001b26e  add     esp, 4
0x1001b271  movzx   eax, ax
0x1001b274  lea     ecx, [ebp+var_18]
0x1001b277  mov     [esi+2Ch], ax
0x1001b27b  cmp     edi, 5
0x1001b27e  mov     edx, edi
0x1001b280  push    ecx; int
0x1001b281  mov     ecx, [ebp+lpFileName]; lpFileName
0x1001b284  push    eax; __int16
0x1001b285  push    dword ptr [esi+24h]; int
0x1001b288  sbb     eax, eax
0x1001b28a  and     eax, 0FFFFF800h
0x1001b28f  add     eax, 800h
0x1001b294  push    eax; int
0x1001b295  call    _ExcelCreateFile@24; ExcelCreateFile(x,x,x,x,x,x)
0x1001b29a  mov     [ebp+lpFileName], eax
0x1001b29d  test    eax, eax
0x1001b29f  jz      short loc_1001B2C3
0x1001b2a1  mov     ecx, esi
0x1001b2a3  call    _MemFree@4; MemFree(x)
0x1001b2a8  mov     ecx, [ebp+lpFileName]
0x1001b2ab  call    _TranslateEXErrorToJETError@4; TranslateEXErrorToJETError(x)
0x1001b2b0  pop     edi
0x1001b2b1  pop     esi
0x1001b2b2  pop     ebx
0x1001b2b3  mov     ecx, [ebp+var_4]
0x1001b2b6  xor     ecx, ebp; StackCookie
0x1001b2b8  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001b2bd  mov     esp, ebp
0x1001b2bf  pop     ebp
0x1001b2c0  retn    4
0x1001b2c3  mov     eax, [ebp+var_18]
0x1001b2c6  mov     ecx, [ebp+var_4]
0x1001b2c9  mov     [esi+4], edi
0x1001b2cc  xor     ecx, ebp; StackCookie
0x1001b2ce  mov     [esi+8], eax
0x1001b2d1  xor     eax, eax
0x1001b2d3  mov     dword ptr [esi], 0
0x1001b2d9  pop     edi
0x1001b2da  mov     [ebx], esi
0x1001b2dc  pop     esi
0x1001b2dd  pop     ebx
0x1001b2de  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001b2e3  mov     esp, ebp
0x1001b2e5  pop     ebp
0x1001b2e6  retn    4
```
