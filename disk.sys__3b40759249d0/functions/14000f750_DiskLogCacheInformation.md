# DiskLogCacheInformation

- ea: `0x14000f750`
- end: `0x14000f7fb`
- name: `DiskLogCacheInformation`
- size: `171`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ef98`

## callees

- `0x14000f750`

## import_xrefs

- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14000f76e`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14000f76e`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14000f7de`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14000f7de`

## pseudocode

```c
void __fastcall DiskLogCacheInformation(__int64 a1, __int64 a2, int a3)
{
  _DWORD *ErrorLogEntry; // rax
  unsigned __int8 *v7; // r9
  unsigned __int16 v8; // cx

  ErrorLogEntry = IoAllocateErrorLogEntry(*(PVOID *)(a1 + 8), 0x40u);
  if ( ErrorLogEntry )
  {
    v7 = *(unsigned __int8 **)(a1 + 96);
    v8 = *(_WORD *)(a1 + 640) & 1;
    ErrorLogEntry[5] = a3;
    *((_QWORD *)ErrorLogEntry + 3) = 0;
    *ErrorLogEntry = 1048591;
    ErrorLogEntry[4] = 1;
    ErrorLogEntry[3] = 2 * (v8 ^ 1) - 2147221472;
    ErrorLogEntry[10] = v7[13];
    ErrorLogEntry[11] = v7[14];
    ErrorLogEntry[12] = v7[15];
    ErrorLogEntry[13] = *(unsigned __int8 *)(a2 + 2);
    IoWriteErrorLogEntry(ErrorLogEntry);
  }
}

```

## disassembly

```asm
0x14000f750  mov     [rsp+arg_0], rbx
0x14000f755  mov     [rsp+arg_8], rsi
0x14000f75a  push    rdi
0x14000f75b  sub     rsp, 20h
0x14000f75f  mov     rsi, rdx
0x14000f762  mov     rbx, rcx
0x14000f765  mov     rcx, [rcx+8]; IoObject
0x14000f769  mov     dl, 40h ; '@'; EntrySize
0x14000f76b  mov     edi, r8d
0x14000f76e  call    cs:__imp_IoAllocateErrorLogEntry
0x14000f775  nop     dword ptr [rax+rax+00h]
0x14000f77a  xor     edx, edx
0x14000f77c  mov     r10, rax
0x14000f77f  test    rax, rax
0x14000f782  jz      short loc_14000F7EA
0x14000f784  movzx   ecx, word ptr [rbx+280h]
0x14000f78b  lea     eax, [rdx+1]
0x14000f78e  mov     r9, [rbx+60h]
0x14000f792  and     cx, ax
0x14000f795  mov     [r10+14h], edi
0x14000f799  mov     [r10+18h], rdx
0x14000f79d  mov     dword ptr [r10], 10000Fh
0x14000f7a4  mov     [r10+10h], eax
0x14000f7a8  movzx   ecx, cx
0x14000f7ab  xor     ecx, eax
0x14000f7ad  lea     ecx, ds:0FFFFFFFF80040020h[rcx*2]
0x14000f7b4  mov     [r10+0Ch], ecx
0x14000f7b8  mov     rcx, r10; ElEntry
0x14000f7bb  movzx   eax, byte ptr [r9+0Dh]
0x14000f7c0  mov     [r10+28h], eax
0x14000f7c4  movzx   eax, byte ptr [r9+0Eh]
0x14000f7c9  mov     [r10+2Ch], eax
0x14000f7cd  movzx   eax, byte ptr [r9+0Fh]
0x14000f7d2  mov     [r10+30h], eax
0x14000f7d6  movzx   eax, byte ptr [rsi+2]
0x14000f7da  mov     [r10+34h], eax
0x14000f7de  call    cs:__imp_IoWriteErrorLogEntry
0x14000f7e5  nop     dword ptr [rax+rax+00h]
0x14000f7ea  mov     rbx, [rsp+28h+arg_0]
0x14000f7ef  mov     rsi, [rsp+28h+arg_8]
0x14000f7f4  add     rsp, 20h
0x14000f7f8  pop     rdi
0x14000f7f9  retn
```
