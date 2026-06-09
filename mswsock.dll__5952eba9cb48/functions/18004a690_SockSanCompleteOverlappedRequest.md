# SockSanCompleteOverlappedRequest

- ea: `0x18004a690`
- end: `0x18004a7b3`
- name: `SockSanCompleteOverlappedRequest`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180005f78`
- `0x180038104`
- `0x18004a520`
- `0x18004a690`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004a6bf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004a712`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004a6bf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004a712`

## pseudocode

```c
__int64 __fastcall SockSanCompleteOverlappedRequest(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        _DWORD *a5)
{
  DWORD v5; // ecx
  LPVOID Value; // rbx
  int v11; // eax
  __int64 v12; // r9
  int v13; // ecx
  __int64 v14; // rax
  unsigned int v15; // edx
  unsigned int v16; // r8d
  __int64 v17; // rcx
  int v18; // [rsp+60h] [rbp+18h] BYREF

  v5 = MSAFD_SockTlsSlot;
  *(_QWORD *)(a2 + 8) = a4;
  v18 = 0;
  *(_QWORD *)a2 = 0;
  *(_DWORD *)(a2 + 20) = a3;
  Value = TlsGetValue(v5);
  if ( !Value )
  {
    if ( !(unsigned int)MSAFD_SockThreadInitialize() )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_(1025, 11, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids);
      *a5 = 10055;
      return 0xFFFFFFFFLL;
    }
    Value = TlsGetValue(MSAFD_SockTlsSlot);
  }
  v11 = *((_DWORD *)Value + 10);
  if ( v11 == 4 )
  {
    *(_DWORD *)(a2 + 16) = a4;
    if ( *((_QWORD *)Value + 6) )
      **((_QWORD **)Value + 7) = a2;
    else
      *((_QWORD *)Value + 6) = a2;
    *((_QWORD *)Value + 7) = a2;
    *(_QWORD *)a2 = 0;
  }
  else
  {
    v12 = (__int64)a5;
    *((_DWORD *)Value + 10) = v11 + 1;
    SanOverlappedCompletionAux(a2, a3, a4, v12);
    v13 = *((_DWORD *)Value + 10);
    *((_DWORD *)Value + 10) = v13 - 1;
    if ( v13 == 1 )
    {
      *((_DWORD *)Value + 10) = 1;
      while ( 1 )
      {
        v17 = *((_QWORD *)Value + 6);
        if ( !v17 )
          break;
        *((_QWORD *)Value + 6) = *(_QWORD *)v17;
        v14 = *(unsigned int *)(v17 + 16);
        v15 = *(_DWORD *)(v17 + 20);
        v16 = *(_DWORD *)(v17 + 16);
        *(_QWORD *)v17 = 0;
        *(_QWORD *)(v17 + 8) = v14;
        SanOverlappedCompletionAux(v17, v15, v16, (__int64)&v18);
      }
      --*((_DWORD *)Value + 10);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004a690  push    rbx
0x18004a692  push    rbp
0x18004a693  push    rsi
0x18004a694  push    rdi
0x18004a695  sub     rsp, 28h
0x18004a699  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x18004a69f  mov     ebp, r8d
0x18004a6a2  mov     esi, r9d
0x18004a6a5  mov     rdi, rdx
0x18004a6a8  mov     [rdx+8], rsi
0x18004a6ac  mov     [rsp+48h+arg_10], 0
0x18004a6b4  mov     qword ptr [rdx], 0
0x18004a6bb  mov     [rdx+14h], r8d
0x18004a6bf  call    cs:__imp_TlsGetValue
0x18004a6c6  nop     dword ptr [rax+rax+00h]
0x18004a6cb  mov     rbx, rax
0x18004a6ce  test    rax, rax
0x18004a6d1  jnz     short loc_18004A721
0x18004a6d3  call    MSAFD_SockThreadInitialize
0x18004a6d8  test    eax, eax
0x18004a6da  jnz     short loc_18004A70C
0x18004a6dc  test    byte ptr cs:xmmword_180063D60, 2
0x18004a6e3  jz      short loc_18004A6F9
0x18004a6e5  lea     edx, [rbx+0Bh]
0x18004a6e8  mov     ecx, 401h
0x18004a6ed  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18004a6f4  call    WPP_SF_
0x18004a6f9  mov     rax, [rsp+48h+arg_20]
0x18004a6fe  mov     dword ptr [rax], 2747h
0x18004a704  or      eax, 0FFFFFFFFh
0x18004a707  jmp     loc_18004A7A9
0x18004a70c  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x18004a712  call    cs:__imp_TlsGetValue
0x18004a719  nop     dword ptr [rax+rax+00h]
0x18004a71e  mov     rbx, rax
0x18004a721  mov     eax, [rbx+28h]
0x18004a724  cmp     eax, 4
0x18004a727  jnz     short loc_18004A74D
0x18004a729  mov     [rdi+10h], esi
0x18004a72c  cmp     qword ptr [rbx+30h], 0
0x18004a731  jnz     short loc_18004A739
0x18004a733  mov     [rbx+30h], rdi
0x18004a737  jmp     short loc_18004A740
0x18004a739  mov     rax, [rbx+38h]
0x18004a73d  mov     [rax], rdi
0x18004a740  mov     [rbx+38h], rdi
0x18004a744  mov     qword ptr [rdi], 0
0x18004a74b  jmp     short loc_18004A7A7
0x18004a74d  mov     r9, [rsp+48h+arg_20]
0x18004a752  inc     eax
0x18004a754  mov     r8d, esi
0x18004a757  mov     [rbx+28h], eax
0x18004a75a  mov     edx, ebp
0x18004a75c  mov     rcx, rdi
0x18004a75f  call    SanOverlappedCompletionAux
0x18004a764  mov     ecx, [rbx+28h]
0x18004a767  lea     eax, [rcx-1]
0x18004a76a  mov     [rbx+28h], eax
0x18004a76d  test    eax, eax
0x18004a76f  jnz     short loc_18004A7A7
0x18004a771  mov     [rbx+28h], ecx
0x18004a774  jmp     short loc_18004A79B
0x18004a776  mov     rax, [rcx]
0x18004a779  lea     r9, [rsp+48h+arg_10]
0x18004a77e  mov     [rbx+30h], rax
0x18004a782  mov     eax, [rcx+10h]
0x18004a785  mov     edx, [rcx+14h]
0x18004a788  mov     r8d, eax
0x18004a78b  mov     qword ptr [rcx], 0
0x18004a792  mov     [rcx+8], rax
0x18004a796  call    SanOverlappedCompletionAux
0x18004a79b  mov     rcx, [rbx+30h]
0x18004a79f  test    rcx, rcx
0x18004a7a2  jnz     short loc_18004A776
0x18004a7a4  dec     dword ptr [rbx+28h]
0x18004a7a7  xor     eax, eax
0x18004a7a9  add     rsp, 28h
0x18004a7ad  pop     rdi
0x18004a7ae  pop     rsi
0x18004a7af  pop     rbp
0x18004a7b0  pop     rbx
0x18004a7b1  retn
```
