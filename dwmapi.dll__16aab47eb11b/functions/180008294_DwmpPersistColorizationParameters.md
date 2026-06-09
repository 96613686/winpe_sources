# DwmpPersistColorizationParameters

- ea: `0x180008294`
- end: `0x18000844f`
- name: `DwmpPersistColorizationParameters`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800080e0`

## callees

- `0x180003370`
- `0x180008294`
- `0x180008458`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800083ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800083ce`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800082f0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800082f0`

## pseudocode

```c
__int64 __fastcall DwmpPersistColorizationParameters(unsigned int *a1)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  unsigned int v4; // edx
  int v5; // ecx
  int v7; // eax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    v4 = 123;
    goto LABEL_6;
  }
  v2 = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\DWM", 0, 0, 0, 2u, 0, &hKey, 0);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 < 0 )
  {
    v4 = 135;
LABEL_6:
    v5 = v3;
LABEL_7:
    DoStackCaptureDirect(v5, v4);
    goto LABEL_8;
  }
  v7 = DwmpSaveColorizationParameter(hKey, L"ColorizationColor", *a1);
  v3 = v7;
  if ( v7 < 0 )
  {
    v4 = 137;
    goto LABEL_17;
  }
  v7 = DwmpSaveColorizationParameter(hKey, L"ColorizationColorBalance", a1[2]);
  v3 = v7;
  if ( v7 < 0 )
  {
    v4 = 138;
    goto LABEL_17;
  }
  v7 = DwmpSaveColorizationParameter(hKey, L"ColorizationAfterglow", a1[1]);
  v3 = v7;
  if ( v7 < 0 )
  {
    v4 = 139;
    goto LABEL_17;
  }
  v7 = DwmpSaveColorizationParameter(hKey, L"ColorizationAfterglowBalance", a1[3]);
  v3 = v7;
  if ( v7 < 0 )
  {
    v4 = 140;
    goto LABEL_17;
  }
  v7 = DwmpSaveColorizationParameter(hKey, L"ColorizationBlurBalance", a1[4]);
  v3 = v7;
  if ( v7 < 0 )
  {
    v4 = 141;
LABEL_17:
    v5 = v7;
    goto LABEL_7;
  }
  v7 = DwmpSaveColorizationParameter(hKey, L"EnableWindowColorization", a1[5]);
  v3 = v7;
  if ( v7 < 0 )
  {
    v4 = 142;
    goto LABEL_17;
  }
  v7 = DwmpSaveColorizationParameter(hKey, L"ColorizationGlassAttribute", a1[6]);
  v3 = v7;
  if ( v7 < 0 )
  {
    v4 = 143;
    goto LABEL_17;
  }
LABEL_8:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180008294  mov     r11, rsp
0x180008297  mov     [r11+10h], rbx
0x18000829b  push    rdi
0x18000829c  sub     rsp, 50h
0x1800082a0  mov     qword ptr [r11+8], 0
0x1800082a8  mov     rdi, rcx
0x1800082ab  test    rcx, rcx
0x1800082ae  jz      loc_1800083E7
0x1800082b4  mov     qword ptr [r11-18h], 0
0x1800082bc  lea     rax, [r11+8]
0x1800082c0  mov     [r11-20h], rax
0x1800082c4  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\DWM"
0x1800082cb  mov     qword ptr [r11-28h], 0
0x1800082d3  xor     r9d, r9d; lpClass
0x1800082d6  mov     [rsp+58h+samDesired], 2; samDesired
0x1800082de  xor     r8d, r8d; Reserved
0x1800082e1  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800082e8  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800082f0  call    cs:__imp_RegCreateKeyExW
0x1800082f6  mov     ebx, eax
0x1800082f8  test    eax, eax
0x1800082fa  jle     short loc_180008305
0x1800082fc  movzx   ebx, ax
0x1800082ff  or      ebx, 80070000h
0x180008305  test    ebx, ebx
0x180008307  jns     short loc_180008330
0x180008309  mov     edx, 87h; unsigned int
0x18000830e  mov     ecx, ebx; int
0x180008310  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180008315  mov     rcx, [rsp+58h+hKey]; hKey
0x18000831a  test    rcx, rcx
0x18000831d  jnz     loc_1800083CE
0x180008323  mov     eax, ebx
0x180008325  mov     rbx, [rsp+58h+arg_8]
0x18000832a  add     rsp, 50h
0x18000832e  pop     rdi
0x18000832f  retn
0x180008330  mov     r8d, [rdi]
0x180008333  lea     rdx, ValueName; "ColorizationColor"
0x18000833a  mov     rcx, [rsp+58h+hKey]
0x18000833f  call    DwmpSaveColorizationParameter
0x180008344  mov     ebx, eax
0x180008346  test    eax, eax
0x180008348  js      loc_1800083E0
0x18000834e  mov     r8d, [rdi+8]
0x180008352  lea     rdx, aColorizationco_0; "ColorizationColorBalance"
0x180008359  mov     rcx, [rsp+58h+hKey]
0x18000835e  call    DwmpSaveColorizationParameter
0x180008363  mov     ebx, eax
0x180008365  test    eax, eax
0x180008367  js      loc_180008445
0x18000836d  mov     r8d, [rdi+4]
0x180008371  lea     rdx, aColorizationaf_0; "ColorizationAfterglow"
0x180008378  mov     rcx, [rsp+58h+hKey]
0x18000837d  call    DwmpSaveColorizationParameter
0x180008382  mov     ebx, eax
0x180008384  test    eax, eax
0x180008386  js      loc_18000843E
0x18000838c  mov     r8d, [rdi+0Ch]
0x180008390  lea     rdx, aColorizationaf; "ColorizationAfterglowBalance"
0x180008397  mov     rcx, [rsp+58h+hKey]
0x18000839c  call    DwmpSaveColorizationParameter
0x1800083a1  mov     ebx, eax
0x1800083a3  test    eax, eax
0x1800083a5  js      short loc_1800083D9
0x1800083a7  mov     r8d, [rdi+10h]
0x1800083ab  lea     rdx, aColorizationbl; "ColorizationBlurBalance"
0x1800083b2  mov     rcx, [rsp+58h+hKey]
0x1800083b7  call    DwmpSaveColorizationParameter
0x1800083bc  mov     ebx, eax
0x1800083be  test    eax, eax
0x1800083c0  jns     short loc_1800083F6
0x1800083c2  mov     edx, 8Dh
0x1800083c7  mov     ecx, eax
0x1800083c9  jmp     loc_180008310
0x1800083ce  call    cs:__imp_RegCloseKey
0x1800083d4  jmp     loc_180008323
0x1800083d9  mov     edx, 8Ch
0x1800083de  jmp     short loc_1800083C7
0x1800083e0  mov     edx, 89h
0x1800083e5  jmp     short loc_1800083C7
0x1800083e7  mov     ebx, 80070057h
0x1800083ec  mov     edx, 7Bh ; '{'
0x1800083f1  jmp     loc_18000830E
0x1800083f6  mov     r8d, [rdi+14h]
0x1800083fa  lea     rdx, aEnablewindowco; "EnableWindowColorization"
0x180008401  mov     rcx, [rsp+58h+hKey]
0x180008406  call    DwmpSaveColorizationParameter
0x18000840b  mov     ebx, eax
0x18000840d  test    eax, eax
0x18000840f  js      short loc_180008437
0x180008411  mov     r8d, [rdi+18h]
0x180008415  lea     rdx, aColorizationgl; "ColorizationGlassAttribute"
0x18000841c  mov     rcx, [rsp+58h+hKey]
0x180008421  call    DwmpSaveColorizationParameter
0x180008426  mov     ebx, eax
0x180008428  test    eax, eax
0x18000842a  jns     loc_180008315
0x180008430  mov     edx, 8Fh
0x180008435  jmp     short loc_1800083C7
0x180008437  mov     edx, 8Eh
0x18000843c  jmp     short loc_1800083C7
0x18000843e  mov     edx, 8Bh
0x180008443  jmp     short loc_1800083C7
0x180008445  mov     edx, 8Ah
0x18000844a  jmp     loc_1800083C7
```
