# EEDBManager::GetEnrollmentsRootKey(void)

- ea: `0x18000e938`
- end: `0x18000e95e`
- name: `?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ`
- size: `38`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `7`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001580`
- `0x18000ddd0`
- `0x18000ec08`
- `0x18000f0ec`
- `0x18000f860`
- `0x18000faf0`
- `0x18000ffa0`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18000e93c`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000e93c`

## pseudocode

```c
const unsigned __int16 *EEDBManager::GetEnrollmentsRootKey(void)
{
  char IsStateSeparationEnabled; // al
  const wchar_t *v1; // rcx

  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v1 = L"OSData\\Software\\Microsoft\\Enrollments";
  if ( !IsStateSeparationEnabled )
    return L"Software\\Microsoft\\Enrollments";
  return v1;
}

```

## disassembly

```asm
0x18000e938  sub     rsp, 28h
0x18000e93c  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000e942  test    al, al
0x18000e944  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Enrollments"
0x18000e94b  lea     rcx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Enrollment"...
0x18000e952  cmovz   rcx, rdx
0x18000e956  mov     rax, rcx
0x18000e959  add     rsp, 28h
0x18000e95d  retn
```
