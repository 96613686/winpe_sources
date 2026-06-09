# AslRegistryBuildUserPath

- ea: `0x140827e40`
- end: `0x140827f1c`
- name: `AslRegistryBuildUserPath`
- size: `220`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140acb824`

## callees

- `0x140388690`
- `0x140388750`
- `0x140827e40`
- `0x140855d90`
- `0x1408bf658`
- `0x1408c2f88`
- `0x14094b120`

## string_xrefs

- `0x140827e6c`: `RtlFormatCurrentUserKeyPath failed [%x]`
- `0x140827e7d`: `AslRegistryBuildUserPath`
- `0x140827ed4`: `AslRegistryBuildUserPath`

## pseudocode

```c
__int64 __fastcall AslRegistryBuildUserPath(PUNICODE_STRING Destination, PCWSTR Source)
{
  __int64 v4; // rcx
  int v5; // ebx
  __int64 v6; // rax
  unsigned __int16 v7; // ax
  wchar_t *v8; // rax
  UNICODE_STRING Sourcea; // [rsp+30h] [rbp-38h] BYREF

  Sourcea = 0;
  v5 = RtlFormatCurrentUserKeyPath(&Sourcea);
  if ( v5 >= 0 )
  {
    Destination->Length = 0;
    v6 = -1;
    do
      ++v6;
    while ( Source[v6] );
    v7 = Sourcea.Length + 2 * (v6 + 1);
    Destination->MaximumLength = v7;
    v8 = (wchar_t *)AslAlloc(v4, v7);
    Destination->Buffer = v8;
    if ( v8 )
    {
      RtlAppendUnicodeStringToString(Destination, &Sourcea);
      RtlAppendUnicodeToString(Destination, Source);
      v5 = 0;
    }
    else
    {
      v5 = -1073741801;
      AslLogCallPrintf(1, (unsigned int)"AslRegistryBuildUserPath", 1650, (unsigned int)"Out of memory");
    }
  }
  else
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"AslRegistryBuildUserPath",
      1638,
      (unsigned int)"RtlFormatCurrentUserKeyPath failed [%x]");
  }
  RtlFreeAnsiString(&Sourcea);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140827e40  push    rbx
0x140827e42  push    rbp
0x140827e43  push    rsi
0x140827e44  push    rdi
0x140827e45  push    r14
0x140827e47  sub     rsp, 40h
0x140827e4b  mov     rdi, rcx
0x140827e4e  xorps   xmm0, xmm0
0x140827e51  lea     rcx, [rsp+68h+Source]; UnicodeString
0x140827e56  mov     rbp, rdx
0x140827e59  movups  xmmword ptr [rsp+68h+Source.Length], xmm0
0x140827e5e  call    RtlFormatCurrentUserKeyPath
0x140827e63  xor     r14d, r14d
0x140827e66  mov     ebx, eax
0x140827e68  test    eax, eax
0x140827e6a  jns     short loc_140827E8F
0x140827e6c  lea     r9, aRtlformatcurre; "RtlFormatCurrentUserKeyPath failed [%x]"
0x140827e73  mov     [rsp+68h+var_48], eax
0x140827e77  mov     r8d, 666h
0x140827e7d  lea     rdx, aAslregistrybui_0; "AslRegistryBuildUserPath"
0x140827e84  lea     ecx, [r14+1]
0x140827e88  call    AslLogCallPrintf
0x140827e8d  jmp     short loc_140827F04
0x140827e8f  mov     [rdi], r14w
0x140827e93  or      rax, 0FFFFFFFFFFFFFFFFh
0x140827e97  inc     rax
0x140827e9a  cmp     [rbp+rax*2+0], r14w
0x140827ea0  jnz     short loc_140827E97
0x140827ea2  mov     esi, 1
0x140827ea7  add     ax, si
0x140827eaa  add     ax, ax
0x140827ead  add     ax, [rsp+68h+Source.Length]
0x140827eb2  movzx   edx, ax
0x140827eb5  mov     [rdi+2], dx
0x140827eb9  call    AslAlloc
0x140827ebe  mov     [rdi+8], rax
0x140827ec2  test    rax, rax
0x140827ec5  jnz     short loc_140827EE9
0x140827ec7  lea     r9, aOutOfMemory_0; "Out of memory"
0x140827ece  mov     r8d, 672h
0x140827ed4  lea     rdx, aAslregistrybui_0; "AslRegistryBuildUserPath"
0x140827edb  mov     ecx, esi
0x140827edd  mov     ebx, 0C0000017h
0x140827ee2  call    AslLogCallPrintf
0x140827ee7  jmp     short loc_140827F04
0x140827ee9  lea     rdx, [rsp+68h+Source]; Source
0x140827eee  mov     rcx, rdi; Destination
0x140827ef1  call    RtlAppendUnicodeStringToString
0x140827ef6  mov     rdx, rbp; Source
0x140827ef9  mov     rcx, rdi; Destination
0x140827efc  call    RtlAppendUnicodeToString
0x140827f01  mov     ebx, r14d
0x140827f04  lea     rcx, [rsp+68h+Source]; UnicodeString
0x140827f09  call    RtlFreeAnsiString
0x140827f0e  mov     eax, ebx
0x140827f10  add     rsp, 40h
0x140827f14  pop     r14
0x140827f16  pop     rdi
0x140827f17  pop     rsi
0x140827f18  pop     rbp
0x140827f19  pop     rbx
0x140827f1a  retn
```
