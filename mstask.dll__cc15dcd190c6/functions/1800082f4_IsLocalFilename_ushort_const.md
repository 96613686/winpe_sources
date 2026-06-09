# IsLocalFilename(ushort const *)

- ea: `0x1800082f4`
- end: `0x18000844a`
- name: `?IsLocalFilename@@YAHPEBG@Z`
- size: `342`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007860`
- `0x1800114b4`
- `0x180011c90`
- `0x180012a04`
- `0x180018300`

## callees

- `0x1800082f4`
- `0x18001aac0`

## import_xrefs

- `msvcrt!wcschr` at `0x180008350`
- `msvcrt!wcschr` at `0x180008350`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000839f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000839f`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180008414`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180008414`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800083bb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800083bb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18000837a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18000837a`

## pseudocode

```c
_BOOL8 __fastcall IsLocalFilename(const unsigned __int16 *a1)
{
  __int16 v2; // cx
  const WCHAR *v3; // rdi
  wchar_t *v4; // rax
  int v5; // ebx
  WCHAR *v6; // rdx
  UINT DriveTypeW; // eax
  DWORD nSize; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v10[6]; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t v11; // [rsp+2Eh] [rbp-D2h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR v13[264]; // [rsp+240h] [rbp+140h] BYREF

  if ( a1 )
  {
    v2 = *a1;
    if ( v2 )
    {
      if ( v2 == 92 )
      {
        if ( a1[1] == 92 )
        {
          v3 = a1 + 2;
          v4 = wcschr(a1 + 2, 0x5Cu);
          if ( v4 )
          {
            nSize = 257;
            v5 = v4 - a1 - 2;
            if ( GetComputerNameW(Buffer, &nSize) )
            {
              *(_DWORD *)v10 = 257;
              if ( GetComputerNameExW(ComputerNamePhysicalDnsFullyQualified, v13, (LPDWORD)v10) )
              {
                if ( v5 == nSize )
                {
                  v6 = Buffer;
                  return lstrcmpiW(v3, v6) == 0;
                }
                if ( v5 == *(_DWORD *)v10 )
                {
                  v6 = v13;
                  return lstrcmpiW(v3, v6) == 0;
                }
              }
            }
          }
          return 0;
        }
        return 1;
      }
      if ( (unsigned __int16)(v2 - 97) > 0x19u && (unsigned __int16)(v2 - 65) > 0x19u )
        return 1;
      if ( a1[1] != 58 )
        return 1;
      *(_DWORD *)&v10[2] = *(_DWORD *)L":\\";
      *(_WORD *)v10 = v2;
      v11 = asc_18001DAC8[3];
      DriveTypeW = GetDriveTypeW((LPCWSTR)v10);
      if ( (DriveTypeW & 0xFFFFFFFA) != 0 || DriveTypeW == 5 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800082f4  push    rbp
0x1800082f6  push    rbx
0x1800082f7  push    rsi
0x1800082f8  push    rdi
0x1800082f9  lea     rbp, [rsp-368h]
0x180008301  sub     rsp, 468h
0x180008308  mov     rax, cs:__security_cookie
0x18000830f  xor     rax, rsp
0x180008312  mov     [rbp+380h+var_30], rax
0x180008319  xor     esi, esi
0x18000831b  mov     rbx, rcx
0x18000831e  test    rcx, rcx
0x180008321  jz      loc_18000842D
0x180008327  movzx   ecx, word ptr [rcx]
0x18000832a  test    cx, cx
0x18000832d  jz      loc_18000842D
0x180008333  lea     edx, [rsi+5Ch]; Ch
0x180008336  cmp     cx, dx
0x180008339  jnz     loc_1800083DB
0x18000833f  cmp     [rbx+2], dx
0x180008343  jnz     loc_180008426
0x180008349  lea     rdi, [rbx+4]
0x18000834d  mov     rcx, rdi; Str
0x180008350  call    cs:__imp_wcschr
0x180008356  test    rax, rax
0x180008359  jz      loc_18000842D
0x18000835f  sub     rax, rbx
0x180008362  mov     [rsp+480h+nSize], 101h
0x18000836a  sar     rax, 1
0x18000836d  lea     rdx, [rsp+480h+nSize]; nSize
0x180008372  lea     rcx, [rsp+480h+Buffer]; lpBuffer
0x180008377  lea     ebx, [rax-2]
0x18000837a  call    cs:__imp_GetComputerNameW
0x180008380  test    eax, eax
0x180008382  jz      loc_18000842D
0x180008388  lea     r8, [rsp+480h+var_458]; nSize
0x18000838d  mov     dword ptr [rsp+480h+var_458], 101h
0x180008395  lea     rdx, [rbp+380h+var_240]; lpBuffer
0x18000839c  lea     ecx, [rsi+7]; NameType
0x18000839f  call    cs:__imp_GetComputerNameExW
0x1800083a5  test    eax, eax
0x1800083a7  jz      loc_18000842D
0x1800083ad  cmp     ebx, [rsp+480h+nSize]
0x1800083b1  jnz     short loc_1800083CC
0x1800083b3  lea     rdx, [rsp+480h+Buffer]; lpString2
0x1800083b8  mov     rcx, rdi; lpString1
0x1800083bb  call    cs:__imp_lstrcmpiW
0x1800083c1  test    eax, eax
0x1800083c3  mov     ecx, esi
0x1800083c5  setz    cl
0x1800083c8  mov     eax, ecx
0x1800083ca  jmp     short loc_18000842F
0x1800083cc  cmp     ebx, dword ptr [rsp+480h+var_458]
0x1800083d0  jnz     short loc_18000842D
0x1800083d2  lea     rdx, [rbp+380h+var_240]
0x1800083d9  jmp     short loc_1800083B8
0x1800083db  lea     eax, [rcx-61h]
0x1800083de  cmp     ax, 19h
0x1800083e2  jbe     short loc_1800083ED
0x1800083e4  lea     eax, [rcx-41h]
0x1800083e7  cmp     ax, 19h
0x1800083eb  ja      short loc_180008426
0x1800083ed  cmp     word ptr [rbx+2], 3Ah ; ':'
0x1800083f2  jnz     short loc_180008426
0x1800083f4  mov     eax, dword ptr cs:asc_18001DAC8+2; ":\\"
0x1800083fa  mov     dword ptr [rsp+480h+var_458+2], eax
0x1800083fe  movzx   eax, word ptr cs:asc_18001DAC8+6; ""
0x180008405  mov     word ptr [rsp+480h+var_458], cx
0x18000840a  lea     rcx, [rsp+480h+var_458]; lpRootPathName
0x18000840f  mov     [rsp+480h+var_452], ax
0x180008414  call    cs:__imp_GetDriveTypeW
0x18000841a  test    eax, 0FFFFFFFAh
0x18000841f  jnz     short loc_180008426
0x180008421  cmp     eax, 5
0x180008424  jnz     short loc_18000842D
0x180008426  mov     eax, 1
0x18000842b  jmp     short loc_18000842F
0x18000842d  xor     eax, eax
0x18000842f  mov     rcx, [rbp+380h+var_30]
0x180008436  xor     rcx, rsp; StackCookie
0x180008439  call    __security_check_cookie
0x18000843e  add     rsp, 468h
0x180008445  pop     rdi
0x180008446  pop     rsi
0x180008447  pop     rbx
0x180008448  pop     rbp
0x180008449  retn
```
