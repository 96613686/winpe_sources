# HelloIntervalTickExpired

- ea: `0x140015e70`
- end: `0x140016008`
- name: `HelloIntervalTickExpired`
- size: `408`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x140002030`
- `0x140002bd8`
- `0x140015e70`
- `0x1400165a0`
- `0x140018054`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015f57`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140015f57`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140015ebf`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140015ebf`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140015fb8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140015fb8`

## pseudocode

```c
__int64 __fastcall HelloIntervalTickExpired(__int64 a1, __int64 a2)
{
  __int64 v4; // r8
  char v5; // si
  _DWORD *v6; // rax
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 32));
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 16));
  if ( ((*(_DWORD *)(a1 + 24) - 4) & 0xFFFFFFF7) == 0 )
  {
    if ( *(_BYTE *)(a1 + 320) )
    {
      *(_QWORD *)(a1 + 312) = 0;
      *(_BYTE *)(a1 + 320) = 0;
    }
    else
    {
      ++*(_DWORD *)(a1 + 312);
      v5 = 0;
      if ( *(_DWORD *)(a1 + 312) >= *(_DWORD *)(a1 + 304) )
      {
        if ( ++*(_DWORD *)(a1 + 316) <= 1u )
        {
          v5 = 1;
          *(_DWORD *)(a1 + 312) = 0;
        }
        else
        {
          *(_DWORD *)(a1 + 316) = 0;
          MoveToAbortState2(a1, 0, v4, 8, 1, a2);
        }
      }
      *(_BYTE *)(a1 + 320) = 0;
      if ( v5 )
      {
        v6 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)SstpFsmGlobalInfo + 1);
        if ( v6 )
        {
          v6[4] = 17825800;
          *((_WORD *)v6 + 11) = 2048;
          *((_WORD *)v6 + 12) = 0;
          *((_WORD *)v6 + 10) = __ROR2__(*((_WORD *)v6 + 8), 8);
          SendControlFrame(a1);
        }
        else
        {
          *(_DWORD *)(a1 + 312) = *(_DWORD *)(a1 + 304);
        }
      }
    }
  }
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 16));
  result = DereferenceRefCount(a1 + 32);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer) & 0x84;
    if ( (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140015e70  push    rbx
0x140015e72  push    rbp
0x140015e73  push    rsi
0x140015e74  push    rdi
0x140015e75  push    r13
0x140015e77  push    r14
0x140015e79  sub     rsp, 38h
0x140015e7d  mov     r14, rdx
0x140015e80  mov     rbx, rcx
0x140015e83  mov     rcx, cs:WPP_GLOBAL_Control
0x140015e8a  lea     r13, WPP_GLOBAL_Control
0x140015e91  cmp     rcx, r13
0x140015e94  jz      short loc_140015EB7
0x140015e96  mov     eax, [rcx+2Ch]
0x140015e99  and     eax, 84h
0x140015e9e  cmp     al, 84h
0x140015ea0  jnz     short loc_140015EB7
0x140015ea2  mov     rcx, [rcx+18h]
0x140015ea6  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140015ead  mov     edx, 1Ch
0x140015eb2  call    WPP_SF_
0x140015eb7  lock inc dword ptr [rbx+20h]
0x140015ebb  lea     rcx, [rbx+10h]; SpinLock
0x140015ebf  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140015ec6  nop     dword ptr [rax+rax+00h]
0x140015ecb  mov     eax, [rbx+18h]
0x140015ece  sub     eax, 4
0x140015ed1  test    eax, 0FFFFFFF7h
0x140015ed6  jnz     loc_140015FB4
0x140015edc  cmp     byte ptr [rbx+140h], 0
0x140015ee3  jnz     loc_140015FA2
0x140015ee9  inc     dword ptr [rbx+138h]
0x140015eef  xor     sil, sil
0x140015ef2  mov     eax, [rbx+138h]
0x140015ef8  cmp     eax, [rbx+130h]
0x140015efe  jb      short loc_140015F40
0x140015f00  inc     dword ptr [rbx+13Ch]
0x140015f06  cmp     dword ptr [rbx+13Ch], 1
0x140015f0d  jbe     short loc_140015F33
0x140015f0f  xor     edx, edx
0x140015f11  mov     [rsp+68h+var_40], r14
0x140015f16  mov     rcx, rbx
0x140015f19  mov     dword ptr [rbx+13Ch], 0
0x140015f23  mov     [rsp+68h+var_48], 1
0x140015f28  lea     r9d, [rdx+8]
0x140015f2c  call    MoveToAbortState2
0x140015f31  jmp     short loc_140015F40
0x140015f33  mov     sil, 1
0x140015f36  mov     dword ptr [rbx+138h], 0
0x140015f40  mov     byte ptr [rbx+140h], 0
0x140015f47  test    sil, sil
0x140015f4a  jz      short loc_140015FB4
0x140015f4c  mov     rcx, cs:SstpFsmGlobalInfo
0x140015f53  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x140015f57  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140015f5e  nop     dword ptr [rax+rax+00h]
0x140015f63  mov     rdx, rax
0x140015f66  test    rax, rax
0x140015f69  jnz     short loc_140015F79
0x140015f6b  mov     eax, [rbx+130h]
0x140015f71  mov     [rbx+138h], eax
0x140015f77  jmp     short loc_140015FB4
0x140015f79  mov     dword ptr [rax+10h], 1100008h
0x140015f80  mov     word ptr [rax+16h], 800h
0x140015f86  xor     eax, eax
0x140015f88  mov     [rdx+18h], ax
0x140015f8c  movzx   eax, word ptr [rdx+10h]
0x140015f90  ror     ax, 8
0x140015f94  mov     [rdx+14h], ax
0x140015f98  mov     rcx, rbx
0x140015f9b  call    SendControlFrame
0x140015fa0  jmp     short loc_140015FB4
0x140015fa2  mov     qword ptr [rbx+138h], 0
0x140015fad  mov     byte ptr [rbx+140h], 0
0x140015fb4  lea     rcx, [rbx+10h]; SpinLock
0x140015fb8  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140015fbf  nop     dword ptr [rax+rax+00h]
0x140015fc4  lea     rcx, [rbx+20h]
0x140015fc8  call    DereferenceRefCount
0x140015fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x140015fd4  cmp     rcx, r13
0x140015fd7  jz      short loc_140015FFA
0x140015fd9  mov     eax, [rcx+2Ch]
0x140015fdc  and     eax, 84h
0x140015fe1  cmp     al, 84h
0x140015fe3  jnz     short loc_140015FFA
0x140015fe5  mov     rcx, [rcx+18h]
0x140015fe9  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140015ff0  mov     edx, 1Dh
0x140015ff5  call    WPP_SF_
0x140015ffa  add     rsp, 38h
0x140015ffe  pop     r14
0x140016000  pop     r13
0x140016002  pop     rdi
0x140016003  pop     rsi
0x140016004  pop     rbp
0x140016005  pop     rbx
0x140016006  retn
```
