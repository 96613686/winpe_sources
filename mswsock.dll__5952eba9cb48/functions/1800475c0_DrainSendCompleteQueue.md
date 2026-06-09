# DrainSendCompleteQueue

- ea: `0x1800475c0`
- end: `0x1800477a2`
- name: `DrainSendCompleteQueue`
- size: `482`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180023c0c`
- `0x18003dbe4`
- `0x1800411a8`
- `0x180042128`
- `0x1800485dc`

## callees

- `0x18003ae8c`
- `0x18003aefc`
- `0x18003f158`
- `0x1800475c0`
- `0x18004a2dc`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004774b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047771`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047785`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004774b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047771`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047785`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800476ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047762`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800476ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047762`

## pseudocode

```c
void __fastcall DrainSendCompleteQueue(char *CompletionContext)
{
  _QWORD *v1; // r15
  _QWORD *v3; // r14
  int v4; // r12d
  __int64 v5; // rax
  char v6; // al
  int v7; // ecx
  char *v8; // rax
  unsigned int v9; // [rsp+80h] [rbp+8h] BYREF
  int v10; // [rsp+88h] [rbp+10h] BYREF
  int v11; // [rsp+90h] [rbp+18h] BYREF

  v1 = CompletionContext + 384;
  v9 = 0;
  v11 = 0;
  v10 = 0;
  while ( 1 )
  {
    v3 = (_QWORD *)*v1;
    if ( (_QWORD *)*v1 == v1 || !*((_BYTE *)v3 + 44) )
      break;
    v4 = *(_DWORD *)(v3[7] + 8LL);
    if ( (xmmword_180063D60 & 0x80u) != 0LL )
      WPP_SF_qq(1031, 215, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v3 - 5, CompletionContext);
    v5 = *((_QWORD *)CompletionContext + 2);
    v10 = 0;
    if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD *, int *, _QWORD, int *, unsigned int *))(v5 + 152))(
            *((_QWORD *)CompletionContext + 13),
            v3 - 4,
            &v11,
            0,
            &v10,
            &v9) )
    {
      v6 = xmmword_180063D60;
      if ( (xmmword_180063D60 & 0x80u) != 0LL )
      {
        WPP_SF_d(1031, 216, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v9);
        v6 = xmmword_180063D60;
      }
      if ( v9 == 996 )
        return;
      if ( (v6 & 2) != 0 )
        WPP_SF_d(1025, 217, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v9);
      v11 = *(_DWORD *)(v3[7] + 4LL);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
    if ( v3 != (_QWORD *)*v1 || (_QWORD *)*v1 == v1 || v4 != *(_DWORD *)(v3[7] + 8LL) )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
      return;
    }
    HandleCompletedSend(v3 - 5);
    if ( *((_WORD *)CompletionContext + 422) )
    {
      v7 = 0;
      v8 = (char *)*((_QWORD *)CompletionContext + 46);
      while ( v8 != CompletionContext + 368 )
      {
        v8 = *(char **)v8;
        ++v7;
      }
      if ( v7 == *(_DWORD *)(*((_QWORD *)CompletionContext + 2) + 368LL) )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
        ResizeSendBuffers(CompletionContext);
        EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  }
}

```

## disassembly

```asm
0x1800475c0  mov     rax, rsp
0x1800475c3  push    rbx
0x1800475c4  push    rsi
0x1800475c5  push    rdi
0x1800475c6  push    r12
0x1800475c8  push    r13
0x1800475ca  push    r14
0x1800475cc  push    r15
0x1800475ce  sub     rsp, 40h
0x1800475d2  xor     r13d, r13d
0x1800475d5  lea     r15, [rcx+180h]
0x1800475dc  mov     [rax+8], r13d
0x1800475e0  mov     rbx, rcx
0x1800475e3  mov     [rax+18h], r13d
0x1800475e7  mov     [rax+10h], r13d
0x1800475eb  mov     r14, [r15]
0x1800475ee  cmp     r14, r15
0x1800475f1  jz      loc_180047791
0x1800475f7  cmp     [r14+2Ch], r13b
0x1800475fb  jz      loc_180047791
0x180047601  mov     rax, [r14+38h]
0x180047605  mov     r12d, [rax+8]
0x180047609  cmp     byte ptr cs:xmmword_180063D60, r13b
0x180047610  jge     short loc_180047631
0x180047612  mov     edx, 0D7h
0x180047617  mov     [rsp+78h+var_58], rbx
0x18004761c  mov     ecx, 407h
0x180047621  lea     r9, [r14-28h]
0x180047625  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18004762c  call    WPP_SF_qq
0x180047631  mov     rax, [rbx+10h]
0x180047635  lea     rcx, [rsp+78h+arg_0]
0x18004763d  mov     [rsp+78h+var_50], rcx
0x180047642  lea     rdx, [r14-20h]
0x180047646  lea     rcx, [rsp+78h+arg_8]
0x18004764e  mov     [rsp+78h+arg_8], r13d
0x180047656  mov     [rsp+78h+var_58], rcx
0x18004765b  lea     r8, [rsp+78h+arg_10]
0x180047663  mov     rcx, [rbx+68h]
0x180047667  xor     r9d, r9d
0x18004766a  mov     rax, [rax+98h]
0x180047671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047676  test    eax, eax
0x180047678  jnz     short loc_1800476E5
0x18004767a  mov     al, byte ptr cs:xmmword_180063D60
0x180047680  test    al, al
0x180047682  jns     short loc_1800476A8
0x180047684  mov     r9d, [rsp+78h+arg_0]
0x18004768c  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x180047693  mov     edx, 0D8h
0x180047698  mov     ecx, 407h
0x18004769d  call    WPP_SF_d
0x1800476a2  mov     al, byte ptr cs:xmmword_180063D60
0x1800476a8  mov     r9d, [rsp+78h+arg_0]
0x1800476b0  cmp     r9d, 3E4h
0x1800476b7  jz      loc_180047791
0x1800476bd  test    al, 2
0x1800476bf  jz      short loc_1800476D7
0x1800476c1  mov     edx, 0D9h
0x1800476c6  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x1800476cd  mov     ecx, 401h
0x1800476d2  call    WPP_SF_d
0x1800476d7  mov     rax, [r14+38h]
0x1800476db  mov     ecx, [rax+4]
0x1800476de  mov     [rsp+78h+arg_10], ecx
0x1800476e5  lea     rsi, [rbx+30h]
0x1800476e9  mov     rcx, rsi; lpCriticalSection
0x1800476ec  call    cs:__imp_EnterCriticalSection
0x1800476f3  nop     dword ptr [rax+rax+00h]
0x1800476f8  cmp     r14, [r15]
0x1800476fb  jnz     loc_180047782
0x180047701  cmp     [r15], r15
0x180047704  jz      short loc_180047782
0x180047706  mov     rax, [r14+38h]
0x18004770a  cmp     r12d, [rax+8]
0x18004770e  jnz     short loc_180047782
0x180047710  lea     rcx, [r14-28h]
0x180047714  call    HandleCompletedSend
0x180047719  cmp     [rbx+34Ch], r13w
0x180047721  jz      short loc_18004776E
0x180047723  lea     rdx, [rbx+170h]
0x18004772a  mov     ecx, r13d
0x18004772d  mov     rax, [rdx]
0x180047730  jmp     short loc_180047737
0x180047732  mov     rax, [rax]
0x180047735  inc     ecx
0x180047737  cmp     rax, rdx
0x18004773a  jnz     short loc_180047732
0x18004773c  mov     rax, [rbx+10h]
0x180047740  cmp     ecx, [rax+170h]
0x180047746  jnz     short loc_18004776E
0x180047748  mov     rcx, rsi; lpCriticalSection
0x18004774b  call    cs:__imp_LeaveCriticalSection
0x180047752  nop     dword ptr [rax+rax+00h]
0x180047757  mov     rcx, rbx; CompletionContext
0x18004775a  call    ResizeSendBuffers
0x18004775f  mov     rcx, rsi; lpCriticalSection
0x180047762  call    cs:__imp_EnterCriticalSection
0x180047769  nop     dword ptr [rax+rax+00h]
0x18004776e  mov     rcx, rsi; lpCriticalSection
0x180047771  call    cs:__imp_LeaveCriticalSection
0x180047778  nop     dword ptr [rax+rax+00h]
0x18004777d  jmp     loc_1800475EB
0x180047782  mov     rcx, rsi; lpCriticalSection
0x180047785  call    cs:__imp_LeaveCriticalSection
0x18004778c  nop     dword ptr [rax+rax+00h]
0x180047791  add     rsp, 40h
0x180047795  pop     r15
0x180047797  pop     r14
0x180047799  pop     r13
0x18004779b  pop     r12
0x18004779d  pop     rdi
0x18004779e  pop     rsi
0x18004779f  pop     rbx
0x1800477a0  retn
```
