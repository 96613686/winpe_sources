# CdCleanupFileContext

- ea: `0x14001203c`
- end: `0x1400120c5`
- name: `CdCleanupFileContext`
- size: `137`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c8b4`
- `0x14000dc38`
- `0x140011138`
- `0x140011744`
- `0x1400135d0`

## callees

- `0x14001203c`

## import_xrefs

- `ntoskrnl!CcUnpinData` at `0x140012066`
- `ntoskrnl!CcUnpinData` at `0x140012066`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012094`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012094`

## pseudocode

```c
__int64 __fastcall CdCleanupFileContext(__int64 a1, __int64 a2)
{
  unsigned int v3; // edi
  __int64 v4; // rsi
  void *v5; // rcx
  void *v6; // rcx
  __int64 result; // rax

  v3 = 2;
  do
  {
    v4 = 224LL * v3;
    v5 = *(void **)(v4 + a2 + 112);
    if ( v5 )
    {
      CcUnpinData(v5);
      *(_QWORD *)(v4 + a2 + 112) = 0;
    }
    if ( (*(_BYTE *)(v4 + a2 + 153) & 1) != 0 )
    {
      v6 = *(void **)(v4 + a2 + 192);
      if ( v6 )
      {
        ExFreePoolWithTag(v6, 0);
        *(_QWORD *)(v4 + a2 + 192) = 0;
      }
    }
    result = v3--;
  }
  while ( (_DWORD)result );
  return result;
}

```

## disassembly

```asm
0x14001203c  mov     [rsp+arg_0], rbx
0x140012041  mov     [rsp+arg_8], rsi
0x140012046  push    rdi
0x140012047  sub     rsp, 20h
0x14001204b  mov     rbx, rdx
0x14001204e  mov     edi, 2
0x140012053  mov     eax, edi
0x140012055  imul    rsi, rax, 0E0h
0x14001205c  mov     rcx, [rsi+rbx+70h]; Bcb
0x140012061  test    rcx, rcx
0x140012064  jz      short loc_14001207B
0x140012066  call    cs:__imp_CcUnpinData
0x14001206d  nop     dword ptr [rax+rax+00h]
0x140012072  mov     qword ptr [rsi+rbx+70h], 0
0x14001207b  test    byte ptr [rsi+rbx+99h], 1
0x140012083  jz      short loc_1400120AC
0x140012085  mov     rcx, [rsi+rbx+0C0h]; P
0x14001208d  test    rcx, rcx
0x140012090  jz      short loc_1400120AC
0x140012092  xor     edx, edx; Tag
0x140012094  call    cs:__imp_ExFreePoolWithTag
0x14001209b  nop     dword ptr [rax+rax+00h]
0x1400120a0  mov     qword ptr [rsi+rbx+0C0h], 0
0x1400120ac  mov     eax, edi
0x1400120ae  dec     edi
0x1400120b0  test    eax, eax
0x1400120b2  jnz     short loc_140012053
0x1400120b4  mov     rbx, [rsp+28h+arg_0]
0x1400120b9  mov     rsi, [rsp+28h+arg_8]
0x1400120be  add     rsp, 20h
0x1400120c2  pop     rdi
0x1400120c3  retn
```
