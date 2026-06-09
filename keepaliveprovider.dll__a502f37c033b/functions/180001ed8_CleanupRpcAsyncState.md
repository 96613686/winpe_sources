# CleanupRpcAsyncState

- ea: `0x180001ed8`
- end: `0x180001f5b`
- name: `CleanupRpcAsyncState`
- size: `131`
- prototype: `int __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002110`
- `0x1800030a4`

## callees

- `0x180001e20`
- `0x180001ed8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001f1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001f1d`

## pseudocode

```c
int __fastcall CleanupRpcAsyncState(__int64 a1)
{
  int result; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids);
  }
  result = CloseHandle(*(HANDLE *)(a1 + 48));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180001ed8  mov     [rsp+arg_0], rbx
0x180001edd  push    rdi
0x180001ede  sub     rsp, 20h
0x180001ee2  mov     rbx, rcx
0x180001ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x180001eec  lea     rdi, WPP_GLOBAL_Control
0x180001ef3  cmp     rcx, rdi
0x180001ef6  jz      short loc_180001F19
0x180001ef8  test    byte ptr [rcx+1Ch], 1
0x180001efc  jz      short loc_180001F19
0x180001efe  cmp     byte ptr [rcx+19h], 6
0x180001f02  jb      short loc_180001F19
0x180001f04  mov     rcx, [rcx+10h]
0x180001f08  lea     r8, WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids
0x180001f0f  mov     edx, 33h ; '3'
0x180001f14  call    WPP_SF_
0x180001f19  mov     rcx, [rbx+30h]; hObject
0x180001f1d  call    cs:__imp_CloseHandle
0x180001f23  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f2a  cmp     rcx, rdi
0x180001f2d  jz      short loc_180001F50
0x180001f2f  test    byte ptr [rcx+1Ch], 1
0x180001f33  jz      short loc_180001F50
0x180001f35  cmp     byte ptr [rcx+19h], 6
0x180001f39  jb      short loc_180001F50
0x180001f3b  mov     rcx, [rcx+10h]
0x180001f3f  lea     r8, WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids
0x180001f46  mov     edx, 34h ; '4'
0x180001f4b  call    WPP_SF_
0x180001f50  mov     rbx, [rsp+28h+arg_0]
0x180001f55  add     rsp, 20h
0x180001f59  pop     rdi
0x180001f5a  retn
```
