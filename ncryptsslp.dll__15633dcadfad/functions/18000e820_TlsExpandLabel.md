# TlsExpandLabel

- ea: `0x18000e820`
- end: `0x18000eaed`
- name: `TlsExpandLabel`
- size: `717`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003050`
- `0x18000dea0`
- `0x180020718`

## callees

- `0x18000b594`
- `0x18000e820`
- `0x180020cb4`
- `0x180024fb0`

## import_xrefs

- `bcrypt!BCryptKeyDerivation` at `0x18000e9a5`
- `bcrypt!BCryptKeyDerivation` at `0x18000e9a5`
- `ntdll!RtlFreeHeap` at `0x18000ea40`
- `ntdll!RtlFreeHeap` at `0x18000ea40`
- `ntdll!RtlAllocateHeap` at `0x18000e90c`
- `ntdll!RtlAllocateHeap` at `0x18000e90c`

## string_xrefs

- `0x18000e9ce`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000ea92`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000eac3`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsExpandLabel(
        __int64 a1,
        const char *a2,
        const void *a3,
        unsigned __int8 a4,
        __int64 a5,
        unsigned __int16 a6)
{
  size_t v8; // r15
  int v9; // r8d
  unsigned __int8 v10; // r13
  SIZE_T v11; // rsi
  _BYTE *Heap; // rax
  int v13; // r8d
  _BYTE *v14; // rdi
  _BYTE *v15; // rdi
  unsigned int v16; // ebp
  int v17; // r8d
  _BYTE *v19; // rax
  int v20; // [rsp+44h] [rbp-74h] BYREF
  char v21; // [rsp+4Ah] [rbp-6Eh]
  PVOID P; // [rsp+50h] [rbp-68h]
  _DWORD v23[2]; // [rsp+58h] [rbp-60h] BYREF
  PVOID v24; // [rsp+60h] [rbp-58h]
  _DWORD v25[2]; // [rsp+68h] [rbp-50h] BYREF
  _DWORD *v26; // [rsp+70h] [rbp-48h]

  v21 = aTls13[6];
  v8 = a4;
  v23[1] = 20;
  v23[0] = 0;
  v10 = strnlen_s(a2, (size_t)a2);
  v24 = 0;
  v26 = v23;
  v25[0] = 0;
  v25[1] = 1;
  v20 = 0;
  if ( !a1 || v10 == 0xF9 )
    goto LABEL_20;
  if ( a3 )
  {
    if ( !(_BYTE)v8 )
      goto LABEL_20;
  }
  else if ( (_BYTE)v8 )
  {
    goto LABEL_20;
  }
  if ( a5 && a6 )
  {
    v11 = (unsigned __int16)(v8 + 4 + (unsigned __int8)(v10 + 6));
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
    P = Heap;
    if ( Heap )
    {
      Heap[2] = v10 + 6;
      Heap[1] = a6;
      *Heap = HIBYTE(a6);
      *(_DWORD *)(Heap + 3) = *(_DWORD *)"tls13 ";
      v14 = Heap + 9;
      *(_WORD *)(Heap + 7) = *(_WORD *)"3 ";
      memmove(Heap + 9, a2, v10);
      v14[v10] = v8;
      memmove(&v14[v10 + 1], a3, v8);
      v15 = P;
      v23[0] = v11;
      v24 = P;
      v16 = BCryptKeyDerivation(a1, v25, a5, a6, &v20, 0);
      if ( (v16 || v20 != a6)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          v17,
          (unsigned int)"Status",
          v16,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          195);
      }
      v19 = v15;
      do
      {
        *v19++ = 0;
        --v11;
      }
      while ( v11 );
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
      return v16;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          v13,
          (unsigned int)"Status",
          23,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          169);
      return 3221225495LL;
    }
  }
LABEL_20:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      v9,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      150);
  return 3221225485LL;
}

```

## disassembly

```asm
0x18000e820  mov     [rsp+Src], rdx
0x18000e825  mov     [rsp+arg_0], rcx
0x18000e82a  push    rbx
0x18000e82b  push    rbp
0x18000e82c  push    rdi
0x18000e82d  push    r12
0x18000e82f  push    r13
0x18000e831  push    r14
0x18000e833  push    r15
0x18000e835  sub     rsp, 80h
0x18000e83c  movzx   eax, word ptr cs:aTls13+4; "3 "
0x18000e843  mov     rbx, rcx
0x18000e846  mov     edi, dword ptr cs:aTls13; "tls13 "
0x18000e84c  mov     rcx, rdx; String
0x18000e84f  mov     [rsp+0B8h+var_78], ax
0x18000e854  mov     r12, r8
0x18000e857  movzx   eax, byte ptr cs:aTls13+6; ""
0x18000e85e  mov     [rsp+0B8h+var_6E], al
0x18000e862  movzx   r15d, r9b
0x18000e866  call    strnlen_s
0x18000e86b  xor     ecx, ecx
0x18000e86d  mov     [rsp+0B8h+var_5C], 14h
0x18000e875  mov     [rsp+0B8h+var_60], ecx
0x18000e879  mov     r13, rax
0x18000e87c  mov     [rsp+0B8h+var_58], rcx
0x18000e881  lea     rax, [rsp+0B8h+var_60]
0x18000e886  mov     [rsp+0B8h+var_48], rax
0x18000e88b  mov     [rsp+0B8h+var_50], ecx
0x18000e88f  mov     [rsp+0B8h+var_4C], 1
0x18000e897  mov     [rsp+0B8h+var_74], ecx
0x18000e89b  test    rbx, rbx
0x18000e89e  jz      loc_18000EA63
0x18000e8a4  lea     ebx, [r13+6]
0x18000e8a8  cmp     bl, 0FFh
0x18000e8ab  jnb     loc_18000EA63
0x18000e8b1  test    r12, r12
0x18000e8b4  jz      loc_18000EA83
0x18000e8ba  test    r15b, r15b
0x18000e8bd  jz      loc_18000EA63
0x18000e8c3  mov     r14, [rsp+0B8h+arg_20]
0x18000e8cb  test    r14, r14
0x18000e8ce  jz      loc_18000EA63
0x18000e8d4  movzx   ebp, [rsp+0B8h+arg_28]
0x18000e8dc  test    bp, bp
0x18000e8df  jz      loc_18000EA63
0x18000e8e5  movzx   ecx, bl
0x18000e8e8  lea     eax, [r15+4]
0x18000e8ec  add     cx, ax
0x18000e8ef  mov     [rsp+0B8h+arg_10], rsi
0x18000e8f7  movzx   esi, cx
0x18000e8fa  xor     edx, edx; Flags
0x18000e8fc  mov     rcx, gs:60h
0x18000e905  mov     r8d, esi; Size
0x18000e908  mov     rcx, [rcx+30h]; HeapHandle
0x18000e90c  call    cs:__imp_RtlAllocateHeap
0x18000e912  mov     [rsp+0B8h+P], rax
0x18000e917  mov     rcx, rax
0x18000e91a  test    rax, rax
0x18000e91d  jz      loc_18000E9F4
0x18000e923  mov     rdx, [rsp+0B8h+Src]; Src
0x18000e92b  movzx   eax, bp
0x18000e92e  mov     [rcx+2], bl
0x18000e931  mov     [rcx+1], bpl
0x18000e935  shr     ax, 8
0x18000e939  mov     [rcx], al
0x18000e93b  movzx   eax, [rsp+0B8h+var_78]
0x18000e940  mov     [rcx+3], edi
0x18000e943  lea     rdi, [rcx+9]
0x18000e947  mov     [rcx+7], ax
0x18000e94b  mov     rcx, rdi; void *
0x18000e94e  movzx   ebx, r13b
0x18000e952  mov     r8d, ebx; Size
0x18000e955  call    memmove
0x18000e95a  lea     rcx, [rdi+1]
0x18000e95e  mov     [rdi+rbx], r15b
0x18000e962  add     rcx, rbx; void *
0x18000e965  mov     r8, r15; Size
0x18000e968  mov     rdx, r12; Src
0x18000e96b  call    memmove
0x18000e970  mov     rdi, [rsp+0B8h+P]
0x18000e975  lea     rax, [rsp+0B8h+var_74]
0x18000e97a  mov     rcx, [rsp+0B8h+arg_0]
0x18000e982  lea     rdx, [rsp+0B8h+var_50]
0x18000e987  mov     dword ptr [rsp+0B8h+var_90], 0
0x18000e98f  mov     r9d, ebp
0x18000e992  mov     r8, r14
0x18000e995  mov     [rsp+0B8h+var_98], rax
0x18000e99a  mov     [rsp+0B8h+var_60], esi
0x18000e99e  mov     ebx, ebp
0x18000e9a0  mov     [rsp+0B8h+var_58], rdi
0x18000e9a5  call    cs:__imp_BCryptKeyDerivation
0x18000e9ab  mov     ebp, eax
0x18000e9ad  test    eax, eax
0x18000e9af  jz      short loc_18000EA18
0x18000e9b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9b8  lea     rax, WPP_GLOBAL_Control
0x18000e9bf  cmp     rcx, rax
0x18000e9c2  jz      short loc_18000EA1E
0x18000e9c4  test    byte ptr [rcx+1Ch], 1
0x18000e9c8  jz      short loc_18000EA1E
0x18000e9ca  mov     rcx, [rcx+10h]
0x18000e9ce  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e9d5  mov     [rsp+0B8h+var_88], 0FC3h
0x18000e9dd  lea     r9, aStatus; "Status"
0x18000e9e4  mov     [rsp+0B8h+var_90], rdx
0x18000e9e9  mov     dword ptr [rsp+0B8h+var_98], ebp
0x18000e9ed  call    WPP_SF_sDsd
0x18000e9f2  jmp     short loc_18000EA1E
0x18000e9f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9fb  lea     rax, WPP_GLOBAL_Control
0x18000ea02  cmp     rcx, rax
0x18000ea05  jz      short loc_18000EA11
0x18000ea07  test    byte ptr [rcx+1Ch], 1
0x18000ea0b  jnz     loc_18000EA8E
0x18000ea11  mov     eax, 0C0000017h
0x18000ea16  jmp     short loc_18000EA48
0x18000ea18  cmp     [rsp+0B8h+var_74], ebx
0x18000ea1c  jnz     short loc_18000E9B1
0x18000ea1e  mov     rax, rdi
0x18000ea21  mov     byte ptr [rax], 0
0x18000ea24  lea     rax, [rax+1]
0x18000ea28  sub     rsi, 1
0x18000ea2c  jnz     short loc_18000EA21
0x18000ea2e  mov     rcx, gs:60h
0x18000ea37  mov     r8, rdi; P
0x18000ea3a  xor     edx, edx; Flags
0x18000ea3c  mov     rcx, [rcx+30h]; HeapHandle
0x18000ea40  call    cs:__imp_RtlFreeHeap
0x18000ea46  mov     eax, ebp
0x18000ea48  mov     rsi, [rsp+0B8h+arg_10]
0x18000ea50  add     rsp, 80h
0x18000ea57  pop     r15
0x18000ea59  pop     r14
0x18000ea5b  pop     r13
0x18000ea5d  pop     r12
0x18000ea5f  pop     rdi
0x18000ea60  pop     rbp
0x18000ea61  pop     rbx
0x18000ea62  retn
0x18000ea63  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea6a  lea     rax, WPP_GLOBAL_Control
0x18000ea71  cmp     rcx, rax
0x18000ea74  jz      short loc_18000EA7C
0x18000ea76  test    byte ptr [rcx+1Ch], 1
0x18000ea7a  jnz     short loc_18000EABF
0x18000ea7c  mov     eax, 0C000000Dh
0x18000ea81  jmp     short loc_18000EA50
0x18000ea83  test    r15b, r15b
0x18000ea86  jz      loc_18000E8C3
0x18000ea8c  jmp     short loc_18000EA63
0x18000ea8e  mov     rcx, [rcx+10h]
0x18000ea92  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ea99  mov     [rsp+0B8h+var_88], 0FA9h
0x18000eaa1  lea     r9, aStatus; "Status"
0x18000eaa8  mov     [rsp+0B8h+var_90], rdx
0x18000eaad  mov     dword ptr [rsp+0B8h+var_98], 0C0000017h
0x18000eab5  call    WPP_SF_sDsd
0x18000eaba  jmp     loc_18000EA11
0x18000eabf  mov     rcx, [rcx+10h]
0x18000eac3  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000eaca  mov     [rsp+0B8h+var_88], 0F96h
0x18000ead2  lea     r9, aStatus; "Status"
0x18000ead9  mov     [rsp+0B8h+var_90], rdx
0x18000eade  mov     dword ptr [rsp+0B8h+var_98], 0C000000Dh
0x18000eae6  call    WPP_SF_sDsd
0x18000eaeb  jmp     short loc_18000EA7C
```
