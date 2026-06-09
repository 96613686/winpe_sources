# ScPolicyStoreLogonReaderInfo

- ea: `0x180002114`
- end: `0x180002240`
- name: `ScPolicyStoreLogonReaderInfo`
- size: `300`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001ee0`

## callees

- `0x180002114`
- `0x1800070ec`
- `0x18000b0c2`
- `0x18000b100`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800021c2`
- `KERNEL32!LocalAlloc` at `0x1800021c2`
- `KERNEL32!LocalFree` at `0x18000220e`
- `KERNEL32!LocalFree` at `0x18000220e`
- `KERNEL32!RegCloseKey` at `0x18000221e`
- `KERNEL32!RegCloseKey` at `0x18000221e`
- `KERNEL32!RegSetValueExA` at `0x180002203`
- `KERNEL32!RegSetValueExA` at `0x180002203`
- `KERNEL32!RegCreateKeyExA` at `0x18000217b`
- `KERNEL32!RegCreateKeyExA` at `0x18000217b`

## pseudocode

```c
__int64 __fastcall ScPolicyStoreLogonReaderInfo(__int64 a1, __int64 a2, int a3, int a4, _WORD *Src)
{
  unsigned int v7; // ebx
  __int64 v8; // rax
  size_t v9; // rbx
  DWORD v10; // esi
  BYTE *v11; // rax
  BYTE *v12; // rdi
  HKEY hKey; // [rsp+50h] [rbp-58h] BYREF
  char pszDest[16]; // [rsp+58h] [rbp-50h] BYREF

  hKey = 0;
  v7 = RegCreateKeyExA(
         HKEY_LOCAL_MACHINE,
         "Software\\Microsoft\\Windows NT\\CurrentVersion\\Removal Policy",
         0,
         0,
         1u,
         2u,
         0,
         &hKey,
         0);
  if ( !v7 )
  {
    StringCbPrintfA(pszDest, 9u, "%x", a3);
    v8 = -1;
    do
      ++v8;
    while ( Src[v8] );
    v9 = (unsigned int)(2 * v8 + 2);
    v10 = 2 * v8 + 6;
    v11 = (BYTE *)LocalAlloc(0x40u, v10);
    v12 = v11;
    if ( v11 )
    {
      memcpy_0(v11, Src, v9);
      *(_DWORD *)&v12[v9] = a4;
      v7 = RegSetValueExA(hKey, pszDest, 0, 3u, v12, v10);
      LocalFree(v12);
    }
    else
    {
      v7 = 8;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180002114  mov     r11, rsp
0x180002117  push    rbx
0x180002118  push    rbp
0x180002119  push    rsi
0x18000211a  push    rdi
0x18000211b  push    r14
0x18000211d  push    r15
0x18000211f  sub     rsp, 78h
0x180002123  mov     rax, cs:__security_cookie
0x18000212a  xor     rax, rsp
0x18000212d  mov     [rsp+0A8h+var_40], rax
0x180002132  mov     rbp, [rsp+0A8h+Src]
0x18000213a  lea     rax, [r11-58h]
0x18000213e  xor     r15d, r15d
0x180002141  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x180002148  mov     [r11-68h], r15
0x18000214c  mov     r14d, r9d
0x18000214f  mov     [r11-70h], rax
0x180002153  mov     edi, r8d
0x180002156  mov     [r11-78h], r15
0x18000215a  xor     r9d, r9d; lpClass
0x18000215d  mov     [rsp+0A8h+samDesired], 2; samDesired
0x180002165  xor     r8d, r8d; Reserved
0x180002168  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000216f  mov     [rsp+0A8h+dwOptions], 1; dwOptions
0x180002177  mov     [r11-58h], r15
0x18000217b  call    cs:__imp_RegCreateKeyExA
0x180002181  mov     ebx, eax
0x180002183  test    eax, eax
0x180002185  jnz     loc_180002214
0x18000218b  mov     r9d, edi
0x18000218e  lea     r8, pszFormat; "%x"
0x180002195  lea     edx, [rax+9]; cbDest
0x180002198  lea     rcx, [rsp+0A8h+pszDest]; pszDest
0x18000219d  call    StringCbPrintfA
0x1800021a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800021a6  inc     rax
0x1800021a9  cmp     [rbp+rax*2+0], r15w
0x1800021af  jnz     short loc_1800021A6
0x1800021b1  lea     ebx, ds:2[rax*2]
0x1800021b8  mov     ecx, 40h ; '@'; uFlags
0x1800021bd  lea     esi, [rbx+4]
0x1800021c0  mov     edx, esi; uBytes
0x1800021c2  call    cs:__imp_LocalAlloc
0x1800021c8  mov     rdi, rax
0x1800021cb  test    rax, rax
0x1800021ce  jnz     short loc_1800021D5
0x1800021d0  lea     ebx, [rax+8]
0x1800021d3  jmp     short loc_180002214
0x1800021d5  mov     r8, rbx; Size
0x1800021d8  mov     rdx, rbp; Src
0x1800021db  mov     rcx, rdi; void *
0x1800021de  call    memcpy_0
0x1800021e3  mov     [rbx+rdi], r14d
0x1800021e7  lea     rdx, [rsp+0A8h+pszDest]; lpValueName
0x1800021ec  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1800021f1  mov     r9d, 3; dwType
0x1800021f7  xor     r8d, r8d; Reserved
0x1800021fa  mov     [rsp+0A8h+samDesired], esi; cbData
0x1800021fe  mov     qword ptr [rsp+0A8h+dwOptions], rdi; lpData
0x180002203  call    cs:__imp_RegSetValueExA
0x180002209  mov     ebx, eax
0x18000220b  mov     rcx, rdi; hMem
0x18000220e  call    cs:__imp_LocalFree
0x180002214  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180002219  test    rcx, rcx
0x18000221c  jz      short loc_180002224
0x18000221e  call    cs:__imp_RegCloseKey
0x180002224  mov     eax, ebx
0x180002226  mov     rcx, [rsp+0A8h+var_40]
0x18000222b  xor     rcx, rsp; StackCookie
0x18000222e  call    __security_check_cookie
0x180002233  add     rsp, 78h
0x180002237  pop     r15
0x180002239  pop     r14
0x18000223b  pop     rdi
0x18000223c  pop     rsi
0x18000223d  pop     rbp
0x18000223e  pop     rbx
0x18000223f  retn
```
