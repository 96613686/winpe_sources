# wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))

- ea: `0x140004660`
- end: `0x14000471a`
- name: `?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z`
- size: `186`
- prototype: `void __fastcall(wil::TraceLoggingProvider *this, const struct _tlgProvider_t *const, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140004418`
- `0x1400044e0`

## callees

- `0x140004660`
- `0x14001e050`
- `0x14001f010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1400046bd`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1400046bd`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1400046d8`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1400046d8`

## pseudocode

```c
void __fastcall wil::TraceLoggingProvider::Register(
        wil::TraceLoggingProvider *this,
        const struct _tlgProvider_t *const a2,
        void (*a3)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))
{
  bool v5; // zf
  __int64 v6; // rax
  GUID ProviderId; // [rsp+20h] [rbp-28h] BYREF

  *((_QWORD *)this + 1) = a2;
  *((_BYTE *)this + 16) = 1;
  v5 = *((_QWORD *)a2 + 4) == 0;
  ProviderId = *(GUID *)(*((_QWORD *)a2 + 1) - 16LL);
  if ( !v5 )
    __fastfail(5u);
  *((_QWORD *)a2 + 5) = 0;
  *((_QWORD *)a2 + 6) = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, a2, (PREGHANDLE)a2 + 4) )
    EventSetInformation(
      *((_QWORD *)a2 + 4),
      2,
      *((_QWORD *)a2 + 1),
      **((unsigned __int16 **)a2 + 1),
      *(_QWORD *)&ProviderId.Data1,
      *(_QWORD *)ProviderId.Data4);
  v6 = *(_QWORD *)this;
  *((_DWORD *)this + 5) = 1;
  (*(void (__fastcall **)(wil::TraceLoggingProvider *))(v6 + 8))(this);
}

```

## disassembly

```asm
0x140004660  mov     [rsp+arg_10], rbx
0x140004665  mov     [rsp+arg_18], rsi
0x14000466a  push    rdi
0x14000466b  sub     rsp, 40h
0x14000466f  mov     rax, cs:__security_cookie
0x140004676  xor     rax, rsp
0x140004679  mov     [rsp+48h+var_18], rax
0x14000467e  mov     [rcx+8], rdx
0x140004682  mov     rdi, rdx
0x140004685  mov     byte ptr [rcx+10h], 1
0x140004689  mov     rbx, rcx
0x14000468c  cmp     qword ptr [rdx+20h], 0
0x140004691  mov     rax, [rdx+8]
0x140004695  movups  xmm0, xmmword ptr [rax-10h]
0x140004699  movups  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x14000469e  jnz     short loc_140004711
0x1400046a0  xor     eax, eax
0x1400046a2  lea     r9, [rdx+20h]; RegHandle
0x1400046a6  mov     [rdx+28h], rax
0x1400046aa  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x1400046af  mov     [rdx+30h], rax
0x1400046b3  mov     r8, rdi; CallbackContext
0x1400046b6  lea     rdx, _tlgEnableCallback; EnableCallback
0x1400046bd  call    cs:__imp_EventRegister
0x1400046c3  test    eax, eax
0x1400046c5  jnz     short loc_1400046DE
0x1400046c7  mov     r8, [rdi+8]
0x1400046cb  mov     edx, 2
0x1400046d0  mov     rcx, [rdi+20h]
0x1400046d4  movzx   r9d, word ptr [r8]
0x1400046d8  call    cs:__imp_EventSetInformation
0x1400046de  mov     rax, [rbx]
0x1400046e1  mov     rcx, rbx
0x1400046e4  mov     dword ptr [rbx+14h], 1
0x1400046eb  mov     rax, [rax+8]
0x1400046ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046f4  mov     rcx, [rsp+48h+var_18]
0x1400046f9  xor     rcx, rsp; StackCookie
0x1400046fc  call    __security_check_cookie
0x140004701  mov     rbx, [rsp+48h+arg_10]
0x140004706  mov     rsi, [rsp+48h+arg_18]
0x14000470b  add     rsp, 40h
0x14000470f  pop     rdi
0x140004710  retn
0x140004711  mov     ecx, 5
0x140004716  int     29h; Win8: RtlFailFast(ecx)
0x140004718  jmp     short loc_1400046A0
```
