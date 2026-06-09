# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180024bd4`
- end: `0x180024c4b`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026aa0`

## callees

- `0x180024bd4`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024c28`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024c28`

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
0x180024bd4  mov     [rsp+arg_0], rbx
0x180024bd9  mov     [rsp+arg_8], rsi
0x180024bde  push    rdi
0x180024bdf  sub     rsp, 20h
0x180024be3  cmp     dword ptr [rcx], 0
0x180024be6  mov     rbx, rcx
0x180024be9  jz      short loc_180024C3A
0x180024beb  mov     rdi, [rcx+10h]
0x180024bef  cmp     rdi, [rcx+18h]
0x180024bf3  jnb     short loc_180024C24
0x180024bf5  mov     rsi, [rdi]
0x180024bf8  test    rsi, rsi
0x180024bfb  jz      short loc_180024C1A
0x180024bfd  mov     rcx, [rsi+20h]
0x180024c01  test    rcx, rcx
0x180024c04  jz      short loc_180024C12
0x180024c06  mov     rax, [rcx]
0x180024c09  mov     rax, [rax+10h]
0x180024c0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c12  mov     qword ptr [rsi+20h], 0
0x180024c1a  add     rdi, 8
0x180024c1e  cmp     rdi, [rbx+18h]
0x180024c22  jb      short loc_180024BF5
0x180024c24  lea     rcx, [rbx+20h]; lpCriticalSection
0x180024c28  call    cs:__imp_DeleteCriticalSection
0x180024c2f  nop     dword ptr [rax+rax+00h]
0x180024c34  mov     dword ptr [rbx], 0
0x180024c3a  mov     rbx, [rsp+28h+arg_0]
0x180024c3f  mov     rsi, [rsp+28h+arg_8]
0x180024c44  add     rsp, 20h
0x180024c48  pop     rdi
0x180024c49  retn
```
