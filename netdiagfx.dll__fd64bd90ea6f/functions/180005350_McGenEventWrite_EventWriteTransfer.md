# McGenEventWrite_EventWriteTransfer

- ea: `0x180005350`
- end: `0x1800053a2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180004940`
- `0x180008970`
- `0x180008f50`
- `0x18000a3e8`
- `0x18000e034`
- `0x18000f4dc`
- `0x1800103e0`

## callees

- `0x180005350`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180005397`
- `ADVAPI32!EventWriteTransfer` at `0x180005397`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_180041008;
  if ( qword_180041008 )
  {
    UserData->Ptr = qword_180041008;
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
  return EventWriteTransfer(NETDIAG_EVT_GUID_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180005350  sub     rsp, 38h
0x180005354  mov     rcx, cs:qword_180041008
0x18000535b  mov     rax, [rsp+38h+arg_20]
0x180005360  test    rcx, rcx
0x180005363  jnz     short loc_18000536D
0x180005365  mov     [rax], rcx
0x180005368  xor     r8d, r8d
0x18000536b  jmp     short loc_180005379
0x18000536d  mov     [rax], rcx
0x180005370  mov     r8d, 2
0x180005376  movzx   ecx, word ptr [rcx]
0x180005379  mov     [rax+8], ecx
0x18000537c  mov     [rax+0Ch], r8d
0x180005380  xor     r8d, r8d; ActivityId
0x180005383  mov     rcx, cs:NETDIAG_EVT_GUID_Context; RegHandle
0x18000538a  mov     [rsp+38h+UserData], rax; UserData
0x18000538f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180005394  xor     r9d, r9d; RelatedActivityId
0x180005397  call    cs:__imp_EventWriteTransfer
0x18000539d  add     rsp, 38h
0x1800053a1  retn
```
