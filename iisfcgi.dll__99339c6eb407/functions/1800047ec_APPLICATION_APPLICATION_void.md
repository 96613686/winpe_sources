# APPLICATION::~APPLICATION(void)

- ea: `0x1800047ec`
- end: `0x180004936`
- name: `??1APPLICATION@@AEAA@XZ`
- size: `330`
- prototype: `void __fastcall(APPLICATION *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005030`

## callees

- `0x180001048`
- `0x180001d50`
- `0x1800033e0`
- `0x1800047ec`
- `0x180007090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004859`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004859`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048c9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004918`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004918`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000492f`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000481d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000481d`

## pseudocode

```c
void __fastcall APPLICATION::~APPLICATION(APPLICATION *this)
{
  BUFFER *v1; // rdi
  PROTOCOL *v3; // rcx
  SEND_QUEUE *v4; // rcx
  SEND_QUEUE *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  volatile signed __int32 *v8; // rdi

  v1 = (BUFFER *)*((_QWORD *)this + 25);
  *(_QWORD *)this = &APPLICATION::`vftable'{for `ISEND_QUEUE_PRODUCER'};
  *((_QWORD *)this + 1) = &APPLICATION::`vftable'{for `ISEND_QUEUE_CONSUMER'};
  if ( v1 )
  {
    BUFFER::~BUFFER(v1);
    operator delete(v1);
    *((_QWORD *)this + 25) = 0;
  }
  v3 = (PROTOCOL *)*((_QWORD *)this + 10);
  if ( v3 )
  {
    PROTOCOL::DereferenceProtocol(v3);
    *((_QWORD *)this + 10) = 0;
  }
  if ( *((_DWORD *)this + 38) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  if ( *((_DWORD *)this + 53) )
  {
    v4 = (SEND_QUEUE *)*((_QWORD *)this + 9);
    if ( v4 )
    {
      *((_DWORD *)this + 53) = 0;
      SEND_QUEUE::DereferenceSendQueue(v4);
    }
  }
  v5 = (SEND_QUEUE *)*((_QWORD *)this + 8);
  if ( v5 )
  {
    SEND_QUEUE::DereferenceSendQueue(v5);
    *((_QWORD *)this + 8) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 29);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 29) = 0;
    *((_DWORD *)this + 63) = -1;
  }
  v7 = (void *)*((_QWORD *)this + 30);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 30) = 0;
  }
  v8 = (volatile signed __int32 *)*((_QWORD *)this + 12);
  if ( _InterlockedExchangeAdd(v8 + 35, 0xFFFFFFFF) == 1 && v8 )
  {
    APPLICATION_MANAGER::~APPLICATION_MANAGER((APPLICATION_MANAGER *)v8);
    operator delete((void *)v8);
  }
  _InterlockedDecrement(&APPLICATION::sm_cTotalApplications);
  *((_DWORD *)this + 4) = 1634165606;
  STRU::~STRU((APPLICATION *)((char *)this + 368));
  STRU::~STRU((APPLICATION *)((char *)this + 312));
}

```

## disassembly

```asm
0x1800047ec  mov     [rsp+arg_8], rbx
0x1800047f1  push    rdi
0x1800047f2  sub     rsp, 20h
0x1800047f6  mov     rdi, [rcx+0C8h]
0x1800047fd  lea     rax, ??_7APPLICATION@@6BISEND_QUEUE_PRODUCER@@@; const APPLICATION::`vftable'{for `ISEND_QUEUE_PRODUCER'}
0x180004804  mov     [rcx], rax
0x180004807  lea     rax, ??_7APPLICATION@@6BISEND_QUEUE_CONSUMER@@@; const APPLICATION::`vftable'{for `ISEND_QUEUE_CONSUMER'}
0x18000480e  mov     [rcx+8], rax
0x180004812  mov     rbx, rcx
0x180004815  test    rdi, rdi
0x180004818  jz      short loc_180004836
0x18000481a  mov     rcx, rdi
0x18000481d  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180004823  mov     rcx, rdi; Block
0x180004826  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000482b  mov     qword ptr [rbx+0C8h], 0
0x180004836  mov     rcx, [rbx+50h]; this
0x18000483a  test    rcx, rcx
0x18000483d  jz      short loc_18000484C
0x18000483f  call    ?DereferenceProtocol@PROTOCOL@@QEAAXXZ; PROTOCOL::DereferenceProtocol(void)
0x180004844  mov     qword ptr [rbx+50h], 0
0x18000484c  cmp     dword ptr [rbx+98h], 0
0x180004853  jz      short loc_18000485F
0x180004855  lea     rcx, [rbx+70h]; lpCriticalSection
0x180004859  call    cs:__imp_DeleteCriticalSection
0x18000485f  cmp     dword ptr [rbx+0D4h], 0
0x180004866  jz      short loc_180004880
0x180004868  mov     rcx, [rbx+48h]; this
0x18000486c  test    rcx, rcx
0x18000486f  jz      short loc_180004880
0x180004871  mov     dword ptr [rbx+0D4h], 0
0x18000487b  call    ?DereferenceSendQueue@SEND_QUEUE@@QEAAXXZ; SEND_QUEUE::DereferenceSendQueue(void)
0x180004880  mov     rcx, [rbx+40h]; this
0x180004884  test    rcx, rcx
0x180004887  jz      short loc_180004896
0x180004889  call    ?DereferenceSendQueue@SEND_QUEUE@@QEAAXXZ; SEND_QUEUE::DereferenceSendQueue(void)
0x18000488e  mov     qword ptr [rbx+40h], 0
0x180004896  mov     rcx, [rbx+0E8h]; hObject
0x18000489d  test    rcx, rcx
0x1800048a0  jz      short loc_1800048BD
0x1800048a2  call    cs:__imp_CloseHandle
0x1800048a8  mov     qword ptr [rbx+0E8h], 0
0x1800048b3  mov     dword ptr [rbx+0FCh], 0FFFFFFFFh
0x1800048bd  mov     rcx, [rbx+0F0h]; hObject
0x1800048c4  test    rcx, rcx
0x1800048c7  jz      short loc_1800048DA
0x1800048c9  call    cs:__imp_CloseHandle
0x1800048cf  mov     qword ptr [rbx+0F0h], 0
0x1800048da  mov     rdi, [rbx+60h]
0x1800048de  or      eax, 0FFFFFFFFh
0x1800048e1  lock xadd [rdi+8Ch], eax
0x1800048e9  cmp     eax, 1
0x1800048ec  jnz     short loc_180004903
0x1800048ee  test    rdi, rdi
0x1800048f1  jz      short loc_180004903
0x1800048f3  mov     rcx, rdi; this
0x1800048f6  call    ??1APPLICATION_MANAGER@@AEAA@XZ; APPLICATION_MANAGER::~APPLICATION_MANAGER(void)
0x1800048fb  mov     rcx, rdi; Block
0x1800048fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004903  lock dec cs:?sm_cTotalApplications@APPLICATION@@2JA; long APPLICATION::sm_cTotalApplications
0x18000490a  lea     rcx, [rbx+170h]
0x180004911  mov     dword ptr [rbx+10h], 61676366h
0x180004918  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000491e  lea     rcx, [rbx+138h]
0x180004925  mov     rbx, [rsp+28h+arg_8]
0x18000492a  add     rsp, 20h
0x18000492e  pop     rdi
0x18000492f  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
