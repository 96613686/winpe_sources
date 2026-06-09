# CCspSimpleRegHelper::GetBinaryRegValue(HKEY__ *,ushort const *,ushort const *,tagVARIANT *)

- ea: `0x1800fd250`
- end: `0x1800fd430`
- name: `?GetBinaryRegValue@CCspSimpleRegHelper@@CAJPEAUHKEY__@@PEBG1PEAUtagVARIANT@@@Z`
- size: `480`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800fd680`

## callees

- `0x180009cac`
- `0x1800fd250`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800fd36c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800fd36c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800fd3ff`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800fd3ff`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800fd387`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800fd387`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800fd3ac`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800fd3f0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800fd3ac`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800fd3f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fd414`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fd414`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fd2e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fd343`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fd2e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800fd343`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fd296`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fd296`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fd3d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fd3d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800fd309`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800fd309`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCspSimpleRegHelper::GetBinaryRegValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct tagVARIANT *a4)
{
  BYTE *v4; // rsi
  SAFEARRAY *v7; // rdi
  LSTATUS v8; // eax
  int v9; // ebx
  bool v10; // cc
  SAFEARRAY *v11; // rax
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  DWORD Type; // [rsp+34h] [rbp-24h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp-20h] BYREF
  void *ppvData; // [rsp+40h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-10h] BYREF

  v4 = 0;
  hKey = 0;
  cbData = 0;
  Type = 0;
  rgsabound = 0;
  ppvData = 0;
  v7 = 0;
  v8 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  v9 = v8;
  if ( v8 == 2 )
    goto LABEL_2;
  v10 = v8 <= 0;
  if ( v8 )
    goto LABEL_4;
  v8 = RegQueryValueExW(hKey, a3, 0, &Type, 0, &cbData);
  v9 = v8;
  if ( v8 == 2 )
    goto LABEL_2;
  v10 = v8 <= 0;
  if ( v8 )
    goto LABEL_4;
  if ( Type != 3 )
  {
LABEL_2:
    v9 = -2046820350;
    goto LABEL_16;
  }
  v4 = (BYTE *)LocalAlloc(0, cbData);
  if ( !v4 )
  {
LABEL_10:
    v9 = -2147024882;
    goto LABEL_16;
  }
  v8 = RegQueryValueExW(hKey, a3, 0, &Type, v4, &cbData);
  v9 = v8;
  v10 = v8 <= 0;
  if ( v8 )
  {
LABEL_4:
    if ( !v10 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_16;
  }
  rgsabound.cElements = cbData;
  rgsabound.lLbound = 0;
  v11 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v7 = v11;
  if ( !v11 )
    goto LABEL_10;
  v9 = SafeArrayAccessData(v11, &ppvData);
  if ( v9 >= 0 )
  {
    memcpy_0(ppvData, v4, cbData);
    v9 = SafeArrayUnaccessData(v7);
    if ( v9 >= 0 )
    {
      a4->llVal = (LONGLONG)v7;
      v7 = 0;
      ppvData = 0;
      a4->vt = 8209;
    }
  }
LABEL_16:
  LocalFree(v4);
  if ( v7 )
  {
    if ( ppvData )
      SafeArrayUnaccessData(v7);
    SafeArrayDestroy(v7);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800fd250  push    rbp
0x1800fd252  push    rbx
0x1800fd253  push    rsi
0x1800fd254  push    rdi
0x1800fd255  push    r14
0x1800fd257  push    r15
0x1800fd259  mov     rbp, rsp
0x1800fd25c  sub     rsp, 58h
0x1800fd260  xor     esi, esi
0x1800fd262  mov     [rbp+hKey], 0
0x1800fd26a  mov     r14, r9
0x1800fd26d  mov     [rbp+cbData], esi
0x1800fd270  mov     r15, r8
0x1800fd273  mov     [rbp+Type], esi
0x1800fd276  lea     rax, [rbp+hKey]
0x1800fd27a  mov     qword ptr [rbp+rgsabound.cElements], rsi
0x1800fd27e  mov     r9d, 20019h; samDesired
0x1800fd284  mov     [rsp+58h+phkResult], rax; phkResult
0x1800fd289  xor     r8d, r8d; ulOptions
0x1800fd28c  mov     [rbp+ppvData], 0
0x1800fd294  xor     edi, edi
0x1800fd296  call    cs:__imp_RegOpenKeyExW
0x1800fd29d  nop     dword ptr [rax+rax+00h]
0x1800fd2a2  mov     ebx, eax
0x1800fd2a4  cmp     eax, 2
0x1800fd2a7  jnz     short loc_1800FD2B3
0x1800fd2a9  mov     ebx, 86000002h
0x1800fd2ae  jmp     loc_1800FD3D2
0x1800fd2b3  test    eax, eax
0x1800fd2b5  jz      short loc_1800FD2CB
0x1800fd2b7  jle     loc_1800FD3D2
0x1800fd2bd  movzx   ebx, ax
0x1800fd2c0  or      ebx, 80070000h
0x1800fd2c6  jmp     loc_1800FD3D2
0x1800fd2cb  mov     rcx, [rbp+hKey]; hKey
0x1800fd2cf  lea     rax, [rbp+cbData]
0x1800fd2d3  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800fd2d8  lea     r9, [rbp+Type]; lpType
0x1800fd2dc  xor     r8d, r8d; lpReserved
0x1800fd2df  mov     [rsp+58h+phkResult], rsi; lpData
0x1800fd2e4  mov     rdx, r15; lpValueName
0x1800fd2e7  call    cs:__imp_RegQueryValueExW
0x1800fd2ee  nop     dword ptr [rax+rax+00h]
0x1800fd2f3  mov     ebx, eax
0x1800fd2f5  cmp     eax, 2
0x1800fd2f8  jz      short loc_1800FD2A9
0x1800fd2fa  test    eax, eax
0x1800fd2fc  jnz     short loc_1800FD2B7
0x1800fd2fe  cmp     [rbp+Type], 3
0x1800fd302  jnz     short loc_1800FD2A9
0x1800fd304  mov     edx, [rbp+cbData]; uBytes
0x1800fd307  xor     ecx, ecx; uFlags
0x1800fd309  call    cs:__imp_LocalAlloc
0x1800fd310  nop     dword ptr [rax+rax+00h]
0x1800fd315  mov     rsi, rax
0x1800fd318  test    rax, rax
0x1800fd31b  jnz     short loc_1800FD327
0x1800fd31d  mov     ebx, 8007000Eh
0x1800fd322  jmp     loc_1800FD3D2
0x1800fd327  mov     rcx, [rbp+hKey]; hKey
0x1800fd32b  lea     rax, [rbp+cbData]
0x1800fd32f  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800fd334  lea     r9, [rbp+Type]; lpType
0x1800fd338  xor     r8d, r8d; lpReserved
0x1800fd33b  mov     [rsp+58h+phkResult], rsi; lpData
0x1800fd340  mov     rdx, r15; lpValueName
0x1800fd343  call    cs:__imp_RegQueryValueExW
0x1800fd34a  nop     dword ptr [rax+rax+00h]
0x1800fd34f  mov     ebx, eax
0x1800fd351  test    eax, eax
0x1800fd353  jnz     loc_1800FD2B7
0x1800fd359  mov     eax, [rbp+cbData]
0x1800fd35c  lea     ecx, [rbx+11h]; vt
0x1800fd35f  lea     r8, [rbp+rgsabound]; rgsabound
0x1800fd363  mov     [rbp+rgsabound.cElements], eax
0x1800fd366  lea     edx, [rbx+1]; cDims
0x1800fd369  mov     [rbp+rgsabound.lLbound], edi
0x1800fd36c  call    cs:__imp_SafeArrayCreate
0x1800fd373  nop     dword ptr [rax+rax+00h]
0x1800fd378  mov     rdi, rax
0x1800fd37b  test    rax, rax
0x1800fd37e  jz      short loc_1800FD31D
0x1800fd380  lea     rdx, [rbp+ppvData]; ppvData
0x1800fd384  mov     rcx, rax; psa
0x1800fd387  call    cs:__imp_SafeArrayAccessData
0x1800fd38e  nop     dword ptr [rax+rax+00h]
0x1800fd393  mov     ebx, eax
0x1800fd395  test    eax, eax
0x1800fd397  js      short loc_1800FD3D2
0x1800fd399  mov     r8d, [rbp+cbData]; Size
0x1800fd39d  mov     rdx, rsi; Src
0x1800fd3a0  mov     rcx, [rbp+ppvData]; void *
0x1800fd3a4  call    memcpy_0
0x1800fd3a9  mov     rcx, rdi; psa
0x1800fd3ac  call    cs:__imp_SafeArrayUnaccessData
0x1800fd3b3  nop     dword ptr [rax+rax+00h]
0x1800fd3b8  mov     ebx, eax
0x1800fd3ba  test    eax, eax
0x1800fd3bc  js      short loc_1800FD3D2
0x1800fd3be  mov     [r14+8], rdi
0x1800fd3c2  xor     edi, edi
0x1800fd3c4  mov     [rbp+ppvData], 0
0x1800fd3cc  mov     word ptr [r14], 2011h
0x1800fd3d2  mov     rcx, rsi; hMem
0x1800fd3d5  call    cs:__imp_LocalFree
0x1800fd3dc  nop     dword ptr [rax+rax+00h]
0x1800fd3e1  test    rdi, rdi
0x1800fd3e4  jz      short loc_1800FD40B
0x1800fd3e6  cmp     [rbp+ppvData], 0
0x1800fd3eb  jz      short loc_1800FD3FC
0x1800fd3ed  mov     rcx, rdi; psa
0x1800fd3f0  call    cs:__imp_SafeArrayUnaccessData
0x1800fd3f7  nop     dword ptr [rax+rax+00h]
0x1800fd3fc  mov     rcx, rdi; psa
0x1800fd3ff  call    cs:__imp_SafeArrayDestroy
0x1800fd406  nop     dword ptr [rax+rax+00h]
0x1800fd40b  mov     rcx, [rbp+hKey]; hKey
0x1800fd40f  test    rcx, rcx
0x1800fd412  jz      short loc_1800FD420
0x1800fd414  call    cs:__imp_RegCloseKey
0x1800fd41b  nop     dword ptr [rax+rax+00h]
0x1800fd420  mov     eax, ebx
0x1800fd422  add     rsp, 58h
0x1800fd426  pop     r15
0x1800fd428  pop     r14
0x1800fd42a  pop     rdi
0x1800fd42b  pop     rsi
0x1800fd42c  pop     rbx
0x1800fd42d  pop     rbp
0x1800fd42e  retn
```
