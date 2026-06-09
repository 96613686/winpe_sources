# FveDcbHeiQueryInfo

- ea: `0x140073cb0`
- end: `0x140073f71`
- name: `FveDcbHeiQueryInfo`
- size: `705`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000aef4`
- `0x140021d00`
- `0x140073cb0`
- `0x1400da590`
- `0x1400da8d4`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140073da6`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140073da6`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140073efc`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140073efc`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140073d76`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140073dd2`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140073d76`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140073dd2`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140073ed4`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140073f16`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140073ed4`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140073f16`

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
0x140073cb0  mov     [rsp+arg_18], r9b
0x140073cb5  push    rbx
0x140073cb6  push    rbp
0x140073cb7  push    rsi
0x140073cb8  push    rdi
0x140073cb9  push    r12
0x140073cbb  push    r13
0x140073cbd  push    r14
0x140073cbf  push    r15
0x140073cc1  sub     rsp, 0C8h
0x140073cc8  mov     r13d, r8d
0x140073ccb  mov     rsi, rdx
0x140073cce  mov     rbx, rcx
0x140073cd1  xor     edx, edx; Val
0x140073cd3  mov     r8d, 90h; Size
0x140073cd9  lea     rcx, [rsp+108h+var_D8]; void *
0x140073cde  mov     r15b, r9b
0x140073ce1  call    memset
0x140073ce6  mov     rcx, cs:WPP_GLOBAL_Control
0x140073ced  lea     rax, WPP_GLOBAL_Control
0x140073cf4  cmp     rcx, rax
0x140073cf7  jz      short loc_140073D1D
0x140073cf9  test    dword ptr [rcx+2Ch], 400h
0x140073d00  jz      short loc_140073D1D
0x140073d02  cmp     byte ptr [rcx+29h], 5
0x140073d06  jb      short loc_140073D1D
0x140073d08  mov     rcx, [rcx+18h]
0x140073d0c  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140073d13  mov     edx, 3Eh ; '>'
0x140073d18  call    WPP_SF_
0x140073d1d  test    rbx, rbx
0x140073d20  jz      loc_140073F5A
0x140073d26  mov     rax, [rbx+0C8h]
0x140073d2d  test    rax, rax
0x140073d30  jz      loc_140073F5A
0x140073d36  cmp     dword ptr [rbx+0B0h], 3
0x140073d3d  jnz     loc_140073F5A
0x140073d43  mov     rbp, [rbx+8]
0x140073d47  test    rbp, rbp
0x140073d4a  jz      loc_140073F5A
0x140073d50  cmp     qword ptr [rbp+0C8h], 0
0x140073d58  jz      loc_140073F5A
0x140073d5e  cmp     dword ptr [rax+8], 2
0x140073d62  jnz     loc_140073F5A
0x140073d68  xor     edi, edi
0x140073d6a  xor     r14d, r14d
0x140073d6d  test    r15b, r15b
0x140073d70  jnz     short loc_140073D82
0x140073d72  lea     rcx, [rbp+18h]; Mutex
0x140073d76  call    cs:__imp_KeAcquireGuardedMutex
0x140073d7d  nop     dword ptr [rax+rax+00h]
0x140073d82  mov     r12, [rbp+0C8h]
0x140073d89  lea     r8, File; File
0x140073d90  mov     r9d, 1; Line
0x140073d96  mov     [rsp+108h+RemlockSize], 20h ; ' '; RemlockSize
0x140073d9e  mov     rdx, r12; Tag
0x140073da1  lea     rcx, [r12+8]; RemoveLock
0x140073da6  call    cs:__imp_IoAcquireRemoveLockEx
0x140073dad  nop     dword ptr [rax+rax+00h]
0x140073db2  mov     r15d, eax
0x140073db5  test    eax, eax
0x140073db7  js      short loc_140073DBD
0x140073db9  mov     rdi, [r12]
0x140073dbd  shr     r15d, 1Fh
0x140073dc1  xor     r15b, 1
0x140073dc5  test    rdi, rdi
0x140073dc8  jz      loc_140073EE2
0x140073dce  lea     rcx, [rbx+18h]; Mutex
0x140073dd2  call    cs:__imp_KeAcquireGuardedMutex
0x140073dd9  nop     dword ptr [rax+rax+00h]
0x140073dde  mov     r14d, 4
0x140073de4  test    rsi, rsi
0x140073de7  jz      loc_140073EC9
0x140073ded  cmp     r13d, r14d
0x140073df0  jb      loc_140073EC9
0x140073df6  xor     eax, eax
0x140073df8  lea     rdx, [rsp+108h+var_D8]
0x140073dfd  xor     r8d, r8d
0x140073e00  mov     [rsi], eax
0x140073e02  mov     rcx, rdi
0x140073e05  call    FvepAcquireDevFveLock
0x140073e0a  xor     ecx, ecx
0x140073e0c  mov     dword ptr [rsi], 0
0x140073e12  mov     eax, [rdi+344h]
0x140073e18  cmp     eax, 5
0x140073e1b  jz      short loc_140073E7B
0x140073e1d  cmp     eax, 6
0x140073e20  jz      short loc_140073E7B
0x140073e22  lea     edx, [rcx+7]
0x140073e25  cmp     eax, edx
0x140073e27  jz      short loc_140073E7B
0x140073e29  cmp     eax, 8
0x140073e2c  jz      short loc_140073E7B
0x140073e2e  lea     eax, [rcx+1]
0x140073e31  mov     [rsi], eax
0x140073e33  mov     ecx, eax
0x140073e35  cmp     [rdi+344h], eax
0x140073e3b  jz      short loc_140073E7B
0x140073e3d  lea     eax, [rdx-4]
0x140073e40  mov     [rsi], eax
0x140073e42  mov     ecx, eax
0x140073e44  cmp     dword ptr [rdi+344h], 2
0x140073e4b  jnz     short loc_140073E7B
0x140073e4d  test    dword ptr [rdi+354h], 200h
0x140073e57  jz      short loc_140073E7B
0x140073e59  mov     [rsi], edx
0x140073e5b  mov     ecx, edx
0x140073e5d  mov     eax, [rdi+328h]
0x140073e63  test    al, 40h
0x140073e65  jz      short loc_140073E6C
0x140073e67  lea     ecx, [rdx+8]
0x140073e6a  mov     [rsi], ecx
0x140073e6c  mov     eax, [rdi+354h]
0x140073e72  test    al, 2
0x140073e74  jnz     short loc_140073E7B
0x140073e76  or      ecx, 10h
0x140073e79  mov     [rsi], ecx
0x140073e7b  mov     r10, cs:WPP_GLOBAL_Control
0x140073e82  lea     rdi, WPP_GLOBAL_Control
0x140073e89  cmp     r10, rdi
0x140073e8c  jz      short loc_140073EBD
0x140073e8e  test    dword ptr [r10+2Ch], 400h
0x140073e96  jz      short loc_140073EBD
0x140073e98  cmp     byte ptr [r10+29h], 5
0x140073e9d  jb      short loc_140073EBD
0x140073e9f  mov     r9d, [r12+28h]
0x140073ea4  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140073eab  mov     [rsp+108h+RemlockSize], ecx
0x140073eaf  mov     edx, 3Fh ; '?'
0x140073eb4  mov     rcx, [r10+18h]
0x140073eb8  call    WPP_SF_Dd
0x140073ebd  lea     rcx, [rsp+108h+var_D8]
0x140073ec2  call    FvepReleaseDevFveLock
0x140073ec7  jmp     short loc_140073ED0
0x140073ec9  lea     rdi, WPP_GLOBAL_Control
0x140073ed0  lea     rcx, [rbx+18h]; Mutex
0x140073ed4  call    cs:__imp_KeReleaseGuardedMutex
0x140073edb  nop     dword ptr [rax+rax+00h]
0x140073ee0  jmp     short loc_140073EE9
0x140073ee2  lea     rdi, WPP_GLOBAL_Control
0x140073ee9  test    r15b, r15b
0x140073eec  jz      short loc_140073F08
0x140073eee  mov     r8d, 20h ; ' '; RemlockSize
0x140073ef4  lea     rcx, [r12+8]; RemoveLock
0x140073ef9  mov     rdx, r12; Tag
0x140073efc  call    cs:__imp_IoReleaseRemoveLockEx
0x140073f03  nop     dword ptr [rax+rax+00h]
0x140073f08  cmp     [rsp+108h+arg_18], 0
0x140073f10  jnz     short loc_140073F22
0x140073f12  lea     rcx, [rbp+18h]; Mutex
0x140073f16  call    cs:__imp_KeReleaseGuardedMutex
0x140073f1d  nop     dword ptr [rax+rax+00h]
0x140073f22  mov     rcx, cs:WPP_GLOBAL_Control
0x140073f29  cmp     rcx, rdi
0x140073f2c  jz      short loc_140073F55
0x140073f2e  test    dword ptr [rcx+2Ch], 400h
0x140073f35  jz      short loc_140073F55
0x140073f37  cmp     byte ptr [rcx+29h], 5
0x140073f3b  jb      short loc_140073F55
0x140073f3d  mov     rcx, [rcx+18h]
0x140073f41  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140073f48  mov     edx, 40h ; '@'
0x140073f4d  mov     r9d, r14d
0x140073f50  call    WPP_SF_d
0x140073f55  mov     eax, r14d
0x140073f58  jmp     short loc_140073F5C
0x140073f5a  xor     eax, eax
0x140073f5c  add     rsp, 0C8h
0x140073f63  pop     r15
0x140073f65  pop     r14
0x140073f67  pop     r13
0x140073f69  pop     r12
0x140073f6b  pop     rdi
0x140073f6c  pop     rsi
0x140073f6d  pop     rbp
0x140073f6e  pop     rbx
0x140073f6f  retn
```
