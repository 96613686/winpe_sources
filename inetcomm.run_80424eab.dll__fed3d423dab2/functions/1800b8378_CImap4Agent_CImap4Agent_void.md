# CImap4Agent::~CImap4Agent(void)

- ea: `0x1800b8378`
- end: `0x1800b8477`
- name: `??1CImap4Agent@@MEAA@XZ`
- size: `255`
- prototype: `void __fastcall(CImap4Agent *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x1800b84c8`

## callees

- `0x180002098`
- `0x180029a10`
- `0x1800b8378`
- `0x1800ba0a0`
- `0x1800ba5b0`
- `0x1800c4058`
- `0x1800c552c`
- `0x1800cd010`

## import_xrefs

- `ADVAPI32!CryptReleaseContext` at `0x1800b8418`
- `ADVAPI32!CryptReleaseContext` at `0x1800b8418`
- `KERNEL32!DeleteCriticalSection` at `0x1800b843e`
- `KERNEL32!DeleteCriticalSection` at `0x1800b844b`
- `KERNEL32!DeleteCriticalSection` at `0x1800b8458`
- `KERNEL32!DeleteCriticalSection` at `0x1800b843e`
- `KERNEL32!DeleteCriticalSection` at `0x1800b844b`
- `KERNEL32!DeleteCriticalSection` at `0x1800b8458`

## pseudocode

```c
void __fastcall CImap4Agent::~CImap4Agent(CImap4Agent *this)
{
  CIxpBase *v2; // rdi
  __int64 v3; // rcx
  HCRYPTPROV v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &CImap4Agent::`vftable';
  v2 = (CImap4Agent *)((char *)this + 8);
  *((_QWORD *)this + 1) = &CImap4Agent::`vftable'{for `CPrivateUnknown'};
  *((_QWORD *)this + 5) = &CImap4Agent::`vftable'{for `IInternetTransport'};
  *((_QWORD *)this + 6) = &CImap4Agent::`vftable'{for `IInternetTransportW'};
  *((_QWORD *)this + 7) = &CImap4Agent::`vftable'{for `IAsyncConnCB'};
  *((_QWORD *)this + 8) = &CNNTPTransport::`vftable'{for `IAsyncConnPrompt'};
  CImap4Agent::DropConnection(this);
  CImap4Agent::FreeAllData(this, -2147467259);
  v3 = *((_QWORD *)this + 638);
  if ( v3 )
  {
    *((_QWORD *)this + 638) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 4840);
  v4 = *((_QWORD *)this + 699);
  if ( v4 )
    CryptReleaseContext(v4, 0);
  v5 = (void *)*((_QWORD *)this + 700);
  if ( v5 )
    operator delete(v5);
  CIxpBase::Reset(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 4872));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 4912));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 4952));
  _InterlockedDecrement(&g_cRef);
  CIxpBase::~CIxpBase(v2);
}

```

## disassembly

```asm
0x1800b8378  mov     [rsp+arg_0], rbx
0x1800b837d  push    rdi
0x1800b837e  sub     rsp, 20h
0x1800b8382  lea     rax, ??_7CImap4Agent@@6B@; const CImap4Agent::`vftable'
0x1800b8389  mov     rbx, rcx
0x1800b838c  mov     [rcx], rax
0x1800b838f  lea     rdi, [rcx+8]
0x1800b8393  lea     rax, ??_7CImap4Agent@@6BCPrivateUnknown@@@; const CImap4Agent::`vftable'{for `CPrivateUnknown'}
0x1800b839a  mov     [rdi], rax
0x1800b839d  lea     rax, ??_7CImap4Agent@@6BIInternetTransport@@@; const CImap4Agent::`vftable'{for `IInternetTransport'}
0x1800b83a4  mov     [rcx+28h], rax
0x1800b83a8  lea     rax, ??_7CImap4Agent@@6BIInternetTransportW@@@; const CImap4Agent::`vftable'{for `IInternetTransportW'}
0x1800b83af  mov     [rcx+30h], rax
0x1800b83b3  lea     rax, ??_7CImap4Agent@@6BIAsyncConnCB@@@; const CImap4Agent::`vftable'{for `IAsyncConnCB'}
0x1800b83ba  mov     [rcx+38h], rax
0x1800b83be  lea     rax, ??_7CNNTPTransport@@6BIAsyncConnPrompt@@@; const CNNTPTransport::`vftable'{for `IAsyncConnPrompt'}
0x1800b83c5  mov     [rcx+40h], rax
0x1800b83c9  call    ?DropConnection@CImap4Agent@@UEAAJXZ; CImap4Agent::DropConnection(void)
0x1800b83ce  mov     edx, 80004005h; int
0x1800b83d3  mov     rcx, rbx; this
0x1800b83d6  call    ?FreeAllData@CImap4Agent@@AEAAXJ@Z; CImap4Agent::FreeAllData(long)
0x1800b83db  mov     rcx, [rbx+13F0h]
0x1800b83e2  test    rcx, rcx
0x1800b83e5  jz      short loc_1800B83FE
0x1800b83e7  mov     qword ptr [rbx+13F0h], 0
0x1800b83f2  mov     rax, [rcx]
0x1800b83f5  mov     rax, [rax+10h]
0x1800b83f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b83fe  lea     rcx, [rbx+12E8h]
0x1800b8405  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800b840a  mov     rcx, [rbx+15D8h]; hProv
0x1800b8411  test    rcx, rcx
0x1800b8414  jz      short loc_1800B841E
0x1800b8416  xor     edx, edx; dwFlags
0x1800b8418  call    cs:__imp_CryptReleaseContext
0x1800b841e  mov     rcx, [rbx+15E0h]; Block
0x1800b8425  test    rcx, rcx
0x1800b8428  jz      short loc_1800B842F
0x1800b842a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b842f  mov     rcx, rdi; this
0x1800b8432  call    ?Reset@CIxpBase@@IEAAXXZ; CIxpBase::Reset(void)
0x1800b8437  lea     rcx, [rbx+1308h]; lpCriticalSection
0x1800b843e  call    cs:__imp_DeleteCriticalSection
0x1800b8444  lea     rcx, [rbx+1330h]; lpCriticalSection
0x1800b844b  call    cs:__imp_DeleteCriticalSection
0x1800b8451  lea     rcx, [rbx+1358h]; lpCriticalSection
0x1800b8458  call    cs:__imp_DeleteCriticalSection
0x1800b845e  lock dec cs:?g_cRef@@3JA; long g_cRef
0x1800b8465  mov     rcx, rdi; this
0x1800b8468  mov     rbx, [rsp+28h+arg_0]
0x1800b846d  add     rsp, 20h
0x1800b8471  pop     rdi
0x1800b8472  jmp     ??1CIxpBase@@MEAA@XZ; CIxpBase::~CIxpBase(void)
```
