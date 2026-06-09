# ClasspLogSystemEventWithDeviceNumber

- ea: `0x1400317e0`
- end: `0x140031862`
- name: `ClasspLogSystemEventWithDeviceNumber`
- size: `130`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140016350`
- `0x14002b700`
- `0x14002b800`
- `0x14002b8b0`
- `0x14005fe50`

## callees

- `0x140014110`
- `0x1400317e0`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!IoWriteErrorLogEntry` at `0x140031848`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x140031848`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x1400317f6`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x1400317f6`

## pseudocode

```c
__int64 __fastcall ClasspLogSystemEventWithDeviceNumber(_QWORD *a1, int a2)
{
  __int64 v2; // rbp
  unsigned int v4; // edi
  _WORD *ErrorLogEntry; // rax
  _WORD *v6; // rbx

  v2 = a1[8];
  v4 = -1073741670;
  ErrorLogEntry = IoAllocateErrorLogEntry(a1, 0x46u);
  v6 = ErrorLogEntry;
  if ( ErrorLogEntry )
  {
    memset(ErrorLogEntry, 0, 0x46u);
    v6[3] = 48;
    *((_DWORD *)v6 + 3) = a2;
    if ( RtlStringCbPrintfW(v6 + 24, 0x16u, (NTSTRSAFE_PCWSTR)"%\x00d", *(unsigned int *)(v2 + 588)) >= 0 )
      ++v6[2];
    IoWriteErrorLogEntry(v6);
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1400317e0  push    rbx
0x1400317e2  push    rbp
0x1400317e3  push    rsi
0x1400317e4  push    rdi
0x1400317e5  sub     rsp, 28h
0x1400317e9  mov     rbp, [rcx+40h]
0x1400317ed  mov     esi, edx
0x1400317ef  mov     dl, 46h ; 'F'; EntrySize
0x1400317f1  mov     edi, 0C000009Ah
0x1400317f6  call    cs:__imp_IoAllocateErrorLogEntry
0x1400317fd  nop     dword ptr [rax+rax+00h]
0x140031802  mov     rbx, rax
0x140031805  test    rax, rax
0x140031808  jz      short loc_140031856
0x14003180a  xor     edx, edx; Val
0x14003180c  mov     rcx, rax; void *
0x14003180f  lea     r8d, [rdx+46h]; Size
0x140031813  call    memset
0x140031818  mov     word ptr [rbx+6], 30h ; '0'
0x14003181e  lea     rcx, [rbx+30h]; pszDest
0x140031822  mov     [rbx+0Ch], esi
0x140031825  lea     r8, a0123456789abcd+10h; pszFormat
0x14003182c  mov     r9d, [rbp+24Ch]
0x140031833  mov     edx, 16h; cbDest
0x140031838  call    RtlStringCbPrintfW
0x14003183d  test    eax, eax
0x14003183f  js      short loc_140031845
0x140031841  inc     word ptr [rbx+4]
0x140031845  mov     rcx, rbx; ElEntry
0x140031848  call    cs:__imp_IoWriteErrorLogEntry
0x14003184f  nop     dword ptr [rax+rax+00h]
0x140031854  xor     edi, edi
0x140031856  mov     eax, edi
0x140031858  add     rsp, 28h
0x14003185c  pop     rdi
0x14003185d  pop     rsi
0x14003185e  pop     rbp
0x14003185f  pop     rbx
0x140031860  retn
```
