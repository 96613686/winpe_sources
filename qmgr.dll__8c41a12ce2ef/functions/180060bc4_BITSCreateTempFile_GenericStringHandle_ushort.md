# BITSCreateTempFile(GenericStringHandle<ushort>)

- ea: `0x180060bc4`
- end: `0x180060e9d`
- name: `?BITSCreateTempFile@@YA?AV?$GenericStringHandle@G@@V1@@Z`
- size: `729`
- prototype: `void **__fastcall(void **, void **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028d60`
- `0x18008a9a0`

## callees

- `0x180060bc4`
- `0x180060ea4`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800ab738`
- `0x1800f5574`
- `0x1800f5798`
- `0x1800f5d60`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060d07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060dd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060e06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060e10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060e18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060d07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060dd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060e06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060e10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060e18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060e5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060e5d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180060ce3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180060ce3`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180060dad`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180060dad`

## string_xrefs

- `0x180060d8c`: `CreateFile2`
- `0x180060d64`: `BITSCreateFile2AsApp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void **__fastcall BITSCreateTempFile(void **a1, void **a2)
{
  void **v4; // rax
  int v5; // edx
  int v6; // r8d
  void *v7; // rdi
  const unsigned __int16 *v8; // rdi
  DWORD LastError; // eax
  const wchar_t *v10; // r14
  void *File2; // rax
  char v12; // al
  unsigned int v13; // eax
  _DWORD v15[4]; // [rsp+48h] [rbp-51h] BYREF
  __int128 v16; // [rsp+58h] [rbp-41h]
  void **pExceptionObject; // [rsp+70h] [rbp-29h] BYREF
  __int128 v18; // [rsp+78h] [rbp-21h]
  unsigned int v19; // [rsp+88h] [rbp-11h]
  int v20; // [rsp+8Ch] [rbp-Dh]
  int v21; // [rsp+90h] [rbp-9h]
  int TokenInformation; // [rsp+110h] [rbp+77h] BYREF
  volatile signed __int32 *ReturnLength; // [rsp+118h] [rbp+7Fh] BYREF

  _InterlockedIncrement(&dword_180145058);
  *a1 = &GenericStringHandle<unsigned short>::s_EmptyString;
  v4 = BITSGetTempFileName((void **)&ReturnLength, (const WCHAR *)*a2 + 6);
  _InterlockedIncrement((volatile signed __int32 *)*v4 + 2);
  v7 = *v4;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)*a1 + 2, 0xFFFFFFFF) == 1 )
      operator delete(*a1, 0x10u);
    *a1 = 0;
  }
  *a1 = v7;
  if ( ReturnLength && _InterlockedExchangeAdd(ReturnLength + 2, 0xFFFFFFFF) == 1 )
    operator delete((void *)ReturnLength, 0x10u);
  v8 = (const unsigned __int16 *)((char *)*a1 + 12);
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SDDDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, (_DWORD)v8, 0, 0, 2, -2147483646, 1);
  LODWORD(ReturnLength) = 0;
  TokenInformation = 0;
  if ( !GetTokenInformation(
          (HANDLE)0xFFFFFFFFFFFFFFFALL,
          TokenIsAppContainer,
          &TokenInformation,
          4u,
          (PDWORD)&ReturnLength) )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids, LastError);
    }
    goto LABEL_23;
  }
  v15[3] = 0;
  v15[0] = 32;
  v15[1] = 2;
  v15[2] = 0x80000000;
  v16 = 0;
  if ( TokenInformation && IsAppContainerFileFunctionalitySupported() )
  {
    v10 = L"BITSCreateFile2AsApp";
    File2 = (void *)BITSCreateFile2AsApp(v8, 0x40000000, 0, 2, (struct _CREATEFILE2_EXTENDED_PARAMETERS *)v15);
  }
  else
  {
    v10 = L"CreateFile2";
    File2 = (void *)CreateFile2(v8, 0x40000000, 0, 2, v15);
  }
  if ( File2 == (void *)-1LL )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)&WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids,
        (_DWORD)v10,
        v12);
    }
LABEL_23:
    if ( (int)GetLastError() > 0 )
      v13 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v13 = GetLastError();
    v18 = 0;
    pExceptionObject = &ComError::`vftable';
    v19 = v13;
    v20 = 514;
    v21 = 1;
    throw (ComError *)&pExceptionObject;
  }
  CloseHandle(File2);
  if ( *a2 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)*a2 + 2, 0xFFFFFFFF) == 1 )
      operator delete(*a2, 0x10u);
    *a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180060bc4  mov     [rsp-8+arg_8], rdx
0x180060bc9  mov     [rsp-8+arg_0], rcx
0x180060bce  push    rbp
0x180060bcf  push    rbx
0x180060bd0  push    rsi
0x180060bd1  push    rdi
0x180060bd2  push    r14
0x180060bd4  lea     rbp, [rsp-37h]
0x180060bd9  sub     rsp, 0D0h
0x180060be0  mov     rsi, rdx
0x180060be3  mov     rbx, rcx
0x180060be6  mov     [rbp+57h+var_B0], 0
0x180060bed  lock inc cs:dword_180145058
0x180060bf4  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x180060bfb  mov     [rcx], rax
0x180060bfe  mov     [rbp+57h+var_B0], 1
0x180060c05  mov     rdx, [rdx]
0x180060c08  add     rdx, 0Ch
0x180060c0c  lea     rcx, [rbp+57h+arg_18]
0x180060c10  call    ?BITSGetTempFileName@@YA?AV?$GenericStringHandle@G@@PEBG0I@Z; BITSGetTempFileName(ushort const *,ushort const *,uint)
0x180060c15  mov     rcx, [rax]
0x180060c18  lock inc dword ptr [rcx+8]
0x180060c1c  mov     rdi, [rax]
0x180060c1f  mov     rcx, [rbx]
0x180060c22  test    rcx, rcx
0x180060c25  jz      short loc_180060C46
0x180060c27  or      eax, 0FFFFFFFFh
0x180060c2a  lock xadd [rcx+8], eax
0x180060c2f  cmp     eax, 1
0x180060c32  jnz     short loc_180060C3F
0x180060c34  lea     edx, [rax+0Fh]; unsigned __int64
0x180060c37  mov     rcx, [rbx]; void *
0x180060c3a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180060c3f  mov     qword ptr [rbx], 0
0x180060c46  mov     [rbx], rdi
0x180060c49  mov     rax, [rbp+57h+arg_18]
0x180060c4d  test    rax, rax
0x180060c50  jz      short loc_180060C6B
0x180060c52  or      ecx, 0FFFFFFFFh
0x180060c55  lock xadd [rax+8], ecx
0x180060c5a  cmp     ecx, 1
0x180060c5d  jnz     short loc_180060C6B
0x180060c5f  lea     edx, [rcx+0Fh]; unsigned __int64
0x180060c62  mov     rcx, [rbp+57h+arg_18]; void *
0x180060c66  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180060c6b  mov     rdi, [rbx]
0x180060c6e  add     rdi, 0Ch
0x180060c72  lea     r14, WPP_GLOBAL_Control
0x180060c79  mov     rcx, cs:WPP_GLOBAL_Control
0x180060c80  cmp     rcx, r14
0x180060c83  jz      short loc_180060CB7
0x180060c85  test    byte ptr [rcx+1Ch], 1
0x180060c89  jz      short loc_180060CB7
0x180060c8b  mov     [rsp+0F0h+var_B8], 80000002h
0x180060c93  mov     [rsp+0F0h+var_C0], 2
0x180060c9b  mov     [rsp+0F0h+var_C8], 0
0x180060ca3  mov     dword ptr [rsp+0F0h+ReturnLength], 40000000h
0x180060cab  mov     r9, rdi
0x180060cae  mov     rcx, [rcx+10h]
0x180060cb2  call    WPP_SF_SDDDD
0x180060cb7  mov     dword ptr [rbp+57h+arg_18], 0
0x180060cbe  mov     [rbp+57h+TokenInformation], 0
0x180060cc5  lea     rax, [rbp+57h+arg_18]
0x180060cc9  mov     [rsp+0F0h+ReturnLength], rax; ReturnLength
0x180060cce  mov     r9d, 4; TokenInformationLength
0x180060cd4  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180060cd8  lea     edx, [r9+19h]; TokenInformationClass
0x180060cdc  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x180060ce3  call    cs:__imp_GetTokenInformation
0x180060ce9  test    eax, eax
0x180060ceb  jnz     short loc_180060D31
0x180060ced  mov     rax, cs:WPP_GLOBAL_Control
0x180060cf4  cmp     rax, r14
0x180060cf7  jz      loc_180060E06
0x180060cfd  test    byte ptr [rax+1Ch], 4
0x180060d01  jz      loc_180060E06
0x180060d07  call    cs:__imp_GetLastError
0x180060d0d  mov     edx, 28h ; '('
0x180060d12  mov     r9d, eax
0x180060d15  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x180060d1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180060d23  mov     rcx, [rcx+10h]
0x180060d27  call    WPP_SF_d
0x180060d2c  jmp     loc_180060E06
0x180060d31  mov     [rbp+57h+var_9C], 0
0x180060d38  mov     [rbp+57h+var_A8], 20h ; ' '
0x180060d3f  mov     [rbp+57h+var_A4], 2
0x180060d46  mov     [rbp+57h+var_A0], 80000000h
0x180060d4d  xorps   xmm0, xmm0
0x180060d50  movdqu  [rbp+57h+var_98], xmm0
0x180060d55  cmp     [rbp+57h+TokenInformation], 0
0x180060d59  jz      short loc_180060D8C
0x180060d5b  call    ?IsAppContainerFileFunctionalitySupported@@YA_NXZ; IsAppContainerFileFunctionalitySupported(void)
0x180060d60  test    al, al
0x180060d62  jz      short loc_180060D8C
0x180060d64  lea     r14, aBitscreatefile; "BITSCreateFile2AsApp"
0x180060d6b  lea     rax, [rbp+57h+var_A8]
0x180060d6f  mov     [rsp+0F0h+ReturnLength], rax; struct _CREATEFILE2_EXTENDED_PARAMETERS *
0x180060d74  mov     r9d, 2; unsigned int
0x180060d7a  xor     r8d, r8d; unsigned int
0x180060d7d  mov     edx, 40000000h; unsigned int
0x180060d82  mov     rcx, rdi; unsigned __int16 *
0x180060d85  call    ?BITSCreateFile2AsApp@@YAPEAXPEBGKKKPEAU_CREATEFILE2_EXTENDED_PARAMETERS@@@Z; BITSCreateFile2AsApp(ushort const *,ulong,ulong,ulong,_CREATEFILE2_EXTENDED_PARAMETERS *)
0x180060d8a  jmp     short loc_180060DB3
0x180060d8c  lea     r14, aCreatefile2; "CreateFile2"
0x180060d93  lea     rax, [rbp+57h+var_A8]
0x180060d97  mov     [rsp+0F0h+ReturnLength], rax
0x180060d9c  mov     r9d, 2
0x180060da2  xor     r8d, r8d
0x180060da5  mov     edx, 40000000h
0x180060daa  mov     rcx, rdi
0x180060dad  call    cs:__imp_CreateFile2
0x180060db3  mov     rdi, rax
0x180060db6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180060dba  jnz     loc_180060E5A
0x180060dc0  mov     rax, cs:WPP_GLOBAL_Control
0x180060dc7  lea     rcx, WPP_GLOBAL_Control
0x180060dce  cmp     rax, rcx
0x180060dd1  jz      short loc_180060E00
0x180060dd3  test    byte ptr [rax+1Ch], 2
0x180060dd7  jz      short loc_180060E00
0x180060dd9  call    cs:__imp_GetLastError
0x180060ddf  lea     edx, [rdi+2Ah]
0x180060de2  mov     dword ptr [rsp+0F0h+ReturnLength], eax
0x180060de6  mov     r9, r14
0x180060de9  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x180060df0  mov     rcx, cs:WPP_GLOBAL_Control
0x180060df7  mov     rcx, [rcx+10h]
0x180060dfb  call    WPP_SF_Sd
0x180060e00  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180060e04  jnz     short loc_180060E5A
0x180060e06  call    cs:__imp_GetLastError
0x180060e0c  test    eax, eax
0x180060e0e  jg      short loc_180060E18
0x180060e10  call    cs:__imp_GetLastError
0x180060e16  jmp     short loc_180060E26
0x180060e18  call    cs:__imp_GetLastError
0x180060e1e  movzx   eax, ax
0x180060e21  or      eax, 80070000h
0x180060e26  xorps   xmm0, xmm0
0x180060e29  movups  [rbp+57h+var_78], xmm0
0x180060e2d  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180060e34  mov     [rbp+57h+pExceptionObject], rcx
0x180060e38  mov     [rbp+57h+var_68], eax
0x180060e3b  mov     [rbp+57h+var_64], 202h
0x180060e42  mov     [rbp+57h+var_60], 1
0x180060e49  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180060e50  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180060e54  call    _CxxThrowException_0
0x180060e5a  mov     rcx, rdi; hObject
0x180060e5d  call    cs:__imp_CloseHandle
0x180060e63  nop
0x180060e64  mov     rcx, [rsi]
0x180060e67  test    rcx, rcx
0x180060e6a  jz      short loc_180060E8B
0x180060e6c  or      eax, 0FFFFFFFFh
0x180060e6f  lock xadd [rcx+8], eax
0x180060e74  cmp     eax, 1
0x180060e77  jnz     short loc_180060E84
0x180060e79  lea     edx, [rax+0Fh]; unsigned __int64
0x180060e7c  mov     rcx, [rsi]; void *
0x180060e7f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180060e84  mov     qword ptr [rsi], 0
0x180060e8b  mov     rax, rbx
0x180060e8e  add     rsp, 0D0h
0x180060e95  pop     r14
0x180060e97  pop     rdi
0x180060e98  pop     rsi
0x180060e99  pop     rbx
0x180060e9a  pop     rbp
0x180060e9b  retn
```
