# CloudAPHelper::LogonUserW(uchar *,ulong,void * *,long *)

- ea: `0x1800943c0`
- end: `0x180094742`
- name: `?LogonUserW@CloudAPHelper@@UEAAJPEAEKPEAPEAXPEAJ@Z`
- size: `898`
- prototype: `int(CloudAPHelper *__hidden this, unsigned __int8 *, unsigned int, void **, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001aa0`
- `0x180004714`
- `0x180005090`
- `0x180078c20`
- `0x180089578`
- `0x1800943c0`
- `0x180096fb8`

## import_xrefs

- `SspiCli!LsaFreeReturnBuffer` at `0x180094723`
- `SspiCli!LsaFreeReturnBuffer` at `0x180094723`
- `SspiCli!LsaLogonUser` at `0x1800945d6`
- `SspiCli!LsaLogonUser` at `0x1800945d6`

## string_xrefs

- `0x180094487`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180094527`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180094624`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18009441c`: `Terminal Services API`
- `0x1800944fe`: `Missing paramter phToken`

## pseudocode

```c

```
