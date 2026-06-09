# EfspGetRequestorProcessName

- ea: `0x140055c54`
- end: `0x140055e06`
- name: `EfspGetRequestorProcessName`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400510ac`

## callees

- `0x14000c380`
- `0x14000c680`
- `0x140055c54`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcess` at `0x140055c75`
- `ntoskrnl!IoGetRequestorProcess` at `0x140055c75`
- `ntoskrnl!ZwClose` at `0x140055dea`
- `ntoskrnl!ZwClose` at `0x140055dea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055dce`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055dce`
- `ntoskrnl!ExAllocatePool2` at `0x140055d19`
- `ntoskrnl!ExAllocatePool2` at `0x140055d7a`
- `ntoskrnl!ExAllocatePool2` at `0x140055d19`
- `ntoskrnl!ExAllocatePool2` at `0x140055d7a`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140055ce2`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140055d50`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140055ce2`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140055d50`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140055cb5`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140055cb5`

## pseudocode

```c
__int64 __fastcall EfspGetRequestorProcessName(IRP *a1, _QWORD *a2)
{
  PEPROCESS RequestorProcess; // rax
  NTSTATUS InformationProcess; // ebx
  NTSTATUS v5; // eax
  const void **Pool2; // rax
  const void **v7; // rdi
  unsigned int v8; // eax
  __int64 v9; // rdx
  void *v10; // rax
  void *v11; // rbx
  ULONG ReturnLength; // [rsp+70h] [rbp+30h] BYREF
  HANDLE ProcessHandle; // [rsp+78h] [rbp+38h] BYREF

  ReturnLength = 0;
  ProcessHandle = 0;
  RequestorProcess = IoGetRequestorProcess(a1);
  if ( !RequestorProcess )
    goto LABEL_2;
  InformationProcess = ObOpenObjectByPointer(RequestorProcess, 0x200u, 0, 0, 0, 0, &ProcessHandle);
  if ( InformationProcess >= 0 )
  {
    v5 = ZwQueryInformationProcess(ProcessHandle, ProcessImageFileName, 0, 0, &ReturnLength);
    InformationProcess = v5;
    if ( v5 == -1073741820 )
    {
      if ( ReturnLength < 0x10 )
      {
        InformationProcess = -1073741595;
      }
      else
      {
        Pool2 = (const void **)ExAllocatePool2(256, ReturnLength, 1416848965);
        v7 = Pool2;
        if ( Pool2 )
        {
          InformationProcess = ZwQueryInformationProcess(ProcessHandle, ProcessImageFileName, Pool2, ReturnLength, 0);
          if ( InformationProcess >= 0 )
          {
            v8 = *(unsigned __int16 *)v7;
            v9 = v8 + 2;
            if ( (unsigned int)v9 < v8 )
            {
              ReturnLength = -1;
              InformationProcess = -1073741675;
            }
            else
            {
              ReturnLength = v8 + 2;
              v10 = (void *)ExAllocatePool2(256, v9, 1416848965);
              v11 = v10;
              if ( v10 )
              {
                memset(v10, 0, ReturnLength);
                memmove(v11, v7[1], *(unsigned __int16 *)v7);
                *a2 = v11;
                InformationProcess = 0;
              }
              else
              {
                InformationProcess = -1073741670;
              }
            }
          }
          ExFreePoolWithTag(v7, 0x54736645u);
        }
        else
        {
          InformationProcess = -1073741670;
        }
      }
    }
    else if ( v5 >= 0 )
    {
LABEL_2:
      InformationProcess = -1073741823;
    }
  }
  if ( ProcessHandle )
    ZwClose(ProcessHandle);
  return (unsigned int)InformationProcess;
}

```

## disassembly

```asm
0x140055c54  mov     [rsp-18h+arg_0], rbx
0x140055c59  push    rbp
0x140055c5a  push    rsi
0x140055c5b  push    rdi
0x140055c5c  mov     rbp, rsp
0x140055c5f  sub     rsp, 40h
0x140055c63  mov     rsi, rdx
0x140055c66  mov     [rbp+ReturnLength], 0
0x140055c6d  mov     [rbp+ProcessHandle], 0
0x140055c75  call    cs:__imp_IoGetRequestorProcess
0x140055c7c  nop     dword ptr [rax+rax+00h]
0x140055c81  test    rax, rax
0x140055c84  jnz     short loc_140055C90
0x140055c86  mov     ebx, 0C0000001h
0x140055c8b  jmp     loc_140055DE1
0x140055c90  lea     rcx, [rbp+ProcessHandle]
0x140055c94  xor     r9d, r9d; DesiredAccess
0x140055c97  mov     [rsp+40h+Handle], rcx; Handle
0x140055c9c  xor     r8d, r8d; PassedAccessState
0x140055c9f  mov     [rsp+40h+AccessMode], 0; AccessMode
0x140055ca4  mov     rcx, rax; Object
0x140055ca7  mov     edx, 200h; HandleAttributes
0x140055cac  mov     [rsp+40h+ObjectType], 0; ObjectType
0x140055cb5  call    cs:__imp_ObOpenObjectByPointer
0x140055cbc  nop     dword ptr [rax+rax+00h]
0x140055cc1  mov     ebx, eax
0x140055cc3  test    eax, eax
0x140055cc5  js      loc_140055DE1
0x140055ccb  mov     rcx, [rbp+ProcessHandle]; ProcessHandle
0x140055ccf  lea     rax, [rbp+ReturnLength]
0x140055cd3  xor     r9d, r9d; ProcessInformationLength
0x140055cd6  mov     [rsp+40h+ObjectType], rax; ReturnLength
0x140055cdb  xor     r8d, r8d; ProcessInformation
0x140055cde  lea     edx, [r9+1Bh]; ProcessInformationClass
0x140055ce2  call    cs:__imp_ZwQueryInformationProcess
0x140055ce9  nop     dword ptr [rax+rax+00h]
0x140055cee  mov     ebx, eax
0x140055cf0  cmp     eax, 0C0000004h
0x140055cf5  jz      short loc_140055D01
0x140055cf7  test    eax, eax
0x140055cf9  js      loc_140055DE1
0x140055cff  jmp     short loc_140055C86
0x140055d01  cmp     [rbp+ReturnLength], 10h
0x140055d05  jb      loc_140055DDC
0x140055d0b  mov     edx, [rbp+ReturnLength]
0x140055d0e  mov     ecx, 100h
0x140055d13  mov     r8d, 54736645h
0x140055d19  call    cs:__imp_ExAllocatePool2
0x140055d20  nop     dword ptr [rax+rax+00h]
0x140055d25  mov     rdi, rax
0x140055d28  test    rax, rax
0x140055d2b  jnz     short loc_140055D37
0x140055d2d  mov     ebx, 0C000009Ah
0x140055d32  jmp     loc_140055DE1
0x140055d37  mov     r9d, [rbp+ReturnLength]; ProcessInformationLength
0x140055d3b  mov     r8, rdi; ProcessInformation
0x140055d3e  mov     rcx, [rbp+ProcessHandle]; ProcessHandle
0x140055d42  mov     edx, 1Bh; ProcessInformationClass
0x140055d47  mov     [rsp+40h+ObjectType], 0; ReturnLength
0x140055d50  call    cs:__imp_ZwQueryInformationProcess
0x140055d57  nop     dword ptr [rax+rax+00h]
0x140055d5c  mov     ebx, eax
0x140055d5e  test    eax, eax
0x140055d60  js      short loc_140055DC6
0x140055d62  movzx   eax, word ptr [rdi]
0x140055d65  lea     edx, [rax+2]
0x140055d68  cmp     edx, eax
0x140055d6a  jb      short loc_140055DBA
0x140055d6c  mov     ecx, 100h
0x140055d71  mov     [rbp+ReturnLength], edx
0x140055d74  mov     r8d, 54736645h
0x140055d7a  call    cs:__imp_ExAllocatePool2
0x140055d81  nop     dword ptr [rax+rax+00h]
0x140055d86  mov     rbx, rax
0x140055d89  test    rax, rax
0x140055d8c  jnz     short loc_140055D95
0x140055d8e  mov     ebx, 0C000009Ah
0x140055d93  jmp     short loc_140055DC6
0x140055d95  mov     r8d, [rbp+ReturnLength]; Size
0x140055d99  xor     edx, edx; Val
0x140055d9b  mov     rcx, rbx; void *
0x140055d9e  call    memset
0x140055da3  movzx   r8d, word ptr [rdi]; Size
0x140055da7  mov     rcx, rbx; void *
0x140055daa  mov     rdx, [rdi+8]; Src
0x140055dae  call    memmove
0x140055db3  mov     [rsi], rbx
0x140055db6  xor     ebx, ebx
0x140055db8  jmp     short loc_140055DC6
0x140055dba  mov     [rbp+ReturnLength], 0FFFFFFFFh
0x140055dc1  mov     ebx, 0C0000095h
0x140055dc6  mov     edx, 54736645h; Tag
0x140055dcb  mov     rcx, rdi; P
0x140055dce  call    cs:__imp_ExFreePoolWithTag
0x140055dd5  nop     dword ptr [rax+rax+00h]
0x140055dda  jmp     short loc_140055DE1
0x140055ddc  mov     ebx, 0C00000E5h
0x140055de1  mov     rcx, [rbp+ProcessHandle]; Handle
0x140055de5  test    rcx, rcx
0x140055de8  jz      short loc_140055DF6
0x140055dea  call    cs:__imp_ZwClose
0x140055df1  nop     dword ptr [rax+rax+00h]
0x140055df6  mov     eax, ebx
0x140055df8  mov     rbx, [rsp+40h+arg_0]
0x140055dfd  add     rsp, 40h
0x140055e01  pop     rdi
0x140055e02  pop     rsi
0x140055e03  pop     rbp
0x140055e04  retn
```
