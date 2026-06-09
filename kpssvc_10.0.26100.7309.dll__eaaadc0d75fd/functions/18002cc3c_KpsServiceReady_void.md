# KpsServiceReady(void)

- ea: `0x18002cc3c`
- end: `0x18002ccbb`
- name: `?KpsServiceReady@@YAEXZ`
- size: `127`
- prototype: `unsigned __int8(void)`
- caller_count: `11`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001e728`
- `0x18001e8e8`
- `0x18001eb40`
- `0x18001edec`
- `0x18001f048`
- `0x18001f390`
- `0x18001f5ec`
- `0x18001fd08`
- `0x180020038`
- `0x180020750`
- `0x1800225d0`

## callees

- `0x18001ae7c`
- `0x18002cc3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002cc4b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002cc4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc83`

## pseudocode

```c
unsigned __int8 KpsServiceReady(void)
{
  DWORD v0; // ebx
  DWORD LastError; // eax

  v0 = WaitForSingleObject(hEvent, 0);
  if ( !v0 )
    return 1;
  if ( v0 != 258
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, v0, LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x18002cc3c  push    rbx
0x18002cc3e  sub     rsp, 30h
0x18002cc42  mov     rcx, cs:hEvent; hHandle
0x18002cc49  xor     edx, edx; dwMilliseconds
0x18002cc4b  call    cs:__imp_WaitForSingleObject
0x18002cc52  nop     dword ptr [rax+rax+00h]
0x18002cc57  mov     ebx, eax
0x18002cc59  test    eax, eax
0x18002cc5b  jnz     short loc_18002CC61
0x18002cc5d  mov     al, 1
0x18002cc5f  jmp     short loc_18002CCB4
0x18002cc61  cmp     ebx, 102h
0x18002cc67  jz      short loc_18002CCB2
0x18002cc69  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc70  lea     rax, WPP_GLOBAL_Control
0x18002cc77  cmp     rcx, rax
0x18002cc7a  jz      short loc_18002CCB2
0x18002cc7c  mov     al, 1
0x18002cc7e  test    [rcx+1Ch], al
0x18002cc81  jz      short loc_18002CCB2
0x18002cc83  call    cs:__imp_GetLastError
0x18002cc8a  nop     dword ptr [rax+rax+00h]
0x18002cc8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc96  lea     r8, WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids
0x18002cc9d  mov     edx, 0Eh
0x18002cca2  mov     [rsp+38h+var_18], eax
0x18002cca6  mov     r9d, ebx
0x18002cca9  mov     rcx, [rcx+10h]
0x18002ccad  call    WPP_SF_dD
0x18002ccb2  xor     al, al
0x18002ccb4  add     rsp, 30h
0x18002ccb8  pop     rbx
0x18002ccb9  retn
```
