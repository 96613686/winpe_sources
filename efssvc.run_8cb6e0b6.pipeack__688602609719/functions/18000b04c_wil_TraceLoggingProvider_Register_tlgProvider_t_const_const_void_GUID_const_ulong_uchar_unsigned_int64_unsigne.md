# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x18000b04c`
- end: `0x18000b117`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `203`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180008db0`
- `0x180009d00`

## callees

- `0x18000b04c`
- `0x18000d1c0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000b0d7`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000b0d7`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000b0b9`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000b0b9`

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
0x18000b04c  mov     [rsp+arg_10], rbx
0x18000b051  mov     [rsp+arg_18], rsi
0x18000b056  push    rdi
0x18000b057  sub     rsp, 40h
0x18000b05b  mov     rax, cs:__security_cookie
0x18000b062  xor     rax, rsp
0x18000b065  mov     [rsp+48h+var_18], rax
0x18000b06a  mov     [rcx+8], rdx
0x18000b06e  lea     rsi, [rdx+20h]
0x18000b072  mov     byte ptr [rcx+10h], 1
0x18000b076  mov     rdi, rdx
0x18000b079  cmp     qword ptr [rsi], 0
0x18000b07d  mov     rbx, rcx
0x18000b080  mov     rax, [rdx+8]
0x18000b084  movups  xmm0, xmmword ptr [rax-10h]
0x18000b088  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x18000b08e  jz      short loc_18000B097
0x18000b090  mov     ecx, 5
0x18000b095  int     29h; Win8: RtlFailFast(ecx)
0x18000b097  mov     qword ptr [rdx+28h], 0
0x18000b09f  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x18000b0a4  mov     qword ptr [rdx+30h], 0
0x18000b0ac  mov     r9, rsi; RegHandle
0x18000b0af  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000b0b6  mov     r8, rdi; CallbackContext
0x18000b0b9  call    cs:__imp_EventRegister
0x18000b0c0  nop     dword ptr [rax+rax+00h]
0x18000b0c5  test    eax, eax
0x18000b0c7  jnz     short loc_18000B0E3
0x18000b0c9  mov     r8, [rdi+8]
0x18000b0cd  lea     edx, [rax+2]
0x18000b0d0  mov     rcx, [rsi]
0x18000b0d3  movzx   r9d, word ptr [r8]
0x18000b0d7  call    cs:__imp_EventSetInformation
0x18000b0de  nop     dword ptr [rax+rax+00h]
0x18000b0e3  mov     rax, [rbx]
0x18000b0e6  mov     rcx, rbx
0x18000b0e9  mov     dword ptr [rbx+14h], 1
0x18000b0f0  mov     rax, [rax+8]
0x18000b0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0f9  mov     rcx, [rsp+48h+var_18]
0x18000b0fe  xor     rcx, rsp; StackCookie
0x18000b101  call    __security_check_cookie
0x18000b106  mov     rbx, [rsp+48h+arg_10]
0x18000b10b  mov     rsi, [rsp+48h+arg_18]
0x18000b110  add     rsp, 40h
0x18000b114  pop     rdi
0x18000b115  retn
```
