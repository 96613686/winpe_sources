# DfscCreateLinkedConnectionWorker

- ea: `0x140014520`
- end: `0x140014651`
- name: `DfscCreateLinkedConnectionWorker`
- size: `305`
- prototype: `void __fastcall(_QWORD *StartContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x1400057c4`
- `0x14001338c`
- `0x140014520`
- `0x1400170a8`
- `0x140017294`
- `0x14002545c`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x140014634`
- `ntoskrnl!PsTerminateSystemThread` at `0x140014634`
- `ntoskrnl!KeSetEvent` at `0x140014626`
- `ntoskrnl!KeSetEvent` at `0x140014626`

## pseudocode

```c
void __fastcall DfscCreateLinkedConnectionWorker(_QWORD *StartContext)
{
  int NetUseConnection; // edi
  __int64 v3; // rcx
  _WORD *v4; // rdx
  _WORD *v5; // rax
  __int64 v6; // r8
  _WORD *v7; // rax
  __int64 v8; // rdx

  NetUseConnection = DfscImpersonateLinkedToken(*StartContext);
  if ( NetUseConnection < 0 )
  {
    if ( NetUseConnection == -1073741788 )
      NetUseConnection = 0;
  }
  else
  {
    NetUseConnection = DfscCreateNetUseConnection(
                         StartContext[11],
                         StartContext[5],
                         StartContext[6],
                         StartContext[7],
                         StartContext[8],
                         *((_DWORD *)StartContext + 20),
                         *((_DWORD *)StartContext + 24),
                         1,
                         0);
    if ( NetUseConnection >= 0 )
    {
      v3 = StartContext[8];
      if ( !*(_DWORD *)(v3 + 52) )
      {
        v4 = (_WORD *)(v3 + 56);
        if ( v3 != -56 )
        {
          if ( *v4 )
          {
            v5 = *(_WORD **)(v3 + 64);
            if ( v5 )
            {
              if ( *v5 )
              {
                v6 = StartContext[9];
                if ( v6 )
                {
                  if ( *(_WORD *)v6 )
                  {
                    v7 = *(_WORD **)(v6 + 8);
                    if ( v7 )
                    {
                      if ( *v7 )
                      {
                        NetUseConnection = DfscCredWrite(v3 + 8, (__int64)v4, v6);
                        if ( NetUseConnection < 0 )
                        {
                          v8 = StartContext[6];
                          if ( !v8 )
                            v8 = StartContext[7] + 80LL;
                          DfscDeleteNetUseConnection(StartContext[11], v8, StartContext[5], 2, 0, 0, 1);
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    DfscRevert();
  }
  *((_DWORD *)StartContext + 8) = NetUseConnection;
  KeSetEvent((PRKEVENT)(StartContext + 1), 0, 0);
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x140014520  mov     [rsp+arg_0], rbx
0x140014525  mov     [rsp+arg_8], rsi
0x14001452a  push    rdi
0x14001452b  sub     rsp, 50h
0x14001452f  mov     rbx, rcx
0x140014532  mov     rcx, [rcx]
0x140014535  call    DfscImpersonateLinkedToken
0x14001453a  xor     esi, esi
0x14001453c  mov     edi, eax
0x14001453e  test    eax, eax
0x140014540  js      loc_140014611
0x140014546  mov     eax, [rbx+60h]
0x140014549  mov     r9, [rbx+38h]
0x14001454d  mov     r8, [rbx+30h]
0x140014551  mov     rdx, [rbx+28h]
0x140014555  mov     rcx, [rbx+58h]
0x140014559  mov     [rsp+58h+var_18], rsi
0x14001455e  mov     [rsp+58h+var_20], 1
0x140014563  mov     [rsp+58h+var_28], eax
0x140014567  mov     eax, [rbx+50h]
0x14001456a  mov     dword ptr [rsp+58h+var_30], eax
0x14001456e  mov     rax, [rbx+40h]
0x140014572  mov     [rsp+58h+var_38], rax
0x140014577  call    DfscCreateNetUseConnection
0x14001457c  mov     edi, eax
0x14001457e  test    eax, eax
0x140014580  js      loc_14001460A
0x140014586  mov     rcx, [rbx+40h]
0x14001458a  cmp     [rcx+34h], esi
0x14001458d  jnz     short loc_14001460A
0x14001458f  lea     rdx, [rcx+38h]
0x140014593  test    rdx, rdx
0x140014596  jz      short loc_14001460A
0x140014598  cmp     [rdx], si
0x14001459b  jz      short loc_14001460A
0x14001459d  mov     rax, [rcx+40h]
0x1400145a1  test    rax, rax
0x1400145a4  jz      short loc_14001460A
0x1400145a6  cmp     [rax], si
0x1400145a9  jz      short loc_14001460A
0x1400145ab  mov     r8, [rbx+48h]
0x1400145af  test    r8, r8
0x1400145b2  jz      short loc_14001460A
0x1400145b4  cmp     [r8], si
0x1400145b8  jz      short loc_14001460A
0x1400145ba  mov     rax, [r8+8]
0x1400145be  test    rax, rax
0x1400145c1  jz      short loc_14001460A
0x1400145c3  cmp     [rax], si
0x1400145c6  jz      short loc_14001460A
0x1400145c8  add     rcx, 8
0x1400145cc  call    DfscCredWrite
0x1400145d1  mov     edi, eax
0x1400145d3  test    eax, eax
0x1400145d5  jns     short loc_14001460A
0x1400145d7  mov     rdx, [rbx+30h]
0x1400145db  test    rdx, rdx
0x1400145de  jnz     short loc_1400145E8
0x1400145e0  mov     rdx, [rbx+38h]
0x1400145e4  add     rdx, 50h ; 'P'
0x1400145e8  mov     r8, [rbx+28h]
0x1400145ec  mov     r9d, 2
0x1400145f2  mov     rcx, [rbx+58h]
0x1400145f6  mov     byte ptr [rsp+58h+var_28], 1
0x1400145fb  mov     [rsp+58h+var_30], rsi
0x140014600  mov     [rsp+58h+var_38], rsi
0x140014605  call    DfscDeleteNetUseConnection
0x14001460a  call    DfscRevert
0x14001460f  jmp     short loc_14001461A
0x140014611  cmp     edi, 0C0000024h
0x140014617  cmovz   edi, esi
0x14001461a  lea     rcx, [rbx+8]; Event
0x14001461e  mov     [rbx+20h], edi
0x140014621  xor     r8d, r8d; Wait
0x140014624  xor     edx, edx; Increment
0x140014626  call    cs:__imp_KeSetEvent
0x14001462d  nop     dword ptr [rax+rax+00h]
0x140014632  xor     ecx, ecx; ExitStatus
0x140014634  call    cs:__imp_PsTerminateSystemThread
0x14001463b  nop     dword ptr [rax+rax+00h]
0x140014640  mov     rbx, [rsp+58h+arg_0]
0x140014645  mov     rsi, [rsp+58h+arg_8]
0x14001464a  add     rsp, 50h
0x14001464e  pop     rdi
0x14001464f  retn
```
