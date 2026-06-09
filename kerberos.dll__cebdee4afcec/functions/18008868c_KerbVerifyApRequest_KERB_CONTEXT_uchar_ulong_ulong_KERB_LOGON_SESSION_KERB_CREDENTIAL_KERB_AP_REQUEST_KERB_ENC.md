# KerbVerifyApRequest(_KERB_CONTEXT * *,uchar *,ulong,ulong,_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,KERB_AP_REQUEST * *,KERB_ENCRYPTED_TICKET * *,KERB_AUTHENTICATOR * *,_KERB_ENCRYPTION_KEY *,_KERB_ENCRYPTION_KEY *,_KERB_ENCRYPTION_KEY *,ulong *,ulong *,long *,ulong *,PSEC_CHANNEL_BINDINGS_ANY,_SEC_CHANNEL_BINDINGS_RESULT *,KerberosTransportContext *)

- ea: `0x18008868c`
- end: `0x1800898c4`
- name: `?KerbVerifyApRequest@@YAJPEAPEAU_KERB_CONTEXT@@PEAEKKPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAPEAUKERB_AP_REQUEST@@PEAPEAUKERB_ENCRYPTED_TICKET@@PEAPEAUKERB_AUTHENTICATOR@@PEAU_KERB_ENCRYPTION_KEY@@77PEAK8PEAJ8TPSEC_CHANNEL_BINDINGS_ANY@@PEAU_SEC_CHANNEL_BINDINGS_RESULT@@PEAVKerberosTransportContext@@@Z`
- size: `4664`
- prototype: `int __high(struct _KERB_CONTEXT **, unsigned __int8 *, unsigned int, unsigned int, struct _KERB_LOGON_SESSION *, struct _KERB_CREDENTIAL *, struct KERB_AP_REQUEST **, struct KERB_ENCRYPTED_TICKET **, struct KERB_AUTHENTICATOR **, struct _KERB_ENCRYPTION_KEY *, struct _KERB_ENCRYPTION_KEY *, struct _KERB_ENCRYPTION_KEY *, unsigned int *, unsigned int *, int *, unsigned int *, union PSEC_CHANNEL_BINDINGS_ANY, struct _SEC_CHANNEL_BINDINGS_RESULT *, struct KerberosTransportContext *)`
- caller_count: `3`
- callee_count: `40`
- tags: `loader_planting`

## callers

- `0x18002db10`
- `0x1800ce9ac`
- `0x1800cefe4`

## callees

- `0x180002ba4`
- `0x180004760`
- `0x180006920`
- `0x180009afc`
- `0x18000a630`
- `0x18000b5c0`
- `0x180010c60`
- `0x180010e90`
- `0x180011150`
- `0x1800113f0`
- `0x180011520`
- `0x18001245c`
- `0x180015698`
- `0x180030ea8`
- `0x180032964`
- `0x180036994`
- `0x1800428e4`
- `0x18006a2a8`
- `0x18006aa04`
- `0x18006ba6c`
- `0x18006cbec`
- `0x18006d5a0`
- `0x18006d928`
- `0x18006e90c`
- `0x18007108c`
- `0x1800744cf`
- `0x18008529c`
- `0x1800872a0`
- `0x180087d7c`
- `0x18008868c`
- `0x180089ec0`
- `0x180089f9c`
- `0x18008a49c`
- `0x18008b70c`
- `0x18008fca0`
- `0x18008fd08`
- `0x18008fda0`
- `0x1800c2fbc`
- `0x1800d54f8`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180088958`
- `ntdll!RtlEnterCriticalSection` at `0x180088b22`
- `ntdll!RtlEnterCriticalSection` at `0x180088c5b`
- `ntdll!RtlEnterCriticalSection` at `0x180088db5`
- `ntdll!RtlEnterCriticalSection` at `0x180088f53`
- `ntdll!RtlEnterCriticalSection` at `0x180089061`
- `ntdll!RtlEnterCriticalSection` at `0x1800891ae`
- `ntdll!RtlEnterCriticalSection` at `0x180088958`
- `ntdll!RtlEnterCriticalSection` at `0x180088b22`
- `ntdll!RtlEnterCriticalSection` at `0x180088c5b`
- `ntdll!RtlEnterCriticalSection` at `0x180088db5`
- `ntdll!RtlEnterCriticalSection` at `0x180088f53`
- `ntdll!RtlEnterCriticalSection` at `0x180089061`
- `ntdll!RtlEnterCriticalSection` at `0x1800891ae`
- `ntdll!RtlLeaveCriticalSection` at `0x180088a9a`
- `ntdll!RtlLeaveCriticalSection` at `0x180088bf6`
- `ntdll!RtlLeaveCriticalSection` at `0x180088d57`
- `ntdll!RtlLeaveCriticalSection` at `0x180088e77`
- `ntdll!RtlLeaveCriticalSection` at `0x180088f0e`
- `ntdll!RtlLeaveCriticalSection` at `0x180089172`
- `ntdll!RtlLeaveCriticalSection` at `0x1800892cf`
- `ntdll!RtlLeaveCriticalSection` at `0x180089833`
- `ntdll!RtlLeaveCriticalSection` at `0x180088a9a`
- `ntdll!RtlLeaveCriticalSection` at `0x180088bf6`
- `ntdll!RtlLeaveCriticalSection` at `0x180088d57`
- `ntdll!RtlLeaveCriticalSection` at `0x180088e77`
- `ntdll!RtlLeaveCriticalSection` at `0x180088f0e`
- `ntdll!RtlLeaveCriticalSection` at `0x180089172`
- `ntdll!RtlLeaveCriticalSection` at `0x1800892cf`
- `ntdll!RtlLeaveCriticalSection` at `0x180089833`

## string_xrefs

- `0x1800889f3`: `failed to create empty context%#x\n`

## pseudocode

```c

```
