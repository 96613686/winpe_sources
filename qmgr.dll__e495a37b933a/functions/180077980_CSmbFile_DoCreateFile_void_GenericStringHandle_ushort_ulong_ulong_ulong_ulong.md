# CSmbFile::DoCreateFile(void * &,GenericStringHandle<ushort> &,ulong,ulong,ulong,ulong)

- ea: `0x180077980`
- end: `0x180077bae`
- name: `?DoCreateFile@CSmbFile@@KAXAEAPEAXAEAV?$GenericStringHandle@G@@KKKK@Z`
- size: `558`
- prototype: `EVENT_LOG *__fastcall(__int64 *, _QWORD *, unsigned int, unsigned int, unsigned int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003cac0`

## callees

- `0x180077980`
- `0x18009e9c8`
- `0x1800ab738`
- `0x1800f5574`
- `0x1800f5798`
- `0x1800f5d60`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077a33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077a33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b51`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180077a17`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180077a17`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180077ae6`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180077ae6`

## string_xrefs

- `0x180077adc`: `CreateFile2`
- `0x180077aba`: `BITSCreateFile2AsApp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
EVENT_LOG *__fastcall CSmbFile::DoCreateFile(
        __int64 *a1,
        _QWORD *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        int a6)
{
  const unsigned __int16 *v7; // r14
  int v10; // ebx
  unsigned int v11; // r15d
  EVENT_LOG *result; // rax
  DWORD v13; // eax
  __int64 v14; // rbx
  const wchar_t *v15; // r12
  char LastError; // al
  unsigned int v17; // eax
  _DWORD v18[3]; // [rsp+40h] [rbp-69h] BYREF
  int v19; // [rsp+4Ch] [rbp-5Dh]
  __int128 v20; // [rsp+50h] [rbp-59h]
  void **pExceptionObject; // [rsp+60h] [rbp-49h] BYREF
  __int128 v22; // [rsp+68h] [rbp-41h]
  unsigned int v23; // [rsp+78h] [rbp-31h]
  int v24; // [rsp+7Ch] [rbp-2Dh]
  int v25; // [rsp+80h] [rbp-29h]
  int TokenInformation; // [rsp+100h] [rbp+57h] BYREF
  DWORD ReturnLength; // [rsp+108h] [rbp+5Fh] BYREF

  v7 = (const unsigned __int16 *)(*a2 + 12LL);
  v10 = a6;
  v11 = a5;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SDDDD(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)a2, a3, (_DWORD)v7, a3, a4, a5, a6);
  ReturnLength = 0;
  TokenInformation = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
  {
    v19 = 0;
    v18[0] = 32;
    v18[1] = v10 & 0x7FB7;
    v18[2] = v10 & 0xFFF00000;
    v20 = 0;
    if ( (v10 & 0x100000) != 0 )
      v19 = v10 & 0x1F0000;
    if ( TokenInformation && IsAppContainerFileFunctionalitySupported() )
    {
      v15 = L"BITSCreateFile2AsApp";
      result = (EVENT_LOG *)BITSCreateFile2AsApp(v7, a3, a4, v11, (struct _CREATEFILE2_EXTENDED_PARAMETERS *)v18);
    }
    else
    {
      v15 = L"CreateFile2";
      result = (EVENT_LOG *)CreateFile2(v7, a3, a4, v11, v18);
    }
    v14 = (__int64)result;
    if ( result == (EVENT_LOG *)-1LL )
    {
      result = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        LastError = GetLastError();
        result = (EVENT_LOG *)WPP_SF_Sd(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                41,
                                (unsigned int)WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids,
                                (_DWORD)v15,
                                LastError);
      }
    }
  }
  else
  {
    result = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v13 = GetLastError();
      result = (EVENT_LOG *)WPP_SF_d(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              40,
                              WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids,
                              v13);
    }
    v14 = -1;
  }
  *a1 = v14;
  if ( v14 == -1 )
  {
    if ( (int)GetLastError() > 0 )
      v17 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v17 = GetLastError();
    v23 = v17;
    pExceptionObject = &ComError::`vftable';
    v24 = 393;
    v25 = 1;
    v22 = 0;
    throw (ComError *)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180077980  mov     [rsp-8+arg_10], rbx
0x180077985  push    rbp
0x180077986  push    rsi
0x180077987  push    rdi
0x180077988  push    r12
0x18007798a  push    r13
0x18007798c  push    r14
0x18007798e  push    r15
0x180077990  lea     rbp, [rsp-17h]
0x180077995  sub     rsp, 0C0h
0x18007799c  mov     r14, [rdx]
0x18007799f  mov     edi, r9d
0x1800779a2  add     r14, 0Ch
0x1800779a6  mov     esi, r8d
0x1800779a9  mov     r13, rcx
0x1800779ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800779b3  lea     r12, WPP_GLOBAL_Control
0x1800779ba  mov     ebx, [rbp+47h+arg_28]
0x1800779bd  mov     r15d, [rbp+47h+arg_20]
0x1800779c1  cmp     rcx, r12
0x1800779c4  jz      short loc_1800779EB
0x1800779c6  test    byte ptr [rcx+1Ch], 1
0x1800779ca  jz      short loc_1800779EB
0x1800779cc  mov     rcx, [rcx+10h]
0x1800779d0  mov     [rsp+0F0h+var_B8], ebx
0x1800779d4  mov     [rsp+0F0h+var_C0], r15d
0x1800779d9  mov     [rsp+0F0h+var_C8], r9d
0x1800779de  mov     r9, r14
0x1800779e1  mov     dword ptr [rsp+0F0h+ReturnLength], r8d
0x1800779e6  call    WPP_SF_SDDDD
0x1800779eb  mov     r9d, 4; TokenInformationLength
0x1800779f1  mov     [rbp+47h+arg_8], 0
0x1800779f8  lea     rax, [rbp+47h+arg_8]
0x1800779fc  mov     [rbp+47h+TokenInformation], 0
0x180077a03  lea     r8, [rbp+47h+TokenInformation]; TokenInformation
0x180077a07  mov     [rsp+0F0h+ReturnLength], rax; ReturnLength
0x180077a0c  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x180077a13  lea     edx, [r9+19h]; TokenInformationClass
0x180077a17  call    cs:__imp_GetTokenInformation
0x180077a1d  test    eax, eax
0x180077a1f  jnz     short loc_180077A61
0x180077a21  mov     rax, cs:WPP_GLOBAL_Control
0x180077a28  cmp     rax, r12
0x180077a2b  jz      short loc_180077A58
0x180077a2d  test    byte ptr [rax+1Ch], 4
0x180077a31  jz      short loc_180077A58
0x180077a33  call    cs:__imp_GetLastError
0x180077a39  mov     rcx, cs:WPP_GLOBAL_Control
0x180077a40  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x180077a47  mov     edx, 28h ; '('
0x180077a4c  mov     r9d, eax
0x180077a4f  mov     rcx, [rcx+10h]
0x180077a53  call    WPP_SF_d
0x180077a58  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180077a5c  jmp     loc_180077B35
0x180077a61  mov     eax, ebx
0x180077a63  mov     [rbp+47h+var_A4], 0
0x180077a6a  and     eax, 7FB7h
0x180077a6f  mov     [rbp+47h+var_B0], 20h ; ' '
0x180077a76  mov     [rbp+47h+var_AC], eax
0x180077a79  xorps   xmm0, xmm0
0x180077a7c  mov     eax, ebx
0x180077a7e  and     eax, 0FFF00000h
0x180077a83  mov     [rbp+47h+var_A8], eax
0x180077a86  movdqu  [rbp+47h+var_A0], xmm0
0x180077a8b  bt      ebx, 14h
0x180077a8f  jnb     short loc_180077A9A
0x180077a91  and     ebx, 1F0000h
0x180077a97  mov     [rbp+47h+var_A4], ebx
0x180077a9a  cmp     [rbp+47h+TokenInformation], 0
0x180077a9e  jz      short loc_180077ACB
0x180077aa0  call    ?IsAppContainerFileFunctionalitySupported@@YA_NXZ; IsAppContainerFileFunctionalitySupported(void)
0x180077aa5  test    al, al
0x180077aa7  jz      short loc_180077ACB
0x180077aa9  lea     rax, [rbp+47h+var_B0]
0x180077aad  mov     r9d, r15d; unsigned int
0x180077ab0  mov     r8d, edi; unsigned int
0x180077ab3  mov     [rsp+0F0h+ReturnLength], rax; struct _CREATEFILE2_EXTENDED_PARAMETERS *
0x180077ab8  mov     edx, esi; unsigned int
0x180077aba  lea     r12, aBitscreatefile; "BITSCreateFile2AsApp"
0x180077ac1  mov     rcx, r14; unsigned __int16 *
0x180077ac4  call    ?BITSCreateFile2AsApp@@YAPEAXPEBGKKKPEAU_CREATEFILE2_EXTENDED_PARAMETERS@@@Z; BITSCreateFile2AsApp(ushort const *,ulong,ulong,ulong,_CREATEFILE2_EXTENDED_PARAMETERS *)
0x180077ac9  jmp     short loc_180077AEC
0x180077acb  lea     rax, [rbp+47h+var_B0]
0x180077acf  mov     r9d, r15d
0x180077ad2  mov     r8d, edi
0x180077ad5  mov     [rsp+0F0h+ReturnLength], rax
0x180077ada  mov     edx, esi
0x180077adc  lea     r12, aCreatefile2; "CreateFile2"
0x180077ae3  mov     rcx, r14
0x180077ae6  call    cs:__imp_CreateFile2
0x180077aec  mov     rbx, rax
0x180077aef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180077af3  jnz     short loc_180077B35
0x180077af5  mov     rax, cs:WPP_GLOBAL_Control
0x180077afc  lea     rcx, WPP_GLOBAL_Control
0x180077b03  cmp     rax, rcx
0x180077b06  jz      short loc_180077B35
0x180077b08  test    byte ptr [rax+1Ch], 2
0x180077b0c  jz      short loc_180077B35
0x180077b0e  call    cs:__imp_GetLastError
0x180077b14  mov     rcx, cs:WPP_GLOBAL_Control
0x180077b1b  lea     edx, [rbx+2Ah]
0x180077b1e  mov     r9, r12
0x180077b21  mov     dword ptr [rsp+0F0h+ReturnLength], eax
0x180077b25  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x180077b2c  mov     rcx, [rcx+10h]
0x180077b30  call    WPP_SF_Sd
0x180077b35  mov     [r13+0], rbx
0x180077b39  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180077b3d  jnz     short loc_180077B93
0x180077b3f  call    cs:__imp_GetLastError
0x180077b45  test    eax, eax
0x180077b47  jg      short loc_180077B51
0x180077b49  call    cs:__imp_GetLastError
0x180077b4f  jmp     short loc_180077B5F
0x180077b51  call    cs:__imp_GetLastError
0x180077b57  movzx   eax, ax
0x180077b5a  or      eax, 80070000h
0x180077b5f  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180077b66  mov     [rbp+47h+var_78], eax
0x180077b69  mov     [rbp+47h+pExceptionObject], rcx
0x180077b6d  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180077b74  xorps   xmm0, xmm0
0x180077b77  mov     [rbp+47h+var_74], 189h
0x180077b7e  lea     rcx, [rbp+47h+pExceptionObject]; pExceptionObject
0x180077b82  mov     [rbp+47h+var_70], 1
0x180077b89  movups  [rbp+47h+var_88], xmm0
0x180077b8d  call    _CxxThrowException_0
0x180077b93  mov     rbx, [rsp+0F0h+arg_10]
0x180077b9b  add     rsp, 0C0h
0x180077ba2  pop     r15
0x180077ba4  pop     r14
0x180077ba6  pop     r13
0x180077ba8  pop     r12
0x180077baa  pop     rdi
0x180077bab  pop     rsi
0x180077bac  pop     rbp
0x180077bad  retn
```
