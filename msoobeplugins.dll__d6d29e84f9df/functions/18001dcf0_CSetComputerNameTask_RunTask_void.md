# CSetComputerNameTask::RunTask(void)

- ea: `0x18001dcf0`
- end: `0x18001de51`
- name: `?RunTask@CSetComputerNameTask@@UEAAJXZ`
- size: `353`
- prototype: `__int64 __fastcall(CSetComputerNameTask *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003470`
- `0x18000ac48`
- `0x18001dcf0`
- `0x18001de58`
- `0x1800b8834`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x18001dd6c`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x18001dd9e`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x18001dd6c`
- `api-ms-win-core-sysinfo-l1-2-0!SetComputerNameExW` at `0x18001dd9e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DnsHostnameToComputerNameW` at `0x18001dd43`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DnsHostnameToComputerNameW` at `0x18001dd43`

## string_xrefs

- `0x18001dd15`: `Setting computer name to [%s]`
- `0x18001dd88`: `Manually setting ComputerNamePhysicalNetBIOS due to mismatched code pages`
- `0x18001ddb4`: `Failed to set ComputerNamePhysicalNetBIOS [0x%08X]`
- `0x18001ddd1`: `ComputerName`
- `0x18001ddd8`: `System\CurrentControlSet\Control\ComputerName\ActiveComputerName`
- `0x18001ddf4`: `System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x18001de23`: `Failed to set active computer name [0x%08X]`
- `0x18001dd58`: `Failed to convert to NetBIOS computer name [0x%08X]`

## pseudocode

```c
__int64 __fastcall CSetComputerNameTask::RunTask(CSetComputerNameTask *this)
{
  const WCHAR *v1; // rdi
  int v2; // eax
  unsigned int v3; // ebx
  int Error; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  DWORD nSize; // [rsp+20h] [rbp-38h] BYREF
  WCHAR ComputerName[8]; // [rsp+28h] [rbp-30h] BYREF
  __int128 v11; // [rsp+38h] [rbp-20h]

  v1 = (const WCHAR *)((char *)this + 552);
  UnattendLogW(0, L"Setting computer name to [%s]", (char *)this + 552);
  nSize = 16;
  *(_OWORD *)ComputerName = 0;
  v11 = 0;
  if ( DnsHostnameToComputerNameW(v1, ComputerName, &nSize) || (v2 = ResultFromKnownLastError(), v3 = v2, v2 >= 0) )
  {
    if ( !SetComputerNameExW(ComputerNamePhysicalDnsHostname, v1) )
    {
      Error = ResultFromKnownLastError();
      v3 = Error;
      if ( Error == -2147023686 )
      {
        UnattendLogW(0, L"Manually setting ComputerNamePhysicalNetBIOS due to mismatched code pages");
        if ( !SetComputerNameExW(ComputerNamePhysicalNetBIOS, v1) )
        {
          v5 = ResultFromKnownLastError();
          if ( v5 < 0 )
            UnattendLogW(2, L"Failed to set ComputerNamePhysicalNetBIOS [0x%08X]", (unsigned int)v5);
        }
      }
      else if ( Error < 0 )
      {
        UnattendLogW(1, L"Failed to set DNS hostname [0x%08X]", (unsigned int)Error);
        return v3;
      }
    }
    v6 = SHRegSetString(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\ComputerName\\ActiveComputerName",
           L"ComputerName",
           ComputerName);
    v3 = v6;
    if ( v6 < 0 )
    {
      UnattendLogW(1, L"Failed to set active computer name [0x%08X]", (unsigned int)v6);
    }
    else
    {
      v7 = SHRegSetString(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters",
             L"Hostname",
             v1);
      v3 = v7;
      if ( v7 < 0 )
        UnattendLogW(1, L"Failed to set volitile hostname [0x%08X]", (unsigned int)v7);
    }
  }
  else
  {
    UnattendLogW(1, L"Failed to convert to NetBIOS computer name [0x%08X]", (unsigned int)v2);
  }
  return v3;
}

```

## disassembly

```asm
0x18001dcf0  mov     [rsp+arg_8], rbx
0x18001dcf5  push    rdi
0x18001dcf6  sub     rsp, 50h
0x18001dcfa  mov     rax, cs:__security_cookie
0x18001dd01  xor     rax, rsp
0x18001dd04  mov     [rsp+58h+var_10], rax
0x18001dd09  lea     rdi, [rcx+228h]
0x18001dd10  xor     ecx, ecx
0x18001dd12  mov     r8, rdi
0x18001dd15  lea     rdx, aSettingCompute; "Setting computer name to [%s]"
0x18001dd1c  call    UnattendLogW
0x18001dd21  xorps   xmm0, xmm0
0x18001dd24  mov     [rsp+58h+nSize], 10h
0x18001dd2c  lea     r8, [rsp+58h+nSize]; nSize
0x18001dd31  mov     rcx, rdi; Hostname
0x18001dd34  lea     rdx, [rsp+58h+ComputerName]; ComputerName
0x18001dd39  movups  xmmword ptr [rsp+58h+ComputerName], xmm0
0x18001dd3e  movups  [rsp+58h+var_20], xmm0
0x18001dd43  call    cs:__imp_DnsHostnameToComputerNameW
0x18001dd49  test    eax, eax
0x18001dd4b  jnz     short loc_18001DD64
0x18001dd4d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001dd52  mov     ebx, eax
0x18001dd54  test    eax, eax
0x18001dd56  jns     short loc_18001DD64
0x18001dd58  lea     rdx, aFailedToConver_0; "Failed to convert to NetBIOS computer n"...
0x18001dd5f  jmp     loc_18001DE2A
0x18001dd64  mov     rdx, rdi; lpBuffer
0x18001dd67  mov     ecx, 5; NameType
0x18001dd6c  call    cs:__imp_SetComputerNameExW
0x18001dd72  test    eax, eax
0x18001dd74  jnz     short loc_18001DDC5
0x18001dd76  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001dd7b  mov     ebx, eax
0x18001dd7d  cmp     eax, 800704BAh
0x18001dd82  jnz     loc_18001DE16
0x18001dd88  lea     rdx, aManuallySettin; "Manually setting ComputerNamePhysicalNe"...
0x18001dd8f  xor     ecx, ecx
0x18001dd91  call    UnattendLogW
0x18001dd96  mov     rdx, rdi; lpBuffer
0x18001dd99  mov     ecx, 4; NameType
0x18001dd9e  call    cs:__imp_SetComputerNameExW
0x18001dda4  test    eax, eax
0x18001dda6  jnz     short loc_18001DDC5
0x18001dda8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001ddad  test    eax, eax
0x18001ddaf  jns     short loc_18001DDC5
0x18001ddb1  mov     r8d, eax
0x18001ddb4  lea     rdx, aFailedToSetCom; "Failed to set ComputerNamePhysicalNetBI"...
0x18001ddbb  mov     ecx, 2
0x18001ddc0  call    UnattendLogW
0x18001ddc5  lea     r9, [rsp+58h+ComputerName]; unsigned __int16 *
0x18001ddca  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18001ddd1  lea     r8, aComputername; "ComputerName"
0x18001ddd8  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Com"...
0x18001dddf  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001dde4  mov     ebx, eax
0x18001dde6  test    eax, eax
0x18001dde8  js      short loc_18001DE23
0x18001ddea  mov     r9, rdi; unsigned __int16 *
0x18001dded  lea     r8, aHostname; "Hostname"
0x18001ddf4  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Tc"...
0x18001ddfb  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18001de02  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001de07  mov     ebx, eax
0x18001de09  test    eax, eax
0x18001de0b  jns     short loc_18001DE37
0x18001de0d  lea     rdx, aFailedToSetVol; "Failed to set volitile hostname [0x%08X"...
0x18001de14  jmp     short loc_18001DE2A
0x18001de16  test    eax, eax
0x18001de18  jns     short loc_18001DDC5
0x18001de1a  lea     rdx, aFailedToSetDns; "Failed to set DNS hostname [0x%08X]"
0x18001de21  jmp     short loc_18001DE2A
0x18001de23  lea     rdx, aFailedToSetAct; "Failed to set active computer name [0x%"...
0x18001de2a  mov     r8d, eax
0x18001de2d  mov     ecx, 1
0x18001de32  call    UnattendLogW
0x18001de37  mov     eax, ebx
0x18001de39  mov     rcx, [rsp+58h+var_10]
0x18001de3e  xor     rcx, rsp; StackCookie
0x18001de41  call    __security_check_cookie
0x18001de46  mov     rbx, [rsp+58h+arg_8]
0x18001de4b  add     rsp, 50h
0x18001de4f  pop     rdi
0x18001de50  retn
```
