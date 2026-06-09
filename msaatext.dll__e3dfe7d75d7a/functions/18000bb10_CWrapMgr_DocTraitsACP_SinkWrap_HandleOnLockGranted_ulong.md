# CWrapMgr<DocTraitsACP>::SinkWrap_HandleOnLockGranted(ulong)

- ea: `0x18000bb10`
- end: `0x18000bd17`
- name: `?SinkWrap_HandleOnLockGranted@?$CWrapMgr@VDocTraitsACP@@@@QEAAJK@Z`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009ae0`

## callees

- `0x1800026d0`
- `0x18000bb10`
- `0x180014010`

## string_xrefs

- `0x18000bb40`: `( dwLockFlags & ~ ( TS_LF_SYNC | TS_LF_READ | TS_LF_READWRITE ) ) == 0`
- `0x18000bc4e`: `! ( m_dwPendingLock & TS_LF_READWRITE ) || ( dwLockFlags & TS_LF_READWRITE )`
- `0x18000bcd6`: `Write lock requested while holding read lock - not implemented yet`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWrapMgr<DocTraitsACP>::SinkWrap_HandleOnLockGranted(__int64 a1, unsigned int a2)
{
  _DWORD *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 result; // rax
  int v9; // r14d
  int v10; // ecx
  __int64 i; // rdi
  int v12; // edx
  int v13; // [rsp+20h] [rbp-48h]

  if ( (a2 & 0xFFFFFFF8) != 0 )
    InternalTrace(
      L"windows\\oleacc\\msaatext\\docwrap.cpp",
      0x253u,
      8u,
      0,
      v13,
      0,
      (wchar_t *)L"( dwLockFlags & ~ ( TS_LF_SYNC | TS_LF_READ | TS_LF_READWRITE ) ) == 0");
  v4 = (_DWORD *)(a1 + 72);
  ++*(_DWORD *)(a1 + 72);
  if ( *(_DWORD *)(a1 + 32) )
  {
    if ( (a2 & 1) == 0 )
      InternalTrace(
        L"windows\\oleacc\\msaatext\\docwrap.cpp",
        0x25Au,
        8u,
        0,
        v13,
        0,
        (wchar_t *)L"dwLockFlags & TS_LF_SYNC");
    v5 = *(_QWORD *)(a1 + 24);
    if ( !v5 || !*(_QWORD *)(v5 + 112) )
      InternalTrace(
        L"windows\\oleacc\\msaatext\\docwrap.cpp",
        0x25Bu,
        8u,
        0,
        v13,
        0,
        (wchar_t *)L"m_pLockRequestedBy && m_pLockRequestedBy->m_Sink.m_pSink");
    v6 = *(_QWORD *)(a1 + 24);
    if ( v6 && (v7 = *(_QWORD *)(v6 + 112)) != 0 )
    {
      result = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 64LL))(v7, a2);
      --*v4;
    }
    else
    {
      --*v4;
      return 2147549183LL;
    }
  }
  else
  {
    if ( (a2 & 1) != 0 )
      InternalTrace(
        L"windows\\oleacc\\msaatext\\docwrap.cpp",
        0x268u,
        8u,
        0,
        v13,
        0,
        (wchar_t *)L"! ( dwLockFlags & TS_LF_SYNC )");
    if ( (*(_BYTE *)(a1 + 36) & 6) != 0 && (a2 & 6) == 0 )
      InternalTrace(
        L"windows\\oleacc\\msaatext\\docwrap.cpp",
        0x26Bu,
        8u,
        0,
        v13,
        0,
        (wchar_t *)L"! ( m_dwPendingLock & TS_LF_READWRITE ) || ( dwLockFlags & TS_LF_READWRITE )");
    *(_DWORD *)(a1 + 36) = 0;
    v9 = 0;
    do
    {
      v10 = 0;
      for ( i = *(_QWORD *)(a1 + 56); i; i = *(_QWORD *)(i + 8) )
      {
        v12 = *(_DWORD *)(i + 16);
        if ( v12 )
        {
          if ( (a2 | v12) == a2 )
          {
            *(_DWORD *)(i + 20) = v12;
            *(_DWORD *)(i + 16) = 0;
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(i + 24) + 64LL))(*(_QWORD *)(i + 24));
            *(_DWORD *)(i + 20) = 0;
            v10 = 1;
          }
          else
          {
            v9 = 1;
          }
        }
      }
    }
    while ( v10 );
    if ( v9 )
      InternalTrace(
        L"windows\\oleacc\\msaatext\\docwrap.cpp",
        0x2ACu,
        8u,
        0,
        v13,
        0,
        (wchar_t *)L"Write lock requested while holding read lock - not implemented yet");
    --*v4;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000bb10  mov     [rsp+arg_8], rbx
0x18000bb15  mov     [rsp+arg_10], rbp
0x18000bb1a  push    rsi
0x18000bb1b  push    rdi
0x18000bb1c  push    r12
0x18000bb1e  push    r13
0x18000bb20  push    r14
0x18000bb22  sub     rsp, 40h
0x18000bb26  mov     ebp, edx
0x18000bb28  mov     rsi, rcx
0x18000bb2b  mov     r12d, 8
0x18000bb31  lea     r13, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x18000bb38  test    edx, 0FFFFFFF8h
0x18000bb3e  jz      short loc_18000BB67
0x18000bb40  lea     rax, aDwlockflagsTsL_1; "( dwLockFlags & ~ ( TS_LF_SYNC | TS_LF_"...
0x18000bb47  mov     [rsp+68h+var_38], rax; __int64
0x18000bb4c  mov     [rsp+68h+var_40], 0; int
0x18000bb54  xor     r9d, r9d
0x18000bb57  mov     r8d, r12d
0x18000bb5a  mov     edx, 253h; Value
0x18000bb5f  mov     rcx, r13; unsigned __int16 *
0x18000bb62  call    InternalTrace
0x18000bb67  lea     rbx, [rsi+48h]
0x18000bb6b  mov     [rsp+68h+arg_0], rbx
0x18000bb70  inc     dword ptr [rbx]
0x18000bb72  mov     eax, ebp
0x18000bb74  and     eax, 1
0x18000bb77  cmp     dword ptr [rsi+20h], 0
0x18000bb7b  jz      loc_18000BC17
0x18000bb81  test    eax, eax
0x18000bb83  jnz     short loc_18000BBAC
0x18000bb85  lea     rax, aDwlockflagsTsL; "dwLockFlags & TS_LF_SYNC"
0x18000bb8c  mov     [rsp+68h+var_38], rax; __int64
0x18000bb91  mov     [rsp+68h+var_40], 0; int
0x18000bb99  xor     r9d, r9d
0x18000bb9c  mov     r8d, r12d
0x18000bb9f  mov     edx, 25Ah; Value
0x18000bba4  mov     rcx, r13; unsigned __int16 *
0x18000bba7  call    InternalTrace
0x18000bbac  mov     rax, [rsi+18h]
0x18000bbb0  test    rax, rax
0x18000bbb3  jz      short loc_18000BBBC
0x18000bbb5  cmp     qword ptr [rax+70h], 0
0x18000bbba  jnz     short loc_18000BBE3
0x18000bbbc  lea     rax, aMPlockrequeste; "m_pLockRequestedBy && m_pLockRequestedB"...
0x18000bbc3  mov     [rsp+68h+var_38], rax; __int64
0x18000bbc8  mov     [rsp+68h+var_40], 0; int
0x18000bbd0  xor     r9d, r9d
0x18000bbd3  mov     r8d, r12d
0x18000bbd6  mov     edx, 25Bh; Value
0x18000bbdb  mov     rcx, r13; unsigned __int16 *
0x18000bbde  call    InternalTrace
0x18000bbe3  mov     rcx, [rsi+18h]
0x18000bbe7  test    rcx, rcx
0x18000bbea  jz      short loc_18000BC0B
0x18000bbec  mov     rcx, [rcx+70h]
0x18000bbf0  test    rcx, rcx
0x18000bbf3  jz      short loc_18000BC0B
0x18000bbf5  mov     rax, [rcx]
0x18000bbf8  mov     edx, ebp
0x18000bbfa  mov     rax, [rax+40h]
0x18000bbfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc03  nop
0x18000bc04  dec     dword ptr [rbx]
0x18000bc06  jmp     loc_18000BCFE
0x18000bc0b  dec     dword ptr [rbx]
0x18000bc0d  mov     eax, 8000FFFFh
0x18000bc12  jmp     loc_18000BCFE
0x18000bc17  test    eax, eax
0x18000bc19  jz      short loc_18000BC42
0x18000bc1b  lea     rax, aDwlockflagsTsL_0; "! ( dwLockFlags & TS_LF_SYNC )"
0x18000bc22  mov     [rsp+68h+var_38], rax; __int64
0x18000bc27  mov     [rsp+68h+var_40], 0; int
0x18000bc2f  xor     r9d, r9d
0x18000bc32  mov     r8d, r12d
0x18000bc35  mov     edx, 268h; Value
0x18000bc3a  mov     rcx, r13; unsigned __int16 *
0x18000bc3d  call    InternalTrace
0x18000bc42  test    byte ptr [rsi+24h], 6
0x18000bc46  jz      short loc_18000BC75
0x18000bc48  test    bpl, 6
0x18000bc4c  jnz     short loc_18000BC75
0x18000bc4e  lea     rax, aMDwpendinglock; "! ( m_dwPendingLock & TS_LF_READWRITE )"...
0x18000bc55  mov     [rsp+68h+var_38], rax; __int64
0x18000bc5a  mov     [rsp+68h+var_40], 0; int
0x18000bc62  xor     r9d, r9d
0x18000bc65  mov     r8d, r12d
0x18000bc68  mov     edx, 26Bh; Value
0x18000bc6d  mov     rcx, r13; unsigned __int16 *
0x18000bc70  call    InternalTrace
0x18000bc75  mov     dword ptr [rsi+24h], 0
0x18000bc7c  xor     r14d, r14d
0x18000bc7f  xor     ecx, ecx
0x18000bc81  mov     rdi, [rsi+38h]
0x18000bc85  test    rdi, rdi
0x18000bc88  jz      short loc_18000BCCD
0x18000bc8a  mov     edx, [rdi+10h]
0x18000bc8d  test    edx, edx
0x18000bc8f  jz      short loc_18000BCC7
0x18000bc91  mov     eax, edx
0x18000bc93  or      eax, ebp
0x18000bc95  cmp     eax, ebp
0x18000bc97  jnz     short loc_18000BCC1
0x18000bc99  mov     [rdi+14h], edx
0x18000bc9c  mov     dword ptr [rdi+10h], 0
0x18000bca3  mov     rcx, [rdi+18h]
0x18000bca7  mov     rax, [rcx]
0x18000bcaa  mov     rax, [rax+40h]
0x18000bcae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcb3  mov     dword ptr [rdi+14h], 0
0x18000bcba  mov     ecx, 1
0x18000bcbf  jmp     short loc_18000BCC7
0x18000bcc1  mov     r14d, 1
0x18000bcc7  mov     rdi, [rdi+8]
0x18000bccb  jmp     short loc_18000BC85
0x18000bccd  test    ecx, ecx
0x18000bccf  jnz     short loc_18000BC7F
0x18000bcd1  test    r14d, r14d
0x18000bcd4  jz      short loc_18000BCFA
0x18000bcd6  lea     rax, aWriteLockReque; "Write lock requested while holding read"...
0x18000bcdd  mov     [rsp+68h+var_38], rax; __int64
0x18000bce2  mov     [rsp+68h+var_40], ecx; int
0x18000bce6  xor     r9d, r9d
0x18000bce9  mov     r8d, r12d
0x18000bcec  mov     edx, 2ACh; Value
0x18000bcf1  mov     rcx, r13; unsigned __int16 *
0x18000bcf4  call    InternalTrace
0x18000bcf9  nop
0x18000bcfa  dec     dword ptr [rbx]
0x18000bcfc  xor     eax, eax
0x18000bcfe  lea     r11, [rsp+68h+var_28]
0x18000bd03  mov     rbx, [r11+38h]
0x18000bd07  mov     rbp, [r11+40h]
0x18000bd0b  mov     rsp, r11
0x18000bd0e  pop     r14
0x18000bd10  pop     r13
0x18000bd12  pop     r12
0x18000bd14  pop     rdi
0x18000bd15  pop     rsi
0x18000bd16  retn
```
