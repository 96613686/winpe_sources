# GetTimerEntry

- ea: `0x14000bdfc`
- end: `0x14000be5c`
- name: `GetTimerEntry`
- size: `96`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000a7b0`
- `0x14000bbcc`
- `0x14000c3ec`
- `0x14000e408`
- `0x140026380`

## callees

- `0x14000bdfc`
- `0x140040294`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000be0c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000be0c`

## pseudocode

```c
__int64 __fastcall GetTimerEntry(_QWORD *a1)
{
  _DWORD *v2; // rax

  v2 = ExAllocateFromNPagedLookasideList(&Lookaside);
  if ( v2 )
  {
    v2[4] = 829253972;
    ++dword_1400396A0;
    *a1 = v2;
    return 0;
  }
  else
  {
    if ( (BYTE1(xmmword_140038420) & 2) != 0 )
      WPP_SF_(1033, 10, WPP_8528aed0382a3da68b410153017c41e5_Traceguids);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x14000bdfc  push    rbx
0x14000bdfe  sub     rsp, 20h
0x14000be02  mov     rbx, rcx
0x14000be05  lea     rcx, Lookaside; Lookaside
0x14000be0c  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000be13  nop     dword ptr [rax+rax+00h]
0x14000be18  test    rax, rax
0x14000be1b  jz      short loc_14000BE36
0x14000be1d  mov     dword ptr [rax+10h], 316D6954h
0x14000be24  inc     cs:dword_1400396A0
0x14000be2a  mov     [rbx], rax
0x14000be2d  xor     eax, eax
0x14000be2f  add     rsp, 20h
0x14000be33  pop     rbx
0x14000be34  retn
0x14000be36  test    byte ptr cs:xmmword_140038420+1, 2
0x14000be3d  jz      short loc_14000BE55
0x14000be3f  mov     edx, 0Ah
0x14000be44  lea     r8, WPP_8528aed0382a3da68b410153017c41e5_Traceguids
0x14000be4b  mov     ecx, 409h
0x14000be50  call    WPP_SF_
0x14000be55  mov     eax, 0C000009Ah
0x14000be5a  jmp     short loc_14000BE2F
```
