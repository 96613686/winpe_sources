# BOOLfromPSZ

- ea: `0x140001a24`
- end: `0x140001afd`
- name: `BOOLfromPSZ`
- size: `217`
- prototype: `__int64 __fastcall(char *String1)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400023f0`
- `0x140003d28`
- `0x140007934`
- `0x14000be40`

## callees

- `0x140001a24`
- `0x140008620`

## import_xrefs

- `msvcrt!_stricmp` at `0x140001a4a`
- `msvcrt!_stricmp` at `0x140001a62`
- `msvcrt!_stricmp` at `0x140001a7a`
- `msvcrt!_stricmp` at `0x140001a99`
- `msvcrt!_stricmp` at `0x140001aad`
- `msvcrt!_stricmp` at `0x140001ac1`
- `msvcrt!_stricmp` at `0x140001a4a`
- `msvcrt!_stricmp` at `0x140001a62`
- `msvcrt!_stricmp` at `0x140001a7a`
- `msvcrt!_stricmp` at `0x140001a99`
- `msvcrt!_stricmp` at `0x140001aad`
- `msvcrt!_stricmp` at `0x140001ac1`

## pseudocode

```c
__int64 __fastcall BOOLfromPSZ(char *String1, __int64 a2)
{
  if ( *String1 == 48 && !String1[1]
    || !_stricmp(String1, "No")
    || !_stricmp(String1, "Off")
    || !_stricmp(String1, "False") )
  {
    return 0;
  }
  if ( *String1 == 49 && !String1[1]
    || !_stricmp(String1, "Yes")
    || !_stricmp(String1, "On")
    || !_stricmp(String1, "True") )
  {
    return 1;
  }
  ErrSet(a2, (int)"Invalid boolean value: %1", "%s", String1);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x140001a24  mov     [rsp+arg_0], rbx
0x140001a29  push    rdi
0x140001a2a  sub     rsp, 20h
0x140001a2e  cmp     byte ptr [rcx], 30h ; '0'
0x140001a31  mov     rdi, rdx
0x140001a34  mov     rbx, rcx
0x140001a37  jnz     short loc_140001A43
0x140001a39  cmp     byte ptr [rcx+1], 0
0x140001a3d  jz      loc_140001AF0
0x140001a43  lea     rdx, String2; "No"
0x140001a4a  call    cs:__imp__stricmp
0x140001a50  test    eax, eax
0x140001a52  jz      loc_140001AF0
0x140001a58  lea     rdx, aOff; "Off"
0x140001a5f  mov     rcx, rbx; String1
0x140001a62  call    cs:__imp__stricmp
0x140001a68  test    eax, eax
0x140001a6a  jz      loc_140001AF0
0x140001a70  lea     rdx, aFalse; "False"
0x140001a77  mov     rcx, rbx; String1
0x140001a7a  call    cs:__imp__stricmp
0x140001a80  test    eax, eax
0x140001a82  jz      short loc_140001AF0
0x140001a84  cmp     byte ptr [rbx], 31h ; '1'
0x140001a87  jnz     short loc_140001A8F
0x140001a89  cmp     byte ptr [rbx+1], 0
0x140001a8d  jz      short loc_140001AE9
0x140001a8f  lea     rdx, aYes; "Yes"
0x140001a96  mov     rcx, rbx; String1
0x140001a99  call    cs:__imp__stricmp
0x140001a9f  test    eax, eax
0x140001aa1  jz      short loc_140001AE9
0x140001aa3  lea     rdx, aOn; "On"
0x140001aaa  mov     rcx, rbx; String1
0x140001aad  call    cs:__imp__stricmp
0x140001ab3  test    eax, eax
0x140001ab5  jz      short loc_140001AE9
0x140001ab7  lea     rdx, aTrue; "True"
0x140001abe  mov     rcx, rbx; String1
0x140001ac1  call    cs:__imp__stricmp
0x140001ac7  test    eax, eax
0x140001ac9  jz      short loc_140001AE9
0x140001acb  mov     r9, rbx
0x140001ace  lea     r8, aS_4; "%s"
0x140001ad5  lea     rdx, aInvalidBoolean; "Invalid boolean value: %1"
0x140001adc  mov     rcx, rdi
0x140001adf  call    ErrSet
0x140001ae4  or      eax, 0FFFFFFFFh
0x140001ae7  jmp     short loc_140001AF2
0x140001ae9  mov     eax, 1
0x140001aee  jmp     short loc_140001AF2
0x140001af0  xor     eax, eax
0x140001af2  mov     rbx, [rsp+28h+arg_0]
0x140001af7  add     rsp, 20h
0x140001afb  pop     rdi
0x140001afc  retn
```
