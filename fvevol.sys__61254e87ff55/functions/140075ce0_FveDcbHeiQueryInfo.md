# FveDcbHeiQueryInfo

- ea: `0x140075ce0`
- end: `0x140075fa1`
- name: `FveDcbHeiQueryInfo`
- size: `705`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000afb4`
- `0x140023040`
- `0x140075ce0`
- `0x1400dce00`
- `0x1400dd144`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140075dd6`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140075dd6`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140075f2c`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140075f2c`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140075da6`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140075e02`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140075da6`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140075e02`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140075f04`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140075f46`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140075f04`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140075f46`

## pseudocode

```c
__int64 __fastcall FveDcbHeiQueryInfo(__int64 a1, int *a2, unsigned int a3, char a4)
{
  __int64 v8; // rax
  __int64 v9; // rbp
  _DWORD *v10; // rdi
  unsigned int v11; // r14d
  _QWORD *v12; // r12
  NTSTATUS v13; // r15d
  bool v14; // r15
  int v15; // ecx
  int v16; // eax
  _BYTE v18[216]; // [rsp+30h] [rbp-D8h] BYREF

  memset(v18, 0, 0x90u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids);
  }
  if ( !a1 )
    return 0;
  v8 = *(_QWORD *)(a1 + 200);
  if ( !v8 )
    return 0;
  if ( *(_DWORD *)(a1 + 176) != 3 )
    return 0;
  v9 = *(_QWORD *)(a1 + 8);
  if ( !v9 || !*(_QWORD *)(v9 + 200) || *(_DWORD *)(v8 + 8) != 2 )
    return 0;
  v10 = 0;
  v11 = 0;
  if ( !a4 )
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v9 + 24));
  v12 = *(_QWORD **)(v9 + 200);
  v13 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v12 + 1), v12, File, 1u, 0x20u);
  if ( v13 >= 0 )
    v10 = (_DWORD *)*v12;
  v14 = v13 >= 0;
  if ( v10 )
  {
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a1 + 24));
    v11 = 4;
    if ( a2 && a3 >= 4 )
    {
      *a2 = 0;
      FvepAcquireDevFveLock(v10, v18, 0);
      v15 = 0;
      *a2 = 0;
      v16 = v10[209];
      if ( v16 != 5 && v16 != 6 && v16 != 7 && v16 != 8 )
      {
        *a2 = 1;
        v15 = 1;
        if ( v10[209] != 1 )
        {
          *a2 = 3;
          v15 = 3;
          if ( v10[209] == 2 && (v10[213] & 0x200) != 0 )
          {
            *a2 = 7;
            v15 = 7;
            if ( (v10[202] & 0x40) != 0 )
            {
              v15 = 15;
              *a2 = 15;
            }
            if ( (v10[213] & 2) == 0 )
            {
              v15 |= 0x10u;
              *a2 = v15;
            }
          }
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          63,
          WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
          *((unsigned int *)v12 + 10),
          v15);
      }
      FvepReleaseDevFveLock(v18);
    }
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a1 + 24));
  }
  if ( v14 )
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v12 + 1), v12, 0x20u);
  if ( !a4 )
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v9 + 24));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x140075ce0  mov     [rsp+arg_18], r9b
0x140075ce5  push    rbx
0x140075ce6  push    rbp
0x140075ce7  push    rsi
0x140075ce8  push    rdi
0x140075ce9  push    r12
0x140075ceb  push    r13
0x140075ced  push    r14
0x140075cef  push    r15
0x140075cf1  sub     rsp, 0C8h
0x140075cf8  mov     r13d, r8d
0x140075cfb  mov     rsi, rdx
0x140075cfe  mov     rbx, rcx
0x140075d01  xor     edx, edx; Val
0x140075d03  mov     r8d, 90h; Size
0x140075d09  lea     rcx, [rsp+108h+var_D8]; void *
0x140075d0e  mov     r15b, r9b
0x140075d11  call    memset
0x140075d16  mov     rcx, cs:WPP_GLOBAL_Control
0x140075d1d  lea     rax, WPP_GLOBAL_Control
0x140075d24  cmp     rcx, rax
0x140075d27  jz      short loc_140075D4D
0x140075d29  test    dword ptr [rcx+2Ch], 400h
0x140075d30  jz      short loc_140075D4D
0x140075d32  cmp     byte ptr [rcx+29h], 5
0x140075d36  jb      short loc_140075D4D
0x140075d38  mov     rcx, [rcx+18h]
0x140075d3c  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140075d43  mov     edx, 3Eh ; '>'
0x140075d48  call    WPP_SF_
0x140075d4d  test    rbx, rbx
0x140075d50  jz      loc_140075F8A
0x140075d56  mov     rax, [rbx+0C8h]
0x140075d5d  test    rax, rax
0x140075d60  jz      loc_140075F8A
0x140075d66  cmp     dword ptr [rbx+0B0h], 3
0x140075d6d  jnz     loc_140075F8A
0x140075d73  mov     rbp, [rbx+8]
0x140075d77  test    rbp, rbp
0x140075d7a  jz      loc_140075F8A
0x140075d80  cmp     qword ptr [rbp+0C8h], 0
0x140075d88  jz      loc_140075F8A
0x140075d8e  cmp     dword ptr [rax+8], 2
0x140075d92  jnz     loc_140075F8A
0x140075d98  xor     edi, edi
0x140075d9a  xor     r14d, r14d
0x140075d9d  test    r15b, r15b
0x140075da0  jnz     short loc_140075DB2
0x140075da2  lea     rcx, [rbp+18h]; Mutex
0x140075da6  call    cs:__imp_KeAcquireGuardedMutex
0x140075dad  nop     dword ptr [rax+rax+00h]
0x140075db2  mov     r12, [rbp+0C8h]
0x140075db9  lea     r8, File; File
0x140075dc0  mov     r9d, 1; Line
0x140075dc6  mov     [rsp+108h+RemlockSize], 20h ; ' '; RemlockSize
0x140075dce  mov     rdx, r12; Tag
0x140075dd1  lea     rcx, [r12+8]; RemoveLock
0x140075dd6  call    cs:__imp_IoAcquireRemoveLockEx
0x140075ddd  nop     dword ptr [rax+rax+00h]
0x140075de2  mov     r15d, eax
0x140075de5  test    eax, eax
0x140075de7  js      short loc_140075DED
0x140075de9  mov     rdi, [r12]
0x140075ded  shr     r15d, 1Fh
0x140075df1  xor     r15b, 1
0x140075df5  test    rdi, rdi
0x140075df8  jz      loc_140075F12
0x140075dfe  lea     rcx, [rbx+18h]; Mutex
0x140075e02  call    cs:__imp_KeAcquireGuardedMutex
0x140075e09  nop     dword ptr [rax+rax+00h]
0x140075e0e  mov     r14d, 4
0x140075e14  test    rsi, rsi
0x140075e17  jz      loc_140075EF9
0x140075e1d  cmp     r13d, r14d
0x140075e20  jb      loc_140075EF9
0x140075e26  xor     eax, eax
0x140075e28  lea     rdx, [rsp+108h+var_D8]
0x140075e2d  xor     r8d, r8d
0x140075e30  mov     [rsi], eax
0x140075e32  mov     rcx, rdi
0x140075e35  call    FvepAcquireDevFveLock
0x140075e3a  xor     ecx, ecx
0x140075e3c  mov     dword ptr [rsi], 0
0x140075e42  mov     eax, [rdi+344h]
0x140075e48  cmp     eax, 5
0x140075e4b  jz      short loc_140075EAB
0x140075e4d  cmp     eax, 6
0x140075e50  jz      short loc_140075EAB
0x140075e52  lea     edx, [rcx+7]
0x140075e55  cmp     eax, edx
0x140075e57  jz      short loc_140075EAB
0x140075e59  cmp     eax, 8
0x140075e5c  jz      short loc_140075EAB
0x140075e5e  lea     eax, [rcx+1]
0x140075e61  mov     [rsi], eax
0x140075e63  mov     ecx, eax
0x140075e65  cmp     [rdi+344h], eax
0x140075e6b  jz      short loc_140075EAB
0x140075e6d  lea     eax, [rdx-4]
0x140075e70  mov     [rsi], eax
0x140075e72  mov     ecx, eax
0x140075e74  cmp     dword ptr [rdi+344h], 2
0x140075e7b  jnz     short loc_140075EAB
0x140075e7d  test    dword ptr [rdi+354h], 200h
0x140075e87  jz      short loc_140075EAB
0x140075e89  mov     [rsi], edx
0x140075e8b  mov     ecx, edx
0x140075e8d  mov     eax, [rdi+328h]
0x140075e93  test    al, 40h
0x140075e95  jz      short loc_140075E9C
0x140075e97  lea     ecx, [rdx+8]
0x140075e9a  mov     [rsi], ecx
0x140075e9c  mov     eax, [rdi+354h]
0x140075ea2  test    al, 2
0x140075ea4  jnz     short loc_140075EAB
0x140075ea6  or      ecx, 10h
0x140075ea9  mov     [rsi], ecx
0x140075eab  mov     r10, cs:WPP_GLOBAL_Control
0x140075eb2  lea     rdi, WPP_GLOBAL_Control
0x140075eb9  cmp     r10, rdi
0x140075ebc  jz      short loc_140075EED
0x140075ebe  test    dword ptr [r10+2Ch], 400h
0x140075ec6  jz      short loc_140075EED
0x140075ec8  cmp     byte ptr [r10+29h], 5
0x140075ecd  jb      short loc_140075EED
0x140075ecf  mov     r9d, [r12+28h]
0x140075ed4  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140075edb  mov     [rsp+108h+RemlockSize], ecx
0x140075edf  mov     edx, 3Fh ; '?'
0x140075ee4  mov     rcx, [r10+18h]
0x140075ee8  call    WPP_SF_Dd
0x140075eed  lea     rcx, [rsp+108h+var_D8]
0x140075ef2  call    FvepReleaseDevFveLock
0x140075ef7  jmp     short loc_140075F00
0x140075ef9  lea     rdi, WPP_GLOBAL_Control
0x140075f00  lea     rcx, [rbx+18h]; Mutex
0x140075f04  call    cs:__imp_KeReleaseGuardedMutex
0x140075f0b  nop     dword ptr [rax+rax+00h]
0x140075f10  jmp     short loc_140075F19
0x140075f12  lea     rdi, WPP_GLOBAL_Control
0x140075f19  test    r15b, r15b
0x140075f1c  jz      short loc_140075F38
0x140075f1e  mov     r8d, 20h ; ' '; RemlockSize
0x140075f24  lea     rcx, [r12+8]; RemoveLock
0x140075f29  mov     rdx, r12; Tag
0x140075f2c  call    cs:__imp_IoReleaseRemoveLockEx
0x140075f33  nop     dword ptr [rax+rax+00h]
0x140075f38  cmp     [rsp+108h+arg_18], 0
0x140075f40  jnz     short loc_140075F52
0x140075f42  lea     rcx, [rbp+18h]; Mutex
0x140075f46  call    cs:__imp_KeReleaseGuardedMutex
0x140075f4d  nop     dword ptr [rax+rax+00h]
0x140075f52  mov     rcx, cs:WPP_GLOBAL_Control
0x140075f59  cmp     rcx, rdi
0x140075f5c  jz      short loc_140075F85
0x140075f5e  test    dword ptr [rcx+2Ch], 400h
0x140075f65  jz      short loc_140075F85
0x140075f67  cmp     byte ptr [rcx+29h], 5
0x140075f6b  jb      short loc_140075F85
0x140075f6d  mov     rcx, [rcx+18h]
0x140075f71  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140075f78  mov     edx, 40h ; '@'
0x140075f7d  mov     r9d, r14d
0x140075f80  call    WPP_SF_d
0x140075f85  mov     eax, r14d
0x140075f88  jmp     short loc_140075F8C
0x140075f8a  xor     eax, eax
0x140075f8c  add     rsp, 0C8h
0x140075f93  pop     r15
0x140075f95  pop     r14
0x140075f97  pop     r13
0x140075f99  pop     r12
0x140075f9b  pop     rdi
0x140075f9c  pop     rsi
0x140075f9d  pop     rbp
0x140075f9e  pop     rbx
0x140075f9f  retn
```
