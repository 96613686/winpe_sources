# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18001fbb0`
- end: `0x18001fc20`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002fa50`

## callees

- `0x18001fbb0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fc04`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fc04`

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
0x18001fbb0  mov     [rsp+arg_0], rbx
0x18001fbb5  mov     [rsp+arg_8], rsi
0x18001fbba  push    rdi
0x18001fbbb  sub     rsp, 20h
0x18001fbbf  cmp     dword ptr [rcx], 0
0x18001fbc2  mov     rbx, rcx
0x18001fbc5  jz      short loc_18001FC10
0x18001fbc7  mov     rdi, [rcx+10h]
0x18001fbcb  cmp     rdi, [rcx+18h]
0x18001fbcf  jnb     short loc_18001FC00
0x18001fbd1  mov     rsi, [rdi]
0x18001fbd4  test    rsi, rsi
0x18001fbd7  jz      short loc_18001FBF6
0x18001fbd9  mov     rcx, [rsi+20h]
0x18001fbdd  test    rcx, rcx
0x18001fbe0  jz      short loc_18001FBEE
0x18001fbe2  mov     rax, [rcx]
0x18001fbe5  mov     rax, [rax+10h]
0x18001fbe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbee  mov     qword ptr [rsi+20h], 0
0x18001fbf6  add     rdi, 8
0x18001fbfa  cmp     rdi, [rbx+18h]
0x18001fbfe  jb      short loc_18001FBD1
0x18001fc00  lea     rcx, [rbx+20h]; lpCriticalSection
0x18001fc04  call    cs:__imp_DeleteCriticalSection
0x18001fc0a  mov     dword ptr [rbx], 0
0x18001fc10  mov     rbx, [rsp+28h+arg_0]
0x18001fc15  mov     rsi, [rsp+28h+arg_8]
0x18001fc1a  add     rsp, 20h
0x18001fc1e  pop     rdi
0x18001fc1f  retn
```
