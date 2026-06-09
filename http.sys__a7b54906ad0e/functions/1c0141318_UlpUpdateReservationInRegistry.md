# UlpUpdateReservationInRegistry

- ea: `0x1c0141318`
- end: `0x1c0141513`
- name: `UlpUpdateReservationInRegistry`
- size: `507`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x1c00da2b8`
- `0x1c0140e5c`

## callees

- `0x1c00022d0`
- `0x1c001b640`
- `0x1c0141318`

## import_xrefs

- `ntoskrnl!wcschr` at `0x1c01413d1`
- `ntoskrnl!wcschr` at `0x1c01413f0`
- `ntoskrnl!wcschr` at `0x1c014140b`
- `ntoskrnl!wcschr` at `0x1c014142b`
- `ntoskrnl!wcschr` at `0x1c01413d1`
- `ntoskrnl!wcschr` at `0x1c01413f0`
- `ntoskrnl!wcschr` at `0x1c014140b`
- `ntoskrnl!wcschr` at `0x1c014142b`
- `ntoskrnl!ZwDeleteValueKey` at `0x1c01414c0`
- `ntoskrnl!ZwDeleteValueKey` at `0x1c01414ce`
- `ntoskrnl!ZwDeleteValueKey` at `0x1c01414c0`
- `ntoskrnl!ZwDeleteValueKey` at `0x1c01414ce`
- `ntoskrnl!ZwSetValueKey` at `0x1c01414a2`
- `ntoskrnl!ZwSetValueKey` at `0x1c01414a2`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0141388`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0141388`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01414e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c01414e6`

## pseudocode

```c
__int64 __fastcall UlpUpdateReservationInRegistry(__int64 a1, char a2, __int64 a3, void *a4, ULONG DataSize)
{
  wchar_t *v9; // rsi
  NTSTATUS inited; // ebx
  SIZE_T v11; // r14
  wchar_t *PoolWithTagPriority; // rax
  wchar_t *v13; // rax
  wchar_t *v14; // rax
  wchar_t *v15; // rax
  char *v16; // rdi
  wchar_t *v17; // rax
  wchar_t v18; // cx
  signed __int64 v19; // rax
  wchar_t *v20; // rdx
  void *v21; // rcx
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-38h] BYREF

  v9 = 0;
  ValueName = 0;
  if ( !*(_QWORD *)(a1 + 1392) )
    return (unsigned int)-1073741816;
  if ( *(_DWORD *)(a3 + 4) != 2 )
  {
    v20 = *(wchar_t **)(a3 + 8);
    goto LABEL_17;
  }
  v11 = 2LL * *(unsigned __int16 *)(a3 + 56) + 2;
  PoolWithTagPriority = (wchar_t *)ExAllocatePoolWithTagPriority(PagedPool, v11, 0x4C556C55u, LowPoolPriority);
  v9 = PoolWithTagPriority;
  if ( PoolWithTagPriority )
  {
    inited = 0;
    memmove(PoolWithTagPriority, *(const void **)(a3 + 8), v11);
    v13 = v9 + 7;
    if ( v9[7] == 91 || v9[8] == 91 )
    {
      v13 = wcschr(v9 + 7, 0x5Du);
      if ( !v13 )
        goto LABEL_22;
    }
    v14 = wcschr(v13, 0x3Au);
    if ( !v14 )
      goto LABEL_22;
    v15 = wcschr(v14 + 1, 0x3Au);
    v16 = (char *)v15;
    if ( !v15 )
      goto LABEL_22;
    v17 = wcschr(v15, 0x2Fu);
    if ( !v17 )
      goto LABEL_22;
    v18 = *v17;
    if ( *v17 )
    {
      v19 = (char *)v17 - v16;
      do
      {
        *(_WORD *)v16 = v18;
        v16 += 2;
        v18 = *(_WORD *)&v16[v19];
      }
      while ( v18 );
    }
    *(_WORD *)v16 = 0;
    v20 = v9;
LABEL_17:
    inited = UlInitUnicodeStringEx(&ValueName, v20);
    if ( inited >= 0 )
    {
      v21 = *(void **)(a1 + 1392);
      if ( a2 )
      {
        inited = ZwSetValueKey(v21, &ValueName, 0, 3u, a4, DataSize);
        if ( inited < 0 )
          ZwDeleteValueKey(*(HANDLE *)(a1 + 1392), &ValueName);
      }
      else
      {
        inited = ZwDeleteValueKey(v21, &ValueName);
      }
    }
    goto LABEL_22;
  }
  inited = -1073741670;
LABEL_22:
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1c0141318  mov     rax, rsp
0x1c014131b  mov     [rax+8], rbx
0x1c014131f  mov     [rax+10h], rbp
0x1c0141323  mov     [rax+18h], rsi
0x1c0141327  push    rdi
0x1c0141328  push    r12
0x1c014132a  push    r13
0x1c014132c  push    r14
0x1c014132e  push    r15
0x1c0141330  sub     rsp, 40h
0x1c0141334  xor     r13d, r13d
0x1c0141337  xorps   xmm0, xmm0
0x1c014133a  mov     r12, r9
0x1c014133d  mov     rdi, r8
0x1c0141340  mov     r15b, dl
0x1c0141343  mov     rbp, rcx
0x1c0141346  mov     esi, r13d
0x1c0141349  movups  xmmword ptr [rax-38h], xmm0
0x1c014134d  cmp     [rcx+570h], r13
0x1c0141354  jnz     short loc_1C0141360
0x1c0141356  mov     ebx, 0C0000008h
0x1c014135b  jmp     loc_1C01414F2
0x1c0141360  cmp     dword ptr [r8+4], 2
0x1c0141365  jnz     loc_1C0141464
0x1c014136b  movzx   eax, word ptr [r8+38h]
0x1c0141370  xor     r9d, r9d; Priority
0x1c0141373  mov     r8d, 4C556C55h; Tag
0x1c0141379  lea     r14, ds:2[rax*2]
0x1c0141381  mov     rdx, r14; NumberOfBytes
0x1c0141384  lea     ecx, [r9+1]; PoolType
0x1c0141388  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c014138f  nop     dword ptr [rax+rax+00h]
0x1c0141394  mov     rsi, rax
0x1c0141397  test    rax, rax
0x1c014139a  jnz     short loc_1C01413A6
0x1c014139c  mov     ebx, 0C000009Ah
0x1c01413a1  jmp     loc_1C01414DC
0x1c01413a6  mov     rdx, [rdi+8]; Src
0x1c01413aa  mov     r8, r14; Size
0x1c01413ad  mov     rcx, rsi; void *
0x1c01413b0  mov     ebx, r13d
0x1c01413b3  call    memmove
0x1c01413b8  lea     rax, [rsi+0Eh]
0x1c01413bc  cmp     word ptr [rax], 5Bh ; '['
0x1c01413c0  jz      short loc_1C01413C9
0x1c01413c2  cmp     word ptr [rax+2], 5Bh ; '['
0x1c01413c7  jnz     short loc_1C01413E6
0x1c01413c9  mov     edx, 5Dh ; ']'; Ch
0x1c01413ce  mov     rcx, rax; Str
0x1c01413d1  call    cs:__imp_wcschr
0x1c01413d8  nop     dword ptr [rax+rax+00h]
0x1c01413dd  test    rax, rax
0x1c01413e0  jz      loc_1C01414DC
0x1c01413e6  mov     edi, 3Ah ; ':'
0x1c01413eb  mov     rcx, rax; Str
0x1c01413ee  mov     edx, edi; Ch
0x1c01413f0  call    cs:__imp_wcschr
0x1c01413f7  nop     dword ptr [rax+rax+00h]
0x1c01413fc  test    rax, rax
0x1c01413ff  jz      loc_1C01414DC
0x1c0141405  mov     edx, edi; Ch
0x1c0141407  lea     rcx, [rax+2]; Str
0x1c014140b  call    cs:__imp_wcschr
0x1c0141412  nop     dword ptr [rax+rax+00h]
0x1c0141417  mov     rdi, rax
0x1c014141a  test    rax, rax
0x1c014141d  jz      loc_1C01414DC
0x1c0141423  mov     edx, 2Fh ; '/'; Ch
0x1c0141428  mov     rcx, rax; Str
0x1c014142b  call    cs:__imp_wcschr
0x1c0141432  nop     dword ptr [rax+rax+00h]
0x1c0141437  test    rax, rax
0x1c014143a  jz      loc_1C01414DC
0x1c0141440  movzx   ecx, word ptr [rax]
0x1c0141443  test    cx, cx
0x1c0141446  jz      short loc_1C014145B
0x1c0141448  sub     rax, rdi
0x1c014144b  mov     [rdi], cx
0x1c014144e  add     rdi, 2
0x1c0141452  movzx   ecx, word ptr [rax+rdi]
0x1c0141456  test    cx, cx
0x1c0141459  jnz     short loc_1C014144B
0x1c014145b  mov     [rdi], r13w
0x1c014145f  mov     rdx, rsi
0x1c0141462  jmp     short loc_1C0141468
0x1c0141464  mov     rdx, [r8+8]
0x1c0141468  lea     rcx, [rsp+68h+ValueName]
0x1c014146d  call    UlInitUnicodeStringEx
0x1c0141472  mov     ebx, eax
0x1c0141474  test    eax, eax
0x1c0141476  js      short loc_1C01414DC
0x1c0141478  mov     rcx, [rbp+570h]; KeyHandle
0x1c014147f  lea     rdx, [rsp+68h+ValueName]; ValueName
0x1c0141484  test    r15b, r15b
0x1c0141487  jz      short loc_1C01414CE
0x1c0141489  mov     eax, [rsp+68h+arg_20]
0x1c0141490  mov     r9d, 3; Type
0x1c0141496  mov     [rsp+68h+DataSize], eax; DataSize
0x1c014149a  xor     r8d, r8d; TitleIndex
0x1c014149d  mov     [rsp+68h+Data], r12; Data
0x1c01414a2  call    cs:__imp_ZwSetValueKey
0x1c01414a9  nop     dword ptr [rax+rax+00h]
0x1c01414ae  mov     ebx, eax
0x1c01414b0  test    eax, eax
0x1c01414b2  jns     short loc_1C01414DC
0x1c01414b4  mov     rcx, [rbp+570h]; KeyHandle
0x1c01414bb  lea     rdx, [rsp+68h+ValueName]; ValueName
0x1c01414c0  call    cs:__imp_ZwDeleteValueKey
0x1c01414c7  nop     dword ptr [rax+rax+00h]
0x1c01414cc  jmp     short loc_1C01414DC
0x1c01414ce  call    cs:__imp_ZwDeleteValueKey
0x1c01414d5  nop     dword ptr [rax+rax+00h]
0x1c01414da  mov     ebx, eax
0x1c01414dc  test    rsi, rsi
0x1c01414df  jz      short loc_1C01414F2
0x1c01414e1  xor     edx, edx; Tag
0x1c01414e3  mov     rcx, rsi; P
0x1c01414e6  call    cs:__imp_ExFreePoolWithTag
0x1c01414ed  nop     dword ptr [rax+rax+00h]
0x1c01414f2  lea     r11, [rsp+68h+var_28]
0x1c01414f7  mov     eax, ebx
0x1c01414f9  mov     rbx, [r11+30h]
0x1c01414fd  mov     rbp, [r11+38h]
0x1c0141501  mov     rsi, [r11+40h]
0x1c0141505  mov     rsp, r11
0x1c0141508  pop     r15
0x1c014150a  pop     r14
0x1c014150c  pop     r13
0x1c014150e  pop     r12
0x1c0141510  pop     rdi
0x1c0141511  retn
```
