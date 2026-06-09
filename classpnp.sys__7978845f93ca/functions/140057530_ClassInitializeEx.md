# ClassInitializeEx

- ea: `0x140057530`
- end: `0x140057755`
- name: `ClassInitializeEx`
- size: `549`
- prototype: `ULONG __stdcall(PDRIVER_OBJECT DriverObject, LPGUID Guid, PVOID Data)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140057530`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400575e1`
- `ntoskrnl!ExAllocatePool2` at `0x140057688`
- `ntoskrnl!ExAllocatePool2` at `0x1400575e1`
- `ntoskrnl!ExAllocatePool2` at `0x140057688`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400576f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400576f0`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14005754c`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14005754c`

## pseudocode

```c
ULONG __stdcall ClassInitializeEx(PDRIVER_OBJECT DriverObject, LPGUID Guid, PVOID Data)
{
  _DWORD *DriverObjectExtension; // rax
  _DWORD *v6; // rdi
  __int64 v8; // rcx
  ULONG v9; // ebx
  __int64 v10; // rcx
  __int64 Pool2; // rax
  void *v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // ecx
  __int64 v16; // rcx

  DriverObjectExtension = IoGetDriverObjectExtension(DriverObject, ClassInitialize);
  v6 = DriverObjectExtension;
  if ( !DriverObjectExtension )
    return -1073741823;
  v8 = *(_QWORD *)&Guid->Data1 - ClassGuidQueryRegInfoEx;
  if ( *(_QWORD *)&Guid->Data1 == ClassGuidQueryRegInfoEx )
    v8 = *(_QWORD *)Guid->Data4 - qword_140063008;
  if ( v8 )
  {
    v10 = *(_QWORD *)&Guid->Data1 - ClassGuidWorkingSet;
    if ( *(_QWORD *)&Guid->Data1 == ClassGuidWorkingSet )
      v10 = *(_QWORD *)Guid->Data4 - qword_140063028;
    if ( !v10 )
    {
      if ( *(_DWORD *)Data != 12 )
        return -1073741811;
      Pool2 = ExAllocatePool2(64, 12, 1935106899);
      v12 = (void *)Pool2;
      if ( !Pool2 )
        return -1073741670;
      *(_QWORD *)Pool2 = *(_QWORD *)Data;
      *(_DWORD *)(Pool2 + 8) = *((_DWORD *)Data + 2);
      if ( *(_DWORD *)Pool2 == 12 && *(_DWORD *)(Pool2 + 4) <= 0x800u && *(_DWORD *)(Pool2 + 8) <= 0x800u )
      {
        if ( v6[7] != 2 )
        {
          v9 = -1073741808;
LABEL_38:
          ExFreePoolWithTag(v12, 0);
          return v9;
        }
        if ( !*((_QWORD *)v6 + 112) )
        {
          v9 = 0;
          *((_QWORD *)v6 + 112) = Pool2;
          return v9;
        }
      }
      v9 = -1073741811;
      goto LABEL_38;
    }
    v13 = *(_QWORD *)&Guid->Data1 - ClassGuidSenseInfo2;
    if ( *(_QWORD *)&Guid->Data1 == ClassGuidSenseInfo2 )
      v13 = *(_QWORD *)Guid->Data4 - qword_140063018;
    if ( v13 )
    {
      v16 = *(_QWORD *)&Guid->Data1 - ClassGuidSrbSupport;
      if ( *(_QWORD *)&Guid->Data1 == ClassGuidSrbSupport )
        v16 = *(_QWORD *)Guid->Data4 - qword_140063038;
      if ( v16 )
        return -1073741637;
      if ( (*(_DWORD *)Data & 3) != 0 )
      {
        DriverObjectExtension[226] = *(_DWORD *)Data;
        return 0;
      }
      return -1073741811;
    }
    if ( *(_DWORD *)Data != 24 )
      return -1073741811;
    v14 = ExAllocatePool2(64, 24, 844325715);
    if ( !v14 )
      return -1073741670;
    *(_OWORD *)v14 = *(_OWORD *)Data;
    *(_QWORD *)(v14 + 16) = *((_QWORD *)Data + 2);
    if ( *(_DWORD *)v14 == 24 )
    {
      v15 = *(_DWORD *)(v14 + 4);
      if ( v15 <= 0x7530 && *(_QWORD *)(v14 + 8) && v15 && *(_QWORD *)(v14 + 16) )
      {
        if ( v6[7] != 2 )
        {
          v9 = -1073741808;
LABEL_37:
          v12 = (void *)v14;
          goto LABEL_38;
        }
        if ( !*((_QWORD *)v6 + 111) )
        {
          v9 = 0;
          *((_QWORD *)v6 + 111) = v14;
          return v9;
        }
      }
    }
    v9 = -1073741811;
    goto LABEL_37;
  }
  if ( *(_DWORD *)Data != 24 )
    return -1073741811;
  *((_QWORD *)DriverObjectExtension + 52) = *((_QWORD *)Data + 1);
  *((_QWORD *)DriverObjectExtension + 53) = *((_QWORD *)Data + 2);
  return 0;
}

```

## disassembly

```asm
0x140057530  mov     [rsp+arg_0], rbx
0x140057535  mov     [rsp+arg_8], rsi
0x14005753a  push    rdi
0x14005753b  sub     rsp, 20h
0x14005753f  mov     rsi, rdx
0x140057542  mov     rbx, r8
0x140057545  lea     rdx, ClassInitialize; ClientIdentificationAddress
0x14005754c  call    cs:__imp_IoGetDriverObjectExtension
0x140057553  nop     dword ptr [rax+rax+00h]
0x140057558  mov     rdi, rax
0x14005755b  test    rax, rax
0x14005755e  jnz     short loc_14005756A
0x140057560  mov     eax, 0C0000001h
0x140057565  jmp     loc_140057744
0x14005756a  mov     rcx, [rsi]
0x14005756d  sub     rcx, cs:ClassGuidQueryRegInfoEx
0x140057574  jnz     short loc_140057581
0x140057576  mov     rcx, [rsi+8]
0x14005757a  sub     rcx, cs:qword_140063008
0x140057581  test    rcx, rcx
0x140057584  jnz     short loc_1400575AC
0x140057586  cmp     dword ptr [rbx], 18h
0x140057589  jnz     loc_140057736
0x14005758f  mov     rax, [rbx+8]
0x140057593  mov     [rdi+1A0h], rax
0x14005759a  mov     rax, [rbx+10h]
0x14005759e  mov     [rdi+1A8h], rax
0x1400575a5  xor     ebx, ebx
0x1400575a7  jmp     loc_140057742
0x1400575ac  mov     rcx, [rsi]
0x1400575af  sub     rcx, cs:ClassGuidWorkingSet
0x1400575b6  jnz     short loc_1400575C3
0x1400575b8  mov     rcx, [rsi+8]
0x1400575bc  sub     rcx, cs:qword_140063028
0x1400575c3  test    rcx, rcx
0x1400575c6  jnz     loc_140057653
0x1400575cc  cmp     dword ptr [rbx], 0Ch
0x1400575cf  jnz     loc_140057736
0x1400575d5  lea     edx, [rcx+0Ch]
0x1400575d8  mov     r8d, 73576353h
0x1400575de  lea     ecx, [rdx+34h]
0x1400575e1  call    cs:__imp_ExAllocatePool2
0x1400575e8  nop     dword ptr [rax+rax+00h]
0x1400575ed  mov     rcx, rax
0x1400575f0  test    rax, rax
0x1400575f3  jnz     short loc_1400575FF
0x1400575f5  mov     ebx, 0C000009Ah
0x1400575fa  jmp     loc_140057742
0x1400575ff  movsd   xmm0, qword ptr [rbx]
0x140057603  movsd   qword ptr [rax], xmm0
0x140057607  mov     eax, [rbx+8]
0x14005760a  mov     [rcx+8], eax
0x14005760d  cmp     dword ptr [rcx], 0Ch
0x140057610  jnz     short loc_14005763B
0x140057612  mov     eax, 800h
0x140057617  cmp     [rcx+4], eax
0x14005761a  ja      short loc_14005763B
0x14005761c  cmp     [rcx+8], eax
0x14005761f  ja      short loc_14005763B
0x140057621  cmp     dword ptr [rdi+1Ch], 2
0x140057625  jz      short loc_140057631
0x140057627  mov     ebx, 0C0000010h
0x14005762c  jmp     loc_1400576EE
0x140057631  cmp     qword ptr [rdi+380h], 0
0x140057639  jz      short loc_140057645
0x14005763b  mov     ebx, 0C000000Dh
0x140057640  jmp     loc_1400576EE
0x140057645  xor     ebx, ebx
0x140057647  mov     [rdi+380h], rcx
0x14005764e  jmp     loc_140057742
0x140057653  mov     rcx, [rsi]
0x140057656  sub     rcx, cs:ClassGuidSenseInfo2
0x14005765d  jnz     short loc_14005766A
0x14005765f  mov     rcx, [rsi+8]
0x140057663  sub     rcx, cs:qword_140063018
0x14005766a  test    rcx, rcx
0x14005766d  jnz     loc_140057709
0x140057673  cmp     dword ptr [rbx], 18h
0x140057676  jnz     loc_140057736
0x14005767c  lea     edx, [rcx+18h]
0x14005767f  mov     r8d, 32536353h
0x140057685  lea     ecx, [rdx+28h]
0x140057688  call    cs:__imp_ExAllocatePool2
0x14005768f  nop     dword ptr [rax+rax+00h]
0x140057694  test    rax, rax
0x140057697  jz      loc_1400575F5
0x14005769d  movups  xmm0, xmmword ptr [rbx]
0x1400576a0  movups  xmmword ptr [rax], xmm0
0x1400576a3  movsd   xmm1, qword ptr [rbx+10h]
0x1400576a8  movsd   qword ptr [rax+10h], xmm1
0x1400576ad  cmp     dword ptr [rax], 18h
0x1400576b0  jnz     short loc_1400576E6
0x1400576b2  mov     ecx, [rax+4]
0x1400576b5  cmp     ecx, 7530h
0x1400576bb  ja      short loc_1400576E6
0x1400576bd  cmp     qword ptr [rax+8], 0
0x1400576c2  jz      short loc_1400576E6
0x1400576c4  test    ecx, ecx
0x1400576c6  jz      short loc_1400576E6
0x1400576c8  cmp     qword ptr [rax+10h], 0
0x1400576cd  jz      short loc_1400576E6
0x1400576cf  cmp     dword ptr [rdi+1Ch], 2
0x1400576d3  jz      short loc_1400576DC
0x1400576d5  mov     ebx, 0C0000010h
0x1400576da  jmp     short loc_1400576EB
0x1400576dc  cmp     qword ptr [rdi+378h], 0
0x1400576e4  jz      short loc_1400576FE
0x1400576e6  mov     ebx, 0C000000Dh
0x1400576eb  mov     rcx, rax; P
0x1400576ee  xor     edx, edx; Tag
0x1400576f0  call    cs:__imp_ExFreePoolWithTag
0x1400576f7  nop     dword ptr [rax+rax+00h]
0x1400576fc  jmp     short loc_140057742
0x1400576fe  xor     ebx, ebx
0x140057700  mov     [rdi+378h], rax
0x140057707  jmp     short loc_140057742
0x140057709  mov     rcx, [rsi]
0x14005770c  sub     rcx, cs:ClassGuidSrbSupport
0x140057713  jnz     short loc_140057720
0x140057715  mov     rcx, [rsi+8]
0x140057719  sub     rcx, cs:qword_140063038
0x140057720  test    rcx, rcx
0x140057723  jnz     short loc_14005773D
0x140057725  mov     eax, [rbx]
0x140057727  test    al, 3
0x140057729  jz      short loc_140057736
0x14005772b  mov     [rdi+388h], eax
0x140057731  jmp     loc_1400575A5
0x140057736  mov     ebx, 0C000000Dh
0x14005773b  jmp     short loc_140057742
0x14005773d  mov     ebx, 0C00000BBh
0x140057742  mov     eax, ebx
0x140057744  mov     rbx, [rsp+28h+arg_0]
0x140057749  mov     rsi, [rsp+28h+arg_8]
0x14005774e  add     rsp, 20h
0x140057752  pop     rdi
0x140057753  retn
```
