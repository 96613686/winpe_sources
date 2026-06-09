# CMsmqVssWriter::AddServiceQueues(IVssCreateWriterMetadata *,wchar_t const *)

- ea: `0x18008e528`
- end: `0x18008e81e`
- name: `?AddServiceQueues@CMsmqVssWriter@@AEAAJPEAVIVssCreateWriterMetadata@@PEB_W@Z`
- size: `758`
- prototype: `__int64 __fastcall(CMsmqVssWriter *__hidden this, struct IVssCreateWriterMetadata *, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, service_task`

## callers

- `0x18008dbe0`

## callees

- `0x18000bb04`
- `0x18002c61c`
- `0x18008e528`
- `0x18009a590`
- `0x18009bd1c`
- `0x1800e4010`

## import_xrefs

- `msvcrt!free` at `0x18008e674`
- `msvcrt!free` at `0x18008e683`
- `msvcrt!free` at `0x18008e6ed`
- `msvcrt!free` at `0x18008e6fc`
- `msvcrt!free` at `0x18008e75d`
- `msvcrt!free` at `0x18008e767`
- `msvcrt!free` at `0x18008e776`
- `msvcrt!free` at `0x18008e7bf`
- `msvcrt!free` at `0x18008e7c9`
- `msvcrt!free` at `0x18008e7d8`
- `msvcrt!free` at `0x18008e7e4`
- `msvcrt!free` at `0x18008e7ee`
- `msvcrt!free` at `0x18008e7fd`
- `msvcrt!free` at `0x18008e674`
- `msvcrt!free` at `0x18008e683`
- `msvcrt!free` at `0x18008e6ed`
- `msvcrt!free` at `0x18008e6fc`
- `msvcrt!free` at `0x18008e75d`
- `msvcrt!free` at `0x18008e767`
- `msvcrt!free` at `0x18008e776`
- `msvcrt!free` at `0x18008e7bf`
- `msvcrt!free` at `0x18008e7c9`
- `msvcrt!free` at `0x18008e7d8`
- `msvcrt!free` at `0x18008e7e4`
- `msvcrt!free` at `0x18008e7ee`
- `msvcrt!free` at `0x18008e7fd`

## string_xrefs

- `0x18008e5e1`: `StorePersistentPath`
- `0x18008e5ac`: `writer/mqwriter`
- `0x18008e662`: `writer/mqwriter`
- `0x18008e6db`: `writer/mqwriter`
- `0x18008e74b`: `writer/mqwriter`
- `0x18008e7ad`: `writer/mqwriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMsmqVssWriter::AddServiceQueues(
        CMsmqVssWriter *this,
        struct IVssCreateWriterMetadata *a2,
        const wchar_t *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  wchar_t *v9; // rbx
  int v10; // eax
  unsigned int v11; // edi
  int v12; // eax
  wchar_t *v13; // rdi
  int v14; // eax
  unsigned int v15; // ebp
  int v16; // eax
  int v17; // [rsp+28h] [rbp-A0h]
  char v18; // [rsp+38h] [rbp-90h]
  char v19; // [rsp+40h] [rbp-88h]
  char v20; // [rsp+48h] [rbp-80h]
  char v21; // [rsp+50h] [rbp-78h]
  int v22; // [rsp+78h] [rbp-50h] BYREF
  __int64 v23; // [rsp+80h] [rbp-48h]
  const wchar_t *v24; // [rsp+88h] [rbp-40h]
  int v25; // [rsp+90h] [rbp-38h]
  __int64 v26; // [rsp+98h] [rbp-30h]
  void *Block; // [rsp+D8h] [rbp+10h] BYREF
  wchar_t *v28; // [rsp+E8h] [rbp+20h]

  v21 = 1;
  v20 = 1;
  v19 = 0;
  v18 = 0;
  v6 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, const wchar_t *, const wchar_t *, _QWORD, _QWORD, _DWORD, char, char, char, char, _DWORD))(*(_QWORD *)a2 + 16LL))(
         a2,
         2,
         L"storage",
         L"queue",
         0,
         0,
         0,
         v18,
         v19,
         v20,
         v21,
         0);
  v7 = v6;
  if ( v6 < 0 )
  {
    LogMsgHR(v6, (wchar_t *)L"writer/mqwriter", 0x348u);
    return v7;
  }
  Block = 0;
  v22 = 1;
  v23 = *((_QWORD *)this + 4);
  v24 = L"StorePersistentPath";
  v25 = 0;
  v26 = -2147483646;
  CmQueryValue((const struct RegEntry *)&v22, (wchar_t **)&Block);
  v9 = (wchar_t *)MmAllocate(0x20Au);
  v28 = v9;
  v10 = StringCchPrintfW(v9, 0x105u, L"%s\\%s", Block, L"LQS");
  v11 = v10;
  if ( v10 < 0 )
  {
    LogMsgHR(v10, (wchar_t *)L"writer/mqwriter", 0x35Cu);
    free(v9);
    free(Block);
    return v11;
  }
  LOBYTE(v17) = 0;
  v12 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, const wchar_t *, const wchar_t *, wchar_t *, const wchar_t *, int, _QWORD, int))(*(_QWORD *)a2 + 40LL))(
          a2,
          L"storage",
          L"queue",
          v9,
          L"*",
          v17,
          0,
          3855);
  v11 = v12;
  if ( v12 < 0 )
  {
    LogMsgHR(v12, (wchar_t *)L"writer/mqwriter", 0x370u);
    free(v9);
    free(Block);
    return v11;
  }
  v13 = (wchar_t *)MmAllocate(0x20Au);
  v14 = StringCchPrintfW(v13, 0x105u, L"%s\\%s\\%s", a3, L"Restore", L"queue");
  v15 = v14;
  if ( v14 < 0 )
  {
    LogMsgHR(v14, (wchar_t *)L"writer/mqwriter", 0x384u);
    free(v13);
    free(v9);
    free(Block);
    return v15;
  }
  v16 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, wchar_t *, const wchar_t *, _QWORD, wchar_t *))(*(_QWORD *)a2 + 56LL))(
          a2,
          v9,
          L"*",
          0,
          v13);
  v15 = v16;
  if ( v16 < 0 )
  {
    LogMsgHR(v16, (wchar_t *)L"writer/mqwriter", 0x398u);
    free(v13);
    free(v9);
    free(Block);
    return v15;
  }
  free(v13);
  free(v9);
  free(Block);
  return 0;
}

```

## disassembly

```asm
0x18008e528  mov     [rsp+arg_0], rbx
0x18008e52d  push    rbp
0x18008e52e  push    rdi
0x18008e52f  push    r12
0x18008e531  push    r13
0x18008e533  push    r14
0x18008e535  sub     rsp, 0A0h
0x18008e53c  mov     rbp, r8
0x18008e53f  mov     r14, rdx
0x18008e542  mov     rdi, rcx
0x18008e545  mov     rax, [rdx]
0x18008e548  mov     [rsp+0C8h+var_70], 0
0x18008e550  mov     [rsp+0C8h+var_78], 1
0x18008e555  mov     [rsp+0C8h+var_80], 1
0x18008e55a  mov     [rsp+0C8h+var_88], 0
0x18008e55f  mov     [rsp+0C8h+var_90], 0
0x18008e564  mov     dword ptr [rsp+0C8h+var_98], 0
0x18008e56c  mov     [rsp+0C8h+var_A0], 0
0x18008e575  mov     [rsp+0C8h+var_A8], 0
0x18008e57e  lea     r12, aQueue; "queue"
0x18008e585  mov     r9, r12
0x18008e588  lea     r8, aStorage; "storage"
0x18008e58f  mov     edx, 2
0x18008e594  mov     rcx, r14
0x18008e597  mov     rax, [rax+10h]
0x18008e59b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e5a0  mov     ebx, eax
0x18008e5a2  test    eax, eax
0x18008e5a4  jns     short loc_18008E5C1
0x18008e5a6  mov     r8d, 348h; unsigned __int16
0x18008e5ac  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008e5b3  mov     ecx, eax; int
0x18008e5b5  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008e5ba  mov     eax, ebx
0x18008e5bc  jmp     loc_18008E806
0x18008e5c1  mov     [rsp+0C8h+Block], 0
0x18008e5cd  mov     [rsp+0C8h+var_50], 1
0x18008e5d5  mov     rax, [rdi+20h]
0x18008e5d9  mov     [rsp+0C8h+var_48], rax
0x18008e5e1  lea     rax, aStorepersisten; "StorePersistentPath"
0x18008e5e8  mov     [rsp+0C8h+var_40], rax
0x18008e5f0  mov     [rsp+0C8h+var_38], 0
0x18008e5fb  mov     [rsp+0C8h+var_30], 0FFFFFFFF80000002h
0x18008e607  lea     rdx, [rsp+0C8h+Block]; wchar_t **
0x18008e60f  lea     rcx, [rsp+0C8h+var_50]; struct RegEntry *
0x18008e614  call    ?CmQueryValue@@YAXAEBVRegEntry@@PEAPEA_W@Z; CmQueryValue(RegEntry const &,wchar_t * *)
0x18008e619  mov     ecx, 20Ah; unsigned __int64
0x18008e61e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18008e623  mov     rbx, rax
0x18008e626  mov     [rsp+0C8h+arg_18], rax
0x18008e62e  lea     rax, aLqs_1; "LQS"
0x18008e635  mov     [rsp+0C8h+var_A8], rax
0x18008e63a  mov     r9, [rsp+0C8h+Block]
0x18008e642  lea     r8, aSS_3; "%s\\%s"
0x18008e649  mov     edx, 105h; unsigned __int64
0x18008e64e  mov     rcx, rbx; wchar_t *
0x18008e651  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18008e656  mov     edi, eax
0x18008e658  test    eax, eax
0x18008e65a  jns     short loc_18008E691
0x18008e65c  mov     r8d, 35Ch; unsigned __int16
0x18008e662  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008e669  mov     ecx, eax; int
0x18008e66b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008e670  nop
0x18008e671  mov     rcx, rbx; Block
0x18008e674  call    cs:__imp_free
0x18008e67a  nop
0x18008e67b  mov     rcx, [rsp+0C8h+Block]; Block
0x18008e683  call    cs:__imp_free
0x18008e689  nop
0x18008e68a  mov     eax, edi
0x18008e68c  jmp     loc_18008E806
0x18008e691  mov     rax, [r14]
0x18008e694  mov     dword ptr [rsp+0C8h+var_90], 0F0Fh
0x18008e69c  mov     [rsp+0C8h+var_98], 0
0x18008e6a5  mov     byte ptr [rsp+0C8h+var_A0], 0
0x18008e6aa  lea     r13, asc_180104F98; "*"
0x18008e6b1  mov     [rsp+0C8h+var_A8], r13
0x18008e6b6  mov     r9, rbx
0x18008e6b9  mov     r8, r12
0x18008e6bc  lea     rdx, aStorage; "storage"
0x18008e6c3  mov     rcx, r14
0x18008e6c6  mov     rax, [rax+28h]
0x18008e6ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e6cf  mov     edi, eax
0x18008e6d1  test    eax, eax
0x18008e6d3  jns     short loc_18008E705
0x18008e6d5  mov     r8d, 370h; unsigned __int16
0x18008e6db  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008e6e2  mov     ecx, eax; int
0x18008e6e4  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008e6e9  nop
0x18008e6ea  mov     rcx, rbx; Block
0x18008e6ed  call    cs:__imp_free
0x18008e6f3  nop
0x18008e6f4  mov     rcx, [rsp+0C8h+Block]; Block
0x18008e6fc  call    cs:__imp_free
0x18008e702  nop
0x18008e703  jmp     short loc_18008E68A
0x18008e705  mov     ecx, 20Ah; unsigned __int64
0x18008e70a  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18008e70f  mov     rdi, rax
0x18008e712  mov     [rsp+0C8h+var_58], rax
0x18008e717  mov     [rsp+0C8h+var_A0], r12
0x18008e71c  lea     rax, aRestore; "Restore"
0x18008e723  mov     [rsp+0C8h+var_A8], rax
0x18008e728  mov     r9, rbp
0x18008e72b  lea     r8, aSSS; "%s\\%s\\%s"
0x18008e732  mov     edx, 105h; unsigned __int64
0x18008e737  mov     rcx, rdi; wchar_t *
0x18008e73a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18008e73f  mov     ebp, eax
0x18008e741  test    eax, eax
0x18008e743  jns     short loc_18008E784
0x18008e745  mov     r8d, 384h; unsigned __int16
0x18008e74b  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008e752  mov     ecx, eax; int
0x18008e754  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008e759  nop
0x18008e75a  mov     rcx, rdi; Block
0x18008e75d  call    cs:__imp_free
0x18008e763  nop
0x18008e764  mov     rcx, rbx; Block
0x18008e767  call    cs:__imp_free
0x18008e76d  nop
0x18008e76e  mov     rcx, [rsp+0C8h+Block]; Block
0x18008e776  call    cs:__imp_free
0x18008e77c  nop
0x18008e77d  mov     eax, ebp
0x18008e77f  jmp     loc_18008E806
0x18008e784  mov     rax, [r14]
0x18008e787  mov     [rsp+0C8h+var_A8], rdi
0x18008e78c  xor     r9d, r9d
0x18008e78f  mov     r8, r13
0x18008e792  mov     rdx, rbx
0x18008e795  mov     rcx, r14
0x18008e798  mov     rax, [rax+38h]
0x18008e79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e7a1  mov     ebp, eax
0x18008e7a3  test    eax, eax
0x18008e7a5  jns     short loc_18008E7E1
0x18008e7a7  mov     r8d, 398h; unsigned __int16
0x18008e7ad  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008e7b4  mov     ecx, eax; int
0x18008e7b6  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008e7bb  nop
0x18008e7bc  mov     rcx, rdi; Block
0x18008e7bf  call    cs:__imp_free
0x18008e7c5  nop
0x18008e7c6  mov     rcx, rbx; Block
0x18008e7c9  call    cs:__imp_free
0x18008e7cf  nop
0x18008e7d0  mov     rcx, [rsp+0C8h+Block]; Block
0x18008e7d8  call    cs:__imp_free
0x18008e7de  nop
0x18008e7df  jmp     short loc_18008E77D
0x18008e7e1  mov     rcx, rdi; Block
0x18008e7e4  call    cs:__imp_free
0x18008e7ea  nop
0x18008e7eb  mov     rcx, rbx; Block
0x18008e7ee  call    cs:__imp_free
0x18008e7f4  nop
0x18008e7f5  mov     rcx, [rsp+0C8h+Block]; Block
0x18008e7fd  call    cs:__imp_free
0x18008e803  nop
0x18008e804  xor     eax, eax
0x18008e806  mov     rbx, [rsp+0C8h+arg_0]
0x18008e80e  add     rsp, 0A0h
0x18008e815  pop     r14
0x18008e817  pop     r13
0x18008e819  pop     r12
0x18008e81b  pop     rdi
0x18008e81c  pop     rbp
0x18008e81d  retn
```
