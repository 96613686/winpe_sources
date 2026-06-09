# HSTS_HANDLER::CreateHstsHeaderValue(ulong,int,int,STRA *)

- ea: `0x180001ab0`
- end: `0x180001b5b`
- name: `?CreateHstsHeaderValue@HSTS_HANDLER@@CAJKHHPEAVSTRA@@@Z`
- size: `171`
- prototype: `__int64 __fastcall(unsigned int, int, int, struct STRA *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180001010`

## callees

- `0x180001ab0`
- `0x180002760`

## import_xrefs

- `msvcrt!_ultoa_s` at `0x180001ae4`
- `msvcrt!_ultoa_s` at `0x180001ae4`
- `iisutil!?Reset@STRA@@QEAAXXZ` at `0x180001b53`
- `iisutil!?Reset@STRA@@QEAAXXZ` at `0x180001b53`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180001afe`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180001afe`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180001b12`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800031ce`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800031ed`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180001b12`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800031ce`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800031ed`

## pseudocode

```c
__int64 __fastcall HSTS_HANDLER::CreateHstsHeaderValue(unsigned int a1, int a2, int a3, struct STRA *a4)
{
  errno_t v7; // eax
  signed int v8; // ebx
  char Buffer[32]; // [rsp+20h] [rbp-48h] BYREF

  v7 = _ultoa_s(a1, Buffer, 0x20u, 10);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
LABEL_7:
    if ( v8 >= 0 )
      return (unsigned int)v8;
LABEL_8:
    STRA::Reset(a4);
    return (unsigned int)v8;
  }
  v8 = STRA::Copy(a4, "max-age=");
  if ( v8 < 0 )
    goto LABEL_8;
  v8 = STRA::Append(a4, Buffer);
  if ( v8 < 0 )
    goto LABEL_8;
  if ( a2 == 1 )
  {
    v8 = STRA::Append(a4, "; includeSubDomains");
    if ( v8 < 0 )
      goto LABEL_8;
  }
  if ( a3 == 1 )
  {
    v8 = STRA::Append(a4, "; preload");
    goto LABEL_7;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180001ab0  mov     [rsp+arg_8], rbx
0x180001ab5  push    rbp
0x180001ab6  push    rsi
0x180001ab7  push    rdi
0x180001ab8  sub     rsp, 50h
0x180001abc  mov     rax, cs:__security_cookie
0x180001ac3  xor     rax, rsp
0x180001ac6  mov     [rsp+68h+var_28], rax
0x180001acb  mov     rdi, r9
0x180001ace  mov     esi, r8d
0x180001ad1  mov     ebp, edx
0x180001ad3  mov     r9d, 0Ah; Radix
0x180001ad9  mov     r8d, 20h ; ' '; BufferCount
0x180001adf  lea     rdx, [rsp+68h+Buffer]; Buffer
0x180001ae4  call    cs:__imp__ultoa_s
0x180001aea  mov     ebx, eax
0x180001aec  test    eax, eax
0x180001aee  jnz     loc_1800031B0
0x180001af4  lea     rdx, aMaxAge; "max-age="
0x180001afb  mov     rcx, rdi
0x180001afe  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180001b04  mov     ebx, eax
0x180001b06  test    eax, eax
0x180001b08  js      short loc_180001B50
0x180001b0a  lea     rdx, [rsp+68h+Buffer]
0x180001b0f  mov     rcx, rdi
0x180001b12  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180001b18  mov     ebx, eax
0x180001b1a  test    eax, eax
0x180001b1c  js      short loc_180001B50
0x180001b1e  cmp     ebp, 1
0x180001b21  jz      loc_1800031C4
0x180001b27  cmp     esi, 1
0x180001b2a  jz      loc_1800031E3
0x180001b30  mov     eax, ebx
0x180001b32  mov     rcx, [rsp+68h+var_28]
0x180001b37  xor     rcx, rsp; StackCookie
0x180001b3a  call    __security_check_cookie
0x180001b3f  mov     rbx, [rsp+68h+arg_8]
0x180001b44  add     rsp, 50h
0x180001b48  pop     rdi
0x180001b49  pop     rsi
0x180001b4a  pop     rbp
0x180001b4b  retn
0x180001b4c  test    ebx, ebx
0x180001b4e  jns     short loc_180001B30
0x180001b50  mov     rcx, rdi
0x180001b53  call    cs:__imp_?Reset@STRA@@QEAAXXZ; STRA::Reset(void)
0x180001b59  jmp     short loc_180001B30
0x1800031b0  jle     loc_180001B4C
0x1800031b6  movzx   ebx, ax
0x1800031b9  or      ebx, 80070000h
0x1800031bf  jmp     loc_180001B4C
0x1800031c4  lea     rdx, aIncludesubdoma; "; includeSubDomains"
0x1800031cb  mov     rcx, rdi
0x1800031ce  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x1800031d4  mov     ebx, eax
0x1800031d6  test    eax, eax
0x1800031d8  js      loc_180001B50
0x1800031de  jmp     loc_180001B27
0x1800031e3  lea     rdx, aPreload_0; "; preload"
0x1800031ea  mov     rcx, rdi
0x1800031ed  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x1800031f3  mov     ebx, eax
0x1800031f5  jmp     loc_180001B4C
```
