# DhcpRegDeleteValue

- ea: `0x180003d30`
- end: `0x180003e99`
- name: `DhcpRegDeleteValue`
- size: `361`
- prototype: `LSTATUS __fastcall(__int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004a30`

## callees

- `0x180003d30`
- `0x180046794`
- `0x180047e3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180003d53`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180003d53`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003da3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003da3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003e8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003e8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003dfa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003dfa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180003e48`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180003e81`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180003e48`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180003e81`

## pseudocode

```c
LSTATUS __fastcall DhcpRegDeleteValue(__int64 a1, const wchar_t *a2)
{
  wchar_t *v3; // rax
  wchar_t *v4; // rbp
  SIZE_T v5; // rdi
  void *v6; // rsi
  unsigned __int64 v7; // rax
  LSTATUS v8; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  v3 = wcsrchr(a2, 0x5Cu);
  v4 = v3;
  if ( !v3 )
  {
    hKey = HKEY_LOCAL_MACHINE;
    return RegDeleteValueW(HKEY_LOCAL_MACHINE, a2);
  }
  v5 = 2 * (v3 - a2) + 2;
  if ( v5 >= 0xFFFFFFFF )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return 14;
  }
  v6 = HeapAlloc(NtCurrentPeb()->ProcessHeap, 8u, v5);
  if ( !v6 )
    return 14;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  if ( v7 >= v5 )
    memcpy_0(v6, a2, v5);
  *((_WORD *)v6 + (v5 >> 1) - 1) = 0;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v6, 0, 0xFu, &hKey);
  if ( !v8 )
  {
    v8 = RegDeleteValueW(hKey, v4 + 1);
    RegCloseKey(hKey);
  }
  HeapFree(NtCurrentPeb()->ProcessHeap, 0, v6);
  return v8;
}

```

## disassembly

```asm
0x180003d30  mov     [rsp+arg_18], rbx
0x180003d35  mov     [rsp+hKey], rcx
0x180003d3a  push    rbp
0x180003d3b  sub     rsp, 30h
0x180003d3f  mov     rbx, rdx
0x180003d42  mov     [rsp+38h+hKey], 0
0x180003d4b  mov     rcx, rbx; Str
0x180003d4e  mov     edx, 5Ch ; '\'; Ch
0x180003d53  call    cs:__imp_wcsrchr
0x180003d59  mov     rbp, rax
0x180003d5c  test    rax, rax
0x180003d5f  jz      loc_180003E35
0x180003d65  mov     rcx, rax
0x180003d68  mov     [rsp+38h+arg_10], rdi
0x180003d6d  sub     rcx, rbx
0x180003d70  mov     [rsp+38h+arg_8], rsi
0x180003d75  sar     rcx, 1
0x180003d78  mov     eax, 0FFFFFFFFh
0x180003d7d  lea     rdi, ds:2[rcx*2]
0x180003d85  cmp     rdi, rax
0x180003d88  jnb     loc_180003E59
0x180003d8e  mov     rcx, gs:60h
0x180003d97  mov     r8, rdi; dwBytes
0x180003d9a  mov     edx, 8; dwFlags
0x180003d9f  mov     rcx, [rcx+30h]; hHeap
0x180003da3  call    cs:__imp_HeapAlloc
0x180003da9  mov     rsi, rax
0x180003dac  test    rax, rax
0x180003daf  jz      loc_180003E5E
0x180003db5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003dbc  nop     dword ptr [rax+00h]
0x180003dc0  inc     rax
0x180003dc3  cmp     word ptr [rbx+rax*2], 0
0x180003dc8  jnz     short loc_180003DC0
0x180003dca  cmp     rax, rdi
0x180003dcd  jnb     loc_180003E65
0x180003dd3  xor     eax, eax
0x180003dd5  shr     rdi, 1
0x180003dd8  mov     r9d, 0Fh; samDesired
0x180003dde  xor     r8d, r8d; ulOptions
0x180003de1  mov     rdx, rsi; lpSubKey
0x180003de4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003deb  mov     [rsi+rdi*2-2], ax
0x180003df0  lea     rax, [rsp+38h+hKey]
0x180003df5  mov     [rsp+38h+phkResult], rax; phkResult
0x180003dfa  call    cs:__imp_RegOpenKeyExW
0x180003e00  mov     ebx, eax
0x180003e02  test    eax, eax
0x180003e04  jz      short loc_180003E78
0x180003e06  mov     rcx, gs:60h
0x180003e0f  mov     r8, rsi; lpMem
0x180003e12  xor     edx, edx; dwFlags
0x180003e14  mov     rcx, [rcx+30h]; hHeap
0x180003e18  call    cs:__imp_HeapFree
0x180003e1e  mov     eax, ebx
0x180003e20  mov     rsi, [rsp+38h+arg_8]
0x180003e25  mov     rdi, [rsp+38h+arg_10]
0x180003e2a  mov     rbx, [rsp+38h+arg_18]
0x180003e2f  add     rsp, 30h
0x180003e33  pop     rbp
0x180003e34  retn
0x180003e35  mov     rdx, rbx; lpValueName
0x180003e38  mov     [rsp+38h+hKey], 0FFFFFFFF80000002h
0x180003e41  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003e48  call    cs:__imp_RegDeleteValueW
0x180003e4e  mov     rbx, [rsp+38h+arg_18]
0x180003e53  add     rsp, 30h
0x180003e57  pop     rbp
0x180003e58  retn
0x180003e59  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180003e5e  mov     eax, 0Eh
0x180003e63  jmp     short loc_180003E20
0x180003e65  mov     r8, rdi; Size
0x180003e68  mov     rdx, rbx; Src
0x180003e6b  mov     rcx, rsi; void *
0x180003e6e  call    memcpy_0
0x180003e73  jmp     loc_180003DD3
0x180003e78  mov     rcx, [rsp+38h+hKey]; hKey
0x180003e7d  lea     rdx, [rbp+2]; lpValueName
0x180003e81  call    cs:__imp_RegDeleteValueW
0x180003e87  mov     rcx, [rsp+38h+hKey]; hKey
0x180003e8c  mov     ebx, eax
0x180003e8e  call    cs:__imp_RegCloseKey
0x180003e94  jmp     loc_180003E06
```
