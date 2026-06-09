# IoctlQueryBSSIdList(_IRP *,ulong,void *,ulong *)

- ea: `0x1400155ac`
- end: `0x140015896`
- name: `?IoctlQueryBSSIdList@@YAJPEAU_IRP@@KPEAXPEAK@Z`
- size: `746`
- prototype: `int(struct _IRP *, unsigned int, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000cb10`

## callees

- `0x14000d22c`
- `0x1400155ac`
- `0x14001589c`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140015624`
- `ntoskrnl!KeWaitForSingleObject` at `0x140015840`
- `ntoskrnl!KeWaitForSingleObject` at `0x140015624`
- `ntoskrnl!KeWaitForSingleObject` at `0x140015840`
- `ntoskrnl!KeSetEvent` at `0x140015668`
- `ntoskrnl!KeSetEvent` at `0x140015872`
- `ntoskrnl!KeSetEvent` at `0x140015668`
- `ntoskrnl!KeSetEvent` at `0x140015872`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015803`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140015803`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015814`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015814`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400156f5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400156f5`

## pseudocode

```c
__int64 __fastcall IoctlQueryBSSIdList(struct _IRP *a1, int a2, unsigned __int8 *a3, unsigned int *a4)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct DOT11_BYTE_ARRAY *v5; // rbp
  int v6; // r12d
  _FILE_OBJECT *FileObject; // r10
  char *FsContext; // rsi
  __int64 v12; // rax
  int v13; // ebx
  signed int v14; // edi
  __int64 v15; // rdx
  _MDL *MdlAddress; // rbx
  _DWORD *MappedSystemVa; // r14
  unsigned int ByteCount; // eax
  unsigned __int8 *v19; // r9
  int v20; // r8d
  unsigned int v21; // ebx
  signed int v22; // eax
  unsigned int uNumOfBytes; // eax
  unsigned int v24; // ebx
  unsigned int v25; // ecx
  unsigned int uTotalNumOfBytes; // eax
  __int16 v28; // [rsp+70h] [rbp+8h] BYREF
  char v29; // [rsp+72h] [rbp+Ah]
  unsigned __int8 *v30; // [rsp+80h] [rbp+18h]
  struct DOT11_BYTE_ARRAY *v31; // [rsp+88h] [rbp+20h] BYREF

  v30 = a3;
  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  v5 = 0;
  v6 = 0;
  v31 = 0;
  FileObject = CurrentStackLocation->FileObject;
  v28 = 0;
  v29 = 0;
  *a4 = 0;
  FsContext = (char *)FileObject->FsContext;
  if ( !FsContext )
    goto LABEL_38;
  FsContext = (char *)*((_QWORD *)FsContext + 2);
  if ( *((_DWORD *)FsContext + 1402) )
  {
LABEL_10:
    v14 = -1073741810;
LABEL_39:
    v25 = 0;
    goto LABEL_40;
  }
  KeWaitForSingleObject(FsContext + 8048, Executive, 0, 0, 0);
  *((_QWORD *)FsContext + 1009) = KeGetCurrentThread();
  v12 = *((_QWORD *)FsContext + 2);
  if ( !v12 || *(_DWORD *)(v12 + 20) == 6 )
  {
    v13 = 0;
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)FsContext + 1403);
    v13 = 1;
  }
  *((_QWORD *)FsContext + 1009) = 0;
  KeSetEvent((PRKEVENT)(FsContext + 8048), 1, 0);
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_9d07a56bbaea364d4305f48ac15d89f0_Traceguids);
    goto LABEL_10;
  }
  v15 = 1;
  v6 = 1;
  if ( (*(_QWORD *)(*((_QWORD *)FsContext + 2) + 48LL) & *(_QWORD *)(*((_QWORD *)FsContext + 2) + 40LL)) == 0 )
  {
    v14 = -1071439870;
    goto LABEL_39;
  }
  MdlAddress = a1->MdlAddress;
  if ( !MdlAddress )
  {
    v14 = -1073741811;
    goto LABEL_39;
  }
  if ( (MdlAddress->MdlFlags & 5) != 0 )
    MappedSystemVa = MdlAddress->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
  if ( !MappedSystemVa )
  {
    v14 = -1073741670;
    goto LABEL_39;
  }
  ByteCount = MdlAddress->ByteCount;
  if ( ByteCount < 8 )
  {
    v14 = -1073741789;
    goto LABEL_39;
  }
  if ( ((unsigned __int8)MappedSystemVa & 3) != 0 )
  {
    v14 = -1073741115;
    goto LABEL_39;
  }
  if ( MdlAddress->Next )
  {
    v14 = -1073741637;
    goto LABEL_39;
  }
  v19 = (unsigned __int8 *)&v28;
  v20 = 3;
  if ( a2 )
  {
    v19 = v30;
    v20 = a2;
  }
  if ( v20 != 3 )
  {
LABEL_38:
    v14 = -1073741811;
    goto LABEL_39;
  }
  v21 = ByteCount - 8;
  v22 = NwfCallByteArray(*((struct _ADAPT **)FsContext + 2), v15, 3u, v19, ByteCount - 8, &v31);
  v5 = v31;
  v14 = 0;
  if ( v22 != -2147483643 )
    v14 = v22;
  if ( v14 )
  {
    if ( v14 >= 0 )
      v14 = -1073741823;
    goto LABEL_39;
  }
  uNumOfBytes = v31->uNumOfBytes;
  if ( uNumOfBytes >= v21 )
    uNumOfBytes = v21;
  v24 = uNumOfBytes;
  memmove(MappedSystemVa + 2, v31->ucBuffer, uNumOfBytes);
  *MappedSystemVa = v24;
  v25 = v24 + 8;
  uTotalNumOfBytes = v5->uTotalNumOfBytes;
  MappedSystemVa[1] = uTotalNumOfBytes;
  v14 = v24 < uTotalNumOfBytes ? 0x80000005 : 0;
LABEL_40:
  *a4 = v25;
  if ( v5 )
  {
    if ( *(_QWORD *)&v5[-1].Header.Type )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)&v5[-1].Header.Type, &v5[-1]);
    else
      ExFreePoolWithTag(&v5[-1], v5[-1].uTotalNumOfBytes);
  }
  if ( v6 )
  {
    KeWaitForSingleObject(FsContext + 8048, Executive, 0, 0, 0);
    *((_QWORD *)FsContext + 1009) = KeGetCurrentThread();
    _InterlockedDecrement((volatile signed __int32 *)FsContext + 1403);
    *((_QWORD *)FsContext + 1009) = 0;
    KeSetEvent((PRKEVENT)(FsContext + 8048), 1, 0);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400155ac  mov     r11, rsp
0x1400155af  mov     [r11+10h], rbx
0x1400155b3  mov     [r11+18h], r8
0x1400155b7  push    rbp
0x1400155b8  push    rsi
0x1400155b9  push    rdi
0x1400155ba  push    r12
0x1400155bc  push    r13
0x1400155be  push    r14
0x1400155c0  push    r15
0x1400155c2  sub     rsp, 30h
0x1400155c6  mov     rax, [rcx+0B8h]
0x1400155cd  xor     ebp, ebp
0x1400155cf  xor     r12d, r12d
0x1400155d2  mov     [r11+20h], rbp
0x1400155d6  mov     r13, r9
0x1400155d9  mov     r15d, edx
0x1400155dc  mov     r14, rcx
0x1400155df  mov     r10, [rax+30h]
0x1400155e3  xor     eax, eax
0x1400155e5  mov     [rsp+68h+arg_0], ax
0x1400155ea  mov     [rsp+68h+arg_2], al
0x1400155ee  mov     [r9], eax
0x1400155f1  mov     rsi, [r10+18h]
0x1400155f5  test    rsi, rsi
0x1400155f8  jz      loc_1400157E1
0x1400155fe  mov     rsi, [rsi+10h]
0x140015602  cmp     [rsi+15E8h], eax
0x140015608  jnz     loc_14001569E
0x14001560e  lea     rdi, [rsi+1F70h]
0x140015615  mov     [r11-48h], rax
0x140015619  mov     rcx, rdi; Object
0x14001561c  xor     r9d, r9d; Alertable
0x14001561f  xor     r8d, r8d; WaitMode
0x140015622  xor     edx, edx; WaitReason
0x140015624  call    cs:__imp_KeWaitForSingleObject
0x14001562b  nop     dword ptr [rax+rax+00h]
0x140015630  mov     rax, gs:188h
0x140015639  mov     [rdi+18h], rax
0x14001563d  mov     rax, [rsi+10h]
0x140015641  test    rax, rax
0x140015644  jz      short loc_140015658
0x140015646  cmp     dword ptr [rax+14h], 6
0x14001564a  jz      short loc_140015658
0x14001564c  lock inc dword ptr [rsi+15ECh]
0x140015653  lea     ebx, [rbp+1]
0x140015656  jmp     short loc_14001565A
0x140015658  xor     ebx, ebx
0x14001565a  xor     r8d, r8d; Wait
0x14001565d  mov     [rdi+18h], rbp
0x140015661  mov     rcx, rdi; Event
0x140015664  lea     edx, [r8+1]; Increment
0x140015668  call    cs:__imp_KeSetEvent
0x14001566f  nop     dword ptr [rax+rax+00h]
0x140015674  test    ebx, ebx
0x140015676  jnz     short loc_1400156A8
0x140015678  mov     rcx, cs:WPP_GLOBAL_Control
0x14001567f  lea     rax, WPP_GLOBAL_Control
0x140015686  cmp     rcx, rax
0x140015689  jz      short loc_14001569E
0x14001568b  mov     rcx, [rcx+18h]
0x14001568f  lea     edx, [rbx+10h]
0x140015692  lea     r8, WPP_9d07a56bbaea364d4305f48ac15d89f0_Traceguids
0x140015699  call    WPP_SF_
0x14001569e  mov     edi, 0C000000Eh
0x1400156a3  jmp     loc_1400157E6
0x1400156a8  mov     rcx, [rsi+10h]
0x1400156ac  mov     edx, 1
0x1400156b1  mov     r12d, edx
0x1400156b4  mov     rax, [rcx+30h]
0x1400156b8  test    [rcx+28h], rax
0x1400156bc  jz      loc_1400157DA
0x1400156c2  mov     rbx, [r14+8]
0x1400156c6  test    rbx, rbx
0x1400156c9  jnz     short loc_1400156D2
0x1400156cb  mov     edi, 0C000000Dh
0x1400156d0  jmp     short loc_14001572A
0x1400156d2  test    byte ptr [rbx+0Ah], 5
0x1400156d6  jz      short loc_1400156DE
0x1400156d8  mov     r14, [rbx+18h]
0x1400156dc  jmp     short loc_140015704
0x1400156de  mov     r8d, edx; CacheType
0x1400156e1  mov     [rsp+68h+Priority], 40000010h; Priority
0x1400156e9  xor     edx, edx; AccessMode
0x1400156eb  mov     [rsp+68h+BugCheckOnFailure], ebp; BugCheckOnFailure
0x1400156ef  xor     r9d, r9d; RequestedAddress
0x1400156f2  mov     rcx, rbx; MemoryDescriptorList
0x1400156f5  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400156fc  nop     dword ptr [rax+rax+00h]
0x140015701  mov     r14, rax
0x140015704  test    r14, r14
0x140015707  jnz     short loc_140015710
0x140015709  mov     edi, 0C000009Ah
0x14001570e  jmp     short loc_14001572A
0x140015710  mov     eax, [rbx+28h]
0x140015713  cmp     eax, 8
0x140015716  jnb     short loc_14001571F
0x140015718  mov     edi, 0C0000023h
0x14001571d  jmp     short loc_14001572A
0x14001571f  test    r14b, 3
0x140015723  jz      short loc_140015739
0x140015725  mov     edi, 0C00002C5h
0x14001572a  xor     ebx, ebx
0x14001572c  xor     r14d, r14d
0x14001572f  xor     eax, eax
0x140015731  test    edi, edi
0x140015733  js      loc_1400157E6
0x140015739  cmp     [rbx], rbp
0x14001573c  jz      short loc_140015748
0x14001573e  mov     edi, 0C00000BBh
0x140015743  jmp     loc_1400157E6
0x140015748  test    r15d, r15d
0x14001574b  lea     r9, [rsp+68h+arg_0]
0x140015750  mov     r8d, 3
0x140015756  cmovnz  r9, [rsp+68h+arg_10]; unsigned __int8 *
0x14001575f  cmovnz  r8d, r15d; unsigned int
0x140015763  cmp     r8d, 3
0x140015767  jnz     short loc_1400157E1
0x140015769  mov     rcx, [rsi+10h]; struct _ADAPT *
0x14001576d  lea     ebx, [rax-8]
0x140015770  lea     rax, [rsp+68h+arg_18]
0x140015778  mov     qword ptr [rsp+68h+Priority], rax; struct DOT11_BYTE_ARRAY **
0x14001577d  mov     [rsp+68h+BugCheckOnFailure], ebx; unsigned int
0x140015781  call    ?NwfCallByteArray@@YAHPEAU_ADAPT@@KKPEAEKPEAPEAUDOT11_BYTE_ARRAY@@@Z; NwfCallByteArray(_ADAPT *,ulong,ulong,uchar *,ulong,DOT11_BYTE_ARRAY * *)
0x140015786  mov     rbp, [rsp+68h+arg_18]
0x14001578e  xor     edi, edi
0x140015790  mov     r15d, 80000005h
0x140015796  cmp     eax, r15d
0x140015799  cmovnz  edi, eax
0x14001579c  test    edi, edi
0x14001579e  jz      short loc_1400157AA
0x1400157a0  mov     eax, 0C0000001h
0x1400157a5  cmovns  edi, eax
0x1400157a8  jmp     short loc_1400157E6
0x1400157aa  mov     eax, [rbp+4]
0x1400157ad  lea     rdx, [rbp+0Ch]; Src
0x1400157b1  cmp     eax, ebx
0x1400157b3  lea     rcx, [r14+8]; void *
0x1400157b7  cmovnb  eax, ebx
0x1400157ba  mov     r8d, eax; Size
0x1400157bd  mov     ebx, eax
0x1400157bf  call    memmove
0x1400157c4  mov     [r14], ebx
0x1400157c7  lea     ecx, [rbx+8]
0x1400157ca  mov     eax, [rbp+8]
0x1400157cd  cmp     ebx, eax
0x1400157cf  mov     [r14+4], eax
0x1400157d3  sbb     edi, edi
0x1400157d5  and     edi, r15d
0x1400157d8  jmp     short loc_1400157E8
0x1400157da  mov     edi, 0C0232002h
0x1400157df  jmp     short loc_1400157E6
0x1400157e1  mov     edi, 0C000000Dh
0x1400157e6  xor     ecx, ecx
0x1400157e8  mov     [r13+0], ecx
0x1400157ec  test    rbp, rbp
0x1400157ef  jz      short loc_140015820
0x1400157f1  lea     rcx, [rbp-10h]; P
0x1400157f5  mov     rax, [rcx]
0x1400157f8  test    rax, rax
0x1400157fb  jz      short loc_140015811
0x1400157fd  mov     rdx, rcx; Entry
0x140015800  mov     rcx, rax; Lookaside
0x140015803  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001580a  nop     dword ptr [rax+rax+00h]
0x14001580f  jmp     short loc_140015820
0x140015811  mov     edx, [rcx+8]; Tag
0x140015814  call    cs:__imp_ExFreePoolWithTag
0x14001581b  nop     dword ptr [rax+rax+00h]
0x140015820  test    r12d, r12d
0x140015823  jz      short loc_14001587E
0x140015825  lea     rbx, [rsi+1F70h]
0x14001582c  mov     qword ptr [rsp+68h+BugCheckOnFailure], 0; Timeout
0x140015835  mov     rcx, rbx; Object
0x140015838  xor     r9d, r9d; Alertable
0x14001583b  xor     r8d, r8d; WaitMode
0x14001583e  xor     edx, edx; WaitReason
0x140015840  call    cs:__imp_KeWaitForSingleObject
0x140015847  nop     dword ptr [rax+rax+00h]
0x14001584c  mov     r8, gs:188h
0x140015855  mov     rcx, rbx; Event
0x140015858  mov     [rbx+18h], r8
0x14001585c  xor     r8d, r8d; Wait
0x14001585f  lock dec dword ptr [rsi+15ECh]
0x140015866  mov     qword ptr [rbx+18h], 0
0x14001586e  lea     edx, [r8+1]; Increment
0x140015872  call    cs:__imp_KeSetEvent
0x140015879  nop     dword ptr [rax+rax+00h]
0x14001587e  mov     rbx, [rsp+68h+arg_8]
0x140015883  mov     eax, edi
0x140015885  add     rsp, 30h
0x140015889  pop     r15
0x14001588b  pop     r14
0x14001588d  pop     r13
0x14001588f  pop     r12
0x140015891  pop     rdi
0x140015892  pop     rsi
0x140015893  pop     rbp
0x140015894  retn
```
