# util_WriteConfigurationChangedFile(ushort const *)

- ea: `0x14003817c`
- end: `0x14003827d`
- name: `?util_WriteConfigurationChangedFile@@YAJPEBG@Z`
- size: `257`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000ccfc`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140008120`
- `0x140033ab0`
- `0x1400344fc`
- `0x14003817c`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14003820e`
- `KERNEL32!CreateFileW` at `0x14003820e`
- `KERNEL32!CloseHandle` at `0x140038234`
- `KERNEL32!CloseHandle` at `0x140038234`

## string_xrefs

- `0x1400381d0`: `extensions.configurationchanged`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall util_WriteConfigurationChangedFile(const unsigned __int16 *a1)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  LPCWSTR v4; // rbx
  HANDLE FileW; // rax
  unsigned int Error; // edi
  void *v7; // rcx
  LPCWSTR lpFileName; // [rsp+40h] [rbp-28h] BYREF
  __int128 v9; // [rsp+48h] [rbp-20h]

  if ( !a1 )
    return 2147942487LL;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  lpFileName = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                       + 24);
  v9 = 0;
  ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Combine(
    &lpFileName,
    a1,
    L"extensions.configurationchanged");
  v4 = lpFileName;
  FileW = CreateFileW(lpFileName, 0x40000000u, 1u, 0, 2u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    Error = ATL::AtlHresultFromLastError();
    FileW = 0;
    v7 = (void *)v9;
  }
  else
  {
    v7 = FileW;
    Error = 0;
  }
  if ( FileW )
    CloseHandle(v7);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 - 3) + 8LL))(*((_QWORD *)v4 - 3));
  }
  return Error;
}

```

## disassembly

```asm
0x14003817c  mov     [rsp+arg_8], rbx
0x140038181  push    rdi
0x140038182  sub     rsp, 60h
0x140038186  mov     rax, cs:__security_cookie
0x14003818d  xor     rax, rsp
0x140038190  mov     [rsp+68h+var_10], rax
0x140038195  mov     rbx, rcx
0x140038198  test    rcx, rcx
0x14003819b  jnz     short loc_1400381A7
0x14003819d  mov     eax, 80070057h
0x1400381a2  jmp     loc_14003825A
0x1400381a7  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x1400381ac  mov     rcx, rax
0x1400381af  test    rax, rax
0x1400381b2  jz      loc_140038272
0x1400381b8  mov     rax, [rax]
0x1400381bb  call    qword ptr [rax+18h]
0x1400381be  add     rax, 18h
0x1400381c2  mov     [rsp+68h+lpFileName], rax
0x1400381c7  xorps   xmm1, xmm1
0x1400381ca  movdqu  [rsp+68h+var_20], xmm1
0x1400381d0  lea     r8, aExtensionsConf; "extensions.configurationchanged"
0x1400381d7  mov     rdx, rbx
0x1400381da  lea     rcx, [rsp+68h+lpFileName]
0x1400381df  call    ?Combine@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAXPEBG0@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Combine(ushort const *,ushort const *)
0x1400381e4  and     [rsp+68h+var_38], 0
0x1400381ea  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400381f2  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x1400381fa  xor     r9d, r9d; lpSecurityAttributes
0x1400381fd  mov     edx, 40000000h; dwDesiredAccess
0x140038202  lea     r8d, [r9+1]; dwShareMode
0x140038206  mov     rbx, [rsp+68h+lpFileName]
0x14003820b  mov     rcx, rbx; lpFileName
0x14003820e  call    cs:__imp_CreateFileW
0x140038214  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140038218  jnz     short loc_14003822A
0x14003821a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14003821f  mov     edi, eax
0x140038221  xor     eax, eax
0x140038223  mov     rcx, qword ptr [rsp+68h+var_20]
0x140038228  jmp     short loc_14003822F
0x14003822a  mov     rcx, rax; hObject
0x14003822d  xor     edi, edi
0x14003822f  test    rax, rax
0x140038232  jz      short loc_14003823B
0x140038234  call    cs:__imp_CloseHandle
0x14003823a  nop
0x14003823b  lea     rdx, [rbx-18h]
0x14003823f  or      eax, 0FFFFFFFFh
0x140038242  lock xadd [rdx+10h], eax
0x140038247  sub     eax, 1
0x14003824a  jg      short loc_140038258
0x14003824c  lfence
0x14003824f  mov     rcx, [rdx]
0x140038252  mov     rax, [rcx]
0x140038255  call    qword ptr [rax+8]
0x140038258  mov     eax, edi
0x14003825a  mov     rcx, [rsp+68h+var_10]
0x14003825f  xor     rcx, rsp; StackCookie
0x140038262  call    __security_check_cookie
0x140038267  mov     rbx, [rsp+68h+arg_8]
0x14003826c  add     rsp, 60h
0x140038270  pop     rdi
0x140038271  retn
0x140038272  mov     ecx, 80004005h; int
0x140038277  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
