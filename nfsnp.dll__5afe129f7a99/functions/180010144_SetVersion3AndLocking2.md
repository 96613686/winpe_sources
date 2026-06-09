# SetVersion3AndLocking2

- ea: `0x180010144`
- end: `0x18001035e`
- name: `SetVersion3AndLocking2`
- size: `538`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c738`

## callees

- `0x180010144`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x1800101cf`
- `msvcrt!wcscat_s` at `0x1800101cf`
- `msvcrt!wcsncpy_s` at `0x1800101b2`
- `msvcrt!wcsncpy_s` at `0x1800101b2`
- `ADVAPI32!RegCloseKey` at `0x1800102b6`
- `ADVAPI32!RegCloseKey` at `0x1800102b6`
- `ADVAPI32!RegQueryValueExW` at `0x180010239`
- `ADVAPI32!RegQueryValueExW` at `0x18001026f`
- `ADVAPI32!RegQueryValueExW` at `0x1800102a5`
- `ADVAPI32!RegQueryValueExW` at `0x180010239`
- `ADVAPI32!RegQueryValueExW` at `0x18001026f`
- `ADVAPI32!RegQueryValueExW` at `0x1800102a5`
- `ADVAPI32!RegOpenKeyExW` at `0x1800101f6`
- `ADVAPI32!RegOpenKeyExW` at `0x1800101f6`

## string_xrefs

- `0x1800101be`: `\Mount`
- `0x18001028a`: `EUCMount`

## pseudocode

```c
__int64 __fastcall SetVersion3AndLocking2(HKEY hKey, wchar_t *Source, __int64 a3)
{
  int v5; // eax
  unsigned int v6; // eax
  __int64 result; // rax
  int v8; // ecx
  int v9; // edx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  BYTE v12[4]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v13[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  HKEY hKeya; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Destination[264]; // [rsp+50h] [rbp-B0h] BYREF

  *(_DWORD *)Data = 1;
  *(_DWORD *)v12 = 1;
  cbData = 0;
  *(_DWORD *)v13 = 0;
  hKeya = 0;
  Destination[259] = 0;
  wcsncpy_s(Destination, 0x104u, Source, 0x103u);
  wcscat_s(Destination, 0x104u, L"\\Mount");
  if ( !RegOpenKeyExW(hKey, Destination, 0, 0x20019u, &hKeya) )
  {
    cbData = 4;
    RegQueryValueExW(hKeya, L"Locking", 0, 0, Data, &cbData);
    cbData = 4;
    RegQueryValueExW(hKeya, L"Version3", 0, 0, v12, &cbData);
    cbData = 4;
    RegQueryValueExW(hKeya, L"EUCMount", 0, 0, v13, &cbData);
    RegCloseKey(hKeya);
  }
  v5 = *(_DWORD *)(a3 + 56);
  if ( *(_DWORD *)Data )
    v6 = v5 | 1;
  else
    v6 = v5 & 0xFFFFFFFE;
  if ( *(_DWORD *)v12 )
    result = v6 | 4;
  else
    result = v6 & 0xFFFFFFFB;
  v8 = *(_DWORD *)v13;
  *(_DWORD *)(a3 + 56) = result;
  if ( !v8 )
  {
    result = (unsigned int)result & 0xFFF01FBF;
    goto LABEL_22;
  }
  v9 = 0x2000;
  if ( v8 == 0x2000 )
    goto LABEL_11;
  if ( v8 == 64 )
  {
    result = (unsigned int)result | 0x40;
    goto LABEL_22;
  }
  v9 = 0x4000;
  if ( v8 == 0x4000
    || (v9 = 0x8000, v8 == 0x8000)
    || (v9 = 0x10000, v8 == 0x10000)
    || (v9 = 0x20000, v8 == 0x20000)
    || (v9 = 0x40000, v8 == 0x40000)
    || (v9 = 0x80000, v8 == 0x80000) )
  {
LABEL_11:
    result = v9 | (unsigned int)result;
LABEL_22:
    *(_DWORD *)(a3 + 56) = result;
  }
  return result;
}

```

## disassembly

```asm
0x180010144  push    rbp
0x180010146  push    rbx
0x180010147  push    rdi
0x180010148  lea     rbp, [rsp-170h]
0x180010150  sub     rsp, 270h
0x180010157  mov     rax, cs:__security_cookie
0x18001015e  xor     rax, rsp
0x180010161  mov     [rbp+180h+var_20], rax
0x180010168  mov     r9d, 103h; MaxCount
0x18001016e  mov     dword ptr [rsp+280h+Data], 1
0x180010176  mov     rdi, r8
0x180010179  mov     dword ptr [rsp+280h+var_248], 1
0x180010181  mov     rbx, rcx
0x180010184  mov     [rsp+280h+cbData], 0
0x18001018c  xor     eax, eax
0x18001018e  mov     dword ptr [rsp+280h+var_244], 0
0x180010196  mov     r8, rdx; Source
0x180010199  mov     [rsp+280h+hKey], 0
0x1800101a2  lea     edx, [r9+1]; SizeInWords
0x1800101a6  mov     [rbp+180h+var_2A], ax
0x1800101ad  lea     rcx, [rsp+280h+Destination]; Destination
0x1800101b2  call    cs:__imp_wcsncpy_s
0x1800101b9  nop     dword ptr [rax+rax+00h]
0x1800101be  lea     r8, aMount; "\\Mount"
0x1800101c5  mov     edx, 104h; SizeInWords
0x1800101ca  lea     rcx, [rsp+280h+Destination]; Destination
0x1800101cf  call    cs:__imp_wcscat_s
0x1800101d6  nop     dword ptr [rax+rax+00h]
0x1800101db  lea     rax, [rsp+280h+hKey]
0x1800101e0  mov     r9d, 20019h; samDesired
0x1800101e6  xor     r8d, r8d; ulOptions
0x1800101e9  mov     [rsp+280h+phkResult], rax; phkResult
0x1800101ee  lea     rdx, [rsp+280h+Destination]; lpSubKey
0x1800101f3  mov     rcx, rbx; hKey
0x1800101f6  call    cs:__imp_RegOpenKeyExW
0x1800101fd  nop     dword ptr [rax+rax+00h]
0x180010202  mov     ebx, 4
0x180010207  test    eax, eax
0x180010209  jnz     loc_1800102C2
0x18001020f  mov     rcx, [rsp+280h+hKey]; hKey
0x180010214  lea     rax, [rsp+280h+cbData]
0x180010219  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18001021e  lea     rdx, aLocking; "Locking"
0x180010225  lea     rax, [rsp+280h+Data]
0x18001022a  mov     [rsp+280h+cbData], ebx
0x18001022e  xor     r9d, r9d; lpType
0x180010231  mov     [rsp+280h+phkResult], rax; lpData
0x180010236  xor     r8d, r8d; lpReserved
0x180010239  call    cs:__imp_RegQueryValueExW
0x180010240  nop     dword ptr [rax+rax+00h]
0x180010245  mov     rcx, [rsp+280h+hKey]; hKey
0x18001024a  lea     rax, [rsp+280h+cbData]
0x18001024f  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180010254  lea     rdx, aVersion3; "Version3"
0x18001025b  lea     rax, [rsp+280h+var_248]
0x180010260  mov     [rsp+280h+cbData], ebx
0x180010264  xor     r9d, r9d; lpType
0x180010267  mov     [rsp+280h+phkResult], rax; lpData
0x18001026c  xor     r8d, r8d; lpReserved
0x18001026f  call    cs:__imp_RegQueryValueExW
0x180010276  nop     dword ptr [rax+rax+00h]
0x18001027b  mov     rcx, [rsp+280h+hKey]; hKey
0x180010280  lea     rax, [rsp+280h+cbData]
0x180010285  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18001028a  lea     rdx, aEucmount; "EUCMount"
0x180010291  lea     rax, [rsp+280h+var_244]
0x180010296  mov     [rsp+280h+cbData], ebx
0x18001029a  xor     r9d, r9d; lpType
0x18001029d  mov     [rsp+280h+phkResult], rax; lpData
0x1800102a2  xor     r8d, r8d; lpReserved
0x1800102a5  call    cs:__imp_RegQueryValueExW
0x1800102ac  nop     dword ptr [rax+rax+00h]
0x1800102b1  mov     rcx, [rsp+280h+hKey]; hKey
0x1800102b6  call    cs:__imp_RegCloseKey
0x1800102bd  nop     dword ptr [rax+rax+00h]
0x1800102c2  cmp     dword ptr [rsp+280h+Data], 0
0x1800102c7  mov     eax, [rdi+38h]
0x1800102ca  jz      short loc_1800102D1
0x1800102cc  or      eax, 1
0x1800102cf  jmp     short loc_1800102D4
0x1800102d1  and     eax, 0FFFFFFFEh
0x1800102d4  cmp     dword ptr [rsp+280h+var_248], 0
0x1800102d9  jz      short loc_1800102DF
0x1800102db  or      eax, ebx
0x1800102dd  jmp     short loc_1800102E2
0x1800102df  and     eax, 0FFFFFFFBh
0x1800102e2  mov     ecx, dword ptr [rsp+280h+var_244]
0x1800102e6  mov     [rdi+38h], eax
0x1800102e9  test    ecx, ecx
0x1800102eb  jz      short loc_18001033B
0x1800102ed  mov     edx, 2000h
0x1800102f2  cmp     ecx, edx
0x1800102f4  jnz     short loc_1800102FA
0x1800102f6  or      eax, edx
0x1800102f8  jmp     short loc_180010340
0x1800102fa  cmp     ecx, 40h ; '@'
0x1800102fd  jnz     short loc_180010303
0x1800102ff  or      eax, ecx
0x180010301  jmp     short loc_180010340
0x180010303  mov     edx, 4000h
0x180010308  cmp     ecx, edx
0x18001030a  jz      short loc_1800102F6
0x18001030c  mov     edx, 8000h
0x180010311  cmp     ecx, edx
0x180010313  jz      short loc_1800102F6
0x180010315  mov     edx, 10000h
0x18001031a  cmp     ecx, edx
0x18001031c  jz      short loc_1800102F6
0x18001031e  mov     edx, 20000h
0x180010323  cmp     ecx, edx
0x180010325  jz      short loc_1800102F6
0x180010327  mov     edx, 40000h
0x18001032c  cmp     ecx, edx
0x18001032e  jz      short loc_1800102F6
0x180010330  mov     edx, 80000h
0x180010335  cmp     ecx, edx
0x180010337  jnz     short loc_180010343
0x180010339  jmp     short loc_1800102F6
0x18001033b  and     eax, 0FFF01FBFh
0x180010340  mov     [rdi+38h], eax
0x180010343  mov     rcx, [rbp+180h+var_20]
0x18001034a  xor     rcx, rsp; StackCookie
0x18001034d  call    __security_check_cookie
0x180010352  add     rsp, 270h
0x180010359  pop     rdi
0x18001035a  pop     rbx
0x18001035b  pop     rbp
0x18001035c  retn
```
