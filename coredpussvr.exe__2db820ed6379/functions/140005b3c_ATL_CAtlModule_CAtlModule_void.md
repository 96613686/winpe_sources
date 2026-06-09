# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x140005b3c`
- end: `0x140005bec`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `176`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140005dc0`
- `0x140009370`

## callees

- `0x140001794`
- `0x140005b3c`
- `0x140008afc`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005bc1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005bc1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this, unsigned int a2)
{
  unsigned __int64 v3; // r14
  __int64 v4; // rsi
  _QWORD *v5; // r15
  _QWORD *v6; // rbx
  __int64 v7; // rcx

  v3 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v4 = v3 & -(__int64)(this != 0);
      if ( !v4 )
      {
        ATL::_AtlRaiseException(0xC0000005, a2);
        JUMPOUT(0x140005BEBLL);
      }
      v5 = *(_QWORD **)((v3 & -(__int64)(this != 0)) + 8);
      if ( v5 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v5)(v5[1]);
          v6 = (_QWORD *)v5[2];
          operator delete(v5);
          v5 = v6;
        }
        while ( v6 );
      }
      *(_QWORD *)(v4 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v7 = *((_QWORD *)this + 8);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v3 = 0;
  }
}

```

## disassembly

```asm
0x140005b3c  push    rbx
0x140005b3e  push    rsi
0x140005b3f  push    rdi
0x140005b40  push    r14
0x140005b42  push    r15
0x140005b44  sub     rsp, 20h
0x140005b48  mov     rdi, rcx
0x140005b4b  lea     r14, [rcx+8]
0x140005b4f  cmp     dword ptr [r14], 0
0x140005b53  jz      short loc_140005BD4
0x140005b55  cmp     qword ptr [rcx+10h], 0
0x140005b5a  jz      short loc_140005BA8
0x140005b5c  mov     rax, rcx
0x140005b5f  neg     rax
0x140005b62  sbb     rsi, rsi
0x140005b65  and     rsi, r14
0x140005b68  jz      short loc_140005BE1
0x140005b6a  mov     r15, [rsi+8]
0x140005b6e  test    r15, r15
0x140005b71  jz      short loc_140005B98
0x140005b73  mov     rcx, [r15+8]
0x140005b77  mov     rax, [r15]
0x140005b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b7f  mov     rbx, [r15+10h]
0x140005b83  mov     edx, 18h
0x140005b88  mov     rcx, r15; Block
0x140005b8b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005b90  mov     r15, rbx
0x140005b93  test    rbx, rbx
0x140005b96  jnz     short loc_140005B73
0x140005b98  mov     qword ptr [rsi+8], 0
0x140005ba0  mov     qword ptr [rdi+10h], 0
0x140005ba8  mov     rcx, [rdi+40h]
0x140005bac  test    rcx, rcx
0x140005baf  jz      short loc_140005BBD
0x140005bb1  mov     rax, [rcx]
0x140005bb4  mov     rax, [rax+10h]
0x140005bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005bbd  lea     rcx, [rdi+18h]; lpCriticalSection
0x140005bc1  call    cs:__imp_DeleteCriticalSection
0x140005bc8  nop     dword ptr [rax+rax+00h]
0x140005bcd  mov     dword ptr [r14], 0
0x140005bd4  add     rsp, 20h
0x140005bd8  pop     r15
0x140005bda  pop     r14
0x140005bdc  pop     rdi
0x140005bdd  pop     rsi
0x140005bde  pop     rbx
0x140005bdf  retn
0x140005be1  mov     ecx, 0C0000005h; unsigned int
0x140005be6  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
