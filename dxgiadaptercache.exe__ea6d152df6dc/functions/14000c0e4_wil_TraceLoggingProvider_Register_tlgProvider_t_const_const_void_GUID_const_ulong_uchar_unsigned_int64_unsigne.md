# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x14000c0e4`
- end: `0x14000c1a2`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void __fastcall(wil::TraceLoggingProvider *this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a9b4`
- `0x14000aa74`

## callees

- `0x1400022a0`
- `0x14000c0e4`
- `0x140012010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x14000c169`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x14000c169`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x14000c151`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x14000c151`

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
0x14000c0e4  mov     [rsp+arg_10], rbx
0x14000c0e9  mov     [rsp+arg_18], rsi
0x14000c0ee  push    rdi
0x14000c0ef  sub     rsp, 40h
0x14000c0f3  mov     rax, cs:__security_cookie
0x14000c0fa  xor     rax, rsp
0x14000c0fd  mov     [rsp+48h+var_18], rax
0x14000c102  mov     [rcx+8], rdx
0x14000c106  lea     rsi, [rdx+20h]
0x14000c10a  mov     byte ptr [rcx+10h], 1
0x14000c10e  mov     rdi, rdx
0x14000c111  cmp     qword ptr [rsi], 0
0x14000c115  mov     rbx, rcx
0x14000c118  mov     rax, [rdx+8]
0x14000c11c  movups  xmm0, xmmword ptr [rax-10h]
0x14000c120  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x14000c126  jz      short loc_14000C12F
0x14000c128  mov     ecx, 5
0x14000c12d  int     29h; Win8: RtlFailFast(ecx)
0x14000c12f  mov     qword ptr [rdx+28h], 0
0x14000c137  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x14000c13c  mov     qword ptr [rdx+30h], 0
0x14000c144  mov     r9, rsi; RegHandle
0x14000c147  lea     rdx, _tlgEnableCallback; EnableCallback
0x14000c14e  mov     r8, rdi; CallbackContext
0x14000c151  call    cs:__imp_EventRegister
0x14000c157  test    eax, eax
0x14000c159  jnz     short loc_14000C16F
0x14000c15b  mov     r8, [rdi+8]
0x14000c15f  lea     edx, [rax+2]
0x14000c162  mov     rcx, [rsi]
0x14000c165  movzx   r9d, word ptr [r8]
0x14000c169  call    cs:__imp_EventSetInformation
0x14000c16f  mov     rax, [rbx]
0x14000c172  mov     rcx, rbx
0x14000c175  mov     dword ptr [rbx+14h], 1
0x14000c17c  mov     rax, [rax+8]
0x14000c180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c185  mov     rcx, [rsp+48h+var_18]
0x14000c18a  xor     rcx, rsp; StackCookie
0x14000c18d  call    __security_check_cookie
0x14000c192  mov     rbx, [rsp+48h+arg_10]
0x14000c197  mov     rsi, [rsp+48h+arg_18]
0x14000c19c  add     rsp, 40h
0x14000c1a0  pop     rdi
0x14000c1a1  retn
```
