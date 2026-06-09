# DiscpComputeStaticTargetSize

- ea: `0x1800025ac`
- end: `0x1800026f2`
- name: `DiscpComputeStaticTargetSize`
- size: `326`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _DWORD *, _DWORD *, _DWORD *, unsigned int *, unsigned int *, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001fb8`

## callees

- `0x180001410`
- `0x1800025ac`

## import_xrefs

- `ISCSIUM!DiscpULongAddList` at `0x1800026d0`
- `ISCSIUM!DiscpULongAddList` at `0x1800026d0`

## pseudocode

```c
__int64 __fastcall DiscpComputeStaticTargetSize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        _DWORD *a6,
        _DWORD *a7,
        unsigned int *a8,
        unsigned int *a9,
        unsigned int *a10,
        __int64 a11)
{
  __int64 v12; // r9
  __int64 v13; // rax
  int v14; // eax
  unsigned int v15; // eax
  int v16; // ecx
  int v17; // eax
  unsigned int v18; // ecx
  unsigned int v19; // eax
  _DWORD v21[6]; // [rsp+20h] [rbp-58h] BYREF

  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(a1 + 2 * v13) );
  *a6 = (2 * v13 + 9) & 0xFFFFFFF8;
  if ( a2 )
  {
    do
      ++v12;
    while ( *(_WORD *)(a2 + 2 * v12) );
    v14 = (2 * v12 + 9) & 0xFFFFFFF8;
  }
  else
  {
    v14 = 0;
  }
  *a7 = v14;
  if ( a5 )
    v15 = (1026 * *a5 + 11) & 0xFFFFFFF8;
  else
    v15 = 0;
  *a9 = v15;
  v16 = 7;
  if ( a3 )
    v17 = 16 * *(_DWORD *)(a3 + 1504) + 1527;
  else
    v17 = 7;
  *a8 = v17 & 0xFFFFFFF8;
  if ( a4 )
    v16 = *(_DWORD *)(a4 + 36) + *(_DWORD *)(a4 + 40) + 71;
  v18 = v16 & 0xFFFFFFF8;
  v21[0] = 28;
  *a10 = v18;
  v21[1] = *a6;
  v21[2] = *a7;
  v21[3] = *a8;
  v19 = *a9;
  v21[5] = v18;
  v21[4] = v19;
  return DiscpULongAddList(v21, 6, a11);
}

```

## disassembly

```asm
0x1800025ac  push    rbx
0x1800025ae  push    rbp
0x1800025af  push    rsi
0x1800025b0  push    rdi
0x1800025b1  push    r12
0x1800025b3  push    r14
0x1800025b5  push    r15
0x1800025b7  sub     rsp, 40h
0x1800025bb  mov     rax, cs:__security_cookie
0x1800025c2  xor     rax, rsp
0x1800025c5  mov     [rsp+78h+var_40], rax
0x1800025ca  mov     rsi, [rsp+78h+arg_28]
0x1800025d2  mov     r10, r9
0x1800025d5  mov     rdi, [rsp+78h+arg_30]
0x1800025dd  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800025e1  mov     r11, [rsp+78h+arg_38]
0x1800025e9  mov     rax, r9
0x1800025ec  mov     rbx, [rsp+78h+arg_40]
0x1800025f4  xor     r15d, r15d
0x1800025f7  mov     r14, [rsp+78h+arg_48]
0x1800025ff  mov     rbp, [rsp+78h+arg_50]
0x180002607  inc     rax
0x18000260a  cmp     [rcx+rax*2], r15w
0x18000260f  jnz     short loc_180002607
0x180002611  lea     eax, ds:9[rax*2]
0x180002618  mov     r12d, 0FFFFFFF8h
0x18000261e  and     eax, r12d
0x180002621  mov     [rsi], eax
0x180002623  test    rdx, rdx
0x180002626  jz      short loc_180002640
0x180002628  inc     r9
0x18000262b  cmp     [rdx+r9*2], r15w
0x180002630  jnz     short loc_180002628
0x180002632  lea     rax, ds:9[r9*2]
0x18000263a  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000263e  jmp     short loc_180002643
0x180002640  mov     rax, r15
0x180002643  mov     [rdi], eax
0x180002645  mov     rax, [rsp+78h+arg_20]
0x18000264d  test    rax, rax
0x180002650  jz      short loc_180002660
0x180002652  imul    eax, [rax], 402h
0x180002658  add     eax, 0Bh
0x18000265b  and     eax, r12d
0x18000265e  jmp     short loc_180002663
0x180002660  mov     eax, r15d
0x180002663  mov     [rbx], eax
0x180002665  mov     ecx, 7
0x18000266a  test    r8, r8
0x18000266d  jz      short loc_180002680
0x18000266f  mov     eax, [r8+5E0h]
0x180002676  shl     eax, 4
0x180002679  add     eax, 5F7h
0x18000267e  jmp     short loc_180002682
0x180002680  mov     eax, ecx
0x180002682  and     eax, r12d
0x180002685  mov     [r11], eax
0x180002688  test    r10, r10
0x18000268b  jz      short loc_180002698
0x18000268d  mov     ecx, [r10+28h]
0x180002691  add     ecx, 47h ; 'G'
0x180002694  add     ecx, [r10+24h]
0x180002698  and     ecx, r12d
0x18000269b  mov     [rsp+78h+var_58], 1Ch
0x1800026a3  mov     [r14], ecx
0x1800026a6  mov     r8, rbp
0x1800026a9  mov     eax, [rsi]
0x1800026ab  mov     edx, 6
0x1800026b0  mov     [rsp+78h+var_54], eax
0x1800026b4  mov     eax, [rdi]
0x1800026b6  mov     [rsp+78h+var_50], eax
0x1800026ba  mov     eax, [r11]
0x1800026bd  mov     [rsp+78h+var_4C], eax
0x1800026c1  mov     eax, [rbx]
0x1800026c3  mov     [rsp+78h+var_44], ecx
0x1800026c7  lea     rcx, [rsp+78h+var_58]
0x1800026cc  mov     [rsp+78h+var_48], eax
0x1800026d0  call    cs:__imp_DiscpULongAddList
0x1800026d6  mov     rcx, [rsp+78h+var_40]
0x1800026db  xor     rcx, rsp; StackCookie
0x1800026de  call    __security_check_cookie
0x1800026e3  add     rsp, 40h
0x1800026e7  pop     r15
0x1800026e9  pop     r14
0x1800026eb  pop     r12
0x1800026ed  pop     rdi
0x1800026ee  pop     rsi
0x1800026ef  pop     rbp
0x1800026f0  pop     rbx
0x1800026f1  retn
```
