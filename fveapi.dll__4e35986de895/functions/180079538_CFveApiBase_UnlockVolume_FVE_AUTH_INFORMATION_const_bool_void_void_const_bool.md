# CFveApiBase::UnlockVolume(_FVE_AUTH_INFORMATION const *,bool,void (*)(void const *),bool *)

- ea: `0x180079538`
- end: `0x18007afdc`
- name: `?UnlockVolume@CFveApiBase@@QEAAJPEBU_FVE_AUTH_INFORMATION@@_NP6AXPEBX@ZPEA_N@Z`
- size: `6820`
- prototype: `__int64 __usercall@<rax>(CFveApiBase *__hidden this@<rcx>, const struct _FVE_AUTH_INFORMATION *@<rdx>, bool@<r8b>, void (*)(const void *)@<r9>, bool *)`
- caller_count: `6`
- callee_count: `37`
- tags: `loader_planting`

## callers

- `0x18006be70`
- `0x18006c0e0`
- `0x18006c270`
- `0x180085be8`
- `0x1800ce438`
- `0x1800ceb48`

## callees

- `0x1800022ac`
- `0x180008d70`
- `0x1800090c0`
- `0x180009130`
- `0x180018b10`
- `0x180019128`
- `0x18001ac58`
- `0x18001b260`
- `0x18001c470`
- `0x18001de20`
- `0x18001f010`
- `0x180037edc`
- `0x18003a314`
- `0x180045444`
- `0x18004ad74`
- `0x180053a20`
- `0x180053a80`
- `0x180053b5c`
- `0x180053bac`
- `0x180053e64`
- `0x180058334`
- `0x180070ccc`
- `0x180078fd0`
- `0x1800790a4`
- `0x180079538`
- `0x18007b1f8`
- `0x180084090`
- `0x18008568c`
- `0x1800a5c14`
- `0x1800a5d3c`
- `0x1800a6b54`
- `0x1800ed5e0`
- `0x1800eec64`
- `0x1800eefb0`
- `0x180111bb8`
- `0x180111cd0`
- `0x18011f010`

## import_xrefs

- `ntdll!NtSetSystemEnvironmentValueEx` at `0x18007ae9f`
- `ntdll!NtSetSystemEnvironmentValueEx` at `0x180123a8b`
- `ntdll!NtSetSystemEnvironmentValueEx` at `0x18007ae9f`
- `ntdll!NtSetSystemEnvironmentValueEx` at `0x180123a8b`
- `ntdll!RtlInitUnicodeString` at `0x18007ae75`
- `ntdll!RtlInitUnicodeString` at `0x180123a63`
- `ntdll!RtlInitUnicodeString` at `0x18007ae75`
- `ntdll!RtlInitUnicodeString` at `0x180123a63`
- `ncrypt!NCryptIsKeyHandle` at `0x180079ada`
- `ncrypt!NCryptIsKeyHandle` at `0x180079ada`

## string_xrefs

- `0x18007aaac`: `VolumePath`
- `0x18012369a`: `VolumePath`

## pseudocode

```c

```
