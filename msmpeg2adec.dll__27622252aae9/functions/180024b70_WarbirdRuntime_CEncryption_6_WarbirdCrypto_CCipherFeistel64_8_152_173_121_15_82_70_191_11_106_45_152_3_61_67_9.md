# WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::Encrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7 *)

- ea: `0x180024b70`
- end: `0x180024c00`
- name: `?Encrypt@?$CEncryption@$05V?$CCipherFeistel64@$07$0JI@$0KN@$0HJ@$0P@$0FC@$0EG@$0LP@$0L@$0GK@$0CN@$0JI@$02$0DN@$0ED@$08$0M@$0HL@$0DN@$0GO@$04$0KF@$0PE@$0CJ@$0BM@$0NK@$0CA@$0HN@$0A@$0O@$0EG@$0EI@$0BC@$0JE@$0PJ@$0CA@$08$0IG@$0FF@$0ED@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$01$02$0FLGHJNDFFJOLLCJB@@2@UENCRYPTED_SEGMENT_DATA_CONST_7@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_7@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_7@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_7@2@@Z`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010c10`

## callees

- `0x1800232d0`
- `0x180024b70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024bd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024bd8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024b91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024b91`

## pseudocode

```c
__int64 WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::Encrypt()
{
  int v1; // edx
  unsigned int v2; // ebx

  if ( (WarbirdRuntime::g_EncryptedSegmentConstData_66 & 1) == 0 )
    return 0;
  EnterCriticalSection(&WarbirdRuntime::g_encryptionLock);
  if ( WarbirdRuntime::g_EncryptedSegmentReadWriteData_66 == 1 )
  {
    v2 = WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::DoCrypt(
           1,
           v1,
           1);
    WarbirdRuntime::g_EncryptedSegmentReadWriteData_66 = 0;
  }
  else
  {
    v2 = 0;
    if ( (unsigned int)(WarbirdRuntime::g_EncryptedSegmentReadWriteData_66 - 1) <= 0xFFFFFFFD )
      --WarbirdRuntime::g_EncryptedSegmentReadWriteData_66;
  }
  LeaveCriticalSection(&WarbirdRuntime::g_encryptionLock);
  return v2;
}

```

## disassembly

```asm
0x180024b70  sub     rsp, 28h
0x180024b74  test    byte ptr cs:?g_EncryptedSegmentConstData_66@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_7@1@A, 1; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7 WarbirdRuntime::g_EncryptedSegmentConstData_66
0x180024b7b  jnz     short loc_180024B85
0x180024b7d  xor     eax, eax
0x180024b7f  add     rsp, 28h
0x180024b83  retn
0x180024b85  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x180024b8c  mov     [rsp+28h+var_8], rbx
0x180024b91  call    cs:__imp_EnterCriticalSection
0x180024b98  nop     dword ptr [rax+rax+00h]
0x180024b9d  mov     ecx, cs:?g_EncryptedSegmentReadWriteData_66@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_7@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7 WarbirdRuntime::g_EncryptedSegmentReadWriteData_66
0x180024ba3  cmp     ecx, 1
0x180024ba6  jnz     short loc_180024BBE
0x180024ba8  mov     r8d, ecx
0x180024bab  call    ?DoCrypt@?$CEncryption@$05V?$CCipherFeistel64@$07$0JI@$0KN@$0HJ@$0P@$0FC@$0EG@$0LP@$0L@$0GK@$0CN@$0JI@$02$0DN@$0ED@$08$0M@$0HL@$0DN@$0GO@$04$0KF@$0PE@$0CJ@$0BM@$0NK@$0CA@$0HN@$0A@$0O@$0EG@$0EI@$0BC@$0JE@$0PJ@$0CA@$08$0IG@$0FF@$0ED@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$01$02$0FLGHJNDFFJOLLCJB@@2@UENCRYPTED_SEGMENT_DATA_CONST_7@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_7@5@@WarbirdRuntime@@CAJPEAUENCRYPTED_SEGMENT_DATA_CONST_7@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_7@2@H@Z; WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::DoCrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7 *,int)
0x180024bb0  mov     ebx, eax
0x180024bb2  mov     cs:?g_EncryptedSegmentReadWriteData_66@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_7@1@A, 0; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7 WarbirdRuntime::g_EncryptedSegmentReadWriteData_66
0x180024bbc  jmp     short loc_180024BD1
0x180024bbe  xor     ebx, ebx
0x180024bc0  lea     eax, [rcx-1]
0x180024bc3  cmp     eax, 0FFFFFFFDh
0x180024bc6  ja      short loc_180024BD1
0x180024bc8  lea     eax, [rcx-1]
0x180024bcb  mov     cs:?g_EncryptedSegmentReadWriteData_66@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_7@1@A, eax; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7 WarbirdRuntime::g_EncryptedSegmentReadWriteData_66
0x180024bd1  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x180024bd8  call    cs:__imp_LeaveCriticalSection
0x180024bdf  nop     dword ptr [rax+rax+00h]
0x180024be4  mov     eax, ebx
0x180024be6  mov     rbx, [rsp+28h+var_8]
0x180024beb  add     rsp, 28h
0x180024bef  retn
```
