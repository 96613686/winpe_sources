# KsFastPropertyHandler

- ea: `0x180038ca0`
- end: `0x180038e8c`
- name: `KsFastPropertyHandler`
- size: `492`
- prototype: `BOOLEAN __stdcall(PFILE_OBJECT FileObject, PKSPROPERTY Property, ULONG PropertyLength, PVOID Data, ULONG DataLength, PIO_STATUS_BLOCK IoStatus, ULONG PropertySetsCount, const KSPROPERTY_SET *PropertySet)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180019cb0`
- `0x180038ca0`
- `0x18004bbe0`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x180038ccf`
- `ntoskrnl!ExGetPreviousMode` at `0x180038ccf`
- `ntoskrnl!ProbeForRead` at `0x180038cee`
- `ntoskrnl!ProbeForRead` at `0x180038e3c`
- `ntoskrnl!ProbeForRead` at `0x180038cee`
- `ntoskrnl!ProbeForRead` at `0x180038e3c`
- `ntoskrnl!ProbeForWrite` at `0x180038de1`
- `ntoskrnl!ProbeForWrite` at `0x180038de1`

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
  const KSFASTPROPERTY_ITEM *FastIoTable; // rbx
  ULONG i; // ecx
  __int64 PropertyItem; // rax
  int v17; // edx
  int v18; // r10d
  __int64 v19; // rsi
  unsigned int v20; // r10d
  ULONG v21; // r8d

  if ( PropertyLength >= 0x18 )
  {
    PreviousMode = ExGetPreviousMode();
    if ( PreviousMode )
      ProbeForRead(Property, PropertyLength, 4u);
    if ( (Property->Flags & 0xFFF00) == 0 )
    {
      while ( PropertySetsCount )
      {
        if ( Property->Alignment == *(_QWORD *)&PropertySet->Set->Data1
          && *(&Property->Alignment + 1) == *(_QWORD *)PropertySet->Set->Data4 )
        {
          FastIoTable = PropertySet->FastIoTable;
          for ( i = PropertySet->FastIoCount; i; --i )
          {
            if ( Property->Id == FastIoTable->PropertyId )
              goto LABEL_13;
            ++FastIoTable;
          }
          FastIoTable = 0;
LABEL_13:
          if ( !FastIoTable )
            return 0;
          PropertyItem = FindPropertyItem(PropertySet, 72);
          v19 = PropertyItem;
          if ( !PropertyItem
            || PropertyLength < *(_DWORD *)(PropertyItem + 16)
            || DataLength < *(_DWORD *)(PropertyItem + 20) )
          {
            return 0;
          }
          v20 = v18 & 0xEFFFFFFF;
          v21 = v17 - 71;
          if ( v20 == v17 - 71 )
          {
            if ( !FastIoTable->GetPropertyHandler )
              return 0;
            if ( PreviousMode )
              ProbeForWrite(Data, DataLength, v21);
            IoStatus->Information = *(unsigned int *)(v19 + 16);
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
            if ( v20 != 2 || !FastIoTable->SetPropertyHandler )
              return 0;
            if ( PreviousMode )
              ProbeForRead(Data, DataLength, v21);
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
0x180038ca0  mov     [rsp+arg_8], rbx
0x180038ca5  mov     [rsp+arg_10], rsi
0x180038caa  mov     [rsp+arg_0], rcx
0x180038caf  push    rdi
0x180038cb0  push    r12
0x180038cb2  push    r13
0x180038cb4  push    r14
0x180038cb6  push    r15
0x180038cb8  sub     rsp, 40h
0x180038cbc  mov     r13, r9
0x180038cbf  mov     r12d, r8d
0x180038cc2  mov     r14, rdx
0x180038cc5  cmp     r8d, 18h
0x180038cc9  jb      loc_180038E6F
0x180038ccf  call    cs:__imp_ExGetPreviousMode
0x180038cd6  nop     dword ptr [rax+rax+00h]
0x180038cdb  mov     r15b, al
0x180038cde  test    al, al
0x180038ce0  jz      short loc_180038D04
0x180038ce2  mov     edx, r12d; Length
0x180038ce5  mov     r8d, 4; Alignment
0x180038ceb  mov     rcx, r14; Address
0x180038cee  call    cs:__imp_ProbeForRead
0x180038cf5  nop     dword ptr [rax+rax+00h]
0x180038cfa  nop
0x180038cfb  jmp     short loc_180038D04
0x180038cfd  xor     al, al
0x180038cff  jmp     loc_180038E71
0x180038d04  mov     ecx, 14h
0x180038d09  mov     r10, r14
0x180038d0c  lea     r8d, [rcx-4]
0x180038d10  mov     r11, r14
0x180038d13  lea     eax, [rcx-0Ch]
0x180038d16  mov     r9, r14
0x180038d19  mov     rdx, r14
0x180038d1c  mov     r10d, [r14+rcx]
0x180038d20  mov     r9, [rax+r14]
0x180038d24  mov     rbx, [rdx]
0x180038d27  test    r10d, 0FFF00h
0x180038d2e  jnz     loc_180038E6F
0x180038d34  mov     ecx, [rsp+68h+PropertySetsCount]
0x180038d3b  or      edi, 0FFFFFFFFh
0x180038d3e  mov     rax, [rsp+68h+PropertySet]
0x180038d46  test    ecx, ecx
0x180038d48  jz      loc_180038E6F
0x180038d4e  mov     rdx, [rax]
0x180038d51  cmp     rbx, [rdx]
0x180038d54  jnz     loc_180038E64
0x180038d5a  cmp     r9, [rdx+8]
0x180038d5e  jnz     loc_180038E64
0x180038d64  mov     r8d, [r11+r8]
0x180038d68  mov     rbx, [rax+20h]
0x180038d6c  mov     ecx, [rax+18h]
0x180038d6f  test    ecx, ecx
0x180038d71  jz      short loc_180038D80
0x180038d73  cmp     r8d, [rbx]
0x180038d76  jz      short loc_180038D82
0x180038d78  add     ecx, edi
0x180038d7a  add     rbx, 20h ; ' '
0x180038d7e  jmp     short loc_180038D6F
0x180038d80  xor     ebx, ebx
0x180038d82  test    rbx, rbx
0x180038d85  jz      loc_180038E6F
0x180038d8b  mov     edx, 48h ; 'H'
0x180038d90  mov     rcx, rax
0x180038d93  call    FindPropertyItem
0x180038d98  mov     rsi, rax
0x180038d9b  test    rax, rax
0x180038d9e  jz      loc_180038E6F
0x180038da4  cmp     r12d, [rax+10h]
0x180038da8  jb      loc_180038E6F
0x180038dae  mov     edi, [rsp+68h+DataLength]
0x180038db5  cmp     edi, [rax+14h]
0x180038db8  jb      loc_180038E6F
0x180038dbe  btr     r10d, 1Ch
0x180038dc3  lea     r8d, [rdx-47h]; Alignment
0x180038dc7  cmp     r10d, r8d
0x180038dca  jnz     short loc_180038E24
0x180038dcc  cmp     qword ptr [rbx+8], 0
0x180038dd1  jz      loc_180038E6F
0x180038dd7  test    r15b, r15b
0x180038dda  jz      short loc_180038DF3
0x180038ddc  mov     edx, edi; Length
0x180038dde  mov     rcx, r13; Address
0x180038de1  call    cs:__imp_ProbeForWrite
0x180038de8  nop     dword ptr [rax+rax+00h]
0x180038ded  jmp     short loc_180038DF3
0x180038def  xor     al, al
0x180038df1  jmp     short loc_180038E71
0x180038df3  mov     eax, [rsi+10h]
0x180038df6  mov     rcx, [rsp+68h+IoStatus]
0x180038dfe  mov     [rcx+8], rax
0x180038e02  mov     rax, [rbx+8]
0x180038e06  mov     [rsp+68h+var_40], rcx
0x180038e0b  mov     [rsp+68h+var_48], edi
0x180038e0f  mov     r9, r13
0x180038e12  mov     r8d, r12d
0x180038e15  mov     rdx, r14
0x180038e18  mov     rcx, [rsp+68h+arg_0]
0x180038e1d  call    _guard_dispatch_icall
0x180038e22  jmp     short loc_180038E71
0x180038e24  cmp     r10d, 2
0x180038e28  jnz     short loc_180038E6F
0x180038e2a  cmp     qword ptr [rbx+10h], 0
0x180038e2f  jz      short loc_180038E6F
0x180038e31  test    r15b, r15b
0x180038e34  jz      short loc_180038E4E
0x180038e36  mov     rdx, rdi; Length
0x180038e39  mov     rcx, r13; Address
0x180038e3c  call    cs:__imp_ProbeForRead
0x180038e43  nop     dword ptr [rax+rax+00h]
0x180038e48  jmp     short loc_180038E4E
0x180038e4a  xor     al, al
0x180038e4c  jmp     short loc_180038E71
0x180038e4e  mov     rcx, [rsp+68h+IoStatus]
0x180038e56  mov     qword ptr [rcx+8], 0
0x180038e5e  mov     rax, [rbx+10h]
0x180038e62  jmp     short loc_180038E06
0x180038e64  add     rax, 28h ; '('
0x180038e68  add     ecx, edi
0x180038e6a  jmp     loc_180038D46
0x180038e6f  xor     al, al
0x180038e71  lea     r11, [rsp+68h+var_28]
0x180038e76  mov     rbx, [r11+38h]
0x180038e7a  mov     rsi, [r11+40h]
0x180038e7e  mov     rsp, r11
0x180038e81  pop     r15
0x180038e83  pop     r14
0x180038e85  pop     r13
0x180038e87  pop     r12
0x180038e89  pop     rdi
0x180038e8a  retn
```
