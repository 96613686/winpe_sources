# LegacyQmgrStateFilesManager::TryOpenStateFile(ulong)

- ea: `0x180049810`
- end: `0x180049c36`
- name: `?TryOpenStateFile@LegacyQmgrStateFilesManager@@AEAA_NK@Z`
- size: `1062`
- prototype: `char __fastcall(LegacyQmgrStateFilesManager *this, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180049614`

## callees

- `0x180049810`
- `0x180049c3c`
- `0x18009befc`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800ab738`
- `0x1800e0fa4`
- `0x1800e1068`
- `0x1800e1114`
- `0x1800e11e0`
- `0x1800e1578`
- `0x1800f5574`
- `0x1800f5798`
- `0x1800f5d60`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049a44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049a6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049a44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049a6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800498a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800498a6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004994e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004994e`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180049a1b`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180049a1b`

## string_xrefs

- `0x180049a10`: `CreateFile2`
- `0x1800499e6`: `BITSCreateFile2AsApp`

## pseudocode

```c
char __fastcall LegacyQmgrStateFilesManager::TryOpenStateFile(LegacyQmgrStateFilesManager *this, unsigned int a2)
{
  __int64 v3; // r14
  __int64 *FileNameFromIndex; // rax
  __int64 v5; // r8
  void *v6; // rcx
  char *v7; // r12
  GUID *v8; // r15
  __int64 v9; // rcx
  unsigned __int16 *v10; // rax
  DWORD LastError; // eax
  const wchar_t *v12; // r13
  void *File2; // rax
  char v14; // al
  signed int v15; // ebx
  __int64 v17; // r9
  LegacyQmgrStateFilesManager *v18; // rcx
  __int64 v19; // rax
  unsigned int v20; // r9d
  LegacyQmgrStateFilesManager *v21; // rcx
  __int64 v22; // r8
  LegacyQmgrStateFilesManager *v23; // rcx
  LegacyQmgrStateFilesManager *v24; // rcx
  unsigned int v25; // r9d
  unsigned int v26; // r9d
  __int64 v27; // rax
  LegacyQmgrStateFilesManager *v28; // rcx
  __int128 v29; // [rsp+40h] [rbp-79h] BYREF
  __int64 v30; // [rsp+50h] [rbp-69h]
  _QWORD v31[5]; // [rsp+58h] [rbp-61h] BYREF
  void **pExceptionObject; // [rsp+80h] [rbp-39h] BYREF
  __int128 v33; // [rsp+88h] [rbp-31h]
  signed int v34; // [rsp+98h] [rbp-21h]
  int v35; // [rsp+9Ch] [rbp-1Dh]
  int v36; // [rsp+A0h] [rbp-19h]
  void *ReturnLength; // [rsp+120h] [rbp+67h] BYREF
  int TokenInformation; // [rsp+128h] [rbp+6Fh] BYREF
  unsigned __int16 *v39; // [rsp+130h] [rbp+77h]

  v3 = a2;
  FileNameFromIndex = (__int64 *)LegacyQmgrStateFilesManager::GetFileNameFromIndex(&ReturnLength);
  v5 = *FileNameFromIndex;
  *FileNameFromIndex = 0;
  v6 = (void *)*((_QWORD *)this + v3 + 2);
  *((_QWORD *)this + v3 + 2) = v5;
  if ( v6 )
    operator delete(v6, 2u);
  if ( ReturnLength )
    operator delete(ReturnLength, 2u);
  *((_QWORD *)this + v3 + 4) = 0;
  *((_QWORD *)this + v3 + 6) = 0;
  v7 = (char *)this + 8 * v3;
  *((_QWORD *)v7 + 8) = 0;
  v8 = (GUID *)((char *)this + 16 * v3 + 80);
  *v8 = GUID_NULL;
  if ( *(_QWORD *)v7 != -1 )
    CloseHandle(*(HANDLE *)v7);
  *(_QWORD *)v7 = -1;
  v30 = 0;
  v29 = 0;
  LODWORD(v29) = 24;
  v9 = *((_QWORD *)g_GlobalInfo + 5);
  v10 = (unsigned __int16 *)*((_QWORD *)this + v3 + 2);
  v39 = v10;
  *((_QWORD *)&v29 + 1) = v9;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)&WPP_GLOBAL_Control,
      v5,
      (_DWORD)v10,
      0,
      1,
      3,
      0x8000000,
      v29,
      v30);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids, LastError);
    }
LABEL_22:
    v15 = GetLastError();
    if ( v15 != 2 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( v15 > 0 )
          v17 = (unsigned __int16)v15 | 0x80070000;
        else
          v17 = (unsigned int)v15;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_95c67aae43af30e544d2621a4e92d158_Traceguids, v17);
      }
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      v34 = v15;
      v35 = 610;
      pExceptionObject = &ComError::`vftable';
      v36 = 1;
      v33 = 0;
      throw (ComError *)&pExceptionObject;
    }
    return 0;
  }
  v31[1] = 0x8000000;
  v31[2] = &v29;
  v31[0] = 32;
  v31[3] = 0;
  if ( TokenInformation && IsAppContainerFileFunctionalitySupported() )
  {
    v12 = L"BITSCreateFile2AsApp";
    File2 = BITSCreateFile2AsApp(v39, 0xC0000000, 1u, 3u, (struct _CREATEFILE2_EXTENDED_PARAMETERS *)v31);
  }
  else
  {
    v12 = L"CreateFile2";
    File2 = (void *)CreateFile2(v39, 3221225472LL, 1, 3, v31);
  }
  if ( File2 == (void *)-1LL )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v14 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids,
        (_DWORD)v12,
        v14);
    }
    goto LABEL_22;
  }
  auto_HANDLE<-1>::operator=((char *)this + 8 * v3, File2);
  v19 = LegacyQmgrStateFilesManager::BITSGetFileSize(v18, *(void **)v7);
  *((_QWORD *)this + v3 + 4) = v19;
  if ( v19 <= 0x4000 )
  {
    *((_QWORD *)this + v3 + 6) = 0x4000;
    if ( !v19 )
    {
      LegacyQmgrStateFilesManager::DeleteStateFile(this, v3);
      return 0;
    }
  }
  else
  {
    *((_QWORD *)this + v3 + 6) = v19;
  }
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_95c67aae43af30e544d2621a4e92d158_Traceguids, (unsigned int)v3);
  v22 = *((_QWORD *)this + v3 + 6);
  if ( *((_QWORD *)this + v3 + 4) != v22 )
  {
    LegacyQmgrStateFilesManager::BITSSetFilePointer(v21, *(void **)v7, v22, v20);
    LegacyQmgrStateFilesManager::BITSSetEndOfFile(v23, *(void **)v7);
    LegacyQmgrStateFilesManager::BITSSetFilePointer(v24, *(void **)v7, 0, v25);
  }
  LegacyQmgrStateFilesManager::ReadFromFile(*(HANDLE *)v7, (char *)this + 16 * v3 + 80, 0x10u);
  v27 = *(_QWORD *)&v8->Data1 - 0x45E9C7A609ED3228LL;
  if ( *(_QWORD *)&v8->Data1 == 0x45E9C7A609ED3228LL )
    v27 = *(_QWORD *)v8->Data4 - 0x3E7CC246D9366D8FLL;
  if ( v27 )
  {
    *((_QWORD *)v7 + 8) = 0;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        WPP_95c67aae43af30e544d2621a4e92d158_Traceguids,
        (unsigned int)v3);
  }
  else
  {
    LegacyQmgrStateFilesManager::ReadFromFile(*(HANDLE *)v7, v7 + 64, 8u);
  }
  LegacyQmgrStateFilesManager::BITSSetFilePointer(v28, *(void **)v7, 0, v26);
  return 1;
}

```

## disassembly

```asm
0x180049810  mov     [rsp-8+arg_18], rbx
0x180049815  push    rbp
0x180049816  push    rsi
0x180049817  push    rdi
0x180049818  push    r12
0x18004981a  push    r13
0x18004981c  push    r14
0x18004981e  push    r15
0x180049820  lea     rbp, [rsp-27h]
0x180049825  sub     rsp, 0E0h
0x18004982c  mov     rbx, rcx
0x18004982f  mov     r14d, edx
0x180049832  lea     rcx, [rbp+57h+arg_0]
0x180049836  call    ?GetFileNameFromIndex@LegacyQmgrStateFilesManager@@CA?AV?$unique_ptr@GU?$default_delete@G@std@@@std@@K@Z; LegacyQmgrStateFilesManager::GetFileNameFromIndex(ulong)
0x18004983b  xor     r13d, r13d
0x18004983e  mov     r8, [rax]
0x180049841  mov     [rax], r13
0x180049844  mov     rcx, [rbx+r14*8+10h]; void *
0x180049849  mov     [rbx+r14*8+10h], r8
0x18004984e  test    rcx, rcx
0x180049851  jz      short loc_18004985C
0x180049853  lea     edx, [r13+2]; unsigned __int64
0x180049857  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004985c  mov     rcx, [rbp+57h+arg_0]; void *
0x180049860  test    rcx, rcx
0x180049863  jz      short loc_18004986F
0x180049865  mov     edx, 2; unsigned __int64
0x18004986a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004986f  mov     [rbx+r14*8+20h], r13
0x180049874  lea     r15, [r14+5]
0x180049878  mov     [rbx+r14*8+30h], r13
0x18004987d  lea     r12, [rbx+r14*8]
0x180049881  mov     [r12+40h], r13
0x180049886  lea     rsi, [rbx+r14*8]
0x18004988a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180049891  shl     r15, 4
0x180049895  add     r15, rbx
0x180049898  movdqu  xmmword ptr [r15], xmm0
0x18004989d  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1800498a1  jz      short loc_1800498AC
0x1800498a3  mov     rcx, [rsi]; hObject
0x1800498a6  call    cs:__imp_CloseHandle
0x1800498ac  xor     eax, eax
0x1800498ae  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1800498b5  mov     [rbp+57h+var_C0], rax
0x1800498b9  xorps   xmm0, xmm0
0x1800498bc  mov     rax, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x1800498c3  movups  [rbp+57h+var_D0], xmm0
0x1800498c7  mov     dword ptr [rbp+57h+var_D0], 18h
0x1800498ce  mov     rcx, [rax+28h]
0x1800498d2  mov     rax, [rbx+r14*8+10h]
0x1800498d7  mov     [rbp+57h+arg_10], rax
0x1800498db  mov     qword ptr [rbp+57h+var_D0+8], rcx
0x1800498df  mov     dword ptr [rbp+57h+var_C0], r13d
0x1800498e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800498ea  lea     rdx, WPP_GLOBAL_Control
0x1800498f1  cmp     rcx, rdx
0x1800498f4  jz      short loc_180049928
0x1800498f6  test    byte ptr [rcx+1Ch], 1
0x1800498fa  jz      short loc_180049928
0x1800498fc  mov     rcx, [rcx+10h]
0x180049900  mov     r9, rax
0x180049903  mov     [rsp+110h+var_D8], 8000000h
0x18004990b  mov     [rsp+110h+var_E0], 3
0x180049913  mov     [rsp+110h+var_E8], 1
0x18004991b  mov     dword ptr [rsp+110h+ReturnLength], 0C0000000h
0x180049923  call    WPP_SF_SDDDD
0x180049928  mov     r9d, 4; TokenInformationLength
0x18004992e  mov     dword ptr [rbp+57h+arg_0], r13d
0x180049932  lea     rax, [rbp+57h+arg_0]
0x180049936  mov     [rbp+57h+TokenInformation], r13d
0x18004993a  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18004993e  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x180049943  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18004994a  lea     edx, [r9+19h]; TokenInformationClass
0x18004994e  call    cs:__imp_GetTokenInformation
0x180049954  test    eax, eax
0x180049956  jnz     short loc_1800499A3
0x180049958  mov     rax, cs:WPP_GLOBAL_Control
0x18004995f  lea     rdi, WPP_GLOBAL_Control
0x180049966  cmp     rax, rdi
0x180049969  jz      loc_180049A6D
0x18004996f  test    byte ptr [rax+1Ch], 4
0x180049973  jz      loc_180049A6D
0x180049979  call    cs:__imp_GetLastError
0x18004997f  mov     rcx, cs:WPP_GLOBAL_Control
0x180049986  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x18004998d  mov     edx, 28h ; '('
0x180049992  mov     r9d, eax
0x180049995  mov     rcx, [rcx+10h]
0x180049999  call    WPP_SF_d
0x18004999e  jmp     loc_180049A6D
0x1800499a3  lea     rax, [rbp+57h+var_D0]
0x1800499a7  mov     [rbp+57h+var_B0], 8000000h
0x1800499af  mov     [rbp+57h+var_A8], rax
0x1800499b3  mov     [rbp+57h+var_B8], 20h ; ' '
0x1800499bb  mov     [rbp+57h+var_A0], r13
0x1800499bf  cmp     [rbp+57h+TokenInformation], r13d
0x1800499c3  jz      short loc_1800499F8
0x1800499c5  call    ?IsAppContainerFileFunctionalitySupported@@YA_NXZ; IsAppContainerFileFunctionalitySupported(void)
0x1800499ca  test    al, al
0x1800499cc  jz      short loc_1800499F8
0x1800499ce  mov     rcx, [rbp+57h+arg_10]; unsigned __int16 *
0x1800499d2  lea     rax, [rbp+57h+var_B8]
0x1800499d6  mov     r9d, 3; unsigned int
0x1800499dc  mov     [rsp+110h+ReturnLength], rax; struct _CREATEFILE2_EXTENDED_PARAMETERS *
0x1800499e1  mov     edx, 0C0000000h; unsigned int
0x1800499e6  lea     r13, aBitscreatefile; "BITSCreateFile2AsApp"
0x1800499ed  lea     r8d, [r9-2]; unsigned int
0x1800499f1  call    ?BITSCreateFile2AsApp@@YAPEAXPEBGKKKPEAU_CREATEFILE2_EXTENDED_PARAMETERS@@@Z; BITSCreateFile2AsApp(ushort const *,ulong,ulong,ulong,_CREATEFILE2_EXTENDED_PARAMETERS *)
0x1800499f6  jmp     short loc_180049A21
0x1800499f8  mov     rcx, [rbp+57h+arg_10]
0x1800499fc  lea     rax, [rbp+57h+var_B8]
0x180049a00  mov     r9d, 3
0x180049a06  mov     [rsp+110h+ReturnLength], rax
0x180049a0b  mov     edx, 0C0000000h
0x180049a10  lea     r13, aCreatefile2; "CreateFile2"
0x180049a17  lea     r8d, [r9-2]
0x180049a1b  call    cs:__imp_CreateFile2
0x180049a21  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180049a25  jnz     loc_180049AFA
0x180049a2b  mov     rax, cs:WPP_GLOBAL_Control
0x180049a32  lea     rdi, WPP_GLOBAL_Control
0x180049a39  cmp     rax, rdi
0x180049a3c  jz      short loc_180049A6D
0x180049a3e  test    byte ptr [rax+1Ch], 2
0x180049a42  jz      short loc_180049A6D
0x180049a44  call    cs:__imp_GetLastError
0x180049a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180049a51  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x180049a58  mov     edx, 29h ; ')'
0x180049a5d  mov     dword ptr [rsp+110h+ReturnLength], eax
0x180049a61  mov     r9, r13
0x180049a64  mov     rcx, [rcx+10h]
0x180049a68  call    WPP_SF_Sd
0x180049a6d  call    cs:__imp_GetLastError
0x180049a73  mov     ebx, eax
0x180049a75  cmp     eax, 2
0x180049a78  jnz     short loc_180049A81
0x180049a7a  xor     al, al
0x180049a7c  jmp     loc_180049C1B
0x180049a81  mov     rcx, cs:WPP_GLOBAL_Control
0x180049a88  mov     esi, 80070000h
0x180049a8d  cmp     rcx, rdi
0x180049a90  jz      short loc_180049ABD
0x180049a92  test    byte ptr [rcx+1Ch], 4
0x180049a96  jz      short loc_180049ABD
0x180049a98  test    ebx, ebx
0x180049a9a  jg      short loc_180049AA1
0x180049a9c  mov     r9d, ebx
0x180049a9f  jmp     short loc_180049AA8
0x180049aa1  movzx   r9d, bx
0x180049aa5  or      r9d, esi
0x180049aa8  mov     rcx, [rcx+10h]
0x180049aac  lea     r8, WPP_95c67aae43af30e544d2621a4e92d158_Traceguids
0x180049ab3  mov     edx, 1Eh
0x180049ab8  call    WPP_SF_d
0x180049abd  test    ebx, ebx
0x180049abf  jle     short loc_180049AC6
0x180049ac1  movzx   ebx, bx
0x180049ac4  or      ebx, esi
0x180049ac6  xorps   xmm0, xmm0
0x180049ac9  mov     [rbp+57h+var_78], ebx
0x180049acc  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180049ad3  mov     [rbp+57h+var_74], 262h
0x180049ada  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180049ae1  mov     [rbp+57h+pExceptionObject], rax
0x180049ae5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180049ae9  mov     [rbp+57h+var_70], 1
0x180049af0  movups  [rbp+57h+var_88], xmm0
0x180049af4  call    _CxxThrowException_0
0x180049afa  mov     rdx, rax
0x180049afd  mov     rcx, rsi
0x180049b00  call    ??4?$auto_HANDLE@$0?0@@QEAAAEAV0@PEAX@Z; auto_HANDLE<-1>::operator=(void *)
0x180049b05  mov     rdx, [rsi]; void *
0x180049b08  call    ?BITSGetFileSize@LegacyQmgrStateFilesManager@@AEAA_JPEAX@Z; LegacyQmgrStateFilesManager::BITSGetFileSize(void *)
0x180049b0d  mov     ecx, 4000h
0x180049b12  mov     [rbx+r14*8+20h], rax
0x180049b17  cmp     rax, rcx
0x180049b1a  jle     loc_180049BBD
0x180049b20  mov     [rbx+r14*8+30h], rax
0x180049b25  mov     rcx, cs:WPP_GLOBAL_Control
0x180049b2c  lea     r13, WPP_GLOBAL_Control
0x180049b33  cmp     rcx, r13
0x180049b36  jz      short loc_180049B56
0x180049b38  test    byte ptr [rcx+1Ch], 1
0x180049b3c  jz      short loc_180049B56
0x180049b3e  mov     rcx, [rcx+10h]
0x180049b42  lea     r8, WPP_95c67aae43af30e544d2621a4e92d158_Traceguids
0x180049b49  mov     edx, 1Fh
0x180049b4e  mov     r9d, r14d
0x180049b51  call    WPP_SF_d
0x180049b56  mov     r8, [rbx+r14*8+30h]; __int64
0x180049b5b  cmp     [rbx+r14*8+20h], r8
0x180049b60  jz      short loc_180049B7D
0x180049b62  mov     rdx, [rsi]; void *
0x180049b65  call    ?BITSSetFilePointer@LegacyQmgrStateFilesManager@@AEAA_JPEAX_JK@Z; LegacyQmgrStateFilesManager::BITSSetFilePointer(void *,__int64,ulong)
0x180049b6a  mov     rdx, [rsi]; void *
0x180049b6d  call    ?BITSSetEndOfFile@LegacyQmgrStateFilesManager@@AEAAXPEAX@Z; LegacyQmgrStateFilesManager::BITSSetEndOfFile(void *)
0x180049b72  mov     rdx, [rsi]; void *
0x180049b75  xor     r8d, r8d; __int64
0x180049b78  call    ?BITSSetFilePointer@LegacyQmgrStateFilesManager@@AEAA_JPEAX_JK@Z; LegacyQmgrStateFilesManager::BITSSetFilePointer(void *,__int64,ulong)
0x180049b7d  mov     rcx, [rsi]; hFile
0x180049b80  mov     r8d, 10h; nNumberOfBytesToRead
0x180049b86  mov     rdx, r15; void *
0x180049b89  call    ?ReadFromFile@LegacyQmgrStateFilesManager@@SAXPEAX0K@Z; LegacyQmgrStateFilesManager::ReadFromFile(void *,void *,ulong)
0x180049b8e  mov     rax, [r15]
0x180049b91  sub     rax, cs:qword_18011A7F0
0x180049b98  jnz     short loc_180049BA5
0x180049b9a  mov     rax, [r15+8]
0x180049b9e  sub     rax, cs:qword_18011A7F8
0x180049ba5  test    rax, rax
0x180049ba8  jnz     short loc_180049BDB
0x180049baa  mov     rcx, [rsi]; hFile
0x180049bad  lea     r8d, [rax+8]; nNumberOfBytesToRead
0x180049bb1  lea     rdx, [r12+40h]; void *
0x180049bb6  call    ?ReadFromFile@LegacyQmgrStateFilesManager@@SAXPEAX0K@Z; LegacyQmgrStateFilesManager::ReadFromFile(void *,void *,ulong)
0x180049bbb  jmp     short loc_180049C0E
0x180049bbd  mov     [rbx+r14*8+30h], rcx
0x180049bc2  test    rax, rax
0x180049bc5  jnz     loc_180049B25
0x180049bcb  mov     edx, r14d; unsigned int
0x180049bce  mov     rcx, rbx; this
0x180049bd1  call    ?DeleteStateFile@LegacyQmgrStateFilesManager@@AEAAXK@Z; LegacyQmgrStateFilesManager::DeleteStateFile(ulong)
0x180049bd6  jmp     loc_180049A7A
0x180049bdb  mov     qword ptr [r12+40h], 0
0x180049be4  mov     rcx, cs:WPP_GLOBAL_Control
0x180049beb  cmp     rcx, r13
0x180049bee  jz      short loc_180049C0E
0x180049bf0  test    byte ptr [rcx+1Ch], 1
0x180049bf4  jz      short loc_180049C0E
0x180049bf6  mov     rcx, [rcx+10h]
0x180049bfa  lea     r8, WPP_95c67aae43af30e544d2621a4e92d158_Traceguids
0x180049c01  mov     edx, 20h ; ' '
0x180049c06  mov     r9d, r14d
0x180049c09  call    WPP_SF_d
0x180049c0e  mov     rdx, [rsi]; void *
0x180049c11  xor     r8d, r8d; __int64
0x180049c14  call    ?BITSSetFilePointer@LegacyQmgrStateFilesManager@@AEAA_JPEAX_JK@Z; LegacyQmgrStateFilesManager::BITSSetFilePointer(void *,__int64,ulong)
0x180049c19  mov     al, 1
0x180049c1b  mov     rbx, [rsp+110h+arg_18]
0x180049c23  add     rsp, 0E0h
0x180049c2a  pop     r15
0x180049c2c  pop     r14
0x180049c2e  pop     r13
0x180049c30  pop     r12
0x180049c32  pop     rdi
0x180049c33  pop     rsi
0x180049c34  pop     rbp
0x180049c35  retn
```
