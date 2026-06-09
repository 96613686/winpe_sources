# Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x1800099a0`
- end: `0x180009bc6`
- name: `?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `550`
- prototype: `__int64 __fastcall(__int64, HKEY, const WCHAR *, char)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009488`
- `0x18000dd18`

## callees

- `0x1800099a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009afa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009bbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009afa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009bbe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a34`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009ab6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a34`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009ab6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009aa8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009aec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009bb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009aa8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009aec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009bb0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800099e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009a63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800099e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009a63`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009a97`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009ad1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009a97`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009ad1`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_InitializeFromRegistry(
        __int64 a1,
        HKEY a2,
        const WCHAR *a3,
        char a4)
{
  BYTE *lpData; // rbx
  LSTATUS v9; // eax
  signed int v10; // edi
  DWORD v11; // ebx
  HANDLE ProcessHeap; // rax
  LSTATUS v13; // eax
  __int64 v14; // rsi
  DWORD v15; // ebp
  HANDLE v16; // rax
  WCHAR *v17; // rax
  WCHAR *v18; // r15
  DWORD v19; // eax
  DWORD v20; // esi
  HANDLE v21; // rax
  void *v22; // rbp
  HANDLE v23; // rax
  __int64 v24; // rax
  HANDLE v25; // rax
  HANDLE v27; // rax
  DWORD cbData; // [rsp+30h] [rbp-48h] BYREF
  DWORD Type[17]; // [rsp+34h] [rbp-44h] BYREF

  Type[0] = 0;
  cbData = 0;
  lpData = 0;
  v9 = RegQueryValueExW(a2, a3, 0, Type, 0, &cbData);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 >= 0 )
  {
    if ( Type[0] - 1 > 1 || !cbData || (cbData & 1) != 0 )
      goto LABEL_27;
    v11 = cbData;
    ProcessHeap = GetProcessHeap();
    lpData = (BYTE *)HeapAlloc(ProcessHeap, 0, v11);
    if ( !lpData )
      goto LABEL_26;
    v13 = RegQueryValueExW(a2, a3, 0, Type, lpData, &cbData);
    v10 = v13;
    if ( v13 > 0 )
      v10 = (unsigned __int16)v13 | 0x80070000;
    if ( v10 >= 0 )
    {
      v14 = (cbData >> 1) - 1;
      if ( Type[0] != 2 )
        goto LABEL_18;
      if ( !a4 )
        goto LABEL_18;
      v15 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
      if ( !v15 )
        goto LABEL_18;
      v16 = GetProcessHeap();
      v17 = (WCHAR *)HeapAlloc(v16, 0, 2LL * v15);
      v18 = v17;
      if ( v17 )
      {
        v19 = ExpandEnvironmentStringsW((LPCWSTR)lpData, v17, v15);
        v20 = v19;
        if ( !v19 || v19 > v15 )
        {
          v10 = -2147024774;
          v27 = GetProcessHeap();
          HeapFree(v27, 0, v18);
          goto LABEL_25;
        }
        v10 = 0;
        v21 = GetProcessHeap();
        HeapFree(v21, 0, lpData);
        v14 = v20 - 1;
        lpData = (BYTE *)v18;
LABEL_18:
        if ( !*(_WORD *)&lpData[2 * v14] )
        {
          v22 = *(void **)a1;
          if ( *(_QWORD *)a1 )
          {
            v23 = GetProcessHeap();
            HeapFree(v23, 0, v22);
            *(_QWORD *)a1 = 0;
          }
          *(_QWORD *)(a1 + 8) = 0;
          *(_QWORD *)(a1 + 16) = 0;
          if ( lpData )
          {
            v24 = (unsigned int)(v14 + 1);
            if ( (_DWORD)v14 != -1 )
            {
              *(_QWORD *)a1 = lpData;
              *(_QWORD *)(a1 + 8) = v24 - 1;
              *(_QWORD *)(a1 + 16) = (unsigned int)v24;
              *(_WORD *)&lpData[2 * (unsigned int)v24 - 2] = 0;
            }
          }
          lpData = 0;
          goto LABEL_25;
        }
LABEL_27:
        v10 = -2147024883;
        goto LABEL_25;
      }
LABEL_26:
      v10 = -2147024882;
    }
  }
LABEL_25:
  v25 = GetProcessHeap();
  HeapFree(v25, 0, lpData);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800099a0  push    rbx
0x1800099a2  push    rbp
0x1800099a3  push    rsi
0x1800099a4  push    rdi
0x1800099a5  push    r12
0x1800099a7  push    r14
0x1800099a9  push    r15
0x1800099ab  sub     rsp, 40h
0x1800099af  xor     r12d, r12d
0x1800099b2  lea     rax, [rsp+78h+cbData]
0x1800099b7  mov     rsi, r8
0x1800099ba  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800099bf  mov     rbp, rdx
0x1800099c2  mov     [rsp+78h+lpData], r12; lpData
0x1800099c7  movzx   r15d, r9b
0x1800099cb  mov     [rsp+78h+Type], r12d
0x1800099d0  mov     r14, rcx
0x1800099d3  mov     [rsp+78h+cbData], r12d
0x1800099d8  mov     rdx, rsi; lpValueName
0x1800099db  lea     r9, [rsp+78h+Type]; lpType
0x1800099e0  mov     rcx, rbp; hKey
0x1800099e3  xor     r8d, r8d; lpReserved
0x1800099e6  mov     ebx, r12d
0x1800099e9  call    cs:__imp_RegQueryValueExW
0x1800099ef  mov     edi, eax
0x1800099f1  test    eax, eax
0x1800099f3  jg      loc_180009B88
0x1800099f9  test    edi, edi
0x1800099fb  js      loc_180009B5C
0x180009a01  mov     eax, [rsp+78h+Type]
0x180009a05  dec     eax
0x180009a07  cmp     eax, 1
0x180009a0a  ja      loc_180009BA4
0x180009a10  mov     eax, [rsp+78h+cbData]
0x180009a14  test    eax, eax
0x180009a16  jz      loc_180009BA4
0x180009a1c  test    al, 1
0x180009a1e  jnz     loc_180009BA4
0x180009a24  mov     ebx, eax
0x180009a26  call    cs:__imp_GetProcessHeap
0x180009a2c  mov     r8d, ebx; dwBytes
0x180009a2f  xor     edx, edx; dwFlags
0x180009a31  mov     rcx, rax; hHeap
0x180009a34  call    cs:__imp_HeapAlloc
0x180009a3a  mov     rbx, rax
0x180009a3d  test    rax, rax
0x180009a40  jz      loc_180009B81
0x180009a46  lea     rax, [rsp+78h+cbData]
0x180009a4b  xor     r8d, r8d; lpReserved
0x180009a4e  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180009a53  lea     r9, [rsp+78h+Type]; lpType
0x180009a58  mov     rdx, rsi; lpValueName
0x180009a5b  mov     [rsp+78h+lpData], rbx; lpData
0x180009a60  mov     rcx, rbp; hKey
0x180009a63  call    cs:__imp_RegQueryValueExW
0x180009a69  mov     edi, eax
0x180009a6b  test    eax, eax
0x180009a6d  jg      loc_180009B96
0x180009a73  test    edi, edi
0x180009a75  js      loc_180009B5C
0x180009a7b  mov     esi, [rsp+78h+cbData]
0x180009a7f  shr     esi, 1
0x180009a81  dec     esi
0x180009a83  cmp     [rsp+78h+Type], 2
0x180009a88  jnz     short loc_180009B05
0x180009a8a  test    r15b, r15b
0x180009a8d  jz      short loc_180009B05
0x180009a8f  xor     r8d, r8d; nSize
0x180009a92  xor     edx, edx; lpDst
0x180009a94  mov     rcx, rbx; lpSrc
0x180009a97  call    cs:__imp_ExpandEnvironmentStringsW
0x180009a9d  mov     ebp, eax
0x180009a9f  test    eax, eax
0x180009aa1  jz      short loc_180009B05
0x180009aa3  mov     edi, ebp
0x180009aa5  add     rdi, rdi
0x180009aa8  call    cs:__imp_GetProcessHeap
0x180009aae  mov     r8, rdi; dwBytes
0x180009ab1  xor     edx, edx; dwFlags
0x180009ab3  mov     rcx, rax; hHeap
0x180009ab6  call    cs:__imp_HeapAlloc
0x180009abc  mov     r15, rax
0x180009abf  test    rax, rax
0x180009ac2  jz      loc_180009B81
0x180009ac8  mov     r8d, ebp; nSize
0x180009acb  mov     rdx, rax; lpDst
0x180009ace  mov     rcx, rbx; lpSrc
0x180009ad1  call    cs:__imp_ExpandEnvironmentStringsW
0x180009ad7  mov     esi, eax
0x180009ad9  test    eax, eax
0x180009adb  jz      loc_180009BAB
0x180009ae1  cmp     eax, ebp
0x180009ae3  ja      loc_180009BAB
0x180009ae9  mov     edi, r12d
0x180009aec  call    cs:__imp_GetProcessHeap
0x180009af2  mov     r8, rbx; lpMem
0x180009af5  xor     edx, edx; dwFlags
0x180009af7  mov     rcx, rax; hHeap
0x180009afa  call    cs:__imp_HeapFree
0x180009b00  dec     esi
0x180009b02  mov     rbx, r15
0x180009b05  cmp     [rbx+rsi*2], r12w
0x180009b0a  jnz     loc_180009BA4
0x180009b10  mov     rbp, [r14]
0x180009b13  test    rbp, rbp
0x180009b16  jz      short loc_180009B2F
0x180009b18  call    cs:__imp_GetProcessHeap
0x180009b1e  mov     r8, rbp; lpMem
0x180009b21  xor     edx, edx; dwFlags
0x180009b23  mov     rcx, rax; hHeap
0x180009b26  call    cs:__imp_HeapFree
0x180009b2c  mov     [r14], r12
0x180009b2f  mov     [r14+8], r12
0x180009b33  mov     [r14+10h], r12
0x180009b37  test    rbx, rbx
0x180009b3a  jz      short loc_180009B59
0x180009b3c  lea     eax, [rsi+1]
0x180009b3f  mov     ecx, eax
0x180009b41  test    eax, eax
0x180009b43  jz      short loc_180009B59
0x180009b45  dec     rax
0x180009b48  mov     [r14], rbx
0x180009b4b  mov     [r14+8], rax
0x180009b4f  mov     [r14+10h], rcx
0x180009b53  mov     [rbx+rcx*2-2], r12w
0x180009b59  mov     rbx, r12
0x180009b5c  call    cs:__imp_GetProcessHeap
0x180009b62  mov     r8, rbx; lpMem
0x180009b65  xor     edx, edx; dwFlags
0x180009b67  mov     rcx, rax; hHeap
0x180009b6a  call    cs:__imp_HeapFree
0x180009b70  mov     eax, edi
0x180009b72  add     rsp, 40h
0x180009b76  pop     r15
0x180009b78  pop     r14
0x180009b7a  pop     r12
0x180009b7c  pop     rdi
0x180009b7d  pop     rsi
0x180009b7e  pop     rbp
0x180009b7f  pop     rbx
0x180009b80  retn
0x180009b81  mov     edi, 8007000Eh
0x180009b86  jmp     short loc_180009B5C
0x180009b88  movzx   edi, ax
0x180009b8b  or      edi, 80070000h
0x180009b91  jmp     loc_1800099F9
0x180009b96  movzx   edi, ax
0x180009b99  or      edi, 80070000h
0x180009b9f  jmp     loc_180009A73
0x180009ba4  mov     edi, 8007000Dh
0x180009ba9  jmp     short loc_180009B5C
0x180009bab  mov     edi, 8007007Ah
0x180009bb0  call    cs:__imp_GetProcessHeap
0x180009bb6  mov     r8, r15; lpMem
0x180009bb9  xor     edx, edx; dwFlags
0x180009bbb  mov     rcx, rax; hHeap
0x180009bbe  call    cs:__imp_HeapFree
0x180009bc4  jmp     short loc_180009B5C
```
