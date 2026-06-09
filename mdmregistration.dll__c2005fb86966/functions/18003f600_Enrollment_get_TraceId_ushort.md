# Enrollment::get_TraceId(ushort * *)

- ea: `0x18003f600`
- end: `0x18003f83c`
- name: `?get_TraceId@Enrollment@@UEAAJPEAPEAG@Z`
- size: `572`
- prototype: `__int64 __fastcall(Enrollment *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x18000bc44`
- `0x18003f1c4`
- `0x18003f600`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18003f656`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18003f656`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f7f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003f7f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f7db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003f7db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f744`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f763`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f763`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f755`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f807`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f755`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f807`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f793`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f793`
- `OLEAUT32!__imp_SysAllocString` at `0x18003f7cc`
- `OLEAUT32!__imp_SysAllocString` at `0x18003f7cc`

## pseudocode

```c
__int64 __fastcall Enrollment::get_TraceId(Enrollment *this, unsigned __int16 **a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // rcx
  char IsStateSeparationEnabled; // al
  __int64 v8; // r8
  WCHAR *v9; // rax
  WCHAR *v10; // rcx
  WCHAR *v11; // rdx
  signed int String; // ebx
  unsigned __int64 v13; // rcx
  __int64 v14; // rax
  DWORD LastError; // ebx
  LSTATUS v16; // eax
  HKEY v17; // rcx
  HANDLE ProcessHeap; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR *psz; // [rsp+38h] [rbp-C8h]
  WCHAR SubKey[264]; // [rsp+40h] [rbp-C0h] BYREF

  memset_0(SubKey, 0, 0x208u);
  v4 = 2147483646;
  hKey = 0;
  psz = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v6, v5);
  v8 = 260;
  v9 = *(wchar_t **)((char *)off_18004F588 + (IsStateSeparationEnabled != 0 ? 8 : 0));
  v10 = SubKey;
  do
  {
    if ( !v4 )
      break;
    if ( !*v9 )
      break;
    *v10++ = *v9++;
    --v4;
    --v8;
  }
  while ( v8 );
  v11 = v10 - 1;
  String = v8 == 0 ? 0x8007007A : 0;
  if ( v8 )
    v11 = v10;
  *v11 = 0;
  if ( !v8 )
    goto LABEL_20;
  String = StringCchCatW(SubKey, 0x104u, L"Status");
  if ( String < 0 )
    goto LABEL_20;
  String = StringCchCatW(SubKey, 0x104u, L"\\");
  if ( String < 0 )
    goto LABEL_20;
  v13 = (unsigned __int64)this + 150;
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(v13 + 2 * v14) );
  String = StringCchCatW(SubKey, 0x104u, (const unsigned __int16 *)(v13 & -(__int64)(v14 != 0)));
  if ( String < 0 )
    goto LABEL_20;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(hKey);
    SetLastError(LastError);
  }
  hKey = 0;
  v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
  String = v16;
  if ( v16 > 0 )
    String = (unsigned __int16)v16 | 0x80070000;
  v17 = hKey;
  if ( String >= 0 )
  {
    String = RegistryAllocAndGetString(hKey);
    if ( String >= 0 )
    {
      *a2 = SysAllocString(psz);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, psz);
    }
LABEL_20:
    v17 = hKey;
  }
  if ( v17 )
    RegCloseKey(v17);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18003f600  mov     [rsp-8+arg_10], rbx
0x18003f605  push    rbp
0x18003f606  push    rsi
0x18003f607  push    rdi
0x18003f608  push    r14
0x18003f60a  push    r15
0x18003f60c  lea     rbp, [rsp-160h]
0x18003f614  sub     rsp, 260h
0x18003f61b  mov     rax, cs:__security_cookie
0x18003f622  xor     rax, rsp
0x18003f625  mov     [rbp+180h+var_30], rax
0x18003f62c  mov     rsi, rdx
0x18003f62f  mov     rdi, rcx
0x18003f632  xor     edx, edx; Val
0x18003f634  lea     rcx, [rsp+280h+SubKey]; void *
0x18003f639  mov     r8d, 208h; Size
0x18003f63f  call    memset_0
0x18003f644  xor     r14d, r14d
0x18003f647  mov     ebx, 7FFFFFFEh
0x18003f64c  mov     [rsp+280h+hKey], r14
0x18003f651  mov     [rsp+280h+psz], r14
0x18003f656  call    cs:__imp_RtlIsStateSeparationEnabled
0x18003f65d  nop     dword ptr [rax+rax+00h]
0x18003f662  neg     al
0x18003f664  mov     r15d, 104h
0x18003f66a  lea     rax, off_18004F588; "Software\\Microsoft\\Enrollments\\"
0x18003f671  mov     r8d, r15d
0x18003f674  sbb     rcx, rcx
0x18003f677  and     ecx, 8
0x18003f67a  mov     rax, [rcx+rax]
0x18003f67e  lea     rcx, [rsp+280h+SubKey]
0x18003f683  test    rbx, rbx
0x18003f686  jz      short loc_18003F6A4
0x18003f688  movzx   edx, word ptr [rax]
0x18003f68b  test    dx, dx
0x18003f68e  jz      short loc_18003F6A4
0x18003f690  mov     [rcx], dx
0x18003f693  add     rax, 2
0x18003f697  add     rcx, 2
0x18003f69b  dec     rbx
0x18003f69e  sub     r8, 1
0x18003f6a2  jnz     short loc_18003F683
0x18003f6a4  mov     rax, r8
0x18003f6a7  lea     rdx, [rcx-2]
0x18003f6ab  neg     rax
0x18003f6ae  sbb     ebx, ebx
0x18003f6b0  not     ebx
0x18003f6b2  and     ebx, 8007007Ah
0x18003f6b8  test    r8, r8
0x18003f6bb  cmovnz  rdx, rcx
0x18003f6bf  mov     [rdx], r14w
0x18003f6c3  jz      loc_18003F7FD
0x18003f6c9  lea     r8, aStatus; "Status"
0x18003f6d0  mov     rdx, r15; unsigned __int64
0x18003f6d3  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x18003f6d8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003f6dd  mov     ebx, eax
0x18003f6df  test    eax, eax
0x18003f6e1  js      loc_18003F7FD
0x18003f6e7  lea     r8, asc_180063078; "\\"
0x18003f6ee  mov     rdx, r15; unsigned __int64
0x18003f6f1  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x18003f6f6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003f6fb  mov     ebx, eax
0x18003f6fd  test    eax, eax
0x18003f6ff  js      loc_18003F7FD
0x18003f705  lea     rcx, [rdi+96h]
0x18003f70c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003f710  inc     rax
0x18003f713  cmp     [rcx+rax*2], r14w
0x18003f718  jnz     short loc_18003F710
0x18003f71a  neg     rax
0x18003f71d  mov     rdx, r15; unsigned __int64
0x18003f720  sbb     r8, r8
0x18003f723  and     r8, rcx; unsigned __int16 *
0x18003f726  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x18003f72b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003f730  mov     ebx, eax
0x18003f732  test    eax, eax
0x18003f734  js      loc_18003F7FD
0x18003f73a  mov     rdi, [rsp+280h+hKey]
0x18003f73f  test    rdi, rdi
0x18003f742  jz      short loc_18003F76F
0x18003f744  call    cs:__imp_GetLastError
0x18003f74b  nop     dword ptr [rax+rax+00h]
0x18003f750  mov     rcx, rdi; hKey
0x18003f753  mov     ebx, eax
0x18003f755  call    cs:__imp_RegCloseKey
0x18003f75c  nop     dword ptr [rax+rax+00h]
0x18003f761  mov     ecx, ebx; dwErrCode
0x18003f763  call    cs:__imp_SetLastError
0x18003f76a  nop     dword ptr [rax+rax+00h]
0x18003f76f  lea     rax, [rsp+280h+hKey]
0x18003f774  mov     [rsp+280h+hKey], r14
0x18003f779  mov     r9d, 1; samDesired
0x18003f77f  mov     [rsp+280h+phkResult], rax; phkResult
0x18003f784  xor     r8d, r8d; ulOptions
0x18003f787  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x18003f78c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003f793  call    cs:__imp_RegOpenKeyExW
0x18003f79a  nop     dword ptr [rax+rax+00h]
0x18003f79f  mov     ebx, eax
0x18003f7a1  test    eax, eax
0x18003f7a3  jle     short loc_18003F7AE
0x18003f7a5  movzx   ebx, ax
0x18003f7a8  or      ebx, 80070000h
0x18003f7ae  mov     rcx, [rsp+280h+hKey]; hKey
0x18003f7b3  test    ebx, ebx
0x18003f7b5  js      short loc_18003F802
0x18003f7b7  lea     r8, [rsp+280h+psz]
0x18003f7bc  call    RegistryAllocAndGetString
0x18003f7c1  mov     ebx, eax
0x18003f7c3  test    eax, eax
0x18003f7c5  js      short loc_18003F7FD
0x18003f7c7  mov     rcx, [rsp+280h+psz]; psz
0x18003f7cc  call    cs:__imp_SysAllocString
0x18003f7d3  nop     dword ptr [rax+rax+00h]
0x18003f7d8  mov     [rsi], rax
0x18003f7db  call    cs:__imp_GetProcessHeap
0x18003f7e2  nop     dword ptr [rax+rax+00h]
0x18003f7e7  mov     r8, [rsp+280h+psz]; lpMem
0x18003f7ec  xor     edx, edx; dwFlags
0x18003f7ee  mov     rcx, rax; hHeap
0x18003f7f1  call    cs:__imp_HeapFree
0x18003f7f8  nop     dword ptr [rax+rax+00h]
0x18003f7fd  mov     rcx, [rsp+280h+hKey]; hKey
0x18003f802  test    rcx, rcx
0x18003f805  jz      short loc_18003F813
0x18003f807  call    cs:__imp_RegCloseKey
0x18003f80e  nop     dword ptr [rax+rax+00h]
0x18003f813  mov     eax, ebx
0x18003f815  mov     rcx, [rbp+180h+var_30]
0x18003f81c  xor     rcx, rsp; StackCookie
0x18003f81f  call    __security_check_cookie
0x18003f824  mov     rbx, [rsp+280h+arg_10]
0x18003f82c  add     rsp, 260h
0x18003f833  pop     r15
0x18003f835  pop     r14
0x18003f837  pop     rdi
0x18003f838  pop     rsi
0x18003f839  pop     rbp
0x18003f83a  retn
```
