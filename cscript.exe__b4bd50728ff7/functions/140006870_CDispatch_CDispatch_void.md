# CDispatch::~CDispatch(void)

- ea: `0x140006870`
- end: `0x1400068e4`
- name: `??1CDispatch@@UEAA@XZ`
- size: `116`
- prototype: `void __fastcall(CDispatch *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140006680`
- `0x140006750`
- `0x140008e60`
- `0x140012d0c`
- `0x1400150c0`

## callees

- `0x140006870`
- `0x140017010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140006898`
- `KERNEL32!EnterCriticalSection` at `0x140006898`
- `KERNEL32!LeaveCriticalSection` at `0x1400068c2`
- `KERNEL32!LeaveCriticalSection` at `0x1400068c2`

## pseudocode

```c
void __fastcall CDispatch::~CDispatch(CDispatch *this)
{
  bool v1; // zf
  __int64 v3; // rdi
  __int64 v4; // rcx

  v1 = *((_BYTE *)this + 48) == 0;
  *(_QWORD *)this = &CDispatch::`vftable';
  if ( !v1 )
  {
    v3 = *((_QWORD *)this + 5);
    EnterCriticalSection(&CDispatch::s_oCS);
    v4 = *(_QWORD *)(v3 + 56);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *(_QWORD *)(v3 + 56) = 0;
    LeaveCriticalSection(&CDispatch::s_oCS);
  }
  *(_QWORD *)this = &CUnknown::`vftable';
  _InterlockedDecrement(&Global::g_cObjects);
}

```

## disassembly

```asm
0x140006870  mov     [rsp+arg_0], rbx
0x140006875  push    rdi
0x140006876  sub     rsp, 20h
0x14000687a  cmp     byte ptr [rcx+30h], 0
0x14000687e  lea     rax, ??_7CDispatch@@6B@; const CDispatch::`vftable'
0x140006885  mov     [rcx], rax
0x140006888  mov     rbx, rcx
0x14000688b  jz      short loc_1400068C8
0x14000688d  mov     rdi, [rcx+28h]
0x140006891  lea     rcx, ?s_oCS@CDispatch@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140006898  call    cs:__imp_EnterCriticalSection
0x14000689e  mov     rcx, [rdi+38h]
0x1400068a2  test    rcx, rcx
0x1400068a5  jz      short loc_1400068B3
0x1400068a7  mov     rax, [rcx]
0x1400068aa  mov     rax, [rax+10h]
0x1400068ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068b3  lea     rcx, ?s_oCS@CDispatch@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400068ba  mov     qword ptr [rdi+38h], 0
0x1400068c2  call    cs:__imp_LeaveCriticalSection
0x1400068c8  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x1400068cf  mov     [rbx], rax
0x1400068d2  lock dec cs:?g_cObjects@Global@@2JA; long Global::g_cObjects
0x1400068d9  mov     rbx, [rsp+28h+arg_0]
0x1400068de  add     rsp, 20h
0x1400068e2  pop     rdi
0x1400068e3  retn
```
