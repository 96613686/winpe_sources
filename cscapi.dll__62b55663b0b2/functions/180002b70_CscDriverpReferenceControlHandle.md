# CscDriverpReferenceControlHandle

- ea: `0x180002b70`
- end: `0x180002cc0`
- name: `CscDriverpReferenceControlHandle`
- size: `336`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180001020`
- `0x1800016b0`
- `0x180002080`
- `0x180003920`

## callees

- `0x180002b70`
- `0x180002cd0`
- `0x180008d78`
- `0x180008eb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002beb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002beb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c26`

## pseudocode

```c
__int64 __fastcall CscDriverpReferenceControlHandle(_QWORD *a1, __int64 a2, __int64 a3)
{
  signed __int32 v3; // ebp
  HANDLE v5; // rdi
  _QWORD *v6; // rcx
  int v7; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8

  v3 = -1;
  v5 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 40, a3, 0);
    v6 = WPP_GLOBAL_Control;
  }
  if ( dword_18000E990 )
  {
    EnterCriticalSection(&CriticalSection);
    if ( dword_18000E9C0 < 0 )
    {
      v7 = -1073740768;
    }
    else if ( FileHandle )
    {
      v5 = FileHandle;
      v3 = _InterlockedIncrement(&dword_18000E9C0);
      v7 = 0;
    }
    else
    {
      v7 = CscDriverpOpenControl(&FileHandle, v9, v10);
      if ( v7 >= 0 )
      {
        v5 = FileHandle;
        v3 = 1;
        dword_18000E9C0 = 1;
      }
    }
    LeaveCriticalSection(&CriticalSection);
    v6 = WPP_GLOBAL_Control;
  }
  else
  {
    v7 = -1073740768;
  }
  *a1 = v5;
  if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 17) & 0x200) != 0 && *((_BYTE *)v6 + 65) >= 4u )
    WPP_SF_Dqd(v6[7], a2, a3, (unsigned int)v7, v5, v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180002b70  mov     [rsp+arg_18], rbp
0x180002b75  push    rdi
0x180002b76  sub     rsp, 30h
0x180002b7a  mov     [rsp+38h+arg_8], rsi
0x180002b7f  mov     ebp, 0FFFFFFFFh
0x180002b84  mov     [rsp+38h+arg_10], r14
0x180002b89  mov     rsi, rcx
0x180002b8c  xor     edi, edi
0x180002b8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b95  lea     r14, WPP_GLOBAL_Control
0x180002b9c  cmp     rcx, r14
0x180002b9f  jz      short loc_180002BAE
0x180002ba1  test    dword ptr [rcx+44h], 200h
0x180002ba8  jnz     loc_180002C76
0x180002bae  cmp     cs:dword_18000E990, edi
0x180002bb4  mov     [rsp+38h+arg_0], rbx
0x180002bb9  jnz     short loc_180002BE4
0x180002bbb  mov     ebx, 0C0000420h
0x180002bc0  mov     [rsi], rdi
0x180002bc3  mov     rsi, [rsp+38h+arg_8]
0x180002bc8  cmp     rcx, r14
0x180002bcb  mov     r14, [rsp+38h+arg_10]
0x180002bd0  jnz     short loc_180002C49
0x180002bd2  mov     rbp, [rsp+38h+arg_18]
0x180002bd7  mov     eax, ebx
0x180002bd9  mov     rbx, [rsp+38h+arg_0]
0x180002bde  add     rsp, 30h
0x180002be2  pop     rdi
0x180002be3  retn
0x180002be4  lea     rcx, CriticalSection; lpCriticalSection
0x180002beb  call    cs:__imp_EnterCriticalSection
0x180002bf1  cmp     cs:dword_18000E9C0, edi
0x180002bf7  jl      loc_180002C9D
0x180002bfd  mov     rax, cs:FileHandle
0x180002c04  test    rax, rax
0x180002c07  jnz     loc_180002CA7
0x180002c0d  lea     rcx, FileHandle; FileHandle
0x180002c14  call    CscDriverpOpenControl
0x180002c19  mov     ebx, eax
0x180002c1b  test    eax, eax
0x180002c1d  jns     short loc_180002C35
0x180002c1f  lea     rcx, CriticalSection; lpCriticalSection
0x180002c26  call    cs:__imp_LeaveCriticalSection
0x180002c2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c33  jmp     short loc_180002BC0
0x180002c35  mov     rdi, cs:FileHandle
0x180002c3c  mov     ebp, 1
0x180002c41  mov     cs:dword_18000E9C0, ebp
0x180002c47  jmp     short loc_180002C1F
0x180002c49  test    dword ptr [rcx+44h], 200h
0x180002c50  jz      short loc_180002BD2
0x180002c52  cmp     byte ptr [rcx+41h], 4
0x180002c56  jb      loc_180002BD2
0x180002c5c  mov     rcx, [rcx+38h]
0x180002c60  mov     r9d, ebx
0x180002c63  mov     [rsp+38h+var_10], ebp
0x180002c67  mov     [rsp+38h+var_18], rdi
0x180002c6c  call    WPP_SF_Dqd
0x180002c71  jmp     loc_180002BD2
0x180002c76  cmp     byte ptr [rcx+41h], 4
0x180002c7a  jb      loc_180002BAE
0x180002c80  mov     rcx, [rcx+38h]
0x180002c84  mov     edx, 28h ; '('
0x180002c89  xor     r9d, r9d
0x180002c8c  call    WPP_SF_q
0x180002c91  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c98  jmp     loc_180002BAE
0x180002c9d  mov     ebx, 0C0000420h
0x180002ca2  jmp     loc_180002C1F
0x180002ca7  mov     rdi, rax
0x180002caa  mov     ebp, 1
0x180002caf  lock xadd cs:dword_18000E9C0, ebp
0x180002cb7  inc     ebp
0x180002cb9  xor     ebx, ebx
0x180002cbb  jmp     loc_180002C1F
```
