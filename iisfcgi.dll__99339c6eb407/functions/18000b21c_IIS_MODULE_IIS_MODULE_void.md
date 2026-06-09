# IIS_MODULE::~IIS_MODULE(void)

- ea: `0x18000b21c`
- end: `0x18000b2ee`
- name: `??1IIS_MODULE@@UEAA@XZ`
- size: `210`
- prototype: `void __fastcall(IIS_MODULE *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000b33c`

## callees

- `0x180001048`
- `0x180009128`
- `0x18000b21c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b2b8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b2b8`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x18000b2d2`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x18000b2d2`

## pseudocode

```c
void __fastcall IIS_MODULE::~IIS_MODULE(IIS_MODULE *this)
{
  _QWORD **v2; // rdi
  _QWORD *v3; // rcx
  _QWORD *v4; // rax
  void *v5; // rcx
  FCGI_BUFFER *v6; // rcx

  *(_QWORD *)this = &IIS_MODULE::`vftable'{for `IAPPLICATION_CALLBACK'};
  v2 = (_QWORD **)((char *)this + 240);
  *((_QWORD *)this + 1) = &IIS_MODULE::`vftable'{for `IAPPLICATION_MANAGER_CALLBACK'};
  *((_QWORD *)this + 4) = &IIS_MODULE::`vftable'{for `CHttpModule'};
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == v2 )
      break;
    if ( (_QWORD **)v3[1] != v2 || (v4 = (_QWORD *)*v3, *(_QWORD **)(*v3 + 8LL) != v3) )
      __fastfail(3u);
    *v2 = v4;
    v4[1] = v2;
    FCGI_BUFFER::Free((FCGI_BUFFER *)(v3 - 4));
  }
  v5 = (void *)*((_QWORD *)this + 15);
  if ( v5 )
  {
    operator delete(v5);
    *((_QWORD *)this + 15) = 0;
  }
  v6 = (FCGI_BUFFER *)*((_QWORD *)this + 17);
  if ( v6 )
  {
    FCGI_BUFFER::Free(v6);
    *((_QWORD *)this + 17) = 0;
  }
  if ( *((_DWORD *)this + 39) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    *((_DWORD *)this + 39) = 0;
  }
  *((_DWORD *)this + 29) = 1768383334;
  MULTISZA::~MULTISZA((IIS_MODULE *)((char *)this + 176));
  *((_QWORD *)this + 4) = &CHttpModule::`vftable';
}

```

## disassembly

```asm
0x18000b21c  mov     [rsp+arg_0], rbx
0x18000b221  push    rdi
0x18000b222  sub     rsp, 20h
0x18000b226  lea     rax, ??_7IIS_MODULE@@6BIAPPLICATION_CALLBACK@@@; const IIS_MODULE::`vftable'{for `IAPPLICATION_CALLBACK'}
0x18000b22d  mov     rbx, rcx
0x18000b230  mov     [rcx], rax
0x18000b233  lea     rdi, [rcx+0F0h]
0x18000b23a  lea     rax, ??_7IIS_MODULE@@6BIAPPLICATION_MANAGER_CALLBACK@@@; const IIS_MODULE::`vftable'{for `IAPPLICATION_MANAGER_CALLBACK'}
0x18000b241  mov     [rcx+8], rax
0x18000b245  lea     rax, ??_7IIS_MODULE@@6BCHttpModule@@@; const IIS_MODULE::`vftable'{for `CHttpModule'}
0x18000b24c  mov     [rcx+20h], rax
0x18000b250  mov     rcx, [rdi]
0x18000b253  cmp     rcx, rdi
0x18000b256  jz      short loc_18000B280
0x18000b258  cmp     [rcx+8], rdi
0x18000b25c  jnz     short loc_18000B279
0x18000b25e  mov     rax, [rcx]
0x18000b261  cmp     [rax+8], rcx
0x18000b265  jnz     short loc_18000B279
0x18000b267  mov     [rdi], rax
0x18000b26a  add     rcx, 0FFFFFFFFFFFFFFE0h; this
0x18000b26e  mov     [rax+8], rdi
0x18000b272  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x18000b277  jmp     short loc_18000B250
0x18000b279  mov     ecx, 3
0x18000b27e  int     29h; Win8: RtlFailFast(ecx)
0x18000b280  mov     rcx, [rbx+78h]; Block
0x18000b284  xor     edi, edi
0x18000b286  test    rcx, rcx
0x18000b289  jz      short loc_18000B294
0x18000b28b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b290  mov     [rbx+78h], rdi
0x18000b294  mov     rcx, [rbx+88h]; this
0x18000b29b  test    rcx, rcx
0x18000b29e  jz      short loc_18000B2AC
0x18000b2a0  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x18000b2a5  mov     [rbx+88h], rdi
0x18000b2ac  cmp     [rbx+9Ch], edi
0x18000b2b2  jz      short loc_18000B2C4
0x18000b2b4  lea     rcx, [rbx+30h]; lpCriticalSection
0x18000b2b8  call    cs:__imp_DeleteCriticalSection
0x18000b2be  mov     [rbx+9Ch], edi
0x18000b2c4  lea     rcx, [rbx+0B0h]
0x18000b2cb  mov     dword ptr [rbx+74h], 69676366h
0x18000b2d2  call    cs:__imp_??1MULTISZA@@QEAA@XZ; MULTISZA::~MULTISZA(void)
0x18000b2d8  lea     rax, ??_7CHttpModule@@6B@; const CHttpModule::`vftable'
0x18000b2df  mov     [rbx+20h], rax
0x18000b2e3  mov     rbx, [rsp+28h+arg_0]
0x18000b2e8  add     rsp, 20h
0x18000b2ec  pop     rdi
0x18000b2ed  retn
```
