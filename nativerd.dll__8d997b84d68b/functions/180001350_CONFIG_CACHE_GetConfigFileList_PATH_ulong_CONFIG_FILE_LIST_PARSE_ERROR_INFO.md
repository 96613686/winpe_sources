# CONFIG_CACHE::GetConfigFileList(PATH *,ulong,CONFIG_FILE_LIST *,PARSE_ERROR_INFO *)

- ea: `0x180001350`
- end: `0x1800013fe`
- name: `?GetConfigFileList@CONFIG_CACHE@@QEAAJPEAVPATH@@KPEAVCONFIG_FILE_LIST@@PEAVPARSE_ERROR_INFO@@@Z`
- size: `174`
- prototype: `__int64 __usercall@<rax>(CONFIG_CACHE *__hidden this@<rcx>, struct PATH *@<rdx>, unsigned int@<r8d>, struct CONFIG_FILE_LIST *@<r9>, struct PARSE_ERROR_INFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003ada4`

## callees

- `0x180001350`
- `0x180002b20`
- `0x180003440`
- `0x180003840`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x1800013e9`
- `iisutil!WriteRefTraceLog` at `0x1800013f6`
- `iisutil!WriteRefTraceLog` at `0x1800013e9`
- `iisutil!WriteRefTraceLog` at `0x1800013f6`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000136e`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000136e`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800013c0`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800013c0`

## pseudocode

```c
__int64 __fastcall CONFIG_CACHE::GetConfigFileList(
        CONFIG_CACHE *this,
        struct PATH *a2,
        unsigned int a3,
        struct CONFIG_FILE_LIST *a4,
        struct PARSE_ERROR_INFO *a5)
{
  __int64 v9; // rcx
  int v10; // edi
  __int64 v12; // rcx

  CReaderWriterLock3::ReadLock((CONFIG_CACHE *)((char *)this + 344));
  v9 = *((_QWORD *)this + 98);
  if ( v9 )
    WriteRefTraceLog(v9, 0, this);
  v10 = CONFIG_CACHE::ProcessConfigPath(this, a2, a3, a4, a5);
  if ( v10 >= 0 )
  {
    CReaderWriterLock3::ReadUnlock((CONFIG_CACHE *)((char *)this + 344));
    v12 = *((_QWORD *)this + 98);
    if ( v12 )
      WriteRefTraceLog(v12, 0, this);
    return CONFIG_CACHE::ManageCacheSize(this);
  }
  else
  {
    CONFIG_CACHE::ReadUnlock(this);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x180001350  push    rbx
0x180001352  push    rbp
0x180001353  push    rsi
0x180001354  push    rdi
0x180001355  push    r14
0x180001357  sub     rsp, 30h
0x18000135b  mov     rbx, rcx
0x18000135e  mov     rdi, r9
0x180001361  add     rcx, 158h
0x180001368  mov     ebp, r8d
0x18000136b  mov     r14, rdx
0x18000136e  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180001374  mov     rcx, [rbx+310h]
0x18000137b  test    rcx, rcx
0x18000137e  jnz     short loc_1800013E4
0x180001380  mov     rax, [rsp+58h+arg_20]
0x180001388  mov     r9, rdi; struct CONFIG_FILE_LIST *
0x18000138b  mov     r8d, ebp; unsigned int
0x18000138e  mov     [rsp+58h+var_38], rax; struct PARSE_ERROR_INFO *
0x180001393  mov     rdx, r14; struct PATH *
0x180001396  mov     rcx, rbx; this
0x180001399  call    ?ProcessConfigPath@CONFIG_CACHE@@AEAAJPEAVPATH@@KPEAVCONFIG_FILE_LIST@@PEAVPARSE_ERROR_INFO@@@Z; CONFIG_CACHE::ProcessConfigPath(PATH *,ulong,CONFIG_FILE_LIST *,PARSE_ERROR_INFO *)
0x18000139e  mov     edi, eax
0x1800013a0  test    eax, eax
0x1800013a2  jns     short loc_1800013B9
0x1800013a4  mov     rcx, rbx; this
0x1800013a7  call    ?ReadUnlock@CONFIG_CACHE@@AEAAXXZ; CONFIG_CACHE::ReadUnlock(void)
0x1800013ac  mov     eax, edi
0x1800013ae  add     rsp, 30h
0x1800013b2  pop     r14
0x1800013b4  pop     rdi
0x1800013b5  pop     rsi
0x1800013b6  pop     rbp
0x1800013b7  pop     rbx
0x1800013b8  retn
0x1800013b9  lea     rcx, [rbx+158h]
0x1800013c0  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800013c6  mov     rcx, [rbx+310h]
0x1800013cd  test    rcx, rcx
0x1800013d0  jnz     short loc_1800013F1
0x1800013d2  mov     rcx, rbx; this
0x1800013d5  add     rsp, 30h
0x1800013d9  pop     r14
0x1800013db  pop     rdi
0x1800013dc  pop     rsi
0x1800013dd  pop     rbp
0x1800013de  pop     rbx
0x1800013df  jmp     ?ManageCacheSize@CONFIG_CACHE@@AEAAJXZ; CONFIG_CACHE::ManageCacheSize(void)
0x1800013e4  mov     r8, rbx
0x1800013e7  xor     edx, edx
0x1800013e9  call    cs:__imp_WriteRefTraceLog
0x1800013ef  jmp     short loc_180001380
0x1800013f1  mov     r8, rbx
0x1800013f4  xor     edx, edx
0x1800013f6  call    cs:__imp_WriteRefTraceLog
0x1800013fc  jmp     short loc_1800013D2
```
