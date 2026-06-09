# FatReadDirectoryFile

- ea: `0x140024584`
- end: `0x1400246b3`
- name: `FatReadDirectoryFile`
- size: `303`
- prototype: `__int64 __fastcall(int, int, int, int, char, PVOID *, PVOID *, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x14003062c`
- `0x14003172c`
- `0x1400319bc`
- `0x140031b84`
- `0x140031e8c`
- `0x140032e98`
- `0x140032ff0`

## callees

- `0x140023df4`
- `0x140024584`

## import_xrefs

- `ntoskrnl!CcMapData` at `0x140024666`
- `ntoskrnl!CcMapData` at `0x140024666`
- `ntoskrnl!CcPinRead` at `0x140024652`
- `ntoskrnl!CcPinRead` at `0x140024652`
- `ntoskrnl!ExRaiseStatus` at `0x1400245fe`
- `ntoskrnl!ExRaiseStatus` at `0x14002468c`
- `ntoskrnl!ExRaiseStatus` at `0x1400245fe`
- `ntoskrnl!ExRaiseStatus` at `0x14002468c`

## pseudocode

```c
_DWORD *__fastcall FatReadDirectoryFile(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        ULONG a4,
        char a5,
        PVOID *Bcb,
        PVOID *Buffer,
        _DWORD *a8)
{
  union _LARGE_INTEGER v9; // rdi
  unsigned int v12; // eax
  _DWORD *result; // rax
  unsigned int v14; // eax
  int v15; // eax
  struct _FILE_OBJECT *v16; // rcx
  ULONG v17; // r9d
  BOOLEAN v18; // al
  union _LARGE_INTEGER FileOffset; // [rsp+30h] [rbp-38h] BYREF

  v9.QuadPart = a3;
  FileOffset.QuadPart = 0;
  FatOpenDirectoryFile(a1, (char *)a2);
  v12 = *(_DWORD *)(a2 + 24);
  if ( v9.LowPart < v12 )
  {
    v14 = v12 - v9.LowPart;
    if ( v14 < a4 )
      a4 = v14;
    if ( ((v9.LowPart ^ (a4 + v9.LowPart - 1)) & 0xFFFC0000) != 0 )
    {
      *(_DWORD *)(a1 + 72) = -1073741566;
      ExRaiseStatus(-1073741566);
    }
    v15 = *(_DWORD *)(a1 + 68) & 2;
    v16 = *(struct _FILE_OBJECT **)(a2 + 344);
    FileOffset = v9;
    v17 = v15 != 0;
    if ( a5 )
      v18 = CcPinRead(v16, &FileOffset, a4, v17, Bcb, Buffer);
    else
      v18 = CcMapData(v16, &FileOffset, a4, v17, Bcb, Buffer);
    if ( !v18 )
    {
      *Bcb = 0;
      *Buffer = 0;
      *(_DWORD *)(a1 + 72) = -1073741608;
      ExRaiseStatus(-1073741608);
    }
    result = a8;
    *a8 = 0;
  }
  else
  {
    *Bcb = 0;
    *Buffer = 0;
    result = a8;
    *a8 = -1073741807;
  }
  return result;
}

```

## disassembly

```asm
0x140024584  push    rbx
0x140024586  push    rbp
0x140024587  push    rsi
0x140024588  push    rdi
0x140024589  push    r14
0x14002458b  sub     rsp, 40h
0x14002458f  mov     esi, r9d
0x140024592  mov     edi, r8d
0x140024595  mov     rbp, rdx
0x140024598  mov     qword ptr [rsp+68h+FileOffset], 0
0x1400245a1  mov     rbx, rcx
0x1400245a4  call    FatOpenDirectoryFile
0x1400245a9  mov     eax, [rbp+18h]
0x1400245ac  cmp     edi, eax
0x1400245ae  jb      short loc_1400245E1
0x1400245b0  mov     rax, [rsp+68h+arg_28]
0x1400245b8  mov     qword ptr [rax], 0
0x1400245bf  mov     rax, [rsp+68h+arg_30]
0x1400245c7  mov     qword ptr [rax], 0
0x1400245ce  mov     rax, [rsp+68h+arg_38]
0x1400245d6  mov     dword ptr [rax], 0C0000011h
0x1400245dc  jmp     loc_1400246A7
0x1400245e1  sub     eax, edi
0x1400245e3  cmp     eax, esi
0x1400245e5  cmovb   esi, eax
0x1400245e8  lea     eax, [rdi-1]
0x1400245eb  add     eax, esi
0x1400245ed  xor     eax, edi
0x1400245ef  test    eax, 0FFFC0000h
0x1400245f4  jz      short loc_14002460B
0x1400245f6  mov     ecx, 0C0000102h; Status
0x1400245fb  mov     [rbx+48h], ecx
0x1400245fe  call    cs:__imp_ExRaiseStatus
0x14002460b  mov     eax, [rbx+44h]
0x14002460e  lea     rdx, [rsp+68h+FileOffset]; FileOffset
0x140024613  mov     r14, [rsp+68h+arg_28]
0x14002461b  and     eax, 2
0x14002461e  mov     rcx, [rbp+158h]; FileObject
0x140024625  xor     r9d, r9d
0x140024628  mov     r8d, esi; Length
0x14002462b  mov     qword ptr [rsp+68h+FileOffset], rdi
0x140024630  mov     rdi, [rsp+68h+arg_30]
0x140024638  mov     [rsp+68h+Buffer], rdi; Buffer
0x14002463d  mov     [rsp+68h+Bcb], r14; Bcb
0x140024642  cmp     [rsp+68h+arg_20], r9b
0x14002464a  jz      short loc_140024660
0x14002464c  test    eax, eax
0x14002464e  setnz   r9b; Flags
0x140024652  call    cs:__imp_CcPinRead
0x140024659  nop     dword ptr [rax+rax+00h]
0x14002465e  jmp     short loc_140024672
0x140024660  test    eax, eax
0x140024662  setnz   r9b; Flags
0x140024666  call    cs:__imp_CcMapData
0x14002466d  nop     dword ptr [rax+rax+00h]
0x140024672  test    al, al
0x140024674  jnz     short loc_140024699
0x140024676  mov     qword ptr [r14], 0
0x14002467d  mov     ecx, 0C00000D8h; Status
0x140024682  mov     qword ptr [rdi], 0
0x140024689  mov     [rbx+48h], ecx
0x14002468c  call    cs:__imp_ExRaiseStatus
0x140024699  mov     rax, [rsp+68h+arg_38]
0x1400246a1  mov     dword ptr [rax], 0
0x1400246a7  add     rsp, 40h
0x1400246ab  pop     r14
0x1400246ad  pop     rdi
0x1400246ae  pop     rsi
0x1400246af  pop     rbp
0x1400246b0  pop     rbx
0x1400246b1  retn
```
