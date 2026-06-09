# UpdateSessionState(ushort const *,OMADM_SESSION_STATE)

- ea: `0x180020268`
- end: `0x180020408`
- name: `?UpdateSessionState@@YAJPEBGW4OMADM_SESSION_STATE@@@Z`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180019684`

## callees

- `0x1800075f0`
- `0x180007930`
- `0x180011b98`
- `0x18001e208`
- `0x180020268`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800202ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800202ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800202ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800202ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002036e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800203ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002036e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800203ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800202df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800203ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800202df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800203ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002031d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002031d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180020389`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180020389`

## pseudocode

```c
__int64 __fastcall UpdateSessionState(const WCHAR *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  HKEY v4; // rdi
  DWORD LastError; // ebx
  unsigned int v6; // eax
  __int64 v7; // rdx
  LSTATUS v8; // eax
  int phkResult; // [rsp+20h] [rbp-20h]
  unsigned int phkResulta; // [rsp+20h] [rbp-20h]
  BYTE Data[8]; // [rsp+30h] [rbp-10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HKEY hKey; // [rsp+70h] [rbp+30h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp+38h] BYREF

  *(_DWORD *)Data = 7;
  SystemTimeAsFileTime = 0;
  hKey = 0;
  hObject = 0;
  v2 = AcquireOmaDmMutex(&hObject);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\throttling.cpp",
      (const char *)(unsigned int)v2,
      phkResult);
    goto LABEL_12;
  }
  v4 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v4);
    SetLastError(LastError);
  }
  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a1, 0, 0x20006u, &hKey);
  if ( v6 )
  {
    v7 = 364;
LABEL_7:
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v7,
           (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmapi\\src\\throttling.cpp",
           (const char *)v6,
           phkResulta);
    goto LABEL_12;
  }
  v6 = RegSetValueExW(hKey, L"SessionState", 0, 4u, Data, 4u);
  if ( v6 )
  {
    v7 = 374;
    goto LABEL_7;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v8 = RegSetValueExW(hKey, L"SessionStateTimeStamp", 0, 3u, (const BYTE *)&SystemTimeAsFileTime, 8u);
  v3 = v8;
  if ( v8 > 0 )
    v3 = (unsigned __int16)v8 | 0x80070000;
LABEL_12:
  if ( hObject )
    ReleaseOmaDmMutex(hObject);
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x180020268  mov     [rsp-18h+arg_0], rbx
0x18002026d  push    rbp
0x18002026e  push    rsi
0x18002026f  push    rdi
0x180020270  mov     rbp, rsp
0x180020273  sub     rsp, 40h
0x180020277  mov     rsi, rcx
0x18002027a  mov     dword ptr [rbp+Data], 7
0x180020281  lea     rcx, [rbp+hObject]; void **
0x180020285  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18002028d  mov     [rbp+hKey], 0
0x180020295  mov     [rbp+hObject], 0
0x18002029d  call    ?AcquireOmaDmMutex@@YAJPEAPEAX@Z; AcquireOmaDmMutex(void * *)
0x1800202a2  mov     ebx, eax
0x1800202a4  test    eax, eax
0x1800202a6  jns     short loc_1800202C5
0x1800202a8  mov     rcx, [rbp+18h]; this
0x1800202ac  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x1800202b3  mov     r9d, eax; char *
0x1800202b6  mov     edx, 163h; void *
0x1800202bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800202c0  jmp     loc_1800203D5
0x1800202c5  mov     rdi, [rbp+hKey]
0x1800202c9  test    rdi, rdi
0x1800202cc  jz      short loc_1800202F9
0x1800202ce  call    cs:__imp_GetLastError
0x1800202d5  nop     dword ptr [rax+rax+00h]
0x1800202da  mov     rcx, rdi; hKey
0x1800202dd  mov     ebx, eax
0x1800202df  call    cs:__imp_RegCloseKey
0x1800202e6  nop     dword ptr [rax+rax+00h]
0x1800202eb  mov     ecx, ebx; dwErrCode
0x1800202ed  call    cs:__imp_SetLastError
0x1800202f4  nop     dword ptr [rax+rax+00h]
0x1800202f9  lea     rax, [rbp+hKey]
0x1800202fd  mov     [rbp+hKey], 0
0x180020305  mov     r9d, 20006h; samDesired
0x18002030b  mov     [rsp+40h+phkResult], rax; unsigned int
0x180020310  xor     r8d, r8d; ulOptions
0x180020313  mov     rdx, rsi; lpSubKey
0x180020316  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002031d  call    cs:__imp_RegOpenKeyExW
0x180020324  nop     dword ptr [rax+rax+00h]
0x180020329  test    eax, eax
0x18002032b  jz      short loc_18002034C
0x18002032d  mov     edx, 16Ch; void *
0x180020332  mov     rcx, [rbp+18h]; this
0x180020336  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\dm\\omadm\\omadmapi"...
0x18002033d  mov     r9d, eax; char *
0x180020340  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180020345  mov     ebx, eax
0x180020347  jmp     loc_1800203D5
0x18002034c  mov     rcx, [rbp+hKey]; hKey
0x180020350  lea     rax, [rbp+Data]
0x180020354  mov     r9d, 4; dwType
0x18002035a  lea     rdx, aSessionstate; "SessionState"
0x180020361  mov     [rsp+40h+cbData], r9d; cbData
0x180020366  xor     r8d, r8d; Reserved
0x180020369  mov     [rsp+40h+phkResult], rax; lpData
0x18002036e  call    cs:__imp_RegSetValueExW
0x180020375  nop     dword ptr [rax+rax+00h]
0x18002037a  test    eax, eax
0x18002037c  jz      short loc_180020385
0x18002037e  mov     edx, 176h
0x180020383  jmp     short loc_180020332
0x180020385  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180020389  call    cs:__imp_GetSystemTimeAsFileTime
0x180020390  nop     dword ptr [rax+rax+00h]
0x180020395  mov     rcx, [rbp+hKey]; hKey
0x180020399  lea     rax, [rbp+SystemTimeAsFileTime]
0x18002039d  mov     [rsp+40h+cbData], 8; cbData
0x1800203a5  lea     rdx, aSessionstateti; "SessionStateTimeStamp"
0x1800203ac  mov     r9d, 3; dwType
0x1800203b2  mov     [rsp+40h+phkResult], rax; lpData
0x1800203b7  xor     r8d, r8d; Reserved
0x1800203ba  call    cs:__imp_RegSetValueExW
0x1800203c1  nop     dword ptr [rax+rax+00h]
0x1800203c6  mov     ebx, eax
0x1800203c8  test    eax, eax
0x1800203ca  jle     short loc_1800203D5
0x1800203cc  movzx   ebx, ax
0x1800203cf  or      ebx, 80070000h
0x1800203d5  mov     rcx, [rbp+hObject]; hObject
0x1800203d9  test    rcx, rcx
0x1800203dc  jz      short loc_1800203E3
0x1800203de  call    ?ReleaseOmaDmMutex@@YAXPEAX@Z; ReleaseOmaDmMutex(void *)
0x1800203e3  mov     rcx, [rbp+hKey]; hKey
0x1800203e7  test    rcx, rcx
0x1800203ea  jz      short loc_1800203F8
0x1800203ec  call    cs:__imp_RegCloseKey
0x1800203f3  nop     dword ptr [rax+rax+00h]
0x1800203f8  mov     eax, ebx
0x1800203fa  mov     rbx, [rsp+40h+arg_0]
0x1800203ff  add     rsp, 40h
0x180020403  pop     rdi
0x180020404  pop     rsi
0x180020405  pop     rbp
0x180020406  retn
```
