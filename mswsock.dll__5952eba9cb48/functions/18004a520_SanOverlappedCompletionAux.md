# SanOverlappedCompletionAux

- ea: `0x18004a520`
- end: `0x18004a688`
- name: `SanOverlappedCompletionAux`
- size: `360`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004a690`
- `0x180050c40`

## callees

- `0x180008250`
- `0x180038118`
- `0x18003b760`
- `0x18003f158`
- `0x180049ba8`
- `0x18004a520`
- `0x18004f460`
- `0x18004f6c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a5d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a638`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a5d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a638`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a5bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a620`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a5bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a620`

## pseudocode

```c
__int64 __fastcall SanOverlappedCompletionAux(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  __int64 v4; // rdi
  __int64 v8; // rbx
  __int64 v9; // rsi
  __int64 v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // ebx

  v4 = a1 - 8;
  if ( *(_DWORD *)(a1 - 8) == 572662306 || *(_DWORD *)v4 == 286331153 )
  {
    v10 = *(_QWORD *)(v4 + 56);
    if ( (xmmword_180063D60 & 0x80u) != 0LL )
      WPP_SF_q(1031, 12, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v4);
    if ( *(_BYTE *)(v4 + 86) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
      HandleCompletedSend(v4);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 48));
    }
    else
    {
      v13 = *(_DWORD *)(v10 + 168);
      HandleCompletedRecv(v4, a3, a2);
      if ( v13 == 3 )
        return 0;
    }
    if ( _InterlockedExchangeAdd(*(volatile signed __int32 **)(v10 + 8), 0xFFFFFFFF) == 1 )
      SockDestroySocket(*(_QWORD *)(v10 + 8), v11, v12);
  }
  else if ( *(_DWORD *)v4 == 1145328981 )
  {
    HandleRdmaReadCompletion(a1 - 8, a3, a2);
  }
  else
  {
    v8 = *(_QWORD *)(v4 + 56);
    v9 = *(_QWORD *)(v4 + 64);
    if ( a2 || _InterlockedIncrement((volatile signed __int32 *)(v4 + 88)) != 2 )
    {
      if ( (BYTE1(xmmword_180063D60) & 0x10) != 0 )
        WPP_SF_q(1036, 15, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v4);
      CleanupRdmaWrite(v4, a4);
      EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 48));
      *(_DWORD *)(v9 + 92) &= ~0x80u;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 48));
      PostProcessRdmaSend(v4, a3, a2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004a520  push    rbx
0x18004a522  push    rbp
0x18004a523  push    rsi
0x18004a524  push    rdi
0x18004a525  push    r14
0x18004a527  push    r15
0x18004a529  sub     rsp, 28h
0x18004a52d  lea     rdi, [rcx-8]
0x18004a531  mov     r15, r9
0x18004a534  cmp     dword ptr [rdi], 22222222h
0x18004a53a  mov     r14d, r8d
0x18004a53d  mov     ebp, edx
0x18004a53f  jz      loc_18004A5F0
0x18004a545  cmp     dword ptr [rdi], 11111111h
0x18004a54b  jz      loc_18004A5F0
0x18004a551  cmp     dword ptr [rdi], 44445555h
0x18004a557  jnz     short loc_18004A56C
0x18004a559  mov     r8d, edx
0x18004a55c  mov     rcx, rdi
0x18004a55f  mov     edx, r14d
0x18004a562  call    HandleRdmaReadCompletion
0x18004a567  jmp     loc_18004A678
0x18004a56c  mov     rbx, [rdi+38h]
0x18004a570  mov     rsi, [rdi+40h]
0x18004a574  test    ebp, ebp
0x18004a576  jnz     short loc_18004A58B
0x18004a578  lea     eax, [rbp+1]
0x18004a57b  lock xadd [rdi+58h], eax
0x18004a580  inc     eax
0x18004a582  cmp     eax, 2
0x18004a585  jz      loc_18004A678
0x18004a58b  test    byte ptr cs:xmmword_180063D60+1, 10h
0x18004a592  jz      short loc_18004A5AD
0x18004a594  mov     edx, 0Fh
0x18004a599  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18004a5a0  mov     ecx, 40Ch
0x18004a5a5  mov     r9, rdi
0x18004a5a8  call    WPP_SF_q
0x18004a5ad  mov     rdx, r15
0x18004a5b0  mov     rcx, rdi
0x18004a5b3  call    CleanupRdmaWrite
0x18004a5b8  lea     rcx, [rbx+30h]; lpCriticalSection
0x18004a5bc  call    cs:__imp_EnterCriticalSection
0x18004a5c3  nop     dword ptr [rax+rax+00h]
0x18004a5c8  btr     dword ptr [rsi+5Ch], 7
0x18004a5cd  lea     rcx, [rbx+30h]; lpCriticalSection
0x18004a5d1  call    cs:__imp_LeaveCriticalSection
0x18004a5d8  nop     dword ptr [rax+rax+00h]
0x18004a5dd  mov     r8d, ebp
0x18004a5e0  mov     edx, r14d
0x18004a5e3  mov     rcx, rdi
0x18004a5e6  call    PostProcessRdmaSend
0x18004a5eb  jmp     loc_18004A678
0x18004a5f0  mov     rsi, [rdi+38h]
0x18004a5f4  cmp     byte ptr cs:xmmword_180063D60, 0
0x18004a5fb  jge     short loc_18004A616
0x18004a5fd  mov     edx, 0Ch
0x18004a602  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18004a609  mov     ecx, 407h
0x18004a60e  mov     r9, rdi
0x18004a611  call    WPP_SF_q
0x18004a616  cmp     byte ptr [rdi+56h], 0
0x18004a61a  jz      short loc_18004A646
0x18004a61c  lea     rcx, [rsi+30h]; lpCriticalSection
0x18004a620  call    cs:__imp_EnterCriticalSection
0x18004a627  nop     dword ptr [rax+rax+00h]
0x18004a62c  mov     rcx, rdi
0x18004a62f  call    HandleCompletedSend
0x18004a634  lea     rcx, [rsi+30h]; lpCriticalSection
0x18004a638  call    cs:__imp_LeaveCriticalSection
0x18004a63f  nop     dword ptr [rax+rax+00h]
0x18004a644  jmp     short loc_18004A65F
0x18004a646  mov     ebx, [rsi+0A8h]
0x18004a64c  mov     r8d, ebp
0x18004a64f  mov     edx, r14d
0x18004a652  mov     rcx, rdi
0x18004a655  call    HandleCompletedRecv
0x18004a65a  cmp     ebx, 3
0x18004a65d  jz      short loc_18004A678
0x18004a65f  mov     rcx, [rsi+8]
0x18004a663  or      eax, 0FFFFFFFFh
0x18004a666  lock xadd [rcx], eax
0x18004a66a  cmp     eax, 1
0x18004a66d  jnz     short loc_18004A678
0x18004a66f  mov     rcx, [rsi+8]
0x18004a673  call    SockDestroySocket
0x18004a678  xor     eax, eax
0x18004a67a  add     rsp, 28h
0x18004a67e  pop     r15
0x18004a680  pop     r14
0x18004a682  pop     rdi
0x18004a683  pop     rsi
0x18004a684  pop     rbp
0x18004a685  pop     rbx
0x18004a686  retn
```
