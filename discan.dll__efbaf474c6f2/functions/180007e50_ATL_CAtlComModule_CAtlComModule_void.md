# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180007e50`
- end: `0x180007ec0`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180038cd0`

## callees

- `0x180007e50`
- `0x180039010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007ea4`
- `KERNEL32!DeleteCriticalSection` at `0x180007ea4`

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
0x180007e50  mov     [rsp+arg_0], rbx
0x180007e55  mov     [rsp+arg_8], rsi
0x180007e5a  push    rdi
0x180007e5b  sub     rsp, 20h
0x180007e5f  cmp     dword ptr [rcx], 0
0x180007e62  mov     rbx, rcx
0x180007e65  jz      short loc_180007EB0
0x180007e67  mov     rdi, [rcx+10h]
0x180007e6b  cmp     rdi, [rcx+18h]
0x180007e6f  jnb     short loc_180007EA0
0x180007e71  mov     rsi, [rdi]
0x180007e74  test    rsi, rsi
0x180007e77  jz      short loc_180007E96
0x180007e79  mov     rcx, [rsi+20h]
0x180007e7d  test    rcx, rcx
0x180007e80  jz      short loc_180007E8E
0x180007e82  mov     rax, [rcx]
0x180007e85  mov     rax, [rax+10h]
0x180007e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e8e  mov     qword ptr [rsi+20h], 0
0x180007e96  add     rdi, 8
0x180007e9a  cmp     rdi, [rbx+18h]
0x180007e9e  jb      short loc_180007E71
0x180007ea0  lea     rcx, [rbx+20h]; lpCriticalSection
0x180007ea4  call    cs:__imp_DeleteCriticalSection
0x180007eaa  mov     dword ptr [rbx], 0
0x180007eb0  mov     rbx, [rsp+28h+arg_0]
0x180007eb5  mov     rsi, [rsp+28h+arg_8]
0x180007eba  add     rsp, 20h
0x180007ebe  pop     rdi
0x180007ebf  retn
```
