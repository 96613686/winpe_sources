# CRdpWindowTracker::HookProc(HWINEVENTHOOK__ *,ulong,HWND__ *,long,long,ulong,ulong)

- ea: `0x14005d16c`
- end: `0x14005d86c`
- name: `?HookProc@CRdpWindowTracker@@AEAAXPEAUHWINEVENTHOOK__@@KPEAUHWND__@@JJKK@Z`
- size: `1792`
- prototype: `void __usercall(CRdpWindowTracker *__hidden this@<rcx>, HWINEVENTHOOK@<rdx>, unsigned int@<r8d>, HWND@<r9>, int, int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x14005ee00`

## callees

- `0x140004b1c`
- `0x140005750`
- `0x14000a640`
- `0x14000d350`
- `0x14000efb8`
- `0x14001094c`
- `0x140033cd4`
- `0x14005c5dc`
- `0x14005c788`
- `0x14005d16c`
- `0x14005e17c`
- `0x14005e4a0`
- `0x14005f1c0`
- `0x14005f470`
- `0x14006b010`

## import_xrefs

- `USER32!IsWindowVisible` at `0x14005d291`
- `USER32!IsWindowVisible` at `0x14005d291`
- `USER32!IsChild` at `0x14005d271`
- `USER32!IsChild` at `0x14005d5ac`
- `USER32!IsChild` at `0x14005d271`
- `USER32!IsChild` at `0x14005d5ac`
- `USER32!GetParent` at `0x14005d288`
- `USER32!GetParent` at `0x14005d762`
- `USER32!GetParent` at `0x14005d288`
- `USER32!GetParent` at `0x14005d762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005d771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005d771`

## string_xrefs

- `0x14005d6ed`: `UpdateAllGeometries() failed`

## pseudocode

```c

```
