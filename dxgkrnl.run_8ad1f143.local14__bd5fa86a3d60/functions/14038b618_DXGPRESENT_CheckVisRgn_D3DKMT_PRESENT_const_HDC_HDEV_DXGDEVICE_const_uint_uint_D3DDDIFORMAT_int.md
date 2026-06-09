# DXGPRESENT::CheckVisRgn(_D3DKMT_PRESENT const *,HDC__ *,HDEV__ *,DXGDEVICE const *,uint,uint,_D3DDDIFORMAT,int)

- ea: `0x14038b618`
- end: `0x14038bf8b`
- name: `?CheckVisRgn@DXGPRESENT@@QEAAJPEBU_D3DKMT_PRESENT@@PEAUHDC__@@PEAUHDEV__@@PEBVDXGDEVICE@@IIW4_D3DDDIFORMAT@@H@Z`
- size: `2419`
- prototype: `__int64 __usercall@<rax>(DXGPRESENT *__hidden this@<rcx>, const struct _D3DKMT_PRESENT *@<rdx>, HDC@<r8>, HDEV@<r9>, const struct DXGDEVICE *, unsigned int, unsigned int, enum _D3DDDIFORMAT, int)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x14039aac0`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x14001b868`
- `0x14001b9c0`
- `0x140033f08`
- `0x14004d4a4`
- `0x1400a0cb0`
- `0x14019cf50`
- `0x1401f670c`
- `0x1401f7b58`
- `0x14038b5d0`
- `0x14038b618`
- `0x14038bf94`
- `0x14038c7d8`
- `0x140396818`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x14038b80a`
- `watchdog!WdLogSingleEntry2` at `0x14038bd70`
- `watchdog!WdLogSingleEntry2` at `0x14038bdfb`
- `watchdog!WdLogSingleEntry2` at `0x14038b80a`
- `watchdog!WdLogSingleEntry2` at `0x14038bd70`
- `watchdog!WdLogSingleEntry2` at `0x14038bdfb`
- `watchdog!WdLogSingleEntry3` at `0x14038bf57`
- `watchdog!WdLogSingleEntry3` at `0x14038bf57`
- `watchdog!WdLogSingleEntry0` at `0x14038b777`
- `watchdog!WdLogSingleEntry0` at `0x14038be52`
- `watchdog!WdLogSingleEntry0` at `0x14038b777`
- `watchdog!WdLogSingleEntry0` at `0x14038be52`
- `watchdog!WdLogSingleEntry5` at `0x14038b9e2`
- `watchdog!WdLogSingleEntry5` at `0x14038ba52`
- `watchdog!WdLogSingleEntry5` at `0x14038baa6`
- `watchdog!WdLogSingleEntry5` at `0x14038bb8f`
- `watchdog!WdLogSingleEntry5` at `0x14038bc20`
- `watchdog!WdLogSingleEntry5` at `0x14038b9e2`
- `watchdog!WdLogSingleEntry5` at `0x14038ba52`
- `watchdog!WdLogSingleEntry5` at `0x14038baa6`
- `watchdog!WdLogSingleEntry5` at `0x14038bb8f`
- `watchdog!WdLogSingleEntry5` at `0x14038bc20`
- `watchdog!WdLogSingleEntry1` at `0x14038b684`
- `watchdog!WdLogSingleEntry1` at `0x14038b72a`
- `watchdog!WdLogSingleEntry1` at `0x14038b8ec`
- `watchdog!WdLogSingleEntry1` at `0x14038b684`
- `watchdog!WdLogSingleEntry1` at `0x14038b72a`
- `watchdog!WdLogSingleEntry1` at `0x14038b8ec`

## string_xrefs

- `0x14038bb9b`: `0x%I64x not able to create hVisRgn hWindow = 0x%I64x hdc = 0x%I64x hDev = 0x%I64x PresentFlags = 0x%I64x`

## pseudocode

```c

```
