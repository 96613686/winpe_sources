# sub_1802E7FCC

- ea: `0x1802e7fcc`
- end: `0x1802e81f1`
- name: `sub_1802E7FCC`
- size: `549`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x1802e8c7c`
- `0x1802eb314`
- `0x18050b950`
- `0x18050be50`

## callees

- `0x180021de0`
- `0x180023070`
- `0x18007e5b8`
- `0x18013f000`
- `0x1801a166c`
- `0x1801a5560`
- `0x1802e7fcc`

## import_xrefs

- `KERNEL32!GetThreadPriority` at `0x1802e8111`
- `KERNEL32!GetThreadPriority` at `0x1802e8111`
- `KERNEL32!SetThreadPriority` at `0x1802e817b`
- `KERNEL32!SetThreadPriority` at `0x1802e817b`
- `KERNEL32!GetCurrentThread` at `0x1802e8039`
- `KERNEL32!GetCurrentThread` at `0x1802e80af`
- `KERNEL32!GetCurrentThread` at `0x1802e8108`
- `KERNEL32!GetCurrentThread` at `0x1802e8170`
- `KERNEL32!GetCurrentThread` at `0x1802e8039`
- `KERNEL32!GetCurrentThread` at `0x1802e80af`
- `KERNEL32!GetCurrentThread` at `0x1802e8108`
- `KERNEL32!GetCurrentThread` at `0x1802e8170`
- `KERNEL32!GetLastError` at `0x1802e807b`
- `KERNEL32!GetLastError` at `0x1802e80f8`
- `KERNEL32!GetLastError` at `0x1802e8141`
- `KERNEL32!GetLastError` at `0x1802e81a2`
- `KERNEL32!GetLastError` at `0x1802e807b`
- `KERNEL32!GetLastError` at `0x1802e80f8`
- `KERNEL32!GetLastError` at `0x1802e8141`
- `KERNEL32!GetLastError` at `0x1802e81a2`

## pseudocode

```c
__int64 __fastcall sub_1802E7FCC(__int64 a1, __int64 a2, char a3)
{
  int *v5; // rsi
  int v6; // ecx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE v9; // rax
  __int64 v10; // rdx
  HANDLE v11; // rax
  int ThreadPriority; // eax
  DWORD v13; // eax
  HANDLE v14; // rax
  int nPriority; // [rsp+30h] [rbp-18h] BYREF

  *(_WORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = &CAutoThreadPriority<0>::`vftable';
  v5 = (int *)(a1 + 12);
  v6 = sub_18007E5B8();
  *v5 = 0;
  *(_BYTE *)(a1 + 10) = v6 != 0;
  if ( !a3 )
    return a1;
  nPriority = 0;
  if ( v6 )
  {
    nPriority = 8;
    CurrentThread = GetCurrentThread();
    if ( !(unsigned int)sub_180021DE0(CurrentThread, 1, a1 + 12) )
    {
      if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        sub_1801A166C(*((_QWORD *)hDevice + 2), 10, qword_180C2FDB0, LastError);
      }
      return a1;
    }
    if ( nPriority == *v5 )
      return a1;
    v9 = GetCurrentThread();
    if ( !(unsigned int)sub_180023070(v9, 1, &nPriority, 4) )
    {
      if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
        return a1;
      GetLastError();
      v10 = 11;
      goto LABEL_21;
    }
    goto LABEL_22;
  }
  v11 = GetCurrentThread();
  ThreadPriority = GetThreadPriority(v11);
  *v5 = ThreadPriority;
  if ( ThreadPriority != 0x7FFFFFFF )
  {
    if ( nPriority == ThreadPriority )
      return a1;
    v14 = GetCurrentThread();
    if ( !SetThreadPriority(v14, nPriority) )
    {
      if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
        return a1;
      GetLastError();
      v10 = 13;
LABEL_21:
      sub_1801A5560(*((_QWORD *)hDevice + 2), v10, qword_180C2FDB0);
      return a1;
    }
LABEL_22:
    *(_BYTE *)(a1 + 8) = 1;
    return a1;
  }
  if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
  {
    v13 = GetLastError();
    sub_1801A166C(*((_QWORD *)hDevice + 2), 12, qword_180C2FDB0, v13);
  }
  return a1;
}

```

## disassembly

```asm
0x1802e7fcc  mov     [rsp+arg_8], rbx
0x1802e7fd1  mov     [rsp+arg_10], rsi
0x1802e7fd6  push    rdi
0x1802e7fd7  sub     rsp, 40h
0x1802e7fdb  mov     rax, cs:__security_cookie
0x1802e7fe2  xor     rax, rsp
0x1802e7fe5  mov     [rsp+48h+var_10], rax
0x1802e7fea  lea     rax, ??_7?$CAutoThreadPriority@$0A@@@6B@; const CAutoThreadPriority<0>::`vftable'
0x1802e7ff1  mov     word ptr [rcx+8], 0
0x1802e7ff7  mov     [rcx], rax
0x1802e7ffa  mov     bl, r8b
0x1802e7ffd  mov     rdi, rcx
0x1802e8000  call    sub_18007E5B8
0x1802e8005  test    eax, eax
0x1802e8007  lea     rsi, [rdi+0Ch]
0x1802e800b  mov     ecx, eax
0x1802e800d  mov     dword ptr [rsi], 0
0x1802e8013  setnz   al
0x1802e8016  mov     [rdi+0Ah], al
0x1802e8019  test    bl, bl
0x1802e801b  jz      loc_1802E81D1
0x1802e8021  mov     [rsp+48h+nPriority], 0
0x1802e8029  test    ecx, ecx
0x1802e802b  jz      loc_1802E8108
0x1802e8031  mov     [rsp+48h+nPriority], 8
0x1802e8039  call    cs:GetCurrentThread
0x1802e803f  mov     ebx, 4
0x1802e8044  mov     r8, rsi
0x1802e8047  mov     rcx, rax
0x1802e804a  mov     r9d, ebx
0x1802e804d  lea     edx, [rbx-3]
0x1802e8050  call    cs:off_180BC66A8
0x1802e8056  test    eax, eax
0x1802e8058  jnz     short loc_1802E80A3
0x1802e805a  mov     rcx, cs:hDevice
0x1802e8061  lea     rax, hDevice
0x1802e8068  cmp     rcx, rax
0x1802e806b  jz      loc_1802E81D1
0x1802e8071  test    byte ptr [rcx+1Ch], 1
0x1802e8075  jz      loc_1802E81D1
0x1802e807b  call    cs:__imp_GetLastError
0x1802e8081  mov     rcx, cs:hDevice
0x1802e8088  lea     edx, [rbx+6]
0x1802e808b  mov     r9d, eax
0x1802e808e  lea     r8, qword_180C2FDB0
0x1802e8095  mov     rcx, [rcx+10h]
0x1802e8099  call    sub_1801A166C
0x1802e809e  jmp     loc_1802E81D1
0x1802e80a3  mov     eax, [rsi]
0x1802e80a5  cmp     [rsp+48h+nPriority], eax
0x1802e80a9  jz      loc_1802E81D1
0x1802e80af  call    cs:GetCurrentThread
0x1802e80b5  mov     r9d, ebx
0x1802e80b8  lea     r8, [rsp+48h+nPriority]
0x1802e80bd  mov     rcx, rax
0x1802e80c0  mov     edx, 1
0x1802e80c5  call    cs:off_180BC6758
0x1802e80cb  test    eax, eax
0x1802e80cd  jnz     loc_1802E81CD
0x1802e80d3  mov     rcx, cs:hDevice
0x1802e80da  lea     rax, hDevice
0x1802e80e1  cmp     rcx, rax
0x1802e80e4  jz      loc_1802E81D1
0x1802e80ea  test    byte ptr [rcx+1Ch], 1
0x1802e80ee  jz      loc_1802E81D1
0x1802e80f4  mov     ebx, [rsp+48h+nPriority]
0x1802e80f8  call    cs:__imp_GetLastError
0x1802e80fe  mov     edx, 0Bh
0x1802e8103  jmp     loc_1802E81AD
0x1802e8108  call    cs:GetCurrentThread
0x1802e810e  mov     rcx, rax; hThread
0x1802e8111  call    cs:GetThreadPriority
0x1802e8117  mov     [rsi], eax
0x1802e8119  cmp     eax, 7FFFFFFFh
0x1802e811e  jnz     short loc_1802E8168
0x1802e8120  mov     rcx, cs:hDevice
0x1802e8127  lea     rax, hDevice
0x1802e812e  cmp     rcx, rax
0x1802e8131  jz      loc_1802E81D1
0x1802e8137  test    byte ptr [rcx+1Ch], 1
0x1802e813b  jz      loc_1802E81D1
0x1802e8141  call    cs:__imp_GetLastError
0x1802e8147  mov     rcx, cs:hDevice
0x1802e814e  lea     r8, qword_180C2FDB0
0x1802e8155  mov     edx, 0Ch
0x1802e815a  mov     r9d, eax
0x1802e815d  mov     rcx, [rcx+10h]
0x1802e8161  call    sub_1801A166C
0x1802e8166  jmp     short loc_1802E81D1
0x1802e8168  mov     ebx, [rsp+48h+nPriority]
0x1802e816c  cmp     ebx, eax
0x1802e816e  jz      short loc_1802E81D1
0x1802e8170  call    cs:GetCurrentThread
0x1802e8176  mov     rcx, rax; hThread
0x1802e8179  mov     edx, ebx; nPriority
0x1802e817b  call    cs:SetThreadPriority
0x1802e8181  test    eax, eax
0x1802e8183  jnz     short loc_1802E81CD
0x1802e8185  mov     rcx, cs:hDevice
0x1802e818c  lea     rax, hDevice
0x1802e8193  cmp     rcx, rax
0x1802e8196  jz      short loc_1802E81D1
0x1802e8198  test    byte ptr [rcx+1Ch], 1
0x1802e819c  jz      short loc_1802E81D1
0x1802e819e  mov     ebx, [rsp+48h+nPriority]
0x1802e81a2  call    cs:__imp_GetLastError
0x1802e81a8  mov     edx, 0Dh
0x1802e81ad  mov     rcx, cs:hDevice
0x1802e81b4  lea     r8, qword_180C2FDB0
0x1802e81bb  mov     r9d, eax
0x1802e81be  mov     [rsp+48h+var_28], ebx
0x1802e81c2  mov     rcx, [rcx+10h]
0x1802e81c6  call    sub_1801A5560
0x1802e81cb  jmp     short loc_1802E81D1
0x1802e81cd  mov     byte ptr [rdi+8], 1
0x1802e81d1  mov     rax, rdi
0x1802e81d4  mov     rcx, [rsp+48h+var_10]
0x1802e81d9  xor     rcx, rsp; StackCookie
0x1802e81dc  call    __security_check_cookie
0x1802e81e1  mov     rbx, [rsp+48h+arg_8]
0x1802e81e6  mov     rsi, [rsp+48h+arg_10]
0x1802e81eb  add     rsp, 40h
0x1802e81ef  pop     rdi
0x1802e81f0  retn
```
