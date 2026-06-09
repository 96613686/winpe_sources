# BinaryLogReader_Core_Init

- ea: `0x18002906c`
- end: `0x1800290ee`
- name: `BinaryLogReader_Core_Init`
- size: `130`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180025e90`
- `0x18002a9c0`

## callees

- `0x18000ac44`
- `0x18002906c`
- `0x180044842`
- `0x180044880`

## import_xrefs

- `mibincodec!MI_Application_NewDeserializer_Binary` at `0x1800290a5`
- `mibincodec!MI_Application_NewDeserializer_Binary` at `0x1800290a5`

## pseudocode

```c
__int64 __fastcall BinaryLogReader_Core_Init(_DWORD *a1)
{
  int v2; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+20h] [rbp-28h] BYREF

  memset_0(a1, 0, 0x70u);
  a1[1] = -1;
  v2 = MI_Application_NewDeserializer_Binary(0, 0, &dword_18005C6C4, a1 + 10);
  if ( !v2 )
    return 0;
  *(_DWORD *)&EventDescriptor.Id = 215;
  EventDescriptor.Keyword = 1;
  *(_DWORD *)&EventDescriptor.Level = 4;
  Etw_Trace1_int(&EventDescriptor, v2);
  return 1;
}

```

## disassembly

```asm
0x18002906c  push    rbx
0x18002906e  sub     rsp, 40h
0x180029072  mov     rax, cs:__security_cookie
0x180029079  xor     rax, rsp
0x18002907c  mov     [rsp+48h+var_18], rax
0x180029081  xor     edx, edx; Val
0x180029083  mov     rbx, rcx
0x180029086  lea     r8d, [rdx+70h]; Size
0x18002908a  call    memset_0
0x18002908f  lea     r9, [rbx+28h]
0x180029093  mov     dword ptr [rbx+4], 0FFFFFFFFh
0x18002909a  lea     r8, dword_18005C6C4
0x1800290a1  xor     edx, edx
0x1800290a3  xor     ecx, ecx
0x1800290a5  call    cs:__imp_MI_Application_NewDeserializer_Binary
0x1800290ab  test    eax, eax
0x1800290ad  jz      short loc_1800290D9
0x1800290af  mov     ebx, 1
0x1800290b4  mov     dword ptr [rsp+48h+EventDescriptor.Id], 0D7h
0x1800290bc  mov     edx, eax
0x1800290be  mov     [rsp+48h+EventDescriptor.Keyword], rbx
0x1800290c3  lea     rcx, [rsp+48h+EventDescriptor]; EventDescriptor
0x1800290c8  mov     dword ptr [rsp+48h+EventDescriptor.Level], 4
0x1800290d0  call    Etw_Trace1_int
0x1800290d5  mov     eax, ebx
0x1800290d7  jmp     short loc_1800290DB
0x1800290d9  xor     eax, eax
0x1800290db  mov     rcx, [rsp+48h+var_18]
0x1800290e0  xor     rcx, rsp; StackCookie
0x1800290e3  call    __security_check_cookie
0x1800290e8  add     rsp, 40h
0x1800290ec  pop     rbx
0x1800290ed  retn
```
