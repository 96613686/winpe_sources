# APP_POOL_ISOLATION::GenerateConfigWorkItem(MULTI_WORK_ITEM *)

- ea: `0x18000ca78`
- end: `0x18000cc39`
- name: `?GenerateConfigWorkItem@APP_POOL_ISOLATION@@AEAAJPEAVMULTI_WORK_ITEM@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(APP_POOL_ISOLATION *__hidden this, struct MULTI_WORK_ITEM *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x18000c950`

## callees

- `0x180001234`
- `0x180001274`
- `0x1800074b0`
- `0x1800077e8`
- `0x180007b60`
- `0x180007d30`
- `0x18000ca78`
- `0x18000dfe8`
- `0x18000e1f0`
- `0x180062010`

## import_xrefs

- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000cae7`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000cae7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cbf5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cc10`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cbf5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cc10`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000cabd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000cabd`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000caca`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000caca`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cb60`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cbb7`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cb60`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000cbb7`

## pseudocode

```c
__int64 __fastcall APP_POOL_ISOLATION::GenerateConfigWorkItem(APP_POOL_ISOLATION *this, struct MULTI_WORK_ITEM *a2)
{
  const unsigned __int16 **v2; // r14
  unsigned __int16 *v4; // rsi
  unsigned int *v5; // rax
  unsigned int *v6; // rdi
  __int64 v7; // rdx
  int Key; // eax
  struct STRING_TO_STRING_SET_TABLE_ITEM *v9; // r15
  int BlankWorkItem; // ebx
  struct WORK_ITEM *v11; // rbx
  const unsigned __int16 *v13[3]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v14; // [rsp+48h] [rbp-18h]
  int v15; // [rsp+50h] [rbp-10h]
  STRING_TO_STRING_SET_TABLE_ITEM *v16; // [rsp+98h] [rbp+38h] BYREF
  struct WORK_ITEM *v17; // [rsp+A0h] [rbp+40h] BYREF

  v2 = (const unsigned __int16 **)*((_QWORD *)a2 + 5);
  v17 = 0;
  v4 = (unsigned __int16 *)*v2;
  v5 = (unsigned int *)operator new(0x40u);
  v6 = v5;
  if ( v5 )
  {
    STRU::STRU((STRU *)(v5 + 2));
    CReaderWriterLock3::ReadLock((APP_POOL_ISOLATION *)((char *)this + 16));
    v7 = *((_QWORD *)v4 + 7);
    v16 = 0;
    Key = CLKRHashTable::FindKey((char *)this + 160, v7, &v16);
    v9 = v16;
    if ( Key >= 0 && v16 )
    {
      LODWORD(v13[0]) = *((_DWORD *)this + 6);
      v13[2] = *((const unsigned __int16 **)this + 16);
      v14 = *((_QWORD *)this + 30);
      v15 = 1413695809;
      _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
      *v6 = APP_POOL_ISOLATION_CONTEXT::GenerateAppPoolConfig(
              v13,
              *((struct AUTO_GROWING_BUFFER **)this + 29),
              v9,
              v2[5],
              v6 + 1,
              (struct STRU *)(v6 + 2));
      APP_POOL_ISOLATION_CONTEXT::~APP_POOL_ISOLATION_CONTEXT((APP_POOL_ISOLATION_CONTEXT *)v13);
      CReaderWriterLock3::ReadUnlock((APP_POOL_ISOLATION *)((char *)this + 16));
      BlankWorkItem = WORK_QUEUE::GetBlankWorkItem((WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 16), &v17);
      if ( BlankWorkItem >= 0 )
      {
        v11 = v17;
        WORK_ITEM::SetWorkDispatchPointer(v17, (struct WORK_DISPATCH *)v4);
        *((_QWORD *)v11 + 3) = 1;
        *((_QWORD *)v11 + 11) = v6;
        v6 = 0;
        BlankWorkItem = WORK_QUEUE::QueueWorkItem((WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 16), v11);
      }
    }
    else
    {
      CReaderWriterLock3::ReadUnlock((APP_POOL_ISOLATION *)((char *)this + 16));
      BlankWorkItem = -2147467259;
      if ( !v9 )
        goto LABEL_9;
    }
    STRING_TO_STRING_SET_TABLE_ITEM::DereferenceItem(v9);
  }
  else
  {
    BlankWorkItem = -2147024882;
    v6 = 0;
  }
LABEL_9:
  if ( v4 )
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v4 + 8LL))(v4);
  if ( v2 )
  {
    STRU::~STRU((STRU *)(v2 + 1));
    operator delete(v2);
  }
  if ( BlankWorkItem < 0 && v6 )
  {
    STRU::~STRU((STRU *)(v6 + 2));
    operator delete(v6);
  }
  return (unsigned int)BlankWorkItem;
}

```

## disassembly

```asm
0x18000ca78  mov     [rsp-28h+arg_0], rbx
0x18000ca7d  mov     [rsp-28h+arg_18], rsi
0x18000ca82  push    rbp
0x18000ca83  push    rdi
0x18000ca84  push    r12
0x18000ca86  push    r14
0x18000ca88  push    r15
0x18000ca8a  mov     rbp, rsp
0x18000ca8d  sub     rsp, 60h
0x18000ca91  mov     r14, [rdx+28h]
0x18000ca95  mov     rbx, rcx
0x18000ca98  mov     ecx, 40h ; '@'; Size
0x18000ca9d  mov     [rbp+arg_10], 0
0x18000caa5  mov     rsi, [r14]
0x18000caa8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000caad  mov     rdi, rax
0x18000cab0  test    rax, rax
0x18000cab3  jz      loc_18000CBD1
0x18000cab9  lea     rcx, [rax+8]
0x18000cabd  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000cac3  lea     r12, [rbx+10h]
0x18000cac7  mov     rcx, r12
0x18000caca  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000cad0  mov     rdx, [rsi+38h]
0x18000cad4  lea     rcx, [rbx+0A0h]
0x18000cadb  lea     r8, [rbp+arg_8]
0x18000cadf  mov     [rbp+arg_8], 0
0x18000cae7  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18000caed  mov     r15, [rbp+arg_8]
0x18000caf1  test    eax, eax
0x18000caf3  js      loc_18000CBB4
0x18000caf9  test    r15, r15
0x18000cafc  jz      loc_18000CBB4
0x18000cb02  mov     eax, [rbx+18h]
0x18000cb05  mov     [rbp+var_30], eax
0x18000cb08  mov     rax, [rbx+80h]
0x18000cb0f  mov     [rbp+var_20], rax
0x18000cb13  mov     rax, [rbx+0F0h]
0x18000cb1a  mov     [rbp+var_18], rax
0x18000cb1e  mov     [rbp+var_10], 54434941h
0x18000cb25  lock inc dword ptr [rax+8]
0x18000cb29  mov     r9, [r14+28h]; unsigned __int16 *
0x18000cb2d  lea     rax, [rdi+8]
0x18000cb31  lea     rdx, [rdi+4]
0x18000cb35  mov     [rsp+60h+var_38], rax; struct STRU *
0x18000cb3a  mov     [rsp+60h+var_40], rdx; unsigned int *
0x18000cb3f  lea     rcx, [rbp+var_30]; this
0x18000cb43  mov     rdx, [rbx+0E8h]; struct AUTO_GROWING_BUFFER *
0x18000cb4a  mov     r8, r15; struct STRING_TO_STRING_SET_TABLE_ITEM *
0x18000cb4d  call    ?GenerateAppPoolConfig@APP_POOL_ISOLATION_CONTEXT@@QEAAJPEAVAUTO_GROWING_BUFFER@@PEAVSTRING_TO_STRING_SET_TABLE_ITEM@@PEBGPEAKPEAVSTRU@@@Z; APP_POOL_ISOLATION_CONTEXT::GenerateAppPoolConfig(AUTO_GROWING_BUFFER *,STRING_TO_STRING_SET_TABLE_ITEM *,ushort const *,ulong *,STRU *)
0x18000cb52  lea     rcx, [rbp+var_30]; this
0x18000cb56  mov     [rdi], eax
0x18000cb58  call    ??1APP_POOL_ISOLATION_CONTEXT@@QEAA@XZ; APP_POOL_ISOLATION_CONTEXT::~APP_POOL_ISOLATION_CONTEXT(void)
0x18000cb5d  mov     rcx, r12
0x18000cb60  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000cb66  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18000cb6d  lea     rdx, [rbp+arg_10]; struct WORK_ITEM **
0x18000cb71  add     rcx, 10h; this
0x18000cb75  call    ?GetBlankWorkItem@WORK_QUEUE@@QEAAJPEAPEAVWORK_ITEM@@@Z; WORK_QUEUE::GetBlankWorkItem(WORK_ITEM * *)
0x18000cb7a  mov     ebx, eax
0x18000cb7c  test    eax, eax
0x18000cb7e  js      short loc_18000CBC7
0x18000cb80  mov     rbx, [rbp+arg_10]
0x18000cb84  mov     rdx, rsi; struct WORK_DISPATCH *
0x18000cb87  mov     rcx, rbx; this
0x18000cb8a  call    ?SetWorkDispatchPointer@WORK_ITEM@@QEAAXPEAVWORK_DISPATCH@@@Z; WORK_ITEM::SetWorkDispatchPointer(WORK_DISPATCH *)
0x18000cb8f  mov     qword ptr [rbx+18h], 1
0x18000cb97  mov     rdx, rbx; struct WORK_ITEM *
0x18000cb9a  mov     [rbx+58h], rdi
0x18000cb9e  xor     edi, edi
0x18000cba0  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18000cba7  add     rcx, 10h; this
0x18000cbab  call    ?QueueWorkItem@WORK_QUEUE@@QEAAJPEAVWORK_ITEM@@@Z; WORK_QUEUE::QueueWorkItem(WORK_ITEM *)
0x18000cbb0  mov     ebx, eax
0x18000cbb2  jmp     short loc_18000CBC7
0x18000cbb4  mov     rcx, r12
0x18000cbb7  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000cbbd  mov     ebx, 80004005h
0x18000cbc2  test    r15, r15
0x18000cbc5  jz      short loc_18000CBD8
0x18000cbc7  mov     rcx, r15; this
0x18000cbca  call    ?DereferenceItem@STRING_TO_STRING_SET_TABLE_ITEM@@QEAAXXZ; STRING_TO_STRING_SET_TABLE_ITEM::DereferenceItem(void)
0x18000cbcf  jmp     short loc_18000CBD8
0x18000cbd1  mov     ebx, 8007000Eh
0x18000cbd6  xor     edi, edi
0x18000cbd8  test    rsi, rsi
0x18000cbdb  jz      short loc_18000CBEC
0x18000cbdd  mov     rax, [rsi]
0x18000cbe0  mov     rcx, rsi
0x18000cbe3  mov     rax, [rax+8]
0x18000cbe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbec  test    r14, r14
0x18000cbef  jz      short loc_18000CC03
0x18000cbf1  lea     rcx, [r14+8]
0x18000cbf5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000cbfb  mov     rcx, r14; Block
0x18000cbfe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cc03  test    ebx, ebx
0x18000cc05  jns     short loc_18000CC1E
0x18000cc07  test    rdi, rdi
0x18000cc0a  jz      short loc_18000CC1E
0x18000cc0c  lea     rcx, [rdi+8]
0x18000cc10  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000cc16  mov     rcx, rdi; Block
0x18000cc19  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cc1e  lea     r11, [rsp+60h+var_s0]
0x18000cc23  mov     eax, ebx
0x18000cc25  mov     rbx, [r11+30h]
0x18000cc29  mov     rsi, [r11+48h]
0x18000cc2d  mov     rsp, r11
0x18000cc30  pop     r15
0x18000cc32  pop     r14
0x18000cc34  pop     r12
0x18000cc36  pop     rdi
0x18000cc37  pop     rbp
0x18000cc38  retn
```
