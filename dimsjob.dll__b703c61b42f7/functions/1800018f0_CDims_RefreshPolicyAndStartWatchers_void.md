# CDims::RefreshPolicyAndStartWatchers(void)

- ea: `0x1800018f0`
- end: `0x180001b13`
- name: `?RefreshPolicyAndStartWatchers@CDims@@QEAAXXZ`
- size: `547`
- prototype: `void __fastcall(CDims *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001410`
- `0x1800078e0`

## callees

- `0x1800018f0`
- `0x180009af4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001a06`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001a49`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001a88`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001a06`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001a49`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001a88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800019a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800019a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001969`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001969`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800019bf`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001917`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180001917`

## string_xrefs

- `0x180001a38`: `UserTaskRoamEnabled`

## pseudocode

```c
void __fastcall CDims::RefreshPolicyAndStartWatchers(CDims *this)
{
  char *v2; // rdi
  __int32 v3; // r15d
  __int32 v4; // r14d
  __int32 v5; // esi
  HKEY v6; // rcx
  int v7; // edx
  __int32 Data; // [rsp+70h] [rbp+20h] BYREF
  DWORD Type; // [rsp+78h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF

  v2 = (char *)this + *(int *)(*((_QWORD *)this + 8) + 12LL) + 64;
  RtlAcquireSRWLockExclusive(&v2[*(int *)(*(_QWORD *)v2 + 4LL)]);
  if ( *((_BYTE *)this + 220) )
    goto LABEL_7;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  if ( RegOpenKeyExW(
         (HKEY)((*((_BYTE *)this + 8) != 0) - 0x7FFFFFFFLL),
         L"SOFTWARE\\Policies\\Microsoft\\Cryptography\\AutoEnrollment",
         0,
         1u,
         &hKey) )
  {
    hKey = 0;
  }
  else
  {
    v6 = hKey;
    if ( hKey )
    {
      if ( !*((_BYTE *)this + 8) )
      {
        Data = 0;
        Type = 0;
        cbData = 4;
        if ( !RegQueryValueExW(hKey, L"DIMSRoaming", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
          v4 = Data;
        else
          Data = 0;
        Data = 0;
        Type = 0;
        cbData = 4;
        if ( !RegQueryValueExW(hKey, L"UserTaskRoamEnabled", 0, &Type, (LPBYTE)&Data, &cbData)
          && Type == 4
          && cbData == 4 )
        {
          v3 = Data;
        }
        else
        {
          Data = 0;
        }
        v6 = hKey;
      }
      Data = 0;
      Type = 0;
      cbData = 4;
      if ( !RegQueryValueExW(v6, L"AEPolicy", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
        v5 = Data;
      else
        Data = 0;
    }
  }
  _InterlockedExchange((volatile __int32 *)this + 50, v4);
  _InterlockedExchange((volatile __int32 *)this + 51, v5);
  if ( !*((_BYTE *)this + 8) )
  {
    if ( (v4 & 1) != 0 )
    {
      if ( v3 )
        goto LABEL_5;
      v7 = 1;
    }
    else
    {
      if ( !v3 )
        goto LABEL_5;
      v7 = 0;
    }
    CDims::p_EnableSchedule((CDims *)v6, v7);
  }
LABEL_5:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_7:
  RtlReleaseSRWLockExclusive(&v2[*(int *)(*(_QWORD *)v2 + 4LL)]);
}

```

## disassembly

```asm
0x1800018f0  push    rbp
0x1800018f2  push    rbx
0x1800018f3  push    rdi
0x1800018f4  mov     rbp, rsp
0x1800018f7  sub     rsp, 50h
0x1800018fb  mov     rax, [rcx+40h]
0x1800018ff  mov     rbx, rcx
0x180001902  movsxd  rcx, dword ptr [rax+0Ch]
0x180001906  lea     rdi, [rbx+40h]
0x18000190a  add     rdi, rcx
0x18000190d  mov     rax, [rdi]
0x180001910  movsxd  rcx, dword ptr [rax+4]
0x180001914  add     rcx, rdi
0x180001917  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000191d  cmp     byte ptr [rbx+0DCh], 0
0x180001924  jnz     loc_1800019AE
0x18000192a  xor     ecx, ecx
0x18000192c  mov     [rsp+50h+var_8], rsi
0x180001931  mov     [rsp+50h+var_10], r14
0x180001936  lea     rax, [rbp+hKey]
0x18000193a  mov     [rsp+50h+var_18], r15
0x18000193f  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Cryptogr"...
0x180001946  xor     r15d, r15d
0x180001949  mov     [rsp+50h+phkResult], rax; phkResult
0x18000194e  xor     r14d, r14d
0x180001951  xor     esi, esi
0x180001953  cmp     [rbx+8], cl
0x180001956  mov     r9d, 1; samDesired
0x18000195c  setnz   cl
0x18000195f  xor     r8d, r8d; ulOptions
0x180001962  add     rcx, 0FFFFFFFF80000001h; hKey
0x180001969  call    cs:__imp_RegOpenKeyExW
0x18000196f  test    eax, eax
0x180001971  jz      short loc_1800019C6
0x180001973  mov     [rbp+hKey], rsi
0x180001977  mov     eax, r14d
0x18000197a  xchg    eax, [rbx+0C8h]
0x180001980  xchg    esi, [rbx+0CCh]
0x180001986  cmp     byte ptr [rbx+8], 0
0x18000198a  mov     rsi, [rsp+50h+var_8]
0x18000198f  jz      loc_180001A9A
0x180001995  mov     rcx, [rbp+hKey]; hKey
0x180001999  mov     r15, [rsp+50h+var_18]
0x18000199e  mov     r14, [rsp+50h+var_10]
0x1800019a3  test    rcx, rcx
0x1800019a6  jz      short loc_1800019AE
0x1800019a8  call    cs:__imp_RegCloseKey
0x1800019ae  mov     rax, [rdi]
0x1800019b1  movsxd  rcx, dword ptr [rax+4]
0x1800019b5  add     rcx, rdi
0x1800019b8  add     rsp, 50h
0x1800019bc  pop     rdi
0x1800019bd  pop     rbx
0x1800019be  pop     rbp
0x1800019bf  jmp     cs:__imp_RtlReleaseSRWLockExclusive
0x1800019c6  mov     rcx, [rbp+hKey]; hKey
0x1800019ca  test    rcx, rcx
0x1800019cd  jz      short loc_180001977
0x1800019cf  cmp     [rbx+8], sil
0x1800019d3  jnz     loc_180001A5B
0x1800019d9  lea     rax, [rbp+cbData]
0x1800019dd  mov     [rbp+Data], esi
0x1800019e0  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800019e5  lea     r9, [rbp+Type]; lpType
0x1800019e9  lea     rax, [rbp+Data]
0x1800019ed  mov     [rbp+Type], esi
0x1800019f0  xor     r8d, r8d; lpReserved
0x1800019f3  mov     [rsp+50h+phkResult], rax; lpData
0x1800019f8  lea     rdx, aDimsroaming; "DIMSRoaming"
0x1800019ff  mov     [rbp+cbData], 4
0x180001a06  call    cs:__imp_RegQueryValueExW
0x180001a0c  test    eax, eax
0x180001a0e  jz      loc_180001AB5
0x180001a14  mov     [rbp+Data], r14d
0x180001a18  mov     rcx, [rbp+hKey]; hKey
0x180001a1c  lea     rax, [rbp+cbData]
0x180001a20  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180001a25  lea     r9, [rbp+Type]; lpType
0x180001a29  lea     rax, [rbp+Data]
0x180001a2d  mov     [rbp+Data], esi
0x180001a30  xor     r8d, r8d; lpReserved
0x180001a33  mov     [rsp+50h+phkResult], rax; lpData
0x180001a38  lea     rdx, aUsertaskroamen; "UserTaskRoamEnabled"
0x180001a3f  mov     [rbp+Type], esi
0x180001a42  mov     [rbp+cbData], 4
0x180001a49  call    cs:__imp_RegQueryValueExW
0x180001a4f  test    eax, eax
0x180001a51  jz      short loc_180001AD2
0x180001a53  mov     [rbp+Data], r15d
0x180001a57  mov     rcx, [rbp+hKey]; hKey
0x180001a5b  lea     rax, [rbp+cbData]
0x180001a5f  mov     [rbp+Data], esi
0x180001a62  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180001a67  lea     r9, [rbp+Type]; lpType
0x180001a6b  lea     rax, [rbp+Data]
0x180001a6f  mov     [rbp+Type], esi
0x180001a72  xor     r8d, r8d; lpReserved
0x180001a75  mov     [rsp+50h+phkResult], rax; lpData
0x180001a7a  lea     rdx, aAepolicy; "AEPolicy"
0x180001a81  mov     [rbp+cbData], 4
0x180001a88  call    cs:__imp_RegQueryValueExW
0x180001a8e  test    eax, eax
0x180001a90  jz      short loc_180001AEF
0x180001a92  mov     [rbp+Data], esi
0x180001a95  jmp     loc_180001977
0x180001a9a  test    r14b, 1
0x180001a9e  jnz     short loc_180001B03
0x180001aa0  test    r15d, r15d
0x180001aa3  jz      loc_180001995
0x180001aa9  xor     edx, edx; int
0x180001aab  call    ?p_EnableSchedule@CDims@@AEAAJH@Z; CDims::p_EnableSchedule(int)
0x180001ab0  jmp     loc_180001995
0x180001ab5  cmp     [rbp+Type], 4
0x180001ab9  jnz     loc_180001A14
0x180001abf  cmp     [rbp+cbData], 4
0x180001ac3  jnz     loc_180001A14
0x180001ac9  mov     r14d, [rbp+Data]
0x180001acd  jmp     loc_180001A18
0x180001ad2  cmp     [rbp+Type], 4
0x180001ad6  jnz     loc_180001A53
0x180001adc  cmp     [rbp+cbData], 4
0x180001ae0  jnz     loc_180001A53
0x180001ae6  mov     r15d, [rbp+Data]
0x180001aea  jmp     loc_180001A57
0x180001aef  cmp     [rbp+Type], 4
0x180001af3  jnz     short loc_180001A92
0x180001af5  cmp     [rbp+cbData], 4
0x180001af9  jnz     short loc_180001A92
0x180001afb  mov     esi, [rbp+Data]
0x180001afe  jmp     loc_180001977
0x180001b03  test    r15d, r15d
0x180001b06  jnz     loc_180001995
0x180001b0c  mov     edx, 1
0x180001b11  jmp     short loc_180001AAB
```
