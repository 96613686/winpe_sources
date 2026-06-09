# PackageCopier::CopyFileW(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18003ae84`
- end: `0x18003b11a`
- name: `?CopyFileW@PackageCopier@@QEAAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `662`
- prototype: `__int64 __fastcall(const WCHAR *, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800172e8`

## callees

- `0x180001008`
- `0x18000109c`
- `0x1800011ac`
- `0x1800017f4`
- `0x1800018ec`
- `0x1800071a4`
- `0x18000b140`
- `0x180021cf4`
- `0x18003ae84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003af76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b08d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003af76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b08d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003aead`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003af33`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003aead`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003af33`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003af5a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003af5a`
- `api-ms-win-core-file-l2-1-0!CopyFile2` at `0x18003af14`
- `api-ms-win-core-file-l2-1-0!CopyFile2` at `0x18003af14`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PackageCopier::CopyFileW(const WCHAR *a1, const WCHAR *a2, __int64 a3)
{
  const WCHAR *v4; // rbx
  const WCHAR *v5; // rcx
  int v6; // r9d
  const WCHAR *v8; // rdx
  const WCHAR *v9; // rcx
  HRESULT v10; // esi
  const WCHAR *v11; // rcx
  DWORD FileAttributesW; // eax
  DWORD v13; // eax
  const WCHAR *v14; // rcx
  signed int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rax
  __int64 v18; // rax
  int v19; // r9d
  unsigned int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // r8
  int v25; // r9d
  unsigned int v26; // eax
  signed int LastError; // eax
  unsigned int v28; // ebx
  __int64 v29; // rax
  __int64 v30; // rax
  int v31; // r9d
  unsigned int v32; // eax
  int v33; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  const WCHAR *v35; // [rsp+60h] [rbp+20h] BYREF
  char v36; // [rsp+68h] [rbp+28h] BYREF
  char v37; // [rsp+78h] [rbp+38h] BYREF

  v35 = a1;
  v4 = a2;
  if ( *((_QWORD *)a2 + 3) < 8u )
    v5 = a2;
  else
    v5 = *(const WCHAR **)a2;
  if ( (GetFileAttributesW(v5) & 0x10) != 0 )
  {
    if ( (unsigned int)dword_18005A000 > 3 )
    {
      if ( *((_QWORD *)v4 + 3) >= 8u )
        v4 = *(const WCHAR **)v4;
      v35 = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (unsigned int)&dword_18005A000,
        (unsigned int)word_1800504DA,
        0,
        v6,
        (__int64)&v35);
    }
    return 0;
  }
  else
  {
    if ( *(_QWORD *)(a3 + 24) < 8u )
      v8 = (const WCHAR *)a3;
    else
      v8 = *(const WCHAR **)a3;
    if ( *((_QWORD *)v4 + 3) < 8u )
      v9 = v4;
    else
      v9 = *(const WCHAR **)v4;
    v10 = CopyFile2(v9, v8, 0);
    if ( v10 < 0 )
    {
      if ( (unsigned int)dword_18005A000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18005A000, 0) )
      {
        LODWORD(v35) = v10;
        v21 = std::wstring::c_str(a3);
        _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v36, v21);
        v22 = std::wstring::c_str(v4);
        v23 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v37, v22);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (unsigned int)&v35,
          (unsigned int)byte_18005048D,
          v24,
          v25,
          v23,
          v24,
          (__int64)&v35);
      }
      v26 = wil::verify_hresult<long>((unsigned int)v10);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecopier.cpp",
        (const char *)v26,
        v33);
    }
    if ( *(_QWORD *)(a3 + 24) < 8u )
      v11 = (const WCHAR *)a3;
    else
      v11 = *(const WCHAR **)a3;
    FileAttributesW = GetFileAttributesW(v11);
    if ( FileAttributesW == -1 )
    {
      LastError = GetLastError();
      v28 = LastError;
      if ( LastError > 0 )
        v28 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)dword_18005A000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18005A000, 0) )
      {
        LODWORD(v35) = v28;
        v29 = std::wstring::c_str(a3);
        v30 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v36, v29);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18005A000,
          (unsigned int)byte_18005040B,
          0,
          v31,
          v30,
          (__int64)&v35);
      }
      v32 = wil::verify_hresult<long>(v28);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF5,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecopier.cpp",
        (const char *)v32,
        v33);
    }
    if ( (FileAttributesW & 1) != 0 )
    {
      v13 = FileAttributesW & 0xFFFFFFFE;
      v14 = *(_QWORD *)(a3 + 24) < 8u ? (const WCHAR *)a3 : *(const WCHAR **)a3;
      if ( !SetFileAttributesW(v14, v13) )
      {
        v15 = GetLastError();
        v16 = v15;
        if ( v15 > 0 )
          v16 = (unsigned __int16)v15 | 0x80070000;
        if ( (unsigned int)dword_18005A000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18005A000, 0) )
        {
          LODWORD(v35) = v16;
          v17 = std::wstring::c_str(a3);
          v18 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v36, v17);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18005A000,
            (unsigned int)&dword_18005044C,
            0,
            v19,
            v18,
            (__int64)&v35);
        }
        v20 = wil::verify_hresult<long>(v16);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x103,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecopier.cpp",
          (const char *)v20,
          v33);
      }
    }
    return 1;
  }
}

```

## disassembly

```asm
0x18003ae84  mov     [rsp-18h+arg_10], rbx
0x18003ae89  mov     [rsp-18h+arg_0], rcx
0x18003ae8e  push    rbp
0x18003ae8f  push    rsi
0x18003ae90  push    rdi
0x18003ae91  mov     rbp, rsp
0x18003ae94  sub     rsp, 40h
0x18003ae98  cmp     qword ptr [rdx+18h], 8
0x18003ae9d  mov     rdi, r8
0x18003aea0  mov     rbx, rdx
0x18003aea3  jb      short loc_18003AEAA
0x18003aea5  mov     rcx, [rdx]
0x18003aea8  jmp     short loc_18003AEAD
0x18003aeaa  mov     rcx, rbx; lpFileName
0x18003aead  call    cs:__imp_GetFileAttributesW
0x18003aeb3  test    al, 10h
0x18003aeb5  jz      short loc_18003AEF3
0x18003aeb7  mov     eax, cs:dword_18005A000
0x18003aebd  cmp     eax, 3
0x18003aec0  jbe     short loc_18003AEEF
0x18003aec2  cmp     qword ptr [rbx+18h], 8
0x18003aec7  jb      short loc_18003AECC
0x18003aec9  mov     rbx, [rbx]
0x18003aecc  lea     rax, [rbp+arg_0]
0x18003aed0  mov     [rbp+arg_0], rbx
0x18003aed4  xor     r8d, r8d
0x18003aed7  mov     qword ptr [rsp+40h+var_20], rax
0x18003aedc  lea     rdx, word_1800504DA
0x18003aee3  lea     rcx, dword_18005A000
0x18003aeea  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003aeef  xor     eax, eax
0x18003aef1  jmp     short loc_18003AF69
0x18003aef3  cmp     qword ptr [rdi+18h], 8
0x18003aef8  jb      short loc_18003AEFF
0x18003aefa  mov     rdx, [rdi]
0x18003aefd  jmp     short loc_18003AF02
0x18003aeff  mov     rdx, rdi; pwszNewFileName
0x18003af02  cmp     qword ptr [rbx+18h], 8
0x18003af07  jb      short loc_18003AF0E
0x18003af09  mov     rcx, [rbx]
0x18003af0c  jmp     short loc_18003AF11
0x18003af0e  mov     rcx, rbx; pwszExistingFileName
0x18003af11  xor     r8d, r8d; pExtendedParameters
0x18003af14  call    cs:__imp_CopyFile2
0x18003af1a  mov     esi, eax
0x18003af1c  test    eax, eax
0x18003af1e  js      loc_18003B003
0x18003af24  cmp     qword ptr [rdi+18h], 8
0x18003af29  jb      short loc_18003AF30
0x18003af2b  mov     rcx, [rdi]
0x18003af2e  jmp     short loc_18003AF33
0x18003af30  mov     rcx, rdi; lpFileName
0x18003af33  call    cs:__imp_GetFileAttributesW
0x18003af39  cmp     eax, 0FFFFFFFFh
0x18003af3c  jz      loc_18003B08D
0x18003af42  test    al, 1
0x18003af44  jz      short loc_18003AF64
0x18003af46  and     eax, 0FFFFFFFEh
0x18003af49  cmp     qword ptr [rdi+18h], 8
0x18003af4e  jb      short loc_18003AF55
0x18003af50  mov     rcx, [rdi]
0x18003af53  jmp     short loc_18003AF58
0x18003af55  mov     rcx, rdi; lpFileName
0x18003af58  mov     edx, eax; dwFileAttributes
0x18003af5a  call    cs:__imp_SetFileAttributesW
0x18003af60  test    eax, eax
0x18003af62  jz      short loc_18003AF76
0x18003af64  mov     eax, 1
0x18003af69  mov     rbx, [rsp+40h+arg_10]
0x18003af6e  add     rsp, 40h
0x18003af72  pop     rdi
0x18003af73  pop     rsi
0x18003af74  pop     rbp
0x18003af75  retn
0x18003af76  call    cs:__imp_GetLastError
0x18003af7c  mov     ebx, eax
0x18003af7e  test    eax, eax
0x18003af80  jle     short loc_18003AF8B
0x18003af82  movzx   ebx, ax
0x18003af85  or      ebx, 80070000h
0x18003af8b  mov     eax, cs:dword_18005A000
0x18003af91  cmp     eax, 2
0x18003af94  jbe     short loc_18003AFE3
0x18003af96  xor     edx, edx
0x18003af98  lea     rcx, dword_18005A000
0x18003af9f  call    _tlgKeywordOn
0x18003afa4  test    al, al
0x18003afa6  jz      short loc_18003AFE3
0x18003afa8  mov     rcx, rdi
0x18003afab  mov     dword ptr [rbp+arg_0], ebx
0x18003afae  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18003afb3  mov     rdx, rax
0x18003afb6  lea     rcx, [rbp+arg_8]
0x18003afba  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18003afbf  lea     rcx, [rbp+arg_0]
0x18003afc3  xor     r8d, r8d
0x18003afc6  mov     [rsp+40h+var_18], rcx
0x18003afcb  lea     rdx, dword_18005044C
0x18003afd2  lea     rcx, dword_18005A000
0x18003afd9  mov     qword ptr [rsp+40h+var_20], rax; int
0x18003afde  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003afe3  mov     ecx, ebx
0x18003afe5  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18003afea  mov     rcx, [rbp+18h]; this
0x18003afee  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x18003aff5  mov     r9d, eax; char *
0x18003aff8  mov     edx, 103h; void *
0x18003affd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003b003  mov     ecx, cs:dword_18005A000
0x18003b009  cmp     ecx, 2
0x18003b00c  jbe     short loc_18003B06D
0x18003b00e  xor     edx, edx
0x18003b010  lea     rcx, dword_18005A000
0x18003b017  call    _tlgKeywordOn
0x18003b01c  test    al, al
0x18003b01e  jz      short loc_18003B06D
0x18003b020  mov     rcx, rdi
0x18003b023  mov     dword ptr [rbp+arg_0], esi
0x18003b026  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18003b02b  mov     rdx, rax
0x18003b02e  lea     rcx, [rbp+arg_8]
0x18003b032  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18003b037  mov     rcx, rbx
0x18003b03a  mov     r8, rax
0x18003b03d  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18003b042  mov     rdx, rax
0x18003b045  lea     rcx, [rbp+arg_18]
0x18003b049  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18003b04e  lea     rcx, [rbp+arg_0]
0x18003b052  mov     [rsp+40h+var_10], rcx
0x18003b057  lea     rdx, byte_18005048D
0x18003b05e  mov     [rsp+40h+var_18], r8
0x18003b063  mov     qword ptr [rsp+40h+var_20], rax; int
0x18003b068  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003b06d  mov     ecx, esi
0x18003b06f  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18003b074  mov     rcx, [rbp+18h]; this
0x18003b078  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x18003b07f  mov     r9d, eax; char *
0x18003b082  mov     edx, 0E8h; void *
0x18003b087  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003b08d  call    cs:__imp_GetLastError
0x18003b093  mov     ebx, eax
0x18003b095  test    eax, eax
0x18003b097  jle     short loc_18003B0A2
0x18003b099  movzx   ebx, ax
0x18003b09c  or      ebx, 80070000h
0x18003b0a2  mov     eax, cs:dword_18005A000
0x18003b0a8  cmp     eax, 2
0x18003b0ab  jbe     short loc_18003B0FA
0x18003b0ad  xor     edx, edx
0x18003b0af  lea     rcx, dword_18005A000
0x18003b0b6  call    _tlgKeywordOn
0x18003b0bb  test    al, al
0x18003b0bd  jz      short loc_18003B0FA
0x18003b0bf  mov     rcx, rdi
0x18003b0c2  mov     dword ptr [rbp+arg_0], ebx
0x18003b0c5  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18003b0ca  mov     rdx, rax
0x18003b0cd  lea     rcx, [rbp+arg_8]
0x18003b0d1  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18003b0d6  lea     rcx, [rbp+arg_0]
0x18003b0da  xor     r8d, r8d
0x18003b0dd  mov     [rsp+40h+var_18], rcx
0x18003b0e2  lea     rdx, byte_18005040B
0x18003b0e9  lea     rcx, dword_18005A000
0x18003b0f0  mov     qword ptr [rsp+40h+var_20], rax; int
0x18003b0f5  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003b0fa  mov     ecx, ebx
0x18003b0fc  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18003b101  mov     rcx, [rbp+18h]; this
0x18003b105  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x18003b10c  mov     r9d, eax; char *
0x18003b10f  mov     edx, 0F5h; void *
0x18003b114  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
