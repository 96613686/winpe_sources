# CAssociationCallback::~CAssociationCallback(void)

- ea: `0x1400177a0`
- end: `0x140017836`
- name: `??1CAssociationCallback@@IEAA@XZ`
- size: `150`
- prototype: `void __fastcall(CAssociationCallback *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140018220`

## callees

- `0x140009090`
- `0x1400177a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14001782f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017818`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017818`

## pseudocode

```c
void __fastcall CAssociationCallback::~CAssociationCallback(CAssociationCallback *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  *(_QWORD *)this = &CAssociationCallback::`vftable'{for `IAepAssociationCallback'};
  *((_QWORD *)this + 1) = &CAssociationCallback::`vftable'{for `IDafPrivImpersonationToken'};
  *((_QWORD *)this + 2) = &CAssociationCallback::`vftable'{for `IServiceProvider'};
  v2 = (void *)*((_QWORD *)this + 5);
  if ( v2 )
    MIDL_user_free(v2);
  v3 = (void *)*((_QWORD *)this + 6);
  if ( v3 )
    MIDL_user_free(v3);
  v4 = (void *)*((_QWORD *)this + 8);
  if ( v4 )
    MIDL_user_free(v4);
  v5 = (void *)*((_QWORD *)this + 9);
  if ( v5 )
    MIDL_user_free(v5);
  v6 = (void *)*((_QWORD *)this + 11);
  if ( v6 )
    MIDL_user_free(v6);
  v7 = (void *)*((_QWORD *)this + 12);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 12) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
}

```

## disassembly

```asm
0x1400177a0  push    rbx
0x1400177a2  sub     rsp, 20h
0x1400177a6  lea     rax, ??_7CAssociationCallback@@6BIAepAssociationCallback@@@; const CAssociationCallback::`vftable'{for `IAepAssociationCallback'}
0x1400177ad  mov     rbx, rcx
0x1400177b0  mov     [rcx], rax
0x1400177b3  lea     rax, ??_7CAssociationCallback@@6BIDafPrivImpersonationToken@@@; const CAssociationCallback::`vftable'{for `IDafPrivImpersonationToken'}
0x1400177ba  mov     [rcx+8], rax
0x1400177be  lea     rax, ??_7CAssociationCallback@@6BIServiceProvider@@@; const CAssociationCallback::`vftable'{for `IServiceProvider'}
0x1400177c5  mov     [rcx+10h], rax
0x1400177c9  mov     rcx, [rcx+28h]; void *
0x1400177cd  test    rcx, rcx
0x1400177d0  jz      short loc_1400177D7
0x1400177d2  call    MIDL_user_free
0x1400177d7  mov     rcx, [rbx+30h]; void *
0x1400177db  test    rcx, rcx
0x1400177de  jz      short loc_1400177E5
0x1400177e0  call    MIDL_user_free
0x1400177e5  mov     rcx, [rbx+40h]; void *
0x1400177e9  test    rcx, rcx
0x1400177ec  jz      short loc_1400177F3
0x1400177ee  call    MIDL_user_free
0x1400177f3  mov     rcx, [rbx+48h]; void *
0x1400177f7  test    rcx, rcx
0x1400177fa  jz      short loc_140017801
0x1400177fc  call    MIDL_user_free
0x140017801  mov     rcx, [rbx+58h]; void *
0x140017805  test    rcx, rcx
0x140017808  jz      short loc_14001780F
0x14001780a  call    MIDL_user_free
0x14001780f  mov     rcx, [rbx+60h]; hObject
0x140017813  test    rcx, rcx
0x140017816  jz      short loc_140017826
0x140017818  call    cs:__imp_CloseHandle
0x14001781e  mov     qword ptr [rbx+60h], 0
0x140017826  lea     rcx, [rbx+70h]
0x14001782a  add     rsp, 20h
0x14001782e  pop     rbx
0x14001782f  jmp     cs:__imp_DeleteCriticalSection
```
