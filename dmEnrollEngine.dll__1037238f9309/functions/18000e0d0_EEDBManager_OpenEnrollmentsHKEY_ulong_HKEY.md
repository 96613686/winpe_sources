# EEDBManager::OpenEnrollmentsHKEY(ulong,HKEY__ * *)

- ea: `0x18000e0d0`
- end: `0x18000e13f`
- name: `?OpenEnrollmentsHKEY@EEDBManager@@SAJKPEAPEAUHKEY__@@@Z`
- size: `111`
- prototype: `static int(unsigned int, HKEY *)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012e60`
- `0x18001846c`
- `0x180019ad0`
- `0x18001dc4c`
- `0x180035f30`
- `0x180036220`
- `0x180040b50`
- `0x180040ea4`
- `0x1800426e0`
- `0x18006db08`
- `0x18006e7c0`

## callees

- `0x18000e0d0`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18000e0df`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000e0df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e120`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e120`

## pseudocode

```c
LSTATUS __fastcall EEDBManager::OpenEnrollmentsHKEY(__int64 a1, HKEY *a2)
{
  int v3; // edi
  char IsStateSeparationEnabled; // al
  const WCHAR *v5; // rdx
  LSTATUS result; // eax

  v3 = a1;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1, a2);
  v5 = L"OSData\\Software\\Microsoft\\Enrollments";
  if ( !IsStateSeparationEnabled )
    v5 = L"Software\\Microsoft\\Enrollments";
  result = RegOpenKeyExW((HKEY)((word_1800AFC84 != 0x2000) - 0x7FFFFFFFLL), v5, 0, v3 | 0x100, a2);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000e0d0  mov     [rsp+arg_0], rbx
0x18000e0d5  push    rdi
0x18000e0d6  sub     rsp, 30h
0x18000e0da  mov     rbx, rdx
0x18000e0dd  mov     edi, ecx
0x18000e0df  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000e0e5  lea     rcx, SubKey; "Software\\Microsoft\\Enrollments"
0x18000e0ec  mov     [rsp+38h+phkResult], rbx; phkResult
0x18000e0f1  test    al, al
0x18000e0f3  lea     rdx, aOsdataSoftware_8; "OSData\\Software\\Microsoft\\Enrollment"...
0x18000e0fa  mov     eax, 2000h
0x18000e0ff  cmovz   rdx, rcx; lpSubKey
0x18000e103  xor     ecx, ecx
0x18000e105  cmp     cs:word_1800AFC84, ax
0x18000e10c  setnz   cl
0x18000e10f  bts     edi, 8
0x18000e113  mov     r9d, edi; samDesired
0x18000e116  add     rcx, 0FFFFFFFF80000001h; hKey
0x18000e11d  xor     r8d, r8d; ulOptions
0x18000e120  call    cs:__imp_RegOpenKeyExW
0x18000e126  test    eax, eax
0x18000e128  jg      short loc_18000E135
0x18000e12a  mov     rbx, [rsp+38h+arg_0]
0x18000e12f  add     rsp, 30h
0x18000e133  pop     rdi
0x18000e134  retn
0x18000e135  movzx   eax, ax
0x18000e138  or      eax, 80070000h
0x18000e13d  jmp     short loc_18000E12A
```
