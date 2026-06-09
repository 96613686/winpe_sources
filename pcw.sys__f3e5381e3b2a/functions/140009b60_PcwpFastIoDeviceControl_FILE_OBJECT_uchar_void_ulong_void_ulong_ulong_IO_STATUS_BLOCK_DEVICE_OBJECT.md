# PcwpFastIoDeviceControl(_FILE_OBJECT *,uchar,void *,ulong,void *,ulong,ulong,_IO_STATUS_BLOCK *,_DEVICE_OBJECT *)

- ea: `0x140009b60`
- end: `0x140009d2f`
- name: `?PcwpFastIoDeviceControl@@YAEPEAU_FILE_OBJECT@@EPEAXK1KKPEAU_IO_STATUS_BLOCK@@PEAU_DEVICE_OBJECT@@@Z`
- size: `463`
- prototype: `unsigned __int8 __fastcall(struct _FILE_OBJECT *, __int64, void *, unsigned int, void *Address, SIZE_T Length, unsigned int, struct _IO_STATUS_BLOCK *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400010c4`
- `0x140001450`
- `0x140009b60`
- `0x14000a280`
- `0x14000ad30`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140009c6c`
- `ntoskrnl!ProbeForRead` at `0x140009c6c`
- `ntoskrnl!ProbeForWrite` at `0x140009c54`
- `ntoskrnl!ProbeForWrite` at `0x140009c54`

## pseudocode

```c
unsigned __int8 __fastcall PcwpFastIoDeviceControl(
        struct _FILE_OBJECT *a1,
        __int64 a2,
        void *a3,
        unsigned int a4,
        void *Address,
        SIZE_T Length,
        unsigned int a7,
        struct _IO_STATUS_BLOCK *a8)
{
  SIZE_T v8; // rbx
  struct _IO_STATUS_BLOCK *v10; // rsi
  __int64 v11; // r9
  __int64 v12; // r8
  unsigned int v13; // edi
  int v14; // eax
  int v15; // eax
  _OWORD v17[3]; // [rsp+20h] [rbp-78h] BYREF
  __int64 v18; // [rsp+50h] [rbp-48h]

  v8 = a4;
  memset(v17, 0, sizeof(v17));
  v18 = 0;
  v10 = a8;
  a8->Information = 0;
  if ( (a7 | 0x3FFC) == 0x227FFF )
  {
    v13 = (a7 >> 2) & 0xFFF;
    if ( v13 < 0x10 )
    {
      if ( LODWORD(qword_140003150[2 * v13]) == a4
        && ((a7 = (a7 >> 2) & 0xFFF, v14 = HIDWORD(qword_140003150[2 * v13]), v14 == (_DWORD)Length) || v14 == -1) )
      {
        if ( Address )
          ProbeForWrite(Address, (unsigned int)Length, 1u);
        ProbeForRead(a3, v8, 1u);
        RtlCopyFromUser(v17, a3, v8);
        v15 = (*(&funcs_140009CA3 + 2 * v13))((union PCW_IOCTL_INPUT *)v17, Address, (unsigned int *)&Length);
        v12 = (unsigned int)v15;
        v10->Status = v15;
        v10->Information = (unsigned int)Length;
        if ( v15 >= 0 || (Microsoft_Windows_Diagnosis_PCWEnableBits & 0x10) == 0 )
          return 1;
      }
      else
      {
        v10->Status = -1073741306;
        if ( (Microsoft_Windows_Diagnosis_PCWEnableBits & 0x10) == 0 )
          return 1;
        v12 = 3221225990LL;
      }
    }
    else
    {
      v10->Status = -1073741808;
      if ( (Microsoft_Windows_Diagnosis_PCWEnableBits & 0x10) == 0 )
        return 1;
      v12 = 3221225488LL;
    }
    v11 = v13;
    goto LABEL_18;
  }
  v10->Status = -1073741808;
  if ( (Microsoft_Windows_Diagnosis_PCWEnableBits & 0x10) != 0 )
  {
    v11 = 0xFFFFFFFFLL;
    v12 = 3221225488LL;
LABEL_18:
    McTemplateU0qq_EtwWriteTransfer(a1, PcwIoctlFail, v12, v11);
  }
  return 1;
}

```

## disassembly

```asm
0x140009b60  push    rbx
0x140009b62  push    rsi
0x140009b63  push    rdi
0x140009b64  push    r12
0x140009b66  push    r13
0x140009b68  push    r14
0x140009b6a  sub     rsp, 68h
0x140009b6e  mov     ebx, r9d
0x140009b71  mov     r12, r8
0x140009b74  xorps   xmm0, xmm0
0x140009b77  xor     eax, eax
0x140009b79  movups  [rsp+98h+var_78], xmm0
0x140009b7e  movups  [rsp+98h+var_68], xmm0
0x140009b83  movups  [rsp+98h+var_58], xmm0
0x140009b88  mov     [rsp+98h+var_48], rax
0x140009b8d  mov     rsi, [rsp+98h+arg_38]
0x140009b95  mov     [rsi+8], rax
0x140009b99  mov     edi, [rsp+98h+arg_30]
0x140009ba0  mov     eax, edi
0x140009ba2  or      eax, 3FFCh
0x140009ba7  cmp     eax, 227FFFh
0x140009bac  jz      short loc_140009BD1
0x140009bae  mov     dword ptr [rsi], 0C0000010h
0x140009bb4  mov     eax, cs:Microsoft_Windows_Diagnosis_PCWEnableBits
0x140009bba  test    al, 10h
0x140009bbc  jz      loc_140009D1E
0x140009bc2  or      r9d, 0FFFFFFFFh
0x140009bc6  mov     r8d, 0C0000010h
0x140009bcc  jmp     loc_140009D12
0x140009bd1  shr     edi, 2
0x140009bd4  and     edi, 0FFFh
0x140009bda  cmp     edi, 10h
0x140009bdd  jb      short loc_140009BFE
0x140009bdf  mov     dword ptr [rsi], 0C0000010h
0x140009be5  mov     eax, cs:Microsoft_Windows_Diagnosis_PCWEnableBits
0x140009beb  test    al, 10h
0x140009bed  jz      loc_140009D1E
0x140009bf3  mov     r8d, 0C0000010h
0x140009bf9  jmp     loc_140009D0F
0x140009bfe  mov     r14d, edi
0x140009c01  add     r14, r14
0x140009c04  lea     r13, qword_140003150
0x140009c0b  cmp     [r13+r14*8+0], ebx
0x140009c10  jnz     loc_140009CF9
0x140009c16  mov     [rsp+98h+arg_30], edi
0x140009c1d  mov     eax, [r13+r14*8+4]
0x140009c22  cmp     eax, dword ptr [rsp+98h+Length]
0x140009c29  jz      short loc_140009C34
0x140009c2b  cmp     eax, 0FFFFFFFFh
0x140009c2e  jnz     loc_140009CF9
0x140009c34  cmp     [rsp+98h+Address], 0
0x140009c3d  jz      short loc_140009C60
0x140009c3f  mov     edx, dword ptr [rsp+98h+Length]; Length
0x140009c46  mov     r8d, 1; Alignment
0x140009c4c  mov     rcx, [rsp+98h+Address]; Address
0x140009c54  call    cs:__imp_ProbeForWrite
0x140009c5b  nop     dword ptr [rax+rax+00h]
0x140009c60  mov     r8d, 1; Alignment
0x140009c66  mov     rdx, rbx; Length
0x140009c69  mov     rcx, r12; Address
0x140009c6c  call    cs:__imp_ProbeForRead
0x140009c73  nop     dword ptr [rax+rax+00h]
0x140009c78  mov     r8, rbx; Size
0x140009c7b  mov     rdx, r12; Src
0x140009c7e  lea     rcx, [rsp+98h+var_78]; void *
0x140009c83  call    RtlCopyFromUser
0x140009c88  nop
0x140009c89  mov     rax, ds:(funcs_140009CA3 - 140003150h)[r13+r14*8]
0x140009c8e  lea     r8, [rsp+98h+Length]
0x140009c96  mov     rdx, [rsp+98h+Address]
0x140009c9e  lea     rcx, [rsp+98h+var_78]
0x140009ca3  call    _guard_dispatch_icall; PcwpIoctlCreateQuery(PCW_IOCTL_INPUT *,void *,ulong *) ...
0x140009ca8  mov     r8d, eax
0x140009cab  mov     [rsi], eax
0x140009cad  mov     eax, dword ptr [rsp+98h+Length]
0x140009cb4  mov     [rsi+8], rax
0x140009cb8  test    r8d, r8d
0x140009cbb  jns     short loc_140009D1E
0x140009cbd  mov     eax, cs:Microsoft_Windows_Diagnosis_PCWEnableBits
0x140009cc3  test    al, 10h
0x140009cc5  jz      short loc_140009D1E
0x140009cc7  jmp     short loc_140009D0F
0x140009cc9  mov     r8d, eax
0x140009ccc  mov     rax, [rsp+98h+arg_38]
0x140009cd4  mov     [rax], r8d
0x140009cd7  mov     eax, cs:Microsoft_Windows_Diagnosis_PCWEnableBits
0x140009cdd  test    al, 10h
0x140009cdf  jz      short loc_140009CF5
0x140009ce1  mov     r9d, [rsp+98h+arg_30]
0x140009ce9  lea     rdx, PcwIoctlFail
0x140009cf0  call    McTemplateU0qq_EtwWriteTransfer
0x140009cf5  mov     al, 1
0x140009cf7  jmp     short loc_140009D20
0x140009cf9  mov     dword ptr [rsi], 0C0000206h
0x140009cff  mov     eax, cs:Microsoft_Windows_Diagnosis_PCWEnableBits
0x140009d05  test    al, 10h
0x140009d07  jz      short loc_140009D1E
0x140009d09  mov     r8d, 0C0000206h
0x140009d0f  mov     r9d, edi
0x140009d12  lea     rdx, PcwIoctlFail
0x140009d19  call    McTemplateU0qq_EtwWriteTransfer
0x140009d1e  mov     al, 1
0x140009d20  add     rsp, 68h
0x140009d24  pop     r14
0x140009d26  pop     r13
0x140009d28  pop     r12
0x140009d2a  pop     rdi
0x140009d2b  pop     rsi
0x140009d2c  pop     rbx
0x140009d2d  retn
```
