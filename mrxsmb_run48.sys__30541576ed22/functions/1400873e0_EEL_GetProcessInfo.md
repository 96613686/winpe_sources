# EEL_GetProcessInfo

- ea: `0x1400873e0`
- end: `0x14008758a`
- name: `EEL_GetProcessInfo`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140086c94`

## callees

- `0x14005967c`
- `0x14005a200`
- `0x1400873e0`
- `0x140087590`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400874f3`
- `ntoskrnl!ExAllocatePool2` at `0x1400874f3`
- `ntoskrnl!ZwClose` at `0x14008744d`
- `ntoskrnl!ZwClose` at `0x14008749f`
- `ntoskrnl!ZwClose` at `0x14008744d`
- `ntoskrnl!ZwClose` at `0x14008749f`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x14008741e`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x14008741e`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x140087470`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x140087470`
- `ntoskrnl!ZwQueryInformationProcess` at `0x1400874c4`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14008751b`
- `ntoskrnl!ZwQueryInformationProcess` at `0x1400874c4`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14008751b`

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
0x1400873e0  mov     [rsp-18h+arg_18], rbx
0x1400873e5  push    rbp
0x1400873e6  push    rsi
0x1400873e7  push    rdi
0x1400873e8  mov     rbp, rsp
0x1400873eb  sub     rsp, 30h
0x1400873ef  xor     edx, edx; Val
0x1400873f1  mov     rbx, rcx
0x1400873f4  lea     r8d, [rdx+48h]; Size
0x1400873f8  call    memset
0x1400873fd  xor     edi, edi
0x1400873ff  lea     rax, [rbp+Handle]
0x140087403  mov     esi, 200h
0x140087408  mov     [rbp+Handle], rdi
0x14008740c  mov     r9d, esi; HandleAttributes
0x14008740f  mov     [rsp+30h+TokenHandle], rax; TokenHandle
0x140087414  mov     r8b, 1; OpenAsSelf
0x140087417  lea     edx, [rdi+8]; DesiredAccess
0x14008741a  lea     rcx, [rdi-2]; ThreadHandle
0x14008741e  call    cs:__imp_ZwOpenThreadTokenEx
0x140087425  nop     dword ptr [rax+rax+00h]
0x14008742a  mov     rcx, [rbp+Handle]
0x14008742e  test    rcx, rcx
0x140087431  jz      short loc_140087459
0x140087433  lea     rdx, [rbx+20h]
0x140087437  call    SrpGetEnterpriseContextToken
0x14008743c  mov     rcx, [rbp+Handle]
0x140087440  lea     rdx, [rbx+38h]
0x140087444  call    EEL_GetUserSidStringForToken
0x140087449  mov     rcx, [rbp+Handle]; Handle
0x14008744d  call    cs:__imp_ZwClose
0x140087454  nop     dword ptr [rax+rax+00h]
0x140087459  mov     r8d, esi; HandleAttributes
0x14008745c  mov     [rbp+arg_10], rdi
0x140087460  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140087464  lea     r9, [rbp+arg_10]; TokenHandle
0x140087468  mov     rcx, rsi; ProcessHandle
0x14008746b  mov     edx, 8; DesiredAccess
0x140087470  call    cs:__imp_ZwOpenProcessTokenEx
0x140087477  nop     dword ptr [rax+rax+00h]
0x14008747c  mov     rcx, [rbp+arg_10]
0x140087480  test    rcx, rcx
0x140087483  jz      short loc_1400874AB
0x140087485  lea     rdx, [rbx+18h]
0x140087489  call    SrpGetEnterpriseContextToken
0x14008748e  mov     rcx, [rbp+arg_10]
0x140087492  lea     rdx, [rbx+28h]
0x140087496  call    EEL_GetUserSidStringForToken
0x14008749b  mov     rcx, [rbp+arg_10]; Handle
0x14008749f  call    cs:__imp_ZwClose
0x1400874a6  nop     dword ptr [rax+rax+00h]
0x1400874ab  xor     r9d, r9d; ProcessInformationLength
0x1400874ae  mov     [rbp+ReturnLength], edi
0x1400874b1  lea     rax, [rbp+ReturnLength]
0x1400874b5  xor     r8d, r8d; ProcessInformation
0x1400874b8  mov     rcx, rsi; ProcessHandle
0x1400874bb  mov     [rsp+30h+TokenHandle], rax; ReturnLength
0x1400874c0  lea     edx, [r9+1Bh]; ProcessInformationClass
0x1400874c4  call    cs:__imp_ZwQueryInformationProcess
0x1400874cb  nop     dword ptr [rax+rax+00h]
0x1400874d0  cmp     eax, 0C0000004h
0x1400874d5  jnz     loc_140087579
0x1400874db  cmp     [rbp+ReturnLength], 10h
0x1400874df  jbe     loc_140087579
0x1400874e5  mov     edx, [rbp+ReturnLength]
0x1400874e8  mov     ecx, 100h
0x1400874ed  mov     r8d, 65706445h
0x1400874f3  call    cs:__imp_ExAllocatePool2
0x1400874fa  nop     dword ptr [rax+rax+00h]
0x1400874ff  mov     [rbx], rax
0x140087502  test    rax, rax
0x140087505  jz      short loc_140087579
0x140087507  mov     r9d, [rbp+ReturnLength]; ProcessInformationLength
0x14008750b  mov     r8, rax; ProcessInformation
0x14008750e  mov     edx, 1Bh; ProcessInformationClass
0x140087513  mov     [rsp+30h+TokenHandle], rdi; ReturnLength
0x140087518  mov     rcx, rsi; ProcessHandle
0x14008751b  call    cs:__imp_ZwQueryInformationProcess
0x140087522  nop     dword ptr [rax+rax+00h]
0x140087527  mov     r9, [rbx]
0x14008752a  mov     [rbx+10h], rdi
0x14008752e  mov     [rbx+8], di
0x140087532  movzx   ecx, word ptr [r9]
0x140087536  shr     cx, 1
0x140087539  jz      short loc_140087579
0x14008753b  lea     edx, [rcx-1]
0x14008753e  test    dx, dx
0x140087541  jz      short loc_140087579
0x140087543  mov     r8, [r9+8]
0x140087547  movzx   eax, dx
0x14008754a  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x140087550  jz      short loc_14008755C
0x140087552  mov     eax, 0FFFFh
0x140087557  add     dx, ax
0x14008755a  jmp     short loc_14008753E
0x14008755c  inc     rax
0x14008755f  sub     cx, dx
0x140087562  add     cx, cx
0x140087565  sub     cx, 2
0x140087569  mov     [rbx+0Ah], cx
0x14008756d  lea     rax, [r8+rax*2]
0x140087571  mov     [rbx+8], cx
0x140087575  mov     [rbx+10h], rax
0x140087579  mov     rax, rbx
0x14008757c  mov     rbx, [rsp+30h+arg_18]
0x140087581  add     rsp, 30h
0x140087585  pop     rdi
0x140087586  pop     rsi
0x140087587  pop     rbp
0x140087588  retn
```
