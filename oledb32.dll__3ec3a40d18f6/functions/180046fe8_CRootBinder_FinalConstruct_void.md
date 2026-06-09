# CRootBinder::FinalConstruct(void)

- ea: `0x180046fe8`
- end: `0x18004716b`
- name: `?FinalConstruct@CRootBinder@@QEAAJXZ`
- size: `387`
- prototype: `__int64 __fastcall(CRootBinder *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18003341c`
- `0x180033904`

## callees

- `0x180013870`
- `0x180029560`
- `0x180044064`
- `0x18004429c`
- `0x180046fe8`
- `0x180087010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180047001`
- `KERNEL32!EnterCriticalSection` at `0x180047001`
- `KERNEL32!LeaveCriticalSection` at `0x18004712d`
- `KERNEL32!LeaveCriticalSection` at `0x18004712d`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x1800470d6`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x1800470d6`

## pseudocode

```c
__int64 __fastcall CRootBinder::FinalConstruct(CRootBinder *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  CMatchMaker *Instance; // rax
  unsigned int FreeThreadedMarshaler; // ebx
  __int64 v5; // rdx
  IUnknown *v6; // rax

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 104);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  Instance = CMatchMaker::GetInstance();
  *((_QWORD *)this + 49) = Instance;
  if ( Instance )
  {
    if ( (unsigned int)CMatchMaker::Initialize(Instance) )
    {
      v6 = (IUnknown *)(*(__int64 (__fastcall **)(CRootBinder *))(*(_QWORD *)this + 32LL))(this);
      FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v6, (LPUNKNOWN *)this + 46);
      if ( (FreeThreadedMarshaler & 0x80000000) != 0 && (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(FreeThreadedMarshaler, L"<CRootBinder::FinalConstruct|OLEDB|ERR> ", 0x2Du);
        if ( (bidGblFlags & 2) != 0 )
          bidTraceHR(off_1800C83B0[0], 46089, L"<CRootBinder::FinalConstruct|Trace|HR> ", FreeThreadedMarshaler);
      }
    }
    else
    {
      FreeThreadedMarshaler = -2147467259;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147467259, L"<CRootBinder::FinalConstruct|OLEDB|ERR> ", 0x2Au);
        if ( (bidGblFlags & 2) != 0 )
        {
          v5 = 43017;
          goto LABEL_5;
        }
      }
    }
  }
  else
  {
    FreeThreadedMarshaler = -2147467259;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147467259, L"<CRootBinder::FinalConstruct|OLEDB|ERR> ", 0x28u);
      if ( (bidGblFlags & 2) != 0 )
      {
        v5 = 40969;
LABEL_5:
        FreeThreadedMarshaler = bidTraceHR(
                                  off_1800C83B0[0],
                                  v5,
                                  L"<CRootBinder::FinalConstruct|Trace|HR> ",
                                  2147500037LL);
      }
    }
  }
  LeaveCriticalSection(v1);
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(
                           off_1800C83B0[0],
                           51209,
                           L"<CRootBinder::FinalConstruct|Trace|HR> ",
                           FreeThreadedMarshaler);
  return FreeThreadedMarshaler;
}

```

## disassembly

```asm
0x180046fe8  mov     [rsp+arg_0], rbx
0x180046fed  mov     [rsp+arg_8], rsi
0x180046ff2  push    rdi
0x180046ff3  sub     rsp, 20h
0x180046ff7  lea     rsi, [rcx+68h]
0x180046ffb  mov     rdi, rcx
0x180046ffe  mov     rcx, rsi; lpCriticalSection
0x180047001  call    cs:__imp_EnterCriticalSection
0x180047007  call    ?GetInstance@CMatchMaker@@SAPEAV1@XZ; CMatchMaker::GetInstance(void)
0x18004700c  mov     [rdi+188h], rax
0x180047013  test    rax, rax
0x180047016  jnz     short loc_180047074
0x180047018  mov     eax, cs:_bidGblFlags
0x18004701e  mov     dil, 2
0x180047021  mov     ebx, 80004005h
0x180047026  test    dil, al
0x180047029  jz      loc_18004712A
0x18004702f  mov     r8d, 28h ; '('; unsigned int
0x180047035  lea     rdx, aCrootbinderFin_0; "<CRootBinder::FinalConstruct|OLEDB|ERR>"...
0x18004703c  mov     ecx, ebx; int
0x18004703e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180047043  mov     eax, cs:_bidGblFlags
0x180047049  test    dil, al
0x18004704c  jz      loc_18004712A
0x180047052  mov     edx, 0A009h
0x180047057  mov     rcx, cs:off_1800C83B0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004705e  lea     r8, aCrootbinderFin; "<CRootBinder::FinalConstruct|Trace|HR> "
0x180047065  mov     r9d, ebx
0x180047068  call    _bidTraceHR
0x18004706d  mov     ebx, eax
0x18004706f  jmp     loc_18004712A
0x180047074  mov     rcx, rax; this
0x180047077  call    ?Initialize@CMatchMaker@@QEAAHXZ; CMatchMaker::Initialize(void)
0x18004707c  test    eax, eax
0x18004707e  jnz     short loc_1800470BD
0x180047080  mov     eax, cs:_bidGblFlags
0x180047086  mov     dil, 2
0x180047089  mov     ebx, 80004005h
0x18004708e  test    dil, al
0x180047091  jz      loc_18004712A
0x180047097  mov     r8d, 2Ah ; '*'; unsigned int
0x18004709d  lea     rdx, aCrootbinderFin_0; "<CRootBinder::FinalConstruct|OLEDB|ERR>"...
0x1800470a4  mov     ecx, ebx; int
0x1800470a6  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800470ab  mov     eax, cs:_bidGblFlags
0x1800470b1  test    dil, al
0x1800470b4  jz      short loc_18004712A
0x1800470b6  mov     edx, 0A809h
0x1800470bb  jmp     short loc_180047057
0x1800470bd  mov     rax, [rdi]
0x1800470c0  mov     rcx, rdi
0x1800470c3  mov     rax, [rax+20h]
0x1800470c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470cc  mov     rcx, rax; punkOuter
0x1800470cf  lea     rdx, [rdi+170h]; ppunkMarshal
0x1800470d6  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800470dc  mov     ebx, eax
0x1800470de  mov     dil, 2
0x1800470e1  test    eax, eax
0x1800470e3  jns     short loc_18004712A
0x1800470e5  mov     eax, cs:_bidGblFlags
0x1800470eb  test    dil, al
0x1800470ee  jz      short loc_18004712A
0x1800470f0  mov     r8d, 2Dh ; '-'; unsigned int
0x1800470f6  lea     rdx, aCrootbinderFin_0; "<CRootBinder::FinalConstruct|OLEDB|ERR>"...
0x1800470fd  mov     ecx, ebx; int
0x1800470ff  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180047104  mov     eax, cs:_bidGblFlags
0x18004710a  test    dil, al
0x18004710d  jz      short loc_18004712A
0x18004710f  mov     rcx, cs:off_1800C83B0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180047116  lea     r8, aCrootbinderFin; "<CRootBinder::FinalConstruct|Trace|HR> "
0x18004711d  mov     r9d, ebx
0x180047120  mov     edx, 0B409h
0x180047125  call    _bidTraceHR
0x18004712a  mov     rcx, rsi; lpCriticalSection
0x18004712d  call    cs:__imp_LeaveCriticalSection
0x180047133  test    byte ptr cs:_bidGblFlags, dil
0x18004713a  jz      short loc_180047159
0x18004713c  mov     rcx, cs:off_1800C83B0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180047143  lea     r8, aCrootbinderFin; "<CRootBinder::FinalConstruct|Trace|HR> "
0x18004714a  mov     r9d, ebx
0x18004714d  mov     edx, 0C809h
0x180047152  call    _bidTraceHR
0x180047157  mov     ebx, eax
0x180047159  mov     rsi, [rsp+28h+arg_8]
0x18004715e  mov     eax, ebx
0x180047160  mov     rbx, [rsp+28h+arg_0]
0x180047165  add     rsp, 20h
0x180047169  pop     rdi
0x18004716a  retn
```
