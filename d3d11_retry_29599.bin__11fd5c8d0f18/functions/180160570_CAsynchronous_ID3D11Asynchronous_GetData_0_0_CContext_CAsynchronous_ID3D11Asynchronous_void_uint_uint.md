# CAsynchronous<ID3D11Asynchronous>::GetData<0,0>(CContext *,CAsynchronous<ID3D11Asynchronous> *,void *,uint,uint)

- ea: `0x180160570`
- end: `0x18016069c`
- name: `??$GetData@$0A@$0A@@?$CAsynchronous@UID3D11Asynchronous@@@@SAJPEAVCContext@@PEAV0@PEAXII@Z`
- size: `300`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180118080`
- `0x180169da0`
- `0x18016ab80`

## callees

- `0x180160570`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801605c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801605c3`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18016066a`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18016066a`

## pseudocode

```c
__int64 __fastcall CAsynchronous<ID3D11Asynchronous>::GetData<0,0>(
        __int64 a1,
        _BYTE *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5)
{
  unsigned int v10; // eax
  int v11; // ebp
  __int64 v12; // rbx
  unsigned int v13; // r15d
  unsigned __int8 v15; // al
  __int16 v16; // [rsp+81h] [rbp+9h]
  char v17; // [rsp+83h] [rbp+Bh]

  if ( a2[272] )
    return 2289696769LL;
  do
  {
    v10 = a5 & 0xFFFFFFFE;
    if ( a2[273] != 0xFE )
      v10 = a5;
    a5 = v10;
    v11 = *(_DWORD *)(a1 + 3688);
    v12 = *(_QWORD *)(a1 + 3692);
    *(_DWORD *)(a1 + 3688) = GetCurrentThreadId();
    *(_BYTE *)(a1 + 3692) = 5;
    *(_WORD *)(a1 + 3693) = v16;
    *(_BYTE *)(a1 + 3695) = v17;
    *(_DWORD *)(a1 + 3696) = 0;
    (*(void (__fastcall **)(__int64, _BYTE *, __int64, _QWORD, unsigned int))(a1 + 1856))(
      a1 + 40768,
      a2 + 280,
      a3,
      a4,
      a5);
    v13 = *(_DWORD *)(a1 + 3696);
    if ( (a5 & 1) != 0 )
    {
      if ( v13 == 1 )
      {
        v15 = a2[273];
        if ( v15 < 0xFEu )
          a2[273] = v15 + 1;
      }
    }
    else
    {
      a2[273] = -1;
    }
    *(_DWORD *)(a1 + 3688) = v11;
    *(_QWORD *)(a1 + 3692) = v12;
  }
  while ( (a2[212] & 0x10) != 0 && v13 == 1 && !SleepEx(0, 0) );
  return v13;
}

```

## disassembly

```asm
0x180160570  push    rbx
0x180160572  push    rbp
0x180160573  push    rsi
0x180160574  push    rdi
0x180160575  push    r12
0x180160577  push    r13
0x180160579  push    r14
0x18016057b  push    r15
0x18016057d  sub     rsp, 38h
0x180160581  mov     r12d, r9d
0x180160584  mov     r13, r8
0x180160587  mov     rsi, rdx
0x18016058a  mov     rdi, rcx
0x18016058d  cmp     byte ptr [rdx+110h], 0
0x180160594  jnz     loc_180160695
0x18016059a  mov     r14d, [rsp+78h+arg_20]
0x1801605a2  mov     eax, r14d
0x1801605a5  and     eax, 0FFFFFFFEh
0x1801605a8  cmp     byte ptr [rsi+111h], 0FEh
0x1801605af  cmovnz  eax, r14d
0x1801605b3  mov     r14d, eax
0x1801605b6  mov     ebp, [rdi+0E68h]
0x1801605bc  mov     rbx, [rdi+0E6Ch]
0x1801605c3  call    cs:__imp_GetCurrentThreadId
0x1801605c9  mov     [rdi+0E68h], eax
0x1801605cf  mov     byte ptr [rdi+0E6Ch], 5
0x1801605d6  movzx   eax, [rsp+78h+arg_1]
0x1801605de  mov     [rdi+0E6Dh], ax
0x1801605e5  movzx   eax, [rsp+78h+arg_3]
0x1801605ed  mov     [rdi+0E6Fh], al
0x1801605f3  mov     dword ptr [rdi+0E70h], 0
0x1801605fd  mov     [rsp+78h+var_58], r14d
0x180160602  mov     r9d, r12d
0x180160605  mov     r8, r13
0x180160608  lea     rdx, [rsi+118h]
0x18016060f  lea     rcx, [rdi+9F40h]
0x180160616  mov     rax, [rdi+740h]
0x18016061d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180160622  mov     r15d, [rdi+0E70h]
0x180160629  test    r14b, 1
0x18016062d  jnz     short loc_18016067A
0x18016062f  mov     byte ptr [rsi+111h], 0FFh
0x180160636  mov     [rdi+0E68h], ebp
0x18016063c  mov     [rdi+0E6Ch], rbx
0x180160643  test    byte ptr [rsi+0D4h], 10h
0x18016064a  jnz     short loc_180160660
0x18016064c  mov     eax, r15d
0x18016064f  add     rsp, 38h
0x180160653  pop     r15
0x180160655  pop     r14
0x180160657  pop     r13
0x180160659  pop     r12
0x18016065b  pop     rdi
0x18016065c  pop     rsi
0x18016065d  pop     rbp
0x18016065e  pop     rbx
0x18016065f  retn
0x180160660  cmp     r15d, 1
0x180160664  jnz     short loc_18016064C
0x180160666  xor     edx, edx; bAlertable
0x180160668  xor     ecx, ecx; dwMilliseconds
0x18016066a  call    cs:__imp_SleepEx
0x180160670  test    eax, eax
0x180160672  jz      loc_1801605A2
0x180160678  jmp     short loc_18016064C
0x18016067a  cmp     r15d, 1
0x18016067e  jnz     short loc_180160636
0x180160680  movzx   eax, byte ptr [rsi+111h]
0x180160687  cmp     al, 0FEh
0x180160689  jnb     short loc_180160636
0x18016068b  inc     al
0x18016068d  mov     [rsi+111h], al
0x180160693  jmp     short loc_180160636
0x180160695  mov     eax, 887A0001h
0x18016069a  jmp     short loc_18016064F
```
