# UMRxFreeSecondaryBuffer

- ea: `0x140027a20`
- end: `0x140027ba6`
- name: `UMRxFreeSecondaryBuffer`
- size: `390`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `13`
- callee_count: `4`
- tags: ``

## callers

- `0x140005030`
- `0x140011a20`
- `0x140014e00`
- `0x140015900`
- `0x140015c30`
- `0x14001a6f0`
- `0x14001aa30`
- `0x14001bdf0`
- `0x14001c3a0`
- `0x14001e6a0`
- `0x1400214d0`
- `0x140021720`
- `0x140021a50`

## callees

- `0x14000163c`
- `0x140001838`
- `0x140001b64`
- `0x140027a20`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140027a67`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027aa3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027b1d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027a67`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027aa3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027b1d`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x140027b62`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x140027b62`

## pseudocode

```c
__int64 __fastcall UMRxFreeSecondaryBuffer(__int64 a1, void *a2)
{
  unsigned int v3; // r14d
  __int64 v4; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v6; // rbx
  HANDLE v7; // rax
  unsigned int v8; // ecx
  unsigned int v9; // esi
  __int64 v10; // rbx
  HANDLE v11; // rax
  NTSTATUS v12; // eax
  ULONG_PTR RegionSize; // [rsp+60h] [rbp+8h] BYREF
  PVOID BaseAddress; // [rsp+68h] [rbp+10h] BYREF

  BaseAddress = a2;
  RegionSize = 0;
  v3 = -1073741811;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v4, 112, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_qqq(v6, 113, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v7, a1, BaseAddress);
    }
  }
  v8 = *(_DWORD *)(a1 + 224);
  v9 = 0;
  if ( v8 )
  {
    while ( BaseAddress != *(PVOID *)(a1 + 16LL * v9 + 232) )
    {
      if ( ++v9 >= v8 )
        return v3;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) != 0 )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v11 = PsGetCurrentThreadId();
      WPP_SF_qqD(v10, 114, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v11, BaseAddress, v9);
    }
    v12 = ZwFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, &RegionSize, 0x8000u);
    --*(_DWORD *)(a1 + 224);
    v3 = v12;
    *(_OWORD *)(a1 + 16LL * v9 + 232) = *(_OWORD *)(a1 + 16LL * *(unsigned int *)(a1 + 224) + 232);
  }
  return v3;
}

```

## disassembly

```asm
0x140027a20  mov     [rsp+arg_10], rbx
0x140027a25  mov     [rsp+BaseAddress], rdx
0x140027a2a  push    rbp
0x140027a2b  push    rsi
0x140027a2c  push    rdi
0x140027a2d  push    r14
0x140027a2f  push    r15
0x140027a31  sub     rsp, 30h
0x140027a35  mov     rdi, rcx
0x140027a38  mov     [rsp+58h+RegionSize], 0
0x140027a41  mov     r14d, 0C000000Dh
0x140027a47  mov     rbx, cs:WPP_GLOBAL_Control
0x140027a4e  lea     r15, WPP_GLOBAL_Control
0x140027a55  cmp     rbx, r15
0x140027a58  jz      short loc_140027AD5
0x140027a5a  test    dword ptr [rbx+2Ch], 400h
0x140027a61  jz      short loc_140027A8A
0x140027a63  mov     rbx, [rbx+18h]
0x140027a67  call    cs:__imp_PsGetCurrentThreadId
0x140027a6e  nop     dword ptr [rax+rax+00h]
0x140027a73  mov     edx, 70h ; 'p'
0x140027a78  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027a7f  mov     r9, rax
0x140027a82  mov     rcx, rbx
0x140027a85  call    WPP_SF_q
0x140027a8a  mov     rbx, cs:WPP_GLOBAL_Control
0x140027a91  cmp     rbx, r15
0x140027a94  jz      short loc_140027AD5
0x140027a96  test    dword ptr [rbx+2Ch], 200h
0x140027a9d  jz      short loc_140027AD5
0x140027a9f  mov     rbx, [rbx+18h]
0x140027aa3  call    cs:__imp_PsGetCurrentThreadId
0x140027aaa  nop     dword ptr [rax+rax+00h]
0x140027aaf  mov     edx, 71h ; 'q'
0x140027ab4  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027abb  mov     r9, rax
0x140027abe  mov     rcx, rbx
0x140027ac1  mov     rax, [rsp+58h+BaseAddress]
0x140027ac6  mov     [rsp+58h+var_30], rax
0x140027acb  mov     [rsp+58h+var_38], rdi
0x140027ad0  call    WPP_SF_qqq
0x140027ad5  mov     ecx, [rdi+0E0h]
0x140027adb  xor     esi, esi
0x140027add  test    ecx, ecx
0x140027adf  jz      loc_140027B91
0x140027ae5  mov     ebp, esi
0x140027ae7  add     rbp, rbp
0x140027aea  mov     rax, [rdi+rbp*8+0E8h]
0x140027af2  cmp     [rsp+58h+BaseAddress], rax
0x140027af7  jz      short loc_140027B04
0x140027af9  inc     esi
0x140027afb  cmp     esi, ecx
0x140027afd  jb      short loc_140027AE5
0x140027aff  jmp     loc_140027B91
0x140027b04  mov     rbx, cs:WPP_GLOBAL_Control
0x140027b0b  cmp     rbx, r15
0x140027b0e  jz      short loc_140027B4E
0x140027b10  test    dword ptr [rbx+2Ch], 400h
0x140027b17  jz      short loc_140027B4E
0x140027b19  mov     rbx, [rbx+18h]
0x140027b1d  call    cs:__imp_PsGetCurrentThreadId
0x140027b24  nop     dword ptr [rax+rax+00h]
0x140027b29  mov     edx, 72h ; 'r'
0x140027b2e  mov     dword ptr [rsp+58h+var_30], esi
0x140027b32  mov     r9, rax
0x140027b35  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027b3c  mov     rax, [rsp+58h+BaseAddress]
0x140027b41  mov     rcx, rbx
0x140027b44  mov     [rsp+58h+var_38], rax
0x140027b49  call    WPP_SF_qqD
0x140027b4e  mov     r9d, 8000h; FreeType
0x140027b54  lea     r8, [rsp+58h+RegionSize]; RegionSize
0x140027b59  lea     rdx, [rsp+58h+BaseAddress]; BaseAddress
0x140027b5e  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140027b62  call    cs:__imp_ZwFreeVirtualMemory
0x140027b69  nop     dword ptr [rax+rax+00h]
0x140027b6e  dec     dword ptr [rdi+0E0h]
0x140027b74  mov     r14d, eax
0x140027b77  mov     ecx, [rdi+0E0h]
0x140027b7d  add     rcx, rcx
0x140027b80  movups  xmm0, xmmword ptr [rdi+rcx*8+0E8h]
0x140027b88  movdqu  xmmword ptr [rdi+rbp*8+0E8h], xmm0
0x140027b91  mov     rbx, [rsp+58h+arg_10]
0x140027b96  mov     eax, r14d
0x140027b99  add     rsp, 30h
0x140027b9d  pop     r15
0x140027b9f  pop     r14
0x140027ba1  pop     rdi
0x140027ba2  pop     rsi
0x140027ba3  pop     rbp
0x140027ba4  retn
```
