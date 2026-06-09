# CDimThreadPool::Initialize(ulong,ulong)

- ea: `0x180030514`
- end: `0x180030628`
- name: `?Initialize@CDimThreadPool@@QEAAKKK@Z`
- size: `276`
- prototype: `unsigned int __fastcall(CDimThreadPool *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013f9c`

## callees

- `0x180030514`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800305c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800305c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18003060c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18003060c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180030600`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x180030600`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180030596`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180030596`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180030584`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180030584`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800305dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800305dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800305bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800305bf`

## pseudocode

```c
__int64 __fastcall CDimThreadPool::Initialize(CDimThreadPool *this)
{
  PTP_POOL Threadpool; // rax
  PTP_CLEANUP_GROUP *v4; // rdi
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  DWORD LastError; // esi
  struct _TP_POOL *v7; // rcx

  if ( *((_BYTE *)this + 88) )
    return 4317;
  *((_DWORD *)this + 4) = 3;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_DWORD *)this + 19) = 1;
  *((_DWORD *)this + 20) = 72;
  Threadpool = CreateThreadpool(0);
  *(_QWORD *)this = Threadpool;
  v4 = (PTP_CLEANUP_GROUP *)((char *)this + 8);
  if ( Threadpool && (ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup(), (*v4 = ThreadpoolCleanupGroup) != 0) )
  {
    v7 = *(struct _TP_POOL **)this;
    LastError = 0;
    *((_QWORD *)this + 3) = *(_QWORD *)this;
    *((_QWORD *)this + 4) = ThreadpoolCleanupGroup;
    *((_QWORD *)this + 5) = 0;
    SetThreadpoolThreadMaximum(v7, 0xAu);
    SetThreadpoolThreadMinimum(*(PTP_POOL *)this, 1u);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( *v4 )
      {
        CloseThreadpoolCleanupGroupMembers(*v4, 1, 0);
        CloseThreadpoolCleanupGroup(*v4);
        *v4 = 0;
      }
      if ( *(_QWORD *)this )
      {
        CloseThreadpool(*(PTP_POOL *)this);
        *(_QWORD *)this = 0;
      }
      return LastError;
    }
  }
  *((_BYTE *)this + 88) = 1;
  return LastError;
}

```

## disassembly

```asm
0x180030514  mov     [rsp+arg_0], rbx
0x180030519  mov     [rsp+arg_8], rsi
0x18003051e  push    rdi
0x18003051f  sub     rsp, 20h
0x180030523  cmp     byte ptr [rcx+58h], 0
0x180030527  mov     rbx, rcx
0x18003052a  jz      short loc_180030536
0x18003052c  mov     eax, 10DDh
0x180030531  jmp     loc_180030618
0x180030536  mov     dword ptr [rcx+10h], 3
0x18003053d  mov     qword ptr [rcx+18h], 0
0x180030545  mov     qword ptr [rcx+20h], 0
0x18003054d  mov     qword ptr [rcx+28h], 0
0x180030555  mov     qword ptr [rcx+30h], 0
0x18003055d  mov     qword ptr [rcx+38h], 0
0x180030565  mov     qword ptr [rcx+40h], 0
0x18003056d  mov     dword ptr [rcx+48h], 0
0x180030574  mov     dword ptr [rcx+4Ch], 1
0x18003057b  mov     dword ptr [rcx+50h], 48h ; 'H'
0x180030582  xor     ecx, ecx; reserved
0x180030584  call    cs:__imp_CreateThreadpool
0x18003058a  mov     [rbx], rax
0x18003058d  lea     rdi, [rbx+8]
0x180030591  test    rax, rax
0x180030594  jz      short loc_1800305A4
0x180030596  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18003059c  mov     [rdi], rax
0x18003059f  test    rax, rax
0x1800305a2  jnz     short loc_1800305EC
0x1800305a4  call    cs:__imp_GetLastError
0x1800305aa  mov     esi, eax
0x1800305ac  test    eax, eax
0x1800305ae  jz      short loc_180030612
0x1800305b0  mov     rcx, [rdi]; ptpcg
0x1800305b3  test    rcx, rcx
0x1800305b6  jz      short loc_1800305D5
0x1800305b8  xor     r8d, r8d; pvCleanupContext
0x1800305bb  lea     edx, [r8+1]; fCancelPendingCallbacks
0x1800305bf  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800305c5  mov     rcx, [rdi]; ptpcg
0x1800305c8  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800305ce  mov     qword ptr [rdi], 0
0x1800305d5  mov     rcx, [rbx]; ptpp
0x1800305d8  test    rcx, rcx
0x1800305db  jz      short loc_180030616
0x1800305dd  call    cs:__imp_CloseThreadpool
0x1800305e3  mov     qword ptr [rbx], 0
0x1800305ea  jmp     short loc_180030616
0x1800305ec  mov     rcx, [rbx]; ptpp
0x1800305ef  xor     esi, esi
0x1800305f1  mov     [rbx+18h], rcx
0x1800305f5  mov     [rbx+20h], rax
0x1800305f9  mov     [rbx+28h], rsi
0x1800305fd  lea     edx, [rsi+0Ah]; cthrdMost
0x180030600  call    cs:__imp_SetThreadpoolThreadMaximum
0x180030606  mov     rcx, [rbx]; ptpp
0x180030609  lea     edx, [rsi+1]; cthrdMic
0x18003060c  call    cs:__imp_SetThreadpoolThreadMinimum
0x180030612  mov     byte ptr [rbx+58h], 1
0x180030616  mov     eax, esi
0x180030618  mov     rbx, [rsp+28h+arg_0]
0x18003061d  mov     rsi, [rsp+28h+arg_8]
0x180030622  add     rsp, 20h
0x180030626  pop     rdi
0x180030627  retn
```
