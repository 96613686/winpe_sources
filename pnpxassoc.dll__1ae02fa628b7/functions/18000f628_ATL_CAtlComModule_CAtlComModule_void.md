# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000f628`
- end: `0x18000f698`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013300`

## callees

- `0x18000f628`
- `0x180014010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000f67c`
- `KERNEL32!DeleteCriticalSection` at `0x18000f67c`

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
0x18000f628  mov     [rsp+arg_0], rbx
0x18000f62d  mov     [rsp+arg_8], rsi
0x18000f632  push    rdi
0x18000f633  sub     rsp, 20h
0x18000f637  cmp     dword ptr [rcx], 0
0x18000f63a  mov     rbx, rcx
0x18000f63d  jz      short loc_18000F688
0x18000f63f  mov     rdi, [rcx+10h]
0x18000f643  cmp     rdi, [rcx+18h]
0x18000f647  jnb     short loc_18000F678
0x18000f649  mov     rsi, [rdi]
0x18000f64c  test    rsi, rsi
0x18000f64f  jz      short loc_18000F66E
0x18000f651  mov     rcx, [rsi+20h]
0x18000f655  test    rcx, rcx
0x18000f658  jz      short loc_18000F666
0x18000f65a  mov     rax, [rcx]
0x18000f65d  mov     rax, [rax+10h]
0x18000f661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f666  mov     qword ptr [rsi+20h], 0
0x18000f66e  add     rdi, 8
0x18000f672  cmp     rdi, [rbx+18h]
0x18000f676  jb      short loc_18000F649
0x18000f678  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000f67c  call    cs:__imp_DeleteCriticalSection
0x18000f682  mov     dword ptr [rbx], 0
0x18000f688  mov     rbx, [rsp+28h+arg_0]
0x18000f68d  mov     rsi, [rsp+28h+arg_8]
0x18000f692  add     rsp, 20h
0x18000f696  pop     rdi
0x18000f697  retn
```
