# CPersistStreamInit::~CPersistStreamInit(void)

- ea: `0x18001b354`
- end: `0x18001b3f3`
- name: `??1CPersistStreamInit@@QEAA@XZ`
- size: `159`
- prototype: `void __fastcall(CPersistStreamInit *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180013dc8`

## callees

- `0x180002770`
- `0x18001b354`
- `0x1800213b8`
- `0x180031010`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18001b3e7`

## pseudocode

```c
void __fastcall CPersistStreamInit::~CPersistStreamInit(CPersistStreamInit *this)
{
  int (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v3; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &CPersistStreamInit::`vftable';
  v2 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 4);
  if ( v2 )
  {
    if ( *((_QWORD *)this + 7) )
    {
      v3 = 0;
      if ( (**v2)(v2, &IID_IChapteredRowset, &v3) >= 0 )
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 32LL))(v3, *((_QWORD *)this + 7), 0);
      *((_QWORD *)this + 7) = 0;
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v3);
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 16LL))(*((_QWORD *)this + 4));
  }
  ReleaseDataConvert(*((struct IDataConvert **)this + 5));
  MPDeleteCriticalSection((char *)this + 16);
}

```

## disassembly

```asm
0x18001b354  push    rbx
0x18001b356  sub     rsp, 20h
0x18001b35a  mov     rbx, rcx
0x18001b35d  lea     rax, ??_7CPersistStreamInit@@6B@; const CPersistStreamInit::`vftable'
0x18001b364  mov     [rcx], rax
0x18001b367  mov     rcx, [rcx+20h]
0x18001b36b  test    rcx, rcx
0x18001b36e  jz      short loc_18001B3D5
0x18001b370  cmp     qword ptr [rbx+38h], 0
0x18001b375  jz      short loc_18001B3C5
0x18001b377  mov     [rsp+28h+arg_0], 0
0x18001b380  mov     rax, [rcx]
0x18001b383  lea     r8, [rsp+28h+arg_0]
0x18001b388  lea     rdx, IID_IChapteredRowset
0x18001b38f  mov     rax, [rax]
0x18001b392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b397  test    eax, eax
0x18001b399  js      short loc_18001B3B3
0x18001b39b  mov     rcx, [rsp+28h+arg_0]
0x18001b3a0  mov     rax, [rcx]
0x18001b3a3  xor     r8d, r8d
0x18001b3a6  mov     rdx, [rbx+38h]
0x18001b3aa  mov     rax, [rax+20h]
0x18001b3ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3b3  mov     qword ptr [rbx+38h], 0
0x18001b3bb  lea     rcx, [rsp+28h+arg_0]
0x18001b3c0  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18001b3c5  mov     rcx, [rbx+20h]
0x18001b3c9  mov     rax, [rcx]
0x18001b3cc  mov     rax, [rax+10h]
0x18001b3d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3d5  mov     rcx, [rbx+28h]; struct IDataConvert *
0x18001b3d9  call    ?ReleaseDataConvert@@YAXPEAUIDataConvert@@@Z; ReleaseDataConvert(IDataConvert *)
0x18001b3de  lea     rcx, [rbx+10h]
0x18001b3e2  add     rsp, 20h
0x18001b3e6  pop     rbx
0x18001b3e7  jmp     cs:__imp_MPDeleteCriticalSection
```
