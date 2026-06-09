# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x180005584`
- end: `0x180005642`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `190`
- prototype: `void(wil::TraceLoggingProvider *__hidden this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180002eac`
- `0x180007fc0`
- `0x18000812c`

## callees

- `0x180005584`
- `0x180012040`
- `0x180013010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180005609`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180005609`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800055f1`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800055f1`

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
0x180005584  mov     [rsp+arg_10], rbx
0x180005589  mov     [rsp+arg_18], rsi
0x18000558e  push    rdi
0x18000558f  sub     rsp, 40h
0x180005593  mov     rax, cs:__security_cookie
0x18000559a  xor     rax, rsp
0x18000559d  mov     [rsp+48h+var_18], rax
0x1800055a2  mov     [rcx+8], rdx
0x1800055a6  lea     rsi, [rdx+20h]
0x1800055aa  mov     byte ptr [rcx+10h], 1
0x1800055ae  mov     rdi, rdx
0x1800055b1  cmp     qword ptr [rsi], 0
0x1800055b5  mov     rbx, rcx
0x1800055b8  mov     rax, [rdx+8]
0x1800055bc  movups  xmm0, xmmword ptr [rax-10h]
0x1800055c0  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x1800055c6  jz      short loc_1800055CF
0x1800055c8  mov     ecx, 5
0x1800055cd  int     29h; Win8: RtlFailFast(ecx)
0x1800055cf  mov     qword ptr [rdx+28h], 0
0x1800055d7  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x1800055dc  mov     qword ptr [rdx+30h], 0
0x1800055e4  mov     r9, rsi; RegHandle
0x1800055e7  lea     rdx, _tlgEnableCallback; EnableCallback
0x1800055ee  mov     r8, rdi; CallbackContext
0x1800055f1  call    cs:__imp_EventRegister
0x1800055f7  test    eax, eax
0x1800055f9  jnz     short loc_18000560F
0x1800055fb  mov     r8, [rdi+8]
0x1800055ff  lea     edx, [rax+2]
0x180005602  mov     rcx, [rsi]
0x180005605  movzx   r9d, word ptr [r8]
0x180005609  call    cs:__imp_EventSetInformation
0x18000560f  mov     rax, [rbx]
0x180005612  mov     rcx, rbx
0x180005615  mov     dword ptr [rbx+14h], 1
0x18000561c  mov     rax, [rax+8]
0x180005620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005625  mov     rcx, [rsp+48h+var_18]
0x18000562a  xor     rcx, rsp; StackCookie
0x18000562d  call    __security_check_cookie
0x180005632  mov     rbx, [rsp+48h+arg_10]
0x180005637  mov     rsi, [rsp+48h+arg_18]
0x18000563c  add     rsp, 40h
0x180005640  pop     rdi
0x180005641  retn
```
