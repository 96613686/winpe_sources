# WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Decrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3 *)

- ea: `0x1800205b0`
- end: `0x180020640`
- name: `?Decrypt@?$CEncryption@$01V?$CCipherFeistel64@$0A@$0GD@$0FH@$0OH@$0BF@$0LC@$0LB@$0BN@$0N@$0DK@$0FJ@$0ID@$0BB@$0LD@$0OK@$0FA@$0BD@$0LL@$0MF@$0MH@$02$0EA@$0JO@$01$01$0PL@$0GM@$0KE@$0P@$0LK@$0EI@$0NL@$0BC@$09$0CK@$0LM@$0BO@$0GO@$0HK@$0DC@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$00$0BKGBKNDEJDGFEBEE@@2@UENCRYPTED_SEGMENT_DATA_CONST_3@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_3@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_3@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_3@2@@Z`
- size: `144`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a140`
- `0x18000de70`
- `0x180015a40`

## callees

- `0x1800205b0`
- `0x180022820`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020617`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020617`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800205d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800205d1`

## pseudocode

```c
__int64 WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Decrypt()
{
  return 0;
}

```

## disassembly

```asm
0x1800205b0  sub     rsp, 28h
0x1800205b4  test    byte ptr cs:qword_1800A4800, 1
0x1800205bb  jnz     short loc_1800205C5
0x1800205bd  xor     eax, eax
0x1800205bf  add     rsp, 28h
0x1800205c3  retn
0x1800205c5  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x1800205cc  mov     [rsp+28h+var_8], rbx
0x1800205d1  call    cs:__imp_EnterCriticalSection
0x1800205d8  nop     dword ptr [rax+rax+00h]
0x1800205dd  mov     eax, cs:?g_EncryptedSegmentReadWriteData_14@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_3@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3 WarbirdRuntime::g_EncryptedSegmentReadWriteData_14
0x1800205e3  test    eax, eax
0x1800205e5  jnz     short loc_180020601
0x1800205e7  xor     r8d, r8d
0x1800205ea  call    ?DoCrypt@?$CEncryption@$01V?$CCipherFeistel64@$0A@$0GD@$0FH@$0OH@$0BF@$0LC@$0LB@$0BN@$0N@$0DK@$0FJ@$0ID@$0BB@$0LD@$0OK@$0FA@$0BD@$0LL@$0MF@$0MH@$02$0EA@$0JO@$01$01$0PL@$0GM@$0KE@$0P@$0LK@$0EI@$0NL@$0BC@$09$0CK@$0LM@$0BO@$0GO@$0HK@$0DC@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$00$0BKGBKNDEJDGFEBEE@@2@UENCRYPTED_SEGMENT_DATA_CONST_3@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_3@5@@WarbirdRuntime@@CAJPEAUENCRYPTED_SEGMENT_DATA_CONST_3@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_3@2@H@Z; WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::DoCrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3 *,int)
0x1800205ef  mov     ebx, eax
0x1800205f1  test    eax, eax
0x1800205f3  js      short loc_180020610
0x1800205f5  mov     cs:?g_EncryptedSegmentReadWriteData_14@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_3@1@A, 1; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3 WarbirdRuntime::g_EncryptedSegmentReadWriteData_14
0x1800205ff  jmp     short loc_180020610
0x180020601  xor     ebx, ebx
0x180020603  cmp     eax, 0FFFFFFFFh
0x180020606  jz      short loc_180020610
0x180020608  inc     eax
0x18002060a  mov     cs:?g_EncryptedSegmentReadWriteData_14@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_3@1@A, eax; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3 WarbirdRuntime::g_EncryptedSegmentReadWriteData_14
0x180020610  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x180020617  call    cs:__imp_LeaveCriticalSection
0x18002061e  nop     dword ptr [rax+rax+00h]
0x180020623  mov     eax, ebx
0x180020625  mov     rbx, [rsp+28h+var_8]
0x18002062a  add     rsp, 28h
0x18002062e  retn
```
