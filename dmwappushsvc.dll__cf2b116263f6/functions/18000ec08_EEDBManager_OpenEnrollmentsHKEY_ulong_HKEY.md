# EEDBManager::OpenEnrollmentsHKEY(ulong,HKEY__ * *)

- ea: `0x18000ec08`
- end: `0x18000ec26`
- name: `?OpenEnrollmentsHKEY@EEDBManager@@SAJKPEAPEAUHKEY__@@@Z`
- size: `30`
- prototype: `LSTATUS __fastcall(__int64, HKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f0ec`

## callees

- `0x18000e938`
- `0x18000ec2c`

## pseudocode

```c
LSTATUS __fastcall EEDBManager::OpenEnrollmentsHKEY(__int64 a1, HKEY *a2)
{
  const WCHAR *EnrollmentsRootKey; // rax
  __int64 v4; // rdx

  EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
  return EEDBManager::OpenHKEY(EnrollmentsRootKey, v4, a2);
}

```

## disassembly

```asm
0x18000ec08  push    rbx
0x18000ec0a  sub     rsp, 20h
0x18000ec0e  mov     rbx, rdx
0x18000ec11  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x18000ec16  mov     rcx, rax; lpSubKey
0x18000ec19  mov     r8, rbx; HKEY *
0x18000ec1c  add     rsp, 20h
0x18000ec20  pop     rbx
0x18000ec21  jmp     ?OpenHKEY@EEDBManager@@SAJPEBGKPEAPEAUHKEY__@@@Z; EEDBManager::OpenHKEY(ushort const *,ulong,HKEY__ * *)
```
