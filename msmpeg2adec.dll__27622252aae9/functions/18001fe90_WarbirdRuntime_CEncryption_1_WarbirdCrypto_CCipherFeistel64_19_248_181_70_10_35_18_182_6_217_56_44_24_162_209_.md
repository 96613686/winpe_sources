# WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::Decrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2 *)

- ea: `0x18001fe90`
- end: `0x18001ff20`
- name: `?Decrypt@?$CEncryption@$00V?$CCipherFeistel64@$0BD@$0PI@$0LF@$0EG@$09$0CD@$0BC@$0LG@$05$0NJ@$0DI@$0CM@$0BI@$0KC@$0NB@$0JF@$0BA@$0NF@$0NO@$0LH@$0BE@$0CD@$0DD@$0CI@$0BN@$0IL@$0HD@$0NF@$0M@$0OE@$0BK@$0PN@$03$0FI@$0HI@$0DF@$0BF@$0OF@$0CP@$0OD@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$0A@$0ENFLKLIPNEIOMFLN@@2@UENCRYPTED_SEGMENT_DATA_CONST_2@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_2@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_2@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_2@2@@Z`
- size: `144`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b900`
- `0x18001e410`

## callees

- `0x18001fe90`
- `0x180022470`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fef7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fef7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001feb1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001feb1`

## pseudocode

```c
__int64 WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::Decrypt()
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  int v3; // ebx

  if ( !WarbirdRuntime::g_EncryptedSegmentConstData_4 )
    return 0;
  EnterCriticalSection(&WarbirdRuntime::g_encryptionLock);
  if ( WarbirdRuntime::g_EncryptedSegmentReadWriteData_4 )
  {
    v3 = 0;
    if ( WarbirdRuntime::g_EncryptedSegmentReadWriteData_4 != -1 )
      ++WarbirdRuntime::g_EncryptedSegmentReadWriteData_4;
  }
  else
  {
    v3 = WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::DoCrypt(
           v2,
           v1,
           0);
    if ( v3 >= 0 )
      WarbirdRuntime::g_EncryptedSegmentReadWriteData_4 = 1;
  }
  LeaveCriticalSection(&WarbirdRuntime::g_encryptionLock);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001fe90  sub     rsp, 28h
0x18001fe94  test    byte ptr cs:?g_EncryptedSegmentConstData_4@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_CONST_2@1@A, 1; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2 WarbirdRuntime::g_EncryptedSegmentConstData_4
0x18001fe9b  jnz     short loc_18001FEA5
0x18001fe9d  xor     eax, eax
0x18001fe9f  add     rsp, 28h
0x18001fea3  retn
0x18001fea5  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x18001feac  mov     [rsp+28h+var_8], rbx
0x18001feb1  call    cs:__imp_EnterCriticalSection
0x18001feb8  nop     dword ptr [rax+rax+00h]
0x18001febd  mov     eax, cs:?g_EncryptedSegmentReadWriteData_4@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_2@1@A; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2 WarbirdRuntime::g_EncryptedSegmentReadWriteData_4
0x18001fec3  test    eax, eax
0x18001fec5  jnz     short loc_18001FEE1
0x18001fec7  xor     r8d, r8d
0x18001feca  call    ?DoCrypt@?$CEncryption@$00V?$CCipherFeistel64@$0BD@$0PI@$0LF@$0EG@$09$0CD@$0BC@$0LG@$05$0NJ@$0DI@$0CM@$0BI@$0KC@$0NB@$0JF@$0BA@$0NF@$0NO@$0LH@$0BE@$0CD@$0DD@$0CI@$0BN@$0IL@$0HD@$0NF@$0M@$0OE@$0BK@$0PN@$03$0FI@$0HI@$0DF@$0BF@$0OF@$0CP@$0OD@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$0A@$0ENFLKLIPNEIOMFLN@@2@UENCRYPTED_SEGMENT_DATA_CONST_2@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_2@5@@WarbirdRuntime@@CAJPEAUENCRYPTED_SEGMENT_DATA_CONST_2@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_2@2@H@Z; WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::DoCrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2 *,int)
0x18001fecf  mov     ebx, eax
0x18001fed1  test    eax, eax
0x18001fed3  js      short loc_18001FEF0
0x18001fed5  mov     cs:?g_EncryptedSegmentReadWriteData_4@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_2@1@A, 1; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2 WarbirdRuntime::g_EncryptedSegmentReadWriteData_4
0x18001fedf  jmp     short loc_18001FEF0
0x18001fee1  xor     ebx, ebx
0x18001fee3  cmp     eax, 0FFFFFFFFh
0x18001fee6  jz      short loc_18001FEF0
0x18001fee8  inc     eax
0x18001feea  mov     cs:?g_EncryptedSegmentReadWriteData_4@WarbirdRuntime@@3UENCRYPTED_SEGMENT_DATA_READ_WRITE_2@1@A, eax; WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2 WarbirdRuntime::g_EncryptedSegmentReadWriteData_4
0x18001fef0  lea     rcx, ?g_encryptionLock@WarbirdRuntime@@3VCLock@1@A; lpCriticalSection
0x18001fef7  call    cs:__imp_LeaveCriticalSection
0x18001fefe  nop     dword ptr [rax+rax+00h]
0x18001ff03  mov     eax, ebx
0x18001ff05  mov     rbx, [rsp+28h+var_8]
0x18001ff0a  add     rsp, 28h
0x18001ff0e  retn
```
