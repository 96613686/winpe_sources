# MachineProfile::_Initialize(void)

- ea: `0x180035a34`
- end: `0x180035bdc`
- name: `?_Initialize@MachineProfile@@AEAAXXZ`
- size: `424`
- prototype: `void __fastcall(MachineProfile *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035348`

## callees

- `0x180004f90`
- `0x180005588`
- `0x18000c230`
- `0x180035a34`
- `0x180036004`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035aca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035aca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035b05`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035b43`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035b05`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180035b43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035a98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035a98`

## pseudocode

```c
void __fastcall MachineProfile::_Initialize(MachineProfile *this)
{
  HKEY *v2; // rdi
  HKEY v3; // rsi
  HKEY v4; // rcx
  HKEY v5; // rcx
  LSTATUS v6; // edi
  __int64 v7; // r8
  int phkResult; // [rsp+20h] [rbp-10h]
  DWORD Type; // [rsp+60h] [rbp+30h] BYREF
  int Data; // [rsp+68h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+40h] BYREF
  DWORD lpcbData; // [rsp+78h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 12, &WPP_1cf9d866e54432687271528bd30a9afa_Traceguids);
  }
  v2 = (HKEY *)((char *)this + 8);
  *((_DWORD *)this + 4) = 0;
  v3 = (HKEY)*((_QWORD *)this + 1);
  if ( v3 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&Type);
    RegCloseKey(v3);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&Type);
  }
  *v2 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\dot3svc\\MigrationData\\dot3svc", 0, 0x2001Fu, v2) )
  {
    Type = 0;
    v4 = *v2;
    cbData = 520;
    if ( !RegQueryValueExW(v4, L"ProfileList", 0, &Type, (LPBYTE)this + 20, &cbData) )
    {
      v5 = *v2;
      Data = 0;
      *(_BYTE *)this = 1;
      lpcbData = 4;
      v6 = RegQueryValueExW(v5, L"machineProfileMigrationStatus", 0, &Type, (LPBYTE)&Data, &lpcbData);
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        LOBYTE(phkResult) = *(_BYTE *)this;
        WPP_SF_Dc(WPP_GLOBAL_Control[1].Flink, 13, v7, *((unsigned int *)this + 4), phkResult);
      }
      if ( v6 )
      {
        if ( v6 == 2 || v6 == 1168 )
          *((_DWORD *)this + 4) = 1;
        else
          *((_DWORD *)this + 4) = 3;
      }
      else
      {
        *((_DWORD *)this + 4) = Data;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 14, &WPP_1cf9d866e54432687271528bd30a9afa_Traceguids);
  }
}

```

## disassembly

```asm
0x180035a34  push    rbp
0x180035a36  push    rbx
0x180035a37  push    rsi
0x180035a38  push    rdi
0x180035a39  push    r12
0x180035a3b  mov     rbp, rsp
0x180035a3e  sub     rsp, 30h
0x180035a42  mov     rbx, rcx
0x180035a45  mov     rcx, cs:WPP_GLOBAL_Control
0x180035a4c  lea     r12, WPP_GLOBAL_Control
0x180035a53  cmp     rcx, r12
0x180035a56  jz      short loc_180035A79
0x180035a58  cmp     byte ptr [rcx+19h], 4
0x180035a5c  jb      short loc_180035A79
0x180035a5e  test    byte ptr [rcx+1Ch], 1
0x180035a62  jz      short loc_180035A79
0x180035a64  mov     rcx, [rcx+10h]
0x180035a68  lea     r8, WPP_1cf9d866e54432687271528bd30a9afa_Traceguids
0x180035a6f  mov     edx, 0Ch
0x180035a74  call    WPP_SF_
0x180035a79  lea     rdi, [rbx+8]
0x180035a7d  mov     dword ptr [rbx+10h], 0
0x180035a84  mov     rsi, [rdi]
0x180035a87  test    rsi, rsi
0x180035a8a  jz      short loc_180035AA7
0x180035a8c  lea     rcx, [rbp+Type]; this
0x180035a90  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180035a95  mov     rcx, rsi; hKey
0x180035a98  call    cs:__imp_RegCloseKey
0x180035a9e  lea     rcx, [rbp+Type]; this
0x180035aa2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180035aa7  mov     r9d, 2001Fh; samDesired
0x180035aad  mov     qword ptr [rdi], 0
0x180035ab4  xor     r8d, r8d; ulOptions
0x180035ab7  mov     [rsp+30h+phkResult], rdi; phkResult
0x180035abc  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\dot3svc\\Migration"...
0x180035ac3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035aca  call    cs:__imp_RegOpenKeyExW
0x180035ad0  test    eax, eax
0x180035ad2  jnz     loc_180035BA4
0x180035ad8  lea     rcx, [rbp+cbData]
0x180035adc  mov     [rbp+Type], eax
0x180035adf  mov     [rsp+30h+lpcbData], rcx; lpcbData
0x180035ae4  lea     rax, [rbx+14h]
0x180035ae8  mov     rcx, [rdi]; hKey
0x180035aeb  lea     r9, [rbp+Type]; lpType
0x180035aef  xor     r8d, r8d; lpReserved
0x180035af2  mov     [rbp+cbData], 208h
0x180035af9  lea     rdx, aProfilelist; "ProfileList"
0x180035b00  mov     [rsp+30h+phkResult], rax; lpData
0x180035b05  call    cs:__imp_RegQueryValueExW
0x180035b0b  test    eax, eax
0x180035b0d  jnz     loc_180035BA4
0x180035b13  mov     rcx, [rdi]; hKey
0x180035b16  lea     r9, [rbp+Type]; lpType
0x180035b1a  mov     [rbp+Data], eax
0x180035b1d  lea     rdx, aMachineprofile; "machineProfileMigrationStatus"
0x180035b24  lea     rax, [rbp+arg_18]
0x180035b28  mov     byte ptr [rbx], 1
0x180035b2b  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180035b30  xor     r8d, r8d; lpReserved
0x180035b33  lea     rax, [rbp+Data]
0x180035b37  mov     [rbp+arg_18], 4
0x180035b3e  mov     [rsp+30h+phkResult], rax; lpData
0x180035b43  call    cs:__imp_RegQueryValueExW
0x180035b49  mov     edi, eax
0x180035b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b52  cmp     rcx, r12
0x180035b55  jz      short loc_180035B7B
0x180035b57  cmp     byte ptr [rcx+19h], 3
0x180035b5b  jb      short loc_180035B7B
0x180035b5d  test    byte ptr [rcx+1Ch], 1
0x180035b61  jz      short loc_180035B7B
0x180035b63  mov     al, [rbx]
0x180035b65  mov     edx, 0Dh
0x180035b6a  mov     r9d, [rbx+10h]
0x180035b6e  mov     rcx, [rcx+10h]
0x180035b72  mov     byte ptr [rsp+30h+phkResult], al
0x180035b76  call    WPP_SF_Dc
0x180035b7b  test    edi, edi
0x180035b7d  jz      short loc_180035B9E
0x180035b7f  cmp     edi, 2
0x180035b82  jz      short loc_180035B95
0x180035b84  cmp     edi, 490h
0x180035b8a  jz      short loc_180035B95
0x180035b8c  mov     dword ptr [rbx+10h], 3
0x180035b93  jmp     short loc_180035BA4
0x180035b95  mov     dword ptr [rbx+10h], 1
0x180035b9c  jmp     short loc_180035BA4
0x180035b9e  mov     eax, [rbp+Data]
0x180035ba1  mov     [rbx+10h], eax
0x180035ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x180035bab  cmp     rcx, r12
0x180035bae  jz      short loc_180035BD1
0x180035bb0  cmp     byte ptr [rcx+19h], 4
0x180035bb4  jb      short loc_180035BD1
0x180035bb6  test    byte ptr [rcx+1Ch], 1
0x180035bba  jz      short loc_180035BD1
0x180035bbc  mov     rcx, [rcx+10h]
0x180035bc0  lea     r8, WPP_1cf9d866e54432687271528bd30a9afa_Traceguids
0x180035bc7  mov     edx, 0Eh
0x180035bcc  call    WPP_SF_
0x180035bd1  add     rsp, 30h
0x180035bd5  pop     r12
0x180035bd7  pop     rdi
0x180035bd8  pop     rsi
0x180035bd9  pop     rbx
0x180035bda  pop     rbp
0x180035bdb  retn
```
