# WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::Decrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7 *)

- ea: `0x180021a20`
- end: `0x180021aa0`
- name: `?Decrypt@?$CEncryption@$05V?$CCipherFeistel64@$07$0JI@$0KN@$0HJ@$0P@$0FC@$0EG@$0LP@$0L@$0GK@$0CN@$0JI@$02$0DN@$0ED@$08$0M@$0HL@$0DN@$0GO@$04$0KF@$0PE@$0CJ@$0BM@$0NK@$0CA@$0HN@$0A@$0O@$0EG@$0EI@$0BC@$0JE@$0PJ@$0CA@$08$0IG@$0FF@$0ED@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$01$02$0FLGHJNDFFJOLLCJB@@2@UENCRYPTED_SEGMENT_DATA_CONST_7@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_7@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_7@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_7@2@@Z`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010c10`

## callees

- `0x180021a20`
- `0x1800232d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021a87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021a87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021a41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021a41`

## pseudocode

```c
__int64 WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::Decrypt()
{
  int v1; // edx
  __int64 v2; // rcx
  int v3; // ebx

  if ( (WarbirdRuntime::g_EncryptedSegmentConstData_66 & 1) == 0 )
    return 0;
  EnterCriticalSection(&WarbirdRuntime::g_encryptionLock);
  if ( WarbirdRuntime::g_EncryptedSegmentReadWriteData_66 )
  {
    v3 = 0;
    if ( WarbirdRuntime::g_EncryptedSegmentReadWriteData_66 != -1 )
      ++WarbirdRuntime::g_EncryptedSegmentReadWriteData_66;
  }
  else
  {
    v3 = WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::DoCrypt(
           v2,
           v1,
           0);
    if ( v3 >= 0 )
      WarbirdRuntime::g_EncryptedSegmentReadWriteData_66 = 1;
  }
  LeaveCriticalSection(&WarbirdRuntime::g_encryptionLock);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180021a20  sub     rsp, 28h
0x180021a24  test    byte ptr cs:?g_EncryptedSegmentConstData_66@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_7@1@A, 1; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7 WarbirdRuntime::g_EncryptedSegmentConstData_66
0x180021a2b  jnz     short loc_180021A35
0x180021a2d  xor     eax, eax
0x180021a2f  add     rsp, 28h
0x180021a33  retn
0x180021a35  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x180021a3c  mov     [rsp+28h+var_8], rbx
0x180021a41  call    cs:__imp_EnterCriticalSection
0x180021a48  nop     dword ptr [rax+rax+00h]
0x180021a4d  mov     eax, cs:?g_EncryptedSegmentReadWriteData_66@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_7@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7 WarbirdRuntime::g_EncryptedSegmentReadWriteData_66
0x180021a53  test    eax, eax
0x180021a55  jnz     short loc_180021A71
0x180021a57  xor     r8d, r8d
0x180021a5a  call    ?DoCrypt@?$CEncryption@$05V?$CCipherFeistel64@$07$0JI@$0KN@$0HJ@$0P@$0FC@$0EG@$0LP@$0L@$0GK@$0CN@$0JI@$02$0DN@$0ED@$08$0M@$0HL@$0DN@$0GO@$04$0KF@$0PE@$0CJ@$0BM@$0NK@$0CA@$0HN@$0A@$0O@$0EG@$0EI@$0BC@$0JE@$0PJ@$0CA@$08$0IG@$0FF@$0ED@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$01$02$0FLGHJNDFFJOLLCJB@@2@UENCRYPTED_SEGMENT_DATA_CONST_7@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_7@5@@WarbirdRuntime@@CAJPEAUENCRYPTED_SEGMENT_DATA_CONST_7@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_7@2@H@Z; WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::DoCrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7 *,int)
0x180021a5f  mov     ebx, eax
0x180021a61  test    eax, eax
0x180021a63  js      short loc_180021A80
0x180021a65  mov     cs:?g_EncryptedSegmentReadWriteData_66@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_7@1@A, 1; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7 WarbirdRuntime::g_EncryptedSegmentReadWriteData_66
0x180021a6f  jmp     short loc_180021A80
0x180021a71  xor     ebx, ebx
0x180021a73  cmp     eax, 0FFFFFFFFh
0x180021a76  jz      short loc_180021A80
0x180021a78  inc     eax
0x180021a7a  mov     cs:?g_EncryptedSegmentReadWriteData_66@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_7@1@A, eax; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7 WarbirdRuntime::g_EncryptedSegmentReadWriteData_66
0x180021a80  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x180021a87  call    cs:__imp_LeaveCriticalSection
0x180021a8e  nop     dword ptr [rax+rax+00h]
0x180021a93  mov     eax, ebx
0x180021a95  mov     rbx, [rsp+28h+var_8]
0x180021a9a  add     rsp, 28h
0x180021a9e  retn
```
