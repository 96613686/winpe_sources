# DeleteQMPolicyInformation

- ea: `0x18002b9a8`
- end: `0x18002ba3b`
- name: `DeleteQMPolicyInformation`
- size: `147`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180001710`
- `0x18000acb4`
- `0x18000b29c`

## callees

- `0x18000e510`
- `0x180028b2c`
- `0x180029d48`
- `0x18002b9a8`

## pseudocode

```c
__int64 __fastcall DeleteQMPolicyInformation(__int64 a1)
{
  unsigned int v2; // edi
  __int64 v3; // rsi
  __int64 i; // rbx
  unsigned int v5; // eax
  __int128 v7; // [rsp+20h] [rbp-18h] BYREF

  PADeleteQMFilters(*(_QWORD *)(a1 + 32), *(unsigned int *)(a1 + 40));
  v2 = *(_DWORD *)(a1 + 40);
  v3 = *(_QWORD *)(a1 + 32);
  for ( i = 0; (unsigned int)i < v2; i = (unsigned int)(i + 1) )
  {
    v7 = *(_OWORD *)*(_QWORD *)(*(_QWORD *)(v3 + 8 * i) + 104LL);
    v5 = PADeleteQMPolicy(&v7);
    if ( v5
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_23b1f3110213325002571ebd730d21df_Traceguids, v5);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002b9a8  mov     [rsp+arg_0], rbx
0x18002b9ad  mov     [rsp+arg_8], rsi
0x18002b9b2  push    rdi
0x18002b9b3  sub     rsp, 30h
0x18002b9b7  mov     edx, [rcx+28h]
0x18002b9ba  mov     rbx, rcx
0x18002b9bd  mov     rcx, [rcx+20h]
0x18002b9c1  call    PADeleteQMFilters
0x18002b9c6  mov     edi, [rbx+28h]
0x18002b9c9  mov     rsi, [rbx+20h]
0x18002b9cd  xor     ebx, ebx
0x18002b9cf  test    edi, edi
0x18002b9d1  jz      short loc_18002BA29
0x18002b9d3  mov     rcx, [rsi+rbx*8]
0x18002b9d7  mov     rax, [rcx+68h]
0x18002b9db  lea     rcx, [rsp+38h+var_18]
0x18002b9e0  movups  xmm0, xmmword ptr [rax]
0x18002b9e3  movdqu  [rsp+38h+var_18], xmm0
0x18002b9e9  call    PADeleteQMPolicy
0x18002b9ee  test    eax, eax
0x18002b9f0  jz      short loc_18002BA23
0x18002b9f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9f9  lea     rdx, WPP_GLOBAL_Control
0x18002ba00  cmp     rcx, rdx
0x18002ba03  jz      short loc_18002BA23
0x18002ba05  test    byte ptr [rcx+1Ch], 10h
0x18002ba09  jz      short loc_18002BA23
0x18002ba0b  mov     rcx, [rcx+10h]
0x18002ba0f  lea     r8, WPP_23b1f3110213325002571ebd730d21df_Traceguids
0x18002ba16  mov     edx, 1Bh
0x18002ba1b  mov     r9d, eax
0x18002ba1e  call    WPP_SF_d
0x18002ba23  inc     ebx
0x18002ba25  cmp     ebx, edi
0x18002ba27  jb      short loc_18002B9D3
0x18002ba29  mov     rbx, [rsp+38h+arg_0]
0x18002ba2e  xor     eax, eax
0x18002ba30  mov     rsi, [rsp+38h+arg_8]
0x18002ba35  add     rsp, 30h
0x18002ba39  pop     rdi
0x18002ba3a  retn
```
