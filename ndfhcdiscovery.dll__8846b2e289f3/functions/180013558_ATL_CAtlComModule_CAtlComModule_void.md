# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180013558`
- end: `0x1800135cf`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014560`

## callees

- `0x180013558`
- `0x180015010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800135ac`
- `KERNEL32!DeleteCriticalSection` at `0x1800135ac`

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
0x180013558  mov     [rsp+arg_0], rbx
0x18001355d  mov     [rsp+arg_8], rsi
0x180013562  push    rdi
0x180013563  sub     rsp, 20h
0x180013567  cmp     dword ptr [rcx], 0
0x18001356a  mov     rbx, rcx
0x18001356d  jz      short loc_1800135BE
0x18001356f  mov     rdi, [rcx+10h]
0x180013573  cmp     rdi, [rcx+18h]
0x180013577  jnb     short loc_1800135A8
0x180013579  mov     rsi, [rdi]
0x18001357c  test    rsi, rsi
0x18001357f  jz      short loc_18001359E
0x180013581  mov     rcx, [rsi+20h]
0x180013585  test    rcx, rcx
0x180013588  jz      short loc_180013596
0x18001358a  mov     rax, [rcx]
0x18001358d  mov     rax, [rax+10h]
0x180013591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013596  mov     qword ptr [rsi+20h], 0
0x18001359e  add     rdi, 8
0x1800135a2  cmp     rdi, [rbx+18h]
0x1800135a6  jb      short loc_180013579
0x1800135a8  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800135ac  call    cs:__imp_DeleteCriticalSection
0x1800135b3  nop     dword ptr [rax+rax+00h]
0x1800135b8  mov     dword ptr [rbx], 0
0x1800135be  mov     rbx, [rsp+28h+arg_0]
0x1800135c3  mov     rsi, [rsp+28h+arg_8]
0x1800135c8  add     rsp, 20h
0x1800135cc  pop     rdi
0x1800135cd  retn
```
