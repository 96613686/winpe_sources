# FreeHidDevice

- ea: `0x180005680`
- end: `0x180005702`
- name: `FreeHidDevice`
- size: `130`
- prototype: `HLOCAL __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180006460`
- `0x180006978`

## callees

- `0x180005680`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800056ae`
- `KERNEL32!LocalFree` at `0x1800056b8`
- `KERNEL32!LocalFree` at `0x1800056d6`
- `KERNEL32!LocalFree` at `0x1800056e3`
- `KERNEL32!LocalFree` at `0x1800056ae`
- `KERNEL32!LocalFree` at `0x1800056b8`
- `KERNEL32!LocalFree` at `0x1800056d6`
- `KERNEL32!LocalFree` at `0x1800056e3`
- `KERNEL32!LocalFree` at `0x1800056fb`
- `HID!HidD_FreePreparsedData` at `0x180005696`
- `HID!HidD_FreePreparsedData` at `0x180005696`

## pseudocode

```c
HLOCAL __fastcall FreeHidDevice(__int64 a1)
{
  __int64 v2; // rdi
  unsigned __int8 v3; // si
  unsigned __int16 i; // ax

  HidD_FreePreparsedData(*(PHIDP_PREPARSED_DATA *)(a1 + 16));
  v2 = *(_QWORD *)(a1 + 192);
  v3 = 0;
  for ( i = 0; i < *(_WORD *)(a1 + 68); i = v3 )
  {
    LocalFree(*(HLOCAL *)(v2 + 32));
    LocalFree(*(HLOCAL *)(v2 + 24));
    ++v3;
    v2 += 40;
  }
  LocalFree(*(HLOCAL *)(a1 + 192));
  LocalFree(*(HLOCAL *)(a1 + 184));
  return LocalFree((HLOCAL)a1);
}

```

## disassembly

```asm
0x180005680  mov     [rsp+arg_0], rbx
0x180005685  mov     [rsp+arg_8], rsi
0x18000568a  push    rdi
0x18000568b  sub     rsp, 20h
0x18000568f  mov     rbx, rcx
0x180005692  mov     rcx, [rcx+10h]; PreparsedData
0x180005696  call    cs:__imp_HidD_FreePreparsedData
0x18000569c  mov     rdi, [rbx+0C0h]
0x1800056a3  xor     sil, sil
0x1800056a6  xor     eax, eax
0x1800056a8  jmp     short loc_1800056C9
0x1800056aa  mov     rcx, [rdi+20h]; hMem
0x1800056ae  call    cs:__imp_LocalFree
0x1800056b4  mov     rcx, [rdi+18h]; hMem
0x1800056b8  call    cs:__imp_LocalFree
0x1800056be  inc     sil
0x1800056c1  lea     rdi, [rdi+28h]
0x1800056c5  movzx   eax, sil
0x1800056c9  cmp     ax, [rbx+44h]
0x1800056cd  jb      short loc_1800056AA
0x1800056cf  mov     rcx, [rbx+0C0h]; hMem
0x1800056d6  call    cs:__imp_LocalFree
0x1800056dc  mov     rcx, [rbx+0B8h]; hMem
0x1800056e3  call    cs:__imp_LocalFree
0x1800056e9  mov     rcx, rbx
0x1800056ec  mov     rbx, [rsp+28h+arg_0]
0x1800056f1  mov     rsi, [rsp+28h+arg_8]
0x1800056f6  add     rsp, 20h
0x1800056fa  pop     rdi
0x1800056fb  jmp     cs:__imp_LocalFree
```
