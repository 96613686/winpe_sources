# SQLGetInstalledDrivers

- ea: `0x18000eea0`
- end: `0x18000ef5e`
- name: `SQLGetInstalledDrivers`
- size: `190`
- prototype: `BOOL __stdcall(LPSTR lpszBuf, WORD cchBufMax, WORD *pcchBufOut)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180002940`
- `0x180008dc0`
- `0x18000eea0`
- `0x180013c2c`
- `0x180014364`

## import_xrefs

- `msvcrt!calloc` at `0x18000eee5`
- `msvcrt!calloc` at `0x18000eee5`

## pseudocode

```c
BOOL __stdcall SQLGetInstalledDrivers(LPSTR lpszBuf, WORD cchBufMax, WORD *pcchBufOut)
{
  WORD *v4; // rdi
  WCHAR *v5; // rbx
  BOOL v6; // r14d
  WORD v7; // bp
  unsigned __int16 v8; // ax
  __int64 v9; // rcx
  __int16 v11; // [rsp+40h] [rbp-48h] BYREF
  LPSTR v12; // [rsp+90h] [rbp+8h] BYREF

  v11 = 0;
  v4 = (WORD *)&v11;
  v12 = lpszBuf;
  if ( pcchBufOut )
    v4 = pcchBufOut;
  v5 = 0;
  if ( !lpszBuf || !cchBufMax || (*lpszBuf = 0, v6 = 0, (v5 = (WCHAR *)calloc(2LL * cchBufMax, 1u)) != 0) )
  {
    v6 = SQLGetInstalledDriversW(v5, cchBufMax, v4);
    if ( *v4 )
    {
      if ( v5 )
      {
        v7 = cchBufMax < *v4 ? *v4 : 0;
        v8 = wdnlen(v5);
        LConvertToAnsiWordLengths(v9, v5, v8, &v12, cchBufMax, v4);
        if ( v7 )
          *v4 = v7;
      }
    }
  }
  OFree(v5);
  return v6;
}

```

## disassembly

```asm
0x18000eea0  mov     rax, rsp
0x18000eea3  push    rbx
0x18000eea4  push    rbp
0x18000eea5  push    rsi
0x18000eea6  push    rdi
0x18000eea7  push    r14
0x18000eea9  push    r15
0x18000eeab  sub     rsp, 58h
0x18000eeaf  xor     r15d, r15d
0x18000eeb2  movzx   esi, dx
0x18000eeb5  test    r8, r8
0x18000eeb8  mov     [rax-48h], r15w
0x18000eebd  lea     rdi, [rax-48h]
0x18000eec1  mov     [rax+8], rcx
0x18000eec5  cmovnz  rdi, r8
0x18000eec9  mov     ebx, r15d
0x18000eecc  test    rcx, rcx
0x18000eecf  jz      short loc_18000EEF3
0x18000eed1  test    si, si
0x18000eed4  jz      short loc_18000EEF3
0x18000eed6  mov     [rcx], r15b
0x18000eed9  lea     edx, [r15+1]; Size
0x18000eedd  mov     ecx, esi
0x18000eedf  mov     r14d, r15d
0x18000eee2  add     rcx, rcx; Count
0x18000eee5  call    cs:__imp_calloc
0x18000eeeb  mov     rbx, rax
0x18000eeee  test    rax, rax
0x18000eef1  jz      short loc_18000EF46
0x18000eef3  mov     r8, rdi; pcchBufOut
0x18000eef6  movzx   edx, si; cchBufMax
0x18000eef9  mov     rcx, rbx; lpszBuf
0x18000eefc  call    SQLGetInstalledDriversW
0x18000ef01  mov     r14d, eax
0x18000ef04  cmp     [rdi], r15w
0x18000ef08  jz      short loc_18000EF46
0x18000ef0a  test    rbx, rbx
0x18000ef0d  jz      short loc_18000EF46
0x18000ef0f  cmp     si, [rdi]
0x18000ef12  mov     rcx, rbx
0x18000ef15  sbb     bp, bp
0x18000ef18  and     bp, [rdi]
0x18000ef1b  call    wdnlen
0x18000ef20  movzx   r8d, ax
0x18000ef24  mov     [rsp+88h+var_60], rdi
0x18000ef29  mov     rdx, rbx
0x18000ef2c  mov     [rsp+88h+var_68], si
0x18000ef31  lea     r9, [rsp+88h+arg_0]
0x18000ef39  call    LConvertToAnsiWordLengths
0x18000ef3e  test    bp, bp
0x18000ef41  jz      short loc_18000EF46
0x18000ef43  mov     [rdi], bp
0x18000ef46  mov     rcx, rbx
0x18000ef49  call    OFree
0x18000ef4e  mov     eax, r14d
0x18000ef51  add     rsp, 58h
0x18000ef55  pop     r15
0x18000ef57  pop     r14
0x18000ef59  pop     rdi
0x18000ef5a  pop     rsi
0x18000ef5b  pop     rbp
0x18000ef5c  pop     rbx
0x18000ef5d  retn
```
