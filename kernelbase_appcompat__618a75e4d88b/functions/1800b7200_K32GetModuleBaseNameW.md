# K32GetModuleBaseNameW

- ea: `0x1800b7200`
- end: `0x1800b7494`
- name: `K32GetModuleBaseNameW`
- size: `660`
- prototype: `DWORD __stdcall(HANDLE hProcess, HMODULE hModule, LPWSTR lpBaseName, DWORD nSize)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800b7160`

## callees

- `0x18001cd34`
- `0x18004b9d0`
- `0x1800b7200`
- `0x1800b7c58`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800b747f`
- `ntdll!RtlNtStatusToDosError` at `0x1800b747f`
- `ntdll!NtQueryInformationProcess` at `0x1800b727d`
- `ntdll!NtQueryInformationProcess` at `0x1800b727d`
- `ntdll!NtReadVirtualMemory` at `0x1800b72c4`
- `ntdll!NtReadVirtualMemory` at `0x1800b7307`
- `ntdll!NtReadVirtualMemory` at `0x1800b7351`
- `ntdll!NtReadVirtualMemory` at `0x1800b73c6`
- `ntdll!NtReadVirtualMemory` at `0x1800b743e`
- `ntdll!NtReadVirtualMemory` at `0x1800b72c4`
- `ntdll!NtReadVirtualMemory` at `0x1800b7307`
- `ntdll!NtReadVirtualMemory` at `0x1800b7351`
- `ntdll!NtReadVirtualMemory` at `0x1800b73c6`
- `ntdll!NtReadVirtualMemory` at `0x1800b743e`

## pseudocode

```c
DWORD __stdcall K32GetModuleBaseNameW(HANDLE hProcess, HMODULE hModule, LPWSTR lpBaseName, DWORD nSize)
{
  int InformationProcess; // eax
  __int64 v9; // rbx
  NTSTATUS v10; // eax
  __int64 v11; // rsi
  unsigned int v12; // ebx
  __int64 v13; // rax
  ULONG v14; // ecx
  DWORD v15; // ebx
  unsigned int v16; // edx
  __int64 v17; // rsi
  DWORD v18; // r8d
  ULONG_PTR NumberOfBytesRead; // [rsp+30h] [rbp-D0h] BYREF
  HMODULE v21; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 Buffer; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD ProcessInformation[3]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[16]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v26; // [rsp+90h] [rbp-70h]
  HMODULE v27; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v28; // [rsp+D8h] [rbp-28h]
  PVOID BaseAddress; // [rsp+E0h] [rbp-20h]
  __int16 v30; // [rsp+ECh] [rbp-14h]

  memset_0(v25, 0, 0x88u);
  v21 = hModule;
  Buffer = 0;
  v22 = 0;
  memset(ProcessInformation, 0, 44);
  InformationProcess = NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
  if ( InformationProcess < 0 )
  {
    v14 = RtlNtStatusToDosError(InformationProcess);
    goto LABEL_29;
  }
  v9 = *((_QWORD *)&ProcessInformation[0] + 1);
  if ( !v21
    && (NumberOfBytesRead = 0,
        v10 = NtReadVirtualMemory(
                hProcess,
                (PVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 16LL),
                &v21,
                8u,
                &NumberOfBytesRead),
        v10 < 0)
    || (NumberOfBytesRead = 0,
        v10 = NtReadVirtualMemory(hProcess, (PVOID)(v9 + 24), &Buffer, 8u, &NumberOfBytesRead),
        v10 < 0) )
  {
LABEL_22:
    BaseSetLastNTError((unsigned int)v10);
    return 0;
  }
  if ( !Buffer )
  {
LABEL_11:
    v14 = 6;
LABEL_29:
    SetLastError_0(v14);
    return 0;
  }
  v11 = Buffer + 32;
  NumberOfBytesRead = 0;
  v10 = NtReadVirtualMemory(hProcess, (PVOID)(Buffer + 32), &v22, 8u, &NumberOfBytesRead);
  if ( v10 < 0 )
    goto LABEL_22;
  v12 = 0;
  v13 = v22;
  while ( v13 != v11 )
  {
    NumberOfBytesRead = 0;
    v10 = NtReadVirtualMemory(hProcess, (PVOID)(v13 - 16), v25, 0x88u, &NumberOfBytesRead);
    if ( v10 < 0 )
      goto LABEL_22;
    if ( v27 == v21 )
    {
      if ( !v30 )
        return 0;
      goto LABEL_13;
    }
    v13 = v26;
    ++v12;
    v22 = v26;
    if ( v12 > 0x2710 )
      goto LABEL_11;
  }
  if ( !(unsigned int)Wow64FindModuleEx(hProcess) )
    return 0;
LABEL_13:
  v15 = 2 * nSize;
  v16 = v28 + 2;
  NumberOfBytesRead = 0;
  v17 = 2 * nSize;
  if ( 2 * nSize >= v16 )
    v17 = v16;
  v10 = NtReadVirtualMemory(hProcess, BaseAddress, lpBaseName, (unsigned int)v17, &NumberOfBytesRead);
  if ( v10 < 0 )
    goto LABEL_22;
  v18 = v17 - 2;
  if ( v17 != v28 + 2LL )
    v18 = v17;
  if ( v18 >= v15 )
  {
    if ( v15 )
      lpBaseName[((unsigned __int64)v15 >> 1) - 1] = 0;
  }
  else
  {
    lpBaseName[(unsigned __int64)v18 >> 1] = 0;
  }
  return v18 >> 1;
}

```

## disassembly

```asm
0x1800b7200  push    rbp; GetModuleBaseNameW
0x1800b7202  push    rbx
0x1800b7203  push    rsi
0x1800b7204  push    rdi
0x1800b7205  push    r12
0x1800b7207  push    r13
0x1800b7209  push    r14
0x1800b720b  push    r15
0x1800b720d  lea     rbp, [rsp-28h]
0x1800b7212  sub     rsp, 128h
0x1800b7219  mov     rax, cs:__security_cookie
0x1800b7220  xor     rax, rsp
0x1800b7223  mov     [rbp+60h+var_50], rax
0x1800b7227  mov     r14, r8
0x1800b722a  mov     rbx, rdx
0x1800b722d  mov     rdi, rcx
0x1800b7230  xor     edx, edx; Val
0x1800b7232  mov     r8d, 88h; Size
0x1800b7238  lea     rcx, [rbp+60h+var_E0]; void *
0x1800b723c  mov     r15d, r9d
0x1800b723f  call    memset_0
0x1800b7244  xorps   xmm0, xmm0
0x1800b7247  mov     [rsp+160h+var_128], rbx
0x1800b724c  xor     r12d, r12d
0x1800b724f  lea     r8, [rsp+160h+ProcessInformation]; ProcessInformation
0x1800b7254  xor     eax, eax
0x1800b7256  mov     [rsp+160h+Buffer], r12
0x1800b725b  movups  xmmword ptr [rsp+160h+var_100], xmm0
0x1800b7260  xor     edx, edx; ProcessInformationClass
0x1800b7262  mov     [rsp+160h+var_120], r12
0x1800b7267  mov     rcx, rdi; ProcessHandle
0x1800b726a  mov     [rsp+160h+ReturnLength], r12; ReturnLength
0x1800b726f  lea     r9d, [rax+30h]; ProcessInformationLength
0x1800b7273  movups  [rsp+160h+ProcessInformation], xmm0
0x1800b7278  movups  xmmword ptr [rsp+160h+var_100+0Ch], xmm0
0x1800b727d  call    cs:__imp_NtQueryInformationProcess
0x1800b7284  nop     dword ptr [rax+rax+00h]
0x1800b7289  test    eax, eax
0x1800b728b  js      loc_1800B747D
0x1800b7291  lea     r13d, [r12+8]
0x1800b7296  mov     rbx, qword ptr [rsp+160h+ProcessInformation+8]
0x1800b729b  cmp     [rsp+160h+var_128], r12
0x1800b72a0  jz      loc_1800B7420
0x1800b72a6  lea     rax, [rsp+160h+NumberOfBytesRead]
0x1800b72ab  mov     [rsp+160h+NumberOfBytesRead], r12
0x1800b72b0  lea     rdx, [rbx+18h]; BaseAddress
0x1800b72b4  mov     [rsp+160h+ReturnLength], rax; NumberOfBytesRead
0x1800b72b9  mov     r9, r13; NumberOfBytesToRead
0x1800b72bc  lea     r8, [rsp+160h+Buffer]; Buffer
0x1800b72c1  mov     rcx, rdi; ProcessHandle
0x1800b72c4  call    cs:__imp_NtReadVirtualMemory
0x1800b72cb  nop     dword ptr [rax+rax+00h]
0x1800b72d0  test    eax, eax
0x1800b72d2  js      loc_1800B7452
0x1800b72d8  mov     rax, [rsp+160h+Buffer]
0x1800b72dd  test    rax, rax
0x1800b72e0  jz      loc_1800B7383
0x1800b72e6  lea     rsi, [rax+20h]
0x1800b72ea  mov     [rsp+160h+NumberOfBytesRead], r12
0x1800b72ef  lea     rax, [rsp+160h+NumberOfBytesRead]
0x1800b72f4  mov     rdx, rsi; BaseAddress
0x1800b72f7  mov     r9, r13; NumberOfBytesToRead
0x1800b72fa  mov     [rsp+160h+ReturnLength], rax; NumberOfBytesRead
0x1800b72ff  lea     r8, [rsp+160h+var_120]; Buffer
0x1800b7304  mov     rcx, rdi; ProcessHandle
0x1800b7307  call    cs:__imp_NtReadVirtualMemory
0x1800b730e  nop     dword ptr [rax+rax+00h]
0x1800b7313  test    eax, eax
0x1800b7315  js      loc_1800B7452
0x1800b731b  mov     rdx, [rsp+160h+var_128]
0x1800b7320  mov     ebx, r12d
0x1800b7323  mov     rax, [rsp+160h+var_120]
0x1800b7328  lea     r8, [rbp+60h+var_E0]; Buffer
0x1800b732c  mov     rcx, rdi; ProcessHandle
0x1800b732f  cmp     rax, rsi
0x1800b7332  jz      loc_1800B746E
0x1800b7338  lea     rdx, [rax-10h]; BaseAddress
0x1800b733c  mov     [rsp+160h+NumberOfBytesRead], r12
0x1800b7341  lea     rax, [rsp+160h+NumberOfBytesRead]
0x1800b7346  mov     r9d, 88h; NumberOfBytesToRead
0x1800b734c  mov     [rsp+160h+ReturnLength], rax; NumberOfBytesRead
0x1800b7351  call    cs:__imp_NtReadVirtualMemory
0x1800b7358  nop     dword ptr [rax+rax+00h]
0x1800b735d  test    eax, eax
0x1800b735f  js      loc_1800B7452
0x1800b7365  mov     rdx, [rsp+160h+var_128]
0x1800b736a  cmp     [rbp+60h+var_B0], rdx
0x1800b736e  jz      short loc_1800B738D
0x1800b7370  mov     rax, [rbp+60h+var_D0]
0x1800b7374  inc     ebx
0x1800b7376  mov     [rsp+160h+var_120], rax
0x1800b737b  cmp     ebx, 2710h
0x1800b7381  jbe     short loc_1800B7328
0x1800b7383  mov     ecx, 6
0x1800b7388  jmp     loc_1800B748D
0x1800b738d  cmp     [rbp+60h+var_74], r12w
0x1800b7392  jz      loc_1800B7459
0x1800b7398  movzx   edx, [rbp+60h+var_88]
0x1800b739c  lea     ebx, [r15+r15]
0x1800b73a0  add     edx, 2
0x1800b73a3  mov     [rsp+160h+NumberOfBytesRead], r12
0x1800b73a8  cmp     ebx, edx
0x1800b73aa  lea     rax, [rsp+160h+NumberOfBytesRead]
0x1800b73af  mov     esi, ebx
0x1800b73b1  mov     [rsp+160h+ReturnLength], rax; NumberOfBytesRead
0x1800b73b6  cmovnb  esi, edx
0x1800b73b9  mov     r8, r14; Buffer
0x1800b73bc  mov     rdx, [rbp+60h+BaseAddress]; BaseAddress
0x1800b73c0  mov     r9d, esi; NumberOfBytesToRead
0x1800b73c3  mov     rcx, rdi; ProcessHandle
0x1800b73c6  call    cs:__imp_NtReadVirtualMemory
0x1800b73cd  nop     dword ptr [rax+rax+00h]
0x1800b73d2  test    eax, eax
0x1800b73d4  js      short loc_1800B7452
0x1800b73d6  movzx   eax, [rbp+60h+var_88]
0x1800b73da  lea     r8d, [rsi-2]
0x1800b73de  add     rax, 2
0x1800b73e2  cmp     rsi, rax
0x1800b73e5  cmovnz  r8d, esi
0x1800b73e9  cmp     r8d, ebx
0x1800b73ec  jnb     short loc_1800B745D
0x1800b73ee  mov     ecx, r8d
0x1800b73f1  shr     rcx, 1
0x1800b73f4  mov     [r14+rcx*2], r12w
0x1800b73f9  shr     r8d, 1
0x1800b73fc  mov     eax, r8d
0x1800b73ff  mov     rcx, [rbp+60h+var_50]
0x1800b7403  xor     rcx, rsp; StackCookie
0x1800b7406  call    __security_check_cookie
0x1800b740b  add     rsp, 128h
0x1800b7412  pop     r15
0x1800b7414  pop     r14
0x1800b7416  pop     r13
0x1800b7418  pop     r12
0x1800b741a  pop     rdi
0x1800b741b  pop     rsi
0x1800b741c  pop     rbx
0x1800b741d  pop     rbp
0x1800b741e  retn
0x1800b7420  lea     rax, [rsp+160h+NumberOfBytesRead]
0x1800b7425  mov     [rsp+160h+NumberOfBytesRead], r12
0x1800b742a  lea     rdx, [rbx+10h]; BaseAddress
0x1800b742e  mov     [rsp+160h+ReturnLength], rax; NumberOfBytesRead
0x1800b7433  mov     r9, r13; NumberOfBytesToRead
0x1800b7436  lea     r8, [rsp+160h+var_128]; Buffer
0x1800b743b  mov     rcx, rdi; ProcessHandle
0x1800b743e  call    cs:__imp_NtReadVirtualMemory
0x1800b7445  nop     dword ptr [rax+rax+00h]
0x1800b744a  test    eax, eax
0x1800b744c  jns     loc_1800B72A6
0x1800b7452  mov     ecx, eax
0x1800b7454  call    BaseSetLastNTError
0x1800b7459  xor     eax, eax
0x1800b745b  jmp     short loc_1800B73FF
0x1800b745d  test    ebx, ebx
0x1800b745f  jz      short loc_1800B73F9
0x1800b7461  mov     edx, ebx
0x1800b7463  shr     rdx, 1
0x1800b7466  mov     [r14+rdx*2-2], r12w
0x1800b746c  jmp     short loc_1800B73F9
0x1800b746e  call    Wow64FindModuleEx
0x1800b7473  test    eax, eax
0x1800b7475  jnz     loc_1800B7398
0x1800b747b  jmp     short loc_1800B7459
0x1800b747d  mov     ecx, eax; Status
0x1800b747f  call    cs:__imp_RtlNtStatusToDosError
0x1800b7486  nop     dword ptr [rax+rax+00h]
0x1800b748b  mov     ecx, eax; dwErrCode
0x1800b748d  call    SetLastError_0
0x1800b7492  jmp     short loc_1800B7459
```
