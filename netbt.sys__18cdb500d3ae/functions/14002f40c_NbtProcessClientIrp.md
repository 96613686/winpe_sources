# NbtProcessClientIrp

- ea: `0x14002f40c`
- end: `0x14002f879`
- name: `NbtProcessClientIrp`
- size: `1133`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14001e168`
- `0x140021610`
- `0x140024cc0`
- `0x14002d608`

## callees

- `0x1400280f4`
- `0x14002f3d4`
- `0x14002f40c`
- `0x1400406e8`
- `0x140041104`
- `0x140043574`
- `0x140043600`
- `0x140043880`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14002f838`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14002f838`
- `ntoskrnl!IoBuildPartialMdl` at `0x14002f76c`
- `ntoskrnl!IoBuildPartialMdl` at `0x14002f76c`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002f750`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002f750`
- `ntoskrnl!IofCompleteRequest` at `0x14002f6ac`
- `ntoskrnl!IofCompleteRequest` at `0x14002f6ac`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002f6bc`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002f6bc`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002f69b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002f69b`
- `TDI!TdiCopyBufferToMdl` at `0x14002f56e`
- `TDI!TdiCopyBufferToMdl` at `0x14002f56e`

## pseudocode

```c
__int64 __fastcall NbtProcessClientIrp(struct _MDL **a1, ULONG a2, __int64 a3, char a4)
{
  IRP *v4; // rdi
  struct _MDL *v5; // rbx
  ULONG v6; // r14d
  KSPIN_LOCK *v7; // rsi
  ULONG v8; // ebp
  struct _EPROCESS **p_Process; // r15
  ULONG *v10; // r12
  int *v11; // r13
  const char *v12; // rcx
  unsigned int v13; // r15d
  ULONG_PTR MappedSystemVa_low; // rax
  ULONG v15; // eax
  struct _MDL **p_MdlAddress; // r12
  struct _MDL *v17; // r9
  void *v18; // rcx
  ULONG v19; // r8d
  NTSTATUS v20; // eax
  ULONG v21; // edx
  int MappedSystemVa; // r9d
  int v23; // r13d
  int v24; // edx
  int v25; // r10d
  const char *v26; // rcx
  const char *v27; // rax
  __int64 result; // rax
  unsigned int v29; // edx
  struct _MDL *v30; // rax
  unsigned int v31; // ecx
  unsigned int v32; // r8d
  struct _MDL *v33; // r13
  char *v34; // r15
  PVOID *StartVa; // rcx
  ULONG v36; // ebp
  ULONG v37; // eax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v39; // rbx
  __int64 v40; // [rsp+60h] [rbp-48h]
  int v41; // [rsp+60h] [rbp-48h]
  struct _EPROCESS **v42; // [rsp+B0h] [rbp+8h]
  int v43; // [rsp+B0h] [rbp+8h]
  int v44; // [rsp+C0h] [rbp+18h]
  ULONG BytesCopied; // [rsp+C8h] [rbp+20h] BYREF

  LOBYTE(BytesCopied) = a4;
  v4 = (IRP *)a3;
  v5 = a1[3];
  v6 = a2;
  v7 = (KSPIN_LOCK *)a1;
  v40 = *(_QWORD *)(a3 + 184);
  v8 = *(_DWORD *)(v40 + 8);
  p_Process = &v5[4].Process;
  v42 = &v5[4].Process;
  v10 = (ULONG *)(a1 + 35);
  v11 = (int *)&v5[4].Process + 1;
  if ( (BYTE3(xmmword_140038420) & 8) != 0 )
  {
    v12 = "New";
    if ( !a4 )
      v12 = "Old";
    WPP_SF_qqsqddddd(
      (_DWORD)v12,
      a2,
      a3,
      (_DWORD)v7,
      (char)v5,
      (__int64)v12,
      a3,
      v8,
      *v11,
      *(_DWORD *)p_Process,
      *v10,
      a2);
    a4 = BytesCopied;
  }
  else
  {
    v42 = &v5[4].Process;
  }
  if ( a4 )
  {
    NbtValidateReceiveRequest(v4);
    if ( *v11 == *(_DWORD *)p_Process )
    {
      v13 = 0;
      v4->IoStatus.Status = 0;
      MappedSystemVa_low = 0;
      LODWORD(a3) = 0;
LABEL_29:
      v4->IoStatus.Information = MappedSystemVa_low;
      if ( (BYTE3(xmmword_140038420) & 8) != 0 )
        WPP_SF_qqqd(1051, 30, WPP_e821b053d0733e5b06ead08bfa3e1f1d_Traceguids, v7, v5, v4, a3);
      KeReleaseSpinLockFromDpcLevel(v7 + 13);
      IofCompleteRequest(v4, 0);
      KeAcquireSpinLockAtDpcLevel(v7 + 13);
      return v13;
    }
    if ( !*(_DWORD *)(v40 + 8) )
    {
      LODWORD(a3) = -2147483643;
      v13 = 0;
LABEL_11:
      v4->IoStatus.Status = -2147483643;
      MappedSystemVa_low = 0;
      goto LABEL_29;
    }
    LODWORD(v5[4].MappedSystemVa) = 0;
    HIDWORD(v5[4].MappedSystemVa) = v8;
    v15 = *v10;
    p_MdlAddress = &v4->MdlAddress;
    if ( v15 )
    {
      v17 = *p_MdlAddress;
      v18 = (void *)v7[29];
      v19 = v6;
      if ( v8 < v6 )
        v19 = v8;
      BytesCopied = 0;
      if ( v19 >= v15 )
        v19 = v15;
      v20 = TdiCopyBufferToMdl(v18, 0, v19, v17, 0, &BytesCopied);
      v21 = BytesCopied;
      *v11 += BytesCopied;
      v6 -= v21;
      LODWORD(v5[4].MappedSystemVa) += v21;
      v13 = v20;
      NbtCopyToStartOfIndicate(v7);
      MappedSystemVa = (int)v5[4].MappedSystemVa;
      v23 = *v11;
      v44 = MappedSystemVa;
      v24 = *(_DWORD *)v42;
      v43 = *(_DWORD *)v42;
      v25 = *(_DWORD *)(v40 + 8);
      v41 = v25;
      if ( (BYTE3(xmmword_140038420) & 8) != 0 )
      {
        v26 = "TRUE";
        v27 = "TRUE";
        if ( MappedSystemVa != v25 )
          v27 = "FALSE";
        if ( v23 != v24 )
          v26 = "FALSE";
        WPP_SF_qqqdssd(
          (_DWORD)v26,
          v24,
          (unsigned int)"FALSE",
          (_DWORD)v7,
          (char)v5,
          (char)v4,
          BytesCopied,
          (__int64)v26,
          (__int64)v27,
          v13);
        v24 = v43;
        MappedSystemVa = v44;
        v25 = v41;
      }
      a3 = 2147483653LL;
      if ( v13 == -2147483643 )
        goto LABEL_11;
      if ( v23 == v24 )
      {
        v4->IoStatus.Status = 0;
        LODWORD(a3) = 0;
LABEL_28:
        MappedSystemVa_low = LODWORD(v5[4].MappedSystemVa);
        goto LABEL_29;
      }
      if ( MappedSystemVa == v25 )
      {
        v4->IoStatus.Status = -2147483643;
        goto LABEL_28;
      }
    }
    v5[4].Next = (struct _MDL *)v4;
    *(_QWORD *)&v5[4].Size = *p_MdlAddress;
  }
  v29 = (unsigned int)v5[4].MappedSystemVa;
  if ( v29 )
  {
    v30 = *(struct _MDL **)&v5[4].Size;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    do
    {
      if ( !v30 )
        break;
      v33 = v30;
      v32 = v29 - v31;
      v31 += v30->ByteCount;
      v30 = v30->Next;
    }
    while ( v31 <= v29 );
    if ( v31 >= v29 )
      v34 = (char *)v33->StartVa + v33->ByteOffset + v32;
    else
      v34 = 0;
    *(_QWORD *)v5[4].StartVa = 0;
    StartVa = (PVOID *)v5[4].StartVa;
    if ( (*((_BYTE *)StartVa + 10) & 0x20) != 0 )
      MmUnmapLockedPages(StartVa[3], (PMDL)v5[4].StartVa);
    IoBuildPartialMdl(v33, (PMDL)v5[4].StartVa, v34, 0);
    if ( (BYTE3(xmmword_140038420) & 8) != 0 )
      WPP_SF_qqqq(1051, 28, WPP_e821b053d0733e5b06ead08bfa3e1f1d_Traceguids, v7, v5, v5[4].StartVa, v4);
    a1 = (struct _MDL **)v5[4].StartVa;
    *a1 = v33->Next;
    v4->MdlAddress = (PMDL)v5[4].StartVa;
  }
  v36 = v8 - LODWORD(v5[4].MappedSystemVa);
  if ( (BYTE3(xmmword_140038420) & 8) != 0 )
  {
    v37 = v36;
    if ( v6 < v36 )
      v37 = v6;
    WPP_SF_qqqddd(a1, 29, a3, v7, v5, v4, v6, v36, v37);
  }
  if ( v6 >= v36 )
    v6 = v36;
  CurrentStackLocation = v4->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&NbtClientIrpCompletion;
  CurrentStackLocation[-1].Context = v7;
  CurrentStackLocation[-1].Control = -32;
  v39 = v4->Tail.Overlay.CurrentStackLocation;
  *(_WORD *)&v39[-1].MajorFunction = 2063;
  v39[-1].DeviceObject = IoGetRelatedDeviceObject((PFILE_OBJECT)v7[6]);
  v39[-1].FileObject = (PFILE_OBJECT)v7[6];
  result = 3221225494LL;
  *(&v39[-1].Parameters.Read.Length + 1) = 32;
  v39[-1].Parameters.Read.Length = v6;
  return result;
}

```

## disassembly

```asm
0x14002f40c  mov     r11, rsp
0x14002f40f  mov     [r11+10h], rbx
0x14002f413  mov     [r11+20h], r9b
0x14002f417  push    rbp
0x14002f418  push    rsi
0x14002f419  push    rdi
0x14002f41a  push    r12
0x14002f41c  push    r13
0x14002f41e  push    r14
0x14002f420  push    r15
0x14002f422  sub     rsp, 70h
0x14002f426  mov     rax, [r8+0B8h]
0x14002f42d  mov     rdi, r8
0x14002f430  mov     rbx, [rcx+18h]
0x14002f434  mov     r14d, edx
0x14002f437  mov     rsi, rcx
0x14002f43a  mov     [rsp+0A8h+var_48], rax
0x14002f43f  mov     ebp, [rax+8]
0x14002f442  test    byte ptr cs:xmmword_140038420+3, 8
0x14002f449  lea     r15, [rbx+0D0h]
0x14002f450  mov     [rsp+0A8h+arg_0], r15
0x14002f458  lea     r12, [rcx+118h]
0x14002f45f  lea     r13, [rbx+0D4h]
0x14002f466  jz      short loc_14002F4BB
0x14002f468  mov     [r11-50h], edx
0x14002f46c  lea     rax, aOld; "Old"
0x14002f473  test    r9b, r9b
0x14002f476  lea     rcx, aNew; "New"
0x14002f47d  mov     r9, rsi
0x14002f480  cmovz   rcx, rax
0x14002f484  mov     eax, [r12]
0x14002f488  mov     [rsp+0A8h+var_58], eax
0x14002f48c  mov     eax, [r15]
0x14002f48f  mov     [rsp+0A8h+var_60], eax
0x14002f493  mov     eax, [r13+0]
0x14002f497  mov     dword ptr [rsp+0A8h+var_68], eax
0x14002f49b  mov     dword ptr [rsp+0A8h+var_70], ebp
0x14002f49f  mov     [r11-78h], r8
0x14002f4a3  mov     [r11-80h], rcx
0x14002f4a7  mov     qword ptr [rsp+0A8h+DestinationOffset], rbx
0x14002f4ac  call    WPP_SF_qqsqddddd
0x14002f4b1  mov     r9b, byte ptr [rsp+0A8h+arg_18]
0x14002f4b9  jmp     short loc_14002F4C3
0x14002f4bb  mov     [rsp+0A8h+arg_0], r15
0x14002f4c3  test    r9b, r9b
0x14002f4c6  jz      loc_14002F6E2
0x14002f4cc  mov     rcx, rdi
0x14002f4cf  call    NbtValidateReceiveRequest
0x14002f4d4  mov     eax, [r15]
0x14002f4d7  cmp     [r13+0], eax
0x14002f4db  jnz     short loc_14002F4F1
0x14002f4dd  xor     r15d, r15d
0x14002f4e0  mov     dword ptr [rdi+30h], 0
0x14002f4e7  xor     eax, eax
0x14002f4e9  xor     r8d, r8d
0x14002f4ec  jmp     loc_14002F662
0x14002f4f1  mov     rax, [rsp+0A8h+var_48]
0x14002f4f6  cmp     dword ptr [rax+8], 0
0x14002f4fa  jnz     short loc_14002F510
0x14002f4fc  mov     r8d, 80000005h
0x14002f502  xor     r15d, r15d
0x14002f505  mov     [rdi+30h], r8d
0x14002f509  xor     eax, eax
0x14002f50b  jmp     loc_14002F662
0x14002f510  mov     dword ptr [rbx+0D8h], 0
0x14002f51a  mov     [rbx+0DCh], ebp
0x14002f520  mov     eax, [r12]
0x14002f524  lea     r12, [rdi+8]
0x14002f528  test    eax, eax
0x14002f52a  jz      loc_14002F6D0
0x14002f530  mov     r9, [r12]; DestinationMdlChain
0x14002f534  cmp     ebp, r14d
0x14002f537  mov     rcx, [rsi+0E8h]; SourceBuffer
0x14002f53e  mov     r8d, r14d
0x14002f541  cmovb   r8d, ebp
0x14002f545  mov     [rsp+0A8h+arg_18], 0
0x14002f550  cmp     r8d, eax
0x14002f553  cmovnb  r8d, eax; SourceBytesToCopy
0x14002f557  lea     rax, [rsp+0A8h+arg_18]
0x14002f55f  mov     [rsp+0A8h+BytesCopied], rax; BytesCopied
0x14002f564  xor     edx, edx; SourceOffset
0x14002f566  mov     [rsp+0A8h+DestinationOffset], 0; DestinationOffset
0x14002f56e  call    cs:__imp_TdiCopyBufferToMdl
0x14002f575  nop     dword ptr [rax+rax+00h]
0x14002f57a  mov     edx, [rsp+0A8h+arg_18]
0x14002f581  mov     rcx, rsi
0x14002f584  add     [r13+0], edx
0x14002f588  sub     r14d, edx
0x14002f58b  add     [rbx+0D8h], edx
0x14002f591  mov     r15d, eax
0x14002f594  call    NbtCopyToStartOfIndicate
0x14002f599  mov     rax, [rsp+0A8h+arg_0]
0x14002f5a1  mov     r9d, [rbx+0D8h]
0x14002f5a8  mov     r13d, [r13+0]
0x14002f5ac  mov     [rsp+0A8h+arg_10], r9d
0x14002f5b4  mov     edx, [rax]
0x14002f5b6  mov     rax, [rsp+0A8h+var_48]
0x14002f5bb  mov     dword ptr [rsp+0A8h+arg_0], edx
0x14002f5c2  mov     r10d, [rax+8]
0x14002f5c6  mov     dword ptr [rsp+0A8h+var_48], r10d
0x14002f5cb  test    byte ptr cs:xmmword_140038420+3, 8
0x14002f5d2  jz      short loc_14002F633
0x14002f5d4  mov     [rsp+0A8h+var_60], r15d
0x14002f5d9  lea     r8, aFalse; "FALSE"
0x14002f5e0  cmp     r9d, r10d
0x14002f5e3  lea     rcx, aTrue; "TRUE"
0x14002f5ea  mov     rax, rcx
0x14002f5ed  mov     r9, rsi
0x14002f5f0  cmovnz  rax, r8
0x14002f5f4  cmp     r13d, edx
0x14002f5f7  mov     [rsp+0A8h+var_68], rax
0x14002f5fc  mov     eax, [rsp+0A8h+arg_18]
0x14002f603  cmovnz  rcx, r8
0x14002f607  mov     [rsp+0A8h+var_70], rcx
0x14002f60c  mov     dword ptr [rsp+0A8h+var_78], eax
0x14002f610  mov     [rsp+0A8h+BytesCopied], rdi
0x14002f615  mov     qword ptr [rsp+0A8h+DestinationOffset], rbx
0x14002f61a  call    WPP_SF_qqqdssd
0x14002f61f  mov     edx, dword ptr [rsp+0A8h+arg_0]
0x14002f626  mov     r9d, [rsp+0A8h+arg_10]
0x14002f62e  mov     r10d, dword ptr [rsp+0A8h+var_48]
0x14002f633  mov     r8d, 80000005h
0x14002f639  cmp     r15d, r8d
0x14002f63c  jz      loc_14002F505
0x14002f642  cmp     r13d, edx
0x14002f645  jnz     short loc_14002F653
0x14002f647  mov     dword ptr [rdi+30h], 0
0x14002f64e  xor     r8d, r8d
0x14002f651  jmp     short loc_14002F65C
0x14002f653  cmp     r9d, r10d
0x14002f656  jnz     short loc_14002F6D0
0x14002f658  mov     [rdi+30h], r8d
0x14002f65c  mov     eax, [rbx+0D8h]
0x14002f662  mov     [rdi+38h], rax
0x14002f666  test    byte ptr cs:xmmword_140038420+3, 8
0x14002f66d  jz      short loc_14002F697
0x14002f66f  mov     dword ptr [rsp+0A8h+var_78], r8d
0x14002f674  mov     edx, 1Eh
0x14002f679  mov     [rsp+0A8h+BytesCopied], rdi
0x14002f67e  lea     r8, WPP_e821b053d0733e5b06ead08bfa3e1f1d_Traceguids
0x14002f685  mov     ecx, 41Bh
0x14002f68a  mov     qword ptr [rsp+0A8h+DestinationOffset], rbx
0x14002f68f  mov     r9, rsi
0x14002f692  call    WPP_SF_qqqd
0x14002f697  lea     rcx, [rsi+68h]; SpinLock
0x14002f69b  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14002f6a2  nop     dword ptr [rax+rax+00h]
0x14002f6a7  xor     edx, edx; PriorityBoost
0x14002f6a9  mov     rcx, rdi; Irp
0x14002f6ac  call    cs:__imp_IofCompleteRequest
0x14002f6b3  nop     dword ptr [rax+rax+00h]
0x14002f6b8  lea     rcx, [rsi+68h]; SpinLock
0x14002f6bc  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14002f6c3  nop     dword ptr [rax+rax+00h]
0x14002f6c8  mov     eax, r15d
0x14002f6cb  jmp     loc_14002F860
0x14002f6d0  mov     [rbx+0C0h], rdi
0x14002f6d7  mov     rax, [r12]
0x14002f6db  mov     [rbx+0C8h], rax
0x14002f6e2  mov     edx, [rbx+0D8h]
0x14002f6e8  test    edx, edx
0x14002f6ea  jz      loc_14002F7C9
0x14002f6f0  mov     rax, [rbx+0C8h]
0x14002f6f7  xor     ecx, ecx
0x14002f6f9  xor     r8d, r8d
0x14002f6fc  xor     r13d, r13d
0x14002f6ff  test    rax, rax
0x14002f702  jz      short loc_14002F717
0x14002f704  mov     r8d, edx
0x14002f707  mov     r13, rax
0x14002f70a  sub     r8d, ecx
0x14002f70d  add     ecx, [rax+28h]
0x14002f710  mov     rax, [rax]
0x14002f713  cmp     ecx, edx
0x14002f715  jbe     short loc_14002F6FF
0x14002f717  cmp     ecx, edx
0x14002f719  jnb     short loc_14002F720
0x14002f71b  xor     r15d, r15d
0x14002f71e  jmp     short loc_14002F72E
0x14002f720  mov     r15d, [r13+2Ch]
0x14002f724  add     r15, [r13+20h]
0x14002f728  mov     eax, r8d
0x14002f72b  add     r15, rax
0x14002f72e  mov     rax, [rbx+0E0h]
0x14002f735  mov     qword ptr [rax], 0
0x14002f73c  mov     rcx, [rbx+0E0h]
0x14002f743  test    byte ptr [rcx+0Ah], 20h
0x14002f747  jz      short loc_14002F75C
0x14002f749  mov     rdx, rcx; MemoryDescriptorList
0x14002f74c  mov     rcx, [rcx+18h]; BaseAddress
0x14002f750  call    cs:__imp_MmUnmapLockedPages
0x14002f757  nop     dword ptr [rax+rax+00h]
0x14002f75c  mov     rdx, [rbx+0E0h]; TargetMdl
0x14002f763  xor     r9d, r9d; Length
0x14002f766  mov     r8, r15; VirtualAddress
0x14002f769  mov     rcx, r13; SourceMdl
0x14002f76c  call    cs:__imp_IoBuildPartialMdl
0x14002f773  nop     dword ptr [rax+rax+00h]
0x14002f778  test    byte ptr cs:xmmword_140038420+3, 8
0x14002f77f  jz      short loc_14002F7B0
0x14002f781  mov     rax, [rbx+0E0h]
0x14002f788  lea     r8, WPP_e821b053d0733e5b06ead08bfa3e1f1d_Traceguids
0x14002f78f  mov     [rsp+0A8h+var_78], rdi
0x14002f794  mov     edx, 1Ch
0x14002f799  mov     [rsp+0A8h+BytesCopied], rax
0x14002f79e  mov     ecx, 41Bh
0x14002f7a3  mov     r9, rsi
0x14002f7a6  mov     qword ptr [rsp+0A8h+DestinationOffset], rbx
0x14002f7ab  call    WPP_SF_qqqq
0x14002f7b0  mov     rax, [r13+0]
0x14002f7b4  mov     rcx, [rbx+0E0h]
0x14002f7bb  mov     [rcx], rax
0x14002f7be  mov     rax, [rbx+0E0h]
0x14002f7c5  mov     [rdi+8], rax
0x14002f7c9  sub     ebp, [rbx+0D8h]
0x14002f7cf  test    byte ptr cs:xmmword_140038420+3, 8
0x14002f7d6  jz      short loc_14002F805
0x14002f7d8  cmp     r14d, ebp
0x14002f7db  mov     eax, ebp
0x14002f7dd  mov     edx, 1Dh
0x14002f7e2  mov     r9, rsi
0x14002f7e5  cmovb   eax, r14d
0x14002f7e9  mov     dword ptr [rsp+0A8h+var_68], eax
0x14002f7ed  mov     dword ptr [rsp+0A8h+var_70], ebp
0x14002f7f1  mov     dword ptr [rsp+0A8h+var_78], r14d
0x14002f7f6  mov     [rsp+0A8h+BytesCopied], rdi
0x14002f7fb  mov     qword ptr [rsp+0A8h+DestinationOffset], rbx
0x14002f800  call    WPP_SF_qqqddd
0x14002f805  cmp     r14d, ebp
0x14002f808  jb      short loc_14002F80D
0x14002f80a  mov     r14d, ebp
0x14002f80d  mov     rax, [rdi+0B8h]
0x14002f814  lea     rcx, NbtClientIrpCompletion
0x14002f81b  mov     [rax-10h], rcx
0x14002f81f  mov     [rax-8], rsi
0x14002f823  mov     byte ptr [rax-45h], 0E0h
0x14002f827  mov     rbx, [rdi+0B8h]
0x14002f82e  mov     word ptr [rbx-48h], 80Fh
0x14002f834  mov     rcx, [rsi+30h]; FileObject
0x14002f838  call    cs:__imp_IoGetRelatedDeviceObject
0x14002f83f  nop     dword ptr [rax+rax+00h]
0x14002f844  mov     [rbx-20h], rax
0x14002f848  mov     rax, [rsi+30h]
0x14002f84c  mov     [rbx-18h], rax
0x14002f850  mov     eax, 0C0000016h
0x14002f855  mov     dword ptr [rbx-3Ch], 20h ; ' '
0x14002f85c  mov     [rbx-40h], r14d
0x14002f860  mov     rbx, [rsp+0A8h+arg_8]
0x14002f868  add     rsp, 70h
0x14002f86c  pop     r15
0x14002f86e  pop     r14
0x14002f870  pop     r13
0x14002f872  pop     r12
0x14002f874  pop     rdi
0x14002f875  pop     rsi
0x14002f876  pop     rbp
0x14002f877  retn
```
