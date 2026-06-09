# GetFileVersion_0

- ea: `0x18000b3c4`
- end: `0x18000b5e0`
- name: `GetFileVersion_0`
- size: `540`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009af4`
- `0x180024930`
- `0x18002a600`

## callees

- `0x180003070`
- `0x18000b3c4`
- `0x18000b5e8`
- `0x18000d264`
- `0x180028cb8`
- `0x180028ce8`
- `0x18002a7c8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000b488`
- `KERNEL32!GetLastError` at `0x18000b488`
- `KERNEL32!CreateFileW` at `0x18000b44f`
- `KERNEL32!CreateFileW` at `0x18000b44f`
- `KERNEL32!SetLastError` at `0x18000b49d`
- `KERNEL32!SetLastError` at `0x18000b4ae`
- `KERNEL32!SetLastError` at `0x18000b49d`
- `KERNEL32!SetLastError` at `0x18000b4ae`
- `KERNEL32!GetFileSize` at `0x18000b479`
- `KERNEL32!GetFileSize` at `0x18000b479`
- `KERNEL32!CreateFileMappingW` at `0x18000b4cd`
- `KERNEL32!CreateFileMappingW` at `0x18000b4cd`
- `KERNEL32!MapViewOfFile` at `0x18000b507`
- `KERNEL32!MapViewOfFile` at `0x18000b507`

## pseudocode

```c
__int64 __fastcall GetFileVersion_0(const WCHAR *a1, wchar_t *a2, unsigned int a3, unsigned int *a4)
{
  rsize_t v4; // r12
  HANDLE FileW; // rax
  __int64 v9; // rdi
  void *v10; // r15
  unsigned int v11; // ebx
  DWORD FileSize; // esi
  HANDLE FileMappingW; // rax
  unsigned int LastError; // ebx
  unsigned __int8 *v15; // rax
  unsigned __int16 *PERuntimeVersion; // rax
  const wchar_t *v17; // r8
  unsigned int v18; // eax
  HANDLE v19; // [rsp+40h] [rbp-29h] BYREF
  int v20; // [rsp+48h] [rbp-21h]
  unsigned __int8 *v21; // [rsp+50h] [rbp-19h] BYREF
  int v22; // [rsp+58h] [rbp-11h]
  unsigned __int16 *v23; // [rsp+60h] [rbp-9h] BYREF
  int v24; // [rsp+68h] [rbp-1h]
  HANDLE v25; // [rsp+70h] [rbp+7h] BYREF
  int v26; // [rsp+78h] [rbp+Fh]
  DWORD FileSizeHigh; // [rsp+D0h] [rbp+67h] BYREF

  v4 = a3;
  v23 = 0;
  v24 = 0;
  v19 = 0;
  v21 = 0;
  v20 = 1;
  v22 = 0;
  if ( !a1 && !a4 )
  {
    Wrapper<void *,&void DoNothing<void *>(void *),&void VoidUnmapViewOfFile(void *),0,&int CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&void DoNothing<void *>(void *),&void VoidUnmapViewOfFile(void *),0,&int CompareDefault<void *>(void *,void *),2>(&v21);
    Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2>(&v19);
    Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v23);
    return 2147500035LL;
  }
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  v9 = -1;
  v26 = 0;
  v25 = FileW;
  v10 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = HRESULT_FROM_GetLastError();
  }
  else
  {
    v26 = 1;
    FileSizeHigh = 0;
    v11 = -1;
    FileSize = GetFileSize(FileW, &FileSizeHigh);
    if ( FileSize != -1 || !GetLastError() )
    {
      if ( FileSizeHigh )
      {
        SetLastError(8u);
      }
      else
      {
        if ( FileSize == -1 )
          SetLastError(8u);
        v11 = FileSize;
      }
    }
    FileMappingW = CreateFileMappingW(v10, 0, 2u, 0, 0, 0);
    v20 = 0;
    v19 = FileMappingW;
    if ( (FileMappingW == (HANDLE)-1LL || (v20 = 1, FileMappingW))
      && (v15 = (unsigned __int8 *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0), (v21 = v15) != 0) )
    {
      v22 = 1;
      PERuntimeVersion = GetPERuntimeVersion(v15, v11, 0);
      v23 = PERuntimeVersion;
      v17 = PERuntimeVersion;
      if ( PERuntimeVersion )
      {
        v24 = 1;
        do
          ++v9;
        while ( PERuntimeVersion[v9] );
        v18 = v9 + 1;
        if ( a4 )
          *a4 = v18;
        if ( a2 && v18 <= (unsigned int)v4 )
        {
          wcsncpy_s(a2, v4, v17, v18);
          Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2>(&v25);
          Wrapper<void *,&void DoNothing<void *>(void *),&void VoidUnmapViewOfFile(void *),0,&int CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&void DoNothing<void *>(void *),&void VoidUnmapViewOfFile(void *),0,&int CompareDefault<void *>(void *,void *),2>(&v21);
          Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2>(&v19);
          Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v23);
          return 0;
        }
        LastError = -2147024774;
      }
      else
      {
        LastError = -2147024885;
      }
    }
    else
    {
      LastError = -2147024882;
    }
  }
  Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2>(&v25);
  Wrapper<void *,&void DoNothing<void *>(void *),&void VoidUnmapViewOfFile(void *),0,&int CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&void DoNothing<void *>(void *),&void VoidUnmapViewOfFile(void *),0,&int CompareDefault<void *>(void *,void *),2>(&v21);
  Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2>(&v19);
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v23);
  return LastError;
}

```

## disassembly

```asm
0x18000b3c4  push    rbp
0x18000b3c6  push    rbx
0x18000b3c7  push    rsi
0x18000b3c8  push    rdi
0x18000b3c9  push    r12
0x18000b3cb  push    r13
0x18000b3cd  push    r14
0x18000b3cf  push    r15
0x18000b3d1  lea     rbp, [rsp-1Fh]
0x18000b3d6  sub     rsp, 88h
0x18000b3dd  xor     ebx, ebx
0x18000b3df  mov     r12d, r8d
0x18000b3e2  mov     [rbp+57h+var_60], rbx
0x18000b3e6  mov     r14, r9
0x18000b3e9  mov     [rbp+57h+var_58], ebx
0x18000b3ec  mov     r13, rdx
0x18000b3ef  mov     [rbp+57h+var_80], rbx
0x18000b3f3  mov     [rbp+57h+var_70], rbx
0x18000b3f7  lea     esi, [rbx+1]
0x18000b3fa  mov     [rbp+57h+var_78], esi
0x18000b3fd  mov     [rbp+57h+var_68], ebx
0x18000b400  test    rcx, rcx
0x18000b403  jnz     short loc_18000B42F
0x18000b405  test    r9, r9
0x18000b408  jnz     short loc_18000B42F
0x18000b40a  lea     rcx, [rbp+57h+var_70]
0x18000b40e  call    ??1?$Wrapper@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?VoidUnmapViewOfFile@@YAX0@Z$0A@$1??$CompareDefault@PEAX@@YAH00@Z$01@@QEAA@XZ; Wrapper<void *,&DoNothing<void *>(void *),&VoidUnmapViewOfFile(void *),0,&CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&DoNothing<void *>(void *),&VoidUnmapViewOfFile(void *),0,&CompareDefault<void *>(void *,void *),2>(void)
0x18000b413  lea     rcx, [rbp+57h+var_80]
0x18000b417  call    ??1?$Wrapper@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?VoidCloseHandle@@YAX0@Z$0?0$1??$CompareDefault@PEAX@@YAH00@Z$01@@QEAA@XZ; Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2>(void)
0x18000b41c  lea     rcx, [rbp+57h+var_60]
0x18000b420  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x18000b425  mov     eax, 80004003h
0x18000b42a  jmp     loc_18000B5CC
0x18000b42f  mov     [rsp+0C0h+hTemplateFile], rbx; hTemplateFile
0x18000b434  xor     r9d, r9d; lpSecurityAttributes
0x18000b437  mov     [rsp+0C0h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18000b43f  mov     r8d, esi; dwShareMode
0x18000b442  mov     edx, 80000000h; dwDesiredAccess
0x18000b447  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000b44f  call    cs:__imp_CreateFileW
0x18000b455  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000b459  mov     [rbp+57h+var_48], ebx
0x18000b45c  mov     [rbp+57h+var_50], rax
0x18000b460  mov     r15, rax
0x18000b463  cmp     rax, rdi
0x18000b466  jz      loc_18000B59F
0x18000b46c  lea     rdx, [rbp+57h+FileSizeHigh]; lpFileSizeHigh
0x18000b470  mov     [rbp+57h+var_48], esi
0x18000b473  mov     rcx, rax; hFile
0x18000b476  mov     [rbp+57h+FileSizeHigh], ebx
0x18000b479  call    cs:__imp_GetFileSize
0x18000b47f  or      ebx, 0FFFFFFFFh
0x18000b482  mov     esi, eax
0x18000b484  cmp     eax, ebx
0x18000b486  jnz     short loc_18000B492
0x18000b488  call    cs:__imp_GetLastError
0x18000b48e  test    eax, eax
0x18000b490  jnz     short loc_18000B4B6
0x18000b492  cmp     [rbp+57h+FileSizeHigh], 0
0x18000b496  jz      short loc_18000B4A5
0x18000b498  mov     ecx, 8; dwErrCode
0x18000b49d  call    cs:__imp_SetLastError
0x18000b4a3  jmp     short loc_18000B4B6
0x18000b4a5  cmp     esi, ebx
0x18000b4a7  jnz     short loc_18000B4B4
0x18000b4a9  mov     ecx, 8; dwErrCode
0x18000b4ae  call    cs:__imp_SetLastError
0x18000b4b4  mov     ebx, esi
0x18000b4b6  xor     esi, esi
0x18000b4b8  xor     r9d, r9d; dwMaximumSizeHigh
0x18000b4bb  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rsi; lpName
0x18000b4c0  xor     edx, edx; lpFileMappingAttributes
0x18000b4c2  mov     rcx, r15; hFile
0x18000b4c5  mov     [rsp+0C0h+dwCreationDisposition], esi; dwMaximumSizeLow
0x18000b4c9  lea     r8d, [rsi+2]; flProtect
0x18000b4cd  call    cs:__imp_CreateFileMappingW
0x18000b4d3  mov     [rbp+57h+var_78], esi
0x18000b4d6  mov     [rbp+57h+var_80], rax
0x18000b4da  cmp     rax, rdi
0x18000b4dd  jz      short loc_18000B4F5
0x18000b4df  mov     [rbp+57h+var_78], 1
0x18000b4e6  test    rax, rax
0x18000b4e9  jnz     short loc_18000B4F5
0x18000b4eb  mov     ebx, 8007000Eh
0x18000b4f0  jmp     loc_18000B5A6
0x18000b4f5  xor     r9d, r9d; dwFileOffsetLow
0x18000b4f8  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rsi; dwNumberOfBytesToMap
0x18000b4fd  xor     r8d, r8d; dwFileOffsetHigh
0x18000b500  mov     rcx, rax; hFileMappingObject
0x18000b503  lea     edx, [r9+4]; dwDesiredAccess
0x18000b507  call    cs:__imp_MapViewOfFile
0x18000b50d  mov     [rbp+57h+var_70], rax
0x18000b511  test    rax, rax
0x18000b514  jz      short loc_18000B4EB
0x18000b516  xor     r8d, r8d; int
0x18000b519  mov     [rbp+57h+var_68], 1
0x18000b520  mov     edx, ebx; unsigned int
0x18000b522  mov     rcx, rax; unsigned __int8 *
0x18000b525  call    ?GetPERuntimeVersion@@YAPEAGPEAEKH@Z; GetPERuntimeVersion(uchar *,ulong,int)
0x18000b52a  mov     [rbp+57h+var_60], rax
0x18000b52e  mov     r8, rax; Source
0x18000b531  test    rax, rax
0x18000b534  jz      short loc_18000B598
0x18000b536  mov     [rbp+57h+var_58], 1
0x18000b53d  inc     rdi
0x18000b540  cmp     [rax+rdi*2], si
0x18000b544  jnz     short loc_18000B53D
0x18000b546  lea     eax, [rdi+1]
0x18000b549  test    r14, r14
0x18000b54c  jz      short loc_18000B551
0x18000b54e  mov     [r14], eax
0x18000b551  test    r13, r13
0x18000b554  jz      short loc_18000B591
0x18000b556  cmp     eax, r12d
0x18000b559  ja      short loc_18000B591
0x18000b55b  mov     r9d, eax; MaxCount
0x18000b55e  mov     rdx, r12; SizeInWords
0x18000b561  mov     rcx, r13; Destination
0x18000b564  call    wcsncpy_s
0x18000b569  lea     rcx, [rbp+57h+var_50]
0x18000b56d  call    ??1?$Wrapper@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?VoidCloseHandle@@YAX0@Z$0?0$1??$CompareDefault@PEAX@@YAH00@Z$01@@QEAA@XZ; Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2>(void)
0x18000b572  lea     rcx, [rbp+57h+var_70]
0x18000b576  call    ??1?$Wrapper@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?VoidUnmapViewOfFile@@YAX0@Z$0A@$1??$CompareDefault@PEAX@@YAH00@Z$01@@QEAA@XZ; Wrapper<void *,&DoNothing<void *>(void *),&VoidUnmapViewOfFile(void *),0,&CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&DoNothing<void *>(void *),&VoidUnmapViewOfFile(void *),0,&CompareDefault<void *>(void *,void *),2>(void)
0x18000b57b  lea     rcx, [rbp+57h+var_80]
0x18000b57f  call    ??1?$Wrapper@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?VoidCloseHandle@@YAX0@Z$0?0$1??$CompareDefault@PEAX@@YAH00@Z$01@@QEAA@XZ; Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2>(void)
0x18000b584  lea     rcx, [rbp+57h+var_60]
0x18000b588  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x18000b58d  xor     eax, eax
0x18000b58f  jmp     short loc_18000B5CC
0x18000b591  mov     ebx, 8007007Ah
0x18000b596  jmp     short loc_18000B5A6
0x18000b598  mov     ebx, 8007000Bh
0x18000b59d  jmp     short loc_18000B5A6
0x18000b59f  call    ?HRESULT_FROM_GetLastError@@YAJXZ; HRESULT_FROM_GetLastError(void)
0x18000b5a4  mov     ebx, eax
0x18000b5a6  lea     rcx, [rbp+57h+var_50]
0x18000b5aa  call    ??1?$Wrapper@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?VoidCloseHandle@@YAX0@Z$0?0$1??$CompareDefault@PEAX@@YAH00@Z$01@@QEAA@XZ; Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2>(void)
0x18000b5af  lea     rcx, [rbp+57h+var_70]
0x18000b5b3  call    ??1?$Wrapper@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?VoidUnmapViewOfFile@@YAX0@Z$0A@$1??$CompareDefault@PEAX@@YAH00@Z$01@@QEAA@XZ; Wrapper<void *,&DoNothing<void *>(void *),&VoidUnmapViewOfFile(void *),0,&CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&DoNothing<void *>(void *),&VoidUnmapViewOfFile(void *),0,&CompareDefault<void *>(void *,void *),2>(void)
0x18000b5b8  lea     rcx, [rbp+57h+var_80]
0x18000b5bc  call    ??1?$Wrapper@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?VoidCloseHandle@@YAX0@Z$0?0$1??$CompareDefault@PEAX@@YAH00@Z$01@@QEAA@XZ; Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2>::~Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2>(void)
0x18000b5c1  lea     rcx, [rbp+57h+var_60]
0x18000b5c5  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x18000b5ca  mov     eax, ebx
0x18000b5cc  add     rsp, 88h
0x18000b5d3  pop     r15
0x18000b5d5  pop     r14
0x18000b5d7  pop     r13
0x18000b5d9  pop     r12
0x18000b5db  pop     rdi
0x18000b5dc  pop     rsi
0x18000b5dd  pop     rbx
0x18000b5de  pop     rbp
0x18000b5df  retn
```
