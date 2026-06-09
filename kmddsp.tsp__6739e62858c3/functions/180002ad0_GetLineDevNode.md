# GetLineDevNode

- ea: `0x180002ad0`
- end: `0x180002b66`
- name: `GetLineDevNode`
- size: `150`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180004520`
- `0x180005a10`
- `0x1800062b0`
- `0x180006820`
- `0x180006950`
- `0x180006a20`
- `0x180006e30`

## callees

- `0x180002ad0`
- `0x180007df8`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180002b0b`
- `KERNEL32!LocalAlloc` at `0x180002b0b`
- `KERNEL32!LeaveCriticalSection` at `0x180002b4b`
- `KERNEL32!LeaveCriticalSection` at `0x180002b4b`
- `KERNEL32!EnterCriticalSection` at `0x180002ae3`
- `KERNEL32!EnterCriticalSection` at `0x180002ae3`

## pseudocode

```c
_DWORD *__fastcall GetLineDevNode(int a1)
{
  _DWORD *i; // rbx
  _QWORD *v3; // rax

  EnterCriticalSection(&stru_18000E3B0);
  for ( i = qword_18000E3D8; i; i = *(_DWORD **)i )
  {
    if ( i[4] == a1 )
      goto LABEL_8;
  }
  v3 = LocalAlloc(0x40u, 0x28u);
  i = v3;
  if ( v3 )
  {
    *((_DWORD *)v3 + 4) = a1;
    *v3 = qword_18000E3D8;
    qword_18000E3D8 = v3;
  }
  else
  {
    TspLog(1, "GetLineDevNode: failed to alloc LINE_DEV_NODE");
  }
LABEL_8:
  LeaveCriticalSection(&stru_18000E3B0);
  return i;
}

```

## disassembly

```asm
0x180002ad0  mov     [rsp+arg_0], rbx
0x180002ad5  push    rdi
0x180002ad6  sub     rsp, 20h
0x180002ada  mov     edi, ecx
0x180002adc  lea     rcx, stru_18000E3B0; lpCriticalSection
0x180002ae3  call    cs:__imp_EnterCriticalSection
0x180002aea  nop     dword ptr [rax+rax+00h]
0x180002aef  mov     rbx, cs:qword_18000E3D8
0x180002af6  jmp     short loc_180002B00
0x180002af8  cmp     [rbx+10h], edi
0x180002afb  jz      short loc_180002B44
0x180002afd  mov     rbx, [rbx]
0x180002b00  test    rbx, rbx
0x180002b03  jnz     short loc_180002AF8
0x180002b05  lea     edx, [rbx+28h]; uBytes
0x180002b08  lea     ecx, [rbx+40h]; uFlags
0x180002b0b  call    cs:__imp_LocalAlloc
0x180002b12  nop     dword ptr [rax+rax+00h]
0x180002b17  mov     rbx, rax
0x180002b1a  test    rax, rax
0x180002b1d  jnz     short loc_180002B30
0x180002b1f  lea     rdx, aGetlinedevnode; "GetLineDevNode: failed to alloc LINE_DE"...
0x180002b26  lea     ecx, [rax+1]
0x180002b29  call    TspLog
0x180002b2e  jmp     short loc_180002B44
0x180002b30  mov     [rax+10h], edi
0x180002b33  mov     rax, cs:qword_18000E3D8
0x180002b3a  mov     [rbx], rax
0x180002b3d  mov     cs:qword_18000E3D8, rbx
0x180002b44  lea     rcx, stru_18000E3B0; lpCriticalSection
0x180002b4b  call    cs:__imp_LeaveCriticalSection
0x180002b52  nop     dword ptr [rax+rax+00h]
0x180002b57  mov     rax, rbx
0x180002b5a  mov     rbx, [rsp+28h+arg_0]
0x180002b5f  add     rsp, 20h
0x180002b63  pop     rdi
0x180002b64  retn
```
