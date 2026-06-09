# StorageInfo::GetSystemVolumeTotalCapacity(void)

- ea: `0x1800861c0`
- end: `0x1800863fb`
- name: `?GetSystemVolumeTotalCapacity@StorageInfo@@QEBA_JXZ`
- size: `571`
- prototype: `__int64 __fastcall(StorageInfo *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180008dc0`
- `0x1800157b8`
- `0x180016748`
- `0x18001dad0`
- `0x18001dcc8`
- `0x18001e3e4`
- `0x180084978`
- `0x1800861c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800863e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800863e0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008630d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008630d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18008636e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18008636e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008621d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008621d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StorageInfo::GetSystemVolumeTotalCapacity(StorageInfo *this)
{
  WCHAR *v1; // rcx
  __int64 v2; // r8
  LPWSTR *v3; // rcx
  __int16 v4; // bx
  __int64 v5; // rdx
  LPWSTR *v6; // rcx
  __int64 v7; // rdx
  LPWSTR *v8; // rcx
  const WCHAR *v9; // rcx
  HANDLE FileW; // rax
  __int64 v11; // rbx
  signed int LastError; // eax
  int v14; // edx
  unsigned int v15; // r8d
  __int64 OutBuffer; // [rsp+40h] [rbp-19h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-11h] BYREF
  void **v18; // [rsp+50h] [rbp-9h] BYREF
  __int64 v19; // [rsp+58h] [rbp-1h]
  LPWSTR lpBuffer[2]; // [rsp+60h] [rbp+7h] BYREF
  UINT uSize[2]; // [rsp+70h] [rbp+17h]
  unsigned __int64 v22; // [rsp+78h] [rbp+1Fh]

  *(_OWORD *)lpBuffer = 0;
  *(_QWORD *)uSize = 0;
  v22 = 7;
  LOWORD(lpBuffer[0]) = 0;
  std::wstring::resize(lpBuffer);
  v1 = (WCHAR *)lpBuffer;
  if ( v22 > 7 )
    v1 = lpBuffer[0];
  if ( !GetSystemDirectoryW(v1, uSize[0]) )
    goto LABEL_28;
  if ( v22 > 7 )
  {
    v3 = (LPWSTR *)lpBuffer[0];
    v4 = *lpBuffer[0];
LABEL_7:
    *(_QWORD *)uSize = 4;
    *v3 = (LPWSTR)0x5C002E005C005CLL;
    *((_WORD *)v3 + 4) = 0;
    goto LABEL_9;
  }
  v4 = (__int16)lpBuffer[0];
  v3 = lpBuffer;
  if ( v22 >= 4 )
    goto LABEL_7;
  std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
    (char **)lpBuffer,
    4u,
    v2,
    L"\\\\.\\");
LABEL_9:
  v5 = *(_QWORD *)uSize;
  v6 = lpBuffer;
  if ( *(_QWORD *)uSize >= v22 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(lpBuffer);
  }
  else
  {
    ++*(_QWORD *)uSize;
    if ( v22 > 7 )
      v6 = (LPWSTR *)lpBuffer[0];
    *((_WORD *)v6 + v5) = v4;
    *((_WORD *)v6 + v5 + 1) = 0;
  }
  v7 = *(_QWORD *)uSize;
  v8 = lpBuffer;
  if ( *(_QWORD *)uSize >= v22 )
  {
    std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(lpBuffer);
  }
  else
  {
    ++*(_QWORD *)uSize;
    if ( v22 > 7 )
      v8 = (LPWSTR *)lpBuffer[0];
    *(_DWORD *)((char *)v8 + 2 * v7) = 58;
  }
  v9 = (const WCHAR *)lpBuffer;
  if ( v22 > 7 )
    v9 = lpBuffer[0];
  FileW = CreateFileW(v9, 0x80000000, 3u, 0, 3u, 0, 0);
  v18 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
  v19 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
LABEL_28:
    std::wstring::~wstring((char **)lpBuffer);
    return -1;
  }
  v11 = -1;
  OutBuffer = 0;
  BytesReturned = 0;
  if ( DeviceIoControl(FileW, 0x7405Cu, 0, 0, &OutBuffer, 8u, &BytesReturned, 0) )
  {
    v11 = OutBuffer / 0x100000;
    OutBuffer /= 0x100000;
  }
  v18 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
  if ( v19 != -1 )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::InternalClose(&v18) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v14, v15);
      JUMPOUT(0x1800863FALL);
    }
    v19 = -1;
  }
  std::wstring::~wstring((char **)lpBuffer);
  return v11;
}

```

## disassembly

```asm
0x1800861c0  push    rbp
0x1800861c2  push    rbx
0x1800861c3  push    rsi
0x1800861c4  push    r14
0x1800861c6  lea     rbp, [rsp-3Fh]
0x1800861cb  sub     rsp, 98h
0x1800861d2  mov     rax, cs:__security_cookie
0x1800861d9  xor     rax, rsp
0x1800861dc  mov     [rbp+57h+var_30], rax
0x1800861e0  xorps   xmm0, xmm0
0x1800861e3  movups  xmmword ptr [rbp+57h+lpBuffer], xmm0
0x1800861e7  mov     qword ptr [rbp+57h+uSize], 0
0x1800861ef  mov     r14d, 7
0x1800861f5  mov     [rbp+57h+var_38], r14
0x1800861f9  xor     eax, eax
0x1800861fb  mov     word ptr [rbp+57h+lpBuffer], ax
0x1800861ff  mov     edx, 104h
0x180086204  lea     rcx, [rbp+57h+lpBuffer]; Src
0x180086208  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18008620d  lea     rcx, [rbp+57h+lpBuffer]
0x180086211  cmp     [rbp+57h+var_38], r14
0x180086215  cmova   rcx, [rbp+57h+lpBuffer]; lpBuffer
0x18008621a  mov     edx, [rbp+57h+uSize]; uSize
0x18008621d  call    cs:__imp_GetSystemDirectoryW
0x180086223  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180086227  test    eax, eax
0x180086229  jz      loc_1800863BB
0x18008622f  lea     edx, [rsi+5]
0x180086232  cmp     [rbp+57h+var_38], r14
0x180086236  jbe     short loc_180086241
0x180086238  mov     rcx, [rbp+57h+lpBuffer]
0x18008623c  movzx   ebx, word ptr [rcx]
0x18008623f  jmp     short loc_18008624F
0x180086241  movzx   ebx, word ptr [rbp+57h+lpBuffer]
0x180086245  lea     rcx, [rbp+57h+lpBuffer]
0x180086249  cmp     [rbp+57h+var_38], rdx
0x18008624d  jb      short loc_180086268
0x18008624f  mov     qword ptr [rbp+57h+uSize], rdx
0x180086253  mov     rax, 5C002E005C005Ch
0x18008625d  mov     [rcx], rax
0x180086260  xor     eax, eax
0x180086262  mov     [rcx+8], ax
0x180086266  jmp     short loc_180086274
0x180086268  lea     r9, asc_1801BE8A0; "\\\\.\\"
0x18008626f  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180086274  mov     rdx, qword ptr [rbp+57h+uSize]
0x180086278  lea     rcx, [rbp+57h+lpBuffer]; Src
0x18008627c  cmp     rdx, [rbp+57h+var_38]
0x180086280  jnb     short loc_1800862A0
0x180086282  lea     rax, [rdx+1]
0x180086286  mov     qword ptr [rbp+57h+uSize], rax
0x18008628a  cmp     [rbp+57h+var_38], r14
0x18008628e  cmova   rcx, [rbp+57h+lpBuffer]
0x180086293  mov     [rcx+rdx*2], bx
0x180086297  xor     eax, eax
0x180086299  mov     [rcx+rdx*2+2], ax
0x18008629e  jmp     short loc_1800862A9
0x1800862a0  movzx   r9d, bx
0x1800862a4  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x1800862a9  mov     rdx, qword ptr [rbp+57h+uSize]
0x1800862ad  lea     rcx, [rbp+57h+lpBuffer]; Src
0x1800862b1  cmp     rdx, [rbp+57h+var_38]
0x1800862b5  jnb     short loc_1800862D1
0x1800862b7  lea     rax, [rdx+1]
0x1800862bb  mov     qword ptr [rbp+57h+uSize], rax
0x1800862bf  cmp     [rbp+57h+var_38], r14
0x1800862c3  cmova   rcx, [rbp+57h+lpBuffer]
0x1800862c8  mov     dword ptr [rcx+rdx*2], 3Ah ; ':'
0x1800862cf  jmp     short loc_1800862DC
0x1800862d1  mov     r9d, 3Ah ; ':'
0x1800862d7  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x1800862dc  lea     rcx, [rbp+57h+lpBuffer]
0x1800862e0  cmp     [rbp+57h+var_38], r14
0x1800862e4  cmova   rcx, [rbp+57h+lpBuffer]; lpFileName
0x1800862e9  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x1800862f2  mov     [rsp+0B0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800862fa  mov     r8d, 3; dwShareMode
0x180086300  mov     [rsp+0B0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180086305  xor     r9d, r9d; lpSecurityAttributes
0x180086308  mov     edx, 80000000h; dwDesiredAccess
0x18008630d  call    cs:__imp_CreateFileW
0x180086313  lea     r14, ??_7?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable'
0x18008631a  mov     [rbp+57h+var_60], r14
0x18008631e  mov     [rbp+57h+var_58], rax
0x180086322  cmp     rax, rsi
0x180086325  jz      loc_1800863BB
0x18008632b  mov     rbx, rsi
0x18008632e  mov     [rbp+57h+OutBuffer], 0
0x180086336  mov     [rbp+57h+BytesReturned], 0
0x18008633d  mov     [rsp+0B0h+lpOverlapped], 0; lpOverlapped
0x180086346  lea     rcx, [rbp+57h+BytesReturned]
0x18008634a  mov     [rsp+0B0h+hTemplateFile], rcx; lpBytesReturned
0x18008634f  mov     [rsp+0B0h+dwFlagsAndAttributes], 8; nOutBufferSize
0x180086357  lea     rcx, [rbp+57h+OutBuffer]
0x18008635b  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rcx; lpOutBuffer
0x180086360  xor     r9d, r9d; nInBufferSize
0x180086363  xor     r8d, r8d; lpInBuffer
0x180086366  mov     edx, 7405Ch; dwIoControlCode
0x18008636b  mov     rcx, rax; hDevice
0x18008636e  call    cs:__imp_DeviceIoControl
0x180086374  test    eax, eax
0x180086376  jz      short loc_180086392
0x180086378  mov     rax, [rbp+57h+OutBuffer]
0x18008637c  cqo
0x18008637e  and     edx, 0FFFFFh
0x180086384  add     rax, rdx
0x180086387  sar     rax, 14h
0x18008638b  mov     rbx, rax
0x18008638e  mov     [rbp+57h+OutBuffer], rax
0x180086392  mov     [rbp+57h+var_60], r14
0x180086396  cmp     [rbp+57h+var_58], rsi
0x18008639a  jz      short loc_1800863AD
0x18008639c  lea     rcx, [rbp+57h+var_60]
0x1800863a0  call    ?InternalClose@?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::InternalClose(void)
0x1800863a5  test    al, al
0x1800863a7  jz      short loc_1800863E0
0x1800863a9  mov     [rbp+57h+var_58], rsi
0x1800863ad  lea     rcx, [rbp+57h+lpBuffer]
0x1800863b1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800863b6  mov     rax, rbx
0x1800863b9  jmp     short loc_1800863C7
0x1800863bb  lea     rcx, [rbp+57h+lpBuffer]
0x1800863bf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800863c4  mov     rax, rsi
0x1800863c7  mov     rcx, [rbp+57h+var_30]
0x1800863cb  xor     rcx, rsp; StackCookie
0x1800863ce  call    __security_check_cookie
0x1800863d3  add     rsp, 98h
0x1800863da  pop     r14
0x1800863dc  pop     rsi
0x1800863dd  pop     rbx
0x1800863de  pop     rbp
0x1800863df  retn
0x1800863e0  call    cs:__imp_GetLastError
0x1800863e6  nop
0x1800863e7  test    eax, eax
0x1800863e9  jle     short loc_1800863F3
0x1800863eb  movzx   eax, ax
0x1800863ee  or      eax, 80070000h
0x1800863f3  mov     ecx, eax; this
0x1800863f5  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
