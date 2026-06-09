# NDownLevelCrew::TWorkCrew::CancelWork(void *,uchar)

- ea: `0x14005c600`
- end: `0x14005c75f`
- name: `?CancelWork@TWorkCrew@NDownLevelCrew@@CAXPEAXE@Z`
- size: `351`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14005c824`

## callees

- `0x140005358`
- `0x1400086a4`
- `0x1400172e8`
- `0x14005c600`

## import_xrefs

- `KERNEL32!UnregisterWaitEx` at `0x14005c6c3`
- `KERNEL32!UnregisterWaitEx` at `0x14005c6c3`
- `KERNEL32!LeaveCriticalSection` at `0x14005c673`
- `KERNEL32!LeaveCriticalSection` at `0x14005c74c`
- `KERNEL32!LeaveCriticalSection` at `0x14005c673`
- `KERNEL32!LeaveCriticalSection` at `0x14005c74c`
- `KERNEL32!DeleteTimerQueueTimer` at `0x14005c6a1`
- `KERNEL32!DeleteTimerQueueTimer` at `0x14005c6a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall NDownLevelCrew::TWorkCrew::CancelWork(char *a1)
{
  char *v2; // rbx
  char *i; // rdi
  __int64 v4; // rdi
  void *v5; // rcx
  void *v6; // rdx
  NCoreLibrary *v7; // rcx
  void *v8; // rcx
  NCoreLibrary *v9; // rcx

  if ( !a1 || *((_DWORD *)a1 + 4) != 2003985271 )
    return;
  v2 = a1 + 32;
  NCoreLibrary::TCriticalSection::Enter((struct _RTL_CRITICAL_SECTION *)(a1 + 32));
  if ( *((_DWORD *)a1 + 50) )
    goto LABEL_23;
  *((_DWORD *)a1 + 50) = 1;
  for ( i = (char *)*((_QWORD *)a1 + 19); ; i = (char *)*((_QWORD *)a1 + 19) )
  {
    *(_QWORD *)(*((_QWORD *)i + 2) + 24LL) = *((_QWORD *)i + 3);
    *(_QWORD *)(*((_QWORD *)i + 3) + 16LL) = *((_QWORD *)i + 2);
    *((_QWORD *)i + 2) = i;
    *((_QWORD *)i + 3) = i;
    if ( i == a1 + 136 )
      i = 0;
    if ( !i )
      break;
    if ( !--*((_DWORD *)v2 + 11) )
      *((_DWORD *)v2 + 10) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)v2);
    v4 = *((_QWORD *)i + 4);
    if ( *(_DWORD *)(v4 + 76) == 1 )
    {
      v8 = *(void **)(v4 + 104);
      if ( !v8 )
        goto LABEL_18;
      if ( !UnregisterWaitEx(v8, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
        NCoreLibrary::GetLastErrorAsHResult(v9);
LABEL_17:
      *(_QWORD *)(v4 + 104) = 0;
      goto LABEL_18;
    }
    if ( *(_DWORD *)(v4 + 76) == 2 )
    {
      v5 = (void *)*((_QWORD *)a1 + 3);
      if ( v5 )
      {
        v6 = *(void **)(v4 + 104);
        if ( v6 )
        {
          if ( DeleteTimerQueueTimer(v5, v6, (HANDLE)0xFFFFFFFFFFFFFFFFLL)
            || (int)NCoreLibrary::GetLastErrorAsHResult(v7) >= 0 )
          {
            goto LABEL_17;
          }
        }
      }
    }
LABEL_18:
    *(_DWORD *)(v4 + 112) = 0;
    *(_QWORD *)(v4 + 120) = 0;
    NCoreLibrary::TReferenceCount::Release((NCoreLibrary::TReferenceCount *)v4);
    NCoreLibrary::TCriticalSection::Enter((struct _RTL_CRITICAL_SECTION *)v2);
  }
  *((_DWORD *)a1 + 50) = 0;
LABEL_23:
  if ( (*((_DWORD *)v2 + 11))-- == 1 )
    *((_DWORD *)v2 + 10) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v2);
}

```

## disassembly

```asm
0x14005c600  test    rcx, rcx
0x14005c603  jz      locret_14005C75E
0x14005c609  mov     [rsp+arg_8], rbx
0x14005c60e  push    rbp
0x14005c60f  push    rsi
0x14005c610  push    rdi
0x14005c611  sub     rsp, 20h
0x14005c615  mov     rsi, rcx
0x14005c618  cmp     dword ptr [rcx+10h], 77726377h
0x14005c61f  jnz     loc_14005C752
0x14005c625  lea     rbx, [rcx+20h]
0x14005c629  mov     [rsp+38h+arg_0], rbx
0x14005c62e  mov     rcx, rbx; this
0x14005c631  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x14005c636  nop
0x14005c637  cmp     dword ptr [rsi+0C8h], 0
0x14005c63e  jnz     loc_14005C739
0x14005c644  mov     dword ptr [rsi+0C8h], 1
0x14005c64e  lea     rbp, [rsi+88h]
0x14005c655  mov     rdi, [rbp+10h]
0x14005c659  jmp     loc_14005C701
0x14005c65e  mov     [rsp+38h+arg_10], rbx
0x14005c663  dec     dword ptr [rbx+2Ch]
0x14005c666  mov     eax, [rbx+2Ch]
0x14005c669  test    eax, eax
0x14005c66b  jnz     short loc_14005C670
0x14005c66d  mov     [rbx+28h], eax
0x14005c670  mov     rcx, rbx; lpCriticalSection
0x14005c673  call    cs:__imp_LeaveCriticalSection
0x14005c679  nop
0x14005c67a  mov     rdi, [rdi+20h]
0x14005c67e  mov     ecx, [rdi+4Ch]
0x14005c681  sub     ecx, 1
0x14005c684  jz      short loc_14005C6B6
0x14005c686  cmp     ecx, 1
0x14005c689  jnz     short loc_14005C6DA
0x14005c68b  mov     rcx, [rsi+18h]; TimerQueue
0x14005c68f  test    rcx, rcx
0x14005c692  jz      short loc_14005C6DA
0x14005c694  mov     rdx, [rdi+68h]; Timer
0x14005c698  test    rdx, rdx
0x14005c69b  jz      short loc_14005C6DA
0x14005c69d  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x14005c6a1  call    cs:__imp_DeleteTimerQueueTimer
0x14005c6a7  test    eax, eax
0x14005c6a9  jnz     short loc_14005C6D2
0x14005c6ab  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14005c6b0  test    eax, eax
0x14005c6b2  js      short loc_14005C6DA
0x14005c6b4  jmp     short loc_14005C6D2
0x14005c6b6  mov     rcx, [rdi+68h]; WaitHandle
0x14005c6ba  test    rcx, rcx
0x14005c6bd  jz      short loc_14005C6DA
0x14005c6bf  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x14005c6c3  call    cs:__imp_UnregisterWaitEx
0x14005c6c9  test    eax, eax
0x14005c6cb  jnz     short loc_14005C6D2
0x14005c6cd  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14005c6d2  mov     qword ptr [rdi+68h], 0
0x14005c6da  mov     dword ptr [rdi+70h], 0
0x14005c6e1  mov     qword ptr [rdi+78h], 0
0x14005c6e9  mov     rcx, rdi; this
0x14005c6ec  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x14005c6f1  nop
0x14005c6f2  mov     rcx, rbx; this
0x14005c6f5  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x14005c6fa  mov     rdi, [rsi+98h]
0x14005c701  mov     rcx, [rdi+10h]
0x14005c705  mov     rax, [rdi+18h]
0x14005c709  mov     [rcx+18h], rax
0x14005c70d  mov     rcx, [rdi+18h]
0x14005c711  mov     rax, [rdi+10h]
0x14005c715  mov     [rcx+10h], rax
0x14005c719  xor     eax, eax
0x14005c71b  mov     [rdi+10h], rdi
0x14005c71f  mov     [rdi+18h], rdi
0x14005c723  cmp     rdi, rbp
0x14005c726  cmovz   rdi, rax
0x14005c72a  test    rdi, rdi
0x14005c72d  jnz     loc_14005C65E
0x14005c733  mov     [rsi+0C8h], edi
0x14005c739  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x14005c73d  mov     eax, [rbx+2Ch]
0x14005c740  jnz     short loc_14005C749
0x14005c742  mov     dword ptr [rbx+28h], 0
0x14005c749  mov     rcx, rbx; lpCriticalSection
0x14005c74c  call    cs:__imp_LeaveCriticalSection
0x14005c752  mov     rbx, [rsp+38h+arg_8]
0x14005c757  add     rsp, 20h
0x14005c75b  pop     rdi
0x14005c75c  pop     rsi
0x14005c75d  pop     rbp
0x14005c75e  retn
```
