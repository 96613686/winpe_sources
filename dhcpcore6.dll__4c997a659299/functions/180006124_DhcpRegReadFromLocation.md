# DhcpRegReadFromLocation

- ea: `0x180006124`
- end: `0x1800062e2`
- name: `DhcpRegReadFromLocation`
- size: `446`
- prototype: `__int64 __fastcall(void *Src, __int64, BYTE **, DWORD *, LPDWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180005db8`
- `0x180005e8c`
- `0x18000890c`

## callees

- `0x180006124`
- `0x180007344`
- `0x180007564`
- `0x1800337d0`
- `0x1800338c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800061b3`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800061b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006287`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006287`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800061ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800061ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000621d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000625d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000621d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000625d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000629d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000629d`

## pseudocode

```c
__int64 __fastcall DhcpRegReadFromLocation(void *Src, __int64 a2, BYTE **a3, DWORD *a4, LPDWORD a5)
{
  LPDWORD lpcbData; // r14
  unsigned int Value; // ebx
  wchar_t *v10; // rax
  const WCHAR *v11; // rdi
  BYTE *v12; // rax
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_S(1028, 16, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids, a2);
  lpcbData = a5;
  *a3 = 0;
  *lpcbData = 0;
  *a4 = 0;
  Value = DhcpRegExpandString(Src);
  if ( !Value )
  {
    v10 = wcsrchr(0, 0x5Cu);
    v11 = v10;
    if ( v10 )
    {
      *v10 = 0;
      v11 = v10 + 1;
    }
    Value = RegOpenKeyExW(HKEY_LOCAL_MACHINE, 0, 0, 0xFu, &hKey);
    if ( !Value )
    {
      Value = RegQueryValueExW(hKey, v11, 0, a4, 0, lpcbData);
      if ( !Value )
      {
        v12 = (BYTE *)DhcpAlloc(*lpcbData);
        *a3 = v12;
        if ( v12 )
          Value = RegQueryValueExW(hKey, v11, 0, a4, v12, lpcbData);
        else
          Value = 8;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 17, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids, Value);
  return Value;
}

```

## disassembly

```asm
0x180006124  mov     rax, rsp
0x180006127  mov     [rax+8], rbx
0x18000612b  mov     [rax+10h], rbp
0x18000612f  push    rdi
0x180006130  push    r14
0x180006132  push    r15
0x180006134  sub     rsp, 30h
0x180006138  mov     r15, r9
0x18000613b  mov     qword ptr [rax+18h], 0
0x180006143  mov     rbp, r8
0x180006146  mov     qword ptr [rax+20h], 0
0x18000614e  mov     rbx, rdx
0x180006151  mov     rdi, rcx
0x180006154  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000615b  jz      short loc_180006176
0x18000615d  mov     edx, 10h
0x180006162  lea     r8, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids
0x180006169  mov     ecx, 404h
0x18000616e  mov     r9, rbx
0x180006171  call    WPP_SF_S
0x180006176  mov     r14, [rsp+48h+arg_20]
0x18000617b  lea     r8, [rsp+48h+Str]
0x180006180  mov     rdx, rbx
0x180006183  mov     qword ptr [rbp+0], 0
0x18000618b  mov     rcx, rdi; Src
0x18000618e  mov     dword ptr [r14], 0
0x180006195  mov     dword ptr [r15], 0
0x18000619c  call    DhcpRegExpandString
0x1800061a1  mov     ebx, eax
0x1800061a3  test    eax, eax
0x1800061a5  jnz     loc_18000626B
0x1800061ab  mov     rcx, [rsp+48h+Str]; Str
0x1800061b0  lea     edx, [rax+5Ch]; Ch
0x1800061b3  call    cs:__imp_wcsrchr
0x1800061ba  nop     dword ptr [rax+rax+00h]
0x1800061bf  mov     rdi, rax
0x1800061c2  test    rax, rax
0x1800061c5  jz      short loc_1800061D0
0x1800061c7  xor     ecx, ecx
0x1800061c9  mov     [rax], cx
0x1800061cc  add     rdi, 2
0x1800061d0  mov     rdx, [rsp+48h+Str]; lpSubKey
0x1800061d5  lea     rax, [rsp+48h+hKey]
0x1800061da  mov     r9d, 0Fh; samDesired
0x1800061e0  mov     [rsp+48h+phkResult], rax; phkResult
0x1800061e5  xor     r8d, r8d; ulOptions
0x1800061e8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800061ef  call    cs:__imp_RegOpenKeyExW
0x1800061f6  nop     dword ptr [rax+rax+00h]
0x1800061fb  mov     ebx, eax
0x1800061fd  test    eax, eax
0x1800061ff  jnz     short loc_18000626B
0x180006201  mov     rcx, [rsp+48h+hKey]; hKey
0x180006206  mov     r9, r15; lpType
0x180006209  mov     [rsp+48h+lpcbData], r14; lpcbData
0x18000620e  xor     r8d, r8d; lpReserved
0x180006211  mov     rdx, rdi; lpValueName
0x180006214  mov     [rsp+48h+phkResult], 0; lpData
0x18000621d  call    cs:__imp_RegQueryValueExW
0x180006224  nop     dword ptr [rax+rax+00h]
0x180006229  mov     ebx, eax
0x18000622b  test    eax, eax
0x18000622d  jnz     short loc_18000626B
0x18000622f  mov     ecx, [r14]
0x180006232  call    DhcpAlloc
0x180006237  mov     [rbp+0], rax
0x18000623b  test    rax, rax
0x18000623e  jnz     short loc_180006245
0x180006240  lea     ebx, [rax+8]
0x180006243  jmp     short loc_18000626B
0x180006245  mov     rcx, [rsp+48h+hKey]; hKey
0x18000624a  mov     r9, r15; lpType
0x18000624d  mov     [rsp+48h+lpcbData], r14; lpcbData
0x180006252  xor     r8d, r8d; lpReserved
0x180006255  mov     rdx, rdi; lpValueName
0x180006258  mov     [rsp+48h+phkResult], rax; lpData
0x18000625d  call    cs:__imp_RegQueryValueExW
0x180006264  nop     dword ptr [rax+rax+00h]
0x180006269  mov     ebx, eax
0x18000626b  cmp     [rsp+48h+Str], 0
0x180006271  jz      short loc_180006293
0x180006273  mov     rcx, gs:60h
0x18000627c  xor     edx, edx; dwFlags
0x18000627e  mov     r8, [rsp+48h+Str]; lpMem
0x180006283  mov     rcx, [rcx+30h]; hHeap
0x180006287  call    cs:__imp_HeapFree
0x18000628e  nop     dword ptr [rax+rax+00h]
0x180006293  mov     rcx, [rsp+48h+hKey]; hKey
0x180006298  test    rcx, rcx
0x18000629b  jz      short loc_1800062A9
0x18000629d  call    cs:__imp_RegCloseKey
0x1800062a4  nop     dword ptr [rax+rax+00h]
0x1800062a9  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800062b0  jz      short loc_1800062CB
0x1800062b2  mov     edx, 11h
0x1800062b7  lea     r8, WPP_5d68708c8ecd3afe0a2d79d623927bf9_Traceguids
0x1800062be  mov     ecx, 404h
0x1800062c3  mov     r9d, ebx
0x1800062c6  call    WPP_SF_D
0x1800062cb  mov     rbp, [rsp+48h+arg_8]
0x1800062d0  mov     eax, ebx
0x1800062d2  mov     rbx, [rsp+48h+arg_0]
0x1800062d7  add     rsp, 30h
0x1800062db  pop     r15
0x1800062dd  pop     r14
0x1800062df  pop     rdi
0x1800062e0  retn
```
