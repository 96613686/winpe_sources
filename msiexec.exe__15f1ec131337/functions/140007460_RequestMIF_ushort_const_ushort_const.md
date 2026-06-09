# RequestMIF(ushort const *,ushort const *)

- ea: `0x140007460`
- end: `0x1400074f9`
- name: `?RequestMIF@@YAHPEBG0@Z`
- size: `153`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x1400011e4`

## callees

- `0x140007460`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1400074c0`
- `KERNEL32!WideCharToMultiByte` at `0x1400074c0`
- `msi!__imp_MsiSetExternalUIA` at `0x1400074dd`
- `msi!__imp_MsiSetExternalUIA` at `0x1400074dd`

## pseudocode

```c
__int64 __fastcall RequestMIF(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  WINBOOL v3; // [rsp+60h] [rbp+18h] BYREF

  byte_140010CC0 = 0;
  szValueBuf = 0;
  MultiByteStr = 0;
  byte_140010DE0 = 0;
  byte_140010F10 = 0;
  if ( !a2 || !*a2 )
    return 0;
  v3 = 0;
  if ( WideCharToMultiByte(0, 0, a2, -1, (LPSTR)&qword_140011180, 9, 0, &v3) && !v3 )
  {
    MsiSetExternalUIA(UIHandlerMIF, 3u, 0);
    byte_140010F60 = 1;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x140007460  mov     r11, rsp
0x140007463  push    rbx
0x140007464  sub     rsp, 40h
0x140007468  xor     ebx, ebx
0x14000746a  mov     cs:byte_140010CC0, bl
0x140007470  mov     cs:szValueBuf, bl
0x140007476  mov     cs:MultiByteStr, bl
0x14000747c  mov     cs:byte_140010DE0, bl
0x140007482  mov     cs:byte_140010F10, bl
0x140007488  test    rdx, rdx
0x14000748b  jz      short loc_1400074EA
0x14000748d  cmp     [rdx], bx
0x140007490  jz      short loc_1400074EA
0x140007492  lea     rax, [r11+18h]
0x140007496  mov     [rsp+48h+arg_10], ebx
0x14000749a  mov     [r11-10h], rax
0x14000749e  mov     r8, rdx; lpWideCharStr
0x1400074a1  mov     [r11-18h], rbx
0x1400074a5  lea     rax, qword_140011180
0x1400074ac  mov     [rsp+48h+cbMultiByte], 9; cbMultiByte
0x1400074b4  or      r9d, 0FFFFFFFFh; cchWideChar
0x1400074b8  xor     edx, edx; dwFlags
0x1400074ba  mov     [r11-28h], rax
0x1400074be  xor     ecx, ecx; CodePage
0x1400074c0  call    cs:__imp_WideCharToMultiByte
0x1400074c6  test    eax, eax
0x1400074c8  jz      short loc_1400074F2
0x1400074ca  cmp     [rsp+48h+arg_10], ebx
0x1400074ce  jnz     short loc_1400074F2
0x1400074d0  xor     r8d, r8d; pvContext
0x1400074d3  lea     edx, [rbx+3]; dwMessageFilter
0x1400074d6  lea     rcx, ?UIHandlerMIF@@YAHPEAXIPEBD@Z; puiHandler
0x1400074dd  call    cs:__imp_MsiSetExternalUIA
0x1400074e3  mov     cs:byte_140010F60, 1
0x1400074ea  xor     eax, eax
0x1400074ec  add     rsp, 40h
0x1400074f0  pop     rbx
0x1400074f1  retn
0x1400074f2  mov     eax, 1
0x1400074f7  jmp     short loc_1400074EC
```
