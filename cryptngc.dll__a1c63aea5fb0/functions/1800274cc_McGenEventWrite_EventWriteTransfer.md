# McGenEventWrite_EventWriteTransfer

- ea: `0x1800274cc`
- end: `0x180027519`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `47`
- callee_count: `1`
- tags: ``

## callers

- `0x180006980`
- `0x180009050`
- `0x180009a70`
- `0x18000d770`
- `0x18000dde0`
- `0x18000e298`
- `0x18000e5d4`
- `0x180010a60`
- `0x180010dd0`
- `0x180015b10`
- `0x180015d54`
- `0x1800186b0`
- `0x180018720`
- `0x18001b65c`
- `0x1800255d0`
- `0x180025640`
- `0x1800256b0`
- `0x180025720`
- `0x180026a20`
- `0x180026a90`
- `0x180026b00`
- `0x180026b70`
- `0x180026be0`
- `0x180026c50`
- `0x180026cf0`
- `0x180026d60`
- `0x180026dd0`
- `0x180026e40`
- `0x180026eb0`
- `0x180026f20`
- `0x180026ff0`
- `0x180027060`
- `0x180027130`
- `0x1800271a0`
- `0x180027210`
- `0x1800272d4`
- `0x180027394`
- `0x180027520`
- `0x180027600`
- `0x180027670`
- `0x18002d5c8`
- `0x180035e28`
- `0x180036b60`
- `0x180037b40`
- `0x18003ee60`
- `0x180044ad4`
- `0x180044bbc`

## callees

- `0x1800274cc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002750e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002750e`

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
0x1800274cc  sub     rsp, 38h
0x1800274d0  mov     r8, [rcx+8]
0x1800274d4  mov     rax, [rsp+38h+arg_20]
0x1800274d9  test    r8, r8
0x1800274dc  jnz     short loc_1800274E6
0x1800274de  mov     [rax], r8
0x1800274e1  xor     r10d, r10d
0x1800274e4  jmp     short loc_1800274F3
0x1800274e6  mov     [rax], r8
0x1800274e9  mov     r10d, 2
0x1800274ef  movzx   r8d, word ptr [r8]
0x1800274f3  mov     [rax+8], r8d
0x1800274f7  xor     r8d, r8d; ActivityId
0x1800274fa  mov     [rsp+38h+UserData], rax; UserData
0x1800274ff  mov     [rax+0Ch], r10d
0x180027503  mov     rcx, [rcx]; RegHandle
0x180027506  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18002750b  xor     r9d, r9d; RelatedActivityId
0x18002750e  call    cs:__imp_EventWriteTransfer
0x180027514  add     rsp, 38h
0x180027518  retn
```
