# CMsmqVssWriter::DeleteStorageFiles(void)

- ea: `0x18008fe00`
- end: `0x18008ffb9`
- name: `?DeleteStorageFiles@CMsmqVssWriter@@AEAAJXZ`
- size: `441`
- prototype: `__int64 __fastcall(CMsmqVssWriter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x18009331c`

## callees

- `0x18002c61c`
- `0x18008fe00`
- `0x180092180`
- `0x18009a590`

## import_xrefs

- `msvcrt!free` at `0x18008fec6`
- `msvcrt!free` at `0x18008fee9`
- `msvcrt!free` at `0x18008ff8a`
- `msvcrt!free` at `0x18008ff98`
- `msvcrt!free` at `0x18008fec6`
- `msvcrt!free` at `0x18008fee9`
- `msvcrt!free` at `0x18008ff8a`
- `msvcrt!free` at `0x18008ff98`

## string_xrefs

- `0x18008fe1d`: `StorePersistentPath`
- `0x18008ff23`: `StoreXactLogPath`
- `0x18008fe28`: `StoreJournalPath`
- `0x18008fe33`: `StoreLogPath`
- `0x18008fed7`: `writer/mqwriter`
- `0x18008ff78`: `writer/mqwriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMsmqVssWriter::DeleteStorageFiles(CMsmqVssWriter *this)
{
  __int64 i; // rdi
  __int64 v3; // rax
  void *v4; // rsi
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v8; // rbx
  wchar_t *v9; // rdi
  int v10; // eax
  unsigned int v11; // esi
  void *v12; // [rsp+20h] [rbp-29h]
  _QWORD v13[3]; // [rsp+30h] [rbp-19h]
  wchar_t *v14; // [rsp+48h] [rbp-1h]
  const wchar_t *v15; // [rsp+50h] [rbp+7h]
  const wchar_t *v16; // [rsp+58h] [rbp+Fh]
  int v17; // [rsp+60h] [rbp+17h] BYREF
  __int64 v18; // [rsp+68h] [rbp+1Fh]
  const wchar_t *v19; // [rsp+70h] [rbp+27h]
  int v20; // [rsp+78h] [rbp+2Fh]
  __int64 v21; // [rsp+80h] [rbp+37h]
  void *Block; // [rsp+B8h] [rbp+6Fh] BYREF

  v13[0] = L"StorePersistentPath";
  v13[1] = L"StoreJournalPath";
  v13[2] = L"StoreLogPath";
  v14 = L"p*.mq";
  v15 = L"j*.mq";
  v16 = L"l*.mq";
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v3 = *((_QWORD *)this + 4);
    Block = 0;
    if ( (unsigned int)i >= 3 )
      break;
    v17 = 1;
    v18 = v3;
    v19 = (const wchar_t *)v13[i];
    v20 = 0;
    v21 = -2147483646;
    CmQueryValue((const struct RegEntry *)&v17, (wchar_t **)&Block);
    v4 = Block;
    v5 = CMsmqVssWriter::PrepareDirectoryForBackupRestore(this, (const wchar_t *)Block, (&v14)[i], 0, v12);
    v6 = v5;
    if ( v5 < 0 )
    {
      LogMsgHR(v5, (wchar_t *)L"writer/mqwriter", 0x118u);
      free(v4);
      return v6;
    }
    free(v4);
  }
  v14 = L"qmlog";
  v15 = L"mqinseqs.*";
  v16 = L"mqtrans.*";
  v17 = 1;
  v18 = v3;
  v19 = L"StoreXactLogPath";
  v20 = 0;
  v21 = -2147483646;
  CmQueryValue((const struct RegEntry *)&v17, (wchar_t **)&Block);
  v8 = 0;
  v9 = (wchar_t *)Block;
  while ( (unsigned int)v8 < 3 )
  {
    v10 = CMsmqVssWriter::PrepareDirectoryForBackupRestore(this, v9, (&v14)[v8], 0, v12);
    v11 = v10;
    if ( v10 < 0 )
    {
      LogMsgHR(v10, (wchar_t *)L"writer/mqwriter", 0x140u);
      free(v9);
      return v11;
    }
    v8 = (unsigned int)(v8 + 1);
  }
  free(v9);
  return 0;
}

```

## disassembly

```asm
0x18008fe00  mov     [rsp-8+arg_0], rbx
0x18008fe05  mov     [rsp-8+arg_10], rsi
0x18008fe0a  push    rbp
0x18008fe0b  push    rdi
0x18008fe0c  push    r14
0x18008fe0e  lea     rbp, [rsp-47h]
0x18008fe13  sub     rsp, 90h
0x18008fe1a  mov     r14, rcx
0x18008fe1d  lea     rax, aStorepersisten; "StorePersistentPath"
0x18008fe24  mov     [rbp+57h+var_70], rax
0x18008fe28  lea     rax, aStorejournalpa; "StoreJournalPath"
0x18008fe2f  mov     [rbp+57h+var_68], rax
0x18008fe33  lea     rax, aStorelogpath; "StoreLogPath"
0x18008fe3a  mov     [rbp+57h+var_60], rax
0x18008fe3e  lea     rax, aPMq; "p*.mq"
0x18008fe45  mov     [rbp+57h+var_58], rax
0x18008fe49  lea     rax, aJMq; "j*.mq"
0x18008fe50  mov     [rbp+57h+var_50], rax
0x18008fe54  lea     rax, aLMq; "l*.mq"
0x18008fe5b  mov     [rbp+57h+var_48], rax
0x18008fe5f  xor     edi, edi
0x18008fe61  mov     rax, [r14+20h]
0x18008fe65  mov     [rbp+57h+Block], 0
0x18008fe6d  cmp     edi, 3
0x18008fe70  jnb     loc_18008FEF7
0x18008fe76  mov     [rbp+57h+var_40], 1
0x18008fe7d  mov     [rbp+57h+var_38], rax
0x18008fe81  mov     rax, [rbp+rdi*8+57h+var_70]
0x18008fe86  mov     [rbp+57h+var_30], rax
0x18008fe8a  mov     [rbp+57h+var_28], 0
0x18008fe91  mov     [rbp+57h+var_20], 0FFFFFFFF80000002h
0x18008fe99  lea     rdx, [rbp+57h+Block]; wchar_t **
0x18008fe9d  lea     rcx, [rbp+57h+var_40]; struct RegEntry *
0x18008fea1  call    ?CmQueryValue@@YAXAEBVRegEntry@@PEAPEA_W@Z; CmQueryValue(RegEntry const &,wchar_t * *)
0x18008fea6  xor     r9d, r9d; int
0x18008fea9  mov     r8, [rbp+rdi*8+57h+var_58]; wchar_t *
0x18008feae  mov     rsi, [rbp+57h+Block]
0x18008feb2  mov     rdx, rsi; wchar_t *
0x18008feb5  mov     rcx, r14; this
0x18008feb8  call    ?PrepareDirectoryForBackupRestore@CMsmqVssWriter@@AEAAJPEB_W0HPEAX@Z; CMsmqVssWriter::PrepareDirectoryForBackupRestore(wchar_t const *,wchar_t const *,int,void *)
0x18008febd  mov     ebx, eax
0x18008febf  test    eax, eax
0x18008fec1  js      short loc_18008FED1
0x18008fec3  mov     rcx, rsi; Block
0x18008fec6  call    cs:__imp_free
0x18008fecc  nop
0x18008fecd  inc     edi
0x18008fecf  jmp     short loc_18008FE61
0x18008fed1  mov     r8d, 118h; unsigned __int16
0x18008fed7  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008fede  mov     ecx, ebx; int
0x18008fee0  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008fee5  nop
0x18008fee6  mov     rcx, rsi; Block
0x18008fee9  call    cs:__imp_free
0x18008feef  nop
0x18008fef0  mov     eax, ebx
0x18008fef2  jmp     loc_18008FFA1
0x18008fef7  lea     rcx, aQmlog_0; "qmlog"
0x18008fefe  mov     [rbp+57h+var_58], rcx
0x18008ff02  lea     rcx, aMqinseqs_0; "mqinseqs.*"
0x18008ff09  mov     [rbp+57h+var_50], rcx
0x18008ff0d  lea     rcx, aMqtrans; "mqtrans.*"
0x18008ff14  mov     [rbp+57h+var_48], rcx
0x18008ff18  mov     [rbp+57h+var_40], 1
0x18008ff1f  mov     [rbp+57h+var_38], rax
0x18008ff23  lea     rax, aStorexactlogpa; "StoreXactLogPath"
0x18008ff2a  mov     [rbp+57h+var_30], rax
0x18008ff2e  mov     [rbp+57h+var_28], 0
0x18008ff35  mov     [rbp+57h+var_20], 0FFFFFFFF80000002h
0x18008ff3d  lea     rdx, [rbp+57h+Block]; wchar_t **
0x18008ff41  lea     rcx, [rbp+57h+var_40]; struct RegEntry *
0x18008ff45  call    ?CmQueryValue@@YAXAEBVRegEntry@@PEAPEA_W@Z; CmQueryValue(RegEntry const &,wchar_t * *)
0x18008ff4a  xor     ebx, ebx
0x18008ff4c  mov     rdi, [rbp+57h+Block]
0x18008ff50  cmp     ebx, 3
0x18008ff53  jnb     short loc_18008FF95
0x18008ff55  xor     r9d, r9d; int
0x18008ff58  mov     r8, [rbp+rbx*8+57h+var_58]; wchar_t *
0x18008ff5d  mov     rdx, rdi; wchar_t *
0x18008ff60  mov     rcx, r14; this
0x18008ff63  call    ?PrepareDirectoryForBackupRestore@CMsmqVssWriter@@AEAAJPEB_W0HPEAX@Z; CMsmqVssWriter::PrepareDirectoryForBackupRestore(wchar_t const *,wchar_t const *,int,void *)
0x18008ff68  mov     esi, eax
0x18008ff6a  test    eax, eax
0x18008ff6c  js      short loc_18008FF72
0x18008ff6e  inc     ebx
0x18008ff70  jmp     short loc_18008FF50
0x18008ff72  mov     r8d, 140h; unsigned __int16
0x18008ff78  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008ff7f  mov     ecx, esi; int
0x18008ff81  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008ff86  nop
0x18008ff87  mov     rcx, rdi; Block
0x18008ff8a  call    cs:__imp_free
0x18008ff90  nop
0x18008ff91  mov     eax, esi
0x18008ff93  jmp     short loc_18008FFA1
0x18008ff95  mov     rcx, rdi; Block
0x18008ff98  call    cs:__imp_free
0x18008ff9e  nop
0x18008ff9f  xor     eax, eax
0x18008ffa1  lea     r11, [rsp+0A0h+var_10]
0x18008ffa9  mov     rbx, [r11+20h]
0x18008ffad  mov     rsi, [r11+30h]
0x18008ffb1  mov     rsp, r11
0x18008ffb4  pop     r14
0x18008ffb6  pop     rdi
0x18008ffb7  pop     rbp
0x18008ffb8  retn
```
