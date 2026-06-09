# KsFastPropertyHandler

- ea: `0x180038b90`
- end: `0x180038d7c`
- name: `KsFastPropertyHandler`
- size: `492`
- prototype: `BOOLEAN __stdcall(PFILE_OBJECT FileObject, PKSPROPERTY Property, ULONG PropertyLength, PVOID Data, ULONG DataLength, PIO_STATUS_BLOCK IoStatus, ULONG PropertySetsCount, const KSPROPERTY_SET *PropertySet)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180019c60`
- `0x180038b90`
- `0x18004d4c0`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x180038bbf`
- `ntoskrnl!ExGetPreviousMode` at `0x180038bbf`
- `ntoskrnl!ProbeForWrite` at `0x180038cd1`
- `ntoskrnl!ProbeForWrite` at `0x180038cd1`
- `ntoskrnl!ProbeForRead` at `0x180038bde`
- `ntoskrnl!ProbeForRead` at `0x180038d2c`
- `ntoskrnl!ProbeForRead` at `0x180038bde`
- `ntoskrnl!ProbeForRead` at `0x180038d2c`

## pseudocode

```c
BOOLEAN __stdcall KsFastPropertyHandler(
        PFILE_OBJECT FileObject,
        PKSPROPERTY Property,
        ULONG PropertyLength,
        PVOID Data,
        ULONG DataLength,
        PIO_STATUS_BLOCK IoStatus,
        ULONG PropertySetsCount,
        const KSPROPERTY_SET *PropertySet)
{
  KPROCESSOR_MODE PreviousMode; // r15
  __int64 v12; // r9
  __int64 Id; // r8
  const KSFASTPROPERTY_ITEM *FastIoTable; // rbx
  ULONG i; // ecx
  __int64 PropertyItem; // rax
  int v19; // edx
  int v20; // r10d
  __int64 v21; // rsi
  unsigned int v22; // r10d
  ULONG v23; // r8d

  if ( PropertyLength >= 0x18 )
  {
    PreviousMode = ExGetPreviousMode();
    if ( PreviousMode )
      ProbeForRead(Property, PropertyLength, 4u);
    v12 = *(&Property->Alignment + 1);
    if ( (Property->Flags & 0xFFF00) == 0 )
    {
      while ( PropertySetsCount )
      {
        if ( Property->Alignment == *(_QWORD *)&PropertySet->Set->Data1 && v12 == *(_QWORD *)PropertySet->Set->Data4 )
        {
          Id = Property->Id;
          FastIoTable = PropertySet->FastIoTable;
          for ( i = PropertySet->FastIoCount; i; --i )
          {
            if ( (_DWORD)Id == FastIoTable->PropertyId )
              goto LABEL_13;
            ++FastIoTable;
          }
          FastIoTable = 0;
LABEL_13:
          if ( !FastIoTable )
            return 0;
          PropertyItem = FindPropertyItem(PropertySet, 72, Id, v12);
          v21 = PropertyItem;
          if ( !PropertyItem
            || PropertyLength < *(_DWORD *)(PropertyItem + 16)
            || DataLength < *(_DWORD *)(PropertyItem + 20) )
          {
            return 0;
          }
          v22 = v20 & 0xEFFFFFFF;
          v23 = v19 - 71;
          if ( v22 == v19 - 71 )
          {
            if ( !FastIoTable->GetPropertyHandler )
              return 0;
            if ( PreviousMode )
              ProbeForWrite(Data, DataLength, v23);
            IoStatus->Information = *(unsigned int *)(v21 + 16);
            return ((__int64 (__fastcall *)(PFILE_OBJECT, PKSPROPERTY, _QWORD, PVOID, ULONG, PIO_STATUS_BLOCK))FastIoTable->GetPropertyHandler)(
                     FileObject,
                     Property,
                     PropertyLength,
                     Data,
                     DataLength,
                     IoStatus);
          }
          else
          {
            if ( v22 != 2 || !FastIoTable->SetPropertyHandler )
              return 0;
            if ( PreviousMode )
              ProbeForRead(Data, DataLength, v23);
            IoStatus->Information = 0;
            return ((__int64 (__fastcall *)(PFILE_OBJECT, PKSPROPERTY, _QWORD, PVOID, ULONG, PIO_STATUS_BLOCK))FastIoTable->SetPropertyHandler)(
                     FileObject,
                     Property,
                     PropertyLength,
                     Data,
                     DataLength,
                     IoStatus);
          }
        }
        ++PropertySet;
        --PropertySetsCount;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180038b90  mov     [rsp+arg_8], rbx
0x180038b95  mov     [rsp+arg_10], rsi
0x180038b9a  mov     [rsp+arg_0], rcx
0x180038b9f  push    rdi
0x180038ba0  push    r12
0x180038ba2  push    r13
0x180038ba4  push    r14
0x180038ba6  push    r15
0x180038ba8  sub     rsp, 40h
0x180038bac  mov     r13, r9
0x180038baf  mov     r12d, r8d
0x180038bb2  mov     r14, rdx
0x180038bb5  cmp     r8d, 18h
0x180038bb9  jb      loc_180038D5F
0x180038bbf  call    cs:__imp_ExGetPreviousMode
0x180038bc6  nop     dword ptr [rax+rax+00h]
0x180038bcb  mov     r15b, al
0x180038bce  test    al, al
0x180038bd0  jz      short loc_180038BF4
0x180038bd2  mov     edx, r12d; Length
0x180038bd5  mov     r8d, 4; Alignment
0x180038bdb  mov     rcx, r14; Address
0x180038bde  call    cs:__imp_ProbeForRead
0x180038be5  nop     dword ptr [rax+rax+00h]
0x180038bea  nop
0x180038beb  jmp     short loc_180038BF4
0x180038bed  xor     al, al
0x180038bef  jmp     loc_180038D61
0x180038bf4  mov     ecx, 14h
0x180038bf9  mov     r10, r14
0x180038bfc  lea     r8d, [rcx-4]
0x180038c00  mov     r11, r14
0x180038c03  lea     eax, [rcx-0Ch]
0x180038c06  mov     r9, r14
0x180038c09  mov     rdx, r14
0x180038c0c  mov     r10d, [r14+rcx]
0x180038c10  mov     r9, [rax+r14]
0x180038c14  mov     rbx, [rdx]
0x180038c17  test    r10d, 0FFF00h
0x180038c1e  jnz     loc_180038D5F
0x180038c24  mov     ecx, [rsp+68h+PropertySetsCount]
0x180038c2b  or      edi, 0FFFFFFFFh
0x180038c2e  mov     rax, [rsp+68h+PropertySet]
0x180038c36  test    ecx, ecx
0x180038c38  jz      loc_180038D5F
0x180038c3e  mov     rdx, [rax]
0x180038c41  cmp     rbx, [rdx]
0x180038c44  jnz     loc_180038D54
0x180038c4a  cmp     r9, [rdx+8]
0x180038c4e  jnz     loc_180038D54
0x180038c54  mov     r8d, [r11+r8]
0x180038c58  mov     rbx, [rax+20h]
0x180038c5c  mov     ecx, [rax+18h]
0x180038c5f  test    ecx, ecx
0x180038c61  jz      short loc_180038C70
0x180038c63  cmp     r8d, [rbx]
0x180038c66  jz      short loc_180038C72
0x180038c68  add     ecx, edi
0x180038c6a  add     rbx, 20h ; ' '
0x180038c6e  jmp     short loc_180038C5F
0x180038c70  xor     ebx, ebx
0x180038c72  test    rbx, rbx
0x180038c75  jz      loc_180038D5F
0x180038c7b  mov     edx, 48h ; 'H'
0x180038c80  mov     rcx, rax
0x180038c83  call    FindPropertyItem
0x180038c88  mov     rsi, rax
0x180038c8b  test    rax, rax
0x180038c8e  jz      loc_180038D5F
0x180038c94  cmp     r12d, [rax+10h]
0x180038c98  jb      loc_180038D5F
0x180038c9e  mov     edi, [rsp+68h+DataLength]
0x180038ca5  cmp     edi, [rax+14h]
0x180038ca8  jb      loc_180038D5F
0x180038cae  btr     r10d, 1Ch
0x180038cb3  lea     r8d, [rdx-47h]; Alignment
0x180038cb7  cmp     r10d, r8d
0x180038cba  jnz     short loc_180038D14
0x180038cbc  cmp     qword ptr [rbx+8], 0
0x180038cc1  jz      loc_180038D5F
0x180038cc7  test    r15b, r15b
0x180038cca  jz      short loc_180038CE3
0x180038ccc  mov     edx, edi; Length
0x180038cce  mov     rcx, r13; Address
0x180038cd1  call    cs:__imp_ProbeForWrite
0x180038cd8  nop     dword ptr [rax+rax+00h]
0x180038cdd  jmp     short loc_180038CE3
0x180038cdf  xor     al, al
0x180038ce1  jmp     short loc_180038D61
0x180038ce3  mov     eax, [rsi+10h]
0x180038ce6  mov     rcx, [rsp+68h+IoStatus]
0x180038cee  mov     [rcx+8], rax
0x180038cf2  mov     rax, [rbx+8]
0x180038cf6  mov     [rsp+68h+var_40], rcx
0x180038cfb  mov     [rsp+68h+var_48], edi
0x180038cff  mov     r9, r13
0x180038d02  mov     r8d, r12d
0x180038d05  mov     rdx, r14
0x180038d08  mov     rcx, [rsp+68h+arg_0]
0x180038d0d  call    _guard_dispatch_icall
0x180038d12  jmp     short loc_180038D61
0x180038d14  cmp     r10d, 2
0x180038d18  jnz     short loc_180038D5F
0x180038d1a  cmp     qword ptr [rbx+10h], 0
0x180038d1f  jz      short loc_180038D5F
0x180038d21  test    r15b, r15b
0x180038d24  jz      short loc_180038D3E
0x180038d26  mov     rdx, rdi; Length
0x180038d29  mov     rcx, r13; Address
0x180038d2c  call    cs:__imp_ProbeForRead
0x180038d33  nop     dword ptr [rax+rax+00h]
0x180038d38  jmp     short loc_180038D3E
0x180038d3a  xor     al, al
0x180038d3c  jmp     short loc_180038D61
0x180038d3e  mov     rcx, [rsp+68h+IoStatus]
0x180038d46  mov     qword ptr [rcx+8], 0
0x180038d4e  mov     rax, [rbx+10h]
0x180038d52  jmp     short loc_180038CF6
0x180038d54  add     rax, 28h ; '('
0x180038d58  add     ecx, edi
0x180038d5a  jmp     loc_180038C36
0x180038d5f  xor     al, al
0x180038d61  lea     r11, [rsp+68h+var_28]
0x180038d66  mov     rbx, [r11+38h]
0x180038d6a  mov     rsi, [r11+40h]
0x180038d6e  mov     rsp, r11
0x180038d71  pop     r15
0x180038d73  pop     r14
0x180038d75  pop     r13
0x180038d77  pop     r12
0x180038d79  pop     rdi
0x180038d7a  retn
```
