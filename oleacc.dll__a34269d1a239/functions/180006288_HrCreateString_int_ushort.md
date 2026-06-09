# HrCreateString(int,ushort * *)

- ea: `0x180006288`
- end: `0x180006305`
- name: `?HrCreateString@@YAJHPEAPEAG@Z`
- size: `125`
- prototype: `__int64 __fastcall(UINT uID, unsigned __int16 **)`
- caller_count: `46`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002c20`
- `0x180004c60`
- `0x180004f50`
- `0x1800057a0`
- `0x180005910`
- `0x18001a670`
- `0x18001b4b0`
- `0x18001b5b0`
- `0x180026fd0`
- `0x180027100`
- `0x1800279c0`
- `0x180027d80`
- `0x180028160`
- `0x1800290b0`
- `0x180029af0`
- `0x18002a610`
- `0x18002cba0`
- `0x18002d120`
- `0x18002e550`
- `0x180030360`
- `0x1800314f0`
- `0x180032170`
- `0x18003a2a0`
- `0x18003a490`
- `0x18003a550`
- `0x18003a870`
- `0x18003abd0`
- `0x18003c1c0`
- `0x18003c5d0`
- `0x18003e340`
- `0x18003e3b0`
- `0x18003e420`
- `0x18003e4c0`
- `0x18003e530`
- `0x18003e5a0`
- `0x18003e640`
- `0x18003ff40`
- `0x18003ffb0`
- `0x180040de0`
- `0x180042690`
- `0x180043080`
- `0x180043110`
- `0x180044360`
- `0x1800443c0`
- `0x1800445d0`
- `0x180044eb0`

## callees

- `0x180006288`
- `0x18001e4c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800062c1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800062c1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800062ee`
- `OLEAUT32!__imp_SysAllocString` at `0x1800062ee`

## pseudocode

```c
__int64 __fastcall HrCreateString(UINT uID, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rax
  WCHAR Buffer[256]; // [rsp+20h] [rbp-218h] BYREF

  *a2 = 0;
  if ( !LoadStringW(hinstResDll, uID, Buffer, 256) )
    return 2147942414LL;
  v4 = SysAllocString(Buffer);
  *a2 = v4;
  return v4 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x180006288  push    rbx
0x18000628a  sub     rsp, 230h
0x180006291  mov     rax, cs:__security_cookie
0x180006298  xor     rax, rsp
0x18000629b  mov     [rsp+238h+var_18], rax
0x1800062a3  mov     rbx, rdx
0x1800062a6  mov     qword ptr [rdx], 0
0x1800062ad  mov     edx, ecx; uID
0x1800062af  lea     r8, [rsp+238h+Buffer]; lpBuffer
0x1800062b4  mov     rcx, cs:?hinstResDll@@3PEAUHINSTANCE__@@EA; hInstance
0x1800062bb  mov     r9d, 100h; cchBufferMax
0x1800062c1  call    cs:__imp_LoadStringW
0x1800062c7  test    eax, eax
0x1800062c9  jnz     short loc_1800062E9
0x1800062cb  mov     eax, 8007000Eh
0x1800062d0  mov     rcx, [rsp+238h+var_18]
0x1800062d8  xor     rcx, rsp; StackCookie
0x1800062db  call    __security_check_cookie
0x1800062e0  add     rsp, 230h
0x1800062e7  pop     rbx
0x1800062e8  retn
0x1800062e9  lea     rcx, [rsp+238h+Buffer]; psz
0x1800062ee  call    cs:__imp_SysAllocString
0x1800062f4  mov     [rbx], rax
0x1800062f7  neg     rax
0x1800062fa  sbb     eax, eax
0x1800062fc  not     eax
0x1800062fe  and     eax, 8007000Eh
0x180006303  jmp     short loc_1800062D0
```
