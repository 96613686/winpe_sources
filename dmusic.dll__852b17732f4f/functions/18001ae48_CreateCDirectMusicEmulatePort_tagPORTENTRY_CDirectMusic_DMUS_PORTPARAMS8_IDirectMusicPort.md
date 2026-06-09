# CreateCDirectMusicEmulatePort(tagPORTENTRY *,CDirectMusic *,_DMUS_PORTPARAMS8 *,IDirectMusicPort * *)

- ea: `0x18001ae48`
- end: `0x18001afa0`
- name: `?CreateCDirectMusicEmulatePort@@YAJPEAUtagPORTENTRY@@PEAVCDirectMusic@@PEAU_DMUS_PORTPARAMS8@@PEAPEAUIDirectMusicPort@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(struct tagPORTENTRY *, struct CDirectMusic *, struct _DMUS_PORTPARAMS8 *, struct IDirectMusicPort **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800131a0`

## callees

- `0x18001aae0`
- `0x18001ae48`
- `0x18001c048`
- `0x18001c38c`
- `0x180022010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001ae7c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001af23`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001ae7c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001af23`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreateCDirectMusicEmulatePort(
        struct tagPORTENTRY *a1,
        struct CDirectMusic *a2,
        struct _DMUS_PORTPARAMS8 *a3,
        struct IDirectMusicPort **a4)
{
  CDirectMusicEmulatePort *v8; // rax
  struct IDirectMusicPort *v9; // rbx
  _QWORD *v10; // rcx
  CDirectMusicEmulateInPort *v11; // rax
  __int64 result; // rax
  unsigned int v13; // edi

  *a4 = 0;
  if ( *((_DWORD *)a1 + 14) == 1 )
  {
    v8 = (CDirectMusicEmulatePort *)malloc(0x1E8u);
    v9 = (struct IDirectMusicPort *)v8;
    if ( v8 )
    {
      CDirectMusicEmulatePort::CDirectMusicEmulatePort(v8, a1, a2);
      *v10 = &CDirectMusicEmulateOutPort::`vftable'{for `IDirectMusicPort'};
      v10[1] = &CDirectMusicEmulatePort::`vftable'{for `IDirectMusicThru'};
      v10[2] = &CDirectMusicEmulateOutPort::`vftable'{for `IDirectMusicPortPrivate'};
      v10[3] = &CDirectMusicEmulateInPort::`vftable'{for `IKsControl'};
      v10[49] = 0;
      v10[55] = 0;
      v10 += 56;
      *v10 = 102;
      v10[1] = 0;
      *((_DWORD *)v10 + 4) = 0;
      v10[3] = 0;
      CPool<DMQUEUEDEVENT>::RefillFreeList();
      v9[60].lpVtbl = 0;
    }
    else
    {
      v9 = 0;
    }
  }
  else
  {
    v11 = (CDirectMusicEmulateInPort *)malloc(0x86B8u);
    if ( v11 )
      v9 = (struct IDirectMusicPort *)CDirectMusicEmulateInPort::CDirectMusicEmulateInPort(v11, a1, a2);
    else
      v9 = 0;
  }
  if ( !v9 )
    return 2147942414LL;
  result = ((__int64 (__fastcall *)(struct IDirectMusicPort *, struct _DMUS_PORTPARAMS8 *))v9->lpVtbl[1].AddRef)(v9, a3);
  v13 = result;
  if ( (int)result >= 0 )
  {
    *a4 = v9;
  }
  else
  {
    ((void (__fastcall *)(struct IDirectMusicPort *, __int64))v9->lpVtbl[1].QueryInterface)(v9, 1);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x18001ae48  mov     [rsp+arg_8], rbx
0x18001ae4d  mov     [rsp+arg_10], rbp
0x18001ae52  push    rsi
0x18001ae53  push    rdi
0x18001ae54  push    r14
0x18001ae56  sub     rsp, 20h
0x18001ae5a  mov     rsi, r9
0x18001ae5d  mov     r14, r8
0x18001ae60  mov     rbp, rdx
0x18001ae63  mov     rdi, rcx
0x18001ae66  mov     qword ptr [r9], 0
0x18001ae6d  cmp     dword ptr [rcx+38h], 1
0x18001ae71  jnz     loc_18001AF1E
0x18001ae77  mov     ecx, 1E8h; Size
0x18001ae7c  call    cs:__imp_malloc
0x18001ae82  mov     rbx, rax
0x18001ae85  mov     [rsp+38h+arg_0], rax
0x18001ae8a  test    rax, rax
0x18001ae8d  jz      loc_18001AF1A
0x18001ae93  mov     r8, rbp; struct CDirectMusic *
0x18001ae96  mov     rdx, rdi; struct tagPORTENTRY *
0x18001ae99  mov     rcx, rax; this
0x18001ae9c  call    ??0CDirectMusicEmulatePort@@QEAA@PEAUtagPORTENTRY@@PEAVCDirectMusic@@@Z; CDirectMusicEmulatePort::CDirectMusicEmulatePort(tagPORTENTRY *,CDirectMusic *)
0x18001aea1  nop
0x18001aea2  lea     rax, ??_7CDirectMusicEmulateOutPort@@6BIDirectMusicPort@@@; const CDirectMusicEmulateOutPort::`vftable'{for `IDirectMusicPort'}
0x18001aea9  mov     [rcx], rax
0x18001aeac  lea     rax, ??_7CDirectMusicEmulatePort@@6BIDirectMusicThru@@@; const CDirectMusicEmulatePort::`vftable'{for `IDirectMusicThru'}
0x18001aeb3  mov     [rcx+8], rax
0x18001aeb7  lea     rax, ??_7CDirectMusicEmulateOutPort@@6BIDirectMusicPortPrivate@@@; const CDirectMusicEmulateOutPort::`vftable'{for `IDirectMusicPortPrivate'}
0x18001aebe  mov     [rcx+10h], rax
0x18001aec2  lea     rax, ??_7CDirectMusicEmulateInPort@@6BIKsControl@@@; const CDirectMusicEmulateInPort::`vftable'{for `IKsControl'}
0x18001aec9  mov     [rcx+18h], rax
0x18001aecd  mov     qword ptr [rcx+188h], 0
0x18001aed8  mov     qword ptr [rcx+1B8h], 0
0x18001aee3  lea     rcx, [rcx+1C0h]
0x18001aeea  mov     qword ptr [rcx], 66h ; 'f'
0x18001aef1  mov     qword ptr [rcx+8], 0
0x18001aef9  mov     dword ptr [rcx+10h], 0
0x18001af00  mov     qword ptr [rcx+18h], 0
0x18001af08  call    ?RefillFreeList@?$CPool@UDMQUEUEDEVENT@@@@AEAA_NXZ; CPool<DMQUEUEDEVENT>::RefillFreeList(void)
0x18001af0d  mov     qword ptr [rbx+1E0h], 0
0x18001af18  jmp     short loc_18001AF1C
0x18001af1a  xor     ebx, ebx
0x18001af1c  jmp     short loc_18001AF48
0x18001af1e  mov     ecx, 86B8h; Size
0x18001af23  call    cs:__imp_malloc
0x18001af29  mov     [rsp+38h+arg_0], rax
0x18001af2e  test    rax, rax
0x18001af31  jz      short loc_18001AF46
0x18001af33  mov     r8, rbp; struct CDirectMusic *
0x18001af36  mov     rdx, rdi; struct tagPORTENTRY *
0x18001af39  mov     rcx, rax; this
0x18001af3c  call    ??0CDirectMusicEmulateInPort@@QEAA@PEAUtagPORTENTRY@@PEAVCDirectMusic@@@Z; CDirectMusicEmulateInPort::CDirectMusicEmulateInPort(tagPORTENTRY *,CDirectMusic *)
0x18001af41  mov     rbx, rax
0x18001af44  jmp     short loc_18001AF48
0x18001af46  xor     ebx, ebx
0x18001af48  test    rbx, rbx
0x18001af4b  jnz     short loc_18001AF54
0x18001af4d  mov     eax, 8007000Eh
0x18001af52  jmp     short loc_18001AF8D
0x18001af54  mov     rax, [rbx]
0x18001af57  mov     rdx, r14
0x18001af5a  mov     rcx, rbx
0x18001af5d  mov     rax, [rax+0A8h]
0x18001af64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af69  mov     edi, eax
0x18001af6b  test    eax, eax
0x18001af6d  jns     short loc_18001AF8A
0x18001af6f  mov     r8, [rbx]
0x18001af72  mov     edx, 1
0x18001af77  mov     rcx, rbx
0x18001af7a  mov     rax, [r8+0A0h]
0x18001af81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af86  mov     eax, edi
0x18001af88  jmp     short loc_18001AF8D
0x18001af8a  mov     [rsi], rbx
0x18001af8d  mov     rbx, [rsp+38h+arg_8]
0x18001af92  mov     rbp, [rsp+38h+arg_10]
0x18001af97  add     rsp, 20h
0x18001af9b  pop     r14
0x18001af9d  pop     rdi
0x18001af9e  pop     rsi
0x18001af9f  retn
```
