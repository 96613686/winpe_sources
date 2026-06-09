# CImapiReadOnlyStreamImpl<CMsftStreamZero,IStream>::UpdateAccessTime(void)

- ea: `0x180013a8c`
- end: `0x180013ab8`
- name: `?UpdateAccessTime@?$CImapiReadOnlyStreamImpl@VCMsftStreamZero@@UIStream@@@@QEAAXXZ`
- size: `44`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180011f40`
- `0x180012100`
- `0x180012c40`
- `0x180014ab0`
- `0x1800152f0`
- `0x180015b90`
- `0x180015df0`
- `0x180016160`
- `0x1800165c0`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180013aa3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180013aa3`

## pseudocode

```c
struct _FILETIME __fastcall CImapiReadOnlyStreamImpl<CMsftStreamZero,IStream>::UpdateAccessTime(struct _FILETIME *a1)
{
  struct _FILETIME result; // rax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp+8h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  result = SystemTimeAsFileTime;
  a1[3] = SystemTimeAsFileTime;
  return result;
}

```

## disassembly

```asm
0x180013a8c  push    rbx
0x180013a8e  sub     rsp, 20h
0x180013a92  mov     rbx, rcx
0x180013a95  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180013a9e  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180013aa3  call    cs:__imp_GetSystemTimeAsFileTime
0x180013aa9  mov     rax, qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x180013aae  mov     [rbx+18h], rax
0x180013ab2  add     rsp, 20h
0x180013ab6  pop     rbx
0x180013ab7  retn
```
