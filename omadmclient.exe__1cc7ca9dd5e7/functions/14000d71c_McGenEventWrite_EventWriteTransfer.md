# McGenEventWrite_EventWriteTransfer

- ea: `0x14000d71c`
- end: `0x14000d770`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `84`
- prototype: ``
- caller_count: `132`
- callee_count: `1`
- tags: ``

## callers

- `0x140007930`
- `0x14000aab0`
- `0x14000bae4`
- `0x14000d778`
- `0x14000d860`
- `0x14000eb54`
- `0x14000ec44`
- `0x14000f29c`
- `0x14000f358`
- `0x14000f47c`
- `0x14000f590`
- `0x14000f6e0`
- `0x14000f8b0`
- `0x14000ff64`
- `0x14001021c`
- `0x1400103bc`
- `0x1400104ac`
- `0x1400105ec`
- `0x140010784`
- `0x1400109dc`
- `0x140010acc`
- `0x14001125c`
- `0x140011380`
- `0x140011404`
- `0x1400114a8`
- `0x140011554`
- `0x140011678`
- `0x14001173c`
- `0x140011818`
- `0x14001194c`
- `0x1400134a4`
- `0x140013674`
- `0x140015868`
- `0x140015d88`
- `0x140016718`
- `0x140016c40`
- `0x140016dec`
- `0x140018550`
- `0x1400189a0`
- `0x140018f30`
- `0x14001fe18`
- `0x140020340`
- `0x140020870`
- `0x140020f04`
- `0x1400211e0`
- `0x1400215c0`
- `0x1400217e0`
- `0x140021a20`
- `0x140022060`
- `0x1400223f0`

## callees

- `0x14000d71c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000d75e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000d75e`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r8
  int v6; // r10d

  v5 = (unsigned __int16 *)a1[1];
  if ( v5 )
  {
    UserData->Ptr = (ULONGLONG)v5;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v6 = 0;
  }
  UserData->Size = (unsigned int)v5;
  UserData->Reserved = v6;
  return EventWriteTransfer(*a1, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x14000d71c  sub     rsp, 38h
0x14000d720  mov     r8, [rcx+8]
0x14000d724  mov     rax, [rsp+38h+arg_20]
0x14000d729  test    r8, r8
0x14000d72c  jnz     short loc_14000D736
0x14000d72e  mov     [rax], r8
0x14000d731  xor     r10d, r10d
0x14000d734  jmp     short loc_14000D743
0x14000d736  mov     [rax], r8
0x14000d739  mov     r10d, 2
0x14000d73f  movzx   r8d, word ptr [r8]
0x14000d743  mov     [rax+8], r8d
0x14000d747  xor     r8d, r8d; ActivityId
0x14000d74a  mov     [rsp+38h+UserData], rax; UserData
0x14000d74f  mov     [rax+0Ch], r10d
0x14000d753  mov     rcx, [rcx]; RegHandle
0x14000d756  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14000d75b  xor     r9d, r9d; RelatedActivityId
0x14000d75e  call    cs:__imp_EventWriteTransfer
0x14000d765  nop     dword ptr [rax+rax+00h]
0x14000d76a  add     rsp, 38h
0x14000d76e  retn
```
