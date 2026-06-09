# DllInitialize

- ea: `0x180001270`
- end: `0x180001390`
- name: `DllInitialize`
- size: `288`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001270`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18000134c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180001371`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000134c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180001371`
- `ntoskrnl!ExAllocatePool2` at `0x1800012bb`
- `ntoskrnl!ExAllocatePool2` at `0x1800012ff`
- `ntoskrnl!ExAllocatePool2` at `0x180001327`
- `ntoskrnl!ExAllocatePool2` at `0x1800012bb`
- `ntoskrnl!ExAllocatePool2` at `0x1800012ff`
- `ntoskrnl!ExAllocatePool2` at `0x180001327`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800012e1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800012e1`

## pseudocode

```c
__int64 __fastcall DllInitialize(PCUNICODE_STRING SourceString)
{
  int v2; // ebx
  _QWORD *Pool2; // rax
  _QWORD *v4; // rdi
  __int64 v5; // rax

  Globals = 0;
  *(_OWORD *)&P = 0;
  Globals.MaximumLength = SourceString->Length + 2;
  Globals.Length = SourceString->Length;
  Globals.Buffer = (PWSTR)ExAllocatePool2(256, Globals.MaximumLength, 1213486401);
  if ( !Globals.Buffer )
  {
    v2 = -1073741670;
LABEL_9:
    if ( Globals.Buffer )
      ExFreePoolWithTag(Globals.Buffer, 0x48545541u);
    return (unsigned int)v2;
  }
  RtlCopyUnicodeString(&Globals, SourceString);
  v2 = -1073741801;
  Pool2 = (_QWORD *)ExAllocatePool2(258, 16, 1213486401);
  v4 = Pool2;
  if ( Pool2 )
  {
    *Pool2 = 4;
    v5 = ExAllocatePool2(256, 32, 1213486401);
    v4[1] = v5;
    if ( v5 )
    {
      P = v4;
      v2 = 0;
    }
    else
    {
      ExFreePoolWithTag(v4, 0x48545541u);
    }
  }
  if ( v2 < 0 )
    goto LABEL_9;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180001270  mov     [rsp+arg_0], rbx
0x180001275  mov     [rsp+arg_8], rsi
0x18000127a  push    rdi
0x18000127b  sub     rsp, 20h
0x18000127f  xorps   xmm0, xmm0
0x180001282  mov     rbx, rcx
0x180001285  movups  xmmword ptr cs:Globals.Length, xmm0
0x18000128c  mov     esi, 48545541h
0x180001291  movups  cs:P, xmm0
0x180001298  movzx   eax, word ptr [rcx]
0x18000129b  mov     r8d, esi
0x18000129e  add     ax, 2
0x1800012a2  movzx   edx, ax
0x1800012a5  mov     cs:Globals.MaximumLength, dx
0x1800012ac  movzx   eax, word ptr [rcx]
0x1800012af  mov     ecx, 100h
0x1800012b4  mov     cs:Globals.Length, ax
0x1800012bb  call    cs:__imp_ExAllocatePool2
0x1800012c2  nop     dword ptr [rax+rax+00h]
0x1800012c7  mov     cs:Globals.Buffer, rax
0x1800012ce  test    rax, rax
0x1800012d1  jz      loc_18000135E
0x1800012d7  mov     rdx, rbx; SourceString
0x1800012da  lea     rcx, Globals; DestinationString
0x1800012e1  call    cs:__imp_RtlCopyUnicodeString
0x1800012e8  nop     dword ptr [rax+rax+00h]
0x1800012ed  mov     r8d, esi
0x1800012f0  mov     edx, 10h
0x1800012f5  mov     ecx, 102h
0x1800012fa  mov     ebx, 0C0000017h
0x1800012ff  call    cs:__imp_ExAllocatePool2
0x180001306  nop     dword ptr [rax+rax+00h]
0x18000130b  mov     rdi, rax
0x18000130e  test    rax, rax
0x180001311  jz      short loc_180001358
0x180001313  mov     r8d, esi
0x180001316  mov     qword ptr [rax], 4
0x18000131d  mov     edx, 20h ; ' '
0x180001322  mov     ecx, 100h
0x180001327  call    cs:__imp_ExAllocatePool2
0x18000132e  nop     dword ptr [rax+rax+00h]
0x180001333  mov     [rdi+8], rax
0x180001337  test    rax, rax
0x18000133a  jz      short loc_180001347
0x18000133c  mov     qword ptr cs:P, rdi
0x180001343  xor     ebx, ebx
0x180001345  jmp     short loc_180001358
0x180001347  mov     edx, esi; Tag
0x180001349  mov     rcx, rdi; P
0x18000134c  call    cs:__imp_ExFreePoolWithTag
0x180001353  nop     dword ptr [rax+rax+00h]
0x180001358  test    ebx, ebx
0x18000135a  jns     short loc_18000137D
0x18000135c  jmp     short loc_180001363
0x18000135e  mov     ebx, 0C000009Ah
0x180001363  mov     rcx, cs:Globals.Buffer; P
0x18000136a  test    rcx, rcx
0x18000136d  jz      short loc_18000137D
0x18000136f  mov     edx, esi; Tag
0x180001371  call    cs:__imp_ExFreePoolWithTag
0x180001378  nop     dword ptr [rax+rax+00h]
0x18000137d  mov     rsi, [rsp+28h+arg_8]
0x180001382  mov     eax, ebx
0x180001384  mov     rbx, [rsp+28h+arg_0]
0x180001389  add     rsp, 20h
0x18000138d  pop     rdi
0x18000138e  retn
```
