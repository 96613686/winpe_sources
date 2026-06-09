# McGenEventWrite_EventWriteTransfer

- ea: `0x1400055c8`
- end: `0x140005621`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400014e4`

## callees

- `0x1400055c8`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!EventWriteTransfer` at `0x140005616`
- `api-ms-win-downlevel-advapi32-l1-1-0!EventWriteTransfer` at `0x140005616`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // edx

  v5 = (unsigned __int16 *)qword_14000A048;
  if ( qword_14000A048 )
  {
    UserData->Ptr = qword_14000A048;
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
  return EventWriteTransfer(BERP_IEFRAME2_Context, &WINMAIN_INFO, 0, 0, 1u, UserData);
}

```

## disassembly

```asm
0x1400055c8  sub     rsp, 38h
0x1400055cc  mov     rcx, cs:qword_14000A048
0x1400055d3  mov     rax, [rsp+38h+arg_20]
0x1400055d8  test    rcx, rcx
0x1400055db  jnz     short loc_1400055E4
0x1400055dd  mov     [rax], rcx
0x1400055e0  xor     edx, edx
0x1400055e2  jmp     short loc_1400055EF
0x1400055e4  mov     [rax], rcx
0x1400055e7  mov     edx, 2
0x1400055ec  movzx   ecx, word ptr [rcx]
0x1400055ef  mov     [rax+8], ecx
0x1400055f2  xor     r9d, r9d; RelatedActivityId
0x1400055f5  mov     [rax+0Ch], edx
0x1400055f8  xor     r8d, r8d; ActivityId
0x1400055fb  mov     rcx, cs:BERP_IEFRAME2_Context; RegHandle
0x140005602  lea     rdx, WINMAIN_INFO; EventDescriptor
0x140005609  mov     [rsp+38h+UserData], rax; UserData
0x14000560e  mov     [rsp+38h+UserDataCount], 1; UserDataCount
0x140005616  call    cs:__imp_EventWriteTransfer
0x14000561c  add     rsp, 38h
0x140005620  retn
```
