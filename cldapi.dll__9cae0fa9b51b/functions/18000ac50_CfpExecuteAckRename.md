# CfpExecuteAckRename

- ea: `0x18000ac50`
- end: `0x18000ada7`
- name: `CfpExecuteAckRename`
- size: `343`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006010`

## callees

- `0x180001aa0`
- `0x1800090d4`
- `0x18000ac50`
- `0x18000b5a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000acbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ad5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000acbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ad5c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000acd3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000acd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ad70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ad70`
- `FLTLIB!FilterSendMessage` at `0x18000ad3f`
- `FLTLIB!FilterSendMessage` at `0x18000ad3f`

## pseudocode

```c
__int64 __fastcall CfpExecuteAckRename(__int64 a1, __int64 a2)
{
  unsigned int v2; // esi
  DWORD *v3; // rbx
  int MessageHeaderSize; // eax
  unsigned int v7; // r8d
  int v8; // eax
  int v9; // r9d
  unsigned int v10; // r8d
  HANDLE ProcessHeap; // rax
  int v12; // edi
  HANDLE v13; // rax
  DWORD BytesReturned[4]; // [rsp+30h] [rbp-138h] BYREF
  _BYTE InBuffer[256]; // [rsp+40h] [rbp-128h] BYREF

  BytesReturned[0] = 0;
  v2 = 256;
  v3 = (DWORD *)InBuffer;
  MessageHeaderSize = CfpGetMessageHeaderSize();
  if ( ((MessageHeaderSize + 3) & 0xFFFFFFFC) + 12 < v7 )
    goto LABEL_6;
  v8 = CfpGetMessageHeaderSize();
  v2 = (v9 & (v8 + 11)) + 4;
  if ( v2 <= v10 )
    goto LABEL_6;
  ProcessHeap = GetProcessHeap();
  v3 = (DWORD *)HeapAlloc(ProcessHeap, 0, v2);
  v12 = v3 == 0 ? 8 : 0;
  if ( !v3 )
    v12 |= 0x80070000;
  if ( v12 >= 0 )
  {
LABEL_6:
    v12 = CfpBuildAckRenameMessage((__int64)v3, v2, a1, *(_DWORD *)(a2 + 8), *(_DWORD *)(a2 + 12));
    if ( v12 >= 0 )
      v12 = FilterSendMessage(hPort, v3, v3[2], 0, 0, BytesReturned);
  }
  if ( v3 && v3 != (DWORD *)InBuffer )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v3);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000ac50  mov     [rsp+arg_8], rbx
0x18000ac55  mov     [rsp+arg_10], rbp
0x18000ac5a  push    rsi
0x18000ac5b  push    rdi
0x18000ac5c  push    r14
0x18000ac5e  sub     rsp, 150h
0x18000ac65  mov     rax, cs:__security_cookie
0x18000ac6c  xor     rax, rsp
0x18000ac6f  mov     [rsp+168h+var_28], rax
0x18000ac77  mov     r8d, 100h
0x18000ac7d  mov     [rsp+168h+BytesReturned], 0
0x18000ac85  mov     esi, r8d
0x18000ac88  lea     rbx, [rsp+168h+InBuffer]
0x18000ac8d  mov     r14, rdx
0x18000ac90  mov     rbp, rcx
0x18000ac93  call    CfpGetMessageHeaderSize
0x18000ac98  add     eax, 3
0x18000ac9b  mov     r9d, 0FFFFFFFCh
0x18000aca1  and     eax, r9d
0x18000aca4  add     eax, 0Ch
0x18000aca7  cmp     eax, r8d
0x18000acaa  jb      short loc_18000ACFD
0x18000acac  call    CfpGetMessageHeaderSize
0x18000acb1  lea     esi, [rax+0Bh]
0x18000acb4  and     esi, r9d
0x18000acb7  add     esi, 4
0x18000acba  cmp     esi, r8d
0x18000acbd  jbe     short loc_18000ACFD
0x18000acbf  call    cs:__imp_GetProcessHeap
0x18000acc6  nop     dword ptr [rax+rax+00h]
0x18000accb  mov     r8d, esi; dwBytes
0x18000acce  xor     edx, edx; dwFlags
0x18000acd0  mov     rcx, rax; hHeap
0x18000acd3  call    cs:__imp_HeapAlloc
0x18000acda  nop     dword ptr [rax+rax+00h]
0x18000acdf  mov     rbx, rax
0x18000ace2  neg     rax
0x18000ace5  sbb     edi, edi
0x18000ace7  not     edi
0x18000ace9  and     edi, 8
0x18000acec  mov     eax, edi
0x18000acee  or      eax, 80070000h
0x18000acf3  test    rbx, rbx
0x18000acf6  cmovz   edi, eax
0x18000acf9  test    edi, edi
0x18000acfb  js      short loc_18000AD4D
0x18000acfd  mov     eax, [r14+0Ch]
0x18000ad01  mov     r8, rbp
0x18000ad04  mov     r9d, [r14+8]
0x18000ad08  mov     edx, esi
0x18000ad0a  mov     rcx, rbx
0x18000ad0d  mov     [rsp+168h+dwOutBufferSize], eax
0x18000ad11  call    CfpBuildAckRenameMessage
0x18000ad16  mov     edi, eax
0x18000ad18  test    eax, eax
0x18000ad1a  js      short loc_18000AD4D
0x18000ad1c  mov     r8d, [rbx+8]; dwInBufferSize
0x18000ad20  lea     rax, [rsp+168h+BytesReturned]
0x18000ad25  mov     rcx, qword ptr cs:hPort; hPort
0x18000ad2c  xor     r9d, r9d; lpOutBuffer
0x18000ad2f  mov     [rsp+168h+lpBytesReturned], rax; lpBytesReturned
0x18000ad34  mov     rdx, rbx; lpInBuffer
0x18000ad37  mov     [rsp+168h+dwOutBufferSize], 0; dwOutBufferSize
0x18000ad3f  call    cs:__imp_FilterSendMessage
0x18000ad46  nop     dword ptr [rax+rax+00h]
0x18000ad4b  mov     edi, eax
0x18000ad4d  test    rbx, rbx
0x18000ad50  jz      short loc_18000AD7C
0x18000ad52  lea     rax, [rsp+168h+InBuffer]
0x18000ad57  cmp     rbx, rax
0x18000ad5a  jz      short loc_18000AD7C
0x18000ad5c  call    cs:__imp_GetProcessHeap
0x18000ad63  nop     dword ptr [rax+rax+00h]
0x18000ad68  mov     r8, rbx; lpMem
0x18000ad6b  xor     edx, edx; dwFlags
0x18000ad6d  mov     rcx, rax; hHeap
0x18000ad70  call    cs:__imp_HeapFree
0x18000ad77  nop     dword ptr [rax+rax+00h]
0x18000ad7c  mov     eax, edi
0x18000ad7e  mov     rcx, [rsp+168h+var_28]
0x18000ad86  xor     rcx, rsp; StackCookie
0x18000ad89  call    __security_check_cookie
0x18000ad8e  lea     r11, [rsp+168h+var_18]
0x18000ad96  mov     rbx, [r11+28h]
0x18000ad9a  mov     rbp, [r11+30h]
0x18000ad9e  mov     rsp, r11
0x18000ada1  pop     r14
0x18000ada3  pop     rdi
0x18000ada4  pop     rsi
0x18000ada5  retn
```
