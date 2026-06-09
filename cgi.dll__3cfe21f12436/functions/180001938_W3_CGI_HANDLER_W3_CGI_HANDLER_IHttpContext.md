# W3_CGI_HANDLER::W3_CGI_HANDLER(IHttpContext *)

- ea: `0x180001938`
- end: `0x180001a92`
- name: `??0W3_CGI_HANDLER@@QEAA@PEAVIHttpContext@@@Z`
- size: `346`
- prototype: `W3_CGI_HANDLER *__fastcall(W3_CGI_HANDLER *__hidden this, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000259c`

## callees

- `0x180001938`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800019ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800019ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001a28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001a28`

## pseudocode

```c
W3_CGI_HANDLER *__fastcall W3_CGI_HANDLER::W3_CGI_HANDLER(W3_CGI_HANDLER *this, struct IHttpContext *a2)
{
  struct _LIST_ENTRY *v4; // rbx
  struct _LIST_ENTRY *Flink; // rax
  __int64 v6; // rax
  void (__fastcall ***v7)(_QWORD, __int64, __int64); // rbx

  *(_QWORD *)this = &W3_CGI_HANDLER::`vftable';
  *((_QWORD *)this + 3) = -1;
  v4 = (struct _LIST_ENTRY *)((char *)this + 8344);
  *((_QWORD *)this + 4) = -1;
  *((_QWORD *)this + 1032) = 0;
  *((_QWORD *)this + 1036) = (char *)this + 8256;
  *((_DWORD *)this + 2074) = 32;
  *((_WORD *)this + 4150) = 256;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 15) = 0;
  *((_DWORD *)this + 2076) = 0;
  *((_DWORD *)this + 2090) = 0;
  *((_QWORD *)this + 1046) = 0;
  *((_QWORD *)this + 1049) = 0;
  *((_DWORD *)this + 2100) = 0;
  *((_QWORD *)this + 6) = a2;
  *((_DWORD *)this + 14) = -1;
  *(_OWORD *)((char *)this + 8312) = 0;
  *(_OWORD *)((char *)this + 8328) = 0;
  *((_QWORD *)this + 1044) = (char *)this + 8344;
  *((_QWORD *)this + 1043) = (char *)this + 8344;
  *((_QWORD *)this + 1048) = (char *)this + 8376;
  *((_QWORD *)this + 1047) = (char *)this + 8376;
  EnterCriticalSection(&W3_CGI_HANDLER::sm_CgiListLock);
  Flink = W3_CGI_HANDLER::sm_CgiListHead.Flink;
  if ( W3_CGI_HANDLER::sm_CgiListHead.Flink->Blink != &W3_CGI_HANDLER::sm_CgiListHead )
    __fastfail(3u);
  v4->Blink = &W3_CGI_HANDLER::sm_CgiListHead;
  v4->Flink = Flink;
  Flink->Blink = v4;
  W3_CGI_HANDLER::sm_CgiListHead.Flink = v4;
  LeaveCriticalSection(&W3_CGI_HANDLER::sm_CgiListLock);
  v6 = (**(__int64 (__fastcall ***)(struct IHttpContext *))a2)(a2);
  v7 = (void (__fastcall ***)(_QWORD, __int64, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
  (**v7)(v7, 26, 1);
  (**v7)(v7, 27, 1);
  return this;
}

```

## disassembly

```asm
0x180001938  mov     [rsp+arg_0], rbx
0x18000193d  mov     [rsp+arg_8], rsi
0x180001942  push    rdi
0x180001943  sub     rsp, 20h
0x180001947  mov     rdi, rcx
0x18000194a  lea     rax, ??_7W3_CGI_HANDLER@@6B@; const W3_CGI_HANDLER::`vftable'
0x180001951  mov     [rcx], rax
0x180001954  xorps   xmm0, xmm0
0x180001957  xor     ecx, ecx
0x180001959  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000195d  mov     rsi, rdx
0x180001960  mov     [rdi+18h], rax
0x180001964  lea     rbx, [rdi+2098h]
0x18000196b  mov     [rdi+20h], rax
0x18000196f  lea     rax, [rdi+2040h]
0x180001976  mov     [rax], rcx
0x180001979  mov     [rax+20h], rax
0x18000197d  mov     dword ptr [rax+28h], 20h ; ' '
0x180001984  mov     word ptr [rax+2Ch], 100h
0x18000198a  lea     rax, [rdi+20B8h]
0x180001991  mov     [rdi+8], rcx
0x180001995  mov     [rdi+10h], rcx
0x180001999  mov     [rdi+28h], rcx
0x18000199d  mov     [rdi+3Ch], ecx
0x1800019a0  mov     [rdi+2070h], ecx
0x1800019a6  mov     [rdi+20A8h], ecx
0x1800019ac  mov     [rdi+20B0h], rcx
0x1800019b3  mov     [rdi+20C8h], rcx
0x1800019ba  mov     [rdi+20D0h], ecx
0x1800019c0  lea     rcx, ?sm_CgiListLock@W3_CGI_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800019c7  mov     [rdi+30h], rdx
0x1800019cb  mov     dword ptr [rdi+38h], 0FFFFFFFFh
0x1800019d2  movups  xmmword ptr [rdi+2078h], xmm0
0x1800019d9  movups  xmmword ptr [rdi+2088h], xmm0
0x1800019e0  mov     [rbx+8], rbx
0x1800019e4  mov     [rbx], rbx
0x1800019e7  mov     [rax+8], rax
0x1800019eb  mov     [rax], rax
0x1800019ee  call    cs:__imp_EnterCriticalSection
0x1800019f4  mov     rax, cs:?sm_CgiListHead@W3_CGI_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY W3_CGI_HANDLER::sm_CgiListHead
0x1800019fb  lea     rcx, ?sm_CgiListHead@W3_CGI_HANDLER@@0U_LIST_ENTRY@@A; _LIST_ENTRY W3_CGI_HANDLER::sm_CgiListHead
0x180001a02  cmp     [rax+8], rcx
0x180001a06  jz      short loc_180001A0F
0x180001a08  mov     ecx, 3
0x180001a0d  int     29h; Win8: RtlFailFast(ecx)
0x180001a0f  mov     [rbx+8], rcx
0x180001a13  lea     rcx, ?sm_CgiListLock@W3_CGI_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001a1a  mov     [rbx], rax
0x180001a1d  mov     [rax+8], rbx
0x180001a21  mov     cs:?sm_CgiListHead@W3_CGI_HANDLER@@0U_LIST_ENTRY@@A, rbx; _LIST_ENTRY W3_CGI_HANDLER::sm_CgiListHead
0x180001a28  call    cs:__imp_LeaveCriticalSection
0x180001a2e  mov     rax, [rsi]
0x180001a31  mov     rcx, rsi
0x180001a34  mov     rax, [rax]
0x180001a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a3c  mov     rdx, rax
0x180001a3f  mov     rcx, [rax]
0x180001a42  mov     rax, [rcx+18h]
0x180001a46  mov     rcx, rdx
0x180001a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a4e  mov     rbx, rax
0x180001a51  mov     edx, 1Ah
0x180001a56  mov     rcx, [rax]
0x180001a59  lea     r8d, [rdx-19h]
0x180001a5d  mov     rax, [rcx]
0x180001a60  mov     rcx, rbx
0x180001a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a68  mov     rcx, [rbx]
0x180001a6b  mov     edx, 1Bh
0x180001a70  mov     rax, [rcx]
0x180001a73  lea     r8d, [rdx-1Ah]
0x180001a77  mov     rcx, rbx
0x180001a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a7f  mov     rbx, [rsp+28h+arg_0]
0x180001a84  mov     rax, rdi
0x180001a87  mov     rsi, [rsp+28h+arg_8]
0x180001a8c  add     rsp, 20h
0x180001a90  pop     rdi
0x180001a91  retn
```
