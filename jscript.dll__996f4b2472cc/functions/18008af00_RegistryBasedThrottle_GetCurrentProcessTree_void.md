# RegistryBasedThrottle::GetCurrentProcessTree(void)

- ea: `0x18008af00`
- end: `0x18008b13c`
- name: `?GetCurrentProcessTree@RegistryBasedThrottle@@QEAAPEADXZ`
- size: `572`
- prototype: `char *__fastcall(RegistryBasedThrottle *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18007cce0`

## callees

- `0x18007fa70`
- `0x18008af00`
- `0x18008b5c0`
- `0x1800966aa`
- `0x1800966e0`

## import_xrefs

- `msvcrt!strcat_s` at `0x18008b0c0`
- `msvcrt!strcat_s` at `0x18008b0d9`
- `msvcrt!strcat_s` at `0x18008b0c0`
- `msvcrt!strcat_s` at `0x18008b0d9`
- `KERNEL32!Process32Next` at `0x18008b002`
- `KERNEL32!Process32Next` at `0x18008b002`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x18008afba`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x18008afba`
- `KERNEL32!Process32First` at `0x18008afd7`
- `KERNEL32!Process32First` at `0x18008afd7`
- `KERNEL32!CloseHandle` at `0x18008b015`
- `KERNEL32!CloseHandle` at `0x18008b0ec`
- `KERNEL32!CloseHandle` at `0x18008b10b`
- `KERNEL32!CloseHandle` at `0x18008b015`
- `KERNEL32!CloseHandle` at `0x18008b0ec`
- `KERNEL32!CloseHandle` at `0x18008b10b`
- `KERNEL32!GetCurrentProcessId` at `0x18008af77`
- `KERNEL32!GetCurrentProcessId` at `0x18008af77`

## pseudocode

```c
char *__fastcall RegistryBasedThrottle::GetCurrentProcessTree(RegistryBasedThrottle *this)
{
  char *result; // rax
  DWORD CurrentProcessId; // ebx
  char *v4; // rsi
  _BYTE *i; // r14
  HANDLE Toolhelp32Snapshot; // rax
  void *v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rax
  PROCESSENTRY32 pe; // [rsp+20h] [rbp-158h] BYREF

  if ( *((_DWORD *)this + 1753) )
    return (char *)*((_QWORD *)this + 873);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetImpl'::`2'::impl) )
  {
    RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(this);
    return (char *)*((_QWORD *)this + 873);
  }
  else
  {
    CurrentProcessId = GetCurrentProcessId();
    memset_0(&pe.cntUsage, 0, 0x12Cu);
    pe.dwSize = 304;
    v4 = (char *)this + 568;
    *((_BYTE *)this + 568) = 0;
    for ( i = (char *)this + 568; CurrentProcessId; v4 = (char *)this + 568 )
    {
      Toolhelp32Snapshot = CreateToolhelp32Snapshot(2u, 0);
      v7 = Toolhelp32Snapshot;
      if ( Toolhelp32Snapshot == (HANDLE)-1LL )
        break;
      if ( !Process32First(Toolhelp32Snapshot, &pe) )
      {
LABEL_9:
        CloseHandle(v7);
        break;
      }
      while ( pe.th32ProcessID != CurrentProcessId )
      {
        if ( !Process32Next(v7, &pe) )
          goto LABEL_9;
      }
      v8 = -1;
      do
        ++v8;
      while ( pe.szExeFile[v8] );
      v9 = -1;
      do
        ++v9;
      while ( v4[v9] );
      if ( (unsigned __int64)(v9 + v8 + 1) >= 0x104 )
      {
        CloseHandle(v7);
        result = (char *)this + 568;
        *((_QWORD *)this + 873) = i;
        *((_DWORD *)this + 1753) = 1;
        return result;
      }
      if ( *i )
        strcat_s((char *)this + 568, 0x104u, ";");
      strcat_s((char *)this + 568, 0x104u, pe.szExeFile);
      CurrentProcessId = pe.th32ParentProcessID;
      CloseHandle(v7);
    }
    *((_QWORD *)this + 873) = (char *)this + 568;
    result = (char *)this + 568;
    *((_DWORD *)this + 1753) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x18008af00  push    rbp
0x18008af02  sub     rsp, 170h
0x18008af09  mov     rax, cs:__security_cookie
0x18008af10  xor     rax, rsp
0x18008af13  mov     [rsp+178h+var_28], rax
0x18008af1b  cmp     dword ptr [rcx+1B64h], 0
0x18008af22  mov     rbp, rcx
0x18008af25  jnz     loc_18008B130
0x18008af2b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging> `wil::Feature<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetImpl(void)'::`2'::impl
0x18008af32  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::__private_IsEnabled(void)
0x18008af37  test    al, al
0x18008af39  jz      short loc_18008AF4F
0x18008af3b  mov     rcx, rbp; this
0x18008af3e  call    ?IdentifyCurrentProcessTreeEnhanced@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(void)
0x18008af43  mov     rax, [rbp+1B48h]
0x18008af4a  jmp     loc_18008B05D
0x18008af4f  mov     [rsp+178h+arg_8], rbx
0x18008af57  mov     [rsp+178h+arg_10], rsi
0x18008af5f  mov     [rsp+178h+arg_18], rdi
0x18008af67  mov     [rsp+178h+var_10], r14
0x18008af6f  mov     [rsp+178h+var_18], r15
0x18008af77  call    cs:__imp_GetCurrentProcessId
0x18008af7e  nop     dword ptr [rax+rax+00h]
0x18008af83  xor     edx, edx; Val
0x18008af85  lea     rcx, [rsp+178h+pe.cntUsage]; void *
0x18008af8a  mov     r8d, 12Ch; Size
0x18008af90  mov     ebx, eax
0x18008af92  call    memset_0
0x18008af97  mov     [rsp+178h+pe.dwSize], 130h
0x18008af9f  lea     rsi, [rbp+238h]
0x18008afa6  mov     byte ptr [rsi], 0
0x18008afa9  mov     r14, rsi
0x18008afac  mov     r15, rsi
0x18008afaf  test    ebx, ebx
0x18008afb1  jz      short loc_18008B021
0x18008afb3  xor     edx, edx; th32ProcessID
0x18008afb5  mov     ecx, 2; dwFlags
0x18008afba  call    cs:__imp_CreateToolhelp32Snapshot
0x18008afc1  nop     dword ptr [rax+rax+00h]
0x18008afc6  mov     rdi, rax
0x18008afc9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008afcd  jz      short loc_18008B021
0x18008afcf  lea     rdx, [rsp+178h+pe]; lppe
0x18008afd4  mov     rcx, rax; hSnapshot
0x18008afd7  call    cs:__imp_Process32First
0x18008afde  nop     dword ptr [rax+rax+00h]
0x18008afe3  test    eax, eax
0x18008afe5  jz      short loc_18008B012
0x18008afe7  nop     word ptr [rax+rax+00000000h]
0x18008aff0  cmp     [rsp+178h+pe.th32ProcessID], ebx
0x18008aff4  jz      loc_18008B077
0x18008affa  lea     rdx, [rsp+178h+pe]; lppe
0x18008afff  mov     rcx, rdi; hSnapshot
0x18008b002  call    cs:__imp_Process32Next
0x18008b009  nop     dword ptr [rax+rax+00h]
0x18008b00e  test    eax, eax
0x18008b010  jnz     short loc_18008AFF0
0x18008b012  mov     rcx, rdi; hObject
0x18008b015  call    cs:__imp_CloseHandle
0x18008b01c  nop     dword ptr [rax+rax+00h]
0x18008b021  mov     [rbp+1B48h], r15
0x18008b028  mov     rax, r15
0x18008b02b  mov     dword ptr [rbp+1B64h], 1
0x18008b035  mov     r14, [rsp+178h+var_10]
0x18008b03d  mov     rdi, [rsp+178h+arg_18]
0x18008b045  mov     rsi, [rsp+178h+arg_10]
0x18008b04d  mov     rbx, [rsp+178h+arg_8]
0x18008b055  mov     r15, [rsp+178h+var_18]
0x18008b05d  mov     rcx, [rsp+178h+var_28]
0x18008b065  xor     rcx, rsp; StackCookie
0x18008b068  call    __security_check_cookie
0x18008b06d  add     rsp, 170h
0x18008b074  pop     rbp
0x18008b075  retn
0x18008b077  lea     rax, [rsp+178h+pe.szExeFile]
0x18008b07c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18008b083  inc     rcx
0x18008b086  cmp     byte ptr [rax+rcx], 0
0x18008b08a  jnz     short loc_18008B083
0x18008b08c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18008b093  inc     rax
0x18008b096  cmp     byte ptr [rsi+rax], 0
0x18008b09a  jnz     short loc_18008B093
0x18008b09c  inc     rcx
0x18008b09f  add     rcx, rax
0x18008b0a2  cmp     rcx, 104h
0x18008b0a9  jnb     short loc_18008B108
0x18008b0ab  cmp     byte ptr [r14], 0
0x18008b0af  jz      short loc_18008B0CC
0x18008b0b1  lea     r8, asc_1800AA210; ";"
0x18008b0b8  mov     edx, 104h; SizeInBytes
0x18008b0bd  mov     rcx, r15; Destination
0x18008b0c0  call    cs:__imp_strcat_s
0x18008b0c7  nop     dword ptr [rax+rax+00h]
0x18008b0cc  lea     r8, [rsp+178h+pe.szExeFile]; Source
0x18008b0d1  mov     edx, 104h; SizeInBytes
0x18008b0d6  mov     rcx, r15; Destination
0x18008b0d9  call    cs:__imp_strcat_s
0x18008b0e0  nop     dword ptr [rax+rax+00h]
0x18008b0e5  mov     ebx, [rsp+178h+pe.th32ParentProcessID]
0x18008b0e9  mov     rcx, rdi; hObject
0x18008b0ec  call    cs:__imp_CloseHandle
0x18008b0f3  nop     dword ptr [rax+rax+00h]
0x18008b0f8  mov     rsi, r14
0x18008b0fb  test    ebx, ebx
0x18008b0fd  jnz     loc_18008AFB3
0x18008b103  jmp     loc_18008B021
0x18008b108  mov     rcx, rdi; hObject
0x18008b10b  call    cs:__imp_CloseHandle
0x18008b112  nop     dword ptr [rax+rax+00h]
0x18008b117  mov     rax, r14
0x18008b11a  mov     [rbp+1B48h], r14
0x18008b121  mov     dword ptr [rbp+1B64h], 1
0x18008b12b  jmp     loc_18008B035
0x18008b130  mov     rax, [rcx+1B48h]
0x18008b137  jmp     loc_18008B05D
```
