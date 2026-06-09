# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000c388`
- end: `0x18000c3f8`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ce70`

## callees

- `0x18000c388`
- `0x18000d010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000c3dc`
- `KERNEL32!DeleteCriticalSection` at `0x18000c3dc`

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
0x18000c388  mov     [rsp+arg_0], rbx
0x18000c38d  mov     [rsp+arg_8], rsi
0x18000c392  push    rdi
0x18000c393  sub     rsp, 20h
0x18000c397  cmp     dword ptr [rcx], 0
0x18000c39a  mov     rbx, rcx
0x18000c39d  jz      short loc_18000C3E8
0x18000c39f  mov     rdi, [rcx+10h]
0x18000c3a3  cmp     rdi, [rcx+18h]
0x18000c3a7  jnb     short loc_18000C3D8
0x18000c3a9  mov     rsi, [rdi]
0x18000c3ac  test    rsi, rsi
0x18000c3af  jz      short loc_18000C3CE
0x18000c3b1  mov     rcx, [rsi+20h]
0x18000c3b5  test    rcx, rcx
0x18000c3b8  jz      short loc_18000C3C6
0x18000c3ba  mov     rax, [rcx]
0x18000c3bd  mov     rax, [rax+10h]
0x18000c3c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3c6  mov     qword ptr [rsi+20h], 0
0x18000c3ce  add     rdi, 8
0x18000c3d2  cmp     rdi, [rbx+18h]
0x18000c3d6  jb      short loc_18000C3A9
0x18000c3d8  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000c3dc  call    cs:__imp_DeleteCriticalSection
0x18000c3e2  mov     dword ptr [rbx], 0
0x18000c3e8  mov     rbx, [rsp+28h+arg_0]
0x18000c3ed  mov     rsi, [rsp+28h+arg_8]
0x18000c3f2  add     rsp, 20h
0x18000c3f6  pop     rdi
0x18000c3f7  retn
```
