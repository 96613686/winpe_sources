# CPath::Append(ushort const *)

- ea: `0x180006310`
- end: `0x180006358`
- name: `?Append@CPath@@QEAAJPEBG@Z`
- size: `72`
- prototype: `__int64 __fastcall(CPath *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180037da0`
- `0x180039bcc`
- `0x18003e35c`

## callees

- `0x180006310`
- `0x180032b8c`

## import_xrefs

- `ntdll!RtlAppendPathElement` at `0x18000633d`
- `ntdll!RtlAppendPathElement` at `0x18000633d`
- `ntdll!RtlInitUnicodeString` at `0x180006326`
- `ntdll!RtlInitUnicodeString` at `0x180006326`

## pseudocode

```c
__int64 __fastcall CPath::Append(CPath *this, const unsigned __int16 *a2)
{
  int appended; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  appended = RtlAppendPathElement(1, (char *)this + 520, &DestinationString);
  if ( appended >= 0 )
    return 0;
  else
    return ResultFromNtStatus(appended);
}

```

## disassembly

```asm
0x180006310  push    rbx
0x180006312  sub     rsp, 30h
0x180006316  mov     rbx, rcx
0x180006319  xorps   xmm0, xmm0
0x18000631c  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x180006321  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x180006326  call    cs:__imp_RtlInitUnicodeString
0x18000632c  lea     rdx, [rbx+208h]
0x180006333  mov     ecx, 1
0x180006338  lea     r8, [rsp+38h+DestinationString]
0x18000633d  call    cs:__imp_RtlAppendPathElement
0x180006343  test    eax, eax
0x180006345  jns     short loc_180006350
0x180006347  mov     ecx, eax; int
0x180006349  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x18000634e  jmp     short loc_180006352
0x180006350  xor     eax, eax
0x180006352  add     rsp, 30h
0x180006356  pop     rbx
0x180006357  retn
```
