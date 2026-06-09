# IASTL::IASComponent::~IASComponent(void)

- ea: `0x18000d904`
- end: `0x18000d96b`
- name: `??1IASComponent@IASTL@@QEAA@XZ`
- size: `103`
- prototype: `void __fastcall(IASTL::IASComponent *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d6a0`
- `0x18000d9f0`

## callees

- `0x18000d904`

## import_xrefs

- `KERNEL32!Sleep` at `0x18000d914`
- `KERNEL32!Sleep` at `0x18000d914`
- `KERNEL32!DeleteCriticalSection` at `0x18000d95e`
- `KERNEL32!DeleteCriticalSection` at `0x18000d95e`
- `rtutils!TraceDeregisterW` at `0x18000d938`
- `rtutils!TraceDeregisterW` at `0x18000d938`

## pseudocode

```c
void __fastcall IASTL::IASComponent::~IASComponent(IASTL::IASComponent *this)
{
  while ( _InterlockedExchange(&lLocked, 1) )
    Sleep(5u);
  if ( !--lRefCount )
  {
    TraceDeregisterW(dwTraceID);
    dwTraceID = -1;
  }
  _InterlockedExchange(&lLocked, 0);
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x18000d904  push    rbx
0x18000d906  sub     rsp, 20h
0x18000d90a  mov     rbx, rcx
0x18000d90d  jmp     short loc_18000D91A
0x18000d90f  mov     ecx, 5; dwMilliseconds
0x18000d914  call    cs:__imp_Sleep
0x18000d91a  mov     eax, 1
0x18000d91f  xchg    eax, cs:lLocked
0x18000d925  test    eax, eax
0x18000d927  jnz     short loc_18000D90F
0x18000d929  sub     cs:lRefCount, 1
0x18000d930  jnz     short loc_18000D948
0x18000d932  mov     ecx, cs:dwTraceID; dwTraceID
0x18000d938  call    cs:__imp_TraceDeregisterW
0x18000d93e  mov     cs:dwTraceID, 0FFFFFFFFh
0x18000d948  xor     eax, eax
0x18000d94a  xchg    eax, cs:lLocked
0x18000d950  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000d954  cmp     byte ptr [rcx+28h], 0
0x18000d958  jz      short loc_18000D965
0x18000d95a  mov     byte ptr [rcx+28h], 0
0x18000d95e  call    cs:__imp_DeleteCriticalSection
0x18000d964  nop
0x18000d965  add     rsp, 20h
0x18000d969  pop     rbx
0x18000d96a  retn
```
