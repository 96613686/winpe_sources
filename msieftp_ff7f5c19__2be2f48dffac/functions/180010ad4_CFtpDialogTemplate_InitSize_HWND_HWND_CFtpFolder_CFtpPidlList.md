# CFtpDialogTemplate::_InitSize(HWND__ *,HWND__ *,CFtpFolder *,CFtpPidlList *)

- ea: `0x180010ad4`
- end: `0x180010c46`
- name: `?_InitSize@CFtpDialogTemplate@@AEAAJPEAUHWND__@@0PEAVCFtpFolder@@PEAVCFtpPidlList@@@Z`
- size: `370`
- prototype: `int(CFtpDialogTemplate *__hidden this, HWND, HWND, struct CFtpFolder *, struct CFtpPidlList *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010390`

## callees

- `0x180002240`
- `0x180010020`
- `0x180010ad4`
- `0x180010f08`
- `0x1800252fc`
- `0x18002698c`

## import_xrefs

- `SHLWAPI!StrFormatByteSizeW` at `0x180010b66`
- `SHLWAPI!StrFormatByteSizeW` at `0x180010b66`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180010b94`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180010b94`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180010bdd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180010bdd`

## pseudocode

```c
int __fastcall CFtpDialogTemplate::_InitSize(
        CFtpDialogTemplate *this,
        HWND a2,
        HWND a3,
        struct CFtpFolder *a4,
        struct CFtpPidlList *a5)
{
  struct _DPA *v7; // rcx
  CFtpDialogTemplate *v8; // rcx
  unsigned int v9; // r8d
  int v10; // edx
  __int64 pData; // [rsp+40h] [rbp-C0h] BYREF
  LONGLONG qdw; // [rsp+48h] [rbp-B8h]
  va_list Arguments[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR lpBuffer[128]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszBuf[64]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v17[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  WCHAR Buffer[64]; // [rsp+260h] [rbp+160h] BYREF

  qdw = 0;
  pData = 1;
  lpBuffer[0] = 0;
  v7 = *(struct _DPA **)(*((_QWORD *)a5 + 2) + 16LL);
  if ( *(int *)v7 > 0 )
  {
    DPA_EnumCallback(v7, CFtpDialogTemplate::_InitSizeTally, &pData);
    if ( pData < 0
      || (_DWORD)pData
      || (StrFormatByteSizeW(qdw, pszBuf, 0x40u),
          AddCommas64(qdw, v17, v9),
          LoadStringW(g_hinst, 0x125u, Buffer, 64),
          Arguments[0] = (va_list)pszBuf,
          Arguments[1] = (va_list)v17,
          FormatMessageW(0x2400u, Buffer, 0, 0, lpBuffer, 0x80u, Arguments)) )
    {
      if ( lpBuffer[0] )
        return CFtpDialogTemplate::_ReinsertDlgText(v8, a2, lpBuffer, L"%s");
    }
    else
    {
      lpBuffer[0] = 0;
    }
  }
  ShowEnableWindow(a2, (int)a2);
  if ( a3 )
    ShowEnableWindow(a3, v10);
  return 0;
}

```

## disassembly

```asm
0x180010ad4  mov     [rsp-8+arg_0], rbx
0x180010ad9  push    rbp
0x180010ada  push    rdi
0x180010adb  push    r14
0x180010add  lea     rbp, [rsp-1F0h]
0x180010ae5  sub     rsp, 2F0h
0x180010aec  mov     rax, cs:__security_cookie
0x180010af3  xor     rax, rsp
0x180010af6  mov     [rbp+200h+var_20], rax
0x180010afd  mov     rcx, [rbp+200h+arg_20]
0x180010b04  xor     r14d, r14d
0x180010b07  mov     [rsp+300h+qdw], r14
0x180010b0c  mov     rbx, r8
0x180010b0f  mov     [rsp+300h+pData], 1
0x180010b18  mov     rdi, rdx
0x180010b1b  mov     [rsp+300h+var_2A0], r14w
0x180010b21  mov     rax, [rcx+10h]
0x180010b25  mov     rcx, [rax+10h]; hdpa
0x180010b29  cmp     [rcx], r14d
0x180010b2c  jle     loc_180010BED
0x180010b32  lea     r8, [rsp+300h+pData]; pData
0x180010b37  lea     rdx, ?_InitSizeTally@CFtpDialogTemplate@@SAHPEBXPEAX@Z; pfnCB
0x180010b3e  call    DPA_EnumCallback
0x180010b43  cmp     dword ptr [rsp+300h+pData+4], r14d
0x180010b48  jl      loc_180010C28
0x180010b4e  cmp     dword ptr [rsp+300h+pData], r14d
0x180010b53  jnz     loc_180010C28
0x180010b59  mov     rcx, [rsp+300h+qdw]; qdw
0x180010b5e  lea     r8d, [r14+40h]; cchBuf
0x180010b62  lea     rdx, [rbp+200h+pszBuf]; pszBuf
0x180010b66  call    cs:__imp_StrFormatByteSizeW
0x180010b6c  mov     rcx, [rsp+300h+qdw]; __int64
0x180010b71  lea     rdx, [rbp+200h+var_120]; unsigned __int16 *
0x180010b78  call    ?AddCommas64@@YAPEAG_JPEAGI@Z; AddCommas64(__int64,ushort *,uint)
0x180010b7d  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x180010b84  lea     r9d, [r14+40h]; cchBufferMax
0x180010b88  lea     r8, [rbp+200h+Buffer]; lpBuffer
0x180010b8f  mov     edx, 125h; uID
0x180010b94  call    cs:__imp_LoadStringW
0x180010b9a  lea     rax, [rbp+200h+pszBuf]
0x180010b9e  xor     r9d, r9d; dwLanguageId
0x180010ba1  mov     [rsp+300h+var_2B0], rax
0x180010ba6  lea     rdx, [rbp+200h+Buffer]; lpSource
0x180010bad  lea     rax, [rbp+200h+var_120]
0x180010bb4  xor     r8d, r8d; dwMessageId
0x180010bb7  mov     [rsp+300h+var_2A8], rax
0x180010bbc  mov     ecx, 2400h; dwFlags
0x180010bc1  lea     rax, [rsp+300h+var_2B0]
0x180010bc6  mov     [rsp+300h+Arguments], rax; Arguments
0x180010bcb  lea     rax, [rsp+300h+var_2A0]
0x180010bd0  mov     [rsp+300h+nSize], 80h; nSize
0x180010bd8  mov     [rsp+300h+lpBuffer], rax; lpBuffer
0x180010bdd  call    cs:__imp_FormatMessageW
0x180010be3  test    eax, eax
0x180010be5  jnz     short loc_180010C28
0x180010be7  mov     [rsp+300h+var_2A0], r14w
0x180010bed  mov     rcx, rdi; HWND
0x180010bf0  call    ?ShowEnableWindow@@YAXPEAUHWND__@@H@Z; ShowEnableWindow(HWND__ *,int)
0x180010bf5  test    rbx, rbx
0x180010bf8  jz      short loc_180010C02
0x180010bfa  mov     rcx, rbx; HWND
0x180010bfd  call    ?ShowEnableWindow@@YAXPEAUHWND__@@H@Z; ShowEnableWindow(HWND__ *,int)
0x180010c02  mov     eax, r14d
0x180010c05  mov     rcx, [rbp+200h+var_20]
0x180010c0c  xor     rcx, rsp; StackCookie
0x180010c0f  call    __security_check_cookie
0x180010c14  mov     rbx, [rsp+300h+arg_0]
0x180010c1c  add     rsp, 2F0h
0x180010c23  pop     r14
0x180010c25  pop     rdi
0x180010c26  pop     rbp
0x180010c27  retn
0x180010c28  cmp     [rsp+300h+var_2A0], r14w
0x180010c2e  jz      short loc_180010BED
0x180010c30  lea     r9, aS; "%s"
0x180010c37  mov     rdx, rdi; HWND
0x180010c3a  lea     r8, [rsp+300h+var_2A0]; void *
0x180010c3f  call    ?_ReinsertDlgText@CFtpDialogTemplate@@AEAAJPEAUHWND__@@PEBXPEBG@Z; CFtpDialogTemplate::_ReinsertDlgText(HWND__ *,void const *,ushort const *)
0x180010c44  jmp     short loc_180010C05
```
