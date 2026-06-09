# UpdateReplicatedUniqueIds

- ea: `0x140010680`
- end: `0x1400107ed`
- name: `UpdateReplicatedUniqueIds`
- size: `365`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400119a0`

## callees

- `0x140001b30`
- `0x140002f80`
- `0x140010680`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400106f1`
- `ntoskrnl!ExAllocatePool2` at `0x14001074d`
- `ntoskrnl!ExAllocatePool2` at `0x1400106f1`
- `ntoskrnl!ExAllocatePool2` at `0x14001074d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001076a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001076a`
- `ntoskrnl!RtlCompareMemory` at `0x1400106bd`
- `ntoskrnl!RtlCompareMemory` at `0x1400106bd`

## pseudocode

```c
SIZE_T __fastcall UpdateReplicatedUniqueIds(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rbx
  _QWORD *v3; // rsi
  unsigned __int16 *v6; // rcx
  SIZE_T v7; // rdi
  SIZE_T result; // rax
  _QWORD *Pool2; // rbx
  _WORD *v10; // rax
  __int64 v11; // r14

  v2 = *(_QWORD **)(a1 + 32);
  v3 = (_QWORD *)(a1 + 32);
  if ( v2 == (_QWORD *)(a1 + 32) )
    goto LABEL_7;
  while ( 1 )
  {
    v6 = (unsigned __int16 *)v2[2];
    if ( *v6 == *(_WORD *)(a2 + 14) )
    {
      v7 = *v6;
      result = RtlCompareMemory(v6 + 1, (const void *)(a2 + *(unsigned __int16 *)(a2 + 12)), v7);
      if ( result == v7 )
        break;
    }
    v2 = (_QWORD *)*v2;
    if ( v2 == v3 )
      goto LABEL_7;
  }
  if ( v2 == v3 )
  {
LABEL_7:
    Pool2 = (_QWORD *)ExAllocatePool2(258, 24, 1098149453);
    if ( Pool2 )
    {
      v10 = (_WORD *)ExAllocatePool2(258, *(unsigned __int16 *)(a2 + 14) + 4LL, 1098149453);
      Pool2[2] = v10;
      if ( v10 )
      {
        *v10 = *(_WORD *)(a2 + 14);
        memmove(
          (void *)(Pool2[2] + 2LL),
          (const void *)(a2 + *(unsigned __int16 *)(a2 + 12)),
          *(unsigned __int16 *)Pool2[2]);
        result = *(_QWORD *)(a1 + 40);
        v11 = a1 + 32;
        if ( *(_QWORD *)result != v11 )
          __fastfail(3u);
        *Pool2 = v11;
        Pool2[1] = result;
        *(_QWORD *)result = Pool2;
        *(_QWORD *)(v11 + 8) = Pool2;
      }
      else
      {
        ExFreePoolWithTag(Pool2, 0);
        result = (SIZE_T)&WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          result = HIDWORD(WPP_GLOBAL_Control->Timer);
          if ( (result & 4) != 0 )
            return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 122);
        }
      }
    }
    else
    {
      result = (SIZE_T)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        result = HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( (result & 4) != 0 )
          return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 121);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140010680  push    rbx
0x140010682  push    rbp
0x140010683  push    rsi
0x140010684  push    rdi
0x140010685  push    r14
0x140010687  sub     rsp, 20h
0x14001068b  mov     rbx, [rcx+20h]
0x14001068f  lea     rsi, [rcx+20h]
0x140010693  mov     rbp, rdx
0x140010696  mov     r14, rcx
0x140010699  cmp     rbx, rsi
0x14001069c  jz      short loc_1400106E1
0x14001069e  xchg    ax, ax
0x1400106a0  mov     rcx, [rbx+10h]
0x1400106a4  movzx   eax, word ptr [rcx]
0x1400106a7  cmp     ax, [rbp+0Eh]
0x1400106ab  jnz     short loc_1400106CE
0x1400106ad  movzx   edx, word ptr [rbp+0Ch]
0x1400106b1  add     rcx, 2; Source1
0x1400106b5  add     rdx, rbp; Source2
0x1400106b8  mov     r8d, eax; Length
0x1400106bb  mov     edi, eax
0x1400106bd  call    cs:__imp_RtlCompareMemory
0x1400106c4  nop     dword ptr [rax+rax+00h]
0x1400106c9  cmp     rax, rdi
0x1400106cc  jz      short loc_1400106D8
0x1400106ce  mov     rbx, [rbx]
0x1400106d1  cmp     rbx, rsi
0x1400106d4  jnz     short loc_1400106A0
0x1400106d6  jmp     short loc_1400106E1
0x1400106d8  cmp     rbx, rsi
0x1400106db  jnz     loc_1400107E1
0x1400106e1  mov     edx, 18h
0x1400106e6  mov     ecx, 102h
0x1400106eb  mov     r8d, 41746E4Dh
0x1400106f1  call    cs:__imp_ExAllocatePool2
0x1400106f8  nop     dword ptr [rax+rax+00h]
0x1400106fd  mov     rbx, rax
0x140010700  test    rax, rax
0x140010703  jnz     short loc_14001073A
0x140010705  mov     rcx, cs:WPP_GLOBAL_Control
0x14001070c  lea     rax, WPP_GLOBAL_Control
0x140010713  cmp     rcx, rax
0x140010716  jz      loc_1400107E1
0x14001071c  mov     eax, [rcx+2Ch]
0x14001071f  test    al, 4
0x140010721  jz      loc_1400107E1
0x140010727  mov     rcx, [rcx+18h]
0x14001072b  mov     edx, 79h ; 'y'
0x140010730  call    WPP_SF_
0x140010735  jmp     loc_1400107E1
0x14001073a  movzx   edx, word ptr [rbp+0Eh]
0x14001073e  mov     ecx, 102h
0x140010743  add     rdx, 4
0x140010747  mov     r8d, 41746E4Dh
0x14001074d  call    cs:__imp_ExAllocatePool2
0x140010754  nop     dword ptr [rax+rax+00h]
0x140010759  mov     [rbx+10h], rax
0x14001075d  mov     rcx, rax
0x140010760  test    rax, rax
0x140010763  jnz     short loc_1400107A0
0x140010765  xor     edx, edx; Tag
0x140010767  mov     rcx, rbx; P
0x14001076a  call    cs:__imp_ExFreePoolWithTag
0x140010771  nop     dword ptr [rax+rax+00h]
0x140010776  mov     rcx, cs:WPP_GLOBAL_Control
0x14001077d  lea     rax, WPP_GLOBAL_Control
0x140010784  cmp     rcx, rax
0x140010787  jz      short loc_1400107E1
0x140010789  mov     eax, [rcx+2Ch]
0x14001078c  test    al, 4
0x14001078e  jz      short loc_1400107E1
0x140010790  mov     rcx, [rcx+18h]
0x140010794  mov     edx, 7Ah ; 'z'
0x140010799  call    WPP_SF_
0x14001079e  jmp     short loc_1400107E1
0x1400107a0  movzx   eax, word ptr [rbp+0Eh]
0x1400107a4  mov     [rcx], ax
0x1400107a7  mov     rcx, [rbx+10h]
0x1400107ab  movzx   edx, word ptr [rbp+0Ch]
0x1400107af  add     rdx, rbp; Src
0x1400107b2  movzx   r8d, word ptr [rcx]; Size
0x1400107b6  add     rcx, 2; void *
0x1400107ba  call    memmove
0x1400107bf  mov     rax, [r14+28h]
0x1400107c3  add     r14, 20h ; ' '
0x1400107c7  cmp     [rax], r14
0x1400107ca  jz      short loc_1400107D3
0x1400107cc  mov     ecx, 3
0x1400107d1  int     29h; Win8: RtlFailFast(ecx)
0x1400107d3  mov     [rbx], r14
0x1400107d6  mov     [rbx+8], rax
0x1400107da  mov     [rax], rbx
0x1400107dd  mov     [r14+8], rbx
0x1400107e1  add     rsp, 20h
0x1400107e5  pop     r14
0x1400107e7  pop     rdi
0x1400107e8  pop     rsi
0x1400107e9  pop     rbp
0x1400107ea  pop     rbx
0x1400107eb  retn
```
