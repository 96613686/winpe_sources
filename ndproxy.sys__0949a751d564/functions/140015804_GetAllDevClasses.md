# GetAllDevClasses

- ea: `0x140015804`
- end: `0x140015915`
- name: `GetAllDevClasses`
- size: `273`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140012590`
- `0x1400130a0`

## callees

- `0x1400081c0`
- `0x140015804`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001582f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001585b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001582f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001585b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400158c8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400158f0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400158c8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400158f0`

## pseudocode

```c
void __fastcall GetAllDevClasses(__int64 a1, char *a2, unsigned int *a3)
{
  KSPIN_LOCK *v3; // r12
  unsigned int v6; // ebp
  _QWORD *v7; // r14
  _QWORD *v8; // rbx
  unsigned int v9; // r12d
  _QWORD *v10; // rsi
  char *v11; // r14
  __int64 v12; // rdx
  size_t v13; // r8
  __int64 v14; // rax
  unsigned int v15; // edx

  v3 = (KSPIN_LOCK *)(a1 + 624);
  v6 = 0;
  v7 = (_QWORD *)(a1 + 80);
  *(_BYTE *)(a1 + 632) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 624));
  v8 = (_QWORD *)*v7;
  if ( (_QWORD *)*v7 != v7 )
  {
    v9 = *a3;
    do
    {
      *((_BYTE *)v8 + 96) = KeAcquireSpinLockRaiseToDpc(v8 + 11);
      v10 = (_QWORD *)v8[5];
      if ( v10 != v8 + 5 )
      {
        v11 = a2;
        do
        {
          v12 = v10[6];
          v13 = *(unsigned int *)(v12 + 4);
          if ( v9 < v13 + 2 )
            break;
          memmove(v11, (const void *)(v12 + 8), v13);
          v14 = v10[6];
          v10 = (_QWORD *)*v10;
          v15 = *(_DWORD *)(v14 + 4) + 2;
          v6 += v15;
          v11 += v15;
          v9 -= v15;
        }
        while ( v10 != v8 + 5 );
        a2 = v11;
        v7 = (_QWORD *)(a1 + 80);
      }
      KeReleaseSpinLock(v8 + 11, *((_BYTE *)v8 + 96));
      v8 = (_QWORD *)*v8;
    }
    while ( v8 != v7 );
    v3 = (KSPIN_LOCK *)(a1 + 624);
  }
  KeReleaseSpinLock(v3, *(_BYTE *)(a1 + 632));
  *a3 = v6;
}

```

## disassembly

```asm
0x140015804  mov     [rsp+arg_10], rbx
0x140015809  mov     [rsp+arg_8], rdx
0x14001580e  push    rbp
0x14001580f  push    rsi
0x140015810  push    rdi
0x140015811  push    r12
0x140015813  push    r13
0x140015815  push    r14
0x140015817  push    r15
0x140015819  sub     rsp, 20h
0x14001581d  lea     r12, [rcx+270h]
0x140015824  mov     rdi, rcx
0x140015827  mov     rcx, r12; SpinLock
0x14001582a  mov     r15, r8
0x14001582d  xor     ebp, ebp
0x14001582f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015836  nop     dword ptr [rax+rax+00h]
0x14001583b  lea     r14, [rdi+50h]
0x14001583f  mov     [rdi+278h], al
0x140015845  mov     rbx, [r14]
0x140015848  mov     eax, [r15]
0x14001584b  cmp     rbx, r14
0x14001584e  jz      loc_1400158E7
0x140015854  mov     r12d, eax
0x140015857  lea     rcx, [rbx+58h]; SpinLock
0x14001585b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015862  nop     dword ptr [rax+rax+00h]
0x140015867  lea     r13, [rbx+28h]
0x14001586b  mov     [rbx+60h], al
0x14001586e  mov     rsi, [r13+0]
0x140015872  cmp     rsi, r13
0x140015875  jz      short loc_1400158C1
0x140015877  mov     r14, [rsp+58h+arg_8]
0x14001587c  mov     rdx, [rsi+30h]
0x140015880  mov     eax, r12d
0x140015883  mov     r8d, [rdx+4]; Size
0x140015887  lea     rcx, [r8+2]
0x14001588b  cmp     rax, rcx
0x14001588e  jb      short loc_1400158B8
0x140015890  add     rdx, 8; Src
0x140015894  mov     rcx, r14; void *
0x140015897  call    memmove
0x14001589c  mov     rax, [rsi+30h]
0x1400158a0  mov     rsi, [rsi]
0x1400158a3  mov     edx, [rax+4]
0x1400158a6  add     edx, 2
0x1400158a9  mov     eax, edx
0x1400158ab  add     ebp, edx
0x1400158ad  add     r14, rax
0x1400158b0  sub     r12d, edx
0x1400158b3  cmp     rsi, r13
0x1400158b6  jnz     short loc_14001587C
0x1400158b8  mov     [rsp+58h+arg_8], r14
0x1400158bd  lea     r14, [rdi+50h]
0x1400158c1  mov     dl, [rbx+60h]; NewIrql
0x1400158c4  lea     rcx, [rbx+58h]; SpinLock
0x1400158c8  call    cs:__imp_KeReleaseSpinLock
0x1400158cf  nop     dword ptr [rax+rax+00h]
0x1400158d4  mov     rbx, [rbx]
0x1400158d7  cmp     rbx, r14
0x1400158da  jnz     loc_140015857
0x1400158e0  lea     r12, [rdi+270h]
0x1400158e7  mov     dl, [rdi+278h]; NewIrql
0x1400158ed  mov     rcx, r12; SpinLock
0x1400158f0  call    cs:__imp_KeReleaseSpinLock
0x1400158f7  nop     dword ptr [rax+rax+00h]
0x1400158fc  mov     rbx, [rsp+58h+arg_10]
0x140015901  mov     [r15], ebp
0x140015904  add     rsp, 20h
0x140015908  pop     r15
0x14001590a  pop     r14
0x14001590c  pop     r13
0x14001590e  pop     r12
0x140015910  pop     rdi
0x140015911  pop     rsi
0x140015912  pop     rbp
0x140015913  retn
```
