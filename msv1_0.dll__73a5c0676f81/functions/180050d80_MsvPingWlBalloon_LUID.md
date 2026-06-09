# MsvPingWlBalloon(_LUID *)

- ea: `0x180050d80`
- end: `0x180050e21`
- name: `?MsvPingWlBalloon@@YAEPEAU_LUID@@@Z`
- size: `161`
- prototype: `unsigned __int8 __fastcall(struct _LUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800513c4`

## callees

- `0x18002fb50`
- `0x180030844`
- `0x1800308b0`
- `0x180050d80`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050e00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050e00`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180050de6`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180050de6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180050df7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180050df7`

## pseudocode

```c
unsigned __int8 __fastcall MsvPingWlBalloon(struct _LUID *a1)
{
  HANDLE v2; // rax
  void *v3; // rbx
  DWORD LowPart; // [rsp+20h] [rbp-428h]
  wchar_t Buffer[512]; // [rsp+30h] [rbp-418h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  LowPart = a1->LowPart;
  swprintf_s(
    Buffer,
    0x1FFu,
    L"Global\\%08x%08x_%s",
    (unsigned int)a1->HighPart,
    LowPart,
    L"WlballoonNTLMNotificationEventName");
  v2 = OpenEventW(2u, 0, Buffer);
  v3 = v2;
  if ( v2 )
  {
    SetEvent(v2);
    CloseHandle(v3);
    LOBYTE(v2) = 1;
  }
  return (unsigned __int8)v2;
}

```

## disassembly

```asm
0x180050d80  push    rbx
0x180050d82  sub     rsp, 440h
0x180050d89  mov     rax, cs:__security_cookie
0x180050d90  xor     rax, rsp
0x180050d93  mov     [rsp+448h+var_18], rax
0x180050d9b  mov     rbx, rcx
0x180050d9e  xor     edx, edx; Val
0x180050da0  lea     rcx, [rsp+448h+Buffer]; void *
0x180050da5  mov     r8d, 400h; Size
0x180050dab  call    memset_0
0x180050db0  mov     r9d, [rbx+4]
0x180050db4  lea     rax, aWlballoonntlmn; "WlballoonNTLMNotificationEventName"
0x180050dbb  mov     [rsp+448h+var_420], rax
0x180050dc0  lea     r8, aGlobal08x08xS; "Global\\%08x%08x_%s"
0x180050dc7  mov     eax, [rbx]
0x180050dc9  lea     rcx, [rsp+448h+Buffer]; Buffer
0x180050dce  mov     edx, 1FFh; BufferCount
0x180050dd3  mov     [rsp+448h+var_428], eax
0x180050dd7  call    swprintf_s
0x180050ddc  xor     edx, edx; bInheritHandle
0x180050dde  lea     r8, [rsp+448h+Buffer]; lpName
0x180050de3  lea     ecx, [rdx+2]; dwDesiredAccess
0x180050de6  call    cs:__imp_OpenEventW
0x180050dec  mov     rbx, rax
0x180050def  test    rax, rax
0x180050df2  jz      short loc_180050E08
0x180050df4  mov     rcx, rbx; hEvent
0x180050df7  call    cs:__imp_SetEvent
0x180050dfd  mov     rcx, rbx; hObject
0x180050e00  call    cs:__imp_CloseHandle
0x180050e06  mov     al, 1
0x180050e08  mov     rcx, [rsp+448h+var_18]
0x180050e10  xor     rcx, rsp; StackCookie
0x180050e13  call    __security_check_cookie
0x180050e18  add     rsp, 440h
0x180050e1f  pop     rbx
0x180050e20  retn
```
