# GetComputerNameExW

- ea: `0x1800caa90`
- end: `0x1800caff3`
- name: `GetComputerNameExW`
- size: `1379`
- prototype: `BOOL __stdcall(COMPUTER_NAME_FORMAT NameType, LPWSTR lpBuffer, LPDWORD nSize)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800ca960`
- `0x1800caa90`
- `0x18013296c`

## callees

- `0x18004b9d0`
- `0x1800ca7c8`
- `0x1800caa90`
- `0x1800caffc`
- `0x1800cb0a0`
- `0x1800cb390`
- `0x180194eb9`

## import_xrefs

- `ntdll!wcslen` at `0x1800cae59`
- `ntdll!wcslen` at `0x1800cae59`
- `ntdll!RtlEnterCriticalSection` at `0x1800cad83`
- `ntdll!RtlEnterCriticalSection` at `0x1800cad83`
- `ntdll!RtlLeaveCriticalSection` at `0x1800cae79`
- `ntdll!RtlLeaveCriticalSection` at `0x1800cae79`
- `ntdll!RtlSetLastWin32Error` at `0x1800cace3`
- `ntdll!RtlSetLastWin32Error` at `0x1801a0922`
- `ntdll!RtlSetLastWin32Error` at `0x1800cace3`
- `ntdll!RtlSetLastWin32Error` at `0x1801a0922`
- `ntdll!RtlAllocateHeap` at `0x1800cae26`
- `ntdll!RtlAllocateHeap` at `0x1800cae26`

## string_xrefs

- `0x1800cac00`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName\ActiveComputerName`
- `0x1800cabf7`: `ComputerName`
- `0x1801a093e`: `ComputerName`
- `0x1800cabb2`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x1800cabb9`: `DnscacheTcpipParameters`
- `0x1800cab8c`: `\Registry\Machine\Software\Policies\Microsoft\System\DNSClient`
- `0x1800cadad`: `\Registry\Machine\System\Setup`
- `0x1800cade4`: `\Registry\Machine\System\Setup`
- `0x1800cae9c`: `\Registry\Machine\System\CurrentControlSet\Services\CCG`
- `0x1801a0947`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName\ComputerName`

## pseudocode

```c
BOOL __stdcall GetComputerNameExW(COMPUTER_NAME_FORMAT NameType, LPWSTR lpBuffer, LPDWORD nSize)
{
  __int64 v3; // r14
  DWORD EnvironmentVariableW; // r15d
  int v7; // r15d
  BOOL v8; // edi
  int NameFromReg; // eax
  int VolatileNameInReg; // edx
  const wchar_t *v11; // r8
  int v13; // eax
  COMPUTER_NAME_FORMAT v14; // ecx
  COMPUTER_NAME_FORMAT v15; // ecx
  DWORD v16; // ecx
  DWORD v17; // r8d
  ULONG v18; // ecx
  __int64 v19; // rcx
  int v20; // eax
  wchar_t *Heap; // rax
  const wchar_t *v22; // r14
  int v23; // eax
  COMPUTER_NAME_FORMAT v24; // ecx
  int v25; // [rsp+30h] [rbp-10h] BYREF
  _DWORD v26[3]; // [rsp+34h] [rbp-Ch] BYREF
  DWORD nSizea; // [rsp+80h] [rbp+40h] BYREF
  DWORD v28; // [rsp+98h] [rbp+58h] BYREF

  v3 = NameType;
  nSizea = 0;
  v28 = 0;
  v25 = 0;
  if ( NameType >= ComputerNameMax )
  {
    v19 = 3221225485LL;
    goto LABEL_54;
  }
  if ( !nSize || !lpBuffer && *nSize )
  {
    v18 = 87;
LABEL_44:
    RtlSetLastWin32Error(v18);
    return 0;
  }
  if ( (unsigned int)NameType <= ComputerNameDnsFullyQualified )
  {
    EnvironmentVariableW = GetEnvironmentVariableW(ClusterNameVars[NameType], lpBuffer, *nSize);
    if ( EnvironmentVariableW )
    {
      if ( *nSize < EnvironmentVariableW )
      {
        v8 = 0;
        RtlSetLastWin32Error(0xEAu);
      }
      else
      {
        v8 = 1;
      }
      *nSize = EnvironmentVariableW;
      return v8;
    }
  }
  if ( !dword_1803A54A0 || (unsigned int)v3 > 2 )
  {
LABEL_7:
    if ( (v3 & 0xFFFFFFFB) == 0 && qword_1803AADE0 )
    {
      if ( *nSize >= dword_1803AADE8 + 1 )
      {
        *nSize = dword_1803AADE8;
        v8 = 1;
        memcpy_0(lpBuffer, qword_1803AADE0, 2LL * (*nSize + 1));
        return v8;
      }
      *nSize = dword_1803AADE8 + 1;
LABEL_79:
      v18 = 234;
      goto LABEL_44;
    }
    v7 = 0;
    if ( lpBuffer && *nSize )
      *lpBuffer = 0;
    v8 = 1;
    if ( (_DWORD)v3 )
    {
      switch ( (_DWORD)v3 )
      {
        case 1:
          goto LABEL_67;
        case 2:
LABEL_18:
          NameFromReg = BasepGetNameFromReg(
                          0,
                          (unsigned int)L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\System\\DNSClient",
                          (unsigned int)L"PrimaryDnsSuffix",
                          (_DWORD)lpBuffer,
                          (__int64)nSize);
          VolatileNameInReg = NameFromReg;
          if ( NameFromReg >= 0 )
            goto LABEL_26;
          if ( NameFromReg == -2147483643 )
            goto LABEL_22;
          v11 = L"Domain";
          goto LABEL_21;
        case 3:
LABEL_30:
          v14 = ComputerNamePhysicalDnsHostname;
          if ( lpBuffer )
          {
            nSizea = *nSize;
            if ( (_DWORD)v3 != 7 )
              v14 = ComputerNameDnsHostname;
            if ( GetComputerNameExW(v14, lpBuffer, &nSizea) )
            {
              ++nSizea;
              v15 = ComputerNamePhysicalDnsDomain;
              lpBuffer[nSizea - 1] = 46;
              v28 = *nSize - nSizea;
              if ( (_DWORD)v3 != 7 )
                v15 = ComputerNameDnsDomain;
              if ( GetComputerNameExW(v15, &lpBuffer[nSizea], &v28) )
              {
                v16 = v28;
                VolatileNameInReg = 0;
                if ( v28 )
                {
                  if ( v28 == 1 && lpBuffer[nSizea] == 46 )
                  {
                    v16 = 0;
                    lpBuffer[nSizea] = 0;
                    v28 = 0;
                  }
                }
                else
                {
                  lpBuffer[--nSizea] = 0;
                  v16 = v28;
                }
                v17 = v16 + nSizea;
                goto LABEL_40;
              }
              if ( NtCurrentTeb()->LastErrorValue == 234 )
              {
                VolatileNameInReg = -2147483643;
                v7 = 0;
                v17 = v28 + nSizea;
                goto LABEL_41;
              }
LABEL_69:
              v17 = 0;
              VolatileNameInReg = -1073741823;
LABEL_40:
              v7 = 1;
LABEL_41:
              *nSize = v17;
LABEL_22:
              if ( VolatileNameInReg < 0 )
              {
                if ( v7 )
                  return 0;
                goto LABEL_53;
              }
LABEL_26:
              if ( dword_1803A54A4 && (v3 & 0xFFFFFFFB) == 0 )
              {
                RtlEnterCriticalSection(&stru_1803AADF0);
                v26[0] = 4;
                if ( (int)BasepGetValueFromReg(0, L"\\Registry\\Machine\\System\\Setup", L"OOBEInProgress", &v25, v26) >= 0
                  && v25
                  || (v26[0] = 4,
                      (int)BasepGetValueFromReg(
                             0,
                             L"\\Registry\\Machine\\System\\Setup",
                             L"SystemSetupInProgress",
                             &v25,
                             v26) >= 0)
                  && v25 )
                {
                  v20 = 0;
                  dword_1803A54A4 = 0;
                }
                else
                {
                  v20 = dword_1803A54A4;
                }
                if ( v20 && !qword_1803AADE0 )
                {
                  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2LL * (*nSize + 1));
                  v22 = Heap;
                  if ( Heap )
                  {
                    memcpy_0(Heap, lpBuffer, 2LL * *nSize);
                    v22[*nSize] = 0;
                    dword_1803AADE8 = wcslen(v22);
                    qword_1803AADE0 = (PVOID)v22;
                  }
                  else
                  {
                    dword_1803A54A4 = 0;
                  }
                }
                RtlLeaveCriticalSection(&stru_1803AADF0);
              }
              return v8;
            }
            if ( NtCurrentTeb()->LastErrorValue != 234 )
              goto LABEL_69;
            v28 = 0;
          }
          else
          {
            v28 = 0;
            nSizea = 0;
            if ( (_DWORD)v3 != 7 )
              v14 = ComputerNameDnsHostname;
            GetComputerNameExW(v14, 0, &nSizea);
            if ( NtCurrentTeb()->LastErrorValue != 234 )
              return 0;
          }
          v24 = ComputerNamePhysicalDnsDomain;
          if ( (_DWORD)v3 != 7 )
            v24 = ComputerNameDnsDomain;
          GetComputerNameExW(v24, 0, &v28);
          if ( NtCurrentTeb()->LastErrorValue != 234 )
            return 0;
          VolatileNameInReg = -2147483643;
          *nSize = v28 + nSizea;
LABEL_53:
          v19 = (unsigned int)VolatileNameInReg;
LABEL_54:
          BaseSetLastNTError(v19);
          return 0;
      }
      if ( (_DWORD)v3 != 4 )
      {
        if ( (_DWORD)v3 != 5 )
        {
          if ( (_DWORD)v3 == 6 )
            goto LABEL_18;
          if ( (_DWORD)v3 != 7 )
          {
            VolatileNameInReg = -1073741811;
            goto LABEL_53;
          }
          goto LABEL_30;
        }
LABEL_67:
        v11 = L"Hostname";
LABEL_21:
        VolatileNameInReg = BasepGetNameFromReg(
                              (unsigned int)L"DnscacheTcpipParameters",
                              (unsigned int)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters",
                              (_DWORD)v11,
                              (_DWORD)lpBuffer,
                              (__int64)nSize);
        goto LABEL_22;
      }
    }
    v13 = BasepGetNameFromReg(
            0,
            (unsigned int)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\ComputerName\\ActiveComputerName",
            (unsigned int)L"ComputerName",
            (_DWORD)lpBuffer,
            (__int64)nSize);
    VolatileNameInReg = v13;
    if ( v13 >= 0 )
      goto LABEL_26;
    if ( v13 != -2147483643 )
    {
      VolatileNameInReg = BasepGetNameFromReg(
                            0,
                            (unsigned int)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\ComputerName\\ComputerName",
                            (unsigned int)L"ComputerName",
                            (_DWORD)lpBuffer,
                            (__int64)nSize);
      if ( VolatileNameInReg >= 0 )
      {
        VolatileNameInReg = BaseCreateVolatileNameInReg(lpBuffer);
        if ( (int)(VolatileNameInReg + 0x80000000) < 0 || VolatileNameInReg == -1073741790 )
          goto LABEL_26;
        dword_1803A54A4 = 0;
      }
    }
    goto LABEL_53;
  }
  v23 = BasepGetNameFromReg(
          0,
          (unsigned int)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\CCG",
          (unsigned int)EDJRegistryValues[v3],
          (_DWORD)lpBuffer,
          (__int64)nSize);
  if ( v23 < 0 )
  {
    if ( v23 == -2147483643 )
      goto LABEL_79;
    dword_1803A54A0 = 0;
    goto LABEL_7;
  }
  return 1;
}

```

## disassembly

```asm
0x1800caa90  mov     [rsp-38h+arg_8], rbx
0x1800caa95  push    rbp
0x1800caa96  push    rsi
0x1800caa97  push    rdi
0x1800caa98  push    r12
0x1800caa9a  push    r13
0x1800caa9c  push    r14
0x1800caa9e  push    r15
0x1800caaa0  mov     rbp, rsp
0x1800caaa3  sub     rsp, 40h
0x1800caaa7  xor     r12d, r12d
0x1800caaaa  movsxd  r14, ecx
0x1800caaad  mov     [rbp+nSize], r12d
0x1800caab1  mov     rbx, r8
0x1800caab4  mov     [rbp+arg_18], r12d
0x1800caab8  mov     rsi, rdx
0x1800caabb  mov     [rbp+var_10], r12d
0x1800caabf  cmp     r14d, 8
0x1800caac3  jge     loc_1800CAF21
0x1800caac9  test    rbx, rbx
0x1800caacc  jz      loc_1800CACDE
0x1800caad2  test    rdx, rdx
0x1800caad5  jz      loc_1800CACD5
0x1800caadb  lea     rax, __ImageBase
0x1800caae2  mov     rdi, r14
0x1800caae5  cmp     r14d, 3
0x1800caae9  ja      short loc_1800CAB0D
0x1800caaeb  mov     r8d, [r8]; nSize
0x1800caaee  mov     rcx, ds:rva ClusterNameVars[rax+r14*8]; lpName
0x1800caaf6  call    GetEnvironmentVariableW
0x1800caafb  mov     r15d, eax
0x1800caafe  test    eax, eax
0x1800cab00  jnz     loc_1800CAF2B
0x1800cab06  lea     rax, __ImageBase
0x1800cab0d  cmp     cs:dword_1803A54A0, r12d
0x1800cab14  mov     r13d, 80000005h
0x1800cab1a  jnz     loc_1800CAE8A
0x1800cab20  test    r14d, 0FFFFFFFBh
0x1800cab27  jz      loc_1800CACF4
0x1800cab2d  mov     r15d, r12d
0x1800cab30  test    rsi, rsi
0x1800cab33  jz      short loc_1800CAB3E
0x1800cab35  cmp     [rbx], r12d
0x1800cab38  jbe     short loc_1800CAB3E
0x1800cab3a  mov     [rsi], r12w
0x1800cab3e  mov     ecx, r14d
0x1800cab41  mov     edi, 1
0x1800cab46  test    r14d, r14d
0x1800cab49  jz      loc_1800CABEF
0x1800cab4f  sub     ecx, edi
0x1800cab51  jz      loc_1800CAEC4
0x1800cab57  sub     ecx, edi
0x1800cab59  jz      short loc_1800CAB7B
0x1800cab5b  sub     ecx, edi
0x1800cab5d  jz      loc_1800CAC38
0x1800cab63  sub     ecx, edi
0x1800cab65  jz      loc_1800CABEF
0x1800cab6b  sub     ecx, edi
0x1800cab6d  jz      loc_1800CAEC4
0x1800cab73  sub     ecx, edi
0x1800cab75  jnz     loc_1800CAC30
0x1800cab7b  mov     r9, rsi
0x1800cab7e  mov     [rsp+40h+var_20], rbx
0x1800cab83  lea     r8, aPrimarydnssuff; "PrimaryDnsSuffix"
0x1800cab8a  xor     ecx, ecx
0x1800cab8c  lea     rdx, aRegistryMachin_6; "\\Registry\\Machine\\Software\\Policies"...
0x1800cab93  call    BasepGetNameFromReg
0x1800cab98  mov     edx, eax
0x1800cab9a  test    eax, eax
0x1800cab9c  jns     short loc_1800CAC16
0x1800cab9e  cmp     eax, r13d
0x1800caba1  jz      short loc_1800CABC7
0x1800caba3  lea     r8, aDomain; "Domain"
0x1800cabaa  mov     r9, rsi
0x1800cabad  mov     [rsp+40h+var_20], rbx
0x1800cabb2  lea     rdx, aRegistryMachin_38; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800cabb9  lea     rcx, aDnscachetcpipp; "DnscacheTcpipParameters"
0x1800cabc0  call    BasepGetNameFromReg
0x1800cabc5  mov     edx, eax
0x1800cabc7  test    edx, edx
0x1800cabc9  jns     short loc_1800CAC16
0x1800cabcb  test    r15d, r15d
0x1800cabce  jz      loc_1800CAD70
0x1800cabd4  xor     eax, eax
0x1800cabd6  mov     rbx, [rsp+40h+arg_8]
0x1800cabde  add     rsp, 40h
0x1800cabe2  pop     r15
0x1800cabe4  pop     r14
0x1800cabe6  pop     r13
0x1800cabe8  pop     r12
0x1800cabea  pop     rdi
0x1800cabeb  pop     rsi
0x1800cabec  pop     rbp
0x1800cabed  retn
0x1800cabef  mov     r9, rsi
0x1800cabf2  mov     [rsp+40h+var_20], rbx
0x1800cabf7  lea     r8, aComputername_1; "ComputerName"
0x1800cabfe  xor     ecx, ecx
0x1800cac00  lea     rdx, aRegistryMachin_33; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800cac07  call    BasepGetNameFromReg
0x1800cac0c  mov     edx, eax
0x1800cac0e  test    eax, eax
0x1800cac10  js      loc_1800CAD67
0x1800cac16  cmp     cs:dword_1803A54A4, r12d
0x1800cac1d  jz      short loc_1800CAC2C
0x1800cac1f  test    r14d, 0FFFFFFFBh
0x1800cac26  jz      loc_1800CAD7C
0x1800cac2c  mov     eax, edi
0x1800cac2e  jmp     short loc_1800CABD6
0x1800cac30  cmp     ecx, edi
0x1800cac32  jnz     loc_1800CAF5B
0x1800cac38  lea     r8, [rbp+nSize]; nSize
0x1800cac3c  mov     ecx, 5
0x1800cac41  test    rsi, rsi
0x1800cac44  jz      loc_1800CAD39
0x1800cac4a  mov     eax, [rbx]
0x1800cac4c  cmp     r14d, 7
0x1800cac50  mov     rdx, rsi; lpBuffer
0x1800cac53  mov     [rbp+nSize], eax
0x1800cac56  cmovnz  ecx, edi; NameType
0x1800cac59  call    GetComputerNameExW
0x1800cac5e  test    eax, eax
0x1800cac60  jz      loc_1800CAED0
0x1800cac66  mov     eax, [rbp+nSize]
0x1800cac69  lea     r8, [rbp+arg_18]; nSize
0x1800cac6d  add     eax, edi
0x1800cac6f  mov     r15d, 2Eh ; '.'
0x1800cac75  mov     [rbp+nSize], eax
0x1800cac78  dec     eax
0x1800cac7a  lea     ecx, [r15-28h]
0x1800cac7e  mov     [rsi+rax*2], r15w
0x1800cac83  mov     eax, [rbx]
0x1800cac85  sub     eax, [rbp+nSize]
0x1800cac88  mov     [rbp+arg_18], eax
0x1800cac8b  cmp     r14d, 7
0x1800cac8f  mov     eax, [rbp+nSize]
0x1800cac92  lea     rdx, [rsi+rax*2]; lpBuffer
0x1800cac96  lea     eax, [rcx-4]
0x1800cac99  cmovnz  ecx, eax; NameType
0x1800cac9c  call    GetComputerNameExW
0x1800caca1  test    eax, eax
0x1800caca3  jz      loc_1800CAEF0
0x1800caca9  mov     ecx, [rbp+arg_18]
0x1800cacac  mov     edx, r12d
0x1800cacaf  test    ecx, ecx
0x1800cacb1  jz      loc_1800CAFA6
0x1800cacb7  cmp     ecx, edi
0x1800cacb9  jz      loc_1800CAFBB
0x1800cacbf  mov     r8d, [rbp+nSize]
0x1800cacc3  lea     r8d, [rcx+r8]
0x1800cacc7  mov     r15d, edi
0x1800cacca  mov     rax, rbx
0x1800caccd  mov     [rbx], r8d
0x1800cacd0  jmp     loc_1800CABC7
0x1800cacd5  cmp     [r8], r12d
0x1800cacd8  jbe     loc_1800CAADB
0x1800cacde  mov     ecx, 57h ; 'W'; LastError
0x1800cace3  call    cs:__imp_RtlSetLastWin32Error
0x1800cacea  nop     dword ptr [rax+rax+00h]
0x1800cacef  jmp     loc_1800CABD4
0x1800cacf4  mov     rax, cs:qword_1803AADE0
0x1800cacfb  test    rax, rax
0x1800cacfe  jz      loc_1800CAB2D
0x1800cad04  mov     ecx, cs:dword_1803AADE8
0x1800cad0a  lea     eax, [rcx+1]
0x1800cad0d  cmp     [rbx], eax
0x1800cad0f  jb      loc_1800CAF4F
0x1800cad15  mov     [rbx], ecx
0x1800cad17  mov     edi, 1
0x1800cad1c  mov     rdx, cs:qword_1803AADE0; Src
0x1800cad23  mov     rcx, rsi; void *
0x1800cad26  mov     r8d, [rbx]
0x1800cad29  add     r8d, edi
0x1800cad2c  add     r8, r8; Size
0x1800cad2f  call    memcpy_0
0x1800cad34  jmp     loc_1800CAC2C
0x1800cad39  cmp     r14d, 7
0x1800cad3d  mov     [rbp+arg_18], r12d
0x1800cad41  mov     [rbp+nSize], r12d
0x1800cad45  cmovnz  ecx, edi; NameType
0x1800cad48  xor     edx, edx; lpBuffer
0x1800cad4a  call    GetComputerNameExW
0x1800cad4f  mov     eax, gs:68h
0x1800cad57  cmp     eax, 0EAh
0x1800cad5c  jnz     loc_1800CABD4
0x1800cad62  jmp     loc_1800CAF69
0x1800cad67  cmp     eax, r13d
0x1800cad6a  jnz     loc_1801A0936
0x1800cad70  mov     ecx, edx
0x1800cad72  call    BaseSetLastNTError
0x1800cad77  jmp     loc_1800CABD4
0x1800cad7c  lea     rcx, stru_1803AADF0; CriticalSection
0x1800cad83  call    cs:__imp_RtlEnterCriticalSection
0x1800cad8a  nop     dword ptr [rax+rax+00h]
0x1800cad8f  lea     rax, [rbp+var_C]
0x1800cad93  mov     r14d, 4
0x1800cad99  lea     r9, [rbp+var_10]
0x1800cad9d  mov     [rsp+40h+var_20], rax
0x1800cada2  lea     r8, aOobeinprogress; "OOBEInProgress"
0x1800cada9  mov     [rbp+var_C], r14d
0x1800cadad  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\Setup"
0x1800cadb4  xor     ecx, ecx
0x1800cadb6  call    BasepGetValueFromReg
0x1800cadbb  test    eax, eax
0x1800cadbd  js      short loc_1800CADCA
0x1800cadbf  mov     eax, [rbp+var_10]
0x1800cadc2  test    eax, eax
0x1800cadc4  jnz     loc_1800CAFE5
0x1800cadca  lea     rax, [rbp+var_C]
0x1800cadce  mov     [rbp+var_C], r14d
0x1800cadd2  lea     r9, [rbp+var_10]
0x1800cadd6  mov     [rsp+40h+var_20], rax
0x1800caddb  lea     r8, aSystemsetupinp; "SystemSetupInProgress"
0x1800cade2  xor     ecx, ecx
0x1800cade4  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\Setup"
0x1800cadeb  call    BasepGetValueFromReg
0x1800cadf0  test    eax, eax
0x1800cadf2  jns     loc_1800CAFDA
0x1800cadf8  mov     eax, cs:dword_1803A54A4
0x1800cadfe  test    eax, eax
0x1800cae00  jz      short loc_1800CAE72
0x1800cae02  mov     rax, cs:qword_1803AADE0
0x1800cae09  test    rax, rax
0x1800cae0c  jnz     short loc_1800CAE72
0x1800cae0e  mov     r8d, [rbx]
0x1800cae11  xor     edx, edx; Flags
0x1800cae13  mov     rcx, gs:60h
0x1800cae1c  add     r8d, edi
0x1800cae1f  add     r8, r8; Size
0x1800cae22  mov     rcx, [rcx+30h]; HeapHandle
0x1800cae26  call    cs:__imp_RtlAllocateHeap
0x1800cae2d  nop     dword ptr [rax+rax+00h]
0x1800cae32  mov     r14, rax
0x1800cae35  test    rax, rax
0x1800cae38  jz      loc_1800CAF15
0x1800cae3e  mov     r8d, [rbx]
0x1800cae41  mov     rdx, rsi; Src
0x1800cae44  add     r8, r8; Size
0x1800cae47  mov     rcx, rax; void *
0x1800cae4a  call    memcpy_0
0x1800cae4f  mov     edx, [rbx]
0x1800cae51  mov     rcx, r14; String
0x1800cae54  mov     [r14+rdx*2], r12w
0x1800cae59  call    cs:__imp_wcslen
0x1800cae60  nop     dword ptr [rax+rax+00h]
0x1800cae65  mov     cs:dword_1803AADE8, eax
0x1800cae6b  mov     cs:qword_1803AADE0, r14
0x1800cae72  lea     rcx, stru_1803AADF0; CriticalSection
0x1800cae79  call    cs:__imp_RtlLeaveCriticalSection
0x1800cae80  nop     dword ptr [rax+rax+00h]
0x1800cae85  jmp     loc_1800CAC2C
0x1800cae8a  cmp     r14d, 2
0x1800cae8e  ja      loc_1800CAB20
0x1800cae94  mov     r8, ds:rva EDJRegistryValues[rax+rdi*8]
0x1800cae9c  lea     rdx, aRegistryMachin_13; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800caea3  mov     r9, rsi
0x1800caea6  mov     [rsp+40h+var_20], rbx
0x1800caeab  xor     ecx, ecx
0x1800caead  call    BasepGetNameFromReg
0x1800caeb2  test    eax, eax
0x1800caeb4  js      loc_1800CAF3E
0x1800caeba  mov     eax, 1
0x1800caebf  jmp     loc_1800CABD6
0x1800caec4  lea     r8, aHostname; "Hostname"
0x1800caecb  jmp     loc_1800CABAA
0x1800caed0  mov     eax, gs:68h
0x1800caed8  cmp     eax, 0EAh
0x1800caedd  jz      loc_1800CAF65
0x1800caee3  mov     r8d, r12d
0x1800caee6  mov     edx, 0C0000001h
0x1800caeeb  jmp     loc_1800CACC7
0x1800caef0  mov     eax, gs:68h
0x1800caef8  cmp     eax, 0EAh
0x1800caefd  jnz     short loc_1800CAEE3
0x1800caeff  mov     ecx, [rbp+nSize]
0x1800caf02  mov     edx, r13d
0x1800caf05  mov     r8d, [rbp+arg_18]
0x1800caf09  mov     r15d, r12d
0x1800caf0c  lea     r8d, [r8+rcx]
0x1800caf10  jmp     loc_1800CACCA
0x1800caf15  mov     cs:dword_1803A54A4, r12d
0x1800caf1c  jmp     loc_1800CAE72
0x1800caf21  mov     ecx, 0C000000Dh
0x1800caf26  jmp     loc_1800CAD72
0x1800caf2b  cmp     [rbx], r15d
0x1800caf2e  jb      loc_1801A091A
0x1800caf34  mov     edi, 1
0x1800caf39  jmp     loc_1801A092E
0x1800caf3e  cmp     eax, r13d
0x1800caf41  jz      short loc_1800CAF51
0x1800caf43  mov     cs:dword_1803A54A0, r12d
0x1800caf4a  jmp     loc_1800CAB20
0x1800caf4f  mov     [rbx], eax
0x1800caf51  mov     ecx, 0EAh
0x1800caf56  jmp     loc_1800CACE3
0x1800caf5b  mov     edx, 0C000000Dh
0x1800caf60  jmp     loc_1800CAD70
0x1800caf65  mov     [rbp+arg_18], r12d
0x1800caf69  mov     ecx, 6
0x1800caf6e  lea     r8, [rbp+arg_18]; nSize
  ... truncated ...
```
