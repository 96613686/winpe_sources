# DhcpDeRegisterOptions

- ea: `0x1800062b0`
- end: `0x1800062ee`
- name: `DhcpDeRegisterOptions`
- size: `62`
- prototype: `__int64 __fastcall(HANDLE hObject)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003d50`
- `0x1800062b0`
- `0x1800127f0`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800062c2`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800062c2`

## pseudocode

```c
__int64 __fastcall DhcpDeRegisterOptions(HANDLE hObject, __int64 a2, __int64 a3)
{
  LPWSTR CommandLineW; // rax

  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1028, 110, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
  }
  return DhcpDeRegisterParameterChangeNotification(hObject, a2, a3);
}

```

## disassembly

```asm
0x1800062b0  push    rbx
0x1800062b2  sub     rsp, 20h
0x1800062b6  mov     rbx, rcx
0x1800062b9  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800062c0  jz      short loc_1800062E1
0x1800062c2  call    cs:__imp_GetCommandLineW
0x1800062c8  mov     edx, 6Eh ; 'n'
0x1800062cd  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800062d4  mov     r9, rax
0x1800062d7  mov     ecx, 404h
0x1800062dc  call    WPP_SF_S
0x1800062e1  mov     rcx, rbx; hObject
0x1800062e4  add     rsp, 20h
0x1800062e8  pop     rbx
0x1800062e9  jmp     DhcpDeRegisterParameterChangeNotification
```
