# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x18000cfe4`
- end: `0x18000d08d`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *this, int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d7e0`
- `0x18005b5c0`

## callees

- `0x1800028b0`
- `0x18000cfe4`
- `0x180013354`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d069`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d069`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this, int a2, unsigned int a3)
{
  unsigned __int64 v4; // r14
  __int64 v5; // rsi
  _QWORD *v6; // r15
  _QWORD *v7; // rbx
  __int64 v8; // rcx

  v4 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v5 = v4 & -(__int64)(this != 0);
      if ( !v5 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC0000005LL, a2, a3);
        JUMPOUT(0x18000D08CLL);
      }
      v6 = *(_QWORD **)((v4 & -(__int64)(this != 0)) + 8);
      if ( v6 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v6)(v6[1]);
          v7 = (_QWORD *)v6[2];
          operator delete(v6);
          v6 = v7;
        }
        while ( v7 );
      }
      *(_QWORD *)(v5 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v8 = *((_QWORD *)this + 8);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v4 = 0;
  }
}

```

## disassembly

```asm
0x18000cfe4  push    rbx
0x18000cfe6  push    rsi
0x18000cfe7  push    rdi
0x18000cfe8  push    r14
0x18000cfea  push    r15
0x18000cfec  sub     rsp, 20h
0x18000cff0  mov     rdi, rcx
0x18000cff3  lea     r14, [rcx+8]
0x18000cff7  cmp     dword ptr [r14], 0
0x18000cffb  jz      short loc_18000D076
0x18000cffd  cmp     qword ptr [rcx+10h], 0
0x18000d002  jz      short loc_18000D050
0x18000d004  mov     rax, rcx
0x18000d007  neg     rax
0x18000d00a  sbb     rsi, rsi
0x18000d00d  and     rsi, r14
0x18000d010  jz      short loc_18000D082
0x18000d012  mov     r15, [rsi+8]
0x18000d016  test    r15, r15
0x18000d019  jz      short loc_18000D040
0x18000d01b  mov     rcx, [r15+8]
0x18000d01f  mov     rax, [r15]
0x18000d022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d027  mov     rbx, [r15+10h]
0x18000d02b  mov     edx, 18h
0x18000d030  mov     rcx, r15; Block
0x18000d033  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d038  mov     r15, rbx
0x18000d03b  test    rbx, rbx
0x18000d03e  jnz     short loc_18000D01B
0x18000d040  mov     qword ptr [rsi+8], 0
0x18000d048  mov     qword ptr [rdi+10h], 0
0x18000d050  mov     rcx, [rdi+40h]
0x18000d054  test    rcx, rcx
0x18000d057  jz      short loc_18000D065
0x18000d059  mov     rax, [rcx]
0x18000d05c  mov     rax, [rax+10h]
0x18000d060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d065  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000d069  call    cs:__imp_DeleteCriticalSection
0x18000d06f  mov     dword ptr [r14], 0
0x18000d076  add     rsp, 20h
0x18000d07a  pop     r15
0x18000d07c  pop     r14
0x18000d07e  pop     rdi
0x18000d07f  pop     rsi
0x18000d080  pop     rbx
0x18000d081  retn
0x18000d082  mov     ecx, 0C0000005h; this
0x18000d087  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
