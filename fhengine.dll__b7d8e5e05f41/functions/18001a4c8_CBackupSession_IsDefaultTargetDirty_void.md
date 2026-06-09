# CBackupSession::IsDefaultTargetDirty(void)

- ea: `0x18001a4c8`
- end: `0x18001a6a7`
- name: `?IsDefaultTargetDirty@CBackupSession@@AEAAHXZ`
- size: `479`
- prototype: `__int64 __fastcall(CBackupSession *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180021240`

## callees

- `0x180002c24`
- `0x1800062d0`
- `0x180007818`
- `0x180009258`
- `0x18000a1ec`
- `0x18000bca8`
- `0x180012278`
- `0x18001a4c8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001a59c`
- `KERNEL32!GetLastError` at `0x18001a637`
- `KERNEL32!GetLastError` at `0x18001a59c`
- `KERNEL32!GetLastError` at `0x18001a637`
- `KERNEL32!CloseHandle` at `0x18001a686`
- `KERNEL32!CloseHandle` at `0x18001a686`
- `KERNEL32!CreateFileW` at `0x18001a58d`
- `KERNEL32!CreateFileW` at `0x18001a58d`
- `KERNEL32!DeviceIoControl` at `0x18001a62b`
- `KERNEL32!DeviceIoControl` at `0x18001a62b`

## pseudocode

```c
__int64 __fastcall CBackupSession::IsDefaultTargetDirty(CBackupSession *this)
{
  unsigned int v2; // ebx
  unsigned __int16 v3; // ax
  HANDLE FileW; // rdi
  char LastError; // al
  signed int v6; // eax
  int v8[10]; // [rsp+40h] [rbp-28h] BYREF
  int OutBuffer; // [rsp+78h] [rbp+10h] BYREF
  DWORD BytesReturned; // [rsp+80h] [rbp+18h] BYREF
  LPCWSTR lpFileName; // [rsp+88h] [rbp+20h] BYREF

  v2 = 0;
  OutBuffer = 0;
  BytesReturned = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpFileName);
  if ( *((_DWORD *)this + 29) == 4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        431,
        &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        *((_QWORD *)this + 9));
    goto LABEL_17;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v3 = ATL::CSimpleStringT<unsigned short,0>::operator[]((char *)this + 72, 0);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      (__int64)&lpFileName,
      (__int64)L"\\\\?\\%c:",
      v3);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)v8) )
    {
      if ( v8[0] < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            432,
            &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
            (unsigned int)v8[0]);
        v2 = 0;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18001A555);
        goto LABEL_17;
      }
      v2 = 0;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18001A55E);
    }
  }
  FileW = CreateFileW(lpFileName, 0x20u, 3u, 0, 3u, 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        433,
        (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        (_DWORD)lpFileName,
        LastError);
  }
  else
  {
    v2 = DeviceIoControl(FileW, 0x90078u, 0, 0, &OutBuffer, 4u, &BytesReturned, 0);
    if ( v2 )
    {
      v2 = OutBuffer & 1;
    }
    else
    {
      v6 = GetLastError();
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          434,
          &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          (unsigned int)v6);
    }
    CloseHandle(FileW);
  }
LABEL_17:
  ATL::CStringData::Release((ATL::CStringData *)(lpFileName - 12));
  return v2;
}

```

## disassembly

```asm
0x18001a4c8  mov     rax, rsp
0x18001a4cb  push    rbx
0x18001a4cc  push    rdi
0x18001a4cd  sub     rsp, 58h
0x18001a4d1  mov     rdi, rcx
0x18001a4d4  xor     ebx, ebx
0x18001a4d6  mov     [rsp+68h+arg_0], ebx
0x18001a4da  mov     [rax+10h], ebx
0x18001a4dd  mov     [rax+18h], ebx
0x18001a4e0  lea     rcx, [rax+20h]
0x18001a4e4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001a4e9  nop
0x18001a4ea  cmp     dword ptr [rdi+74h], 4
0x18001a4ee  jnz     short loc_18001A52F
0x18001a4f0  lea     rdx, WPP_GLOBAL_Control
0x18001a4f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a4fe  cmp     rcx, rdx
0x18001a501  jz      loc_18001A68D
0x18001a507  test    byte ptr [rcx+1Ch], 8
0x18001a50b  jz      loc_18001A68D
0x18001a511  mov     edx, 1AFh
0x18001a516  mov     r9, [rdi+48h]
0x18001a51a  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001a521  mov     rcx, [rcx+10h]
0x18001a525  call    WPP_SF_S
0x18001a52a  jmp     loc_18001A68D
0x18001a52f  lea     rcx, [rdi+48h]
0x18001a533  xor     edx, edx
0x18001a535  call    ??A?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::operator[](int)
0x18001a53a  movzx   r8d, ax
0x18001a53e  lea     rdx, aC; "\\\\?\\%c:"
0x18001a545  lea     rcx, [rsp+68h+lpFileName]
0x18001a54d  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001a552  nop
0x18001a553  jmp     short loc_18001A562
0x18001a555  mov     ebx, [rsp+68h+arg_0]
0x18001a559  jmp     loc_18001A68D
0x18001a55e  mov     ebx, [rsp+68h+arg_0]
0x18001a562  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18001a56b  mov     [rsp+68h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18001a573  mov     r8d, 3; dwShareMode
0x18001a579  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001a57e  xor     r9d, r9d; lpSecurityAttributes
0x18001a581  lea     edx, [r8+1Dh]; dwDesiredAccess
0x18001a585  mov     rcx, [rsp+68h+lpFileName]; lpFileName
0x18001a58d  call    cs:__imp_CreateFileW
0x18001a593  mov     rdi, rax
0x18001a596  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a59a  jnz     short loc_18001A5F5
0x18001a59c  call    cs:__imp_GetLastError
0x18001a5a2  test    eax, eax
0x18001a5a4  jle     short loc_18001A5AE
0x18001a5a6  movzx   eax, ax
0x18001a5a9  or      eax, 80070000h
0x18001a5ae  lea     rdx, WPP_GLOBAL_Control
0x18001a5b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a5bc  cmp     rcx, rdx
0x18001a5bf  jz      loc_18001A68D
0x18001a5c5  test    byte ptr [rcx+1Ch], 1
0x18001a5c9  jz      loc_18001A68D
0x18001a5cf  mov     edx, 1B1h
0x18001a5d4  mov     [rsp+68h+dwCreationDisposition], eax
0x18001a5d8  mov     r9, [rsp+68h+lpFileName]
0x18001a5e0  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001a5e7  mov     rcx, [rcx+10h]
0x18001a5eb  call    WPP_SF_Sd
0x18001a5f0  jmp     loc_18001A68D
0x18001a5f5  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18001a5fe  lea     rax, [rsp+68h+BytesReturned]
0x18001a606  mov     [rsp+68h+hTemplateFile], rax; lpBytesReturned
0x18001a60b  mov     [rsp+68h+dwFlagsAndAttributes], 4; nOutBufferSize
0x18001a613  lea     rax, [rsp+68h+OutBuffer]
0x18001a618  mov     qword ptr [rsp+68h+dwCreationDisposition], rax; lpOutBuffer
0x18001a61d  xor     r9d, r9d; nInBufferSize
0x18001a620  xor     r8d, r8d; lpInBuffer
0x18001a623  mov     edx, 90078h; dwIoControlCode
0x18001a628  mov     rcx, rdi; hDevice
0x18001a62b  call    cs:__imp_DeviceIoControl
0x18001a631  mov     ebx, eax
0x18001a633  test    eax, eax
0x18001a635  jnz     short loc_18001A67C
0x18001a637  call    cs:__imp_GetLastError
0x18001a63d  test    eax, eax
0x18001a63f  jle     short loc_18001A649
0x18001a641  movzx   eax, ax
0x18001a644  or      eax, 80070000h
0x18001a649  lea     rdx, WPP_GLOBAL_Control
0x18001a650  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a657  cmp     rcx, rdx
0x18001a65a  jz      short loc_18001A683
0x18001a65c  test    byte ptr [rcx+1Ch], 1
0x18001a660  jz      short loc_18001A683
0x18001a662  mov     edx, 1B2h
0x18001a667  mov     r9d, eax
0x18001a66a  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001a671  mov     rcx, [rcx+10h]
0x18001a675  call    WPP_SF_d
0x18001a67a  jmp     short loc_18001A683
0x18001a67c  mov     ebx, [rsp+68h+OutBuffer]
0x18001a680  and     ebx, 1
0x18001a683  mov     rcx, rdi; hObject
0x18001a686  call    cs:__imp_CloseHandle
0x18001a68c  nop
0x18001a68d  mov     rcx, [rsp+68h+lpFileName]
0x18001a695  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001a699  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001a69e  mov     eax, ebx
0x18001a6a0  add     rsp, 58h
0x18001a6a4  pop     rdi
0x18001a6a5  pop     rbx
0x18001a6a6  retn
```
