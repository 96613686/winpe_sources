# AslRegistryBuildUserPath

- ea: `0x140825ed0`
- end: `0x140825fac`
- name: `AslRegistryBuildUserPath`
- size: `220`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140ac65d4`

## callees

- `0x1403f4770`
- `0x1403f4830`
- `0x140825ed0`
- `0x140866d10`
- `0x1408eeff0`
- `0x140979890`
- `0x14097d158`

## string_xrefs

- `0x140825f0d`: `AslRegistryBuildUserPath`
- `0x140825f64`: `AslRegistryBuildUserPath`
- `0x140825efc`: `RtlFormatCurrentUserKeyPath failed [%x]`

## pseudocode

```c
__int64 __fastcall AslRegistryBuildUserPath(PUNICODE_STRING Destination, PCWSTR Source)
{
  int v4; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rax
  unsigned __int16 v8; // ax
  wchar_t *v9; // rax
  int v11; // [rsp+20h] [rbp-48h]
  UNICODE_STRING Sourcea; // [rsp+30h] [rbp-38h] BYREF

  Sourcea = 0;
  v4 = RtlFormatCurrentUserKeyPath(&Sourcea);
  v6 = v4;
  if ( v4 >= 0 )
  {
    Destination->Length = 0;
    v7 = -1;
    do
      ++v7;
    while ( Source[v7] );
    v8 = Sourcea.Length + 2 * (v7 + 1);
    Destination->MaximumLength = v8;
    v9 = (wchar_t *)AslAlloc(v5, v8);
    Destination->Buffer = v9;
    if ( v9 )
    {
      RtlAppendUnicodeStringToString(Destination, &Sourcea);
      RtlAppendUnicodeToString(Destination, Source);
      v6 = 0;
    }
    else
    {
      v6 = -1073741801;
      AslLogCallPrintf(1, (unsigned int)"AslRegistryBuildUserPath", 1650, (unsigned int)"Out of memory");
    }
  }
  else
  {
    v11 = v4;
    AslLogCallPrintf(
      1,
      (unsigned int)"AslRegistryBuildUserPath",
      1638,
      (unsigned int)"RtlFormatCurrentUserKeyPath failed [%x]",
      v11);
  }
  RtlFreeAnsiString(&Sourcea);
  return v6;
}

```

## disassembly

```asm
0x140825ed0  push    rbx
0x140825ed2  push    rbp
0x140825ed3  push    rsi
0x140825ed4  push    rdi
0x140825ed5  push    r14
0x140825ed7  sub     rsp, 40h
0x140825edb  mov     rdi, rcx
0x140825ede  xorps   xmm0, xmm0
0x140825ee1  lea     rcx, [rsp+68h+Source]; UnicodeString
0x140825ee6  mov     rbp, rdx
0x140825ee9  movups  xmmword ptr [rsp+68h+Source.Length], xmm0
0x140825eee  call    RtlFormatCurrentUserKeyPath
0x140825ef3  xor     r14d, r14d
0x140825ef6  mov     ebx, eax
0x140825ef8  test    eax, eax
0x140825efa  jns     short loc_140825F1F
0x140825efc  lea     r9, aRtlformatcurre; "RtlFormatCurrentUserKeyPath failed [%x]"
0x140825f03  mov     [rsp+68h+var_48], eax
0x140825f07  mov     r8d, 666h
0x140825f0d  lea     rdx, aAslregistrybui_0; "AslRegistryBuildUserPath"
0x140825f14  lea     ecx, [r14+1]
0x140825f18  call    AslLogCallPrintf
0x140825f1d  jmp     short loc_140825F94
0x140825f1f  mov     [rdi], r14w
0x140825f23  or      rax, 0FFFFFFFFFFFFFFFFh
0x140825f27  inc     rax
0x140825f2a  cmp     [rbp+rax*2+0], r14w
0x140825f30  jnz     short loc_140825F27
0x140825f32  mov     esi, 1
0x140825f37  add     ax, si
0x140825f3a  add     ax, ax
0x140825f3d  add     ax, [rsp+68h+Source.Length]
0x140825f42  movzx   edx, ax
0x140825f45  mov     [rdi+2], dx
0x140825f49  call    AslAlloc
0x140825f4e  mov     [rdi+8], rax
0x140825f52  test    rax, rax
0x140825f55  jnz     short loc_140825F79
0x140825f57  lea     r9, aOutOfMemory_0; "Out of memory"
0x140825f5e  mov     r8d, 672h
0x140825f64  lea     rdx, aAslregistrybui_0; "AslRegistryBuildUserPath"
0x140825f6b  mov     ecx, esi
0x140825f6d  mov     ebx, 0C0000017h
0x140825f72  call    AslLogCallPrintf
0x140825f77  jmp     short loc_140825F94
0x140825f79  lea     rdx, [rsp+68h+Source]; Source
0x140825f7e  mov     rcx, rdi; Destination
0x140825f81  call    RtlAppendUnicodeStringToString
0x140825f86  mov     rdx, rbp; Source
0x140825f89  mov     rcx, rdi; Destination
0x140825f8c  call    RtlAppendUnicodeToString
0x140825f91  mov     ebx, r14d
0x140825f94  lea     rcx, [rsp+68h+Source]; UnicodeString
0x140825f99  call    RtlFreeAnsiString
0x140825f9e  mov     eax, ebx
0x140825fa0  add     rsp, 40h
0x140825fa4  pop     r14
0x140825fa6  pop     rdi
0x140825fa7  pop     rsi
0x140825fa8  pop     rbp
0x140825fa9  pop     rbx
0x140825faa  retn
```
