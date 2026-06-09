# IsROBOMode(ushort const *,int *)

- ea: `0x1800244a8`
- end: `0x18002457e`
- name: `?IsROBOMode@@YAJPEBGPEAH@Z`
- size: `214`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ea90`

## callees

- `0x1800244a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024566`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024566`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024500`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024500`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800244cd`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800244cd`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18002452d`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18002452d`

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
0x1800244a8  mov     rax, rsp
0x1800244ab  mov     [rax+8], rbx
0x1800244af  mov     [rax+10h], rsi
0x1800244b3  push    rdi
0x1800244b4  sub     rsp, 30h
0x1800244b8  mov     rdi, rdx
0x1800244bb  mov     dword ptr [rax+18h], 0
0x1800244c2  mov     rsi, rcx
0x1800244c5  mov     qword ptr [rax+20h], 0
0x1800244cd  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800244d3  lea     rcx, off_18003CA70; "Software\\Microsoft\\Enrollments"
0x1800244da  mov     r9d, 20019h; samDesired
0x1800244e0  neg     al
0x1800244e2  lea     rax, [rsp+38h+hKey]
0x1800244e7  sbb     rdx, rdx
0x1800244ea  mov     [rsp+38h+phkResult], rax; phkResult
0x1800244ef  and     edx, 8
0x1800244f2  xor     r8d, r8d; ulOptions
0x1800244f5  mov     rdx, [rdx+rcx]; lpSubKey
0x1800244f9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180024500  call    cs:__imp_RegOpenKeyExW
0x180024506  mov     ebx, eax
0x180024508  test    eax, eax
0x18002450a  jle     short loc_180024515
0x18002450c  movzx   ebx, ax
0x18002450f  or      ebx, 80070000h
0x180024515  mov     rcx, [rsp+38h+hKey]
0x18002451a  test    ebx, ebx
0x18002451c  js      short loc_180024558
0x18002451e  lea     r9, [rsp+38h+arg_10]
0x180024523  mov     rdx, rsi
0x180024526  lea     r8, aRenewrobosuppo; "RenewROBOSupport"
0x18002452d  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180024533  mov     ebx, eax
0x180024535  cmp     eax, 80070002h
0x18002453a  jz      short loc_180024549
0x18002453c  cmp     eax, 8007065Dh
0x180024541  jz      short loc_180024549
0x180024543  mov     eax, [rsp+38h+arg_10]
0x180024547  jmp     short loc_180024551
0x180024549  xor     eax, eax
0x18002454b  mov     [rsp+38h+arg_10], eax
0x18002454f  xor     ebx, ebx
0x180024551  mov     rcx, [rsp+38h+hKey]; hKey
0x180024556  mov     [rdi], eax
0x180024558  mov     [rsp+38h+hKey], 0
0x180024561  test    rcx, rcx
0x180024564  jz      short loc_18002456C
0x180024566  call    cs:__imp_RegCloseKey
0x18002456c  mov     rsi, [rsp+38h+arg_8]
0x180024571  mov     eax, ebx
0x180024573  mov     rbx, [rsp+38h+arg_0]
0x180024578  add     rsp, 30h
0x18002457c  pop     rdi
0x18002457d  retn
```
