# GetRenewPeriodInSeconds(ushort const *,ulong *)

- ea: `0x18001d75c`
- end: `0x18001d854`
- name: `?GetRenewPeriodInSeconds@@YAJPEBGPEAK@Z`
- size: `248`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18000be00`

## callees

- `0x18001d75c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d83c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d83c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d7b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d7b4`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001d781`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001d781`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18001d7e1`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18001d7e1`

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
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1, a2);
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         *(wchar_t **)((char *)off_180021160 + (IsStateSeparationEnabled != 0 ? 8 : 0)),
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
0x18001d75c  mov     rax, rsp
0x18001d75f  mov     [rax+8], rbx
0x18001d763  mov     [rax+10h], rsi
0x18001d767  push    rdi
0x18001d768  sub     rsp, 30h
0x18001d76c  mov     rdi, rdx
0x18001d76f  mov     dword ptr [rax+18h], 0
0x18001d776  mov     rsi, rcx
0x18001d779  mov     qword ptr [rax+20h], 0
0x18001d781  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001d787  lea     rcx, off_180021160; "Software\\Microsoft\\Enrollments"
0x18001d78e  mov     r9d, 20019h; samDesired
0x18001d794  neg     al
0x18001d796  lea     rax, [rsp+38h+hKey]
0x18001d79b  sbb     rdx, rdx
0x18001d79e  mov     [rsp+38h+phkResult], rax; phkResult
0x18001d7a3  and     edx, 8
0x18001d7a6  xor     r8d, r8d; ulOptions
0x18001d7a9  mov     rdx, [rdx+rcx]; lpSubKey
0x18001d7ad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d7b4  call    cs:__imp_RegOpenKeyExW
0x18001d7ba  mov     ebx, eax
0x18001d7bc  test    eax, eax
0x18001d7be  jle     short loc_18001D7C9
0x18001d7c0  movzx   ebx, ax
0x18001d7c3  or      ebx, 80070000h
0x18001d7c9  mov     rcx, [rsp+38h+hKey]
0x18001d7ce  test    ebx, ebx
0x18001d7d0  js      short loc_18001D82E
0x18001d7d2  lea     r9, [rsp+38h+arg_10]
0x18001d7d7  mov     rdx, rsi
0x18001d7da  lea     r8, aRenewalperiod; "RenewalPeriod"
0x18001d7e1  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001d7e7  test    eax, eax
0x18001d7e9  jns     short loc_18001D7F2
0x18001d7eb  mov     eax, 375F00h
0x18001d7f0  jmp     short loc_18001D81E
0x18001d7f2  mov     eax, [rsp+38h+arg_10]
0x18001d7f6  mov     edx, 0FFFFFFFFh
0x18001d7fb  lea     rcx, [rax+rax*2]
0x18001d7ff  shl     rcx, 3
0x18001d803  cmp     rcx, rdx
0x18001d806  ja      short loc_18001D824
0x18001d808  mov     eax, ecx
0x18001d80a  imul    rcx, rax, 3Ch ; '<'
0x18001d80e  cmp     rcx, rdx
0x18001d811  ja      short loc_18001D824
0x18001d813  mov     eax, ecx
0x18001d815  imul    rax, 3Ch ; '<'
0x18001d819  cmp     rax, rdx
0x18001d81c  ja      short loc_18001D824
0x18001d81e  xor     ebx, ebx
0x18001d820  mov     [rdi], eax
0x18001d822  jmp     short loc_18001D829
0x18001d824  mov     ebx, 80070216h
0x18001d829  mov     rcx, [rsp+38h+hKey]; hKey
0x18001d82e  mov     [rsp+38h+hKey], 0
0x18001d837  test    rcx, rcx
0x18001d83a  jz      short loc_18001D842
0x18001d83c  call    cs:__imp_RegCloseKey
0x18001d842  mov     rsi, [rsp+38h+arg_8]
0x18001d847  mov     eax, ebx
0x18001d849  mov     rbx, [rsp+38h+arg_0]
0x18001d84e  add     rsp, 30h
0x18001d852  pop     rdi
0x18001d853  retn
```
