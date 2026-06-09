# QuicRetryTokenDecrypt

- ea: `0x1400424d4`
- end: `0x140042647`
- name: `QuicRetryTokenDecrypt`
- size: `371`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140015b70`
- `0x14002a048`

## callees

- `0x14002d468`
- `0x14003455c`
- `0x14003c8e0`
- `0x14003cb00`
- `0x1400424d4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400425ad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400425ad`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400425d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042613`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400425d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042613`

## pseudocode

```c
bool __fastcall QuicRetryTokenDecrypt(__int64 a1, _OWORD *a2, __int64 a3)
{
  KSPIN_LOCK *v4; // rdi
  unsigned __int8 v5; // r8
  unsigned __int8 v6; // r10
  __int64 *v7; // rcx
  char *v8; // r9
  int v9; // ecx
  unsigned __int8 v10; // kr00_1
  char v11; // al
  const void *v12; // rdx
  void *StatelessRetryKeyForTimestamp; // rcx
  int v15; // ebx
  __int64 v16; // [rsp+30h] [rbp-48h] BYREF
  int v17; // [rsp+38h] [rbp-40h]

  v4 = (KSPIN_LOCK *)((char *)Val + 2496 * *(unsigned __int16 *)(a1 + 26));
  *(_OWORD *)a3 = *a2;
  *(_OWORD *)(a3 + 16) = a2[1];
  *(_OWORD *)(a3 + 32) = a2[2];
  *(_OWORD *)(a3 + 48) = a2[3];
  *(_OWORD *)(a3 + 64) = a2[4];
  v5 = 12;
  v6 = byte_14005C562;
  if ( (unsigned __int8)byte_14005C562 < 0xCu )
  {
    v12 = *(const void **)(a1 + 64);
    v16 = 0;
    v17 = 0;
    memmove(&v16, v12, (unsigned __int8)byte_14005C562);
  }
  else
  {
    v7 = *(__int64 **)(a1 + 64);
    v16 = *v7;
    v17 = *((_DWORD *)v7 + 2);
    if ( (unsigned __int8)byte_14005C562 > 0xCu )
    {
      v8 = (char *)v7 + 12;
      do
      {
        v9 = v5;
        v10 = v5++;
        v11 = *v8++;
        *((_BYTE *)&v16 + (int)(v9 - 12 * (v10 / 0xCu))) ^= v11;
      }
      while ( v5 < v6 );
    }
  }
  *((_BYTE *)v4 + 56) = KeAcquireSpinLockRaiseToDpc(v4 + 6);
  StatelessRetryKeyForTimestamp = (void *)QuicPartitionGetStatelessRetryKeyForTimestamp(v4, *(_QWORD *)a3 >> 1);
  if ( StatelessRetryKeyForTimestamp )
  {
    v15 = CxPlatDecrypt(StatelessRetryKeyForTimestamp, 68, (PUCHAR)(a3 + 8));
    KeReleaseSpinLock(v4 + 6, *((_BYTE *)v4 + 56));
    return v15 >= 0;
  }
  else
  {
    KeReleaseSpinLock(v4 + 6, *((_BYTE *)v4 + 56));
    return 0;
  }
}

```

## disassembly

```asm
0x1400424d4  mov     [rsp+arg_8], rbx
0x1400424d9  mov     [rsp+arg_18], rsi
0x1400424de  push    rdi
0x1400424df  sub     rsp, 70h
0x1400424e3  mov     rax, cs:__security_cookie
0x1400424ea  xor     rax, rsp
0x1400424ed  mov     [rsp+78h+var_18], rax
0x1400424f2  movzx   eax, word ptr [rcx+1Ah]
0x1400424f6  mov     rbx, r8
0x1400424f9  movups  xmm0, xmmword ptr [rdx]
0x1400424fc  imul    rdi, rax, 9C0h
0x140042503  add     rdi, cs:Val
0x14004250a  movaps  xmmword ptr [r8], xmm0
0x14004250e  movups  xmm1, xmmword ptr [rdx+10h]
0x140042512  movaps  xmmword ptr [r8+10h], xmm1
0x140042517  movups  xmm0, xmmword ptr [rdx+20h]
0x14004251b  movaps  xmmword ptr [r8+20h], xmm0
0x140042520  movups  xmm1, xmmword ptr [rdx+30h]
0x140042524  movaps  xmmword ptr [r8+30h], xmm1
0x140042529  movups  xmm0, xmmword ptr [rdx+40h]
0x14004252d  movaps  xmmword ptr [r8+40h], xmm0
0x140042532  mov     r8b, 0Ch
0x140042535  movzx   r10d, cs:byte_14005C562
0x14004253d  cmp     r10b, r8b
0x140042540  jb      short loc_14004258A
0x140042542  mov     rcx, [rcx+40h]
0x140042546  movsd   xmm0, qword ptr [rcx]
0x14004254a  movsd   [rsp+78h+var_48], xmm0
0x140042550  mov     eax, [rcx+8]
0x140042553  mov     [rsp+78h+var_40], eax
0x140042557  jbe     short loc_1400425A6
0x140042559  lea     r9, [rcx+0Ch]
0x14004255d  movzx   ecx, r8b
0x140042561  mov     eax, 0AAAAAAABh
0x140042566  mul     ecx
0x140042568  inc     r8b
0x14004256b  shr     edx, 3
0x14004256e  lea     eax, [rdx+rdx*2]
0x140042571  shl     eax, 2
0x140042574  sub     ecx, eax
0x140042576  mov     al, [r9]
0x140042579  movsxd  rcx, ecx
0x14004257c  inc     r9
0x14004257f  xor     byte ptr [rsp+rcx+78h+var_48], al
0x140042583  cmp     r8b, r10b
0x140042586  jb      short loc_14004255D
0x140042588  jmp     short loc_1400425A6
0x14004258a  mov     rdx, [rcx+40h]; Src
0x14004258e  xor     eax, eax
0x140042590  lea     rcx, [rsp+78h+var_48]; void *
0x140042595  mov     [rsp+78h+var_48], rax
0x14004259a  mov     r8, r10; Size
0x14004259d  mov     [rsp+78h+var_40], eax
0x1400425a1  call    memmove
0x1400425a6  lea     rsi, [rdi+30h]
0x1400425aa  mov     rcx, rsi; SpinLock
0x1400425ad  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400425b4  nop     dword ptr [rax+rax+00h]
0x1400425b9  mov     [rdi+38h], al
0x1400425bc  mov     rcx, rdi
0x1400425bf  mov     rdx, [rbx]
0x1400425c2  shr     rdx, 1
0x1400425c5  call    QuicPartitionGetStatelessRetryKeyForTimestamp
0x1400425ca  mov     rcx, rax; hKey
0x1400425cd  test    rax, rax
0x1400425d0  jnz     short loc_1400425E8
0x1400425d2  mov     dl, [rdi+38h]; NewIrql
0x1400425d5  mov     rcx, rsi; SpinLock
0x1400425d8  call    cs:__imp_KeReleaseSpinLock
0x1400425df  nop     dword ptr [rax+rax+00h]
0x1400425e4  xor     al, al
0x1400425e6  jmp     short loc_140042627
0x1400425e8  lea     rax, [rbx+8]
0x1400425ec  mov     r8d, 8
0x1400425f2  mov     [rsp+78h+pbInput], rax; pbInput
0x1400425f7  lea     rdx, [rsp+78h+var_48]
0x1400425fc  mov     r9, rbx
0x1400425ff  mov     [rsp+78h+var_58], 44h ; 'D'; __int16
0x140042606  call    CxPlatDecrypt
0x14004260b  mov     dl, [rdi+38h]; NewIrql
0x14004260e  mov     rcx, rsi; SpinLock
0x140042611  mov     ebx, eax
0x140042613  call    cs:__imp_KeReleaseSpinLock
0x14004261a  nop     dword ptr [rax+rax+00h]
0x14004261f  shr     ebx, 1Fh
0x140042622  xor     bl, 1
0x140042625  mov     al, bl
0x140042627  mov     rcx, [rsp+78h+var_18]
0x14004262c  xor     rcx, rsp; StackCookie
0x14004262f  call    __security_check_cookie
0x140042634  lea     r11, [rsp+78h+var_8]
0x140042639  mov     rbx, [r11+18h]
0x14004263d  mov     rsi, [r11+28h]
0x140042641  mov     rsp, r11
0x140042644  pop     rdi
0x140042645  retn
```
