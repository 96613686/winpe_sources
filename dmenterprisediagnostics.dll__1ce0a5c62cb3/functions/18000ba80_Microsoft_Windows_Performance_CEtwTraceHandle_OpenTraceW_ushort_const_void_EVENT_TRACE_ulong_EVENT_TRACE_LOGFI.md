# Microsoft::Windows::Performance::CEtwTraceHandle::OpenTraceW(ushort const *,void (*)(_EVENT_TRACE *),ulong (*)(_EVENT_TRACE_LOGFILEW *),ulong)

- ea: `0x18000ba80`
- end: `0x18000bb3e`
- name: `?OpenTraceW@CEtwTraceHandle@Performance@Windows@Microsoft@@QEAAJPEBGP6AXPEAU_EVENT_TRACE@@@ZP6AKPEAU_EVENT_TRACE_LOGFILEW@@@ZK@Z`
- size: `190`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEtwTraceHandle *__hidden this, const unsigned __int16 *, void (*)(struct _EVENT_TRACE *), unsigned int (*)(struct _EVENT_TRACE_LOGFILEW *), unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000bb44`

## callees

- `0x1800017e0`
- `0x1800023c0`
- `0x180009994`
- `0x18000ba80`

## import_xrefs

- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18000bae5`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18000bae5`

## pseudocode

```c
signed int __fastcall Microsoft::Windows::Performance::CEtwTraceHandle::OpenTraceW(
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
0x18000ba80  push    rbx
0x18000ba82  push    rsi
0x18000ba83  push    rdi
0x18000ba84  push    r14
0x18000ba86  sub     rsp, 1F8h
0x18000ba8d  mov     rax, cs:__security_cookie
0x18000ba94  xor     rax, rsp
0x18000ba97  mov     [rsp+218h+var_38], rax
0x18000ba9f  mov     rdi, r8
0x18000baa2  mov     rbx, rdx
0x18000baa5  mov     r14, rcx
0x18000baa8  xor     edx, edx; Val
0x18000baaa  mov     r8d, 1C0h; Size
0x18000bab0  lea     rcx, [rsp+218h+Logfile]; void *
0x18000bab5  mov     rsi, r9
0x18000bab8  call    memset_0
0x18000babd  mov     eax, [rsp+218h+arg_20]
0x18000bac4  lea     rcx, [rsp+218h+Logfile]; Logfile
0x18000bac9  mov     [rsp+218h+Logfile.LogfileHeader.ReservedFlags], eax
0x18000bad0  mov     [rsp+218h+Logfile.LogFileName], rbx
0x18000bad5  mov     qword ptr [rsp+218h+Logfile.1A8h], rdi
0x18000badd  mov     [rsp+218h+Logfile.BufferCallback], rsi
0x18000bae5  call    cs:__imp_OpenTraceW
0x18000baeb  movzx   ecx, byte ptr [rsp+218h+Logfile.LogfileHeader.4]
0x18000baf3  movzx   edx, byte ptr [rsp+218h+Logfile.LogfileHeader.4+1]
0x18000bafb  shl     edx, 8
0x18000bafe  or      edx, ecx
0x18000bb00  mov     [r14], rax
0x18000bb03  mov     ecx, [rsp+218h+Logfile.LogfileHeader.BufferSize]
0x18000bb0a  mov     [r14+8], edx
0x18000bb0e  mov     [r14+0Ch], ecx
0x18000bb12  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000bb16  jz      short loc_18000BB1C
0x18000bb18  xor     eax, eax
0x18000bb1a  jmp     short loc_18000BB21
0x18000bb1c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000bb21  mov     rcx, [rsp+218h+var_38]
0x18000bb29  xor     rcx, rsp; StackCookie
0x18000bb2c  call    __security_check_cookie
0x18000bb31  add     rsp, 1F8h
0x18000bb38  pop     r14
0x18000bb3a  pop     rdi
0x18000bb3b  pop     rsi
0x18000bb3c  pop     rbx
0x18000bb3d  retn
```
