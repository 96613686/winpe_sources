# _RegQueryValueBuffer<std::vector<uchar,std::allocator<uchar>>>(HKEY__ *,char const *,char const *,uint,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x1800a53c8`
- end: `0x1800a5551`
- name: `??$_RegQueryValueBuffer@V?$vector@EV?$allocator@E@std@@@std@@@@YAJPEAUHKEY__@@PEBD1IAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800a1360`

## callees

- `0x180008b1c`
- `0x1800552c8`
- `0x1800a53c8`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a5439`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a549c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a550f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a5523`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a5439`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a549c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a550f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a5523`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800a5417`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800a5417`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800a547a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800a54e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800a547a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800a54e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall _RegQueryValueBuffer<std::vector<unsigned char>>(
        HKEY a1,
        __int64 a2,
        const CHAR *a3,
        __int64 a4,
        __int64 a5)
{
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  LSTATUS ValueA; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  unsigned int v12; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-48h]
  DWORD pcbData; // [rsp+40h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( *(_QWORD *)a5 != *(_QWORD *)(a5 + 8) )
    *(_QWORD *)(a5 + 8) = *(_QWORD *)a5;
  hKey = 0;
  v6 = RegOpenKeyExA(a1, 0, 0, 0x20019u, &hKey);
  if ( v6 )
  {
    v7 = (unsigned __int16)v6 | 0x80070000;
    if ( v6 <= 0 )
      v7 = v6;
    if ( hKey )
      RegCloseKey(hKey);
    return v7;
  }
  else
  {
    pcbData = 0;
    ValueA = RegGetValueA(hKey, 0, a3, 8u, 0, 0, &pcbData);
    if ( ValueA )
    {
      v10 = (unsigned __int16)ValueA | 0x80070000;
      if ( ValueA <= 0 )
        v10 = ValueA;
      if ( hKey )
        RegCloseKey(hKey);
      return v10;
    }
    else
    {
      std::vector<unsigned char>::resize(a5, pcbData);
      v11 = RegGetValueA(hKey, 0, a3, 8u, 0, *(PVOID *)a5, &pcbData);
      if ( v11 )
      {
        v12 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x16,
                (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\RegUtil.cpp",
                (const char *)v11,
                phkResult);
        if ( hKey )
          RegCloseKey(hKey);
        return v12;
      }
      else
      {
        if ( hKey )
          RegCloseKey(hKey);
        return 0;
      }
    }
  }
}

```

## disassembly

```asm
0x1800a53c8  mov     [rsp+arg_8], rbx
0x1800a53cd  push    rdi
0x1800a53ce  sub     rsp, 60h
0x1800a53d2  mov     rax, cs:__security_cookie
0x1800a53d9  xor     rax, rsp
0x1800a53dc  mov     [rsp+68h+var_18], rax
0x1800a53e1  mov     rdi, r8
0x1800a53e4  mov     rbx, [rsp+68h+arg_20]
0x1800a53ec  mov     rax, [rbx]
0x1800a53ef  cmp     rax, [rbx+8]
0x1800a53f3  jz      short loc_1800A53F9
0x1800a53f5  mov     [rbx+8], rax
0x1800a53f9  mov     [rsp+68h+hKey], 0
0x1800a5402  lea     rax, [rsp+68h+hKey]
0x1800a5407  mov     [rsp+68h+phkResult], rax; phkResult
0x1800a540c  mov     r9d, 20019h; samDesired
0x1800a5412  xor     r8d, r8d; ulOptions
0x1800a5415  xor     edx, edx; lpSubKey
0x1800a5417  call    cs:__imp_RegOpenKeyExA
0x1800a541d  test    eax, eax
0x1800a541f  jz      short loc_1800A5446
0x1800a5421  movzx   ebx, ax
0x1800a5424  or      ebx, 80070000h
0x1800a542a  test    eax, eax
0x1800a542c  cmovle  ebx, eax
0x1800a542f  mov     rcx, [rsp+68h+hKey]; hKey
0x1800a5434  test    rcx, rcx
0x1800a5437  jz      short loc_1800A543F
0x1800a5439  call    cs:__imp_RegCloseKey
0x1800a543f  mov     eax, ebx
0x1800a5441  jmp     loc_1800A5538
0x1800a5446  mov     [rsp+68h+var_28], 0
0x1800a544e  lea     rax, [rsp+68h+var_28]
0x1800a5453  mov     [rsp+68h+pcbData], rax; pcbData
0x1800a5458  mov     [rsp+68h+pvData], 0; pvData
0x1800a5461  mov     [rsp+68h+phkResult], 0; pdwType
0x1800a546a  mov     r9d, 8; dwFlags
0x1800a5470  mov     r8, rdi; lpValue
0x1800a5473  xor     edx, edx; lpSubKey
0x1800a5475  mov     rcx, [rsp+68h+hKey]; hkey
0x1800a547a  call    cs:__imp_RegGetValueA
0x1800a5480  test    eax, eax
0x1800a5482  jz      short loc_1800A54A9
0x1800a5484  movzx   ebx, ax
0x1800a5487  or      ebx, 80070000h
0x1800a548d  test    eax, eax
0x1800a548f  cmovle  ebx, eax
0x1800a5492  mov     rcx, [rsp+68h+hKey]; hKey
0x1800a5497  test    rcx, rcx
0x1800a549a  jz      short loc_1800A54A2
0x1800a549c  call    cs:__imp_RegCloseKey
0x1800a54a2  mov     eax, ebx
0x1800a54a4  jmp     loc_1800A5538
0x1800a54a9  mov     edx, [rsp+68h+var_28]
0x1800a54ad  mov     rcx, rbx
0x1800a54b0  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800a54b5  lea     rax, [rsp+68h+var_28]
0x1800a54ba  mov     [rsp+68h+pcbData], rax; pcbData
0x1800a54bf  mov     rax, [rbx]
0x1800a54c2  mov     [rsp+68h+pvData], rax; pvData
0x1800a54c7  mov     [rsp+68h+phkResult], 0; unsigned int
0x1800a54d0  mov     r9d, 8; dwFlags
0x1800a54d6  mov     r8, rdi; lpValue
0x1800a54d9  xor     edx, edx; lpSubKey
0x1800a54db  mov     rcx, [rsp+68h+hKey]; hkey
0x1800a54e0  call    cs:__imp_RegGetValueA
0x1800a54e6  test    eax, eax
0x1800a54e8  jz      short loc_1800A5519
0x1800a54ea  mov     rcx, [rsp+68h]; this
0x1800a54ef  mov     r9d, eax; char *
0x1800a54f2  lea     r8, aCW1SSrcDeliver_92; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800a54f9  mov     edx, 16h; void *
0x1800a54fe  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a5503  mov     ebx, eax
0x1800a5505  mov     rcx, [rsp+68h+hKey]; hKey
0x1800a550a  test    rcx, rcx
0x1800a550d  jz      short loc_1800A5515
0x1800a550f  call    cs:__imp_RegCloseKey
0x1800a5515  mov     eax, ebx
0x1800a5517  jmp     short loc_1800A5538
0x1800a5519  mov     rcx, [rsp+68h+hKey]; hKey
0x1800a551e  test    rcx, rcx
0x1800a5521  jz      short loc_1800A5529
0x1800a5523  call    cs:__imp_RegCloseKey
0x1800a5529  xor     eax, eax
0x1800a552b  jmp     short loc_1800A5538
0x1800a552d  mov     eax, 8007000Eh
0x1800a5532  jmp     short loc_1800A5538
0x1800a5534  mov     eax, [rsp+68h+var_28]
0x1800a5538  mov     rcx, [rsp+68h+var_18]
0x1800a553d  xor     rcx, rsp; StackCookie
0x1800a5540  call    __security_check_cookie
0x1800a5545  mov     rbx, [rsp+68h+arg_8]
0x1800a554a  add     rsp, 60h
0x1800a554e  pop     rdi
0x1800a554f  retn
```
