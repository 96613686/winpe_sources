# InitializeCVMapForDmSession(ushort const *)

- ea: `0x14000e710`
- end: `0x14000e905`
- name: `?InitializeCVMapForDmSession@@YAJPEBG@Z`
- size: `501`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000fff0`

## callees

- `0x140008504`
- `0x14000e3e4`
- `0x14000e710`
- `0x14000e90c`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x14000e728`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14000e728`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000e83e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000e83e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000e760`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000e7a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000e760`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000e7a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e87a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e890`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e8d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e8e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e87a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e890`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e8d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000e8e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall InitializeCVMapForDmSession(const unsigned __int16 *a1)
{
  char IsStateSeparationEnabled; // al
  unsigned int v3; // eax
  unsigned int v4; // r8d
  unsigned int v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // r8d
  __int64 v8; // rdx
  __int64 v9; // rcx
  const unsigned __int16 *v10; // rax
  unsigned __int64 cbData; // rax
  __int64 v12; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-10h]
  unsigned int phkResulta; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF
  HKEY v18; // [rsp+60h] [rbp+30h] BYREF

  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         *(wchar_t **)((char *)`DMGetKnownRegPath'::`2'::Paths + (IsStateSeparationEnabled != 0 ? 8 : 0)),
         0,
         0x2001Fu,
         &hKey);
  if ( v3 )
  {
    v5 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0xA5, v4, (const char *)v3, phkResult);
LABEL_27:
    if ( hKey )
      RegCloseKey(hKey);
    return v5;
  }
  v18 = 0;
  v6 = RegOpenKeyExW(hKey, a1, 0, 0x20019u, &v18);
  if ( v6 )
  {
    v8 = 175;
LABEL_5:
    v5 = wil::details::in1diag3::Return_Win32(retaddr, (void *)v8, v7, (const char *)v6, phkResulta);
    goto LABEL_25;
  }
  if ( !a1 )
  {
    v5 = -2147024809;
LABEL_23:
    v12 = 180;
    goto LABEL_24;
  }
  v9 = 0x7FFFFFFF;
  v10 = a1;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  v5 = v9 == 0 ? 0x80070057 : 0;
  if ( !v9 )
    goto LABEL_23;
  cbData = (2 * (0x7FFFFFFF - v9)) & -(__int64)(v9 != 0);
  if ( cbData > 0xFFFFFFFF )
  {
    v5 = -2147024362;
    v12 = 182;
    goto LABEL_24;
  }
  v6 = RegSetValueExW(hKey, L"CurrentEnrollmentId", 0, 1u, (const BYTE *)a1, cbData);
  if ( v6 )
  {
    v8 = 191;
    goto LABEL_5;
  }
  v5 = InitializeCVForDmComponents(a1, hKey);
  if ( (v5 & 0x80000000) != 0 )
  {
    v12 = 194;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
      (const char *)v5,
      phkResulta);
LABEL_25:
    if ( v18 )
      RegCloseKey(v18);
    goto LABEL_27;
  }
  if ( v18 )
    RegCloseKey(v18);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x14000e710  mov     [rsp-18h+arg_0], rbx
0x14000e715  push    rbp
0x14000e716  push    rsi
0x14000e717  push    rdi
0x14000e718  mov     rbp, rsp
0x14000e71b  sub     rsp, 30h
0x14000e71f  mov     rdi, rcx
0x14000e722  xor     esi, esi
0x14000e724  mov     [rbp+hKey], rsi
0x14000e728  call    cs:__imp_RtlIsStateSeparationEnabled
0x14000e72f  nop     dword ptr [rax+rax+00h]
0x14000e734  neg     al
0x14000e736  sbb     rdx, rdx
0x14000e739  and     edx, 8
0x14000e73c  lea     rcx, ?Paths@?1??DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z@4QAY01QEBGA; ushort const * (near * `DMGetKnownRegPath(REFKNOWNREGID)'::`2'::Paths)[2]
0x14000e743  lea     rax, [rbp+hKey]
0x14000e747  mov     [rsp+30h+phkResult], rax; unsigned int
0x14000e74c  mov     r9d, 2001Fh; samDesired
0x14000e752  xor     r8d, r8d; ulOptions
0x14000e755  mov     rdx, [rdx+rcx]; lpSubKey
0x14000e759  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000e760  call    cs:__imp_RegOpenKeyExW
0x14000e767  nop     dword ptr [rax+rax+00h]
0x14000e76c  test    eax, eax
0x14000e76e  jz      short loc_14000E788
0x14000e770  mov     rcx, [rbp+18h]; this
0x14000e774  mov     r9d, eax; char *
0x14000e777  mov     edx, 0A5h; void *
0x14000e77c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000e781  mov     ebx, eax
0x14000e783  jmp     loc_14000E8E0
0x14000e788  mov     [rbp+arg_10], rsi
0x14000e78c  lea     rax, [rbp+arg_10]
0x14000e790  mov     [rsp+30h+phkResult], rax; int
0x14000e795  mov     r9d, 20019h; samDesired
0x14000e79b  xor     r8d, r8d; ulOptions
0x14000e79e  mov     rdx, rdi; lpSubKey
0x14000e7a1  mov     rcx, [rbp+hKey]; hKey
0x14000e7a5  call    cs:__imp_RegOpenKeyExW
0x14000e7ac  nop     dword ptr [rax+rax+00h]
0x14000e7b1  test    eax, eax
0x14000e7b3  jz      short loc_14000E7CD
0x14000e7b5  mov     edx, 0AFh; void *
0x14000e7ba  mov     r9d, eax; char *
0x14000e7bd  mov     rcx, [rbp+18h]; this
0x14000e7c1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14000e7c6  mov     ebx, eax
0x14000e7c8  jmp     loc_14000E8CA
0x14000e7cd  test    rdi, rdi
0x14000e7d0  jz      loc_14000E8AC
0x14000e7d6  mov     edx, 7FFFFFFFh
0x14000e7db  mov     ecx, edx
0x14000e7dd  mov     rax, rdi
0x14000e7e0  cmp     [rax], si
0x14000e7e3  jz      short loc_14000E7EF
0x14000e7e5  add     rax, 2
0x14000e7e9  sub     rcx, 1
0x14000e7ed  jnz     short loc_14000E7E0
0x14000e7ef  mov     rax, rcx
0x14000e7f2  neg     rax
0x14000e7f5  sbb     ebx, ebx
0x14000e7f7  not     ebx
0x14000e7f9  and     ebx, 80070057h
0x14000e7ff  test    rcx, rcx
0x14000e802  jz      loc_14000E8B1
0x14000e808  sub     rdx, rcx
0x14000e80b  add     rdx, rdx
0x14000e80e  neg     rcx
0x14000e811  sbb     rax, rax
0x14000e814  and     rax, rdx
0x14000e817  mov     ecx, 0FFFFFFFFh
0x14000e81c  cmp     rax, rcx
0x14000e81f  ja      short loc_14000E8A0
0x14000e821  mov     [rsp+30h+cbData], eax; cbData
0x14000e825  mov     [rsp+30h+phkResult], rdi; lpData
0x14000e82a  mov     r9d, 1; dwType
0x14000e830  xor     r8d, r8d; Reserved
0x14000e833  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x14000e83a  mov     rcx, [rbp+hKey]; hKey
0x14000e83e  call    cs:__imp_RegSetValueExW
0x14000e845  nop     dword ptr [rax+rax+00h]
0x14000e84a  test    eax, eax
0x14000e84c  jz      short loc_14000E858
0x14000e84e  mov     edx, 0BFh
0x14000e853  jmp     loc_14000E7BA
0x14000e858  mov     rdx, [rbp+hKey]; HKEY
0x14000e85c  mov     rcx, rdi; unsigned __int16 *
0x14000e85f  call    ?InitializeCVForDmComponents@@YAJPEBGPEAUHKEY__@@@Z; InitializeCVForDmComponents(ushort const *,HKEY__ *)
0x14000e864  mov     ebx, eax
0x14000e866  test    eax, eax
0x14000e868  jns     short loc_14000E871
0x14000e86a  mov     edx, 0C2h
0x14000e86f  jmp     short loc_14000E8B6
0x14000e871  mov     rcx, [rbp+arg_10]; hKey
0x14000e875  test    rcx, rcx
0x14000e878  jz      short loc_14000E887
0x14000e87a  call    cs:__imp_RegCloseKey
0x14000e881  nop     dword ptr [rax+rax+00h]
0x14000e886  nop
0x14000e887  mov     rcx, [rbp+hKey]; hKey
0x14000e88b  test    rcx, rcx
0x14000e88e  jz      short loc_14000E89C
0x14000e890  call    cs:__imp_RegCloseKey
0x14000e897  nop     dword ptr [rax+rax+00h]
0x14000e89c  xor     eax, eax
0x14000e89e  jmp     short loc_14000E8F7
0x14000e8a0  mov     ebx, 80070216h
0x14000e8a5  mov     edx, 0B6h
0x14000e8aa  jmp     short loc_14000E8B6
0x14000e8ac  mov     ebx, 80070057h
0x14000e8b1  mov     edx, 0B4h; void *
0x14000e8b6  mov     r9d, ebx; char *
0x14000e8b9  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x14000e8c0  mov     rcx, [rbp+18h]; this
0x14000e8c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e8c9  nop
0x14000e8ca  mov     rcx, [rbp+arg_10]; hKey
0x14000e8ce  test    rcx, rcx
0x14000e8d1  jz      short loc_14000E8E0
0x14000e8d3  call    cs:__imp_RegCloseKey
0x14000e8da  nop     dword ptr [rax+rax+00h]
0x14000e8df  nop
0x14000e8e0  mov     rcx, [rbp+hKey]; hKey
0x14000e8e4  test    rcx, rcx
0x14000e8e7  jz      short loc_14000E8F5
0x14000e8e9  call    cs:__imp_RegCloseKey
0x14000e8f0  nop     dword ptr [rax+rax+00h]
0x14000e8f5  mov     eax, ebx
0x14000e8f7  mov     rbx, [rsp+30h+arg_0]
0x14000e8fc  add     rsp, 30h
0x14000e900  pop     rdi
0x14000e901  pop     rsi
0x14000e902  pop     rbp
0x14000e903  retn
```
