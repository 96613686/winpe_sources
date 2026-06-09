# CTsRdpCertSignature::GetHandleToMsgStore(uchar const *,ulong)

- ea: `0x1400a58c8`
- end: `0x1400a5a15`
- name: `?GetHandleToMsgStore@CTsRdpCertSignature@@AEAAPEAXPEBEK@Z`
- size: `333`
- prototype: `void *(CTsRdpCertSignature *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1400a6ed0`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x1400a58c8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400a591e`
- `KERNEL32!GetLastError` at `0x1400a595b`
- `KERNEL32!GetLastError` at `0x1400a599e`
- `KERNEL32!GetLastError` at `0x1400a59db`
- `KERNEL32!GetLastError` at `0x1400a591e`
- `KERNEL32!GetLastError` at `0x1400a595b`
- `KERNEL32!GetLastError` at `0x1400a599e`
- `KERNEL32!GetLastError` at `0x1400a59db`
- `CRYPT32!CryptMsgClose` at `0x1400a5a03`
- `CRYPT32!CryptMsgClose` at `0x1400a5a03`
- `CRYPT32!CryptMsgOpenToDecode` at `0x1400a58f1`
- `CRYPT32!CryptMsgOpenToDecode` at `0x1400a58f1`
- `CRYPT32!CryptMsgUpdate` at `0x1400a5975`
- `CRYPT32!CryptMsgUpdate` at `0x1400a5975`
- `CRYPT32!CertOpenStore` at `0x1400a59f7`
- `CRYPT32!CertOpenStore` at `0x1400a59f7`

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
0x1400a58c8  push    rbx
0x1400a58ca  push    rbp
0x1400a58cb  push    rsi
0x1400a58cc  push    rdi
0x1400a58cd  sub     rsp, 38h
0x1400a58d1  xor     esi, esi
0x1400a58d3  mov     ebx, r8d
0x1400a58d6  mov     rbp, rdx
0x1400a58d9  mov     [rsp+58h+pStreamInfo], rsi; pStreamInfo
0x1400a58de  xor     r9d, r9d; hCryptProv
0x1400a58e1  mov     [rsp+58h+pRecipientInfo], rsi; pRecipientInfo
0x1400a58e6  xor     r8d, r8d; dwMsgType
0x1400a58e9  mov     ecx, 10001h; dwMsgEncodingType
0x1400a58ee  lea     edx, [rsi+4]; dwFlags
0x1400a58f1  call    cs:__imp_CryptMsgOpenToDecode
0x1400a58f7  mov     rdi, rax
0x1400a58fa  test    rax, rax
0x1400a58fd  jnz     short loc_1400A5966
0x1400a58ff  mov     rax, cs:WPP_GLOBAL_Control
0x1400a5906  lea     rcx, WPP_GLOBAL_Control
0x1400a590d  cmp     rax, rcx
0x1400a5910  jz      short loc_1400A595B
0x1400a5912  test    byte ptr [rax+1Ch], 8
0x1400a5916  jz      short loc_1400A595B
0x1400a5918  cmp     byte ptr [rax+19h], 2
0x1400a591c  jb      short loc_1400A595B
0x1400a591e  call    cs:__imp_GetLastError
0x1400a5924  mov     ebx, eax
0x1400a5926  test    eax, eax
0x1400a5928  jle     short loc_1400A5933
0x1400a592a  movzx   ebx, ax
0x1400a592d  or      ebx, 80070000h
0x1400a5933  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a5938  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a593f  lea     r8, WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids
0x1400a5946  mov     edx, 3Eh ; '>'
0x1400a594b  mov     dword ptr [rsp+58h+pRecipientInfo], ebx
0x1400a594f  mov     r9d, eax
0x1400a5952  mov     rcx, [rcx+10h]
0x1400a5956  call    WPP_SF_Dd
0x1400a595b  call    cs:__imp_GetLastError
0x1400a5961  jmp     loc_1400A5A09
0x1400a5966  mov     r9d, 1; fFinal
0x1400a596c  mov     r8d, ebx; cbData
0x1400a596f  mov     rdx, rbp; pbData
0x1400a5972  mov     rcx, rdi; hCryptMsg
0x1400a5975  call    cs:__imp_CryptMsgUpdate
0x1400a597b  test    eax, eax
0x1400a597d  jnz     short loc_1400A59E3
0x1400a597f  mov     rax, cs:WPP_GLOBAL_Control
0x1400a5986  lea     rcx, WPP_GLOBAL_Control
0x1400a598d  cmp     rax, rcx
0x1400a5990  jz      short loc_1400A59DB
0x1400a5992  test    byte ptr [rax+1Ch], 8
0x1400a5996  jz      short loc_1400A59DB
0x1400a5998  cmp     byte ptr [rax+19h], 2
0x1400a599c  jb      short loc_1400A59DB
0x1400a599e  call    cs:__imp_GetLastError
0x1400a59a4  mov     ebx, eax
0x1400a59a6  test    eax, eax
0x1400a59a8  jle     short loc_1400A59B3
0x1400a59aa  movzx   ebx, ax
0x1400a59ad  or      ebx, 80070000h
0x1400a59b3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a59b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a59bf  lea     r8, WPP_f8797c192eb93a6e11ea4a0966e1d424_Traceguids
0x1400a59c6  mov     edx, 3Fh ; '?'
0x1400a59cb  mov     dword ptr [rsp+58h+pRecipientInfo], ebx
0x1400a59cf  mov     r9d, eax
0x1400a59d2  mov     rcx, [rcx+10h]
0x1400a59d6  call    WPP_SF_Dd
0x1400a59db  call    cs:__imp_GetLastError
0x1400a59e1  jmp     short loc_1400A5A00
0x1400a59e3  xor     r9d, r9d; dwFlags
0x1400a59e6  mov     [rsp+58h+pRecipientInfo], rdi; pvPara
0x1400a59eb  xor     r8d, r8d; hCryptProv
0x1400a59ee  mov     edx, 10001h; dwEncodingType
0x1400a59f3  lea     ecx, [r9+1]; lpszStoreProvider
0x1400a59f7  call    cs:__imp_CertOpenStore
0x1400a59fd  mov     rsi, rax
0x1400a5a00  mov     rcx, rdi; hCryptMsg
0x1400a5a03  call    cs:__imp_CryptMsgClose
0x1400a5a09  mov     rax, rsi
0x1400a5a0c  add     rsp, 38h
0x1400a5a10  pop     rdi
0x1400a5a11  pop     rsi
0x1400a5a12  pop     rbp
0x1400a5a13  pop     rbx
0x1400a5a14  retn
```
