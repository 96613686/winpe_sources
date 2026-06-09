# CIMEUIWindowHandler::ImeUINotifyHandler(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18001a9e0`
- end: `0x18001b204`
- name: `?ImeUINotifyHandler@CIMEUIWindowHandler@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `2084`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `2`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a9e0`
- `0x180047a70`

## callees

- `0x180015850`
- `0x180016dc0`
- `0x1800185f0`
- `0x18001a460`
- `0x18001a9e0`
- `0x18001cc80`
- `0x18003d290`
- `0x180049234`
- `0x18004e334`
- `0x180051b14`
- `0x180057fd0`
- `0x18005e578`
- `0x180060178`
- `0x180061a6c`
- `0x18006d5c0`
- `0x18006e2dc`
- `0x18008c58c`
- `0x180098bfc`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001abff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001acd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001abff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001acd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af66`
- `USER32!SendMessageW` at `0x18001b167`
- `USER32!SendMessageW` at `0x18001b167`
- `USER32!PostMessageW` at `0x18001aed9`
- `USER32!PostMessageW` at `0x18001aed9`
- `USER32!SetTimer` at `0x18001b0f6`
- `USER32!SetTimer` at `0x18001b0f6`
- `USER32!IsWindowVisible` at `0x18001afeb`
- `USER32!IsWindowVisible` at `0x18001b048`
- `USER32!IsWindowVisible` at `0x18001afeb`
- `USER32!IsWindowVisible` at `0x18001b048`
- `USER32!GetWindowLongPtrW` at `0x18001aa2b`
- `USER32!GetWindowLongPtrW` at `0x18001ac13`
- `USER32!GetWindowLongPtrW` at `0x18001ac93`
- `USER32!GetWindowLongPtrW` at `0x18001ae7b`
- `USER32!GetWindowLongPtrW` at `0x18001aa2b`
- `USER32!GetWindowLongPtrW` at `0x18001ac13`
- `USER32!GetWindowLongPtrW` at `0x18001ac93`
- `USER32!GetWindowLongPtrW` at `0x18001ae7b`
- `USER32!IsWindow` at `0x18001ad7e`
- `USER32!IsWindow` at `0x18001ada2`
- `USER32!IsWindow` at `0x18001aeb9`
- `USER32!IsWindow` at `0x18001ad7e`
- `USER32!IsWindow` at `0x18001ada2`
- `USER32!IsWindow` at `0x18001aeb9`
- `IMM32!ImmLockIMC` at `0x18001aa57`
- `IMM32!ImmLockIMC` at `0x18001aa57`
- `IMM32!ImmGetDefaultIMEWnd` at `0x18001aead`
- `IMM32!ImmGetDefaultIMEWnd` at `0x18001aead`
- `IMM32!ImmUnlockIMC` at `0x18001abc0`
- `IMM32!ImmUnlockIMC` at `0x18001ac70`
- `IMM32!ImmUnlockIMC` at `0x18001acef`
- `IMM32!ImmUnlockIMC` at `0x18001ad65`
- `IMM32!ImmUnlockIMC` at `0x18001abc0`
- `IMM32!ImmUnlockIMC` at `0x18001ac70`
- `IMM32!ImmUnlockIMC` at `0x18001acef`
- `IMM32!ImmUnlockIMC` at `0x18001ad65`
- `IMM32!ImmLockIMCC` at `0x18001aa91`
- `IMM32!ImmLockIMCC` at `0x18001ade6`
- `IMM32!ImmLockIMCC` at `0x18001aa91`
- `IMM32!ImmLockIMCC` at `0x18001ade6`
- `IMM32!ImmUnlockIMCC` at `0x18001ab9a`
- `IMM32!ImmUnlockIMCC` at `0x18001abf5`
- `IMM32!ImmUnlockIMCC` at `0x18001ac4a`
- `IMM32!ImmUnlockIMCC` at `0x18001acc9`
- `IMM32!ImmUnlockIMCC` at `0x18001ad3f`
- `IMM32!ImmUnlockIMCC` at `0x18001af58`
- `IMM32!ImmUnlockIMCC` at `0x18001ab9a`
- `IMM32!ImmUnlockIMCC` at `0x18001abf5`
- `IMM32!ImmUnlockIMCC` at `0x18001ac4a`
- `IMM32!ImmUnlockIMCC` at `0x18001acc9`
- `IMM32!ImmUnlockIMCC` at `0x18001ad3f`
- `IMM32!ImmUnlockIMCC` at `0x18001af58`

## string_xrefs

- `0x18001af3b`: `UIComposition::OnPrivateGetContextFlag. imc_ctfime==NULL`
- `0x18001ae2e`: `UIComposition::OnPrivateGetContextFlag. _pCicContext==NULL`

## pseudocode

```c

```
