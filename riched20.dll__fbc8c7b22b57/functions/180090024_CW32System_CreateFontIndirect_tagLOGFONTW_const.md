# CW32System::CreateFontIndirect(tagLOGFONTW const *)

- ea: `0x180090024`
- end: `0x1800900be`
- name: `?CreateFontIndirect@CW32System@@SAPEAUHFONT__@@PEBUtagLOGFONTW@@@Z`
- size: `154`
- prototype: `HFONT __fastcall(const struct tagLOGFONTW *)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a1d0`
- `0x1800112c0`
- `0x18001aa0c`
- `0x180024d88`
- `0x180025380`
- `0x180025bb0`
- `0x18003c080`
- `0x180060b64`
- `0x180090b14`
- `0x180091dd4`

## callees

- `0x180090024`
- `0x180092410`
- `0x180093c00`

## import_xrefs

- `GDI32!CreateFontIndirectA` at `0x18009009c`
- `GDI32!CreateFontIndirectA` at `0x18009009c`
- `GDI32!CreateFontIndirectW` at `0x180090043`
- `GDI32!CreateFontIndirectW` at `0x180090043`

## pseudocode

```c
HFONT __fastcall CW32System::CreateFontIndirect(const struct tagLOGFONTW *a1)
{
  unsigned __int128 v2; // xmm1
  __int128 v3; // xmm0
  LOGFONTA lf; // [rsp+30h] [rbp-58h] BYREF

  if ( CW32System::_dwPlatformId != 1 )
    return CreateFontIndirectW(a1);
  v2 = *(_OWORD *)&a1->lfOrientation;
  memset(&lf.lfWeight, 0, 44);
  v3 = *(_OWORD *)&a1->lfHeight;
  lf.lfEscapement = *(_QWORD *)&a1->lfEscapement;
  *(_OWORD *)&lf.lfOrientation = v2;
  ((void (__fastcall *)(CHAR *, __int64, WCHAR *, __int64, _DWORD, int, _QWORD, _QWORD, _QWORD, _QWORD))CW32System::MbcsFromUnicode)(
    lf.lfFaceName,
    32,
    a1->lfFaceName,
    0xFFFFFFFFLL,
    0,
    1,
    v3,
    *(_QWORD *)&lf.lfEscapement,
    v2 >> 32,
    *(_QWORD *)&lf.lfOutPrecision);
  return CreateFontIndirectA(&lf);
}

```

## disassembly

```asm
0x180090024  sub     rsp, 88h
0x18009002b  mov     rax, cs:__security_cookie
0x180090032  xor     rax, rsp
0x180090035  mov     [rsp+88h+var_18], rax
0x18009003a  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x180090041  jz      short loc_180090051
0x180090043  call    cs:__imp_CreateFontIndirectW
0x18009004a  nop     dword ptr [rax+rax+00h]
0x18009004f  jmp     short loc_1800900A8
0x180090051  movups  xmm1, xmmword ptr [rcx+0Ch]
0x180090055  mov     [rsp+88h+var_60], 1
0x18009005d  xor     eax, eax
0x18009005f  xorps   xmm0, xmm0
0x180090062  mov     [rsp+88h+var_68], eax
0x180090066  movups  xmmword ptr [rsp+88h+lf.lfFaceName+4], xmm0
0x18009006b  lea     r8, [rcx+1Ch]
0x18009006f  or      r9d, 0FFFFFFFFh
0x180090073  movups  xmmword ptr [rsp+88h+lf.lfWeight], xmm0
0x180090078  lea     edx, [rax+20h]
0x18009007b  movups  xmmword ptr [rsp+88h+lf.lfFaceName+10h], xmm0
0x180090080  movaps  xmm0, xmmword ptr [rcx]
0x180090083  lea     rcx, [rsp+88h+lf.lfFaceName]
0x180090088  movups  xmmword ptr [rsp+88h+lf.lfHeight], xmm0
0x18009008d  movups  xmmword ptr [rsp+88h+lf.lfOrientation], xmm1
0x180090092  call    ?MbcsFromUnicode@CW32System@@SAHPEADHPEBGHIW4UN_FLAGS@@@Z; CW32System::MbcsFromUnicode(char *,int,ushort const *,int,uint,UN_FLAGS)
0x180090097  lea     rcx, [rsp+88h+lf]; lplf
0x18009009c  call    cs:__imp_CreateFontIndirectA
0x1800900a3  nop     dword ptr [rax+rax+00h]
0x1800900a8  mov     rcx, [rsp+88h+var_18]
0x1800900ad  xor     rcx, rsp; StackCookie
0x1800900b0  call    __security_check_cookie
0x1800900b5  add     rsp, 88h
0x1800900bc  retn
```
