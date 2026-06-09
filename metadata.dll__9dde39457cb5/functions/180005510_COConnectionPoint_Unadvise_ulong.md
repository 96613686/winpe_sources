# COConnectionPoint::Unadvise(ulong)

- ea: `0x180005510`
- end: `0x1800055b6`
- name: `?Unadvise@COConnectionPoint@@UEAAJK@Z`
- size: `166`
- prototype: `__int64 __fastcall(COConnectionPoint *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005510`
- `0x180031010`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180005564`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180005564`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000552e`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000552e`

## pseudocode

```c
__int64 __fastcall COConnectionPoint::Unadvise(COConnectionPoint *this, int a2)
{
  unsigned int i; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 v8; // rbx
  __int64 v9; // rcx

  if ( !a2 )
    return 2147942487LL;
  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockSinkResource);
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)this + 12) )
    {
      v6 = -2147220992;
      goto LABEL_7;
    }
    v5 = *((_QWORD *)this + 7);
    if ( a2 == *(_DWORD *)(v5 + 16LL * i + 8) )
      break;
  }
  v8 = 2LL * i;
  v9 = *(_QWORD *)(v5 + 16LL * i);
  *(_QWORD *)(*((_QWORD *)this + 7) + 16LL * i) = 0;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  *(_DWORD *)(*((_QWORD *)this + 7) + 8 * v8 + 8) = 0;
  --*((_DWORD *)this + 11);
  v6 = 0;
LABEL_7:
  CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockSinkResource);
  return v6;
}

```

## disassembly

```asm
0x180005510  mov     [rsp+arg_0], rbx
0x180005515  push    rdi
0x180005516  sub     rsp, 20h
0x18000551a  mov     ebx, edx
0x18000551c  mov     rdi, rcx
0x18000551f  test    edx, edx
0x180005521  jz      loc_1800055AF
0x180005527  lea     rcx, ?g_LockSinkResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockSinkResource
0x18000552e  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180005534  mov     r8d, [rdi+30h]
0x180005538  xor     eax, eax
0x18000553a  nop     word ptr [rax+rax+00h]
0x180005540  cmp     eax, r8d
0x180005543  jnb     short loc_180005558
0x180005545  mov     rcx, [rdi+38h]
0x180005549  mov     edx, eax
0x18000554b  add     rdx, rdx
0x18000554e  cmp     ebx, [rcx+rdx*8+8]
0x180005552  jz      short loc_180005577
0x180005554  inc     eax
0x180005556  jmp     short loc_180005540
0x180005558  mov     ebx, 80040200h
0x18000555d  lea     rcx, ?g_LockSinkResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockSinkResource
0x180005564  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000556a  mov     eax, ebx
0x18000556c  mov     rbx, [rsp+28h+arg_0]
0x180005571  add     rsp, 20h
0x180005575  pop     rdi
0x180005576  retn
0x180005577  mov     ebx, eax
0x180005579  mov     rax, rcx
0x18000557c  add     rbx, rbx
0x18000557f  mov     rcx, [rcx+rbx*8]
0x180005583  mov     qword ptr [rax+rbx*8], 0
0x18000558b  test    rcx, rcx
0x18000558e  jz      short loc_18000559C
0x180005590  mov     rax, [rcx]
0x180005593  mov     rax, [rax+10h]
0x180005597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000559c  mov     rax, [rdi+38h]
0x1800055a0  mov     dword ptr [rax+rbx*8+8], 0
0x1800055a8  dec     dword ptr [rdi+2Ch]
0x1800055ab  xor     ebx, ebx
0x1800055ad  jmp     short loc_18000555D
0x1800055af  mov     eax, 80070057h
0x1800055b4  jmp     short loc_18000556C
```
