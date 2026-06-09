# SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)

- ea: `0x180055e38`
- end: `0x180055faa`
- name: `?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z`
- size: `370`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, int, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800561b0`

## callees

- `0x180002b60`
- `0x1800041c1`
- `0x180055e38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180055f6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180055f6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180055e96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180055e96`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180055edd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180055f3e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180055edd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180055f3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055ef4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055ef4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055f55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055f55`

## pseudocode

```c
__int64 __fastcall SHRegAllocData(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        void **a5)
{
  HKEY v5; // rcx
  int v7; // esi
  LSTATUS v8; // eax
  int v9; // ebx
  LSTATUS ValueW; // eax
  void *pvData; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Src[256]; // [rsp+50h] [rbp-B0h] BYREF

  v5 = HKEY_LOCAL_MACHINE;
  hkey = HKEY_LOCAL_MACHINE;
  if ( a2 && *a2 )
  {
    v7 = 1;
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 1u, &hkey);
    v5 = hkey;
    v9 = v8;
  }
  else
  {
    v9 = 0;
    v7 = 0;
  }
  if ( v9 )
    goto LABEL_18;
  pcbData = 256;
  ValueW = RegGetValueW(v5, 0, a3, 2u, 0, Src, &pcbData);
  v9 = ValueW;
  if ( !ValueW || ValueW == 234 )
  {
    pvData = CoTaskMemAlloc(pcbData);
    *a5 = pvData;
    if ( pvData )
    {
      if ( v9 )
      {
        if ( RegGetValueW(hkey, 0, a3, 2u, 0, pvData, &pcbData) )
        {
          v9 = 1003;
          CoTaskMemFree(*a5);
        }
        else
        {
          v9 = 0;
        }
      }
      else
      {
        memcpy_0(pvData, Src, pcbData);
      }
    }
    else
    {
      v9 = 14;
    }
  }
  if ( v7 )
    RegCloseKey(hkey);
  if ( v9 )
  {
LABEL_18:
    *a5 = 0;
    if ( v9 > 0 )
      return (unsigned __int16)v9 | 0x80070000;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180055e38  mov     [rsp-8+arg_0], rbx
0x180055e3d  push    rbp
0x180055e3e  push    rsi
0x180055e3f  push    rdi
0x180055e40  push    r14
0x180055e42  push    r15
0x180055e44  lea     rbp, [rsp-60h]
0x180055e49  sub     rsp, 160h
0x180055e50  mov     rax, cs:__security_cookie
0x180055e57  xor     rax, rsp
0x180055e5a  mov     [rbp+80h+var_30], rax
0x180055e5e  mov     rdi, [rbp+80h+arg_20]
0x180055e65  xor     r15d, r15d
0x180055e68  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180055e6f  mov     r14, r8
0x180055e72  mov     [rsp+180h+hkey], rcx
0x180055e77  test    rdx, rdx
0x180055e7a  jz      short loc_180055EA5
0x180055e7c  cmp     [rdx], r15w
0x180055e80  jz      short loc_180055EA5
0x180055e82  lea     rax, [rsp+180h+hkey]
0x180055e87  xor     r8d, r8d; ulOptions
0x180055e8a  lea     esi, [r15+1]
0x180055e8e  mov     [rsp+180h+phkResult], rax; phkResult
0x180055e93  mov     r9d, esi; samDesired
0x180055e96  call    cs:__imp_RegOpenKeyExW
0x180055e9c  mov     rcx, [rsp+180h+hkey]
0x180055ea1  mov     ebx, eax
0x180055ea3  jmp     short loc_180055EAB
0x180055ea5  mov     ebx, r15d
0x180055ea8  mov     esi, r15d
0x180055eab  test    ebx, ebx
0x180055ead  jnz     loc_180055F75
0x180055eb3  lea     rax, [rsp+180h+var_140]
0x180055eb8  mov     [rsp+180h+var_140], 100h
0x180055ec0  mov     [rsp+180h+pcbData], rax; pcbData
0x180055ec5  lea     r9d, [rbx+2]; dwFlags
0x180055ec9  lea     rax, [rsp+180h+Src]
0x180055ece  mov     r8, r14; lpValue
0x180055ed1  mov     [rsp+180h+pvData], rax; pvData
0x180055ed6  xor     edx, edx; lpSubKey
0x180055ed8  mov     [rsp+180h+phkResult], r15; pdwType
0x180055edd  call    cs:__imp_RegGetValueW
0x180055ee3  mov     ebx, eax
0x180055ee5  test    eax, eax
0x180055ee7  jz      short loc_180055EF0
0x180055ee9  cmp     eax, 0EAh
0x180055eee  jnz     short loc_180055F62
0x180055ef0  mov     ecx, [rsp+180h+var_140]; cb
0x180055ef4  call    cs:__imp_CoTaskMemAlloc
0x180055efa  mov     [rdi], rax
0x180055efd  test    rax, rax
0x180055f00  jz      short loc_180055F5D
0x180055f02  test    ebx, ebx
0x180055f04  jnz     short loc_180055F1A
0x180055f06  mov     r8d, [rsp+180h+var_140]; Size
0x180055f0b  lea     rdx, [rsp+180h+Src]; Src
0x180055f10  mov     rcx, rax; void *
0x180055f13  call    memcpy_0
0x180055f18  jmp     short loc_180055F62
0x180055f1a  lea     rcx, [rsp+180h+var_140]
0x180055f1f  mov     r9d, 2; dwFlags
0x180055f25  mov     [rsp+180h+pcbData], rcx; pcbData
0x180055f2a  mov     r8, r14; lpValue
0x180055f2d  mov     rcx, [rsp+180h+hkey]; hkey
0x180055f32  xor     edx, edx; lpSubKey
0x180055f34  mov     [rsp+180h+pvData], rax; pvData
0x180055f39  mov     [rsp+180h+phkResult], r15; pdwType
0x180055f3e  call    cs:__imp_RegGetValueW
0x180055f44  test    eax, eax
0x180055f46  jnz     short loc_180055F4D
0x180055f48  mov     ebx, r15d
0x180055f4b  jmp     short loc_180055F62
0x180055f4d  mov     rcx, [rdi]; pv
0x180055f50  mov     ebx, 3EBh
0x180055f55  call    cs:__imp_CoTaskMemFree
0x180055f5b  jmp     short loc_180055F62
0x180055f5d  mov     ebx, 0Eh
0x180055f62  test    esi, esi
0x180055f64  jz      short loc_180055F71
0x180055f66  mov     rcx, [rsp+180h+hkey]; hKey
0x180055f6b  call    cs:__imp_RegCloseKey
0x180055f71  test    ebx, ebx
0x180055f73  jz      short loc_180055F85
0x180055f75  mov     [rdi], r15
0x180055f78  test    ebx, ebx
0x180055f7a  jle     short loc_180055F85
0x180055f7c  movzx   ebx, bx
0x180055f7f  or      ebx, 80070000h
0x180055f85  mov     eax, ebx
0x180055f87  mov     rcx, [rbp+80h+var_30]
0x180055f8b  xor     rcx, rsp; StackCookie
0x180055f8e  call    __security_check_cookie
0x180055f93  mov     rbx, [rsp+180h+arg_0]
0x180055f9b  add     rsp, 160h
0x180055fa2  pop     r15
0x180055fa4  pop     r14
0x180055fa6  pop     rdi
0x180055fa7  pop     rsi
0x180055fa8  pop     rbp
0x180055fa9  retn
```
