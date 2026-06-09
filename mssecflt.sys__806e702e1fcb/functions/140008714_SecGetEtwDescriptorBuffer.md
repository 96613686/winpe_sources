# SecGetEtwDescriptorBuffer

- ea: `0x140008714`
- end: `0x14000876b`
- name: `SecGetEtwDescriptorBuffer`
- size: `87`
- prototype: ``
- caller_count: `41`
- callee_count: `2`
- tags: ``

## callers

- `0x140004e08`
- `0x140004fb0`
- `0x140005230`
- `0x140005418`
- `0x140005638`
- `0x140007870`
- `0x140007a30`
- `0x140007bb0`
- `0x14000c1f0`
- `0x14000c2a4`
- `0x14000c514`
- `0x140025b78`
- `0x140025cf8`
- `0x140025f00`
- `0x1400260b8`
- `0x1400262c8`
- `0x14002643c`
- `0x140026630`
- `0x14002685c`
- `0x14002b490`
- `0x14002b5ec`
- `0x14002b76c`
- `0x14002e97c`
- `0x140030ca8`
- `0x140031300`
- `0x140031598`
- `0x140031924`
- `0x140035b7c`
- `0x140035cfc`
- `0x140035e7c`
- `0x140036098`
- `0x140036258`
- `0x140036418`
- `0x1400365d8`
- `0x14003e4bc`
- `0x140043150`
- `0x1400434bc`
- `0x14004377c`
- `0x140043840`
- `0x140043bf4`
- `0x140043cc8`

## callees

- `0x140008714`
- `0x140011610`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000873c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000873c`

## pseudocode

```c
PSLIST_ENTRY __fastcall SecGetEtwDescriptorBuffer(unsigned int a1)
{
  PSLIST_ENTRY result; // rax
  char *v2; // rbx
  union _SLIST_HEADER *v3; // rcx

  if ( a1 > 0x32 )
    return 0;
  v2 = (char *)SecData + 896;
  v3 = (union _SLIST_HEADER *)((char *)SecData + 896);
  ++*((_DWORD *)SecData + 229);
  result = ExpInterlockedPopEntrySList(v3);
  if ( !result )
  {
    ++*((_DWORD *)v2 + 6);
    return (PSLIST_ENTRY)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))v2 + 6))(
                           *((unsigned int *)v2 + 9),
                           *((unsigned int *)v2 + 11),
                           *((unsigned int *)v2 + 10));
  }
  return result;
}

```

## disassembly

```asm
0x140008714  push    rbx
0x140008716  sub     rsp, 20h
0x14000871a  cmp     ecx, 32h ; '2'
0x14000871d  jbe     short loc_140008728
0x14000871f  xor     eax, eax
0x140008721  add     rsp, 20h
0x140008725  pop     rbx
0x140008726  retn
0x140008728  mov     rbx, cs:SecData
0x14000872f  add     rbx, 380h
0x140008736  mov     rcx, rbx; ListHead
0x140008739  inc     dword ptr [rbx+14h]
0x14000873c  call    cs:__imp_ExpInterlockedPopEntrySList
0x140008743  nop     dword ptr [rax+rax+00h]
0x140008748  test    rax, rax
0x14000874b  jnz     short loc_140008764
0x14000874d  inc     dword ptr [rbx+18h]
0x140008750  mov     edx, [rbx+2Ch]
0x140008753  mov     rax, [rbx+30h]
0x140008757  mov     r8d, [rbx+28h]
0x14000875b  mov     ecx, [rbx+24h]
0x14000875e  call    cs:__guard_dispatch_icall_fptr
0x140008764  add     rsp, 20h
0x140008768  pop     rbx
0x140008769  retn
```
