# InitializeCVMapForDmSession(ushort const *)

- ea: `0x140012e5c`
- end: `0x14001305f`
- name: `?InitializeCVMapForDmSession@@YAJPEBG@Z`
- size: `515`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000d860`

## callees

- `0x14000b0f4`
- `0x140012b54`
- `0x140012e5c`
- `0x140013068`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012eac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012ef8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012eac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012ef8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140012f98`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140012f98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012fd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012fea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001302d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140013043`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012fd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012fea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001302d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140013043`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140012e74`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140012e74`

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
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
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
0x140012e5c  mov     [rsp-18h+arg_0], rbx
0x140012e61  push    rbp
0x140012e62  push    rsi
0x140012e63  push    rdi
0x140012e64  mov     rbp, rsp
0x140012e67  sub     rsp, 30h
0x140012e6b  mov     rdi, rcx
0x140012e6e  xor     esi, esi
0x140012e70  mov     [rbp+hKey], rsi
0x140012e74  call    cs:__imp_RtlIsStateSeparationEnabled
0x140012e7b  nop     dword ptr [rax+rax+00h]
0x140012e80  neg     al
0x140012e82  sbb     rdx, rdx
0x140012e85  and     edx, 8
0x140012e88  lea     rcx, ?Paths@?1??DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z@4QAY01QEBGA; ushort const * (near * `DMGetKnownRegPath(REFKNOWNREGID)'::`2'::Paths)[2]
0x140012e8f  lea     rax, [rbp+hKey]
0x140012e93  mov     [rsp+30h+phkResult], rax; unsigned int
0x140012e98  mov     r9d, 2001Fh; samDesired
0x140012e9e  xor     r8d, r8d; ulOptions
0x140012ea1  mov     rdx, [rdx+rcx]; lpSubKey
0x140012ea5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140012eac  call    cs:__imp_RegOpenKeyExW
0x140012eb3  nop     dword ptr [rax+rax+00h]
0x140012eb8  test    eax, eax
0x140012eba  jz      short loc_140012EDB
0x140012ebc  mov     rcx, [rbp+18h]; this
0x140012ec0  mov     r9d, eax; char *
0x140012ec3  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x140012eca  mov     edx, 0A5h; void *
0x140012ecf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140012ed4  mov     ebx, eax
0x140012ed6  jmp     loc_14001303A
0x140012edb  mov     [rbp+arg_10], rsi
0x140012edf  lea     rax, [rbp+arg_10]
0x140012ee3  mov     [rsp+30h+phkResult], rax; int
0x140012ee8  mov     r9d, 20019h; samDesired
0x140012eee  xor     r8d, r8d; ulOptions
0x140012ef1  mov     rdx, rdi; lpSubKey
0x140012ef4  mov     rcx, [rbp+hKey]; hKey
0x140012ef8  call    cs:__imp_RegOpenKeyExW
0x140012eff  nop     dword ptr [rax+rax+00h]
0x140012f04  test    eax, eax
0x140012f06  jz      short loc_140012F27
0x140012f08  mov     edx, 0AFh; void *
0x140012f0d  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x140012f14  mov     r9d, eax; char *
0x140012f17  mov     rcx, [rbp+18h]; this
0x140012f1b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140012f20  mov     ebx, eax
0x140012f22  jmp     loc_140013024
0x140012f27  test    rdi, rdi
0x140012f2a  jz      loc_140013006
0x140012f30  mov     edx, 7FFFFFFFh
0x140012f35  mov     ecx, edx
0x140012f37  mov     rax, rdi
0x140012f3a  cmp     [rax], si
0x140012f3d  jz      short loc_140012F49
0x140012f3f  add     rax, 2
0x140012f43  sub     rcx, 1
0x140012f47  jnz     short loc_140012F3A
0x140012f49  mov     rax, rcx
0x140012f4c  neg     rax
0x140012f4f  sbb     ebx, ebx
0x140012f51  not     ebx
0x140012f53  and     ebx, 80070057h
0x140012f59  test    rcx, rcx
0x140012f5c  jz      loc_14001300B
0x140012f62  sub     rdx, rcx
0x140012f65  add     rdx, rdx
0x140012f68  neg     rcx
0x140012f6b  sbb     rax, rax
0x140012f6e  and     rax, rdx
0x140012f71  mov     ecx, 0FFFFFFFFh
0x140012f76  cmp     rax, rcx
0x140012f79  ja      short loc_140012FFA
0x140012f7b  mov     [rsp+30h+cbData], eax; cbData
0x140012f7f  mov     [rsp+30h+phkResult], rdi; lpData
0x140012f84  mov     r9d, 1; dwType
0x140012f8a  xor     r8d, r8d; Reserved
0x140012f8d  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x140012f94  mov     rcx, [rbp+hKey]; hKey
0x140012f98  call    cs:__imp_RegSetValueExW
0x140012f9f  nop     dword ptr [rax+rax+00h]
0x140012fa4  test    eax, eax
0x140012fa6  jz      short loc_140012FB2
0x140012fa8  mov     edx, 0BFh
0x140012fad  jmp     loc_140012F0D
0x140012fb2  mov     rdx, [rbp+hKey]; HKEY
0x140012fb6  mov     rcx, rdi; unsigned __int16 *
0x140012fb9  call    ?InitializeCVForDmComponents@@YAJPEBGPEAUHKEY__@@@Z; InitializeCVForDmComponents(ushort const *,HKEY__ *)
0x140012fbe  mov     ebx, eax
0x140012fc0  test    eax, eax
0x140012fc2  jns     short loc_140012FCB
0x140012fc4  mov     edx, 0C2h
0x140012fc9  jmp     short loc_140013010
0x140012fcb  mov     rcx, [rbp+arg_10]; hKey
0x140012fcf  test    rcx, rcx
0x140012fd2  jz      short loc_140012FE1
0x140012fd4  call    cs:__imp_RegCloseKey
0x140012fdb  nop     dword ptr [rax+rax+00h]
0x140012fe0  nop
0x140012fe1  mov     rcx, [rbp+hKey]; hKey
0x140012fe5  test    rcx, rcx
0x140012fe8  jz      short loc_140012FF6
0x140012fea  call    cs:__imp_RegCloseKey
0x140012ff1  nop     dword ptr [rax+rax+00h]
0x140012ff6  xor     eax, eax
0x140012ff8  jmp     short loc_140013051
0x140012ffa  mov     ebx, 80070216h
0x140012fff  mov     edx, 0B6h
0x140013004  jmp     short loc_140013010
0x140013006  mov     ebx, 80070057h
0x14001300b  mov     edx, 0B4h; void *
0x140013010  mov     r9d, ebx; char *
0x140013013  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x14001301a  mov     rcx, [rbp+18h]; this
0x14001301e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013023  nop
0x140013024  mov     rcx, [rbp+arg_10]; hKey
0x140013028  test    rcx, rcx
0x14001302b  jz      short loc_14001303A
0x14001302d  call    cs:__imp_RegCloseKey
0x140013034  nop     dword ptr [rax+rax+00h]
0x140013039  nop
0x14001303a  mov     rcx, [rbp+hKey]; hKey
0x14001303e  test    rcx, rcx
0x140013041  jz      short loc_14001304F
0x140013043  call    cs:__imp_RegCloseKey
0x14001304a  nop     dword ptr [rax+rax+00h]
0x14001304f  mov     eax, ebx
0x140013051  mov     rbx, [rsp+30h+arg_0]
0x140013056  add     rsp, 30h
0x14001305a  pop     rdi
0x14001305b  pop     rsi
0x14001305c  pop     rbp
0x14001305d  retn
```
