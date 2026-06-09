# KsFastMethodHandler

- ea: `0x180038970`
- end: `0x180038b15`
- name: `KsFastMethodHandler`
- size: `421`
- prototype: `BOOLEAN __stdcall(PFILE_OBJECT FileObject, PKSMETHOD Method, ULONG MethodLength, PVOID Data, ULONG DataLength, PIO_STATUS_BLOCK IoStatus, ULONG MethodSetsCount, const KSMETHOD_SET *MethodSet)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180019c60`
- `0x180038970`
- `0x180051460`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x180038996`
- `ntoskrnl!ExGetPreviousMode` at `0x180038996`
- `ntoskrnl!ProbeForWrite` at `0x180038a9d`
- `ntoskrnl!ProbeForWrite` at `0x180038a9d`
- `ntoskrnl!ProbeForRead` at `0x1800389b5`
- `ntoskrnl!ProbeForRead` at `0x180038a81`
- `ntoskrnl!ProbeForRead` at `0x1800389b5`
- `ntoskrnl!ProbeForRead` at `0x180038a81`

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
            MethodItem = FindMethodItem(MethodSet, 40, Id);
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
0x180038970  push    rbx
0x180038972  push    rsi
0x180038973  push    rdi
0x180038974  push    r12
0x180038976  push    r13
0x180038978  push    r14
0x18003897a  push    r15
0x18003897c  sub     rsp, 40h
0x180038980  mov     r12, r9
0x180038983  mov     r14d, r8d
0x180038986  mov     rsi, rdx
0x180038989  mov     r13, rcx
0x18003898c  cmp     r8d, 18h
0x180038990  jb      loc_180038B02
0x180038996  call    cs:__imp_ExGetPreviousMode
0x18003899d  nop     dword ptr [rax+rax+00h]
0x1800389a2  mov     r15b, al
0x1800389a5  test    al, al
0x1800389a7  jz      short loc_1800389CB
0x1800389a9  mov     edx, r14d; Length
0x1800389ac  mov     r8d, 4; Alignment
0x1800389b2  mov     rcx, rsi; Address
0x1800389b5  call    cs:__imp_ProbeForRead
0x1800389bc  nop     dword ptr [rax+rax+00h]
0x1800389c1  nop
0x1800389c2  jmp     short loc_1800389CB
0x1800389c4  xor     al, al
0x1800389c6  jmp     loc_180038B04
0x1800389cb  mov     ecx, 14h
0x1800389d0  mov     r9, rsi
0x1800389d3  lea     r11d, [rcx-4]
0x1800389d7  mov     r10, rsi
0x1800389da  lea     eax, [rcx-0Ch]
0x1800389dd  mov     r8, rsi
0x1800389e0  mov     rdx, rsi
0x1800389e3  mov     r8, [rsi+rax]
0x1800389e7  mov     rbx, [rdx]
0x1800389ea  test    dword ptr [rcx+rsi], 0FFF00h
0x1800389f1  jnz     loc_180038B02
0x1800389f7  mov     eax, [rsp+78h+MethodSetsCount]
0x1800389fe  or      r9d, 0FFFFFFFFh
0x180038a02  mov     rcx, [rsp+78h+MethodSet]
0x180038a0a  test    eax, eax
0x180038a0c  jz      loc_180038B02
0x180038a12  mov     rdx, [rcx]
0x180038a15  cmp     rbx, [rdx]
0x180038a18  jnz     loc_180038AF6
0x180038a1e  cmp     r8, [rdx+8]
0x180038a22  jnz     loc_180038AF6
0x180038a28  mov     r8d, [r11+r10]
0x180038a2c  mov     rbx, [rcx+20h]
0x180038a30  mov     eax, [rcx+18h]
0x180038a33  test    eax, eax
0x180038a35  jz      short loc_180038A45
0x180038a37  cmp     r8d, [rbx]
0x180038a3a  jz      short loc_180038A47
0x180038a3c  add     eax, r9d
0x180038a3f  add     rbx, 10h
0x180038a43  jmp     short loc_180038A33
0x180038a45  xor     ebx, ebx
0x180038a47  test    rbx, rbx
0x180038a4a  jz      loc_180038B02
0x180038a50  mov     edx, 28h ; '('
0x180038a55  call    FindMethodItem
0x180038a5a  mov     rdi, rax
0x180038a5d  test    rax, rax
0x180038a60  jz      loc_180038B02
0x180038a66  test    r15b, r15b
0x180038a69  jz      short loc_180038AAF
0x180038a6b  mov     eax, [rax+20h]
0x180038a6e  lea     r8d, [rdx-27h]; Alignment
0x180038a72  test    r8b, al
0x180038a75  jz      short loc_180038A8F
0x180038a77  mov     edx, [rsp+78h+DataLength]; Length
0x180038a7e  mov     rcx, r12; Address
0x180038a81  call    cs:__imp_ProbeForRead
0x180038a88  nop     dword ptr [rax+rax+00h]
0x180038a8d  jmp     short loc_180038AA9
0x180038a8f  test    al, 2
0x180038a91  jz      short loc_180038AA9
0x180038a93  mov     edx, [rsp+78h+DataLength]; Length
0x180038a9a  mov     rcx, r12; Address
0x180038a9d  call    cs:__imp_ProbeForWrite
0x180038aa4  nop     dword ptr [rax+rax+00h]
0x180038aa9  jmp     short loc_180038AAF
0x180038aab  xor     al, al
0x180038aad  jmp     short loc_180038B04
0x180038aaf  mov     rdx, [rsp+78h+IoStatus]
0x180038ab7  mov     qword ptr [rdx+8], 0
0x180038abf  mov     rax, [rbx+8]
0x180038ac3  test    rax, rax
0x180038ac6  jz      short loc_180038B02
0x180038ac8  cmp     r14d, [rdi+10h]
0x180038acc  jb      short loc_180038B02
0x180038ace  mov     ecx, [rsp+78h+DataLength]
0x180038ad5  cmp     ecx, [rdi+14h]
0x180038ad8  jb      short loc_180038B02
0x180038ada  mov     [rsp+78h+var_50], rdx
0x180038adf  mov     [rsp+78h+var_58], ecx
0x180038ae3  mov     r9, r12
0x180038ae6  mov     r8d, r14d
0x180038ae9  mov     rdx, rsi
0x180038aec  mov     rcx, r13
0x180038aef  call    _guard_dispatch_icall
0x180038af4  jmp     short loc_180038B04
0x180038af6  add     rcx, 28h ; '('
0x180038afa  add     eax, r9d
0x180038afd  jmp     loc_180038A0A
0x180038b02  xor     al, al
0x180038b04  add     rsp, 40h
0x180038b08  pop     r15
0x180038b0a  pop     r14
0x180038b0c  pop     r13
0x180038b0e  pop     r12
0x180038b10  pop     rdi
0x180038b11  pop     rsi
0x180038b12  pop     rbx
0x180038b13  retn
```
