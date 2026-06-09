# RegistryBasedThrottle::GetCurrentProcessTree(void)

- ea: `0x180089030`
- end: `0x180089231`
- name: `?GetCurrentProcessTree@RegistryBasedThrottle@@QEAAPEADXZ`
- size: `513`
- prototype: `char *__fastcall(RegistryBasedThrottle *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18007b4b8`

## callees

- `0x18007e100`
- `0x180089030`
- `0x180089640`
- `0x18009429a`
- `0x1800942d0`

## import_xrefs

- `msvcrt!strcat_s` at `0x1800891cd`
- `msvcrt!strcat_s` at `0x1800891e0`
- `msvcrt!strcat_s` at `0x1800891cd`
- `msvcrt!strcat_s` at `0x1800891e0`
- `KERNEL32!Process32Next` at `0x180089116`
- `KERNEL32!Process32Next` at `0x180089116`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x1800890e7`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x1800890e7`
- `KERNEL32!Process32First` at `0x1800890fe`
- `KERNEL32!Process32First` at `0x1800890fe`
- `KERNEL32!CloseHandle` at `0x180089123`
- `KERNEL32!CloseHandle` at `0x1800891ed`
- `KERNEL32!CloseHandle` at `0x180089206`
- `KERNEL32!CloseHandle` at `0x180089123`
- `KERNEL32!CloseHandle` at `0x1800891ed`
- `KERNEL32!CloseHandle` at `0x180089206`
- `KERNEL32!GetCurrentProcessId` at `0x1800890a7`
- `KERNEL32!GetCurrentProcessId` at `0x1800890a7`

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
0x180089030  push    rbp
0x180089032  sub     rsp, 170h
0x180089039  mov     rax, cs:__security_cookie
0x180089040  xor     rax, rsp
0x180089043  mov     [rsp+178h+var_28], rax
0x18008904b  cmp     dword ptr [rcx+1B64h], 0
0x180089052  mov     rbp, rcx
0x180089055  jnz     loc_180089225
0x18008905b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging> `wil::Feature<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetImpl(void)'::`2'::impl
0x180089062  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::__private_IsEnabled(void)
0x180089067  test    al, al
0x180089069  jz      short loc_18008907F
0x18008906b  mov     rcx, rbp; this
0x18008906e  call    ?IdentifyCurrentProcessTreeEnhanced@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(void)
0x180089073  mov     rax, [rbp+1B48h]
0x18008907a  jmp     loc_180089165
0x18008907f  mov     [rsp+178h+arg_8], rbx
0x180089087  mov     [rsp+178h+arg_10], rsi
0x18008908f  mov     [rsp+178h+arg_18], rdi
0x180089097  mov     [rsp+178h+var_10], r14
0x18008909f  mov     [rsp+178h+var_18], r15
0x1800890a7  call    cs:__imp_GetCurrentProcessId
0x1800890ad  xor     edx, edx; Val
0x1800890af  lea     rcx, [rsp+178h+pe.cntUsage]; void *
0x1800890b4  mov     r8d, 12Ch; Size
0x1800890ba  mov     ebx, eax
0x1800890bc  call    memset_0
0x1800890c1  mov     [rsp+178h+pe.dwSize], 130h
0x1800890c9  lea     rsi, [rbp+238h]
0x1800890d0  mov     byte ptr [rsi], 0
0x1800890d3  mov     r14, rsi
0x1800890d6  mov     r15, rsi
0x1800890d9  test    ebx, ebx
0x1800890db  jz      short loc_180089129
0x1800890dd  nop     dword ptr [rax]
0x1800890e0  xor     edx, edx; th32ProcessID
0x1800890e2  mov     ecx, 2; dwFlags
0x1800890e7  call    cs:__imp_CreateToolhelp32Snapshot
0x1800890ed  mov     rdi, rax
0x1800890f0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800890f4  jz      short loc_180089129
0x1800890f6  lea     rdx, [rsp+178h+pe]; lppe
0x1800890fb  mov     rcx, rax; hSnapshot
0x1800890fe  call    cs:__imp_Process32First
0x180089104  test    eax, eax
0x180089106  jz      short loc_180089120
0x180089108  cmp     [rsp+178h+pe.th32ProcessID], ebx
0x18008910c  jz      short loc_18008917E
0x18008910e  lea     rdx, [rsp+178h+pe]; lppe
0x180089113  mov     rcx, rdi; hSnapshot
0x180089116  call    cs:__imp_Process32Next
0x18008911c  test    eax, eax
0x18008911e  jnz     short loc_180089108
0x180089120  mov     rcx, rdi; hObject
0x180089123  call    cs:__imp_CloseHandle
0x180089129  mov     [rbp+1B48h], r15
0x180089130  mov     rax, r15
0x180089133  mov     dword ptr [rbp+1B64h], 1
0x18008913d  mov     r14, [rsp+178h+var_10]
0x180089145  mov     rdi, [rsp+178h+arg_18]
0x18008914d  mov     rsi, [rsp+178h+arg_10]
0x180089155  mov     rbx, [rsp+178h+arg_8]
0x18008915d  mov     r15, [rsp+178h+var_18]
0x180089165  mov     rcx, [rsp+178h+var_28]
0x18008916d  xor     rcx, rsp; StackCookie
0x180089170  call    __security_check_cookie
0x180089175  add     rsp, 170h
0x18008917c  pop     rbp
0x18008917d  retn
0x18008917e  lea     rax, [rsp+178h+pe.szExeFile]
0x180089183  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18008918a  nop     word ptr [rax+rax+00h]
0x180089190  inc     rcx
0x180089193  cmp     byte ptr [rax+rcx], 0
0x180089197  jnz     short loc_180089190
0x180089199  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800891a0  inc     rax
0x1800891a3  cmp     byte ptr [rsi+rax], 0
0x1800891a7  jnz     short loc_1800891A0
0x1800891a9  inc     rcx
0x1800891ac  add     rcx, rax
0x1800891af  cmp     rcx, 104h
0x1800891b6  jnb     short loc_180089203
0x1800891b8  cmp     byte ptr [r14], 0
0x1800891bc  jz      short loc_1800891D3
0x1800891be  lea     r8, asc_1800A82AC; ";"
0x1800891c5  mov     edx, 104h; SizeInBytes
0x1800891ca  mov     rcx, r15; Destination
0x1800891cd  call    cs:__imp_strcat_s
0x1800891d3  lea     r8, [rsp+178h+pe.szExeFile]; Source
0x1800891d8  mov     edx, 104h; SizeInBytes
0x1800891dd  mov     rcx, r15; Destination
0x1800891e0  call    cs:__imp_strcat_s
0x1800891e6  mov     ebx, [rsp+178h+pe.th32ParentProcessID]
0x1800891ea  mov     rcx, rdi; hObject
0x1800891ed  call    cs:__imp_CloseHandle
0x1800891f3  mov     rsi, r14
0x1800891f6  test    ebx, ebx
0x1800891f8  jnz     loc_1800890E0
0x1800891fe  jmp     loc_180089129
0x180089203  mov     rcx, rdi; hObject
0x180089206  call    cs:__imp_CloseHandle
0x18008920c  mov     rax, r14
0x18008920f  mov     [rbp+1B48h], r14
0x180089216  mov     dword ptr [rbp+1B64h], 1
0x180089220  jmp     loc_18008913D
0x180089225  mov     rax, [rcx+1B48h]
0x18008922c  jmp     loc_180089165
```
