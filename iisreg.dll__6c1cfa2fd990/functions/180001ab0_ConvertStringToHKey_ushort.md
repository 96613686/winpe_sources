# ConvertStringToHKey(ushort *)

- ea: `0x180001ab0`
- end: `0x180001af5`
- name: `?ConvertStringToHKey@@YAPEAUHKEY__@@PEAG@Z`
- size: `69`
- prototype: `HKEY __fastcall(wchar_t *String1)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800018e0`
- `0x180001d7c`
- `0x18000200c`
- `0x1800029c4`
- `0x180002b90`
- `0x180002d14`

## callees

- `0x180001ab0`
- `0x18000361d`

## pseudocode

```c
unsigned __int64 __fastcall ConvertStringToHKey(wchar_t *String1)
{
  if ( !wcscmp_0(String1, L"HKCR") )
    return 0xFFFFFFFF80000000uLL;
  else
    return -(__int64)(wcscmp_0(String1, L"HKLM") == 0) & 0xFFFFFFFF80000002uLL;
}

```

## disassembly

```asm
0x180001ab0  push    rbx
0x180001ab2  sub     rsp, 20h
0x180001ab6  lea     rdx, aHkcr; "HKCR"
0x180001abd  mov     rbx, rcx
0x180001ac0  call    wcscmp_0
0x180001ac5  test    eax, eax
0x180001ac7  jnz     short loc_180001AD2
0x180001ac9  mov     rax, 0FFFFFFFF80000000h
0x180001ad0  jmp     short loc_180001AEF
0x180001ad2  lea     rdx, aHklm; "HKLM"
0x180001ad9  mov     rcx, rbx; String1
0x180001adc  call    wcscmp_0
0x180001ae1  neg     eax
0x180001ae3  sbb     rax, rax
0x180001ae6  not     rax
0x180001ae9  and     rax, 0FFFFFFFF80000002h
0x180001aef  add     rsp, 20h
0x180001af3  pop     rbx
0x180001af4  retn
```
