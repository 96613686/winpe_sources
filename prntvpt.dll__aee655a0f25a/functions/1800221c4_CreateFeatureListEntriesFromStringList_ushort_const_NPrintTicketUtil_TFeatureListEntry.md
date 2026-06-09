# CreateFeatureListEntriesFromStringList(ushort const * *,NPrintTicketUtil::TFeatureListEntry * *)

- ea: `0x1800221c4`
- end: `0x1800222cf`
- name: `?CreateFeatureListEntriesFromStringList@@YAJPEAPEBGPEAPEAVTFeatureListEntry@NPrintTicketUtil@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(const unsigned __int16 **, struct NPrintTicketUtil::TFeatureListEntry **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800222d8`

## callees

- `0x180005aa4`
- `0x18000f53c`
- `0x1800221c4`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180022232`
- `OLEAUT32!__imp_SysAllocString` at `0x180022248`
- `OLEAUT32!__imp_SysAllocString` at `0x180022232`
- `OLEAUT32!__imp_SysAllocString` at `0x180022248`

## string_xrefs

- `0x180022241`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall CreateFeatureListEntriesFromStringList(
        const unsigned __int16 **a1,
        struct NPrintTicketUtil::TFeatureListEntry **a2)
{
  int v2; // edi
  struct NPrintTicketUtil::TFeatureListEntry *v4; // rsi
  void (__fastcall ***v6)(void *, __int64); // rbx
  BSTR v7; // rax
  BSTR v8; // rax
  struct NPrintTicketUtil::TFeatureListEntry *v9; // rbx

  v2 = 0;
  v4 = 0;
  while ( *a1 )
  {
    v6 = (void (__fastcall ***)(void *, __int64))operator new(0x38u);
    if ( !v6 )
    {
      v6 = 0;
LABEL_9:
      v2 = -2147024882;
      if ( !v6 )
        break;
LABEL_10:
      (**v6)(v6, 1);
      break;
    }
    v6[1] = 0;
    *v6 = (void (__fastcall **)(void *, __int64))&NPrintTicketUtil::TFeatureListEntry::`vftable';
    v6[2] = 0;
    v6[3] = 0;
    v6[4] = 0;
    *((_DWORD *)v6 + 10) = 0;
    v6[6] = 0;
    v7 = SysAllocString(*a1);
    v6[3] = (void (__fastcall **)(void *, __int64))v7;
    if ( !v7 )
      goto LABEL_9;
    v8 = SysAllocString(L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords");
    v6[2] = (void (__fastcall **)(void *, __int64))v8;
    if ( !v8 )
      goto LABEL_9;
    v2 = NPrintTicketUtil::TFeatureListEntry::ConfigureScopePrefix((NPrintTicketUtil::TFeatureListEntry *)v6);
    if ( v2 < 0 )
      goto LABEL_10;
    v6[1] = (void (__fastcall **)(void *, __int64))v4;
    ++a1;
    v4 = (struct NPrintTicketUtil::TFeatureListEntry *)v6;
  }
  if ( v2 < 0 )
  {
    if ( v4 )
    {
      do
      {
        v9 = (struct NPrintTicketUtil::TFeatureListEntry *)*((_QWORD *)v4 + 1);
        (**(void (__fastcall ***)(struct NPrintTicketUtil::TFeatureListEntry *, __int64))v4)(v4, 1);
        v4 = v9;
      }
      while ( v9 );
    }
    v4 = 0;
  }
  *a2 = v4;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800221c4  push    rbx
0x1800221c6  push    rsi
0x1800221c7  push    rdi
0x1800221c8  push    r14
0x1800221ca  push    r15
0x1800221cc  sub     rsp, 20h
0x1800221d0  xor     edi, edi
0x1800221d2  mov     r15, rdx
0x1800221d5  xor     esi, esi
0x1800221d7  mov     r14, rcx
0x1800221da  cmp     qword ptr [r14], 0
0x1800221de  jz      loc_180022294
0x1800221e4  mov     ecx, 38h ; '8'; Size
0x1800221e9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800221ee  mov     rbx, rax
0x1800221f1  test    rax, rax
0x1800221f4  jz      short loc_180022275
0x1800221f6  lea     rax, ??_7TFeatureListEntry@NPrintTicketUtil@@6B@; const NPrintTicketUtil::TFeatureListEntry::`vftable'
0x1800221fd  mov     qword ptr [rbx+8], 0
0x180022205  mov     [rbx], rax
0x180022208  mov     qword ptr [rbx+10h], 0
0x180022210  mov     qword ptr [rbx+18h], 0
0x180022218  mov     qword ptr [rbx+20h], 0
0x180022220  mov     dword ptr [rbx+28h], 0
0x180022227  mov     qword ptr [rbx+30h], 0
0x18002222f  mov     rcx, [r14]; psz
0x180022232  call    cs:__imp_SysAllocString
0x180022238  mov     [rbx+18h], rax
0x18002223c  test    rax, rax
0x18002223f  jz      short loc_180022277
0x180022241  lea     rcx, aHttpSchemasMic_3; "http://schemas.microsoft.com/windows/20"...
0x180022248  call    cs:__imp_SysAllocString
0x18002224e  mov     [rbx+10h], rax
0x180022252  test    rax, rax
0x180022255  jz      short loc_180022277
0x180022257  mov     rcx, rbx; this
0x18002225a  call    ?ConfigureScopePrefix@TFeatureListEntry@NPrintTicketUtil@@QEAAJXZ; NPrintTicketUtil::TFeatureListEntry::ConfigureScopePrefix(void)
0x18002225f  mov     edi, eax
0x180022261  test    eax, eax
0x180022263  js      short loc_180022281
0x180022265  mov     [rbx+8], rsi
0x180022269  add     r14, 8
0x18002226d  mov     rsi, rbx
0x180022270  jmp     loc_1800221DA
0x180022275  xor     ebx, ebx
0x180022277  mov     edi, 8007000Eh
0x18002227c  test    rbx, rbx
0x18002227f  jz      short loc_180022294
0x180022281  mov     rax, [rbx]
0x180022284  mov     edx, 1
0x180022289  mov     rcx, rbx
0x18002228c  mov     rax, [rax]
0x18002228f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022294  test    edi, edi
0x180022296  jns     short loc_1800222BE
0x180022298  test    rsi, rsi
0x18002229b  jz      short loc_1800222BC
0x18002229d  mov     rax, [rsi]
0x1800222a0  mov     edx, 1
0x1800222a5  mov     rbx, [rsi+8]
0x1800222a9  mov     rcx, rsi
0x1800222ac  mov     rax, [rax]
0x1800222af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222b4  mov     rsi, rbx
0x1800222b7  test    rbx, rbx
0x1800222ba  jnz     short loc_18002229D
0x1800222bc  xor     esi, esi
0x1800222be  mov     [r15], rsi
0x1800222c1  mov     eax, edi
0x1800222c3  add     rsp, 20h
0x1800222c7  pop     r15
0x1800222c9  pop     r14
0x1800222cb  pop     rdi
0x1800222cc  pop     rsi
0x1800222cd  pop     rbx
0x1800222ce  retn
```
