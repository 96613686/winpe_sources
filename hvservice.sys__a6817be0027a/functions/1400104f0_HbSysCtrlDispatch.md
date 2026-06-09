# HbSysCtrlDispatch

- ea: `0x1400104f0`
- end: `0x1400105cc`
- name: `HbSysCtrlDispatch`
- size: `220`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001600`
- `0x1400104f0`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140010519`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140010519`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400105b4`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400105b4`
- `ntoskrnl!IofCompleteRequest` at `0x140010554`
- `ntoskrnl!IofCompleteRequest` at `0x140010554`
- `ntoskrnl!IofCallDriver` at `0x140010574`
- `ntoskrnl!IofCallDriver` at `0x140010574`

## string_xrefs

- `0x140010535`: `SysCtrl dispatch: IoAcquireRemoveLock failed with 0x%x`

## pseudocode

```c
__int64 __fastcall HbSysCtrlDispatch(__int64 a1, IRP *a2)
{
  __int64 v2; // rbp
  NTSTATUS v4; // eax
  unsigned int v5; // edi
  NTSTATUS v6; // eax

  v2 = *(_QWORD *)(a1 + 64);
  v4 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 64), a2, File, 1u, 0x20u);
  v5 = v4;
  if ( v4 >= 0 )
  {
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    v6 = IofCallDriver(*(PDEVICE_OBJECT *)(v2 + 24), a2);
    v5 = v6;
    if ( v6 < 0 )
      HbpTraceEvent(1, "HbSysCtrlDispatch", 94, "SysCtrl dispatch: IoCallDriver failed with 0x%x", v6);
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 64), a2, 0x20u);
  }
  else
  {
    HbpTraceEvent(1, "HbSysCtrlDispatch", 77, "SysCtrl dispatch: IoAcquireRemoveLock failed with 0x%x", v4);
    a2->IoStatus.Status = v5;
    IofCompleteRequest(a2, 0);
  }
  return v5;
}

```

## disassembly

```asm
0x1400104f0  push    rbx
0x1400104f2  push    rbp
0x1400104f3  push    rsi
0x1400104f4  push    rdi
0x1400104f5  sub     rsp, 38h
0x1400104f9  mov     rbp, [rcx+40h]
0x1400104fd  lea     r8, File; File
0x140010504  mov     r9d, 1; Line
0x14001050a  mov     [rsp+58h+RemlockSize], 20h ; ' '; RemlockSize
0x140010512  mov     rbx, rdx
0x140010515  lea     rcx, [rbp+40h]; RemoveLock
0x140010519  call    cs:__imp_IoAcquireRemoveLockEx
0x140010520  nop     dword ptr [rax+rax+00h]
0x140010525  mov     edi, eax
0x140010527  test    eax, eax
0x140010529  jns     short loc_140010562
0x14001052b  mov     r8d, 4Dh ; 'M'
0x140010531  mov     [rsp+58h+RemlockSize], eax
0x140010535  lea     r9, aSysctrlDispatc; "SysCtrl dispatch: IoAcquireRemoveLock f"...
0x14001053c  lea     rdx, aHbsysctrldispa; "HbSysCtrlDispatch"
0x140010543  lea     ecx, [r8-4Ch]
0x140010547  call    HbpTraceEvent
0x14001054c  xor     edx, edx; PriorityBoost
0x14001054e  mov     [rbx+30h], edi
0x140010551  mov     rcx, rbx; Irp
0x140010554  call    cs:__imp_IofCompleteRequest
0x14001055b  nop     dword ptr [rax+rax+00h]
0x140010560  jmp     short loc_1400105C0
0x140010562  inc     byte ptr [rbx+43h]
0x140010565  mov     rdx, rbx; Irp
0x140010568  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x140010570  mov     rcx, [rbp+18h]; DeviceObject
0x140010574  call    cs:__imp_IofCallDriver
0x14001057b  nop     dword ptr [rax+rax+00h]
0x140010580  mov     edi, eax
0x140010582  test    eax, eax
0x140010584  jns     short loc_1400105A7
0x140010586  mov     r8d, 5Eh ; '^'
0x14001058c  mov     [rsp+58h+RemlockSize], eax
0x140010590  lea     r9, aSysctrlDispatc_0; "SysCtrl dispatch: IoCallDriver failed w"...
0x140010597  lea     rdx, aHbsysctrldispa; "HbSysCtrlDispatch"
0x14001059e  lea     ecx, [r8-5Dh]
0x1400105a2  call    HbpTraceEvent
0x1400105a7  mov     r8d, 20h ; ' '; RemlockSize
0x1400105ad  lea     rcx, [rbp+40h]; RemoveLock
0x1400105b1  mov     rdx, rbx; Tag
0x1400105b4  call    cs:__imp_IoReleaseRemoveLockEx
0x1400105bb  nop     dword ptr [rax+rax+00h]
0x1400105c0  mov     eax, edi
0x1400105c2  add     rsp, 38h
0x1400105c6  pop     rdi
0x1400105c7  pop     rsi
0x1400105c8  pop     rbp
0x1400105c9  pop     rbx
0x1400105ca  retn
```
