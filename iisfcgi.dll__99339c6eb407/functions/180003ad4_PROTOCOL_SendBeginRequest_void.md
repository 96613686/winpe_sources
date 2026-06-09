# PROTOCOL::SendBeginRequest(void)

- ea: `0x180003ad4`
- end: `0x180003bb9`
- name: `?SendBeginRequest@PROTOCOL@@QEAAJXZ`
- size: `229`
- prototype: `__int64 __fastcall(PROTOCOL *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004b90`

## callees

- `0x1800035f8`
- `0x180003ad4`
- `0x18000ee10`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003b09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003b09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003b9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003b9c`

## pseudocode

```c
__int64 __fastcall PROTOCOL::SendBeginRequest(PROTOCOL *this)
{
  int v2; // edi
  __int64 v3; // rcx
  _BYTE v5[9]; // [rsp+30h] [rbp-28h] BYREF
  int v6; // [rsp+39h] [rbp-1Fh]
  __int16 v7; // [rsp+3Dh] [rbp-1Bh]
  char v8; // [rsp+3Fh] [rbp-19h]

  memset(v5, 0, sizeof(v5));
  v6 = 0;
  v7 = 0;
  v8 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_DWORD *)this + 27) )
  {
    v2 = -2147023901;
  }
  else if ( *((_DWORD *)this + 13) || *((_DWORD *)this + 14) )
  {
    v2 = -2147024883;
  }
  else
  {
    *((_DWORD *)this + 35) = 0;
    v2 = PROTOCOL::PendReceive(this);
    if ( v2 >= 0 )
    {
      v3 = *((_QWORD *)this + 4);
      v5[2] = *((_BYTE *)this + 41);
      v5[3] = *((_BYTE *)this + 40);
      *((_DWORD *)this + 11) = 1;
      *(_WORD *)v5 = 257;
      v5[5] = 8;
      LOWORD(v6) = 257;
      v2 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *, __int64, _DWORD))(*(_QWORD *)v3 + 48LL))(
             v3,
             1,
             v5,
             16,
             0);
      if ( v2 >= 0 )
        *((_DWORD *)this + 11) = 2;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003ad4  push    rbp
0x180003ad6  push    rbx
0x180003ad7  push    rsi
0x180003ad8  push    rdi
0x180003ad9  mov     rbp, rsp
0x180003adc  sub     rsp, 58h
0x180003ae0  mov     rax, cs:__security_cookie
0x180003ae7  xor     rax, rsp
0x180003aea  mov     [rbp+var_18], rax
0x180003aee  xor     eax, eax
0x180003af0  mov     byte ptr [rbp+var_28], 0
0x180003af4  mov     rbx, rcx
0x180003af7  mov     qword ptr [rbp+var_28+1], rax
0x180003afb  add     rcx, 40h ; '@'; lpCriticalSection
0x180003aff  mov     [rbp+var_1F], eax
0x180003b02  mov     [rbp+var_1B], ax
0x180003b06  mov     [rbp+var_19], al
0x180003b09  call    cs:__imp_EnterCriticalSection
0x180003b0f  cmp     dword ptr [rbx+6Ch], 0
0x180003b13  jz      short loc_180003B1C
0x180003b15  mov     edi, 800703E3h
0x180003b1a  jmp     short loc_180003B98
0x180003b1c  cmp     dword ptr [rbx+34h], 0
0x180003b20  jnz     short loc_180003B93
0x180003b22  cmp     dword ptr [rbx+38h], 0
0x180003b26  jnz     short loc_180003B93
0x180003b28  mov     rcx, rbx; this
0x180003b2b  mov     dword ptr [rbx+8Ch], 0
0x180003b35  call    ?PendReceive@PROTOCOL@@AEAAJXZ; PROTOCOL::PendReceive(void)
0x180003b3a  mov     edi, eax
0x180003b3c  test    eax, eax
0x180003b3e  js      short loc_180003B98
0x180003b40  mov     al, [rbx+29h]
0x180003b43  lea     r8, [rbp+var_28]
0x180003b47  mov     rcx, [rbx+20h]
0x180003b4b  mov     edx, 1
0x180003b50  mov     [rbp-26h], al
0x180003b53  mov     al, [rbx+28h]
0x180003b56  mov     [rbp-25h], al
0x180003b59  mov     [rbx+2Ch], edx
0x180003b5c  lea     r9d, [rdx+0Fh]
0x180003b60  mov     [rbp+var_28], 101h
0x180003b66  mov     [rbp+var_23], 8
0x180003b6a  mov     word ptr [rbp+var_1F], 101h
0x180003b70  mov     rax, [rcx]
0x180003b73  mov     [rsp+58h+var_38], 0
0x180003b7b  mov     rax, [rax+30h]
0x180003b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b84  mov     edi, eax
0x180003b86  test    eax, eax
0x180003b88  js      short loc_180003B98
0x180003b8a  mov     dword ptr [rbx+2Ch], 2
0x180003b91  jmp     short loc_180003B98
0x180003b93  mov     edi, 8007000Dh
0x180003b98  lea     rcx, [rbx+40h]; lpCriticalSection
0x180003b9c  call    cs:__imp_LeaveCriticalSection
0x180003ba2  mov     eax, edi
0x180003ba4  mov     rcx, [rbp+var_18]
0x180003ba8  xor     rcx, rsp; StackCookie
0x180003bab  call    __security_check_cookie
0x180003bb0  add     rsp, 58h
0x180003bb4  pop     rdi
0x180003bb5  pop     rsi
0x180003bb6  pop     rbx
0x180003bb7  pop     rbp
0x180003bb8  retn
```
