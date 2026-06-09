# IsROBOMode(ushort const *,int *)

- ea: `0x18001da98`
- end: `0x18001db6e`
- name: `?IsROBOMode@@YAJPEBGPEAH@Z`
- size: `214`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18000be00`

## callees

- `0x18001da98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001db56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001db56`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001daf0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001daf0`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001dabd`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001dabd`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18001db1d`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18001db1d`

## pseudocode

```c
__int64 __fastcall IsROBOMode(const unsigned __int16 *a1, int *a2)
{
  char IsStateSeparationEnabled; // al
  LSTATUS v5; // eax
  signed int v6; // ebx
  HKEY v7; // rcx
  signed int DWORD; // eax
  int v9; // eax
  int v11; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v11 = 0;
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
    DWORD = OmaDmRegistryGetDWORD(hKey, a1, L"RenewROBOSupport", (unsigned int *)&v11);
    v6 = DWORD;
    if ( DWORD == -2147024894 || DWORD == -2147023267 )
    {
      v9 = 0;
      v11 = 0;
      v6 = 0;
    }
    else
    {
      v9 = v11;
    }
    v7 = hKey;
    *a2 = v9;
  }
  hKey = 0;
  if ( v7 )
    RegCloseKey(v7);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001da98  mov     rax, rsp
0x18001da9b  mov     [rax+8], rbx
0x18001da9f  mov     [rax+10h], rsi
0x18001daa3  push    rdi
0x18001daa4  sub     rsp, 30h
0x18001daa8  mov     rdi, rdx
0x18001daab  mov     dword ptr [rax+18h], 0
0x18001dab2  mov     rsi, rcx
0x18001dab5  mov     qword ptr [rax+20h], 0
0x18001dabd  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001dac3  lea     rcx, off_180021160; "Software\\Microsoft\\Enrollments"
0x18001daca  mov     r9d, 20019h; samDesired
0x18001dad0  neg     al
0x18001dad2  lea     rax, [rsp+38h+hKey]
0x18001dad7  sbb     rdx, rdx
0x18001dada  mov     [rsp+38h+phkResult], rax; phkResult
0x18001dadf  and     edx, 8
0x18001dae2  xor     r8d, r8d; ulOptions
0x18001dae5  mov     rdx, [rdx+rcx]; lpSubKey
0x18001dae9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001daf0  call    cs:__imp_RegOpenKeyExW
0x18001daf6  mov     ebx, eax
0x18001daf8  test    eax, eax
0x18001dafa  jle     short loc_18001DB05
0x18001dafc  movzx   ebx, ax
0x18001daff  or      ebx, 80070000h
0x18001db05  mov     rcx, [rsp+38h+hKey]
0x18001db0a  test    ebx, ebx
0x18001db0c  js      short loc_18001DB48
0x18001db0e  lea     r9, [rsp+38h+arg_10]
0x18001db13  mov     rdx, rsi
0x18001db16  lea     r8, aRenewrobosuppo; "RenewROBOSupport"
0x18001db1d  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001db23  mov     ebx, eax
0x18001db25  cmp     eax, 80070002h
0x18001db2a  jz      short loc_18001DB39
0x18001db2c  cmp     eax, 8007065Dh
0x18001db31  jz      short loc_18001DB39
0x18001db33  mov     eax, [rsp+38h+arg_10]
0x18001db37  jmp     short loc_18001DB41
0x18001db39  xor     eax, eax
0x18001db3b  mov     [rsp+38h+arg_10], eax
0x18001db3f  xor     ebx, ebx
0x18001db41  mov     rcx, [rsp+38h+hKey]; hKey
0x18001db46  mov     [rdi], eax
0x18001db48  mov     [rsp+38h+hKey], 0
0x18001db51  test    rcx, rcx
0x18001db54  jz      short loc_18001DB5C
0x18001db56  call    cs:__imp_RegCloseKey
0x18001db5c  mov     rsi, [rsp+38h+arg_8]
0x18001db61  mov     eax, ebx
0x18001db63  mov     rbx, [rsp+38h+arg_0]
0x18001db68  add     rsp, 30h
0x18001db6c  pop     rdi
0x18001db6d  retn
```
