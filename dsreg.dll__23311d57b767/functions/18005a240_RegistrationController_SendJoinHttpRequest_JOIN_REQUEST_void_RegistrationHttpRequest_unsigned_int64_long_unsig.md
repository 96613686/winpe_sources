# RegistrationController::SendJoinHttpRequest(_JOIN_REQUEST *,void (*)(RegistrationHttpRequest *,unsigned __int64,long),unsigned __int64)

- ea: `0x18005a240`
- end: `0x18005aa88`
- name: `?SendJoinHttpRequest@RegistrationController@@AEAAJPEAU_JOIN_REQUEST@@P6AXPEAVRegistrationHttpRequest@@_KJ@Z2@Z`
- size: `2120`
- prototype: `int(RegistrationController *__hidden this, struct _JOIN_REQUEST *, void (*)(struct RegistrationHttpRequest *, unsigned __int64, int), unsigned __int64)`
- caller_count: `1`
- callee_count: `38`
- tags: ``

## callers

- `0x180057c74`

## callees

- `0x1800011ec`
- `0x1800012a4`
- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x18000fc20`
- `0x180012948`
- `0x1800204f0`
- `0x1800307c4`
- `0x18003334c`
- `0x18003f200`
- `0x180043ef8`
- `0x180044300`
- `0x18004651c`
- `0x180051604`
- `0x180053e60`
- `0x180055174`
- `0x180055194`
- `0x180057260`
- `0x18005786c`
- `0x180057bd8`
- `0x180057c18`
- `0x180057e64`
- `0x18005a240`
- `0x18005b348`
- `0x18005b6c4`
- `0x18005e604`
- `0x18005f178`
- `0x18005f1e4`
- `0x1800612b0`
- `0x180063e78`
- `0x180064b9c`
- `0x180064ed0`
- `0x18006e66c`
- `0x180076b8c`
- `0x180077118`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005a543`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005a543`
- `CRYPT32!CertFreeCertificateContext` at `0x18005aa2a`
- `CRYPT32!CertFreeCertificateContext` at `0x18005aa2a`

## string_xrefs

- `0x18005a46b`: `CopyStringSafeW`
- `0x18005a477`: `%s: Device token was provided by the caller. MSA device ticket will not be retrieved.`
- `0x18005a825`: `RegistrationRequestSerializer::CreateRegistrationRequestBody`
- `0x18005a96b`: `RegistrationRequestSerializer::CreateRegistrationRequestHeaders`
- `0x18005a984`: `%s: Sending join request to server: %s; Path: %s; Method: %s.`

## pseudocode

```c

```
