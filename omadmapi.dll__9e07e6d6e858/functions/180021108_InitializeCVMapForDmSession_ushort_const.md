# InitializeCVMapForDmSession(ushort const *)

- ea: `0x180021108`
- end: `0x18002130b`
- name: `?InitializeCVMapForDmSession@@YAJPEBG@Z`
- size: `515`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019684`

## callees

- `0x180011b98`
- `0x18001e208`
- `0x180020df4`
- `0x180021108`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021244`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021244`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021280`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021296`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800212d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800212ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021280`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021296`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800212d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800212ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021158`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800211a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021158`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800211a4`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180021120`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180021120`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InitializeCVMapForDmSession(const unsigned __int16 *a1)
{
  char IsStateSeparationEnabled; // al
  unsigned int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  const unsigned __int16 *v8; // rax
  unsigned __int64 cbData; // rax
  __int64 v10; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-10h]
  unsigned int phkResulta; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF
  HKEY v16; // [rsp+60h] [rbp+30h] BYREF

  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         *(wchar_t **)((char *)`DMGetKnownRegPath'::`2'::Paths + (IsStateSeparationEnabled != 0 ? 8 : 0)),
         0,
         0x2001Fu,
         &hKey);
  if ( v3 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xA5,
           (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
           (const char *)v3,
           phkResult);
LABEL_27:
    if ( hKey )
      RegCloseKey(hKey);
    return v4;
  }
  v16 = 0;
  v5 = RegOpenKeyExW(hKey, a1, 0, 0x20019u, &v16);
  if ( v5 )
  {
    v6 = 175;
LABEL_5:
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v6,
           (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
           (const char *)v5,
           phkResulta);
    goto LABEL_25;
  }
  if ( !a1 )
  {
    v4 = -2147024809;
LABEL_23:
    v10 = 180;
    goto LABEL_24;
  }
  v7 = 0x7FFFFFFF;
  v8 = a1;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v7;
  }
  while ( v7 );
  v4 = v7 == 0 ? 0x80070057 : 0;
  if ( !v7 )
    goto LABEL_23;
  cbData = (2 * (0x7FFFFFFF - v7)) & -(__int64)(v7 != 0);
  if ( cbData > 0xFFFFFFFF )
  {
    v4 = -2147024362;
    v10 = 182;
    goto LABEL_24;
  }
  v5 = RegSetValueExW(hKey, L"CurrentEnrollmentId", 0, 1u, (const BYTE *)a1, cbData);
  if ( v5 )
  {
    v6 = 191;
    goto LABEL_5;
  }
  v4 = InitializeCVForDmComponents(a1, hKey);
  if ( (v4 & 0x80000000) != 0 )
  {
    v10 = 194;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
      (const char *)v4,
      phkResulta);
LABEL_25:
    if ( v16 )
      RegCloseKey(v16);
    goto LABEL_27;
  }
  if ( v16 )
    RegCloseKey(v16);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180021108  mov     [rsp-18h+arg_0], rbx
0x18002110d  push    rbp
0x18002110e  push    rsi
0x18002110f  push    rdi
0x180021110  mov     rbp, rsp
0x180021113  sub     rsp, 30h
0x180021117  mov     rdi, rcx
0x18002111a  xor     esi, esi
0x18002111c  mov     [rbp+hKey], rsi
0x180021120  call    cs:__imp_RtlIsStateSeparationEnabled
0x180021127  nop     dword ptr [rax+rax+00h]
0x18002112c  neg     al
0x18002112e  sbb     rdx, rdx
0x180021131  and     edx, 8
0x180021134  lea     rcx, ?Paths@?1??DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z@4QAY01QEBGA; ushort const * (near * `DMGetKnownRegPath(REFKNOWNREGID)'::`2'::Paths)[2]
0x18002113b  lea     rax, [rbp+hKey]
0x18002113f  mov     [rsp+30h+phkResult], rax; unsigned int
0x180021144  mov     r9d, 2001Fh; samDesired
0x18002114a  xor     r8d, r8d; ulOptions
0x18002114d  mov     rdx, [rdx+rcx]; lpSubKey
0x180021151  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021158  call    cs:__imp_RegOpenKeyExW
0x18002115f  nop     dword ptr [rax+rax+00h]
0x180021164  test    eax, eax
0x180021166  jz      short loc_180021187
0x180021168  mov     rcx, [rbp+18h]; this
0x18002116c  mov     r9d, eax; char *
0x18002116f  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x180021176  mov     edx, 0A5h; void *
0x18002117b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180021180  mov     ebx, eax
0x180021182  jmp     loc_1800212E6
0x180021187  mov     [rbp+arg_10], rsi
0x18002118b  lea     rax, [rbp+arg_10]
0x18002118f  mov     [rsp+30h+phkResult], rax; int
0x180021194  mov     r9d, 20019h; samDesired
0x18002119a  xor     r8d, r8d; ulOptions
0x18002119d  mov     rdx, rdi; lpSubKey
0x1800211a0  mov     rcx, [rbp+hKey]; hKey
0x1800211a4  call    cs:__imp_RegOpenKeyExW
0x1800211ab  nop     dword ptr [rax+rax+00h]
0x1800211b0  test    eax, eax
0x1800211b2  jz      short loc_1800211D3
0x1800211b4  mov     edx, 0AFh; void *
0x1800211b9  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x1800211c0  mov     r9d, eax; char *
0x1800211c3  mov     rcx, [rbp+18h]; this
0x1800211c7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800211cc  mov     ebx, eax
0x1800211ce  jmp     loc_1800212D0
0x1800211d3  test    rdi, rdi
0x1800211d6  jz      loc_1800212B2
0x1800211dc  mov     edx, 7FFFFFFFh
0x1800211e1  mov     ecx, edx
0x1800211e3  mov     rax, rdi
0x1800211e6  cmp     [rax], si
0x1800211e9  jz      short loc_1800211F5
0x1800211eb  add     rax, 2
0x1800211ef  sub     rcx, 1
0x1800211f3  jnz     short loc_1800211E6
0x1800211f5  mov     rax, rcx
0x1800211f8  neg     rax
0x1800211fb  sbb     ebx, ebx
0x1800211fd  not     ebx
0x1800211ff  and     ebx, 80070057h
0x180021205  test    rcx, rcx
0x180021208  jz      loc_1800212B7
0x18002120e  sub     rdx, rcx
0x180021211  add     rdx, rdx
0x180021214  neg     rcx
0x180021217  sbb     rax, rax
0x18002121a  and     rax, rdx
0x18002121d  mov     ecx, 0FFFFFFFFh
0x180021222  cmp     rax, rcx
0x180021225  ja      short loc_1800212A6
0x180021227  mov     [rsp+30h+cbData], eax; cbData
0x18002122b  mov     [rsp+30h+phkResult], rdi; lpData
0x180021230  mov     r9d, 1; dwType
0x180021236  xor     r8d, r8d; Reserved
0x180021239  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x180021240  mov     rcx, [rbp+hKey]; hKey
0x180021244  call    cs:__imp_RegSetValueExW
0x18002124b  nop     dword ptr [rax+rax+00h]
0x180021250  test    eax, eax
0x180021252  jz      short loc_18002125E
0x180021254  mov     edx, 0BFh
0x180021259  jmp     loc_1800211B9
0x18002125e  mov     rdx, [rbp+hKey]; HKEY
0x180021262  mov     rcx, rdi; unsigned __int16 *
0x180021265  call    ?InitializeCVForDmComponents@@YAJPEBGPEAUHKEY__@@@Z; InitializeCVForDmComponents(ushort const *,HKEY__ *)
0x18002126a  mov     ebx, eax
0x18002126c  test    eax, eax
0x18002126e  jns     short loc_180021277
0x180021270  mov     edx, 0C2h
0x180021275  jmp     short loc_1800212BC
0x180021277  mov     rcx, [rbp+arg_10]; hKey
0x18002127b  test    rcx, rcx
0x18002127e  jz      short loc_18002128D
0x180021280  call    cs:__imp_RegCloseKey
0x180021287  nop     dword ptr [rax+rax+00h]
0x18002128c  nop
0x18002128d  mov     rcx, [rbp+hKey]; hKey
0x180021291  test    rcx, rcx
0x180021294  jz      short loc_1800212A2
0x180021296  call    cs:__imp_RegCloseKey
0x18002129d  nop     dword ptr [rax+rax+00h]
0x1800212a2  xor     eax, eax
0x1800212a4  jmp     short loc_1800212FD
0x1800212a6  mov     ebx, 80070216h
0x1800212ab  mov     edx, 0B6h
0x1800212b0  jmp     short loc_1800212BC
0x1800212b2  mov     ebx, 80070057h
0x1800212b7  mov     edx, 0B4h; void *
0x1800212bc  mov     r9d, ebx; char *
0x1800212bf  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x1800212c6  mov     rcx, [rbp+18h]; this
0x1800212ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800212cf  nop
0x1800212d0  mov     rcx, [rbp+arg_10]; hKey
0x1800212d4  test    rcx, rcx
0x1800212d7  jz      short loc_1800212E6
0x1800212d9  call    cs:__imp_RegCloseKey
0x1800212e0  nop     dword ptr [rax+rax+00h]
0x1800212e5  nop
0x1800212e6  mov     rcx, [rbp+hKey]; hKey
0x1800212ea  test    rcx, rcx
0x1800212ed  jz      short loc_1800212FB
0x1800212ef  call    cs:__imp_RegCloseKey
0x1800212f6  nop     dword ptr [rax+rax+00h]
0x1800212fb  mov     eax, ebx
0x1800212fd  mov     rbx, [rsp+30h+arg_0]
0x180021302  add     rsp, 30h
0x180021306  pop     rdi
0x180021307  pop     rsi
0x180021308  pop     rbp
0x180021309  retn
```
