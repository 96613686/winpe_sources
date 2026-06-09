# MoveToCallDisconnectedState

- ea: `0x140016cf0`
- end: `0x140016e7e`
- name: `MoveToCallDisconnectedState`
- size: `398`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `7`
- tags: ``

## callers

- `0x140005110`
- `0x140014150`
- `0x140014220`
- `0x140014a90`
- `0x140014c30`
- `0x140014d00`
- `0x140014ef0`
- `0x1400150e0`
- `0x1400155b0`
- `0x140016414`
- `0x1400165a0`
- `0x140016734`
- `0x1400169a4`
- `0x14001707c`
- `0x140017204`
- `0x140017550`

## callees

- `0x140002030`
- `0x140002bd8`
- `0x140002f88`
- `0x1400054ec`
- `0x1400055f8`
- `0x140005ef0`
- `0x140016cf0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140016da9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140016dd3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140016e39`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140016da9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140016dd3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140016e39`

## pseudocode

```c
void __fastcall MoveToCallDisconnectedState(__int64 a1, __int64 a2, _BYTE *a3)
{
  char v4; // bp
  KSPIN_LOCK *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rbx

  v4 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids, a1 + 364);
    }
  }
  if ( ((*(_DWORD *)(a1 + 24) - 1) & 0xFFFFFFF7) != 0 )
  {
    LOBYTE(a2) = v4;
    *(_DWORD *)(a1 + 24) = *(_BYTE *)(a1 + 326) != 0 ? 1 : 9;
    SstpTimerDisable(a1 + 48, a2);
    v6 = (KSPIN_LOCK *)(a1 + 16);
    if ( *(_BYTE *)(a1 + 325) )
    {
      KeReleaseSpinLockFromDpcLevel(v6);
      (*((void (__fastcall **)(_QWORD, __int64))SstpFsmGlobalInfo + 12))(*(_QWORD *)(a1 + 136), 3221226049LL);
    }
    else
    {
      KeReleaseSpinLockFromDpcLevel(v6);
      LOBYTE(v8) = *(_BYTE *)(a1 + 322);
      LOBYTE(v9) = *(_BYTE *)(a1 + 321);
      (*((void (__fastcall **)(_QWORD, __int64, __int64))SstpFsmGlobalInfo + 13))(*(_QWORD *)(a1 + 136), v9, v8);
    }
    LOBYTE(v7) = v4;
    SstpTimerDelete(a1 + 48, v7);
    if ( a3 )
      *a3 = 1;
    v10 = a1 + 32;
    DereferenceRefCount(v10);
    DereferenceRefCount(v10);
    DereferenceRefCount(v10);
  }
  else
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 16));
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
}

```

## disassembly

```asm
0x140016cf0  push    rbx
0x140016cf2  push    rbp
0x140016cf3  push    rsi
0x140016cf4  push    rdi
0x140016cf5  push    r15
0x140016cf7  sub     rsp, 20h
0x140016cfb  mov     rdi, r8
0x140016cfe  mov     bpl, dl
0x140016d01  mov     rbx, rcx
0x140016d04  mov     rcx, cs:WPP_GLOBAL_Control
0x140016d0b  lea     r15, WPP_GLOBAL_Control
0x140016d12  cmp     rcx, r15
0x140016d15  jz      short loc_140016D6D
0x140016d17  mov     eax, [rcx+2Ch]
0x140016d1a  and     eax, 84h
0x140016d1f  cmp     al, 84h
0x140016d21  jnz     short loc_140016D38
0x140016d23  mov     rcx, [rcx+18h]
0x140016d27  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140016d2e  mov     edx, 2Eh ; '.'
0x140016d33  call    WPP_SF_
0x140016d38  mov     rcx, cs:WPP_GLOBAL_Control
0x140016d3f  cmp     rcx, r15
0x140016d42  jz      short loc_140016D6D
0x140016d44  mov     eax, [rcx+2Ch]
0x140016d47  test    al, 4
0x140016d49  jz      short loc_140016D6D
0x140016d4b  cmp     byte ptr [rcx+29h], 3
0x140016d4f  jb      short loc_140016D6D
0x140016d51  mov     rcx, [rcx+18h]
0x140016d55  lea     r9, [rbx+16Ch]
0x140016d5c  mov     edx, 2Fh ; '/'
0x140016d61  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140016d68  call    WPP_SF__guid_
0x140016d6d  mov     eax, [rbx+18h]
0x140016d70  dec     eax
0x140016d72  test    eax, 0FFFFFFF7h
0x140016d77  jz      loc_140016E35
0x140016d7d  mov     al, [rbx+146h]
0x140016d83  mov     dl, bpl
0x140016d86  neg     al
0x140016d88  sbb     ecx, ecx
0x140016d8a  and     ecx, 0FFFFFFF8h
0x140016d8d  add     ecx, 9
0x140016d90  mov     [rbx+18h], ecx
0x140016d93  lea     rcx, [rbx+30h]
0x140016d97  call    SstpTimerDisable
0x140016d9c  cmp     byte ptr [rbx+145h], 0
0x140016da3  lea     rcx, [rbx+10h]; SpinLock
0x140016da7  jz      short loc_140016DD3
0x140016da9  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140016db0  nop     dword ptr [rax+rax+00h]
0x140016db5  mov     rax, cs:SstpFsmGlobalInfo
0x140016dbc  mov     edx, 0C0000241h
0x140016dc1  mov     rcx, [rbx+88h]
0x140016dc8  mov     rax, [rax+60h]
0x140016dcc  call    _guard_dispatch_icall
0x140016dd1  jmp     short loc_140016E03
0x140016dd3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140016dda  nop     dword ptr [rax+rax+00h]
0x140016ddf  mov     rax, cs:SstpFsmGlobalInfo
0x140016de6  mov     r8b, [rbx+142h]
0x140016ded  mov     dl, [rbx+141h]
0x140016df3  mov     rcx, [rbx+88h]
0x140016dfa  mov     rax, [rax+68h]
0x140016dfe  call    _guard_dispatch_icall
0x140016e03  mov     dl, bpl
0x140016e06  lea     rcx, [rbx+30h]
0x140016e0a  call    SstpTimerDelete
0x140016e0f  test    rdi, rdi
0x140016e12  jz      short loc_140016E17
0x140016e14  mov     byte ptr [rdi], 1
0x140016e17  add     rbx, 20h ; ' '
0x140016e1b  mov     rcx, rbx
0x140016e1e  call    DereferenceRefCount
0x140016e23  mov     rcx, rbx
0x140016e26  call    DereferenceRefCount
0x140016e2b  mov     rcx, rbx
0x140016e2e  call    DereferenceRefCount
0x140016e33  jmp     short loc_140016E45
0x140016e35  lea     rcx, [rbx+10h]; SpinLock
0x140016e39  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140016e40  nop     dword ptr [rax+rax+00h]
0x140016e45  mov     rcx, cs:WPP_GLOBAL_Control
0x140016e4c  cmp     rcx, r15
0x140016e4f  jz      short loc_140016E72
0x140016e51  mov     eax, [rcx+2Ch]
0x140016e54  and     eax, 84h
0x140016e59  cmp     al, 84h
0x140016e5b  jnz     short loc_140016E72
0x140016e5d  mov     rcx, [rcx+18h]
0x140016e61  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140016e68  mov     edx, 30h ; '0'
0x140016e6d  call    WPP_SF_
0x140016e72  add     rsp, 20h
0x140016e76  pop     r15
0x140016e78  pop     rdi
0x140016e79  pop     rsi
0x140016e7a  pop     rbp
0x140016e7b  pop     rbx
0x140016e7c  retn
```
