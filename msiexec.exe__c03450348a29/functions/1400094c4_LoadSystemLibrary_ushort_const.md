# LoadSystemLibrary(ushort const *)

- ea: `0x1400094c4`
- end: `0x140009534`
- name: `?LoadSystemLibrary@@YAPEAUHINSTANCE__@@PEBG@Z`
- size: `112`
- prototype: `HINSTANCE __fastcall(const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400011e4`
- `0x140008dfc`
- `0x140008e98`
- `0x140008f34`

## callees

- `0x140003883`
- `0x1400094c4`
- `0x14000953c`
- `0x140009820`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x140009511`
- `KERNEL32!LoadLibraryW` at `0x140009511`

## pseudocode

```c
HINSTANCE __fastcall LoadSystemLibrary(const unsigned __int16 *a1)
{
  unsigned __int64 v2; // r8
  WCHAR LibFileName; // [rsp+20h] [rbp-228h] BYREF
  _BYTE v5[526]; // [rsp+22h] [rbp-226h] BYREF

  LibFileName = 0;
  memset_0(v5, 0, 0x208u);
  if ( MakeFullSystemPath(a1, &LibFileName, v2) )
    return LoadLibraryW(&LibFileName);
  else
    return 0;
}

```

## disassembly

```asm
0x1400094c4  push    rbx
0x1400094c6  sub     rsp, 240h
0x1400094cd  mov     rax, cs:__security_cookie
0x1400094d4  xor     rax, rsp
0x1400094d7  mov     [rsp+248h+var_18], rax
0x1400094df  mov     rbx, rcx
0x1400094e2  xor     eax, eax
0x1400094e4  lea     rcx, [rsp+248h+var_226]; void *
0x1400094e9  mov     [rsp+248h+LibFileName], ax
0x1400094ee  xor     edx, edx; Val
0x1400094f0  mov     r8d, 208h; Size
0x1400094f6  call    memset_0
0x1400094fb  lea     rdx, [rsp+248h+LibFileName]; unsigned __int16 *
0x140009500  mov     rcx, rbx; unsigned __int16 *
0x140009503  call    ?MakeFullSystemPath@@YA_NPEBGPEAG_K@Z; MakeFullSystemPath(ushort const *,ushort *,unsigned __int64)
0x140009508  test    al, al
0x14000950a  jz      short loc_140009519
0x14000950c  lea     rcx, [rsp+248h+LibFileName]; lpLibFileName
0x140009511  call    cs:__imp_LoadLibraryW
0x140009517  jmp     short loc_14000951B
0x140009519  xor     eax, eax
0x14000951b  mov     rcx, [rsp+248h+var_18]
0x140009523  xor     rcx, rsp; StackCookie
0x140009526  call    __security_check_cookie
0x14000952b  add     rsp, 240h
0x140009532  pop     rbx
0x140009533  retn
```
