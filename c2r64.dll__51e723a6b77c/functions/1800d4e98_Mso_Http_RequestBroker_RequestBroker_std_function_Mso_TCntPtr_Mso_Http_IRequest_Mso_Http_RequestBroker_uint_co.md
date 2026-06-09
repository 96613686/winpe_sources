# Mso::Http::RequestBroker::RequestBroker(std::function<Mso::TCntPtr<Mso::Http::IRequest> (Mso::Http::RequestBroker &,uint)> const &)

- ea: `0x1800d4e98`
- end: `0x1800d4f80`
- name: `??0RequestBroker@Http@Mso@@QEAA@AEBV?$function@$$A6A?AV?$TCntPtr@VIRequest@Http@Mso@@@Mso@@AEAVRequestBroker@Http@2@I@Z@std@@@Z`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800d5270`

## callees

- `0x18000f4c0`
- `0x180052cd0`
- `0x1800d4e70`
- `0x1800d4e98`
- `0x180146090`

## import_xrefs

- `KERNEL32!CreateEventExW` at `0x1800d4f2a`
- `KERNEL32!CreateEventExW` at `0x1800d4f2a`
- `KERNEL32!CloseHandle` at `0x1800d4f4a`
- `KERNEL32!CloseHandle` at `0x1800d4f4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Mso::Http::RequestBroker::RequestBroker(__int64 a1, __int64 a2)
{
  __int64 (__fastcall ***v4)(_QWORD, __int64); // rcx
  HANDLE Event; // rbx
  void *v6; // rcx

  *(_DWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &Mso::Http::RequestBroker::`vftable';
  std::unordered_map<Mso::Http::IRequest const *,Mso::TCntPtr<Mso::Http::IRequest>>::unordered_map<Mso::Http::IRequest const *,Mso::TCntPtr<Mso::Http::IRequest>>(a1 + 16);
  std::_Mutex_base::_Mutex_base((std::_Mutex_base *)(a1 + 80), 256);
  *(_QWORD *)(a1 + 160) = 0;
  *(_BYTE *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 232) = 0;
  v4 = *(__int64 (__fastcall ****)(_QWORD, __int64))(a2 + 56);
  if ( v4 )
    *(_QWORD *)(a1 + 232) = (**v4)(v4, a1 + 176);
  Event = CreateEventExW(0, 0, 3u, 0x1F0003u);
  v6 = *(void **)(a1 + 160);
  if ( v6 )
  {
    *(_QWORD *)(a1 + 160) = 0;
    CloseHandle(v6);
  }
  *(_QWORD *)(a1 + 160) = Event;
  if ( !Event )
    CrashWithRecovery(0x598304u, 0);
  return a1;
}

```

## disassembly

```asm
0x1800d4e98  mov     [rsp+arg_10], rbx
0x1800d4e9d  mov     [rsp+arg_18], rsi
0x1800d4ea2  mov     [rsp+arg_0], rcx
0x1800d4ea7  push    rdi
0x1800d4ea8  sub     rsp, 20h
0x1800d4eac  mov     rbx, rdx
0x1800d4eaf  mov     rdi, rcx
0x1800d4eb2  mov     dword ptr [rcx+8], 1
0x1800d4eb9  lea     rax, ??_7RequestBroker@Http@Mso@@6B@; const Mso::Http::RequestBroker::`vftable'
0x1800d4ec0  mov     [rcx], rax
0x1800d4ec3  add     rcx, 10h
0x1800d4ec7  call    ??0?$unordered_map@PEBVIRequest@Http@Mso@@V?$TCntPtr@VIRequest@Http@Mso@@@3@U?$hash@PEBVIRequest@Http@Mso@@@std@@U?$equal_to@PEBVIRequest@Http@Mso@@@6@V?$allocator@U?$pair@QEBVIRequest@Http@Mso@@V?$TCntPtr@VIRequest@Http@Mso@@@3@@std@@@6@@std@@QEAA@XZ; std::unordered_map<Mso::Http::IRequest const *,Mso::TCntPtr<Mso::Http::IRequest>>::unordered_map<Mso::Http::IRequest const *,Mso::TCntPtr<Mso::Http::IRequest>>(void)
0x1800d4ecc  lea     rcx, [rdi+50h]; this
0x1800d4ed0  mov     edx, 100h; int
0x1800d4ed5  call    ??0_Mutex_base@std@@QEAA@H@Z; std::_Mutex_base::_Mutex_base(int)
0x1800d4eda  mov     qword ptr [rdi+0A0h], 0
0x1800d4ee5  mov     byte ptr [rdi+0A8h], 0
0x1800d4eec  lea     rsi, [rdi+0B0h]
0x1800d4ef3  mov     [rsp+28h+arg_8], rsi
0x1800d4ef8  mov     qword ptr [rsi+38h], 0
0x1800d4f00  mov     rcx, [rbx+38h]
0x1800d4f04  test    rcx, rcx
0x1800d4f07  jz      short loc_1800D4F1C
0x1800d4f09  mov     rax, [rcx]
0x1800d4f0c  mov     rdx, rsi
0x1800d4f0f  mov     rax, [rax]
0x1800d4f12  call    cs:__guard_dispatch_icall_fptr
0x1800d4f18  mov     [rsi+38h], rax
0x1800d4f1c  xor     edx, edx; lpName
0x1800d4f1e  xor     ecx, ecx; lpEventAttributes
0x1800d4f20  mov     r9d, 1F0003h; dwDesiredAccess
0x1800d4f26  lea     r8d, [rdx+3]; dwFlags
0x1800d4f2a  call    cs:__imp_CreateEventExW
0x1800d4f30  mov     rbx, rax
0x1800d4f33  mov     rcx, [rdi+0A0h]; hObject
0x1800d4f3a  test    rcx, rcx
0x1800d4f3d  jz      short loc_1800D4F51
0x1800d4f3f  mov     qword ptr [rdi+0A0h], 0
0x1800d4f4a  call    cs:__imp_CloseHandle
0x1800d4f50  nop
0x1800d4f51  mov     [rdi+0A0h], rbx
0x1800d4f58  test    rbx, rbx
0x1800d4f5b  jnz     short loc_1800D4F6D
0x1800d4f5d  xor     edx, edx; struct CrashContext *
0x1800d4f5f  mov     ecx, 598304h; unsigned int
0x1800d4f64  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800d4f6a  jmp     short $+2
0x1800d4f6c  nop
0x1800d4f6d  mov     rax, rdi
0x1800d4f70  mov     rbx, [rsp+28h+arg_10]
0x1800d4f75  mov     rsi, [rsp+28h+arg_18]
0x1800d4f7a  add     rsp, 20h
0x1800d4f7e  pop     rdi
0x1800d4f7f  retn
```
