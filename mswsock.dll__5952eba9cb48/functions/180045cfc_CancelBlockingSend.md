# CancelBlockingSend

- ea: `0x180045cfc`
- end: `0x180045e6e`
- name: `CancelBlockingSend`
- size: `370`
- prototype: `__int64 __fastcall(PVOID CompletionContext)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180040d78`

## callees

- `0x180008250`
- `0x180023cc0`
- `0x180045cfc`
- `0x1800462b0`
- `0x1800496e4`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045e51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045e51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045d1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045d1e`

## pseudocode

```c
void __fastcall CancelBlockingSend(char *CompletionContext, __int64 a2)
{
  __int64 v3; // rbx
  _BYTE *v4; // rax
  int v5; // ecx
  __int64 v6; // rdx
  __int64 v7; // r8
  _DWORD *v8; // rax
  PVOID *v9; // rdx
  _QWORD *v10; // rax
  __int64 v11; // rdx
  int v12; // [rsp+48h] [rbp+10h] BYREF
  int v13; // [rsp+4Ch] [rbp+14h]

  v13 = HIDWORD(a2);
  v12 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  if ( *((char **)CompletionContext + 50) != CompletionContext + 400 )
  {
    v3 = *((_QWORD *)CompletionContext + 51);
    v4 = CompletionContext + 801;
    v5 = *(_DWORD *)(v3 + 76) & 0x80;
    if ( (!v5 || (*v4 & 8) != 0) && !*(_DWORD *)(v3 + 20) )
    {
      *(_DWORD *)(v3 + 20) = 1;
      if ( (*v4 & 8) != 0 && v5 )
      {
        CompletionContext[800] |= 4u;
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, int *))(*((_QWORD *)CompletionContext + 2) + 328LL))(
          *((_QWORD *)CompletionContext + 13),
          *(_QWORD *)(*(_QWORD *)(v3 + 104) + 96LL),
          *(unsigned int *)(*((_QWORD *)CompletionContext + 2) + 20LL),
          &v12);
        if ( _InterlockedExchangeAdd(*((volatile signed __int32 **)CompletionContext + 1), 0xFFFFFFFF) == 1 )
          SockDestroySocket(*((_QWORD *)CompletionContext + 1), v6, v7);
        v8 = *(_DWORD **)(v3 + 104);
        *v8 = 1145324612;
        v9 = (PVOID *)*((_QWORD *)CompletionContext + 97);
        if ( *v9 != CompletionContext + 768 )
          __fastfail(3u);
        v10 = v8 + 10;
        v10[1] = v9;
        *v10 = CompletionContext + 768;
        *v9 = v10;
        *((_QWORD *)CompletionContext + 97) = v10;
        *(_QWORD *)(v3 + 104) = 0;
      }
      v11 = *(_QWORD *)(v3 + 120);
      *(_DWORD *)(v3 + 76) = 0;
      if ( v11 )
        IndicateRedirError(CompletionContext, v11, 258);
      else
        CompleteOverlappedIO(
          *(_QWORD *)(*(_QWORD *)CompletionContext + 8LL),
          *(_QWORD *)(v3 - 8),
          *(void **)(v3 + 48),
          *(void **)(v3 + 56),
          0x274Cu,
          *(_DWORD *)(v3 + 24));
      CheckBSQHeadForCompletion(CompletionContext);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
}

```

## disassembly

```asm
0x180045cfc  mov     rax, rsp
0x180045cff  mov     [rax+8], rbx
0x180045d03  mov     [rax+18h], rsi
0x180045d07  mov     [rax+10h], rdx
0x180045d0b  push    rdi
0x180045d0c  sub     rsp, 30h
0x180045d10  mov     rdi, rcx
0x180045d13  mov     dword ptr [rax+10h], 0
0x180045d1a  add     rcx, 30h ; '0'; lpCriticalSection
0x180045d1e  call    cs:__imp_EnterCriticalSection
0x180045d25  nop     dword ptr [rax+rax+00h]
0x180045d2a  lea     rax, [rdi+190h]
0x180045d31  cmp     [rax], rax
0x180045d34  jz      loc_180045E4D
0x180045d3a  mov     rbx, [rdi+198h]
0x180045d41  lea     rax, [rdi+321h]
0x180045d48  mov     ecx, [rbx+4Ch]
0x180045d4b  and     ecx, 80h
0x180045d51  jz      short loc_180045D5C
0x180045d53  test    byte ptr [rax], 8
0x180045d56  jz      loc_180045E4D
0x180045d5c  cmp     dword ptr [rbx+14h], 0
0x180045d60  jnz     loc_180045E4D
0x180045d66  mov     dword ptr [rbx+14h], 1
0x180045d6d  test    byte ptr [rax], 8
0x180045d70  jz      loc_180045DFE
0x180045d76  test    ecx, ecx
0x180045d78  jz      loc_180045DFE
0x180045d7e  or      byte ptr [rdi+320h], 4
0x180045d85  lea     r9, [rsp+38h+arg_8]
0x180045d8a  mov     r8, [rdi+10h]
0x180045d8e  mov     rdx, [rbx+68h]
0x180045d92  mov     rcx, [rdi+68h]
0x180045d96  mov     rax, [r8+148h]
0x180045d9d  mov     r8d, [r8+14h]
0x180045da1  mov     rdx, [rdx+60h]
0x180045da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045daa  mov     rcx, [rdi+8]
0x180045dae  or      eax, 0FFFFFFFFh
0x180045db1  lock xadd [rcx], eax
0x180045db5  cmp     eax, 1
0x180045db8  jnz     short loc_180045DC3
0x180045dba  mov     rcx, [rdi+8]
0x180045dbe  call    SockDestroySocket
0x180045dc3  mov     rax, [rbx+68h]
0x180045dc7  lea     rcx, [rdi+300h]
0x180045dce  mov     dword ptr [rax], 44444444h
0x180045dd4  mov     rdx, [rcx+8]
0x180045dd8  cmp     [rdx], rcx
0x180045ddb  jz      short loc_180045DE4
0x180045ddd  mov     ecx, 3
0x180045de2  int     29h; Win8: RtlFailFast(ecx)
0x180045de4  add     rax, 28h ; '('
0x180045de8  mov     [rax+8], rdx
0x180045dec  mov     [rax], rcx
0x180045def  mov     [rdx], rax
0x180045df2  mov     [rcx+8], rax
0x180045df6  mov     qword ptr [rbx+68h], 0
0x180045dfe  mov     rdx, [rbx+78h]
0x180045e02  mov     dword ptr [rbx+4Ch], 0
0x180045e09  test    rdx, rdx
0x180045e0c  jz      short loc_180045E1E
0x180045e0e  mov     r8d, 102h
0x180045e14  mov     rcx, rdi
0x180045e17  call    IndicateRedirError
0x180045e1c  jmp     short loc_180045E45
0x180045e1e  mov     rcx, [rdi]
0x180045e21  mov     eax, [rbx+18h]
0x180045e24  mov     r9, [rbx+38h]
0x180045e28  mov     r8, [rbx+30h]
0x180045e2c  mov     rcx, [rcx+8]
0x180045e30  mov     rdx, [rbx-8]
0x180045e34  mov     [rsp+38h+var_10], eax
0x180045e38  mov     [rsp+38h+var_18], 274Ch
0x180045e40  call    CompleteOverlappedIO
0x180045e45  mov     rcx, rdi; CompletionContext
0x180045e48  call    CheckBSQHeadForCompletion
0x180045e4d  lea     rcx, [rdi+30h]; lpCriticalSection
0x180045e51  call    cs:__imp_LeaveCriticalSection
0x180045e58  nop     dword ptr [rax+rax+00h]
0x180045e5d  mov     rbx, [rsp+38h+arg_0]
0x180045e62  mov     rsi, [rsp+38h+arg_10]
0x180045e67  add     rsp, 30h
0x180045e6b  pop     rdi
0x180045e6c  retn
```
