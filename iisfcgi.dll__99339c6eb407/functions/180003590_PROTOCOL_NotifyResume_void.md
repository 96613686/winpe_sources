# PROTOCOL::NotifyResume(void)

- ea: `0x180003590`
- end: `0x1800035f1`
- name: `?NotifyResume@PROTOCOL@@UEAAXXZ`
- size: `97`
- prototype: `void __fastcall(PROTOCOL *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003590`
- `0x1800035f8`
- `0x180006480`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800035a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800035a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800035bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800035bb`

## pseudocode

```c
void __fastcall PROTOCOL::NotifyResume(PROTOCOL *this)
{
  int v2; // esi

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v2 = PROTOCOL::PendReceive((PROTOCOL *)((char *)this - 16));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( v2 < 0 )
    APPLICATION::RealShutdown(*((APPLICATION **)this + 19), v2, 0, 0, 1);
}

```

## disassembly

```asm
0x180003590  mov     [rsp+arg_0], rbx
0x180003595  mov     [rsp+arg_8], rsi
0x18000359a  push    rdi
0x18000359b  sub     rsp, 30h
0x18000359f  mov     rdi, rcx
0x1800035a2  add     rcx, 30h ; '0'; lpCriticalSection
0x1800035a6  call    cs:__imp_EnterCriticalSection
0x1800035ac  lea     rcx, [rdi-10h]; this
0x1800035b0  call    ?PendReceive@PROTOCOL@@AEAAJXZ; PROTOCOL::PendReceive(void)
0x1800035b5  mov     esi, eax
0x1800035b7  lea     rcx, [rdi+30h]; lpCriticalSection
0x1800035bb  call    cs:__imp_LeaveCriticalSection
0x1800035c1  test    esi, esi
0x1800035c3  jns     short loc_1800035E1
0x1800035c5  mov     rcx, [rdi+98h]; this
0x1800035cc  xor     r9d, r9d; int
0x1800035cf  xor     r8d, r8d; unsigned int
0x1800035d2  mov     [rsp+38h+var_18], 1; int
0x1800035da  mov     edx, esi; int
0x1800035dc  call    ?RealShutdown@APPLICATION@@QEAAXJIHH@Z; APPLICATION::RealShutdown(long,uint,int,int)
0x1800035e1  mov     rbx, [rsp+38h+arg_0]
0x1800035e6  mov     rsi, [rsp+38h+arg_8]
0x1800035eb  add     rsp, 30h
0x1800035ef  pop     rdi
0x1800035f0  retn
```
