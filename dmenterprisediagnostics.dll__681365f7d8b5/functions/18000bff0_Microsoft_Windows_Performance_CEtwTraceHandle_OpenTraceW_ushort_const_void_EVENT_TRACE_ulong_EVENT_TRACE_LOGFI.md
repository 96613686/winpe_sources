# Microsoft::Windows::Performance::CEtwTraceHandle::OpenTraceW(ushort const *,void (*)(_EVENT_TRACE *),ulong (*)(_EVENT_TRACE_LOGFILEW *),ulong)

- ea: `0x18000bff0`
- end: `0x18000c0b5`
- name: `?OpenTraceW@CEtwTraceHandle@Performance@Windows@Microsoft@@QEAAJPEBGP6AXPEAU_EVENT_TRACE@@@ZP6AKPEAU_EVENT_TRACE_LOGFILEW@@@ZK@Z`
- size: `197`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEtwTraceHandle *__hidden this, const unsigned __int16 *, void (*)(struct _EVENT_TRACE *), unsigned int (*)(struct _EVENT_TRACE_LOGFILEW *), unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c0bc`

## callees

- `0x180001800`
- `0x1800023e0`
- `0x180009e70`
- `0x18000bff0`

## import_xrefs

- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18000c055`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18000c055`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEtwTraceHandle::OpenTraceW(
        Microsoft::Windows::Performance::CEtwTraceHandle *this,
        WCHAR *a2,
        void (*a3)(struct _EVENT_TRACE *),
        unsigned int (*a4)(struct _EVENT_TRACE_LOGFILEW *),
        ULONG a5)
{
  TRACEHANDLE v9; // rax
  int Version_low; // edx
  ULONG BufferSize; // ecx
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+20h] [rbp-1F8h] BYREF

  memset_0(&Logfile, 0, sizeof(Logfile));
  Logfile.LogfileHeader.ReservedFlags = a5;
  Logfile.LogFileName = a2;
  Logfile.EventCallback = a3;
  Logfile.BufferCallback = a4;
  v9 = OpenTraceW(&Logfile);
  Version_low = LOWORD(Logfile.LogfileHeader.Version);
  *(_QWORD *)this = v9;
  BufferSize = Logfile.LogfileHeader.BufferSize;
  *((_DWORD *)this + 2) = Version_low;
  *((_DWORD *)this + 3) = BufferSize;
  if ( v9 == -1 )
    return ATL::AtlHresultFromLastError();
  else
    return 0;
}

```

## disassembly

```asm
0x18000bff0  push    rbx
0x18000bff2  push    rsi
0x18000bff3  push    rdi
0x18000bff4  push    r14
0x18000bff6  sub     rsp, 1F8h
0x18000bffd  mov     rax, cs:__security_cookie
0x18000c004  xor     rax, rsp
0x18000c007  mov     [rsp+218h+var_38], rax
0x18000c00f  mov     rdi, r8
0x18000c012  mov     rbx, rdx
0x18000c015  mov     r14, rcx
0x18000c018  xor     edx, edx; Val
0x18000c01a  mov     r8d, 1C0h; Size
0x18000c020  lea     rcx, [rsp+218h+Logfile]; void *
0x18000c025  mov     rsi, r9
0x18000c028  call    memset_0
0x18000c02d  mov     eax, [rsp+218h+arg_20]
0x18000c034  lea     rcx, [rsp+218h+Logfile]; Logfile
0x18000c039  mov     [rsp+218h+Logfile.LogfileHeader.ReservedFlags], eax
0x18000c040  mov     [rsp+218h+Logfile.LogFileName], rbx
0x18000c045  mov     qword ptr [rsp+218h+Logfile.1A8h], rdi
0x18000c04d  mov     [rsp+218h+Logfile.BufferCallback], rsi
0x18000c055  call    cs:__imp_OpenTraceW
0x18000c05c  nop     dword ptr [rax+rax+00h]
0x18000c061  movzx   ecx, byte ptr [rsp+218h+Logfile.LogfileHeader.4]
0x18000c069  movzx   edx, byte ptr [rsp+218h+Logfile.LogfileHeader.4+1]
0x18000c071  shl     edx, 8
0x18000c074  or      edx, ecx
0x18000c076  mov     [r14], rax
0x18000c079  mov     ecx, [rsp+218h+Logfile.LogfileHeader.BufferSize]
0x18000c080  mov     [r14+8], edx
0x18000c084  mov     [r14+0Ch], ecx
0x18000c088  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c08c  jz      short loc_18000C092
0x18000c08e  xor     eax, eax
0x18000c090  jmp     short loc_18000C097
0x18000c092  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000c097  mov     rcx, [rsp+218h+var_38]
0x18000c09f  xor     rcx, rsp; StackCookie
0x18000c0a2  call    __security_check_cookie
0x18000c0a7  add     rsp, 1F8h
0x18000c0ae  pop     r14
0x18000c0b0  pop     rdi
0x18000c0b1  pop     rsi
0x18000c0b2  pop     rbx
0x18000c0b3  retn
```
