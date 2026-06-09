# DockingProviders::SubmitWork(Work *)

- ea: `0x180016f0c`
- end: `0x180016fed`
- name: `?SubmitWork@DockingProviders@@QEAAJPEAVWork@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, struct Work *)`
- caller_count: `9`
- callee_count: `6`
- tags: ``

## callers

- `0x18000af40`
- `0x18000b2f0`
- `0x18000b390`
- `0x18000b470`
- `0x18000b520`
- `0x18000b5c0`
- `0x18000b660`
- `0x180018fc0`
- `0x180019900`

## callees

- `0x18000d460`
- `0x180010664`
- `0x180013b24`
- `0x180016f0c`
- `0x18001a770`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180016f5f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180016f5f`

## pseudocode

```c
__int64 __fastcall DockingProviders::SubmitWork(PSRWLOCK SRWLock, struct Work *a2)
{
  int v4; // ebx
  int v5; // eax
  PSRWLOCK v7; // [rsp+30h] [rbp-38h] BYREF
  char v8; // [rsp+38h] [rbp-30h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, SRWLock, a2);
  }
  v7 = SRWLock;
  AcquireSRWLockShared(SRWLock);
  v8 = 1;
  if ( a2 )
  {
    v5 = WorkItems::SubmitWork((WorkItems *)&SRWLock[4], a2);
    v4 = v5;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qqd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        127,
        &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids,
        SRWLock,
        a2,
        v5);
    }
    if ( v4 >= 0 )
      v4 = 0;
    else
      (**(void (__fastcall ***)(struct Work *, __int64))a2)(a2, 1);
  }
  else
  {
    v4 = -2147024882;
  }
  ReadLock::~ReadLock((ReadLock *)&v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180016f0c  push    rbx
0x180016f0e  push    rbp
0x180016f0f  push    rsi
0x180016f10  push    rdi
0x180016f11  sub     rsp, 48h
0x180016f15  mov     rdi, rdx
0x180016f18  mov     rsi, rcx
0x180016f1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f22  lea     rbp, WPP_GLOBAL_Control
0x180016f29  cmp     rcx, rbp
0x180016f2c  jz      short loc_180016F57
0x180016f2e  cmp     byte ptr [rcx+19h], 3
0x180016f32  jb      short loc_180016F57
0x180016f34  test    byte ptr [rcx+1Ch], 1
0x180016f38  jz      short loc_180016F57
0x180016f3a  mov     rcx, [rcx+10h]
0x180016f3e  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180016f45  mov     edx, 7Eh ; '~'
0x180016f4a  mov     [rsp+68h+var_48], rdi
0x180016f4f  mov     r9, rsi
0x180016f52  call    WPP_SF_qq
0x180016f57  mov     rcx, rsi; SRWLock
0x180016f5a  mov     [rsp+68h+var_38], rsi
0x180016f5f  call    cs:__imp_AcquireSRWLockShared
0x180016f65  mov     [rsp+68h+var_30], 1
0x180016f6a  test    rdi, rdi
0x180016f6d  jnz     short loc_180016F76
0x180016f6f  mov     ebx, 8007000Eh
0x180016f74  jmp     short loc_180016FD8
0x180016f76  lea     rcx, [rsi+20h]; this
0x180016f7a  mov     rdx, rdi; struct Work *
0x180016f7d  call    ?SubmitWork@WorkItems@@QEAAJPEAVWork@@@Z; WorkItems::SubmitWork(Work *)
0x180016f82  mov     ebx, eax
0x180016f84  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f8b  cmp     rcx, rbp
0x180016f8e  jz      short loc_180016FBD
0x180016f90  cmp     byte ptr [rcx+19h], 3
0x180016f94  jb      short loc_180016FBD
0x180016f96  test    byte ptr [rcx+1Ch], 1
0x180016f9a  jz      short loc_180016FBD
0x180016f9c  mov     rcx, [rcx+10h]
0x180016fa0  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180016fa7  mov     [rsp+68h+var_40], eax
0x180016fab  mov     edx, 7Fh
0x180016fb0  mov     r9, rsi
0x180016fb3  mov     [rsp+68h+var_48], rdi
0x180016fb8  call    WPP_SF_qqd
0x180016fbd  test    ebx, ebx
0x180016fbf  jns     short loc_180016FD6
0x180016fc1  mov     rax, [rdi]
0x180016fc4  mov     edx, 1
0x180016fc9  mov     rcx, rdi
0x180016fcc  mov     rax, [rax]
0x180016fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fd4  jmp     short loc_180016FD8
0x180016fd6  xor     ebx, ebx
0x180016fd8  lea     rcx, [rsp+68h+var_38]; this
0x180016fdd  call    ??1ReadLock@@QEAA@XZ; ReadLock::~ReadLock(void)
0x180016fe2  mov     eax, ebx
0x180016fe4  add     rsp, 48h
0x180016fe8  pop     rdi
0x180016fe9  pop     rsi
0x180016fea  pop     rbp
0x180016feb  pop     rbx
0x180016fec  retn
```
