# BLTQUEUE::Present(DXGCONTEXT *,_D3DKMT_PRESENT const *,_DXGKARG_PRESENT const *,COREDEVICEACCESS *)

- ea: `0x14037db44`
- end: `0x14037e7e3`
- name: `?Present@BLTQUEUE@@QEAAJPEAVDXGCONTEXT@@PEBU_D3DKMT_PRESENT@@PEBU_DXGKARG_PRESENT@@PEAVCOREDEVICEACCESS@@@Z`
- size: `3231`
- prototype: `__int64 __usercall@<rax>(BLTQUEUE *__hidden this@<rcx>, struct DXGCONTEXT *@<rdx>, const struct _D3DKMT_PRESENT *@<r8>, const struct _DXGKARG_PRESENT *@<r9>, struct COREDEVICEACCESS *)`
- caller_count: `1`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x14037da88`

## callees

- `0x140012b14`
- `0x140013860`
- `0x1400144ec`
- `0x1400150d0`
- `0x1400161c8`
- `0x140019838`
- `0x14001a9d0`
- `0x14001ab20`
- `0x14001b890`
- `0x14001c320`
- `0x14001d0e4`
- `0x1400378f0`
- `0x140045ff8`
- `0x140059174`
- `0x1400670a4`
- `0x1400a01e0`
- `0x1400a0540`
- `0x14019fcc4`
- `0x1401e5360`
- `0x14028bed8`
- `0x140301f60`
- `0x140323854`
- `0x140327c10`
- `0x1403412b8`
- `0x14037d514`
- `0x14037db44`
- `0x14037ed4c`
- `0x14037ee14`
- `0x14037f300`
- `0x14037f3dc`
- `0x14037f4ac`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14037e793`
- `ntoskrnl!KeSetEvent` at `0x14037e793`
- `ntoskrnl!KeWaitForSingleObject` at `0x14037dd8d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14037de64`
- `ntoskrnl!KeWaitForSingleObject` at `0x14037e0f7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14037dd8d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14037de64`
- `ntoskrnl!KeWaitForSingleObject` at `0x14037e0f7`
- `ntoskrnl!KeReleaseMutex` at `0x14037dda6`
- `ntoskrnl!KeReleaseMutex` at `0x14037de7c`
- `ntoskrnl!KeReleaseMutex` at `0x14037e12e`
- `ntoskrnl!KeReleaseMutex` at `0x14037dda6`
- `ntoskrnl!KeReleaseMutex` at `0x14037de7c`
- `ntoskrnl!KeReleaseMutex` at `0x14037e12e`
- `HAL!KeQueryPerformanceCounter` at `0x14037e774`
- `HAL!KeQueryPerformanceCounter` at `0x14037e774`
- `watchdog!WdLogSingleEntry2` at `0x14037dc89`
- `watchdog!WdLogSingleEntry2` at `0x14037ddcb`
- `watchdog!WdLogSingleEntry2` at `0x14037deb2`
- `watchdog!WdLogSingleEntry2` at `0x14037df41`
- `watchdog!WdLogSingleEntry2` at `0x14037dfa2`
- `watchdog!WdLogSingleEntry2` at `0x14037e084`
- `watchdog!WdLogSingleEntry2` at `0x14037dc89`
- `watchdog!WdLogSingleEntry2` at `0x14037ddcb`
- `watchdog!WdLogSingleEntry2` at `0x14037deb2`
- `watchdog!WdLogSingleEntry2` at `0x14037df41`
- `watchdog!WdLogSingleEntry2` at `0x14037dfa2`
- `watchdog!WdLogSingleEntry2` at `0x14037e084`
- `watchdog!WdLogSingleEntry3` at `0x14037e604`
- `watchdog!WdLogSingleEntry3` at `0x14037e680`
- `watchdog!WdLogSingleEntry3` at `0x14037e604`
- `watchdog!WdLogSingleEntry3` at `0x14037e680`
- `watchdog!WdLogSingleEntry0` at `0x14037e185`
- `watchdog!WdLogSingleEntry0` at `0x14037e25c`
- `watchdog!WdLogSingleEntry0` at `0x14037e324`
- `watchdog!WdLogSingleEntry0` at `0x14037e185`
- `watchdog!WdLogSingleEntry0` at `0x14037e25c`
- `watchdog!WdLogSingleEntry0` at `0x14037e324`

## string_xrefs

- `0x14037e6bb`: `Exception when accessing command buffer 0x%I64x on 0x%I64x for 0x%I64x.`

## pseudocode

```c

```
