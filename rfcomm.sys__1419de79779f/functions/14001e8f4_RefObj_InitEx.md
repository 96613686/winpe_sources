# RefObj_InitEx

- ea: `0x14001e8f4`
- end: `0x14001ea2b`
- name: `RefObj_InitEx`
- size: `311`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400060c4`
- `0x140008104`
- `0x14000a060`
- `0x140010810`
- `0x1400135cc`
- `0x1400178b8`
- `0x1400195d0`

## callees

- `0x14001e8f4`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14001e9b0`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001e9b0`
- `ntoskrnl!ExAllocatePool2` at `0x14001e935`
- `ntoskrnl!ExAllocatePool2` at `0x14001e9e2`
- `ntoskrnl!ExAllocatePool2` at `0x14001e935`
- `ntoskrnl!ExAllocatePool2` at `0x14001e9e2`

## pseudocode

```c
void __fastcall RefObj_InitEx(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  bool v5; // zf
  __int64 Pool2; // rax
  signed __int32 v10; // ecx
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rax

  v5 = BthLib_RefObjDebugEnabled == 0;
  *(_DWORD *)a1 = 1;
  *(_QWORD *)(a1 + 8) = a2;
  *(_QWORD *)(a1 + 16) = 0;
  if ( !v5 )
  {
    Pool2 = ExAllocatePool2(64, 1048, 1415996754);
    *(_QWORD *)(a1 + 16) = Pool2;
    if ( Pool2 )
    {
      v10 = _InterlockedExchangeAdd((volatile signed __int32 *)(Pool2 + 1028), 1u);
      v11 = *(_QWORD *)(a1 + 16);
      v12 = 5LL * (v10 % 25);
      *(_DWORD *)(v11 + 8 * v12 + 24) = 0;
      *(_DWORD *)(v11 + 8 * v12 + 40) = a4;
      *(_QWORD *)(v11 + 8 * v12 + 48) = a3;
      *(_QWORD *)(v11 + 8 * v12 + 32) = a5;
      *(_QWORD *)(v11 + 8 * v12 + 56) = MEMORY[0xFFFFF78000000320];
      KeInitializeSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 16) + 8LL));
      **(_DWORD **)(a1 + 16) = 826885202;
      *(_DWORD *)(*(_QWORD *)(a1 + 16) + 1024LL) = 843662418;
      v13 = ExAllocatePool2(64, 40, 1415996754);
      if ( v13 )
      {
        *(_QWORD *)(v13 + 8) = a3;
        *(_DWORD *)(v13 + 32) = a4;
        *(_QWORD *)(v13 + 24) = a5;
        *(_QWORD *)(v13 + 16) = MEMORY[0xFFFFF78000000320];
        *(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL) = v13;
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 16) + 4LL));
      }
    }
  }
}

```

## disassembly

```asm
0x14001e8f4  push    rbx
0x14001e8f6  push    rbp
0x14001e8f7  push    rsi
0x14001e8f8  push    rdi
0x14001e8f9  sub     rsp, 28h
0x14001e8fd  cmp     cs:BthLib_RefObjDebugEnabled, 0
0x14001e904  mov     edi, r9d
0x14001e907  mov     rsi, r8
0x14001e90a  mov     dword ptr [rcx], 1
0x14001e910  mov     rbx, rcx
0x14001e913  mov     [rcx+8], rdx
0x14001e917  mov     qword ptr [rcx+10h], 0
0x14001e91f  jz      loc_14001EA21
0x14001e925  mov     edx, 418h
0x14001e92a  mov     ecx, 40h ; '@'
0x14001e92f  mov     r8d, 54666552h
0x14001e935  call    cs:__imp_ExAllocatePool2
0x14001e93c  nop     dword ptr [rax+rax+00h]
0x14001e941  mov     [rbx+10h], rax
0x14001e945  test    rax, rax
0x14001e948  jz      loc_14001EA21
0x14001e94e  mov     ecx, 1
0x14001e953  lock xadd [rax+404h], ecx
0x14001e95b  mov     rbp, [rsp+48h+arg_20]
0x14001e960  mov     eax, 51EB851Fh
0x14001e965  imul    ecx
0x14001e967  sar     edx, 3
0x14001e96a  mov     eax, edx
0x14001e96c  shr     eax, 1Fh
0x14001e96f  add     edx, eax
0x14001e971  imul    eax, edx, 19h
0x14001e974  mov     rdx, [rbx+10h]
0x14001e978  sub     ecx, eax
0x14001e97a  movsxd  rax, ecx
0x14001e97d  lea     r9, [rax+rax*4]
0x14001e981  mov     dword ptr [rdx+r9*8+18h], 0
0x14001e98a  mov     [rdx+r9*8+28h], edi
0x14001e98f  mov     [rdx+r9*8+30h], rsi
0x14001e994  mov     [rdx+r9*8+20h], rbp
0x14001e999  mov     rax, ds:0FFFFF78000000320h
0x14001e9a3  mov     [rdx+r9*8+38h], rax
0x14001e9a8  mov     rcx, [rbx+10h]
0x14001e9ac  add     rcx, 8; SpinLock
0x14001e9b0  call    cs:__imp_KeInitializeSpinLock
0x14001e9b7  nop     dword ptr [rax+rax+00h]
0x14001e9bc  mov     rax, [rbx+10h]
0x14001e9c0  mov     edx, 28h ; '('
0x14001e9c5  mov     r8d, 54666552h
0x14001e9cb  mov     dword ptr [rax], 31494452h
0x14001e9d1  lea     ecx, [rdx+18h]
0x14001e9d4  mov     rax, [rbx+10h]
0x14001e9d8  mov     dword ptr [rax+400h], 32494452h
0x14001e9e2  call    cs:__imp_ExAllocatePool2
0x14001e9e9  nop     dword ptr [rax+rax+00h]
0x14001e9ee  mov     rdx, rax
0x14001e9f1  test    rax, rax
0x14001e9f4  jz      short loc_14001EA19
0x14001e9f6  mov     [rax+8], rsi
0x14001e9fa  mov     [rax+20h], edi
0x14001e9fd  mov     [rax+18h], rbp
0x14001ea01  mov     rax, ds:0FFFFF78000000320h
0x14001ea0b  mov     [rdx+10h], rax
0x14001ea0f  mov     rcx, [rbx+10h]
0x14001ea13  mov     [rcx+10h], rdx
0x14001ea17  jmp     short loc_14001EA21
0x14001ea19  mov     rax, [rbx+10h]
0x14001ea1d  lock inc dword ptr [rax+4]
0x14001ea21  add     rsp, 28h
0x14001ea25  pop     rdi
0x14001ea26  pop     rsi
0x14001ea27  pop     rbp
0x14001ea28  pop     rbx
0x14001ea29  retn
```
