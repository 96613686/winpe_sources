# CdCompleteIo

- ea: `0x14000ca90`
- end: `0x14000cc0a`
- name: `CdCompleteIo`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000c870`

## callees

- `0x140001154`
- `0x140001500`
- `0x14000c3d0`
- `0x14000ca90`
- `0x14000d3e0`
- `0x14000d4a0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cb30`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cb30`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cb79`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cb79`
- `ntoskrnl!IofCompleteRequest` at `0x14000cbb2`
- `ntoskrnl!IofCompleteRequest` at `0x14000cbb2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000cb41`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000cb41`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000cb6d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000cb6d`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14000cb1f`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14000cb1f`
- `ntoskrnl!ProbeForRead` at `0x14000cafc`
- `ntoskrnl!ProbeForRead` at `0x14000cafc`

## pseudocode

```c
__int64 __fastcall CdCompleteIo(_QWORD *a1, unsigned __int8 a2, void *a3, int a4)
{
  __int64 v6; // rax
  IRP *v7; // rdi
  unsigned int v8; // ebx
  volatile void *v10; // rdx
  int v11; // eax
  __int128 v12; // [rsp+28h] [rbp-30h] BYREF
  volatile void *Address[2]; // [rsp+38h] [rbp-20h] BYREF
  SIZE_T Length; // [rsp+48h] [rbp-10h]

  v12 = 0;
  *(_OWORD *)Address = 0;
  Length = 0;
  if ( a4 != 40 )
    return 3221225990LL;
  if ( a2 )
  {
    if ( ((unsigned __int8)a3 & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(&v12, a3, 0x28u);
  }
  else
  {
    RtlCopyVolatileMemory(&v12, a3, 0x28u);
  }
  if ( a2 )
    ProbeForRead(Address[1], (unsigned int)Length, 1u);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(*a1, 0);
  v6 = CdpLookupIo(a1 + 5, &v12);
  v7 = (IRP *)v6;
  if ( v6 )
  {
    if ( (_DWORD)Length )
    {
      v11 = CdpWriteIoOutput(v6, a2, &Address[1], 0);
      if ( v11 < 0 )
      {
        DWORD2(v12) = v11;
        Address[0] = 0;
      }
    }
    if ( (unsigned __int8)CdpPrepareIoCompletion(v7, 0) )
    {
      v8 = 0;
      goto LABEL_11;
    }
    v7 = 0;
  }
  v8 = -1073741536;
LABEL_11:
  ExReleasePushLockExclusiveEx(*a1, 0);
  KeLeaveCriticalRegion();
  if ( v7 )
  {
    v10 = Address[0];
    v7->IoStatus.Status = DWORD2(v12);
    v7->IoStatus.Information = (ULONG_PTR)v10;
    IofCompleteRequest(v7, 0);
  }
  return v8;
}

```

## disassembly

```asm
0x14000ca90  mov     [rsp+arg_0], rbx
0x14000ca95  mov     [rsp+arg_10], rsi
0x14000ca9a  mov     [rsp+arg_8], dl
0x14000ca9e  push    rdi
0x14000ca9f  sub     rsp, 50h
0x14000caa3  mov     rax, r8
0x14000caa6  movzx   ebx, dl
0x14000caa9  mov     rsi, rcx
0x14000caac  xorps   xmm0, xmm0
0x14000caaf  xor     ecx, ecx
0x14000cab1  movups  [rsp+58h+var_30], xmm0
0x14000cab6  movups  xmmword ptr [rsp+58h+Address], xmm0
0x14000cabb  mov     [rsp+58h+Length], rcx
0x14000cac0  cmp     r9d, 28h ; '('
0x14000cac4  jnz     loc_14000CC03
0x14000caca  test    dl, dl
0x14000cacc  jz      short loc_14000CB0A
0x14000cace  test    al, 3
0x14000cad0  jnz     short loc_14000CB1F
0x14000cad2  test    dl, dl
0x14000cad4  jz      short loc_14000CB0A
0x14000cad6  mov     r8d, 28h ; '('; Size
0x14000cadc  mov     rdx, rax; Src
0x14000cadf  lea     rcx, [rsp+58h+var_30]; void *
0x14000cae4  call    RtlCopyFromUser
0x14000cae9  test    bl, bl
0x14000caeb  jz      short loc_14000CB2C
0x14000caed  mov     edx, dword ptr [rsp+58h+Length]; Length
0x14000caf1  mov     r8d, 1; Alignment
0x14000caf7  mov     rcx, [rsp+58h+Address+8]; Address
0x14000cafc  call    cs:__imp_ProbeForRead
0x14000cb03  nop     dword ptr [rax+rax+00h]
0x14000cb08  jmp     short loc_14000CB2C
0x14000cb0a  mov     r8d, 28h ; '('; Size
0x14000cb10  mov     rdx, rax; Src
0x14000cb13  lea     rcx, [rsp+58h+var_30]; void *
0x14000cb18  call    RtlCopyVolatileMemory
0x14000cb1d  jmp     short loc_14000CAE9
0x14000cb1f  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14000cb26  nop     dword ptr [rax+rax+00h]
0x14000cb2b  int     3; Trap to Debugger
0x14000cb2c  jmp     short loc_14000CB30
0x14000cb2e  jmp     short loc_14000CB8C
0x14000cb30  call    cs:__imp_KeEnterCriticalRegion
0x14000cb37  nop     dword ptr [rax+rax+00h]
0x14000cb3c  xor     edx, edx
0x14000cb3e  mov     rcx, [rsi]
0x14000cb41  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000cb48  nop     dword ptr [rax+rax+00h]
0x14000cb4d  lea     rcx, [rsi+28h]
0x14000cb51  lea     rdx, [rsp+58h+var_30]
0x14000cb56  call    CdpLookupIo
0x14000cb5b  mov     rdi, rax
0x14000cb5e  test    rax, rax
0x14000cb61  jnz     short loc_14000CBC0
0x14000cb63  mov     ebx, 0C0000120h
0x14000cb68  xor     edx, edx
0x14000cb6a  mov     rcx, [rsi]
0x14000cb6d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000cb74  nop     dword ptr [rax+rax+00h]
0x14000cb79  call    cs:__imp_KeLeaveCriticalRegion
0x14000cb80  nop     dword ptr [rax+rax+00h]
0x14000cb85  test    rdi, rdi
0x14000cb88  jnz     short loc_14000CB9D
0x14000cb8a  mov     eax, ebx
0x14000cb8c  mov     rbx, [rsp+58h+arg_0]
0x14000cb91  mov     rsi, [rsp+58h+arg_10]
0x14000cb96  add     rsp, 50h
0x14000cb9a  pop     rdi
0x14000cb9b  retn
0x14000cb9d  mov     rdx, [rsp+58h+Address]
0x14000cba2  mov     ecx, dword ptr [rsp+58h+var_30+8]
0x14000cba6  mov     [rdi+30h], ecx
0x14000cba9  mov     [rdi+38h], rdx
0x14000cbad  xor     edx, edx; PriorityBoost
0x14000cbaf  mov     rcx, rdi; Irp
0x14000cbb2  call    cs:__imp_IofCompleteRequest
0x14000cbb9  nop     dword ptr [rax+rax+00h]
0x14000cbbe  jmp     short loc_14000CB8A
0x14000cbc0  cmp     dword ptr [rsp+58h+Length], 0
0x14000cbc5  jnz     short loc_14000CBDD
0x14000cbc7  xor     edx, edx
0x14000cbc9  mov     rcx, rdi
0x14000cbcc  call    CdpPrepareIoCompletion
0x14000cbd1  test    al, al
0x14000cbd3  jz      short loc_14000CBD9
0x14000cbd5  xor     ebx, ebx
0x14000cbd7  jmp     short loc_14000CB68
0x14000cbd9  xor     edi, edi
0x14000cbdb  jmp     short loc_14000CB63
0x14000cbdd  xor     r9d, r9d
0x14000cbe0  lea     r8, [rsp+58h+Address+8]
0x14000cbe5  movzx   edx, bl
0x14000cbe8  mov     rcx, rdi
0x14000cbeb  call    CdpWriteIoOutput
0x14000cbf0  test    eax, eax
0x14000cbf2  jns     short loc_14000CBC7
0x14000cbf4  mov     dword ptr [rsp+58h+var_30+8], eax
0x14000cbf8  mov     [rsp+58h+Address], 0
0x14000cc01  jmp     short loc_14000CBC7
0x14000cc03  mov     eax, 0C0000206h
0x14000cc08  jmp     short loc_14000CB8C
0x14000e6e0  push    rbp
0x14000e6e2  sub     rsp, 20h
0x14000e6e6  mov     rbp, rdx
0x14000e6e9  xor     eax, eax
0x14000e6eb  cmp     [rbp+68h], al
0x14000e6ee  setnz   al
0x14000e6f1  mov     [rbp+20h], eax
0x14000e6f4  mov     eax, [rbp+20h]
0x14000e6f7  add     rsp, 20h
0x14000e6fb  pop     rbp
0x14000e6fc  retn
```
