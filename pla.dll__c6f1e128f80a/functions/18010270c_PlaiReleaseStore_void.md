# PlaiReleaseStore(void)

- ea: `0x18010270c`
- end: `0x1801028be`
- name: `?PlaiReleaseStore@@YAJXZ`
- size: `434`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800f2f2c`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x18008d6b0`
- `0x18010270c`
- `0x18013aee0`

## import_xrefs

- `ntdll!EtwNotificationUnregister` at `0x18010273b`
- `ntdll!EtwNotificationUnregister` at `0x18010273b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18010288f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18010288f`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180102754`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180102754`

## pseudocode

```c
__int64 PlaiReleaseStore(void)
{
  RPC_STATUS v0; // eax
  int v1; // eax
  __int64 v2; // rax
  struct _COLLECTORSET_STORE *Flink; // rcx
  struct _LIST_ENTRY *v4; // rax
  int v6; // [rsp+78h] [rbp-A0h] BYREF
  unsigned __int16 v7[64]; // [rsp+80h] [rbp-98h] BYREF

  if ( qword_180169CF8 )
  {
    EtwNotificationUnregister(qword_180169CF8, 0);
    qword_180169CF8 = 0;
  }
  v0 = RpcServerUnregisterIfEx(qword_180142F00, 0, 0);
  v1 = PlaiHResultFromWin32(v0);
  if ( v1 < 0 )
  {
    v6 = v1;
    if ( (_DWORD)xmmword_180169738 )
    {
      if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v7, 0x4000000000000800uLL);
        v2 = -1;
        do
          ++v2;
        while ( v7[v2] );
        EventingWriteEvent((__int64)&g_Eventing, (__int64)PLA_EVENT_ERROR, 5, (__int64)&v6);
      }
    }
  }
  while ( 1 )
  {
    Flink = (struct _COLLECTORSET_STORE *)stru_180169BA8.Flink;
    if ( stru_180169BA8.Flink == &stru_180169BA8 )
      break;
    if ( stru_180169BA8.Flink->Blink != &stru_180169BA8
      || (v4 = stru_180169BA8.Flink->Flink, stru_180169BA8.Flink->Flink->Blink != stru_180169BA8.Flink) )
    {
      __fastfail(3u);
    }
    stru_180169BA8.Flink = stru_180169BA8.Flink->Flink;
    v4->Blink = &stru_180169BA8;
    PlaiDeleteStoreEntry(Flink);
  }
  if ( (_DWORD)xmmword_180169D00 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)&xmmword_180169D00 + 8));
    LODWORD(xmmword_180169D00) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18010270c  mov     [rsp+arg_0], rbx
0x180102711  push    rdi
0x180102712  sub     rsp, 110h
0x180102719  mov     rax, cs:__security_cookie
0x180102720  xor     rax, rsp
0x180102723  mov     [rsp+118h+var_18], rax
0x18010272b  mov     rcx, cs:qword_180169CF8
0x180102732  xor     ebx, ebx
0x180102734  test    rcx, rcx
0x180102737  jz      short loc_180102748
0x180102739  xor     edx, edx
0x18010273b  call    cs:__imp_EtwNotificationUnregister
0x180102741  mov     cs:qword_180169CF8, rbx
0x180102748  xor     r8d, r8d; RundownContextHandles
0x18010274b  lea     rcx, qword_180142F00; IfSpec
0x180102752  xor     edx, edx; MgrTypeUuid
0x180102754  call    cs:__imp_RpcServerUnregisterIfEx
0x18010275a  mov     ecx, eax; unsigned int
0x18010275c  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180102761  test    eax, eax
0x180102763  jns     loc_180102845
0x180102769  cmp     dword ptr cs:xmmword_180169738, ebx
0x18010276f  mov     [rsp+118h+var_A8], ebx
0x180102773  mov     [rsp+118h+var_A0], eax
0x180102777  jz      loc_180102845
0x18010277d  mov     rdx, 4000000000000800h; unsigned __int64
0x180102787  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010278e  jz      loc_180102845
0x180102794  mov     rax, cs:qword_180169748
0x18010279b  and     rax, rdx
0x18010279e  cmp     cs:qword_180169748, rax
0x1801027a5  jnz     loc_180102845
0x1801027ab  lea     rcx, [rsp+118h+var_98]; unsigned __int16 *
0x1801027b3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1801027b8  lea     rcx, [rsp+118h+var_98]
0x1801027c0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801027c4  inc     rax
0x1801027c7  cmp     [rcx+rax*2], bx
0x1801027cb  jnz     short loc_1801027C4
0x1801027cd  lea     ecx, [rax+rax]
0x1801027d0  add     rcx, 2
0x1801027d4  lea     rax, [rsp+118h+var_98]
0x1801027dc  mov     [rsp+118h+var_B8], rcx
0x1801027e1  lea     r9, [rsp+118h+var_A0]
0x1801027e6  mov     [rsp+118h+var_C0], rax
0x1801027eb  lea     rdx, PLA_EVENT_ERROR
0x1801027f2  mov     [rsp+118h+var_C8], 11h
0x1801027fb  lea     rax, aPlaireleasesto; "PlaiReleaseStore"
0x180102802  mov     [rsp+118h+var_D0], rax
0x180102807  mov     ecx, 4
0x18010280c  mov     [rsp+118h+var_D8], rcx
0x180102811  lea     rax, [rsp+118h+var_A8]
0x180102816  mov     [rsp+118h+var_E0], rax
0x18010281b  lea     rax, qword_180147320
0x180102822  mov     [rsp+118h+var_E8], 1
0x18010282b  mov     [rsp+118h+var_F0], rax
0x180102830  lea     r8d, [rcx+1]
0x180102834  mov     [rsp+118h+var_F8], rcx
0x180102839  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180102840  call    EventingWriteEvent
0x180102845  lea     rdi, stru_180169BA8
0x18010284c  mov     rcx, cs:stru_180169BA8.Flink; struct _COLLECTORSET_STORE *
0x180102853  cmp     rcx, rdi
0x180102856  jz      short loc_180102880
0x180102858  cmp     [rcx+8], rdi
0x18010285c  jnz     short loc_180102879
0x18010285e  mov     rax, [rcx]
0x180102861  cmp     [rax+8], rcx
0x180102865  jnz     short loc_180102879
0x180102867  mov     cs:stru_180169BA8.Flink, rax
0x18010286e  mov     [rax+8], rdi
0x180102872  call    ?PlaiDeleteStoreEntry@@YAJPEAU_COLLECTORSET_STORE@@@Z; PlaiDeleteStoreEntry(_COLLECTORSET_STORE *)
0x180102877  jmp     short loc_18010284C
0x180102879  mov     ecx, 3
0x18010287e  int     29h; Win8: RtlFailFast(ecx)
0x180102880  cmp     dword ptr cs:xmmword_180169D00, ebx
0x180102886  jz      short loc_18010289B
0x180102888  lea     rcx, xmmword_180169D00+8; lpCriticalSection
0x18010288f  call    cs:__imp_DeleteCriticalSection
0x180102895  mov     dword ptr cs:xmmword_180169D00, ebx
0x18010289b  xor     eax, eax
0x18010289d  mov     rcx, [rsp+118h+var_18]
0x1801028a5  xor     rcx, rsp; StackCookie
0x1801028a8  call    __security_check_cookie
0x1801028ad  mov     rbx, [rsp+118h+arg_0]
0x1801028b5  add     rsp, 110h
0x1801028bc  pop     rdi
0x1801028bd  retn
```
