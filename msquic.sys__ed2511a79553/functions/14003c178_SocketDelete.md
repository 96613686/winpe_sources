# SocketDelete

- ea: `0x14003c178`
- end: `0x14003c25d`
- name: `SocketDelete`
- size: `229`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14002df00`
- `0x14003501c`
- `0x140035190`
- `0x14003b850`

## callees

- `0x1400291f0`
- `0x14003ae64`
- `0x14003c178`
- `0x14003c980`
- `0x14003fdf8`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14003c1bc`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14003c1bc`
- `ntoskrnl!IoReuseIrp` at `0x14003c1de`
- `ntoskrnl!IoReuseIrp` at `0x14003c1de`

## pseudocode

```c
__int64 __fastcall SocketDelete(char *P)
{
  unsigned int i; // ebx
  __int64 v3; // rax
  __int64 result; // rax

  if ( (byte_14005C48E & 8) != 0 )
    McTemplateU0p_EtwWriteTransfer((__int64)P, (const EVENT_DESCRIPTOR *)QuicDatapathDestroyed, (__int64)P);
  if ( !*((_QWORD *)P + 11) )
    return CxPlatSocketDeleteComplete(P);
  for ( i = 0; i < CxPlatProcessorCount; ++i )
    ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)&P[8 * i + 424]);
  IoReuseIrp((PIRP)(P + 128), 0);
  v3 = *((_QWORD *)P + 39);
  *(_QWORD *)(v3 - 16) = CxPlatDataPathCloseSocketIoCompletion;
  *(_QWORD *)(v3 - 8) = P;
  *(_BYTE *)(v3 - 69) = -32;
  result = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)P + 11) + 8LL))(*((_QWORD *)P + 11), P + 128);
  if ( (_DWORD)result != 259 )
  {
    if ( (int)result < 0 && (byte_14005C48E & 4) != 0 )
      McTemplateU0pqs_EtwWriteTransfer(
        (__int64)"WskCloseSocket",
        (const EVENT_DESCRIPTOR *)QuicDatapathErrorStatus,
        (__int64)P,
        result,
        "WskCloseSocket");
    return CxPlatSocketDeleteComplete(P);
  }
  return result;
}

```

## disassembly

```asm
0x14003c178  mov     [rsp+arg_0], rbx
0x14003c17d  push    rdi
0x14003c17e  sub     rsp, 30h
0x14003c182  test    cs:byte_14005C48E, 8
0x14003c189  mov     rdi, rcx
0x14003c18c  jz      short loc_14003C19D
0x14003c18e  mov     r8, rcx
0x14003c191  lea     rdx, QuicDatapathDestroyed
0x14003c198  call    McTemplateU0p_EtwWriteTransfer
0x14003c19d  cmp     qword ptr [rdi+58h], 0
0x14003c1a2  jz      loc_14003C249
0x14003c1a8  xor     ebx, ebx
0x14003c1aa  cmp     cs:CxPlatProcessorCount, ebx
0x14003c1b0  jbe     short loc_14003C1D2
0x14003c1b2  mov     eax, ebx
0x14003c1b4  add     rax, 35h ; '5'
0x14003c1b8  lea     rcx, [rdi+rax*8]; RunRef
0x14003c1bc  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14003c1c3  nop     dword ptr [rax+rax+00h]
0x14003c1c8  inc     ebx
0x14003c1ca  cmp     ebx, cs:CxPlatProcessorCount
0x14003c1d0  jb      short loc_14003C1B2
0x14003c1d2  lea     rbx, [rdi+80h]
0x14003c1d9  xor     edx, edx; Iostatus
0x14003c1db  mov     rcx, rbx; Irp
0x14003c1de  call    cs:__imp_IoReuseIrp
0x14003c1e5  nop     dword ptr [rax+rax+00h]
0x14003c1ea  mov     rax, [rdi+138h]
0x14003c1f1  lea     rcx, CxPlatDataPathCloseSocketIoCompletion
0x14003c1f8  mov     rdx, rbx
0x14003c1fb  mov     [rax-10h], rcx
0x14003c1ff  mov     [rax-8], rdi
0x14003c203  mov     byte ptr [rax-45h], 0E0h
0x14003c207  mov     rcx, [rdi+58h]
0x14003c20b  mov     rax, [rcx]
0x14003c20e  mov     rax, [rax+8]
0x14003c212  call    _guard_dispatch_icall
0x14003c217  cmp     eax, 103h
0x14003c21c  jz      short loc_14003C251
0x14003c21e  test    eax, eax
0x14003c220  jns     short loc_14003C249
0x14003c222  test    cs:byte_14005C48E, 4
0x14003c229  jz      short loc_14003C249
0x14003c22b  lea     rcx, aWskclosesocket_0; "WskCloseSocket"
0x14003c232  mov     r9d, eax
0x14003c235  mov     r8, rdi
0x14003c238  mov     [rsp+38h+var_18], rcx
0x14003c23d  lea     rdx, QuicDatapathErrorStatus
0x14003c244  call    McTemplateU0pqs_EtwWriteTransfer
0x14003c249  mov     rcx, rdi; P
0x14003c24c  call    CxPlatSocketDeleteComplete
0x14003c251  mov     rbx, [rsp+38h+arg_0]
0x14003c256  add     rsp, 30h
0x14003c25a  pop     rdi
0x14003c25b  retn
```
