# Microsoft::Windows::MDM::OmadmClient::EventHandler::CreateEventW(_SECURITY_ATTRIBUTES *,int,int,ushort const *,void * *)

- ea: `0x14004d6c0`
- end: `0x14004d72c`
- name: `?CreateEventW@EventHandler@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEAU_SECURITY_ATTRIBUTES@@HHPEBGPEAPEAX@Z`
- size: `108`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::EventHandler *__hidden this, struct _SECURITY_ATTRIBUTES *, int, int, const unsigned __int16 *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14004d6c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14004d6f5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14004d6f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d709`

## pseudocode

```c
int __fastcall Microsoft::Windows::MDM::OmadmClient::EventHandler::CreateEventW(
        Microsoft::Windows::MDM::OmadmClient::EventHandler *this,
        struct _SECURITY_ATTRIBUTES *a2,
        BOOL a3,
        BOOL a4,
        const unsigned __int16 *lpName,
        void **a6)
{
  int result; // eax
  HANDLE EventW; // rax

  if ( !a6 )
    return -805306125;
  *a6 = 0;
  EventW = CreateEventW(a2, a3, a4, lpName);
  *a6 = EventW;
  if ( EventW )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14004d6c0  push    rbx
0x14004d6c2  sub     rsp, 20h
0x14004d6c6  mov     rbx, [rsp+28h+arg_28]
0x14004d6cb  mov     eax, r9d
0x14004d6ce  mov     r10d, r8d
0x14004d6d1  mov     r11, rdx
0x14004d6d4  test    rbx, rbx
0x14004d6d7  jnz     short loc_14004D6E0
0x14004d6d9  mov     eax, 0D00000F3h
0x14004d6de  jmp     short loc_14004D725
0x14004d6e0  mov     r9, [rsp+28h+lpName]; lpName
0x14004d6e5  mov     r8d, eax; bInitialState
0x14004d6e8  mov     edx, r10d; bManualReset
0x14004d6eb  mov     qword ptr [rbx], 0
0x14004d6f2  mov     rcx, r11; lpEventAttributes
0x14004d6f5  call    cs:__imp_CreateEventW
0x14004d6fc  nop     dword ptr [rax+rax+00h]
0x14004d701  mov     [rbx], rax
0x14004d704  test    rax, rax
0x14004d707  jnz     short loc_14004D723
0x14004d709  call    cs:__imp_GetLastError
0x14004d710  nop     dword ptr [rax+rax+00h]
0x14004d715  test    eax, eax
0x14004d717  jle     short loc_14004D725
0x14004d719  movzx   eax, ax
0x14004d71c  or      eax, 80070000h
0x14004d721  jmp     short loc_14004D725
0x14004d723  xor     eax, eax
0x14004d725  add     rsp, 20h
0x14004d729  pop     rbx
0x14004d72a  retn
```
