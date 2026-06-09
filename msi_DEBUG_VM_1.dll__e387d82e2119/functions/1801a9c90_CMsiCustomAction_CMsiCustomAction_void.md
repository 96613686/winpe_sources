# CMsiCustomAction::~CMsiCustomAction(void)

- ea: `0x1801a9c90`
- end: `0x1801a9eb7`
- name: `??1CMsiCustomAction@@IEAA@XZ`
- size: `551`
- prototype: `void __fastcall(CMsiCustomAction *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1801abba0`

## callees

- `0x1800af818`
- `0x1801a9c90`
- `0x18025c010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1801a9e17`
- `KERNEL32!DeleteCriticalSection` at `0x1801a9e24`
- `KERNEL32!DeleteCriticalSection` at `0x1801a9e31`
- `KERNEL32!DeleteCriticalSection` at `0x1801a9e3e`
- `KERNEL32!DeleteCriticalSection` at `0x1801a9e17`
- `KERNEL32!DeleteCriticalSection` at `0x1801a9e24`
- `KERNEL32!DeleteCriticalSection` at `0x1801a9e31`
- `KERNEL32!DeleteCriticalSection` at `0x1801a9e3e`
- `KERNEL32!CloseHandle` at `0x1801a9cf4`
- `KERNEL32!CloseHandle` at `0x1801a9d04`
- `KERNEL32!CloseHandle` at `0x1801a9cf4`
- `KERNEL32!CloseHandle` at `0x1801a9d04`
- `KERNEL32!GlobalFree` at `0x1801a9d2f`
- `KERNEL32!GlobalFree` at `0x1801a9d55`
- `KERNEL32!GlobalFree` at `0x1801a9d7c`
- `KERNEL32!GlobalFree` at `0x1801a9e5b`
- `KERNEL32!GlobalFree` at `0x1801a9e89`
- `KERNEL32!GlobalFree` at `0x1801a9d2f`
- `KERNEL32!GlobalFree` at `0x1801a9d55`
- `KERNEL32!GlobalFree` at `0x1801a9d7c`
- `KERNEL32!GlobalFree` at `0x1801a9e5b`
- `KERNEL32!GlobalFree` at `0x1801a9e89`

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
0x1801a9c90  mov     [rsp+arg_0], rbx
0x1801a9c95  mov     [rsp+arg_8], rsi
0x1801a9c9a  push    rdi
0x1801a9c9b  sub     rsp, 20h
0x1801a9c9f  lea     rax, ??_7CMsiCustomAction@@6B@; const CMsiCustomAction::`vftable'
0x1801a9ca6  mov     rbx, rcx
0x1801a9ca9  mov     [rcx], rax
0x1801a9cac  mov     rcx, [rcx+58h]
0x1801a9cb0  test    rcx, rcx
0x1801a9cb3  jz      short loc_1801A9CE7
0x1801a9cb5  mov     edx, [rbx+60h]
0x1801a9cb8  test    edx, edx
0x1801a9cba  jz      short loc_1801A9CCF
0x1801a9cbc  mov     rax, [rcx]
0x1801a9cbf  mov     rax, [rax+20h]
0x1801a9cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a9cc8  mov     dword ptr [rbx+60h], 0
0x1801a9ccf  mov     rcx, [rbx+58h]
0x1801a9cd3  mov     rax, [rcx]
0x1801a9cd6  mov     rax, [rax+10h]
0x1801a9cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a9cdf  mov     qword ptr [rbx+58h], 0
0x1801a9ce7  mov     byte ptr [rbx+18h], 0
0x1801a9ceb  mov     rcx, [rbx+50h]; hObject
0x1801a9cef  test    rcx, rcx
0x1801a9cf2  jz      short loc_1801A9CFA
0x1801a9cf4  call    cs:__imp_CloseHandle
0x1801a9cfa  mov     rcx, [rbx+78h]; hObject
0x1801a9cfe  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801a9d02  jz      short loc_1801A9D0A
0x1801a9d04  call    cs:__imp_CloseHandle
0x1801a9d0a  xor     esi, esi
0x1801a9d0c  cmp     [rbx+150h], esi
0x1801a9d12  jle     loc_1801A9DCD
0x1801a9d18  movsxd  rax, esi
0x1801a9d1b  lea     rdi, [rax+rax*4]
0x1801a9d1f  mov     rax, [rbx+148h]
0x1801a9d26  mov     rcx, [rax+rdi*8]; hMem
0x1801a9d2a  test    rcx, rcx
0x1801a9d2d  jz      short loc_1801A9D44
0x1801a9d2f  call    cs:__imp_GlobalFree
0x1801a9d35  mov     rax, [rbx+148h]
0x1801a9d3c  mov     qword ptr [rax+rdi*8], 0
0x1801a9d44  mov     rax, [rbx+148h]
0x1801a9d4b  mov     rcx, [rax+rdi*8+8]; hMem
0x1801a9d50  test    rcx, rcx
0x1801a9d53  jz      short loc_1801A9D6B
0x1801a9d55  call    cs:__imp_GlobalFree
0x1801a9d5b  mov     rax, [rbx+148h]
0x1801a9d62  mov     qword ptr [rax+rdi*8+8], 0
0x1801a9d6b  mov     rax, [rbx+148h]
0x1801a9d72  mov     rcx, [rax+rdi*8+10h]; hMem
0x1801a9d77  test    rcx, rcx
0x1801a9d7a  jz      short loc_1801A9D92
0x1801a9d7c  call    cs:__imp_GlobalFree
0x1801a9d82  mov     rax, [rbx+148h]
0x1801a9d89  mov     qword ptr [rax+rdi*8+10h], 0
0x1801a9d92  mov     rax, [rbx+148h]
0x1801a9d99  mov     rcx, [rax+rdi*8+20h]
0x1801a9d9e  test    rcx, rcx
0x1801a9da1  jz      short loc_1801A9DBF
0x1801a9da3  mov     rax, [rcx]
0x1801a9da6  mov     rax, [rax+10h]
0x1801a9daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a9daf  mov     rax, [rbx+148h]
0x1801a9db6  mov     qword ptr [rax+rdi*8+20h], 0
0x1801a9dbf  inc     esi
0x1801a9dc1  cmp     esi, [rbx+150h]
0x1801a9dc7  jl      loc_1801A9D18
0x1801a9dcd  mov     rcx, [rbx+2E8h]
0x1801a9dd4  test    rcx, rcx
0x1801a9dd7  jz      short loc_1801A9DF0
0x1801a9dd9  mov     rax, [rcx]
0x1801a9ddc  mov     rax, [rax+10h]
0x1801a9de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a9de5  mov     qword ptr [rbx+2E8h], 0
0x1801a9df0  mov     rcx, [rbx+2F0h]
0x1801a9df7  test    rcx, rcx
0x1801a9dfa  jz      short loc_1801A9E13
0x1801a9dfc  mov     rax, [rcx]
0x1801a9dff  mov     rax, [rax+10h]
0x1801a9e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a9e08  mov     qword ptr [rbx+2F0h], 0
0x1801a9e13  lea     rcx, [rbx+28h]; lpCriticalSection
0x1801a9e17  call    cs:__imp_DeleteCriticalSection
0x1801a9e1d  lea     rcx, [rbx+88h]; lpCriticalSection
0x1801a9e24  call    cs:__imp_DeleteCriticalSection
0x1801a9e2a  lea     rcx, [rbx+120h]; lpCriticalSection
0x1801a9e31  call    cs:__imp_DeleteCriticalSection
0x1801a9e37  lea     rcx, [rbx+318h]; lpCriticalSection
0x1801a9e3e  call    cs:__imp_DeleteCriticalSection
0x1801a9e44  xor     ecx, ecx; bool
0x1801a9e46  call    ?FreeMsiMalloc@@YAX_N@Z; FreeMsiMalloc(bool)
0x1801a9e4b  cmp     dword ptr [rbx+150h], 0Ah
0x1801a9e52  jle     short loc_1801A9E61
0x1801a9e54  mov     rcx, [rbx+148h]; hMem
0x1801a9e5b  call    cs:__imp_GlobalFree
0x1801a9e61  lea     rax, [rbx+158h]
0x1801a9e68  mov     dword ptr [rbx+150h], 0Ah
0x1801a9e72  mov     [rbx+148h], rax
0x1801a9e79  cmp     dword ptr [rbx+0B8h], 4
0x1801a9e80  jle     short loc_1801A9E8F
0x1801a9e82  mov     rcx, [rbx+0B0h]; hMem
0x1801a9e89  call    cs:__imp_GlobalFree
0x1801a9e8f  mov     rsi, [rsp+28h+arg_8]
0x1801a9e94  lea     rax, [rbx+0C0h]
0x1801a9e9b  mov     [rbx+0B0h], rax
0x1801a9ea2  mov     dword ptr [rbx+0B8h], 4
0x1801a9eac  mov     rbx, [rsp+28h+arg_0]
0x1801a9eb1  add     rsp, 20h
0x1801a9eb5  pop     rdi
0x1801a9eb6  retn
```
