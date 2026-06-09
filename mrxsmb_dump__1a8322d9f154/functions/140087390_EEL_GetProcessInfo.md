# EEL_GetProcessInfo

- ea: `0x140087390`
- end: `0x14008753a`
- name: `EEL_GetProcessInfo`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140086c44`

## callees

- `0x14005967c`
- `0x14005a200`
- `0x140087390`
- `0x140087540`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400874a3`
- `ntoskrnl!ExAllocatePool2` at `0x1400874a3`
- `ntoskrnl!ZwClose` at `0x1400873fd`
- `ntoskrnl!ZwClose` at `0x14008744f`
- `ntoskrnl!ZwClose` at `0x1400873fd`
- `ntoskrnl!ZwClose` at `0x14008744f`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x1400873ce`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x1400873ce`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x140087420`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x140087420`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140087474`
- `ntoskrnl!ZwQueryInformationProcess` at `0x1400874cb`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140087474`
- `ntoskrnl!ZwQueryInformationProcess` at `0x1400874cb`

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
    EEL_GetUserSidStringForToken(Handle, (UNICODE_STRING *)(a1 + 7));
    ZwClose(Handle);
  }
  v11 = 0;
  ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0x200u, &v11);
  if ( v11 )
  {
    SrpGetEnterpriseContextToken(v11, a1 + 3);
    EEL_GetUserSidStringForToken(v11, (UNICODE_STRING *)(a1 + 5));
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
0x140087390  mov     [rsp-18h+arg_18], rbx
0x140087395  push    rbp
0x140087396  push    rsi
0x140087397  push    rdi
0x140087398  mov     rbp, rsp
0x14008739b  sub     rsp, 30h
0x14008739f  xor     edx, edx; Val
0x1400873a1  mov     rbx, rcx
0x1400873a4  lea     r8d, [rdx+48h]; Size
0x1400873a8  call    memset
0x1400873ad  xor     edi, edi
0x1400873af  lea     rax, [rbp+Handle]
0x1400873b3  mov     esi, 200h
0x1400873b8  mov     [rbp+Handle], rdi
0x1400873bc  mov     r9d, esi; HandleAttributes
0x1400873bf  mov     [rsp+30h+TokenHandle], rax; TokenHandle
0x1400873c4  mov     r8b, 1; OpenAsSelf
0x1400873c7  lea     edx, [rdi+8]; DesiredAccess
0x1400873ca  lea     rcx, [rdi-2]; ThreadHandle
0x1400873ce  call    cs:__imp_ZwOpenThreadTokenEx
0x1400873d5  nop     dword ptr [rax+rax+00h]
0x1400873da  mov     rcx, [rbp+Handle]
0x1400873de  test    rcx, rcx
0x1400873e1  jz      short loc_140087409
0x1400873e3  lea     rdx, [rbx+20h]
0x1400873e7  call    SrpGetEnterpriseContextToken
0x1400873ec  mov     rcx, [rbp+Handle]
0x1400873f0  lea     rdx, [rbx+38h]
0x1400873f4  call    EEL_GetUserSidStringForToken
0x1400873f9  mov     rcx, [rbp+Handle]; Handle
0x1400873fd  call    cs:__imp_ZwClose
0x140087404  nop     dword ptr [rax+rax+00h]
0x140087409  mov     r8d, esi; HandleAttributes
0x14008740c  mov     [rbp+arg_10], rdi
0x140087410  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140087414  lea     r9, [rbp+arg_10]; TokenHandle
0x140087418  mov     rcx, rsi; ProcessHandle
0x14008741b  mov     edx, 8; DesiredAccess
0x140087420  call    cs:__imp_ZwOpenProcessTokenEx
0x140087427  nop     dword ptr [rax+rax+00h]
0x14008742c  mov     rcx, [rbp+arg_10]
0x140087430  test    rcx, rcx
0x140087433  jz      short loc_14008745B
0x140087435  lea     rdx, [rbx+18h]
0x140087439  call    SrpGetEnterpriseContextToken
0x14008743e  mov     rcx, [rbp+arg_10]
0x140087442  lea     rdx, [rbx+28h]
0x140087446  call    EEL_GetUserSidStringForToken
0x14008744b  mov     rcx, [rbp+arg_10]; Handle
0x14008744f  call    cs:__imp_ZwClose
0x140087456  nop     dword ptr [rax+rax+00h]
0x14008745b  xor     r9d, r9d; ProcessInformationLength
0x14008745e  mov     [rbp+ReturnLength], edi
0x140087461  lea     rax, [rbp+ReturnLength]
0x140087465  xor     r8d, r8d; ProcessInformation
0x140087468  mov     rcx, rsi; ProcessHandle
0x14008746b  mov     [rsp+30h+TokenHandle], rax; ReturnLength
0x140087470  lea     edx, [r9+1Bh]; ProcessInformationClass
0x140087474  call    cs:__imp_ZwQueryInformationProcess
0x14008747b  nop     dword ptr [rax+rax+00h]
0x140087480  cmp     eax, 0C0000004h
0x140087485  jnz     loc_140087529
0x14008748b  cmp     [rbp+ReturnLength], 10h
0x14008748f  jbe     loc_140087529
0x140087495  mov     edx, [rbp+ReturnLength]
0x140087498  mov     ecx, 100h
0x14008749d  mov     r8d, 65706445h
0x1400874a3  call    cs:__imp_ExAllocatePool2
0x1400874aa  nop     dword ptr [rax+rax+00h]
0x1400874af  mov     [rbx], rax
0x1400874b2  test    rax, rax
0x1400874b5  jz      short loc_140087529
0x1400874b7  mov     r9d, [rbp+ReturnLength]; ProcessInformationLength
0x1400874bb  mov     r8, rax; ProcessInformation
0x1400874be  mov     edx, 1Bh; ProcessInformationClass
0x1400874c3  mov     [rsp+30h+TokenHandle], rdi; ReturnLength
0x1400874c8  mov     rcx, rsi; ProcessHandle
0x1400874cb  call    cs:__imp_ZwQueryInformationProcess
0x1400874d2  nop     dword ptr [rax+rax+00h]
0x1400874d7  mov     r9, [rbx]
0x1400874da  mov     [rbx+10h], rdi
0x1400874de  mov     [rbx+8], di
0x1400874e2  movzx   ecx, word ptr [r9]
0x1400874e6  shr     cx, 1
0x1400874e9  jz      short loc_140087529
0x1400874eb  lea     edx, [rcx-1]
0x1400874ee  test    dx, dx
0x1400874f1  jz      short loc_140087529
0x1400874f3  mov     r8, [r9+8]
0x1400874f7  movzx   eax, dx
0x1400874fa  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x140087500  jz      short loc_14008750C
0x140087502  mov     eax, 0FFFFh
0x140087507  add     dx, ax
0x14008750a  jmp     short loc_1400874EE
0x14008750c  inc     rax
0x14008750f  sub     cx, dx
0x140087512  add     cx, cx
0x140087515  sub     cx, 2
0x140087519  mov     [rbx+0Ah], cx
0x14008751d  lea     rax, [r8+rax*2]
0x140087521  mov     [rbx+8], cx
0x140087525  mov     [rbx+10h], rax
0x140087529  mov     rax, rbx
0x14008752c  mov     rbx, [rsp+30h+arg_18]
0x140087531  add     rsp, 30h
0x140087535  pop     rdi
0x140087536  pop     rsi
0x140087537  pop     rbp
0x140087538  retn
```
