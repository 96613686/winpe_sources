# PROVIDER_DEFINITIONS_STORED_LIST::TranslateProviderNameAndAreas(ushort const *,ushort const *,_GUID * *,ulong *,ushort const *,FREB_FAILURE_POINT *)

- ea: `0x180007a80`
- end: `0x180007d22`
- name: `?TranslateProviderNameAndAreas@PROVIDER_DEFINITIONS_STORED_LIST@@QEAAJPEBG0PEAPEAU_GUID@@PEAK0PEAW4FREB_FAILURE_POINT@@@Z`
- size: `674`
- prototype: `int(PROVIDER_DEFINITIONS_STORED_LIST *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct _GUID **, unsigned int *, const unsigned __int16 *, enum FREB_FAILURE_POINT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005b28`

## callees

- `0x180007a80`
- `0x18000a4dc`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180007c0c`
- `msvcrt!_wcsnicmp` at `0x180007c0c`
- `msvcrt!_wcsicmp` at `0x180007ac0`
- `msvcrt!_wcsicmp` at `0x180007ac0`
- `iisutil!PuDbgPrintError` at `0x180007b68`
- `iisutil!PuDbgPrintError` at `0x180007d07`
- `iisutil!PuDbgPrintError` at `0x180007b68`
- `iisutil!PuDbgPrintError` at `0x180007d07`

## string_xrefs

- `0x180007b4e`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\provider_definitions_stored_list.cxx`
- `0x180007cf2`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\provider_definitions_stored_list.cxx`

## pseudocode

```c
__int64 __fastcall PROVIDER_DEFINITIONS_STORED_LIST::TranslateProviderNameAndAreas(
        PROVIDER_DEFINITIONS_STORED_LIST *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _GUID **a4,
        unsigned int *a5,
        const unsigned __int16 *a6,
        enum FREB_FAILURE_POINT *a7)
{
  unsigned int v7; // ebx
  const unsigned __int16 *v8; // r14
  const wchar_t *v9; // r15
  __int64 v11; // rbp
  __int64 v12; // rsi
  unsigned int v13; // ebx
  wchar_t v15; // cx
  unsigned int v16; // r13d
  const wchar_t *v17; // rbx
  wchar_t v18; // ax
  const wchar_t *v19; // rdi
  int v20; // r12d
  unsigned int v21; // r14d
  __int64 v22; // rdi
  unsigned __int64 v23; // r15
  unsigned __int16 *v24; // [rsp+40h] [rbp-68h] BYREF
  __int64 v25; // [rsp+48h] [rbp-60h]
  const wchar_t *v26; // [rsp+50h] [rbp-58h]
  const unsigned __int16 *v27; // [rsp+58h] [rbp-50h]
  const wchar_t *v28; // [rsp+B0h] [rbp+8h]

  v7 = 0;
  v8 = a3;
  v9 = a2;
  if ( *((_DWORD *)this + 2) )
  {
    while ( 1 )
    {
      v11 = *(_QWORD *)this;
      v12 = 88LL * v7;
      if ( !_wcsicmp(v9, *(const wchar_t **)(v12 + *(_QWORD *)this + 32)) )
        break;
      if ( ++v7 >= *((_DWORD *)this + 2) )
        goto LABEL_4;
    }
    v15 = *v8;
    v16 = 0;
    if ( !*v8 )
    {
LABEL_24:
      *a5 = v16;
      *a4 = (struct _GUID *)(v12 + v11 + 56);
      return 0;
    }
    v17 = v8;
    while ( 1 )
    {
      if ( v15 == 32 )
      {
        do
          ++v17;
        while ( *v17 == 32 );
      }
      v18 = *v17;
      v19 = v17;
      v28 = v17;
      if ( *v17 != 44 )
      {
        do
        {
          if ( (v18 & 0xFFDF) == 0 )
            break;
          v18 = *++v19;
        }
        while ( *v19 != 44 );
        v28 = v19;
      }
      v20 = 0;
      v21 = 0;
      if ( !*(_DWORD *)(v12 + v11 + 72) )
        break;
      v22 = v19 - v17;
      do
      {
        v23 = (unsigned __int64)v21 << 6;
        if ( !_wcsnicmp(v17, *(const wchar_t **)(v23 + *(_QWORD *)(v12 + v11 + 80) + 32), (unsigned int)v22) )
        {
          v20 = 1;
          v16 |= *(_DWORD *)(v23 + *(_QWORD *)(v12 + v11 + 80) + 56);
        }
        ++v21;
      }
      while ( v21 < *(_DWORD *)(v12 + v11 + 72) );
      if ( !v20 )
        break;
      if ( *v28 )
      {
        v17 = v28 + 1;
        v15 = v28[1];
        if ( v15 )
          continue;
      }
      goto LABEL_24;
    }
    v24 = 0;
    v25 = 0;
    v26 = v17;
    *(_DWORD *)a7 = 1;
    v27 = a6;
    FREB_LOG_NT_EVENT_TABLE::LogEvent(0x800008ED, 4u, (const unsigned __int16 **const)&v24, 0x80070057);
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\provider_definitions_stored_list.cxx",
        193,
        "PROVIDER_DEFINITIONS_STORED_ENTRY::TranslateAreasToDword",
        -2147024809,
        "Failed to translate areas (%S)\n",
        v17);
    v9 = a2;
    v8 = a3;
  }
  else
  {
LABEL_4:
    *(_DWORD *)a7 = 2;
  }
  v13 = -2147024809;
  v27 = a6;
  v24 = 0;
  v25 = 0;
  v26 = v9;
  FREB_LOG_NT_EVENT_TABLE::LogEvent(0x800008ED, 4u, (const unsigned __int16 **const)&v24, 0x80070057);
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\provider_definitions_stored_list.cxx",
      291,
      "PROVIDER_DEFINITIONS_STORED_LIST::TranslateProviderNameAndAreas",
      -2147024809,
      "Failed to recognize trace provider:\"%S\" and/or trace areas:\"%S\"\n",
      v9,
      v8);
  return v13;
}

```

## disassembly

```asm
0x180007a80  mov     [rsp+arg_18], r9
0x180007a85  mov     [rsp+arg_10], r8
0x180007a8a  mov     [rsp+arg_8], rdx
0x180007a8f  push    rbx
0x180007a90  push    rbp
0x180007a91  push    rsi
0x180007a92  push    rdi
0x180007a93  push    r12
0x180007a95  push    r13
0x180007a97  push    r14
0x180007a99  push    r15
0x180007a9b  sub     rsp, 68h
0x180007a9f  xor     ebx, ebx
0x180007aa1  mov     r14, r8
0x180007aa4  mov     r15, rdx
0x180007aa7  mov     rdi, rcx
0x180007aaa  cmp     [rcx+8], ebx
0x180007aad  jbe     short loc_180007AD5
0x180007aaf  mov     rbp, [rdi]
0x180007ab2  mov     rcx, r15; String1
0x180007ab5  mov     eax, ebx
0x180007ab7  imul    rsi, rax, 58h ; 'X'
0x180007abb  mov     rdx, [rsi+rbp+20h]; String2
0x180007ac0  call    cs:__imp__wcsicmp
0x180007ac6  test    eax, eax
0x180007ac8  jz      loc_180007B81
0x180007ace  inc     ebx
0x180007ad0  cmp     ebx, [rdi+8]
0x180007ad3  jb      short loc_180007AAF
0x180007ad5  mov     rax, [rsp+0A8h+arg_30]
0x180007add  mov     dword ptr [rax], 2
0x180007ae3  mov     ebx, 80070057h
0x180007ae8  mov     rax, [rsp+0A8h+arg_28]
0x180007af0  lea     r8, [rsp+0A8h+var_68]; unsigned __int16 **
0x180007af5  mov     edx, 4; unsigned __int16
0x180007afa  mov     [rsp+0A8h+var_50], rax
0x180007aff  mov     r9d, 80070057h; unsigned int
0x180007b05  mov     [rsp+0A8h+var_68], 0
0x180007b0e  mov     ecx, 800008EDh; unsigned int
0x180007b13  mov     [rsp+0A8h+var_60], 0
0x180007b1c  mov     [rsp+0A8h+var_58], r15
0x180007b21  call    ?LogEvent@FREB_LOG_NT_EVENT_TABLE@@SAXKGQEAPEBGK@Z; FREB_LOG_NT_EVENT_TABLE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180007b26  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007b2d  jz      short loc_180007B6E
0x180007b2f  mov     rcx, cs:g_pDebug
0x180007b36  lea     rax, aFailedToRecogn; "Failed to recognize trace provider:\"%S"...
0x180007b3d  mov     [rsp+0A8h+var_70], r14
0x180007b42  lea     r9, aProviderDefini; "PROVIDER_DEFINITIONS_STORED_LIST::Trans"...
0x180007b49  mov     [rsp+0A8h+var_78], r15
0x180007b4e  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007b55  mov     [rsp+0A8h+var_80], rax
0x180007b5a  mov     r8d, 123h
0x180007b60  mov     [rsp+0A8h+var_88], 80070057h
0x180007b68  call    cs:__imp_PuDbgPrintError
0x180007b6e  mov     eax, ebx
0x180007b70  add     rsp, 68h
0x180007b74  pop     r15
0x180007b76  pop     r14
0x180007b78  pop     r13
0x180007b7a  pop     r12
0x180007b7c  pop     rdi
0x180007b7d  pop     rsi
0x180007b7e  pop     rbp
0x180007b7f  pop     rbx
0x180007b80  retn
0x180007b81  movzx   ecx, word ptr [r14]
0x180007b85  xor     r13d, r13d
0x180007b88  xor     eax, eax
0x180007b8a  cmp     ax, cx
0x180007b8d  jz      loc_180007C5A
0x180007b93  lea     eax, [r13+20h]
0x180007b97  mov     rbx, r14
0x180007b9a  lea     edx, [rax+0Ch]
0x180007b9d  cmp     ax, cx
0x180007ba0  jnz     short loc_180007BAB
0x180007ba2  add     rbx, 2
0x180007ba6  cmp     ax, [rbx]
0x180007ba9  jz      short loc_180007BA2
0x180007bab  movzx   eax, word ptr [rbx]
0x180007bae  mov     rdi, rbx
0x180007bb1  mov     [rsp+0A8h+arg_0], rbx
0x180007bb9  cmp     dx, ax
0x180007bbc  jz      short loc_180007BDC
0x180007bbe  mov     ecx, 0FFDFh
0x180007bc3  test    cx, ax
0x180007bc6  jz      short loc_180007BD4
0x180007bc8  add     rdi, 2
0x180007bcc  movzx   eax, word ptr [rdi]
0x180007bcf  cmp     dx, ax
0x180007bd2  jnz     short loc_180007BBE
0x180007bd4  mov     [rsp+0A8h+arg_0], rdi
0x180007bdc  xor     r12d, r12d
0x180007bdf  xor     r14d, r14d
0x180007be2  cmp     [rsi+rbp+48h], r12d
0x180007be7  jbe     loc_180007C7E
0x180007bed  sub     rdi, rbx
0x180007bf0  sar     rdi, 1
0x180007bf3  mov     edi, edi
0x180007bf5  mov     rdx, [rsi+rbp+50h]
0x180007bfa  mov     r8, rdi; MaxCount
0x180007bfd  mov     r15d, r14d
0x180007c00  mov     rcx, rbx; String1
0x180007c03  shl     r15, 6
0x180007c07  mov     rdx, [r15+rdx+20h]; String2
0x180007c0c  call    cs:__imp__wcsnicmp
0x180007c12  test    eax, eax
0x180007c14  jnz     short loc_180007C24
0x180007c16  lea     r12d, [rax+1]
0x180007c1a  mov     rax, [rsi+rbp+50h]
0x180007c1f  or      r13d, [r15+rax+38h]
0x180007c24  inc     r14d
0x180007c27  cmp     r14d, [rsi+rbp+48h]
0x180007c2c  jb      short loc_180007BF5
0x180007c2e  mov     rdi, [rsp+0A8h+arg_0]
0x180007c36  test    r12d, r12d
0x180007c39  jz      short loc_180007C7E
0x180007c3b  xor     eax, eax
0x180007c3d  cmp     ax, [rdi]
0x180007c40  jz      short loc_180007C5A
0x180007c42  lea     rbx, [rdi+2]
0x180007c46  movzx   ecx, word ptr [rbx]
0x180007c49  cmp     ax, cx
0x180007c4c  mov     eax, 20h ; ' '
0x180007c51  lea     edx, [rax+0Ch]
0x180007c54  jnz     loc_180007B9D
0x180007c5a  mov     rax, [rsp+0A8h+arg_20]
0x180007c62  mov     rcx, [rsp+0A8h+arg_18]
0x180007c6a  mov     [rax], r13d
0x180007c6d  lea     rax, [rbp+38h]
0x180007c71  add     rax, rsi
0x180007c74  mov     [rcx], rax
0x180007c77  xor     ebx, ebx
0x180007c79  jmp     loc_180007B6E
0x180007c7e  mov     rax, [rsp+0A8h+arg_30]
0x180007c86  lea     r8, [rsp+0A8h+var_68]; unsigned __int16 **
0x180007c8b  mov     edx, 4; unsigned __int16
0x180007c90  mov     [rsp+0A8h+var_68], 0
0x180007c99  mov     r9d, 80070057h; unsigned int
0x180007c9f  mov     [rsp+0A8h+var_60], 0
0x180007ca8  mov     ecx, 800008EDh; unsigned int
0x180007cad  mov     [rsp+0A8h+var_58], rbx
0x180007cb2  mov     dword ptr [rax], 1
0x180007cb8  mov     rax, [rsp+0A8h+arg_28]
0x180007cc0  mov     [rsp+0A8h+var_50], rax
0x180007cc5  call    ?LogEvent@FREB_LOG_NT_EVENT_TABLE@@SAXKGQEAPEBGK@Z; FREB_LOG_NT_EVENT_TABLE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180007cca  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007cd1  jz      short loc_180007D0D
0x180007cd3  mov     rcx, cs:g_pDebug
0x180007cda  lea     rax, aFailedToTransl; "Failed to translate areas (%S)\n"
0x180007ce1  mov     [rsp+0A8h+var_78], rbx
0x180007ce6  lea     r9, aProviderDefini_1; "PROVIDER_DEFINITIONS_STORED_ENTRY::Tran"...
0x180007ced  mov     [rsp+0A8h+var_80], rax
0x180007cf2  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007cf9  mov     r8d, 0C1h
0x180007cff  mov     [rsp+0A8h+var_88], 80070057h
0x180007d07  call    cs:__imp_PuDbgPrintError
0x180007d0d  mov     r15, [rsp+0A8h+arg_8]
0x180007d15  mov     r14, [rsp+0A8h+arg_10]
0x180007d1d  jmp     loc_180007AE3
```
