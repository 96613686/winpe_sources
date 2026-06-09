# DiscpAddRemoveDeviceToList

- ea: `0x1800080b0`
- end: `0x180008336`
- name: `DiscpAddRemoveDeviceToList`
- size: `646`
- prototype: `__int64 __fastcall(wchar_t *String1, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180004740`

## callees

- `0x18000325c`
- `0x1800080b0`
- `0x1800085c4`
- `0x18000bca8`
- `0x18001d374`

## import_xrefs

- `ISCSIUM!DiscpAddStringToMultiSzList` at `0x180008275`
- `ISCSIUM!DiscpAddStringToMultiSzList` at `0x180008275`
- `ISCSIUM!DiscpRemoveStringFromMultiSzList` at `0x180008153`
- `ISCSIUM!DiscpRemoveStringFromMultiSzList` at `0x18000829f`
- `ISCSIUM!DiscpRemoveStringFromMultiSzList` at `0x180008153`
- `ISCSIUM!DiscpRemoveStringFromMultiSzList` at `0x18000829f`
- `ISCSIUM!DiscpGetRegistryValue` at `0x180008137`
- `ISCSIUM!DiscpGetRegistryValue` at `0x180008137`
- `ISCSIUM!DiscpAllocMemory` at `0x180008173`
- `ISCSIUM!DiscpAllocMemory` at `0x1800081bf`
- `ISCSIUM!DiscpAllocMemory` at `0x180008173`
- `ISCSIUM!DiscpAllocMemory` at `0x1800081bf`
- `ISCSIUM!DiscpSetRegistryValue` at `0x1800082f0`
- `ISCSIUM!DiscpSetRegistryValue` at `0x1800082f0`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x1800080fe`
- `ISCSIUM!DiscpOpenRegistryKey` at `0x1800080fe`
- `ISCSIUM!DiscpFreeMemory` at `0x18000820a`
- `ISCSIUM!DiscpFreeMemory` at `0x180008288`
- `ISCSIUM!DiscpFreeMemory` at `0x1800082be`
- `ISCSIUM!DiscpFreeMemory` at `0x180008308`
- `ISCSIUM!DiscpFreeMemory` at `0x18000820a`
- `ISCSIUM!DiscpFreeMemory` at `0x180008288`
- `ISCSIUM!DiscpFreeMemory` at `0x1800082be`
- `ISCSIUM!DiscpFreeMemory` at `0x180008308`
- `ISCSIUM!DiscpIsStringInList` at `0x180008238`
- `ISCSIUM!DiscpIsStringInList` at `0x18000825e`
- `ISCSIUM!DiscpIsStringInList` at `0x180008238`
- `ISCSIUM!DiscpIsStringInList` at `0x18000825e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008318`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008318`

## pseudocode

```c
__int64 __fastcall DiscpAddRemoveDeviceToList(wchar_t *String1, char a2)
{
  unsigned int v4; // ebx
  unsigned int RegistryValue; // eax
  _WORD *v6; // rax
  _WORD *v7; // rcx
  __int64 v8; // rbx
  wchar_t *v9; // rax
  const WCHAR *v10; // rsi
  wchar_t *v11; // r8
  int v13; // [rsp+30h] [rbp-30h]
  wchar_t *v14; // [rsp+40h] [rbp-20h]
  HKEY hKey; // [rsp+48h] [rbp-18h] BYREF
  __int64 v16; // [rsp+50h] [rbp-10h] BYREF
  int v17; // [rsp+A0h] [rbp+40h] BYREF
  int v18; // [rsp+B0h] [rbp+50h] BYREF
  _WORD *v19; // [rsp+B8h] [rbp+58h] BYREF

  v14 = 0;
  hKey = 0;
  v19 = 0;
  v17 = 0;
  v16 = 0;
  v18 = 0;
  if ( !*String1 )
    return 87;
  v4 = DiscpOpenRegistryKey(&hKey, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery", 983103);
  if ( !v4 )
  {
    RegistryValue = DiscpGetRegistryValue(hKey, 0, L"VolumeList", 7, 0, &v19, &v17);
    v4 = RegistryValue;
    if ( RegistryValue )
    {
      if ( RegistryValue != 2 )
      {
        v19 = 0;
LABEL_41:
        RegCloseKey(hKey);
        return v4;
      }
      v17 = 2;
      v6 = (_WORD *)DiscpAllocMemory(2);
      v19 = v6;
      v7 = v6;
      if ( !v6 )
      {
        v4 = 8;
LABEL_38:
        if ( v7 )
          DiscpFreeMemory(v7);
        goto LABEL_41;
      }
      *v6 = 0;
    }
    else
    {
      if ( a2 )
        goto LABEL_11;
      if ( !(unsigned int)DiscpRemoveStringFromMultiSzList(&v19, &v17, String1) )
      {
LABEL_35:
        LOBYTE(v13) = 0;
        v4 = DiscpSetRegistryValue(hKey, 0, L"VolumeList", 7, v19, v17, v13);
LABEL_36:
        v7 = v19;
        goto LABEL_38;
      }
    }
    v4 = 0;
LABEL_11:
    if ( !wcsncmp_0(String1, L"\\\\?\\", 4u) )
    {
      v11 = String1;
      v14 = String1;
    }
    else
    {
      v8 = -1;
      do
        ++v8;
      while ( String1[v8] );
      v9 = (wchar_t *)DiscpAllocMemory((unsigned int)(2 * (v8 + 2)));
      v10 = v9;
      if ( v9 )
      {
        StringCchCopyW(v9, (unsigned int)(v8 + 2), String1);
        if ( String1[(unsigned int)(v8 - 1)] != 92 )
        {
          v10[(unsigned int)v8] = 92;
          v10[(unsigned int)(v8 + 1)] = 0;
        }
        v4 = DiscpVolumeDeviceNameForVolumeMountPoint(v10);
        DiscpFreeMemory(v10);
      }
      else
      {
        v4 = 8;
      }
      v11 = 0;
    }
    if ( v4 )
      goto LABEL_36;
    if ( a2 )
    {
      if ( DiscpIsStringInList(v19, v11) )
      {
        v4 = -268500900;
      }
      else
      {
        v4 = DiscpBuildDeviceList(&v16, &v18);
        if ( !v4 )
        {
          if ( DiscpIsStringInList(v16, v14) )
            v4 = DiscpAddStringToMultiSzList(&v19, &v17, v14);
          else
            v4 = -268500898;
          DiscpFreeMemory(v16);
        }
      }
    }
    else
    {
      v4 = DiscpRemoveStringFromMultiSzList(&v19, &v17, v11);
      if ( v4 == 1168 )
        v4 = -268500899;
    }
    if ( v14 != String1 )
      DiscpFreeMemory(v14);
    if ( v4 )
      goto LABEL_36;
    goto LABEL_35;
  }
  return v4;
}

```

## disassembly

```asm
0x1800080b0  push    rbp
0x1800080b2  push    rbx
0x1800080b3  push    rsi
0x1800080b4  push    rdi
0x1800080b5  push    r12
0x1800080b7  push    r14
0x1800080b9  push    r15
0x1800080bb  mov     rbp, rsp
0x1800080be  sub     rsp, 60h
0x1800080c2  xor     r12d, r12d
0x1800080c5  mov     r14b, dl
0x1800080c8  mov     rdi, rcx
0x1800080cb  mov     [rbp+var_20], r12
0x1800080cf  mov     [rbp+hKey], r12
0x1800080d3  mov     [rbp+arg_18], r12
0x1800080d7  mov     [rbp+arg_0], r12d
0x1800080db  mov     [rbp+var_10], r12
0x1800080df  mov     [rbp+arg_10], r12d
0x1800080e3  cmp     [rcx], r12w
0x1800080e7  jz      loc_180008320
0x1800080ed  mov     r8d, 0F003Fh
0x1800080f3  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800080fa  lea     rcx, [rbp+hKey]
0x1800080fe  call    cs:__imp_DiscpOpenRegistryKey
0x180008104  mov     ebx, eax
0x180008106  test    eax, eax
0x180008108  jnz     loc_180008325
0x18000810e  mov     rcx, [rbp+hKey]
0x180008112  lea     rax, [rbp+arg_0]
0x180008116  mov     qword ptr [rsp+60h+var_30], rax
0x18000811b  lea     r9d, [r12+7]
0x180008120  lea     rax, [rbp+arg_18]
0x180008124  xor     edx, edx
0x180008126  mov     [rsp+60h+var_38], rax
0x18000812b  lea     r8, aVolumelist; "VolumeList"
0x180008132  mov     byte ptr [rsp+60h+var_40], r12b
0x180008137  call    cs:__imp_DiscpGetRegistryValue
0x18000813d  mov     ebx, eax
0x18000813f  test    eax, eax
0x180008141  jnz     short loc_180008163
0x180008143  test    r14b, r14b
0x180008146  jnz     short loc_180008190
0x180008148  mov     r8, rdi
0x18000814b  lea     rdx, [rbp+arg_0]
0x18000814f  lea     rcx, [rbp+arg_18]
0x180008153  call    cs:__imp_DiscpRemoveStringFromMultiSzList
0x180008159  test    eax, eax
0x18000815b  jz      loc_1800082C8
0x180008161  jmp     short loc_18000818D
0x180008163  mov     ecx, 2
0x180008168  cmp     eax, ecx
0x18000816a  jnz     loc_180008310
0x180008170  mov     [rbp+arg_0], ecx
0x180008173  call    cs:__imp_DiscpAllocMemory
0x180008179  mov     [rbp+arg_18], rax
0x18000817d  mov     rcx, rax
0x180008180  test    rax, rax
0x180008183  jz      loc_1800082FE
0x180008189  mov     [rax], r12w
0x18000818d  mov     ebx, r12d
0x180008190  mov     r8d, 4; MaxCount
0x180008196  lea     rdx, String2; "\\\\?\\"
0x18000819d  mov     rcx, rdi; String1
0x1800081a0  call    wcsncmp_0
0x1800081a5  test    eax, eax
0x1800081a7  jz      short loc_18000821D
0x1800081a9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800081ad  inc     rbx
0x1800081b0  cmp     [rdi+rbx*2], r12w
0x1800081b5  jnz     short loc_1800081AD
0x1800081b7  lea     r15d, [rbx+2]
0x1800081bb  lea     ecx, [r15+r15]
0x1800081bf  call    cs:__imp_DiscpAllocMemory
0x1800081c5  mov     rsi, rax
0x1800081c8  test    rax, rax
0x1800081cb  jz      short loc_180008212
0x1800081cd  mov     edx, r15d; cchDest
0x1800081d0  mov     r8, rdi; pszSrc
0x1800081d3  mov     rcx, rax; pszDest
0x1800081d6  call    StringCchCopyW
0x1800081db  mov     eax, 5Ch ; '\'
0x1800081e0  lea     r11d, [rbx-1]
0x1800081e4  cmp     [rdi+r11*2], ax
0x1800081e9  jz      short loc_1800081F9
0x1800081eb  mov     ecx, ebx
0x1800081ed  mov     [rsi+rcx*2], ax
0x1800081f1  lea     eax, [rbx+1]
0x1800081f4  mov     [rsi+rax*2], r12w
0x1800081f9  lea     rdx, [rbp+var_20]
0x1800081fd  mov     rcx, rsi; lpszVolumeMountPoint
0x180008200  call    DiscpVolumeDeviceNameForVolumeMountPoint
0x180008205  mov     rcx, rsi
0x180008208  mov     ebx, eax
0x18000820a  call    cs:__imp_DiscpFreeMemory
0x180008210  jmp     short loc_180008217
0x180008212  mov     ebx, 8
0x180008217  mov     r8, [rbp+var_20]
0x18000821b  jmp     short loc_180008224
0x18000821d  mov     r8, rdi
0x180008220  mov     [rbp+var_20], rdi
0x180008224  test    ebx, ebx
0x180008226  jnz     loc_1800082F8
0x18000822c  test    r14b, r14b
0x18000822f  jz      short loc_180008297
0x180008231  mov     rcx, [rbp+arg_18]
0x180008235  mov     rdx, r8
0x180008238  call    cs:__imp_DiscpIsStringInList
0x18000823e  test    rax, rax
0x180008241  jnz     short loc_180008290
0x180008243  lea     rdx, [rbp+arg_10]
0x180008247  lea     rcx, [rbp+var_10]
0x18000824b  call    DiscpBuildDeviceList
0x180008250  mov     ebx, eax
0x180008252  test    eax, eax
0x180008254  jnz     short loc_1800082B5
0x180008256  mov     rdx, [rbp+var_20]
0x18000825a  mov     rcx, [rbp+var_10]
0x18000825e  call    cs:__imp_DiscpIsStringInList
0x180008264  test    rax, rax
0x180008267  jz      short loc_18000827F
0x180008269  mov     r8, [rbp+var_20]
0x18000826d  lea     rdx, [rbp+arg_0]
0x180008271  lea     rcx, [rbp+arg_18]
0x180008275  call    cs:__imp_DiscpAddStringToMultiSzList
0x18000827b  mov     ebx, eax
0x18000827d  jmp     short loc_180008284
0x18000827f  mov     ebx, 0EFFF005Eh
0x180008284  mov     rcx, [rbp+var_10]
0x180008288  call    cs:__imp_DiscpFreeMemory
0x18000828e  jmp     short loc_1800082B5
0x180008290  mov     ebx, 0EFFF005Ch
0x180008295  jmp     short loc_1800082B5
0x180008297  lea     rdx, [rbp+arg_0]
0x18000829b  lea     rcx, [rbp+arg_18]
0x18000829f  call    cs:__imp_DiscpRemoveStringFromMultiSzList
0x1800082a5  mov     ebx, eax
0x1800082a7  mov     eax, 0EFFF005Dh
0x1800082ac  cmp     ebx, 490h
0x1800082b2  cmovz   ebx, eax
0x1800082b5  mov     rcx, [rbp+var_20]
0x1800082b9  cmp     rcx, rdi
0x1800082bc  jz      short loc_1800082C4
0x1800082be  call    cs:__imp_DiscpFreeMemory
0x1800082c4  test    ebx, ebx
0x1800082c6  jnz     short loc_1800082F8
0x1800082c8  mov     eax, [rbp+arg_0]
0x1800082cb  lea     r8, aVolumelist; "VolumeList"
0x1800082d2  mov     rcx, [rbp+hKey]
0x1800082d6  mov     r9d, 7
0x1800082dc  mov     byte ptr [rsp+60h+var_30], r12b
0x1800082e1  xor     edx, edx
0x1800082e3  mov     dword ptr [rsp+60h+var_38], eax
0x1800082e7  mov     rax, [rbp+arg_18]
0x1800082eb  mov     [rsp+60h+var_40], rax
0x1800082f0  call    cs:__imp_DiscpSetRegistryValue
0x1800082f6  mov     ebx, eax
0x1800082f8  mov     rcx, [rbp+arg_18]
0x1800082fc  jmp     short loc_180008303
0x1800082fe  mov     ebx, 8
0x180008303  test    rcx, rcx
0x180008306  jz      short loc_180008314
0x180008308  call    cs:__imp_DiscpFreeMemory
0x18000830e  jmp     short loc_180008314
0x180008310  mov     [rbp+arg_18], r12
0x180008314  mov     rcx, [rbp+hKey]; hKey
0x180008318  call    cs:__imp_RegCloseKey
0x18000831e  jmp     short loc_180008325
0x180008320  mov     ebx, 57h ; 'W'
0x180008325  mov     eax, ebx
0x180008327  add     rsp, 60h
0x18000832b  pop     r15
0x18000832d  pop     r14
0x18000832f  pop     r12
0x180008331  pop     rdi
0x180008332  pop     rsi
0x180008333  pop     rbx
0x180008334  pop     rbp
0x180008335  retn
```
