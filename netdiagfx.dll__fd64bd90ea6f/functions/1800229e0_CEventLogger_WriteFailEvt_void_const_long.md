# CEventLogger::WriteFailEvt(void const *,long)

- ea: `0x1800229e0`
- end: `0x180022a6c`
- name: `?WriteFailEvt@CEventLogger@@EEAAJPEBXJ@Z`
- size: `140`
- prototype: `int(CEventLogger *__hidden this, const void *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800229e0`
- `0x18002c840`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x180022a3d`
- `ADVAPI32!EventWrite` at `0x180022a3d`
- `ADVAPI32!EventEnabled` at `0x180022a20`
- `ADVAPI32!EventEnabled` at `0x180022a20`

## pseudocode

```c
__int64 __fastcall CEventLogger::WriteFailEvt(CEventLogger *this, const EVENT_DESCRIPTOR *a2, int a3)
{
  unsigned int v3; // ebx
  signed int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-28h] BYREF
  int v8; // [rsp+60h] [rbp+18h] BYREF

  v8 = a3;
  v3 = 0;
  if ( a2 )
  {
    UserData.Ptr = (ULONGLONG)&v8;
    *(_QWORD *)&UserData.Size = 4;
    if ( EventEnabled(NETDIAG_EVT_GUID_Context, a2) )
    {
      v5 = EventWrite(NETDIAG_EVT_GUID_Context, a2, 1u, &UserData);
      v3 = v5;
      if ( v5 > 0 )
        return (unsigned __int16)v5 | 0x80070000;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800229e0  mov     r11, rsp
0x1800229e3  mov     [r11+8], rbx
0x1800229e7  mov     [r11+18h], r8d
0x1800229eb  push    rdi
0x1800229ec  sub     rsp, 40h
0x1800229f0  mov     rax, cs:__security_cookie
0x1800229f7  xor     rax, rsp
0x1800229fa  mov     [rsp+48h+var_18], rax
0x1800229ff  xor     ebx, ebx
0x180022a01  mov     rdi, rdx
0x180022a04  test    rdx, rdx
0x180022a07  jz      short loc_180022A52
0x180022a09  mov     rcx, cs:NETDIAG_EVT_GUID_Context; RegHandle
0x180022a10  lea     rax, [r11+18h]
0x180022a14  mov     [r11-28h], rax
0x180022a18  mov     qword ptr [r11-20h], 4
0x180022a20  call    cs:__imp_EventEnabled
0x180022a26  test    al, al
0x180022a28  jz      short loc_180022A52
0x180022a2a  mov     rcx, cs:NETDIAG_EVT_GUID_Context; RegHandle
0x180022a31  lea     r9, [rsp+48h+UserData]; UserData
0x180022a36  lea     r8d, [rbx+1]; UserDataCount
0x180022a3a  mov     rdx, rdi; EventDescriptor
0x180022a3d  call    cs:__imp_EventWrite
0x180022a43  mov     ebx, eax
0x180022a45  test    eax, eax
0x180022a47  jle     short loc_180022A52
0x180022a49  movzx   ebx, ax
0x180022a4c  or      ebx, 80070000h
0x180022a52  mov     eax, ebx
0x180022a54  mov     rcx, [rsp+48h+var_18]
0x180022a59  xor     rcx, rsp; StackCookie
0x180022a5c  call    __security_check_cookie
0x180022a61  mov     rbx, [rsp+48h+arg_0]
0x180022a66  add     rsp, 40h
0x180022a6a  pop     rdi
0x180022a6b  retn
```
