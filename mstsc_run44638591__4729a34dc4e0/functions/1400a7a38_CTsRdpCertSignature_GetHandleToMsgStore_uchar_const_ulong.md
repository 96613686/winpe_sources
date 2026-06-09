# CTsRdpCertSignature::GetHandleToMsgStore(uchar const *,ulong)

- ea: `0x1400a7a38`
- end: `0x1400a7b85`
- name: `?GetHandleToMsgStore@CTsRdpCertSignature@@AEAAPEAXPEBEK@Z`
- size: `333`
- prototype: `void *(CTsRdpCertSignature *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1400a9040`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x1400a7a38`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400a7a8e`
- `KERNEL32!GetLastError` at `0x1400a7acb`
- `KERNEL32!GetLastError` at `0x1400a7b0e`
- `KERNEL32!GetLastError` at `0x1400a7b4b`
- `KERNEL32!GetLastError` at `0x1400a7a8e`
- `KERNEL32!GetLastError` at `0x1400a7acb`
- `KERNEL32!GetLastError` at `0x1400a7b0e`
- `KERNEL32!GetLastError` at `0x1400a7b4b`
- `CRYPT32!CryptMsgClose` at `0x1400a7b73`
- `CRYPT32!CryptMsgClose` at `0x1400a7b73`
- `CRYPT32!CryptMsgOpenToDecode` at `0x1400a7a61`
- `CRYPT32!CryptMsgOpenToDecode` at `0x1400a7a61`
- `CRYPT32!CryptMsgUpdate` at `0x1400a7ae5`
- `CRYPT32!CryptMsgUpdate` at `0x1400a7ae5`
- `CRYPT32!CertOpenStore` at `0x1400a7b67`
- `CRYPT32!CertOpenStore` at `0x1400a7b67`

## pseudocode

```c
HCERTSTORE __fastcall CTsRdpCertSignature::GetHandleToMsgStore(
        CTsRdpCertSignature *this,
        const unsigned __int8 *a2,
        DWORD a3)
{
  HCERTSTORE v3; // rsi
  HCRYPTMSG v6; // rax
  void *v7; // rdi
  signed int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  signed int LastError; // eax
  unsigned int v12; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax

  v3 = 0;
  v6 = CryptMsgOpenToDecode(0x10001u, 4u, 0, 0, 0, 0);
  v7 = v6;
  if ( v6 )
  {
    if ( CryptMsgUpdate(v6, a2, a3, 1) )
    {
      v3 = CertOpenStore((LPCSTR)1, 0x10001u, 0, 0, v7);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          63,
          WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids,
          CurrentThreadActivityIdPrefix,
          v12);
      }
      GetLastError();
    }
    CryptMsgClose(v7);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = GetLastError();
      v9 = v8;
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids, v10, v9);
    }
    GetLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x1400a7a38  push    rbx
0x1400a7a3a  push    rbp
0x1400a7a3b  push    rsi
0x1400a7a3c  push    rdi
0x1400a7a3d  sub     rsp, 38h
0x1400a7a41  xor     esi, esi
0x1400a7a43  mov     ebx, r8d
0x1400a7a46  mov     rbp, rdx
0x1400a7a49  mov     [rsp+58h+pStreamInfo], rsi; pStreamInfo
0x1400a7a4e  xor     r9d, r9d; hCryptProv
0x1400a7a51  mov     [rsp+58h+pRecipientInfo], rsi; pRecipientInfo
0x1400a7a56  xor     r8d, r8d; dwMsgType
0x1400a7a59  mov     ecx, 10001h; dwMsgEncodingType
0x1400a7a5e  lea     edx, [rsi+4]; dwFlags
0x1400a7a61  call    cs:__imp_CryptMsgOpenToDecode
0x1400a7a67  mov     rdi, rax
0x1400a7a6a  test    rax, rax
0x1400a7a6d  jnz     short loc_1400A7AD6
0x1400a7a6f  mov     rax, cs:WPP_GLOBAL_Control
0x1400a7a76  lea     rcx, WPP_GLOBAL_Control
0x1400a7a7d  cmp     rax, rcx
0x1400a7a80  jz      short loc_1400A7ACB
0x1400a7a82  test    byte ptr [rax+1Ch], 8
0x1400a7a86  jz      short loc_1400A7ACB
0x1400a7a88  cmp     byte ptr [rax+19h], 2
0x1400a7a8c  jb      short loc_1400A7ACB
0x1400a7a8e  call    cs:__imp_GetLastError
0x1400a7a94  mov     ebx, eax
0x1400a7a96  test    eax, eax
0x1400a7a98  jle     short loc_1400A7AA3
0x1400a7a9a  movzx   ebx, ax
0x1400a7a9d  or      ebx, 80070000h
0x1400a7aa3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a7aa8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7aaf  lea     r8, WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids
0x1400a7ab6  mov     edx, 3Eh ; '>'
0x1400a7abb  mov     dword ptr [rsp+58h+pRecipientInfo], ebx
0x1400a7abf  mov     r9d, eax
0x1400a7ac2  mov     rcx, [rcx+10h]
0x1400a7ac6  call    WPP_SF_Dd
0x1400a7acb  call    cs:__imp_GetLastError
0x1400a7ad1  jmp     loc_1400A7B79
0x1400a7ad6  mov     r9d, 1; fFinal
0x1400a7adc  mov     r8d, ebx; cbData
0x1400a7adf  mov     rdx, rbp; pbData
0x1400a7ae2  mov     rcx, rdi; hCryptMsg
0x1400a7ae5  call    cs:__imp_CryptMsgUpdate
0x1400a7aeb  test    eax, eax
0x1400a7aed  jnz     short loc_1400A7B53
0x1400a7aef  mov     rax, cs:WPP_GLOBAL_Control
0x1400a7af6  lea     rcx, WPP_GLOBAL_Control
0x1400a7afd  cmp     rax, rcx
0x1400a7b00  jz      short loc_1400A7B4B
0x1400a7b02  test    byte ptr [rax+1Ch], 8
0x1400a7b06  jz      short loc_1400A7B4B
0x1400a7b08  cmp     byte ptr [rax+19h], 2
0x1400a7b0c  jb      short loc_1400A7B4B
0x1400a7b0e  call    cs:__imp_GetLastError
0x1400a7b14  mov     ebx, eax
0x1400a7b16  test    eax, eax
0x1400a7b18  jle     short loc_1400A7B23
0x1400a7b1a  movzx   ebx, ax
0x1400a7b1d  or      ebx, 80070000h
0x1400a7b23  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a7b28  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a7b2f  lea     r8, WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids
0x1400a7b36  mov     edx, 3Fh ; '?'
0x1400a7b3b  mov     dword ptr [rsp+58h+pRecipientInfo], ebx
0x1400a7b3f  mov     r9d, eax
0x1400a7b42  mov     rcx, [rcx+10h]
0x1400a7b46  call    WPP_SF_Dd
0x1400a7b4b  call    cs:__imp_GetLastError
0x1400a7b51  jmp     short loc_1400A7B70
0x1400a7b53  xor     r9d, r9d; dwFlags
0x1400a7b56  mov     [rsp+58h+pRecipientInfo], rdi; pvPara
0x1400a7b5b  xor     r8d, r8d; hCryptProv
0x1400a7b5e  mov     edx, 10001h; dwEncodingType
0x1400a7b63  lea     ecx, [r9+1]; lpszStoreProvider
0x1400a7b67  call    cs:__imp_CertOpenStore
0x1400a7b6d  mov     rsi, rax
0x1400a7b70  mov     rcx, rdi; hCryptMsg
0x1400a7b73  call    cs:__imp_CryptMsgClose
0x1400a7b79  mov     rax, rsi
0x1400a7b7c  add     rsp, 38h
0x1400a7b80  pop     rdi
0x1400a7b81  pop     rsi
0x1400a7b82  pop     rbp
0x1400a7b83  pop     rbx
0x1400a7b84  retn
```
