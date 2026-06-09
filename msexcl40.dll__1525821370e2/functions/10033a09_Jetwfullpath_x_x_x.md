# Jetwfullpath(x,x,x)

- ea: `0x10033a09`
- end: `0x10033aaa`
- name: `_Jetwfullpath@12`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x10026c60`

## callees

- `0x10032925`
- `0x10032956`
- `0x10032a7a`
- `0x10032aee`
- `0x10033a09`
- `0x10035510`
- `0x10035e9f`
- `0x10036060`
- `0x100360ae`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__fullpath` at `0x10033a64`
- `api-ms-win-crt-private-l1-1-0!_o__fullpath` at `0x10033a64`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x10033a2a`
- `api-ms-win-crt-private-l1-1-0!_o__wfullpath` at `0x10033a2a`

## pseudocode

```c
wchar_t *__fastcall Jetwfullpath(wchar_t *a1, const wchar_t *a2, int a3)
{
  _BYTE v5[4]; // [esp+10h] [ebp-440h] BYREF
  char *Path; // [esp+14h] [ebp-43Ch]
  _BYTE v7[4]; // [esp+228h] [ebp-228h] BYREF
  char *Buffer; // [esp+22Ch] [ebp-224h]
  int v9; // [esp+43Ch] [ebp-14h]
  int v10; // [esp+44Ch] [ebp-4h]

  if ( wrap )
    return __wfullpath(a1, a2, 0x103u);
  CStrIn::CStrIn((CStrIn *)v5, a2);
  CStrOut::CStrOut((CStrOut *)v7, a1, 259);
  __fullpath(Buffer, Path, 2 * v9);
  CStrOut::ConvertIncludingNul((CStrOut *)v7);
  v10 = 0;
  CStrOut::ConvertIncludingNul((CStrOut *)v7);
  CConvertStr::Free((CConvertStr *)v7);
  CConvertStr::Free((CConvertStr *)v5);
  return a1;
}

```

## disassembly

```asm
0x10033a09  push    434h
0x10033a0e  mov     eax, offset loc_10036B86
0x10033a13  call    __EH_prolog3_GS
0x10033a18  mov     esi, ecx
0x10033a1a  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10033a21  jz      short loc_10033A35
0x10033a23  push    103h; BufferCount
0x10033a28  push    edx; Path
0x10033a29  push    esi; Buffer
0x10033a2a  call    ds:__imp___wfullpath
0x10033a30  add     esp, 0Ch
0x10033a33  jmp     short loc_10033AA2
0x10033a35  push    edx; unsigned __int16 *
0x10033a36  lea     ecx, [ebp+var_440]; this
0x10033a3c  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10033a41  push    103h; int
0x10033a46  push    esi; unsigned __int16 *
0x10033a47  lea     ecx, [ebp+var_228]; this
0x10033a4d  call    ??0CStrOut@@QAE@PAGH@Z; CStrOut::CStrOut(ushort *,int)
0x10033a52  mov     eax, [ebp+var_14]
0x10033a55  add     eax, eax
0x10033a57  push    eax; BufferCount
0x10033a58  push    [ebp+Path]; Path
0x10033a5e  push    [ebp+Buffer]; Buffer
0x10033a64  call    ds:__imp___fullpath
0x10033a6a  add     esp, 0Ch
0x10033a6d  lea     ecx, [ebp+var_228]; this
0x10033a73  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x10033a78  lea     ecx, [ebp+var_228]; this
0x10033a7e  mov     [ebp+var_4], 0
0x10033a85  call    ?ConvertIncludingNul@CStrOut@@QAEHXZ; CStrOut::ConvertIncludingNul(void)
0x10033a8a  lea     ecx, [ebp+var_228]; this
0x10033a90  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10033a95  lea     ecx, [ebp+var_440]; this
0x10033a9b  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10033aa0  mov     eax, esi
0x10033aa2  call    __EH_epilog3_GS
0x10033aa7  retn    4
0x10035eb0  jmp     ds:__imp____std_terminate
0x10036b86  nop
0x10036b87  nop
0x10036b88  mov     edx, [esp-4+arg_4]
0x10036b8c  lea     eax, [edx+0Ch]
0x10036b8f  mov     ecx, [edx-444h]
0x10036b95  xor     ecx, eax; StackCookie
0x10036b97  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10036b9c  mov     ecx, [edx-4]
0x10036b9f  xor     ecx, eax; StackCookie
0x10036ba1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10036ba6  mov     eax, offset stru_10036C74
0x10036bab  jmp     ___CxxFrameHandler3
```
