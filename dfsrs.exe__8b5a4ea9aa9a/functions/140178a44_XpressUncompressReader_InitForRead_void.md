# XpressUncompressReader::InitForRead(void)

- ea: `0x140178a44`
- end: `0x140178cc7`
- name: `?InitForRead@XpressUncompressReader@@IEAAPEAVFrsStatus@@XZ`
- size: `643`
- prototype: `struct FrsStatus *__fastcall(XpressUncompressReader *__hidden this)`
- caller_count: `7`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14015b648`
- `0x1401787f8`
- `0x140178920`
- `0x140179150`
- `0x140179814`
- `0x140179a20`
- `0x140179cb4`

## callees

- `0x1400036d0`
- `0x1400c2394`
- `0x140178a44`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetFileSizeEx` at `0x140178b45`
- `KERNEL32!GetFileSizeEx` at `0x140178b45`
- `KERNEL32!GetLastError` at `0x140178b63`
- `KERNEL32!GetLastError` at `0x140178b63`
- `KERNEL32!GetCurrentThreadId` at `0x140178aec`
- `KERNEL32!GetCurrentThreadId` at `0x140178b55`
- `KERNEL32!GetCurrentThreadId` at `0x140178b98`
- `KERNEL32!GetCurrentThreadId` at `0x140178bda`
- `KERNEL32!GetCurrentThreadId` at `0x140178aec`
- `KERNEL32!GetCurrentThreadId` at `0x140178b55`
- `KERNEL32!GetCurrentThreadId` at `0x140178b98`
- `KERNEL32!GetCurrentThreadId` at `0x140178bda`

## string_xrefs

- `0x140178a58`: `XpressUncompressReader::InitForRead`

## pseudocode

```c
struct FrsStatus *__fastcall XpressUncompressReader::InitForRead(XpressUncompressReader *this)
{
  __int64 v1; // rdi
  __int64 v3; // rax
  unsigned int *v4; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v6; // rcx
  _QWORD *v7; // rsi
  DWORD v8; // ebx
  DWORD LastError; // eax
  __int64 v10; // rcx
  __int64 v11; // rax
  DWORD v12; // eax
  __int64 v13; // rcx
  DWORD v14; // eax
  __int64 v15; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  _DWORD *v19; // [rsp+70h] [rbp+8h]

  v1 = 0;
  if ( !*((_QWORD *)this + 4632) )
  {
    v17 = 0;
    v7 = (_QWORD *)((char *)this + 37072);
LABEL_14:
    *v7 = v17;
    *((_QWORD *)this + 4617) = 0;
    *((_DWORD *)this + 9236) = 0;
    *((_QWORD *)this + 2) = 1;
    *((_QWORD *)this + 4104) = 0;
    *(_QWORD *)((char *)this + 8236) = 0;
    *((_QWORD *)this + 4619) = 0;
    *((_QWORD *)this + 4620) = 0;
    *((_QWORD *)this + 4629) = 0;
    if ( *((_DWORD *)this + 9271) )
    {
      *((_DWORD *)this + 9270) = 1;
    }
    else
    {
      v18 = *((_QWORD *)this + 4632);
      *((_DWORD *)this + 9270) = 0;
      v4 = (unsigned int *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 40LL))(v18, 0);
      if ( v4 )
        goto LABEL_10;
    }
    *((_DWORD *)this + 9260) = 0;
    *((_DWORD *)this + 9263) = 1;
    return (struct FrsStatus *)v1;
  }
  v19 = operator new(0x30u);
  *(_QWORD *)v19 = &FileReader::`vftable';
  v19[2] = 0;
  *((_QWORD *)v19 + 2) = 0;
  *((_QWORD *)v19 + 4) = -1;
  *((_QWORD *)v19 + 3) = &FileHandle::`vftable';
  v19[10] = 0;
  *((_QWORD *)this + 4633) = v19;
  v3 = FileHandle::OpenStream(
         v19 + 6,
         *(_QWORD *)(*((_QWORD *)this + 4632) + 32LL),
         L":{59828bbb-3f72-4c1b-a420-b51ad66eb5d3}.XPRESS",
         2148532224LL,
         0,
         5);
  v4 = (unsigned int *)v3;
  if ( v3 )
  {
    if ( *(_DWORD *)(v3 + 4) != 2 )
      goto LABEL_10;
    CurrentThreadId = GetCurrentThreadId();
    v4 = (unsigned int *)FrsStatusList::PushNewError(
                           v6,
                           9048,
                           0,
                           3,
                           "base\\fs\\remotefs\\frs\\src\\sync\\xpressstreams.cpp",
                           "XpressUncompressReader::InitForRead",
                           1996,
                           CurrentThreadId,
                           v4);
    if ( v4 )
      goto LABEL_10;
  }
  v7 = (_QWORD *)((char *)this + 37072);
  if ( !GetFileSizeEx(*(HANDLE *)(*((_QWORD *)this + 4633) + 32LL), (PLARGE_INTEGER)this + 4634) )
  {
    v8 = GetCurrentThreadId();
    LastError = GetLastError();
    v11 = FrsStatusList::PushNewError(
            v10,
            LastError,
            0,
            1,
            "base\\fs\\remotefs\\frs\\src\\sync\\xpressstreams.cpp",
            "XpressUncompressReader::InitForRead",
            2009,
            v8,
            0);
    goto LABEL_9;
  }
  if ( (*v7 & 7) == 0 )
  {
    v17 = *v7 >> 3;
    goto LABEL_14;
  }
  *v7 = 0;
  v12 = GetCurrentThreadId();
  v11 = FrsStatusList::PushNewError(
          v13,
          9048,
          0,
          3,
          "base\\fs\\remotefs\\frs\\src\\sync\\xpressstreams.cpp",
          "XpressUncompressReader::InitForRead",
          2015,
          v12,
          0);
LABEL_9:
  v4 = (unsigned int *)v11;
  if ( v11 )
  {
LABEL_10:
    v14 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v15,
                                 v4[1],
                                 v4[2],
                                 *v4,
                                 "base\\fs\\remotefs\\frs\\src\\sync\\xpressstreams.cpp",
                                 "XpressUncompressReader::InitForRead",
                                 2068,
                                 v14,
                                 v4);
  }
  return (struct FrsStatus *)v1;
}

```

## disassembly

```asm
0x140178a44  mov     [rsp+arg_8], rbx
0x140178a49  mov     [rsp+arg_10], rbp
0x140178a4e  push    rsi
0x140178a4f  push    rdi
0x140178a50  push    r14
0x140178a52  sub     rsp, 50h
0x140178a56  xor     edi, edi
0x140178a58  lea     rbp, aXpressuncompre_1; "XpressUncompressReader::InitForRead"
0x140178a5f  lea     r14, aBaseFsRemotefs_43; "base\\fs\\remotefs\\frs\\src\\sync\\xpr"...
0x140178a66  mov     rbx, rcx
0x140178a69  cmp     [rcx+90C0h], rdi
0x140178a70  jz      loc_140178C32
0x140178a76  lea     ecx, [rdi+30h]; Size
0x140178a79  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140178a7e  lea     rcx, ??_7FileReader@@6B@; const FileReader::`vftable'
0x140178a85  mov     [rsp+68h+arg_0], rax
0x140178a8a  lea     rdx, ??_7FileHandle@@6B@; const FileHandle::`vftable'
0x140178a91  mov     dword ptr [rsp+68h+var_40], 5
0x140178a99  mov     r9d, 80100000h
0x140178a9f  mov     dword ptr [rsp+68h+var_48], edi
0x140178aa3  mov     [rax], rcx
0x140178aa6  lea     r8, a59828bbb3f724c; ":{59828bbb-3f72-4c1b-a420-b51ad66eb5d3}"...
0x140178aad  mov     [rax+8], edi
0x140178ab0  lea     rcx, [rax+18h]
0x140178ab4  mov     [rax+10h], rdi
0x140178ab8  or      qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x140178abd  mov     [rcx], rdx
0x140178ac0  mov     [rcx+10h], edi
0x140178ac3  mov     [rbx+90C8h], rax
0x140178aca  mov     rax, [rbx+90C0h]
0x140178ad1  mov     rdx, [rax+20h]
0x140178ad5  call    ?OpenStream@FileHandle@@QEAAPEAVFrsStatus@@PEAXPEBGKW4STREAMOPTIONS@1@K@Z; FileHandle::OpenStream(void *,ushort const *,ulong,FileHandle::STREAMOPTIONS,ulong)
0x140178ada  mov     rsi, rax
0x140178add  test    rax, rax
0x140178ae0  jz      short loc_140178B30
0x140178ae2  cmp     dword ptr [rax+4], 2
0x140178ae6  jnz     loc_140178BDA
0x140178aec  call    cs:__imp_GetCurrentThreadId
0x140178af3  nop     dword ptr [rax+rax+00h]
0x140178af8  mov     [rsp+68h+var_28], rsi
0x140178afd  lea     r9d, [rdi+3]
0x140178b01  mov     [rsp+68h+var_30], eax
0x140178b05  xor     r8d, r8d
0x140178b08  mov     [rsp+68h+var_38], 7CCh
0x140178b10  mov     edx, 2358h
0x140178b15  mov     [rsp+68h+var_40], rbp
0x140178b1a  mov     [rsp+68h+var_48], r14
0x140178b1f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140178b24  mov     rsi, rax
0x140178b27  test    rax, rax
0x140178b2a  jnz     loc_140178BDA
0x140178b30  mov     rax, [rbx+90C8h]
0x140178b37  lea     rsi, [rbx+90D0h]
0x140178b3e  mov     rdx, rsi; lpFileSize
0x140178b41  mov     rcx, [rax+20h]; hFile
0x140178b45  call    cs:__imp_GetFileSizeEx
0x140178b4c  nop     dword ptr [rax+rax+00h]
0x140178b51  test    eax, eax
0x140178b53  jnz     short loc_140178B8A
0x140178b55  call    cs:__imp_GetCurrentThreadId
0x140178b5c  nop     dword ptr [rax+rax+00h]
0x140178b61  mov     ebx, eax
0x140178b63  call    cs:__imp_GetLastError
0x140178b6a  nop     dword ptr [rax+rax+00h]
0x140178b6f  mov     [rsp+68h+var_28], rdi
0x140178b74  mov     r9d, 1
0x140178b7a  mov     [rsp+68h+var_30], ebx
0x140178b7e  mov     edx, eax
0x140178b80  mov     [rsp+68h+var_38], 7D9h
0x140178b88  jmp     short loc_140178BC0
0x140178b8a  mov     rax, [rsi]
0x140178b8d  test    al, 7
0x140178b8f  jz      loc_140178C2C
0x140178b95  mov     [rsi], rdi
0x140178b98  call    cs:__imp_GetCurrentThreadId
0x140178b9f  nop     dword ptr [rax+rax+00h]
0x140178ba4  mov     [rsp+68h+var_28], rdi
0x140178ba9  mov     r9d, 3
0x140178baf  mov     [rsp+68h+var_30], eax
0x140178bb3  mov     edx, 2358h
0x140178bb8  mov     [rsp+68h+var_38], 7DFh
0x140178bc0  mov     [rsp+68h+var_40], rbp
0x140178bc5  xor     r8d, r8d
0x140178bc8  mov     [rsp+68h+var_48], r14
0x140178bcd  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140178bd2  mov     rsi, rax
0x140178bd5  test    rax, rax
0x140178bd8  jz      short loc_140178C13
0x140178bda  call    cs:__imp_GetCurrentThreadId
0x140178be1  nop     dword ptr [rax+rax+00h]
0x140178be6  mov     r9d, [rsi]
0x140178be9  mov     r8d, [rsi+8]
0x140178bed  mov     edx, [rsi+4]
0x140178bf0  mov     [rsp+68h+var_28], rsi
0x140178bf5  mov     [rsp+68h+var_30], eax
0x140178bf9  mov     [rsp+68h+var_38], 814h
0x140178c01  mov     [rsp+68h+var_40], rbp
0x140178c06  mov     [rsp+68h+var_48], r14
0x140178c0b  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140178c10  mov     rdi, rax
0x140178c13  lea     r11, [rsp+68h+var_18]
0x140178c18  mov     rax, rdi
0x140178c1b  mov     rbx, [r11+28h]
0x140178c1f  mov     rbp, [r11+30h]
0x140178c23  mov     rsp, r11
0x140178c26  pop     r14
0x140178c28  pop     rdi
0x140178c29  pop     rsi
0x140178c2a  retn
0x140178c2c  shr     rax, 3
0x140178c30  jmp     short loc_140178C3C
0x140178c32  mov     rax, rdi
0x140178c35  lea     rsi, [rcx+90D0h]
0x140178c3c  mov     [rsi], rax
0x140178c3f  mov     [rbx+9048h], rdi
0x140178c46  mov     [rbx+9050h], edi
0x140178c4c  mov     qword ptr [rbx+10h], 1
0x140178c54  mov     [rbx+8040h], rdi
0x140178c5b  mov     [rbx+202Ch], rdi
0x140178c62  mov     [rbx+9058h], rdi
0x140178c69  mov     [rbx+9060h], rdi
0x140178c70  mov     [rbx+90A8h], rdi
0x140178c77  cmp     [rbx+90DCh], edi
0x140178c7d  jz      short loc_140178C8B
0x140178c7f  mov     dword ptr [rbx+90D8h], 1
0x140178c89  jmp     short loc_140178CB2
0x140178c8b  mov     rcx, [rbx+90C0h]
0x140178c92  xor     edx, edx
0x140178c94  mov     [rbx+90D8h], edi
0x140178c9a  mov     rax, [rcx]
0x140178c9d  mov     rax, [rax+28h]
0x140178ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140178ca6  mov     rsi, rax
0x140178ca9  test    rax, rax
0x140178cac  jnz     loc_140178BDA
0x140178cb2  mov     [rbx+90B0h], edi
0x140178cb8  mov     dword ptr [rbx+90BCh], 1
0x140178cc2  jmp     loc_140178C13
```
