# DpspCreateSecurityAttributes

- ea: `0x18001116c`
- end: `0x18001126e`
- name: `DpspCreateSecurityAttributes`
- size: `258`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800118f0`
- `0x180011c6c`

## callees

- `0x1800013a0`
- `0x180008ea0`
- `0x180009090`
- `0x18001116c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011187`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011187`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011256`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011256`
- `ntdll!AlpcInitializeMessageAttribute` at `0x1800111a5`
- `ntdll!AlpcInitializeMessageAttribute` at `0x1800111cf`
- `ntdll!AlpcInitializeMessageAttribute` at `0x1800111a5`
- `ntdll!AlpcInitializeMessageAttribute` at `0x1800111cf`
- `ntdll!AlpcGetMessageAttribute` at `0x180011226`
- `ntdll!AlpcGetMessageAttribute` at `0x180011226`

## string_xrefs

- `0x180011204`: `DpspCreateSecurityAttributes`

## pseudocode

```c
__int64 __fastcall DpspCreateSecurityAttributes(RTL_SRWLOCK *a1)
{
  __int64 v2; // rax
  void *v3; // rbx
  unsigned int v4; // ebx
  __int64 MessageAttribute; // rax
  __int64 v7; // [rsp+40h] [rbp+8h] BYREF

  if ( a1 )
    AcquireSRWLockExclusive(a1 + 2);
  v7 = 0;
  AlpcInitializeMessageAttribute(2684354560LL, 0, 0, &v7);
  v2 = WdipAlloc(v7);
  v3 = (void *)v2;
  if ( v2 && (int)AlpcInitializeMessageAttribute(2684354560LL, v2, v7, &v7) < 0 )
  {
    WdipFree(v3);
    v3 = 0;
  }
  a1[94].Ptr = v3;
  if ( v3 )
  {
    MessageAttribute = AlpcGetMessageAttribute(v3, 0x80000000LL);
    v4 = 0;
    *(_QWORD *)(MessageAttribute + 8) = 0;
    *((_DWORD *)a1[94].Ptr + 1) = -1610612736;
    *(_QWORD *)(MessageAttribute + 16) = -2;
    *(_DWORD *)MessageAttribute = 0x20000;
  }
  else
  {
    v4 = -2147467259;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpssrv.cpp",
      (int)L"DpspCreateSecurityAttributes",
      69,
      (int)L"Error = %d",
      5);
  }
  ReleaseSRWLockExclusive(a1 + 2);
  return v4;
}

```

## disassembly

```asm
0x18001116c  mov     [rsp+arg_8], rbx
0x180011171  mov     [rsp+arg_10], rsi
0x180011176  push    rdi
0x180011177  sub     rsp, 30h
0x18001117b  mov     rsi, rcx
0x18001117e  test    rcx, rcx
0x180011181  jz      short loc_18001118D
0x180011183  add     rcx, 10h; SRWLock
0x180011187  call    cs:__imp_AcquireSRWLockExclusive
0x18001118d  lea     r9, [rsp+38h+arg_0]
0x180011192  mov     [rsp+38h+arg_0], 0
0x18001119b  xor     r8d, r8d
0x18001119e  xor     edx, edx
0x1800111a0  mov     ecx, 0A0000000h
0x1800111a5  call    cs:__imp_AlpcInitializeMessageAttribute
0x1800111ab  mov     rcx, [rsp+38h+arg_0]
0x1800111b0  call    WdipAlloc
0x1800111b5  mov     rbx, rax
0x1800111b8  test    rax, rax
0x1800111bb  jz      short loc_1800111E3
0x1800111bd  mov     r8, [rsp+38h+arg_0]
0x1800111c2  lea     r9, [rsp+38h+arg_0]
0x1800111c7  mov     rdx, rax
0x1800111ca  mov     ecx, 0A0000000h
0x1800111cf  call    cs:__imp_AlpcInitializeMessageAttribute
0x1800111d5  test    eax, eax
0x1800111d7  jns     short loc_1800111E3
0x1800111d9  mov     rcx, rbx
0x1800111dc  call    WdipFree
0x1800111e1  xor     ebx, ebx
0x1800111e3  mov     [rsi+2F0h], rbx
0x1800111ea  test    rbx, rbx
0x1800111ed  jnz     short loc_18001121E
0x1800111ef  lea     r9, aErrorD; "Error = %d"
0x1800111f6  mov     dword ptr [rsp+38h+Args], 4005h; Args
0x1800111fe  mov     r8d, 45h ; 'E'; int
0x180011204  lea     rdx, aDpspcreatesecu; "DpspCreateSecurityAttributes"
0x18001120b  lea     rcx, aClientcoreBase_5; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180011212  mov     ebx, 80004005h
0x180011217  call    WdipTraceError
0x18001121c  jmp     short loc_180011252
0x18001121e  mov     edx, 80000000h
0x180011223  mov     rcx, rbx
0x180011226  call    cs:__imp_AlpcGetMessageAttribute
0x18001122c  xor     ebx, ebx
0x18001122e  mov     qword ptr [rax+8], 0
0x180011236  mov     rdx, [rsi+2F0h]
0x18001123d  mov     dword ptr [rdx+4], 0A0000000h
0x180011244  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFEh
0x18001124c  mov     dword ptr [rax], 20000h
0x180011252  lea     rcx, [rsi+10h]; SRWLock
0x180011256  call    cs:__imp_ReleaseSRWLockExclusive
0x18001125c  mov     rsi, [rsp+38h+arg_10]
0x180011261  mov     eax, ebx
0x180011263  mov     rbx, [rsp+38h+arg_8]
0x180011268  add     rsp, 30h
0x18001126c  pop     rdi
0x18001126d  retn
```
