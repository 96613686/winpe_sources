# DpiGdoDestroyGdiObjects

- ea: `0x1402c6dd0`
- end: `0x1402c7057`
- name: `DpiGdoDestroyGdiObjects`
- size: `647`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callers

- `0x1402a9720`
- `0x1402a9e9c`

## callees

- `0x140040908`
- `0x14004094c`
- `0x14026aeec`
- `0x1402b7740`
- `0x1402c6dd0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c6ee5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c6ee5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c6ead`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c6ead`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c6f7c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c6fbb`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c6fca`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c6f7c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c6fbb`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402c6fca`
- `ntoskrnl!IoDeleteDevice` at `0x1402c6ff6`
- `ntoskrnl!IoDeleteDevice` at `0x1402c6ff6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402c6dfc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402c6f05`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402c6dfc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402c6f05`
- `ntoskrnl!KeReleaseMutex` at `0x1402c6e9a`
- `ntoskrnl!KeReleaseMutex` at `0x1402c703b`
- `ntoskrnl!KeReleaseMutex` at `0x1402c6e9a`
- `ntoskrnl!KeReleaseMutex` at `0x1402c703b`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1402c6e3f`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1402c6e3f`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402c6e62`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402c6e62`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1402c6ecb`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1402c6ecb`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1402c6faa`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1402c6faa`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1402c6f6b`
- `ntoskrnl!RtlDeleteRegistryValue` at `0x1402c6f6b`
- `watchdog!WdLogSingleEntry3` at `0x1402c701c`
- `watchdog!WdLogSingleEntry3` at `0x1402c701c`

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
0x1402c6dd0  push    rbx
0x1402c6dd2  push    rbp
0x1402c6dd3  push    rsi
0x1402c6dd4  push    rdi
0x1402c6dd5  push    r14
0x1402c6dd7  push    r15
0x1402c6dd9  sub     rsp, 58h
0x1402c6ddd  mov     rsi, [rcx+40h]
0x1402c6de1  xor     r9d, r9d; Alertable
0x1402c6de4  xor     r8d, r8d; WaitMode
0x1402c6de7  mov     [rsp+88h+Timeout], 0; Timeout
0x1402c6df0  xor     edx, edx; WaitReason
0x1402c6df2  lea     rbp, [rsi+0E88h]
0x1402c6df9  mov     rcx, rbp; Object
0x1402c6dfc  call    cs:__imp_KeWaitForSingleObject
0x1402c6e03  nop     dword ptr [rax+rax+00h]
0x1402c6e08  lea     r14, [rsi+0E78h]
0x1402c6e0f  mov     rbx, [r14]
0x1402c6e12  cmp     rbx, r14
0x1402c6e15  jz      loc_1402C7034
0x1402c6e1b  xorps   xmm0, xmm0
0x1402c6e1e  mov     dword ptr [rsp+88h+Timeout], 20h ; ' '; RemlockSize
0x1402c6e26  mov     r9d, 1; Line
0x1402c6e2c  lea     r8, File; File
0x1402c6e33  mov     rdx, rbx; Tag
0x1402c6e36  lea     rcx, [rbx+40h]; RemoveLock
0x1402c6e3a  movups  xmmword ptr [rsp+88h+SymbolicLinkName.Length], xmm0
0x1402c6e3f  call    cs:__imp_IoAcquireRemoveLockEx
0x1402c6e46  nop     dword ptr [rax+rax+00h]
0x1402c6e4b  movsxd  rdi, eax
0x1402c6e4e  test    eax, eax
0x1402c6e50  js      loc_1402C700E
0x1402c6e56  lea     rdi, [rbx+0A0h]
0x1402c6e5d  xor     edx, edx; Enable
0x1402c6e5f  mov     rcx, rdi; SymbolicLinkName
0x1402c6e62  call    cs:__imp_IoSetDeviceInterfaceState
0x1402c6e69  nop     dword ptr [rax+rax+00h]
0x1402c6e6e  mov     rdx, [rbx]
0x1402c6e71  cmp     [rdx+8], rbx
0x1402c6e75  jnz     loc_1402C7007
0x1402c6e7b  mov     rax, [rbx+8]
0x1402c6e7f  cmp     [rax], rbx
0x1402c6e82  jnz     loc_1402C7007
0x1402c6e88  mov     [rax], rdx
0x1402c6e8b  mov     rcx, rbp; Mutex
0x1402c6e8e  mov     [rdx+8], rax
0x1402c6e92  xor     edx, edx; Wait
0x1402c6e94  dec     dword ptr [rsi+0EC0h]
0x1402c6e9a  call    cs:__imp_KeReleaseMutex
0x1402c6ea1  nop     dword ptr [rax+rax+00h]
0x1402c6ea6  mov     rcx, [rsi+0A8h]; Resource
0x1402c6ead  call    cs:__imp_ExReleaseResourceLite
0x1402c6eb4  nop     dword ptr [rax+rax+00h]
0x1402c6eb9  call    ?ReleaseMiniportListMutex@@YAXXZ; ReleaseMiniportListMutex(void)
0x1402c6ebe  mov     r8d, 20h ; ' '; RemlockSize
0x1402c6ec4  lea     rcx, [rbx+40h]; RemoveLock
0x1402c6ec8  mov     rdx, rbx; Tag
0x1402c6ecb  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x1402c6ed2  nop     dword ptr [rax+rax+00h]
0x1402c6ed7  call    ?AcquireMiniportListMutex@@YAXXZ; AcquireMiniportListMutex(void)
0x1402c6edc  mov     rcx, [rsi+0A8h]; Resource
0x1402c6ee3  mov     dl, 1; Wait
0x1402c6ee5  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1402c6eec  nop     dword ptr [rax+rax+00h]
0x1402c6ef1  xor     r9d, r9d; Alertable
0x1402c6ef4  mov     [rsp+88h+Timeout], 0; Timeout
0x1402c6efd  xor     r8d, r8d; WaitMode
0x1402c6f00  xor     edx, edx; WaitReason
0x1402c6f02  mov     rcx, rbp; Object
0x1402c6f05  call    cs:__imp_KeWaitForSingleObject
0x1402c6f0c  nop     dword ptr [rax+rax+00h]
0x1402c6f11  cmp     byte ptr [rsi+0B1Fh], 0
0x1402c6f18  jnz     loc_1402C6FC7
0x1402c6f1e  mov     rax, [rbx+18h]
0x1402c6f22  xorps   xmm0, xmm0
0x1402c6f25  movups  xmmword ptr [rsp+88h+ValueName], xmm0
0x1402c6f2a  mov     rdx, [rax+40h]
0x1402c6f2e  mov     rax, [rdx+20h]
0x1402c6f32  mov     rcx, [rax+40h]
0x1402c6f36  cmp     byte ptr [rcx+0B1Fh], 0
0x1402c6f3d  jnz     short loc_1402C6F88
0x1402c6f3f  mov     edx, [rdx+98h]; Value
0x1402c6f45  lea     r8, [rsp+88h+ValueName]; Destination
0x1402c6f4a  lea     rcx, aDeviceVideo; "\\Device\\Video"
0x1402c6f51  call    DpiAppendNumberToString
0x1402c6f56  test    eax, eax
0x1402c6f58  js      short loc_1402C6F88
0x1402c6f5a  mov     r8, [rsp+88h+ValueName+8]; ValueName
0x1402c6f5f  lea     rdx, aVideo; "VIDEO"
0x1402c6f66  mov     ecx, 4; RelativeTo
0x1402c6f6b  call    cs:__imp_RtlDeleteRegistryValue
0x1402c6f72  nop     dword ptr [rax+rax+00h]
0x1402c6f77  lea     rcx, [rsp+88h+ValueName]; UnicodeString
0x1402c6f7c  call    cs:__imp_RtlFreeUnicodeString
0x1402c6f83  nop     dword ptr [rax+rax+00h]
0x1402c6f88  mov     edx, [rbx+98h]
0x1402c6f8e  lea     r8, [rsp+88h+SymbolicLinkName]; Destination
0x1402c6f93  inc     edx; Value
0x1402c6f95  lea     rcx, aDosdevicesDisp; "\\DosDevices\\DISPLAY"
0x1402c6f9c  call    DpiAppendNumberToString
0x1402c6fa1  test    eax, eax
0x1402c6fa3  js      short loc_1402C6FC7
0x1402c6fa5  lea     rcx, [rsp+88h+SymbolicLinkName]; SymbolicLinkName
0x1402c6faa  call    cs:__imp_IoDeleteSymbolicLink
0x1402c6fb1  nop     dword ptr [rax+rax+00h]
0x1402c6fb6  lea     rcx, [rsp+88h+SymbolicLinkName]; UnicodeString
0x1402c6fbb  call    cs:__imp_RtlFreeUnicodeString
0x1402c6fc2  nop     dword ptr [rax+rax+00h]
0x1402c6fc7  mov     rcx, rdi; UnicodeString
0x1402c6fca  call    cs:__imp_RtlFreeUnicodeString
0x1402c6fd1  nop     dword ptr [rax+rax+00h]
0x1402c6fd6  mov     r8d, [rbx+98h]
0x1402c6fdd  xor     r9d, r9d
0x1402c6fe0  mov     rdx, [rsi+1700h]
0x1402c6fe7  mov     cl, [rsi+0B1Fh]
0x1402c6fed  call    DxgkReleaseGdiViewId
0x1402c6ff2  mov     rcx, [rbx+18h]; DeviceObject
0x1402c6ff6  call    cs:__imp_IoDeleteDevice
0x1402c6ffd  nop     dword ptr [rax+rax+00h]
0x1402c7002  jmp     loc_1402C6E0F
0x1402c7007  mov     ecx, 3
0x1402c700c  int     29h; Win8: RtlFailFast(ecx)
0x1402c700e  xor     ecx, ecx
0x1402c7010  mov     r9, rdi
0x1402c7013  mov     edx, 113h
0x1402c7018  lea     r8d, [rcx+15h]
0x1402c701c  call    cs:__imp_WdLogSingleEntry3
0x1402c7023  nop     dword ptr [rax+rax+00h]
0x1402c7028  mov     cs:WdLogGlobalForLineNumber, 221h
0x1402c7032  jmp     short loc_1402C7036
0x1402c7034  xor     edi, edi
0x1402c7036  xor     edx, edx; Wait
0x1402c7038  mov     rcx, rbp; Mutex
0x1402c703b  call    cs:__imp_KeReleaseMutex
0x1402c7042  nop     dword ptr [rax+rax+00h]
0x1402c7047  mov     eax, edi
0x1402c7049  add     rsp, 58h
0x1402c704d  pop     r15
0x1402c704f  pop     r14
0x1402c7051  pop     rdi
0x1402c7052  pop     rsi
0x1402c7053  pop     rbp
0x1402c7054  pop     rbx
0x1402c7055  retn
```
