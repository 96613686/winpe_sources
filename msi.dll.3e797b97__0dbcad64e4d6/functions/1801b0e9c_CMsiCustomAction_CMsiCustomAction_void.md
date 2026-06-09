# CMsiCustomAction::~CMsiCustomAction(void)

- ea: `0x1801b0e9c`
- end: `0x1801b1106`
- name: `??1CMsiCustomAction@@IEAA@XZ`
- size: `618`
- prototype: `void __fastcall(CMsiCustomAction *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1801b2f40`

## callees

- `0x1800b3314`
- `0x1801b0e9c`
- `0x180266010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1801b1041`
- `KERNEL32!DeleteCriticalSection` at `0x1801b1054`
- `KERNEL32!DeleteCriticalSection` at `0x1801b1067`
- `KERNEL32!DeleteCriticalSection` at `0x1801b107a`
- `KERNEL32!DeleteCriticalSection` at `0x1801b1041`
- `KERNEL32!DeleteCriticalSection` at `0x1801b1054`
- `KERNEL32!DeleteCriticalSection` at `0x1801b1067`
- `KERNEL32!DeleteCriticalSection` at `0x1801b107a`
- `KERNEL32!CloseHandle` at `0x1801b0f00`
- `KERNEL32!CloseHandle` at `0x1801b0f16`
- `KERNEL32!CloseHandle` at `0x1801b0f00`
- `KERNEL32!CloseHandle` at `0x1801b0f16`
- `KERNEL32!GlobalFree` at `0x1801b0f47`
- `KERNEL32!GlobalFree` at `0x1801b0f73`
- `KERNEL32!GlobalFree` at `0x1801b0fa0`
- `KERNEL32!GlobalFree` at `0x1801b109d`
- `KERNEL32!GlobalFree` at `0x1801b10d1`
- `KERNEL32!GlobalFree` at `0x1801b0f47`
- `KERNEL32!GlobalFree` at `0x1801b0f73`
- `KERNEL32!GlobalFree` at `0x1801b0fa0`
- `KERNEL32!GlobalFree` at `0x1801b109d`
- `KERNEL32!GlobalFree` at `0x1801b10d1`

## pseudocode

```c
void __fastcall CMsiCustomAction::~CMsiCustomAction(CMsiCustomAction *this)
{
  __int64 v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  int i; // esi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx

  *(_QWORD *)this = &CMsiCustomAction::`vftable';
  v2 = *((_QWORD *)this + 11);
  if ( v2 )
  {
    if ( *((_DWORD *)this + 24) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 32LL))(v2);
      *((_DWORD *)this + 24) = 0;
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 16LL))(*((_QWORD *)this + 11));
    *((_QWORD *)this + 11) = 0;
  }
  *((_BYTE *)this + 24) = 0;
  v3 = (void *)*((_QWORD *)this + 10);
  if ( v3 )
    CloseHandle(v3);
  v4 = (void *)*((_QWORD *)this + 15);
  if ( v4 != (void *)-1LL )
    CloseHandle(v4);
  for ( i = 0; i < *((_DWORD *)this + 84); ++i )
  {
    v6 = *(void **)(*((_QWORD *)this + 41) + 40LL * i);
    if ( v6 )
    {
      GlobalFree(v6);
      *(_QWORD *)(*((_QWORD *)this + 41) + 40LL * i) = 0;
    }
    v7 = *(void **)(*((_QWORD *)this + 41) + 40LL * i + 8);
    if ( v7 )
    {
      GlobalFree(v7);
      *(_QWORD *)(*((_QWORD *)this + 41) + 40LL * i + 8) = 0;
    }
    v8 = *(void **)(*((_QWORD *)this + 41) + 40LL * i + 16);
    if ( v8 )
    {
      GlobalFree(v8);
      *(_QWORD *)(*((_QWORD *)this + 41) + 40LL * i + 16) = 0;
    }
    v9 = *(_QWORD *)(*((_QWORD *)this + 41) + 40LL * i + 32);
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *(_QWORD *)(*((_QWORD *)this + 41) + 40LL * i + 32) = 0;
    }
  }
  v10 = *((_QWORD *)this + 93);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)this + 93) = 0;
  }
  v11 = *((_QWORD *)this + 94);
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    *((_QWORD *)this + 94) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 288));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 792));
  FreeMsiMalloc(0);
  if ( *((int *)this + 84) > 10 )
    GlobalFree(*((HGLOBAL *)this + 41));
  *((_DWORD *)this + 84) = 10;
  *((_QWORD *)this + 41) = (char *)this + 344;
  if ( *((int *)this + 46) > 4 )
    GlobalFree(*((HGLOBAL *)this + 22));
  *((_QWORD *)this + 22) = (char *)this + 192;
  *((_DWORD *)this + 46) = 4;
}

```

## disassembly

```asm
0x1801b0e9c  mov     [rsp+arg_0], rbx
0x1801b0ea1  mov     [rsp+arg_8], rsi
0x1801b0ea6  push    rdi
0x1801b0ea7  sub     rsp, 20h
0x1801b0eab  lea     rax, ??_7CMsiCustomAction@@6B@; const CMsiCustomAction::`vftable'
0x1801b0eb2  mov     rbx, rcx
0x1801b0eb5  mov     [rcx], rax
0x1801b0eb8  mov     rcx, [rcx+58h]
0x1801b0ebc  test    rcx, rcx
0x1801b0ebf  jz      short loc_1801B0EF3
0x1801b0ec1  mov     edx, [rbx+60h]
0x1801b0ec4  test    edx, edx
0x1801b0ec6  jz      short loc_1801B0EDB
0x1801b0ec8  mov     rax, [rcx]
0x1801b0ecb  mov     rax, [rax+20h]
0x1801b0ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0ed4  mov     dword ptr [rbx+60h], 0
0x1801b0edb  mov     rcx, [rbx+58h]
0x1801b0edf  mov     rax, [rcx]
0x1801b0ee2  mov     rax, [rax+10h]
0x1801b0ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0eeb  mov     qword ptr [rbx+58h], 0
0x1801b0ef3  mov     byte ptr [rbx+18h], 0
0x1801b0ef7  mov     rcx, [rbx+50h]; hObject
0x1801b0efb  test    rcx, rcx
0x1801b0efe  jz      short loc_1801B0F0C
0x1801b0f00  call    cs:__imp_CloseHandle
0x1801b0f07  nop     dword ptr [rax+rax+00h]
0x1801b0f0c  mov     rcx, [rbx+78h]; hObject
0x1801b0f10  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801b0f14  jz      short loc_1801B0F22
0x1801b0f16  call    cs:__imp_CloseHandle
0x1801b0f1d  nop     dword ptr [rax+rax+00h]
0x1801b0f22  xor     esi, esi
0x1801b0f24  cmp     [rbx+150h], esi
0x1801b0f2a  jle     loc_1801B0FF7
0x1801b0f30  movsxd  rax, esi
0x1801b0f33  lea     rdi, [rax+rax*4]
0x1801b0f37  mov     rax, [rbx+148h]
0x1801b0f3e  mov     rcx, [rax+rdi*8]; hMem
0x1801b0f42  test    rcx, rcx
0x1801b0f45  jz      short loc_1801B0F62
0x1801b0f47  call    cs:__imp_GlobalFree
0x1801b0f4e  nop     dword ptr [rax+rax+00h]
0x1801b0f53  mov     rax, [rbx+148h]
0x1801b0f5a  mov     qword ptr [rax+rdi*8], 0
0x1801b0f62  mov     rax, [rbx+148h]
0x1801b0f69  mov     rcx, [rax+rdi*8+8]; hMem
0x1801b0f6e  test    rcx, rcx
0x1801b0f71  jz      short loc_1801B0F8F
0x1801b0f73  call    cs:__imp_GlobalFree
0x1801b0f7a  nop     dword ptr [rax+rax+00h]
0x1801b0f7f  mov     rax, [rbx+148h]
0x1801b0f86  mov     qword ptr [rax+rdi*8+8], 0
0x1801b0f8f  mov     rax, [rbx+148h]
0x1801b0f96  mov     rcx, [rax+rdi*8+10h]; hMem
0x1801b0f9b  test    rcx, rcx
0x1801b0f9e  jz      short loc_1801B0FBC
0x1801b0fa0  call    cs:__imp_GlobalFree
0x1801b0fa7  nop     dword ptr [rax+rax+00h]
0x1801b0fac  mov     rax, [rbx+148h]
0x1801b0fb3  mov     qword ptr [rax+rdi*8+10h], 0
0x1801b0fbc  mov     rax, [rbx+148h]
0x1801b0fc3  mov     rcx, [rax+rdi*8+20h]
0x1801b0fc8  test    rcx, rcx
0x1801b0fcb  jz      short loc_1801B0FE9
0x1801b0fcd  mov     rax, [rcx]
0x1801b0fd0  mov     rax, [rax+10h]
0x1801b0fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b0fd9  mov     rax, [rbx+148h]
0x1801b0fe0  mov     qword ptr [rax+rdi*8+20h], 0
0x1801b0fe9  inc     esi
0x1801b0feb  cmp     esi, [rbx+150h]
0x1801b0ff1  jl      loc_1801B0F30
0x1801b0ff7  mov     rcx, [rbx+2E8h]
0x1801b0ffe  test    rcx, rcx
0x1801b1001  jz      short loc_1801B101A
0x1801b1003  mov     rax, [rcx]
0x1801b1006  mov     rax, [rax+10h]
0x1801b100a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b100f  mov     qword ptr [rbx+2E8h], 0
0x1801b101a  mov     rcx, [rbx+2F0h]
0x1801b1021  test    rcx, rcx
0x1801b1024  jz      short loc_1801B103D
0x1801b1026  mov     rax, [rcx]
0x1801b1029  mov     rax, [rax+10h]
0x1801b102d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b1032  mov     qword ptr [rbx+2F0h], 0
0x1801b103d  lea     rcx, [rbx+28h]; lpCriticalSection
0x1801b1041  call    cs:__imp_DeleteCriticalSection
0x1801b1048  nop     dword ptr [rax+rax+00h]
0x1801b104d  lea     rcx, [rbx+88h]; lpCriticalSection
0x1801b1054  call    cs:__imp_DeleteCriticalSection
0x1801b105b  nop     dword ptr [rax+rax+00h]
0x1801b1060  lea     rcx, [rbx+120h]; lpCriticalSection
0x1801b1067  call    cs:__imp_DeleteCriticalSection
0x1801b106e  nop     dword ptr [rax+rax+00h]
0x1801b1073  lea     rcx, [rbx+318h]; lpCriticalSection
0x1801b107a  call    cs:__imp_DeleteCriticalSection
0x1801b1081  nop     dword ptr [rax+rax+00h]
0x1801b1086  xor     ecx, ecx; bool
0x1801b1088  call    ?FreeMsiMalloc@@YAX_N@Z; FreeMsiMalloc(bool)
0x1801b108d  cmp     dword ptr [rbx+150h], 0Ah
0x1801b1094  jle     short loc_1801B10A9
0x1801b1096  mov     rcx, [rbx+148h]; hMem
0x1801b109d  call    cs:__imp_GlobalFree
0x1801b10a4  nop     dword ptr [rax+rax+00h]
0x1801b10a9  lea     rax, [rbx+158h]
0x1801b10b0  mov     dword ptr [rbx+150h], 0Ah
0x1801b10ba  mov     [rbx+148h], rax
0x1801b10c1  cmp     dword ptr [rbx+0B8h], 4
0x1801b10c8  jle     short loc_1801B10DD
0x1801b10ca  mov     rcx, [rbx+0B0h]; hMem
0x1801b10d1  call    cs:__imp_GlobalFree
0x1801b10d8  nop     dword ptr [rax+rax+00h]
0x1801b10dd  mov     rsi, [rsp+28h+arg_8]
0x1801b10e2  lea     rax, [rbx+0C0h]
0x1801b10e9  mov     [rbx+0B0h], rax
0x1801b10f0  mov     dword ptr [rbx+0B8h], 4
0x1801b10fa  mov     rbx, [rsp+28h+arg_0]
0x1801b10ff  add     rsp, 20h
0x1801b1103  pop     rdi
0x1801b1104  retn
```
