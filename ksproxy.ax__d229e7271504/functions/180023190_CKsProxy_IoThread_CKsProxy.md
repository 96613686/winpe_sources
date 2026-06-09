# CKsProxy::IoThread(CKsProxy *)

- ea: `0x180023190`
- end: `0x180023386`
- name: `?IoThread@CKsProxy@@SAKPEAV1@@Z`
- size: `502`
- prototype: `__int64 __fastcall(char *Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180023190`
- `0x180025860`
- `0x180025890`
- `0x18004485c`
- `0x180045010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180023269`
- `KERNEL32!CloseHandle` at `0x180023269`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800231f3`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1800231f3`
- `KERNEL32!LeaveCriticalSection` at `0x1800232ea`
- `KERNEL32!LeaveCriticalSection` at `0x180023330`
- `KERNEL32!LeaveCriticalSection` at `0x180023341`
- `KERNEL32!LeaveCriticalSection` at `0x1800232ea`
- `KERNEL32!LeaveCriticalSection` at `0x180023330`
- `KERNEL32!LeaveCriticalSection` at `0x180023341`
- `KERNEL32!ReleaseSemaphore` at `0x180023304`
- `KERNEL32!ReleaseSemaphore` at `0x180023304`
- `KERNEL32!EnterCriticalSection` at `0x180023287`
- `KERNEL32!EnterCriticalSection` at `0x180023318`
- `KERNEL32!EnterCriticalSection` at `0x180023287`
- `KERNEL32!EnterCriticalSection` at `0x180023318`

## pseudocode

```c
__int64 __fastcall CKsProxy::IoThread(char *Parameter)
{
  DWORD v2; // eax
  __int64 v3; // rdi
  _QWORD *v4; // rdx
  void *v5; // rcx
  int v6; // edx
  struct _RTL_CRITICAL_SECTION *v7; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
      *((_QWORD *)Parameter + 11));
  while ( 1 )
  {
    while ( 1 )
    {
      v2 = WaitForMultipleObjectsEx(*((_DWORD *)Parameter + 118), *((const HANDLE **)Parameter + 57), 0, 0xFFFFFFFF, 0);
      v3 = v2;
      if ( !v2 )
        break;
      if ( v2 != -1 )
      {
        if ( v2 <= 0x3F )
        {
          _mm_lfence();
          v4 = *(_QWORD **)(*((_QWORD *)Parameter + 58) + 8LL * v2);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 40LL))(*v4);
          v5 = *(void **)(*((_QWORD *)Parameter + 57) + 8 * v3);
          if ( v5 )
          {
            CloseHandle(v5);
            *(_QWORD *)(*((_QWORD *)Parameter + 57) + 8 * v3) = 0;
          }
          EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 408));
          v6 = --*((_DWORD *)Parameter + 118);
          if ( v6 > 1 && (_DWORD)v3 != v6 )
          {
            memmove_0(
              (void *)(*((_QWORD *)Parameter + 57) + 8 * v3),
              (const void *)(*((_QWORD *)Parameter + 57) + 8 * v3 + 8),
              8LL * (unsigned int)(v6 - v3));
            memmove_0(
              (void *)(*((_QWORD *)Parameter + 58) + 8 * v3),
              (const void *)(*((_QWORD *)Parameter + 58) + 8 * v3 + 8),
              8LL * (unsigned int)(*((_DWORD *)Parameter + 118) - v3));
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 408));
          ReleaseSemaphore(*((HANDLE *)Parameter + 56), 1, 0);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids);
        }
      }
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 408));
    v7 = (struct _RTL_CRITICAL_SECTION *)(Parameter + 408);
    if ( *((_DWORD *)Parameter + 101) )
      break;
    LeaveCriticalSection(v7);
  }
  LeaveCriticalSection(v7);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
      *((_QWORD *)Parameter + 11));
  return 0;
}

```

## disassembly

```asm
0x180023190  push    rbx
0x180023192  push    rbp
0x180023193  push    rsi
0x180023194  push    rdi
0x180023195  push    r12
0x180023197  sub     rsp, 30h
0x18002319b  mov     rbx, rcx
0x18002319e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800231a5  lea     r12, WPP_GLOBAL_Control
0x1800231ac  cmp     rcx, r12
0x1800231af  jz      short loc_1800231D0
0x1800231b1  cmp     byte ptr [rcx+19h], 2
0x1800231b5  jb      short loc_1800231D0
0x1800231b7  mov     r9, [rbx+58h]
0x1800231bb  lea     r8, WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids
0x1800231c2  mov     rcx, [rcx+10h]
0x1800231c6  mov     edx, 0Ah
0x1800231cb  call    WPP_SF_S
0x1800231d0  lea     rsi, [rbx+198h]
0x1800231d7  mov     rdx, [rbx+1C8h]; lpHandles
0x1800231de  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800231e2  mov     ecx, [rbx+1D8h]; nCount
0x1800231e8  xor     r8d, r8d; bWaitAll
0x1800231eb  mov     [rsp+58h+bAlertable], 0; bAlertable
0x1800231f3  call    cs:__imp_WaitForMultipleObjectsEx
0x1800231fa  nop     dword ptr [rax+rax+00h]
0x1800231ff  mov     edi, eax
0x180023201  test    eax, eax
0x180023203  jz      loc_180023315
0x180023209  cmp     edi, 0FFFFFFFFh
0x18002320c  jz      short loc_1800231D7
0x18002320e  cmp     edi, 3Fh ; '?'
0x180023211  jbe     short loc_18002323C
0x180023213  mov     rcx, cs:WPP_GLOBAL_Control
0x18002321a  cmp     rcx, r12
0x18002321d  jz      short loc_1800231D7
0x18002321f  cmp     byte ptr [rcx+19h], 2
0x180023223  jb      short loc_1800231D7
0x180023225  mov     rcx, [rcx+10h]
0x180023229  lea     r8, WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids
0x180023230  mov     edx, 0Ch
0x180023235  call    WPP_SF_
0x18002323a  jmp     short loc_1800231D7
0x18002323c  lfence
0x18002323f  mov     rax, [rbx+1D0h]
0x180023246  mov     rdx, [rax+rdi*8]
0x18002324a  mov     rcx, [rdx]
0x18002324d  mov     rax, [rcx]
0x180023250  mov     rax, [rax+28h]
0x180023254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023259  mov     rax, [rbx+1C8h]
0x180023260  mov     rcx, [rax+rdi*8]; hObject
0x180023264  test    rcx, rcx
0x180023267  jz      short loc_180023284
0x180023269  call    cs:__imp_CloseHandle
0x180023270  nop     dword ptr [rax+rax+00h]
0x180023275  mov     rax, [rbx+1C8h]
0x18002327c  mov     qword ptr [rax+rdi*8], 0
0x180023284  mov     rcx, rsi; lpCriticalSection
0x180023287  call    cs:__imp_EnterCriticalSection
0x18002328e  nop     dword ptr [rax+rax+00h]
0x180023293  dec     dword ptr [rbx+1D8h]
0x180023299  mov     edx, [rbx+1D8h]
0x18002329f  cmp     edx, 1
0x1800232a2  jle     short loc_1800232E7
0x1800232a4  cmp     edi, edx
0x1800232a6  jz      short loc_1800232E7
0x1800232a8  mov     rax, [rbx+1C8h]
0x1800232af  sub     edx, edi
0x1800232b1  mov     r8d, edx
0x1800232b4  shl     r8, 3; Size
0x1800232b8  lea     rcx, [rax+rdi*8]; void *
0x1800232bc  lea     rdx, [rcx+8]; Src
0x1800232c0  call    memmove_0
0x1800232c5  mov     r8d, [rbx+1D8h]
0x1800232cc  mov     rax, [rbx+1D0h]
0x1800232d3  sub     r8d, edi
0x1800232d6  shl     r8, 3; Size
0x1800232da  lea     rcx, [rax+rdi*8]; void *
0x1800232de  lea     rdx, [rcx+8]; Src
0x1800232e2  call    memmove_0
0x1800232e7  mov     rcx, rsi; lpCriticalSection
0x1800232ea  call    cs:__imp_LeaveCriticalSection
0x1800232f1  nop     dword ptr [rax+rax+00h]
0x1800232f6  mov     rcx, [rbx+1C0h]; hSemaphore
0x1800232fd  xor     r8d, r8d; lpPreviousCount
0x180023300  lea     edx, [r8+1]; lReleaseCount
0x180023304  call    cs:__imp_ReleaseSemaphore
0x18002330b  nop     dword ptr [rax+rax+00h]
0x180023310  jmp     loc_1800231D7
0x180023315  mov     rcx, rsi; lpCriticalSection
0x180023318  call    cs:__imp_EnterCriticalSection
0x18002331f  nop     dword ptr [rax+rax+00h]
0x180023324  cmp     dword ptr [rbx+194h], 0
0x18002332b  mov     rcx, rsi; lpCriticalSection
0x18002332e  jnz     short loc_180023341
0x180023330  call    cs:__imp_LeaveCriticalSection
0x180023337  nop     dword ptr [rax+rax+00h]
0x18002333c  jmp     loc_1800231D7
0x180023341  call    cs:__imp_LeaveCriticalSection
0x180023348  nop     dword ptr [rax+rax+00h]
0x18002334d  mov     rcx, cs:WPP_GLOBAL_Control
0x180023354  cmp     rcx, r12
0x180023357  jz      short loc_180023378
0x180023359  cmp     byte ptr [rcx+19h], 2
0x18002335d  jb      short loc_180023378
0x18002335f  mov     r9, [rbx+58h]
0x180023363  lea     r8, WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids
0x18002336a  mov     rcx, [rcx+10h]
0x18002336e  mov     edx, 0Bh
0x180023373  call    WPP_SF_S
0x180023378  xor     eax, eax
0x18002337a  add     rsp, 30h
0x18002337e  pop     r12
0x180023380  pop     rdi
0x180023381  pop     rsi
0x180023382  pop     rbp
0x180023383  pop     rbx
0x180023384  retn
```
