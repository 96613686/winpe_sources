# vdbeSorterCreateThread

- ea: `0x140096528`
- end: `0x140096603`
- name: `vdbeSorterCreateThread`
- size: `219`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1400951b8`
- `0x14009599c`
- `0x1400966c4`
- `0x140096dd8`

## callees

- `0x140062c2c`
- `0x140096528`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1400965ac`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1400965ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400965da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400965da`

## pseudocode

```c
__int64 __fastcall vdbeSorterCreateThread(__int64 **a1, __int64 (__fastcall *a2)(__int64), __int64 a3)
{
  __int64 *v6; // rbx
  DWORD *v8; // rsi
  _QWORD *v9; // rdi
  __int64 v10; // rax

  *a1 = 0;
  v6 = (__int64 *)sqlite3Malloc(40);
  if ( !v6 )
    return 7;
  if ( !(_BYTE)word_1400C84B4 || qword_1400C8640 && (unsigned int)qword_1400C8640(200) )
  {
    v9 = v6 + 2;
    v8 = (DWORD *)(v6 + 1);
  }
  else
  {
    v8 = (DWORD *)(v6 + 1);
    v6[3] = a3;
    v9 = v6 + 2;
    v6[2] = (__int64)a2;
    v10 = _o__beginthreadex(0, 0, sqlite3ThreadProc, v6, 0, v6 + 1);
    *v6 = v10;
    if ( v10 )
      goto LABEL_10;
  }
  *(_OWORD *)v6 = 0;
  *((_OWORD *)v6 + 1) = 0;
  v6[4] = 0;
LABEL_10:
  if ( !*v9 )
  {
    *v8 = GetCurrentThreadId();
    v6[4] = a2(a3);
  }
  *a1 = v6;
  return 0;
}

```

## disassembly

```asm
0x140096528  push    rbx
0x14009652a  push    rbp
0x14009652b  push    rsi
0x14009652c  push    rdi
0x14009652d  push    r14
0x14009652f  push    r15
0x140096531  sub     rsp, 38h
0x140096535  mov     r14, rcx
0x140096538  mov     qword ptr [rcx], 0
0x14009653f  mov     ecx, 28h ; '('
0x140096544  mov     rbp, r8
0x140096547  mov     r15, rdx
0x14009654a  call    sqlite3Malloc
0x14009654f  mov     rbx, rax
0x140096552  test    rax, rax
0x140096555  jnz     short loc_14009655F
0x140096557  lea     eax, [rbx+7]
0x14009655a  jmp     loc_1400965F6
0x14009655f  cmp     byte ptr cs:word_1400C84B4, 0
0x140096566  jz      short loc_1400965BC
0x140096568  mov     rax, cs:qword_1400C8640
0x14009656f  test    rax, rax
0x140096572  jz      short loc_140096582
0x140096574  mov     ecx, 0C8h
0x140096579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009657e  test    eax, eax
0x140096580  jnz     short loc_1400965BC
0x140096582  lea     rsi, [rbx+8]
0x140096586  mov     [rbx+18h], rbp
0x14009658a  lea     rdi, [rbx+10h]
0x14009658e  mov     [rsp+68h+var_40], rsi
0x140096593  mov     r9, rbx
0x140096596  mov     [rsp+68h+var_48], 0
0x14009659e  lea     r8, sqlite3ThreadProc
0x1400965a5  mov     [rdi], r15
0x1400965a8  xor     edx, edx
0x1400965aa  xor     ecx, ecx
0x1400965ac  call    cs:__imp__o__beginthreadex
0x1400965b2  mov     [rbx], rax
0x1400965b5  test    rax, rax
0x1400965b8  jz      short loc_1400965C4
0x1400965ba  jmp     short loc_1400965D4
0x1400965bc  lea     rdi, [rbx+10h]
0x1400965c0  lea     rsi, [rbx+8]
0x1400965c4  xorps   xmm0, xmm0
0x1400965c7  xor     eax, eax
0x1400965c9  movups  xmmword ptr [rbx], xmm0
0x1400965cc  movups  xmmword ptr [rbx+10h], xmm0
0x1400965d0  mov     [rbx+20h], rax
0x1400965d4  cmp     qword ptr [rdi], 0
0x1400965d8  jnz     short loc_1400965F1
0x1400965da  call    cs:__imp_GetCurrentThreadId
0x1400965e0  mov     [rsi], eax
0x1400965e2  mov     rcx, rbp
0x1400965e5  mov     rax, r15
0x1400965e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400965ed  mov     [rbx+20h], rax
0x1400965f1  mov     [r14], rbx
0x1400965f4  xor     eax, eax
0x1400965f6  add     rsp, 38h
0x1400965fa  pop     r15
0x1400965fc  pop     r14
0x1400965fe  pop     rdi
0x1400965ff  pop     rsi
0x140096600  pop     rbp
0x140096601  pop     rbx
0x140096602  retn
```
