# ModifyRetryCountInValidRange(ushort const *,int,ulong *)

- ea: `0x140010d08`
- end: `0x140010f3b`
- name: `?ModifyRetryCountInValidRange@@YAJPEBGHPEAK@Z`
- size: `563`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000fff0`
- `0x140011ac8`

## callees

- `0x140008504`
- `0x140010d08`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140010e0d`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140010e0d`
- `DMCmnUtils!BigStrcat` at `0x140010d5f`
- `DMCmnUtils!BigStrcat` at `0x140010d5f`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x140010ecc`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x140010ecc`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140010d30`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140010d30`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140010ddd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140010ddd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010daa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010e57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010e8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010f09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010daa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010e57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010e8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010f09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010ea3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010f19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010ea3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010f19`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ModifyRetryCountInValidRange(const unsigned __int16 *a1, int a2, unsigned int *a3)
{
  char IsStateSeparationEnabled; // al
  const wchar_t *v6; // rdx
  WCHAR *v7; // rbx
  LSTATUS v9; // eax
  unsigned int v10; // edi
  unsigned int DWORD; // eax
  unsigned int v12; // r9d
  int phkResult; // [rsp+20h] [rbp-40h]
  HKEY hKey[5]; // [rsp+30h] [rbp-30h] BYREF
  char v15; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  unsigned int *v17; // [rsp+90h] [rbp+30h] BYREF
  unsigned int v18; // [rsp+98h] [rbp+38h] BYREF

  v17 = a3;
  v18 = 0;
  hKey[0] = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  v6 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
  if ( !IsStateSeparationEnabled )
    v6 = L"Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
  v7 = BigStrcat(3u, v6, L"\\", a1);
  hKey[1] = (HKEY)v7;
  hKey[2] = (HKEY)&v17;
  hKey[3] = (HKEY)&v18;
  hKey[4] = (HKEY)hKey;
  v15 = 1;
  if ( !v7 )
  {
    if ( v17 )
      *v17 = v18;
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    return 2147942414LL;
  }
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x2001Fu, hKey);
  v10 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_16;
  }
  DWORD = OmaDmRegistryGetDWORD(hKey[0], 0, L"RetryCount", &v18);
  v10 = 0;
  if ( DWORD != -2147024894 )
    v10 = DWORD;
  if ( (v10 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x253,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
      (const char *)v10,
      phkResult);
LABEL_16:
    if ( v17 )
      *v17 = v18;
LABEL_18:
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
LABEL_27:
    LocalFree(v7);
    return v10;
  }
  if ( a2 )
  {
    v12 = v18 + 1;
    v18 = v12;
    if ( v12 > 6 )
    {
      if ( v17 )
        *v17 = v12;
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
      v10 = -2102657017;
      goto LABEL_27;
    }
    goto LABEL_30;
  }
  if ( v18 )
  {
    v12 = --v18;
LABEL_30:
    v10 = OmaDmRegistrySetDWORD(hKey[0], 0, L"RetryCount", v12);
    if ( v17 )
      *v17 = v18;
    goto LABEL_18;
  }
  if ( v17 )
    *v17 = 0;
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  LocalFree(v7);
  return 2147549183LL;
}

```

## disassembly

```asm
0x140010d08  mov     [rsp-18h+arg_0], rbx
0x140010d0d  mov     [rsp-18h+arg_10], r8
0x140010d12  push    rbp
0x140010d13  push    rsi
0x140010d14  push    rdi
0x140010d15  mov     rbp, rsp
0x140010d18  sub     rsp, 60h
0x140010d1c  mov     esi, edx
0x140010d1e  mov     rbx, rcx
0x140010d21  mov     [rbp+arg_18], 0
0x140010d28  mov     [rbp+hKey], 0
0x140010d30  call    cs:__imp_RtlIsStateSeparationEnabled
0x140010d37  nop     dword ptr [rax+rax+00h]
0x140010d3c  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\OMAD"...
0x140010d43  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x140010d4a  test    al, al
0x140010d4c  cmovz   rdx, rcx
0x140010d50  mov     r9, rbx
0x140010d53  lea     r8, asc_140019FC8; "\\"
0x140010d5a  mov     ecx, 3
0x140010d5f  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x140010d66  nop     dword ptr [rax+rax+00h]
0x140010d6b  mov     rbx, rax
0x140010d6e  mov     [rbp+var_28], rax
0x140010d72  lea     rax, [rbp+arg_10]
0x140010d76  mov     [rbp+var_20], rax
0x140010d7a  lea     rax, [rbp+arg_18]
0x140010d7e  mov     [rbp+var_18], rax
0x140010d82  lea     rax, [rbp+hKey]
0x140010d86  mov     [rbp+var_10], rax
0x140010d8a  mov     [rbp+var_8], 1
0x140010d8e  test    rbx, rbx
0x140010d91  jnz     short loc_140010DC1
0x140010d93  mov     rcx, [rbp+arg_10]
0x140010d97  test    rcx, rcx
0x140010d9a  jz      short loc_140010DA1
0x140010d9c  mov     eax, [rbp+arg_18]
0x140010d9f  mov     [rcx], eax
0x140010da1  mov     rcx, [rbp+hKey]; hKey
0x140010da5  test    rcx, rcx
0x140010da8  jz      short loc_140010DB7
0x140010daa  call    cs:__imp_RegCloseKey
0x140010db1  nop     dword ptr [rax+rax+00h]
0x140010db6  nop
0x140010db7  mov     eax, 8007000Eh
0x140010dbc  jmp     loc_140010F2A
0x140010dc1  lea     rax, [rbp+hKey]
0x140010dc5  mov     qword ptr [rsp+60h+phkResult], rax; int
0x140010dca  mov     r9d, 2001Fh; samDesired
0x140010dd0  xor     r8d, r8d; ulOptions
0x140010dd3  mov     rdx, rbx; lpSubKey
0x140010dd6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140010ddd  call    cs:__imp_RegOpenKeyExW
0x140010de4  nop     dword ptr [rax+rax+00h]
0x140010de9  mov     edi, eax
0x140010deb  test    eax, eax
0x140010ded  jz      short loc_140010DFC
0x140010def  jle     short loc_140010E40
0x140010df1  movzx   edi, ax
0x140010df4  or      edi, 80070000h
0x140010dfa  jmp     short loc_140010E40
0x140010dfc  lea     r9, [rbp+arg_18]
0x140010e00  lea     r8, ValueName; "RetryCount"
0x140010e07  xor     edx, edx
0x140010e09  mov     rcx, [rbp+hKey]
0x140010e0d  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140010e14  nop     dword ptr [rax+rax+00h]
0x140010e19  xor     edi, edi
0x140010e1b  cmp     eax, 80070002h
0x140010e20  cmovnz  edi, eax
0x140010e23  test    edi, edi
0x140010e25  jns     short loc_140010E65
0x140010e27  mov     rcx, [rbp+18h]; this
0x140010e2b  mov     r9d, edi; char *
0x140010e2e  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x140010e35  mov     edx, 253h; void *
0x140010e3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010e3f  nop
0x140010e40  mov     rcx, [rbp+arg_10]
0x140010e44  test    rcx, rcx
0x140010e47  jz      short loc_140010E4E
0x140010e49  mov     eax, [rbp+arg_18]
0x140010e4c  mov     [rcx], eax
0x140010e4e  mov     rcx, [rbp+hKey]; hKey
0x140010e52  test    rcx, rcx
0x140010e55  jz      short loc_140010EA0
0x140010e57  call    cs:__imp_RegCloseKey
0x140010e5e  nop     dword ptr [rax+rax+00h]
0x140010e63  jmp     short loc_140010EA0
0x140010e65  mov     r9d, [rbp+arg_18]
0x140010e69  test    esi, esi
0x140010e6b  jz      short loc_140010EB3
0x140010e6d  inc     r9d
0x140010e70  mov     [rbp+arg_18], r9d
0x140010e74  cmp     r9d, 6
0x140010e78  jbe     short loc_140010EBF
0x140010e7a  mov     rax, [rbp+arg_10]
0x140010e7e  test    rax, rax
0x140010e81  jz      short loc_140010E86
0x140010e83  mov     [rax], r9d
0x140010e86  mov     rcx, [rbp+hKey]; hKey
0x140010e8a  test    rcx, rcx
0x140010e8d  jz      short loc_140010E9B
0x140010e8f  call    cs:__imp_RegCloseKey
0x140010e96  nop     dword ptr [rax+rax+00h]
0x140010e9b  mov     edi, 82AC0007h
0x140010ea0  mov     rcx, rbx; hMem
0x140010ea3  call    cs:__imp_LocalFree
0x140010eaa  nop     dword ptr [rax+rax+00h]
0x140010eaf  mov     eax, edi
0x140010eb1  jmp     short loc_140010F2A
0x140010eb3  test    r9d, r9d
0x140010eb6  jz      short loc_140010EF1
0x140010eb8  dec     r9d
0x140010ebb  mov     [rbp+arg_18], r9d
0x140010ebf  lea     r8, ValueName; "RetryCount"
0x140010ec6  xor     edx, edx
0x140010ec8  mov     rcx, [rbp+hKey]
0x140010ecc  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x140010ed3  nop     dword ptr [rax+rax+00h]
0x140010ed8  mov     edi, eax
0x140010eda  mov     rdx, [rbp+arg_10]
0x140010ede  test    rdx, rdx
0x140010ee1  jz      loc_140010E4E
0x140010ee7  mov     ecx, [rbp+arg_18]
0x140010eea  mov     [rdx], ecx
0x140010eec  jmp     loc_140010E4E
0x140010ef1  mov     rax, [rbp+arg_10]
0x140010ef5  test    rax, rax
0x140010ef8  jz      short loc_140010F00
0x140010efa  mov     dword ptr [rax], 0
0x140010f00  mov     rcx, [rbp+hKey]; hKey
0x140010f04  test    rcx, rcx
0x140010f07  jz      short loc_140010F16
0x140010f09  call    cs:__imp_RegCloseKey
0x140010f10  nop     dword ptr [rax+rax+00h]
0x140010f15  nop
0x140010f16  mov     rcx, rbx; hMem
0x140010f19  call    cs:__imp_LocalFree
0x140010f20  nop     dword ptr [rax+rax+00h]
0x140010f25  mov     eax, 8000FFFFh
0x140010f2a  mov     rbx, [rsp+60h+arg_0]
0x140010f32  add     rsp, 60h
0x140010f36  pop     rdi
0x140010f37  pop     rsi
0x140010f38  pop     rbp
0x140010f39  retn
```
