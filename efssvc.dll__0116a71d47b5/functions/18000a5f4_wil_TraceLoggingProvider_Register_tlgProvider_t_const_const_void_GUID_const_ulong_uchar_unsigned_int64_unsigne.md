# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x18000a5f4`
- end: `0x18000a6b2`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void __fastcall(wil::TraceLoggingProvider *this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800083cc`
- `0x1800095a0`

## callees

- `0x18000a5f4`
- `0x18000c3c0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000a679`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000a679`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000a661`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000a661`

## pseudocode

```c
void __fastcall wil::TraceLoggingProvider::Register(
        wil::TraceLoggingProvider *this,
        const struct _tlgProvider_t *const a2,
        void (*a3)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))
{
  _QWORD *v3; // rsi
  bool v5; // zf
  __int64 v7; // rax
  GUID ProviderId; // [rsp+20h] [rbp-28h] BYREF

  *((_QWORD *)this + 1) = a2;
  v3 = (_QWORD *)((char *)a2 + 32);
  *((_BYTE *)this + 16) = 1;
  v5 = *((_QWORD *)a2 + 4) == 0;
  ProviderId = *(GUID *)(*((_QWORD *)a2 + 1) - 16LL);
  if ( !v5 )
    __fastfail(5u);
  *((_QWORD *)a2 + 5) = 0;
  *((_QWORD *)a2 + 6) = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, a2, (PREGHANDLE)a2 + 4) )
    EventSetInformation(
      *v3,
      2,
      *((_QWORD *)a2 + 1),
      **((unsigned __int16 **)a2 + 1),
      *(_QWORD *)&ProviderId.Data1,
      *(_QWORD *)ProviderId.Data4);
  v7 = *(_QWORD *)this;
  *((_DWORD *)this + 5) = 1;
  (*(void (__fastcall **)(wil::TraceLoggingProvider *))(v7 + 8))(this);
}

```

## disassembly

```asm
0x18000a5f4  mov     [rsp+arg_10], rbx
0x18000a5f9  mov     [rsp+arg_18], rsi
0x18000a5fe  push    rdi
0x18000a5ff  sub     rsp, 40h
0x18000a603  mov     rax, cs:__security_cookie
0x18000a60a  xor     rax, rsp
0x18000a60d  mov     [rsp+48h+var_18], rax
0x18000a612  mov     [rcx+8], rdx
0x18000a616  lea     rsi, [rdx+20h]
0x18000a61a  mov     byte ptr [rcx+10h], 1
0x18000a61e  mov     rdi, rdx
0x18000a621  cmp     qword ptr [rsi], 0
0x18000a625  mov     rbx, rcx
0x18000a628  mov     rax, [rdx+8]
0x18000a62c  movups  xmm0, xmmword ptr [rax-10h]
0x18000a630  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x18000a636  jz      short loc_18000A63F
0x18000a638  mov     ecx, 5
0x18000a63d  int     29h; Win8: RtlFailFast(ecx)
0x18000a63f  mov     qword ptr [rdx+28h], 0
0x18000a647  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x18000a64c  mov     qword ptr [rdx+30h], 0
0x18000a654  mov     r9, rsi; RegHandle
0x18000a657  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000a65e  mov     r8, rdi; CallbackContext
0x18000a661  call    cs:__imp_EventRegister
0x18000a667  test    eax, eax
0x18000a669  jnz     short loc_18000A67F
0x18000a66b  mov     r8, [rdi+8]
0x18000a66f  lea     edx, [rax+2]
0x18000a672  mov     rcx, [rsi]
0x18000a675  movzx   r9d, word ptr [r8]
0x18000a679  call    cs:__imp_EventSetInformation
0x18000a67f  mov     rax, [rbx]
0x18000a682  mov     rcx, rbx
0x18000a685  mov     dword ptr [rbx+14h], 1
0x18000a68c  mov     rax, [rax+8]
0x18000a690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a695  mov     rcx, [rsp+48h+var_18]
0x18000a69a  xor     rcx, rsp; StackCookie
0x18000a69d  call    __security_check_cookie
0x18000a6a2  mov     rbx, [rsp+48h+arg_10]
0x18000a6a7  mov     rsi, [rsp+48h+arg_18]
0x18000a6ac  add     rsp, 40h
0x18000a6b0  pop     rdi
0x18000a6b1  retn
```
