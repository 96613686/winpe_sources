# FatFileExtensionIsPfile

- ea: `0x140031938`
- end: `0x1400319b5`
- name: `FatFileExtensionIsPfile`
- size: `125`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400065a4`
- `0x1400268c0`
- `0x14002b790`
- `0x14002ed1c`
- `0x140031e8c`
- `0x14003bea4`
- `0x140047960`

## callees

- `0x140031938`

## import_xrefs

- `ntoskrnl!FsRtlAreNamesEqual` at `0x14003199e`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x14003199e`

## pseudocode

```c
bool __fastcall FatFileExtensionIsPfile(unsigned __int16 *a1, BOOLEAN a2)
{
  __int64 v3; // rcx
  __int64 v5; // rax
  UNICODE_STRING ConstantNameB; // [rsp+20h] [rbp-28h] BYREF
  UNICODE_STRING ConstantNameA; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)(&ConstantNameA.MaximumLength + 1) = 0;
  v3 = *a1;
  *(_DWORD *)(&ConstantNameB.MaximumLength + 1) = 0;
  if ( (unsigned __int16)v3 <= 0xCu )
    return 0;
  v5 = *((_QWORD *)a1 + 1) - 12LL;
  *(_DWORD *)&ConstantNameA.Length = 786444;
  *(_DWORD *)&ConstantNameB.Length = 786444;
  ConstantNameA.Buffer = (PWSTR)(v5 + v3);
  ConstantNameB.Buffer = L".PFILE";
  return FsRtlAreNamesEqual(&ConstantNameA, &ConstantNameB, a2, 0) != 0;
}

```

## disassembly

```asm
0x140031938  sub     rsp, 48h
0x14003193c  mov     rax, rcx
0x14003193f  mov     dword ptr [rsp+48h+ConstantNameA+4], 0
0x140031947  movzx   ecx, word ptr [rcx]
0x14003194a  mov     r8d, 0Ch
0x140031950  mov     dword ptr [rsp+48h+ConstantNameB+4], 0
0x140031958  cmp     cx, r8w
0x14003195c  ja      short loc_140031962
0x14003195e  xor     al, al
0x140031960  jmp     short loc_1400319AF
0x140031962  mov     rax, [rax+8]
0x140031966  mov     r8b, dl; IgnoreCase
0x140031969  add     rax, 0FFFFFFFFFFFFFFF4h
0x14003196d  mov     dword ptr [rsp+48h+ConstantNameA.Length], 0C000Ch
0x140031975  add     rcx, rax
0x140031978  mov     dword ptr [rsp+48h+ConstantNameB.Length], 0C000Ch
0x140031980  mov     [rsp+48h+ConstantNameA.Buffer], rcx
0x140031985  lea     rax, aPfile_0; ".PFILE"
0x14003198c  lea     rcx, [rsp+48h+ConstantNameA]; ConstantNameA
0x140031991  mov     [rsp+48h+ConstantNameB.Buffer], rax
0x140031996  xor     r9d, r9d; UpcaseTable
0x140031999  lea     rdx, [rsp+48h+ConstantNameB]; ConstantNameB
0x14003199e  call    cs:__imp_FsRtlAreNamesEqual
0x1400319a5  nop     dword ptr [rax+rax+00h]
0x1400319aa  test    al, al
0x1400319ac  setnz   al
0x1400319af  add     rsp, 48h
0x1400319b3  retn
```
