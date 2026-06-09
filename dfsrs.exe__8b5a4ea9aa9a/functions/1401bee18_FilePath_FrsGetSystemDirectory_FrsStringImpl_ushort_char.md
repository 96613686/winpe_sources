# FilePath::FrsGetSystemDirectory(FrsStringImpl<ushort,char> &)

- ea: `0x1401bee18`
- end: `0x1401befb0`
- name: `?FrsGetSystemDirectory@FilePath@@SAPEAVFrsStatus@@AEAV?$FrsStringImpl@GD@@@Z`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1401fea68`

## callees

- `0x1400255c8`
- `0x140028eec`
- `0x14002c548`
- `0x1401af7b0`
- `0x1401b9494`
- `0x1401bee18`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x1401bee3c`
- `KERNEL32!GetSystemDirectoryW` at `0x1401beed6`
- `KERNEL32!GetSystemDirectoryW` at `0x1401bee3c`
- `KERNEL32!GetSystemDirectoryW` at `0x1401beed6`
- `KERNEL32!GetLastError` at `0x1401bee6a`
- `KERNEL32!GetLastError` at `0x1401beef8`
- `KERNEL32!GetLastError` at `0x1401bee6a`
- `KERNEL32!GetLastError` at `0x1401beef8`
- `KERNEL32!GetCurrentThreadId` at `0x1401bee5c`
- `KERNEL32!GetCurrentThreadId` at `0x1401beeea`
- `KERNEL32!GetCurrentThreadId` at `0x1401bef37`
- `KERNEL32!GetCurrentThreadId` at `0x1401bee5c`
- `KERNEL32!GetCurrentThreadId` at `0x1401beeea`
- `KERNEL32!GetCurrentThreadId` at `0x1401bef37`

## string_xrefs

- `0x1401bee4a`: `FilePath::FrsGetSystemDirectory`
- `0x1401bee51`: `base\fs\remotefs\frs\src\util\filepath.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FilePath::FrsGetSystemDirectory(__int64 a1)
{
  __int64 v2; // rdi
  UINT SystemDirectoryW; // eax
  unsigned __int64 v4; // rbp
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  __int64 v7; // rcx
  unsigned int *v8; // rbx
  WCHAR *v9; // r14
  DWORD v10; // ebx
  DWORD v11; // eax
  __int64 v12; // rcx
  DWORD v13; // eax
  __int64 v14; // rcx
  WCHAR *v16; // [rsp+88h] [rbp+10h] BYREF

  v2 = 0;
  v16 = 0;
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v4 = SystemDirectoryW;
  if ( !SystemDirectoryW )
  {
    CurrentThreadId = GetCurrentThreadId();
    LastError = GetLastError();
    v8 = (unsigned int *)FrsStatusList::PushNewError(
                           v7,
                           LastError,
                           0,
                           1,
                           "base\\fs\\remotefs\\frs\\src\\util\\filepath.cpp",
                           "FilePath::FrsGetSystemDirectory",
                           580,
                           CurrentThreadId,
                           0);
    if ( v8 )
      goto LABEL_5;
  }
  v9 = (WCHAR *)operator_new(saturated_mul(v4, 2u));
  v16 = v9;
  if ( GetSystemDirectoryW(v9, v4)
    || (v10 = GetCurrentThreadId(),
        v11 = GetLastError(),
        (v8 = (unsigned int *)FrsStatusList::PushNewError(
                                v12,
                                v11,
                                0,
                                1,
                                "base\\fs\\remotefs\\frs\\src\\util\\filepath.cpp",
                                "FilePath::FrsGetSystemDirectory",
                                590,
                                v10,
                                0)) == 0) )
  {
    FrsStringImpl<unsigned short,char>::SetEmpty(a1);
    FrsStringImpl<unsigned short,char>::Append(a1, v9);
  }
  else
  {
LABEL_5:
    v13 = GetCurrentThreadId();
    v2 = FrsStatusList::PushNewError(
           v14,
           v8[1],
           v8[2],
           *v8,
           "base\\fs\\remotefs\\frs\\src\\util\\filepath.cpp",
           "FilePath::FrsGetSystemDirectory",
           599,
           v13,
           v8);
  }
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v16);
  return v2;
}

```

## disassembly

```asm
0x1401bee18  mov     rax, rsp
0x1401bee1b  mov     [rax+8], rbx
0x1401bee1f  mov     [rax+18h], rbp
0x1401bee23  push    rsi
0x1401bee24  push    rdi
0x1401bee25  push    r12
0x1401bee27  push    r14
0x1401bee29  push    r15
0x1401bee2b  sub     rsp, 50h
0x1401bee2f  mov     rsi, rcx
0x1401bee32  xor     edi, edi
0x1401bee34  mov     [rax+10h], rdi
0x1401bee38  xor     edx, edx; uSize
0x1401bee3a  xor     ecx, ecx; lpBuffer
0x1401bee3c  call    cs:__imp_GetSystemDirectoryW
0x1401bee43  nop     dword ptr [rax+rax+00h]
0x1401bee48  mov     ebp, eax
0x1401bee4a  lea     r15, aFilepathFrsget; "FilePath::FrsGetSystemDirectory"
0x1401bee51  lea     r12, aBaseFsRemotefs_87; "base\\fs\\remotefs\\frs\\src\\util\\fil"...
0x1401bee58  test    eax, eax
0x1401bee5a  jnz     short loc_1401BEEAB
0x1401bee5c  call    cs:__imp_GetCurrentThreadId
0x1401bee63  nop     dword ptr [rax+rax+00h]
0x1401bee68  mov     ebx, eax
0x1401bee6a  call    cs:__imp_GetLastError
0x1401bee71  nop     dword ptr [rax+rax+00h]
0x1401bee76  mov     [rsp+78h+var_38], rdi
0x1401bee7b  mov     [rsp+78h+var_40], ebx
0x1401bee7f  mov     [rsp+78h+var_48], 244h
0x1401bee87  mov     [rsp+78h+var_50], r15
0x1401bee8c  mov     [rsp+78h+var_58], r12
0x1401bee91  lea     r9d, [rdi+1]
0x1401bee95  xor     r8d, r8d
0x1401bee98  mov     edx, eax
0x1401bee9a  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401bee9f  mov     rbx, rax
0x1401beea2  test    rax, rax
0x1401beea5  jnz     loc_1401BEF37
0x1401beeab  mov     eax, 2
0x1401beeb0  mul     rbp
0x1401beeb3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1401beeba  cmovo   rax, rcx
0x1401beebe  mov     rcx, rax; unsigned __int64
0x1401beec1  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1401beec6  mov     r14, rax
0x1401beec9  mov     [rsp+78h+arg_8], rax
0x1401beed1  mov     edx, ebp; uSize
0x1401beed3  mov     rcx, rax; lpBuffer
0x1401beed6  call    cs:__imp_GetSystemDirectoryW
0x1401beedd  nop     dword ptr [rax+rax+00h]
0x1401beee2  test    eax, eax
0x1401beee4  jnz     loc_1401BEF72
0x1401beeea  call    cs:__imp_GetCurrentThreadId
0x1401beef1  nop     dword ptr [rax+rax+00h]
0x1401beef6  mov     ebx, eax
0x1401beef8  call    cs:__imp_GetLastError
0x1401beeff  nop     dword ptr [rax+rax+00h]
0x1401bef04  mov     [rsp+78h+var_38], rdi
0x1401bef09  mov     [rsp+78h+var_40], ebx
0x1401bef0d  mov     [rsp+78h+var_48], 24Eh
0x1401bef15  mov     [rsp+78h+var_50], r15
0x1401bef1a  mov     [rsp+78h+var_58], r12
0x1401bef1f  mov     r9d, 1
0x1401bef25  xor     r8d, r8d
0x1401bef28  mov     edx, eax
0x1401bef2a  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401bef2f  mov     rbx, rax
0x1401bef32  test    rax, rax
0x1401bef35  jz      short loc_1401BEF72
0x1401bef37  call    cs:__imp_GetCurrentThreadId
0x1401bef3e  nop     dword ptr [rax+rax+00h]
0x1401bef43  mov     [rsp+78h+var_38], rbx
0x1401bef48  mov     [rsp+78h+var_40], eax
0x1401bef4c  mov     [rsp+78h+var_48], 257h
0x1401bef54  mov     [rsp+78h+var_50], r15
0x1401bef59  mov     [rsp+78h+var_58], r12
0x1401bef5e  mov     r9d, [rbx]
0x1401bef61  mov     r8d, [rbx+8]
0x1401bef65  mov     edx, [rbx+4]
0x1401bef68  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401bef6d  mov     rdi, rax
0x1401bef70  jmp     short loc_1401BEF86
0x1401bef72  mov     rcx, rsi
0x1401bef75  call    ?SetEmpty@?$FrsStringImpl@GD@@QEAAXXZ; FrsStringImpl<ushort,char>::SetEmpty(void)
0x1401bef7a  mov     rdx, r14
0x1401bef7d  mov     rcx, rsi
0x1401bef80  call    ?Append@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Append(ushort const *)
0x1401bef85  nop
0x1401bef86  lea     rcx, [rsp+78h+arg_8]
0x1401bef8e  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1401bef93  mov     rax, rdi
0x1401bef96  lea     r11, [rsp+78h+var_28]
0x1401bef9b  mov     rbx, [r11+30h]
0x1401bef9f  mov     rbp, [r11+40h]
0x1401befa3  mov     rsp, r11
0x1401befa6  pop     r15
0x1401befa8  pop     r14
0x1401befaa  pop     r12
0x1401befac  pop     rdi
0x1401befad  pop     rsi
0x1401befae  retn
```
