# InsertNegativeCacheEntry

- ea: `0x140020884`
- end: `0x1400209a7`
- name: `InsertNegativeCacheEntry`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x140004530`

## callees

- `0x140003bd0`
- `0x140005c90`
- `0x140008140`
- `0x140008a50`
- `0x14000c370`
- `0x1400204c0`
- `0x140020884`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140020911`
- `ntoskrnl!KeReleaseMutex` at `0x140020969`
- `ntoskrnl!KeReleaseMutex` at `0x140020911`
- `ntoskrnl!KeReleaseMutex` at `0x140020969`

## pseudocode

```c
void __fastcall InsertNegativeCacheEntry(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const UNICODE_STRING *a4,
        const UNICODE_STRING *a5)
{
  __int64 *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rbx
  struct _UNICODE_STRING *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8

  if ( a2 && a3 && a4 && a5 && a4->Length )
  {
    v8 = HacQueryAndReference(*(PRKMUTEX *)(a2 + 72), a4);
    v11 = (__int64)v8;
    if ( v8 )
    {
      HacUpdateTimeStamp((__int64)v8, v9, v10);
    }
    else
    {
      HacAcquireLock(a3, v9, v10);
      v12 = HacAllocate(a1, *(_QWORD *)(a2 + 72), (const UNICODE_STRING *)(a3 + 64), a5);
      v11 = (__int64)v12;
      if ( !v12 )
      {
        KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
        return;
      }
      v12[3].Length |= 8u;
      LODWORD(v12[6].Buffer) = *(_DWORD *)(a3 + 136);
      HIDWORD(v12[6].Buffer) = *(_DWORD *)(a3 + 200);
      *(_DWORD *)&v12[7].Length = *(_DWORD *)(a3 + 204);
      memset(&v12[8], 0, 0x58u);
      memset((void *)(v11 + 216), 0, 0x44u);
      KeReleaseMutex(*(PRKMUTEX *)(a3 + 40), 0);
      HacUpdateTimeStamp(v11, v13, v14);
      HacInsertEntry(a1, v11);
    }
    HacDereference(a1, v11);
  }
}

```

## disassembly

```asm
0x140020884  test    rdx, rdx
0x140020887  jz      locret_1400209A5
0x14002088d  push    rbx
0x14002088e  push    rbp
0x14002088f  push    rsi
0x140020890  push    rdi
0x140020891  sub     rsp, 38h
0x140020895  mov     rdi, r8
0x140020898  mov     rsi, rdx
0x14002089b  mov     rbp, rcx
0x14002089e  test    r8, r8
0x1400208a1  jz      loc_14002099D
0x1400208a7  test    r9, r9
0x1400208aa  jz      loc_14002099D
0x1400208b0  cmp     [rsp+58h+arg_20], 0
0x1400208b9  jz      loc_14002099D
0x1400208bf  xor     eax, eax
0x1400208c1  cmp     ax, [r9]
0x1400208c5  jz      loc_14002099D
0x1400208cb  mov     rcx, [rsi+48h]; Mutex
0x1400208cf  mov     rdx, r9; String2
0x1400208d2  call    HacQueryAndReference
0x1400208d7  mov     rbx, rax
0x1400208da  test    rax, rax
0x1400208dd  jnz     loc_14002098A
0x1400208e3  mov     rcx, rdi
0x1400208e6  call    HacAcquireLock
0x1400208eb  mov     r9, [rsp+58h+arg_20]
0x1400208f3  lea     r8, [rdi+40h]
0x1400208f7  mov     rdx, [rsi+48h]
0x1400208fb  mov     rcx, rbp
0x1400208fe  call    HacAllocate
0x140020903  xor     edx, edx; Val
0x140020905  mov     rbx, rax
0x140020908  test    rax, rax
0x14002090b  jnz     short loc_14002091F
0x14002090d  mov     rcx, [rdi+28h]; Mutex
0x140020911  call    cs:__imp_KeReleaseMutex
0x140020918  nop     dword ptr [rax+rax+00h]
0x14002091d  jmp     short loc_14002099D
0x14002091f  or      word ptr [rax+30h], 8
0x140020924  lea     rcx, [rbx+80h]; void *
0x14002092b  mov     eax, [rdi+88h]
0x140020931  mov     r8d, 58h ; 'X'; Size
0x140020937  mov     [rbx+68h], eax
0x14002093a  mov     eax, [rdi+0C8h]
0x140020940  mov     [rbx+6Ch], eax
0x140020943  mov     eax, [rdi+0CCh]
0x140020949  mov     [rbx+70h], eax
0x14002094c  call    memset
0x140020951  xor     edx, edx; Val
0x140020953  lea     rcx, [rbx+0D8h]; void *
0x14002095a  lea     r8d, [rdx+44h]; Size
0x14002095e  call    memset
0x140020963  mov     rcx, [rdi+28h]; Mutex
0x140020967  xor     edx, edx; Wait
0x140020969  call    cs:__imp_KeReleaseMutex
0x140020970  nop     dword ptr [rax+rax+00h]
0x140020975  mov     rcx, rbx
0x140020978  call    HacUpdateTimeStamp
0x14002097d  mov     rdx, rbx
0x140020980  mov     rcx, rbp
0x140020983  call    HacInsertEntry
0x140020988  jmp     short loc_140020992
0x14002098a  mov     rcx, rax
0x14002098d  call    HacUpdateTimeStamp
0x140020992  mov     rdx, rbx
0x140020995  mov     rcx, rbp
0x140020998  call    HacDereference
0x14002099d  add     rsp, 38h
0x1400209a1  pop     rdi
0x1400209a2  pop     rsi
0x1400209a3  pop     rbp
0x1400209a4  pop     rbx
0x1400209a5  retn
```
