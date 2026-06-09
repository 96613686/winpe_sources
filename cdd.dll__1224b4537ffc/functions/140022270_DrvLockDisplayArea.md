# DrvLockDisplayArea

- ea: `0x140022270`
- end: `0x140022498`
- name: `DrvLockDisplayArea`
- size: `552`
- prototype: `FN_DrvLockDisplayArea`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140008d28`
- `0x140022270`
- `0x1400224a0`
- `0x1400371f0`
- `0x140037640`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140022379`
- `ntoskrnl!KeWaitForSingleObject` at `0x140022379`
- `ntoskrnl!KeReleaseMutex` at `0x140022460`
- `ntoskrnl!KeReleaseMutex` at `0x140022460`
- `WIN32K!EngAcquireSemaphoreNoWait` at `0x1400223ad`
- `WIN32K!EngAcquireSemaphoreNoWait` at `0x1400223ad`
- `WIN32K!EngIsSemaphoreOwnedByCurrentThread` at `0x14002240d`
- `WIN32K!EngIsSemaphoreOwnedByCurrentThread` at `0x14002240d`
- `WIN32K!EngReleaseSemaphore` at `0x1400223f9`
- `WIN32K!EngReleaseSemaphore` at `0x1400223f9`

## string_xrefs

- `0x14002241d`: `DrvLockDisplayArea tile lock is still locked by current thread!\n`

## pseudocode

```c
void __stdcall DrvLockDisplayArea(DHPDEV dhpdev, RECTL *prcl)
{
  LONG v2; // eax
  LONG top; // r10d
  LONG bottom; // r8d
  int v6; // ecx
  LONG left; // r9d
  LONG right; // edx
  __int64 v9; // rax
  LONG v10; // esi
  LONG v11; // ebx
  unsigned int v12; // eax
  unsigned int v13; // r11d
  unsigned int v14; // ecx
  unsigned int v15; // r8d
  int v16; // ebp
  int v17; // r14d
  int v18; // r13d
  int v19; // r12d
  int v20; // esi
  int i; // ebx
  __int64 v22; // rbp
  int j; // esi
  __int64 v24; // rbx
  __int64 v25; // r14
  int v26; // [rsp+30h] [rbp-B8h]
  int v27; // [rsp+34h] [rbp-B4h]
  _BYTE v28[96]; // [rsp+40h] [rbp-A8h] BYREF

  top = prcl->top;
  bottom = prcl->bottom;
  v6 = bottom;
  left = prcl->left;
  right = prcl->right;
  v2 = right;
  if ( left <= right )
    right = left;
  if ( left <= v2 )
    left = v2;
  v9 = *((_QWORD *)dhpdev + 349);
  if ( top <= bottom )
  {
    v6 = top;
    top = bottom;
  }
  v10 = *(_DWORD *)(v9 + 32);
  v11 = *(_DWORD *)(v9 + 36);
  v12 = 0;
  if ( right >= 0 )
    v12 = right;
  v13 = 0;
  if ( v6 >= 0 )
    v13 = v6;
  if ( v10 >= left )
    v10 = left;
  if ( v11 >= top )
    v11 = top;
  if ( v10 >= (int)v12 )
  {
    if ( v11 < (int)v13 )
      v13 = v11;
    if ( v12 != v10 && v13 != v11 )
    {
      v14 = *((_DWORD *)dhpdev + 894);
      v15 = *((_DWORD *)dhpdev + 895);
      v16 = v12 / v14;
      v26 = v12 / v14;
      v17 = v13 / v15;
      v27 = v13 / v15;
      v18 = v10 / v14 + 1;
      v19 = v11 / v15 + 1;
      while ( 1 )
      {
        memset(v28, 0, 0x51u);
        KeWaitForSingleObject((PVOID)(*((_QWORD *)dhpdev + 449) + 32LL), UserRequest, 0, 0, 0);
        v20 = v17;
LABEL_22:
        if ( v20 >= v19 )
          break;
        for ( i = v16; ; ++i )
        {
          if ( i >= v18 )
          {
            v16 = v26;
            ++v20;
            goto LABEL_22;
          }
          v22 = i + 9LL * v20;
          if ( !EngAcquireSemaphoreNoWait(*((HSEMAPHORE *)dhpdev + v22 + 366)) )
            break;
          v28[v22] = 1;
        }
        for ( j = 8; j >= 0; --j )
        {
          v24 = 8;
          v25 = 9LL * (unsigned int)j;
          do
          {
            if ( v28[v25 + v24] == 1 )
            {
              EngReleaseSemaphore(*((HSEMAPHORE *)dhpdev + v25 + v24 + 366));
              if ( EngIsSemaphoreOwnedByCurrentThread(*((HSEMAPHORE *)dhpdev + v25 + v24 + 366)) )
              {
                DbgLog("DrvLockDisplayArea tile lock is still locked by current thread!\n");
                __debugbreak();
              }
              v28[v25 + v24] = 0;
            }
            --v24;
          }
          while ( v24 != -1 );
        }
        ShadowUnLockWait((struct CDDPDEV *)dhpdev);
        v16 = v26;
        v17 = v27;
      }
      KeReleaseMutex((PRKMUTEX)(*((_QWORD *)dhpdev + 449) + 32LL), 0);
    }
  }
}

```

## disassembly

```asm
0x140022270  mov     [rsp+arg_10], rbx
0x140022275  push    rbp
0x140022276  push    rsi
0x140022277  push    rdi
0x140022278  push    r12
0x14002227a  push    r13
0x14002227c  push    r14
0x14002227e  push    r15
0x140022280  sub     rsp, 0B0h
0x140022287  mov     rax, cs:__security_cookie
0x14002228e  xor     rax, rsp
0x140022291  mov     [rsp+0E8h+var_48], rax
0x140022299  mov     eax, [rdx+8]
0x14002229c  mov     rdi, rcx
0x14002229f  mov     r10d, [rdx+4]
0x1400222a3  mov     r8d, [rdx+0Ch]
0x1400222a7  mov     ecx, r8d
0x1400222aa  mov     r9d, [rdx]
0x1400222ad  cmp     r9d, eax
0x1400222b0  mov     edx, eax
0x1400222b2  cmovle  edx, r9d
0x1400222b6  cmovle  r9d, eax
0x1400222ba  mov     rax, [rdi+0AE8h]
0x1400222c1  cmp     r10d, r8d
0x1400222c4  cmovle  ecx, r10d
0x1400222c8  cmovle  r10d, r8d
0x1400222cc  mov     esi, [rax+20h]
0x1400222cf  mov     ebx, [rax+24h]
0x1400222d2  xor     eax, eax
0x1400222d4  test    edx, edx
0x1400222d6  cmovns  eax, edx
0x1400222d9  xor     r11d, r11d
0x1400222dc  test    ecx, ecx
0x1400222de  cmovns  r11d, ecx
0x1400222e2  cmp     esi, r9d
0x1400222e5  cmovge  esi, r9d
0x1400222e9  cmp     ebx, r10d
0x1400222ec  cmovge  ebx, r10d
0x1400222f0  cmp     esi, eax
0x1400222f2  jl      loc_14002246C
0x1400222f8  cmp     ebx, r11d
0x1400222fb  cmovl   r11d, ebx
0x1400222ff  cmp     eax, esi
0x140022301  jz      loc_14002246C
0x140022307  cmp     r11d, ebx
0x14002230a  jz      loc_14002246C
0x140022310  mov     ecx, [rdi+0DF8h]
0x140022316  xor     edx, edx
0x140022318  mov     r8d, [rdi+0DFCh]
0x14002231f  div     ecx
0x140022321  xor     edx, edx
0x140022323  mov     ebp, eax
0x140022325  mov     [rsp+0E8h+var_B8], eax
0x140022329  mov     eax, r11d
0x14002232c  div     r8d
0x14002232f  xor     edx, edx
0x140022331  mov     r14d, eax
0x140022334  mov     [rsp+0E8h+var_B4], eax
0x140022338  mov     eax, esi
0x14002233a  div     ecx
0x14002233c  xor     edx, edx
0x14002233e  lea     r13d, [rax+1]
0x140022342  mov     eax, ebx
0x140022344  div     r8d
0x140022347  lea     r12d, [rax+1]
0x14002234b  xor     edx, edx; Val
0x14002234d  lea     rcx, [rsp+0E8h+var_A8]; void *
0x140022352  lea     r8d, [rdx+51h]; Size
0x140022356  call    memset
0x14002235b  mov     rcx, [rdi+0E08h]
0x140022362  xor     r9d, r9d; Alertable
0x140022365  add     rcx, 20h ; ' '; Object
0x140022369  mov     [rsp+0E8h+Timeout], 0; Timeout
0x140022372  xor     r8d, r8d; WaitMode
0x140022375  lea     edx, [r9+6]; WaitReason
0x140022379  call    cs:__imp_KeWaitForSingleObject
0x140022380  nop     dword ptr [rax+rax+00h]
0x140022385  mov     esi, r14d
0x140022388  cmp     esi, r12d
0x14002238b  jge     loc_140022453
0x140022391  mov     ebx, ebp
0x140022393  cmp     ebx, r13d
0x140022396  jge     short loc_1400223C6
0x140022398  movsxd  rax, esi
0x14002239b  lea     rbp, [rax+rax*8]
0x14002239f  movsxd  rax, ebx
0x1400223a2  add     rbp, rax
0x1400223a5  mov     rcx, [rdi+rbp*8+0B70h]; hsem
0x1400223ad  call    cs:__imp_EngAcquireSemaphoreNoWait
0x1400223b4  nop     dword ptr [rax+rax+00h]
0x1400223b9  cmp     eax, 1
0x1400223bc  jnz     short loc_1400223CE
0x1400223be  mov     [rsp+rbp+0E8h+var_A8], al
0x1400223c2  inc     ebx
0x1400223c4  jmp     short loc_140022393
0x1400223c6  mov     ebp, [rsp+0E8h+var_B8]
0x1400223ca  inc     esi
0x1400223cc  jmp     short loc_140022388
0x1400223ce  mov     esi, 8
0x1400223d3  mov     eax, esi
0x1400223d5  lea     r15, [rsp+0E8h+var_A8]
0x1400223da  mov     ebx, 8
0x1400223df  lea     r14, [rax+rax*8]
0x1400223e3  add     r15, r14
0x1400223e6  cmp     byte ptr [r15+rbx], 1
0x1400223eb  jnz     short loc_14002242F
0x1400223ed  lea     rbp, [r14+rbx]
0x1400223f1  mov     rcx, [rdi+rbp*8+0B70h]; hsem
0x1400223f9  call    cs:__imp_EngReleaseSemaphore
0x140022400  nop     dword ptr [rax+rax+00h]
0x140022405  mov     rcx, [rdi+rbp*8+0B70h]; hsem
0x14002240d  call    cs:__imp_EngIsSemaphoreOwnedByCurrentThread
0x140022414  nop     dword ptr [rax+rax+00h]
0x140022419  test    eax, eax
0x14002241b  jz      short loc_14002242A
0x14002241d  lea     rcx, aDrvlockdisplay; "DrvLockDisplayArea tile lock is still l"...
0x140022424  call    ?DbgLog@@YAXPEBDZZ; DbgLog(char const *,...)
0x140022429  int     3; Trap to Debugger
0x14002242a  mov     [rsp+rbp+0E8h+var_A8], 0
0x14002242f  dec     rbx
0x140022432  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140022436  jnz     short loc_1400223E6
0x140022438  sub     esi, 1
0x14002243b  jns     short loc_1400223D3
0x14002243d  mov     rcx, rdi; struct CDDPDEV *
0x140022440  call    ?ShadowUnLockWait@@YAXPEAUCDDPDEV@@@Z; ShadowUnLockWait(CDDPDEV *)
0x140022445  mov     ebp, [rsp+0E8h+var_B8]
0x140022449  mov     r14d, [rsp+0E8h+var_B4]
0x14002244e  jmp     loc_14002234B
0x140022453  mov     rcx, [rdi+0E08h]
0x14002245a  xor     edx, edx; Wait
0x14002245c  add     rcx, 20h ; ' '; Mutex
0x140022460  call    cs:__imp_KeReleaseMutex
0x140022467  nop     dword ptr [rax+rax+00h]
0x14002246c  mov     rcx, [rsp+0E8h+var_48]
0x140022474  xor     rcx, rsp; StackCookie
0x140022477  call    __security_check_cookie
0x14002247c  mov     rbx, [rsp+0E8h+arg_10]
0x140022484  add     rsp, 0B0h
0x14002248b  pop     r15
0x14002248d  pop     r14
0x14002248f  pop     r13
0x140022491  pop     r12
0x140022493  pop     rdi
0x140022494  pop     rsi
0x140022495  pop     rbp
0x140022496  retn
```
