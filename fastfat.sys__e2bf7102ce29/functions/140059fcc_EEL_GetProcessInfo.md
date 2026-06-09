# EEL_GetProcessInfo

- ea: `0x140059fcc`
- end: `0x14005a176`
- name: `EEL_GetProcessInfo`
- size: `426`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140058ce4`
- `0x1400592f0`
- `0x140059940`

## callees

- `0x14000b640`
- `0x14000c680`
- `0x140059fcc`
- `0x14005a17c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14005a039`
- `ntoskrnl!ZwClose` at `0x14005a08b`
- `ntoskrnl!ZwClose` at `0x14005a039`
- `ntoskrnl!ZwClose` at `0x14005a08b`
- `ntoskrnl!ExAllocatePool2` at `0x14005a0df`
- `ntoskrnl!ExAllocatePool2` at `0x14005a0df`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14005a05c`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x14005a05c`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14005a0b0`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14005a107`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14005a0b0`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14005a107`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x14005a00a`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x14005a00a`

## pseudocode

```c
__int64 *__fastcall EEL_GetProcessInfo(__int64 *a1)
{
  void *Pool2; // rax
  __int64 v3; // r9
  __int16 v4; // cx
  unsigned __int16 i; // dx
  __int64 v6; // r8
  __int16 v7; // cx
  ULONG ReturnLength; // [rsp+50h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp+28h] BYREF
  HANDLE v11; // [rsp+60h] [rbp+30h] BYREF

  memset(a1, 0, 0x48u);
  Handle = 0;
  ZwOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, 0x200u, &Handle);
  if ( Handle )
  {
    SrpGetEnterpriseContextToken(Handle, a1 + 4);
    EEL_GetUserSidStringForToken(Handle, (struct _UNICODE_STRING *)(a1 + 7));
    ZwClose(Handle);
  }
  v11 = 0;
  ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0x200u, &v11);
  if ( v11 )
  {
    SrpGetEnterpriseContextToken(v11, a1 + 3);
    EEL_GetUserSidStringForToken(v11, (struct _UNICODE_STRING *)(a1 + 5));
    ZwClose(v11);
  }
  ReturnLength = 0;
  if ( ZwQueryInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessImageFileName, 0, 0, &ReturnLength) == -1073741820
    && ReturnLength > 0x10 )
  {
    Pool2 = (void *)ExAllocatePool2(256, ReturnLength, 1701864517);
    *a1 = (__int64)Pool2;
    if ( Pool2 )
    {
      ZwQueryInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessImageFileName, Pool2, ReturnLength, 0);
      v3 = *a1;
      a1[2] = 0;
      *((_WORD *)a1 + 4) = 0;
      v4 = *(_WORD *)v3 >> 1;
      if ( v4 )
      {
        for ( i = v4 - 1; i; --i )
        {
          v6 = *(_QWORD *)(v3 + 8);
          if ( *(_WORD *)(v6 + 2LL * i) == 92 )
          {
            v7 = 2 * (v4 - i) - 2;
            *((_WORD *)a1 + 5) = v7;
            *((_WORD *)a1 + 4) = v7;
            a1[2] = v6 + 2 * (i + 1LL);
            return a1;
          }
        }
      }
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140059fcc  mov     [rsp-18h+arg_18], rbx
0x140059fd1  push    rbp
0x140059fd2  push    rsi
0x140059fd3  push    rdi
0x140059fd4  mov     rbp, rsp
0x140059fd7  sub     rsp, 30h
0x140059fdb  xor     edx, edx; Val
0x140059fdd  mov     rbx, rcx
0x140059fe0  lea     r8d, [rdx+48h]; Size
0x140059fe4  call    memset
0x140059fe9  xor     edi, edi
0x140059feb  lea     rax, [rbp+Handle]
0x140059fef  mov     esi, 200h
0x140059ff4  mov     [rbp+Handle], rdi
0x140059ff8  mov     r9d, esi; HandleAttributes
0x140059ffb  mov     [rsp+30h+TokenHandle], rax; TokenHandle
0x14005a000  mov     r8b, 1; OpenAsSelf
0x14005a003  lea     edx, [rdi+8]; DesiredAccess
0x14005a006  lea     rcx, [rdi-2]; ThreadHandle
0x14005a00a  call    cs:__imp_ZwOpenThreadTokenEx
0x14005a011  nop     dword ptr [rax+rax+00h]
0x14005a016  mov     rcx, [rbp+Handle]
0x14005a01a  test    rcx, rcx
0x14005a01d  jz      short loc_14005A045
0x14005a01f  lea     rdx, [rbx+20h]
0x14005a023  call    SrpGetEnterpriseContextToken
0x14005a028  mov     rcx, [rbp+Handle]
0x14005a02c  lea     rdx, [rbx+38h]
0x14005a030  call    EEL_GetUserSidStringForToken
0x14005a035  mov     rcx, [rbp+Handle]; Handle
0x14005a039  call    cs:__imp_ZwClose
0x14005a040  nop     dword ptr [rax+rax+00h]
0x14005a045  mov     r8d, esi; HandleAttributes
0x14005a048  mov     [rbp+arg_10], rdi
0x14005a04c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14005a050  lea     r9, [rbp+arg_10]; TokenHandle
0x14005a054  mov     rcx, rsi; ProcessHandle
0x14005a057  mov     edx, 8; DesiredAccess
0x14005a05c  call    cs:__imp_ZwOpenProcessTokenEx
0x14005a063  nop     dword ptr [rax+rax+00h]
0x14005a068  mov     rcx, [rbp+arg_10]
0x14005a06c  test    rcx, rcx
0x14005a06f  jz      short loc_14005A097
0x14005a071  lea     rdx, [rbx+18h]
0x14005a075  call    SrpGetEnterpriseContextToken
0x14005a07a  mov     rcx, [rbp+arg_10]
0x14005a07e  lea     rdx, [rbx+28h]
0x14005a082  call    EEL_GetUserSidStringForToken
0x14005a087  mov     rcx, [rbp+arg_10]; Handle
0x14005a08b  call    cs:__imp_ZwClose
0x14005a092  nop     dword ptr [rax+rax+00h]
0x14005a097  xor     r9d, r9d; ProcessInformationLength
0x14005a09a  mov     [rbp+ReturnLength], edi
0x14005a09d  lea     rax, [rbp+ReturnLength]
0x14005a0a1  xor     r8d, r8d; ProcessInformation
0x14005a0a4  mov     rcx, rsi; ProcessHandle
0x14005a0a7  mov     [rsp+30h+TokenHandle], rax; ReturnLength
0x14005a0ac  lea     edx, [r9+1Bh]; ProcessInformationClass
0x14005a0b0  call    cs:__imp_ZwQueryInformationProcess
0x14005a0b7  nop     dword ptr [rax+rax+00h]
0x14005a0bc  cmp     eax, 0C0000004h
0x14005a0c1  jnz     loc_14005A165
0x14005a0c7  cmp     [rbp+ReturnLength], 10h
0x14005a0cb  jbe     loc_14005A165
0x14005a0d1  mov     edx, [rbp+ReturnLength]
0x14005a0d4  mov     ecx, 100h
0x14005a0d9  mov     r8d, 65706445h
0x14005a0df  call    cs:__imp_ExAllocatePool2
0x14005a0e6  nop     dword ptr [rax+rax+00h]
0x14005a0eb  mov     [rbx], rax
0x14005a0ee  test    rax, rax
0x14005a0f1  jz      short loc_14005A165
0x14005a0f3  mov     r9d, [rbp+ReturnLength]; ProcessInformationLength
0x14005a0f7  mov     r8, rax; ProcessInformation
0x14005a0fa  mov     edx, 1Bh; ProcessInformationClass
0x14005a0ff  mov     [rsp+30h+TokenHandle], rdi; ReturnLength
0x14005a104  mov     rcx, rsi; ProcessHandle
0x14005a107  call    cs:__imp_ZwQueryInformationProcess
0x14005a10e  nop     dword ptr [rax+rax+00h]
0x14005a113  mov     r9, [rbx]
0x14005a116  mov     [rbx+10h], rdi
0x14005a11a  mov     [rbx+8], di
0x14005a11e  movzx   ecx, word ptr [r9]
0x14005a122  shr     cx, 1
0x14005a125  jz      short loc_14005A165
0x14005a127  lea     edx, [rcx-1]
0x14005a12a  test    dx, dx
0x14005a12d  jz      short loc_14005A165
0x14005a12f  mov     r8, [r9+8]
0x14005a133  movzx   eax, dx
0x14005a136  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x14005a13c  jz      short loc_14005A148
0x14005a13e  mov     eax, 0FFFFh
0x14005a143  add     dx, ax
0x14005a146  jmp     short loc_14005A12A
0x14005a148  inc     rax
0x14005a14b  sub     cx, dx
0x14005a14e  add     cx, cx
0x14005a151  sub     cx, 2
0x14005a155  mov     [rbx+0Ah], cx
0x14005a159  lea     rax, [r8+rax*2]
0x14005a15d  mov     [rbx+8], cx
0x14005a161  mov     [rbx+10h], rax
0x14005a165  mov     rax, rbx
0x14005a168  mov     rbx, [rsp+30h+arg_18]
0x14005a16d  add     rsp, 30h
0x14005a171  pop     rdi
0x14005a172  pop     rsi
0x14005a173  pop     rbp
0x14005a174  retn
```
