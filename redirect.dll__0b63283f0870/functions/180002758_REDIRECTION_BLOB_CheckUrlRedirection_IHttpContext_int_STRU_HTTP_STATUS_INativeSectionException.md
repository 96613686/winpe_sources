# REDIRECTION_BLOB::CheckUrlRedirection(IHttpContext *,int *,STRU *,HTTP_STATUS *,INativeSectionException * *)

- ea: `0x180002758`
- end: `0x1800029a5`
- name: `?CheckUrlRedirection@REDIRECTION_BLOB@@SAJPEAVIHttpContext@@PEAHPEAVSTRU@@PEAUHTTP_STATUS@@PEAPEAVINativeSectionException@@@Z`
- size: `589`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(struct IHttpContext *), int *, struct STRU *, struct HTTP_STATUS *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800021ec`

## callees

- `0x180001008`
- `0x180002758`
- `0x180002bc4`
- `0x18000304c`
- `0x1800035c6`
- `0x1800035f0`
- `0x180004010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000294b`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000294b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002816`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002820`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002816`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002820`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002934`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002934`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000297b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000297b`

## pseudocode

```c
__int64 __fastcall REDIRECTION_BLOB::CheckUrlRedirection(
        __int64 (__fastcall ***a1)(struct IHttpContext *),
        int *a2,
        struct STRU *a3,
        struct HTTP_STATUS *a4,
        struct INativeSectionException **a5)
{
  __int64 v9; // rsi
  __int64 (__fastcall ***v10)(_QWORD, void *); // rax
  char *v11; // rdi
  int Destination; // ebx
  __int64 v13; // rax
  __int64 (__fastcall ***v14)(_QWORD, void *); // rax
  __int64 v16; // rax
  __int64 v17; // rbx
  _BYTE v18[64]; // [rsp+30h] [rbp-888h] BYREF
  unsigned __int16 v19[1024]; // [rsp+70h] [rbp-848h] BYREF

  v9 = (*a1)[20]((struct IHttpContext *)a1);
  v10 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
  v11 = (char *)(**v10)(v10, g_pRedirectionModuleContext);
  if ( v11 )
    goto LABEL_8;
  v11 = (char *)operator new(0xA0u);
  if ( !v11 )
    return 2147942408LL;
  *((_WORD *)v11 + 4) = 302;
  *(_QWORD *)v11 = &REDIRECTION_BLOB::`vftable';
  *(_QWORD *)(v11 + 12) = 0;
  *(_QWORD *)(v11 + 20) = 0;
  *((_DWORD *)v11 + 7) = 0;
  STRU::STRU((STRU *)(v11 + 32));
  STRU::STRU((STRU *)(v11 + 88));
  *((_QWORD *)v11 + 19) = v11 + 144;
  *((_QWORD *)v11 + 18) = v11 + 144;
  Destination = REDIRECTION_BLOB::Initialize((REDIRECTION_BLOB *)v11, a1, a5);
  if ( Destination >= 0 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
    Destination = (*(__int64 (__fastcall **)(__int64, char *, void *))(*(_QWORD *)v13 + 8LL))(
                    v13,
                    v11,
                    g_pRedirectionModuleContext);
    if ( Destination < 0 )
    {
      (**(void (__fastcall ***)(void *))v11)(v11);
      if ( Destination != -2147024811 )
        return (unsigned int)Destination;
      v14 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
      v11 = (char *)(**v14)(v14, g_pRedirectionModuleContext);
    }
LABEL_8:
    if ( !*((_DWORD *)v11 + 3) )
    {
      *a2 = 0;
      return 0;
    }
    v16 = (*a1)[3]((struct IHttpContext *)a1);
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
    memset_0(v19, 0, sizeof(v19));
    STRU::STRU((STRU *)v18, v19, 0x400u);
    Destination = STRU::Copy((STRU *)v18, *(const unsigned __int16 **)(v17 + 88), *(unsigned __int16 *)(v17 + 68) >> 1);
    if ( Destination >= 0 )
      Destination = REDIRECTION_BLOB::GetDestination(
                      (REDIRECTION_BLOB *)v11,
                      (struct IHttpContext *)a1,
                      (struct STRU *)v18,
                      a3,
                      a2,
                      a4);
    STRU::~STRU((STRU *)v18);
    return (unsigned int)Destination;
  }
  (**(void (__fastcall ***)(void *))v11)(v11);
  return (unsigned int)Destination;
}

```

## disassembly

```asm
0x180002758  push    rbx
0x18000275a  push    rbp
0x18000275b  push    rsi
0x18000275c  push    rdi
0x18000275d  push    r12
0x18000275f  push    r14
0x180002761  push    r15
0x180002763  sub     rsp, 880h
0x18000276a  mov     rax, cs:__security_cookie
0x180002771  xor     rax, rsp
0x180002774  mov     [rsp+8B8h+var_48], rax
0x18000277c  mov     rax, [rcx]
0x18000277f  mov     r12, r9
0x180002782  mov     rbx, [rsp+8B8h+arg_20]
0x18000278a  mov     rbp, r8
0x18000278d  mov     r15, rdx
0x180002790  mov     r14, rcx
0x180002793  mov     rax, [rax+0A0h]
0x18000279a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000279f  mov     rsi, rax
0x1800027a2  mov     rcx, [rax]
0x1800027a5  mov     rax, [rcx+18h]
0x1800027a9  mov     rcx, rsi
0x1800027ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027b1  mov     rdx, cs:?g_pRedirectionModuleContext@@3PEAXEA; void * g_pRedirectionModuleContext
0x1800027b8  mov     r8, rax
0x1800027bb  mov     rcx, [rax]
0x1800027be  mov     rax, [rcx]
0x1800027c1  mov     rcx, r8
0x1800027c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027c9  mov     rdi, rax
0x1800027cc  test    rax, rax
0x1800027cf  jnz     loc_1800028D0
0x1800027d5  mov     ecx, 0A0h; Size
0x1800027da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800027df  mov     rdi, rax
0x1800027e2  test    rax, rax
0x1800027e5  jz      loc_1800028E4
0x1800027eb  lea     rax, ??_7REDIRECTION_BLOB@@6B@; const REDIRECTION_BLOB::`vftable'
0x1800027f2  mov     word ptr [rdi+8], 12Eh
0x1800027f8  lea     rcx, [rdi+20h]
0x1800027fc  mov     [rdi], rax
0x1800027ff  mov     qword ptr [rdi+0Ch], 0
0x180002807  mov     qword ptr [rdi+14h], 0
0x18000280f  mov     dword ptr [rdi+1Ch], 0
0x180002816  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000281c  lea     rcx, [rdi+58h]
0x180002820  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002826  lea     rax, [rdi+90h]
0x18000282d  mov     r8, rbx; struct INativeSectionException **
0x180002830  mov     rdx, r14; struct IHttpContext *
0x180002833  mov     [rax+8], rax
0x180002837  mov     rcx, rdi; this
0x18000283a  mov     [rax], rax
0x18000283d  call    ?Initialize@REDIRECTION_BLOB@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z; REDIRECTION_BLOB::Initialize(IHttpContext *,INativeSectionException * *)
0x180002842  mov     ebx, eax
0x180002844  test    eax, eax
0x180002846  jns     short loc_18000285B
0x180002848  mov     rcx, [rdi]
0x18000284b  mov     rax, [rcx]
0x18000284e  mov     rcx, rdi
0x180002851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002856  jmp     loc_180002981
0x18000285b  mov     rax, [rsi]
0x18000285e  mov     rcx, rsi
0x180002861  mov     rax, [rax+18h]
0x180002865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000286a  mov     r8, cs:?g_pRedirectionModuleContext@@3PEAXEA; void * g_pRedirectionModuleContext
0x180002871  mov     r9, rax
0x180002874  mov     rdx, rdi
0x180002877  mov     rcx, [rax]
0x18000287a  mov     rax, [rcx+8]
0x18000287e  mov     rcx, r9
0x180002881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002886  mov     ebx, eax
0x180002888  test    eax, eax
0x18000288a  jns     short loc_1800028D0
0x18000288c  mov     rcx, [rdi]
0x18000288f  mov     rax, [rcx]
0x180002892  mov     rcx, rdi
0x180002895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000289a  cmp     ebx, 80070055h
0x1800028a0  jnz     loc_180002981
0x1800028a6  mov     rax, [rsi]
0x1800028a9  mov     rcx, rsi
0x1800028ac  mov     rax, [rax+18h]
0x1800028b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028b5  mov     rdx, cs:?g_pRedirectionModuleContext@@3PEAXEA; void * g_pRedirectionModuleContext
0x1800028bc  mov     r8, rax
0x1800028bf  mov     rcx, [rax]
0x1800028c2  mov     rax, [rcx]
0x1800028c5  mov     rcx, r8
0x1800028c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028cd  mov     rdi, rax
0x1800028d0  cmp     dword ptr [rdi+0Ch], 0
0x1800028d4  jnz     short loc_1800028EE
0x1800028d6  mov     dword ptr [r15], 0
0x1800028dd  xor     eax, eax
0x1800028df  jmp     loc_180002983
0x1800028e4  mov     eax, 80070008h
0x1800028e9  jmp     loc_180002983
0x1800028ee  mov     rax, [r14]
0x1800028f1  mov     rcx, r14
0x1800028f4  mov     rax, [rax+18h]
0x1800028f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028fd  mov     rdx, rax
0x180002900  mov     rcx, [rax]
0x180002903  mov     rax, [rcx+8]
0x180002907  mov     rcx, rdx
0x18000290a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000290f  xor     edx, edx; Val
0x180002911  lea     rcx, [rsp+8B8h+var_848]; void *
0x180002916  mov     r8d, 800h; Size
0x18000291c  mov     rbx, rax
0x18000291f  call    memset_0
0x180002924  mov     r8d, 400h
0x18000292a  lea     rdx, [rsp+8B8h+var_848]
0x18000292f  lea     rcx, [rsp+8B8h+var_888]
0x180002934  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000293a  movzx   r8d, word ptr [rbx+44h]
0x18000293f  lea     rcx, [rsp+8B8h+var_888]
0x180002944  mov     rdx, [rbx+58h]
0x180002948  shr     r8d, 1
0x18000294b  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180002951  mov     ebx, eax
0x180002953  test    eax, eax
0x180002955  js      short loc_180002976
0x180002957  mov     [rsp+8B8h+var_890], r12; struct HTTP_STATUS *
0x18000295c  lea     r8, [rsp+8B8h+var_888]; struct STRU *
0x180002961  mov     r9, rbp; struct STRU *
0x180002964  mov     [rsp+8B8h+var_898], r15; int *
0x180002969  mov     rdx, r14; struct IHttpContext *
0x18000296c  mov     rcx, rdi; this
0x18000296f  call    ?GetDestination@REDIRECTION_BLOB@@QEAAJPEAVIHttpContext@@AEAVSTRU@@PEAV3@PEAHPEAUHTTP_STATUS@@@Z; REDIRECTION_BLOB::GetDestination(IHttpContext *,STRU &,STRU *,int *,HTTP_STATUS *)
0x180002974  mov     ebx, eax
0x180002976  lea     rcx, [rsp+8B8h+var_888]
0x18000297b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002981  mov     eax, ebx
0x180002983  mov     rcx, [rsp+8B8h+var_48]
0x18000298b  xor     rcx, rsp; StackCookie
0x18000298e  call    __security_check_cookie
0x180002993  add     rsp, 880h
0x18000299a  pop     r15
0x18000299c  pop     r14
0x18000299e  pop     r12
0x1800029a0  pop     rdi
0x1800029a1  pop     rsi
0x1800029a2  pop     rbp
0x1800029a3  pop     rbx
0x1800029a4  retn
```
