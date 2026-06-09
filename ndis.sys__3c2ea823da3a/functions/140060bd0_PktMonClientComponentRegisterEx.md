# PktMonClientComponentRegisterEx

- ea: `0x140060bd0`
- end: `0x140060cca`
- name: `PktMonClientComponentRegisterEx`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140060b60`

## callees

- `0x140060bd0`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140060cb2`
- `ntoskrnl!KeReleaseMutex` at `0x140060cb2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140060c2e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140060c2e`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400ed1ba`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400ed1ba`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140060c9d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140060c9d`

## pseudocode

```c
__int64 __fastcall PktMonClientComponentRegisterEx(__int64 a1, __int64 a2, __int64 a3, int a4, int a5)
{
  unsigned int v9; // ebx
  __int64 v11; // rax
  __int128 v12; // [rsp+30h] [rbp-58h] BYREF
  __int128 v13; // [rsp+40h] [rbp-48h]
  __int128 v14; // [rsp+50h] [rbp-38h]

  v12 = 0;
  v13 = 0;
  v14 = 0;
  if ( (_QWORD)xmmword_14011D750 )
  {
    KeWaitForSingleObject(&PktMonCompMutex, Executive, 0, 0, 0);
    if ( (_QWORD)xmmword_14011D750 )
    {
      if ( *(_QWORD *)(a1 + 40) )
      {
        v9 = -1073741816;
      }
      else
      {
        *(_DWORD *)(a1 + 32) = 0;
        *(_QWORD *)(a1 + 24) = a1 + 16;
        *(_QWORD *)(a1 + 16) = a1 + 16;
        LOWORD(v12) = 48;
        *((_QWORD *)&v12 + 1) = a1;
        *(_QWORD *)&v13 = a2;
        *((_QWORD *)&v13 + 1) = a3;
        LODWORD(v14) = a4;
        *(_QWORD *)((char *)&v14 + 4) = 0x400000003LL;
        if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
        {
          v9 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64))(*((_QWORD *)&xmmword_14011D750 + 1) + 8LL))(
                 xmmword_14011D750,
                 &v12,
                 a1 + 40);
          if ( !v9 )
          {
            *(_DWORD *)(a1 + 52) = a5;
            *(_DWORD *)(a1 + 48) = a4;
            v11 = PktMonCompList;
            if ( *(__int64 **)(PktMonCompList + 8) != &PktMonCompList )
              __fastfail(3u);
            ++PktMonCompCount;
            *(_QWORD *)a1 = PktMonCompList;
            *(_QWORD *)(a1 + 8) = &PktMonCompList;
            *(_QWORD *)(v11 + 8) = a1;
            PktMonCompList = a1;
          }
          ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
        }
        else
        {
          v9 = -1073741738;
        }
      }
    }
    else
    {
      v9 = -1073741661;
    }
    KeReleaseMutex(&PktMonCompMutex, 0);
  }
  else
  {
    return (unsigned int)-1073741661;
  }
  return v9;
}

```

## disassembly

```asm
0x140060bd0  push    rbx
0x140060bd2  push    rbp
0x140060bd3  push    rsi
0x140060bd4  push    rdi
0x140060bd5  push    r14
0x140060bd7  sub     rsp, 60h
0x140060bdb  cmp     qword ptr cs:xmmword_14011D750, 0
0x140060be3  xorps   xmm0, xmm0
0x140060be6  movups  [rsp+88h+var_58], xmm0
0x140060beb  mov     esi, r9d
0x140060bee  mov     rbx, r8
0x140060bf1  movups  [rsp+88h+var_48], xmm0
0x140060bf6  mov     rbp, rdx
0x140060bf9  mov     rdi, rcx
0x140060bfc  movups  [rsp+88h+var_38], xmm0
0x140060c01  jnz     short loc_140060C16
0x140060c03  mov     ebx, 0C00000A3h
0x140060c08  mov     eax, ebx
0x140060c0a  add     rsp, 60h
0x140060c0e  pop     r14
0x140060c10  pop     rdi
0x140060c11  pop     rsi
0x140060c12  pop     rbp
0x140060c13  pop     rbx
0x140060c14  retn
0x140060c16  xor     r9d, r9d; Alertable
0x140060c19  mov     [rsp+88h+Timeout], 0; Timeout
0x140060c22  xor     r8d, r8d; WaitMode
0x140060c25  lea     rcx, PktMonCompMutex; Object
0x140060c2c  xor     edx, edx; WaitReason
0x140060c2e  call    cs:__imp_KeWaitForSingleObject
0x140060c35  nop     dword ptr [rax+rax+00h]
0x140060c3a  cmp     qword ptr cs:xmmword_14011D750, 0
0x140060c42  jz      short loc_140060CC3
0x140060c44  cmp     qword ptr [rdi+28h], 0
0x140060c49  jz      loc_1400ED174
0x140060c4f  mov     ebx, 0C0000008h
0x140060c54  jmp     short loc_140060CA9
0x140060c56  mov     eax, [rsp+88h+arg_20]
0x140060c5d  lea     rdx, PktMonCompList
0x140060c64  mov     [rdi+34h], eax
0x140060c67  mov     [rdi+30h], esi
0x140060c6a  mov     rax, cs:PktMonCompList
0x140060c71  cmp     [rax+8], rdx
0x140060c75  jz      short loc_140060C7E
0x140060c77  mov     ecx, 3
0x140060c7c  int     29h; Win8: RtlFailFast(ecx)
0x140060c7e  inc     cs:PktMonCompCount
0x140060c84  mov     [rdi], rax
0x140060c87  mov     [rdi+8], rdx
0x140060c8b  mov     [rax+8], rdi
0x140060c8f  mov     cs:PktMonCompList, rdi
0x140060c96  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x140060c9d  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140060ca4  nop     dword ptr [rax+rax+00h]
0x140060ca9  xor     edx, edx; Wait
0x140060cab  lea     rcx, PktMonCompMutex; Mutex
0x140060cb2  call    cs:__imp_KeReleaseMutex
0x140060cb9  nop     dword ptr [rax+rax+00h]
0x140060cbe  jmp     loc_140060C08
0x140060cc3  mov     ebx, 0C00000A3h
0x140060cc8  jmp     short loc_140060CA9
0x1400ed174  lea     rax, [rdi+10h]
0x1400ed178  mov     dword ptr [rdi+20h], 0
0x1400ed17f  mov     [rax+8], rax
0x1400ed183  mov     [rax], rax
0x1400ed186  mov     eax, 30h ; '0'
0x1400ed18b  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x1400ed192  mov     word ptr [rsp+88h+var_58], ax
0x1400ed197  mov     qword ptr [rsp+88h+var_58+8], rdi
0x1400ed19c  mov     qword ptr [rsp+88h+var_48], rbp
0x1400ed1a1  mov     qword ptr [rsp+88h+var_48+8], rbx
0x1400ed1a6  mov     dword ptr [rsp+88h+var_38], esi
0x1400ed1aa  mov     dword ptr [rsp+88h+var_38+4], 3
0x1400ed1b2  mov     dword ptr [rsp+88h+var_38+8], 4
0x1400ed1ba  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x1400ed1c1  nop     dword ptr [rax+rax+00h]
0x1400ed1c6  test    al, al
0x1400ed1c8  jnz     short loc_1400ED1D4
0x1400ed1ca  mov     ebx, 0C0000056h
0x1400ed1cf  jmp     loc_140060CA9
0x1400ed1d4  mov     rax, qword ptr cs:xmmword_14011D750+8
0x1400ed1db  lea     r8, [rdi+28h]
0x1400ed1df  mov     rcx, qword ptr cs:xmmword_14011D750
0x1400ed1e6  lea     rdx, [rsp+88h+var_58]
0x1400ed1eb  mov     rax, [rax+8]
0x1400ed1ef  call    _guard_dispatch_icall
0x1400ed1f4  mov     ebx, eax
0x1400ed1f6  test    eax, eax
0x1400ed1f8  jnz     loc_140060C96
0x1400ed1fe  jmp     loc_140060C56
```
