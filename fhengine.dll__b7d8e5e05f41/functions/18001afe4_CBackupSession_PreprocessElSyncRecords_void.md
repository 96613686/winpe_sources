# CBackupSession::PreprocessElSyncRecords(void)

- ea: `0x18001afe4`
- end: `0x18001b4d9`
- name: `?PreprocessElSyncRecords@CBackupSession@@AEAAJXZ`
- size: `1269`
- prototype: `__int64 __fastcall(CBackupSession *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001fee4`

## callees

- `0x1800025b0`
- `0x1800031b0`
- `0x1800077f0`
- `0x180007818`
- `0x180007a1c`
- `0x180007d5c`
- `0x18000835c`
- `0x180009258`
- `0x18000935c`
- `0x1800093a8`
- `0x1800094d0`
- `0x180009528`
- `0x18000960c`
- `0x180012520`
- `0x18001afe4`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001b266`
- `KERNEL32!GetLastError` at `0x18001b355`
- `KERNEL32!GetLastError` at `0x18001b266`
- `KERNEL32!GetLastError` at `0x18001b355`
- `KERNEL32!CloseHandle` at `0x18001b2fd`
- `KERNEL32!CloseHandle` at `0x18001b2fd`
- `KERNEL32!CreateFileW` at `0x18001b1f9`
- `KERNEL32!CreateFileW` at `0x18001b1f9`
- `KERNEL32!DeviceIoControl` at `0x18001b242`
- `KERNEL32!DeviceIoControl` at `0x18001b242`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b32f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b45f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b32f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b45f`

## pseudocode

```c
__int64 __fastcall CBackupSession::PreprocessElSyncRecords(CBackupSession *this)
{
  CNamespaceRecord *v2; // rax
  _QWORD *v3; // r15
  CNamespaceRecord *v4; // rax
  __int64 *v5; // rbx
  int v6; // eax
  unsigned int v7; // edi
  OLECHAR *v8; // rcx
  int v9; // eax
  HANDLE FileW; // r12
  char v11; // al
  int v12; // eax
  char LastError; // al
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  LPCWSTR lpFileName; // [rsp+60h] [rbp-29h] BYREF
  __int64 v18; // [rsp+68h] [rbp-21h] BYREF
  DWORD BytesReturned; // [rsp+70h] [rbp-19h] BYREF
  __int64 v20; // [rsp+78h] [rbp-11h] BYREF
  int v21; // [rsp+80h] [rbp-9h] BYREF
  int v22; // [rsp+84h] [rbp-5h] BYREF
  int v23; // [rsp+88h] [rbp-1h] BYREF
  int v24; // [rsp+8Ch] [rbp+3h] BYREF
  int v25; // [rsp+90h] [rbp+7h] BYREF
  __int64 OutBuffer; // [rsp+98h] [rbp+Fh] BYREF
  __int64 *v27; // [rsp+A0h] [rbp+17h] BYREF
  _QWORD v28[7]; // [rsp+A8h] [rbp+1Fh] BYREF
  __int16 v29; // [rsp+F8h] [rbp+6Fh] BYREF
  __int16 v30; // [rsp+100h] [rbp+77h] BYREF
  unsigned int v31; // [rsp+108h] [rbp+7Fh] BYREF

  v20 = 0;
  SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(&v27);
  v2 = (CNamespaceRecord *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = (_QWORD *)((char *)this + 24);
  if ( v2 )
    v4 = CNamespaceRecord::CNamespaceRecord(v2, (__int64 *)this + 3, (__int64)this + 32);
  else
    v4 = 0;
  SmartPtr<CNamespaceRecord>::operator=(&v27, v4);
  v5 = v27;
  if ( v27 && *v27 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64 *))(*(_QWORD *)*v3 + 296LL))(*v3, 5, 0, &v20);
    v7 = v6;
    if ( v6 == -2147023728 )
    {
      v7 = 0;
    }
    else if ( v6 >= 0 )
    {
      while ( 1 )
      {
        v18 = 0;
        v8 = 0;
        lpFileName = 0;
        v31 = 0;
        v25 = 0;
        v24 = 0;
        v30 = 0;
        v29 = 0;
        v28[0] = 0;
        v23 = 0;
        v22 = 0;
        v21 = 0;
        if ( *((_DWORD *)this + 40) )
          break;
        v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPCWSTR *, int *, int *, __int16 *, __int16 *, _QWORD *, int *, int *, int *))(*(_QWORD *)v20 + 48LL))(
               v20,
               &v31,
               &lpFileName,
               &v25,
               &v24,
               &v30,
               &v29,
               v28,
               &v23,
               &v22,
               &v21);
        v7 = v9;
        if ( v9 < 0 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v15 = 309;
LABEL_47:
            WPP_SF_d(v14[2], v15, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, (unsigned int)v9);
          }
LABEL_48:
          v8 = (OLECHAR *)lpFileName;
          goto LABEL_53;
        }
        if ( (*(int (__fastcall **)(_QWORD, _QWORD, __int64 *))(*(_QWORD *)*v3 + 240LL))(*v3, v31, &v18) >= 0 )
        {
          v9 = CNamespaceRecord::LoadCurrentFromEnum(*v5, &v18);
          v7 = v9;
          if ( v9 < 0 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v15 = 310;
              goto LABEL_47;
            }
            goto LABEL_48;
          }
          if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v18 + 32LL))(v18) == -2147023728 )
          {
            FileW = CreateFileW(lpFileName, 0, 7u, 0, 3u, 0x200080u, 0);
            if ( FileW == (HANDLE)-1LL )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                LastError = GetLastError();
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  314,
                  (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                  (_DWORD)lpFileName,
                  LastError);
              }
            }
            else
            {
              OutBuffer = 0;
              BytesReturned = 0;
              if ( DeviceIoControl(FileW, 0x900EFu, 0, 0, &OutBuffer, 8u, &BytesReturned, 0) )
              {
                if ( BytesReturned == 8 )
                {
                  *(_QWORD *)(*v5 + 68) = OutBuffer;
                  v12 = CNamespaceRecord::Commit((CNamespaceRecord *)*v5);
                  v7 = v12;
                  if ( v12 < 0 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      WPP_SF_dSd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        313,
                        (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                        *(_DWORD *)(*v5 + 16),
                        (__int64)lpFileName,
                        v12);
                    goto LABEL_48;
                  }
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    312,
                    &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                    BytesReturned,
                    8);
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v11 = GetLastError();
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  311,
                  (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
                  (_DWORD)lpFileName,
                  v11);
              }
              CloseHandle(FileW);
            }
          }
        }
        v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 32LL))(v20);
        v7 = v9;
        if ( v9 == -2147023728 )
        {
          v7 = 0;
          goto LABEL_48;
        }
        if ( v9 < 0 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v15 = 315;
            goto LABEL_47;
          }
          goto LABEL_48;
        }
        SysFreeString((BSTR)lpFileName);
        ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(&v18);
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 308, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
        v8 = (OLECHAR *)lpFileName;
      }
      v7 = -2147220479;
LABEL_53:
      SysFreeString(v8);
      ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(&v18);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        307,
        &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        (unsigned int)v6);
    }
  }
  else
  {
    v7 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        306,
        &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        "namespaceRecord");
  }
  SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(&v27);
  ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(&v20);
  return v7;
}

```

## disassembly

```asm
0x18001afe4  mov     [rsp-8+arg_0], rbx
0x18001afe9  push    rbp
0x18001afea  push    rsi
0x18001afeb  push    rdi
0x18001afec  push    r12
0x18001afee  push    r13
0x18001aff0  push    r14
0x18001aff2  push    r15
0x18001aff4  lea     rbp, [rsp-27h]
0x18001aff9  sub     rsp, 0B0h
0x18001b000  mov     r13, rcx
0x18001b003  xor     r12d, r12d
0x18001b006  mov     [rbp+57h+var_68], r12
0x18001b00a  lea     rcx, [rbp+57h+var_40]
0x18001b00e  call    ??0?$SmartPtr@VCNamespaceRecord@@@@QEAA@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::SmartPtr<CNamespaceRecord>(CNamespaceRecord *)
0x18001b013  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b01a  lea     ecx, [r12+58h]; unsigned __int64
0x18001b01f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001b024  lea     r15, [r13+18h]
0x18001b028  test    rax, rax
0x18001b02b  jz      short loc_18001B03E
0x18001b02d  lea     r8, [r13+20h]
0x18001b031  mov     rdx, r15
0x18001b034  mov     rcx, rax; this
0x18001b037  call    ??0CNamespaceRecord@@QEAA@AEBV?$CComPtr@UIFhCatalog@@@ATL@@AEAVCCatalogStatistics@@@Z; CNamespaceRecord::CNamespaceRecord(ATL::CComPtr<IFhCatalog> const &,CCatalogStatistics &)
0x18001b03c  jmp     short loc_18001B041
0x18001b03e  mov     rax, r12
0x18001b041  mov     rdx, rax
0x18001b044  lea     rcx, [rbp+57h+var_40]
0x18001b048  call    ??4?$SmartPtr@VCNamespaceRecord@@@@QEAAAEAV0@PEAVCNamespaceRecord@@@Z; SmartPtr<CNamespaceRecord>::operator=(CNamespaceRecord *)
0x18001b04d  mov     rbx, [rbp+57h+var_40]
0x18001b051  test    rbx, rbx
0x18001b054  jz      loc_18001B470
0x18001b05a  cmp     [rbx], r12
0x18001b05d  jz      loc_18001B470
0x18001b063  mov     rcx, [r15]
0x18001b066  mov     rax, [rcx]
0x18001b069  mov     edx, 5
0x18001b06e  lea     r9, [rbp+57h+var_68]
0x18001b072  xor     r8d, r8d
0x18001b075  mov     rax, [rax+128h]
0x18001b07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b081  mov     edi, eax
0x18001b083  cmp     eax, 80070490h
0x18001b088  jnz     short loc_18001B092
0x18001b08a  mov     edi, r12d
0x18001b08d  jmp     loc_18001B4AA
0x18001b092  test    eax, eax
0x18001b094  jns     short loc_18001B0D4
0x18001b096  lea     rsi, WPP_GLOBAL_Control
0x18001b09d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0a4  cmp     rcx, rsi
0x18001b0a7  jz      loc_18001B4AA
0x18001b0ad  test    byte ptr [rcx+1Ch], 1
0x18001b0b1  jz      loc_18001B4AA
0x18001b0b7  mov     edx, 133h
0x18001b0bc  mov     r9d, eax
0x18001b0bf  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001b0c6  mov     rcx, [rcx+10h]
0x18001b0ca  call    WPP_SF_d
0x18001b0cf  jmp     loc_18001B4AA
0x18001b0d4  lea     rsi, WPP_GLOBAL_Control
0x18001b0db  lea     r14, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001b0e2  mov     [rbp+57h+var_78], r12
0x18001b0e6  mov     rcx, r12
0x18001b0e9  mov     [rbp+57h+lpFileName], rcx
0x18001b0ed  mov     [rbp+57h+arg_18], r12d
0x18001b0f1  mov     [rbp+57h+var_50], r12d
0x18001b0f5  mov     [rbp+57h+var_54], r12d
0x18001b0f9  mov     [rbp+57h+arg_10], r12w
0x18001b0fe  mov     [rbp+57h+arg_8], r12w
0x18001b103  mov     [rbp+57h+var_38], r12
0x18001b107  mov     [rbp+57h+var_58], r12d
0x18001b10b  mov     [rbp+57h+var_5C], r12d
0x18001b10f  mov     [rbp+57h+var_60], r12d
0x18001b113  cmp     [r13+0A0h], r12d
0x18001b11a  jnz     loc_18001B433
0x18001b120  mov     rcx, [rbp+57h+var_68]
0x18001b124  mov     rax, [rcx]
0x18001b127  lea     rdx, [rbp+57h+var_60]
0x18001b12b  mov     [rsp+0E0h+var_90], rdx
0x18001b130  lea     rdx, [rbp+57h+var_5C]
0x18001b134  mov     [rsp+0E0h+var_98], rdx
0x18001b139  lea     rdx, [rbp+57h+var_58]
0x18001b13d  mov     [rsp+0E0h+var_A0], rdx
0x18001b142  lea     rdx, [rbp+57h+var_38]
0x18001b146  mov     [rsp+0E0h+lpOverlapped], rdx
0x18001b14b  lea     rdx, [rbp+57h+arg_8]
0x18001b14f  mov     [rsp+0E0h+hTemplateFile], rdx
0x18001b154  lea     rdx, [rbp+57h+arg_10]
0x18001b158  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rdx
0x18001b15d  lea     rdx, [rbp+57h+var_54]
0x18001b161  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rdx
0x18001b166  lea     r9, [rbp+57h+var_50]
0x18001b16a  lea     r8, [rbp+57h+lpFileName]
0x18001b16e  lea     rdx, [rbp+57h+arg_18]
0x18001b172  mov     rax, [rax+30h]
0x18001b176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b17b  mov     edi, eax
0x18001b17d  test    eax, eax
0x18001b17f  js      loc_18001B407
0x18001b185  mov     rcx, [r15]
0x18001b188  mov     rax, [rcx]
0x18001b18b  lea     r8, [rbp+57h+var_78]
0x18001b18f  mov     edx, [rbp+57h+arg_18]
0x18001b192  mov     rax, [rax+0F0h]
0x18001b199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b19e  test    eax, eax
0x18001b1a0  js      loc_18001B306
0x18001b1a6  lea     rdx, [rbp+57h+var_78]
0x18001b1aa  mov     rcx, [rbx]
0x18001b1ad  call    ?LoadCurrentFromEnum@CNamespaceRecord@@QEAAJAEBV?$CComPtr@UIFhNamespaceRecordEnum@@@ATL@@@Z; CNamespaceRecord::LoadCurrentFromEnum(ATL::CComPtr<IFhNamespaceRecordEnum> const &)
0x18001b1b2  mov     edi, eax
0x18001b1b4  test    eax, eax
0x18001b1b6  js      loc_18001B3D0
0x18001b1bc  mov     rcx, [rbp+57h+var_78]
0x18001b1c0  mov     rax, [rcx]
0x18001b1c3  mov     rax, [rax+20h]
0x18001b1c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1cc  cmp     eax, 80070490h
0x18001b1d1  jnz     loc_18001B306
0x18001b1d7  mov     [rsp+0E0h+hTemplateFile], r12; hTemplateFile
0x18001b1dc  mov     [rsp+0E0h+dwFlagsAndAttributes], 200080h; dwFlagsAndAttributes
0x18001b1e4  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x18001b1ec  xor     r9d, r9d; lpSecurityAttributes
0x18001b1ef  xor     edx, edx; dwDesiredAccess
0x18001b1f1  lea     r8d, [r9+7]; dwShareMode
0x18001b1f5  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18001b1f9  call    cs:__imp_CreateFileW
0x18001b1ff  mov     r12, rax
0x18001b202  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b206  jz      loc_18001B343
0x18001b20c  xor     edi, edi
0x18001b20e  mov     [rbp+57h+OutBuffer], rdi
0x18001b212  mov     [rbp+57h+BytesReturned], edi
0x18001b215  mov     [rsp+0E0h+lpOverlapped], rdi; lpOverlapped
0x18001b21a  lea     rax, [rbp+57h+BytesReturned]
0x18001b21e  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x18001b223  mov     [rsp+0E0h+dwFlagsAndAttributes], 8; nOutBufferSize
0x18001b22b  lea     rax, [rbp+57h+OutBuffer]
0x18001b22f  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; lpOutBuffer
0x18001b234  xor     r9d, r9d; nInBufferSize
0x18001b237  xor     r8d, r8d; lpInBuffer
0x18001b23a  mov     edx, 900EFh; dwIoControlCode
0x18001b23f  mov     rcx, r12; hDevice
0x18001b242  call    cs:__imp_DeviceIoControl
0x18001b248  test    eax, eax
0x18001b24a  jnz     short loc_18001B29A
0x18001b24c  mov     rax, cs:WPP_GLOBAL_Control
0x18001b253  cmp     rax, rsi
0x18001b256  jz      loc_18001B2FA
0x18001b25c  test    byte ptr [rax+1Ch], 2
0x18001b260  jz      loc_18001B2FA
0x18001b266  call    cs:__imp_GetLastError
0x18001b26c  test    eax, eax
0x18001b26e  jle     short loc_18001B278
0x18001b270  movzx   eax, ax
0x18001b273  or      eax, 80070000h
0x18001b278  mov     edx, 137h
0x18001b27d  mov     [rsp+0E0h+dwCreationDisposition], eax
0x18001b281  mov     r9, [rbp+57h+lpFileName]
0x18001b285  mov     r8, r14
0x18001b288  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b28f  mov     rcx, [rcx+10h]
0x18001b293  call    WPP_SF_Sd
0x18001b298  jmp     short loc_18001B2FA
0x18001b29a  mov     r9d, [rbp+57h+BytesReturned]
0x18001b29e  cmp     r9d, 8
0x18001b2a2  jz      short loc_18001B2D1
0x18001b2a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2ab  cmp     rcx, rsi
0x18001b2ae  jz      short loc_18001B2FA
0x18001b2b0  test    byte ptr [rcx+1Ch], 2
0x18001b2b4  jz      short loc_18001B2FA
0x18001b2b6  mov     edx, 138h
0x18001b2bb  mov     [rsp+0E0h+dwCreationDisposition], 8
0x18001b2c3  mov     r8, r14
0x18001b2c6  mov     rcx, [rcx+10h]
0x18001b2ca  call    WPP_SF_dd
0x18001b2cf  jmp     short loc_18001B2FA
0x18001b2d1  mov     rcx, [rbp+57h+OutBuffer]
0x18001b2d5  sar     rcx, 20h
0x18001b2d9  mov     rax, [rbx]
0x18001b2dc  mov     [rax+48h], ecx
0x18001b2df  mov     rcx, [rbx]
0x18001b2e2  mov     eax, dword ptr [rbp+57h+OutBuffer]
0x18001b2e5  mov     [rcx+44h], eax
0x18001b2e8  mov     rcx, [rbx]; this
0x18001b2eb  call    ?Commit@CNamespaceRecord@@QEAAJXZ; CNamespaceRecord::Commit(void)
0x18001b2f0  mov     edi, eax
0x18001b2f2  test    eax, eax
0x18001b2f4  js      loc_18001B38F
0x18001b2fa  mov     rcx, r12; hObject
0x18001b2fd  call    cs:__imp_CloseHandle
0x18001b303  xor     r12d, r12d
0x18001b306  mov     rcx, [rbp+57h+var_68]
0x18001b30a  mov     rax, [rcx]
0x18001b30d  mov     rax, [rax+20h]
0x18001b311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b316  mov     edi, eax
0x18001b318  cmp     eax, 80070490h
0x18001b31d  jz      loc_18001B402
0x18001b323  test    eax, eax
0x18001b325  js      loc_18001B3E9
0x18001b32b  mov     rcx, [rbp+57h+lpFileName]; bstrString
0x18001b32f  call    cs:__imp_SysFreeString
0x18001b335  lea     rcx, [rbp+57h+var_78]
0x18001b339  call    ??1?$CComPtrBase@UIFhScopeIterator@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(void)
0x18001b33e  jmp     loc_18001B0E2
0x18001b343  mov     rax, cs:WPP_GLOBAL_Control
0x18001b34a  cmp     rax, rsi
0x18001b34d  jz      short loc_18001B303
0x18001b34f  test    byte ptr [rax+1Ch], 2
0x18001b353  jz      short loc_18001B303
0x18001b355  call    cs:__imp_GetLastError
0x18001b35b  xor     r12d, r12d
0x18001b35e  test    eax, eax
0x18001b360  jle     short loc_18001B36A
0x18001b362  movzx   eax, ax
0x18001b365  or      eax, 80070000h
0x18001b36a  mov     edx, 13Ah
0x18001b36f  mov     [rsp+0E0h+dwCreationDisposition], eax
0x18001b373  mov     r9, [rbp+57h+lpFileName]
0x18001b377  mov     r8, r14
0x18001b37a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b381  mov     rcx, [rcx+10h]
0x18001b385  call    WPP_SF_Sd
0x18001b38a  jmp     loc_18001B306
0x18001b38f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b396  cmp     rcx, rsi
0x18001b399  jz      loc_18001B42D
0x18001b39f  test    byte ptr [rcx+1Ch], 1
0x18001b3a3  jz      loc_18001B42D
0x18001b3a9  mov     r9, [rbx]
0x18001b3ac  mov     edx, 139h
0x18001b3b1  mov     [rsp+0E0h+dwFlagsAndAttributes], eax
0x18001b3b5  mov     rax, [rbp+57h+lpFileName]
0x18001b3b9  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax
0x18001b3be  mov     r9d, [r9+10h]
0x18001b3c2  mov     r8, r14
0x18001b3c5  mov     rcx, [rcx+10h]
0x18001b3c9  call    WPP_SF_dSd
0x18001b3ce  jmp     short loc_18001B42D
0x18001b3d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3d7  cmp     rcx, rsi
0x18001b3da  jz      short loc_18001B42D
0x18001b3dc  test    byte ptr [rcx+1Ch], 1
0x18001b3e0  jz      short loc_18001B42D
0x18001b3e2  mov     edx, 136h
0x18001b3e7  jmp     short loc_18001B41E
0x18001b3e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3f0  cmp     rcx, rsi
0x18001b3f3  jz      short loc_18001B42D
0x18001b3f5  test    byte ptr [rcx+1Ch], 1
0x18001b3f9  jz      short loc_18001B42D
0x18001b3fb  mov     edx, 13Bh
0x18001b400  jmp     short loc_18001B41E
0x18001b402  mov     edi, r12d
0x18001b405  jmp     short loc_18001B42D
0x18001b407  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b40e  cmp     rcx, rsi
0x18001b411  jz      short loc_18001B42D
0x18001b413  test    byte ptr [rcx+1Ch], 1
0x18001b417  jz      short loc_18001B42D
0x18001b419  mov     edx, 135h
0x18001b41e  mov     r9d, eax
0x18001b421  mov     r8, r14
0x18001b424  mov     rcx, [rcx+10h]
0x18001b428  call    WPP_SF_d
0x18001b42d  mov     rcx, [rbp+57h+lpFileName]
0x18001b431  jmp     short loc_18001B45F
0x18001b433  mov     rax, cs:WPP_GLOBAL_Control
0x18001b43a  cmp     rax, rsi
0x18001b43d  jz      short loc_18001B45A
0x18001b43f  test    byte ptr [rax+1Ch], 8
0x18001b443  jz      short loc_18001B45A
0x18001b445  mov     edx, 134h
0x18001b44a  mov     r8, r14
0x18001b44d  mov     rcx, [rax+10h]
0x18001b451  call    WPP_SF_
0x18001b456  mov     rcx, [rbp+57h+lpFileName]; bstrString
0x18001b45a  mov     edi, 80040401h
0x18001b45f  call    cs:__imp_SysFreeString
0x18001b465  lea     rcx, [rbp+57h+var_78]
0x18001b469  call    ??1?$CComPtrBase@UIFhScopeIterator@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(void)
0x18001b46e  jmp     short loc_18001B4AA
0x18001b470  mov     edi, 8007000Eh
0x18001b475  lea     rsi, WPP_GLOBAL_Control
0x18001b47c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b483  cmp     rcx, rsi
0x18001b486  jz      short loc_18001B4AA
0x18001b488  test    byte ptr [rcx+1Ch], 1
0x18001b48c  jz      short loc_18001B4AA
0x18001b48e  mov     edx, 132h
0x18001b493  lea     r9, aNamespacerecor; "namespaceRecord"
0x18001b49a  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001b4a1  mov     rcx, [rcx+10h]
0x18001b4a5  call    WPP_SF_s
0x18001b4aa  lea     rcx, [rbp+57h+var_40]
0x18001b4ae  call    ??1?$SmartPtr@VCNamespaceRecord@@@@QEAA@XZ; SmartPtr<CNamespaceRecord>::~SmartPtr<CNamespaceRecord>(void)
  ... truncated ...
```
