# CommonUtil::CMpHashLib::HashFileByHandle(void *,uchar * const)

- ea: `0x1801cadc4`
- end: `0x1801cb114`
- name: `?HashFileByHandle@CMpHashLib@CommonUtil@@QEBAJPEAXQEAE@Z`
- size: `848`
- prototype: `int(CommonUtil::CMpHashLib *__hidden this, void *, unsigned __int8 *const)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801cb114`

## callees

- `0x1800809d0`
- `0x1800af840`
- `0x180104de0`
- `0x18010532c`
- `0x180105450`
- `0x180105e14`
- `0x18010cb40`
- `0x18010ce3c`
- `0x1801cadc4`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x1801cb075`
- `bcrypt!BCryptHashData` at `0x1801cb075`
- `bcrypt!BCryptCreateHash` at `0x1801caf3e`
- `bcrypt!BCryptCreateHash` at `0x1801caf3e`
- `bcrypt!BCryptFinishHash` at `0x1801cb0a6`
- `bcrypt!BCryptFinishHash` at `0x1801cb0a6`
- `bcrypt!BCryptDestroyHash` at `0x1801caeda`
- `bcrypt!BCryptDestroyHash` at `0x1801caf11`
- `bcrypt!BCryptDestroyHash` at `0x1801caf88`
- `bcrypt!BCryptDestroyHash` at `0x1801cb0d2`
- `bcrypt!BCryptDestroyHash` at `0x1801caeda`
- `bcrypt!BCryptDestroyHash` at `0x1801caf11`
- `bcrypt!BCryptDestroyHash` at `0x1801caf88`
- `bcrypt!BCryptDestroyHash` at `0x1801cb0d2`

## pseudocode

```c
__int64 __fastcall CommonUtil::CMpHashLib::HashFileByHandle(
        CommonUtil::CMpHashLib *this,
        unsigned __int64 *a2,
        unsigned __int8 *const a3)
{
  BCRYPT_HASH_HANDLE v5; // r14
  int FileSize; // eax
  unsigned int v7; // ebx
  UCHAR *v9; // rbx
  ULONG v10; // edi
  int v11; // eax
  const struct std::nothrow_t *v12; // rdx
  ULONG dwFlags; // r14d
  NTSTATUS v14; // eax
  const struct std::nothrow_t *v15; // rdx
  int v16; // edi
  _QWORD *v17; // r10
  __int64 v18; // rdx
  void *v19; // r9
  unsigned __int64 *v20; // rdi
  int File; // r15d
  NTSTATUS v22; // eax
  const struct std::nothrow_t *v23; // rdx
  unsigned int v24; // r14d
  unsigned __int64 *pbSecret; // [rsp+20h] [rbp-50h]
  PUCHAR pbInput; // [rsp+40h] [rbp-30h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+48h] [rbp-28h] BYREF
  ULONG cbInput[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v29; // [rsp+58h] [rbp-18h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  v5 = ::hHash;
  v29 = 0;
  FileSize = CommonUtil::UtilGetFileSize((CommonUtil *)&v29, a2, a3);
  v7 = FileSize;
  if ( FileSize < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_a92645543f693321c8f286218df3ca4d_Traceguids,
        (unsigned int)FileSize);
    return v7;
  }
  if ( !v29 )
    return 2147942438LL;
  v9 = 0;
  v10 = 0;
  pbInput = 0;
  hHash = 0;
  if ( !byte_180313B80 )
  {
    if ( !(unsigned int)MpIsWindows7OrGreater() )
    {
      v11 = CommonUtil::MpNewBuffer<unsigned char>(&pbInput, (unsigned int)dword_180313B50);
      v7 = v11;
      if ( v11 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            WPP_a92645543f693321c8f286218df3ca4d_Traceguids,
            (unsigned int)v11);
        if ( hHash )
          BCryptDestroyHash(hHash);
        if ( pbInput )
          operator delete(pbInput, v12);
        return v7;
      }
      v10 = dword_180313B50;
      v9 = pbInput;
    }
    dwFlags = ::dwFlags;
    if ( hHash )
      BCryptDestroyHash(hHash);
    v14 = BCryptCreateHash(qword_180313B40, &hHash, v9, v10, 0, 0, dwFlags);
    v16 = v14 | 0x10000000;
    if ( v14 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          WPP_a92645543f693321c8f286218df3ca4d_Traceguids,
          (unsigned int)v16);
LABEL_27:
      if ( hHash )
        BCryptDestroyHash(hHash);
      if ( v9 )
        operator delete(v9, v15);
      return (unsigned int)v16;
    }
    v5 = hHash;
  }
  pbInput = 0;
  v16 = CommonUtil::MpNewBuffer<unsigned char>(&pbInput, 10485760);
  if ( v16 < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v18 = 18;
LABEL_37:
      WPP_SF_d(v17[2], v18, WPP_a92645543f693321c8f286218df3ca4d_Traceguids, (unsigned int)v16);
      goto LABEL_38;
    }
    goto LABEL_38;
  }
  v16 = CommonUtil::UtilSetFilePointer((CommonUtil *)a2, 0, 0, 0, pbSecret);
  if ( v16 < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v18 = 19;
      goto LABEL_37;
    }
LABEL_38:
    if ( pbInput )
      operator delete(pbInput, v15);
    goto LABEL_27;
  }
  v20 = (unsigned __int64 *)pbInput;
  do
  {
    *(_QWORD *)cbInput = 10485760;
    File = CommonUtil::UtilReadFile((CommonUtil *)a2, cbInput, v20, v19);
    if ( File < 0 )
      break;
    if ( !*(_QWORD *)cbInput )
      break;
    v22 = BCryptHashData(v5, (PUCHAR)v20, cbInput[0], 0);
    File = v22 | 0x10000000;
    if ( v22 < 0 )
      break;
  }
  while ( *(_QWORD *)cbInput );
  v24 = BCryptFinishHash(v5, a3, cbOutput, 0) | 0x10000000;
  if ( File < 0 )
    v24 = File;
  if ( v20 )
    operator delete(v20, v23);
  if ( hHash )
    BCryptDestroyHash(hHash);
  if ( v9 )
    operator delete(v9, v23);
  return v24;
}

```

## disassembly

```asm
0x1801cadc4  mov     [rsp-28h+arg_0], rbx
0x1801cadc9  mov     [rsp-28h+arg_18], rsi
0x1801cadce  push    rbp
0x1801cadcf  push    rdi
0x1801cadd0  push    r12
0x1801cadd2  push    r14
0x1801cadd4  push    r15
0x1801cadd6  mov     rbp, rsp
0x1801cadd9  sub     rsp, 70h
0x1801caddd  mov     rax, cs:__security_cookie
0x1801cade4  xor     rax, rsp
0x1801cade7  mov     [rbp+var_10], rax
0x1801cadeb  mov     r12, r8
0x1801cadee  mov     rsi, rdx
0x1801cadf1  test    rdx, rdx
0x1801cadf4  jz      loc_1801CB0EA
0x1801cadfa  test    r8, r8
0x1801cadfd  jz      loc_1801CB0EA
0x1801cae03  mov     r14, cs:hHash
0x1801cae0a  lea     rcx, [rbp+var_18]; this
0x1801cae0e  mov     [rbp+var_18], 0
0x1801cae16  call    ?UtilGetFileSize@CommonUtil@@YAJPEA_KPEAX@Z; CommonUtil::UtilGetFileSize(unsigned __int64 *,void *)
0x1801cae1b  mov     ebx, eax
0x1801cae1d  test    eax, eax
0x1801cae1f  jns     short loc_1801CAE5A
0x1801cae21  mov     r10, cs:WPP_GLOBAL_Control
0x1801cae28  lea     rcx, WPP_GLOBAL_Control
0x1801cae2f  cmp     r10, rcx
0x1801cae32  jz      short loc_1801CAE53
0x1801cae34  test    byte ptr [r10+1Ch], 1
0x1801cae39  jz      short loc_1801CAE53
0x1801cae3b  mov     rcx, [r10+10h]
0x1801cae3f  lea     r8, WPP_a92645543f693321c8f286218df3ca4d_Traceguids
0x1801cae46  mov     edx, 0Fh
0x1801cae4b  mov     r9d, eax
0x1801cae4e  call    WPP_SF_d
0x1801cae53  mov     eax, ebx
0x1801cae55  jmp     loc_1801CB0EF
0x1801cae5a  cmp     [rbp+var_18], 0
0x1801cae5f  jnz     short loc_1801CAE6B
0x1801cae61  mov     eax, 80070026h
0x1801cae66  jmp     loc_1801CB0EF
0x1801cae6b  xor     ebx, ebx
0x1801cae6d  xor     edi, edi
0x1801cae6f  cmp     cs:byte_180313B80, bl
0x1801cae75  mov     [rbp+pbInput], rbx
0x1801cae79  mov     [rbp+hHash], rbx
0x1801cae7d  jnz     loc_1801CAFA6
0x1801cae83  call    MpIsWindows7OrGreater
0x1801cae88  test    eax, eax
0x1801cae8a  jnz     short loc_1801CAF01
0x1801cae8c  mov     edx, cs:dword_180313B50
0x1801cae92  lea     rcx, [rbp+pbInput]
0x1801cae96  call    ??$MpNewBuffer@E@CommonUtil@@YAJPEAPEAE_K@Z; CommonUtil::MpNewBuffer<uchar>(uchar * *,unsigned __int64)
0x1801cae9b  mov     ebx, eax
0x1801cae9d  test    eax, eax
0x1801cae9f  jns     short loc_1801CAEF7
0x1801caea1  mov     r10, cs:WPP_GLOBAL_Control
0x1801caea8  lea     rcx, WPP_GLOBAL_Control
0x1801caeaf  cmp     r10, rcx
0x1801caeb2  jz      short loc_1801CAED1
0x1801caeb4  test    byte ptr [r10+1Ch], 1
0x1801caeb9  jz      short loc_1801CAED1
0x1801caebb  mov     rcx, [r10+10h]
0x1801caebf  lea     edx, [rdi+10h]
0x1801caec2  mov     r9d, eax
0x1801caec5  lea     r8, WPP_a92645543f693321c8f286218df3ca4d_Traceguids
0x1801caecc  call    WPP_SF_d
0x1801caed1  mov     rcx, [rbp+hHash]; hHash
0x1801caed5  test    rcx, rcx
0x1801caed8  jz      short loc_1801CAEE0
0x1801caeda  call    cs:__imp_BCryptDestroyHash
0x1801caee0  mov     rcx, [rbp+pbInput]; void *
0x1801caee4  test    rcx, rcx
0x1801caee7  jz      loc_1801CAE53
0x1801caeed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801caef2  jmp     loc_1801CAE53
0x1801caef7  mov     edi, cs:dword_180313B50
0x1801caefd  mov     rbx, [rbp+pbInput]
0x1801caf01  mov     rcx, [rbp+hHash]; hHash
0x1801caf05  mov     r14d, cs:dwFlags
0x1801caf0c  test    rcx, rcx
0x1801caf0f  jz      short loc_1801CAF17
0x1801caf11  call    cs:__imp_BCryptDestroyHash
0x1801caf17  mov     rcx, cs:qword_180313B40; hAlgorithm
0x1801caf1e  lea     rdx, [rbp+hHash]; phHash
0x1801caf22  mov     [rsp+70h+dwFlags], r14d; dwFlags
0x1801caf27  mov     r9d, edi; cbHashObject
0x1801caf2a  mov     [rsp+70h+cbSecret], 0; cbSecret
0x1801caf32  mov     r8, rbx; pbHashObject
0x1801caf35  mov     [rsp+70h+pbSecret], 0; unsigned __int64 *
0x1801caf3e  call    cs:__imp_BCryptCreateHash
0x1801caf44  mov     edi, eax
0x1801caf46  or      edi, 10000000h
0x1801caf4c  jge     short loc_1801CAFA2
0x1801caf4e  mov     rax, cs:WPP_GLOBAL_Control
0x1801caf55  lea     rcx, WPP_GLOBAL_Control
0x1801caf5c  cmp     rax, rcx
0x1801caf5f  jz      short loc_1801CAF7F
0x1801caf61  test    byte ptr [rax+1Ch], 1
0x1801caf65  jz      short loc_1801CAF7F
0x1801caf67  mov     rcx, [rax+10h]
0x1801caf6b  lea     r8, WPP_a92645543f693321c8f286218df3ca4d_Traceguids
0x1801caf72  mov     edx, 11h
0x1801caf77  mov     r9d, edi
0x1801caf7a  call    WPP_SF_d
0x1801caf7f  mov     rcx, [rbp+hHash]; hHash
0x1801caf83  test    rcx, rcx
0x1801caf86  jz      short loc_1801CAF8E
0x1801caf88  call    cs:__imp_BCryptDestroyHash
0x1801caf8e  test    rbx, rbx
0x1801caf91  jz      short loc_1801CAF9B
0x1801caf93  mov     rcx, rbx; void *
0x1801caf96  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801caf9b  mov     eax, edi
0x1801caf9d  jmp     loc_1801CB0EF
0x1801cafa2  mov     r14, [rbp+hHash]
0x1801cafa6  mov     edx, 0A00000h
0x1801cafab  mov     [rbp+pbInput], 0
0x1801cafb3  lea     rcx, [rbp+pbInput]
0x1801cafb7  call    ??$MpNewBuffer@E@CommonUtil@@YAJPEAPEAE_K@Z; CommonUtil::MpNewBuffer<uchar>(uchar * *,unsigned __int64)
0x1801cafbc  mov     edi, eax
0x1801cafbe  test    eax, eax
0x1801cafc0  jns     short loc_1801CB007
0x1801cafc2  mov     r10, cs:WPP_GLOBAL_Control
0x1801cafc9  lea     rcx, WPP_GLOBAL_Control
0x1801cafd0  cmp     r10, rcx
0x1801cafd3  jz      short loc_1801CAFF4
0x1801cafd5  test    byte ptr [r10+1Ch], 1
0x1801cafda  jz      short loc_1801CAFF4
0x1801cafdc  mov     edx, 12h
0x1801cafe1  mov     rcx, [r10+10h]
0x1801cafe5  lea     r8, WPP_a92645543f693321c8f286218df3ca4d_Traceguids
0x1801cafec  mov     r9d, edi
0x1801cafef  call    WPP_SF_d
0x1801caff4  mov     rcx, [rbp+pbInput]; void *
0x1801caff8  test    rcx, rcx
0x1801caffb  jz      short loc_1801CAF7F
0x1801caffd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801cb002  jmp     loc_1801CAF7F
0x1801cb007  xor     r9d, r9d; unsigned int
0x1801cb00a  xor     r8d, r8d; unsigned __int64
0x1801cb00d  xor     edx, edx; void *
0x1801cb00f  mov     rcx, rsi; this
0x1801cb012  call    ?UtilSetFilePointer@CommonUtil@@YAJPEAX_KKPEA_K@Z; CommonUtil::UtilSetFilePointer(void *,unsigned __int64,ulong,unsigned __int64 *)
0x1801cb017  mov     edi, eax
0x1801cb019  test    eax, eax
0x1801cb01b  jns     short loc_1801CB03E
0x1801cb01d  mov     r10, cs:WPP_GLOBAL_Control
0x1801cb024  lea     rcx, WPP_GLOBAL_Control
0x1801cb02b  cmp     r10, rcx
0x1801cb02e  jz      short loc_1801CAFF4
0x1801cb030  test    byte ptr [r10+1Ch], 1
0x1801cb035  jz      short loc_1801CAFF4
0x1801cb037  mov     edx, 13h
0x1801cb03c  jmp     short loc_1801CAFE1
0x1801cb03e  mov     rdi, [rbp+pbInput]
0x1801cb042  mov     r8, rdi; unsigned __int64 *
0x1801cb045  mov     qword ptr [rbp+cbInput], 0A00000h
0x1801cb04d  lea     rdx, [rbp+cbInput]; void *
0x1801cb051  mov     rcx, rsi; this
0x1801cb054  call    ?UtilReadFile@CommonUtil@@YAJPEAXPEA_K0@Z; CommonUtil::UtilReadFile(void *,unsigned __int64 *,void *)
0x1801cb059  mov     r15d, eax
0x1801cb05c  test    eax, eax
0x1801cb05e  js      short loc_1801CB090
0x1801cb060  mov     rcx, qword ptr [rbp+cbInput]
0x1801cb064  test    rcx, rcx
0x1801cb067  jz      short loc_1801CB090
0x1801cb069  mov     r8d, ecx; cbInput
0x1801cb06c  xor     r9d, r9d; dwFlags
0x1801cb06f  mov     rcx, r14; hHash
0x1801cb072  mov     rdx, rdi; pbInput
0x1801cb075  call    cs:__imp_BCryptHashData
0x1801cb07b  mov     r15d, eax
0x1801cb07e  or      r15d, 10000000h
0x1801cb085  jl      short loc_1801CB090
0x1801cb087  mov     rcx, qword ptr [rbp+cbInput]
0x1801cb08b  test    rcx, rcx
0x1801cb08e  jnz     short loc_1801CB042
0x1801cb090  mov     r8d, cs:cbOutput; cbOutput
0x1801cb097  mov     esi, r15d
0x1801cb09a  xor     r9d, r9d; dwFlags
0x1801cb09d  shr     esi, 1Fh
0x1801cb0a0  mov     rdx, r12; pbOutput
0x1801cb0a3  mov     rcx, r14; hHash
0x1801cb0a6  call    cs:__imp_BCryptFinishHash
0x1801cb0ac  mov     r14d, eax
0x1801cb0af  bts     r14d, 1Ch
0x1801cb0b4  xor     sil, 1
0x1801cb0b8  cmovz   r14d, r15d
0x1801cb0bc  test    rdi, rdi
0x1801cb0bf  jz      short loc_1801CB0C9
0x1801cb0c1  mov     rcx, rdi; void *
0x1801cb0c4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801cb0c9  mov     rcx, [rbp+hHash]; hHash
0x1801cb0cd  test    rcx, rcx
0x1801cb0d0  jz      short loc_1801CB0D8
0x1801cb0d2  call    cs:__imp_BCryptDestroyHash
0x1801cb0d8  test    rbx, rbx
0x1801cb0db  jz      short loc_1801CB0E5
0x1801cb0dd  mov     rcx, rbx; void *
0x1801cb0e0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801cb0e5  mov     eax, r14d
0x1801cb0e8  jmp     short loc_1801CB0EF
0x1801cb0ea  mov     eax, 80070057h
0x1801cb0ef  mov     rcx, [rbp+var_10]
0x1801cb0f3  xor     rcx, rsp; StackCookie
0x1801cb0f6  call    __security_check_cookie
0x1801cb0fb  lea     r11, [rsp+70h+var_s0]
0x1801cb100  mov     rbx, [r11+30h]
0x1801cb104  mov     rsi, [r11+48h]
0x1801cb108  mov     rsp, r11
0x1801cb10b  pop     r15
0x1801cb10d  pop     r14
0x1801cb10f  pop     r12
0x1801cb111  pop     rdi
0x1801cb112  pop     rbp
0x1801cb113  retn
```
