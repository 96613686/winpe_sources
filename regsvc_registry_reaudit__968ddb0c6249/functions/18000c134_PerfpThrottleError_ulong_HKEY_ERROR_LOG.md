# PerfpThrottleError(ulong,HKEY__ *,ERROR_LOG *)

- ea: `0x18000c134`
- end: `0x18000c2a8`
- name: `?PerfpThrottleError@@YAKKPEAUHKEY__@@PEAUERROR_LOG@@@Z`
- size: `372`
- prototype: `unsigned int(unsigned int, HKEY, struct ERROR_LOG *)`
- caller_count: `9`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800093a8`
- `0x18000b8a0`
- `0x18000e1a8`
- `0x18000f640`
- `0x1800119fc`
- `0x180011d10`
- `0x1800126c8`
- `0x18001277c`
- `0x1800136b0`

## callees

- `0x18000aac8`
- `0x18000bc48`
- `0x18000bf38`
- `0x18000c134`
- `0x18000c8fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c293`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c293`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c1e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c215`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c1e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c215`

## pseudocode

```c
__int64 __fastcall PerfpThrottleError(int a1, HKEY a2, struct ERROR_LOG *a3)
{
  struct ERROR_LOG *Error; // rax
  __int64 v5; // rdx
  struct ERROR_LOG *v6; // rdi
  WCHAR *el_text; // rbp
  unsigned int v8; // eax
  __int64 v9; // r8
  unsigned int v10; // ebx
  __int64 v11; // rdx
  unsigned int v12; // esi
  unsigned int v13; // eax
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = a2;
  if ( lEventLogLevel > 1 )
    return 1;
  if ( lEventLogLevel < 1 )
    return 0;
  Error = PerfpFindError(a1 & 0xFFFFFF, a3);
  v6 = Error;
  if ( !Error )
    return 0;
  el_text = Error->el_text;
  v8 = PerfpCheckErrorTime(Error, v5, hKey);
  v10 = v8;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), hKey, v9, v8, hKey);
  if ( !hKey && v10 )
  {
    v12 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib",
            0,
            0x2001Fu,
            &hKey);
    if ( v12 )
      v12 = RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib",
              0,
              0x20019u,
              &hKey);
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids, v12);
    if ( !v12 )
    {
      v6->el_text = el_text;
      v13 = PerfpCheckErrorTime(v6, v11, hKey);
      v10 = v13;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids, v13);
      RegCloseKey(hKey);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18000c134  mov     [rsp+hKey], rdx
0x18000c139  push    rbx
0x18000c13a  push    rbp
0x18000c13b  push    rsi
0x18000c13c  push    rdi
0x18000c13d  sub     rsp, 38h
0x18000c141  cmp     cs:?lEventLogLevel@@3JA, 1; long lEventLogLevel
0x18000c148  jle     short loc_18000C154
0x18000c14a  mov     eax, 1
0x18000c14f  jmp     loc_18000C29F
0x18000c154  jl      loc_18000C29D
0x18000c15a  and     ecx, 0FFFFFFh; unsigned int
0x18000c160  mov     rdx, r8; struct ERROR_LOG *
0x18000c163  call    ?PerfpFindError@@YAPEAUERROR_LOG@@KPEAU1@@Z; PerfpFindError(ulong,ERROR_LOG *)
0x18000c168  mov     rdi, rax
0x18000c16b  test    rax, rax
0x18000c16e  jz      loc_18000C29D
0x18000c174  mov     r8, [rsp+58h+hKey]; HKEY
0x18000c179  mov     rcx, rax; struct ERROR_LOG *
0x18000c17c  mov     rbp, [rax+18h]
0x18000c180  call    ?PerfpCheckErrorTime@@YAKPEAUERROR_LOG@@_JPEAUHKEY__@@@Z; PerfpCheckErrorTime(ERROR_LOG *,__int64,HKEY__ *)
0x18000c185  mov     ebx, eax
0x18000c187  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c18e  test    dword ptr [rcx+1Ch], 800h
0x18000c195  jz      short loc_18000C1B3
0x18000c197  cmp     byte ptr [rcx+19h], 4
0x18000c19b  jb      short loc_18000C1B3
0x18000c19d  mov     rdx, [rsp+58h+hKey]
0x18000c1a2  mov     r9d, eax
0x18000c1a5  mov     rcx, [rcx+10h]
0x18000c1a9  mov     [rsp+58h+phkResult], rdx
0x18000c1ae  call    WPP_SF_dq
0x18000c1b3  cmp     [rsp+58h+hKey], 0
0x18000c1b9  jnz     loc_18000C299
0x18000c1bf  test    ebx, ebx
0x18000c1c1  jz      loc_18000C299
0x18000c1c7  lea     rax, [rsp+58h+hKey]
0x18000c1cc  mov     r9d, 2001Fh; samDesired
0x18000c1d2  xor     r8d, r8d; ulOptions
0x18000c1d5  mov     [rsp+58h+phkResult], rax; phkResult
0x18000c1da  lea     rdx, ?HKLMPerflibKey@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000c1e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c1e8  call    cs:__imp_RegOpenKeyExW
0x18000c1ee  mov     esi, eax
0x18000c1f0  test    eax, eax
0x18000c1f2  jz      short loc_18000C21D
0x18000c1f4  lea     rax, [rsp+58h+hKey]
0x18000c1f9  mov     r9d, 20019h; samDesired
0x18000c1ff  xor     r8d, r8d; ulOptions
0x18000c202  mov     [rsp+58h+phkResult], rax; phkResult
0x18000c207  lea     rdx, ?HKLMPerflibKey@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000c20e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c215  call    cs:__imp_RegOpenKeyExW
0x18000c21b  mov     esi, eax
0x18000c21d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c224  test    dword ptr [rcx+1Ch], 800h
0x18000c22b  jz      short loc_18000C24B
0x18000c22d  cmp     byte ptr [rcx+19h], 4
0x18000c231  jb      short loc_18000C24B
0x18000c233  mov     rcx, [rcx+10h]
0x18000c237  lea     r8, WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids
0x18000c23e  mov     edx, 27h ; '''
0x18000c243  mov     r9d, esi
0x18000c246  call    WPP_SF_d
0x18000c24b  test    esi, esi
0x18000c24d  jnz     short loc_18000C299
0x18000c24f  mov     [rdi+18h], rbp
0x18000c253  mov     rcx, rdi; struct ERROR_LOG *
0x18000c256  mov     r8, [rsp+58h+hKey]; HKEY
0x18000c25b  call    ?PerfpCheckErrorTime@@YAKPEAUERROR_LOG@@_JPEAUHKEY__@@@Z; PerfpCheckErrorTime(ERROR_LOG *,__int64,HKEY__ *)
0x18000c260  mov     ebx, eax
0x18000c262  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c269  test    dword ptr [rcx+1Ch], 800h
0x18000c270  jz      short loc_18000C28E
0x18000c272  cmp     byte ptr [rcx+19h], 4
0x18000c276  jb      short loc_18000C28E
0x18000c278  mov     rcx, [rcx+10h]
0x18000c27c  lea     edx, [rsi+28h]
0x18000c27f  mov     r9d, eax
0x18000c282  lea     r8, WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids
0x18000c289  call    WPP_SF_d
0x18000c28e  mov     rcx, [rsp+58h+hKey]; hKey
0x18000c293  call    cs:__imp_RegCloseKey
0x18000c299  mov     eax, ebx
0x18000c29b  jmp     short loc_18000C29F
0x18000c29d  xor     eax, eax
0x18000c29f  add     rsp, 38h
0x18000c2a3  pop     rdi
0x18000c2a4  pop     rsi
0x18000c2a5  pop     rbp
0x18000c2a6  pop     rbx
0x18000c2a7  retn
```
