# FREB_REQUEST_CONTEXT::AppendCommon(TRACE_EVENTS_LIST_ENTRY *)

- ea: `0x180003bbc`
- end: `0x180003c50`
- name: `?AppendCommon@FREB_REQUEST_CONTEXT@@AEAAXPEAVTRACE_EVENTS_LIST_ENTRY@@@Z`
- size: `148`
- prototype: `void __fastcall(FREB_REQUEST_CONTEXT *__hidden this, struct TRACE_EVENTS_LIST_ENTRY *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003c58`
- `0x180003d0c`
- `0x180005588`

## callees

- `0x180003bbc`
- `0x18000ac52`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c0f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003bf6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003bff`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003bf6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003bff`

## pseudocode

```c
void __fastcall FREB_REQUEST_CONTEXT::AppendCommon(FREB_REQUEST_CONTEXT *this, struct TRACE_EVENTS_LIST_ENTRY *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  char **v5; // rax
  char *v6; // rdi

  memset_0((char *)a2 + 16, 0, 0x58u);
  *((_QWORD *)a2 + 2) = &GUID_IIS_WWW_SERVER_TRACE_PROVIDER;
  *((_QWORD *)a2 + 4) = &GUID_NULL_GUID;
  *((_DWORD *)a2 + 20) = GetTickCount();
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 112);
  *((_DWORD *)a2 + 26) = GetTickCount();
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  v5 = (char **)*((_QWORD *)this + 13);
  v6 = (char *)this + 96;
  if ( *v5 != v6 )
    __fastfail(3u);
  *(_QWORD *)a2 = v6;
  *((_QWORD *)a2 + 1) = v5;
  *v5 = (char *)a2;
  *((_QWORD *)v6 + 1) = a2;
  LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x180003bbc  mov     [rsp+arg_0], rbx
0x180003bc1  mov     [rsp+arg_8], rsi
0x180003bc6  push    rdi
0x180003bc7  sub     rsp, 20h
0x180003bcb  mov     rsi, rdx
0x180003bce  mov     rdi, rcx
0x180003bd1  xor     edx, edx; Val
0x180003bd3  lea     rcx, [rsi+10h]; void *
0x180003bd7  lea     r8d, [rdx+58h]; Size
0x180003bdb  call    memset_0
0x180003be0  lea     rax, GUID_IIS_WWW_SERVER_TRACE_PROVIDER
0x180003be7  mov     [rsi+10h], rax
0x180003beb  lea     rax, GUID_NULL_GUID
0x180003bf2  mov     [rsi+20h], rax
0x180003bf6  call    cs:__imp_GetTickCount
0x180003bfc  mov     [rsi+50h], eax
0x180003bff  call    cs:__imp_GetTickCount
0x180003c05  lea     rbx, [rdi+70h]
0x180003c09  mov     [rsi+68h], eax
0x180003c0c  mov     rcx, rbx; lpCriticalSection
0x180003c0f  call    cs:__imp_EnterCriticalSection
0x180003c15  mov     rax, [rdi+68h]
0x180003c19  add     rdi, 60h ; '`'
0x180003c1d  cmp     [rax], rdi
0x180003c20  jz      short loc_180003C29
0x180003c22  mov     ecx, 3
0x180003c27  int     29h; Win8: RtlFailFast(ecx)
0x180003c29  mov     [rsi], rdi
0x180003c2c  mov     rcx, rbx
0x180003c2f  mov     [rsi+8], rax
0x180003c33  mov     [rax], rsi
0x180003c36  mov     [rdi+8], rsi
0x180003c3a  mov     rbx, [rsp+28h+arg_0]
0x180003c3f  mov     rsi, [rsp+28h+arg_8]
0x180003c44  add     rsp, 20h
0x180003c48  pop     rdi
0x180003c49  jmp     cs:__imp_LeaveCriticalSection
```
