# DhcpRegReadFromLocation

- ea: `0x180005178`
- end: `0x180005328`
- name: `DhcpRegReadFromLocation`
- size: `432`
- prototype: `__int64 __fastcall(void *Src, void *, BYTE **, DWORD *, LPDWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180004ae0`
- `0x18000582c`
- `0x18001afbc`
- `0x1800368d0`

## callees

- `0x180005178`
- `0x180005330`
- `0x180006440`
- `0x18004d1a0`
- `0x18004d200`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000525a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000525a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005217`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005217`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005227`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005227`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005290`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005290`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800052bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000531b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800052bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000531b`

## pseudocode

```c
__int64 __fastcall DhcpRegReadFromLocation(void *Src, void *a2, BYTE **a3, DWORD *a4, LPDWORD a5)
{
  LPDWORD lpcbData; // r14
  unsigned int Value; // ebx
  wchar_t *v12; // rax
  const WCHAR *v13; // rdi
  BYTE *v14; // rax
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_S(1028, 16, WPP_94d5010c5674399d06148e3a91870046_Traceguids, a2);
  lpcbData = a5;
  *a3 = 0;
  *lpcbData = 0;
  *a4 = 0;
  Value = DhcpRegExpandString(Src, a2);
  if ( !Value )
  {
    v12 = wcsrchr(0, 0x5Cu);
    v13 = v12;
    if ( v12 )
    {
      *v12 = 0;
      v13 = v12 + 1;
    }
    Value = RegOpenKeyExW(HKEY_LOCAL_MACHINE, 0, 0, 0xFu, &hKey);
    if ( !Value )
    {
      Value = RegQueryValueExW(hKey, v13, 0, a4, 0, lpcbData);
      if ( !Value )
      {
        v14 = (BYTE *)DhcpAlloc(*lpcbData);
        *a3 = v14;
        if ( v14 )
          Value = RegQueryValueExW(hKey, v13, 0, a4, v14, lpcbData);
        else
          Value = 8;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 17, WPP_94d5010c5674399d06148e3a91870046_Traceguids, Value);
  return Value;
}

```

## disassembly

```asm
0x180005178  mov     rax, rsp
0x18000517b  mov     [rax+8], rbx
0x18000517f  mov     [rax+10h], rbp
0x180005183  push    rdi
0x180005184  push    r14
0x180005186  push    r15
0x180005188  sub     rsp, 30h
0x18000518c  mov     r15, r9
0x18000518f  mov     qword ptr [rax+18h], 0
0x180005197  mov     rbp, r8
0x18000519a  mov     qword ptr [rax+20h], 0
0x1800051a2  mov     rbx, rdx
0x1800051a5  mov     rdi, rcx
0x1800051a8  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800051af  jz      short loc_1800051CA
0x1800051b1  mov     edx, 10h
0x1800051b6  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x1800051bd  mov     ecx, 404h
0x1800051c2  mov     r9, rbx
0x1800051c5  call    WPP_SF_S
0x1800051ca  mov     r14, [rsp+48h+arg_20]
0x1800051cf  lea     r8, [rsp+48h+lpMem]
0x1800051d4  mov     rdx, rbx; void *
0x1800051d7  mov     qword ptr [rbp+0], 0
0x1800051df  mov     rcx, rdi; Src
0x1800051e2  mov     dword ptr [r14], 0
0x1800051e9  mov     dword ptr [r15], 0
0x1800051f0  call    DhcpRegExpandString
0x1800051f5  mov     ebx, eax
0x1800051f7  test    eax, eax
0x1800051f9  jz      short loc_180005250
0x1800051fb  cmp     [rsp+48h+lpMem], 0
0x180005201  jz      short loc_18000521D
0x180005203  mov     rcx, gs:60h
0x18000520c  xor     edx, edx; dwFlags
0x18000520e  mov     r8, [rsp+48h+lpMem]; lpMem
0x180005213  mov     rcx, [rcx+30h]; hHeap
0x180005217  call    cs:__imp_HeapFree
0x18000521d  mov     rcx, [rsp+48h+hKey]; hKey
0x180005222  test    rcx, rcx
0x180005225  jz      short loc_18000522D
0x180005227  call    cs:__imp_RegCloseKey
0x18000522d  test    byte ptr cs:xmmword_1800616A0, 10h
0x180005234  jnz     loc_1800052E5
0x18000523a  mov     rbp, [rsp+48h+arg_8]
0x18000523f  mov     eax, ebx
0x180005241  mov     rbx, [rsp+48h+arg_0]
0x180005246  add     rsp, 30h
0x18000524a  pop     r15
0x18000524c  pop     r14
0x18000524e  pop     rdi
0x18000524f  retn
0x180005250  mov     rcx, [rsp+48h+lpMem]; Str
0x180005255  mov     edx, 5Ch ; '\'; Ch
0x18000525a  call    cs:__imp_wcsrchr
0x180005260  mov     rdi, rax
0x180005263  test    rax, rax
0x180005266  jz      short loc_180005271
0x180005268  xor     ecx, ecx
0x18000526a  mov     [rax], cx
0x18000526d  add     rdi, 2
0x180005271  mov     rdx, [rsp+48h+lpMem]; lpSubKey
0x180005276  lea     rax, [rsp+48h+hKey]
0x18000527b  mov     r9d, 0Fh; samDesired
0x180005281  mov     [rsp+48h+phkResult], rax; phkResult
0x180005286  xor     r8d, r8d; ulOptions
0x180005289  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005290  call    cs:__imp_RegOpenKeyExW
0x180005296  mov     ebx, eax
0x180005298  test    eax, eax
0x18000529a  jnz     loc_1800051FB
0x1800052a0  mov     rcx, [rsp+48h+hKey]; hKey
0x1800052a5  mov     r9, r15; lpType
0x1800052a8  mov     [rsp+48h+lpcbData], r14; lpcbData
0x1800052ad  xor     r8d, r8d; lpReserved
0x1800052b0  mov     rdx, rdi; lpValueName
0x1800052b3  mov     [rsp+48h+phkResult], 0; lpData
0x1800052bc  call    cs:__imp_RegQueryValueExW
0x1800052c2  mov     ebx, eax
0x1800052c4  test    eax, eax
0x1800052c6  jnz     loc_1800051FB
0x1800052cc  mov     ecx, [r14]
0x1800052cf  call    DhcpAlloc
0x1800052d4  mov     [rbp+0], rax
0x1800052d8  test    rax, rax
0x1800052db  jnz     short loc_180005303
0x1800052dd  lea     ebx, [rax+8]
0x1800052e0  jmp     loc_1800051FB
0x1800052e5  mov     edx, 11h
0x1800052ea  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x1800052f1  mov     ecx, 404h
0x1800052f6  mov     r9d, ebx
0x1800052f9  call    WPP_SF_D
0x1800052fe  jmp     loc_18000523A
0x180005303  mov     rcx, [rsp+48h+hKey]; hKey
0x180005308  mov     r9, r15; lpType
0x18000530b  mov     [rsp+48h+lpcbData], r14; lpcbData
0x180005310  xor     r8d, r8d; lpReserved
0x180005313  mov     rdx, rdi; lpValueName
0x180005316  mov     [rsp+48h+phkResult], rax; lpData
0x18000531b  call    cs:__imp_RegQueryValueExW
0x180005321  mov     ebx, eax
0x180005323  jmp     loc_1800051FB
```
