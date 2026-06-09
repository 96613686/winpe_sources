# RemoveDosDevice

- ea: `0x1800089d4`
- end: `0x180008a99`
- name: `RemoveDosDevice`
- size: `197`
- prototype: `__int64 __fastcall(LPCWSTR lpDeviceName, LPCWSTR lpTargetPath)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180004720`
- `0x180005850`

## callees

- `0x1800023f0`
- `0x180002418`
- `0x1800089d4`
- `0x180008b00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008a43`
- `KERNEL32!GetLastError` at `0x180008a43`
- `KERNEL32!DefineDosDeviceW` at `0x180008a23`
- `KERNEL32!DefineDosDeviceW` at `0x180008a23`

## pseudocode

```c
int __fastcall RemoveDosDevice(LPCWSTR lpDeviceName, LPCWSTR lpTargetPath, int a3)
{
  int result; // eax
  __int64 v6; // rbx
  DWORD LastError; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, a3, (_DWORD)lpDeviceName, (__int64)lpTargetPath);
  result = DefineDosDeviceW(0xFu, lpDeviceName, lpTargetPath);
  if ( result )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v6 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    LastError = GetLastError();
    return WPP_SF_d(v6, 125, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, LastError);
  }
  return result;
}

```

## disassembly

```asm
0x1800089d4  mov     [rsp+arg_0], rbx
0x1800089d9  mov     [rsp+arg_8], rsi
0x1800089de  push    rdi
0x1800089df  sub     rsp, 30h
0x1800089e3  mov     rbx, rdx
0x1800089e6  mov     rdi, rcx
0x1800089e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089f0  lea     rsi, WPP_GLOBAL_Control
0x1800089f7  cmp     rcx, rsi
0x1800089fa  jz      short loc_180008A18
0x1800089fc  test    byte ptr [rcx+1Ch], 1
0x180008a00  jz      short loc_180008A18
0x180008a02  mov     rcx, [rcx+10h]
0x180008a06  mov     edx, 7Ch ; '|'
0x180008a0b  mov     r9, rdi
0x180008a0e  mov     [rsp+38h+var_18], rbx
0x180008a13  call    WPP_SF_SS
0x180008a18  mov     r8, rbx; lpTargetPath
0x180008a1b  mov     rdx, rdi; lpDeviceName
0x180008a1e  mov     ecx, 0Fh; dwFlags
0x180008a23  call    cs:__imp_DefineDosDeviceW
0x180008a29  test    eax, eax
0x180008a2b  jnz     short loc_180008A62
0x180008a2d  mov     rbx, cs:WPP_GLOBAL_Control
0x180008a34  cmp     rbx, rsi
0x180008a37  jz      short loc_180008A89
0x180008a39  test    byte ptr [rbx+1Ch], 2
0x180008a3d  jz      short loc_180008A89
0x180008a3f  mov     rbx, [rbx+10h]
0x180008a43  call    cs:__imp_GetLastError
0x180008a49  mov     edx, 7Dh ; '}'
0x180008a4e  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180008a55  mov     r9d, eax
0x180008a58  mov     rcx, rbx
0x180008a5b  call    WPP_SF_d
0x180008a60  jmp     short loc_180008A89
0x180008a62  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a69  cmp     rcx, rsi
0x180008a6c  jz      short loc_180008A89
0x180008a6e  test    byte ptr [rcx+1Ch], 1
0x180008a72  jz      short loc_180008A89
0x180008a74  mov     rcx, [rcx+10h]
0x180008a78  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180008a7f  mov     edx, 7Eh ; '~'
0x180008a84  call    WPP_SF_
0x180008a89  mov     rbx, [rsp+38h+arg_0]
0x180008a8e  mov     rsi, [rsp+38h+arg_8]
0x180008a93  add     rsp, 30h
0x180008a97  pop     rdi
0x180008a98  retn
```
