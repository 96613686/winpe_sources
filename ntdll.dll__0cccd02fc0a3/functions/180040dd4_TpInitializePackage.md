# TpInitializePackage

- ea: `0x180040dd4`
- end: `0x180040ea7`
- name: `TpInitializePackage`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800d6508`

## callees

- `0x180040dd4`
- `0x180040eb0`
- `0x180041144`
- `0x18015e990`
- `0x18016f030`

## string_xrefs

- `0x180040e08`: `Threadpool!`

## pseudocode

```c
NTSTATUS TpInitializePackage()
{
  NTSTATUS result; // eax
  unsigned __int16 MaximumGroupCount; // ax
  struct _PEB *v2; // rax
  _DWORD SystemInformation[262]; // [rsp+20h] [rbp-418h] BYREF
  ULONG ReturnLength; // [rsp+440h] [rbp+8h] BYREF

  memset_thunk_772440563353939046(SystemInformation, 0, 0x408u);
  ReturnLength = 0;
  TppHeapTag = RtlCreateTagHeap(NtCurrentPeb()->ProcessHeap);
  ReturnLength = 0;
  result = NtQuerySystemInformation(SystemNumaProcessorMap, SystemInformation, 0x408u, &ReturnLength);
  if ( result >= 0 )
  {
    if ( ReturnLength >= 4
      && (TppNumberNodes = SystemInformation[0] + 1,
          MaximumGroupCount = TppQueryMaximumGroupCount(),
          (TppMaximumGroups = MaximumGroupCount) != 0) )
    {
      v2 = NtCurrentPeb();
      v2->TppWorkerpListLock = 0;
      v2 = (struct _PEB *)((char *)v2 + 912);
      v2->Mutant = v2;
      *(_QWORD *)&v2->InheritedAddressSpace = v2;
      return 0;
    }
    else
    {
      return -1073741595;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180040dd4  sub     rsp, 438h
0x180040ddb  xor     edx, edx; Val
0x180040ddd  lea     rcx, [rsp+438h+SystemInformation]; void *
0x180040de2  mov     r8d, 408h; Size
0x180040de8  call    memset$thunk$772440563353939046
0x180040ded  mov     [rsp+438h+ReturnLength], 0
0x180040df8  lea     r9, aCleanupGroup; "Cleanup Group"
0x180040dff  mov     rcx, gs:60h
0x180040e08  lea     r8, aThreadpool; "Threadpool!"
0x180040e0f  xor     edx, edx
0x180040e11  mov     rcx, [rcx+30h]
0x180040e15  call    RtlCreateTagHeap
0x180040e1a  lea     r9, [rsp+438h+ReturnLength]; ReturnLength
0x180040e22  mov     cs:TppHeapTag, eax
0x180040e28  mov     r8d, 408h; SystemInformationLength
0x180040e2e  mov     [rsp+438h+ReturnLength], 0
0x180040e39  lea     rdx, [rsp+438h+SystemInformation]; SystemInformation
0x180040e3e  mov     ecx, 37h ; '7'; SystemInformationClass
0x180040e43  call    NtQuerySystemInformation
0x180040e48  test    eax, eax
0x180040e4a  js      short loc_180040E97
0x180040e4c  cmp     [rsp+438h+ReturnLength], 4
0x180040e54  jb      short loc_180040EA0
0x180040e56  mov     eax, [rsp+438h+SystemInformation]
0x180040e5a  inc     eax
0x180040e5c  mov     cs:TppNumberNodes, eax
0x180040e62  call    TppQueryMaximumGroupCount
0x180040e67  movzx   eax, ax
0x180040e6a  mov     cs:TppMaximumGroups, eax
0x180040e70  test    eax, eax
0x180040e72  jz      short loc_180040EA0
0x180040e74  mov     rax, gs:60h
0x180040e7d  mov     qword ptr [rax+388h], 0
0x180040e88  add     rax, 390h
0x180040e8e  mov     [rax+8], rax
0x180040e92  mov     [rax], rax
0x180040e95  xor     eax, eax
0x180040e97  add     rsp, 438h
0x180040e9e  retn
0x180040ea0  mov     eax, 0C00000E5h
0x180040ea5  jmp     short loc_180040E97
```
