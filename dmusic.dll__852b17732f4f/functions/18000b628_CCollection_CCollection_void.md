# CCollection::~CCollection(void)

- ea: `0x18000b628`
- end: `0x18000b6dd`
- name: `??1CCollection@@QEAA@XZ`
- size: `181`
- prototype: `void __fastcall(CCollection *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cc10`

## callees

- `0x18000b628`
- `0x18000ba24`
- `0x18000ef40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b6a3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b6a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b69a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b69a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b674`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b674`

## pseudocode

```c
void __fastcall CCollection::~CCollection(CCollection *this)
{
  _QWORD **v2; // rbx
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  _QWORD *v4; // rcx
  _QWORD *v5; // rcx
  CInstrument *v6; // rcx

  *(_QWORD *)this = &CCollection::`vftable'{for `IDirectMusicCollection'};
  *((_QWORD *)this + 1) = &CCollection::`vftable'{for `IPersistStream'};
  *((_QWORD *)this + 2) = &CCollection::`vftable'{for `IDirectMusicObject'};
  v2 = (_QWORD **)((char *)this + 248);
  if ( *((_DWORD *)this + 74) )
  {
    CCollection::Cleanup(this);
    v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 256);
    EnterCriticalSection(v3);
    if ( *v2 )
    {
      while ( 1 )
      {
        v4 = *v2;
        if ( !*v2 )
          break;
        *v2 = (_QWORD *)*v4;
        *v4 = 0;
      }
    }
    LeaveCriticalSection(v3);
    DeleteCriticalSection(v3);
  }
  _InterlockedDecrement(&g_cComponent);
  while ( 1 )
  {
    v5 = *v2;
    if ( !*v2 )
      break;
    *v2 = (_QWORD *)*v5;
    *v5 = 0;
    v6 = (CInstrument *)(v5 - 2);
    if ( v6 )
      CInstrument::Release(v6);
  }
}

```

## disassembly

```asm
0x18000b628  mov     [rsp+arg_0], rbx
0x18000b62d  push    rdi
0x18000b62e  sub     rsp, 20h
0x18000b632  mov     rdi, rcx
0x18000b635  lea     rax, ??_7CCollection@@6BIDirectMusicCollection@@@; const CCollection::`vftable'{for `IDirectMusicCollection'}
0x18000b63c  mov     [rcx], rax
0x18000b63f  lea     rax, ??_7CCollection@@6BIPersistStream@@@; const CCollection::`vftable'{for `IPersistStream'}
0x18000b646  mov     [rcx+8], rax
0x18000b64a  lea     rax, ??_7CCollection@@6BIDirectMusicObject@@@; const CCollection::`vftable'{for `IDirectMusicObject'}
0x18000b651  mov     [rcx+10h], rax
0x18000b655  lea     rbx, [rcx+0F8h]
0x18000b65c  cmp     dword ptr [rcx+128h], 0
0x18000b663  jz      short loc_18000B6A9
0x18000b665  call    ?Cleanup@CCollection@@AEAAXXZ; CCollection::Cleanup(void)
0x18000b66a  add     rdi, 100h
0x18000b671  mov     rcx, rdi; lpCriticalSection
0x18000b674  call    cs:__imp_EnterCriticalSection
0x18000b67a  cmp     qword ptr [rbx], 0
0x18000b67e  jz      short loc_18000B697
0x18000b680  mov     rcx, [rbx]
0x18000b683  test    rcx, rcx
0x18000b686  jz      short loc_18000B697
0x18000b688  mov     rax, [rcx]
0x18000b68b  mov     [rbx], rax
0x18000b68e  mov     qword ptr [rcx], 0
0x18000b695  jmp     short loc_18000B680
0x18000b697  mov     rcx, rdi; lpCriticalSection
0x18000b69a  call    cs:__imp_LeaveCriticalSection
0x18000b6a0  mov     rcx, rdi; lpCriticalSection
0x18000b6a3  call    cs:__imp_DeleteCriticalSection
0x18000b6a9  lock dec cs:?g_cComponent@@3JA; long g_cComponent
0x18000b6b0  mov     rcx, [rbx]
0x18000b6b3  test    rcx, rcx
0x18000b6b6  jz      short loc_18000B6D2
0x18000b6b8  mov     rax, [rcx]
0x18000b6bb  mov     [rbx], rax
0x18000b6be  mov     qword ptr [rcx], 0
0x18000b6c5  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x18000b6c9  jz      short loc_18000B6B0
0x18000b6cb  call    ?Release@CInstrument@@UEAAKXZ; CInstrument::Release(void)
0x18000b6d0  jmp     short loc_18000B6B0
0x18000b6d2  mov     rbx, [rsp+28h+arg_0]
0x18000b6d7  add     rsp, 20h
0x18000b6db  pop     rdi
0x18000b6dc  retn
```
