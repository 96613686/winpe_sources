# CONFIG_PATH_MAPPER::GetUserToken(_PATH_CACHE_NODE *,void * *,PARSE_ERROR_INFO *)

- ea: `0x180016ba0`
- end: `0x180016e22`
- name: `?GetUserToken@CONFIG_PATH_MAPPER@@AEAAJPEAU_PATH_CACHE_NODE@@PEAPEAXPEAVPARSE_ERROR_INFO@@@Z`
- size: `642`
- prototype: `int(CONFIG_PATH_MAPPER *__hidden this, struct _PATH_CACHE_NODE *, void **, struct PARSE_ERROR_INFO *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180053068`

## callees

- `0x1800100d0`
- `0x180010468`
- `0x1800169a0`
- `0x180016ba0`
- `0x18001c250`
- `0x18001c290`
- `0x180044df0`
- `0x18004bc68`
- `0x180052540`
- `0x180052614`
- `0x1800562fc`
- `0x180056c80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c25`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180016de8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180016de8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016db5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016dc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016db5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180016dc6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180016d99`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180016d99`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180016c50`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180016c50`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180016d84`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180016d84`

## string_xrefs

- `0x180016cbb`: `applicationHost.config`
- `0x180016e03`: `CONFIG_PATH_MAPPER::GetUserToken`

## pseudocode

```c
int __fastcall CONFIG_PATH_MAPPER::GetUserToken(
        CONFIG_PATH_MAPPER *this,
        struct _PATH_CACHE_NODE *a2,
        void **a3,
        struct PARSE_ERROR_INFO *a4)
{
  CONFIG_VDIR **v4; // rax
  __int64 v9; // rcx
  int result; // eax
  CONFIG_VDIR_TABLE *v11; // r12
  int v12; // edi
  __int64 v13; // rax
  const unsigned __int16 *v14; // rdx
  CONFIG_VDIR_TABLE *v15; // rax
  CONFIG_VDIR_TABLE *v16; // rax
  CONFIG_VDIR *v17; // rbx
  unsigned __int16 *Str; // rax
  HANDLE CurrentProcess; // rdi
  void *v20; // rbx
  HANDLE v21; // rax
  int v22; // edx
  struct CONFIG_FILE *v23; // [rsp+40h] [rbp-38h] BYREF
  CReaderWriterLock3 *v24; // [rsp+48h] [rbp-30h]
  __int64 v25; // [rsp+88h] [rbp+10h] BYREF

  v4 = (CONFIG_VDIR **)((char *)a2 + 48);
  if ( (*((_BYTE *)a2 + 76) & 0x20) != 0 && *v4 || (v9 = *((_QWORD *)a2 + 5)) == 0 )
  {
    v11 = (CONFIG_VDIR_TABLE *)*((_QWORD *)this + 25);
    v12 = 0;
    v23 = 0;
    if ( v11 )
      goto LABEL_7;
    v24 = (CONFIG_PATH_MAPPER *)((char *)this + 208);
    CReaderWriterLock3::WriteLock((CONFIG_PATH_MAPPER *)((char *)this + 208));
    v11 = (CONFIG_VDIR_TABLE *)*((_QWORD *)this + 25);
    if ( !v11 )
    {
      LODWORD(v25) = PATH_CACHE::GetFile(
                       (PATH_CACHE *)(*((_QWORD *)this + 21) + 24LL),
                       L"MACHINE/WEBROOT/APPHOST",
                       *(_DWORD *)(*((_QWORD *)this + 21) + 56LL),
                       &v23);
      v12 = v25;
      if ( (int)v25 >= 0 )
      {
        if ( !v23 )
        {
          v13 = *((_QWORD *)this + 21);
          v14 = L"MACHINE/WEBROOT/APPHOST";
          v25 = 0;
          if ( **(char **)(v13 + 16) >= 0 )
            v14 = L"applicationHost.config";
          SMALL_STRU::Copy((struct PARSE_ERROR_INFO *)((char *)a4 + 32), v14);
          v12 = -2147024894;
          PARSE_ERROR_INFO::SetErrorInfo(a4, 2147942402LL, 3, 3221228229LL, &v25, 0, 0, 0, (_DWORD)v23, v24);
          goto LABEL_28;
        }
        CONFIG_FILE::QueryInitialized(v23, (int *)&v25, a4);
        v12 = v25;
        if ( (int)v25 >= 0 )
        {
          v15 = (CONFIG_VDIR_TABLE *)operator new(0xA8u);
          if ( v15 )
          {
            v16 = CONFIG_VDIR_TABLE::CONFIG_VDIR_TABLE(v15);
            v11 = v16;
            if ( v16 )
            {
              v12 = CONFIG_VDIR_TABLE::Initialize(v16, v23);
              if ( v12 >= 0 )
              {
                *((_QWORD *)this + 25) = v11;
              }
              else
              {
                CONFIG_VDIR_TABLE::~CONFIG_VDIR_TABLE(v11);
                operator delete(v11);
                v11 = 0;
              }
              goto LABEL_28;
            }
          }
          else
          {
            v11 = 0;
          }
          v12 = -2147024888;
        }
      }
    }
LABEL_28:
    CReaderWriterLock3::WriteUnlock(v24);
    v4 = (CONFIG_VDIR **)((char *)a2 + 48);
LABEL_7:
    if ( v12 < 0 )
      return v12;
    v17 = *v4;
    Str = STRU::QueryStr(v11);
    return CONFIG_VDIR::GetUserToken(v17, a3, Str, a4);
  }
  if ( *(_QWORD *)(v9 + 32) )
  {
    CurrentProcess = GetCurrentProcess();
    v20 = *(void **)(*((_QWORD *)a2 + 5) + 32LL);
    v21 = GetCurrentProcess();
    if ( DuplicateHandle(v21, v20, CurrentProcess, a3, 0, 0, 2u) )
    {
      if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 1) != 0 )
        McTemplateU0zpp_EtwEventWriteTransfer(
          (unsigned int)*a3,
          v22,
          (unsigned int)L"CONFIG_PATH_MAPPER::GetUserToken",
          *(_QWORD *)(*((_QWORD *)a2 + 5) + 32LL),
          (char)*a3);
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  else
  {
    *a3 = 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180016ba0  mov     [rsp+arg_10], rbx
0x180016ba5  push    rbp
0x180016ba6  push    rsi
0x180016ba7  push    rdi
0x180016ba8  push    r14
0x180016baa  push    r15
0x180016bac  sub     rsp, 50h
0x180016bb0  test    byte ptr [rdx+4Ch], 20h
0x180016bb4  lea     rax, [rdx+30h]
0x180016bb8  mov     r15, r9
0x180016bbb  mov     r14, r8
0x180016bbe  mov     rsi, rdx
0x180016bc1  mov     rbx, rcx
0x180016bc4  jnz     short loc_180016C39
0x180016bc6  mov     rcx, [rdx+28h]
0x180016bca  test    rcx, rcx
0x180016bcd  jz      short loc_180016BF4
0x180016bcf  xor     ebp, ebp
0x180016bd1  cmp     [rcx+20h], rbp
0x180016bd5  jnz     loc_180016DB5
0x180016bdb  mov     [r8], rbp
0x180016bde  mov     eax, ebp
0x180016be0  mov     rbx, [rsp+78h+arg_10]
0x180016be8  add     rsp, 50h
0x180016bec  pop     r15
0x180016bee  pop     r14
0x180016bf0  pop     rdi
0x180016bf1  pop     rsi
0x180016bf2  pop     rbp
0x180016bf3  retn
0x180016bf4  xor     ebp, ebp
0x180016bf6  mov     [rsp+78h+arg_0], r12
0x180016bfe  mov     r12, [rbx+0C8h]
0x180016c05  mov     edi, ebp
0x180016c07  mov     [rsp+78h+var_38], rbp
0x180016c0c  test    r12, r12
0x180016c0f  jz      short loc_180016C41
0x180016c11  test    edi, edi
0x180016c13  jns     loc_180016D93
0x180016c19  mov     eax, edi
0x180016c1b  mov     r12, [rsp+78h+arg_0]
0x180016c23  jmp     short loc_180016BE0
0x180016c25  call    cs:__imp_GetLastError
0x180016c2b  test    eax, eax
0x180016c2d  jle     short loc_180016BE0
0x180016c2f  movzx   eax, ax
0x180016c32  or      eax, 80070000h
0x180016c37  jmp     short loc_180016BE0
0x180016c39  cmp     qword ptr [rax], 0
0x180016c3d  jnz     short loc_180016BF4
0x180016c3f  jmp     short loc_180016BC6
0x180016c41  lea     rax, [rbx+0D0h]
0x180016c48  mov     rcx, rax
0x180016c4b  mov     [rsp+78h+var_30], rax
0x180016c50  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180016c56  mov     r12, [rbx+0C8h]
0x180016c5d  test    r12, r12
0x180016c60  jnz     loc_180016D7F
0x180016c66  mov     rcx, [rbx+0A8h]
0x180016c6d  lea     r9, [rsp+78h+var_38]; struct CONFIG_FILE **
0x180016c72  add     rcx, 18h; this
0x180016c76  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180016c7d  mov     r8d, [rcx+20h]; unsigned int
0x180016c81  call    ?GetFile@PATH_CACHE@@QEAAJPEBGKPEAPEAVCONFIG_FILE@@@Z; PATH_CACHE::GetFile(ushort const *,ulong,CONFIG_FILE * *)
0x180016c86  mov     dword ptr [rsp+78h+arg_8], eax
0x180016c8d  mov     edi, eax
0x180016c8f  test    eax, eax
0x180016c91  js      loc_180016D7F
0x180016c97  cmp     [rsp+78h+var_38], rbp
0x180016c9c  jnz     short loc_180016D07
0x180016c9e  mov     rax, [rbx+0A8h]
0x180016ca5  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180016cac  mov     [rsp+78h+arg_8], rbp
0x180016cb4  mov     rcx, [rax+10h]
0x180016cb8  test    byte ptr [rcx], 80h
0x180016cbb  lea     rcx, aApplicationhos_0; "applicationHost.config"
0x180016cc2  cmovz   rdx, rcx; unsigned __int16 *
0x180016cc6  lea     rcx, [r15+20h]; this
0x180016cca  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x180016ccf  mov     [rsp+78h+var_40], rbp
0x180016cd4  lea     rax, [rsp+78h+arg_8]
0x180016cdc  mov     qword ptr [rsp+78h+dwOptions], rbp
0x180016ce1  mov     edi, 80070002h
0x180016ce6  mov     [rsp+78h+bInheritHandle], ebp
0x180016cea  mov     edx, edi
0x180016cec  mov     r9d, 0C0000AC5h
0x180016cf2  mov     qword ptr [rsp+78h+dwDesiredAccess], rax
0x180016cf7  mov     r8d, 3
0x180016cfd  mov     rcx, r15
0x180016d00  call    ?SetErrorInfo@PARSE_ERROR_INFO@@QEAAJJW4PARSE_ERROR_TYPE@@KQEAPEBDKPEAVIConfigDom@@PEAVIConfigDomNode@@@Z; PARSE_ERROR_INFO::SetErrorInfo(long,PARSE_ERROR_TYPE,ulong,char const * * const,ulong,IConfigDom *,IConfigDomNode *)
0x180016d05  jmp     short loc_180016D7F
0x180016d07  mov     rcx, [rsp+78h+var_38]; this
0x180016d0c  lea     rdx, [rsp+78h+arg_8]; int *
0x180016d14  mov     r8, r15; struct PARSE_ERROR_INFO *
0x180016d17  call    ?QueryInitialized@CONFIG_FILE@@QEAAHPEAJPEAVPARSE_ERROR_INFO@@@Z; CONFIG_FILE::QueryInitialized(long *,PARSE_ERROR_INFO *)
0x180016d1c  mov     edi, dword ptr [rsp+78h+arg_8]
0x180016d23  test    edi, edi
0x180016d25  js      short loc_180016D7F
0x180016d27  mov     ecx, 0A8h; Size
0x180016d2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016d31  test    rax, rax
0x180016d34  jz      short loc_180016D77
0x180016d36  mov     rcx, rax; this
0x180016d39  call    ??0CONFIG_VDIR_TABLE@@QEAA@XZ; CONFIG_VDIR_TABLE::CONFIG_VDIR_TABLE(void)
0x180016d3e  mov     r12, rax
0x180016d41  test    rax, rax
0x180016d44  jz      short loc_180016D7A
0x180016d46  mov     rdx, [rsp+78h+var_38]; struct CONFIG_FILE *
0x180016d4b  mov     rcx, rax; this
0x180016d4e  call    ?Initialize@CONFIG_VDIR_TABLE@@QEAAJPEAVCONFIG_FILE@@@Z; CONFIG_VDIR_TABLE::Initialize(CONFIG_FILE *)
0x180016d53  mov     edi, eax
0x180016d55  test    eax, eax
0x180016d57  jns     short loc_180016D6E
0x180016d59  mov     rcx, r12; this
0x180016d5c  call    ??1CONFIG_VDIR_TABLE@@QEAA@XZ; CONFIG_VDIR_TABLE::~CONFIG_VDIR_TABLE(void)
0x180016d61  mov     rcx, r12; Block
0x180016d64  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016d69  mov     r12, rbp
0x180016d6c  jmp     short loc_180016D7F
0x180016d6e  mov     [rbx+0C8h], r12
0x180016d75  jmp     short loc_180016D7F
0x180016d77  mov     r12, rbp
0x180016d7a  mov     edi, 80070008h
0x180016d7f  mov     rcx, [rsp+78h+var_30]
0x180016d84  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180016d8a  lea     rax, [rsi+30h]
0x180016d8e  jmp     loc_180016C11
0x180016d93  mov     rbx, [rax]
0x180016d96  mov     rcx, r12
0x180016d99  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180016d9f  mov     r9, r15; struct PARSE_ERROR_INFO *
0x180016da2  mov     rdx, r14; void **
0x180016da5  mov     r8, rax; unsigned __int16 *
0x180016da8  mov     rcx, rbx; this
0x180016dab  call    ?GetUserToken@CONFIG_VDIR@@QEAAJPEAPEAXPEBGPEAVPARSE_ERROR_INFO@@@Z; CONFIG_VDIR::GetUserToken(void * *,ushort const *,PARSE_ERROR_INFO *)
0x180016db0  jmp     loc_180016C1B
0x180016db5  call    cs:__imp_GetCurrentProcess
0x180016dbb  mov     rdi, rax
0x180016dbe  mov     rax, [rsi+28h]
0x180016dc2  mov     rbx, [rax+20h]
0x180016dc6  call    cs:__imp_GetCurrentProcess
0x180016dcc  mov     [rsp+78h+dwOptions], 2; dwOptions
0x180016dd4  mov     r9, r14; lpTargetHandle
0x180016dd7  mov     rcx, rax; hSourceProcessHandle
0x180016dda  mov     [rsp+78h+bInheritHandle], ebp; bInheritHandle
0x180016dde  mov     r8, rdi; hTargetProcessHandle
0x180016de1  mov     [rsp+78h+dwDesiredAccess], ebp; dwDesiredAccess
0x180016de5  mov     rdx, rbx; hSourceHandle
0x180016de8  call    cs:__imp_DuplicateHandle
0x180016dee  test    eax, eax
0x180016df0  jz      loc_180016C25
0x180016df6  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 1
0x180016dfd  jz      short loc_180016E1B
0x180016dff  mov     r9, [rsi+28h]
0x180016e03  lea     r8, aConfigPathMapp; "CONFIG_PATH_MAPPER::GetUserToken"
0x180016e0a  mov     rcx, [r14]
0x180016e0d  mov     qword ptr [rsp+78h+dwDesiredAccess], rcx
0x180016e12  mov     r9, [r9+20h]
0x180016e16  call    McTemplateU0zpp_EtwEventWriteTransfer
0x180016e1b  mov     eax, ebp
0x180016e1d  jmp     loc_180016BE0
```
