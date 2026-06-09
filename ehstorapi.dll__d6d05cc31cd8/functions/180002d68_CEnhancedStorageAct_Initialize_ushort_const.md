# CEnhancedStorageAct::Initialize(ushort const *)

- ea: `0x180002d68`
- end: `0x18000347f`
- name: `?Initialize@CEnhancedStorageAct@@AEAAJPEBG@Z`
- size: `1815`
- prototype: `__int64 __fastcall(CEnhancedStorageAct *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180004380`
- `0x180005960`

## callees

- `0x18000124c`
- `0x180001258`
- `0x180002338`
- `0x180002504`
- `0x180002c4c`
- `0x180002d68`
- `0x180003924`
- `0x180003bdc`
- `0x180003c54`
- `0x180007430`
- `0x180007840`
- `0x18000c4c2`
- `0x18000c4f0`
- `0x18000d010`

## import_xrefs

- `msvcrt!mbstowcs` at `0x180003382`
- `msvcrt!mbstowcs` at `0x1800033d3`
- `msvcrt!mbstowcs` at `0x180003382`
- `msvcrt!mbstowcs` at `0x1800033d3`
- `msvcrt!free` at `0x180002de7`
- `msvcrt!free` at `0x180002de7`
- `KERNEL32!CreateFileW` at `0x180002e1b`
- `KERNEL32!CreateFileW` at `0x180002e1b`
- `KERNEL32!GetLastError` at `0x180002e2f`
- `KERNEL32!GetLastError` at `0x180002eb9`
- `KERNEL32!GetLastError` at `0x180002ec9`
- `KERNEL32!GetLastError` at `0x180002f95`
- `KERNEL32!GetLastError` at `0x180003240`
- `KERNEL32!GetLastError` at `0x180003317`
- `KERNEL32!GetLastError` at `0x180002e2f`
- `KERNEL32!GetLastError` at `0x180002eb9`
- `KERNEL32!GetLastError` at `0x180002ec9`
- `KERNEL32!GetLastError` at `0x180002f95`
- `KERNEL32!GetLastError` at `0x180003240`
- `KERNEL32!GetLastError` at `0x180003317`
- `KERNEL32!DeviceIoControl` at `0x180002eaf`
- `KERNEL32!DeviceIoControl` at `0x180002f8b`
- `KERNEL32!DeviceIoControl` at `0x180003236`
- `KERNEL32!DeviceIoControl` at `0x18000330d`
- `KERNEL32!DeviceIoControl` at `0x180002eaf`
- `KERNEL32!DeviceIoControl` at `0x180002f8b`
- `KERNEL32!DeviceIoControl` at `0x180003236`
- `KERNEL32!DeviceIoControl` at `0x18000330d`
- `KERNEL32!CloseHandle` at `0x18000343d`
- `KERNEL32!CloseHandle` at `0x18000343d`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageAct::Initialize(CEnhancedStorageAct *this, const unsigned __int16 *a2)
{
  CEnhancedStorageAct *v2; // r15
  LPCWSTR *v3; // rdi
  void **v4; // r12
  HANDLE FileW; // rax
  __int64 v6; // r13
  signed int LastError; // eax
  int RegistryProperty; // ebx
  unsigned int *v9; // r14
  signed int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  signed int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // rbx
  CEnhancedStorageSilo *v18; // rdi
  void *v19; // rcx
  CEnhancedStorageSilo *v20; // rax
  char *v21; // rdi
  HANDLE v22; // r12
  signed int v23; // eax
  signed int v24; // eax
  DWORD v25; // ecx
  __int64 v26; // rcx
  wchar_t *v27; // r12
  __int64 v28; // rcx
  DWORD BytesReturned; // [rsp+50h] [rbp-98h] BYREF
  unsigned int v31; // [rsp+54h] [rbp-94h]
  int InBuffer; // [rsp+58h] [rbp-90h] BYREF
  unsigned int v33; // [rsp+5Ch] [rbp-8Ch] BYREF
  CEnhancedStorageSilo *v34; // [rsp+60h] [rbp-88h] BYREF
  void *Block; // [rsp+68h] [rbp-80h] BYREF
  HANDLE hDevice; // [rsp+70h] [rbp-78h]
  unsigned int v37; // [rsp+78h] [rbp-70h]
  signed int v38; // [rsp+7Ch] [rbp-6Ch] BYREF
  int v39; // [rsp+80h] [rbp-68h] BYREF
  __int64 v40; // [rsp+84h] [rbp-64h]
  _OWORD OutBuffer[2]; // [rsp+90h] [rbp-58h] BYREF
  __int64 v42; // [rsp+B0h] [rbp-38h]

  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v2 = this;
    hDevice = this;
    RegistryProperty = 0;
    InBuffer = 3;
    BytesReturned = 0;
    v3 = (LPCWSTR *)((char *)this + 64);
    Block = (char *)this + 64;
    ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 64, a2);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v38) )
    {
      v31 = v38;
      if ( v38 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids,
            (unsigned int)v38);
        RegistryProperty = v31;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180002DC0);
        return (unsigned int)RegistryProperty;
      }
      RegistryProperty = v31;
      v2 = (CEnhancedStorageAct *)hDevice;
      v3 = (LPCWSTR *)Block;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180002DC9);
    }
  }
  v4 = (void **)((char *)v2 + 72);
  if ( *((_QWORD *)v2 + 9) )
  {
    free(*v4);
    *v4 = 0;
  }
  *((_QWORD *)v2 + 10) = 0;
  *((_QWORD *)v2 + 11) = 0;
  FileW = CreateFileW(*v3, 0x80000000, 3u, 0, 3u, 0, 0);
  hDevice = FileW;
  v6 = -1;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    RegistryProperty = LastError;
    if ( LastError > 0 )
      RegistryProperty = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids,
        (unsigned int)RegistryProperty);
    return (unsigned int)RegistryProperty;
  }
  if ( !DeviceIoControl(FileW, 0x2D1410u, &InBuffer, 4u, 0, 0, &BytesReturned, 0) && GetLastError() != 234 )
  {
    v9 = 0;
    v10 = GetLastError();
    RegistryProperty = v10;
    if ( v10 > 0 )
      RegistryProperty = (unsigned __int16)v10 | 0x80070000;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_80;
    v12 = 12;
    goto LABEL_17;
  }
  v9 = (unsigned int *)operator new[](BytesReturned);
  if ( v9 )
  {
    if ( DeviceIoControl(hDevice, 0x2D1410u, &InBuffer, 4u, v9, BytesReturned, &BytesReturned, 0) )
    {
      *((_DWORD *)v2 + 159) = 0;
      v15 = *v9;
      v37 = *v9;
      v16 = 0;
      while ( 1 )
      {
        v31 = v16;
        if ( v16 >= v15 )
          break;
        v34 = 0;
        Block = 0;
        v33 = 0;
        RegistryProperty = ATL::CComObject<CEnhancedStorageSilo>::CreateInstance(&v34);
        if ( RegistryProperty < 0 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v12 = 15;
            goto LABEL_17;
          }
          goto LABEL_80;
        }
        v17 = 264LL * v16;
        HIWORD(v9[v17 + 4]) = v9[v17 + 4];
        (*(void (__fastcall **)(CEnhancedStorageSilo *))(*(_QWORD *)v34 + 8LL))(v34);
        v18 = v34;
        RegistryProperty = CEnhancedStorageSilo::Initialize(
                             v34,
                             (const unsigned __int16 *)&v9[v17 + 4],
                             v31,
                             v9[v17 + 1],
                             BYTE2(v9[v17 + 1]),
                             v9[v17 + 2],
                             v9[v17 + 3],
                             BYTE1(v9[v17 + 3]),
                             BYTE2(v9[v17 + 3]),
                             HIBYTE(v9[v17 + 3]));
        if ( RegistryProperty < 0 )
        {
          (*(void (__fastcall **)(CEnhancedStorageSilo *))(*(_QWORD *)v18 + 16LL))(v18);
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v12 = 16;
            goto LABEL_17;
          }
          goto LABEL_80;
        }
        RegistryProperty = CEnhancedStorageSilo::GetRegistryProperty(
                             v18,
                             L"SiloFlags",
                             (unsigned __int8 **)&Block,
                             &v33,
                             4u);
        if ( RegistryProperty < 0 )
        {
          *((_DWORD *)v2 + 159) = 1;
          RegistryProperty = 0;
        }
        else
        {
          v19 = Block;
          if ( v33 == 4 && (*(_BYTE *)Block & 1) == 0 )
            *((_DWORD *)v2 + 159) = 1;
          operator delete[](v19);
        }
        v20 = (CEnhancedStorageSilo *)*((_QWORD *)v2 + 10);
        v34 = v20;
        if ( (unsigned __int64)v20 >= *((_QWORD *)v2 + 11)
          && !(unsigned __int8)ATL::CAtlArray<ATL::CComObject<CEnhancedStorageSilo> *,ATL::CElementTraits<ATL::CComObject<CEnhancedStorageSilo> *>>::GrowBuffer(
                                 (char *)v2 + 72,
                                 (char *)v20 + 1) )
        {
          ATL::AtlThrowImpl(-2147024882);
        }
        *((_QWORD *)*v4 + (_QWORD)v34) = v18;
        ++*((_QWORD *)v2 + 10);
        v16 = v31 + 1;
        v15 = v37;
      }
      v21 = (char *)v2 + 104;
      memset_0((char *)v2 + 104, 0, 0x20Au);
      *(_QWORD *)((char *)v2 + 628) = 0;
      v40 = 0;
      memset(OutBuffer, 0, sizeof(OutBuffer));
      v42 = 0;
      v39 = 0;
      operator delete[](v9);
      BytesReturned = 0;
      v22 = hDevice;
      if ( DeviceIoControl(hDevice, 0x2D1400u, &v39, 0xCu, OutBuffer, 0x28u, &BytesReturned, 0) )
      {
        BytesReturned = DWORD1(OutBuffer[0]);
        v9 = (unsigned int *)operator new[](DWORD1(OutBuffer[0]));
        if ( v9 )
        {
          if ( DeviceIoControl(v22, 0x2D1400u, &v39, 0xCu, v9, BytesReturned, &BytesReturned, 0) )
          {
            *((_DWORD *)v2 + 158) = *((unsigned __int8 *)v9 + 10);
            v25 = 261;
            BytesReturned = 261;
            if ( v9[3] )
            {
              mbstowcs((wchar_t *)v2 + 52, (const char *)v9 + v9[3], 8u);
              v26 = -1;
              do
                ++v26;
              while ( *(_WORD *)&v21[2 * v26] );
              *(_WORD *)&v21[2 * (unsigned int)v26] = 32;
              v27 = (wchar_t *)&v21[2 * (unsigned int)v26 + 2];
              v25 = -1 - v26 + BytesReturned;
              BytesReturned = v25;
            }
            else
            {
              v27 = (wchar_t *)((char *)v2 + 104);
            }
            if ( v9[4] && v25 >= 0x22 )
            {
              mbstowcs(v27, (const char *)v9 + v9[4], 0x10u);
              v28 = -1;
              do
                ++v28;
              while ( v27[v28] );
              v27[(unsigned int)v28] = 0;
              BytesReturned -= v28;
            }
            do
              ++v6;
            while ( *(_WORD *)&v21[2 * v6] );
            *((_DWORD *)v2 + 157) = v6;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                20,
                (unsigned int)WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids,
                (_DWORD)v2 + 104,
                v6);
          }
          else
          {
            v24 = GetLastError();
            RegistryProperty = v24;
            if ( v24 > 0 )
              RegistryProperty = (unsigned __int16)v24 | 0x80070000;
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v12 = 19;
              goto LABEL_17;
            }
          }
        }
        else
        {
          v13 = 2147942414LL;
          RegistryProperty = -2147024882;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v12 = 18;
            goto LABEL_18;
          }
        }
      }
      else
      {
        v23 = GetLastError();
        RegistryProperty = v23;
        if ( v23 > 0 )
          RegistryProperty = (unsigned __int16)v23 | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids,
            (unsigned int)RegistryProperty);
        v9 = 0;
      }
      goto LABEL_80;
    }
    v14 = GetLastError();
    RegistryProperty = v14;
    if ( v14 > 0 )
      RegistryProperty = (unsigned __int16)v14 | 0x80070000;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 14;
LABEL_17:
      v13 = (unsigned int)RegistryProperty;
LABEL_18:
      WPP_SF_d(v11[2], v12, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids, v13);
    }
  }
  else
  {
    v13 = 2147942414LL;
    RegistryProperty = -2147024882;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 13;
      goto LABEL_18;
    }
  }
LABEL_80:
  CloseHandle(hDevice);
  if ( v9 )
    operator delete[](v9);
  return (unsigned int)RegistryProperty;
}

```

## disassembly

```asm
0x180002d68  mov     [rsp+arg_10], rbx
0x180002d6d  mov     [rsp+arg_18], rsi
0x180002d72  push    rdi
0x180002d73  push    r12
0x180002d75  push    r13
0x180002d77  push    r14
0x180002d79  push    r15
0x180002d7b  sub     rsp, 0C0h
0x180002d82  mov     rax, cs:__security_cookie
0x180002d89  xor     rax, rsp
0x180002d8c  mov     [rsp+0E8h+var_30], rax
0x180002d94  mov     r15, rcx
0x180002d97  mov     [rsp+0E8h+hDevice], rcx
0x180002d9c  xor     esi, esi
0x180002d9e  mov     ebx, esi
0x180002da0  mov     [rsp+0E8h+InBuffer], 3
0x180002da8  mov     [rsp+0E8h+BytesReturned], esi
0x180002dac  lea     rdi, [rcx+40h]
0x180002db0  mov     [rsp+0E8h+Block], rdi
0x180002db5  mov     rcx, rdi
0x180002db8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180002dbd  nop
0x180002dbe  jmp     short loc_180002DD9
0x180002dc0  mov     ebx, [rsp+0E8h+var_94]
0x180002dc4  jmp     loc_180003450
0x180002dc9  xor     esi, esi
0x180002dcb  mov     ebx, [rsp+0E8h+var_94]
0x180002dcf  mov     r15, [rsp+0E8h+hDevice]
0x180002dd4  mov     rdi, [rsp+0E8h+Block]
0x180002dd9  lea     r12, [r15+48h]
0x180002ddd  cmp     [r12], rsi
0x180002de1  jz      short loc_180002DF1
0x180002de3  mov     rcx, [r12]; Block
0x180002de7  call    cs:__imp_free
0x180002ded  mov     [r12], rsi
0x180002df1  mov     [r12+8], rsi
0x180002df6  mov     [r12+10h], rsi
0x180002dfb  mov     [rsp+0E8h+hTemplateFile], rsi; hTemplateFile
0x180002e00  mov     [rsp+0E8h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x180002e04  mov     [rsp+0E8h+dwCreationDisposition], 3; dwCreationDisposition
0x180002e0c  xor     r9d, r9d; lpSecurityAttributes
0x180002e0f  mov     edx, 80000000h; dwDesiredAccess
0x180002e14  lea     r8d, [r9+3]; dwShareMode
0x180002e18  mov     rcx, [rdi]; lpFileName
0x180002e1b  call    cs:__imp_CreateFileW
0x180002e21  mov     [rsp+0E8h+hDevice], rax
0x180002e26  or      r13, 0FFFFFFFFFFFFFFFFh
0x180002e2a  cmp     rax, r13
0x180002e2d  jnz     short loc_180002E82
0x180002e2f  call    cs:__imp_GetLastError
0x180002e35  mov     ebx, eax
0x180002e37  test    eax, eax
0x180002e39  jle     short loc_180002E44
0x180002e3b  movzx   ebx, ax
0x180002e3e  or      ebx, 80070000h
0x180002e44  lea     rax, WPP_GLOBAL_Control
0x180002e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e52  cmp     rcx, rax
0x180002e55  jz      loc_180003450
0x180002e5b  test    byte ptr [rcx+1Ch], 2
0x180002e5f  jz      loc_180003450
0x180002e65  mov     edx, 0Bh
0x180002e6a  mov     r9d, ebx
0x180002e6d  lea     r8, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids
0x180002e74  mov     rcx, [rcx+10h]
0x180002e78  call    WPP_SF_d
0x180002e7d  jmp     loc_180003450
0x180002e82  mov     [rsp+0E8h+lpOverlapped], rsi; lpOverlapped
0x180002e87  lea     rcx, [rsp+0E8h+BytesReturned]
0x180002e8c  mov     [rsp+0E8h+hTemplateFile], rcx; lpBytesReturned
0x180002e91  mov     [rsp+0E8h+dwFlagsAndAttributes], esi; nOutBufferSize
0x180002e95  mov     qword ptr [rsp+0E8h+dwCreationDisposition], rsi; lpOutBuffer
0x180002e9a  mov     edi, 4
0x180002e9f  mov     r9d, edi; nInBufferSize
0x180002ea2  lea     r8, [rsp+0E8h+InBuffer]; lpInBuffer
0x180002ea7  mov     edx, 2D1410h; dwIoControlCode
0x180002eac  mov     rcx, rax; hDevice
0x180002eaf  call    cs:__imp_DeviceIoControl
0x180002eb5  test    eax, eax
0x180002eb7  jnz     short loc_180002F1C
0x180002eb9  call    cs:__imp_GetLastError
0x180002ebf  cmp     eax, 0EAh
0x180002ec4  jz      short loc_180002F1C
0x180002ec6  mov     r14, rsi
0x180002ec9  call    cs:__imp_GetLastError
0x180002ecf  mov     ebx, eax
0x180002ed1  test    eax, eax
0x180002ed3  jle     short loc_180002EDE
0x180002ed5  movzx   ebx, ax
0x180002ed8  or      ebx, 80070000h
0x180002ede  lea     rax, WPP_GLOBAL_Control
0x180002ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x180002eec  cmp     rcx, rax
0x180002eef  jz      loc_180003438
0x180002ef5  test    byte ptr [rcx+1Ch], 2
0x180002ef9  jz      loc_180003438
0x180002eff  mov     edx, 0Ch
0x180002f04  mov     r9d, ebx
0x180002f07  lea     r8, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids
0x180002f0e  mov     rcx, [rcx+10h]
0x180002f12  call    WPP_SF_d
0x180002f17  jmp     loc_180003438
0x180002f1c  mov     ecx, [rsp+0E8h+BytesReturned]; unsigned __int64
0x180002f20  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002f25  mov     r14, rax
0x180002f28  test    rax, rax
0x180002f2b  jnz     short loc_180002F5D
0x180002f2d  mov     r9d, 8007000Eh
0x180002f33  mov     ebx, r9d
0x180002f36  lea     rax, WPP_GLOBAL_Control
0x180002f3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f44  cmp     rcx, rax
0x180002f47  jz      loc_180003438
0x180002f4d  test    byte ptr [rcx+1Ch], 2
0x180002f51  jz      loc_180003438
0x180002f57  lea     edx, [r14+0Dh]
0x180002f5b  jmp     short loc_180002F07
0x180002f5d  mov     [rsp+0E8h+lpOverlapped], rsi; lpOverlapped
0x180002f62  lea     rax, [rsp+0E8h+BytesReturned]
0x180002f67  mov     [rsp+0E8h+hTemplateFile], rax; lpBytesReturned
0x180002f6c  mov     eax, [rsp+0E8h+BytesReturned]
0x180002f70  mov     [rsp+0E8h+dwFlagsAndAttributes], eax; nOutBufferSize
0x180002f74  mov     qword ptr [rsp+0E8h+dwCreationDisposition], r14; lpOutBuffer
0x180002f79  mov     r9d, edi; nInBufferSize
0x180002f7c  lea     r8, [rsp+0E8h+InBuffer]; lpInBuffer
0x180002f81  mov     edx, 2D1410h; dwIoControlCode
0x180002f86  mov     rcx, [rsp+0E8h+hDevice]; hDevice
0x180002f8b  call    cs:__imp_DeviceIoControl
0x180002f91  test    eax, eax
0x180002f93  jnz     short loc_180002FD5
0x180002f95  call    cs:__imp_GetLastError
0x180002f9b  mov     ebx, eax
0x180002f9d  test    eax, eax
0x180002f9f  jle     short loc_180002FAA
0x180002fa1  movzx   ebx, ax
0x180002fa4  or      ebx, 80070000h
0x180002faa  lea     rax, WPP_GLOBAL_Control
0x180002fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fb8  cmp     rcx, rax
0x180002fbb  jz      loc_180003438
0x180002fc1  test    byte ptr [rcx+1Ch], 2
0x180002fc5  jz      loc_180003438
0x180002fcb  mov     edx, 0Eh
0x180002fd0  jmp     loc_180002F04
0x180002fd5  mov     [r15+27Ch], esi
0x180002fdc  mov     eax, [r14]
0x180002fdf  mov     [rsp+0E8h+var_70], eax
0x180002fe3  mov     edi, esi
0x180002fe5  mov     [rsp+0E8h+var_94], edi
0x180002fe9  cmp     edi, eax
0x180002feb  jnb     loc_18000319C
0x180002ff1  mov     [rsp+0E8h+var_88], rsi
0x180002ff6  mov     [rsp+0E8h+Block], rsi
0x180002ffb  mov     [rsp+0E8h+var_8C], esi
0x180002fff  lea     rcx, [rsp+0E8h+var_88]
0x180003004  call    ?CreateInstance@?$CComObject@VCEnhancedStorageSilo@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CEnhancedStorageSilo>::CreateInstance(ATL::CComObject<CEnhancedStorageSilo> * *)
0x180003009  mov     ebx, eax
0x18000300b  test    eax, eax
0x18000300d  js      loc_180003171
0x180003013  mov     eax, edi
0x180003015  imul    rbx, rax, 420h
0x18000301c  lea     rdi, [rbx+r14]
0x180003020  movzx   eax, word ptr [rdi+10h]
0x180003024  mov     [rbx+r14+12h], ax
0x18000302a  mov     rcx, [rsp+0E8h+var_88]
0x18000302f  mov     rax, [rcx]
0x180003032  mov     rax, [rax+8]
0x180003036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000303b  mov     al, [rbx+r14+0Fh]
0x180003040  mov     [rsp+0E8h+var_A0], al; char
0x180003044  mov     al, [rbx+r14+0Eh]
0x180003049  mov     [rsp+0E8h+var_A8], al; char
0x18000304d  mov     al, [rbx+r14+0Dh]
0x180003052  mov     byte ptr [rsp+0E8h+lpOverlapped], al; char
0x180003056  mov     al, [rbx+r14+0Ch]
0x18000305b  mov     byte ptr [rsp+0E8h+hTemplateFile], al; char
0x18000305f  mov     eax, [rbx+r14+8]
0x180003064  mov     [rsp+0E8h+dwFlagsAndAttributes], eax; unsigned int
0x180003068  mov     al, [rbx+r14+6]
0x18000306d  mov     byte ptr [rsp+0E8h+dwCreationDisposition], al; char
0x180003071  mov     r9b, [rbx+r14+4]; unsigned __int8
0x180003076  mov     r8d, [rsp+0E8h+var_94]; unsigned int
0x18000307b  lea     rdx, [rdi+10h]; unsigned __int16 *
0x18000307f  mov     rdi, [rsp+0E8h+var_88]
0x180003084  mov     rcx, rdi; this
0x180003087  call    ?Initialize@CEnhancedStorageSilo@@AEAAJPEBGKEEKEEEE@Z; CEnhancedStorageSilo::Initialize(ushort const *,ulong,uchar,uchar,ulong,uchar,uchar,uchar,uchar)
0x18000308c  mov     ebx, eax
0x18000308e  mov     rcx, rdi; this
0x180003091  test    eax, eax
0x180003093  js      loc_18000313A
0x180003099  mov     [rsp+0E8h+dwCreationDisposition], 4; unsigned int
0x1800030a1  lea     r9, [rsp+0E8h+var_8C]; unsigned int *
0x1800030a6  lea     r8, [rsp+0E8h+Block]; unsigned __int8 **
0x1800030ab  lea     rdx, aSiloflags; "SiloFlags"
0x1800030b2  call    ?GetRegistryProperty@CEnhancedStorageSilo@@AEAAJPEBGPEAPEAEPEAKK@Z; CEnhancedStorageSilo::GetRegistryProperty(ushort const *,uchar * *,ulong *,ulong)
0x1800030b7  mov     ebx, eax
0x1800030b9  test    eax, eax
0x1800030bb  js      short loc_1800030E0
0x1800030bd  mov     rcx, [rsp+0E8h+Block]; Block
0x1800030c2  cmp     [rsp+0E8h+var_8C], 4
0x1800030c7  jnz     short loc_1800030D9
0x1800030c9  test    byte ptr [rcx], 1
0x1800030cc  jnz     short loc_1800030D9
0x1800030ce  mov     dword ptr [r15+27Ch], 1
0x1800030d9  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800030de  jmp     short loc_1800030ED
0x1800030e0  mov     dword ptr [r15+27Ch], 1
0x1800030eb  mov     ebx, esi
0x1800030ed  mov     rax, [r12+8]
0x1800030f2  mov     [rsp+0E8h+var_88], rax
0x1800030f7  cmp     rax, [r12+10h]
0x1800030fc  jb      short loc_18000310E
0x1800030fe  lea     rdx, [rax+1]
0x180003102  mov     rcx, r12
0x180003105  call    ?GrowBuffer@?$CAtlArray@PEAV?$CComObject@VCEnhancedStorageSilo@@@ATL@@V?$CElementTraits@PEAV?$CComObject@VCEnhancedStorageSilo@@@ATL@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CComObject<CEnhancedStorageSilo> *,ATL::CElementTraits<ATL::CComObject<CEnhancedStorageSilo> *>>::GrowBuffer(unsigned __int64)
0x18000310a  test    al, al
0x18000310c  jz      short loc_18000312F
0x18000310e  mov     rax, [r12]
0x180003112  mov     rcx, [rsp+0E8h+var_88]
0x180003117  mov     [rax+rcx*8], rdi
0x18000311b  inc     qword ptr [r12+8]
0x180003120  mov     edi, [rsp+0E8h+var_94]
0x180003124  inc     edi
0x180003126  mov     eax, [rsp+0E8h+var_70]
0x18000312a  jmp     loc_180002FE5
0x18000312f  mov     ecx, 8007000Eh; int
0x180003134  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000313a  mov     rax, [rdi]
0x18000313d  mov     rax, [rax+10h]
0x180003141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003146  lea     rax, WPP_GLOBAL_Control
0x18000314d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003154  cmp     rcx, rax
0x180003157  jz      loc_180003438
0x18000315d  test    byte ptr [rcx+1Ch], 2
0x180003161  jz      loc_180003438
0x180003167  mov     edx, 10h
0x18000316c  jmp     loc_180002F04
0x180003171  lea     rax, WPP_GLOBAL_Control
0x180003178  mov     rcx, cs:WPP_GLOBAL_Control
0x18000317f  cmp     rcx, rax
0x180003182  jz      loc_180003438
0x180003188  test    byte ptr [rcx+1Ch], 2
0x18000318c  jz      loc_180003438
0x180003192  mov     edx, 0Fh
0x180003197  jmp     loc_180002F04
0x18000319c  lea     rdi, [r15+68h]
0x1800031a0  xor     edx, edx; Val
0x1800031a2  mov     r8d, 20Ah; Size
0x1800031a8  mov     rcx, rdi; void *
0x1800031ab  call    memset_0
0x1800031b0  mov     qword ptr [r15+274h], 0
0x1800031bb  mov     [rsp+0E8h+var_64], 0
0x1800031c7  xorps   xmm0, xmm0
0x1800031ca  xor     eax, eax
0x1800031cc  movups  [rsp+0E8h+OutBuffer], xmm0
0x1800031d4  movups  [rsp+0E8h+var_48], xmm0
0x1800031dc  mov     [rsp+0E8h+var_38], rax
0x1800031e4  mov     [rsp+0E8h+var_68], esi
0x1800031eb  mov     rcx, r14; Block
0x1800031ee  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800031f3  mov     [rsp+0E8h+BytesReturned], esi
0x1800031f7  mov     [rsp+0E8h+lpOverlapped], rsi; lpOverlapped
0x1800031fc  lea     rax, [rsp+0E8h+BytesReturned]
0x180003201  mov     [rsp+0E8h+hTemplateFile], rax; lpBytesReturned
0x180003206  mov     [rsp+0E8h+dwFlagsAndAttributes], 28h ; '('; nOutBufferSize
0x18000320e  lea     rax, [rsp+0E8h+OutBuffer]
0x180003216  mov     qword ptr [rsp+0E8h+dwCreationDisposition], rax; lpOutBuffer
0x18000321b  mov     r9d, 0Ch; nInBufferSize
0x180003221  lea     r8, [rsp+0E8h+var_68]; lpInBuffer
0x180003229  mov     edx, 2D1400h; dwIoControlCode
0x18000322e  mov     r12, [rsp+0E8h+hDevice]
0x180003233  mov     rcx, r12; hDevice
0x180003236  call    cs:__imp_DeviceIoControl
0x18000323c  test    eax, eax
0x18000323e  jnz     short loc_18000328E
0x180003240  call    cs:__imp_GetLastError
0x180003246  mov     ebx, eax
0x180003248  test    eax, eax
0x18000324a  jle     short loc_180003255
0x18000324c  movzx   ebx, ax
0x18000324f  or      ebx, 80070000h
0x180003255  lea     rax, WPP_GLOBAL_Control
0x18000325c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003263  cmp     rcx, rax
0x180003266  jz      short loc_180003286
0x180003268  test    byte ptr [rcx+1Ch], 2
0x18000326c  jz      short loc_180003286
0x18000326e  mov     edx, 11h
0x180003273  mov     r9d, ebx
0x180003276  lea     r8, WPP_86ea56442a363db295b8a4ba3de86fee_Traceguids
0x18000327d  mov     rcx, [rcx+10h]
0x180003281  call    WPP_SF_d
0x180003286  mov     r14, rsi
0x180003289  jmp     loc_180003438
0x18000328e  mov     eax, dword ptr [rsp+0E8h+OutBuffer+4]
0x180003295  mov     [rsp+0E8h+BytesReturned], eax
0x180003299  mov     ecx, eax; unsigned __int64
0x18000329b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800032a0  mov     r14, rax
  ... truncated ...
```
