# Accommodation::FindProcess(ushort const *,void * *,int)

- ea: `0x140021580`
- end: `0x14002171d`
- name: `?FindProcess@Accommodation@@SAKPEBGPEAPEAXH@Z`
- size: `413`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, void **, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140021724`

## callees

- `0x140021580`
- `0x140025d70`
- `0x140025e30`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400216d8`
- `KERNEL32!CloseHandle` at `0x1400216d8`
- `KERNEL32!K32GetModuleBaseNameW` at `0x1400216b7`
- `KERNEL32!K32GetModuleBaseNameW` at `0x1400216b7`
- `KERNEL32!K32EnumProcessModules` at `0x140021698`
- `KERNEL32!K32EnumProcessModules` at `0x140021698`
- `KERNEL32!K32EnumProcesses` at `0x1400215da`
- `KERNEL32!K32EnumProcesses` at `0x1400215da`
- `KERNEL32!GetCurrentProcessId` at `0x140021600`
- `KERNEL32!GetCurrentProcessId` at `0x140021600`
- `KERNEL32!ProcessIdToSessionId` at `0x140021618`
- `KERNEL32!ProcessIdToSessionId` at `0x140021641`
- `KERNEL32!ProcessIdToSessionId` at `0x140021618`
- `KERNEL32!ProcessIdToSessionId` at `0x140021641`
- `KERNEL32!OpenProcess` at `0x14002166e`
- `KERNEL32!OpenProcess` at `0x14002166e`
- `msvcrt!_wcsicmp` at `0x1400216cb`
- `msvcrt!_wcsicmp` at `0x1400216cb`

## pseudocode

```c
__int64 __fastcall Accommodation::FindProcess(const unsigned __int16 *a1, void **a2)
{
  DWORD CurrentProcessId; // eax
  DWORD v5; // r15d
  DWORD v6; // esi
  __int64 i; // rbx
  DWORD v8; // ecx
  DWORD v9; // r8d
  HANDLE v10; // rax
  void *v11; // rdi
  DWORD cbNeeded; // [rsp+20h] [rbp-E0h] BYREF
  DWORD pSessionId; // [rsp+24h] [rbp-DCh] BYREF
  DWORD v15; // [rsp+28h] [rbp-D8h] BYREF
  DWORD v16; // [rsp+2Ch] [rbp-D4h] BYREF
  HMODULE hModule; // [rsp+30h] [rbp-D0h] BYREF
  DWORD idProcess[2048]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR BaseName[264]; // [rsp+2040h] [rbp+1F40h] BYREF

  *a2 = 0;
  cbNeeded = 0;
  if ( !K32EnumProcesses(idProcess, 0x2000u, &cbNeeded) )
    return 0;
  cbNeeded >>= 2;
  if ( cbNeeded > 0x800 )
    cbNeeded = 2048;
  CurrentProcessId = GetCurrentProcessId();
  pSessionId = 0;
  v5 = CurrentProcessId;
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    return 0;
  v6 = 0;
  for ( i = 0; (unsigned int)i < cbNeeded; i = (unsigned int)(i + 1) )
  {
    v8 = idProcess[i];
    v15 = 0;
    if ( ProcessIdToSessionId(v8, &v15) )
    {
      if ( v15 == pSessionId )
      {
        v9 = idProcess[i];
        if ( v5 != v9 )
        {
          v10 = OpenProcess(0x410u, 0, v9);
          v11 = v10;
          if ( v10 )
          {
            hModule = 0;
            v16 = 0;
            if ( K32EnumProcessModules(v10, &hModule, 8u, &v16)
              && K32GetModuleBaseNameW(v11, hModule, BaseName, 0x104u)
              && !_wcsicmp(BaseName, a1) )
            {
              v6 = idProcess[i];
              *a2 = v11;
              return v6;
            }
            CloseHandle(v11);
          }
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x140021580  mov     [rsp-8+arg_10], rbx
0x140021585  push    rbp
0x140021586  push    rsi
0x140021587  push    rdi
0x140021588  push    r12
0x14002158a  push    r13
0x14002158c  push    r14
0x14002158e  push    r15
0x140021590  lea     rbp, [rsp-2160h]
0x140021598  mov     eax, 2260h
0x14002159d  call    _alloca_probe
0x1400215a2  sub     rsp, rax
0x1400215a5  mov     rax, cs:__security_cookie
0x1400215ac  xor     rax, rsp
0x1400215af  mov     [rbp+2190h+var_40], rax
0x1400215b6  mov     r12, rdx
0x1400215b9  mov     qword ptr [rdx], 0
0x1400215c0  mov     r13, rcx
0x1400215c3  mov     [rsp+2290h+cbNeeded], 0
0x1400215cb  mov     edx, 2000h; cb
0x1400215d0  lea     rcx, [rsp+2290h+idProcess]; lpidProcess
0x1400215d5  lea     r8, [rsp+2290h+cbNeeded]; lpcbNeeded
0x1400215da  call    cs:__imp_K32EnumProcesses
0x1400215e0  test    eax, eax
0x1400215e2  jz      loc_1400216F1
0x1400215e8  mov     eax, [rsp+2290h+cbNeeded]
0x1400215ec  mov     ecx, 800h
0x1400215f1  shr     eax, 2
0x1400215f4  mov     [rsp+2290h+cbNeeded], eax
0x1400215f8  cmp     eax, ecx
0x1400215fa  jbe     short loc_140021600
0x1400215fc  mov     [rsp+2290h+cbNeeded], ecx
0x140021600  call    cs:__imp_GetCurrentProcessId
0x140021606  lea     rdx, [rsp+2290h+pSessionId]; pSessionId
0x14002160b  mov     [rsp+2290h+pSessionId], 0
0x140021613  mov     ecx, eax; dwProcessId
0x140021615  mov     r15d, eax
0x140021618  call    cs:__imp_ProcessIdToSessionId
0x14002161e  test    eax, eax
0x140021620  jz      loc_1400216F1
0x140021626  xor     esi, esi
0x140021628  xor     ebx, ebx
0x14002162a  cmp     ebx, [rsp+2290h+cbNeeded]
0x14002162e  jnb     loc_1400216ED
0x140021634  mov     ecx, [rsp+rbx*4+2290h+idProcess]; dwProcessId
0x140021638  lea     rdx, [rsp+2290h+var_2268]; pSessionId
0x14002163d  mov     [rsp+2290h+var_2268], esi
0x140021641  call    cs:__imp_ProcessIdToSessionId
0x140021647  test    eax, eax
0x140021649  jz      loc_1400216DE
0x14002164f  mov     eax, [rsp+2290h+pSessionId]
0x140021653  cmp     [rsp+2290h+var_2268], eax
0x140021657  jnz     loc_1400216DE
0x14002165d  mov     r8d, [rsp+rbx*4+2290h+idProcess]; dwProcessId
0x140021662  cmp     r15d, r8d
0x140021665  jz      short loc_1400216DE
0x140021667  xor     edx, edx; bInheritHandle
0x140021669  mov     ecx, 410h; dwDesiredAccess
0x14002166e  call    cs:__imp_OpenProcess
0x140021674  mov     rdi, rax
0x140021677  test    rax, rax
0x14002167a  jz      short loc_1400216DE
0x14002167c  lea     r9, [rsp+2290h+var_2264]; lpcbNeeded
0x140021681  mov     [rsp+2290h+hModule], rsi
0x140021686  mov     r8d, 8; cb
0x14002168c  mov     [rsp+2290h+var_2264], esi
0x140021690  lea     rdx, [rsp+2290h+hModule]; lphModule
0x140021695  mov     rcx, rax; hProcess
0x140021698  call    cs:__imp_K32EnumProcessModules
0x14002169e  test    eax, eax
0x1400216a0  jz      short loc_1400216D5
0x1400216a2  mov     rdx, [rsp+2290h+hModule]; hModule
0x1400216a7  lea     r8, [rbp+2190h+BaseName]; lpBaseName
0x1400216ae  mov     r9d, 104h; nSize
0x1400216b4  mov     rcx, rdi; hProcess
0x1400216b7  call    cs:__imp_K32GetModuleBaseNameW
0x1400216bd  test    eax, eax
0x1400216bf  jz      short loc_1400216D5
0x1400216c1  mov     rdx, r13; String2
0x1400216c4  lea     rcx, [rbp+2190h+BaseName]; String1
0x1400216cb  call    cs:__imp__wcsicmp
0x1400216d1  test    eax, eax
0x1400216d3  jz      short loc_1400216E5
0x1400216d5  mov     rcx, rdi; hObject
0x1400216d8  call    cs:__imp_CloseHandle
0x1400216de  inc     ebx
0x1400216e0  jmp     loc_14002162A
0x1400216e5  mov     esi, [rsp+rbx*4+2290h+idProcess]
0x1400216e9  mov     [r12], rdi
0x1400216ed  mov     eax, esi
0x1400216ef  jmp     short loc_1400216F3
0x1400216f1  xor     eax, eax
0x1400216f3  mov     rcx, [rbp+2190h+var_40]
0x1400216fa  xor     rcx, rsp; StackCookie
0x1400216fd  call    __security_check_cookie
0x140021702  mov     rbx, [rsp+2290h+arg_10]
0x14002170a  add     rsp, 2260h
0x140021711  pop     r15
0x140021713  pop     r14
0x140021715  pop     r13
0x140021717  pop     r12
0x140021719  pop     rdi
0x14002171a  pop     rsi
0x14002171b  pop     rbp
0x14002171c  retn
```
