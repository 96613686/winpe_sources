# FwppReplicaInit

- ea: `0x180003448`
- end: `0x1800034d6`
- name: `FwppReplicaInit`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800031c0`

## callees

- `0x180003448`
- `0x1800034e0`
- `0x180007e38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034a2`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003469`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180003469`

## string_xrefs

- `0x1800034b1`: `CreateSemaphoreExW`

## pseudocode

```c
__int64 FwppReplicaInit()
{
  __int64 v0; // rbx
  DWORD LastError; // eax
  __int64 v3; // rcx
  __int64 v4; // rax

  hSemaphore = CreateSemaphoreExW(0, 0, 1, 0, 0, 0x1F0003u);
  if ( hSemaphore )
  {
    v0 = 0;
    qword_18007C858 = (__int64)&qword_18007C850;
    qword_18007C850 = (__int64)&qword_18007C850;
  }
  else
  {
    LastError = GetLastError();
    v4 = WfpReportSysErrorAsWinError(v3, "CreateSemaphoreExW", LastError);
    v0 = v4;
    if ( v4 )
      WfpReportError(v4, "FwppReplicaInit");
  }
  return v0;
}

```

## disassembly

```asm
0x180003448  push    rbx
0x18000344a  sub     rsp, 30h
0x18000344e  xor     r9d, r9d; lpName
0x180003451  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180003459  xor     edx, edx; lInitialCount
0x18000345b  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180003463  xor     ecx, ecx; lpSemaphoreAttributes
0x180003465  lea     r8d, [r9+1]; lMaximumCount
0x180003469  call    cs:__imp_CreateSemaphoreExW
0x180003470  nop     dword ptr [rax+rax+00h]
0x180003475  mov     cs:hSemaphore, rax
0x18000347c  test    rax, rax
0x18000347f  jz      short loc_1800034A2
0x180003481  lea     rax, qword_18007C850
0x180003488  xor     ebx, ebx
0x18000348a  mov     cs:qword_18007C858, rax
0x180003491  mov     cs:qword_18007C850, rax
0x180003498  mov     rax, rbx
0x18000349b  add     rsp, 30h
0x18000349f  pop     rbx
0x1800034a0  retn
0x1800034a2  call    cs:__imp_GetLastError
0x1800034a9  nop     dword ptr [rax+rax+00h]
0x1800034ae  mov     r8d, eax
0x1800034b1  lea     rdx, aCreatesemaphor; "CreateSemaphoreExW"
0x1800034b8  call    WfpReportSysErrorAsWinError
0x1800034bd  mov     rbx, rax
0x1800034c0  test    rax, rax
0x1800034c3  jz      short loc_180003498
0x1800034c5  lea     rdx, aFwppreplicaini; "FwppReplicaInit"
0x1800034cc  mov     rcx, rax
0x1800034cf  call    WfpReportError
0x1800034d4  jmp     short loc_180003498
```
