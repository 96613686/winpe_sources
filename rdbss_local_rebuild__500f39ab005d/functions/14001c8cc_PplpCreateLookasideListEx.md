# PplpCreateLookasideListEx

- ea: `0x14001c8cc`
- end: `0x14001ca0a`
- name: `PplpCreateLookasideListEx`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14008321c`

## callees

- `0x14001c8cc`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14001c93d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001c93d`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14001c978`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14001c978`
- `ntoskrnl!ExAllocatePool3` at `0x14001c90a`
- `ntoskrnl!ExAllocatePool3` at `0x14001c90a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c9bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c9bd`

## pseudocode

```c
_DWORD *__fastcall PplpCreateLookasideListEx(int a1)
{
  int v1; // ebp
  _DWORD *Pool3; // rbx
  int i; // esi
  _DWORD *v4; // rdi
  _DWORD *result; // rax
  _QWORD v6[7]; // [rsp+40h] [rbp-38h] BYREF

  v1 = a1 + 1;
  v6[1] = 0;
  v6[0] = 1;
  Pool3 = (_DWORD *)ExAllocatePool3(72, ((unsigned __int64)(unsigned int)(a1 + 1) << 7) + 64, 1934456914, v6, 1);
  if ( !Pool3 )
    return 0;
  for ( i = 0; i < v1; ++i )
  {
    v4 = &Pool3[32 * (__int64)i];
    KeInitializeSpinLock((PKSPIN_LOCK)v4 + 21);
    if ( i )
    {
      *((_BYTE *)v4 + 176) = 0;
      *((_QWORD *)v4 + 20) = Pool3 + 16;
    }
    else
    {
      if ( ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(v4 + 16), 0, 0, NonPagedPoolNx, 0, 0x380u, 0x72497852u, 0) < 0 )
      {
        ExFreePoolWithTag(Pool3, 0x734D7852u);
        return 0;
      }
      *((_QWORD *)v4 + 20) = 0;
      *((_BYTE *)v4 + 176) = 1;
    }
  }
  *Pool3 = v1;
  *((_WORD *)Pool3 + 18) = 0;
  *((_QWORD *)Pool3 + 3) = 0;
  result = Pool3;
  Pool3[1] = 0;
  Pool3[2] = 1917417554;
  Pool3[3] = 1934456914;
  *((_QWORD *)Pool3 + 2) = 896;
  Pool3[8] = 512;
  return result;
}

```

## disassembly

```asm
0x14001c8cc  mov     rax, rsp
0x14001c8cf  push    rbx
0x14001c8d0  push    rbp
0x14001c8d1  push    rsi
0x14001c8d2  push    rdi
0x14001c8d3  sub     rsp, 58h
0x14001c8d7  lea     ebp, [rcx+1]
0x14001c8da  mov     qword ptr [rax-30h], 0
0x14001c8e2  mov     edx, ebp
0x14001c8e4  lea     r9, [rax-38h]
0x14001c8e8  shl     rdx, 7
0x14001c8ec  mov     ecx, 48h ; 'H'
0x14001c8f1  add     rdx, 40h ; '@'
0x14001c8f5  mov     qword ptr [rax-38h], 1
0x14001c8fd  mov     r8d, 734D7852h
0x14001c903  mov     dword ptr [rax-58h], 1
0x14001c90a  call    cs:__imp_ExAllocatePool3
0x14001c911  nop     dword ptr [rax+rax+00h]
0x14001c916  mov     rbx, rax
0x14001c919  test    rax, rax
0x14001c91c  jz      loc_14001C9C9
0x14001c922  xor     esi, esi
0x14001c924  cmp     esi, ebp
0x14001c926  jge     loc_14001C9D5
0x14001c92c  movsxd  rdi, esi
0x14001c92f  shl     rdi, 7
0x14001c933  add     rdi, rbx
0x14001c936  lea     rcx, [rdi+0A8h]; SpinLock
0x14001c93d  call    cs:__imp_KeInitializeSpinLock
0x14001c944  nop     dword ptr [rax+rax+00h]
0x14001c949  test    esi, esi
0x14001c94b  jnz     short loc_14001C99C
0x14001c94d  xor     eax, eax
0x14001c94f  lea     rcx, [rdi+40h]; Lookaside
0x14001c953  mov     [rsp+78h+Depth], ax; Depth
0x14001c958  mov     r9d, 200h; PoolType
0x14001c95e  mov     [rsp+78h+Tag], 72497852h; Tag
0x14001c966  xor     r8d, r8d; Free
0x14001c969  mov     [rsp+78h+Size], 380h; Size
0x14001c972  xor     edx, edx; Allocate
0x14001c974  mov     [rsp+78h+Flags], eax; Flags
0x14001c978  call    cs:__imp_ExInitializeLookasideListEx
0x14001c97f  nop     dword ptr [rax+rax+00h]
0x14001c984  test    eax, eax
0x14001c986  js      short loc_14001C9B5
0x14001c988  mov     qword ptr [rdi+0A0h], 0
0x14001c993  mov     byte ptr [rdi+0B0h], 1
0x14001c99a  jmp     short loc_14001C9AE
0x14001c99c  lea     rax, [rbx+40h]
0x14001c9a0  mov     byte ptr [rdi+0B0h], 0
0x14001c9a7  mov     [rdi+0A0h], rax
0x14001c9ae  inc     esi
0x14001c9b0  jmp     loc_14001C924
0x14001c9b5  mov     edx, 734D7852h; Tag
0x14001c9ba  mov     rcx, rbx; P
0x14001c9bd  call    cs:__imp_ExFreePoolWithTag
0x14001c9c4  nop     dword ptr [rax+rax+00h]
0x14001c9c9  xor     eax, eax
0x14001c9cb  add     rsp, 58h
0x14001c9cf  pop     rdi
0x14001c9d0  pop     rsi
0x14001c9d1  pop     rbp
0x14001c9d2  pop     rbx
0x14001c9d3  retn
0x14001c9d5  xor     eax, eax
0x14001c9d7  mov     [rbx], ebp
0x14001c9d9  mov     [rbx+24h], ax
0x14001c9dd  mov     [rbx+18h], rax
0x14001c9e1  mov     rax, rbx
0x14001c9e4  mov     dword ptr [rbx+4], 0
0x14001c9eb  mov     dword ptr [rbx+8], 72497852h
0x14001c9f2  mov     dword ptr [rbx+0Ch], 734D7852h
0x14001c9f9  mov     qword ptr [rbx+10h], 380h
0x14001ca01  mov     dword ptr [rbx+20h], 200h
0x14001ca08  jmp     short loc_14001C9CB
```
