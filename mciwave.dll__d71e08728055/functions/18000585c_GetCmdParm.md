# GetCmdParm

- ea: `0x18000585c`
- end: `0x180005991`
- name: `GetCmdParm`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005680`

## callees

- `0x18000585c`
- `0x180005c60`

## import_xrefs

- `api-ms-win-core-privateprofile-l1-1-0!GetProfileStringW` at `0x18000591c`
- `api-ms-win-core-privateprofile-l1-1-0!GetProfileStringW` at `0x18000591c`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800058af`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x1800058af`

## pseudocode

```c
__int64 GetCmdParm()
{
  __int64 v0; // rdi
  WCHAR v1; // ax
  WCHAR *v2; // r8
  WCHAR *v3; // rbx
  WCHAR *v4; // rcx
  unsigned int v5; // ecx
  int v6; // eax
  WCHAR v8[8]; // [rsp+30h] [rbp-138h] BYREF
  WCHAR ReturnedString[136]; // [rsp+40h] [rbp-128h] BYREF

  v0 = qword_1800085B8;
  if ( GetPrivateProfileStringW(
         *(LPCWSTR *)(qword_1800085B8 + 4),
         *(LPCWSTR *)(qword_1800085B8 + 12),
         &aszNULL,
         ReturnedString,
         0x84u,
         aszSystemIni) )
  {
    v1 = ReturnedString[0];
    v2 = ReturnedString;
    while ( v1 && v1 != 32 )
      v1 = *++v2;
    while ( *v2 == 32 )
      ++v2;
    v3 = v2;
    if ( *v2 )
    {
      do
        v4 = v3--;
      while ( *v3 == 32 );
      v3 = v4;
      *v4 = 0;
    }
    if ( GetProfileStringW(ReturnedString, *(LPCWSTR *)(v0 + 12), v2, v8, 6u) )
      v3 = v8;
  }
  else
  {
    v3 = ReturnedString;
    ReturnedString[0] = 0;
  }
  v5 = 0;
  while ( (unsigned __int16)(*v3 - 48) <= 9u )
  {
    v6 = *v3++;
    v5 = v6 + 2 * (5 * v5 - 24);
    if ( v5 >= 9 )
    {
      if ( v5 > 9 )
        return 4;
      break;
    }
  }
  if ( v5 >= 2 )
    return v5;
  return 4;
}

```

## disassembly

```asm
0x18000585c  mov     [rsp+arg_0], rbx
0x180005861  mov     [rsp+arg_8], rsi
0x180005866  push    rdi
0x180005867  sub     rsp, 160h
0x18000586e  mov     rax, cs:__security_cookie
0x180005875  xor     rax, rsp
0x180005878  mov     [rsp+168h+var_18], rax
0x180005880  mov     rdi, cs:qword_1800085B8
0x180005887  lea     rax, aszSystemIni; "system.ini"
0x18000588e  mov     [rsp+168h+lpFileName], rax; lpFileName
0x180005893  lea     r9, [rsp+168h+ReturnedString]; lpReturnedString
0x180005898  lea     r8, aszNULL; lpDefault
0x18000589f  mov     [rsp+168h+nSize], 84h; nSize
0x1800058a7  mov     rdx, [rdi+0Ch]; lpKeyName
0x1800058ab  mov     rcx, [rdi+4]; lpAppName
0x1800058af  call    cs:__imp_GetPrivateProfileStringW
0x1800058b5  xor     esi, esi
0x1800058b7  test    eax, eax
0x1800058b9  jz      short loc_18000592D
0x1800058bb  movzx   eax, [rsp+168h+ReturnedString]
0x1800058c0  lea     r8, [rsp+168h+ReturnedString]
0x1800058c5  mov     dx, 20h ; ' '
0x1800058c9  jmp     short loc_1800058D8
0x1800058cb  cmp     ax, dx
0x1800058ce  jz      short loc_1800058E3
0x1800058d0  add     r8, 2
0x1800058d4  movzx   eax, word ptr [r8]
0x1800058d8  test    ax, ax
0x1800058db  jnz     short loc_1800058CB
0x1800058dd  jmp     short loc_1800058E3
0x1800058df  add     r8, 2; lpDefault
0x1800058e3  movzx   eax, word ptr [r8]
0x1800058e7  cmp     ax, dx
0x1800058ea  jz      short loc_1800058DF
0x1800058ec  mov     rbx, r8
0x1800058ef  test    ax, ax
0x1800058f2  jz      short loc_180005906
0x1800058f4  mov     rcx, rbx
0x1800058f7  sub     rbx, 2
0x1800058fb  cmp     [rbx], dx
0x1800058fe  jz      short loc_1800058F4
0x180005900  mov     rbx, rcx
0x180005903  mov     [rcx], si
0x180005906  mov     rdx, [rdi+0Ch]; lpKeyName
0x18000590a  lea     r9, [rsp+168h+var_138]; lpReturnedString
0x18000590f  lea     rcx, [rsp+168h+ReturnedString]; lpAppName
0x180005914  mov     [rsp+168h+nSize], 6; nSize
0x18000591c  call    cs:__imp_GetProfileStringW
0x180005922  test    eax, eax
0x180005924  jz      short loc_180005937
0x180005926  lea     rbx, [rsp+168h+var_138]
0x18000592b  jmp     short loc_180005937
0x18000592d  lea     rbx, [rsp+168h+ReturnedString]
0x180005932  mov     [rsp+168h+ReturnedString], si
0x180005937  mov     ecx, esi
0x180005939  mov     edx, 9
0x18000593e  movzx   eax, word ptr [rbx]
0x180005941  sub     ax, 30h ; '0'
0x180005945  cmp     ax, dx
0x180005948  ja      short loc_180005960
0x18000594a  movzx   eax, word ptr [rbx]
0x18000594d  lea     ecx, [rcx+rcx*4]
0x180005950  lea     ecx, [rcx-18h]
0x180005953  add     rbx, 2
0x180005957  lea     ecx, [rax+rcx*2]
0x18000595a  cmp     ecx, edx
0x18000595c  jb      short loc_18000593E
0x18000595e  ja      short loc_180005965
0x180005960  cmp     ecx, 2
0x180005963  jnb     short loc_18000596A
0x180005965  mov     ecx, 4
0x18000596a  mov     eax, ecx
0x18000596c  mov     rcx, [rsp+168h+var_18]
0x180005974  xor     rcx, rsp; StackCookie
0x180005977  call    __security_check_cookie
0x18000597c  lea     r11, [rsp+168h+var_8]
0x180005984  mov     rbx, [r11+10h]
0x180005988  mov     rsi, [r11+18h]
0x18000598c  mov     rsp, r11
0x18000598f  pop     rdi
0x180005990  retn
```
