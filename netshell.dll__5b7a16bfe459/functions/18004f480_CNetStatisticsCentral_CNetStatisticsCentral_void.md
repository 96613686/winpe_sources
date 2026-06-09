# CNetStatisticsCentral::~CNetStatisticsCentral(void)

- ea: `0x18004f480`
- end: `0x18004f511`
- name: `??1CNetStatisticsCentral@@UEAA@XZ`
- size: `145`
- prototype: `void __fastcall(CNetStatisticsCentral *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004f6a0`

## callees

- `0x180017ea0`
- `0x18001a7f8`
- `0x18004f480`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004f4be`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004f4be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f4b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f4b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f4ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f4ac`

## pseudocode

```c
void __fastcall CNetStatisticsCentral::~CNetStatisticsCentral(CNetStatisticsCentral *this)
{
  _QWORD **v2; // rdx
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  g_pnscCentral = 0;
  *(_QWORD *)this = &CNetStatisticsCentral::`vftable';
  EnterCriticalSection(&g_csStatmonData);
  LeaveCriticalSection(&g_csStatmonData);
  DeleteCriticalSection(&g_csStatmonData);
  v2 = (_QWORD **)*((_QWORD *)this + 10);
  *v2[1] = 0;
  v3 = *v2;
  if ( *v2 )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      std::_Deallocate<16>(v3, 0x18u);
      v3 = v4;
    }
    while ( v4 );
  }
  std::_Deallocate<16>(*((void **)this + 10), 0x18u);
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((__int64)this + 8);
}

```

## disassembly

```asm
0x18004f480  mov     [rsp+arg_0], rbx
0x18004f485  push    rdi
0x18004f486  sub     rsp, 20h
0x18004f48a  lea     rax, ??_7CNetStatisticsCentral@@6B@; const CNetStatisticsCentral::`vftable'
0x18004f491  mov     cs:?g_pnscCentral@@3PEAVCNetStatisticsCentral@@EA, 0; CNetStatisticsCentral * g_pnscCentral
0x18004f49c  mov     [rcx], rax
0x18004f49f  lea     rbx, ?g_csStatmonData@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csStatmonData
0x18004f4a6  mov     rdi, rcx
0x18004f4a9  mov     rcx, rbx; lpCriticalSection
0x18004f4ac  call    cs:__imp_EnterCriticalSection
0x18004f4b2  mov     rcx, rbx; lpCriticalSection
0x18004f4b5  call    cs:__imp_LeaveCriticalSection
0x18004f4bb  mov     rcx, rbx; lpCriticalSection
0x18004f4be  call    cs:__imp_DeleteCriticalSection
0x18004f4c4  mov     rdx, [rdi+50h]
0x18004f4c8  mov     rax, [rdx+8]
0x18004f4cc  mov     qword ptr [rax], 0
0x18004f4d3  mov     rcx, [rdx]
0x18004f4d6  test    rcx, rcx
0x18004f4d9  jz      short loc_18004F4F0
0x18004f4db  mov     rbx, [rcx]
0x18004f4de  mov     edx, 18h
0x18004f4e3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004f4e8  mov     rcx, rbx
0x18004f4eb  test    rbx, rbx
0x18004f4ee  jnz     short loc_18004F4DB
0x18004f4f0  mov     rcx, [rdi+50h]
0x18004f4f4  mov     edx, 18h
0x18004f4f9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004f4fe  lea     rcx, [rdi+8]
0x18004f502  mov     rbx, [rsp+28h+arg_0]
0x18004f507  add     rsp, 20h
0x18004f50b  pop     rdi
0x18004f50c  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
