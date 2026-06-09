# ATL::CAtlModule::Term(void)

- ea: `0x180005368`
- end: `0x180005420`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `184`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002960`
- `0x180005c40`
- `0x180006440`

## callees

- `0x180005368`
- `0x180005afc`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800053fc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800053fc`
- `ntdll!RtlFreeHeap` at `0x1800053c5`
- `ntdll!RtlFreeHeap` at `0x1800053c5`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this, unsigned int a2)
{
  unsigned __int64 v2; // r14
  __int64 v4; // rsi
  _QWORD *v5; // r15
  _QWORD *v6; // rbx
  __int64 v7; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v4 = v2 & -(__int64)(this != 0);
      if ( !v4 )
      {
        ATL::_AtlRaiseException(0xC0000005, a2);
        JUMPOUT(0x18000541FLL);
      }
      v5 = *(_QWORD **)((v2 & -(__int64)(this != 0)) + 8);
      if ( v5 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v5)(v5[1]);
          v6 = (_QWORD *)v5[2];
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
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
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x180005368  push    rbx
0x18000536a  push    rsi
0x18000536b  push    rdi
0x18000536c  push    r14
0x18000536e  push    r15
0x180005370  sub     rsp, 20h
0x180005374  lea     r14, [rcx+8]
0x180005378  mov     rdi, rcx
0x18000537b  cmp     dword ptr [r14], 0
0x18000537f  jz      loc_180005409
0x180005385  cmp     qword ptr [rcx+10h], 0
0x18000538a  jz      short loc_1800053E3
0x18000538c  mov     rax, rcx
0x18000538f  neg     rax
0x180005392  sbb     rsi, rsi
0x180005395  and     rsi, r14
0x180005398  jz      short loc_180005415
0x18000539a  mov     r15, [rsi+8]
0x18000539e  test    r15, r15
0x1800053a1  jz      short loc_1800053D3
0x1800053a3  mov     rcx, [r15+8]
0x1800053a7  mov     rax, [r15]
0x1800053aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053af  mov     rcx, gs:60h
0x1800053b8  mov     r8, r15; P
0x1800053bb  mov     rbx, [r15+10h]
0x1800053bf  xor     edx, edx; Flags
0x1800053c1  mov     rcx, [rcx+30h]; HeapHandle
0x1800053c5  call    cs:__imp_RtlFreeHeap
0x1800053cb  mov     r15, rbx
0x1800053ce  test    rbx, rbx
0x1800053d1  jnz     short loc_1800053A3
0x1800053d3  mov     qword ptr [rsi+8], 0
0x1800053db  mov     qword ptr [rdi+10h], 0
0x1800053e3  mov     rcx, [rdi+40h]
0x1800053e7  test    rcx, rcx
0x1800053ea  jz      short loc_1800053F8
0x1800053ec  mov     rax, [rcx]
0x1800053ef  mov     rax, [rax+10h]
0x1800053f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053f8  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800053fc  call    cs:__imp_DeleteCriticalSection
0x180005402  mov     dword ptr [r14], 0
0x180005409  add     rsp, 20h
0x18000540d  pop     r15
0x18000540f  pop     r14
0x180005411  pop     rdi
0x180005412  pop     rsi
0x180005413  pop     rbx
0x180005414  retn
0x180005415  mov     ecx, 0C0000005h; unsigned int
0x18000541a  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
