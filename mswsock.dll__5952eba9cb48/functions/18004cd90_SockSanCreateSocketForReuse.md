# SockSanCreateSocketForReuse

- ea: `0x18004cd90`
- end: `0x18004ced2`
- name: `SockSanCreateSocketForReuse`
- size: `322`
- prototype: `__int64 __fastcall(PVOID CompletionContext)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180044bc8`

## callees

- `0x180042b50`
- `0x18004cd90`
- `0x18004e718`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004cdce`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004cdce`

## pseudocode

```c
__int64 __fastcall SockSanCreateSocketForReuse(
        volatile signed __int32 *CompletionContext,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  __int64 v4; // rdi
  _QWORD *Value; // rsi
  __int64 *v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 result; // rax
  unsigned int v14; // [rsp+70h] [rbp+8h] BYREF
  int v15; // [rsp+78h] [rbp+10h] BYREF

  v4 = *(_QWORD *)(a2 + 264);
  v14 = 0;
  v15 = 0;
  Value = TlsGetValue(MSAFD_SockTlsSlot);
  _InterlockedIncrement(CompletionContext + 4);
  *(_QWORD *)(v4 + 16) = CompletionContext;
  v10 = SockTcpProviderInfo;
  *(_DWORD *)(v4 + 156) = -1;
  Value[3] = v4;
  v11 = *(unsigned int *)(a2 + 28);
  if ( (_DWORD)v11 != 2 )
    v10 = SockTcp6ProviderInfo;
  v12 = (*((__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *, _DWORD, unsigned int, unsigned int *))CompletionContext
         + 36))(
          v11,
          *(unsigned int *)(a2 + 32),
          *(unsigned int *)(a2 + 36),
          v10,
          *(_DWORD *)(a2 + 88),
          *(_DWORD *)(a2 + 72) | 1u,
          &v14);
  *(_QWORD *)(v4 + 104) = v12;
  if ( v12 != -1 )
  {
    if ( (*((unsigned int (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))CompletionContext + 11))(
           v12,
           a3,
           a4,
           &v14) != -1 )
    {
      result = SockSanSetSockOpts(a2);
      if ( !(_DWORD)result )
      {
        Value[3] = -1;
        return result;
      }
    }
    (*((void (__fastcall **)(_QWORD, int *))CompletionContext + 14))(*(_QWORD *)(v4 + 104), &v15);
  }
  Value[3] = -1;
  *(_QWORD *)(v4 + 104) = -1;
  *(_QWORD *)(v4 + 16) = 0;
  if ( _InterlockedExchangeAdd(CompletionContext + 4, 0xFFFFFFFF) == 1 )
    SockSanFreeProvider((PVOID)CompletionContext);
  result = v14;
  if ( !v14 )
    return 10107;
  return result;
}

```

## disassembly

```asm
0x18004cd90  mov     rax, rsp
0x18004cd93  mov     [rax+18h], rbx
0x18004cd97  mov     [rax+20h], rbp
0x18004cd9b  push    rsi
0x18004cd9c  push    rdi
0x18004cd9d  push    r12
0x18004cd9f  push    r14
0x18004cda1  push    r15
0x18004cda3  sub     rsp, 40h
0x18004cda7  mov     rdi, [rdx+108h]
0x18004cdae  mov     rbx, rcx
0x18004cdb1  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x18004cdb7  mov     r14d, r9d
0x18004cdba  mov     r15, r8
0x18004cdbd  mov     dword ptr [rax+8], 0
0x18004cdc4  mov     rbp, rdx
0x18004cdc7  mov     dword ptr [rax+10h], 0
0x18004cdce  call    cs:__imp_TlsGetValue
0x18004cdd5  nop     dword ptr [rax+rax+00h]
0x18004cdda  mov     rsi, rax
0x18004cddd  lock inc dword ptr [rbx+10h]
0x18004cde1  mov     [rdi+10h], rbx
0x18004cde5  lea     r9, SockTcpProviderInfo
0x18004cdec  mov     dword ptr [rdi+9Ch], 0FFFFFFFFh
0x18004cdf6  mov     [rax+18h], rdi
0x18004cdfa  lea     rax, SockTcp6ProviderInfo
0x18004ce01  mov     edx, [rbp+48h]
0x18004ce04  mov     ecx, [rbp+1Ch]
0x18004ce07  or      edx, 1
0x18004ce0a  mov     r8d, [rbp+24h]
0x18004ce0e  cmp     ecx, 2
0x18004ce11  cmovnz  r9, rax
0x18004ce15  lea     rax, [rsp+68h+arg_0]
0x18004ce1a  mov     [rsp+68h+var_38], rax
0x18004ce1f  mov     rax, [rbx+120h]
0x18004ce26  mov     [rsp+68h+var_40], edx
0x18004ce2a  mov     edx, [rbp+58h]
0x18004ce2d  mov     [rsp+68h+var_48], edx
0x18004ce31  mov     edx, [rbp+20h]
0x18004ce34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce39  or      r12, 0FFFFFFFFFFFFFFFFh
0x18004ce3d  mov     [rdi+68h], rax
0x18004ce41  cmp     rax, r12
0x18004ce44  jz      short loc_18004CE86
0x18004ce46  mov     rcx, rax
0x18004ce49  lea     r9, [rsp+68h+arg_0]
0x18004ce4e  mov     rax, [rbx+58h]
0x18004ce52  mov     r8d, r14d
0x18004ce55  mov     rdx, r15
0x18004ce58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce5d  cmp     eax, r12d
0x18004ce60  jz      short loc_18004CE74
0x18004ce62  mov     rcx, rbp
0x18004ce65  call    SockSanSetSockOpts
0x18004ce6a  test    eax, eax
0x18004ce6c  jnz     short loc_18004CE74
0x18004ce6e  mov     [rsi+18h], r12
0x18004ce72  jmp     short loc_18004CEB8
0x18004ce74  mov     rcx, [rdi+68h]
0x18004ce78  lea     rdx, [rsp+68h+arg_8]
0x18004ce7d  mov     rax, [rbx+70h]
0x18004ce81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce86  mov     [rsi+18h], r12
0x18004ce8a  mov     eax, r12d
0x18004ce8d  mov     [rdi+68h], r12
0x18004ce91  mov     qword ptr [rdi+10h], 0
0x18004ce99  lock xadd [rbx+10h], eax
0x18004ce9e  add     eax, r12d
0x18004cea1  jnz     short loc_18004CEAB
0x18004cea3  mov     rcx, rbx; CompletionContext
0x18004cea6  call    SockSanFreeProvider
0x18004ceab  mov     eax, [rsp+68h+arg_0]
0x18004ceaf  test    eax, eax
0x18004ceb1  jnz     short loc_18004CEB8
0x18004ceb3  mov     eax, 277Bh
0x18004ceb8  lea     r11, [rsp+68h+var_28]
0x18004cebd  mov     rbx, [r11+40h]
0x18004cec1  mov     rbp, [r11+48h]
0x18004cec5  mov     rsp, r11
0x18004cec8  pop     r15
0x18004ceca  pop     r14
0x18004cecc  pop     r12
0x18004cece  pop     rdi
0x18004cecf  pop     rsi
0x18004ced0  retn
```
