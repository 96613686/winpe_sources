# DhcpRegReadFromAnyLocation

- ea: `0x180004efc`
- end: `0x180005171`
- name: `DhcpRegReadFromAnyLocation`
- size: `629`
- prototype: `__int64(char *Src, void *, BYTE **, DWORD *, ...)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180004ae0`
- `0x180004ce8`

## callees

- `0x180004efc`
- `0x180005330`
- `0x180006440`
- `0x18004d1a0`
- `0x18004d200`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180005020`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180005020`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004fcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004fcb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004fde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004fde`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005056`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005056`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005086`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000515d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005086`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000515d`

## pseudocode

```c
__int64 DhcpRegReadFromAnyLocation(char *Src, void *a2, BYTE **a3, DWORD *a4, ...)
{
  HKEY lpcbData; // r13
  DWORD *v6; // rbx
  BYTE **v7; // r14
  void *v8; // rdi
  unsigned int v9; // esi
  char v10; // al
  __int64 v11; // r15
  unsigned int Value; // ebx
  wchar_t *v13; // rdi
  BYTE *v15; // rax
  HKEY hKey; // [rsp+A0h] [rbp+28h] BYREF
  va_list hKeya; // [rsp+A0h] [rbp+28h]
  va_list va1; // [rsp+A8h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(hKeya, a4);
  hKey = va_arg(va1, HKEY);
  lpcbData = hKey;
  v6 = a4;
  *a4 = 0;
  v7 = a3;
  v8 = a2;
  *a3 = 0;
  *(_DWORD *)lpcbData = 0;
  v9 = 2;
  v10 = xmmword_1800616A0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
  {
    WPP_SF_S(1028, 18, WPP_94d5010c5674399d06148e3a91870046_Traceguids, a2);
    v10 = xmmword_1800616A0;
  }
  while ( 1 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)&Src[2 * v11] );
    if ( !v11 )
      break;
    hKey = 0;
    if ( (v10 & 0x10) != 0 )
      WPP_SF_S(1028, 16, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v8);
    *(_DWORD *)lpcbData = 0;
    *v6 = 0;
    *v7 = 0;
    Value = DhcpRegExpandString(Src, v8);
    if ( !Value )
    {
      v13 = wcsrchr(0, 0x5Cu);
      if ( v13 )
        *v13++ = 0;
      Value = RegOpenKeyExW(HKEY_LOCAL_MACHINE, 0, 0, 0xFu, (PHKEY)hKeya);
      if ( !Value )
      {
        Value = RegQueryValueExW(hKey, v13, 0, a4, 0, (LPDWORD)lpcbData);
        if ( !Value )
        {
          v15 = (BYTE *)DhcpAlloc(*(_DWORD *)lpcbData);
          *a3 = v15;
          if ( v15 )
            Value = RegQueryValueExW(hKey, v13, 0, a4, v15, (LPDWORD)lpcbData);
          else
            Value = 8;
        }
      }
      v8 = a2;
    }
    if ( hKey )
      RegCloseKey(hKey);
    v10 = xmmword_1800616A0;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
    {
      WPP_SF_D(1028, 17, WPP_94d5010c5674399d06148e3a91870046_Traceguids, Value);
      v10 = xmmword_1800616A0;
    }
    if ( !Value )
    {
      v9 = 0;
      break;
    }
    v6 = a4;
    v7 = a3;
    Src += 2 * v11 + 2;
  }
  if ( (v10 & 0x10) != 0 )
    WPP_SF_D(1028, 19, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180004efc  mov     [rsp+lpType], r9
0x180004f01  mov     [rsp+arg_10], r8
0x180004f06  mov     [rsp+arg_8], rdx
0x180004f0b  push    rbx
0x180004f0c  push    rsi
0x180004f0d  push    rdi
0x180004f0e  push    r12
0x180004f10  push    r13
0x180004f12  push    r14
0x180004f14  push    r15
0x180004f16  sub     rsp, 40h
0x180004f1a  mov     r13, [rsp+78h+hKey]
0x180004f22  mov     r12, rcx
0x180004f25  xor     ecx, ecx
0x180004f27  mov     rbx, r9
0x180004f2a  mov     [r9], ecx
0x180004f2d  mov     r14, r8
0x180004f30  mov     rdi, rdx
0x180004f33  mov     [r8], rcx
0x180004f36  mov     [r13+0], ecx
0x180004f3a  mov     esi, 2
0x180004f3f  mov     al, byte ptr cs:xmmword_1800616A0
0x180004f45  test    al, 10h
0x180004f47  jnz     loc_1800050F6
0x180004f4d  or      r15, 0FFFFFFFFFFFFFFFFh
0x180004f51  inc     r15
0x180004f54  cmp     [r12+r15*2], cx
0x180004f59  jnz     short loc_180004F51
0x180004f5b  test    r15, r15
0x180004f5e  jz      loc_1800050C7
0x180004f64  mov     [rsp+78h+lpMem], rcx
0x180004f69  mov     [rsp+78h+hKey], rcx
0x180004f71  test    al, 10h
0x180004f73  jz      short loc_180004F90
0x180004f75  mov     edx, 10h
0x180004f7a  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x180004f81  mov     ecx, 404h
0x180004f86  mov     r9, rdi
0x180004f89  call    WPP_SF_S
0x180004f8e  xor     ecx, ecx
0x180004f90  mov     [r13+0], ecx
0x180004f94  lea     r8, [rsp+78h+lpMem]
0x180004f99  mov     [rbx], ecx
0x180004f9b  mov     rdx, rdi; void *
0x180004f9e  mov     [r14], rcx
0x180004fa1  mov     rcx, r12; Src
0x180004fa4  call    DhcpRegExpandString
0x180004fa9  mov     r14, [rsp+78h+lpMem]
0x180004fae  mov     ebx, eax
0x180004fb0  test    eax, eax
0x180004fb2  jz      short loc_180005018
0x180004fb4  test    r14, r14
0x180004fb7  jz      short loc_180004FD1
0x180004fb9  mov     rcx, gs:60h
0x180004fc2  mov     r8, r14; lpMem
0x180004fc5  xor     edx, edx; dwFlags
0x180004fc7  mov     rcx, [rcx+30h]; hHeap
0x180004fcb  call    cs:__imp_HeapFree
0x180004fd1  mov     rcx, [rsp+78h+hKey]; hKey
0x180004fd9  test    rcx, rcx
0x180004fdc  jz      short loc_180004FE4
0x180004fde  call    cs:__imp_RegCloseKey
0x180004fe4  mov     al, byte ptr cs:xmmword_1800616A0
0x180004fea  test    al, 10h
0x180004fec  jnz     loc_1800050A3
0x180004ff2  xor     ecx, ecx
0x180004ff4  test    ebx, ebx
0x180004ff6  jz      loc_18000516A
0x180004ffc  mov     rbx, [rsp+78h+lpType]
0x180005004  lea     r12, [r12+r15*2]
0x180005008  mov     r14, [rsp+78h+arg_10]
0x180005010  add     r12, rsi
0x180005013  jmp     loc_180004F4D
0x180005018  mov     edx, 5Ch ; '\'; Ch
0x18000501d  mov     rcx, r14; Str
0x180005020  call    cs:__imp_wcsrchr
0x180005026  mov     rdi, rax
0x180005029  test    rax, rax
0x18000502c  jz      short loc_180005036
0x18000502e  xor     eax, eax
0x180005030  mov     [rdi], ax
0x180005033  add     rdi, rsi
0x180005036  lea     rax, [rsp+78h+hKey]
0x18000503e  mov     r9d, 0Fh; samDesired
0x180005044  xor     r8d, r8d; ulOptions
0x180005047  mov     [rsp+78h+phkResult], rax; phkResult
0x18000504c  mov     rdx, r14; lpSubKey
0x18000504f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005056  call    cs:__imp_RegOpenKeyExW
0x18000505c  mov     ebx, eax
0x18000505e  test    eax, eax
0x180005060  jnz     short loc_180005096
0x180005062  mov     r9, [rsp+78h+lpType]; lpType
0x18000506a  xor     r8d, r8d; lpReserved
0x18000506d  mov     rcx, [rsp+78h+hKey]; hKey
0x180005075  mov     rdx, rdi; lpValueName
0x180005078  mov     [rsp+78h+lpcbData], r13; lpcbData
0x18000507d  mov     [rsp+78h+phkResult], 0; lpData
0x180005086  call    cs:__imp_RegQueryValueExW
0x18000508c  mov     ebx, eax
0x18000508e  test    eax, eax
0x180005090  jz      loc_18000511C
0x180005096  mov     rdi, [rsp+78h+arg_8]
0x18000509e  jmp     loc_180004FB4
0x1800050a3  mov     edx, 11h
0x1800050a8  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x1800050af  mov     ecx, 404h
0x1800050b4  mov     r9d, ebx
0x1800050b7  call    WPP_SF_D
0x1800050bc  mov     al, byte ptr cs:xmmword_1800616A0
0x1800050c2  jmp     loc_180004FF2
0x1800050c7  test    al, 10h
0x1800050c9  jz      short loc_1800050E4
0x1800050cb  mov     edx, 13h
0x1800050d0  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x1800050d7  mov     ecx, 404h
0x1800050dc  mov     r9d, esi
0x1800050df  call    WPP_SF_D
0x1800050e4  mov     eax, esi
0x1800050e6  add     rsp, 40h
0x1800050ea  pop     r15
0x1800050ec  pop     r14
0x1800050ee  pop     r13
0x1800050f0  pop     r12
0x1800050f2  pop     rdi
0x1800050f3  pop     rsi
0x1800050f4  pop     rbx
0x1800050f5  retn
0x1800050f6  mov     edx, 12h
0x1800050fb  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x180005102  mov     ecx, 404h
0x180005107  mov     r9, rdi
0x18000510a  call    WPP_SF_S
0x18000510f  mov     al, byte ptr cs:xmmword_1800616A0
0x180005115  xor     ecx, ecx
0x180005117  jmp     loc_180004F4D
0x18000511c  mov     ecx, [r13+0]
0x180005120  call    DhcpAlloc
0x180005125  mov     rcx, [rsp+78h+arg_10]
0x18000512d  mov     [rcx], rax
0x180005130  test    rax, rax
0x180005133  jnz     short loc_18000513D
0x180005135  lea     ebx, [rax+8]
0x180005138  jmp     loc_180005096
0x18000513d  mov     r9, [rsp+78h+lpType]; lpType
0x180005145  xor     r8d, r8d; lpReserved
0x180005148  mov     rcx, [rsp+78h+hKey]; hKey
0x180005150  mov     rdx, rdi; lpValueName
0x180005153  mov     [rsp+78h+lpcbData], r13; lpcbData
0x180005158  mov     [rsp+78h+phkResult], rax; lpData
0x18000515d  call    cs:__imp_RegQueryValueExW
0x180005163  mov     ebx, eax
0x180005165  jmp     loc_180005096
0x18000516a  mov     esi, ecx
0x18000516c  jmp     loc_1800050C7
```
