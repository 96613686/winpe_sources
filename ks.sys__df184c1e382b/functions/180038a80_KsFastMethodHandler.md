# KsFastMethodHandler

- ea: `0x180038a80`
- end: `0x180038c25`
- name: `KsFastMethodHandler`
- size: `421`
- prototype: `BOOLEAN __stdcall(PFILE_OBJECT FileObject, PKSMETHOD Method, ULONG MethodLength, PVOID Data, ULONG DataLength, PIO_STATUS_BLOCK IoStatus, ULONG MethodSetsCount, const KSMETHOD_SET *MethodSet)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180019cb0`
- `0x180038a80`
- `0x180051600`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x180038aa6`
- `ntoskrnl!ExGetPreviousMode` at `0x180038aa6`
- `ntoskrnl!ProbeForRead` at `0x180038ac5`
- `ntoskrnl!ProbeForRead` at `0x180038b91`
- `ntoskrnl!ProbeForRead` at `0x180038ac5`
- `ntoskrnl!ProbeForRead` at `0x180038b91`
- `ntoskrnl!ProbeForWrite` at `0x180038bad`
- `ntoskrnl!ProbeForWrite` at `0x180038bad`

## pseudocode

```c
BOOLEAN __stdcall KsFastMethodHandler(
        PFILE_OBJECT FileObject,
        PKSMETHOD Method,
        ULONG MethodLength,
        PVOID Data,
        ULONG DataLength,
        PIO_STATUS_BLOCK IoStatus,
        ULONG MethodSetsCount,
        const KSMETHOD_SET *MethodSet)
{
  KPROCESSOR_MODE PreviousMode; // r15
  __int64 Id; // r8
  const KSFASTMETHOD_ITEM *FastIoTable; // rbx
  ULONG i; // eax
  __int64 MethodItem; // rax
  int v19; // edx
  __int64 v20; // rdi
  int v21; // eax
  ULONG v22; // r8d
  __int64 (__fastcall *MethodHandler)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax

  if ( MethodLength >= 0x18 )
  {
    PreviousMode = ExGetPreviousMode();
    if ( PreviousMode )
      ProbeForRead(Method, MethodLength, 4u);
    if ( (Method->Flags & 0xFFF00) == 0 )
    {
      while ( MethodSetsCount )
      {
        if ( Method->Alignment == *(_QWORD *)&MethodSet->Set->Data1
          && *(&Method->Alignment + 1) == *(_QWORD *)MethodSet->Set->Data4 )
        {
          Id = Method->Id;
          FastIoTable = MethodSet->FastIoTable;
          for ( i = MethodSet->FastIoCount; i; --i )
          {
            if ( (_DWORD)Id == FastIoTable->MethodId )
              goto LABEL_13;
            ++FastIoTable;
          }
          FastIoTable = 0;
LABEL_13:
          if ( FastIoTable )
          {
            MethodItem = FindMethodItem(MethodSet, 40, Id, 0xFFFFFFFFLL);
            v20 = MethodItem;
            if ( MethodItem )
            {
              if ( PreviousMode )
              {
                v21 = *(_DWORD *)(MethodItem + 32);
                v22 = v19 - 39;
                if ( ((unsigned __int8)v21 & (unsigned __int8)(v19 - 39)) != 0 )
                {
                  ProbeForRead(Data, DataLength, v22);
                }
                else if ( (v21 & 2) != 0 )
                {
                  ProbeForWrite(Data, DataLength, v22);
                }
              }
              IoStatus->Information = 0;
              MethodHandler = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))FastIoTable->MethodHandler;
              if ( MethodHandler )
              {
                if ( MethodLength >= *(_DWORD *)(v20 + 16) && DataLength >= *(_DWORD *)(v20 + 20) )
                  return MethodHandler(FileObject, Method, MethodLength, Data, DataLength, IoStatus);
              }
            }
          }
          return 0;
        }
        ++MethodSet;
        --MethodSetsCount;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180038a80  push    rbx
0x180038a82  push    rsi
0x180038a83  push    rdi
0x180038a84  push    r12
0x180038a86  push    r13
0x180038a88  push    r14
0x180038a8a  push    r15
0x180038a8c  sub     rsp, 40h
0x180038a90  mov     r12, r9
0x180038a93  mov     r14d, r8d
0x180038a96  mov     rsi, rdx
0x180038a99  mov     r13, rcx
0x180038a9c  cmp     r8d, 18h
0x180038aa0  jb      loc_180038C12
0x180038aa6  call    cs:__imp_ExGetPreviousMode
0x180038aad  nop     dword ptr [rax+rax+00h]
0x180038ab2  mov     r15b, al
0x180038ab5  test    al, al
0x180038ab7  jz      short loc_180038ADB
0x180038ab9  mov     edx, r14d; Length
0x180038abc  mov     r8d, 4; Alignment
0x180038ac2  mov     rcx, rsi; Address
0x180038ac5  call    cs:__imp_ProbeForRead
0x180038acc  nop     dword ptr [rax+rax+00h]
0x180038ad1  nop
0x180038ad2  jmp     short loc_180038ADB
0x180038ad4  xor     al, al
0x180038ad6  jmp     loc_180038C14
0x180038adb  mov     ecx, 14h
0x180038ae0  mov     r9, rsi
0x180038ae3  lea     r11d, [rcx-4]
0x180038ae7  mov     r10, rsi
0x180038aea  lea     eax, [rcx-0Ch]
0x180038aed  mov     r8, rsi
0x180038af0  mov     rdx, rsi
0x180038af3  mov     r8, [rsi+rax]
0x180038af7  mov     rbx, [rdx]
0x180038afa  test    dword ptr [rcx+rsi], 0FFF00h
0x180038b01  jnz     loc_180038C12
0x180038b07  mov     eax, [rsp+78h+MethodSetsCount]
0x180038b0e  or      r9d, 0FFFFFFFFh
0x180038b12  mov     rcx, [rsp+78h+MethodSet]
0x180038b1a  test    eax, eax
0x180038b1c  jz      loc_180038C12
0x180038b22  mov     rdx, [rcx]
0x180038b25  cmp     rbx, [rdx]
0x180038b28  jnz     loc_180038C06
0x180038b2e  cmp     r8, [rdx+8]
0x180038b32  jnz     loc_180038C06
0x180038b38  mov     r8d, [r11+r10]
0x180038b3c  mov     rbx, [rcx+20h]
0x180038b40  mov     eax, [rcx+18h]
0x180038b43  test    eax, eax
0x180038b45  jz      short loc_180038B55
0x180038b47  cmp     r8d, [rbx]
0x180038b4a  jz      short loc_180038B57
0x180038b4c  add     eax, r9d
0x180038b4f  add     rbx, 10h
0x180038b53  jmp     short loc_180038B43
0x180038b55  xor     ebx, ebx
0x180038b57  test    rbx, rbx
0x180038b5a  jz      loc_180038C12
0x180038b60  mov     edx, 28h ; '('
0x180038b65  call    FindMethodItem
0x180038b6a  mov     rdi, rax
0x180038b6d  test    rax, rax
0x180038b70  jz      loc_180038C12
0x180038b76  test    r15b, r15b
0x180038b79  jz      short loc_180038BBF
0x180038b7b  mov     eax, [rax+20h]
0x180038b7e  lea     r8d, [rdx-27h]; Alignment
0x180038b82  test    r8b, al
0x180038b85  jz      short loc_180038B9F
0x180038b87  mov     edx, [rsp+78h+DataLength]; Length
0x180038b8e  mov     rcx, r12; Address
0x180038b91  call    cs:__imp_ProbeForRead
0x180038b98  nop     dword ptr [rax+rax+00h]
0x180038b9d  jmp     short loc_180038BB9
0x180038b9f  test    al, 2
0x180038ba1  jz      short loc_180038BB9
0x180038ba3  mov     edx, [rsp+78h+DataLength]; Length
0x180038baa  mov     rcx, r12; Address
0x180038bad  call    cs:__imp_ProbeForWrite
0x180038bb4  nop     dword ptr [rax+rax+00h]
0x180038bb9  jmp     short loc_180038BBF
0x180038bbb  xor     al, al
0x180038bbd  jmp     short loc_180038C14
0x180038bbf  mov     rdx, [rsp+78h+IoStatus]
0x180038bc7  mov     qword ptr [rdx+8], 0
0x180038bcf  mov     rax, [rbx+8]
0x180038bd3  test    rax, rax
0x180038bd6  jz      short loc_180038C12
0x180038bd8  cmp     r14d, [rdi+10h]
0x180038bdc  jb      short loc_180038C12
0x180038bde  mov     ecx, [rsp+78h+DataLength]
0x180038be5  cmp     ecx, [rdi+14h]
0x180038be8  jb      short loc_180038C12
0x180038bea  mov     [rsp+78h+var_50], rdx
0x180038bef  mov     [rsp+78h+var_58], ecx
0x180038bf3  mov     r9, r12
0x180038bf6  mov     r8d, r14d
0x180038bf9  mov     rdx, rsi
0x180038bfc  mov     rcx, r13
0x180038bff  call    _guard_dispatch_icall
0x180038c04  jmp     short loc_180038C14
0x180038c06  add     rcx, 28h ; '('
0x180038c0a  add     eax, r9d
0x180038c0d  jmp     loc_180038B1A
0x180038c12  xor     al, al
0x180038c14  add     rsp, 40h
0x180038c18  pop     r15
0x180038c1a  pop     r14
0x180038c1c  pop     r13
0x180038c1e  pop     r12
0x180038c20  pop     rdi
0x180038c21  pop     rsi
0x180038c22  pop     rbx
0x180038c23  retn
```
