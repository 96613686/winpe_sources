# SettingsCopier::OpenSessionKey(ATL::CRegKey &,ulong)

- ea: `0x1400252a8`
- end: `0x1400253f8`
- name: `?OpenSessionKey@SettingsCopier@@AEAAJAEAVCRegKey@ATL@@K@Z`
- size: `336`
- prototype: `int(SettingsCopier *__hidden this, struct ATL::CRegKey *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140025184`

## callees

- `0x140007e90`
- `0x140009524`
- `0x140009f28`
- `0x140013a34`
- `0x1400170d8`
- `0x14001c494`
- `0x14001caa4`
- `0x1400252a8`

## import_xrefs

- `msvcrt!free` at `0x1400253ac`
- `msvcrt!free` at `0x1400253c7`
- `msvcrt!free` at `0x1400253ac`
- `msvcrt!free` at `0x1400253c7`

## string_xrefs

- `0x1400252e0`: `%s\ATConfig`
- `0x140025341`: `%s\ATConfig`

## pseudocode

```c
__int64 __fastcall SettingsCopier::OpenSessionKey(SettingsCopier *this, struct ATL::CRegKey *a2)
{
  unsigned int v3; // r11d
  char *v4; // rdi
  char *v5; // rdx
  unsigned int v6; // edi
  unsigned __int16 *v7; // r9
  HKEY v9; // [rsp+30h] [rbp-20h]
  unsigned __int64 v10; // [rsp+40h] [rbp-10h] BYREF
  void *Block; // [rsp+70h] [rbp+20h] BYREF
  unsigned int v12; // [rsp+80h] [rbp+30h] BYREF
  unsigned __int16 *v13; // [rsp+88h] [rbp+38h] BYREF

  Block = this;
  CATUtils::SessionKeyString((__int64)&v13);
  Block = 0;
  v10 = 0;
  if ( (int)StringCchLengthW(SettingsCopier::_ATSessionConfigKeyString, 0x7FFFFFFFu, (unsigned __int64 *)&Block) < 0
    || (int)StringCchLengthW(v13, v3, &v10) < 0
    || (v4 = (char *)Block + v10, (char *)Block + v10 < Block) )
  {
    ATL::CStringData::Release((ATL::CStringData *)(v13 - 12));
    return 2147500037LL;
  }
  else
  {
    v5 = (char *)Block + v10;
    Block = 0;
    if ( !(unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Block, v5) )
    {
      v6 = -2147024882;
LABEL_10:
      free(Block);
      ATL::CStringData::Release((ATL::CStringData *)(v13 - 12));
      return v6;
    }
    if ( (int)StringCchPrintfW(
                (unsigned __int16 *)Block,
                (unsigned __int64)v4,
                SettingsCopier::_ATSessionConfigKeyString,
                v13) < 0
      || (unsigned int)ATL::CRegKey::Open(a2, HKEY_LOCAL_MACHINE, (LPCWSTR)Block, 0x2001Fu)
      && (unsigned int)ATL::CRegKey::Create(a2, HKEY_LOCAL_MACHINE, (LPCWSTR)Block, v7, 1u, 0x2001Fu, v9, &v12) )
    {
      v6 = -2147467259;
      goto LABEL_10;
    }
    free(Block);
    ATL::CStringData::Release((ATL::CStringData *)(v13 - 12));
    return 0;
  }
}

```

## disassembly

```asm
0x1400252a8  mov     [rsp-18h+Block], rcx
0x1400252ad  push    rbp
0x1400252ae  push    rsi
0x1400252af  push    rdi
0x1400252b0  mov     rbp, rsp
0x1400252b3  sub     rsp, 50h
0x1400252b7  lea     rcx, [rbp+arg_18]
0x1400252bb  mov     rsi, rdx
0x1400252be  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x1400252c3  mov     r11d, 7FFFFFFFh
0x1400252c9  mov     [rbp+Block], 0
0x1400252d1  mov     edx, r11d; unsigned __int64
0x1400252d4  mov     [rbp+var_10], 0
0x1400252dc  lea     r8, [rbp+Block]; unsigned __int64 *
0x1400252e0  lea     rcx, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x1400252e7  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1400252ec  test    eax, eax
0x1400252ee  js      loc_1400253DE
0x1400252f4  mov     rcx, [rbp+arg_18]; unsigned __int16 *
0x1400252f8  lea     r8, [rbp+var_10]; unsigned __int64 *
0x1400252fc  mov     edx, r11d; unsigned __int64
0x1400252ff  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x140025304  test    eax, eax
0x140025306  js      loc_1400253DE
0x14002530c  mov     rdi, [rbp+var_10]
0x140025310  add     rdi, [rbp+Block]
0x140025314  cmp     rdi, [rbp+Block]
0x140025318  jb      loc_1400253DE
0x14002531e  mov     rdx, rdi
0x140025321  mov     [rbp+Block], 0
0x140025329  lea     rcx, [rbp+Block]
0x14002532d  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x140025332  test    al, al
0x140025334  jnz     short loc_14002533D
0x140025336  mov     edi, 8007000Eh
0x14002533b  jmp     short loc_1400253A8
0x14002533d  mov     r9, [rbp+arg_18]
0x140025341  lea     r8, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x140025348  mov     rcx, [rbp+Block]; unsigned __int16 *
0x14002534c  mov     rdx, rdi; unsigned __int64
0x14002534f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140025354  test    eax, eax
0x140025356  js      short loc_1400253A3
0x140025358  mov     r8, [rbp+Block]; lpSubKey
0x14002535c  mov     edi, 2001Fh
0x140025361  mov     r9d, edi; unsigned int
0x140025364  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14002536b  mov     rcx, rsi; this
0x14002536e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140025373  test    eax, eax
0x140025375  jz      short loc_1400253C3
0x140025377  mov     r8, [rbp+Block]; lpSubKey
0x14002537b  lea     rax, [rbp+arg_10]
0x14002537f  mov     [rsp+50h+var_18], rax; unsigned int *
0x140025384  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14002538b  mov     [rsp+50h+var_28], edi; REGSAM
0x14002538f  mov     rcx, rsi; this
0x140025392  mov     [rsp+50h+var_30], 1; DWORD
0x14002539a  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x14002539f  test    eax, eax
0x1400253a1  jz      short loc_1400253C3
0x1400253a3  mov     edi, 80004005h
0x1400253a8  mov     rcx, [rbp+Block]; Block
0x1400253ac  call    cs:__imp_free
0x1400253b2  mov     rcx, [rbp+arg_18]
0x1400253b6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400253ba  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400253bf  mov     eax, edi
0x1400253c1  jmp     short loc_1400253F0
0x1400253c3  mov     rcx, [rbp+Block]; Block
0x1400253c7  call    cs:__imp_free
0x1400253cd  mov     rcx, [rbp+arg_18]
0x1400253d1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400253d5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400253da  xor     eax, eax
0x1400253dc  jmp     short loc_1400253F0
0x1400253de  mov     rcx, [rbp+arg_18]
0x1400253e2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400253e6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400253eb  mov     eax, 80004005h
0x1400253f0  add     rsp, 50h
0x1400253f4  pop     rdi
0x1400253f5  pop     rsi
0x1400253f6  pop     rbp
0x1400253f7  retn
```
