# CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::ExtractStrings(CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::CStrings *,void *)

- ea: `0x180002000`
- end: `0x18000206a`
- name: `?ExtractStrings@?$CDescriptor@VCInfoLevelStringEnum_SHARE_INFO@@@@QEAAXPEAVCStrings@1@PEAX@Z`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800016b0`
- `0x180005f30`

## callees

- `0x180002000`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180002034`
- `ntdll!RtlInitUnicodeString` at `0x180002034`
- `ntdll!RtlInitUnicodeString` at `0x180002063`

## pseudocode

```c
void __fastcall CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::ExtractStrings(
        __int64 a1,
        struct _UNICODE_STRING *a2,
        __int64 a3)
{
  unsigned int v6; // eax
  const WCHAR **v7; // rdx
  const WCHAR *v8; // rdx
  unsigned int v9; // eax
  const WCHAR **v10; // rdx
  const WCHAR *v11; // rdx

  _mm_lfence();
  v6 = *(_DWORD *)(a1 + 20);
  if ( v6 == -1 || (v7 = (const WCHAR **)(a3 + v6)) == 0 )
    v8 = 0;
  else
    v8 = *v7;
  RtlInitUnicodeString(a2, v8);
  v9 = *(_DWORD *)(a1 + 24);
  if ( v9 == -1 || (v10 = (const WCHAR **)(a3 + v9)) == 0 )
    v11 = 0;
  else
    v11 = *v10;
  RtlInitUnicodeString(a2 + 1, v11);
}

```

## disassembly

```asm
0x180002000  mov     [rsp+arg_0], rbx
0x180002005  mov     [rsp+arg_8], rsi
0x18000200a  push    rdi
0x18000200b  sub     rsp, 20h
0x18000200f  mov     rdi, r8
0x180002012  mov     rbx, rdx
0x180002015  mov     rsi, rcx
0x180002018  lfence
0x18000201b  mov     eax, [rcx+14h]
0x18000201e  cmp     eax, 0FFFFFFFFh
0x180002021  jz      short loc_18000202F
0x180002023  mov     edx, eax
0x180002025  add     rdx, r8
0x180002028  jz      short loc_18000202F
0x18000202a  mov     rdx, [rdx]
0x18000202d  jmp     short loc_180002031
0x18000202f  xor     edx, edx; SourceString
0x180002031  mov     rcx, rbx; DestinationString
0x180002034  call    cs:__imp_RtlInitUnicodeString
0x18000203a  mov     eax, [rsi+18h]
0x18000203d  cmp     eax, 0FFFFFFFFh
0x180002040  jz      short loc_18000204E
0x180002042  mov     edx, eax
0x180002044  add     rdx, rdi
0x180002047  jz      short loc_18000204E
0x180002049  mov     rdx, [rdx]
0x18000204c  jmp     short loc_180002050
0x18000204e  xor     edx, edx
0x180002050  lea     rcx, [rbx+10h]
0x180002054  mov     rbx, [rsp+28h+arg_0]
0x180002059  mov     rsi, [rsp+28h+arg_8]
0x18000205e  add     rsp, 20h
0x180002062  pop     rdi
0x180002063  jmp     cs:__imp_RtlInitUnicodeString
```
