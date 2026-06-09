# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x1800145bc`
- end: `0x18001462c`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001b390`

## callees

- `0x1800145bc`
- `0x18001c010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180014610`
- `KERNEL32!DeleteCriticalSection` at `0x180014610`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800145bc  mov     [rsp+arg_0], rbx
0x1800145c1  mov     [rsp+arg_8], rsi
0x1800145c6  push    rdi
0x1800145c7  sub     rsp, 20h
0x1800145cb  cmp     dword ptr [rcx], 0
0x1800145ce  mov     rbx, rcx
0x1800145d1  jz      short loc_18001461C
0x1800145d3  mov     rdi, [rcx+10h]
0x1800145d7  cmp     rdi, [rcx+18h]
0x1800145db  jnb     short loc_18001460C
0x1800145dd  mov     rsi, [rdi]
0x1800145e0  test    rsi, rsi
0x1800145e3  jz      short loc_180014602
0x1800145e5  mov     rcx, [rsi+20h]
0x1800145e9  test    rcx, rcx
0x1800145ec  jz      short loc_1800145FA
0x1800145ee  mov     rax, [rcx]
0x1800145f1  mov     rax, [rax+10h]
0x1800145f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145fa  mov     qword ptr [rsi+20h], 0
0x180014602  add     rdi, 8
0x180014606  cmp     rdi, [rbx+18h]
0x18001460a  jb      short loc_1800145DD
0x18001460c  lea     rcx, [rbx+20h]; lpCriticalSection
0x180014610  call    cs:__imp_DeleteCriticalSection
0x180014616  mov     dword ptr [rbx], 0
0x18001461c  mov     rbx, [rsp+28h+arg_0]
0x180014621  mov     rsi, [rsp+28h+arg_8]
0x180014626  add     rsp, 20h
0x18001462a  pop     rdi
0x18001462b  retn
```
