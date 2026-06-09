# SecAuditFileAccessBlock

- ea: `0x140026a80`
- end: `0x140026d08`
- name: `SecAuditFileAccessBlock`
- size: `648`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, int, __int64)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x14003f710`
- `0x14003fae4`
- `0x14003fd54`

## callees

- `0x140005f60`
- `0x1400065e4`
- `0x140006754`
- `0x140006b6c`
- `0x140006d3c`
- `0x140009b80`
- `0x1400102ff`
- `0x140010347`
- `0x1400103e3`
- `0x140011650`
- `0x140025f00`
- `0x140026a80`
- `0x140029598`
- `0x140029658`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140026cb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026cb1`
- `ntoskrnl!IoGetCurrentProcess` at `0x140026b00`
- `ntoskrnl!IoGetCurrentProcess` at `0x140026b00`

## pseudocode

```c
void __fastcall SecAuditFileAccessBlock(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2,
        unsigned __int8 a3,
        char a4,
        int a5,
        const EVENT_DESCRIPTOR *a6)
{
  struct _KTHREAD *Thread; // rdi
  int v7; // r12d
  int v11; // r15d
  PEPROCESS CurrentProcess; // rax
  UNICODE_STRING *p_Name; // rcx
  int Next; // r8d
  __int64 v15; // r10
  struct _SLIST_ENTRY *v16; // rbx
  __int64 v17; // r9
  __int64 v18; // rcx
  PVOID P; // [rsp+60h] [rbp-59h] BYREF
  PSLIST_ENTRY ListEntry; // [rsp+68h] [rbp-51h] BYREF
  PFLT_CONTEXT Context; // [rsp+70h] [rbp-49h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+78h] [rbp-41h]
  PVOID v23; // [rsp+80h] [rbp-39h] BYREF
  PVOID v24; // [rsp+88h] [rbp-31h] BYREF
  PVOID v25; // [rsp+90h] [rbp-29h]
  __int64 v26; // [rsp+98h] [rbp-21h]
  __int64 v27; // [rsp+A0h] [rbp-19h]
  __int128 v28; // [rsp+A8h] [rbp-11h] BYREF
  _BYTE v29[8]; // [rsp+B8h] [rbp-1h] BYREF

  Thread = CallbackData->Thread;
  v7 = a3;
  ListEntry = 0;
  Context = 0;
  FileNameInformation = 0;
  v11 = 0;
  P = 0;
  v23 = 0;
  v29[0] = 0;
  v26 = 0;
  v27 = 0;
  v24 = 0;
  v25 = 0;
  v28 = 0;
  if ( !Thread )
    Thread = KeGetCurrentThread();
  CurrentProcess = IoGetCurrentProcess();
  if ( (int)SecGetProcessContextByObject(CurrentProcess, &ListEntry) >= 0
    && FltGetInstanceContext_0(*(PFLT_INSTANCE *)(a2 + 24), &Context) >= 0 )
  {
    if ( a4 )
    {
      if ( (int)SecQueryFileName(CallbackData) < 0 )
        goto LABEL_15;
      p_Name = &FileNameInformation->Name;
    }
    else
    {
      if ( (int)SecGetFileNetworkPhysicalNameInformation(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32)) < 0 )
        goto LABEL_15;
      LOWORD(v28) = *(_WORD *)v25;
      WORD1(v28) = *(_WORD *)v25;
      *((_QWORD *)&v28 + 1) = (char *)v25 + 4;
      p_Name = (UNICODE_STRING *)&v28;
    }
    if ( (int)SecUnicodeStringToString(p_Name, &P) >= 0
      && (int)SecGetEffectiveTokenUser(Thread, (__int64)ListEntry, &v23, v29, 0) >= 0 )
    {
      if ( a4 )
      {
        SecPopulateFileShareContext(*(PFLT_FILTER *)(a2 + 8));
        SecUnicodeStringToString(v26, &v24);
        v11 = 128;
      }
      Next = (int)ListEntry[2].Next;
      v15 = *(_QWORD *)v23;
      v16 = ListEntry[3].Next;
      v17 = *((_QWORD *)&ListEntry[2].Next + 1);
      v18 = _InterlockedIncrement64((volatile signed __int64 *)SecData + 42);
      EventWriteFileAccessBlock(v18, a6, Next, v17, v16, P, v7, v15, v24, v11, v27, a5);
    }
  }
LABEL_15:
  if ( Context )
    FltReleaseContext_0(Context);
  if ( FileNameInformation )
    FltReleaseFileNameInformation_0(FileNameInformation);
  if ( P )
    SecFreePool(P, 0x74736353u);
  if ( ListEntry )
    SecReleaseProcessContext(ListEntry);
  if ( v23 && v29[0] )
    ExFreePoolWithTag(v23, 0);
  if ( v24 )
    SecFreePool(v24, 0x74736353u);
  if ( v25 )
    SecFreePool(v25, 0x694E6353u);
}

```

## disassembly

```asm
0x140026a80  mov     [rsp-8+arg_10], rbx
0x140026a85  push    rbp
0x140026a86  push    rsi
0x140026a87  push    rdi
0x140026a88  push    r12
0x140026a8a  push    r13
0x140026a8c  push    r14
0x140026a8e  push    r15
0x140026a90  lea     rbp, [rsp-17h]
0x140026a95  sub     rsp, 0D0h
0x140026a9c  mov     rax, cs:__security_cookie
0x140026aa3  xor     rax, rsp
0x140026aa6  mov     [rbp+47h+var_40], rax
0x140026aaa  mov     rdi, [rcx+8]
0x140026aae  xor     eax, eax
0x140026ab0  mov     r13, [rbp+47h+arg_28]
0x140026ab4  xorps   xmm0, xmm0
0x140026ab7  movzx   r12d, r8b
0x140026abb  mov     r14b, r9b
0x140026abe  mov     [rbp+47h+ListEntry], rax
0x140026ac2  mov     rbx, rdx
0x140026ac5  mov     [rbp+47h+Context], rax
0x140026ac9  mov     rsi, rcx
0x140026acc  mov     [rbp+47h+FileNameInformation], rax
0x140026ad0  mov     r15d, eax
0x140026ad3  mov     [rbp+47h+P], rax
0x140026ad7  mov     [rbp+47h+var_80], rax
0x140026adb  mov     [rbp+47h+var_48], al
0x140026ade  mov     [rbp+47h+var_68], rax
0x140026ae2  mov     [rbp+47h+var_60], rax
0x140026ae6  mov     [rbp+47h+var_78], rax
0x140026aea  mov     [rbp+47h+var_70], rax
0x140026aee  movups  [rbp+47h+var_58], xmm0
0x140026af2  test    rdi, rdi
0x140026af5  jnz     short loc_140026B00
0x140026af7  mov     rdi, gs:188h
0x140026b00  call    cs:__imp_IoGetCurrentProcess
0x140026b07  nop     dword ptr [rax+rax+00h]
0x140026b0c  mov     rcx, rax
0x140026b0f  lea     rdx, [rbp+47h+ListEntry]
0x140026b13  call    SecGetProcessContextByObject
0x140026b18  test    eax, eax
0x140026b1a  js      loc_140026C61
0x140026b20  mov     rcx, [rbx+18h]; Instance
0x140026b24  lea     rdx, [rbp+47h+Context]; Context
0x140026b28  call    FltGetInstanceContext_0
0x140026b2d  test    eax, eax
0x140026b2f  js      loc_140026C61
0x140026b35  test    r14b, r14b
0x140026b38  jnz     short loc_140026B73
0x140026b3a  mov     rdx, [rbx+20h]; FileObject
0x140026b3e  lea     r8, [rbp+47h+var_70]
0x140026b42  mov     rcx, [rbx+18h]; Instance
0x140026b46  call    SecGetFileNetworkPhysicalNameInformation
0x140026b4b  test    eax, eax
0x140026b4d  js      loc_140026C61
0x140026b53  mov     rcx, [rbp+47h+var_70]
0x140026b57  movzx   eax, word ptr [rcx]
0x140026b5a  mov     word ptr [rbp+47h+var_58], ax
0x140026b5e  movzx   eax, word ptr [rcx]
0x140026b61  mov     word ptr [rbp+47h+var_58+2], ax
0x140026b65  lea     rax, [rcx+4]
0x140026b69  mov     qword ptr [rbp+47h+var_58+8], rax
0x140026b6d  lea     rcx, [rbp+47h+var_58]
0x140026b71  jmp     short loc_140026B96
0x140026b73  mov     rdx, [rbp+47h+Context]
0x140026b77  lea     r8, [rbp+47h+FileNameInformation]
0x140026b7b  mov     rcx, rsi; CallbackData
0x140026b7e  mov     edx, [rdx+2Ch]
0x140026b81  call    SecQueryFileName
0x140026b86  test    eax, eax
0x140026b88  js      loc_140026C61
0x140026b8e  mov     rcx, [rbp+47h+FileNameInformation]
0x140026b92  add     rcx, 8
0x140026b96  lea     rdx, [rbp+47h+P]
0x140026b9a  call    SecUnicodeStringToString
0x140026b9f  test    eax, eax
0x140026ba1  js      loc_140026C61
0x140026ba7  mov     rdx, [rbp+47h+ListEntry]
0x140026bab  lea     r9, [rbp+47h+var_48]
0x140026baf  lea     r8, [rbp+47h+var_80]
0x140026bb3  mov     [rsp+100h+var_E0], r15; __int64
0x140026bb8  mov     rcx, rdi; Thread
0x140026bbb  call    SecGetEffectiveTokenUser
0x140026bc0  test    eax, eax
0x140026bc2  js      loc_140026C61
0x140026bc8  test    r14b, r14b
0x140026bcb  jz      short loc_140026BF4
0x140026bcd  mov     rcx, [rbx+8]; Filter
0x140026bd1  lea     r9, [rbp+47h+var_60]
0x140026bd5  lea     r8, [rbp+47h+var_68]
0x140026bd9  mov     rdx, rsi
0x140026bdc  call    SecPopulateFileShareContext
0x140026be1  mov     rcx, [rbp+47h+var_68]
0x140026be5  lea     rdx, [rbp+47h+var_78]
0x140026be9  call    SecUnicodeStringToString
0x140026bee  mov     r15d, 80h
0x140026bf4  mov     rcx, [rbp+47h+ListEntry]
0x140026bf8  mov     rax, [rbp+47h+var_80]
0x140026bfc  mov     r8d, [rcx+20h]
0x140026c00  mov     r10, [rax]
0x140026c03  mov     rbx, [rcx+30h]
0x140026c07  mov     r9, [rcx+28h]
0x140026c0b  mov     ecx, 1
0x140026c10  mov     rax, cs:SecData
0x140026c17  lock xadd [rax+150h], rcx
0x140026c20  mov     eax, [rbp+47h+arg_20]
0x140026c23  inc     rcx
0x140026c26  mov     [rsp+100h+var_A8], eax
0x140026c2a  mov     rdx, r13
0x140026c2d  mov     rax, [rbp+47h+var_60]
0x140026c31  mov     [rsp+100h+var_B0], rax
0x140026c36  mov     rax, [rbp+47h+var_78]
0x140026c3a  mov     [rsp+100h+var_B8], r15d
0x140026c3f  mov     [rsp+100h+var_C0], rax
0x140026c44  mov     rax, [rbp+47h+P]
0x140026c48  mov     [rsp+100h+var_C8], r10
0x140026c4d  mov     [rsp+100h+var_D0], r12d
0x140026c52  mov     [rsp+100h+var_D8], rax
0x140026c57  mov     [rsp+100h+var_E0], rbx
0x140026c5c  call    EventWriteFileAccessBlock
0x140026c61  mov     rcx, [rbp+47h+Context]; Context
0x140026c65  test    rcx, rcx
0x140026c68  jz      short loc_140026C6F
0x140026c6a  call    FltReleaseContext_0
0x140026c6f  mov     rcx, [rbp+47h+FileNameInformation]; FileNameInformation
0x140026c73  test    rcx, rcx
0x140026c76  jz      short loc_140026C7D
0x140026c78  call    FltReleaseFileNameInformation_0
0x140026c7d  mov     rcx, [rbp+47h+P]; P
0x140026c81  mov     ebx, 74736353h
0x140026c86  test    rcx, rcx
0x140026c89  jz      short loc_140026C92
0x140026c8b  mov     edx, ebx; Tag
0x140026c8d  call    SecFreePool
0x140026c92  mov     rcx, [rbp+47h+ListEntry]; ListEntry
0x140026c96  test    rcx, rcx
0x140026c99  jz      short loc_140026CA0
0x140026c9b  call    SecReleaseProcessContext
0x140026ca0  mov     rcx, [rbp+47h+var_80]; P
0x140026ca4  test    rcx, rcx
0x140026ca7  jz      short loc_140026CBD
0x140026ca9  cmp     [rbp+47h+var_48], 0
0x140026cad  jz      short loc_140026CBD
0x140026caf  xor     edx, edx; Tag
0x140026cb1  call    cs:__imp_ExFreePoolWithTag
0x140026cb8  nop     dword ptr [rax+rax+00h]
0x140026cbd  mov     rcx, [rbp+47h+var_78]; P
0x140026cc1  test    rcx, rcx
0x140026cc4  jz      short loc_140026CCD
0x140026cc6  mov     edx, ebx; Tag
0x140026cc8  call    SecFreePool
0x140026ccd  mov     rcx, [rbp+47h+var_70]; P
0x140026cd1  test    rcx, rcx
0x140026cd4  jz      short loc_140026CE0
0x140026cd6  mov     edx, 694E6353h; Tag
0x140026cdb  call    SecFreePool
0x140026ce0  mov     rcx, [rbp+47h+var_40]
0x140026ce4  xor     rcx, rsp; StackCookie
0x140026ce7  call    __security_check_cookie
0x140026cec  mov     rbx, [rsp+100h+arg_10]
0x140026cf4  add     rsp, 0D0h
0x140026cfb  pop     r15
0x140026cfd  pop     r14
0x140026cff  pop     r13
0x140026d01  pop     r12
0x140026d03  pop     rdi
0x140026d04  pop     rsi
0x140026d05  pop     rbp
0x140026d06  retn
```
