# CscTpp_CreateThreadPool(tagCSC_TP_INVO *,ulong)

- ea: `0x180069830`
- end: `0x1800698da`
- name: `?CscTpp_CreateThreadPool@@YAJPEAUtagCSC_TP_INVO@@K@Z`
- size: `170`
- prototype: `__int64 __fastcall(struct tagCSC_TP_INVO *, DWORD cthrdMost)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18006969c`

## callees

- `0x18002f10c`
- `0x1800697f0`
- `0x180069830`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180069846`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180069846`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18006989a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18006989a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180069854`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180069854`

## pseudocode

```c
__int64 __fastcall CscTpp_CreateThreadPool(struct tagCSC_TP_INVO *a1, DWORD cthrdMost)
{
  PTP_POOL Threadpool; // rax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  int Error; // edi
  struct _TP_POOL *v7; // rcx

  Threadpool = CreateThreadpool(0);
  *(_QWORD *)a1 = Threadpool;
  if ( Threadpool
    && (ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup(), (*((_QWORD *)a1 + 1) = ThreadpoolCleanupGroup) != 0) )
  {
    Error = 0;
    *((_DWORD *)a1 + 4) = 3;
    *((_QWORD *)a1 + 4) = 0;
    *((_QWORD *)a1 + 5) = 0;
    *((_QWORD *)a1 + 6) = 0;
    *((_QWORD *)a1 + 7) = 0;
    *((_QWORD *)a1 + 8) = 0;
    *((_DWORD *)a1 + 18) = 0;
    *((_DWORD *)a1 + 19) = 1;
    *((_DWORD *)a1 + 20) = 72;
    v7 = *(struct _TP_POOL **)a1;
    *((_QWORD *)a1 + 3) = *(_QWORD *)a1;
    SetThreadpoolThreadMaximum(v7, cthrdMost);
    *((_QWORD *)a1 + 4) = *((_QWORD *)a1 + 1);
    *((_QWORD *)a1 + 5) = CscTppCleanupGroupCancelCallback;
  }
  else
  {
    Error = ResultFromLastError();
    if ( Error < 0 )
      CscTpp_CloseThreadPool(a1);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180069830  mov     [rsp+arg_0], rbx
0x180069835  mov     [rsp+arg_8], rsi
0x18006983a  push    rdi
0x18006983b  sub     rsp, 20h
0x18006983f  mov     rbx, rcx
0x180069842  mov     esi, edx
0x180069844  xor     ecx, ecx; reserved
0x180069846  call    cs:__imp_CreateThreadpool
0x18006984c  mov     [rbx], rax
0x18006984f  test    rax, rax
0x180069852  jz      short loc_1800698B5
0x180069854  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18006985a  mov     [rbx+8], rax
0x18006985e  test    rax, rax
0x180069861  jz      short loc_1800698B5
0x180069863  xor     edi, edi
0x180069865  mov     dword ptr [rbx+10h], 3
0x18006986c  mov     [rbx+20h], rdi
0x180069870  mov     edx, esi; cthrdMost
0x180069872  mov     [rbx+28h], rdi
0x180069876  mov     [rbx+30h], rdi
0x18006987a  mov     [rbx+38h], rdi
0x18006987e  mov     [rbx+40h], rdi
0x180069882  mov     [rbx+48h], edi
0x180069885  mov     dword ptr [rbx+4Ch], 1
0x18006988c  mov     dword ptr [rbx+50h], 48h ; 'H'
0x180069893  mov     rcx, [rbx]; ptpp
0x180069896  mov     [rbx+18h], rcx
0x18006989a  call    cs:__imp_SetThreadpoolThreadMaximum
0x1800698a0  mov     rax, [rbx+8]
0x1800698a4  mov     [rbx+20h], rax
0x1800698a8  lea     rax, ?CscTppCleanupGroupCancelCallback@@YAXPEAX0@Z; CscTppCleanupGroupCancelCallback(void *,void *)
0x1800698af  mov     [rbx+28h], rax
0x1800698b3  jmp     short loc_1800698C8
0x1800698b5  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800698ba  mov     edi, eax
0x1800698bc  test    eax, eax
0x1800698be  jns     short loc_1800698C8
0x1800698c0  mov     rcx, rbx; struct tagCSC_TP_INVO *
0x1800698c3  call    ?CscTpp_CloseThreadPool@@YAXPEAUtagCSC_TP_INVO@@@Z; CscTpp_CloseThreadPool(tagCSC_TP_INVO *)
0x1800698c8  mov     rbx, [rsp+28h+arg_0]
0x1800698cd  mov     eax, edi
0x1800698cf  mov     rsi, [rsp+28h+arg_8]
0x1800698d4  add     rsp, 20h
0x1800698d8  pop     rdi
0x1800698d9  retn
```
