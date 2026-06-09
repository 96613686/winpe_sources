# VolumeIdTable::ExtractVolumePathFromFilePath(FrsStringImpl<ushort,char> const &,FrsStringImpl<ushort,char> &)

- ea: `0x14003ff6c`
- end: `0x14004015d`
- name: `?ExtractVolumePathFromFilePath@VolumeIdTable@@SAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@AEAV3@@Z`
- size: `497`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14003fb40`
- `0x140040a18`

## callees

- `0x14000ee94`
- `0x140010680`
- `0x1400248ac`
- `0x14002c548`
- `0x14003ff6c`
- `0x1401af7b0`
- `0x1401b9494`
- `0x1401bebec`
- `0x1401bec48`

## import_xrefs

- `KERNEL32!GetVolumePathNameW` at `0x140040079`
- `KERNEL32!GetVolumePathNameW` at `0x140040079`
- `KERNEL32!GetLastError` at `0x1400400a4`
- `KERNEL32!GetLastError` at `0x1400400a4`
- `KERNEL32!GetCurrentThreadId` at `0x14003ffbd`
- `KERNEL32!GetCurrentThreadId` at `0x140040096`
- `KERNEL32!GetCurrentThreadId` at `0x1400400f0`
- `KERNEL32!GetCurrentThreadId` at `0x14003ffbd`
- `KERNEL32!GetCurrentThreadId` at `0x140040096`
- `KERNEL32!GetCurrentThreadId` at `0x1400400f0`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x140040011`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x140040011`

## string_xrefs

- `0x14003ffa8`: `base\fs\remotefs\frs\src\config\context.cpp`
- `0x14003ffa1`: `VolumeIdTable::ExtractVolumePathFromFilePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall VolumeIdTable::ExtractVolumePathFromFilePath(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  unsigned int *v4; // rsi
  __int64 v5; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v7; // rcx
  WCHAR *v8; // rbx
  DWORD v9; // ebx
  DWORD LastError; // eax
  __int64 v11; // rcx
  DWORD v12; // eax
  __int64 v13; // rcx
  void **v15; // [rsp+50h] [rbp-28h] BYREF
  __int64 v16; // [rsp+58h] [rbp-20h] BYREF
  WCHAR *v17; // [rsp+80h] [rbp+8h] BYREF

  FilePath::FilePath((FilePath *)&v15, (const unsigned __int16 *)(*(_QWORD *)a1 + 18LL));
  v3 = 0;
  v4 = 0;
  v5 = v16;
  if ( !*(_DWORD *)(v16 + 8) || *(_DWORD *)(v16 + 8) > 0x7FFFu )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = (unsigned int *)FrsStatusList::PushNewError(
                           v7,
                           87,
                           0,
                           1,
                           "base\\fs\\remotefs\\frs\\src\\config\\context.cpp",
                           "VolumeIdTable::ExtractVolumePathFromFilePath",
                           1599,
                           CurrentThreadId,
                           0);
    if ( v4 )
    {
LABEL_13:
      v12 = GetCurrentThreadId();
      v3 = FrsStatusList::PushNewError(
             v13,
             v4[1],
             v4[2],
             *v4,
             "base\\fs\\remotefs\\frs\\src\\config\\context.cpp",
             "VolumeIdTable::ExtractVolumePathFromFilePath",
             1640,
             v12,
             v4);
      goto LABEL_14;
    }
    v5 = v16;
  }
  if ( *(_DWORD *)(v5 + 8) == 2
    && (unsigned int)_o_iswalpha(*(unsigned __int16 *)(v5 + 18))
    && *(_WORD *)(v5 + 20) == 58 )
  {
    FilePath::AppendTrailingBackslash((FilePath *)&v15);
    FilePath::Append((FilePath *)&v15, L".");
  }
  v17 = 0;
  v8 = (WCHAR *)operator_new(0x10000u);
  v17 = v8;
  *v8 = 0;
  if ( GetVolumePathNameW((LPCWSTR)(v16 + 18), v8, 0x8000u) )
  {
    FrsStringImpl<unsigned short,char>::Set(a2, v8);
  }
  else
  {
    v9 = GetCurrentThreadId();
    LastError = GetLastError();
    v4 = (unsigned int *)FrsStatusList::PushNewError(
                           v11,
                           LastError,
                           0,
                           1,
                           "base\\fs\\remotefs\\frs\\src\\config\\context.cpp",
                           "VolumeIdTable::ExtractVolumePathFromFilePath",
                           1636,
                           v9,
                           0);
  }
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v17);
  if ( v4 )
    goto LABEL_13;
LABEL_14:
  v15 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v16);
  return v3;
}

```

## disassembly

```asm
0x14003ff6c  mov     rax, rsp
0x14003ff6f  mov     [rax+10h], rbx
0x14003ff73  mov     [rax+18h], rbp
0x14003ff77  mov     [rax+20h], rsi
0x14003ff7b  push    rdi
0x14003ff7c  push    r14
0x14003ff7e  push    r15
0x14003ff80  sub     rsp, 60h
0x14003ff84  mov     rbp, rdx
0x14003ff87  mov     rdx, [rcx]
0x14003ff8a  add     rdx, 12h; unsigned __int16 *
0x14003ff8e  lea     rcx, [rax-28h]; this
0x14003ff92  call    ??0FilePath@@QEAA@PEBG@Z; FilePath::FilePath(ushort const *)
0x14003ff97  nop
0x14003ff98  xor     edi, edi
0x14003ff9a  mov     esi, edi
0x14003ff9c  mov     rbx, [rsp+78h+var_20]
0x14003ffa1  lea     r14, aVolumeidtableE_0; "VolumeIdTable::ExtractVolumePathFromFil"...
0x14003ffa8  lea     r15, aBaseFsRemotefs_98; "base\\fs\\remotefs\\frs\\src\\config\\c"...
0x14003ffaf  cmp     [rbx+8], edi
0x14003ffb2  jz      short loc_14003FFBD
0x14003ffb4  cmp     dword ptr [rbx+8], 7FFFh
0x14003ffbb  jbe     short loc_140040007
0x14003ffbd  call    cs:__imp_GetCurrentThreadId
0x14003ffc4  nop     dword ptr [rax+rax+00h]
0x14003ffc9  mov     [rsp+78h+var_38], rdi
0x14003ffce  mov     [rsp+78h+var_40], eax
0x14003ffd2  mov     [rsp+78h+var_48], 63Fh
0x14003ffda  mov     [rsp+78h+var_50], r14
0x14003ffdf  mov     [rsp+78h+var_58], r15
0x14003ffe4  mov     r9d, 1
0x14003ffea  xor     r8d, r8d
0x14003ffed  lea     edx, [r9+56h]
0x14003fff1  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14003fff6  mov     rsi, rax
0x14003fff9  test    rax, rax
0x14003fffc  jnz     loc_1400400F0
0x140040002  mov     rbx, [rsp+78h+var_20]
0x140040007  cmp     dword ptr [rbx+8], 2
0x14004000b  jnz     short loc_140040047
0x14004000d  movzx   ecx, word ptr [rbx+12h]
0x140040011  call    cs:__imp__o_iswalpha
0x140040018  nop     dword ptr [rax+rax+00h]
0x14004001d  test    eax, eax
0x14004001f  jz      short loc_140040047
0x140040021  mov     eax, 3Ah ; ':'
0x140040026  cmp     ax, [rbx+14h]
0x14004002a  jnz     short loc_140040047
0x14004002c  lea     rcx, [rsp+78h+var_28]; this
0x140040031  call    ?AppendTrailingBackslash@FilePath@@QEAAXXZ; FilePath::AppendTrailingBackslash(void)
0x140040036  lea     rdx, asc_140245310; "."
0x14004003d  lea     rcx, [rsp+78h+var_28]; this
0x140040042  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x140040047  mov     [rsp+78h+arg_0], rdi
0x14004004f  mov     ecx, 10000h; unsigned __int64
0x140040054  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x140040059  mov     rbx, rax
0x14004005c  mov     [rsp+78h+arg_0], rax
0x140040064  mov     [rax], di
0x140040067  mov     rcx, [rsp+78h+var_20]
0x14004006c  add     rcx, 12h; lpszFileName
0x140040070  mov     r8d, 8000h; cchBufferLength
0x140040076  mov     rdx, rax; lpszVolumePathName
0x140040079  call    cs:__imp_GetVolumePathNameW
0x140040080  nop     dword ptr [rax+rax+00h]
0x140040085  test    eax, eax
0x140040087  jz      short loc_140040096
0x140040089  mov     rdx, rbx
0x14004008c  mov     rcx, rbp
0x14004008f  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x140040094  jmp     short loc_1400400DE
0x140040096  call    cs:__imp_GetCurrentThreadId
0x14004009d  nop     dword ptr [rax+rax+00h]
0x1400400a2  mov     ebx, eax
0x1400400a4  call    cs:__imp_GetLastError
0x1400400ab  nop     dword ptr [rax+rax+00h]
0x1400400b0  mov     [rsp+78h+var_38], rdi
0x1400400b5  mov     [rsp+78h+var_40], ebx
0x1400400b9  mov     [rsp+78h+var_48], 664h
0x1400400c1  mov     [rsp+78h+var_50], r14
0x1400400c6  mov     [rsp+78h+var_58], r15
0x1400400cb  mov     r9d, 1
0x1400400d1  xor     r8d, r8d
0x1400400d4  mov     edx, eax
0x1400400d6  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400400db  mov     rsi, rax
0x1400400de  lea     rcx, [rsp+78h+arg_0]
0x1400400e6  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1400400eb  test    rsi, rsi
0x1400400ee  jz      short loc_140040129
0x1400400f0  call    cs:__imp_GetCurrentThreadId
0x1400400f7  nop     dword ptr [rax+rax+00h]
0x1400400fc  mov     [rsp+78h+var_38], rsi
0x140040101  mov     [rsp+78h+var_40], eax
0x140040105  mov     [rsp+78h+var_48], 668h
0x14004010d  mov     [rsp+78h+var_50], r14
0x140040112  mov     [rsp+78h+var_58], r15
0x140040117  mov     r9d, [rsi]
0x14004011a  mov     r8d, [rsi+8]
0x14004011e  mov     edx, [rsi+4]
0x140040121  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140040126  mov     rdi, rax
0x140040129  lea     rax, ??_7FilePath@@6B@; const FilePath::`vftable'
0x140040130  mov     [rsp+78h+var_28], rax
0x140040135  lea     rcx, [rsp+78h+var_20]
0x14004013a  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x14004013f  mov     rax, rdi
0x140040142  lea     r11, [rsp+78h+var_18]
0x140040147  mov     rbx, [r11+28h]
0x14004014b  mov     rbp, [r11+30h]
0x14004014f  mov     rsi, [r11+38h]
0x140040153  mov     rsp, r11
0x140040156  pop     r15
0x140040158  pop     r14
0x14004015a  pop     rdi
0x14004015b  retn
```
