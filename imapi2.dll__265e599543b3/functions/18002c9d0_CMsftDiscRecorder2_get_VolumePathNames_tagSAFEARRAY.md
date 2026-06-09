# CMsftDiscRecorder2::get_VolumePathNames(tagSAFEARRAY * *)

- ea: `0x18002c9d0`
- end: `0x18002cdbf`
- name: `?get_VolumePathNames@CMsftDiscRecorder2@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `1007`
- prototype: `__int64 __fastcall(CMsftDiscRecorder2 *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002fc8`
- `0x18000f740`
- `0x1800140f4`
- `0x180014134`
- `0x180016778`
- `0x18001cb0c`
- `0x1800236b4`
- `0x18002c9d0`
- `0x1800434c4`
- `0x18004984a`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002caab`
- `KERNEL32!SetLastError` at `0x18002cbb2`
- `KERNEL32!SetLastError` at `0x18002caab`
- `KERNEL32!SetLastError` at `0x18002cbb2`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18002cabf`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18002cbcc`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18002cabf`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18002cbcc`
- `KERNEL32!LocalAlloc` at `0x18002cb3a`
- `KERNEL32!LocalAlloc` at `0x18002cb3a`
- `KERNEL32!LocalFree` at `0x18002cd8e`
- `KERNEL32!LocalFree` at `0x18002cd8e`
- `KERNEL32!GetLastError` at `0x18002cac5`
- `KERNEL32!GetLastError` at `0x18002cac5`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::get_VolumePathNames(LPCWSTR *this, struct tagSAFEARRAY **a2)
{
  WCHAR *v4; // r12
  signed int v5; // ebx
  __int64 v6; // r9
  int v7; // edx
  Imapi2Utility *v8; // rcx
  unsigned int LastErrorAsHresultForceFailure; // eax
  DWORD v10; // r14d
  WCHAR *v11; // rax
  Imapi2Utility *v12; // rcx
  struct tagSAFEARRAY **v13; // r9
  unsigned int v14; // eax
  int VariantSafeArrayFromMultiSzCch; // eax
  const struct _GUID *v16; // r8
  DWORD cchReturnLength; // [rsp+78h] [rbp+10h] BYREF
  struct tagSAFEARRAY *v20; // [rsp+80h] [rbp+18h] BYREF

  v20 = 0;
  v4 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 224, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    }
    v5 = -2147467261;
    goto LABEL_54;
  }
  *a2 = 0;
  v6 = *((unsigned int *)this + 60);
  if ( (v6 & 2) == 0 )
  {
    v5 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        225,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        v6,
        -2147467259);
    }
    goto LABEL_54;
  }
  cchReturnLength = 0;
  SetLastError(0);
  GetVolumePathNamesForVolumeNameW(this[15], 0, 0, &cchReturnLength);
  if ( GetLastError() == 234 )
  {
    v10 = cchReturnLength;
  }
  else
  {
    LastErrorAsHresultForceFailure = Imapi2Utility::GetLastErrorAsHresultForceFailure(v8, v7);
    v5 = LastErrorAsHresultForceFailure;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        226,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        LastErrorAsHresultForceFailure);
    }
    v10 = 0;
    if ( v5 < 0 )
    {
LABEL_54:
      Imapi2Utility::SafeArrayDestroyAndNull((Imapi2Utility *)&v20, a2);
      if ( !v4 )
        goto LABEL_56;
      goto LABEL_55;
    }
  }
  v11 = (WCHAR *)LocalAlloc(0x40u, 2LL * v10);
  v4 = v11;
  if ( !v11 )
  {
    v5 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        227,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        2 * v10,
        2 * v10);
    }
    goto LABEL_54;
  }
  memset_0(v11, 0, 2LL * v10);
  cchReturnLength = 0;
  SetLastError(0);
  if ( GetVolumePathNamesForVolumeNameW(this[15], v4, v10, &cchReturnLength) )
  {
    if ( cchReturnLength != v10 )
    {
      v5 = -2147467259;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
      {
        WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 22), 229, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      }
      goto LABEL_54;
    }
    if ( v10 >= 2 )
    {
      if ( v4[v10 - 1] || v4[v10 - 2] )
      {
        v5 = -2147467259;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 231, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
        }
        goto LABEL_54;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 230, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    }
  }
  else
  {
    v14 = Imapi2Utility::GetLastErrorAsHresultForceFailure(v12, (int)a2);
    v5 = v14;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 228, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, v14);
    }
    if ( v5 < 0 )
      goto LABEL_54;
  }
  VariantSafeArrayFromMultiSzCch = Imapi2Utility::CreateVariantSafeArrayFromMultiSzCch(
                                     v4,
                                     (const unsigned __int16 *)v10,
                                     (unsigned int)&v20,
                                     v13);
  v5 = VariantSafeArrayFromMultiSzCch;
  if ( VariantSafeArrayFromMultiSzCch < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        232,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        (unsigned int)VariantSafeArrayFromMultiSzCch);
    }
    goto LABEL_54;
  }
  *a2 = v20;
LABEL_55:
  LocalFree(v4);
LABEL_56:
  if ( (v5 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v5, (int)&CLSID_MsftDiscRecorder2, v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002c9d0  mov     r11, rsp
0x18002c9d3  mov     [r11+8], rcx
0x18002c9d7  push    rbx
0x18002c9d8  push    rbp
0x18002c9d9  push    r12
0x18002c9db  push    r13
0x18002c9dd  push    r14
0x18002c9df  sub     rsp, 40h
0x18002c9e3  xor     eax, eax
0x18002c9e5  mov     r13, rdx
0x18002c9e8  mov     [r11+18h], rax
0x18002c9ec  mov     rbx, rcx
0x18002c9ef  mov     r12d, eax
0x18002c9f2  test    rdx, rdx
0x18002c9f5  jnz     short loc_18002CA3E
0x18002c9f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c9fe  lea     rbp, WPP_GLOBAL_Control
0x18002ca05  cmp     rcx, rbp
0x18002ca08  jz      short loc_18002CA34
0x18002ca0a  test    byte ptr [rcx+0BCh], 4
0x18002ca11  jz      short loc_18002CA34
0x18002ca13  cmp     byte ptr [rcx+0B9h], 3
0x18002ca1a  jb      short loc_18002CA34
0x18002ca1c  mov     rcx, [rcx+0B0h]
0x18002ca23  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002ca2a  mov     edx, 0E0h
0x18002ca2f  call    WPP_SF_
0x18002ca34  mov     ebx, 80004003h
0x18002ca39  jmp     loc_18002CD79
0x18002ca3e  mov     [rdx], rax
0x18002ca41  mov     r9d, [rcx+0F0h]
0x18002ca48  test    r9b, 2
0x18002ca4c  jnz     short loc_18002CAA5
0x18002ca4e  mov     ebx, 80004005h
0x18002ca53  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca5a  lea     rbp, WPP_GLOBAL_Control
0x18002ca61  cmp     rcx, rbp
0x18002ca64  jz      loc_18002CD79
0x18002ca6a  test    byte ptr [rcx+0BCh], 4
0x18002ca71  jz      loc_18002CD79
0x18002ca77  cmp     byte ptr [rcx+0B9h], 3
0x18002ca7e  jb      loc_18002CD79
0x18002ca84  mov     rcx, [rcx+0B0h]
0x18002ca8b  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002ca92  mov     edx, 0E1h
0x18002ca97  mov     [rsp+68h+var_48], ebx
0x18002ca9b  call    WPP_SF_Dd
0x18002caa0  jmp     loc_18002CD79
0x18002caa5  xor     ecx, ecx; dwErrCode
0x18002caa7  mov     [rsp+68h+cchReturnLength], eax
0x18002caab  call    cs:__imp_SetLastError
0x18002cab1  mov     rcx, [rbx+78h]; lpszVolumeName
0x18002cab5  lea     r9, [rsp+68h+cchReturnLength]; lpcchReturnLength
0x18002caba  xor     r8d, r8d; cchBufferLength
0x18002cabd  xor     edx, edx; lpszVolumePathNames
0x18002cabf  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18002cac5  call    cs:__imp_GetLastError
0x18002cacb  lea     rbp, WPP_GLOBAL_Control
0x18002cad2  cmp     eax, 0EAh
0x18002cad7  jz      short loc_18002CB27
0x18002cad9  call    ?GetLastErrorAsHresultForceFailure@Imapi2Utility@@YAJJ@Z; Imapi2Utility::GetLastErrorAsHresultForceFailure(long)
0x18002cade  mov     ebx, eax
0x18002cae0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cae7  cmp     rcx, rbp
0x18002caea  jz      short loc_18002CB19
0x18002caec  test    byte ptr [rcx+0BCh], 4
0x18002caf3  jz      short loc_18002CB19
0x18002caf5  cmp     byte ptr [rcx+0B9h], 3
0x18002cafc  jb      short loc_18002CB19
0x18002cafe  mov     rcx, [rcx+0B0h]
0x18002cb05  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002cb0c  mov     edx, 0E2h
0x18002cb11  mov     r9d, eax
0x18002cb14  call    WPP_SF_d
0x18002cb19  xor     eax, eax
0x18002cb1b  mov     r14d, eax
0x18002cb1e  test    ebx, ebx
0x18002cb20  jns     short loc_18002CB2C
0x18002cb22  jmp     loc_18002CD79
0x18002cb27  mov     r14d, [rsp+68h+cchReturnLength]
0x18002cb2c  mov     ebx, r14d
0x18002cb2f  mov     ecx, 40h ; '@'; uFlags
0x18002cb34  add     rbx, rbx
0x18002cb37  mov     rdx, rbx; uBytes
0x18002cb3a  call    cs:__imp_LocalAlloc
0x18002cb40  mov     r12, rax
0x18002cb43  test    rax, rax
0x18002cb46  jnz     short loc_18002CB9D
0x18002cb48  mov     ebx, 8007000Eh
0x18002cb4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb54  cmp     rcx, rbp
0x18002cb57  jz      loc_18002CD79
0x18002cb5d  test    byte ptr [rcx+0BCh], 4
0x18002cb64  jz      loc_18002CD79
0x18002cb6a  cmp     byte ptr [rcx+0B9h], 3
0x18002cb71  jb      loc_18002CD79
0x18002cb77  mov     rcx, [rcx+0B0h]
0x18002cb7e  lea     r9d, [r14+r14]
0x18002cb82  mov     edx, 0E3h
0x18002cb87  mov     [rsp+68h+var_48], r9d
0x18002cb8c  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002cb93  call    WPP_SF_Dd
0x18002cb98  jmp     loc_18002CD79
0x18002cb9d  mov     r8, rbx; Size
0x18002cba0  xor     edx, edx; Val
0x18002cba2  mov     rcx, r12; void *
0x18002cba5  call    memset_0
0x18002cbaa  xor     ebx, ebx
0x18002cbac  xor     ecx, ecx; dwErrCode
0x18002cbae  mov     [rsp+68h+cchReturnLength], ebx
0x18002cbb2  call    cs:__imp_SetLastError
0x18002cbb8  mov     rcx, [rsp+68h+arg_0]
0x18002cbbd  lea     r9, [rsp+68h+cchReturnLength]; lpcchReturnLength
0x18002cbc2  mov     r8d, r14d; cchBufferLength
0x18002cbc5  mov     rdx, r12; lpszVolumePathNames
0x18002cbc8  mov     rcx, [rcx+78h]; lpszVolumeName
0x18002cbcc  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18002cbd2  test    eax, eax
0x18002cbd4  jnz     short loc_18002CC23
0x18002cbd6  call    ?GetLastErrorAsHresultForceFailure@Imapi2Utility@@YAJJ@Z; Imapi2Utility::GetLastErrorAsHresultForceFailure(long)
0x18002cbdb  mov     ebx, eax
0x18002cbdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbe4  cmp     rcx, rbp
0x18002cbe7  jz      short loc_18002CC16
0x18002cbe9  test    byte ptr [rcx+0BCh], 4
0x18002cbf0  jz      short loc_18002CC16
0x18002cbf2  cmp     byte ptr [rcx+0B9h], 3
0x18002cbf9  jb      short loc_18002CC16
0x18002cbfb  mov     rcx, [rcx+0B0h]
0x18002cc02  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002cc09  mov     edx, 0E4h
0x18002cc0e  mov     r9d, eax
0x18002cc11  call    WPP_SF_d
0x18002cc16  test    ebx, ebx
0x18002cc18  jns     loc_18002CCDC
0x18002cc1e  jmp     loc_18002CD79
0x18002cc23  mov     eax, [rsp+68h+cchReturnLength]
0x18002cc27  cmp     eax, r14d
0x18002cc2a  jz      short loc_18002CC88
0x18002cc2c  mov     ebx, 80004005h
0x18002cc31  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc38  cmp     rcx, rbp
0x18002cc3b  jz      loc_18002CD79
0x18002cc41  test    byte ptr [rcx+0BCh], 4
0x18002cc48  jz      loc_18002CD79
0x18002cc4e  cmp     byte ptr [rcx+0B9h], 3
0x18002cc55  jb      loc_18002CD79
0x18002cc5b  mov     rcx, [rcx+0B0h]
0x18002cc62  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002cc69  mov     [rsp+68h+var_38], eax
0x18002cc6d  mov     edx, 0E5h
0x18002cc72  mov     [rsp+68h+var_40], eax
0x18002cc76  mov     r9d, r14d
0x18002cc79  mov     [rsp+68h+var_48], r14d
0x18002cc7e  call    WPP_SF_DDDd
0x18002cc83  jmp     loc_18002CD79
0x18002cc88  cmp     r14d, 2
0x18002cc8c  jnb     short loc_18002CCC6
0x18002cc8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc95  cmp     rcx, rbp
0x18002cc98  jz      short loc_18002CCDC
0x18002cc9a  test    byte ptr [rcx+0BCh], 4
0x18002cca1  jz      short loc_18002CCDC
0x18002cca3  cmp     byte ptr [rcx+0B9h], 3
0x18002ccaa  jb      short loc_18002CCDC
0x18002ccac  mov     rcx, [rcx+0B0h]
0x18002ccb3  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002ccba  mov     edx, 0E6h
0x18002ccbf  call    WPP_SF_
0x18002ccc4  jmp     short loc_18002CCDC
0x18002ccc6  lea     eax, [r14-1]
0x18002ccca  cmp     [r12+rax*2], bx
0x18002cccf  jnz     short loc_18002CD3E
0x18002ccd1  lea     eax, [r14-2]
0x18002ccd5  cmp     [r12+rax*2], bx
0x18002ccda  jnz     short loc_18002CD3E
0x18002ccdc  lea     r8, [rsp+68h+arg_10]; unsigned int
0x18002cce4  mov     edx, r14d; unsigned __int16 *
0x18002cce7  mov     rcx, r12; strIn
0x18002ccea  call    ?CreateVariantSafeArrayFromMultiSzCch@Imapi2Utility@@YA?BJPEBGKPEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::CreateVariantSafeArrayFromMultiSzCch(ushort const *,ulong,tagSAFEARRAY * *)
0x18002ccef  mov     ebx, eax
0x18002ccf1  test    eax, eax
0x18002ccf3  jns     short loc_18002CD30
0x18002ccf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ccfc  cmp     rcx, rbp
0x18002ccff  jz      short loc_18002CD79
0x18002cd01  test    byte ptr [rcx+0BCh], 4
0x18002cd08  jz      short loc_18002CD79
0x18002cd0a  cmp     byte ptr [rcx+0B9h], 3
0x18002cd11  jb      short loc_18002CD79
0x18002cd13  mov     rcx, [rcx+0B0h]
0x18002cd1a  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002cd21  mov     edx, 0E8h
0x18002cd26  mov     r9d, eax
0x18002cd29  call    WPP_SF_d
0x18002cd2e  jmp     short loc_18002CD79
0x18002cd30  mov     rax, [rsp+68h+arg_10]
0x18002cd38  mov     [r13+0], rax
0x18002cd3c  jmp     short loc_18002CD8B
0x18002cd3e  mov     ebx, 80004005h
0x18002cd43  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd4a  cmp     rcx, rbp
0x18002cd4d  jz      short loc_18002CD79
0x18002cd4f  test    byte ptr [rcx+0BCh], 4
0x18002cd56  jz      short loc_18002CD79
0x18002cd58  cmp     byte ptr [rcx+0B9h], 3
0x18002cd5f  jb      short loc_18002CD79
0x18002cd61  mov     rcx, [rcx+0B0h]
0x18002cd68  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002cd6f  mov     edx, 0E7h
0x18002cd74  call    WPP_SF_
0x18002cd79  lea     rcx, [rsp+68h+arg_10]; this
0x18002cd81  call    ?SafeArrayDestroyAndNull@Imapi2Utility@@YAXAEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::SafeArrayDestroyAndNull(tagSAFEARRAY * &)
0x18002cd86  test    r12, r12
0x18002cd89  jz      short loc_18002CD94
0x18002cd8b  mov     rcx, r12; hMem
0x18002cd8e  call    cs:__imp_LocalFree
0x18002cd94  mov     eax, ebx
0x18002cd96  and     eax, 80FF0000h
0x18002cd9b  cmp     eax, 80AA0000h
0x18002cda0  jnz     short loc_18002CDB0
0x18002cda2  lea     rdx, CLSID_MsftDiscRecorder2; int
0x18002cda9  mov     ecx, ebx; dwMessageId
0x18002cdab  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18002cdb0  mov     eax, ebx
0x18002cdb2  add     rsp, 40h
0x18002cdb6  pop     r14
0x18002cdb8  pop     r13
0x18002cdba  pop     r12
0x18002cdbc  pop     rbp
0x18002cdbd  pop     rbx
0x18002cdbe  retn
```
