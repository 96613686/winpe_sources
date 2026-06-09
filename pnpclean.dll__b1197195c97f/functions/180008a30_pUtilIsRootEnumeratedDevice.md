# pUtilIsRootEnumeratedDevice

- ea: `0x180008a30`
- end: `0x180008ada`
- name: `pUtilIsRootEnumeratedDevice`
- size: `170`
- prototype: `_BOOL8 __fastcall(DEVINST)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004e74`

## callees

- `0x180008a30`
- `0x180008e30`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180008aae`
- `KERNEL32!CompareStringOrdinal` at `0x180008aae`
- `CFGMGR32!CM_Get_DevNode_PropertyW` at `0x180008a7c`
- `CFGMGR32!CM_Get_DevNode_PropertyW` at `0x180008a7c`

## pseudocode

```c
_BOOL8 __fastcall pUtilIsRootEnumeratedDevice(DEVINST a1)
{
  DEVPROPTYPE PropertyType; // [rsp+30h] [rbp-1B8h] BYREF
  ULONG PropertyBufferSize[3]; // [rsp+34h] [rbp-1B4h] BYREF
  WCHAR PropertyBuffer[200]; // [rsp+40h] [rbp-1A8h] BYREF

  PropertyType = 0;
  PropertyBufferSize[0] = 400;
  return !CM_Get_DevNode_PropertyW(
            a1,
            &DEVPKEY_Device_EnumeratorName,
            &PropertyType,
            (PBYTE)PropertyBuffer,
            PropertyBufferSize,
            0)
      && PropertyType == 18
      && PropertyBufferSize[0] >= 2
      && CompareStringOrdinal(PropertyBuffer, -1, L"Root", -1, 1) == 2;
}

```

## disassembly

```asm
0x180008a30  sub     rsp, 1E8h
0x180008a37  mov     rax, cs:__security_cookie
0x180008a3e  xor     rax, rsp
0x180008a41  mov     [rsp+1E8h+var_18], rax
0x180008a49  lea     rax, [rsp+1E8h+var_1B4]
0x180008a4e  mov     [rsp+1E8h+ulFlags], 0; ulFlags
0x180008a56  lea     r9, [rsp+1E8h+PropertyBuffer]; PropertyBuffer
0x180008a5b  mov     [rsp+1E8h+PropertyBufferSize], rax; PropertyBufferSize
0x180008a60  lea     r8, [rsp+1E8h+PropertyType]; PropertyType
0x180008a65  mov     [rsp+1E8h+PropertyType], 0
0x180008a6d  lea     rdx, DEVPKEY_Device_EnumeratorName; PropertyKey
0x180008a74  mov     [rsp+1E8h+var_1B4], 190h
0x180008a7c  call    cs:__imp_CM_Get_DevNode_PropertyW
0x180008a82  test    eax, eax
0x180008a84  jnz     short loc_180008AC0
0x180008a86  cmp     [rsp+1E8h+PropertyType], 12h
0x180008a8b  jnz     short loc_180008AC0
0x180008a8d  cmp     [rsp+1E8h+var_1B4], 2
0x180008a92  jb      short loc_180008AC0
0x180008a94  or      edx, 0FFFFFFFFh; cchCount1
0x180008a97  mov     dword ptr [rsp+1E8h+PropertyBufferSize], 1; bIgnoreCase
0x180008a9f  mov     r9d, edx; cchCount2
0x180008aa2  lea     r8, aRoot; "Root"
0x180008aa9  lea     rcx, [rsp+1E8h+PropertyBuffer]; lpString1
0x180008aae  call    cs:__imp_CompareStringOrdinal
0x180008ab4  xor     ecx, ecx
0x180008ab6  cmp     eax, 2
0x180008ab9  setz    cl
0x180008abc  mov     eax, ecx
0x180008abe  jmp     short loc_180008AC2
0x180008ac0  xor     eax, eax
0x180008ac2  mov     rcx, [rsp+1E8h+var_18]
0x180008aca  xor     rcx, rsp; StackCookie
0x180008acd  call    __security_check_cookie
0x180008ad2  add     rsp, 1E8h
0x180008ad9  retn
```
