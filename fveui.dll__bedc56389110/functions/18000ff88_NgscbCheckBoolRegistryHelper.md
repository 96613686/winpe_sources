# NgscbCheckBoolRegistryHelper

- ea: `0x18000ff88`
- end: `0x180010072`
- name: `NgscbCheckBoolRegistryHelper`
- size: `234`
- prototype: `__int64 __fastcall(LPCWSTR lpValue)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180010160`
- `0x180010208`

## callees

- `0x1800037a0`
- `0x18000e354`
- `0x18000ff88`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x18000ffd6`
- `ADVAPI32!RegGetValueW` at `0x18000ffd6`

## pseudocode

```c
__int64 __fastcall NgscbCheckBoolRegistryHelper(LPCWSTR lpValue, char *a2)
{
  LSTATUS ValueW; // eax
  unsigned int v4; // ebx
  char v5; // al
  int v7; // [rsp+60h] [rbp+18h] BYREF
  DWORD v8; // [rsp+68h] [rbp+20h] BYREF

  v7 = 0;
  v8 = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Control\\BitLocker",
             lpValue,
             0x10u,
             0,
             &v7,
             &v8);
  v4 = ValueW;
  if ( ValueW == 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 297, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids);
    v4 = 0;
    goto LABEL_6;
  }
  if ( !ValueW )
  {
    v4 = 0;
    if ( v7 )
    {
      v5 = 1;
      goto LABEL_7;
    }
LABEL_6:
    v5 = 0;
LABEL_7:
    *a2 = v5;
    return v4;
  }
  if ( ValueW > 0 )
    v4 = (unsigned __int16)ValueW | 0x80070000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 298, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18000ff88  mov     r11, rsp
0x18000ff8b  mov     [r11+8], rbx
0x18000ff8f  push    rdi
0x18000ff90  sub     rsp, 40h
0x18000ff94  lea     rax, [r11+20h]
0x18000ff98  mov     [rsp+48h+arg_10], 0
0x18000ffa0  mov     [r11-18h], rax
0x18000ffa4  mov     rdi, rdx
0x18000ffa7  lea     rax, [r11+18h]
0x18000ffab  mov     [rsp+48h+arg_18], 4
0x18000ffb3  mov     r8, rcx; lpValue
0x18000ffb6  mov     [r11-20h], rax
0x18000ffba  mov     r9d, 10h; dwFlags
0x18000ffc0  mov     qword ptr [r11-28h], 0
0x18000ffc8  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Bit"...
0x18000ffcf  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000ffd6  call    cs:__imp_RegGetValueW
0x18000ffdc  mov     ebx, eax
0x18000ffde  cmp     eax, 2
0x18000ffe1  jnz     short loc_180010024
0x18000ffe3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ffea  lea     rax, WPP_GLOBAL_Control
0x18000fff1  cmp     rcx, rax
0x18000fff4  jz      short loc_180010011
0x18000fff6  test    byte ptr [rcx+1Ch], 8
0x18000fffa  jz      short loc_180010011
0x18000fffc  mov     rcx, [rcx+10h]
0x180010000  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180010007  mov     edx, 129h
0x18001000c  call    WPP_SF_
0x180010011  xor     ebx, ebx
0x180010013  xor     al, al
0x180010015  mov     [rdi], al
0x180010017  mov     eax, ebx
0x180010019  mov     rbx, [rsp+48h+arg_0]
0x18001001e  add     rsp, 40h
0x180010022  pop     rdi
0x180010023  retn
0x180010024  test    eax, eax
0x180010026  jz      short loc_180010066
0x180010028  jle     short loc_180010033
0x18001002a  movzx   ebx, ax
0x18001002d  or      ebx, 80070000h
0x180010033  mov     rcx, cs:WPP_GLOBAL_Control
0x18001003a  lea     rax, WPP_GLOBAL_Control
0x180010041  cmp     rcx, rax
0x180010044  jz      short loc_180010017
0x180010046  test    byte ptr [rcx+1Ch], 40h
0x18001004a  jz      short loc_180010017
0x18001004c  mov     rcx, [rcx+10h]
0x180010050  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180010057  mov     edx, 12Ah
0x18001005c  mov     r9d, ebx
0x18001005f  call    WPP_SF_d
0x180010064  jmp     short loc_180010017
0x180010066  xor     ebx, ebx
0x180010068  cmp     [rsp+48h+arg_10], ebx
0x18001006c  jz      short loc_180010013
0x18001006e  mov     al, 1
0x180010070  jmp     short loc_180010015
```
