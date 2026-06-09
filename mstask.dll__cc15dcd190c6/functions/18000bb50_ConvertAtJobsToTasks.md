# ConvertAtJobsToTasks

- ea: `0x18000bb50`
- end: `0x18000be5a`
- name: `ConvertAtJobsToTasks`
- size: `778`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180001840`
- `0x180006ec0`
- `0x18000860c`
- `0x180009ef8`
- `0x180009f38`
- `0x18000bb50`
- `0x18001aac0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000bdf0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000be0a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000bdf0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000be0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bdd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bdd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be28`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bcc4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bd3d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bcc4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bd3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bc04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bc86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bc04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bc86`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000bc55`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000bc55`

## string_xrefs

- `0x18000bbc6`: `System\CurrentControlSet\Services\Schedule`
- `0x18000bd36`: `Command`

## pseudocode

```c
CSchedule *ConvertAtJobsToTasks()
{
  CSchedule *result; // rax
  CSchedule *v1; // rdi
  WCHAR *v2; // rsi
  DWORD i; // r14d
  LSTATUS v4; // eax
  LSTATUS v5; // ebx
  unsigned __int16 *v6; // rax
  WCHAR *v7; // rbx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v12; // [rsp+58h] [rbp-A8h] BYREF
  int v13; // [rsp+60h] [rbp-A0h]
  __int16 v14; // [rsp+64h] [rbp-9Ch]
  __int16 v15; // [rsp+66h] [rbp-9Ah]
  BYTE *v16; // [rsp+68h] [rbp-98h]
  struct _FILETIME ftLastWriteTime; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[8]; // [rsp+78h] [rbp-88h] BYREF
  int v19; // [rsp+80h] [rbp-80h]
  WCHAR Name[20]; // [rsp+88h] [rbp-78h] BYREF
  BYTE v21[528]; // [rsp+B0h] [rbp-50h] BYREF

  result = (CSchedule *)operator new(0x50u);
  if ( result )
  {
    result = CSchedule::CSchedule(result);
    v1 = result;
    if ( result )
    {
      if ( (int)CSchedule::Init(result) >= 0 )
      {
        hKey = 0;
        *(_QWORD *)Data = 0;
        v19 = 0;
        cchName = 0;
        Type = 0;
        phkResult = 0;
        ftLastWriteTime = 0;
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Schedule", 0, 0x20019u, &hKey) )
        {
          v2 = 0;
          for ( i = 0; ; ++i )
          {
            cchName = 20;
            v4 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
            if ( v4 )
            {
              if ( v4 != 234 )
                break;
            }
            if ( !RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult) )
            {
              cchName = 12;
              if ( !RegQueryValueExW(phkResult, L"Schedule", 0, &Type, Data, &cchName)
                && Type == 3
                && cchName == 12
                && (v19 & 0x80u) == 0
                && *(int *)&Data[4] >= 0
                && *(_DWORD *)Data < 0x5265BFFu )
              {
                cchName = 520;
                v5 = RegQueryValueExW(phkResult, L"Command", 0, &Type, v21, &cchName);
                RegCloseKey(phkResult);
                if ( !v5 && Type == 1 )
                {
                  v15 = 0;
                  v16 = v21;
                  v12 = *(unsigned int *)Data;
                  v13 = *(_DWORD *)&Data[4];
                  v14 = v19;
                  if ( (*(int (__fastcall **)(CSchedule *, __int64 *, _QWORD))(*(_QWORD *)v1 + 88LL))(v1, &v12, 0) >= 0 )
                  {
                    v6 = (unsigned __int16 *)operator new(0x30u);
                    if ( !v6 )
                    {
                      RegDeleteKeyExW(hKey, Name, 0, 0);
                      break;
                    }
                    *(_QWORD *)v6 = v2;
                    v2 = v6;
                    StringCchCopyW(v6 + 4, 0x14u, Name);
                  }
                }
              }
              else
              {
                RegCloseKey(phkResult);
              }
            }
          }
          if ( v2 )
          {
            do
            {
              RegDeleteKeyExW(hKey, v2 + 4, 0, 0);
              v7 = *(WCHAR **)v2;
              operator delete(v2);
              v2 = v7;
            }
            while ( v7 );
          }
          RegCloseKey(hKey);
        }
        return (CSchedule *)(*(__int64 (__fastcall **)(CSchedule *))(*(_QWORD *)v1 + 16LL))(v1);
      }
      else
      {
        return (CSchedule *)(*(__int64 (__fastcall **)(CSchedule *))(*(_QWORD *)v1 + 16LL))(v1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000bb50  push    rbp
0x18000bb52  push    rbx
0x18000bb53  push    rsi
0x18000bb54  push    rdi
0x18000bb55  push    r14
0x18000bb57  lea     rbp, [rsp-1D0h]
0x18000bb5f  sub     rsp, 2D0h
0x18000bb66  mov     rax, cs:__security_cookie
0x18000bb6d  xor     rax, rsp
0x18000bb70  mov     [rbp+1F0h+var_30], rax
0x18000bb77  mov     ecx, 50h ; 'P'; Size
0x18000bb7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bb81  test    rax, rax
0x18000bb84  jz      loc_18000BE3D
0x18000bb8a  mov     rcx, rax; this
0x18000bb8d  call    ??0CSchedule@@QEAA@XZ; CSchedule::CSchedule(void)
0x18000bb92  mov     rdi, rax
0x18000bb95  test    rax, rax
0x18000bb98  jz      loc_18000BE3D
0x18000bb9e  mov     rcx, rax; this
0x18000bba1  call    ?Init@CSchedule@@QEAAJXZ; CSchedule::Init(void)
0x18000bba6  test    eax, eax
0x18000bba8  jns     short loc_18000BBB6
0x18000bbaa  mov     rcx, [rdi]
0x18000bbad  mov     rax, [rcx+10h]
0x18000bbb1  jmp     loc_18000BE35
0x18000bbb6  xor     eax, eax
0x18000bbb8  mov     [rsp+2F0h+hKey], 0
0x18000bbc1  mov     qword ptr [rsp+2F0h+Data], rax
0x18000bbc6  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Sc"...
0x18000bbcd  mov     [rbp+1F0h+var_270], eax
0x18000bbd0  mov     r9d, 20019h; samDesired
0x18000bbd6  mov     [rsp+2F0h+cchName], eax
0x18000bbda  xor     r8d, r8d; ulOptions
0x18000bbdd  mov     [rsp+2F0h+Type], eax
0x18000bbe1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bbe8  lea     rax, [rsp+2F0h+hKey]
0x18000bbed  mov     [rsp+2F0h+var_2A8], 0
0x18000bbf6  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18000bbfb  mov     qword ptr [rsp+2F0h+ftLastWriteTime.dwLowDateTime], 0
0x18000bc04  call    cs:__imp_RegOpenKeyExW
0x18000bc0a  test    eax, eax
0x18000bc0c  jnz     loc_18000BE2E
0x18000bc12  xor     esi, esi
0x18000bc14  xor     r14d, r14d
0x18000bc17  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18000bc1c  lea     rax, [rsp+2F0h+ftLastWriteTime]
0x18000bc21  mov     [rsp+2F0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000bc26  lea     r9, [rsp+2F0h+cchName]; lpcchName
0x18000bc2b  mov     [rsp+2F0h+lpcchClass], 0; lpcchClass
0x18000bc34  lea     r8, [rbp+1F0h+Name]; lpName
0x18000bc38  mov     [rsp+2F0h+lpClass], 0; lpClass
0x18000bc41  mov     edx, r14d; dwIndex
0x18000bc44  mov     [rsp+2F0h+phkResult], 0; lpReserved
0x18000bc4d  mov     [rsp+2F0h+cchName], 14h
0x18000bc55  call    cs:__imp_RegEnumKeyExW
0x18000bc5b  test    eax, eax
0x18000bc5d  jz      short loc_18000BC6A
0x18000bc5f  cmp     eax, 0EAh
0x18000bc64  jnz     loc_18000BDF6
0x18000bc6a  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18000bc6f  lea     rax, [rsp+2F0h+var_2A8]
0x18000bc74  mov     r9d, 20019h; samDesired
0x18000bc7a  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18000bc7f  xor     r8d, r8d; ulOptions
0x18000bc82  lea     rdx, [rbp+1F0h+Name]; lpSubKey
0x18000bc86  call    cs:__imp_RegOpenKeyExW
0x18000bc8c  test    eax, eax
0x18000bc8e  jnz     loc_18000BDD9
0x18000bc94  mov     rcx, [rsp+2F0h+var_2A8]; hKey
0x18000bc99  lea     rax, [rsp+2F0h+cchName]
0x18000bc9e  mov     [rsp+2F0h+lpClass], rax; lpcbData
0x18000bca3  lea     r9, [rsp+2F0h+Type]; lpType
0x18000bca8  lea     rax, [rsp+2F0h+Data]
0x18000bcad  mov     [rsp+2F0h+cchName], 0Ch
0x18000bcb5  xor     r8d, r8d; lpReserved
0x18000bcb8  mov     [rsp+2F0h+phkResult], rax; lpData
0x18000bcbd  lea     rdx, ServiceName; "Schedule"
0x18000bcc4  call    cs:__imp_RegQueryValueExW
0x18000bcca  test    eax, eax
0x18000bccc  jnz     loc_18000BDCE
0x18000bcd2  cmp     [rsp+2F0h+Type], 3
0x18000bcd7  jnz     loc_18000BDCE
0x18000bcdd  cmp     [rsp+2F0h+cchName], 0Ch
0x18000bce2  jnz     loc_18000BDCE
0x18000bce8  test    byte ptr [rbp+1F0h+var_270], 80h
0x18000bcec  jnz     loc_18000BDCE
0x18000bcf2  test    dword ptr [rsp+2F0h+Data+4], 80000000h
0x18000bcfa  jnz     loc_18000BDCE
0x18000bd00  cmp     dword ptr [rsp+2F0h+Data], 5265BFFh
0x18000bd08  jnb     loc_18000BDCE
0x18000bd0e  mov     rcx, [rsp+2F0h+var_2A8]; hKey
0x18000bd13  lea     rax, [rsp+2F0h+cchName]
0x18000bd18  mov     [rsp+2F0h+lpClass], rax; lpcbData
0x18000bd1d  lea     r9, [rsp+2F0h+Type]; lpType
0x18000bd22  lea     rax, [rbp+1F0h+var_240]
0x18000bd26  mov     [rsp+2F0h+cchName], 208h
0x18000bd2e  xor     r8d, r8d; lpReserved
0x18000bd31  mov     [rsp+2F0h+phkResult], rax; lpData
0x18000bd36  lea     rdx, aCommand; "Command"
0x18000bd3d  call    cs:__imp_RegQueryValueExW
0x18000bd43  mov     rcx, [rsp+2F0h+var_2A8]; hKey
0x18000bd48  mov     ebx, eax
0x18000bd4a  call    cs:__imp_RegCloseKey
0x18000bd50  test    ebx, ebx
0x18000bd52  jnz     loc_18000BDD9
0x18000bd58  cmp     [rsp+2F0h+Type], 1
0x18000bd5d  jnz     short loc_18000BDD9
0x18000bd5f  xor     eax, eax
0x18000bd61  lea     rdx, [rsp+2F0h+var_298]
0x18000bd66  mov     [rsp+2F0h+var_28A], ax
0x18000bd6b  xor     r8d, r8d
0x18000bd6e  lea     rax, [rbp+1F0h+var_240]
0x18000bd72  mov     rcx, rdi
0x18000bd75  mov     [rsp+2F0h+var_288], rax
0x18000bd7a  mov     eax, dword ptr [rsp+2F0h+Data]
0x18000bd7e  mov     [rsp+2F0h+var_298], rax
0x18000bd83  mov     eax, dword ptr [rsp+2F0h+Data+4]
0x18000bd87  mov     [rsp+2F0h+var_290], eax
0x18000bd8b  mov     al, byte ptr [rbp+1F0h+var_270]
0x18000bd8e  mov     byte ptr [rsp+2F0h+var_28C], al
0x18000bd92  mov     al, byte ptr [rbp+1F0h+var_270+1]
0x18000bd95  mov     byte ptr [rsp+2F0h+var_28C+1], al
0x18000bd99  mov     rax, [rdi]
0x18000bd9c  mov     rax, [rax+58h]
0x18000bda0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bda5  test    eax, eax
0x18000bda7  js      short loc_18000BDD9
0x18000bda9  lea     ecx, [rbx+30h]; Size
0x18000bdac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bdb1  test    rax, rax
0x18000bdb4  jz      short loc_18000BDE1
0x18000bdb6  mov     [rax], rsi
0x18000bdb9  lea     rcx, [rax+8]; unsigned __int16 *
0x18000bdbd  lea     r8, [rbp+1F0h+Name]; unsigned __int16 *
0x18000bdc1  mov     rsi, rax
0x18000bdc4  lea     edx, [rbx+14h]; unsigned __int64
0x18000bdc7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bdcc  jmp     short loc_18000BDD9
0x18000bdce  mov     rcx, [rsp+2F0h+var_2A8]; hKey
0x18000bdd3  call    cs:__imp_RegCloseKey
0x18000bdd9  inc     r14d
0x18000bddc  jmp     loc_18000BC17
0x18000bde1  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18000bde6  lea     rdx, [rbp+1F0h+Name]; lpSubKey
0x18000bdea  xor     r9d, r9d; Reserved
0x18000bded  xor     r8d, r8d; samDesired
0x18000bdf0  call    cs:__imp_RegDeleteKeyExW
0x18000bdf6  test    rsi, rsi
0x18000bdf9  jz      short loc_18000BE23
0x18000bdfb  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18000be00  lea     rdx, [rsi+8]; lpSubKey
0x18000be04  xor     r9d, r9d; Reserved
0x18000be07  xor     r8d, r8d; samDesired
0x18000be0a  call    cs:__imp_RegDeleteKeyExW
0x18000be10  mov     rbx, [rsi]
0x18000be13  mov     rcx, rsi; Block
0x18000be16  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000be1b  mov     rsi, rbx
0x18000be1e  test    rbx, rbx
0x18000be21  jnz     short loc_18000BDFB
0x18000be23  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18000be28  call    cs:__imp_RegCloseKey
0x18000be2e  mov     rax, [rdi]
0x18000be31  mov     rax, [rax+10h]
0x18000be35  mov     rcx, rdi
0x18000be38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be3d  mov     rcx, [rbp+1F0h+var_30]
0x18000be44  xor     rcx, rsp; StackCookie
0x18000be47  call    __security_check_cookie
0x18000be4c  add     rsp, 2D0h
0x18000be53  pop     r14
0x18000be55  pop     rdi
0x18000be56  pop     rsi
0x18000be57  pop     rbx
0x18000be58  pop     rbp
0x18000be59  retn
```
