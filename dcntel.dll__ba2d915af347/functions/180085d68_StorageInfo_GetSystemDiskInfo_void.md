# StorageInfo::GetSystemDiskInfo(void)

- ea: `0x180085d68`
- end: `0x18008604f`
- name: `?GetSystemDiskInfo@StorageInfo@@CAAEAU_SYSTEM_DISK_INFO_2@@XZ`
- size: `743`
- prototype: `struct _SYSTEM_DISK_INFO_2 *(void)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180085d30`
- `0x180085d50`

## callees

- `0x180008dc0`
- `0x1800157b8`
- `0x180016748`
- `0x18001dad0`
- `0x18001dcc8`
- `0x18001e3e4`
- `0x180084978`
- `0x180085d68`
- `0x180086058`
- `0x1800cd1fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086034`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086034`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180085ed1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180085ed1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180085f67`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180085fce`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180085f67`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180085fce`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180085ddd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180085ddd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct _SYSTEM_DISK_INFO_2 *StorageInfo::GetSystemDiskInfo(void)
{
  WCHAR *v0; // rcx
  __int64 v1; // r8
  LPWSTR *v2; // rcx
  __int16 v3; // bx
  __int64 v4; // rdx
  LPWSTR *v5; // rcx
  __int64 v6; // rdx
  LPWSTR *v7; // rcx
  const WCHAR *v8; // rcx
  __int64 SystemDiskSizeMB_WindowsCore; // rax
  signed int LastError; // eax
  int v12; // edx
  unsigned int v13; // r8d
  DWORD BytesReturned; // [rsp+40h] [rbp-39h] BYREF
  void **v15; // [rsp+48h] [rbp-31h] BYREF
  HANDLE hDevice; // [rsp+50h] [rbp-29h]
  LPWSTR lpBuffer[2]; // [rsp+58h] [rbp-21h] BYREF
  UINT uSize[2]; // [rsp+68h] [rbp-11h]
  unsigned __int64 v19; // [rsp+70h] [rbp-9h]
  int InBuffer; // [rsp+78h] [rbp-1h] BYREF
  __int64 v21; // [rsp+7Ch] [rbp+3h]
  __int64 v22; // [rsp+88h] [rbp+Fh] BYREF
  int v23; // [rsp+90h] [rbp+17h]
  int OutBuffer; // [rsp+98h] [rbp+1Fh] BYREF
  __int128 v25; // [rsp+9Ch] [rbp+23h]
  __int128 v26; // [rsp+ACh] [rbp+33h]
  int v27; // [rsp+BCh] [rbp+43h]

  if ( !byte_1801FF890 )
  {
    byte_1801FF890 = 1;
    *(_OWORD *)lpBuffer = 0;
    *(_QWORD *)uSize = 0;
    v19 = 7;
    LOWORD(lpBuffer[0]) = 0;
    std::wstring::resize(lpBuffer);
    v0 = (WCHAR *)lpBuffer;
    if ( v19 > 7 )
      v0 = lpBuffer[0];
    if ( !GetSystemDirectoryW(v0, uSize[0]) )
      goto LABEL_35;
    if ( v19 <= 7 )
    {
      v3 = (__int16)lpBuffer[0];
      v2 = lpBuffer;
      if ( v19 < 4 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          (char **)lpBuffer,
          4u,
          v1,
          L"\\\\.\\");
        goto LABEL_10;
      }
    }
    else
    {
      v2 = (LPWSTR *)lpBuffer[0];
      v3 = *lpBuffer[0];
    }
    *(_QWORD *)uSize = 4;
    *v2 = (LPWSTR)0x5C002E005C005CLL;
    *((_WORD *)v2 + 4) = 0;
LABEL_10:
    v4 = *(_QWORD *)uSize;
    v5 = lpBuffer;
    if ( *(_QWORD *)uSize >= v19 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(lpBuffer);
    }
    else
    {
      ++*(_QWORD *)uSize;
      if ( v19 > 7 )
        v5 = (LPWSTR *)lpBuffer[0];
      *((_WORD *)v5 + v4) = v3;
      *((_WORD *)v5 + v4 + 1) = 0;
    }
    v6 = *(_QWORD *)uSize;
    v7 = lpBuffer;
    if ( *(_QWORD *)uSize >= v19 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(lpBuffer);
    }
    else
    {
      ++*(_QWORD *)uSize;
      if ( v19 > 7 )
        v7 = (LPWSTR *)lpBuffer[0];
      *(_DWORD *)((char *)v7 + 2 * v6) = 58;
    }
    v8 = (const WCHAR *)lpBuffer;
    if ( v19 > 7 )
      v8 = lpBuffer[0];
    v15 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
    hDevice = CreateFileW(v8, 0, 3u, 0, 3u, 0, 0);
    if ( hDevice == (HANDLE)-1LL )
    {
      v15 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
    }
    else
    {
      BytesReturned = 0;
      if ( SystemRequirements::IsWindowsCore() )
      {
        SystemDiskSizeMB_WindowsCore = CStorageInfo::GetSystemDiskSizeMB_WindowsCore();
        qword_1801FE898 = SystemDiskSizeMB_WindowsCore;
      }
      else
      {
        SystemDiskSizeMB_WindowsCore = qword_1801FE898;
      }
      if ( SystemDiskSizeMB_WindowsCore == -1 )
      {
        OutBuffer = 0;
        v25 = 0;
        v26 = 0;
        v27 = 0;
        if ( DeviceIoControl(hDevice, 0x700A0u, 0, 0, &OutBuffer, 0x28u, &BytesReturned, 0) )
          qword_1801FE898 = *(_QWORD *)((char *)&v26 + 4) / 0x100000LL;
      }
      v22 = 0;
      v23 = 0;
      v21 = 0;
      InBuffer = 7;
      if ( DeviceIoControl(hDevice, 0x2D1400u, &InBuffer, 0xCu, &v22, 0xCu, &BytesReturned, 0) )
        dword_1801FE8A0 = 4 - ((_BYTE)v23 != 0);
      v15 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
      if ( hDevice != (HANDLE)-1LL )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::InternalClose(&v15) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v12, v13);
          JUMPOUT(0x18008604ELL);
        }
        hDevice = (HANDLE)-1LL;
      }
    }
LABEL_35:
    std::wstring::~wstring((char **)lpBuffer);
  }
  return (struct _SYSTEM_DISK_INFO_2 *)&qword_1801FE898;
}

```

## disassembly

```asm
0x180085d68  mov     [rsp-8+arg_0], rbx
0x180085d6d  mov     [rsp-8+arg_8], r15
0x180085d72  push    rbp
0x180085d73  lea     rbp, [rsp-57h]
0x180085d78  sub     rsp, 0D0h
0x180085d7f  mov     rax, cs:__security_cookie
0x180085d86  xor     rax, rsp
0x180085d89  mov     [rbp+57h+var_10], rax
0x180085d8d  cmp     cs:byte_1801FF890, 0
0x180085d94  jnz     loc_18008600C
0x180085d9a  mov     cs:byte_1801FF890, 1
0x180085da1  xorps   xmm0, xmm0
0x180085da4  movups  xmmword ptr [rbp+57h+lpBuffer], xmm0
0x180085da8  mov     qword ptr [rbp+57h+uSize], 0
0x180085db0  mov     [rbp+57h+var_60], 7
0x180085db8  xor     eax, eax
0x180085dba  mov     word ptr [rbp+57h+lpBuffer], ax
0x180085dbe  mov     edx, 104h
0x180085dc3  lea     rcx, [rbp+57h+lpBuffer]; Src
0x180085dc7  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180085dcc  lea     rcx, [rbp+57h+lpBuffer]
0x180085dd0  cmp     [rbp+57h+var_60], 7
0x180085dd5  cmova   rcx, [rbp+57h+lpBuffer]; lpBuffer
0x180085dda  mov     edx, [rbp+57h+uSize]; uSize
0x180085ddd  call    cs:__imp_GetSystemDirectoryW
0x180085de3  test    eax, eax
0x180085de5  jz      loc_180086003
0x180085deb  cmp     [rbp+57h+var_60], 7
0x180085df0  jbe     short loc_180085DFB
0x180085df2  mov     rcx, [rbp+57h+lpBuffer]
0x180085df6  movzx   ebx, word ptr [rcx]
0x180085df9  jmp     short loc_180085E0A
0x180085dfb  movzx   ebx, word ptr [rbp+57h+lpBuffer]
0x180085dff  lea     rcx, [rbp+57h+lpBuffer]
0x180085e03  cmp     [rbp+57h+var_60], 4
0x180085e08  jb      short loc_180085E27
0x180085e0a  mov     qword ptr [rbp+57h+uSize], 4
0x180085e12  mov     rax, 5C002E005C005Ch
0x180085e1c  mov     [rcx], rax
0x180085e1f  xor     eax, eax
0x180085e21  mov     [rcx+8], ax
0x180085e25  jmp     short loc_180085E38
0x180085e27  lea     r9, asc_1801BE8A0; "\\\\.\\"
0x180085e2e  mov     edx, 4
0x180085e33  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180085e38  mov     rdx, qword ptr [rbp+57h+uSize]
0x180085e3c  lea     rcx, [rbp+57h+lpBuffer]; Src
0x180085e40  cmp     rdx, [rbp+57h+var_60]
0x180085e44  jnb     short loc_180085E65
0x180085e46  lea     rax, [rdx+1]
0x180085e4a  mov     qword ptr [rbp+57h+uSize], rax
0x180085e4e  cmp     [rbp+57h+var_60], 7
0x180085e53  cmova   rcx, [rbp+57h+lpBuffer]
0x180085e58  mov     [rcx+rdx*2], bx
0x180085e5c  xor     eax, eax
0x180085e5e  mov     [rcx+rdx*2+2], ax
0x180085e63  jmp     short loc_180085E6E
0x180085e65  movzx   r9d, bx
0x180085e69  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180085e6e  mov     rdx, qword ptr [rbp+57h+uSize]
0x180085e72  lea     rcx, [rbp+57h+lpBuffer]; Src
0x180085e76  cmp     rdx, [rbp+57h+var_60]
0x180085e7a  jnb     short loc_180085E97
0x180085e7c  lea     rax, [rdx+1]
0x180085e80  mov     qword ptr [rbp+57h+uSize], rax
0x180085e84  cmp     [rbp+57h+var_60], 7
0x180085e89  cmova   rcx, [rbp+57h+lpBuffer]
0x180085e8e  mov     dword ptr [rcx+rdx*2], 3Ah ; ':'
0x180085e95  jmp     short loc_180085EA2
0x180085e97  mov     r9d, 3Ah ; ':'
0x180085e9d  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180085ea2  lea     rcx, [rbp+57h+lpBuffer]
0x180085ea6  cmp     [rbp+57h+var_60], 7
0x180085eab  cmova   rcx, [rbp+57h+lpBuffer]; lpFileName
0x180085eb0  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x180085eb9  mov     [rsp+0D0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180085ec1  mov     r8d, 3; dwShareMode
0x180085ec7  mov     [rsp+0D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180085ecc  xor     r9d, r9d; lpSecurityAttributes
0x180085ecf  xor     edx, edx; dwDesiredAccess
0x180085ed1  call    cs:__imp_CreateFileW
0x180085ed7  lea     r15, ??_7?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable'
0x180085ede  mov     [rbp+57h+var_88], r15
0x180085ee2  mov     [rbp+57h+hDevice], rax
0x180085ee6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180085eea  cmp     rax, rbx
0x180085eed  jnz     short loc_180085EF8
0x180085eef  mov     [rbp+57h+var_88], r15
0x180085ef3  jmp     loc_180086003
0x180085ef8  mov     [rbp+57h+BytesReturned], 0
0x180085eff  call    ?IsWindowsCore@SystemRequirements@@SA_NXZ; SystemRequirements::IsWindowsCore(void)
0x180085f04  test    al, al
0x180085f06  jz      short loc_180085F16
0x180085f08  call    ?GetSystemDiskSizeMB_WindowsCore@CStorageInfo@@CA_JXZ; CStorageInfo::GetSystemDiskSizeMB_WindowsCore(void)
0x180085f0d  mov     cs:qword_1801FE898, rax
0x180085f14  jmp     short loc_180085F1D
0x180085f16  mov     rax, cs:qword_1801FE898
0x180085f1d  cmp     rax, rbx
0x180085f20  jnz     short loc_180085F8B
0x180085f22  mov     [rbp+57h+OutBuffer], 0
0x180085f29  xorps   xmm0, xmm0
0x180085f2c  xor     eax, eax
0x180085f2e  movups  [rbp+57h+var_34], xmm0
0x180085f32  movups  [rbp+57h+var_24], xmm0
0x180085f36  mov     [rbp+57h+var_14], eax
0x180085f39  mov     [rsp+0D0h+lpOverlapped], rax; lpOverlapped
0x180085f3e  lea     rax, [rbp+57h+BytesReturned]
0x180085f42  mov     [rsp+0D0h+hTemplateFile], rax; lpBytesReturned
0x180085f47  mov     [rsp+0D0h+dwFlagsAndAttributes], 28h ; '('; nOutBufferSize
0x180085f4f  lea     rax, [rbp+57h+OutBuffer]
0x180085f53  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; lpOutBuffer
0x180085f58  xor     r9d, r9d; nInBufferSize
0x180085f5b  xor     r8d, r8d; lpInBuffer
0x180085f5e  mov     edx, 700A0h; dwIoControlCode
0x180085f63  mov     rcx, [rbp+57h+hDevice]; hDevice
0x180085f67  call    cs:__imp_DeviceIoControl
0x180085f6d  test    eax, eax
0x180085f6f  jz      short loc_180085F8B
0x180085f71  mov     rax, qword ptr [rbp+57h+var_24+4]
0x180085f75  cqo
0x180085f77  and     edx, 0FFFFFh
0x180085f7d  add     rax, rdx
0x180085f80  sar     rax, 14h
0x180085f84  mov     cs:qword_1801FE898, rax
0x180085f8b  xor     eax, eax
0x180085f8d  mov     [rbp+57h+var_48], rax
0x180085f91  mov     [rbp+57h+var_40], eax
0x180085f94  mov     [rbp+57h+var_54], rax
0x180085f98  mov     [rbp+57h+InBuffer], 7
0x180085f9f  mov     [rsp+0D0h+lpOverlapped], rax; lpOverlapped
0x180085fa4  lea     rax, [rbp+57h+BytesReturned]
0x180085fa8  mov     [rsp+0D0h+hTemplateFile], rax; lpBytesReturned
0x180085fad  mov     r9d, 0Ch; nInBufferSize
0x180085fb3  mov     [rsp+0D0h+dwFlagsAndAttributes], r9d; nOutBufferSize
0x180085fb8  lea     rax, [rbp+57h+var_48]
0x180085fbc  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; lpOutBuffer
0x180085fc1  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x180085fc5  mov     edx, 2D1400h; dwIoControlCode
0x180085fca  mov     rcx, [rbp+57h+hDevice]; hDevice
0x180085fce  call    cs:__imp_DeviceIoControl
0x180085fd4  test    eax, eax
0x180085fd6  jz      short loc_180085FE8
0x180085fd8  mov     al, byte ptr [rbp+57h+var_40]
0x180085fdb  neg     al
0x180085fdd  sbb     ecx, ecx
0x180085fdf  add     ecx, 4
0x180085fe2  mov     cs:dword_1801FE8A0, ecx
0x180085fe8  mov     [rbp+57h+var_88], r15
0x180085fec  cmp     [rbp+57h+hDevice], rbx
0x180085ff0  jz      short loc_180086003
0x180085ff2  lea     rcx, [rbp+57h+var_88]
0x180085ff6  call    ?InternalClose@?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::InternalClose(void)
0x180085ffb  test    al, al
0x180085ffd  jz      short loc_180086034
0x180085fff  mov     [rbp+57h+hDevice], rbx
0x180086003  lea     rcx, [rbp+57h+lpBuffer]
0x180086007  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008600c  lea     rax, qword_1801FE898
0x180086013  mov     rcx, [rbp+57h+var_10]
0x180086017  xor     rcx, rsp; StackCookie
0x18008601a  call    __security_check_cookie
0x18008601f  lea     r11, [rsp+0D0h+var_s0]
0x180086027  mov     rbx, [r11+10h]
0x18008602b  mov     r15, [r11+18h]
0x18008602f  mov     rsp, r11
0x180086032  pop     rbp
0x180086033  retn
0x180086034  call    cs:__imp_GetLastError
0x18008603a  nop
0x18008603b  test    eax, eax
0x18008603d  jle     short loc_180086047
0x18008603f  movzx   eax, ax
0x180086042  or      eax, 80070000h
0x180086047  mov     ecx, eax; this
0x180086049  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
