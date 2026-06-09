# PersistXmlStore::FlushObject(PersistObject *)

- ea: `0x180036710`
- end: `0x1800368bd`
- name: `?FlushObject@PersistXmlStore@@UEAAJPEAVPersistObject@@@Z`
- size: `429`
- prototype: `__int64 __fastcall(PersistXmlStore *__hidden this, struct PersistObject *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180006090`
- `0x18001974c`
- `0x180019904`
- `0x180035c24`
- `0x18003667c`
- `0x180036710`
- `0x180036f3c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003675f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800367f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003675f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800367f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036751`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800367d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036751`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800367d3`
- `DMCmnUtils!CopyString` at `0x1800367e8`
- `DMCmnUtils!CopyString` at `0x1800367e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PersistXmlStore::FlushObject(PersistObject ***this, struct PersistObject *a2)
{
  PersistObject *v4; // rdi
  int v5; // esi
  const unsigned __int16 *v6; // r15
  PersistObject *v7; // rax
  int Entry; // eax
  PersistObject **v9; // rdx
  __int64 v10; // rbx
  PersistObject *v11; // rcx
  unsigned int v13; // [rsp+50h] [rbp+8h] BYREF
  PersistObject *v14; // [rsp+60h] [rbp+18h] BYREF

  v13 = 0;
  v4 = 0;
  if ( ((unsigned int (__fastcall *)(PersistObject ***))(*this)[9])(this) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
    v6 = (const unsigned __int16 *)*((_QWORD *)a2 + 3);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
    if ( v6 )
    {
      v7 = (PersistObject *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
      v14 = v7;
      if ( v7 )
        v4 = PersistObject::PersistObject(v7);
      else
        v4 = 0;
      v14 = v4;
      if ( v4 )
      {
        v5 = PersistObject::CopyData(v4, a2);
        if ( v5 >= 0 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 32));
          v5 = CopyString(v6, 0xFFFFFFFF, (unsigned __int16 **)v4 + 3);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 32));
          if ( v5 >= 0 )
          {
            Entry = PersistXmlStore::FindEntry((PersistXmlStore *)this, v6, &v13);
            try
            {
              if ( Entry == -2147023728 )
              {
                v9 = this[12];
                if ( v9 == this[13] )
                {
                  std::vector<PersistObject *>::_Emplace_reallocate<PersistObject * const &>(this + 11, v9, &v14);
                }
                else
                {
                  *v9 = v4;
                  ++this[12];
                }
                v4 = 0;
                v14 = 0;
              }
              else
              {
                v10 = v13;
                v11 = this[11][v13];
                if ( v11 )
                  (**(void (__fastcall ***)(PersistObject *, __int64))v11)(v11, 1);
                this[11][v10] = 0;
                this[11][v10] = v4;
                v4 = 0;
              }
            }
            catch ( std::bad_alloc )
            {
              v13 = -2147024882;
              v5 = -2147024882;
              v4 = v14;
              goto LABEL_22;
            }
            v5 = PersistXmlStore::PersistAll((PersistXmlStore *)this);
          }
        }
      }
      else
      {
        v5 = -2147024882;
      }
    }
    else
    {
      v5 = -2147024809;
    }
  }
  else
  {
    v5 = -2147418113;
  }
LABEL_22:
  if ( v4 )
    (**(void (__fastcall ***)(PersistObject *, __int64))v4)(v4, 1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180036710  mov     [rsp+arg_8], rbx
0x180036715  mov     [rsp+arg_18], rsi
0x18003671a  push    rdi
0x18003671b  push    r14
0x18003671d  push    r15
0x18003671f  sub     rsp, 30h
0x180036723  mov     rsi, rdx
0x180036726  mov     r14, rcx
0x180036729  mov     [rsp+48h+arg_0], 0
0x180036731  xor     edi, edi
0x180036733  mov     rax, [rcx]
0x180036736  mov     rax, [rax+48h]
0x18003673a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003673f  test    eax, eax
0x180036741  jnz     short loc_18003674D
0x180036743  mov     esi, 8000FFFFh
0x180036748  jmp     loc_18003688F
0x18003674d  lea     rcx, [rsi+20h]; lpCriticalSection
0x180036751  call    cs:__imp_EnterCriticalSection
0x180036757  mov     r15, [rsi+18h]
0x18003675b  lea     rcx, [rsi+20h]; lpCriticalSection
0x18003675f  call    cs:__imp_LeaveCriticalSection
0x180036765  test    r15, r15
0x180036768  jnz     short loc_180036774
0x18003676a  mov     esi, 80070057h
0x18003676f  jmp     loc_18003688F
0x180036774  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003677b  mov     ecx, 60h ; '`'; unsigned __int64
0x180036780  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180036785  mov     [rsp+48h+arg_10], rax
0x18003678a  test    rax, rax
0x18003678d  jz      short loc_18003679C
0x18003678f  mov     rcx, rax; this
0x180036792  call    ??0PersistObject@@QEAA@XZ; PersistObject::PersistObject(void)
0x180036797  mov     rdi, rax
0x18003679a  jmp     short loc_18003679E
0x18003679c  xor     edi, edi
0x18003679e  mov     [rsp+48h+arg_10], rdi
0x1800367a3  test    rdi, rdi
0x1800367a6  jnz     short loc_1800367B2
0x1800367a8  mov     esi, 8007000Eh
0x1800367ad  jmp     loc_18003688F
0x1800367b2  mov     rdx, rsi; struct PersistObject *
0x1800367b5  mov     rcx, rdi; this
0x1800367b8  call    ?CopyData@PersistObject@@QEAAJPEAV1@@Z; PersistObject::CopyData(PersistObject *)
0x1800367bd  mov     esi, eax
0x1800367bf  test    eax, eax
0x1800367c1  js      loc_18003688F
0x1800367c7  lea     rbx, [rdi+20h]
0x1800367cb  mov     [rsp+48h+var_28], rbx
0x1800367d0  mov     rcx, rbx; lpCriticalSection
0x1800367d3  call    cs:__imp_EnterCriticalSection
0x1800367d9  mov     [rsp+48h+var_20], 1
0x1800367de  lea     r8, [rdi+18h]
0x1800367e2  or      edx, 0FFFFFFFFh
0x1800367e5  mov     rcx, r15
0x1800367e8  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800367ee  mov     esi, eax
0x1800367f0  mov     rcx, rbx; lpCriticalSection
0x1800367f3  call    cs:__imp_LeaveCriticalSection
0x1800367f9  test    esi, esi
0x1800367fb  js      loc_18003688F
0x180036801  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x180036806  mov     rdx, r15; unsigned __int16 *
0x180036809  mov     rcx, r14; this
0x18003680c  call    ?FindEntry@PersistXmlStore@@AEAAJPEBGPEAK@Z; PersistXmlStore::FindEntry(ushort const *,ulong *)
0x180036811  cmp     eax, 80070490h
0x180036816  jnz     short loc_18003684E
0x180036818  lea     rcx, [r14+58h]
0x18003681c  mov     rdx, [rcx+8]
0x180036820  cmp     rdx, [rcx+10h]
0x180036824  jz      short loc_180036830
0x180036826  mov     [rdx], rdi
0x180036829  add     qword ptr [rcx+8], 8
0x18003682e  jmp     short loc_18003683A
0x180036830  lea     r8, [rsp+48h+arg_10]
0x180036835  call    ??$_Emplace_reallocate@AEBQEAVPersistObject@@@?$vector@PEAVPersistObject@@V?$allocator@PEAVPersistObject@@@std@@@std@@AEAAPEAPEAVPersistObject@@QEAPEAV2@AEBQEAV2@@Z; std::vector<PersistObject *>::_Emplace_reallocate<PersistObject * const &>(PersistObject * * const,PersistObject * const &)
0x18003683a  xor     edi, edi
0x18003683c  mov     [rsp+48h+arg_10], rdi
0x180036841  jmp     short loc_180036885
0x180036843  mov     esi, [rsp+48h+arg_0]
0x180036847  mov     rdi, [rsp+48h+arg_10]
0x18003684c  jmp     short loc_18003688F
0x18003684e  mov     ebx, [rsp+48h+arg_0]
0x180036852  mov     rax, [r14+58h]
0x180036856  mov     rcx, [rax+rbx*8]
0x18003685a  test    rcx, rcx
0x18003685d  jz      short loc_18003686F
0x18003685f  mov     rax, [rcx]
0x180036862  mov     edx, 1
0x180036867  mov     rax, [rax]
0x18003686a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003686f  mov     rax, [r14+58h]
0x180036873  mov     qword ptr [rax+rbx*8], 0
0x18003687b  mov     rax, [r14+58h]
0x18003687f  mov     [rax+rbx*8], rdi
0x180036883  xor     edi, edi
0x180036885  mov     rcx, r14; this
0x180036888  call    ?PersistAll@PersistXmlStore@@AEAAJXZ; PersistXmlStore::PersistAll(void)
0x18003688d  mov     esi, eax
0x18003688f  test    rdi, rdi
0x180036892  jz      short loc_1800368A7
0x180036894  mov     rax, [rdi]
0x180036897  mov     edx, 1
0x18003689c  mov     rcx, rdi
0x18003689f  mov     rax, [rax]
0x1800368a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368a7  mov     eax, esi
0x1800368a9  mov     rbx, [rsp+48h+arg_8]
0x1800368ae  mov     rsi, [rsp+48h+arg_18]
0x1800368b3  add     rsp, 30h
0x1800368b7  pop     r15
0x1800368b9  pop     r14
0x1800368bb  pop     rdi
0x1800368bc  retn
```
