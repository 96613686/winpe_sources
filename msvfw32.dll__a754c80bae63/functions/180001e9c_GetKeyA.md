# GetKeyA

- ea: `0x180001e9c`
- end: `0x180001fd0`
- name: `GetKeyA`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002374`

## callees

- `0x1800014b0`
- `0x180001e9c`
- `0x180002118`
- `0x1800022cc`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegOpenKeyA` at `0x180001f56`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyA` at `0x180001f56`
- `api-ms-win-core-atoms-l1-1-0!AddAtomA` at `0x180001f70`
- `api-ms-win-core-atoms-l1-1-0!AddAtomA` at `0x180001f70`
- `api-ms-win-core-atoms-l1-1-0!FindAtomA` at `0x180001ed3`
- `api-ms-win-core-atoms-l1-1-0!FindAtomA` at `0x180001ed3`

## pseudocode

```c
HKEY __fastcall GetKeyA(__int64 a1, _DWORD *a2)
{
  ATOM AtomA; // dx
  size_t *v4; // r8
  unsigned int i; // ecx
  unsigned int v7; // r10d
  ATOM v8; // ax
  __int64 v9; // rdx
  size_t v10; // [rsp+20h] [rbp-148h]
  HKEY phkResult; // [rsp+30h] [rbp-138h] BYREF
  char pszDest[272]; // [rsp+40h] [rbp-128h] BYREF

  phkResult = 0;
  *a2 = 0;
  AtomA = FindAtomA(szDrawDib);
  if ( AtomA )
  {
    for ( i = 0; i < keyscached; ++i )
    {
      if ( akeyatoms[i] == AtomA )
        return (HKEY)ahkey[i];
    }
  }
  StringCopyWorkerA(pszDest, 0x104u, v4, "Software\\Microsoft\\Multimedia\\", v10);
  if ( StringCchCatA(pszDest, v7, szDrawDib) < 0 )
    return 0;
  if ( !RegOpenKeyA(HKEY_CURRENT_USER, pszDest, &phkResult) )
  {
    if ( (unsigned int)keyscached < 2 && (v8 = AddAtomA(szDrawDib)) != 0 )
    {
      v9 = (unsigned int)keyscached;
      akeyatoms[keyscached] = v8;
      ahkey[v9] = (__int64)phkResult;
      keyscached = v9 + 1;
    }
    else
    {
      *a2 = 1;
    }
  }
  return phkResult;
}

```

## disassembly

```asm
0x180001e9c  mov     [rsp+arg_0], rbx
0x180001ea1  mov     [rsp+arg_10], rsi
0x180001ea6  push    rdi
0x180001ea7  sub     rsp, 160h
0x180001eae  mov     rax, cs:__security_cookie
0x180001eb5  xor     rax, rsp
0x180001eb8  mov     [rsp+168h+var_18], rax
0x180001ec0  xor     edi, edi
0x180001ec2  lea     rcx, szDrawDib; "DrawDib"
0x180001ec9  mov     [rsp+168h+phkResult], rdi
0x180001ece  mov     rbx, rdx
0x180001ed1  mov     [rdx], edi
0x180001ed3  call    cs:__imp_FindAtomA
0x180001ed9  lea     rsi, cs:180000000h
0x180001ee0  movzx   edx, ax
0x180001ee3  test    ax, ax
0x180001ee6  jz      short loc_180001F0F
0x180001ee8  mov     ecx, edi
0x180001eea  cmp     ecx, cs:keyscached
0x180001ef0  jnb     short loc_180001F0F
0x180001ef2  mov     eax, ecx
0x180001ef4  cmp     rva akeyatoms[rsi+rax*2], dx
0x180001efc  jz      short loc_180001F02
0x180001efe  inc     ecx
0x180001f00  jmp     short loc_180001EEA
0x180001f02  mov     rax, rva ahkey[rsi+rax*8]
0x180001f0a  jmp     loc_180001FAB
0x180001f0f  mov     r10d, 104h
0x180001f15  lea     r9, pszSrc; "Software\\Microsoft\\Multimedia\\"
0x180001f1c  mov     edx, r10d; cchDest
0x180001f1f  lea     rcx, [rsp+168h+pszDest]; pszDest
0x180001f24  call    StringCopyWorkerA
0x180001f29  lea     r8, szDrawDib; "DrawDib"
0x180001f30  mov     edx, r10d; cchDest
0x180001f33  lea     rcx, [rsp+168h+pszDest]; pszDest
0x180001f38  call    StringCchCatA
0x180001f3d  test    eax, eax
0x180001f3f  jns     short loc_180001F45
0x180001f41  xor     eax, eax
0x180001f43  jmp     short loc_180001FAB
0x180001f45  lea     r8, [rsp+168h+phkResult]; phkResult
0x180001f4a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180001f51  lea     rdx, [rsp+168h+pszDest]; lpSubKey
0x180001f56  call    cs:__imp_RegOpenKeyA
0x180001f5c  test    eax, eax
0x180001f5e  jnz     short loc_180001FA6
0x180001f60  cmp     cs:keyscached, 2
0x180001f67  jnb     short loc_180001FA0
0x180001f69  lea     rcx, szDrawDib; "DrawDib"
0x180001f70  call    cs:__imp_AddAtomA
0x180001f76  test    ax, ax
0x180001f79  jz      short loc_180001FA0
0x180001f7b  mov     edx, cs:keyscached
0x180001f81  mov     rva akeyatoms[rsi+rdx*2], ax
0x180001f89  mov     rax, [rsp+168h+phkResult]
0x180001f8e  mov     rva ahkey[rsi+rdx*8], rax
0x180001f96  inc     edx
0x180001f98  mov     cs:keyscached, edx
0x180001f9e  jmp     short loc_180001FA6
0x180001fa0  mov     dword ptr [rbx], 1
0x180001fa6  mov     rax, [rsp+168h+phkResult]
0x180001fab  mov     rcx, [rsp+168h+var_18]
0x180001fb3  xor     rcx, rsp; StackCookie
0x180001fb6  call    __security_check_cookie
0x180001fbb  lea     r11, [rsp+168h+var_8]
0x180001fc3  mov     rbx, [r11+10h]
0x180001fc7  mov     rsi, [r11+20h]
0x180001fcb  mov     rsp, r11
0x180001fce  pop     rdi
0x180001fcf  retn
```
