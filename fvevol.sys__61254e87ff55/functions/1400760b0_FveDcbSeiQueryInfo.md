# FveDcbSeiQueryInfo

- ea: `0x1400760b0`
- end: `0x140076384`
- name: `FveDcbSeiQueryInfo`
- size: `724`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000afb4`
- `0x140023040`
- `0x1400760b0`
- `0x1400dce00`
- `0x1400dd144`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400761a5`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400761a5`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14007630f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14007630f`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140076176`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1400761d1`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140076176`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1400761d1`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400762e8`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140076329`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400762e8`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140076329`

## pseudocode

```c
__int64 __fastcall FveDcbSeiQueryInfo(__int64 a1, int *a2, unsigned int a3, char a4)
{
  __int64 v8; // rax
  __int64 v9; // rbp
  _DWORD *v10; // rdi
  unsigned int v11; // r14d
  _QWORD *v12; // r13
  NTSTATUS v13; // r15d
  bool v14; // r15
  int v15; // ecx
  int v16; // eax
  int v17; // ecx
  _BYTE v19[216]; // [rsp+30h] [rbp-D8h] BYREF

  memset(v19, 0, 0x90u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids);
  }
  if ( !a1 )
    return 0;
  v8 = *(_QWORD *)(a1 + 200);
  if ( !v8 )
    return 0;
  if ( *(_DWORD *)(a1 + 176) != 3 )
    return 0;
  v9 = *(_QWORD *)(a1 + 8);
  if ( !v9 || !*(_QWORD *)(v9 + 200) || *(_DWORD *)(v8 + 8) )
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
      FvepAcquireDevFveLock(v10, v19, 0);
      v15 = 0;
      *a2 = 0;
      v16 = v10[209];
      if ( v16 != 5 && v16 != 6 && v16 != 7 && v16 != 8 )
      {
        *a2 = 1;
        v15 = 1;
        if ( v10[209] != 1 )
        {
          if ( (*a2 = 3, v17 = v10[202], (v17 & 0x17F) != 0) && (v17 & 0x40) == 0 || (v15 = 3, (v10[202] & 0x17F) != 0) )
          {
            *a2 = 7;
            v15 = 7;
            if ( (v10[202] & 0x40) != 0 )
            {
              v15 = 15;
              *a2 = 15;
            }
            if ( (v10[202] & 1) != 0 && (v10[213] & 2) == 0 )
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
          60,
          WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
          *((unsigned int *)v12 + 10),
          v15);
      }
      FvepReleaseDevFveLock(v19);
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
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x1400760b0  mov     [rsp+arg_18], r9b
0x1400760b5  push    rbx
0x1400760b6  push    rbp
0x1400760b7  push    rsi
0x1400760b8  push    rdi
0x1400760b9  push    r12
0x1400760bb  push    r13
0x1400760bd  push    r14
0x1400760bf  push    r15
0x1400760c1  sub     rsp, 0C8h
0x1400760c8  mov     r12d, r8d
0x1400760cb  mov     rsi, rdx
0x1400760ce  mov     rbx, rcx
0x1400760d1  xor     edx, edx; Val
0x1400760d3  mov     r8d, 90h; Size
0x1400760d9  lea     rcx, [rsp+108h+var_D8]; void *
0x1400760de  mov     r15b, r9b
0x1400760e1  call    memset
0x1400760e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400760ed  lea     rax, WPP_GLOBAL_Control
0x1400760f4  cmp     rcx, rax
0x1400760f7  jz      short loc_14007611D
0x1400760f9  test    dword ptr [rcx+2Ch], 400h
0x140076100  jz      short loc_14007611D
0x140076102  cmp     byte ptr [rcx+29h], 5
0x140076106  jb      short loc_14007611D
0x140076108  mov     rcx, [rcx+18h]
0x14007610c  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140076113  mov     edx, 3Bh ; ';'
0x140076118  call    WPP_SF_
0x14007611d  test    rbx, rbx
0x140076120  jz      loc_14007636D
0x140076126  mov     rax, [rbx+0C8h]
0x14007612d  test    rax, rax
0x140076130  jz      loc_14007636D
0x140076136  cmp     dword ptr [rbx+0B0h], 3
0x14007613d  jnz     loc_14007636D
0x140076143  mov     rbp, [rbx+8]
0x140076147  test    rbp, rbp
0x14007614a  jz      loc_14007636D
0x140076150  cmp     qword ptr [rbp+0C8h], 0
0x140076158  jz      loc_14007636D
0x14007615e  cmp     dword ptr [rax+8], 0
0x140076162  jnz     loc_14007636D
0x140076168  xor     edi, edi
0x14007616a  xor     r14d, r14d
0x14007616d  test    r15b, r15b
0x140076170  jnz     short loc_140076182
0x140076172  lea     rcx, [rbp+18h]; Mutex
0x140076176  call    cs:__imp_KeAcquireGuardedMutex
0x14007617d  nop     dword ptr [rax+rax+00h]
0x140076182  mov     r13, [rbp+0C8h]
0x140076189  lea     r8, File; File
0x140076190  mov     r9d, 1; Line
0x140076196  mov     [rsp+108h+RemlockSize], 20h ; ' '; RemlockSize
0x14007619e  mov     rdx, r13; Tag
0x1400761a1  lea     rcx, [r13+8]; RemoveLock
0x1400761a5  call    cs:__imp_IoAcquireRemoveLockEx
0x1400761ac  nop     dword ptr [rax+rax+00h]
0x1400761b1  mov     r15d, eax
0x1400761b4  test    eax, eax
0x1400761b6  js      short loc_1400761BC
0x1400761b8  mov     rdi, [r13+0]
0x1400761bc  shr     r15d, 1Fh
0x1400761c0  xor     r15b, 1
0x1400761c4  test    rdi, rdi
0x1400761c7  jz      loc_1400762F6
0x1400761cd  lea     rcx, [rbx+18h]; Mutex
0x1400761d1  call    cs:__imp_KeAcquireGuardedMutex
0x1400761d8  nop     dword ptr [rax+rax+00h]
0x1400761dd  mov     r14d, 4
0x1400761e3  test    rsi, rsi
0x1400761e6  jz      loc_1400762DD
0x1400761ec  cmp     r12d, r14d
0x1400761ef  jb      loc_1400762DD
0x1400761f5  xor     eax, eax
0x1400761f7  lea     rdx, [rsp+108h+var_D8]
0x1400761fc  xor     r8d, r8d
0x1400761ff  mov     [rsi], eax
0x140076201  mov     rcx, rdi
0x140076204  call    FvepAcquireDevFveLock
0x140076209  xor     ecx, ecx
0x14007620b  mov     dword ptr [rsi], 0
0x140076211  mov     eax, [rdi+344h]
0x140076217  cmp     eax, 5
0x14007621a  jz      short loc_140076290
0x14007621c  cmp     eax, 6
0x14007621f  jz      short loc_140076290
0x140076221  lea     r8d, [r14+3]
0x140076225  cmp     eax, r8d
0x140076228  jz      short loc_140076290
0x14007622a  cmp     eax, 8
0x14007622d  jz      short loc_140076290
0x14007622f  lea     edx, [rcx+1]
0x140076232  mov     [rsi], edx
0x140076234  mov     ecx, edx
0x140076236  cmp     [rdi+344h], edx
0x14007623c  jz      short loc_140076290
0x14007623e  lea     r9d, [r14-1]
0x140076242  mov     [rsi], r9d
0x140076245  mov     ecx, [rdi+328h]
0x14007624b  mov     eax, ecx
0x14007624d  and     eax, 17Fh
0x140076252  jz      short loc_140076259
0x140076254  test    cl, 40h
0x140076257  jz      short loc_140076260
0x140076259  mov     ecx, r9d
0x14007625c  test    eax, eax
0x14007625e  jz      short loc_140076290
0x140076260  mov     [rsi], r8d
0x140076263  mov     ecx, r8d
0x140076266  mov     eax, [rdi+328h]
0x14007626c  test    al, 40h
0x14007626e  jz      short loc_140076277
0x140076270  mov     ecx, 0Fh
0x140076275  mov     [rsi], ecx
0x140076277  mov     eax, [rdi+328h]
0x14007627d  test    dl, al
0x14007627f  jz      short loc_140076290
0x140076281  mov     eax, [rdi+354h]
0x140076287  test    al, 2
0x140076289  jnz     short loc_140076290
0x14007628b  or      ecx, 10h
0x14007628e  mov     [rsi], ecx
0x140076290  mov     r10, cs:WPP_GLOBAL_Control
0x140076297  lea     rdi, WPP_GLOBAL_Control
0x14007629e  cmp     r10, rdi
0x1400762a1  jz      short loc_1400762D1
0x1400762a3  test    dword ptr [r10+2Ch], 400h
0x1400762ab  jz      short loc_1400762D1
0x1400762ad  cmp     byte ptr [r10+29h], 5
0x1400762b2  jb      short loc_1400762D1
0x1400762b4  mov     r9d, [r13+28h]
0x1400762b8  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x1400762bf  mov     [rsp+108h+RemlockSize], ecx
0x1400762c3  mov     edx, 3Ch ; '<'
0x1400762c8  mov     rcx, [r10+18h]
0x1400762cc  call    WPP_SF_Dd
0x1400762d1  lea     rcx, [rsp+108h+var_D8]
0x1400762d6  call    FvepReleaseDevFveLock
0x1400762db  jmp     short loc_1400762E4
0x1400762dd  lea     rdi, WPP_GLOBAL_Control
0x1400762e4  lea     rcx, [rbx+18h]; Mutex
0x1400762e8  call    cs:__imp_KeReleaseGuardedMutex
0x1400762ef  nop     dword ptr [rax+rax+00h]
0x1400762f4  jmp     short loc_1400762FD
0x1400762f6  lea     rdi, WPP_GLOBAL_Control
0x1400762fd  test    r15b, r15b
0x140076300  jz      short loc_14007631B
0x140076302  mov     r8d, 20h ; ' '; RemlockSize
0x140076308  lea     rcx, [r13+8]; RemoveLock
0x14007630c  mov     rdx, r13; Tag
0x14007630f  call    cs:__imp_IoReleaseRemoveLockEx
0x140076316  nop     dword ptr [rax+rax+00h]
0x14007631b  cmp     [rsp+108h+arg_18], 0
0x140076323  jnz     short loc_140076335
0x140076325  lea     rcx, [rbp+18h]; Mutex
0x140076329  call    cs:__imp_KeReleaseGuardedMutex
0x140076330  nop     dword ptr [rax+rax+00h]
0x140076335  mov     rcx, cs:WPP_GLOBAL_Control
0x14007633c  cmp     rcx, rdi
0x14007633f  jz      short loc_140076368
0x140076341  test    dword ptr [rcx+2Ch], 400h
0x140076348  jz      short loc_140076368
0x14007634a  cmp     byte ptr [rcx+29h], 5
0x14007634e  jb      short loc_140076368
0x140076350  mov     rcx, [rcx+18h]
0x140076354  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14007635b  mov     edx, 3Dh ; '='
0x140076360  mov     r9d, r14d
0x140076363  call    WPP_SF_d
0x140076368  mov     eax, r14d
0x14007636b  jmp     short loc_14007636F
0x14007636d  xor     eax, eax
0x14007636f  add     rsp, 0C8h
0x140076376  pop     r15
0x140076378  pop     r14
0x14007637a  pop     r13
0x14007637c  pop     r12
0x14007637e  pop     rdi
0x14007637f  pop     rsi
0x140076380  pop     rbp
0x140076381  pop     rbx
0x140076382  retn
```
