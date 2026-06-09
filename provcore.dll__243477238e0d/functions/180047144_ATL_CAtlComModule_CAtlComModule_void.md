# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180047144`
- end: `0x1800471b4`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18006e370`

## callees

- `0x180047144`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180047198`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180047198`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::~CAtlComModule(ATL::CAtlComModule *this)
{
  ATL::_ATL_OBJMAP_ENTRY30 **i; // rdi
  ATL::_ATL_OBJMAP_ENTRY30 *v3; // rsi
  IUnknown *pCF; // rcx

  if ( this->cbSize )
  {
    for ( i = this->m_ppAutoObjMapFirst; i < this->m_ppAutoObjMapLast; ++i )
    {
      v3 = *i;
      if ( *i )
      {
        pCF = v3->pCF;
        if ( pCF )
          pCF->Release(pCF);
        v3->pCF = 0;
      }
    }
    DeleteCriticalSection(&this->m_csObjMap.m_sec);
    this->cbSize = 0;
  }
}

```

## disassembly

```asm
0x180047144  mov     [rsp+arg_0], rbx
0x180047149  mov     [rsp+arg_8], rsi
0x18004714e  push    rdi
0x18004714f  sub     rsp, 20h
0x180047153  cmp     dword ptr [this], 0
0x180047156  mov     rbx, this
0x180047159  jz      short loc_1800471A4
0x18004715b  mov     rdi, [this+10h]
0x18004715f  cmp     rdi, [this+18h]
0x180047163  jnb     short loc_180047194
0x180047165  mov     rsi, [rdi]
0x180047168  test    rsi, rsi
0x18004716b  jz      short loc_18004718A
0x18004716d  mov     this, [rsi+20h]
0x180047171  test    this, this
0x180047174  jz      short loc_180047182
0x180047176  mov     rax, [this]
0x180047179  mov     rax, [rax+10h]
0x18004717d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047182  mov     qword ptr [rsi+20h], 0
0x18004718a  add     rdi, 8
0x18004718e  cmp     rdi, [rbx+18h]
0x180047192  jb      short loc_180047165
0x180047194  lea     this, [rbx+20h]; lpCriticalSection
0x180047198  call    cs:__imp_DeleteCriticalSection
0x18004719e  mov     dword ptr [rbx], 0
0x1800471a4  mov     rbx, [rsp+28h+arg_0]
0x1800471a9  mov     rsi, [rsp+28h+arg_8]
0x1800471ae  add     rsp, 20h
0x1800471b2  pop     rdi
0x1800471b3  retn
```
