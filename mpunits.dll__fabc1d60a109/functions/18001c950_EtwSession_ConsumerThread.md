# EtwSession_ConsumerThread

- ea: `0x18001c950`
- end: `0x18001ca56`
- name: `EtwSession_ConsumerThread`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000ac44`
- `0x18001c950`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c994`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c994`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18001ca0d`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18001ca0d`

## string_xrefs

- `0x18001c9c5`: `EtwSession_ConsumerThread`

## pseudocode

```c
__int64 __fastcall EtwSession_ConsumerThread(__int64 a1)
{
  void (__fastcall *v1)(_QWORD); // rbx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+20h] [rbp-50h] BYREF
  int v5; // [rsp+30h] [rbp-40h]
  int v6; // [rsp+34h] [rbp-3Ch]
  _OWORD v7[2]; // [rsp+40h] [rbp-30h] BYREF

  v1 = *(void (__fastcall **)(_QWORD))a1;
  memset(v7, 0, sizeof(v7));
  ExecutionContext_SaveThread((LPGUID)v7);
  GetCurrentThreadId();
  *(_DWORD *)&EventDescriptor.Id = 10002;
  *(_DWORD *)&EventDescriptor.Level = 4;
  EventDescriptor.Keyword = 1;
  Etw_Trace1_int(&EventDescriptor);
  if ( NITS_PRESENCE_STUB == 1
    || (v5 = 29,
        *(_QWORD *)&EventDescriptor.Id = "EtwSession_ConsumerThread",
        v6 = -1,
        EventDescriptor.Keyword = (ULONGLONG)"admin\\wmi\\winomi\\mp\\etw\\session.c",
        !((unsigned int (__fastcall *)(EVENT_DESCRIPTOR *, _QWORD))NITS_STUB[0])(&EventDescriptor, 0)) )
  {
    ProcessTrace((PTRACEHANDLE)(a1 + 32), 1u, 0, 0);
  }
  if ( v1 )
    v1(*(_QWORD *)(a1 + 8));
  return ((__int64 (__fastcall *)(_OWORD *))ExecutionContext_RestoreThread)(v7);
}

```

## disassembly

```asm
0x18001c950  mov     [rsp-8+arg_8], rbx
0x18001c955  mov     [rsp-8+arg_10], rdi
0x18001c95a  push    rbp
0x18001c95b  mov     rbp, rsp
0x18001c95e  sub     rsp, 70h
0x18001c962  mov     rax, cs:__security_cookie
0x18001c969  xor     rax, rsp
0x18001c96c  mov     [rbp+var_10], rax
0x18001c970  mov     rax, cs:off_180047C30
0x18001c977  xorps   xmm0, xmm0
0x18001c97a  mov     rbx, [rcx]
0x18001c97d  mov     rdi, rcx
0x18001c980  movups  [rbp+var_30], xmm0
0x18001c984  lea     rcx, [rbp+var_30]
0x18001c988  movups  [rbp+var_20], xmm0
0x18001c98c  mov     rax, [rax]
0x18001c98f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c994  call    cs:__imp_GetCurrentThreadId
0x18001c99a  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x18001c99e  mov     dword ptr [rbp+EventDescriptor.Id], 2712h
0x18001c9a5  mov     edx, eax
0x18001c9a7  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x18001c9ae  mov     [rbp+EventDescriptor.Keyword], 1
0x18001c9b6  call    Etw_Trace1_int
0x18001c9bb  cmp     cs:NITS_PRESENCE_STUB, 1
0x18001c9c3  jz      short loc_18001C9FF
0x18001c9c5  lea     rax, aEtwsessionCons; "EtwSession_ConsumerThread"
0x18001c9cc  mov     [rbp+var_40], 1Dh
0x18001c9d3  mov     qword ptr [rbp+EventDescriptor.Id], rax
0x18001c9d7  lea     rcx, [rbp+EventDescriptor]
0x18001c9db  lea     rax, aAdminWmiWinomi_1; "admin\\wmi\\winomi\\mp\\etw\\session.c"
0x18001c9e2  mov     [rbp+var_3C], 0FFFFFFFFh
0x18001c9e9  mov     [rbp+EventDescriptor.Keyword], rax
0x18001c9ed  xor     edx, edx
0x18001c9ef  mov     rax, cs:NITS_STUB
0x18001c9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9fb  test    eax, eax
0x18001c9fd  jnz     short loc_18001CA13
0x18001c9ff  xor     r9d, r9d; EndTime
0x18001ca02  lea     rcx, [rdi+20h]; HandleArray
0x18001ca06  xor     r8d, r8d; StartTime
0x18001ca09  lea     edx, [r9+1]; HandleCount
0x18001ca0d  call    cs:__imp_ProcessTrace
0x18001ca13  test    rbx, rbx
0x18001ca16  jz      short loc_18001CA24
0x18001ca18  mov     rcx, [rdi+8]
0x18001ca1c  mov     rax, rbx
0x18001ca1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca24  mov     rax, cs:off_180047C30
0x18001ca2b  lea     rcx, [rbp+var_30]
0x18001ca2f  mov     rax, [rax+8]
0x18001ca33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca38  mov     rcx, [rbp+var_10]
0x18001ca3c  xor     rcx, rsp; StackCookie
0x18001ca3f  call    __security_check_cookie
0x18001ca44  lea     r11, [rsp+70h+var_s0]
0x18001ca49  mov     rbx, [r11+18h]
0x18001ca4d  mov     rdi, [r11+20h]
0x18001ca51  mov     rsp, r11
0x18001ca54  pop     rbp
0x18001ca55  retn
```
