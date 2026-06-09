# DpiGdoDestroyGdiObjects

- ea: `0x1402c0380`
- end: `0x1402c0607`
- name: `DpiGdoDestroyGdiObjects`
- size: `647`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callers

- `0x1402a2d70`
- `0x1402a34ec`

## callees

- `0x1400406a8`
- `0x1400406ec`
- `0x14026592c`
- `0x1402b0d90`
- `0x1402c0380`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c0495`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c0495`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c045d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c045d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c052c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c056b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c057a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c052c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c056b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c057a`
- `ntoskrnl!IoDeleteDevice` at `0x1402c05a6`
- `ntoskrnl!IoDeleteDevice` at `0x1402c05a6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402c03ac`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402c04b5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402c03ac`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402c04b5`
- `ntoskrnl!KeReleaseMutex` at `0x1402c044a`
- `ntoskrnl!KeReleaseMutex` at `0x1402c05eb`
- `ntoskrnl!KeReleaseMutex` at `0x1402c044a`
- `ntoskrnl!KeReleaseMutex` at `0x1402c05eb`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1402c03ef`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1402c03ef`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402c0412`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402c0412`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1402c047b`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1402c047b`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1402c055a`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1402c055a`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1402c051b`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1402c051b`
- `watchdog!WdLogSingleEntry3` at `0x1402c05cc`
- `watchdog!WdLogSingleEntry3` at `0x1402c05cc`

## pseudocode

```c
__int64 __fastcall DpiGdoDestroyGdiObjects(__int64 a1)
{
  __int64 v1; // rsi
  _QWORD *v2; // r14
  _QWORD *v3; // rbx
  NTSTATUS v4; // eax
  unsigned int v5; // edi
  __int64 v6; // rdx
  _QWORD *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  PCWSTR ValueName[2]; // [rsp+30h] [rbp-58h] BYREF
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+40h] [rbp-48h] BYREF

  v1 = *(_QWORD *)(a1 + 64);
  KeWaitForSingleObject((PVOID)(v1 + 3720), Executive, 0, 0, 0);
  v2 = (_QWORD *)(v1 + 3704);
  while ( 1 )
  {
    v3 = (_QWORD *)*v2;
    if ( (_QWORD *)*v2 == v2 )
      break;
    SymbolicLinkName = 0;
    v4 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)v3 + 2, v3, File, 1u, 0x20u);
    v5 = v4;
    if ( v4 < 0 )
    {
      WdLogSingleEntry3(0, 275, 21, v4);
      WdLogGlobalForLineNumber = 545;
      goto LABEL_16;
    }
    IoSetDeviceInterfaceState((PUNICODE_STRING)v3 + 10, 0);
    v6 = *v3;
    if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v7 = (_QWORD *)v3[1], (_QWORD *)*v7 != v3) )
      __fastfail(3u);
    *v7 = v6;
    *(_QWORD *)(v6 + 8) = v7;
    --*(_DWORD *)(v1 + 3776);
    KeReleaseMutex((PRKMUTEX)(v1 + 3720), 0);
    ExReleaseResourceLite(*(PERESOURCE *)(v1 + 168));
    ReleaseMiniportListMutex();
    IoReleaseRemoveLockAndWaitEx((PIO_REMOVE_LOCK)v3 + 2, v3, 0x20u);
    AcquireMiniportListMutex();
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v1 + 168), 1u);
    KeWaitForSingleObject((PVOID)(v1 + 3720), Executive, 0, 0, 0);
    if ( !*(_BYTE *)(v1 + 2847) )
    {
      v8 = v3[3];
      *(_OWORD *)ValueName = 0;
      v9 = *(_QWORD *)(v8 + 64);
      if ( !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v9 + 32) + 64LL) + 2847LL)
        && (int)DpiAppendNumberToString(L"\\Device\\Video", *(_DWORD *)(v9 + 152), (PUNICODE_STRING)ValueName) >= 0 )
      {
        RtlDeleteRegistryValue(4u, L"VIDEO", ValueName[1]);
        RtlFreeUnicodeString((PUNICODE_STRING)ValueName);
      }
      if ( (int)DpiAppendNumberToString(L"\\DosDevices\\DISPLAY", *((_DWORD *)v3 + 38) + 1, &SymbolicLinkName) >= 0 )
      {
        IoDeleteSymbolicLink(&SymbolicLinkName);
        RtlFreeUnicodeString(&SymbolicLinkName);
      }
    }
    RtlFreeUnicodeString((PUNICODE_STRING)v3 + 10);
    LOBYTE(v10) = *(_BYTE *)(v1 + 2847);
    DxgkReleaseGdiViewId(v10, *(_QWORD *)(v1 + 5888), *((unsigned int *)v3 + 38), 0);
    IoDeleteDevice((PDEVICE_OBJECT)v3[3]);
  }
  v5 = 0;
LABEL_16:
  KeReleaseMutex((PRKMUTEX)(v1 + 3720), 0);
  return v5;
}

```

## disassembly

```asm
0x1402c0380  push    rbx
0x1402c0382  push    rbp
0x1402c0383  push    rsi
0x1402c0384  push    rdi
0x1402c0385  push    r14
0x1402c0387  push    r15
0x1402c0389  sub     rsp, 58h
0x1402c038d  mov     rsi, [rcx+40h]
0x1402c0391  xor     r9d, r9d; Alertable
0x1402c0394  xor     r8d, r8d; WaitMode
0x1402c0397  mov     [rsp+88h+Timeout], 0; Timeout
0x1402c03a0  xor     edx, edx; WaitReason
0x1402c03a2  lea     rbp, [rsi+0E88h]
0x1402c03a9  mov     rcx, rbp; Object
0x1402c03ac  call    cs:__imp_KeWaitForSingleObject
0x1402c03b3  nop     dword ptr [rax+rax+00h]
0x1402c03b8  lea     r14, [rsi+0E78h]
0x1402c03bf  mov     rbx, [r14]
0x1402c03c2  cmp     rbx, r14
0x1402c03c5  jz      loc_1402C05E4
0x1402c03cb  xorps   xmm0, xmm0
0x1402c03ce  mov     dword ptr [rsp+88h+Timeout], 20h ; ' '; RemlockSize
0x1402c03d6  mov     r9d, 1; Line
0x1402c03dc  lea     r8, File; File
0x1402c03e3  mov     rdx, rbx; Tag
0x1402c03e6  lea     rcx, [rbx+40h]; RemoveLock
0x1402c03ea  movups  xmmword ptr [rsp+88h+SymbolicLinkName.Length], xmm0
0x1402c03ef  call    cs:__imp_IoAcquireRemoveLockEx
0x1402c03f6  nop     dword ptr [rax+rax+00h]
0x1402c03fb  movsxd  rdi, eax
0x1402c03fe  test    eax, eax
0x1402c0400  js      loc_1402C05BE
0x1402c0406  lea     rdi, [rbx+0A0h]
0x1402c040d  xor     edx, edx; Enable
0x1402c040f  mov     rcx, rdi; SymbolicLinkName
0x1402c0412  call    cs:__imp_IoSetDeviceInterfaceState
0x1402c0419  nop     dword ptr [rax+rax+00h]
0x1402c041e  mov     rdx, [rbx]
0x1402c0421  cmp     [rdx+8], rbx
0x1402c0425  jnz     loc_1402C05B7
0x1402c042b  mov     rax, [rbx+8]
0x1402c042f  cmp     [rax], rbx
0x1402c0432  jnz     loc_1402C05B7
0x1402c0438  mov     [rax], rdx
0x1402c043b  mov     rcx, rbp; Mutex
0x1402c043e  mov     [rdx+8], rax
0x1402c0442  xor     edx, edx; Wait
0x1402c0444  dec     dword ptr [rsi+0EC0h]
0x1402c044a  call    cs:__imp_KeReleaseMutex
0x1402c0451  nop     dword ptr [rax+rax+00h]
0x1402c0456  mov     rcx, [rsi+0A8h]; Resource
0x1402c045d  call    cs:__imp_ExReleaseResourceLite
0x1402c0464  nop     dword ptr [rax+rax+00h]
0x1402c0469  call    ?ReleaseMiniportListMutex@@YAXXZ; ReleaseMiniportListMutex(void)
0x1402c046e  mov     r8d, 20h ; ' '; RemlockSize
0x1402c0474  lea     rcx, [rbx+40h]; RemoveLock
0x1402c0478  mov     rdx, rbx; Tag
0x1402c047b  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x1402c0482  nop     dword ptr [rax+rax+00h]
0x1402c0487  call    ?AcquireMiniportListMutex@@YAXXZ; AcquireMiniportListMutex(void)
0x1402c048c  mov     rcx, [rsi+0A8h]; Resource
0x1402c0493  mov     dl, 1; Wait
0x1402c0495  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1402c049c  nop     dword ptr [rax+rax+00h]
0x1402c04a1  xor     r9d, r9d; Alertable
0x1402c04a4  mov     [rsp+88h+Timeout], 0; Timeout
0x1402c04ad  xor     r8d, r8d; WaitMode
0x1402c04b0  xor     edx, edx; WaitReason
0x1402c04b2  mov     rcx, rbp; Object
0x1402c04b5  call    cs:__imp_KeWaitForSingleObject
0x1402c04bc  nop     dword ptr [rax+rax+00h]
0x1402c04c1  cmp     byte ptr [rsi+0B1Fh], 0
0x1402c04c8  jnz     loc_1402C0577
0x1402c04ce  mov     rax, [rbx+18h]
0x1402c04d2  xorps   xmm0, xmm0
0x1402c04d5  movups  xmmword ptr [rsp+88h+ValueName], xmm0
0x1402c04da  mov     rdx, [rax+40h]
0x1402c04de  mov     rax, [rdx+20h]
0x1402c04e2  mov     rcx, [rax+40h]
0x1402c04e6  cmp     byte ptr [rcx+0B1Fh], 0
0x1402c04ed  jnz     short loc_1402C0538
0x1402c04ef  mov     edx, [rdx+98h]; Value
0x1402c04f5  lea     r8, [rsp+88h+ValueName]; Destination
0x1402c04fa  lea     rcx, aDeviceVideo; "\\Device\\Video"
0x1402c0501  call    DpiAppendNumberToString
0x1402c0506  test    eax, eax
0x1402c0508  js      short loc_1402C0538
0x1402c050a  mov     r8, [rsp+88h+ValueName+8]; ValueName
0x1402c050f  lea     rdx, aVideo; "VIDEO"
0x1402c0516  mov     ecx, 4; RelativeTo
0x1402c051b  call    cs:__imp_RtlDeleteRegistryValue
0x1402c0522  nop     dword ptr [rax+rax+00h]
0x1402c0527  lea     rcx, [rsp+88h+ValueName]; UnicodeString
0x1402c052c  call    cs:__imp_RtlFreeUnicodeString
0x1402c0533  nop     dword ptr [rax+rax+00h]
0x1402c0538  mov     edx, [rbx+98h]
0x1402c053e  lea     r8, [rsp+88h+SymbolicLinkName]; Destination
0x1402c0543  inc     edx; Value
0x1402c0545  lea     rcx, aDosdevicesDisp; "\\DosDevices\\DISPLAY"
0x1402c054c  call    DpiAppendNumberToString
0x1402c0551  test    eax, eax
0x1402c0553  js      short loc_1402C0577
0x1402c0555  lea     rcx, [rsp+88h+SymbolicLinkName]; SymbolicLinkName
0x1402c055a  call    cs:__imp_IoDeleteSymbolicLink
0x1402c0561  nop     dword ptr [rax+rax+00h]
0x1402c0566  lea     rcx, [rsp+88h+SymbolicLinkName]; UnicodeString
0x1402c056b  call    cs:__imp_RtlFreeUnicodeString
0x1402c0572  nop     dword ptr [rax+rax+00h]
0x1402c0577  mov     rcx, rdi; UnicodeString
0x1402c057a  call    cs:__imp_RtlFreeUnicodeString
0x1402c0581  nop     dword ptr [rax+rax+00h]
0x1402c0586  mov     r8d, [rbx+98h]
0x1402c058d  xor     r9d, r9d
0x1402c0590  mov     rdx, [rsi+1700h]
0x1402c0597  mov     cl, [rsi+0B1Fh]
0x1402c059d  call    DxgkReleaseGdiViewId
0x1402c05a2  mov     rcx, [rbx+18h]; DeviceObject
0x1402c05a6  call    cs:__imp_IoDeleteDevice
0x1402c05ad  nop     dword ptr [rax+rax+00h]
0x1402c05b2  jmp     loc_1402C03BF
0x1402c05b7  mov     ecx, 3
0x1402c05bc  int     29h; Win8: RtlFailFast(ecx)
0x1402c05be  xor     ecx, ecx
0x1402c05c0  mov     r9, rdi
0x1402c05c3  mov     edx, 113h
0x1402c05c8  lea     r8d, [rcx+15h]
0x1402c05cc  call    cs:__imp_WdLogSingleEntry3
0x1402c05d3  nop     dword ptr [rax+rax+00h]
0x1402c05d8  mov     cs:WdLogGlobalForLineNumber, 221h
0x1402c05e2  jmp     short loc_1402C05E6
0x1402c05e4  xor     edi, edi
0x1402c05e6  xor     edx, edx; Wait
0x1402c05e8  mov     rcx, rbp; Mutex
0x1402c05eb  call    cs:__imp_KeReleaseMutex
0x1402c05f2  nop     dword ptr [rax+rax+00h]
0x1402c05f7  mov     eax, edi
0x1402c05f9  add     rsp, 58h
0x1402c05fd  pop     r15
0x1402c05ff  pop     r14
0x1402c0601  pop     rdi
0x1402c0602  pop     rsi
0x1402c0603  pop     rbp
0x1402c0604  pop     rbx
0x1402c0605  retn
```
