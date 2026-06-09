# GetServerStats(std::vector<_NFS_STAT,std::allocator<_NFS_STAT>> &)

- ea: `0x18002285c`
- end: `0x180022c8e`
- name: `?GetServerStats@@YAKAEAV?$vector@U_NFS_STAT@@V?$allocator@U_NFS_STAT@@@std@@@std@@@Z`
- size: `1074`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000f9c4`

## callees

- `0x18000eae4`
- `0x18000ec88`
- `0x18000efc8`
- `0x18002285c`
- `0x1800232ec`
- `0x180035b02`
- `0x180035b40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002293d`
- `KERNEL32!GetLastError` at `0x180022bac`
- `KERNEL32!GetLastError` at `0x180022c59`
- `KERNEL32!GetLastError` at `0x18002293d`
- `KERNEL32!GetLastError` at `0x180022bac`
- `KERNEL32!GetLastError` at `0x180022c59`
- `KERNEL32!CloseHandle` at `0x180022c51`
- `KERNEL32!CloseHandle` at `0x180022c51`
- `KERNEL32!CreateFileW` at `0x1800228eb`
- `KERNEL32!CreateFileW` at `0x1800228eb`
- `KERNEL32!DeviceIoControl` at `0x180022933`
- `KERNEL32!DeviceIoControl` at `0x180022ba2`
- `KERNEL32!DeviceIoControl` at `0x180022933`
- `KERNEL32!DeviceIoControl` at `0x180022ba2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetServerStats(__int64 a1)
{
  HANDLE FileW; // rsi
  DWORD LastError; // edi
  unsigned int i; // r14d
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  unsigned int j; // r14d
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  unsigned int k; // r14d
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // r14d
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  unsigned int m; // r14d
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  DWORD v25; // [rsp+40h] [rbp-C0h]
  DWORD BytesReturned; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE hDevice; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+58h] [rbp-A8h]
  _WORD v30[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+78h] [rbp-88h]
  _BYTE OutBuffer[848]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v34[2720]; // [rsp+3D0h] [rbp+2D0h] BYREF

  memset_0(OutBuffer, 0, sizeof(OutBuffer));
  BytesReturned = 0;
  memset_0(v34, 0, sizeof(v34));
  FileW = CreateFileW(L"\\\\.\\NfsSvr", 0x80000000, 0, 0, 3u, 0x1000080u, 0);
  hDevice = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    return GetLastError();
  }
  else
  {
    v25 = 0;
    if ( DeviceIoControl(FileW, 0x1000040Cu, 0, 0, OutBuffer, 0x350u, &BytesReturned, 0)
      || (LastError = GetLastError(), (v25 = LastError) == 0) )
    {
      for ( i = 0; i < 6; ++i )
      {
        v32 = 7;
        v31 = 0;
        v30[0] = 0;
        v28 = 1;
        v5 = std::char_traits<unsigned short>::length((&off_1800551B8)[2 * (int)i]);
        std::wstring::assign(v30, v6, v5);
        v29 = *(_DWORD *)&OutBuffer[4 * i + 92];
        std::vector<_NFS_STAT>::push_back(a1, &v28);
        LOBYTE(v7) = 1;
        std::wstring::_Tidy(v30, v7, 0);
      }
      for ( j = 0; j < 6; ++j )
      {
        v32 = 7;
        v31 = 0;
        v30[0] = 0;
        v28 = 3;
        v9 = std::char_traits<unsigned short>::length((&off_180055158)[2 * (int)j]);
        std::wstring::assign(v30, v10, v9);
        v29 = *(_DWORD *)&OutBuffer[4 * j + 116];
        std::vector<_NFS_STAT>::push_back(a1, &v28);
        LOBYTE(v11) = 1;
        std::wstring::_Tidy(v30, v11, 0);
      }
      for ( k = 0; k < 0x12; ++k )
      {
        v32 = 7;
        v31 = 0;
        v30[0] = 0;
        v28 = 0x100000002LL;
        v13 = std::char_traits<unsigned short>::length((&off_180054ED8)[2 * (int)k]);
        std::wstring::assign(v30, v14, v13);
        v29 = *(_DWORD *)&OutBuffer[4 * k + 340];
        std::vector<_NFS_STAT>::push_back(a1, &v28);
        LOBYTE(v15) = 1;
        std::wstring::_Tidy(v30, v15, 0);
      }
      v16 = 0;
      LastError = v25;
      do
      {
        v32 = 7;
        v31 = 0;
        v30[0] = 0;
        v28 = 0x100000003LL;
        v17 = std::char_traits<unsigned short>::length((&off_180054FF8)[2 * (int)v16]);
        std::wstring::assign(v30, v18, v17);
        v29 = *(_DWORD *)&OutBuffer[4 * v16 + 668];
        std::vector<_NFS_STAT>::push_back(a1, &v28);
        LOBYTE(v19) = 1;
        std::wstring::_Tidy(v30, v19, 0);
        ++v16;
      }
      while ( v16 < 0x16 );
      if ( !DeviceIoControl(hDevice, 0x10000460u, 0, 0, v34, 0xAA0u, &BytesReturned, 0) )
        LastError = GetLastError();
      for ( m = 0; m < 0x38; ++m )
      {
        v32 = 7;
        v31 = 0;
        v30[0] = 0;
        v28 = 0x100000004LL;
        v21 = std::char_traits<unsigned short>::length((&off_180055218)[2 * (int)m]);
        std::wstring::assign(v30, v22, v21);
        v29 = *(_DWORD *)&v34[40 * *((int *)&g_nfsV4Operations + 4 * (int)m) + 320];
        std::vector<_NFS_STAT>::push_back(a1, &v28);
        LOBYTE(v23) = 1;
        std::wstring::_Tidy(v30, v23, 0);
      }
      FileW = hDevice;
    }
    CloseHandle(FileW);
  }
  return LastError;
}

```

## disassembly

```asm
0x18002285c  mov     [rsp-8+arg_8], rbx
0x180022861  mov     [rsp-8+arg_10], rsi
0x180022866  push    rbp
0x180022867  push    rdi
0x180022868  push    r13
0x18002286a  push    r14
0x18002286c  push    r15
0x18002286e  lea     rbp, [rsp-0D80h]
0x180022876  sub     rsp, 0E80h
0x18002287d  mov     rax, cs:__security_cookie
0x180022884  xor     rax, rsp
0x180022887  mov     [rbp+0DA0h+var_30], rax
0x18002288e  mov     r15, rcx
0x180022891  mov     ebx, 350h
0x180022896  mov     r8d, ebx; Size
0x180022899  xor     edx, edx; Val
0x18002289b  lea     rcx, [rbp+0DA0h+OutBuffer]; void *
0x18002289f  call    memset_0
0x1800228a4  mov     [rsp+0EA0h+BytesReturned], 0
0x1800228ac  xor     edx, edx; Val
0x1800228ae  mov     r8d, 0AA0h; Size
0x1800228b4  lea     rcx, [rbp+0DA0h+var_AD0]; void *
0x1800228bb  call    memset_0
0x1800228c0  mov     [rsp+0EA0h+hTemplateFile], 0; hTemplateFile
0x1800228c9  mov     [rsp+0EA0h+dwFlagsAndAttributes], 1000080h; dwFlagsAndAttributes
0x1800228d1  mov     [rsp+0EA0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800228d9  xor     r9d, r9d; lpSecurityAttributes
0x1800228dc  xor     r8d, r8d; dwShareMode
0x1800228df  mov     edx, 80000000h; dwDesiredAccess
0x1800228e4  lea     rcx, aNfssvr; "\\\\.\\NfsSvr"
0x1800228eb  call    cs:__imp_CreateFileW
0x1800228f1  mov     rsi, rax
0x1800228f4  mov     [rsp+0EA0h+hDevice], rax
0x1800228f9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800228fd  jz      loc_180022C59
0x180022903  xor     edi, edi
0x180022905  mov     [rsp+0EA0h+var_E60], edi
0x180022909  mov     [rsp+0EA0h+lpOverlapped], rdi; lpOverlapped
0x18002290e  lea     rax, [rsp+0EA0h+BytesReturned]
0x180022913  mov     [rsp+0EA0h+hTemplateFile], rax; lpBytesReturned
0x180022918  mov     [rsp+0EA0h+dwFlagsAndAttributes], ebx; nOutBufferSize
0x18002291c  lea     rax, [rbp+0DA0h+OutBuffer]
0x180022920  mov     qword ptr [rsp+0EA0h+dwCreationDisposition], rax; lpOutBuffer
0x180022925  xor     r9d, r9d; nInBufferSize
0x180022928  xor     r8d, r8d; lpInBuffer
0x18002292b  mov     edx, 1000040Ch; dwIoControlCode
0x180022930  mov     rcx, rsi; hDevice
0x180022933  call    cs:__imp_DeviceIoControl
0x180022939  test    eax, eax
0x18002293b  jnz     short loc_180022951
0x18002293d  call    cs:__imp_GetLastError
0x180022943  mov     edi, eax
0x180022945  mov     [rsp+0EA0h+var_E60], eax
0x180022949  test    eax, eax
0x18002294b  jnz     loc_180022C4E
0x180022951  xor     r14d, r14d
0x180022954  lea     r13d, [r14+1]
0x180022958  lea     rsi, cs:180000000h
0x18002295f  mov     [rsp+0EA0h+var_E28], 7
0x180022968  mov     [rsp+0EA0h+var_E30], 0
0x180022971  xor     eax, eax
0x180022973  mov     [rsp+0EA0h+var_E40], ax
0x180022978  mov     [rsp+0EA0h+var_E50], 1
0x180022981  movsxd  rbx, r14d
0x180022984  mov     rax, rbx
0x180022987  add     rax, rax
0x18002298a  mov     rcx, rva off_1800551B8[rsi+rax*8]; "V1_MNT_NULL" ...
0x180022992  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180022997  mov     r8, rax
0x18002299a  mov     rdx, rcx
0x18002299d  lea     rcx, [rsp+0EA0h+var_E40]
0x1800229a2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800229a7  mov     eax, [rbp+rbx*4+0DA0h+var_DC4]
0x1800229ab  mov     [rsp+0EA0h+var_E48], eax
0x1800229af  lea     rdx, [rsp+0EA0h+var_E50]
0x1800229b4  mov     rcx, r15
0x1800229b7  call    ?push_back@?$vector@U_NFS_STAT@@V?$allocator@U_NFS_STAT@@@std@@@std@@QEAAXAEBU_NFS_STAT@@@Z; std::vector<_NFS_STAT>::push_back(_NFS_STAT const &)
0x1800229bc  nop
0x1800229bd  xor     r8d, r8d
0x1800229c0  mov     dl, r13b
0x1800229c3  lea     rcx, [rsp+0EA0h+var_E40]
0x1800229c8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800229cd  add     r14d, r13d
0x1800229d0  cmp     r14d, 6
0x1800229d4  jb      short loc_18002295F
0x1800229d6  xor     r14d, r14d
0x1800229d9  mov     [rsp+0EA0h+var_E28], 7
0x1800229e2  mov     [rsp+0EA0h+var_E30], 0
0x1800229eb  xor     eax, eax
0x1800229ed  mov     [rsp+0EA0h+var_E40], ax
0x1800229f2  mov     [rsp+0EA0h+var_E50], 3
0x1800229fb  movsxd  rbx, r14d
0x1800229fe  mov     rax, rbx
0x180022a01  add     rax, rax
0x180022a04  lea     rcx, cs:180000000h
0x180022a0b  mov     rcx, rva off_180055158[rcx+rax*8]; "V3_MNT_NULL" ...
0x180022a13  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180022a18  mov     r8, rax
0x180022a1b  mov     rdx, rcx
0x180022a1e  lea     rcx, [rsp+0EA0h+var_E40]
0x180022a23  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180022a28  mov     eax, [rbp+rbx*4+0DA0h+var_DAC]
0x180022a2c  mov     [rsp+0EA0h+var_E48], eax
0x180022a30  lea     rdx, [rsp+0EA0h+var_E50]
0x180022a35  mov     rcx, r15
0x180022a38  call    ?push_back@?$vector@U_NFS_STAT@@V?$allocator@U_NFS_STAT@@@std@@@std@@QEAAXAEBU_NFS_STAT@@@Z; std::vector<_NFS_STAT>::push_back(_NFS_STAT const &)
0x180022a3d  nop
0x180022a3e  xor     r8d, r8d
0x180022a41  mov     dl, r13b
0x180022a44  lea     rcx, [rsp+0EA0h+var_E40]
0x180022a49  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180022a4e  add     r14d, r13d
0x180022a51  cmp     r14d, 6
0x180022a55  jb      short loc_1800229D9
0x180022a57  xor     r14d, r14d
0x180022a5a  lea     rdi, cs:180000000h
0x180022a61  mov     [rsp+0EA0h+var_E28], 7
0x180022a6a  mov     [rsp+0EA0h+var_E30], 0
0x180022a73  xor     eax, eax
0x180022a75  mov     [rsp+0EA0h+var_E40], ax
0x180022a7a  mov     dword ptr [rsp+0EA0h+var_E50], 2
0x180022a82  mov     dword ptr [rsp+0EA0h+var_E50+4], r13d
0x180022a87  movsxd  rbx, r14d
0x180022a8a  mov     rax, rbx
0x180022a8d  add     rax, rax
0x180022a90  mov     rcx, rva off_180054ED8[rdi+rax*8]; "V2_NFS_NULL" ...
0x180022a98  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180022a9d  mov     r8, rax
0x180022aa0  mov     rdx, rcx
0x180022aa3  lea     rcx, [rsp+0EA0h+var_E40]
0x180022aa8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180022aad  mov     eax, [rbp+rbx*4+0DA0h+var_CCC]
0x180022ab4  mov     [rsp+0EA0h+var_E48], eax
0x180022ab8  lea     rdx, [rsp+0EA0h+var_E50]
0x180022abd  mov     rcx, r15
0x180022ac0  call    ?push_back@?$vector@U_NFS_STAT@@V?$allocator@U_NFS_STAT@@@std@@@std@@QEAAXAEBU_NFS_STAT@@@Z; std::vector<_NFS_STAT>::push_back(_NFS_STAT const &)
0x180022ac5  nop
0x180022ac6  xor     r8d, r8d
0x180022ac9  mov     dl, r13b
0x180022acc  lea     rcx, [rsp+0EA0h+var_E40]
0x180022ad1  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180022ad6  add     r14d, r13d
0x180022ad9  cmp     r14d, 12h
0x180022add  jb      short loc_180022A61
0x180022adf  xor     r14d, r14d
0x180022ae2  mov     edi, [rsp+0EA0h+var_E60]
0x180022ae6  lea     rsi, cs:180000000h
0x180022aed  mov     [rsp+0EA0h+var_E28], 7
0x180022af6  mov     [rsp+0EA0h+var_E30], 0
0x180022aff  xor     eax, eax
0x180022b01  mov     [rsp+0EA0h+var_E40], ax
0x180022b06  mov     dword ptr [rsp+0EA0h+var_E50], 3
0x180022b0e  mov     dword ptr [rsp+0EA0h+var_E50+4], r13d
0x180022b13  movsxd  rbx, r14d
0x180022b16  mov     rax, rbx
0x180022b19  add     rax, rax
0x180022b1c  mov     rcx, rva off_180054FF8[rsi+rax*8]; "V3_NFS_NULL" ...
0x180022b24  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180022b29  mov     r8, rax
0x180022b2c  mov     rdx, rcx
0x180022b2f  lea     rcx, [rsp+0EA0h+var_E40]
0x180022b34  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180022b39  mov     eax, [rbp+rbx*4+0DA0h+var_B84]
0x180022b40  mov     [rsp+0EA0h+var_E48], eax
0x180022b44  lea     rdx, [rsp+0EA0h+var_E50]
0x180022b49  mov     rcx, r15
0x180022b4c  call    ?push_back@?$vector@U_NFS_STAT@@V?$allocator@U_NFS_STAT@@@std@@@std@@QEAAXAEBU_NFS_STAT@@@Z; std::vector<_NFS_STAT>::push_back(_NFS_STAT const &)
0x180022b51  nop
0x180022b52  xor     r8d, r8d
0x180022b55  mov     dl, r13b
0x180022b58  lea     rcx, [rsp+0EA0h+var_E40]
0x180022b5d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180022b62  add     r14d, r13d
0x180022b65  cmp     r14d, 16h
0x180022b69  jb      short loc_180022AED
0x180022b6b  mov     [rsp+0EA0h+lpOverlapped], 0; lpOverlapped
0x180022b74  lea     rax, [rsp+0EA0h+BytesReturned]
0x180022b79  mov     [rsp+0EA0h+hTemplateFile], rax; lpBytesReturned
0x180022b7e  mov     [rsp+0EA0h+dwFlagsAndAttributes], 0AA0h; nOutBufferSize
0x180022b86  lea     rax, [rbp+0DA0h+var_AD0]
0x180022b8d  mov     qword ptr [rsp+0EA0h+dwCreationDisposition], rax; lpOutBuffer
0x180022b92  xor     r9d, r9d; nInBufferSize
0x180022b95  xor     r8d, r8d; lpInBuffer
0x180022b98  mov     edx, 10000460h; dwIoControlCode
0x180022b9d  mov     rcx, [rsp+0EA0h+hDevice]; hDevice
0x180022ba2  call    cs:__imp_DeviceIoControl
0x180022ba8  test    eax, eax
0x180022baa  jnz     short loc_180022BB4
0x180022bac  call    cs:__imp_GetLastError
0x180022bb2  mov     edi, eax
0x180022bb4  xor     r14d, r14d
0x180022bb7  lea     rsi, cs:180000000h
0x180022bbe  mov     [rsp+0EA0h+var_E28], 7
0x180022bc7  mov     [rsp+0EA0h+var_E30], 0
0x180022bd0  xor     eax, eax
0x180022bd2  mov     [rsp+0EA0h+var_E40], ax
0x180022bd7  mov     dword ptr [rsp+0EA0h+var_E50], 4
0x180022bdf  mov     dword ptr [rsp+0EA0h+var_E50+4], r13d
0x180022be4  movsxd  rbx, r14d
0x180022be7  add     rbx, rbx
0x180022bea  mov     rcx, rva off_180055218[rsi+rbx*8]; "V4_NFS_ACCESS" ...
0x180022bf2  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180022bf7  mov     r8, rax
0x180022bfa  mov     rdx, rcx
0x180022bfd  lea     rcx, [rsp+0EA0h+var_E40]
0x180022c02  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180022c07  movsxd  rax, rva ?g_nfsV4Operations@@3PAU_NFS_OPERATIONS@@A[rsi+rbx*8]; _NFS_OPERATIONS near * g_nfsV4Operations ...
0x180022c0f  lea     rcx, [rax+rax*4]
0x180022c13  mov     eax, [rbp+rcx*8+0DA0h+var_990]
0x180022c1a  mov     [rsp+0EA0h+var_E48], eax
0x180022c1e  lea     rdx, [rsp+0EA0h+var_E50]
0x180022c23  mov     rcx, r15
0x180022c26  call    ?push_back@?$vector@U_NFS_STAT@@V?$allocator@U_NFS_STAT@@@std@@@std@@QEAAXAEBU_NFS_STAT@@@Z; std::vector<_NFS_STAT>::push_back(_NFS_STAT const &)
0x180022c2b  nop
0x180022c2c  xor     r8d, r8d
0x180022c2f  mov     dl, r13b
0x180022c32  lea     rcx, [rsp+0EA0h+var_E40]
0x180022c37  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180022c3c  add     r14d, r13d
0x180022c3f  cmp     r14d, 38h ; '8'
0x180022c43  jb      loc_180022BBE
0x180022c49  mov     rsi, [rsp+0EA0h+hDevice]
0x180022c4e  mov     rcx, rsi; hObject
0x180022c51  call    cs:__imp_CloseHandle
0x180022c57  jmp     short loc_180022C61
0x180022c59  call    cs:__imp_GetLastError
0x180022c5f  mov     edi, eax
0x180022c61  mov     eax, edi
0x180022c63  mov     rcx, [rbp+0DA0h+var_30]
0x180022c6a  xor     rcx, rsp; StackCookie
0x180022c6d  call    __security_check_cookie
0x180022c72  lea     r11, [rsp+0EA0h+var_20]
0x180022c7a  mov     rbx, [r11+38h]
0x180022c7e  mov     rsi, [r11+40h]
0x180022c82  mov     rsp, r11
0x180022c85  pop     r15
0x180022c87  pop     r14
0x180022c89  pop     r13
0x180022c8b  pop     rdi
0x180022c8c  pop     rbp
0x180022c8d  retn
```
