# GetDeviceEnrollerKey(ushort const *,HKEY__ * *,int)

- ea: `0x18001ef10`
- end: `0x18001f0ba`
- name: `?GetDeviceEnrollerKey@@YAJPEBGPEAPEAUHKEY__@@H@Z`
- size: `426`
- prototype: `__int64 __fastcall(PCWSTR pszMore, HKEY *, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f400`
- `0x18001f5fc`
- `0x18001ffb4`

## callees

- `0x1800039f0`
- `0x1800043a8`
- `0x18000bab4`
- `0x18001ef10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f016`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f003`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f003`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f00e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f068`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f08f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f00e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f068`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f08f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f045`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f045`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001ef8f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001ef8f`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001efb8`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001efb8`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001efda`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001efda`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetDeviceEnrollerKey(PCWSTR pszMore, HKEY *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 v7; // rcx
  char IsStateSeparationEnabled; // al
  LSTATUS v9; // eax
  HKEY v10; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  if ( !pszMore )
  {
    v4 = 4085;
LABEL_3:
    v5 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
      (const char *)(unsigned int)v5,
      phkResult);
    return (unsigned int)v5;
  }
  if ( !a2 )
  {
    v4 = 4086;
    goto LABEL_3;
  }
  *a2 = 0;
  memset_0(pszPathOut, 0, 0x208u);
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v7);
  v5 = PathCchCombine(
         pszPathOut,
         0x104u,
         *(wchar_t **)((char *)off_18003CA80 + (IsStateSeparationEnabled != 0 ? 8 : 0)),
         pszMore);
  if ( v5 < 0 )
  {
    v4 = 4091;
    goto LABEL_4;
  }
  v5 = PathCchAppend(pszPathOut, 0x104u, L"DeviceEnroller");
  if ( v5 < 0 )
  {
    v4 = 4092;
    goto LABEL_4;
  }
  hKey = 0;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszPathOut, 0, 0xF003Fu, &hKey);
  v5 = v9;
  if ( v9 > 0 )
    v5 = (unsigned __int16)v9 | 0x80070000;
  if ( v5 < 0 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v5;
  }
  v10 = hKey;
  hKey = 0;
  *a2 = v10;
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18001ef10  mov     [rsp-8+arg_10], rbx
0x18001ef15  push    rbp
0x18001ef16  push    rsi
0x18001ef17  push    rdi
0x18001ef18  lea     rbp, [rsp-160h]
0x18001ef20  sub     rsp, 260h
0x18001ef27  mov     rax, cs:__security_cookie
0x18001ef2e  xor     rax, rsp
0x18001ef31  mov     [rbp+170h+var_20], rax
0x18001ef38  mov     rsi, rdx
0x18001ef3b  mov     rbx, rcx
0x18001ef3e  test    rcx, rcx
0x18001ef41  jnz     short loc_18001EF6A
0x18001ef43  mov     edx, 0FF5h; void *
0x18001ef48  mov     ebx, 80070057h
0x18001ef4d  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18001ef54  mov     r9d, ebx; char *
0x18001ef57  mov     rcx, [rbp+178h]; this
0x18001ef5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ef63  mov     eax, ebx
0x18001ef65  jmp     loc_18001F098
0x18001ef6a  test    rsi, rsi
0x18001ef6d  jnz     short loc_18001EF76
0x18001ef6f  mov     edx, 0FF6h
0x18001ef74  jmp     short loc_18001EF48
0x18001ef76  mov     qword ptr [rdx], 0
0x18001ef7d  xor     edx, edx; Val
0x18001ef7f  mov     r8d, 208h; Size
0x18001ef85  lea     rcx, [rsp+270h+pszPathOut]; void *
0x18001ef8a  call    memset_0
0x18001ef8f  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001ef95  neg     al
0x18001ef97  sbb     r8, r8
0x18001ef9a  and     r8d, 8
0x18001ef9e  lea     rax, off_18003CA80; "Software\\Microsoft\\Enrollments\\"
0x18001efa5  mov     r9, rbx; pszMore
0x18001efa8  mov     r8, [r8+rax]; pszPathIn
0x18001efac  mov     edi, 104h
0x18001efb1  mov     edx, edi; cchPathOut
0x18001efb3  lea     rcx, [rsp+270h+pszPathOut]; pszPathOut
0x18001efb8  call    cs:__imp_PathCchCombine
0x18001efbe  mov     ebx, eax
0x18001efc0  test    eax, eax
0x18001efc2  jns     short loc_18001EFCB
0x18001efc4  mov     edx, 0FFBh
0x18001efc9  jmp     short loc_18001EF4D
0x18001efcb  lea     r8, pszMore; "DeviceEnroller"
0x18001efd2  mov     rdx, rdi; cchPath
0x18001efd5  lea     rcx, [rsp+270h+pszPathOut]; pszPath
0x18001efda  call    cs:__imp_PathCchAppend
0x18001efe0  mov     ebx, eax
0x18001efe2  test    eax, eax
0x18001efe4  jns     short loc_18001EFF0
0x18001efe6  mov     edx, 0FFCh
0x18001efeb  jmp     loc_18001EF4D
0x18001eff0  mov     [rsp+270h+hKey], 0
0x18001eff9  mov     rdi, [rsp+270h+hKey]
0x18001effe  test    rdi, rdi
0x18001f001  jz      short loc_18001F01D
0x18001f003  call    cs:__imp_GetLastError
0x18001f009  mov     ebx, eax
0x18001f00b  mov     rcx, rdi; hKey
0x18001f00e  call    cs:__imp_RegCloseKey
0x18001f014  mov     ecx, ebx; dwErrCode
0x18001f016  call    cs:__imp_SetLastError
0x18001f01c  nop
0x18001f01d  mov     [rsp+270h+hKey], 0
0x18001f026  lea     rax, [rsp+270h+hKey]
0x18001f02b  mov     qword ptr [rsp+270h+phkResult], rax; phkResult
0x18001f030  mov     r9d, 0F003Fh; samDesired
0x18001f036  xor     r8d, r8d; ulOptions
0x18001f039  lea     rdx, [rsp+270h+pszPathOut]; lpSubKey
0x18001f03e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f045  call    cs:__imp_RegOpenKeyExW
0x18001f04b  mov     ebx, eax
0x18001f04d  test    eax, eax
0x18001f04f  jle     short loc_18001F05A
0x18001f051  movzx   ebx, ax
0x18001f054  or      ebx, 80070000h
0x18001f05a  test    ebx, ebx
0x18001f05c  jns     short loc_18001F074
0x18001f05e  mov     rcx, [rsp+270h+hKey]; hKey
0x18001f063  test    rcx, rcx
0x18001f066  jz      short loc_18001F06F
0x18001f068  call    cs:__imp_RegCloseKey
0x18001f06e  nop
0x18001f06f  jmp     loc_18001EF63
0x18001f074  mov     rax, [rsp+270h+hKey]
0x18001f079  mov     [rsp+270h+hKey], 0
0x18001f082  mov     [rsi], rax
0x18001f085  mov     rcx, [rsp+270h+hKey]; hKey
0x18001f08a  test    rcx, rcx
0x18001f08d  jz      short loc_18001F096
0x18001f08f  call    cs:__imp_RegCloseKey
0x18001f095  nop
0x18001f096  xor     eax, eax
0x18001f098  mov     rcx, [rbp+170h+var_20]
0x18001f09f  xor     rcx, rsp; StackCookie
0x18001f0a2  call    __security_check_cookie
0x18001f0a7  mov     rbx, [rsp+270h+arg_10]
0x18001f0af  add     rsp, 260h
0x18001f0b6  pop     rdi
0x18001f0b7  pop     rsi
0x18001f0b8  pop     rbp
0x18001f0b9  retn
```
