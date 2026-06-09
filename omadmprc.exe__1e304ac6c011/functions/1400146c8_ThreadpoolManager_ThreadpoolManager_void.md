# ThreadpoolManager::~ThreadpoolManager(void)

- ea: `0x1400146c8`
- end: `0x1400147a4`
- name: `??1ThreadpoolManager@@UEAA@XZ`
- size: `220`
- prototype: `void __fastcall(ThreadpoolManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400147b0`

## callees

- `0x1400146c8`
- `0x140017010`

## pseudocode

```c
void __fastcall ThreadpoolManager::~ThreadpoolManager(ThreadpoolManager *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  void (__fastcall ***v6)(_QWORD, __int64); // rcx
  void (__fastcall ***v7)(_QWORD, __int64); // rcx

  *(_QWORD *)this = &ThreadpoolManager::`vftable';
  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v2 )
    (**v2)(v2, 1);
  v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v3 )
    (**v3)(v3, 1);
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v4 )
    (**v4)(v4, 1);
  v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v5 )
    (**v5)(v5, 1);
  v6 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v6 )
    (**v6)(v6, 1);
  v7 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v7 )
    (**v7)(v7, 1);
}

```

## disassembly

```asm
0x1400146c8  mov     [rsp+arg_0], rbx
0x1400146cd  push    rsi
0x1400146ce  sub     rsp, 20h
0x1400146d2  mov     rbx, rcx
0x1400146d5  lea     rax, ??_7ThreadpoolManager@@6B@; const ThreadpoolManager::`vftable'
0x1400146dc  mov     [rcx], rax
0x1400146df  mov     esi, 1
0x1400146e4  mov     rcx, [rcx+8]
0x1400146e8  mov     qword ptr [rbx+8], 0
0x1400146f0  test    rcx, rcx
0x1400146f3  jz      short loc_140014702
0x1400146f5  mov     rax, [rcx]
0x1400146f8  mov     edx, esi
0x1400146fa  mov     rax, [rax]
0x1400146fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014702  mov     rcx, [rbx+10h]
0x140014706  mov     qword ptr [rbx+10h], 0
0x14001470e  test    rcx, rcx
0x140014711  jz      short loc_140014720
0x140014713  mov     rax, [rcx]
0x140014716  mov     edx, esi
0x140014718  mov     rax, [rax]
0x14001471b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014720  mov     rcx, [rbx+18h]
0x140014724  mov     qword ptr [rbx+18h], 0
0x14001472c  test    rcx, rcx
0x14001472f  jz      short loc_14001473E
0x140014731  mov     rax, [rcx]
0x140014734  mov     edx, esi
0x140014736  mov     rax, [rax]
0x140014739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001473e  mov     rcx, [rbx+18h]
0x140014742  mov     qword ptr [rbx+18h], 0
0x14001474a  test    rcx, rcx
0x14001474d  jz      short loc_14001475C
0x14001474f  mov     rax, [rcx]
0x140014752  mov     edx, esi
0x140014754  mov     rax, [rax]
0x140014757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001475c  mov     rcx, [rbx+10h]
0x140014760  mov     qword ptr [rbx+10h], 0
0x140014768  test    rcx, rcx
0x14001476b  jz      short loc_14001477A
0x14001476d  mov     rax, [rcx]
0x140014770  mov     edx, esi
0x140014772  mov     rax, [rax]
0x140014775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001477a  mov     rcx, [rbx+8]
0x14001477e  mov     qword ptr [rbx+8], 0
0x140014786  test    rcx, rcx
0x140014789  jz      short loc_140014798
0x14001478b  mov     rax, [rcx]
0x14001478e  mov     edx, esi
0x140014790  mov     rax, [rax]
0x140014793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014798  mov     rbx, [rsp+28h+arg_0]
0x14001479d  add     rsp, 20h
0x1400147a1  pop     rsi
0x1400147a2  retn
```
