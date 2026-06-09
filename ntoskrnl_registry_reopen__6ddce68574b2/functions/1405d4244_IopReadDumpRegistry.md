# IopReadDumpRegistry

- ea: `0x1405d4244`
- end: `0x1405d43ce`
- name: `IopReadDumpRegistry`
- size: `394`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1405d17d0`
- `0x140759514`

## callees

- `0x1405d4244`
- `0x14087852c`
- `0x14094b0a0`
- `0x140ab52a8`
- `0x140bb19f0`

## string_xrefs

- `0x1405d4261`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl`
- `0x1405d4352`: `UseRemovePagesArray`
- `0x1405d431a`: `MinRemoveAllocSize`

## pseudocode

```c
NTSTATUS __fastcall IopReadDumpRegistry(__int64 a1, _DWORD *a2)
{
  NTSTATUS result; // eax
  char v4; // [rsp+20h] [rbp-20h]
  _QWORD v5[2]; // [rsp+30h] [rbp-10h] BYREF
  HANDLE Handle; // [rsp+60h] [rbp+20h] BYREF

  Handle = 0;
  v5[0] = 8388734;
  v5[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl";
  v4 = 0;
  result = IopOpenRegistryKey(&Handle, 0, v5, 131097, v4);
  if ( result >= 0 )
  {
    if ( (int)IopGetRegistryValue(Handle) >= 0 )
    {
      if ( MEMORY[0xC] )
        IopAutoReboot = *(_DWORD *)MEMORY[8];
      ExFreePoolWithTag(0, 0);
    }
    if ( a2 && (int)IopGetRegistryValue(Handle) >= 0 )
    {
      if ( MEMORY[0xC] )
        *a2 = *(_DWORD *)MEMORY[8];
      ExFreePoolWithTag(0, 0);
    }
    if ( (int)IopGetRegistryValue(Handle) >= 0 )
    {
      if ( MEMORY[0xC] )
        MinRemoveAllocSize = *(_DWORD *)MEMORY[8];
      ExFreePoolWithTag(0, 0);
    }
    if ( (int)IopGetRegistryValue(Handle) >= 0 )
    {
      if ( MEMORY[0xC] )
        UseRemovePagesArray = *(_DWORD *)MEMORY[8];
      ExFreePoolWithTag(0, 0);
    }
    if ( (int)IopGetRegistryValue(Handle) >= 0 )
    {
      if ( MEMORY[0xC] )
        PartialDumpControl = *(_DWORD *)MEMORY[8];
      ExFreePoolWithTag(0, 0);
    }
    return ObCloseHandle(Handle, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1405d4244  mov     [rsp-8+arg_8], rbx
0x1405d4249  mov     [rsp-8+P], rcx
0x1405d424e  push    rbp
0x1405d424f  mov     rbp, rsp
0x1405d4252  sub     rsp, 40h
0x1405d4256  mov     rbx, rdx
0x1405d4259  mov     [rbp+Handle], 0
0x1405d4261  lea     rax, aRegistryMachin_32; "\\Registry\\Machine\\System\\CurrentCon"...
0x1405d4268  mov     [rbp+var_10], 80007Eh
0x1405d4270  xor     edx, edx
0x1405d4272  mov     [rbp+var_8], rax
0x1405d4276  mov     r9d, 20019h
0x1405d427c  mov     [rbp+P], 0
0x1405d4284  lea     r8, [rbp+var_10]
0x1405d4288  mov     [rsp+40h+var_20], 0
0x1405d428d  lea     rcx, [rbp+Handle]
0x1405d4291  call    IopOpenRegistryKey
0x1405d4296  test    eax, eax
0x1405d4298  js      loc_1405D43C2
0x1405d429e  mov     rcx, [rbp+Handle]; KeyHandle
0x1405d42a2  lea     r9, [rbp+P]
0x1405d42a6  xor     r8d, r8d
0x1405d42a9  lea     rdx, aAutoreboot; "AutoReboot"
0x1405d42b0  call    IopGetRegistryValue
0x1405d42b5  test    eax, eax
0x1405d42b7  js      short loc_1405D42D6
0x1405d42b9  mov     rcx, [rbp+P]; P
0x1405d42bd  cmp     dword ptr [rcx+0Ch], 0
0x1405d42c1  jz      short loc_1405D42CF
0x1405d42c3  mov     eax, [rcx+8]
0x1405d42c6  mov     edx, [rax+rcx]
0x1405d42c9  mov     cs:IopAutoReboot, edx
0x1405d42cf  xor     edx, edx; Tag
0x1405d42d1  call    ExFreePoolWithTag
0x1405d42d6  test    rbx, rbx
0x1405d42d9  jz      short loc_1405D430F
0x1405d42db  mov     rcx, [rbp+Handle]; KeyHandle
0x1405d42df  lea     r9, [rbp+P]
0x1405d42e3  xor     r8d, r8d
0x1405d42e6  lea     rdx, aCrashdumpenabl; "CrashDumpEnabled"
0x1405d42ed  call    IopGetRegistryValue
0x1405d42f2  test    eax, eax
0x1405d42f4  js      short loc_1405D430F
0x1405d42f6  mov     rcx, [rbp+P]; P
0x1405d42fa  cmp     dword ptr [rcx+0Ch], 0
0x1405d42fe  jz      short loc_1405D4308
0x1405d4300  mov     eax, [rcx+8]
0x1405d4303  mov     edx, [rax+rcx]
0x1405d4306  mov     [rbx], edx
0x1405d4308  xor     edx, edx; Tag
0x1405d430a  call    ExFreePoolWithTag
0x1405d430f  mov     rcx, [rbp+Handle]; KeyHandle
0x1405d4313  lea     r9, [rbp+P]
0x1405d4317  xor     r8d, r8d
0x1405d431a  lea     rdx, aMinremovealloc; "MinRemoveAllocSize"
0x1405d4321  call    IopGetRegistryValue
0x1405d4326  test    eax, eax
0x1405d4328  js      short loc_1405D4347
0x1405d432a  mov     rcx, [rbp+P]; P
0x1405d432e  cmp     dword ptr [rcx+0Ch], 0
0x1405d4332  jz      short loc_1405D4340
0x1405d4334  mov     eax, [rcx+8]
0x1405d4337  mov     edx, [rax+rcx]
0x1405d433a  mov     cs:MinRemoveAllocSize, edx
0x1405d4340  xor     edx, edx; Tag
0x1405d4342  call    ExFreePoolWithTag
0x1405d4347  mov     rcx, [rbp+Handle]; KeyHandle
0x1405d434b  lea     r9, [rbp+P]
0x1405d434f  xor     r8d, r8d
0x1405d4352  lea     rdx, aUseremovepages; "UseRemovePagesArray"
0x1405d4359  call    IopGetRegistryValue
0x1405d435e  test    eax, eax
0x1405d4360  js      short loc_1405D437F
0x1405d4362  mov     rcx, [rbp+P]; P
0x1405d4366  cmp     dword ptr [rcx+0Ch], 0
0x1405d436a  jz      short loc_1405D4378
0x1405d436c  mov     eax, [rcx+8]
0x1405d436f  mov     edx, [rax+rcx]
0x1405d4372  mov     cs:UseRemovePagesArray, edx
0x1405d4378  xor     edx, edx; Tag
0x1405d437a  call    ExFreePoolWithTag
0x1405d437f  mov     rcx, [rbp+Handle]; KeyHandle
0x1405d4383  lea     r9, [rbp+P]
0x1405d4387  xor     r8d, r8d
0x1405d438a  lea     rdx, aPartialdumpcon; "PartialDumpControl"
0x1405d4391  call    IopGetRegistryValue
0x1405d4396  test    eax, eax
0x1405d4398  js      short loc_1405D43B7
0x1405d439a  mov     rcx, [rbp+P]; P
0x1405d439e  cmp     dword ptr [rcx+0Ch], 0
0x1405d43a2  jz      short loc_1405D43B0
0x1405d43a4  mov     eax, [rcx+8]
0x1405d43a7  mov     edx, [rax+rcx]
0x1405d43aa  mov     cs:PartialDumpControl, edx
0x1405d43b0  xor     edx, edx; Tag
0x1405d43b2  call    ExFreePoolWithTag
0x1405d43b7  mov     rcx, [rbp+Handle]; Handle
0x1405d43bb  xor     edx, edx; PreviousMode
0x1405d43bd  call    ObCloseHandle
0x1405d43c2  mov     rbx, [rsp+40h+arg_8]
0x1405d43c7  add     rsp, 40h
0x1405d43cb  pop     rbp
0x1405d43cc  retn
```
