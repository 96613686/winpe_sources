# McGenEventWrite_EventWriteTransfer

- ea: `0x180010c28`
- end: `0x180010c75`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x18000be0c`
- `0x18000beec`
- `0x180010c7c`
- `0x180010db0`
- `0x180010ea8`
- `0x180011190`
- `0x180011414`
- `0x180011508`
- `0x180011624`
- `0x180011914`
- `0x180011ba0`
- `0x180011c8c`
- `0x18001fac4`
- `0x180036874`

## callees

- `0x180010c28`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180010c6a`
- `ADVAPI32!EventWriteTransfer` at `0x180010c6a`

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
0x180010c28  sub     rsp, 38h
0x180010c2c  mov     r8, [rcx+8]
0x180010c30  mov     rax, [rsp+38h+arg_20]
0x180010c35  test    r8, r8
0x180010c38  jnz     short loc_180010C42
0x180010c3a  mov     [rax], r8
0x180010c3d  xor     r10d, r10d
0x180010c40  jmp     short loc_180010C4F
0x180010c42  mov     [rax], r8
0x180010c45  mov     r10d, 2
0x180010c4b  movzx   r8d, word ptr [r8]
0x180010c4f  mov     [rax+8], r8d
0x180010c53  xor     r8d, r8d; ActivityId
0x180010c56  mov     [rsp+38h+UserData], rax; UserData
0x180010c5b  mov     [rax+0Ch], r10d
0x180010c5f  mov     rcx, [rcx]; RegHandle
0x180010c62  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180010c67  xor     r9d, r9d; RelatedActivityId
0x180010c6a  call    cs:__imp_EventWriteTransfer
0x180010c70  add     rsp, 38h
0x180010c74  retn
```
