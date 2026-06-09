# DisablePerfLibrary(EXT_OBJECT *,ulong,ulong,unsigned __int64,unsigned __int64)

- ea: `0x18000b0e8`
- end: `0x18000b1f5`
- name: `?DisablePerfLibrary@@YAXPEAUEXT_OBJECT@@KK_K1@Z`
- size: `269`
- prototype: `void(struct EXT_OBJECT *, unsigned int, unsigned int, unsigned __int64, unsigned __int64)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000b8a0`
- `0x1800119fc`
- `0x180011d10`
- `0x1800126c8`
- `0x18001277c`
- `0x1800136b0`

## callees

- `0x18000113c`
- `0x180001210`
- `0x18000b008`
- `0x18000b0e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000b17f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000b17f`

## pseudocode

```c
void __fastcall DisablePerfLibrary(struct EXT_OBJECT *a1, int a2, int a3, __int64 a4, unsigned __int64 a5)
{
  int v8; // eax
  unsigned __int16 *v10; // rdx
  __int64 v11; // rcx
  const wchar_t *v12; // rcx
  wchar_t *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 *v17; // rax
  int v18; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int64 v19; // [rsp+58h] [rbp-30h] BYREF
  __int64 v20; // [rsp+60h] [rbp-28h] BYREF
  __int64 *v21; // [rsp+68h] [rbp-20h] BYREF
  __int64 v22; // [rsp+70h] [rbp-18h] BYREF

  if ( (lPerflibConfigFlags & 2) == 0 )
  {
    v8 = *((_DWORD *)a1 + 95);
    if ( (v8 & 0x10) == 0 )
    {
      v10 = (unsigned __int16 *)*((_QWORD *)a1 + 49);
      *((_DWORD *)a1 + 95) = v8 | 0x10;
      DisableLibrary(*((HKEY *)a1 + 13), v10, a2);
      if ( (unsigned int)dword_18002B048 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
        {
          v12 = (const wchar_t *)*((_QWORD *)a1 + 12);
          v19 = a5;
          v20 = a4;
          v18 = a3;
          v13 = wcsrchr(v12, 0x5Cu);
          if ( v13 )
            v17 = (__int64 *)(v13 + 1);
          else
            v17 = (__int64 *)*((_QWORD *)a1 + 12);
          v21 = v17;
          v22 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            v14,
            (unsigned __int8 *)byte_180026261,
            v15,
            v16,
            (__int64)&v22,
            &v21,
            (__int64)&v18,
            (__int64)&v20,
            (__int64)&v19);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18000b0e8  mov     [rsp+arg_0], rbx
0x18000b0ed  mov     [rsp+arg_8], rsi
0x18000b0f2  push    rdi
0x18000b0f3  sub     rsp, 80h
0x18000b0fa  test    byte ptr cs:?lPerflibConfigFlags@@3JA, 2; long lPerflibConfigFlags
0x18000b101  mov     rdi, r9
0x18000b104  mov     esi, r8d
0x18000b107  mov     rbx, rcx
0x18000b10a  jnz     loc_18000B1E0
0x18000b110  mov     eax, [rcx+17Ch]
0x18000b116  test    al, 10h
0x18000b118  jnz     loc_18000B1E0
0x18000b11e  or      eax, 10h
0x18000b121  mov     r8d, edx; unsigned int
0x18000b124  mov     rdx, [rcx+188h]; unsigned __int16 *
0x18000b12b  mov     [rcx+17Ch], eax
0x18000b131  mov     rcx, [rcx+68h]; hKey
0x18000b135  call    ?DisableLibrary@@YAKPEAUHKEY__@@PEAGK@Z; DisableLibrary(HKEY__ *,ushort *,ulong)
0x18000b13a  mov     eax, cs:dword_18002B048
0x18000b140  cmp     eax, 5
0x18000b143  jbe     loc_18000B1E0
0x18000b149  mov     rdx, 400000000000h
0x18000b153  call    _tlgKeywordOn
0x18000b158  test    al, al
0x18000b15a  jz      loc_18000B1E0
0x18000b160  mov     rax, [rsp+88h+arg_20]
0x18000b168  mov     edx, 5Ch ; '\'; Ch
0x18000b16d  mov     rcx, [rbx+60h]; Str
0x18000b171  mov     [rsp+88h+var_30], rax
0x18000b176  mov     [rsp+88h+var_28], rdi
0x18000b17b  mov     [rsp+88h+var_38], esi
0x18000b17f  call    cs:__imp_wcsrchr
0x18000b185  test    rax, rax
0x18000b188  jz      short loc_18000B190
0x18000b18a  add     rax, 2
0x18000b18e  jmp     short loc_18000B194
0x18000b190  mov     rax, [rbx+60h]
0x18000b194  mov     [rsp+88h+var_20], rax
0x18000b199  lea     rdx, byte_180026261
0x18000b1a0  lea     rax, [rsp+88h+var_30]
0x18000b1a5  mov     [rsp+88h+var_18], 1000000h
0x18000b1ae  mov     [rsp+88h+var_48], rax
0x18000b1b3  lea     rax, [rsp+88h+var_28]
0x18000b1b8  mov     [rsp+88h+var_50], rax
0x18000b1bd  lea     rax, [rsp+88h+var_38]
0x18000b1c2  mov     [rsp+88h+var_58], rax
0x18000b1c7  lea     rax, [rsp+88h+var_20]
0x18000b1cc  mov     [rsp+88h+var_60], rax
0x18000b1d1  lea     rax, [rsp+88h+var_18]
0x18000b1d6  mov     [rsp+88h+var_68], rax
0x18000b1db  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18000b1e0  lea     r11, [rsp+88h+var_8]
0x18000b1e8  mov     rbx, [r11+10h]
0x18000b1ec  mov     rsi, [r11+18h]
0x18000b1f0  mov     rsp, r11
0x18000b1f3  pop     rdi
0x18000b1f4  retn
```
