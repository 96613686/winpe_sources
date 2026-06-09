# IsRepeatingMsg(ushort *,unsigned __int64,bool *)

- ea: `0x18001e910`
- end: `0x18001eacc`
- name: `?IsRepeatingMsg@@YAJPEAG_KPEA_N@Z`
- size: `444`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, unsigned __int64, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f690`

## callees

- `0x1800075f0`
- `0x180007930`
- `0x180011b98`
- `0x18001e910`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eaa3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eaa3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ea11`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ea11`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001ea3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001ea3b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001ea85`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001ea85`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001e934`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001e934`
- `DMCmnUtils!BigStrcat` at `0x18001e967`
- `DMCmnUtils!BigStrcat` at `0x18001e967`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsRepeatingMsg(LPCWSTR lpValueName, __int64 a2, bool *a3)
{
  char IsStateSeparationEnabled; // al
  const wchar_t *v6; // rdx
  WCHAR *v7; // rbx
  signed int v9; // eax
  unsigned int v10; // edi
  LSTATUS ValueW; // eax
  int v12; // edi
  LSTATUS v13; // eax
  int pdwType; // [rsp+20h] [rbp-30h]
  __int64 pvData; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  __int64 pcbData; // [rsp+88h] [rbp+38h] BYREF
  HANDLE hObject; // [rsp+90h] [rbp+40h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+98h] [rbp+48h] BYREF

  pcbData = a2;
  *a3 = 0;
  hObject = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(lpValueName);
  v6 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
  if ( !IsStateSeparationEnabled )
    v6 = L"Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
  v7 = BigStrcat(3u, v6, L"\\", L"SessionHash");
  if ( !v7 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x194,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\throttling.cpp",
      (const char *)0x8007000ELL,
      pdwType);
    return 2147942414LL;
  }
  pvData = 0;
  LODWORD(pcbData) = 8;
  hObject = 0;
  v9 = AcquireOmaDmMutex(&hObject);
  v10 = v9;
  if ( v9 >= 0 )
  {
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v7, lpValueName, 8u, 0, &pvData, (LPDWORD)&pcbData);
    v10 = ValueW;
    if ( (ValueW & 0xFFFFFFFD) != 0 )
    {
      if ( ValueW <= 0 )
        goto LABEL_16;
      v12 = (unsigned __int16)ValueW;
    }
    else
    {
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( v10 != 2 && (unsigned __int64)(*(_QWORD *)&SystemTimeAsFileTime - pvData) < 0xB2D05E00 )
        *a3 = 1;
      v13 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v7, lpValueName, 3u, &SystemTimeAsFileTime, 8u);
      v10 = v13;
      if ( v13 <= 0 )
        goto LABEL_16;
      v12 = (unsigned __int16)v13;
    }
    v10 = v12 | 0x80070000;
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x19C,
    (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\throttling.cpp",
    (const char *)(unsigned int)v9,
    pdwType);
LABEL_16:
  LocalFree(v7);
  if ( hObject )
    ReleaseOmaDmMutex(hObject);
  return v10;
}

```

## disassembly

```asm
0x18001e910  mov     [rsp-28h+arg_8], rdx
0x18001e915  push    rbp
0x18001e916  push    rbx
0x18001e917  push    rsi
0x18001e918  push    rdi
0x18001e919  push    r14
0x18001e91b  mov     rbp, rsp
0x18001e91e  sub     rsp, 50h
0x18001e922  mov     rsi, r8
0x18001e925  mov     r14, rcx
0x18001e928  mov     byte ptr [r8], 0
0x18001e92c  mov     [rbp+hObject], 0
0x18001e934  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001e93b  nop     dword ptr [rax+rax+00h]
0x18001e940  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\OMAD"...
0x18001e947  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x18001e94e  test    al, al
0x18001e950  cmovz   rdx, rcx
0x18001e954  lea     r9, aSessionhash; "SessionHash"
0x18001e95b  lea     r8, asc_1800273F4; "\\"
0x18001e962  mov     ecx, 3
0x18001e967  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x18001e96e  nop     dword ptr [rax+rax+00h]
0x18001e973  mov     rbx, rax
0x18001e976  test    rax, rax
0x18001e979  jnz     short loc_18001E9A0
0x18001e97b  mov     rcx, [rbp+28h]; this
0x18001e97f  mov     ebx, 8007000Eh
0x18001e984  mov     r9d, ebx; char *
0x18001e987  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x18001e98e  mov     edx, 194h; void *
0x18001e993  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e998  nop
0x18001e999  mov     eax, ebx
0x18001e99b  jmp     loc_18001EAC0
0x18001e9a0  mov     [rbp+var_10], 0
0x18001e9a8  mov     dword ptr [rbp+arg_8], 8
0x18001e9af  mov     [rbp+hObject], 0
0x18001e9b7  lea     rcx, [rbp+hObject]; void **
0x18001e9bb  call    ?AcquireOmaDmMutex@@YAJPEAPEAX@Z; AcquireOmaDmMutex(void * *)
0x18001e9c0  mov     edi, eax
0x18001e9c2  test    eax, eax
0x18001e9c4  jns     short loc_18001E9E3
0x18001e9c6  mov     rcx, [rbp+28h]; this
0x18001e9ca  mov     r9d, eax; char *
0x18001e9cd  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x18001e9d4  mov     edx, 19Ch; void *
0x18001e9d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e9de  jmp     loc_18001EAA0
0x18001e9e3  lea     rax, [rbp+arg_8]
0x18001e9e7  mov     [rsp+50h+pcbData], rax; pcbData
0x18001e9ec  lea     rax, [rbp+var_10]
0x18001e9f0  mov     [rsp+50h+pvData], rax; pvData
0x18001e9f5  mov     [rsp+50h+pdwType], 0; pdwType
0x18001e9fe  mov     r9d, 8; dwFlags
0x18001ea04  mov     r8, r14; lpValue
0x18001ea07  mov     rdx, rbx; lpSubKey
0x18001ea0a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001ea11  call    cs:__imp_RegGetValueW
0x18001ea18  nop     dword ptr [rax+rax+00h]
0x18001ea1d  mov     edi, eax
0x18001ea1f  test    eax, 0FFFFFFFDh
0x18001ea24  jz      short loc_18001EA2F
0x18001ea26  test    eax, eax
0x18001ea28  jle     short loc_18001EAA0
0x18001ea2a  movzx   edi, di
0x18001ea2d  jmp     short loc_18001EA9A
0x18001ea2f  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001ea37  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001ea3b  call    cs:__imp_GetSystemTimeAsFileTime
0x18001ea42  nop     dword ptr [rax+rax+00h]
0x18001ea47  cmp     edi, 2
0x18001ea4a  jz      short loc_18001EA61
0x18001ea4c  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001ea50  sub     rax, [rbp+var_10]
0x18001ea54  mov     edx, 0B2D05E00h
0x18001ea59  cmp     rax, rdx
0x18001ea5c  jnb     short loc_18001EA61
0x18001ea5e  mov     byte ptr [rsi], 1
0x18001ea61  mov     dword ptr [rsp+50h+pvData], 8; cbData
0x18001ea69  lea     rax, [rbp+SystemTimeAsFileTime]
0x18001ea6d  mov     [rsp+50h+pdwType], rax; lpData
0x18001ea72  mov     r9d, 3; dwType
0x18001ea78  mov     r8, r14; lpValueName
0x18001ea7b  mov     rdx, rbx; lpSubKey
0x18001ea7e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ea85  call    cs:__imp_RegSetKeyValueW
0x18001ea8c  nop     dword ptr [rax+rax+00h]
0x18001ea91  mov     edi, eax
0x18001ea93  test    eax, eax
0x18001ea95  jle     short loc_18001EAA0
0x18001ea97  movzx   edi, ax
0x18001ea9a  or      edi, 80070000h
0x18001eaa0  mov     rcx, rbx; hMem
0x18001eaa3  call    cs:__imp_LocalFree
0x18001eaaa  nop     dword ptr [rax+rax+00h]
0x18001eaaf  nop
0x18001eab0  mov     rcx, [rbp+hObject]; hObject
0x18001eab4  test    rcx, rcx
0x18001eab7  jz      short loc_18001EABE
0x18001eab9  call    ?ReleaseOmaDmMutex@@YAXPEAX@Z; ReleaseOmaDmMutex(void *)
0x18001eabe  mov     eax, edi
0x18001eac0  add     rsp, 50h
0x18001eac4  pop     r14
0x18001eac6  pop     rdi
0x18001eac7  pop     rsi
0x18001eac8  pop     rbx
0x18001eac9  pop     rbp
0x18001eaca  retn
```
