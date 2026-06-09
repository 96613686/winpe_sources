# ProvSession::CreateNewSessionId(void)

- ea: `0x180007cc0`
- end: `0x180008046`
- name: `?CreateNewSessionId@ProvSession@@AEAAJXZ`
- size: `902`
- prototype: `__int64 __fastcall(ProvSession *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180008050`

## callees

- `0x1800010c8`
- `0x1800026c8`
- `0x1800071b0`
- `0x180007cc0`
- `0x1800098dc`
- `0x180009924`
- `0x18000a18c`
- `0x18000a7f4`
- `0x18000b030`
- `0x18000b31c`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007d79`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007f92`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007d79`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007f92`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007e61`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007f65`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007e61`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007f65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e6e`

## pseudocode

```c
__int64 __fastcall ProvSession::CreateNewSessionId(ProvSession *this)
{
  _WORD *v2; // rcx
  TraceLoggingCorrelationVector *v3; // rax
  TraceLoggingCorrelationVector *v4; // rbx
  TraceLoggingCorrelationVector *v5; // rax
  int v6; // ebx
  __int64 v7; // rdx
  __int64 result; // rax
  unsigned __int64 v9; // rbx
  int v10; // eax
  __int64 v11; // r14
  signed int LastError; // eax
  unsigned int v13; // ecx
  char *v14; // r14
  int lpWideCharStr; // [rsp+20h] [rbp-E0h]
  TraceLoggingCorrelationVector *v16; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR v17[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h]
  TraceLoggingCorrelationVector **v19; // [rsp+58h] [rbp-A8h]
  __int64 v20; // [rsp+60h] [rbp-A0h]
  CHAR MultiByteStr[144]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  if ( (unsigned int)dword_18005A000 > 4 )
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004E4CB, 0, 0, 2, v17);
  if ( *((_QWORD *)this + 6) < 8u )
    v2 = (_WORD *)((char *)this + 24);
  else
    v2 = (_WORD *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 5) = 0;
  *v2 = 0;
  v3 = (TraceLoggingCorrelationVector *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  v16 = v3;
  if ( v3 )
    v4 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v3);
  else
    v4 = 0;
  v5 = (TraceLoggingCorrelationVector *)*((_QWORD *)this + 13);
  if ( v4 == v5 )
  {
    v4 = (TraceLoggingCorrelationVector *)*((_QWORD *)this + 13);
  }
  else
  {
    if ( v5 )
      operator delete(*((void **)this + 13));
    *((_QWORD *)this + 13) = v4;
  }
  if ( !v4 )
  {
    if ( (unsigned int)dword_18005A000 > 3 )
    {
      LODWORD(v16) = 0;
      v19 = &v16;
      v20 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, word_18004E282, 0, 0, 3, v17);
    }
    v6 = ProvSession::UseGuidAsSessionId(this);
    if ( v6 < 0 )
    {
      v7 = 237;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provsession.cpp",
        (const char *)(unsigned int)v6,
        lpWideCharStr);
      return (unsigned int)v6;
    }
  }
  if ( (unsigned int)dword_18005A000 > 4 )
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004E479, 0, 0, 2, v17);
  TraceLoggingCorrelationVector::ToString(*((TraceLoggingCorrelationVector **)this + 13), MultiByteStr);
  v9 = -1;
  v10 = MultiByteToWideChar(0xFDE9u, 0, MultiByteStr, -1, 0, 0);
  v11 = v10;
  if ( v10 )
  {
    if ( (unsigned int)dword_18005A000 > 4 )
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004E551, 0, 0, 2, v17);
    *(_OWORD *)v17 = 0;
    v18 = 0;
    std::vector<unsigned short>::resize(v17, v11);
    v14 = (char *)v17[0];
    MultiByteToWideChar(0xFDE9u, 0, MultiByteStr, -1, v17[0], (signed __int64)(v18 - (unsigned __int64)v17[0]) >> 1);
    if ( *(_WORD *)v14 )
    {
      do
        ++v9;
      while ( *(_WORD *)&v14[2 * v9] );
    }
    else
    {
      v9 = 0;
    }
    std::wstring::assign((_QWORD *)this + 3, v14, v9);
    operator delete(v14);
  }
  else
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_18005A000 > 3 )
    {
      LODWORD(v16) = v13;
      v19 = &v16;
      v20 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, &word_18004E51E, 0, 0, 3, v17);
    }
    v6 = ProvSession::UseGuidAsSessionId(this);
    if ( v6 < 0 )
    {
      v7 = 258;
      goto LABEL_19;
    }
  }
  if ( (unsigned int)dword_18005A000 > 4 )
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, &word_18004E35E, 0, 0, 2, v17);
  result = ProvSession::SaveSession(this);
  if ( (int)result < 0 )
  {
    if ( (unsigned int)dword_18005A000 > 3 )
    {
      LODWORD(v16) = result;
      v19 = &v16;
      v20 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004E38B, 0, 0, 3, v17);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180007cc0  push    rbp
0x180007cc2  push    rbx
0x180007cc3  push    rsi
0x180007cc4  push    rdi
0x180007cc5  push    r14
0x180007cc7  push    r15
0x180007cc9  lea     rbp, [rsp-18h]
0x180007cce  sub     rsp, 118h
0x180007cd5  mov     rax, cs:__security_cookie
0x180007cdc  xor     rax, rsp
0x180007cdf  mov     [rbp+40h+var_40], rax
0x180007ce3  mov     rdi, rcx
0x180007ce6  mov     eax, cs:dword_18005A000
0x180007cec  lea     r14, dword_18005A000
0x180007cf3  cmp     eax, 4
0x180007cf6  jbe     short loc_180007D1F
0x180007cf8  lea     rax, [rsp+140h+var_108]
0x180007cfd  mov     qword ptr [rsp+140h+cchWideChar], rax
0x180007d02  mov     dword ptr [rsp+140h+lpWideCharStr], 2
0x180007d0a  xor     r9d, r9d
0x180007d0d  xor     r8d, r8d
0x180007d10  lea     rdx, byte_18004E4CB
0x180007d17  mov     rcx, r14
0x180007d1a  call    _tlgWriteTransfer_EventWriteTransfer
0x180007d1f  lea     rsi, [rdi+18h]
0x180007d23  cmp     qword ptr [rsi+18h], 8
0x180007d28  jb      short loc_180007D2F
0x180007d2a  mov     rcx, [rsi]
0x180007d2d  jmp     short loc_180007D32
0x180007d2f  mov     rcx, rsi
0x180007d32  xor     r15d, r15d
0x180007d35  mov     [rsi+10h], r15
0x180007d39  mov     [rcx], r15w
0x180007d3d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007d44  mov     ecx, 90h; unsigned __int64
0x180007d49  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007d4e  mov     [rsp+140h+var_110], rax
0x180007d53  test    rax, rax
0x180007d56  jz      short loc_180007D65
0x180007d58  mov     rcx, rax; this
0x180007d5b  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180007d60  mov     rbx, rax
0x180007d63  jmp     short loc_180007D68
0x180007d65  mov     rbx, r15
0x180007d68  mov     rax, [rdi+68h]
0x180007d6c  cmp     rbx, rax
0x180007d6f  jz      short loc_180007D85
0x180007d71  test    rax, rax
0x180007d74  jz      short loc_180007D7F
0x180007d76  mov     rcx, rax
0x180007d79  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007d7f  mov     [rdi+68h], rbx
0x180007d83  jmp     short loc_180007D88
0x180007d85  mov     rbx, rax
0x180007d88  test    rbx, rbx
0x180007d8b  jnz     short loc_180007E04
0x180007d8d  mov     eax, cs:dword_18005A000
0x180007d93  cmp     eax, 3
0x180007d96  jbe     short loc_180007DD7
0x180007d98  mov     dword ptr [rsp+140h+var_110], r15d
0x180007d9d  lea     rax, [rsp+140h+var_110]
0x180007da2  mov     [rsp+140h+var_E8], rax
0x180007da7  mov     [rsp+140h+var_E0], 4
0x180007db0  lea     rax, [rsp+140h+var_108]
0x180007db5  mov     qword ptr [rsp+140h+cchWideChar], rax
0x180007dba  mov     dword ptr [rsp+140h+lpWideCharStr], 3; int
0x180007dc2  xor     r9d, r9d
0x180007dc5  xor     r8d, r8d
0x180007dc8  lea     rdx, word_18004E282
0x180007dcf  mov     rcx, r14
0x180007dd2  call    _tlgWriteTransfer_EventWriteTransfer
0x180007dd7  mov     rcx, rdi; this
0x180007dda  call    ?UseGuidAsSessionId@ProvSession@@AEAAJXZ; ProvSession::UseGuidAsSessionId(void)
0x180007ddf  mov     ebx, eax
0x180007de1  test    eax, eax
0x180007de3  jns     short loc_180007E04
0x180007de5  mov     edx, 0EDh; void *
0x180007dea  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180007df1  mov     r9d, ebx; char *
0x180007df4  mov     rcx, [rbp+48h]; this
0x180007df8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007dfd  mov     eax, ebx
0x180007dff  jmp     loc_18000802A
0x180007e04  mov     eax, cs:dword_18005A000
0x180007e0a  cmp     eax, 4
0x180007e0d  jbe     short loc_180007E36
0x180007e0f  lea     rax, [rsp+140h+var_108]
0x180007e14  mov     qword ptr [rsp+140h+cchWideChar], rax
0x180007e19  mov     dword ptr [rsp+140h+lpWideCharStr], 2
0x180007e21  xor     r9d, r9d
0x180007e24  xor     r8d, r8d
0x180007e27  lea     rdx, byte_18004E479
0x180007e2e  mov     rcx, r14
0x180007e31  call    _tlgWriteTransfer_EventWriteTransfer
0x180007e36  lea     rdx, [rsp+140h+MultiByteStr]; Destination
0x180007e3b  mov     rcx, [rdi+68h]; this
0x180007e3f  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x180007e44  mov     [rsp+140h+cchWideChar], r15d; cchWideChar
0x180007e49  mov     [rsp+140h+lpWideCharStr], r15; lpWideCharStr
0x180007e4e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180007e52  mov     r9d, ebx; cbMultiByte
0x180007e55  lea     r8, [rsp+140h+MultiByteStr]; lpMultiByteStr
0x180007e5a  xor     edx, edx; dwFlags
0x180007e5c  mov     ecx, 0FDE9h; CodePage
0x180007e61  call    cs:__imp_MultiByteToWideChar
0x180007e67  movsxd  r14, eax
0x180007e6a  test    eax, eax
0x180007e6c  jnz     short loc_180007EEC
0x180007e6e  call    cs:__imp_GetLastError
0x180007e74  mov     ecx, eax
0x180007e76  test    eax, eax
0x180007e78  jle     short loc_180007E83
0x180007e7a  movzx   ecx, ax
0x180007e7d  or      ecx, 80070000h
0x180007e83  mov     eax, cs:dword_18005A000
0x180007e89  cmp     eax, 3
0x180007e8c  jbe     short loc_180007ED0
0x180007e8e  mov     dword ptr [rsp+140h+var_110], ecx
0x180007e92  lea     rax, [rsp+140h+var_110]
0x180007e97  mov     [rsp+140h+var_E8], rax
0x180007e9c  mov     [rsp+140h+var_E0], 4
0x180007ea5  lea     rax, [rsp+140h+var_108]
0x180007eaa  mov     qword ptr [rsp+140h+cchWideChar], rax
0x180007eaf  mov     dword ptr [rsp+140h+lpWideCharStr], 3
0x180007eb7  xor     r9d, r9d
0x180007eba  xor     r8d, r8d
0x180007ebd  lea     rdx, word_18004E51E
0x180007ec4  lea     rcx, dword_18005A000
0x180007ecb  call    _tlgWriteTransfer_EventWriteTransfer
0x180007ed0  mov     rcx, rdi; this
0x180007ed3  call    ?UseGuidAsSessionId@ProvSession@@AEAAJXZ; ProvSession::UseGuidAsSessionId(void)
0x180007ed8  mov     ebx, eax
0x180007eda  test    eax, eax
0x180007edc  jns     loc_180007F98
0x180007ee2  mov     edx, 102h
0x180007ee7  jmp     loc_180007DEA
0x180007eec  mov     eax, cs:dword_18005A000
0x180007ef2  cmp     eax, 4
0x180007ef5  jbe     short loc_180007F22
0x180007ef7  lea     rax, [rsp+140h+var_108]
0x180007efc  mov     qword ptr [rsp+140h+cchWideChar], rax
0x180007f01  mov     dword ptr [rsp+140h+lpWideCharStr], 2
0x180007f09  xor     r9d, r9d
0x180007f0c  xor     r8d, r8d
0x180007f0f  lea     rdx, byte_18004E551
0x180007f16  lea     rcx, dword_18005A000
0x180007f1d  call    _tlgWriteTransfer_EventWriteTransfer
0x180007f22  xorps   xmm0, xmm0
0x180007f25  movdqu  xmmword ptr [rsp+140h+var_108], xmm0
0x180007f2b  mov     [rsp+140h+var_F8], r15
0x180007f30  mov     rdx, r14
0x180007f33  lea     rcx, [rsp+140h+var_108]
0x180007f38  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180007f3d  mov     rax, [rsp+140h+var_F8]
0x180007f42  mov     r14, [rsp+140h+var_108]
0x180007f47  sub     rax, r14
0x180007f4a  sar     rax, 1
0x180007f4d  mov     [rsp+140h+cchWideChar], eax; cchWideChar
0x180007f51  mov     [rsp+140h+lpWideCharStr], r14; lpWideCharStr
0x180007f56  mov     r9d, ebx; cbMultiByte
0x180007f59  lea     r8, [rsp+140h+MultiByteStr]; lpMultiByteStr
0x180007f5e  xor     edx, edx; dwFlags
0x180007f60  mov     ecx, 0FDE9h; CodePage
0x180007f65  call    cs:__imp_MultiByteToWideChar
0x180007f6b  cmp     [r14], r15w
0x180007f6f  jnz     short loc_180007F76
0x180007f71  mov     rbx, r15
0x180007f74  jmp     short loc_180007F80
0x180007f76  inc     rbx
0x180007f79  cmp     [r14+rbx*2], r15w
0x180007f7e  jnz     short loc_180007F76
0x180007f80  mov     r8, rbx
0x180007f83  mov     rdx, r14; Src
0x180007f86  mov     rcx, rsi; void *
0x180007f89  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180007f8e  nop
0x180007f8f  mov     rcx, r14
0x180007f92  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007f98  mov     eax, cs:dword_18005A000
0x180007f9e  cmp     eax, 4
0x180007fa1  jbe     short loc_180007FCE
0x180007fa3  lea     rax, [rsp+140h+var_108]
0x180007fa8  mov     qword ptr [rsp+140h+cchWideChar], rax
0x180007fad  mov     dword ptr [rsp+140h+lpWideCharStr], 2
0x180007fb5  xor     r9d, r9d
0x180007fb8  xor     r8d, r8d
0x180007fbb  lea     rdx, word_18004E35E
0x180007fc2  lea     rcx, dword_18005A000
0x180007fc9  call    _tlgWriteTransfer_EventWriteTransfer
0x180007fce  mov     rcx, rdi; this
0x180007fd1  call    ?SaveSession@ProvSession@@AEAAJXZ; ProvSession::SaveSession(void)
0x180007fd6  test    eax, eax
0x180007fd8  jns     short loc_18000802A
0x180007fda  mov     ecx, cs:dword_18005A000
0x180007fe0  cmp     ecx, 3
0x180007fe3  jbe     short loc_180008027
0x180007fe5  mov     dword ptr [rsp+140h+var_110], eax
0x180007fe9  lea     rax, [rsp+140h+var_110]
0x180007fee  mov     [rsp+140h+var_E8], rax
0x180007ff3  mov     [rsp+140h+var_E0], 4
0x180007ffc  lea     rax, [rsp+140h+var_108]
0x180008001  mov     qword ptr [rsp+140h+cchWideChar], rax
0x180008006  mov     dword ptr [rsp+140h+lpWideCharStr], 3
0x18000800e  xor     r9d, r9d
0x180008011  xor     r8d, r8d
0x180008014  lea     rdx, byte_18004E38B
0x18000801b  lea     rcx, dword_18005A000
0x180008022  call    _tlgWriteTransfer_EventWriteTransfer
0x180008027  mov     eax, r15d
0x18000802a  mov     rcx, [rbp+40h+var_40]
0x18000802e  xor     rcx, rsp; StackCookie
0x180008031  call    __security_check_cookie
0x180008036  add     rsp, 118h
0x18000803d  pop     r15
0x18000803f  pop     r14
0x180008041  pop     rdi
0x180008042  pop     rsi
0x180008043  pop     rbx
0x180008044  pop     rbp
0x180008045  retn
```
