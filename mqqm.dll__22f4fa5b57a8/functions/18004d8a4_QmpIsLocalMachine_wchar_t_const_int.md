# QmpIsLocalMachine(wchar_t const *,int *)

- ea: `0x18004d8a4`
- end: `0x18004da44`
- name: `?QmpIsLocalMachine@@YAHPEB_WPEAH@Z`
- size: `416`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004c02c`
- `0x18004d0cc`
- `0x18004d280`

## callees

- `0x180009924`
- `0x18000cb80`
- `0x18004d8a4`
- `0x18004da4c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004d99c`
- `msvcrt!_wcsicmp` at `0x18004d99c`
- `msvcrt!wcschr` at `0x18004d92d`
- `msvcrt!wcschr` at `0x18004d92d`
- `KERNEL32!LeaveCriticalSection` at `0x18004d9eb`
- `KERNEL32!LeaveCriticalSection` at `0x18004da2c`
- `KERNEL32!LeaveCriticalSection` at `0x18004da3b`
- `KERNEL32!LeaveCriticalSection` at `0x18004d9eb`
- `KERNEL32!LeaveCriticalSection` at `0x18004da2c`
- `KERNEL32!LeaveCriticalSection` at `0x18004da3b`
- `KERNEL32!CompareStringW` at `0x18004d8e9`
- `KERNEL32!CompareStringW` at `0x18004d914`
- `KERNEL32!CompareStringW` at `0x18004d96d`
- `KERNEL32!CompareStringW` at `0x18004da15`
- `KERNEL32!CompareStringW` at `0x18004d8e9`
- `KERNEL32!CompareStringW` at `0x18004d914`
- `KERNEL32!CompareStringW` at `0x18004d96d`
- `KERNEL32!CompareStringW` at `0x18004da15`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall QmpIsLocalMachine(PCNZWCH lpString1, int *a2)
{
  int cchCount2; // ebx
  const WCHAR *lpString2; // rdi
  int v6; // eax
  PCNZWCH *v8; // rbx

  *a2 = 0;
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, g_szMachineName, -1) == 2
    || CompareStringW(0x7Fu, 1u, lpString1, -1, L"localhost", -1) == 2 )
  {
    return 1;
  }
  if ( wcschr(lpString1, 0x2Eu) )
  {
    cchCount2 = mqwcslen(g_szMachineName);
    lpString2 = g_szMachineName;
    v6 = mqwcslen(g_szMachineName);
    if ( CompareStringW(0x7Fu, 1u, lpString1, v6, lpString2, cchCount2) == 2
      && lpString1[mqwcslen(g_szMachineName)] == 46 )
    {
      if ( g_szComputerDnsName && !_wcsicmp(g_szComputerDnsName, lpString1) )
      {
        *a2 = 1;
        return 1;
      }
      CCriticalSection::Lock((CCriticalSection *)&csLocalMachineNames);
      RefreshLocalComputerDnsCache();
      v8 = (PCNZWCH *)Block;
      if ( Block )
      {
        while ( *v8 )
        {
          if ( CompareStringW(0x7Fu, 1u, lpString1, -1, *v8, -1) == 2 )
          {
            *a2 = 1;
            LeaveCriticalSection(&csLocalMachineNames);
            return 1;
          }
          ++v8;
        }
      }
      LeaveCriticalSection(&csLocalMachineNames);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004d8a4  mov     r11, rsp
0x18004d8a7  mov     [r11+8], rbx
0x18004d8ab  mov     [r11+18h], rbp
0x18004d8af  push    rsi
0x18004d8b0  push    rdi
0x18004d8b1  push    r12
0x18004d8b3  push    r14
0x18004d8b5  push    r15
0x18004d8b7  sub     rsp, 30h
0x18004d8bb  mov     r14, rdx
0x18004d8be  mov     rsi, rcx
0x18004d8c1  mov     dword ptr [rdx], 0
0x18004d8c7  or      r15d, 0FFFFFFFFh
0x18004d8cb  mov     [r11-30h], r15d
0x18004d8cf  mov     rax, cs:?g_szMachineName@@3PEA_WEA; wchar_t * g_szMachineName
0x18004d8d6  mov     [r11-38h], rax
0x18004d8da  mov     r9d, r15d; cchCount1
0x18004d8dd  mov     r8, rcx; lpString1
0x18004d8e0  lea     ebp, [r15+2]
0x18004d8e4  mov     edx, ebp; dwCmpFlags
0x18004d8e6  lea     ecx, [rbp+7Eh]; Locale
0x18004d8e9  call    cs:__imp_CompareStringW
0x18004d8ef  cmp     eax, 2
0x18004d8f2  jz      loc_18004D9A9
0x18004d8f8  mov     [rsp+58h+cchCount2], r15d; cchCount2
0x18004d8fd  lea     rax, aLocalhost_0; "localhost"
0x18004d904  mov     [rsp+58h+lpString2], rax; lpString2
0x18004d909  mov     r9d, r15d; cchCount1
0x18004d90c  mov     r8, rsi; lpString1
0x18004d90f  mov     edx, ebp; dwCmpFlags
0x18004d911  lea     ecx, [rbp+7Eh]; Locale
0x18004d914  call    cs:__imp_CompareStringW
0x18004d91a  cmp     eax, 2
0x18004d91d  jz      loc_18004D9A9
0x18004d923  lea     r12d, [r15+2Fh]
0x18004d927  mov     edx, r12d; Ch
0x18004d92a  mov     rcx, rsi; Str
0x18004d92d  call    cs:__imp_wcschr
0x18004d933  test    rax, rax
0x18004d936  jz      loc_18004D9F2
0x18004d93c  mov     rcx, cs:?g_szMachineName@@3PEA_WEA; wchar_t *
0x18004d943  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18004d948  mov     ebx, eax
0x18004d94a  mov     rdi, cs:?g_szMachineName@@3PEA_WEA; wchar_t * g_szMachineName
0x18004d951  mov     rcx, rdi; wchar_t *
0x18004d954  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18004d959  mov     [rsp+58h+cchCount2], ebx; cchCount2
0x18004d95d  mov     [rsp+58h+lpString2], rdi; lpString2
0x18004d962  mov     r9d, eax; cchCount1
0x18004d965  mov     r8, rsi; lpString1
0x18004d968  mov     edx, ebp; dwCmpFlags
0x18004d96a  lea     ecx, [rbp+7Eh]; Locale
0x18004d96d  call    cs:__imp_CompareStringW
0x18004d973  cmp     eax, 2
0x18004d976  jnz     short loc_18004D9F2
0x18004d978  mov     rcx, cs:?g_szMachineName@@3PEA_WEA; wchar_t *
0x18004d97f  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18004d984  mov     eax, eax
0x18004d986  cmp     [rsi+rax*2], r12w
0x18004d98b  jnz     short loc_18004D9F2
0x18004d98d  mov     rcx, cs:?g_szComputerDnsName@@3V?$AP@_W@@A; String1
0x18004d994  test    rcx, rcx
0x18004d997  jz      short loc_18004D9C2
0x18004d999  mov     rdx, rsi; String2
0x18004d99c  call    cs:__imp__wcsicmp
0x18004d9a2  test    eax, eax
0x18004d9a4  jnz     short loc_18004D9C2
0x18004d9a6  mov     [r14], ebp
0x18004d9a9  mov     eax, ebp
0x18004d9ab  mov     rbx, [rsp+58h+arg_0]
0x18004d9b0  mov     rbp, [rsp+58h+arg_10]
0x18004d9b5  add     rsp, 30h
0x18004d9b9  pop     r15
0x18004d9bb  pop     r14
0x18004d9bd  pop     r12
0x18004d9bf  pop     rdi
0x18004d9c0  pop     rsi
0x18004d9c1  retn
0x18004d9c2  lea     rdi, ?csLocalMachineNames@@3VCCriticalSection@@A; CCriticalSection csLocalMachineNames
0x18004d9c9  mov     [rsp+58h+arg_8], rdi
0x18004d9ce  mov     rcx, rdi; this
0x18004d9d1  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18004d9d6  nop
0x18004d9d7  call    RefreshLocalComputerDnsCache
0x18004d9dc  mov     rbx, cs:Block
0x18004d9e3  test    rbx, rbx
0x18004d9e6  jnz     short loc_18004D9F6
0x18004d9e8  mov     rcx, rdi; lpCriticalSection
0x18004d9eb  call    cs:__imp_LeaveCriticalSection
0x18004d9f1  nop
0x18004d9f2  xor     eax, eax
0x18004d9f4  jmp     short loc_18004D9AB
0x18004d9f6  mov     rax, [rbx]
0x18004d9f9  test    rax, rax
0x18004d9fc  jz      short loc_18004DA38
0x18004d9fe  mov     [rsp+58h+cchCount2], r15d; cchCount2
0x18004da03  mov     [rsp+58h+lpString2], rax; lpString2
0x18004da08  mov     r9d, r15d; cchCount1
0x18004da0b  mov     r8, rsi; lpString1
0x18004da0e  mov     edx, ebp; dwCmpFlags
0x18004da10  mov     ecx, 7Fh; Locale
0x18004da15  call    cs:__imp_CompareStringW
0x18004da1b  cmp     eax, 2
0x18004da1e  jz      short loc_18004DA26
0x18004da20  add     rbx, 8
0x18004da24  jmp     short loc_18004D9F6
0x18004da26  mov     [r14], ebp
0x18004da29  mov     rcx, rdi; lpCriticalSection
0x18004da2c  call    cs:__imp_LeaveCriticalSection
0x18004da32  nop
0x18004da33  jmp     loc_18004D9A9
0x18004da38  mov     rcx, rdi; lpCriticalSection
0x18004da3b  call    cs:__imp_LeaveCriticalSection
0x18004da41  nop
0x18004da42  jmp     short loc_18004D9F2
```
