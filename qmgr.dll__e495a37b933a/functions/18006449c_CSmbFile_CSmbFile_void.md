# CSmbFile::~CSmbFile(void)

- ea: `0x18006449c`
- end: `0x18006469c`
- name: `??1CSmbFile@@UEAA@XZ`
- size: `512`
- prototype: `void __fastcall(CSmbFile *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180064460`

## callees

- `0x18006449c`
- `0x1800646a4`
- `0x18009d024`
- `0x1800a3444`
- `0x1800cc2d0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180064535`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180064535`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180064542`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180064542`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006451a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006457e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800645d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064626`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006451a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006457e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800645d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064626`

## pseudocode

```c
void __fastcall CSmbFile::~CSmbFile(CSmbFile *this)
{
  void *v2; // rdi
  void *v3; // rcx
  struct _TP_IO *v4; // rcx
  char *v5; // rcx
  char *v6; // rcx
  char *v7; // rcx
  __int64 v8; // rcx

  *(_QWORD *)this = &CFileReader::`vftable';
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_544ed435ee403dfadff71ae516532c05_Traceguids);
  v2 = (void *)*((_QWORD *)this + 48);
  if ( v2 )
  {
    UPLOAD_DATA::~UPLOAD_DATA(*((UPLOAD_DATA **)this + 48));
    operator delete(v2, 0x48u);
  }
  v3 = (void *)*((_QWORD *)this + 40);
  if ( v3 != (void *)-1LL )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 40) = -1;
  }
  v4 = (struct _TP_IO *)*((_QWORD *)this + 52);
  if ( v4 )
  {
    WaitForThreadpoolIoCallbacks(v4, 0);
    CloseThreadpoolIo(*((PTP_IO *)this + 52));
    *((_QWORD *)this + 52) = 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)this + 50) + 8LL), 0xFFFFFFFF) == 1 )
  {
    v5 = (char *)**((_QWORD **)this + 50);
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v5);
      **((_QWORD **)this + 50) = 0;
    }
    operator delete(*((void **)this + 50), 0x10u);
    *((_QWORD *)this + 50) = 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)this + 49) + 8LL), 0xFFFFFFFF) == 1 )
  {
    v6 = (char *)**((_QWORD **)this + 49);
    if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v6);
      **((_QWORD **)this + 49) = 0;
    }
    operator delete(*((void **)this + 49), 0x10u);
    *((_QWORD *)this + 49) = 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)this + 41) + 8LL), 0xFFFFFFFF) == 1 )
  {
    v7 = (char *)**((_QWORD **)this + 41);
    if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v7);
      **((_QWORD **)this + 41) = 0;
    }
    operator delete(*((void **)this + 41), 0x10u);
    *((_QWORD *)this + 41) = 0;
  }
  v8 = *((_QWORD *)this + 38);
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v8 + 8), 0xFFFFFFFF) == 1 )
      operator delete(*((void **)this + 38), 0x10u);
    *((_QWORD *)this + 38) = 0;
  }
  CAbstractFile::~CAbstractFile(this);
}

```

## disassembly

```asm
0x18006449c  mov     [rsp+arg_8], rbx
0x1800644a1  mov     [rsp+arg_10], rbp
0x1800644a6  push    rdi
0x1800644a7  sub     rsp, 20h
0x1800644ab  lea     rax, ??_7CFileReader@@6B@; const CFileReader::`vftable'
0x1800644b2  mov     rbx, rcx
0x1800644b5  mov     [rcx], rax
0x1800644b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800644bf  lea     rax, WPP_GLOBAL_Control
0x1800644c6  cmp     rcx, rax
0x1800644c9  jz      short loc_1800644E9
0x1800644cb  test    dword ptr [rcx+1Ch], 800h
0x1800644d2  jz      short loc_1800644E9
0x1800644d4  mov     rcx, [rcx+10h]
0x1800644d8  lea     r8, WPP_544ed435ee403dfadff71ae516532c05_Traceguids
0x1800644df  mov     edx, 0Eh
0x1800644e4  call    WPP_SF_
0x1800644e9  mov     rdi, [rbx+180h]
0x1800644f0  test    rdi, rdi
0x1800644f3  jz      short loc_18006450A
0x1800644f5  mov     rcx, rdi; this
0x1800644f8  call    ??1UPLOAD_DATA@@QEAA@XZ; UPLOAD_DATA::~UPLOAD_DATA(void)
0x1800644fd  mov     edx, 48h ; 'H'; unsigned __int64
0x180064502  mov     rcx, rdi; void *
0x180064505  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006450a  mov     rcx, [rbx+140h]; hObject
0x180064511  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180064515  cmp     rcx, rdi
0x180064518  jz      short loc_180064527
0x18006451a  call    cs:__imp_CloseHandle
0x180064520  mov     [rbx+140h], rdi
0x180064527  mov     rcx, [rbx+1A0h]; pio
0x18006452e  test    rcx, rcx
0x180064531  jz      short loc_180064553
0x180064533  xor     edx, edx; fCancelPendingCallbacks
0x180064535  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x18006453b  mov     rcx, [rbx+1A0h]; pio
0x180064542  call    cs:__imp_CloseThreadpoolIo
0x180064548  mov     qword ptr [rbx+1A0h], 0
0x180064553  mov     rcx, [rbx+190h]
0x18006455a  mov     eax, edi
0x18006455c  lock xadd [rcx+8], eax
0x180064561  mov     ebp, 10h
0x180064566  add     eax, edi
0x180064568  jnz     short loc_1800645AC
0x18006456a  mov     rax, [rbx+190h]
0x180064571  mov     rcx, [rax]; hObject
0x180064574  lea     rax, [rcx-1]
0x180064578  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006457c  ja      short loc_180064592
0x18006457e  call    cs:__imp_CloseHandle
0x180064584  mov     rax, [rbx+190h]
0x18006458b  mov     qword ptr [rax], 0
0x180064592  mov     rcx, [rbx+190h]; void *
0x180064599  mov     rdx, rbp; unsigned __int64
0x18006459c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800645a1  mov     qword ptr [rbx+190h], 0
0x1800645ac  mov     rcx, [rbx+188h]
0x1800645b3  mov     eax, edi
0x1800645b5  lock xadd [rcx+8], eax
0x1800645ba  add     eax, edi
0x1800645bc  jnz     short loc_180064600
0x1800645be  mov     rax, [rbx+188h]
0x1800645c5  mov     rcx, [rax]; hObject
0x1800645c8  lea     rax, [rcx-1]
0x1800645cc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800645d0  ja      short loc_1800645E6
0x1800645d2  call    cs:__imp_CloseHandle
0x1800645d8  mov     rax, [rbx+188h]
0x1800645df  mov     qword ptr [rax], 0
0x1800645e6  mov     rcx, [rbx+188h]; void *
0x1800645ed  mov     rdx, rbp; unsigned __int64
0x1800645f0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800645f5  mov     qword ptr [rbx+188h], 0
0x180064600  mov     rcx, [rbx+148h]
0x180064607  mov     eax, edi
0x180064609  lock xadd [rcx+8], eax
0x18006460e  add     eax, edi
0x180064610  jnz     short loc_180064654
0x180064612  mov     rax, [rbx+148h]
0x180064619  mov     rcx, [rax]; hObject
0x18006461c  lea     rax, [rcx-1]
0x180064620  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180064624  ja      short loc_18006463A
0x180064626  call    cs:__imp_CloseHandle
0x18006462c  mov     rax, [rbx+148h]
0x180064633  mov     qword ptr [rax], 0
0x18006463a  mov     rcx, [rbx+148h]; void *
0x180064641  mov     rdx, rbp; unsigned __int64
0x180064644  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180064649  mov     qword ptr [rbx+148h], 0
0x180064654  mov     rcx, [rbx+130h]
0x18006465b  test    rcx, rcx
0x18006465e  jz      short loc_180064685
0x180064660  mov     eax, edi
0x180064662  lock xadd [rcx+8], eax
0x180064667  add     eax, edi
0x180064669  jnz     short loc_18006467A
0x18006466b  mov     rcx, [rbx+130h]; void *
0x180064672  mov     rdx, rbp; unsigned __int64
0x180064675  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006467a  mov     qword ptr [rbx+130h], 0
0x180064685  mov     rcx, rbx; this
0x180064688  mov     rbx, [rsp+28h+arg_8]
0x18006468d  mov     rbp, [rsp+28h+arg_10]
0x180064692  add     rsp, 20h
0x180064696  pop     rdi
0x180064697  jmp     ??1CAbstractFile@@UEAA@XZ; CAbstractFile::~CAbstractFile(void)
```
