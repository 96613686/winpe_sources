# CStorageInfo::GetSystemDiskInfo(void)

- ea: `0x1800cc788`
- end: `0x1800cca6f`
- name: `?GetSystemDiskInfo@CStorageInfo@@CAAEAU_SYSTEM_DISK_INFO@@XZ`
- size: `743`
- prototype: `struct _SYSTEM_DISK_INFO *(void)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800cc750`
- `0x1800cc770`

## callees

- `0x180008dc0`
- `0x1800157b8`
- `0x180016748`
- `0x18001dad0`
- `0x18001dcc8`
- `0x18001e3e4`
- `0x180084978`
- `0x180086058`
- `0x1800cc788`
- `0x1800cd1fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cca54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cca54`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800cc8f1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800cc8f1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800cc987`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800cc9ee`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800cc987`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800cc9ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800cc7fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800cc7fd`

## pseudocode

```c
struct _SYSTEM_DISK_INFO *CStorageInfo::GetSystemDiskInfo(void)
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

  if ( !byte_180200329 )
  {
    byte_180200329 = 1;
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
        qword_1801FE8E0 = SystemDiskSizeMB_WindowsCore;
      }
      else
      {
        SystemDiskSizeMB_WindowsCore = qword_1801FE8E0;
      }
      if ( SystemDiskSizeMB_WindowsCore == -1 )
      {
        OutBuffer = 0;
        v25 = 0;
        v26 = 0;
        v27 = 0;
        if ( DeviceIoControl(hDevice, 0x700A0u, 0, 0, &OutBuffer, 0x28u, &BytesReturned, 0) )
          qword_1801FE8E0 = *(_QWORD *)((char *)&v26 + 4) / 0x100000LL;
      }
      v22 = 0;
      v23 = 0;
      v21 = 0;
      InBuffer = 7;
      if ( DeviceIoControl(hDevice, 0x2D1400u, &InBuffer, 0xCu, &v22, 0xCu, &BytesReturned, 0) )
        dword_1801FE8E8 = 4 - ((_BYTE)v23 != 0);
      v15 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable';
      if ( hDevice != (HANDLE)-1LL )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::InternalClose(&v15) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v12, v13);
          JUMPOUT(0x1800CCA6ELL);
        }
        hDevice = (HANDLE)-1LL;
      }
    }
LABEL_35:
    std::wstring::~wstring((char **)lpBuffer);
  }
  return (struct _SYSTEM_DISK_INFO *)&qword_1801FE8E0;
}

```

## disassembly

```asm
0x1800cc788  mov     [rsp-8+arg_0], rbx
0x1800cc78d  mov     [rsp-8+arg_8], r15
0x1800cc792  push    rbp
0x1800cc793  lea     rbp, [rsp-57h]
0x1800cc798  sub     rsp, 0D0h
0x1800cc79f  mov     rax, cs:__security_cookie
0x1800cc7a6  xor     rax, rsp
0x1800cc7a9  mov     [rbp+57h+var_10], rax
0x1800cc7ad  cmp     cs:byte_180200329, 0
0x1800cc7b4  jnz     loc_1800CCA2C
0x1800cc7ba  mov     cs:byte_180200329, 1
0x1800cc7c1  xorps   xmm0, xmm0
0x1800cc7c4  movups  xmmword ptr [rbp+57h+lpBuffer], xmm0
0x1800cc7c8  mov     qword ptr [rbp+57h+uSize], 0
0x1800cc7d0  mov     [rbp+57h+var_60], 7
0x1800cc7d8  xor     eax, eax
0x1800cc7da  mov     word ptr [rbp+57h+lpBuffer], ax
0x1800cc7de  mov     edx, 104h
0x1800cc7e3  lea     rcx, [rbp+57h+lpBuffer]; Src
0x1800cc7e7  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800cc7ec  lea     rcx, [rbp+57h+lpBuffer]
0x1800cc7f0  cmp     [rbp+57h+var_60], 7
0x1800cc7f5  cmova   rcx, [rbp+57h+lpBuffer]; lpBuffer
0x1800cc7fa  mov     edx, [rbp+57h+uSize]; uSize
0x1800cc7fd  call    cs:__imp_GetSystemDirectoryW
0x1800cc803  test    eax, eax
0x1800cc805  jz      loc_1800CCA23
0x1800cc80b  cmp     [rbp+57h+var_60], 7
0x1800cc810  jbe     short loc_1800CC81B
0x1800cc812  mov     rcx, [rbp+57h+lpBuffer]
0x1800cc816  movzx   ebx, word ptr [rcx]
0x1800cc819  jmp     short loc_1800CC82A
0x1800cc81b  movzx   ebx, word ptr [rbp+57h+lpBuffer]
0x1800cc81f  lea     rcx, [rbp+57h+lpBuffer]
0x1800cc823  cmp     [rbp+57h+var_60], 4
0x1800cc828  jb      short loc_1800CC847
0x1800cc82a  mov     qword ptr [rbp+57h+uSize], 4
0x1800cc832  mov     rax, 5C002E005C005Ch
0x1800cc83c  mov     [rcx], rax
0x1800cc83f  xor     eax, eax
0x1800cc841  mov     [rcx+8], ax
0x1800cc845  jmp     short loc_1800CC858
0x1800cc847  lea     r9, asc_1801BE8A0; "\\\\.\\"
0x1800cc84e  mov     edx, 4
0x1800cc853  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800cc858  mov     rdx, qword ptr [rbp+57h+uSize]
0x1800cc85c  lea     rcx, [rbp+57h+lpBuffer]; Src
0x1800cc860  cmp     rdx, [rbp+57h+var_60]
0x1800cc864  jnb     short loc_1800CC885
0x1800cc866  lea     rax, [rdx+1]
0x1800cc86a  mov     qword ptr [rbp+57h+uSize], rax
0x1800cc86e  cmp     [rbp+57h+var_60], 7
0x1800cc873  cmova   rcx, [rbp+57h+lpBuffer]
0x1800cc878  mov     [rcx+rdx*2], bx
0x1800cc87c  xor     eax, eax
0x1800cc87e  mov     [rcx+rdx*2+2], ax
0x1800cc883  jmp     short loc_1800CC88E
0x1800cc885  movzx   r9d, bx
0x1800cc889  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x1800cc88e  mov     rdx, qword ptr [rbp+57h+uSize]
0x1800cc892  lea     rcx, [rbp+57h+lpBuffer]; Src
0x1800cc896  cmp     rdx, [rbp+57h+var_60]
0x1800cc89a  jnb     short loc_1800CC8B7
0x1800cc89c  lea     rax, [rdx+1]
0x1800cc8a0  mov     qword ptr [rbp+57h+uSize], rax
0x1800cc8a4  cmp     [rbp+57h+var_60], 7
0x1800cc8a9  cmova   rcx, [rbp+57h+lpBuffer]
0x1800cc8ae  mov     dword ptr [rcx+rdx*2], 3Ah ; ':'
0x1800cc8b5  jmp     short loc_1800CC8C2
0x1800cc8b7  mov     r9d, 3Ah ; ':'
0x1800cc8bd  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x1800cc8c2  lea     rcx, [rbp+57h+lpBuffer]
0x1800cc8c6  cmp     [rbp+57h+var_60], 7
0x1800cc8cb  cmova   rcx, [rbp+57h+lpBuffer]; lpFileName
0x1800cc8d0  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x1800cc8d9  mov     [rsp+0D0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800cc8e1  mov     r8d, 3; dwShareMode
0x1800cc8e7  mov     [rsp+0D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800cc8ec  xor     r9d, r9d; lpSecurityAttributes
0x1800cc8ef  xor     edx, edx; dwDesiredAccess
0x1800cc8f1  call    cs:__imp_CreateFileW
0x1800cc8f7  lea     r15, ??_7?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::`vftable'
0x1800cc8fe  mov     [rbp+57h+var_88], r15
0x1800cc902  mov     [rbp+57h+hDevice], rax
0x1800cc906  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800cc90a  cmp     rax, rbx
0x1800cc90d  jnz     short loc_1800CC918
0x1800cc90f  mov     [rbp+57h+var_88], r15
0x1800cc913  jmp     loc_1800CCA23
0x1800cc918  mov     [rbp+57h+BytesReturned], 0
0x1800cc91f  call    ?IsWindowsCore@SystemRequirements@@SA_NXZ; SystemRequirements::IsWindowsCore(void)
0x1800cc924  test    al, al
0x1800cc926  jz      short loc_1800CC936
0x1800cc928  call    ?GetSystemDiskSizeMB_WindowsCore@CStorageInfo@@CA_JXZ; CStorageInfo::GetSystemDiskSizeMB_WindowsCore(void)
0x1800cc92d  mov     cs:qword_1801FE8E0, rax
0x1800cc934  jmp     short loc_1800CC93D
0x1800cc936  mov     rax, cs:qword_1801FE8E0
0x1800cc93d  cmp     rax, rbx
0x1800cc940  jnz     short loc_1800CC9AB
0x1800cc942  mov     [rbp+57h+OutBuffer], 0
0x1800cc949  xorps   xmm0, xmm0
0x1800cc94c  xor     eax, eax
0x1800cc94e  movups  [rbp+57h+var_34], xmm0
0x1800cc952  movups  [rbp+57h+var_24], xmm0
0x1800cc956  mov     [rbp+57h+var_14], eax
0x1800cc959  mov     [rsp+0D0h+lpOverlapped], rax; lpOverlapped
0x1800cc95e  lea     rax, [rbp+57h+BytesReturned]
0x1800cc962  mov     [rsp+0D0h+hTemplateFile], rax; lpBytesReturned
0x1800cc967  mov     [rsp+0D0h+dwFlagsAndAttributes], 28h ; '('; nOutBufferSize
0x1800cc96f  lea     rax, [rbp+57h+OutBuffer]
0x1800cc973  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; lpOutBuffer
0x1800cc978  xor     r9d, r9d; nInBufferSize
0x1800cc97b  xor     r8d, r8d; lpInBuffer
0x1800cc97e  mov     edx, 700A0h; dwIoControlCode
0x1800cc983  mov     rcx, [rbp+57h+hDevice]; hDevice
0x1800cc987  call    cs:__imp_DeviceIoControl
0x1800cc98d  test    eax, eax
0x1800cc98f  jz      short loc_1800CC9AB
0x1800cc991  mov     rax, qword ptr [rbp+57h+var_24+4]
0x1800cc995  cqo
0x1800cc997  and     edx, 0FFFFFh
0x1800cc99d  add     rax, rdx
0x1800cc9a0  sar     rax, 14h
0x1800cc9a4  mov     cs:qword_1801FE8E0, rax
0x1800cc9ab  xor     eax, eax
0x1800cc9ad  mov     [rbp+57h+var_48], rax
0x1800cc9b1  mov     [rbp+57h+var_40], eax
0x1800cc9b4  mov     [rbp+57h+var_54], rax
0x1800cc9b8  mov     [rbp+57h+InBuffer], 7
0x1800cc9bf  mov     [rsp+0D0h+lpOverlapped], rax; lpOverlapped
0x1800cc9c4  lea     rax, [rbp+57h+BytesReturned]
0x1800cc9c8  mov     [rsp+0D0h+hTemplateFile], rax; lpBytesReturned
0x1800cc9cd  mov     r9d, 0Ch; nInBufferSize
0x1800cc9d3  mov     [rsp+0D0h+dwFlagsAndAttributes], r9d; nOutBufferSize
0x1800cc9d8  lea     rax, [rbp+57h+var_48]
0x1800cc9dc  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; lpOutBuffer
0x1800cc9e1  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x1800cc9e5  mov     edx, 2D1400h; dwIoControlCode
0x1800cc9ea  mov     rcx, [rbp+57h+hDevice]; hDevice
0x1800cc9ee  call    cs:__imp_DeviceIoControl
0x1800cc9f4  test    eax, eax
0x1800cc9f6  jz      short loc_1800CCA08
0x1800cc9f8  mov     al, byte ptr [rbp+57h+var_40]
0x1800cc9fb  neg     al
0x1800cc9fd  sbb     ecx, ecx
0x1800cc9ff  add     ecx, 4
0x1800cca02  mov     cs:dword_1801FE8E8, ecx
0x1800cca08  mov     [rbp+57h+var_88], r15
0x1800cca0c  cmp     [rbp+57h+hDevice], rbx
0x1800cca10  jz      short loc_1800CCA23
0x1800cca12  lea     rcx, [rbp+57h+var_88]
0x1800cca16  call    ?InternalClose@?$HandleT@UFileHandleTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::FileHandleTraits>::InternalClose(void)
0x1800cca1b  test    al, al
0x1800cca1d  jz      short loc_1800CCA54
0x1800cca1f  mov     [rbp+57h+hDevice], rbx
0x1800cca23  lea     rcx, [rbp+57h+lpBuffer]
0x1800cca27  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800cca2c  lea     rax, qword_1801FE8E0
0x1800cca33  mov     rcx, [rbp+57h+var_10]
0x1800cca37  xor     rcx, rsp; StackCookie
0x1800cca3a  call    __security_check_cookie
0x1800cca3f  lea     r11, [rsp+0D0h+var_s0]
0x1800cca47  mov     rbx, [r11+10h]
0x1800cca4b  mov     r15, [r11+18h]
0x1800cca4f  mov     rsp, r11
0x1800cca52  pop     rbp
0x1800cca53  retn
0x1800cca54  call    cs:__imp_GetLastError
0x1800cca5a  nop
0x1800cca5b  test    eax, eax
0x1800cca5d  jle     short loc_1800CCA67
0x1800cca5f  movzx   eax, ax
0x1800cca62  or      eax, 80070000h
0x1800cca67  mov     ecx, eax; this
0x1800cca69  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
