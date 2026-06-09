# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180004054`
- end: `0x1800040c4`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009230`

## callees

- `0x180004054`
- `0x18000a010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800040a8`
- `KERNEL32!DeleteCriticalSection` at `0x1800040a8`

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
0x180004054  mov     [rsp+arg_0], rbx
0x180004059  mov     [rsp+arg_8], rsi
0x18000405e  push    rdi
0x18000405f  sub     rsp, 20h
0x180004063  cmp     dword ptr [rcx], 0
0x180004066  mov     rbx, rcx
0x180004069  jz      short loc_1800040B4
0x18000406b  mov     rdi, [rcx+10h]
0x18000406f  cmp     rdi, [rcx+18h]
0x180004073  jnb     short loc_1800040A4
0x180004075  mov     rsi, [rdi]
0x180004078  test    rsi, rsi
0x18000407b  jz      short loc_18000409A
0x18000407d  mov     rcx, [rsi+20h]
0x180004081  test    rcx, rcx
0x180004084  jz      short loc_180004092
0x180004086  mov     rax, [rcx]
0x180004089  mov     rax, [rax+10h]
0x18000408d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004092  mov     qword ptr [rsi+20h], 0
0x18000409a  add     rdi, 8
0x18000409e  cmp     rdi, [rbx+18h]
0x1800040a2  jb      short loc_180004075
0x1800040a4  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800040a8  call    cs:__imp_DeleteCriticalSection
0x1800040ae  mov     dword ptr [rbx], 0
0x1800040b4  mov     rbx, [rsp+28h+arg_0]
0x1800040b9  mov     rsi, [rsp+28h+arg_8]
0x1800040be  add     rsp, 20h
0x1800040c2  pop     rdi
0x1800040c3  retn
```
