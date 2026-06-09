# TpInitializePackage

- ea: `0x18004e6b4`
- end: `0x18004e787`
- name: `TpInitializePackage`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180050718`

## callees

- `0x18004e6b4`
- `0x18004e790`
- `0x18004ea24`
- `0x18015f1a0`
- `0x18016f030`

## string_xrefs

- `0x18004e6e8`: `Threadpool!`

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
0x18004e6b4  sub     rsp, 438h
0x18004e6bb  xor     edx, edx; Val
0x18004e6bd  lea     rcx, [rsp+438h+SystemInformation]; void *
0x18004e6c2  mov     r8d, 408h; Size
0x18004e6c8  call    memset$thunk$772440563353939046
0x18004e6cd  mov     [rsp+438h+ReturnLength], 0
0x18004e6d8  lea     r9, aCleanupGroup; "Cleanup Group"
0x18004e6df  mov     rcx, gs:60h
0x18004e6e8  lea     r8, aThreadpool; "Threadpool!"
0x18004e6ef  xor     edx, edx
0x18004e6f1  mov     rcx, [rcx+30h]
0x18004e6f5  call    RtlCreateTagHeap
0x18004e6fa  lea     r9, [rsp+438h+ReturnLength]; ReturnLength
0x18004e702  mov     cs:TppHeapTag, eax
0x18004e708  mov     r8d, 408h; SystemInformationLength
0x18004e70e  mov     [rsp+438h+ReturnLength], 0
0x18004e719  lea     rdx, [rsp+438h+SystemInformation]; SystemInformation
0x18004e71e  mov     ecx, 37h ; '7'; SystemInformationClass
0x18004e723  call    NtQuerySystemInformation
0x18004e728  test    eax, eax
0x18004e72a  js      short loc_18004E777
0x18004e72c  cmp     [rsp+438h+ReturnLength], 4
0x18004e734  jb      short loc_18004E780
0x18004e736  mov     eax, [rsp+438h+SystemInformation]
0x18004e73a  inc     eax
0x18004e73c  mov     cs:TppNumberNodes, eax
0x18004e742  call    TppQueryMaximumGroupCount
0x18004e747  movzx   eax, ax
0x18004e74a  mov     cs:TppMaximumGroups, eax
0x18004e750  test    eax, eax
0x18004e752  jz      short loc_18004E780
0x18004e754  mov     rax, gs:60h
0x18004e75d  mov     qword ptr [rax+388h], 0
0x18004e768  add     rax, 390h
0x18004e76e  mov     [rax+8], rax
0x18004e772  mov     [rax], rax
0x18004e775  xor     eax, eax
0x18004e777  add     rsp, 438h
0x18004e77e  retn
0x18004e780  mov     eax, 0C00000E5h
0x18004e785  jmp     short loc_18004E777
```
