# BiCreateEfiEntry

- ea: `0x180036364`
- end: `0x180036539`
- name: `BiCreateEfiEntry`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x180036c88`

## callees

- `0x18002e4a8`
- `0x18002e4fc`
- `0x180034254`
- `0x180034458`
- `0x180035684`
- `0x180035f38`
- `0x180036364`
- `0x180037884`
- `0x180038034`
- `0x18003825c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003651b`
- `ntdll!RtlFreeHeap` at `0x18003651b`

## string_xrefs

- `0x18003648f`: `Created new boot entry %d '%ws'`
- `0x18003640c`: `Created boot entry %d '%ws' using cached variable`
- `0x1800364e0`: `BiCreateEfiEntry failed %x`

## pseudocode

```c
__int64 __fastcall BiCreateEfiEntry(unsigned __int64 a1, __int64 a2)
{
  __int64 v2; // r12
  unsigned int *v4; // rdi
  int v6; // eax
  HANDLE v7; // r14
  int SavedBootEntry; // ebx
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v12; // [rsp+68h] [rbp+48h] BYREF
  PVOID P; // [rsp+70h] [rbp+50h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp+58h] BYREF

  v2 = a2 + 16;
  v12 = 0;
  Handle = 0;
  v4 = 0;
  P = 0;
  v6 = BcdOpenObject(a1, (_QWORD *)(a2 + 16), &Handle);
  v7 = Handle;
  SavedBootEntry = v6;
  if ( v6 < 0 )
    goto LABEL_16;
  if ( (*(_BYTE *)(a2 + 48) & 2) == 0 )
  {
    SavedBootEntry = BiCreateBootEntry((__int64)Handle, &P);
    if ( SavedBootEntry >= 0 )
    {
      v4 = (unsigned int *)P;
      SavedBootEntry = BiAddBootEntry(P, &v12);
      if ( SavedBootEntry >= 0 )
      {
        BiLogMessage(2, L"Created new boot entry %d '%ws'", v12, (char *)v4 + v4[4]);
        v4[2] = v12;
        v10 = v12;
        *(_DWORD *)(a2 + 48) |= 0x21u;
        *(_DWORD *)(a2 + 32) = v10;
        *(_QWORD *)(a2 + 40) = v4;
        SavedBootEntry = BiSaveFirmwareVariable(v7, v2, v4, v4[1]);
        if ( SavedBootEntry >= 0 )
        {
          *(_DWORD *)(a2 + 48) |= 2u;
          goto LABEL_17;
        }
      }
      goto LABEL_16;
    }
    goto LABEL_15;
  }
  SavedBootEntry = BiGetSavedBootEntry(Handle, &P);
  if ( SavedBootEntry < 0 )
  {
LABEL_15:
    v4 = (unsigned int *)P;
    goto LABEL_16;
  }
  v4 = (unsigned int *)P;
  if ( (*(_BYTE *)(a2 + 48) & 8) == 0 )
  {
    SavedBootEntry = BiUpdateObjectReferenceInEfiEntry(P, v7);
    if ( SavedBootEntry >= 0 )
    {
      *(_DWORD *)(a2 + 48) |= 0x20u;
      goto LABEL_7;
    }
LABEL_16:
    BiLogMessage(4, L"BiCreateEfiEntry failed %x", (unsigned int)SavedBootEntry);
    goto LABEL_17;
  }
LABEL_7:
  SavedBootEntry = BiAddBootEntry(v4, &v12);
  if ( SavedBootEntry < 0 )
    goto LABEL_16;
  BiLogMessage(2, L"Created boot entry %d '%ws' using cached variable", v12, (char *)v4 + v4[4]);
  v4[2] = v12;
  v9 = v12;
  *(_DWORD *)(a2 + 48) |= 1u;
  *(_DWORD *)(a2 + 32) = v9;
  *(_QWORD *)(a2 + 40) = v4;
  SavedBootEntry = BiSaveFirmwareVariable(v7, v2, v4, v4[1]);
  if ( SavedBootEntry < 0 )
    goto LABEL_16;
  SavedBootEntry = BiUpdateEfiEntry(a1, a2);
  if ( SavedBootEntry < 0 )
    goto LABEL_16;
LABEL_17:
  if ( v7 )
    BcdCloseObject(v7);
  if ( (*(_BYTE *)(a2 + 48) & 1) == 0 && v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  return (unsigned int)SavedBootEntry;
}

```

## disassembly

```asm
0x180036364  push    rbp
0x180036366  push    rbx
0x180036367  push    rsi
0x180036368  push    rdi
0x180036369  push    r12
0x18003636b  push    r14
0x18003636d  push    r15
0x18003636f  mov     rbp, rsp
0x180036372  sub     rsp, 20h
0x180036376  lea     r12, [rdx+10h]
0x18003637a  mov     [rbp+arg_8], 0
0x180036381  mov     rsi, rdx
0x180036384  mov     [rbp+Handle], 0
0x18003638c  xor     edi, edi
0x18003638e  lea     r8, [rbp+Handle]
0x180036392  mov     rdx, r12
0x180036395  mov     [rbp+P], rdi
0x180036399  mov     r15, rcx
0x18003639c  call    BcdOpenObject
0x1800363a1  mov     r14, [rbp+Handle]
0x1800363a5  mov     ebx, eax
0x1800363a7  test    eax, eax
0x1800363a9  js      loc_1800364DD
0x1800363af  test    byte ptr [rsi+30h], 2
0x1800363b3  lea     rdx, [rbp+P]
0x1800363b7  mov     rcx, r14
0x1800363ba  jz      loc_18003646A
0x1800363c0  call    BiGetSavedBootEntry
0x1800363c5  mov     ebx, eax
0x1800363c7  test    eax, eax
0x1800363c9  js      loc_1800364D9
0x1800363cf  test    byte ptr [rsi+30h], 8
0x1800363d3  mov     rdi, [rbp+P]
0x1800363d7  jnz     short loc_1800363F2
0x1800363d9  mov     rdx, r14
0x1800363dc  mov     rcx, rdi
0x1800363df  call    BiUpdateObjectReferenceInEfiEntry
0x1800363e4  mov     ebx, eax
0x1800363e6  test    eax, eax
0x1800363e8  js      loc_1800364DD
0x1800363ee  or      dword ptr [rsi+30h], 20h
0x1800363f2  lea     rdx, [rbp+arg_8]
0x1800363f6  mov     rcx, rdi
0x1800363f9  call    BiAddBootEntry
0x1800363fe  mov     ebx, eax
0x180036400  test    eax, eax
0x180036402  js      loc_1800364DD
0x180036408  mov     r9d, [rdi+10h]
0x18003640c  lea     rdx, aCreatedBootEnt; "Created boot entry %d '%ws' using cache"...
0x180036413  mov     r8d, [rbp+arg_8]
0x180036417  add     r9, rdi
0x18003641a  mov     ecx, 2
0x18003641f  call    BiLogMessage
0x180036424  mov     eax, [rbp+arg_8]
0x180036427  mov     r8, rdi
0x18003642a  mov     [rdi+8], eax
0x18003642d  mov     rdx, r12
0x180036430  mov     eax, [rbp+arg_8]
0x180036433  mov     rcx, r14
0x180036436  or      dword ptr [rsi+30h], 1
0x18003643a  mov     [rsi+20h], eax
0x18003643d  mov     [rsi+28h], rdi
0x180036441  mov     r9d, [rdi+4]
0x180036445  call    BiSaveFirmwareVariable
0x18003644a  mov     ebx, eax
0x18003644c  test    eax, eax
0x18003644e  js      loc_1800364DD
0x180036454  mov     rdx, rsi
0x180036457  mov     rcx, r15
0x18003645a  call    BiUpdateEfiEntry
0x18003645f  mov     ebx, eax
0x180036461  test    eax, eax
0x180036463  js      short loc_1800364DD
0x180036465  jmp     loc_1800364F1
0x18003646a  call    BiCreateBootEntry
0x18003646f  mov     ebx, eax
0x180036471  test    eax, eax
0x180036473  js      short loc_1800364D9
0x180036475  mov     rdi, [rbp+P]
0x180036479  lea     rdx, [rbp+arg_8]
0x18003647d  mov     rcx, rdi
0x180036480  call    BiAddBootEntry
0x180036485  mov     ebx, eax
0x180036487  test    eax, eax
0x180036489  js      short loc_1800364DD
0x18003648b  mov     r9d, [rdi+10h]
0x18003648f  lea     rdx, aCreatedNewBoot; "Created new boot entry %d '%ws'"
0x180036496  mov     r8d, [rbp+arg_8]
0x18003649a  add     r9, rdi
0x18003649d  mov     ecx, 2
0x1800364a2  call    BiLogMessage
0x1800364a7  mov     eax, [rbp+arg_8]
0x1800364aa  mov     r8, rdi
0x1800364ad  mov     [rdi+8], eax
0x1800364b0  mov     rdx, r12
0x1800364b3  mov     eax, [rbp+arg_8]
0x1800364b6  mov     rcx, r14
0x1800364b9  or      dword ptr [rsi+30h], 21h
0x1800364bd  mov     [rsi+20h], eax
0x1800364c0  mov     [rsi+28h], rdi
0x1800364c4  mov     r9d, [rdi+4]
0x1800364c8  call    BiSaveFirmwareVariable
0x1800364cd  mov     ebx, eax
0x1800364cf  test    eax, eax
0x1800364d1  js      short loc_1800364DD
0x1800364d3  or      dword ptr [rsi+30h], 2
0x1800364d7  jmp     short loc_1800364F1
0x1800364d9  mov     rdi, [rbp+P]
0x1800364dd  mov     r8d, ebx
0x1800364e0  lea     rdx, aBicreateefient; "BiCreateEfiEntry failed %x"
0x1800364e7  mov     ecx, 4
0x1800364ec  call    BiLogMessage
0x1800364f1  test    r14, r14
0x1800364f4  jz      short loc_1800364FE
0x1800364f6  mov     rcx, r14; Handle
0x1800364f9  call    BcdCloseObject
0x1800364fe  test    byte ptr [rsi+30h], 1
0x180036502  jnz     short loc_180036527
0x180036504  test    rdi, rdi
0x180036507  jz      short loc_180036527
0x180036509  mov     rcx, gs:60h
0x180036512  mov     r8, rdi; P
0x180036515  xor     edx, edx; Flags
0x180036517  mov     rcx, [rcx+30h]; HeapHandle
0x18003651b  call    cs:__imp_RtlFreeHeap
0x180036522  nop     dword ptr [rax+rax+00h]
0x180036527  mov     eax, ebx
0x180036529  add     rsp, 20h
0x18003652d  pop     r15
0x18003652f  pop     r14
0x180036531  pop     r12
0x180036533  pop     rdi
0x180036534  pop     rsi
0x180036535  pop     rbx
0x180036536  pop     rbp
0x180036537  retn
```
