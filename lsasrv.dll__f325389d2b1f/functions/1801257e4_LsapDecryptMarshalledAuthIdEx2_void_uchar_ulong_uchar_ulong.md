# LsapDecryptMarshalledAuthIdEx2(void *,uchar *,ulong,uchar * *,ulong *)

- ea: `0x1801257e4`
- end: `0x1801259fe`
- name: `?LsapDecryptMarshalledAuthIdEx2@@YAJPEAXPEAEKPEAPEAEPEAK@Z`
- size: `538`
- prototype: `int(void *, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18012535c`
- `0x18012716c`

## callees

- `0x1800040d0`
- `0x180011278`
- `0x18005fecc`
- `0x180060cb0`
- `0x1800b9304`
- `0x1801257e4`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18012589d`
- `ntdll!NtSetInformationThread` at `0x180125932`
- `ntdll!NtSetInformationThread` at `0x18012589d`
- `ntdll!NtSetInformationThread` at `0x180125932`
- `SspiCli!SspiLocalFree` at `0x1801259ae`
- `SspiCli!SspiLocalFree` at `0x1801259ae`
- `SspiCli!SspiDecryptAuthIdentityEx` at `0x1801258c8`
- `SspiCli!SspiDecryptAuthIdentityEx` at `0x1801258c8`
- `SspiCli!SspiUnmarshalAuthIdentity` at `0x180125846`
- `SspiCli!SspiUnmarshalAuthIdentity` at `0x180125846`
- `SspiCli!SspiFreeAuthIdentity` at `0x1801259cd`
- `SspiCli!SspiFreeAuthIdentity` at `0x1801259cd`
- `SspiCli!SspiMarshalAuthIdentity` at `0x1801258ee`
- `SspiCli!SspiMarshalAuthIdentity` at `0x1801258ee`

## string_xrefs

- `0x1801258af`: `NtSetInformationThread(Impersonate)`
- `0x180125946`: `NtSetInformationThread(Unimpersonate)`

## pseudocode

```c

```
