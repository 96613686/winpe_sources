# MdmLogCollector::GenerateMetadataFile(_iobuf *,ushort const *)

- ea: `0x180110218`
- end: `0x18011039b`
- name: `?GenerateMetadataFile@MdmLogCollector@@AEAAJPEAU_iobuf@@PEBG@Z`
- size: `387`
- prototype: `int(MdmLogCollector *__hidden this, struct _iobuf *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18010bd00`

## callees

- `0x180019080`
- `0x18001a0dc`
- `0x1800e68b0`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00e4`
- `0x180110218`
- `0x180111ec4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18011027a`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18011027a`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180110362`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180110362`

## string_xrefs

- `0x180110247`: `MdmDiagLogMetadata.json`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall MdmLogCollector::GenerateMetadataFile(
        MdmLogCollector *this,
        struct _iobuf *a2,
        const unsigned __int16 *a3)
{
  const wchar_t *v5; // rax
  errno_t v6; // r14d
  __int64 v7; // rdx
  unsigned int v8; // edi
  unsigned __int64 v9; // rsi
  __int64 v10; // rax
  const wchar_t *v11; // rdx
  __int64 v12; // rax
  FILE *Stream; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v15[32]; // [rsp+30h] [rbp-58h] BYREF

  std::wstring::wstring(v15, a3);
  std::wstring::append(v15, L"MdmDiagLogMetadata.json");
  Stream = 0;
  v5 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
  v6 = _wfopen_s(&Stream, v5, L"a+");
  fwprintf_s(Stream, L"{\n");
  v7 = *((_QWORD *)this + 16);
  if ( (*((_QWORD *)this + 17) - v7) >> 5 )
  {
    v8 = 0;
    v9 = 0;
    do
    {
      v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7 + 32 * v9);
      fwprintf_s(Stream, L"  %s", v10);
      v11 = L",\n";
      if ( v9 >= ((__int64)(*((_QWORD *)this + 17) - *((_QWORD *)this + 16)) >> 5) - 1 )
        v11 = L"\n";
      fwprintf_s(Stream, v11);
      ++v8;
      v7 = *((_QWORD *)this + 16);
      v9 = v8;
    }
    while ( v8 < (unsigned __int64)((*((_QWORD *)this + 17) - v7) >> 5) );
  }
  fwprintf_s(Stream, L"}\n");
  v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
  MdmLogCollector::WriteToFile(a2, L"metadataFile generated:%s\n", v12);
  if ( !v6 )
    fclose(Stream);
  std::wstring::_Tidy_deallocate(v15);
  return 0;
}

```

## disassembly

```asm
0x180110218  push    rbx
0x18011021a  push    rsi
0x18011021b  push    rdi
0x18011021c  push    r14
0x18011021e  push    r15
0x180110220  sub     rsp, 60h
0x180110224  mov     rax, cs:__security_cookie
0x18011022b  xor     rax, rsp
0x18011022e  mov     [rsp+88h+var_38], rax
0x180110233  mov     r15, rdx
0x180110236  mov     rbx, rcx
0x180110239  mov     rdx, r8
0x18011023c  lea     rcx, [rsp+88h+var_58]
0x180110241  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180110246  nop
0x180110247  lea     rdx, aMdmdiaglogmeta; "MdmDiagLogMetadata.json"
0x18011024e  lea     rcx, [rsp+88h+var_58]
0x180110253  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180110258  mov     [rsp+88h+Stream], 0
0x180110261  lea     rcx, [rsp+88h+var_58]
0x180110266  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011026b  mov     rdx, rax; FileName
0x18011026e  lea     r8, aA; "a+"
0x180110275  lea     rcx, [rsp+88h+Stream]; Stream
0x18011027a  call    cs:__imp__wfopen_s
0x180110281  nop     dword ptr [rax+rax+00h]
0x180110286  mov     r14d, eax
0x180110289  lea     rdx, asc_1801D3F74; "{\n"
0x180110290  mov     rcx, [rsp+88h+Stream]; Stream
0x180110295  call    fwprintf_s
0x18011029a  mov     rdx, [rbx+80h]
0x1801102a1  mov     rcx, [rbx+88h]
0x1801102a8  sub     rcx, rdx
0x1801102ab  sar     rcx, 5
0x1801102af  test    rcx, rcx
0x1801102b2  jz      short loc_18011032B
0x1801102b4  xor     edi, edi
0x1801102b6  xor     esi, esi
0x1801102b8  mov     rcx, rsi
0x1801102bb  shl     rcx, 5
0x1801102bf  add     rcx, rdx
0x1801102c2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801102c7  mov     r8, rax
0x1801102ca  lea     rdx, aS_0; "  %s"
0x1801102d1  mov     rcx, [rsp+88h+Stream]; Stream
0x1801102d6  call    fwprintf_s
0x1801102db  mov     rax, [rbx+88h]
0x1801102e2  sub     rax, [rbx+80h]
0x1801102e9  sar     rax, 5
0x1801102ed  dec     rax
0x1801102f0  mov     rcx, [rsp+88h+Stream]; Stream
0x1801102f5  cmp     rsi, rax
0x1801102f8  lea     rdx, asc_1801D3F84; ",\n"
0x1801102ff  jb      short loc_180110308
0x180110301  lea     rdx, asc_1801BBCF8; "\n"
0x180110308  call    fwprintf_s
0x18011030d  inc     edi
0x18011030f  mov     rdx, [rbx+80h]
0x180110316  mov     esi, edi
0x180110318  mov     rax, [rbx+88h]
0x18011031f  sub     rax, rdx
0x180110322  sar     rax, 5
0x180110326  cmp     rsi, rax
0x180110329  jb      short loc_1801102B8
0x18011032b  lea     rdx, asc_1801D3F7C; "}\n"
0x180110332  mov     rcx, [rsp+88h+Stream]; Stream
0x180110337  call    fwprintf_s
0x18011033c  lea     rcx, [rsp+88h+var_58]
0x180110341  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180110346  mov     r8, rax
0x180110349  lea     rdx, aMetadatafileGe; "metadataFile generated:%s\n"
0x180110350  mov     rcx, r15; struct _iobuf *
0x180110353  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x180110358  test    r14d, r14d
0x18011035b  jnz     short loc_18011036F
0x18011035d  mov     rcx, [rsp+88h+Stream]; Stream
0x180110362  call    cs:__imp_fclose
0x180110369  nop     dword ptr [rax+rax+00h]
0x18011036e  nop
0x18011036f  lea     rcx, [rsp+88h+var_58]
0x180110374  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180110379  xor     eax, eax
0x18011037b  jmp     short loc_180110381
0x18011037d  mov     eax, [rsp+88h+var_60]
0x180110381  mov     rcx, [rsp+88h+var_38]
0x180110386  xor     rcx, rsp; StackCookie
0x180110389  call    __security_check_cookie
0x18011038e  add     rsp, 60h
0x180110392  pop     r15
0x180110394  pop     r14
0x180110396  pop     rdi
0x180110397  pop     rsi
0x180110398  pop     rbx
0x180110399  retn
```
