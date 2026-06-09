# AddToPendingList

- ea: `0x14000889c`
- end: `0x1400089c2`
- name: `AddToPendingList`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140009844`

## callees

- `0x14000889c`
- `0x1400089c8`
- `0x140031440`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400088d1`
- `ntoskrnl!ExAllocatePool2` at `0x1400088d1`

## pseudocode

```c
__int64 __fastcall AddToPendingList(__int128 *a1, __int64 *a2)
{
  void *Pool2; // rax
  __int64 v5; // rbx
  __int128 v6; // xmm0
  __int64 *v7; // r9

  if ( dword_1400394B0 > dword_1400394B4 )
    return 3221225626LL;
  Pool2 = (void *)ExAllocatePool2(64, 184, 1383359054);
  v5 = (__int64)Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  memset(Pool2, 0, 0xB8u);
  v6 = *a1;
  *(_DWORD *)(v5 + 72) = 128;
  *(_DWORD *)(v5 + 16) = -87097344;
  *(_OWORD *)(v5 + 164) = v6;
  *(_DWORD *)(v5 + 56) = dword_1400395F8;
  NbtCheckNameAddrTimer(v5);
  if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
    WPP_SF_qddds(
      *(_DWORD *)(v5 + 20),
      12,
      (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
      v5,
      *(_DWORD *)(v5 + 20),
      *(_DWORD *)(v5 + 20) + 1,
      178,
      (__int64)"minio\\netbt\\sys\\namesrv.c");
  _InterlockedIncrement((volatile signed __int32 *)(v5 + 20));
  NbtCheckNameAddrTimer(v5);
  v7 = (__int64 *)qword_1400394A8;
  if ( *(__int64 **)qword_1400394A8 != &qword_1400394A0 )
    __fastfail(3u);
  *(_QWORD *)v5 = &qword_1400394A0;
  *(_QWORD *)(v5 + 8) = v7;
  *v7 = v5;
  qword_1400394A8 = v5;
  _InterlockedIncrement(&dword_1400394B0);
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x14000889c  mov     [rsp+arg_0], rbx
0x1400088a1  mov     [rsp+arg_8], rsi
0x1400088a6  push    rdi
0x1400088a7  sub     rsp, 40h
0x1400088ab  mov     eax, cs:dword_1400394B4
0x1400088b1  mov     rdi, rdx
0x1400088b4  cmp     cs:dword_1400394B0, eax
0x1400088ba  mov     rsi, rcx
0x1400088bd  jg      loc_140008979
0x1400088c3  mov     edx, 0B8h
0x1400088c8  mov     r8d, 5274624Eh
0x1400088ce  lea     ecx, [rdx-78h]
0x1400088d1  call    cs:__imp_ExAllocatePool2
0x1400088d8  nop     dword ptr [rax+rax+00h]
0x1400088dd  mov     rbx, rax
0x1400088e0  test    rax, rax
0x1400088e3  jz      loc_140008979
0x1400088e9  xor     edx, edx; Val
0x1400088eb  mov     r8d, 0B8h; Size
0x1400088f1  mov     rcx, rax; void *
0x1400088f4  call    memset
0x1400088f9  movups  xmm0, xmmword ptr [rsi]
0x1400088fc  mov     dword ptr [rbx+48h], 80h
0x140008903  mov     dword ptr [rbx+10h], 0FACF0000h
0x14000890a  movdqu  xmmword ptr [rbx+0A4h], xmm0
0x140008912  mov     ecx, cs:dword_1400395F8
0x140008918  mov     [rbx+38h], ecx
0x14000891b  mov     rcx, rbx
0x14000891e  call    NbtCheckNameAddrTimer
0x140008923  test    byte ptr cs:xmmword_140038420+9, 40h
0x14000892a  jnz     short loc_140008987
0x14000892c  lock inc dword ptr [rbx+14h]
0x140008930  mov     rcx, rbx
0x140008933  call    NbtCheckNameAddrTimer
0x140008938  mov     r9, cs:qword_1400394A8
0x14000893f  lea     rax, qword_1400394A0
0x140008946  cmp     [r9], rax
0x140008949  jnz     short loc_140008980
0x14000894b  mov     [rbx], rax
0x14000894e  mov     [rbx+8], r9
0x140008952  mov     [r9], rbx
0x140008955  mov     cs:qword_1400394A8, rbx
0x14000895c  lock inc cs:dword_1400394B0
0x140008963  mov     [rdi], rbx
0x140008966  xor     eax, eax
0x140008968  mov     rbx, [rsp+48h+arg_0]
0x14000896d  mov     rsi, [rsp+48h+arg_8]
0x140008972  add     rsp, 40h
0x140008976  pop     rdi
0x140008977  retn
0x140008979  mov     eax, 0C000009Ah
0x14000897e  jmp     short loc_140008968
0x140008980  mov     ecx, 3
0x140008985  int     29h; Win8: RtlFailFast(ecx)
0x140008987  mov     ecx, [rbx+14h]
0x14000898a  lea     r8, aMinioNetbtSysN_0; "minio\\netbt\\sys\\namesrv.c"
0x140008991  mov     [rsp+48h+var_10], r8
0x140008996  mov     edx, 0Ch
0x14000899b  mov     [rsp+48h+var_18], 0B2h
0x1400089a3  lea     r8, WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids
0x1400089aa  mov     r9, rbx
0x1400089ad  lea     eax, [rcx+1]
0x1400089b0  mov     [rsp+48h+var_20], eax
0x1400089b4  mov     [rsp+48h+var_28], ecx
0x1400089b8  call    WPP_SF_qddds
0x1400089bd  jmp     loc_14000892C
```
