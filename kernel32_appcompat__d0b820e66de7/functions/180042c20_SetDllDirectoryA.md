# SetDllDirectoryA

- ea: `0x180042c20`
- end: `0x180042ccb`
- name: `SetDllDirectoryA`
- size: `171`
- prototype: `BOOL __stdcall(LPCSTR lpPathName)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000ccf0`
- `0x180042c20`
- `0x180084010`

## import_xrefs

- `ntdll!RtlInitAnsiStringEx` at `0x180042c82`
- `ntdll!RtlInitAnsiStringEx` at `0x180042c82`
- `ntdll!RtlFreeUnicodeString` at `0x180042c66`
- `ntdll!RtlFreeUnicodeString` at `0x180042c66`
- `ntdll!LdrSetDllDirectory` at `0x180042c53`
- `ntdll!LdrSetDllDirectory` at `0x180042c53`
- `ntdll!RtlInitUnicodeString` at `0x180042c42`
- `ntdll!RtlInitUnicodeString` at `0x180042c42`
- `KERNELBASE!GetEightBitStringToUnicodeStringRoutine` at `0x180042c92`
- `KERNELBASE!GetEightBitStringToUnicodeStringRoutine` at `0x180042c92`

## pseudocode

```c
BOOL __stdcall SetDllDirectoryA(LPCSTR lpPathName)
{
  int v1; // ebx
  __int64 v2; // rcx
  NTSTATUS inited; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 (__fastcall *EightBitStringToUnicodeStringRoutine)(struct _UNICODE_STRING *, struct _STRING *, __int64); // rax
  __int64 v9; // r8
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  struct _STRING v12; // [rsp+30h] [rbp-18h] BYREF

  v12 = 0;
  DestinationString = 0;
  if ( lpPathName )
  {
    inited = RtlInitAnsiStringEx(&v12, lpPathName);
    if ( inited < 0
      || (EightBitStringToUnicodeStringRoutine = (__int64 (__fastcall *)(struct _UNICODE_STRING *, struct _STRING *, __int64))GetEightBitStringToUnicodeStringRoutine(v5, v4, v6, v7),
          LOBYTE(v9) = 1,
          inited = EightBitStringToUnicodeStringRoutine(&DestinationString, &v12, v9),
          inited < 0) )
    {
      v2 = (unsigned int)inited;
      goto LABEL_8;
    }
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, 0);
  }
  v1 = LdrSetDllDirectory(&DestinationString);
  RtlFreeUnicodeString(&DestinationString);
  if ( v1 < 0 )
  {
    v2 = (unsigned int)v1;
LABEL_8:
    BaseSetLastNTError(v2);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180042c20  push    rbx
0x180042c22  sub     rsp, 40h
0x180042c26  xorps   xmm0, xmm0
0x180042c29  xorps   xmm1, xmm1
0x180042c2c  movups  xmmword ptr [rsp+48h+var_18.Length], xmm0
0x180042c31  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm1
0x180042c36  test    rcx, rcx
0x180042c39  jnz     short loc_180042C7A
0x180042c3b  xor     edx, edx; SourceString
0x180042c3d  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x180042c42  call    cs:__imp_RtlInitUnicodeString
0x180042c49  nop     dword ptr [rax+rax+00h]
0x180042c4e  lea     rcx, [rsp+48h+DestinationString]
0x180042c53  call    cs:__imp_LdrSetDllDirectory
0x180042c5a  nop     dword ptr [rax+rax+00h]
0x180042c5f  lea     rcx, [rsp+48h+DestinationString]; UnicodeString
0x180042c64  mov     ebx, eax
0x180042c66  call    cs:__imp_RtlFreeUnicodeString
0x180042c6d  nop     dword ptr [rax+rax+00h]
0x180042c72  test    ebx, ebx
0x180042c74  jns     short loc_180042CC4
0x180042c76  mov     ecx, ebx
0x180042c78  jmp     short loc_180042CB6
0x180042c7a  mov     rdx, rcx; SourceString
0x180042c7d  lea     rcx, [rsp+48h+var_18]; DestinationString
0x180042c82  call    cs:__imp_RtlInitAnsiStringEx
0x180042c89  nop     dword ptr [rax+rax+00h]
0x180042c8e  test    eax, eax
0x180042c90  js      short loc_180042CB4
0x180042c92  call    cs:__imp_GetEightBitStringToUnicodeStringRoutine
0x180042c99  nop     dword ptr [rax+rax+00h]
0x180042c9e  mov     r8b, 1
0x180042ca1  lea     rdx, [rsp+48h+var_18]
0x180042ca6  lea     rcx, [rsp+48h+DestinationString]
0x180042cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042cb0  test    eax, eax
0x180042cb2  jns     short loc_180042C4E
0x180042cb4  mov     ecx, eax
0x180042cb6  call    BaseSetLastNTError
0x180042cbb  xor     eax, eax
0x180042cbd  add     rsp, 40h
0x180042cc1  pop     rbx
0x180042cc2  retn
0x180042cc4  mov     eax, 1
0x180042cc9  jmp     short loc_180042CBD
```
