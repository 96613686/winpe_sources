# GetSiufLocPath(ushort * *)

- ea: `0x14001522c`
- end: `0x140015295`
- name: `?GetSiufLocPath@@YAJPEAPEAG@Z`
- size: `105`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400101fc`
- `0x1400103f8`

## callees

- `0x140014e08`
- `0x14001522c`
- `0x1400153dc`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140015247`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140015247`

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
0x14001522c  push    rbx
0x14001522e  sub     rsp, 20h
0x140015232  mov     rbx, rcx
0x140015235  mov     [rsp+28h+arg_8], 0
0x14001523d  xor     ecx, ecx
0x14001523f  lea     rdx, [rsp+28h+arg_8]
0x140015244  xor     r8d, r8d
0x140015247  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x14001524e  nop     dword ptr [rax+rax+00h]
0x140015253  mov     eax, [rsp+28h+arg_8]
0x140015257  sub     eax, 3
0x14001525a  jz      short loc_140015286
0x14001525c  sub     eax, 1
0x14001525f  jz      short loc_140015286
0x140015261  sub     eax, 1
0x140015264  jz      short loc_14001527C
0x140015266  sub     eax, 1
0x140015269  jz      short loc_140015286
0x14001526b  sub     eax, 8
0x14001526e  jz      short loc_140015286
0x140015270  cmp     eax, 2
0x140015273  jz      short loc_140015286
0x140015275  mov     eax, 80070032h
0x14001527a  jmp     short loc_14001528E
0x14001527c  mov     rcx, rbx; unsigned __int16 **
0x14001527f  call    ?BuildSiufLocPathForXbox@@YAJPEAPEAG@Z; BuildSiufLocPathForXbox(ushort * *)
0x140015284  jmp     short loc_14001528E
0x140015286  mov     rcx, rbx; unsigned __int16 **
0x140015289  call    ?GetStateSeparatedSiufLocFilesPath@@YAJPEAPEAG@Z; GetStateSeparatedSiufLocFilesPath(ushort * *)
0x14001528e  add     rsp, 20h
0x140015292  pop     rbx
0x140015293  retn
```
