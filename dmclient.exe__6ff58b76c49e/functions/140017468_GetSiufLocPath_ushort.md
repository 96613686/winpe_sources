# GetSiufLocPath(ushort * *)

- ea: `0x140017468`
- end: `0x1400174ca`
- name: `?GetSiufLocPath@@YAJPEAPEAG@Z`
- size: `98`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000fc30`
- `0x14000fe20`

## callees

- `0x140017094`
- `0x140017468`
- `0x1400175e8`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140017483`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140017483`

## pseudocode

```c
__int64 __fastcall GetSiufLocPath(unsigned __int16 **a1)
{
  int v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v3, 0);
  if ( v3 != 3 && v3 != 4 )
  {
    if ( v3 == 5 )
      return BuildSiufLocPathForXbox(a1);
    if ( v3 != 6 && v3 != 14 && v3 != 16 )
      return 2147942450LL;
  }
  return GetStateSeparatedSiufLocFilesPath(a1);
}

```

## disassembly

```asm
0x140017468  push    rbx
0x14001746a  sub     rsp, 20h
0x14001746e  mov     rbx, rcx
0x140017471  mov     [rsp+28h+arg_8], 0
0x140017479  xor     ecx, ecx
0x14001747b  lea     rdx, [rsp+28h+arg_8]
0x140017480  xor     r8d, r8d
0x140017483  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x140017489  mov     eax, [rsp+28h+arg_8]
0x14001748d  sub     eax, 3
0x140017490  jz      short loc_1400174BC
0x140017492  sub     eax, 1
0x140017495  jz      short loc_1400174BC
0x140017497  sub     eax, 1
0x14001749a  jz      short loc_1400174B2
0x14001749c  sub     eax, 1
0x14001749f  jz      short loc_1400174BC
0x1400174a1  sub     eax, 8
0x1400174a4  jz      short loc_1400174BC
0x1400174a6  cmp     eax, 2
0x1400174a9  jz      short loc_1400174BC
0x1400174ab  mov     eax, 80070032h
0x1400174b0  jmp     short loc_1400174C4
0x1400174b2  mov     rcx, rbx; unsigned __int16 **
0x1400174b5  call    ?BuildSiufLocPathForXbox@@YAJPEAPEAG@Z; BuildSiufLocPathForXbox(ushort * *)
0x1400174ba  jmp     short loc_1400174C4
0x1400174bc  mov     rcx, rbx; unsigned __int16 **
0x1400174bf  call    ?GetStateSeparatedSiufLocFilesPath@@YAJPEAPEAG@Z; GetStateSeparatedSiufLocFilesPath(ushort * *)
0x1400174c4  add     rsp, 20h
0x1400174c8  pop     rbx
0x1400174c9  retn
```
