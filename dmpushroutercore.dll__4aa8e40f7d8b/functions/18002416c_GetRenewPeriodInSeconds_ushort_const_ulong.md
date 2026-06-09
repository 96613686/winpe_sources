# GetRenewPeriodInSeconds(ushort const *,ulong *)

- ea: `0x18002416c`
- end: `0x180024264`
- name: `?GetRenewPeriodInSeconds@@YAJPEBGPEAK@Z`
- size: `248`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ea90`

## callees

- `0x18002416c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002424c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002424c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800241c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800241c4`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180024191`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180024191`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800241f1`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800241f1`

## pseudocode

```c
__int64 __fastcall GetRenewPeriodInSeconds(const unsigned __int16 *a1, unsigned int *a2)
{
  char IsStateSeparationEnabled; // al
  LSTATUS v5; // eax
  signed int v6; // ebx
  HKEY v7; // rcx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  unsigned int v12; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v12 = 0;
  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         *(wchar_t **)((char *)off_18003CA70 + (IsStateSeparationEnabled != 0 ? 8 : 0)),
         0,
         0x20019u,
         &hKey);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  v7 = hKey;
  if ( v6 >= 0 )
  {
    if ( (int)OmaDmRegistryGetDWORD(hKey, a1, L"RenewalPeriod", &v12) >= 0 )
    {
      v9 = 24LL * v12;
      if ( v9 > 0xFFFFFFFF
        || (v10 = 60LL * (unsigned int)v9, v10 > 0xFFFFFFFF)
        || (v8 = 60LL * (unsigned int)v10, v8 > 0xFFFFFFFF) )
      {
        v6 = -2147024362;
        goto LABEL_11;
      }
    }
    else
    {
      LODWORD(v8) = 3628800;
    }
    v6 = 0;
    *a2 = v8;
LABEL_11:
    v7 = hKey;
  }
  hKey = 0;
  if ( v7 )
    RegCloseKey(v7);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002416c  mov     rax, rsp
0x18002416f  mov     [rax+8], rbx
0x180024173  mov     [rax+10h], rsi
0x180024177  push    rdi
0x180024178  sub     rsp, 30h
0x18002417c  mov     rdi, rdx
0x18002417f  mov     dword ptr [rax+18h], 0
0x180024186  mov     rsi, rcx
0x180024189  mov     qword ptr [rax+20h], 0
0x180024191  call    cs:__imp_RtlIsStateSeparationEnabled
0x180024197  lea     rcx, off_18003CA70; "Software\\Microsoft\\Enrollments"
0x18002419e  mov     r9d, 20019h; samDesired
0x1800241a4  neg     al
0x1800241a6  lea     rax, [rsp+38h+hKey]
0x1800241ab  sbb     rdx, rdx
0x1800241ae  mov     [rsp+38h+phkResult], rax; phkResult
0x1800241b3  and     edx, 8
0x1800241b6  xor     r8d, r8d; ulOptions
0x1800241b9  mov     rdx, [rdx+rcx]; lpSubKey
0x1800241bd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800241c4  call    cs:__imp_RegOpenKeyExW
0x1800241ca  mov     ebx, eax
0x1800241cc  test    eax, eax
0x1800241ce  jle     short loc_1800241D9
0x1800241d0  movzx   ebx, ax
0x1800241d3  or      ebx, 80070000h
0x1800241d9  mov     rcx, [rsp+38h+hKey]
0x1800241de  test    ebx, ebx
0x1800241e0  js      short loc_18002423E
0x1800241e2  lea     r9, [rsp+38h+arg_10]
0x1800241e7  mov     rdx, rsi
0x1800241ea  lea     r8, aRenewalperiod; "RenewalPeriod"
0x1800241f1  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800241f7  test    eax, eax
0x1800241f9  jns     short loc_180024202
0x1800241fb  mov     eax, 375F00h
0x180024200  jmp     short loc_18002422E
0x180024202  mov     eax, [rsp+38h+arg_10]
0x180024206  mov     edx, 0FFFFFFFFh
0x18002420b  lea     rcx, [rax+rax*2]
0x18002420f  shl     rcx, 3
0x180024213  cmp     rcx, rdx
0x180024216  ja      short loc_180024234
0x180024218  mov     eax, ecx
0x18002421a  imul    rcx, rax, 3Ch ; '<'
0x18002421e  cmp     rcx, rdx
0x180024221  ja      short loc_180024234
0x180024223  mov     eax, ecx
0x180024225  imul    rax, 3Ch ; '<'
0x180024229  cmp     rax, rdx
0x18002422c  ja      short loc_180024234
0x18002422e  xor     ebx, ebx
0x180024230  mov     [rdi], eax
0x180024232  jmp     short loc_180024239
0x180024234  mov     ebx, 80070216h
0x180024239  mov     rcx, [rsp+38h+hKey]; hKey
0x18002423e  mov     [rsp+38h+hKey], 0
0x180024247  test    rcx, rcx
0x18002424a  jz      short loc_180024252
0x18002424c  call    cs:__imp_RegCloseKey
0x180024252  mov     rsi, [rsp+38h+arg_8]
0x180024257  mov     eax, ebx
0x180024259  mov     rbx, [rsp+38h+arg_0]
0x18002425e  add     rsp, 30h
0x180024262  pop     rdi
0x180024263  retn
```
