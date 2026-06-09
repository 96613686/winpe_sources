# McGenEventWrite_EventWriteTransfer

- ea: `0x180066760`
- end: `0x1800667ad`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x18002a38c`
- `0x18002d730`
- `0x180060b40`
- `0x1800667b4`
- `0x18006682c`
- `0x18006689c`
- `0x180066948`
- `0x1800669a4`
- `0x180066a14`
- `0x18007239c`
- `0x1800724b0`
- `0x180072564`
- `0x180072738`
- `0x1800727dc`
- `0x180072958`
- `0x1800c9fcc`

## callees

- `0x180066760`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800667a2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800667a2`

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
0x180066760  sub     rsp, 38h
0x180066764  mov     r8, [rcx+8]
0x180066768  mov     rax, [rsp+38h+arg_20]
0x18006676d  test    r8, r8
0x180066770  jnz     short loc_18006677A
0x180066772  mov     [rax], r8
0x180066775  xor     r10d, r10d
0x180066778  jmp     short loc_180066787
0x18006677a  mov     [rax], r8
0x18006677d  mov     r10d, 2
0x180066783  movzx   r8d, word ptr [r8]
0x180066787  mov     [rax+8], r8d
0x18006678b  xor     r8d, r8d; ActivityId
0x18006678e  mov     [rsp+38h+UserData], rax; UserData
0x180066793  mov     [rax+0Ch], r10d
0x180066797  mov     rcx, [rcx]; RegHandle
0x18006679a  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18006679f  xor     r9d, r9d; RelatedActivityId
0x1800667a2  call    cs:__imp_EventWriteTransfer
0x1800667a8  add     rsp, 38h
0x1800667ac  retn
```
