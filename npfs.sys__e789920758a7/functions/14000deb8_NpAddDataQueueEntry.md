# NpAddDataQueueEntry

- ea: `0x14000deb8`
- end: `0x14000e1a9`
- name: `NpAddDataQueueEntry`
- size: `753`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, int, size_t Size, __int64, void *Src, int)`
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000b54c`
- `0x14000c800`
- `0x14000ca2c`
- `0x14000cff8`
- `0x14000db40`
- `0x14000e490`
- `0x140010890`

## callees

- `0x140001520`
- `0x140001ad4`
- `0x140001e40`
- `0x14000deb8`
- `0x14000fb00`
- `0x140013d70`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000df50`
- `ntoskrnl!ExAllocatePool2` at `0x14000e006`
- `ntoskrnl!ExAllocatePool2` at `0x14000df50`
- `ntoskrnl!ExAllocatePool2` at `0x14000e006`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e178`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e178`
- `ntoskrnl!ExGetPreviousMode` at `0x14000e077`
- `ntoskrnl!ExGetPreviousMode` at `0x14000e077`

## pseudocode

```c
__int64 __fastcall NpAddDataQueueEntry(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        size_t Size,
        __int64 a7,
        void *Src,
        int a9)
{
  struct _KTHREAD *v11; // r8
  __int64 result; // rax
  _QWORD *Pool2; // rbx
  unsigned int v14; // r14d
  _DWORD *v15; // r15
  unsigned int v16; // ecx
  unsigned int v17; // ebx
  unsigned int v18; // r13d
  int v19; // r14d
  void *v20; // rdx
  KPROCESSOR_MODE PreviousMode; // al
  void *v22; // rcx
  _QWORD *v23; // rax
  PVOID v24; // [rsp+28h] [rbp-40h] BYREF
  PVOID P; // [rsp+30h] [rbp-38h]

  v24 = 0;
  if ( a5 != 2 && a4 == 1 )
  {
    v11 = a7 ? *(struct _KTHREAD **)(a7 + 152) : KeGetCurrentThread();
    result = NpGetClientSecurityContext(a1, a2, v11, &v24);
    if ( (int)result < 0 )
      return result;
  }
  if ( !a5 )
  {
    v16 = 48;
    if ( a4 )
    {
      v16 = Size + 48;
      if ( (int)Size + 48 < (unsigned int)Size )
      {
        v17 = -1073741811;
LABEL_26:
        NpFreeClientSecurityContext(v24);
        return v17;
      }
    }
    v15 = (_DWORD *)(a3 + 32);
    v18 = *(_DWORD *)(a3 + 28) - *(_DWORD *)(a3 + 32);
    v19 = Size - a9;
    if ( v18 < (int)Size - a9 )
      v19 = *(_DWORD *)(a3 + 28) - *(_DWORD *)(a3 + 32);
    if ( v16 == 48 && _interlockedbittestandreset((volatile signed __int32 *)(a3 + 40), 0) )
      Pool2 = *(_QWORD **)(a3 + 40);
    else
      Pool2 = 0;
    P = Pool2;
    if ( Pool2 || (Pool2 = (_QWORD *)ExAllocatePool2(65, v16, 1917218894), (P = Pool2) != 0) )
    {
      *((_DWORD *)Pool2 + 9) = v19;
      Pool2[2] = a7;
      *((_DWORD *)Pool2 + 8) = 0;
      Pool2[3] = v24;
      *((_DWORD *)Pool2 + 10) = Size;
      if ( !a4 )
        goto LABEL_28;
      if ( a7 )
      {
        v20 = *(void **)(a7 + 112);
        PreviousMode = *(_BYTE *)(a7 + 64);
      }
      else
      {
        PreviousMode = ExGetPreviousMode();
        v20 = Src;
      }
      v22 = Pool2 + 6;
      if ( PreviousMode )
        RtlCopyFromUser(v22, v20, (unsigned int)Size);
      else
        RtlCopyVolatileMemory(v22, v20, (unsigned int)Size);
      if ( v18 < (int)Size - a9 && a7 )
      {
LABEL_28:
        v14 = 259;
      }
      else
      {
        Pool2[2] = 0;
        v14 = 0;
      }
      goto LABEL_38;
    }
LABEL_25:
    v17 = -1073741670;
    goto LABEL_26;
  }
  if ( _interlockedbittestandreset((volatile signed __int32 *)(a3 + 40), 0) )
    Pool2 = *(_QWORD **)(a3 + 40);
  else
    Pool2 = 0;
  if ( !Pool2 )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(65, 48, 1917218894);
    if ( !Pool2 )
      goto LABEL_25;
  }
  *((_DWORD *)Pool2 + 8) = a5;
  *((_DWORD *)Pool2 + 9) = 0;
  Pool2[2] = a7;
  *((_DWORD *)Pool2 + 10) = Size;
  Pool2[3] = v24;
  v14 = 259;
  v15 = (_DWORD *)(a3 + 32);
LABEL_38:
  *v15 += *((_DWORD *)Pool2 + 9);
  *(_DWORD *)(a3 + 16) = a4;
  *(_DWORD *)(a3 + 20) += *((_DWORD *)Pool2 + 10);
  ++*(_DWORD *)(a3 + 24);
  if ( a9 )
    *(_DWORD *)(a3 + 36) = a9;
  v23 = *(_QWORD **)(a3 + 8);
  if ( *v23 != a3 )
    __fastfail(3u);
  *Pool2 = a3;
  Pool2[1] = v23;
  *v23 = Pool2;
  *(_QWORD *)(a3 + 8) = Pool2;
  if ( v14 == 259 )
  {
    *(_BYTE *)(*(_QWORD *)(a7 + 184) + 3LL) |= 1u;
    *(_QWORD *)(a7 + 136) = a3;
    *(_QWORD *)(a7 + 144) = Pool2;
    _InterlockedExchange64((volatile __int64 *)(a7 + 104), (__int64)NpCancelDataQueueIrp);
    if ( *(_BYTE *)(a7 + 68) )
    {
      if ( _InterlockedExchange64((volatile __int64 *)(a7 + 104), 0) )
        NpCancelDataQueueIrp(0, a7);
    }
  }
  return v14;
}

```

## disassembly

```asm
0x14000deb8  mov     rax, rsp
0x14000debb  mov     [rax+8], rbx
0x14000debf  mov     [rax+10h], rsi
0x14000dec3  mov     [rax+20h], r9d
0x14000dec7  mov     [rax+18h], r8
0x14000decb  push    rdi
0x14000decc  push    r12
0x14000dece  push    r13
0x14000ded0  push    r14
0x14000ded2  push    r15
0x14000ded4  sub     rsp, 40h
0x14000ded8  mov     ebx, r9d
0x14000dedb  mov     rsi, r8
0x14000dede  mov     qword ptr [rax-40h], 0
0x14000dee6  mov     r14d, [rsp+68h+arg_20]
0x14000deee  mov     rdi, [rsp+68h+arg_30]
0x14000def6  cmp     r14d, 2
0x14000defa  jz      short loc_14000DF2A
0x14000defc  cmp     ebx, 1
0x14000deff  jnz     short loc_14000DF2A
0x14000df01  test    rdi, rdi
0x14000df04  jz      short loc_14000DF0F
0x14000df06  mov     r8, [rdi+98h]
0x14000df0d  jmp     short loc_14000DF18
0x14000df0f  mov     r8, gs:188h
0x14000df18  lea     r9, [rsp+68h+var_40]
0x14000df1d  call    NpGetClientSecurityContext
0x14000df22  test    eax, eax
0x14000df24  js      loc_14000E190
0x14000df2a  test    r14d, r14d
0x14000df2d  jz      short loc_14000DF99
0x14000df2f  lock btr dword ptr [rsi+28h], 0
0x14000df35  jnb     short loc_14000DF3D
0x14000df37  mov     rbx, [rsi+28h]
0x14000df3b  jmp     short loc_14000DF3F
0x14000df3d  xor     ebx, ebx
0x14000df3f  test    rbx, rbx
0x14000df42  jnz     short loc_14000DF68
0x14000df44  lea     edx, [rbx+30h]
0x14000df47  lea     ecx, [rbx+41h]
0x14000df4a  mov     r8d, 7246704Eh
0x14000df50  call    cs:__imp_ExAllocatePool2
0x14000df57  nop     dword ptr [rax+rax+00h]
0x14000df5c  mov     rbx, rax
0x14000df5f  test    rax, rax
0x14000df62  jz      loc_14000E01F
0x14000df68  mov     [rbx+20h], r14d
0x14000df6c  mov     dword ptr [rbx+24h], 0
0x14000df73  mov     [rbx+10h], rdi
0x14000df77  mov     eax, dword ptr [rsp+68h+Size]
0x14000df7e  mov     [rbx+28h], eax
0x14000df81  mov     rax, [rsp+68h+var_40]
0x14000df86  mov     [rbx+18h], rax
0x14000df8a  mov     r14d, 103h
0x14000df90  lea     r15, [rsi+20h]
0x14000df94  jmp     loc_14000E0C4
0x14000df99  mov     ecx, 30h ; '0'
0x14000df9e  test    ebx, ebx
0x14000dfa0  jz      short loc_14000DFB7
0x14000dfa2  mov     eax, dword ptr [rsp+68h+Size]
0x14000dfa9  lea     ecx, [rax+30h]
0x14000dfac  cmp     ecx, eax
0x14000dfae  jnb     short loc_14000DFB7
0x14000dfb0  mov     ebx, 0C000000Dh
0x14000dfb5  jmp     short loc_14000E024
0x14000dfb7  lea     r15, [rsi+20h]
0x14000dfbb  mov     r13d, [rsi+1Ch]
0x14000dfbf  sub     r13d, [r15]
0x14000dfc2  mov     r12d, dword ptr [rsp+68h+Size]
0x14000dfca  sub     r12d, [rsp+68h+arg_40]
0x14000dfd2  mov     r14d, r12d
0x14000dfd5  cmp     r13d, r12d
0x14000dfd8  cmovb   r14d, r13d
0x14000dfdc  cmp     ecx, 30h ; '0'
0x14000dfdf  jnz     short loc_14000DFEF
0x14000dfe1  lock btr dword ptr [rsi+28h], 0
0x14000dfe7  jnb     short loc_14000DFEF
0x14000dfe9  mov     rbx, [rsi+28h]
0x14000dfed  jmp     short loc_14000DFF1
0x14000dfef  xor     ebx, ebx
0x14000dff1  mov     [rsp+68h+P], rbx
0x14000dff6  test    rbx, rbx
0x14000dff9  jnz     short loc_14000E035
0x14000dffb  mov     edx, ecx
0x14000dffd  lea     ecx, [rbx+41h]
0x14000e000  mov     r8d, 7246704Eh
0x14000e006  call    cs:__imp_ExAllocatePool2
0x14000e00d  nop     dword ptr [rax+rax+00h]
0x14000e012  mov     rbx, rax
0x14000e015  mov     [rsp+68h+P], rax
0x14000e01a  test    rax, rax
0x14000e01d  jnz     short loc_14000E035
0x14000e01f  mov     ebx, 0C000009Ah
0x14000e024  mov     rcx, [rsp+68h+var_40]; P
0x14000e029  call    NpFreeClientSecurityContext
0x14000e02e  mov     eax, ebx
0x14000e030  jmp     loc_14000E190
0x14000e035  mov     [rbx+24h], r14d
0x14000e039  mov     [rbx+10h], rdi
0x14000e03d  mov     dword ptr [rbx+20h], 0
0x14000e044  mov     rax, [rsp+68h+var_40]
0x14000e049  mov     [rbx+18h], rax
0x14000e04d  mov     eax, dword ptr [rsp+68h+Size]
0x14000e054  mov     [rbx+28h], eax
0x14000e057  cmp     [rsp+68h+arg_18], 0
0x14000e05f  jnz     short loc_14000E069
0x14000e061  mov     r14d, 103h
0x14000e067  jmp     short loc_14000E0C4
0x14000e069  test    rdi, rdi
0x14000e06c  jz      short loc_14000E077
0x14000e06e  mov     rdx, [rdi+70h]
0x14000e072  mov     al, [rdi+40h]
0x14000e075  jmp     short loc_14000E08B
0x14000e077  call    cs:__imp_ExGetPreviousMode
0x14000e07e  nop     dword ptr [rax+rax+00h]
0x14000e083  mov     rdx, [rsp+68h+Src]; Src
0x14000e08b  mov     byte ptr [rsp+68h+arg_20], al
0x14000e092  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x14000e09a  lea     rcx, [rbx+30h]; void *
0x14000e09e  test    al, al
0x14000e0a0  jz      short loc_14000E0A9
0x14000e0a2  call    RtlCopyFromUser
0x14000e0a7  jmp     short loc_14000E0AF
0x14000e0a9  call    RtlCopyVolatileMemory
0x14000e0ae  nop
0x14000e0af  cmp     r13d, r12d
0x14000e0b2  jnb     short loc_14000E0B9
0x14000e0b4  test    rdi, rdi
0x14000e0b7  jnz     short loc_14000E061
0x14000e0b9  mov     qword ptr [rbx+10h], 0
0x14000e0c1  xor     r14d, r14d
0x14000e0c4  mov     eax, [rbx+24h]
0x14000e0c7  add     [r15], eax
0x14000e0ca  mov     eax, [rsp+68h+arg_18]
0x14000e0d1  mov     [rsi+10h], eax
0x14000e0d4  mov     eax, [rbx+28h]
0x14000e0d7  add     [rsi+14h], eax
0x14000e0da  inc     dword ptr [rsi+18h]
0x14000e0dd  mov     eax, [rsp+68h+arg_40]
0x14000e0e4  test    eax, eax
0x14000e0e6  jz      short loc_14000E0EB
0x14000e0e8  mov     [rsi+24h], eax
0x14000e0eb  mov     rax, [rsi+8]
0x14000e0ef  cmp     [rax], rsi
0x14000e0f2  jz      short loc_14000E0FB
0x14000e0f4  mov     ecx, 3
0x14000e0f9  int     29h; Win8: RtlFailFast(ecx)
0x14000e0fb  mov     [rbx], rsi
0x14000e0fe  mov     [rbx+8], rax
0x14000e102  mov     [rax], rbx
0x14000e105  mov     [rsi+8], rbx
0x14000e109  cmp     r14d, 103h
0x14000e110  jnz     short loc_14000E151
0x14000e112  mov     rax, [rdi+0B8h]
0x14000e119  or      byte ptr [rax+3], 1
0x14000e11d  mov     [rdi+88h], rsi
0x14000e124  mov     [rdi+90h], rbx
0x14000e12b  lea     rax, NpCancelDataQueueIrp
0x14000e132  xchg    rax, [rdi+68h]
0x14000e136  cmp     byte ptr [rdi+44h], 0
0x14000e13a  jz      short loc_14000E151
0x14000e13c  xor     ecx, ecx
0x14000e13e  xchg    rcx, [rdi+68h]
0x14000e142  test    rcx, rcx
0x14000e145  jz      short loc_14000E151
0x14000e147  mov     rdx, rdi
0x14000e14a  xor     ecx, ecx
0x14000e14c  call    NpCancelDataQueueIrp
0x14000e151  mov     eax, r14d
0x14000e154  jmp     short loc_14000E190
0x14000e156  mov     ebx, eax
0x14000e158  mov     r8, [rsp+68h+P]
0x14000e15d  mov     rcx, [rsp+68h+arg_10]
0x14000e165  cmp     [rcx+28h], r8
0x14000e169  jnz     short loc_14000E173
0x14000e16b  lock bts dword ptr [rcx+28h], 0
0x14000e171  jmp     short loc_14000E184
0x14000e173  xor     edx, edx; Tag
0x14000e175  mov     rcx, r8; P
0x14000e178  call    cs:__imp_ExFreePoolWithTag
0x14000e17f  nop     dword ptr [rax+rax+00h]
0x14000e184  mov     rcx, [rsp+68h+var_40]; P
0x14000e189  call    NpFreeClientSecurityContext
0x14000e18e  mov     eax, ebx
0x14000e190  mov     rbx, [rsp+68h+arg_0]
0x14000e195  mov     rsi, [rsp+68h+arg_8]
0x14000e19a  add     rsp, 40h
0x14000e19e  pop     r15
0x14000e1a0  pop     r14
0x14000e1a2  pop     r13
0x14000e1a4  pop     r12
0x14000e1a6  pop     rdi
0x14000e1a7  retn
0x14001662c  push    rbp
0x14001662e  sub     rsp, 20h
0x140016632  mov     rbp, rdx
0x140016635  xor     eax, eax
0x140016637  cmp     [rbp+90h], al
0x14001663d  setnz   al
0x140016640  mov     [rbp+20h], eax
0x140016643  mov     eax, [rbp+20h]
0x140016646  add     rsp, 20h
0x14001664a  pop     rbp
0x14001664b  retn
```
