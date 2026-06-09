# GetCollectionWriter(CWriter *,CMBSchemaWriter * *,CMBCollectionWriter * *,ushort const *,int,ushort const *)

- ea: `0x180011658`
- end: `0x180011766`
- name: `?GetCollectionWriter@@YAJPEAVCWriter@@PEAPEAVCMBSchemaWriter@@PEAPEAVCMBCollectionWriter@@PEBGH3@Z`
- size: `270`
- prototype: `int(struct CWriter *, struct CMBSchemaWriter **, struct CMBCollectionWriter **, const unsigned __int16 *, int, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180011320`
- `0x180011c74`
- `0x180011e74`
- `0x180012938`

## callees

- `0x1800089c8`
- `0x180011658`
- `0x18002f2c4`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x180011709`
- `IisRTL!PuDbgPrintW` at `0x180011751`
- `IisRTL!PuDbgPrintW` at `0x180011709`
- `IisRTL!PuDbgPrintW` at `0x180011751`

## string_xrefs

- `0x180011726`: `[SaveSchema] Error while saving schema tree. Unable to get schema writer failed with hr = 0x%x.\n`
- `0x1800116e0`: `GetCollectionWriter`
- `0x180011736`: `GetCollectionWriter`
- `0x1800116f2`: `[SaveSchema] GetCollectionWriter for %s failed with hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall GetCollectionWriter(
        struct CWriter *a1,
        struct CMBSchemaWriter **a2,
        struct CMBCollectionWriter **a3,
        const unsigned __int16 *a4,
        int a5,
        unsigned __int16 *a6)
{
  struct CMBSchemaWriter *v10; // rax
  int CollectionWriter; // eax
  unsigned int v12; // ebx
  bool v13; // zf

  if ( !*a3 )
  {
    v10 = *a2;
    if ( !*a2 )
    {
      v10 = (struct CMBSchemaWriter *)operator new(0x18u);
      if ( !v10 )
      {
        v13 = (g_dwDebugFlags & 3) == 0;
        *a2 = 0;
        v12 = -2147024882;
        if ( !v13 )
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
            2193,
            "GetCollectionWriter",
            L"[SaveSchema] Error while saving schema tree. Unable to get schema writer failed with hr = 0x%x.\n",
            -2147024882);
        return v12;
      }
      *(_QWORD *)v10 = 0;
      *((_QWORD *)v10 + 1) = 0;
      *((_QWORD *)v10 + 2) = a1;
      *a2 = v10;
    }
    CollectionWriter = CMBSchemaWriter::GetCollectionWriter(v10, a4, a5, a6, a3);
    v12 = CollectionWriter;
    if ( CollectionWriter < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\saveschema.cpp",
          2211,
          "GetCollectionWriter",
          L"[SaveSchema] GetCollectionWriter for %s failed with hr = 0x%x.\n",
          a4,
          CollectionWriter);
      return v12;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011658  push    rbx
0x18001165a  push    rbp
0x18001165b  push    rsi
0x18001165c  push    rdi
0x18001165d  sub     rsp, 48h
0x180011661  cmp     qword ptr [r8], 0
0x180011665  mov     rsi, r9
0x180011668  mov     rdi, r8
0x18001166b  mov     rbx, rdx
0x18001166e  mov     rbp, rcx
0x180011671  jnz     loc_18001175B
0x180011677  mov     rax, [rdx]
0x18001167a  test    rax, rax
0x18001167d  jnz     short loc_1800116A6
0x18001167f  lea     ecx, [rax+18h]; Size
0x180011682  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011687  test    rax, rax
0x18001168a  jz      loc_180011711
0x180011690  mov     qword ptr [rax], 0
0x180011697  mov     qword ptr [rax+8], 0
0x18001169f  mov     [rax+10h], rbp
0x1800116a3  mov     [rbx], rax
0x1800116a6  mov     r9, [rsp+68h+arg_28]; unsigned __int16 *
0x1800116ae  mov     rdx, rsi; unsigned __int16 *
0x1800116b1  mov     r8d, [rsp+68h+arg_20]; int
0x1800116b9  mov     rcx, rax; this
0x1800116bc  mov     [rsp+68h+var_48], rdi; struct CMBCollectionWriter **
0x1800116c1  call    ?GetCollectionWriter@CMBSchemaWriter@@QEAAJPEBGH0PEAPEAVCMBCollectionWriter@@@Z; CMBSchemaWriter::GetCollectionWriter(ushort const *,int,ushort const *,CMBCollectionWriter * *)
0x1800116c6  mov     ebx, eax
0x1800116c8  test    eax, eax
0x1800116ca  jns     loc_18001175B
0x1800116d0  test    byte ptr cs:g_dwDebugFlags, 3
0x1800116d7  jz      short loc_180011757
0x1800116d9  mov     rcx, cs:g_pDebug
0x1800116e0  lea     r9, aGetcollectionw; "GetCollectionWriter"
0x1800116e7  mov     [rsp+68h+var_38], eax
0x1800116eb  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x1800116f2  lea     rax, aSaveschemaGetc; "[SaveSchema] GetCollectionWriter for %s"...
0x1800116f9  mov     [rsp+68h+var_40], rsi
0x1800116fe  mov     r8d, 8A3h
0x180011704  mov     [rsp+68h+var_48], rax
0x180011709  call    cs:__imp_PuDbgPrintW
0x18001170f  jmp     short loc_180011757
0x180011711  test    byte ptr cs:g_dwDebugFlags, 3
0x180011718  mov     qword ptr [rbx], 0
0x18001171f  mov     ebx, 8007000Eh
0x180011724  jz      short loc_180011757
0x180011726  lea     rcx, aSaveschemaErro_3; "[SaveSchema] Error while saving schema "...
0x18001172d  mov     dword ptr [rsp+68h+var_40], ebx
0x180011731  mov     [rsp+68h+var_48], rcx
0x180011736  lea     r9, aGetcollectionw; "GetCollectionWriter"
0x18001173d  mov     rcx, cs:g_pDebug
0x180011744  lea     rdx, aInetsrvIisMbMe_4; "inetsrv\\iis\\mb\\metadata\\saveschema."...
0x18001174b  mov     r8d, 891h
0x180011751  call    cs:__imp_PuDbgPrintW
0x180011757  mov     eax, ebx
0x180011759  jmp     short loc_18001175D
0x18001175b  xor     eax, eax
0x18001175d  add     rsp, 48h
0x180011761  pop     rdi
0x180011762  pop     rsi
0x180011763  pop     rbp
0x180011764  pop     rbx
0x180011765  retn
```
