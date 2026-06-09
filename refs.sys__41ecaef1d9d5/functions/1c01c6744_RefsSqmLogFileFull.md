# RefsSqmLogFileFull

- ea: `0x1c01c6744`
- end: `0x1c01c6a93`
- name: `RefsSqmLogFileFull`
- size: `847`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1c00588cc`

## callees

- `0x1c003c7c4`
- `0x1c0068960`
- `0x1c01c6228`
- `0x1c01c6744`

## import_xrefs

- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01c67ff`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01c67ff`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01c68d4`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01c68d4`
- `ntoskrnl!EtwWrite` at `0x1c01c6992`
- `ntoskrnl!EtwWrite` at `0x1c01c69f8`
- `ntoskrnl!EtwWrite` at `0x1c01c6a5e`
- `ntoskrnl!EtwWrite` at `0x1c01c6992`
- `ntoskrnl!EtwWrite` at `0x1c01c69f8`
- `ntoskrnl!EtwWrite` at `0x1c01c6a5e`

## pseudocode

```c
void __fastcall RefsSqmLogFileFull(int a1, __int64 a2)
{
  __int64 v3; // rbx
  char v4; // si
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rdx
  int v10; // ebx
  __int128 v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // [rsp+30h] [rbp-59h] BYREF
  int v16; // [rsp+34h] [rbp-55h] BYREF
  int v17; // [rsp+38h] [rbp-51h] BYREF
  __int64 v18; // [rsp+40h] [rbp-49h]
  __int128 v19; // [rsp+48h] [rbp-41h]
  _DWORD v20[6]; // [rsp+58h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-19h] BYREF
  __int64 *v22; // [rsp+80h] [rbp-9h]
  __int64 v23; // [rsp+88h] [rbp-1h]
  int *v24; // [rsp+90h] [rbp+7h]
  __int64 v25; // [rsp+98h] [rbp+Fh]
  int *v26; // [rsp+A0h] [rbp+17h]
  __int64 v27; // [rsp+A8h] [rbp+1Fh]

  v3 = 0;
  v4 = 0;
  if ( !qword_1C012E1C0 || !a2 )
    return;
  v5 = MEMORY[0xFFFFF78000000014];
  v6 = _InterlockedExchange64((volatile __int64 *)(a2 + 3344), MEMORY[0xFFFFF78000000014]);
  if ( !v6 )
    v6 = *(_QWORD *)(a2 + 3432);
  if ( v5 < v6 )
  {
    v7 = 0;
LABEL_8:
    v4 = 1;
    goto LABEL_9;
  }
  v3 = (v5 - v6 + 5000) / 10000;
  v7 = v3;
  if ( HIDWORD(v3) )
    goto LABEL_8;
LABEL_9:
  KeAcquireGuardedMutex(&SqmLffStats);
  if ( !v4 )
  {
    v8 = qword_1C012D798 + 1;
    v9 = v3 + qword_1C012D7A0;
    qword_1C012D798 = v8;
    qword_1C012D7A0 += v3;
    if ( v8 < 0 || v9 < 0 )
    {
      v8 = 1;
      v9 = v7;
      qword_1C012D798 = 1;
      xmmword_1C012D7B0 = 0;
      qword_1C012D7A0 = v7;
    }
    qword_1C012D7A8 = v9 / v8;
    if ( !(_QWORD)xmmword_1C012D7B0 || v7 > (__int64)xmmword_1C012D7B0 )
      *(_QWORD *)&xmmword_1C012D7B0 = v3;
    if ( !*((_QWORD *)&xmmword_1C012D7B0 + 1) || v7 < *((__int64 *)&xmmword_1C012D7B0 + 1) )
      *((_QWORD *)&xmmword_1C012D7B0 + 1) = v3;
  }
  v10 = qword_1C012D7A8;
  v11 = xmmword_1C012D7B0;
  v18 = qword_1C012D7A8;
  v19 = xmmword_1C012D7B0;
  KeReleaseGuardedMutex(&SqmLffStats);
  if ( !HIDWORD(v18) && !DWORD1(v19) && !HIDWORD(v19) )
  {
    if ( (unsigned __int8)RefsInstrumentThrottle(v12, 257) )
    {
      v20[0] = 1;
      v20[2] = a1;
      RefsSqmAddToStream(v14, v13, v20);
      UserData.Ptr = (ULONGLONG)&v15;
      v17 = v10;
      v15 = 5;
      v24 = &v16;
      v16 = 10684;
      v26 = &v17;
      *(_QWORD *)&UserData.Size = 4;
      v22 = qword_1C012D740;
      v23 = 16;
      v25 = 4;
      v27 = 4;
      EtwWrite(qword_1C012E1C0, &RefsSqmSetDword, 0, 4u, &UserData);
      UserData.Ptr = (ULONGLONG)&v15;
      v15 = 5;
      v24 = &v16;
      v16 = 10686;
      v26 = &v17;
      v17 = v11;
      *(_QWORD *)&UserData.Size = 4;
      v22 = qword_1C012D740;
      v23 = 16;
      v25 = 4;
      v27 = 4;
      EtwWrite(qword_1C012E1C0, &RefsSqmSetDword, 0, 4u, &UserData);
      UserData.Ptr = (ULONGLONG)&v15;
      v15 = 5;
      v24 = &v16;
      v16 = 10685;
      v26 = &v17;
      v17 = DWORD2(v11);
      *(_QWORD *)&UserData.Size = 4;
      v22 = qword_1C012D740;
      v23 = 16;
      v25 = 4;
      v27 = 4;
      EtwWrite(qword_1C012E1C0, &RefsSqmSetDword, 0, 4u, &UserData);
    }
  }
}

```

## disassembly

```asm
0x1c01c6744  mov     [rsp-8+arg_0], rbx
0x1c01c6749  mov     [rsp-8+arg_10], rsi
0x1c01c674e  push    rbp
0x1c01c674f  push    rdi
0x1c01c6750  push    r13
0x1c01c6752  push    r14
0x1c01c6754  push    r15
0x1c01c6756  lea     rbp, [rsp-37h]
0x1c01c675b  sub     rsp, 0C0h
0x1c01c6762  mov     rax, cs:__security_cookie
0x1c01c6769  xor     rax, rsp
0x1c01c676c  mov     [rbp+57h+var_30], rax
0x1c01c6770  xor     r15d, r15d
0x1c01c6773  mov     r14d, ecx
0x1c01c6776  cmp     cs:qword_1C012E1C0, r15
0x1c01c677d  mov     ebx, r15d
0x1c01c6780  mov     sil, r15b
0x1c01c6783  jz      loc_1C01C6A6A
0x1c01c6789  test    rdx, rdx
0x1c01c678c  jz      loc_1C01C6A6A
0x1c01c6792  mov     rcx, 0FFFFF78000000014h
0x1c01c679c  mov     rcx, [rcx]
0x1c01c679f  mov     rax, rcx
0x1c01c67a2  xchg    rax, [rdx+0D10h]
0x1c01c67a9  test    rax, rax
0x1c01c67ac  jnz     short loc_1C01C67B5
0x1c01c67ae  mov     rax, [rdx+0D68h]
0x1c01c67b5  cmp     rcx, rax
0x1c01c67b8  jge     short loc_1C01C67BF
0x1c01c67ba  mov     rdi, r15
0x1c01c67bd  jmp     short loc_1C01C67F5
0x1c01c67bf  sub     rcx, rax
0x1c01c67c2  mov     rax, 346DC5D63886594Bh
0x1c01c67cc  add     rcx, 1388h
0x1c01c67d3  imul    rcx
0x1c01c67d6  mov     rbx, rdx
0x1c01c67d9  sar     rbx, 0Bh
0x1c01c67dd  mov     rax, rbx
0x1c01c67e0  shr     rax, 3Fh
0x1c01c67e4  add     rbx, rax
0x1c01c67e7  mov     rax, rbx
0x1c01c67ea  mov     rdi, rbx
0x1c01c67ed  shr     rax, 20h
0x1c01c67f1  test    eax, eax
0x1c01c67f3  jz      short loc_1C01C67F8
0x1c01c67f5  mov     sil, 1
0x1c01c67f8  lea     rcx, SqmLffStats; Mutex
0x1c01c67ff  call    cs:__imp_KeAcquireGuardedMutex
0x1c01c6806  nop     dword ptr [rax+rax+00h]
0x1c01c680b  test    sil, sil
0x1c01c680e  jnz     loc_1C01C68AC
0x1c01c6814  mov     rcx, cs:qword_1C012D798
0x1c01c681b  mov     rdx, cs:qword_1C012D7A0
0x1c01c6822  inc     rcx
0x1c01c6825  add     rdx, rbx
0x1c01c6828  mov     cs:qword_1C012D798, rcx
0x1c01c682f  mov     rax, rcx
0x1c01c6832  mov     cs:qword_1C012D7A0, rdx
0x1c01c6839  sar     rax, 20h
0x1c01c683d  test    eax, eax
0x1c01c683f  js      short loc_1C01C684C
0x1c01c6841  mov     rax, rdx
0x1c01c6844  sar     rax, 20h
0x1c01c6848  test    eax, eax
0x1c01c684a  jns     short loc_1C01C686D
0x1c01c684c  mov     ecx, 1
0x1c01c6851  xorps   xmm0, xmm0
0x1c01c6854  mov     rdx, rdi
0x1c01c6857  mov     cs:qword_1C012D798, rcx
0x1c01c685e  movdqu  cs:xmmword_1C012D7B0, xmm0
0x1c01c6866  mov     cs:qword_1C012D7A0, rdx
0x1c01c686d  mov     rax, rdx
0x1c01c6870  cqo
0x1c01c6872  idiv    rcx
0x1c01c6875  mov     cs:qword_1C012D7A8, rax
0x1c01c687c  mov     rax, qword ptr cs:xmmword_1C012D7B0
0x1c01c6883  test    rax, rax
0x1c01c6886  jz      short loc_1C01C688D
0x1c01c6888  cmp     rdi, rax
0x1c01c688b  jle     short loc_1C01C6894
0x1c01c688d  mov     qword ptr cs:xmmword_1C012D7B0, rbx
0x1c01c6894  mov     rax, qword ptr cs:xmmword_1C012D7B0+8
0x1c01c689b  test    rax, rax
0x1c01c689e  jz      short loc_1C01C68A5
0x1c01c68a0  cmp     rdi, rax
0x1c01c68a3  jge     short loc_1C01C68AC
0x1c01c68a5  mov     qword ptr cs:xmmword_1C012D7B0+8, rbx
0x1c01c68ac  mov     rbx, cs:qword_1C012D7A8
0x1c01c68b3  lea     rcx, SqmLffStats; Mutex
0x1c01c68ba  mov     rdi, qword ptr cs:xmmword_1C012D7B0
0x1c01c68c1  mov     rsi, qword ptr cs:xmmword_1C012D7B0+8
0x1c01c68c8  mov     [rbp+57h+var_A0], rbx
0x1c01c68cc  mov     qword ptr [rbp+57h+var_98], rdi
0x1c01c68d0  mov     qword ptr [rbp+57h+var_98+8], rsi
0x1c01c68d4  call    cs:__imp_KeReleaseGuardedMutex
0x1c01c68db  nop     dword ptr [rax+rax+00h]
0x1c01c68e0  cmp     dword ptr [rbp+57h+var_A0+4], r15d
0x1c01c68e4  jnz     loc_1C01C6A6A
0x1c01c68ea  cmp     dword ptr [rbp+57h+var_98+4], r15d
0x1c01c68ee  jnz     loc_1C01C6A6A
0x1c01c68f4  cmp     dword ptr [rbp+57h+var_98+0Ch], r15d
0x1c01c68f8  jnz     loc_1C01C6A6A
0x1c01c68fe  mov     edx, 101h
0x1c01c6903  call    RefsInstrumentThrottle
0x1c01c6908  test    al, al
0x1c01c690a  jz      loc_1C01C6A6A
0x1c01c6910  lea     r8, [rbp+57h+var_88]
0x1c01c6914  mov     [rbp+57h+var_88], 1
0x1c01c691b  mov     [rbp+57h+var_80], r14d
0x1c01c691f  call    RefsSqmAddToStream
0x1c01c6924  mov     rcx, cs:qword_1C012E1C0; RegHandle
0x1c01c692b  lea     rax, [rbp+57h+var_B0]
0x1c01c692f  mov     [rbp+57h+var_70.Ptr], rax
0x1c01c6933  lea     r15, qword_1C012D740
0x1c01c693a  mov     r13d, 4
0x1c01c6940  mov     [rbp+57h+var_A8], ebx
0x1c01c6943  lea     rax, [rbp+57h+var_AC]
0x1c01c6947  mov     [rbp+57h+var_B0], 5
0x1c01c694e  mov     [rbp+57h+var_50], rax
0x1c01c6952  lea     rbx, RefsSqmSetDword
0x1c01c6959  lea     rax, [rbp+57h+var_A8]
0x1c01c695d  mov     [rbp+57h+var_AC], 29BCh
0x1c01c6964  mov     [rbp+57h+var_40], rax
0x1c01c6968  mov     r9d, r13d; UserDataCount
0x1c01c696b  lea     rax, [rbp+57h+var_70]
0x1c01c696f  mov     qword ptr [rbp+57h+var_70.Size], r13
0x1c01c6973  xor     r8d, r8d; ActivityId
0x1c01c6976  mov     [rsp+0E0h+UserData], rax; UserData
0x1c01c697b  mov     rdx, rbx; EventDescriptor
0x1c01c697e  mov     [rbp+57h+var_60], r15
0x1c01c6982  mov     [rbp+57h+var_58], 10h
0x1c01c698a  mov     [rbp+57h+var_48], r13
0x1c01c698e  mov     [rbp+57h+var_38], r13
0x1c01c6992  call    cs:__imp_EtwWrite
0x1c01c6999  nop     dword ptr [rax+rax+00h]
0x1c01c699e  mov     rcx, cs:qword_1C012E1C0; RegHandle
0x1c01c69a5  lea     rax, [rbp+57h+var_B0]
0x1c01c69a9  mov     [rbp+57h+var_70.Ptr], rax
0x1c01c69ad  mov     r9d, r13d; UserDataCount
0x1c01c69b0  lea     rax, [rbp+57h+var_AC]
0x1c01c69b4  mov     [rbp+57h+var_B0], 5
0x1c01c69bb  mov     [rbp+57h+var_50], rax
0x1c01c69bf  xor     r8d, r8d; ActivityId
0x1c01c69c2  lea     rax, [rbp+57h+var_A8]
0x1c01c69c6  mov     [rbp+57h+var_AC], 29BEh
0x1c01c69cd  mov     [rbp+57h+var_40], rax
0x1c01c69d1  mov     rdx, rbx; EventDescriptor
0x1c01c69d4  lea     rax, [rbp+57h+var_70]
0x1c01c69d8  mov     [rbp+57h+var_A8], edi
0x1c01c69db  mov     [rsp+0E0h+UserData], rax; UserData
0x1c01c69e0  mov     qword ptr [rbp+57h+var_70.Size], r13
0x1c01c69e4  mov     [rbp+57h+var_60], r15
0x1c01c69e8  mov     [rbp+57h+var_58], 10h
0x1c01c69f0  mov     [rbp+57h+var_48], r13
0x1c01c69f4  mov     [rbp+57h+var_38], r13
0x1c01c69f8  call    cs:__imp_EtwWrite
0x1c01c69ff  nop     dword ptr [rax+rax+00h]
0x1c01c6a04  mov     rcx, cs:qword_1C012E1C0; RegHandle
0x1c01c6a0b  lea     rax, [rbp+57h+var_B0]
0x1c01c6a0f  mov     [rbp+57h+var_70.Ptr], rax
0x1c01c6a13  mov     r9d, r13d; UserDataCount
0x1c01c6a16  lea     rax, [rbp+57h+var_AC]
0x1c01c6a1a  mov     [rbp+57h+var_B0], 5
0x1c01c6a21  mov     [rbp+57h+var_50], rax
0x1c01c6a25  xor     r8d, r8d; ActivityId
0x1c01c6a28  lea     rax, [rbp+57h+var_A8]
0x1c01c6a2c  mov     [rbp+57h+var_AC], 29BDh
0x1c01c6a33  mov     [rbp+57h+var_40], rax
0x1c01c6a37  mov     rdx, rbx; EventDescriptor
0x1c01c6a3a  lea     rax, [rbp+57h+var_70]
0x1c01c6a3e  mov     [rbp+57h+var_A8], esi
0x1c01c6a41  mov     [rsp+0E0h+UserData], rax; UserData
0x1c01c6a46  mov     qword ptr [rbp+57h+var_70.Size], r13
0x1c01c6a4a  mov     [rbp+57h+var_60], r15
0x1c01c6a4e  mov     [rbp+57h+var_58], 10h
0x1c01c6a56  mov     [rbp+57h+var_48], r13
0x1c01c6a5a  mov     [rbp+57h+var_38], r13
0x1c01c6a5e  call    cs:__imp_EtwWrite
0x1c01c6a65  nop     dword ptr [rax+rax+00h]
0x1c01c6a6a  mov     rcx, [rbp+57h+var_30]
0x1c01c6a6e  xor     rcx, rsp; StackCookie
0x1c01c6a71  call    __security_check_cookie
0x1c01c6a76  lea     r11, [rsp+0E0h+var_20]
0x1c01c6a7e  mov     rbx, [r11+30h]
0x1c01c6a82  mov     rsi, [r11+40h]
0x1c01c6a86  mov     rsp, r11
0x1c01c6a89  pop     r15
0x1c01c6a8b  pop     r14
0x1c01c6a8d  pop     r13
0x1c01c6a8f  pop     rdi
0x1c01c6a90  pop     rbp
0x1c01c6a91  retn
```
