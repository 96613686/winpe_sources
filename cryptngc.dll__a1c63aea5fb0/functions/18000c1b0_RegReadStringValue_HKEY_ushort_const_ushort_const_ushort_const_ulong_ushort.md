# RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)

- ea: `0x18000c1b0`
- end: `0x18000c3e1`
- name: `?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z`
- size: `561`
- prototype: `unsigned int __fastcall(HKEY hkey, LPCWSTR lpSubKey, const unsigned __int16 *, const unsigned __int16 *, SIZE_T dwBytes, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000d2f0`
- `0x180044480`

## callees

- `0x18000c190`
- `0x18000c1b0`
- `0x18000ced0`
- `0x180027448`
- `0x18002bc58`
- `0x18002c23c`
- `0x180044a9c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c23a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c23a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c24b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c24b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c209`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c284`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c209`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c284`

## string_xrefs

- `0x18000c2a8`: `RegReadStringValue`
- `0x18000c2e9`: `RegReadStringValue`
- `0x18000c337`: `RegReadStringValue`
- `0x18000c378`: `RegReadStringValue`
- `0x18000c39a`: `RegReadStringValue`
- `0x18000c2f0`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x18000c33e`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x18000c37f`: `%s: The registry key value "%s@%s" is not of one of the specified types (flags = 0x%08x). Using default value NULL.`

## pseudocode

```c
__int64 __fastcall RegReadStringValue(
        HKEY hkey,
        LPCWSTR lpSubKey,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        SIZE_T dwBytes,
        unsigned __int16 **a6)
{
  void **v6; // rdi
  LSTATUS ValueW; // eax
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  HANDLE ProcessHeap; // rax
  void *pvData; // rax
  int v18; // eax
  const wchar_t *v19; // r9
  BOOL v20; // eax
  const wchar_t *v21; // r9
  BOOL v22; // eax
  const wchar_t *v23; // r9
  LPDWORD pdwType; // [rsp+20h] [rbp-68h]
  DWORD v25[18]; // [rsp+40h] [rbp-48h] BYREF

  v6 = (void **)a6;
  v25[0] = 0;
  LODWORD(dwBytes) = 0;
  if ( a6 )
  {
    *a6 = 0;
    ValueW = RegGetValueW(hkey, lpSubKey, a3, 2u, v25, 0, (LPDWORD)&dwBytes);
    v13 = ValueW;
    if ( ValueW == 2 )
    {
      v20 = !a3 || !*a3;
      LODWORD(pdwType) = 2;
      v21 = L"(default)";
      if ( !v20 )
        v21 = a3;
      Logger::TraceWarning(
        L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.",
        L"RegReadStringValue",
        a4,
        v21,
        pdwType);
      return 0;
    }
    if ( ValueW == 1630 )
    {
      v22 = !a3 || !*a3;
      LODWORD(pdwType) = 2;
      v23 = L"(default)";
      if ( !v22 )
        v23 = a3;
      Logger::TraceWarning(
        L"%s: The registry key value \"%s@%s\" is not of one of the specified types (flags = 0x%08x). Using default value NULL.",
        L"RegReadStringValue",
        a4,
        v23,
        pdwType);
      return 0;
    }
    if ( ValueW && ValueW != 234 )
      goto LABEL_11;
    if ( (_DWORD)dwBytes )
    {
      v14 = dwBytes;
      ProcessHeap = GetProcessHeap();
      pvData = HeapAlloc(ProcessHeap, 8u, v14);
      *v6 = pvData;
      if ( !pvData )
      {
        v13 = 14;
        Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadStringValue");
        goto LABEL_11;
      }
      v13 = RegGetValueW(hkey, lpSubKey, a3, 2u, v25, pvData, (LPDWORD)&dwBytes);
    }
    if ( !v13 )
      return v13;
LABEL_11:
    Logger::WriteRegistryFailureEvent(v13, v12, a4, a3);
    v18 = IsEmptyString(a3);
    LODWORD(pdwType) = v13;
    v19 = L"(default)";
    if ( !v18 )
      v19 = a3;
    Logger::TraceWarning(
      L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
      L"RegReadStringValue",
      a4,
      v19,
      pdwType);
    SafeFree(*v6);
    *v6 = 0;
    return v13;
  }
  Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegReadStringValue", L"pData");
  return 87;
}

```

## disassembly

```asm
0x18000c1b0  mov     r11, rsp
0x18000c1b3  push    rbp
0x18000c1b4  push    rsi
0x18000c1b5  push    rdi
0x18000c1b6  push    r12
0x18000c1b8  push    r14
0x18000c1ba  push    r15
0x18000c1bc  sub     rsp, 58h
0x18000c1c0  mov     rdi, [rsp+88h+arg_28]
0x18000c1c8  xor     r12d, r12d
0x18000c1cb  mov     [r11-48h], r12d
0x18000c1cf  mov     r15, r9
0x18000c1d2  mov     [r11+28h], r12d
0x18000c1d6  mov     rsi, r8
0x18000c1d9  mov     rbp, rdx
0x18000c1dc  mov     r14, rcx
0x18000c1df  test    rdi, rdi
0x18000c1e2  jz      loc_18000C393
0x18000c1e8  lea     rax, [r11+28h]
0x18000c1ec  mov     [r11+8], rbx
0x18000c1f0  mov     [r11-58h], rax
0x18000c1f4  mov     r9d, 2; dwFlags
0x18000c1fa  lea     rax, [r11-48h]
0x18000c1fe  mov     [r11-60h], r12
0x18000c202  mov     [r11-68h], rax
0x18000c206  mov     [rdi], r12
0x18000c209  call    cs:__imp_RegGetValueW
0x18000c20f  mov     ebx, eax
0x18000c211  cmp     eax, 2
0x18000c214  jz      loc_18000C309
0x18000c21a  cmp     eax, 65Eh
0x18000c21f  jz      loc_18000C352
0x18000c225  test    eax, eax
0x18000c227  jnz     loc_18000C3D1
0x18000c22d  mov     eax, dword ptr [rsp+88h+dwBytes]
0x18000c234  test    eax, eax
0x18000c236  jz      short loc_18000C28C
0x18000c238  mov     ebx, eax
0x18000c23a  call    cs:__imp_GetProcessHeap
0x18000c240  mov     r8d, ebx; dwBytes
0x18000c243  mov     edx, 8; dwFlags
0x18000c248  mov     rcx, rax; hHeap
0x18000c24b  call    cs:__imp_HeapAlloc
0x18000c251  mov     [rdi], rax
0x18000c254  test    rax, rax
0x18000c257  jz      short loc_18000C2A8
0x18000c259  lea     rcx, [rsp+88h+dwBytes]
0x18000c261  mov     r9d, 2; dwFlags
0x18000c267  mov     [rsp+88h+pcbData], rcx; pcbData
0x18000c26c  mov     r8, rsi; lpValue
0x18000c26f  mov     [rsp+88h+pvData], rax; pvData
0x18000c274  mov     rdx, rbp; lpSubKey
0x18000c277  lea     rax, [rsp+88h+var_48]
0x18000c27c  mov     rcx, r14; hkey
0x18000c27f  mov     [rsp+88h+pdwType], rax; pdwType
0x18000c284  call    cs:__imp_RegGetValueW
0x18000c28a  mov     ebx, eax
0x18000c28c  test    ebx, ebx
0x18000c28e  jnz     short loc_18000C2C0
0x18000c290  mov     eax, ebx
0x18000c292  mov     rbx, [rsp+88h+arg_0]
0x18000c29a  add     rsp, 58h
0x18000c29e  pop     r15
0x18000c2a0  pop     r14
0x18000c2a2  pop     r12
0x18000c2a4  pop     rdi
0x18000c2a5  pop     rsi
0x18000c2a6  pop     rbp
0x18000c2a7  retn
0x18000c2a8  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18000c2af  mov     ebx, 0Eh
0x18000c2b4  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18000c2bb  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18000c2c0  mov     r9, rsi; unsigned __int16 *
0x18000c2c3  mov     r8, r15; unsigned __int16 *
0x18000c2c6  mov     ecx, ebx; unsigned int
0x18000c2c8  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x18000c2cd  mov     rcx, rsi; unsigned __int16 *
0x18000c2d0  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18000c2d5  test    eax, eax
0x18000c2d7  mov     dword ptr [rsp+88h+pdwType], ebx
0x18000c2db  lea     r9, aDefault; "(default)"
0x18000c2e2  mov     r8, r15
0x18000c2e5  cmovz   r9, rsi
0x18000c2e9  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18000c2f0  lea     rcx, aSCannotReadReg; "%s: Cannot read registry key value \"%s"...
0x18000c2f7  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18000c2fc  mov     rcx, [rdi]; lpMem
0x18000c2ff  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000c304  mov     [rdi], r12
0x18000c307  jmp     short loc_18000C290
0x18000c309  test    rsi, rsi
0x18000c30c  jz      loc_18000C3C0
0x18000c312  cmp     [rsi], r12w
0x18000c316  jz      loc_18000C3C0
0x18000c31c  mov     eax, r12d
0x18000c31f  test    eax, eax
0x18000c321  mov     dword ptr [rsp+88h+pdwType], 2
0x18000c329  lea     r9, aDefault; "(default)"
0x18000c330  mov     r8, r15
0x18000c333  cmovz   r9, rsi
0x18000c337  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18000c33e  lea     rcx, aSTheRegistryKe; "%s: The registry key value \"%s@%s\" do"...
0x18000c345  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18000c34a  mov     ebx, r12d
0x18000c34d  jmp     loc_18000C290
0x18000c352  test    rsi, rsi
0x18000c355  jz      short loc_18000C3CA
0x18000c357  cmp     [rsi], r12w
0x18000c35b  jz      short loc_18000C3CA
0x18000c35d  mov     eax, r12d
0x18000c360  test    eax, eax
0x18000c362  mov     dword ptr [rsp+88h+pdwType], 2
0x18000c36a  lea     r9, aDefault; "(default)"
0x18000c371  mov     r8, r15
0x18000c374  cmovz   r9, rsi
0x18000c378  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18000c37f  lea     rcx, aSTheRegistryKe_4; "%s: The registry key value \"%s@%s\" is"...
0x18000c386  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18000c38b  mov     ebx, r12d
0x18000c38e  jmp     loc_18000C290
0x18000c393  lea     r8, aPdata; "pData"
0x18000c39a  lea     rdx, aRegreadstringv; "RegReadStringValue"
0x18000c3a1  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18000c3a8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000c3ad  mov     eax, 57h ; 'W'
0x18000c3b2  add     rsp, 58h
0x18000c3b6  pop     r15
0x18000c3b8  pop     r14
0x18000c3ba  pop     r12
0x18000c3bc  pop     rdi
0x18000c3bd  pop     rsi
0x18000c3be  pop     rbp
0x18000c3bf  retn
0x18000c3c0  mov     eax, 1
0x18000c3c5  jmp     loc_18000C31F
0x18000c3ca  mov     eax, 1
0x18000c3cf  jmp     short loc_18000C360
0x18000c3d1  cmp     eax, 0EAh
0x18000c3d6  jnz     loc_18000C2C0
0x18000c3dc  jmp     loc_18000C22D
```
