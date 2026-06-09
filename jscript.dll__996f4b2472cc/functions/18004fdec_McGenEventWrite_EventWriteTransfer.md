# McGenEventWrite_EventWriteTransfer

- ea: `0x18004fdec`
- end: `0x18004fe48`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `92`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18004fd84`

## callees

- `0x18004fdec`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x18004fe36`
- `ADVAPI32!EventWriteTransfer` at `0x18004fe36`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // r8d

  v5 = (unsigned __int16 *)qword_1800B3F28;
  if ( qword_1800B3F28 )
  {
    UserData->Ptr = qword_1800B3F28;
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
  return EventWriteTransfer(BERP_IE_Context, a2, 0, 0, 3u, UserData);
}

```

## disassembly

```asm
0x18004fdec  sub     rsp, 38h
0x18004fdf0  mov     rcx, cs:qword_1800B3F28
0x18004fdf7  mov     rax, [rsp+38h+arg_20]
0x18004fdfc  test    rcx, rcx
0x18004fdff  jnz     short loc_18004FE09
0x18004fe01  mov     [rax], rcx
0x18004fe04  xor     r8d, r8d
0x18004fe07  jmp     short loc_18004FE15
0x18004fe09  mov     [rax], rcx
0x18004fe0c  mov     r8d, 2
0x18004fe12  movzx   ecx, word ptr [rcx]
0x18004fe15  mov     [rax+8], ecx
0x18004fe18  xor     r9d, r9d; RelatedActivityId
0x18004fe1b  mov     [rax+0Ch], r8d
0x18004fe1f  xor     r8d, r8d; ActivityId
0x18004fe22  mov     rcx, cs:BERP_IE_Context; RegHandle
0x18004fe29  mov     [rsp+38h+UserData], rax; UserData
0x18004fe2e  mov     [rsp+38h+UserDataCount], 3; UserDataCount
0x18004fe36  call    cs:__imp_EventWriteTransfer
0x18004fe3d  nop     dword ptr [rax+rax+00h]
0x18004fe42  add     rsp, 38h
0x18004fe46  retn
```
