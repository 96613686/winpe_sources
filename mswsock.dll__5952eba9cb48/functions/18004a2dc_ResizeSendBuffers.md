# ResizeSendBuffers

- ea: `0x18004a2dc`
- end: `0x18004a518`
- name: `ResizeSendBuffers`
- size: `572`
- prototype: `__int64 __fastcall(PVOID CompletionContext)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800475c0`
- `0x1800485dc`

## callees

- `0x180038104`
- `0x180038a20`
- `0x18003c7cc`
- `0x18004577c`
- `0x18004a2dc`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18004a3c8`
- `ntdll!RtlFreeHeap` at `0x18004a3c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a4bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a4eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a4bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a4eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a427`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a4cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a427`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a4cb`

## pseudocode

```c
__int64 __fastcall ResizeSendBuffers(char *CompletionContext)
{
  unsigned __int16 v1; // r14
  unsigned __int16 v3; // cx
  __int16 v4; // r13
  _QWORD *v5; // rbx
  char *v6; // rsi
  __int64 v7; // r12
  _QWORD *v8; // rcx
  int v9; // r8d
  _QWORD *v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rdx
  int ControlBuffers; // [rsp+60h] [rbp+8h] BYREF

  v1 = *((_WORD *)CompletionContext + 418);
  v3 = *((_WORD *)CompletionContext + 422);
  ControlBuffers = 0;
  if ( v3 > v1 )
  {
    v4 = *((_WORD *)CompletionContext + 419);
    v5 = CompletionContext + 368;
    v6 = (char *)*((_QWORD *)CompletionContext + 33);
    v7 = *(_QWORD *)(*((_QWORD *)CompletionContext + 46) + 24LL);
    *((_WORD *)CompletionContext + 419) = v3;
    *((_WORD *)CompletionContext + 418) = v3;
    *((_QWORD *)CompletionContext + 47) = CompletionContext + 368;
    *((_QWORD *)CompletionContext + 46) = CompletionContext + 368;
    ControlBuffers = AllocateControlBuffers(
                       CompletionContext,
                       0,
                       *(unsigned int *)(*((_QWORD *)CompletionContext + 2) + 368LL),
                       0);
    if ( ControlBuffers )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
      {
        WPP_SF_qD(1025, 50, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, CompletionContext, ControlBuffers);
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_(1025, 51, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids);
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
      v8 = (_QWORD *)*((_QWORD *)CompletionContext + 36);
      v9 = 0;
      *((_QWORD *)CompletionContext + 33) = v6;
      *((_WORD *)CompletionContext + 419) = v4;
      *((_WORD *)CompletionContext + 418) = v1;
      *((_QWORD *)CompletionContext + 47) = CompletionContext + 368;
      *v5 = v5;
      if ( *(int *)(*((_QWORD *)CompletionContext + 2) + 368LL) > 0 )
      {
        while ( 1 )
        {
          v8[8] = v7;
          v8[12] = v6;
          v10 = (_QWORD *)*((_QWORD *)CompletionContext + 47);
          if ( (_QWORD *)*v10 != v5 )
            __fastfail(3u);
          v11 = *((unsigned __int16 *)CompletionContext + 418);
          v8[5] = v5;
          ++v9;
          v8[6] = v10;
          *v10 = v8 + 5;
          *((_QWORD *)CompletionContext + 47) = v8 + 5;
          if ( v9 >= *(_DWORD *)(*((_QWORD *)CompletionContext + 2) + 368LL) )
            break;
          v6 += v11 + 40;
          v8 += 13;
        }
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
    }
    else
    {
      if ( (BYTE3(xmmword_180063D60) & 1) != 0 )
        WPP_SF_qD(
          1048,
          49,
          WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids,
          CompletionContext,
          *((unsigned __int16 *)CompletionContext + 419));
      (*(void (__fastcall **)(_QWORD, __int64, int *))(*((_QWORD *)CompletionContext + 2) + 312LL))(
        *((_QWORD *)CompletionContext + 13),
        v7,
        &ControlBuffers);
      RtlFreeHeap(SockPrivateHeap, 0, v6);
    }
  }
  else
  {
    *((_WORD *)CompletionContext + 419) = v3;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  CompletionContext[801] &= ~2u;
  *((_WORD *)CompletionContext + 422) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  return RestartBlockedSends((volatile signed __int32 *)CompletionContext, v12);
}

```

## disassembly

```asm
0x18004a2dc  mov     [rsp+arg_8], rbx
0x18004a2e1  mov     [rsp+arg_10], rsi
0x18004a2e6  push    rdi
0x18004a2e7  push    r12
0x18004a2e9  push    r13
0x18004a2eb  push    r14
0x18004a2ed  push    r15
0x18004a2ef  sub     rsp, 30h
0x18004a2f3  movzx   r14d, word ptr [rcx+344h]
0x18004a2fb  mov     rdi, rcx
0x18004a2fe  movzx   ecx, word ptr [rcx+34Ch]
0x18004a305  mov     [rsp+58h+arg_0], 0
0x18004a30d  cmp     cx, r14w
0x18004a311  ja      short loc_18004A31F
0x18004a313  mov     [rdi+346h], cx
0x18004a31a  jmp     loc_18004A4C7
0x18004a31f  movzx   r13d, word ptr [rdi+346h]
0x18004a327  lea     rbx, [rdi+170h]
0x18004a32e  mov     rax, [rbx]
0x18004a331  xor     r9d, r9d
0x18004a334  mov     rsi, [rdi+108h]
0x18004a33b  xor     edx, edx
0x18004a33d  mov     r12, [rax+18h]
0x18004a341  mov     [rdi+346h], cx
0x18004a348  mov     [rdi+344h], cx
0x18004a34f  mov     rcx, rdi
0x18004a352  mov     [rbx+8], rbx
0x18004a356  mov     [rbx], rbx
0x18004a359  mov     r8, [rdi+10h]
0x18004a35d  mov     r8d, [r8+170h]
0x18004a364  call    AllocateControlBuffers
0x18004a369  mov     [rsp+58h+arg_0], eax
0x18004a36d  mov     r8d, eax
0x18004a370  test    eax, eax
0x18004a372  jnz     short loc_18004A3D9
0x18004a374  test    byte ptr cs:xmmword_180063D60+3, 1
0x18004a37b  jz      short loc_18004A3A0
0x18004a37d  movzx   eax, word ptr [rdi+346h]
0x18004a384  lea     edx, [r8+31h]
0x18004a388  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18004a38f  mov     [rsp+58h+var_38], eax
0x18004a393  mov     ecx, 418h
0x18004a398  mov     r9, rdi
0x18004a39b  call    WPP_SF_qD
0x18004a3a0  mov     rax, [rdi+10h]
0x18004a3a4  lea     r8, [rsp+58h+arg_0]
0x18004a3a9  mov     rcx, [rdi+68h]
0x18004a3ad  mov     rdx, r12
0x18004a3b0  mov     rax, [rax+138h]
0x18004a3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a3bc  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18004a3c3  mov     r8, rsi; P
0x18004a3c6  xor     edx, edx; Flags
0x18004a3c8  call    cs:__imp_RtlFreeHeap
0x18004a3cf  nop     dword ptr [rax+rax+00h]
0x18004a3d4  jmp     loc_18004A4C7
0x18004a3d9  mov     al, byte ptr cs:xmmword_180063D60
0x18004a3df  mov     r15d, 401h
0x18004a3e5  test    al, 2
0x18004a3e7  jz      short loc_18004A423
0x18004a3e9  mov     [rsp+58h+var_38], r8d
0x18004a3ee  mov     edx, 32h ; '2'
0x18004a3f3  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18004a3fa  mov     ecx, r15d
0x18004a3fd  mov     r9, rdi
0x18004a400  call    WPP_SF_qD
0x18004a405  mov     al, byte ptr cs:xmmword_180063D60
0x18004a40b  test    al, 2
0x18004a40d  jz      short loc_18004A423
0x18004a40f  mov     edx, 33h ; '3'
0x18004a414  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18004a41b  mov     ecx, r15d
0x18004a41e  call    WPP_SF_
0x18004a423  lea     rcx, [rdi+30h]; lpCriticalSection
0x18004a427  call    cs:__imp_EnterCriticalSection
0x18004a42e  nop     dword ptr [rax+rax+00h]
0x18004a433  mov     rcx, [rdi+120h]
0x18004a43a  xor     r8d, r8d
0x18004a43d  mov     [rdi+108h], rsi
0x18004a444  mov     [rdi+346h], r13w
0x18004a44c  mov     [rdi+344h], r14w
0x18004a454  mov     [rbx+8], rbx
0x18004a458  mov     [rbx], rbx
0x18004a45b  mov     rax, [rdi+10h]
0x18004a45f  cmp     [rax+170h], r8d
0x18004a466  jle     short loc_18004A4B7
0x18004a468  mov     [rcx+40h], r12
0x18004a46c  mov     [rcx+60h], rsi
0x18004a470  mov     rdx, [rbx+8]
0x18004a474  cmp     [rdx], rbx
0x18004a477  jnz     short loc_18004A4B0
0x18004a479  movzx   r9d, word ptr [rdi+344h]
0x18004a481  lea     rax, [rcx+28h]
0x18004a485  mov     [rax], rbx
0x18004a488  inc     r8d
0x18004a48b  mov     [rax+8], rdx
0x18004a48f  mov     [rdx], rax
0x18004a492  mov     [rbx+8], rax
0x18004a496  mov     rax, [rdi+10h]
0x18004a49a  cmp     r8d, [rax+170h]
0x18004a4a1  jge     short loc_18004A4B7
0x18004a4a3  lea     rax, [r9+28h]
0x18004a4a7  add     rsi, rax
0x18004a4aa  add     rcx, 68h ; 'h'
0x18004a4ae  jmp     short loc_18004A468
0x18004a4b0  mov     ecx, 3
0x18004a4b5  int     29h; Win8: RtlFailFast(ecx)
0x18004a4b7  lea     rcx, [rdi+30h]; lpCriticalSection
0x18004a4bb  call    cs:__imp_LeaveCriticalSection
0x18004a4c2  nop     dword ptr [rax+rax+00h]
0x18004a4c7  lea     rcx, [rdi+30h]; lpCriticalSection
0x18004a4cb  call    cs:__imp_EnterCriticalSection
0x18004a4d2  nop     dword ptr [rax+rax+00h]
0x18004a4d7  and     byte ptr [rdi+321h], 0FDh
0x18004a4de  lea     rcx, [rdi+30h]; lpCriticalSection
0x18004a4e2  xor     eax, eax
0x18004a4e4  mov     [rdi+34Ch], ax
0x18004a4eb  call    cs:__imp_LeaveCriticalSection
0x18004a4f2  nop     dword ptr [rax+rax+00h]
0x18004a4f7  mov     rcx, rdi; CompletionContext
0x18004a4fa  call    RestartBlockedSends
0x18004a4ff  mov     rbx, [rsp+58h+arg_8]
0x18004a504  mov     rsi, [rsp+58h+arg_10]
0x18004a509  add     rsp, 30h
0x18004a50d  pop     r15
0x18004a50f  pop     r14
0x18004a511  pop     r13
0x18004a513  pop     r12
0x18004a515  pop     rdi
0x18004a516  retn
```
