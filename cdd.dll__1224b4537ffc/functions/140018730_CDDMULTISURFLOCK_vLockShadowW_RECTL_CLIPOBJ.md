# CDDMULTISURFLOCK::vLockShadowW(_RECTL *,_CLIPOBJ *)

- ea: `0x140018730`
- end: `0x140018a6f`
- name: `?vLockShadowW@CDDMULTISURFLOCK@@QEAAXPEAU_RECTL@@PEAU_CLIPOBJ@@@Z`
- size: `831`
- prototype: `void __fastcall(CDDMULTISURFLOCK *__hidden this, struct _RECTL *, struct _CLIPOBJ *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400087ac`

## callees

- `0x140018730`
- `0x1400224a0`
- `0x140034254`
- `0x140037640`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400188ae`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400188ae`
- `ntoskrnl!KeReleaseMutex` at `0x1400188d9`
- `ntoskrnl!KeReleaseMutex` at `0x1400188d9`
- `WIN32K!EngIsSemaphoreSharedByCurrentThread` at `0x140018955`
- `WIN32K!EngIsSemaphoreSharedByCurrentThread` at `0x140018955`
- `WIN32K!EngAcquireSemaphoreNoWait` at `0x14001897d`
- `WIN32K!EngAcquireSemaphoreNoWait` at `0x14001897d`
- `WIN32K!EngIsSemaphoreOwnedByCurrentThread` at `0x140018931`
- `WIN32K!EngIsSemaphoreOwnedByCurrentThread` at `0x140018931`

## string_xrefs

- `0x140018a32`: `CDDMULTISURFLOCK::CDDMULTISURFLOCK::vLockShadowWTrying to recursively accquire a lock exclusivethat is already owned shared\n`

## pseudocode

```c
void __fastcall CDDMULTISURFLOCK::vLockShadowW(CDDMULTISURFLOCK *this, struct _RECTL *a2, struct _CLIPOBJ *a3)
{
  LONG left; // r14d
  LONG top; // r15d
  LONG right; // ebx
  LONG bottom; // ebp
  __int64 v8; // rcx
  __int64 *v9; // rdi
  LONG v10; // edx
  LONG v11; // r10d
  __int64 v12; // rax
  LONG v13; // r9d
  LONG v14; // r11d
  LONG v15; // eax
  LONG v16; // r8d
  __int64 v17; // rcx
  __int64 v18; // r10
  int v19; // eax
  __int64 v20; // r10
  int v21; // eax
  __int64 v22; // r10
  int v23; // ebp
  int v24; // r14d
  int v25; // eax
  int v26; // r12d
  int v27; // r13d
  __int64 v28; // rcx
  __int64 v29; // rcx
  int i; // ebx
  __int64 v31; // rcx
  __int64 v32; // rbp
  __int64 v33; // rcx
  __int64 v34; // rcx
  int v35; // [rsp+70h] [rbp+8h]
  int v36; // [rsp+80h] [rbp+18h]

  if ( a3 && a3->iDComplexity )
  {
    left = a3->rclBounds.left;
    top = a3->rclBounds.top;
    if ( left <= a2->left )
      left = a2->left;
    right = a3->rclBounds.right;
    bottom = a3->rclBounds.bottom;
    if ( top <= a2->top )
      top = a2->top;
    if ( right >= a2->right )
      right = a2->right;
    if ( bottom >= a2->bottom )
      bottom = a2->bottom;
  }
  else
  {
    left = a2->left;
    top = a2->top;
    right = a2->right;
    bottom = a2->bottom;
  }
  v8 = *((_QWORD *)this + 4);
  v9 = (__int64 *)((char *)this + 40);
  if ( !v8 )
  {
    if ( !*v9 )
    {
      DbgLog("CDDMULTISURFLOCK::VlockShadowW ppdev1 == NULL && ppdev2 == NULL\n");
      __debugbreak();
    }
    v8 = 0;
  }
  v10 = left;
  v11 = top;
  v12 = v8;
  if ( left <= right )
  {
    v10 = right;
    right = left;
  }
  if ( top <= bottom )
  {
    v11 = bottom;
    bottom = top;
  }
  if ( !v8 )
    v12 = *v9;
  v13 = *(_DWORD *)(*(_QWORD *)(v12 + 2792) + 36LL);
  if ( !v8 )
    v8 = *v9;
  v14 = *(_DWORD *)(*(_QWORD *)(v8 + 2792) + 32LL);
  v15 = 0;
  if ( right >= 0 )
    v15 = right;
  v16 = 0;
  if ( bottom >= 0 )
    v16 = bottom;
  if ( v14 >= v10 )
    v14 = v10;
  if ( v13 >= v11 )
    v13 = v11;
  if ( v14 >= v15 )
  {
    if ( v13 < v16 )
      v16 = v13;
    if ( v15 != v14 && v16 != v13 )
    {
      v17 = *((_QWORD *)this + 4);
      v18 = v17;
      if ( !v17 )
        v18 = *v9;
      v19 = (unsigned int)v15 / *(_DWORD *)(v18 + 3576);
      v20 = *((_QWORD *)this + 4);
      v35 = v19;
      if ( !v17 )
        v20 = *v9;
      v21 = (unsigned int)v14 / *(_DWORD *)(v20 + 3576);
      v22 = *((_QWORD *)this + 4);
      v23 = v21;
      if ( !v17 )
        v22 = *v9;
      v36 = (unsigned int)v16 / *(_DWORD *)(v22 + 3580);
      v24 = v36;
      if ( !v17 )
        v17 = *v9;
      v25 = (unsigned int)v13 / *(_DWORD *)(v17 + 3580);
      *((_BYTE *)this + 49) = 1;
      v26 = v25 + 1;
      memset((char *)this + 131, 0, 0x51u);
      v27 = v23 + 1;
      while ( 1 )
      {
        v28 = *((_QWORD *)this + 4);
        if ( !v28 )
          v28 = *v9;
        KeWaitForSingleObject((PVOID)(*(_QWORD *)(v28 + 3592) + 32LL), UserRequest, 0, 0, 0);
LABEL_37:
        if ( v24 >= v26 )
          break;
        for ( i = v35; ; ++i )
        {
          if ( i >= v27 )
          {
            ++v24;
            goto LABEL_37;
          }
          v31 = *((_QWORD *)this + 4);
          if ( !v31 )
            v31 = *v9;
          v32 = i + 9LL * v24;
          if ( !EngIsSemaphoreOwnedByCurrentThread(*(HSEMAPHORE *)(v31 + 8 * v32 + 2928)) )
          {
            v33 = *((_QWORD *)this + 4);
            if ( !v33 )
              v33 = *v9;
            if ( EngIsSemaphoreSharedByCurrentThread(*(HSEMAPHORE *)(v33 + 8 * v32 + 2928)) )
            {
              DbgLog(
                "CDDMULTISURFLOCK::CDDMULTISURFLOCK::vLockShadowWTrying to recursively accquire a lock exclusivethat is a"
                "lready owned shared\n");
              __debugbreak();
            }
          }
          v34 = *((_QWORD *)this + 4);
          if ( !v34 )
            v34 = *v9;
          if ( !EngAcquireSemaphoreNoWait(*(HSEMAPHORE *)(v34 + 8 * v32 + 2928)) )
            break;
          *((_BYTE *)this + v32 + 131) = 1;
        }
        CDDMULTISURFLOCK::vUnLockShadowWAndWait(this);
        memset((char *)this + 131, 0, 0x51u);
        v24 = v36;
      }
      v29 = *((_QWORD *)this + 4);
      if ( !v29 )
        v29 = *v9;
      KeReleaseMutex((PRKMUTEX)(*(_QWORD *)(v29 + 3592) + 32LL), 0);
    }
  }
}

```

## disassembly

```asm
0x140018730  mov     [rsp+arg_8], rbx
0x140018735  push    rbp
0x140018736  push    rsi
0x140018737  push    rdi
0x140018738  push    r12
0x14001873a  push    r13
0x14001873c  push    r14
0x14001873e  push    r15
0x140018740  sub     rsp, 30h
0x140018744  mov     r10, r8
0x140018747  mov     rsi, rcx
0x14001874a  test    r8, r8
0x14001874d  jnz     loc_1400189A8
0x140018753  mov     r14d, [rdx]
0x140018756  mov     r15d, [rdx+4]
0x14001875a  mov     ebx, [rdx+8]
0x14001875d  mov     ebp, [rdx+0Ch]
0x140018760  mov     rcx, [rsi+20h]
0x140018764  lea     rdi, [rsi+28h]
0x140018768  test    rcx, rcx
0x14001876b  jz      loc_1400189EF
0x140018771  cmp     r14d, ebx
0x140018774  mov     edx, r14d
0x140018777  mov     r10d, r15d
0x14001877a  mov     rax, rcx
0x14001877d  cmovle  edx, ebx
0x140018780  cmovle  ebx, r14d
0x140018784  cmp     r15d, ebp
0x140018787  cmovle  r10d, ebp
0x14001878b  cmovle  ebp, r15d
0x14001878f  test    rcx, rcx
0x140018792  jnz     short loc_140018797
0x140018794  mov     rax, [rdi]
0x140018797  mov     rax, [rax+0AE8h]
0x14001879e  mov     r9d, [rax+24h]
0x1400187a2  test    rcx, rcx
0x1400187a5  jz      loc_140018A12
0x1400187ab  mov     rax, [rcx+0AE8h]
0x1400187b2  mov     r11d, [rax+20h]
0x1400187b6  xor     eax, eax
0x1400187b8  test    ebx, ebx
0x1400187ba  cmovns  eax, ebx
0x1400187bd  xor     r8d, r8d
0x1400187c0  test    ebp, ebp
0x1400187c2  cmovns  r8d, ebp
0x1400187c6  cmp     r11d, edx
0x1400187c9  cmovge  r11d, edx
0x1400187cd  cmp     r9d, r10d
0x1400187d0  cmovge  r9d, r10d
0x1400187d4  cmp     r11d, eax
0x1400187d7  jl      loc_1400188E5
0x1400187dd  cmp     r9d, r8d
0x1400187e0  cmovl   r8d, r9d
0x1400187e4  cmp     eax, r11d
0x1400187e7  jz      loc_1400188E5
0x1400187ed  cmp     r8d, r9d
0x1400187f0  jz      loc_1400188E5
0x1400187f6  mov     rcx, [rsi+20h]
0x1400187fa  mov     r10, rcx
0x1400187fd  test    rcx, rcx
0x140018800  jnz     short loc_140018805
0x140018802  mov     r10, [rdi]
0x140018805  xor     edx, edx
0x140018807  div     dword ptr [r10+0DF8h]
0x14001880e  mov     r10, rcx
0x140018811  mov     [rsp+68h+arg_0], eax
0x140018815  test    rcx, rcx
0x140018818  jz      loc_140018A1A
0x14001881e  xor     edx, edx
0x140018820  mov     eax, r11d
0x140018823  div     dword ptr [r10+0DF8h]
0x14001882a  mov     r10, rcx
0x14001882d  mov     ebp, eax
0x14001882f  test    rcx, rcx
0x140018832  jz      loc_1400188FB
0x140018838  xor     edx, edx
0x14001883a  mov     eax, r8d
0x14001883d  div     dword ptr [r10+0DFCh]
0x140018844  mov     [rsp+68h+arg_10], eax
0x14001884b  mov     r14d, eax
0x14001884e  test    rcx, rcx
0x140018851  jz      loc_140018A22
0x140018857  xor     edx, edx
0x140018859  lea     r15, [rsi+83h]
0x140018860  mov     eax, r9d
0x140018863  div     dword ptr [rcx+0DFCh]
0x140018869  xor     edx, edx; Val
0x14001886b  mov     byte ptr [rsi+31h], 1
0x14001886f  mov     rcx, r15; void *
0x140018872  lea     r8d, [rdx+51h]; Size
0x140018876  lea     r12d, [rax+1]
0x14001887a  call    memset
0x14001887f  lea     r13d, [rbp+1]
0x140018883  mov     rcx, [rsi+20h]
0x140018887  test    rcx, rcx
0x14001888a  jz      loc_140018A2A
0x140018890  mov     rcx, [rcx+0E08h]
0x140018897  xor     r9d, r9d; Alertable
0x14001889a  add     rcx, 20h ; ' '; Object
0x14001889e  mov     [rsp+68h+Timeout], 0; Timeout
0x1400188a7  xor     r8d, r8d; WaitMode
0x1400188aa  lea     edx, [r9+6]; WaitReason
0x1400188ae  call    cs:__imp_KeWaitForSingleObject
0x1400188b5  nop     dword ptr [rax+rax+00h]
0x1400188ba  cmp     r14d, r12d
0x1400188bd  jl      short loc_140018903
0x1400188bf  mov     rcx, [rsi+20h]
0x1400188c3  test    rcx, rcx
0x1400188c6  jz      loc_140018A67
0x1400188cc  mov     rcx, [rcx+0E08h]
0x1400188d3  xor     edx, edx; Wait
0x1400188d5  add     rcx, 20h ; ' '; Mutex
0x1400188d9  call    cs:__imp_KeReleaseMutex
0x1400188e0  nop     dword ptr [rax+rax+00h]
0x1400188e5  mov     rbx, [rsp+68h+arg_8]
0x1400188ea  add     rsp, 30h
0x1400188ee  pop     r15
0x1400188f0  pop     r14
0x1400188f2  pop     r13
0x1400188f4  pop     r12
0x1400188f6  pop     rdi
0x1400188f7  pop     rsi
0x1400188f8  pop     rbp
0x1400188f9  retn
0x1400188fb  mov     r10, [rdi]
0x1400188fe  jmp     loc_140018838
0x140018903  mov     ebx, [rsp+68h+arg_0]
0x140018907  cmp     ebx, r13d
0x14001890a  jge     loc_1400189A0
0x140018910  mov     rcx, [rsi+20h]
0x140018914  test    rcx, rcx
0x140018917  jnz     short loc_14001891C
0x140018919  mov     rcx, [rdi]
0x14001891c  movsxd  rax, r14d
0x14001891f  lea     rbp, [rax+rax*8]
0x140018923  movsxd  rax, ebx
0x140018926  add     rbp, rax
0x140018929  mov     rcx, [rcx+rbp*8+0B70h]; hsem
0x140018931  call    cs:__imp_EngIsSemaphoreOwnedByCurrentThread
0x140018938  nop     dword ptr [rax+rax+00h]
0x14001893d  test    eax, eax
0x14001893f  jnz     short loc_140018969
0x140018941  mov     rcx, [rsi+20h]
0x140018945  test    rcx, rcx
0x140018948  jnz     short loc_14001894D
0x14001894a  mov     rcx, [rdi]
0x14001894d  mov     rcx, [rcx+rbp*8+0B70h]; hsem
0x140018955  call    cs:__imp_EngIsSemaphoreSharedByCurrentThread
0x14001895c  nop     dword ptr [rax+rax+00h]
0x140018961  test    eax, eax
0x140018963  jnz     loc_140018A32
0x140018969  mov     rcx, [rsi+20h]
0x14001896d  test    rcx, rcx
0x140018970  jnz     short loc_140018975
0x140018972  mov     rcx, [rdi]
0x140018975  mov     rcx, [rcx+rbp*8+0B70h]; hsem
0x14001897d  call    cs:__imp_EngAcquireSemaphoreNoWait
0x140018984  nop     dword ptr [rax+rax+00h]
0x140018989  cmp     eax, 1
0x14001898c  jnz     loc_140018A44
0x140018992  mov     [rsi+rbp+83h], al
0x140018999  inc     ebx
0x14001899b  jmp     loc_140018907
0x1400189a0  inc     r14d
0x1400189a3  jmp     loc_1400188BA
0x1400189a8  cmp     byte ptr [r8+14h], 0
0x1400189ad  jz      loc_140018753
0x1400189b3  mov     r14d, [r8+4]
0x1400189b7  mov     r15d, [r8+8]
0x1400189bb  mov     eax, [rdx]
0x1400189bd  cmp     r14d, eax
0x1400189c0  mov     r9d, [rdx+4]
0x1400189c4  mov     r8d, [rdx+8]
0x1400189c8  cmovle  r14d, eax
0x1400189cc  mov     ebx, [r10+0Ch]
0x1400189d0  cmp     r15d, r9d
0x1400189d3  mov     ecx, [rdx+0Ch]
0x1400189d6  mov     ebp, [r10+10h]
0x1400189da  cmovle  r15d, r9d
0x1400189de  cmp     ebx, r8d
0x1400189e1  cmovge  ebx, r8d
0x1400189e5  cmp     ebp, ecx
0x1400189e7  cmovge  ebp, ecx
0x1400189ea  jmp     loc_140018760
0x1400189ef  cmp     qword ptr [rdi], 0
0x1400189f3  jnz     short loc_140018A0B
0x1400189f5  lea     rcx, aCddmultisurflo_0; "CDDMULTISURFLOCK::VlockShadowW ppdev1 ="...
0x1400189fc  call    ?DbgLog@@YAXPEBDZZ; DbgLog(char const *,...)
0x140018a01  int     3; Trap to Debugger
0x140018a02  mov     rcx, [rsi+20h]
0x140018a06  jmp     loc_140018771
0x140018a0b  xor     ecx, ecx
0x140018a0d  jmp     loc_140018771
0x140018a12  mov     rcx, [rdi]
0x140018a15  jmp     loc_1400187AB
0x140018a1a  mov     r10, [rdi]
0x140018a1d  jmp     loc_14001881E
0x140018a22  mov     rcx, [rdi]
0x140018a25  jmp     loc_140018857
0x140018a2a  mov     rcx, [rdi]
0x140018a2d  jmp     loc_140018890
0x140018a32  lea     rcx, aCddmultisurflo; "CDDMULTISURFLOCK::CDDMULTISURFLOCK::vLo"...
0x140018a39  call    ?DbgLog@@YAXPEBDZZ; DbgLog(char const *,...)
0x140018a3e  int     3; Trap to Debugger
0x140018a3f  jmp     loc_140018969
0x140018a44  mov     rcx, rsi; this
0x140018a47  call    ?vUnLockShadowWAndWait@CDDMULTISURFLOCK@@QEAAXXZ; CDDMULTISURFLOCK::vUnLockShadowWAndWait(void)
0x140018a4c  xor     edx, edx; Val
0x140018a4e  mov     rcx, r15; void *
0x140018a51  lea     r8d, [rdx+51h]; Size
0x140018a55  call    memset
0x140018a5a  mov     r14d, [rsp+68h+arg_10]
0x140018a62  jmp     loc_140018883
0x140018a67  mov     rcx, [rdi]
0x140018a6a  jmp     loc_1400188CC
```
