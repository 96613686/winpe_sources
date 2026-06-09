# FveDcbSeiQueryInfo

- ea: `0x140074080`
- end: `0x140074354`
- name: `FveDcbSeiQueryInfo`
- size: `724`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000aef4`
- `0x140021d00`
- `0x140074080`
- `0x1400da590`
- `0x1400da8d4`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140074175`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140074175`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400742df`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400742df`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140074146`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1400741a1`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140074146`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1400741a1`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400742b8`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400742f9`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400742b8`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400742f9`

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
0x140074080  mov     [rsp+arg_18], r9b
0x140074085  push    rbx
0x140074086  push    rbp
0x140074087  push    rsi
0x140074088  push    rdi
0x140074089  push    r12
0x14007408b  push    r13
0x14007408d  push    r14
0x14007408f  push    r15
0x140074091  sub     rsp, 0C8h
0x140074098  mov     r12d, r8d
0x14007409b  mov     rsi, rdx
0x14007409e  mov     rbx, rcx
0x1400740a1  xor     edx, edx; Val
0x1400740a3  mov     r8d, 90h; Size
0x1400740a9  lea     rcx, [rsp+108h+var_D8]; void *
0x1400740ae  mov     r15b, r9b
0x1400740b1  call    memset
0x1400740b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400740bd  lea     rax, WPP_GLOBAL_Control
0x1400740c4  cmp     rcx, rax
0x1400740c7  jz      short loc_1400740ED
0x1400740c9  test    dword ptr [rcx+2Ch], 400h
0x1400740d0  jz      short loc_1400740ED
0x1400740d2  cmp     byte ptr [rcx+29h], 5
0x1400740d6  jb      short loc_1400740ED
0x1400740d8  mov     rcx, [rcx+18h]
0x1400740dc  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x1400740e3  mov     edx, 3Bh ; ';'
0x1400740e8  call    WPP_SF_
0x1400740ed  test    rbx, rbx
0x1400740f0  jz      loc_14007433D
0x1400740f6  mov     rax, [rbx+0C8h]
0x1400740fd  test    rax, rax
0x140074100  jz      loc_14007433D
0x140074106  cmp     dword ptr [rbx+0B0h], 3
0x14007410d  jnz     loc_14007433D
0x140074113  mov     rbp, [rbx+8]
0x140074117  test    rbp, rbp
0x14007411a  jz      loc_14007433D
0x140074120  cmp     qword ptr [rbp+0C8h], 0
0x140074128  jz      loc_14007433D
0x14007412e  cmp     dword ptr [rax+8], 0
0x140074132  jnz     loc_14007433D
0x140074138  xor     edi, edi
0x14007413a  xor     r14d, r14d
0x14007413d  test    r15b, r15b
0x140074140  jnz     short loc_140074152
0x140074142  lea     rcx, [rbp+18h]; Mutex
0x140074146  call    cs:__imp_KeAcquireGuardedMutex
0x14007414d  nop     dword ptr [rax+rax+00h]
0x140074152  mov     r13, [rbp+0C8h]
0x140074159  lea     r8, File; File
0x140074160  mov     r9d, 1; Line
0x140074166  mov     [rsp+108h+RemlockSize], 20h ; ' '; RemlockSize
0x14007416e  mov     rdx, r13; Tag
0x140074171  lea     rcx, [r13+8]; RemoveLock
0x140074175  call    cs:__imp_IoAcquireRemoveLockEx
0x14007417c  nop     dword ptr [rax+rax+00h]
0x140074181  mov     r15d, eax
0x140074184  test    eax, eax
0x140074186  js      short loc_14007418C
0x140074188  mov     rdi, [r13+0]
0x14007418c  shr     r15d, 1Fh
0x140074190  xor     r15b, 1
0x140074194  test    rdi, rdi
0x140074197  jz      loc_1400742C6
0x14007419d  lea     rcx, [rbx+18h]; Mutex
0x1400741a1  call    cs:__imp_KeAcquireGuardedMutex
0x1400741a8  nop     dword ptr [rax+rax+00h]
0x1400741ad  mov     r14d, 4
0x1400741b3  test    rsi, rsi
0x1400741b6  jz      loc_1400742AD
0x1400741bc  cmp     r12d, r14d
0x1400741bf  jb      loc_1400742AD
0x1400741c5  xor     eax, eax
0x1400741c7  lea     rdx, [rsp+108h+var_D8]
0x1400741cc  xor     r8d, r8d
0x1400741cf  mov     [rsi], eax
0x1400741d1  mov     rcx, rdi
0x1400741d4  call    FvepAcquireDevFveLock
0x1400741d9  xor     ecx, ecx
0x1400741db  mov     dword ptr [rsi], 0
0x1400741e1  mov     eax, [rdi+344h]
0x1400741e7  cmp     eax, 5
0x1400741ea  jz      short loc_140074260
0x1400741ec  cmp     eax, 6
0x1400741ef  jz      short loc_140074260
0x1400741f1  lea     r8d, [r14+3]
0x1400741f5  cmp     eax, r8d
0x1400741f8  jz      short loc_140074260
0x1400741fa  cmp     eax, 8
0x1400741fd  jz      short loc_140074260
0x1400741ff  lea     edx, [rcx+1]
0x140074202  mov     [rsi], edx
0x140074204  mov     ecx, edx
0x140074206  cmp     [rdi+344h], edx
0x14007420c  jz      short loc_140074260
0x14007420e  lea     r9d, [r14-1]
0x140074212  mov     [rsi], r9d
0x140074215  mov     ecx, [rdi+328h]
0x14007421b  mov     eax, ecx
0x14007421d  and     eax, 17Fh
0x140074222  jz      short loc_140074229
0x140074224  test    cl, 40h
0x140074227  jz      short loc_140074230
0x140074229  mov     ecx, r9d
0x14007422c  test    eax, eax
0x14007422e  jz      short loc_140074260
0x140074230  mov     [rsi], r8d
0x140074233  mov     ecx, r8d
0x140074236  mov     eax, [rdi+328h]
0x14007423c  test    al, 40h
0x14007423e  jz      short loc_140074247
0x140074240  mov     ecx, 0Fh
0x140074245  mov     [rsi], ecx
0x140074247  mov     eax, [rdi+328h]
0x14007424d  test    dl, al
0x14007424f  jz      short loc_140074260
0x140074251  mov     eax, [rdi+354h]
0x140074257  test    al, 2
0x140074259  jnz     short loc_140074260
0x14007425b  or      ecx, 10h
0x14007425e  mov     [rsi], ecx
0x140074260  mov     r10, cs:WPP_GLOBAL_Control
0x140074267  lea     rdi, WPP_GLOBAL_Control
0x14007426e  cmp     r10, rdi
0x140074271  jz      short loc_1400742A1
0x140074273  test    dword ptr [r10+2Ch], 400h
0x14007427b  jz      short loc_1400742A1
0x14007427d  cmp     byte ptr [r10+29h], 5
0x140074282  jb      short loc_1400742A1
0x140074284  mov     r9d, [r13+28h]
0x140074288  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14007428f  mov     [rsp+108h+RemlockSize], ecx
0x140074293  mov     edx, 3Ch ; '<'
0x140074298  mov     rcx, [r10+18h]
0x14007429c  call    WPP_SF_Dd
0x1400742a1  lea     rcx, [rsp+108h+var_D8]
0x1400742a6  call    FvepReleaseDevFveLock
0x1400742ab  jmp     short loc_1400742B4
0x1400742ad  lea     rdi, WPP_GLOBAL_Control
0x1400742b4  lea     rcx, [rbx+18h]; Mutex
0x1400742b8  call    cs:__imp_KeReleaseGuardedMutex
0x1400742bf  nop     dword ptr [rax+rax+00h]
0x1400742c4  jmp     short loc_1400742CD
0x1400742c6  lea     rdi, WPP_GLOBAL_Control
0x1400742cd  test    r15b, r15b
0x1400742d0  jz      short loc_1400742EB
0x1400742d2  mov     r8d, 20h ; ' '; RemlockSize
0x1400742d8  lea     rcx, [r13+8]; RemoveLock
0x1400742dc  mov     rdx, r13; Tag
0x1400742df  call    cs:__imp_IoReleaseRemoveLockEx
0x1400742e6  nop     dword ptr [rax+rax+00h]
0x1400742eb  cmp     [rsp+108h+arg_18], 0
0x1400742f3  jnz     short loc_140074305
0x1400742f5  lea     rcx, [rbp+18h]; Mutex
0x1400742f9  call    cs:__imp_KeReleaseGuardedMutex
0x140074300  nop     dword ptr [rax+rax+00h]
0x140074305  mov     rcx, cs:WPP_GLOBAL_Control
0x14007430c  cmp     rcx, rdi
0x14007430f  jz      short loc_140074338
0x140074311  test    dword ptr [rcx+2Ch], 400h
0x140074318  jz      short loc_140074338
0x14007431a  cmp     byte ptr [rcx+29h], 5
0x14007431e  jb      short loc_140074338
0x140074320  mov     rcx, [rcx+18h]
0x140074324  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14007432b  mov     edx, 3Dh ; '='
0x140074330  mov     r9d, r14d
0x140074333  call    WPP_SF_d
0x140074338  mov     eax, r14d
0x14007433b  jmp     short loc_14007433F
0x14007433d  xor     eax, eax
0x14007433f  add     rsp, 0C8h
0x140074346  pop     r15
0x140074348  pop     r14
0x14007434a  pop     r13
0x14007434c  pop     r12
0x14007434e  pop     rdi
0x14007434f  pop     rsi
0x140074350  pop     rbp
0x140074351  pop     rbx
0x140074352  retn
```
