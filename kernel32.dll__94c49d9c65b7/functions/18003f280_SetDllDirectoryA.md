# SetDllDirectoryA

- ea: `0x18003f280`
- end: `0x18003f30c`
- name: `SetDllDirectoryA`
- size: `140`
- prototype: `BOOL __stdcall(LPCSTR lpPathName)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000f920`
- `0x18003f280`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlInitAnsiStringEx` at `0x18003f2d0`
- `ntdll!RtlInitAnsiStringEx` at `0x18003f2d0`
- `ntdll!RtlFreeUnicodeString` at `0x18003f2ba`
- `ntdll!RtlFreeUnicodeString` at `0x18003f2ba`
- `ntdll!LdrSetDllDirectory` at `0x18003f2ad`
- `ntdll!LdrSetDllDirectory` at `0x18003f2ad`
- `ntdll!RtlInitUnicodeString` at `0x18003f2a2`
- `ntdll!RtlInitUnicodeString` at `0x18003f2a2`
- `KERNELBASE!GetEightBitStringToUnicodeStringRoutine` at `0x18003f2da`
- `KERNELBASE!GetEightBitStringToUnicodeStringRoutine` at `0x18003f2da`

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
0x18003f280  push    rbx
0x18003f282  sub     rsp, 40h
0x18003f286  xorps   xmm0, xmm0
0x18003f289  xorps   xmm1, xmm1
0x18003f28c  movups  xmmword ptr [rsp+48h+var_18.Length], xmm0
0x18003f291  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm1
0x18003f296  test    rcx, rcx
0x18003f299  jnz     short loc_18003F2C8
0x18003f29b  xor     edx, edx; SourceString
0x18003f29d  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18003f2a2  call    cs:__imp_RtlInitUnicodeString
0x18003f2a8  lea     rcx, [rsp+48h+DestinationString]
0x18003f2ad  call    cs:__imp_LdrSetDllDirectory
0x18003f2b3  lea     rcx, [rsp+48h+DestinationString]; UnicodeString
0x18003f2b8  mov     ebx, eax
0x18003f2ba  call    cs:__imp_RtlFreeUnicodeString
0x18003f2c0  test    ebx, ebx
0x18003f2c2  jns     short loc_18003F305
0x18003f2c4  mov     ecx, ebx
0x18003f2c6  jmp     short loc_18003F2F8
0x18003f2c8  mov     rdx, rcx; SourceString
0x18003f2cb  lea     rcx, [rsp+48h+var_18]; DestinationString
0x18003f2d0  call    cs:__imp_RtlInitAnsiStringEx
0x18003f2d6  test    eax, eax
0x18003f2d8  js      short loc_18003F2F6
0x18003f2da  call    cs:__imp_GetEightBitStringToUnicodeStringRoutine
0x18003f2e0  mov     r8b, 1
0x18003f2e3  lea     rdx, [rsp+48h+var_18]
0x18003f2e8  lea     rcx, [rsp+48h+DestinationString]
0x18003f2ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f2f2  test    eax, eax
0x18003f2f4  jns     short loc_18003F2A8
0x18003f2f6  mov     ecx, eax
0x18003f2f8  call    BaseSetLastNTError
0x18003f2fd  xor     eax, eax
0x18003f2ff  add     rsp, 40h
0x18003f303  pop     rbx
0x18003f304  retn
0x18003f305  mov     eax, 1
0x18003f30a  jmp     short loc_18003F2FF
```
