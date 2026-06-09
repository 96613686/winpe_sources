# HandleSanAcceptIndication

- ea: `0x180051b7c`
- end: `0x180051f16`
- name: `HandleSanAcceptIndication`
- size: `922`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180046790`

## callees

- `0x180008250`
- `0x1800222f0`
- `0x180022bd2`
- `0x180038104`
- `0x180038118`
- `0x18003ae8c`
- `0x180042b50`
- `0x180051b7c`
- `0x180051f1c`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180051bcf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180051bcf`
- `ntdll!RtlFreeHeap` at `0x180051e83`
- `ntdll!RtlFreeHeap` at `0x180051e9b`
- `ntdll!RtlFreeHeap` at `0x180051e83`
- `ntdll!RtlFreeHeap` at `0x180051e9b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051e67`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051e67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051ce2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051e57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051ee3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051ce2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051e57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051ee3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051ca5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051df1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051eaa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051ca5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051df1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051eaa`

## pseudocode

```c
__int64 __fastcall HandleSanAcceptIndication(__int64 a1)
{
  _QWORD *Value; // r13
  int v3; // eax
  __int64 *v5; // r14
  __int64 *v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // r15
  __int64 v11; // rsi
  unsigned int v12; // esi
  char v13; // al
  __int64 v14; // rdx
  _QWORD *v15; // rcx
  _QWORD *v16; // rax
  __int64 v17; // r8
  _QWORD *v18; // rdx
  __int64 v19; // rax
  __int64 v20; // r8
  __int64 v21; // rdx
  unsigned int v22; // [rsp+40h] [rbp-C8h] BYREF
  _DWORD v23[3]; // [rsp+44h] [rbp-C4h] BYREF
  _BYTE v24[128]; // [rsp+50h] [rbp-B8h] BYREF

  memset_0(v24, 0, sizeof(v24));
  v23[0] = 0;
  v22 = 0;
  Value = TlsGetValue(MSAFD_SockTlsSlot);
  if ( (BYTE1(xmmword_180063D60) & 0x40) != 0 )
    WPP_SF_(1038, 10, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids);
  v3 = *(_DWORD *)(a1 + 672);
  v23[0] = 128;
  if ( *(_DWORD *)(a1 + 676) != v3 )
  {
    _InterlockedIncrement(*(volatile signed __int32 **)(a1 + 8));
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
    ++*(_DWORD *)(a1 + 676);
    v5 = (__int64 *)(a1 + 680);
    v6 = *(__int64 **)(a1 + 680);
    if ( v6[1] != a1 + 680 )
      goto LABEL_29;
    v7 = *v6;
    if ( *(__int64 **)(*v6 + 8) != v6 )
      goto LABEL_29;
    *v5 = v7;
    *(_QWORD *)(v7 + 8) = v5;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
    v6[2] = a1;
    v6[3] = 0;
    *((_DWORD *)v6 + 10) = 0;
    v8 = *(_QWORD *)(a1 + 16);
    v22 = 0;
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 16));
    v9 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, _DWORD *, __int64 (__fastcall *)(int, int, int, int, __int64, int, int, __int64), __int64 *, unsigned int *))(*(_QWORD *)(a1 + 16) + 64LL))(
           *(_QWORD *)(a1 + 104),
           v24,
           v23,
           AcceptConditionCallback,
           v6,
           &v22);
    v10 = v9;
    if ( (BYTE2(xmmword_180063D60) & 4) != 0 )
      WPP_SF_q(1042, 13, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids, v9);
    v11 = v6[3];
    Value[3] = -1;
    if ( v10 != -1 )
    {
      *(_QWORD *)(v11 + 104) = v10;
      InitializeAcceptSocket((PVOID)v11);
      return 0;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 16) + 16LL), 0xFFFFFFFF) == 1 )
      SockSanFreeProvider(*(PVOID *)(a1 + 16));
    v13 = xmmword_180063D60;
    if ( (xmmword_180063D60 & 2) != 0 )
    {
      WPP_SF_d(1025, 14, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids, v22);
      v13 = xmmword_180063D60;
    }
    if ( v11 )
    {
      if ( (v13 & 2) != 0 )
        WPP_SF_q(1025, 15, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids, a1);
      EnterCriticalSection(&SockSanListCritSec);
      v14 = *(_QWORD *)(v11 + 88);
      if ( *(_QWORD *)(v14 + 8) != v11 + 88 )
        goto LABEL_29;
      v15 = *(_QWORD **)(v11 + 96);
      if ( *v15 != v11 + 88 )
        goto LABEL_29;
      --NumOpenSanSocks;
      *v15 = v14;
      *(_QWORD *)(v14 + 8) = v15;
      v16 = *(_QWORD **)(v11 + 216);
      v17 = *v16;
      if ( *(_QWORD **)(*v16 + 8LL) != v16 )
        goto LABEL_29;
      v18 = (_QWORD *)v16[1];
      if ( (_QWORD *)*v18 != v16 )
        goto LABEL_29;
      *v18 = v17;
      *(_QWORD *)(v17 + 8) = v18;
      LeaveCriticalSection(&SockSanListCritSec);
      DeleteCriticalSection((LPCRITICAL_SECTION)(v11 + 48));
      RtlFreeHeap(SockPrivateHeap, 0, *(PVOID *)(v11 + 216));
      RtlFreeHeap(SockPrivateHeap, 0, (PVOID)v11);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
    v6[3] = 0;
    v19 = *v5;
    if ( *(__int64 **)(*v5 + 8) == v5 )
    {
      *v6 = v19;
      v6[1] = (__int64)v5;
      v12 = -1073741823;
      *(_QWORD *)(v19 + 8) = v6;
      *v5 = (__int64)v6;
      --*(_DWORD *)(a1 + 676);
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
      v21 = (unsigned int)_InterlockedExchangeAdd(*(volatile signed __int32 **)(a1 + 8), 0xFFFFFFFF);
      if ( (_DWORD)v21 == 1 )
        SockDestroySocket(*(_QWORD *)(a1 + 8), v21, v20);
      return v12;
    }
LABEL_29:
    __fastfail(3u);
  }
  if ( (BYTE2(xmmword_180063D60) & 4) != 0 )
    WPP_SF_q(1042, 11, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids, a1);
  (*(void (__fastcall **)(_QWORD, _BYTE *, _DWORD *, __int64 (__fastcall *)(), _QWORD, unsigned int *))(*(_QWORD *)(a1 + 16) + 64LL))(
    *(_QWORD *)(a1 + 104),
    v24,
    v23,
    AcceptRejectConditionCallback,
    0,
    &v22);
  return 3221225473LL;
}

```

## disassembly

```asm
0x180051b7c  mov     [rsp+arg_8], rbx
0x180051b81  mov     [rsp+arg_10], rsi
0x180051b86  push    rdi
0x180051b87  push    r12
0x180051b89  push    r13
0x180051b8b  push    r14
0x180051b8d  push    r15
0x180051b8f  sub     rsp, 0E0h
0x180051b96  mov     rax, cs:__security_cookie
0x180051b9d  xor     rax, rsp
0x180051ba0  mov     [rsp+108h+var_38], rax
0x180051ba8  mov     rbx, rcx
0x180051bab  mov     edi, 80h
0x180051bb0  mov     r8d, edi; Size
0x180051bb3  lea     rcx, [rsp+108h+var_B8]; void *
0x180051bb8  xor     edx, edx; Val
0x180051bba  call    memset_0
0x180051bbf  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180051bc5  xor     esi, esi
0x180051bc7  mov     [rsp+108h+var_C4], esi
0x180051bcb  mov     [rsp+108h+var_C8], esi
0x180051bcf  call    cs:__imp_TlsGetValue
0x180051bd6  nop     dword ptr [rax+rax+00h]
0x180051bdb  mov     r13, rax
0x180051bde  test    byte ptr cs:xmmword_180063D60+1, 40h
0x180051be5  jz      short loc_180051BFB
0x180051be7  lea     edx, [rdi-76h]
0x180051bea  mov     ecx, 40Eh
0x180051bef  lea     r8, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids
0x180051bf6  call    WPP_SF_
0x180051bfb  mov     eax, [rbx+2A0h]
0x180051c01  mov     [rsp+108h+var_C4], edi
0x180051c05  cmp     [rbx+2A4h], eax
0x180051c0b  jnz     loc_180051C97
0x180051c11  test    byte ptr cs:xmmword_180063D60+2, 4
0x180051c18  jz      short loc_180051C33
0x180051c1a  mov     edx, 0Bh
0x180051c1f  lea     r8, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids
0x180051c26  mov     ecx, 412h
0x180051c2b  mov     r9, rbx
0x180051c2e  call    WPP_SF_q
0x180051c33  mov     rax, [rbx+10h]
0x180051c37  lea     rcx, [rsp+108h+var_C8]
0x180051c3c  mov     [rsp+108h+var_E0], rcx
0x180051c41  lea     r9, AcceptRejectConditionCallback
0x180051c48  mov     rcx, [rbx+68h]
0x180051c4c  lea     r8, [rsp+108h+var_C4]
0x180051c51  lea     rdx, [rsp+108h+var_B8]
0x180051c56  mov     [rsp+108h+var_E8], rsi
0x180051c5b  mov     rax, [rax+40h]
0x180051c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c64  mov     eax, 0C0000001h
0x180051c69  mov     rcx, [rsp+108h+var_38]
0x180051c71  xor     rcx, rsp; StackCookie
0x180051c74  call    __security_check_cookie
0x180051c79  lea     r11, [rsp+108h+var_28]
0x180051c81  mov     rbx, [r11+38h]
0x180051c85  mov     rsi, [r11+40h]
0x180051c89  mov     rsp, r11
0x180051c8c  pop     r15
0x180051c8e  pop     r14
0x180051c90  pop     r13
0x180051c92  pop     r12
0x180051c94  pop     rdi
0x180051c95  retn
0x180051c97  mov     rax, [rbx+8]
0x180051c9b  lock inc dword ptr [rax]
0x180051c9e  lea     r12, [rbx+30h]
0x180051ca2  mov     rcx, r12; lpCriticalSection
0x180051ca5  call    cs:__imp_EnterCriticalSection
0x180051cac  nop     dword ptr [rax+rax+00h]
0x180051cb1  inc     dword ptr [rbx+2A4h]
0x180051cb7  lea     r14, [rbx+2A8h]
0x180051cbe  mov     rdi, [r14]
0x180051cc1  cmp     [rdi+8], r14
0x180051cc5  jnz     loc_180051F0F
0x180051ccb  mov     rax, [rdi]
0x180051cce  cmp     [rax+8], rdi
0x180051cd2  jnz     loc_180051F0F
0x180051cd8  mov     [r14], rax
0x180051cdb  mov     rcx, r12; lpCriticalSection
0x180051cde  mov     [rax+8], r14
0x180051ce2  call    cs:__imp_LeaveCriticalSection
0x180051ce9  nop     dword ptr [rax+rax+00h]
0x180051cee  mov     [rdi+10h], rbx
0x180051cf2  mov     [rdi+18h], rsi
0x180051cf6  mov     [rdi+28h], esi
0x180051cf9  mov     rax, [rbx+10h]
0x180051cfd  mov     [rsp+108h+var_C8], esi
0x180051d01  lock inc dword ptr [rax+10h]
0x180051d05  mov     rax, [rbx+10h]
0x180051d09  lea     rcx, [rsp+108h+var_C8]
0x180051d0e  mov     [rsp+108h+var_E0], rcx
0x180051d13  lea     r9, AcceptConditionCallback
0x180051d1a  mov     rcx, [rbx+68h]
0x180051d1e  lea     r8, [rsp+108h+var_C4]
0x180051d23  lea     rdx, [rsp+108h+var_B8]
0x180051d28  mov     [rsp+108h+var_E8], rdi
0x180051d2d  mov     rax, [rax+40h]
0x180051d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d36  mov     r15, rax
0x180051d39  test    byte ptr cs:xmmword_180063D60+2, 4
0x180051d40  jz      short loc_180051D5B
0x180051d42  mov     edx, 0Dh
0x180051d47  lea     r8, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids
0x180051d4e  mov     ecx, 412h
0x180051d53  mov     r9, rax
0x180051d56  call    WPP_SF_q
0x180051d5b  mov     rsi, [rdi+18h]
0x180051d5f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180051d63  mov     [r13+18h], rdx
0x180051d67  cmp     r15, rdx
0x180051d6a  jz      short loc_180051D7F
0x180051d6c  mov     rcx, rsi; P
0x180051d6f  mov     [rsi+68h], r15
0x180051d73  call    InitializeAcceptSocket
0x180051d78  xor     esi, esi
0x180051d7a  jmp     loc_180051F08
0x180051d7f  mov     rcx, [rbx+10h]
0x180051d83  mov     eax, edx
0x180051d85  lock xadd [rcx+10h], eax
0x180051d8a  add     eax, edx
0x180051d8c  jnz     short loc_180051D97
0x180051d8e  mov     rcx, [rbx+10h]; CompletionContext
0x180051d92  call    SockSanFreeProvider
0x180051d97  mov     al, byte ptr cs:xmmword_180063D60
0x180051d9d  mov     r15d, 401h
0x180051da3  test    al, 2
0x180051da5  jz      short loc_180051DC6
0x180051da7  mov     r9d, [rsp+108h+var_C8]
0x180051dac  lea     r8, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids
0x180051db3  mov     edx, 0Eh
0x180051db8  mov     ecx, r15d
0x180051dbb  call    WPP_SF_d
0x180051dc0  mov     al, byte ptr cs:xmmword_180063D60
0x180051dc6  test    rsi, rsi
0x180051dc9  jz      loc_180051EA7
0x180051dcf  test    al, 2
0x180051dd1  jz      short loc_180051DEA
0x180051dd3  mov     edx, 0Fh
0x180051dd8  lea     r8, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids
0x180051ddf  mov     ecx, r15d
0x180051de2  mov     r9, rbx
0x180051de5  call    WPP_SF_q
0x180051dea  lea     rcx, SockSanListCritSec; lpCriticalSection
0x180051df1  call    cs:__imp_EnterCriticalSection
0x180051df8  nop     dword ptr [rax+rax+00h]
0x180051dfd  lea     rax, [rsi+58h]
0x180051e01  mov     rdx, [rax]
0x180051e04  cmp     [rdx+8], rax
0x180051e08  jnz     loc_180051F0F
0x180051e0e  mov     rcx, [rax+8]
0x180051e12  cmp     [rcx], rax
0x180051e15  jnz     loc_180051F0F
0x180051e1b  dec     cs:NumOpenSanSocks
0x180051e21  mov     [rcx], rdx
0x180051e24  mov     [rdx+8], rcx
0x180051e28  mov     rax, [rsi+0D8h]
0x180051e2f  mov     r8, [rax]
0x180051e32  cmp     [r8+8], rax
0x180051e36  jnz     loc_180051F0F
0x180051e3c  mov     rdx, [rax+8]
0x180051e40  cmp     [rdx], rax
0x180051e43  jnz     loc_180051F0F
0x180051e49  mov     [rdx], r8
0x180051e4c  lea     rcx, SockSanListCritSec; lpCriticalSection
0x180051e53  mov     [r8+8], rdx
0x180051e57  call    cs:__imp_LeaveCriticalSection
0x180051e5e  nop     dword ptr [rax+rax+00h]
0x180051e63  lea     rcx, [rsi+30h]; lpCriticalSection
0x180051e67  call    cs:__imp_DeleteCriticalSection
0x180051e6e  nop     dword ptr [rax+rax+00h]
0x180051e73  mov     r8, [rsi+0D8h]; P
0x180051e7a  xor     edx, edx; Flags
0x180051e7c  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180051e83  call    cs:__imp_RtlFreeHeap
0x180051e8a  nop     dword ptr [rax+rax+00h]
0x180051e8f  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180051e96  mov     r8, rsi; P
0x180051e99  xor     edx, edx; Flags
0x180051e9b  call    cs:__imp_RtlFreeHeap
0x180051ea2  nop     dword ptr [rax+rax+00h]
0x180051ea7  mov     rcx, r12; lpCriticalSection
0x180051eaa  call    cs:__imp_EnterCriticalSection
0x180051eb1  nop     dword ptr [rax+rax+00h]
0x180051eb6  mov     qword ptr [rdi+18h], 0
0x180051ebe  mov     rax, [r14]
0x180051ec1  cmp     [rax+8], r14
0x180051ec5  jnz     short loc_180051F0F
0x180051ec7  mov     [rdi], rax
0x180051eca  mov     rcx, r12; lpCriticalSection
0x180051ecd  mov     [rdi+8], r14
0x180051ed1  mov     esi, 0C0000001h
0x180051ed6  mov     [rax+8], rdi
0x180051eda  mov     [r14], rdi
0x180051edd  dec     dword ptr [rbx+2A4h]
0x180051ee3  call    cs:__imp_LeaveCriticalSection
0x180051eea  nop     dword ptr [rax+rax+00h]
0x180051eef  mov     rcx, [rbx+8]
0x180051ef3  or      edx, 0FFFFFFFFh
0x180051ef6  lock xadd [rcx], edx
0x180051efa  cmp     edx, 1
0x180051efd  jnz     short loc_180051F08
0x180051eff  mov     rcx, [rbx+8]
0x180051f03  call    SockDestroySocket
0x180051f08  mov     eax, esi
0x180051f0a  jmp     loc_180051C69
0x180051f0f  mov     ecx, 3
0x180051f14  int     29h; Win8: RtlFailFast(ecx)
```
