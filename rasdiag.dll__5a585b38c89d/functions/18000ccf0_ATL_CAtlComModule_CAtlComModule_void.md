# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000ccf0`
- end: `0x18000cd67`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e690`

## callees

- `0x18000ccf0`
- `0x18000f010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000cd44`
- `KERNEL32!DeleteCriticalSection` at `0x18000cd44`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::~CAtlComModule(ATL::CAtlComModule *this)
{
  __int64 *i; // rdi
  __int64 v3; // rsi
  __int64 v4; // rcx

  if ( *(_DWORD *)this )
  {
    for ( i = (__int64 *)*((_QWORD *)this + 2); (unsigned __int64)i < *((_QWORD *)this + 3); ++i )
    {
      v3 = *i;
      if ( *i )
      {
        v4 = *(_QWORD *)(v3 + 32);
        if ( v4 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        *(_QWORD *)(v3 + 32) = 0;
      }
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18000ccf0  mov     [rsp+arg_0], rbx
0x18000ccf5  mov     [rsp+arg_8], rsi
0x18000ccfa  push    rdi
0x18000ccfb  sub     rsp, 20h
0x18000ccff  cmp     dword ptr [rcx], 0
0x18000cd02  mov     rbx, rcx
0x18000cd05  jz      short loc_18000CD56
0x18000cd07  mov     rdi, [rcx+10h]
0x18000cd0b  cmp     rdi, [rcx+18h]
0x18000cd0f  jnb     short loc_18000CD40
0x18000cd11  mov     rsi, [rdi]
0x18000cd14  test    rsi, rsi
0x18000cd17  jz      short loc_18000CD36
0x18000cd19  mov     rcx, [rsi+20h]
0x18000cd1d  test    rcx, rcx
0x18000cd20  jz      short loc_18000CD2E
0x18000cd22  mov     rax, [rcx]
0x18000cd25  mov     rax, [rax+10h]
0x18000cd29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd2e  mov     qword ptr [rsi+20h], 0
0x18000cd36  add     rdi, 8
0x18000cd3a  cmp     rdi, [rbx+18h]
0x18000cd3e  jb      short loc_18000CD11
0x18000cd40  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000cd44  call    cs:__imp_DeleteCriticalSection
0x18000cd4b  nop     dword ptr [rax+rax+00h]
0x18000cd50  mov     dword ptr [rbx], 0
0x18000cd56  mov     rbx, [rsp+28h+arg_0]
0x18000cd5b  mov     rsi, [rsp+28h+arg_8]
0x18000cd60  add     rsp, 20h
0x18000cd64  pop     rdi
0x18000cd65  retn
```
