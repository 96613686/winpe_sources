# TMetabaseMetaXmlFile::CheckForOverrridingColumnMeta(TElement const &,ulong)

- ea: `0x18001bc88`
- end: `0x18001bd35`
- name: `?CheckForOverrridingColumnMeta@TMetabaseMetaXmlFile@@AEAAXAEBUTElement@@K@Z`
- size: `173`
- prototype: `void __fastcall(TMetabaseMetaXmlFile *__hidden this, const struct TElement *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800199c8`

## callees

- `0x18001bc88`
- `0x18001c814`
- `0x18001dd08`
- `0x180030010`

## pseudocode

```c
void __fastcall TMetabaseMetaXmlFile::CheckForOverrridingColumnMeta(
        TMetabaseMetaXmlFile *this,
        const struct TElement *a2,
        unsigned int a3)
{
  const struct TMetabaseMetaXmlFile::TAttr *Attribute; // rax
  const struct TMetabaseMetaXmlFile::TSizedString *v6; // rdi
  __int64 v7; // rsi
  int v8; // ebx
  unsigned int v9; // edi
  int v10; // eax
  __int64 v11; // rdx

  Attribute = TMetabaseMetaXmlFile::GetAttribute(this, a2, (TMetabaseMetaXmlFile *)((char *)this + 712));
  v6 = (const struct TMetabaseMetaXmlFile::TAttr *)((char *)Attribute + 16);
  if ( *((_QWORD *)Attribute + 3) )
  {
    v7 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 176LL))(this, a3);
    v8 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 152LL))(
           this,
           *(unsigned int *)(v7 + 48));
    v9 = v8 | TMetabaseMetaXmlFile::StringToFlagValue(this, v6, L"COLUMNMETA", 12);
    v10 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 152LL))(
            this,
            *(unsigned int *)(v7 + 48));
    v11 = v9;
    LODWORD(v11) = v9 | 0x100;
    if ( v10 == v9 )
      v11 = v9;
    *(_DWORD *)(v7 + 48) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64))(*(_QWORD *)this + 16LL))(
                             this,
                             v11);
  }
}

```

## disassembly

```asm
0x18001bc88  push    rbx
0x18001bc8a  push    rsi
0x18001bc8b  push    rdi
0x18001bc8c  push    r14
0x18001bc8e  sub     rsp, 28h
0x18001bc92  mov     ebx, r8d
0x18001bc95  mov     r14, rcx
0x18001bc98  lea     r8, [rcx+2C8h]; struct TMetabaseMetaXmlFile::TSizedString *
0x18001bc9f  call    ?GetAttribute@TMetabaseMetaXmlFile@@AEAAAEBUTAttr@1@AEBUTElement@@AEBUTSizedString@1@@Z; TMetabaseMetaXmlFile::GetAttribute(TElement const &,TMetabaseMetaXmlFile::TSizedString const &)
0x18001bca4  lea     rdi, [rax+10h]
0x18001bca8  cmp     qword ptr [rdi+8], 0
0x18001bcad  jz      short loc_18001BD2B
0x18001bcaf  mov     rax, [r14]
0x18001bcb2  mov     edx, ebx
0x18001bcb4  mov     rcx, r14
0x18001bcb7  mov     rax, [rax+0B0h]
0x18001bcbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcc3  mov     rcx, [r14]
0x18001bcc6  mov     rsi, rax
0x18001bcc9  mov     rax, [rcx+98h]
0x18001bcd0  mov     rcx, r14
0x18001bcd3  mov     edx, [rsi+30h]
0x18001bcd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcdb  mov     r9d, 0Ch; unsigned int
0x18001bce1  lea     r8, aColumnmeta; "COLUMNMETA"
0x18001bce8  mov     rdx, rdi; struct TMetabaseMetaXmlFile::TSizedString *
0x18001bceb  mov     rcx, r14; this
0x18001bcee  mov     ebx, eax
0x18001bcf0  call    ?StringToFlagValue@TMetabaseMetaXmlFile@@AEAAKAEBUTSizedString@1@PEBGK@Z; TMetabaseMetaXmlFile::StringToFlagValue(TMetabaseMetaXmlFile::TSizedString const &,ushort const *,ulong)
0x18001bcf5  mov     rcx, [r14]
0x18001bcf8  mov     edi, eax
0x18001bcfa  mov     edx, [rsi+30h]
0x18001bcfd  or      edi, ebx
0x18001bcff  mov     rax, [rcx+98h]
0x18001bd06  mov     rcx, r14
0x18001bd09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd0e  mov     edx, edi
0x18001bd10  mov     rcx, r14
0x18001bd13  bts     edx, 8
0x18001bd17  cmp     eax, edi
0x18001bd19  mov     rax, [r14]
0x18001bd1c  cmovz   edx, edi
0x18001bd1f  mov     rax, [rax+10h]
0x18001bd23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd28  mov     [rsi+30h], eax
0x18001bd2b  add     rsp, 28h
0x18001bd2f  pop     r14
0x18001bd31  pop     rdi
0x18001bd32  pop     rsi
0x18001bd33  pop     rbx
0x18001bd34  retn
```
