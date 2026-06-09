# DOSFindFirstMatchingFile(x,x,x,x,x)

- ea: `0x10026772`
- end: `0x1002681b`
- name: `_DOSFindFirstMatchingFile@20`
- size: `169`
- prototype: `int __thiscall(wchar_t *FullPath, int, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1002b580`

## callees

- `0x10006400`
- `0x10022871`
- `0x10023563`
- `0x10026772`
- `0x100330d6`
- `0x10035510`
- `0x10035f40`

## pseudocode

```c
int __fastcall DOSFindFirstMatchingFile(wchar_t *FullPath, WCHAR *a2, int a3, int *a4, int *a5)
{
  int v7; // eax
  int FirstFileW; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [esp+10h] [ebp-25Ch] BYREF

  memset(&FindFileData, 0, sizeof(FindFileData));
  v7 = NetProtocolType(FullPath);
  *a4 = v7;
  if ( v7 != 1 )
  {
    if ( v7 == 2 )
    {
      if ( !NetFindFirstMatchingFile(FullPath, a2, a4 + 2, a5) )
        return 1;
    }
    else
    {
      FirstFileW = JetFindFirstFileW(FullPath, &FindFileData);
      a4[1] = FirstFileW;
      if ( FirstFileW != -1 )
      {
        WCSCPY2(a2, FindFileData.cFileName, 0x100u);
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x10026772  mov     edi, edi
0x10026774  push    ebp
0x10026775  mov     ebp, esp
0x10026777  sub     esp, 260h
0x1002677d  mov     eax, ___security_cookie
0x10026782  xor     eax, ebp
0x10026784  mov     [ebp+var_8], eax
0x10026787  mov     eax, [ebp+arg_8]
0x1002678a  push    ebx
0x1002678b  push    esi
0x1002678c  mov     esi, [ebp+arg_4]
0x1002678f  mov     ebx, edx
0x10026791  push    edi
0x10026792  push    250h; Size
0x10026797  mov     [ebp+var_260], eax
0x1002679d  mov     edi, ecx
0x1002679f  lea     eax, [ebp+FindFileData]
0x100267a5  push    0; Val
0x100267a7  push    eax; void *
0x100267a8  call    _memset
0x100267ad  add     esp, 0Ch
0x100267b0  mov     ecx, edi
0x100267b2  call    _NetProtocolType@4; NetProtocolType(x)
0x100267b7  mov     [esi], eax
0x100267b9  cmp     eax, 1
0x100267bc  jz      short loc_10026808
0x100267be  cmp     eax, 2
0x100267c1  jnz     short loc_100267DF
0x100267c3  push    [ebp+var_260]; int
0x100267c9  add     esi, 8
0x100267cc  mov     edx, ebx
0x100267ce  push    esi; int
0x100267cf  mov     ecx, edi; FullPath
0x100267d1  call    _NetFindFirstMatchingFile@16; NetFindFirstMatchingFile(x,x,x,x)
0x100267d6  test    eax, eax
0x100267d8  jnz     short loc_10026808
0x100267da  xor     eax, eax
0x100267dc  inc     eax
0x100267dd  jmp     short loc_1002680A
0x100267df  lea     eax, [ebp+FindFileData]
0x100267e5  push    eax; lpFindFileData
0x100267e6  push    edi; lpFileName
0x100267e7  call    _JetFindFirstFileW@8; JetFindFirstFileW(x,x)
0x100267ec  mov     [esi+4], eax
0x100267ef  cmp     eax, 0FFFFFFFFh
0x100267f2  jz      short loc_10026808
0x100267f4  push    100h
0x100267f9  lea     edx, [ebp+FindFileData.cFileName]
0x100267ff  mov     ecx, ebx
0x10026801  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10026806  jmp     short loc_100267DA
0x10026808  xor     eax, eax
0x1002680a  mov     ecx, [ebp+var_8]
0x1002680d  pop     edi
0x1002680e  pop     esi
0x1002680f  xor     ecx, ebp; StackCookie
0x10026811  pop     ebx
0x10026812  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10026817  leave
0x10026818  retn    0Ch
```
