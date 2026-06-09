# IoctlQueryBSSIdList(_IRP *,ulong,void *,ulong *)

- ea: `0x14001559c`
- end: `0x140015886`
- name: `?IoctlQueryBSSIdList@@YAJPEAU_IRP@@KPEAXPEAK@Z`
- size: `746`
- prototype: `int(struct _IRP *, unsigned int, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000cb00`

## callees

- `0x14000d21c`
- `0x14001559c`
- `0x14001588c`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140015614`
- `ntoskrnl!KeWaitForSingleObject` at `0x140015830`
- `ntoskrnl!KeWaitForSingleObject` at `0x140015614`
- `ntoskrnl!KeWaitForSingleObject` at `0x140015830`
- `ntoskrnl!KeSetEvent` at `0x140015658`
- `ntoskrnl!KeSetEvent` at `0x140015862`
- `ntoskrnl!KeSetEvent` at `0x140015658`
- `ntoskrnl!KeSetEvent` at `0x140015862`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400157f3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400157f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015804`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015804`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400156e5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400156e5`

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
0x14001559c  mov     r11, rsp
0x14001559f  mov     [r11+10h], rbx
0x1400155a3  mov     [r11+18h], r8
0x1400155a7  push    rbp
0x1400155a8  push    rsi
0x1400155a9  push    rdi
0x1400155aa  push    r12
0x1400155ac  push    r13
0x1400155ae  push    r14
0x1400155b0  push    r15
0x1400155b2  sub     rsp, 30h
0x1400155b6  mov     rax, [rcx+0B8h]
0x1400155bd  xor     ebp, ebp
0x1400155bf  xor     r12d, r12d
0x1400155c2  mov     [r11+20h], rbp
0x1400155c6  mov     r13, r9
0x1400155c9  mov     r15d, edx
0x1400155cc  mov     r14, rcx
0x1400155cf  mov     r10, [rax+30h]
0x1400155d3  xor     eax, eax
0x1400155d5  mov     [rsp+68h+arg_0], ax
0x1400155da  mov     [rsp+68h+arg_2], al
0x1400155de  mov     [r9], eax
0x1400155e1  mov     rsi, [r10+18h]
0x1400155e5  test    rsi, rsi
0x1400155e8  jz      loc_1400157D1
0x1400155ee  mov     rsi, [rsi+10h]
0x1400155f2  cmp     [rsi+15E8h], eax
0x1400155f8  jnz     loc_14001568E
0x1400155fe  lea     rdi, [rsi+1F70h]
0x140015605  mov     [r11-48h], rax
0x140015609  mov     rcx, rdi; Object
0x14001560c  xor     r9d, r9d; Alertable
0x14001560f  xor     r8d, r8d; WaitMode
0x140015612  xor     edx, edx; WaitReason
0x140015614  call    cs:__imp_KeWaitForSingleObject
0x14001561b  nop     dword ptr [rax+rax+00h]
0x140015620  mov     rax, gs:188h
0x140015629  mov     [rdi+18h], rax
0x14001562d  mov     rax, [rsi+10h]
0x140015631  test    rax, rax
0x140015634  jz      short loc_140015648
0x140015636  cmp     dword ptr [rax+14h], 6
0x14001563a  jz      short loc_140015648
0x14001563c  lock inc dword ptr [rsi+15ECh]
0x140015643  lea     ebx, [rbp+1]
0x140015646  jmp     short loc_14001564A
0x140015648  xor     ebx, ebx
0x14001564a  xor     r8d, r8d; Wait
0x14001564d  mov     [rdi+18h], rbp
0x140015651  mov     rcx, rdi; Event
0x140015654  lea     edx, [r8+1]; Increment
0x140015658  call    cs:__imp_KeSetEvent
0x14001565f  nop     dword ptr [rax+rax+00h]
0x140015664  test    ebx, ebx
0x140015666  jnz     short loc_140015698
0x140015668  mov     rcx, cs:WPP_GLOBAL_Control
0x14001566f  lea     rax, WPP_GLOBAL_Control
0x140015676  cmp     rcx, rax
0x140015679  jz      short loc_14001568E
0x14001567b  mov     rcx, [rcx+18h]
0x14001567f  lea     edx, [rbx+10h]
0x140015682  lea     r8, WPP_9d07a56bbaea364d4305f48ac15d89f0_Traceguids
0x140015689  call    WPP_SF_
0x14001568e  mov     edi, 0C000000Eh
0x140015693  jmp     loc_1400157D6
0x140015698  mov     rcx, [rsi+10h]
0x14001569c  mov     edx, 1
0x1400156a1  mov     r12d, edx
0x1400156a4  mov     rax, [rcx+30h]
0x1400156a8  test    [rcx+28h], rax
0x1400156ac  jz      loc_1400157CA
0x1400156b2  mov     rbx, [r14+8]
0x1400156b6  test    rbx, rbx
0x1400156b9  jnz     short loc_1400156C2
0x1400156bb  mov     edi, 0C000000Dh
0x1400156c0  jmp     short loc_14001571A
0x1400156c2  test    byte ptr [rbx+0Ah], 5
0x1400156c6  jz      short loc_1400156CE
0x1400156c8  mov     r14, [rbx+18h]
0x1400156cc  jmp     short loc_1400156F4
0x1400156ce  mov     r8d, edx; CacheType
0x1400156d1  mov     [rsp+68h+Priority], 40000010h; Priority
0x1400156d9  xor     edx, edx; AccessMode
0x1400156db  mov     [rsp+68h+BugCheckOnFailure], ebp; BugCheckOnFailure
0x1400156df  xor     r9d, r9d; RequestedAddress
0x1400156e2  mov     rcx, rbx; MemoryDescriptorList
0x1400156e5  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400156ec  nop     dword ptr [rax+rax+00h]
0x1400156f1  mov     r14, rax
0x1400156f4  test    r14, r14
0x1400156f7  jnz     short loc_140015700
0x1400156f9  mov     edi, 0C000009Ah
0x1400156fe  jmp     short loc_14001571A
0x140015700  mov     eax, [rbx+28h]
0x140015703  cmp     eax, 8
0x140015706  jnb     short loc_14001570F
0x140015708  mov     edi, 0C0000023h
0x14001570d  jmp     short loc_14001571A
0x14001570f  test    r14b, 3
0x140015713  jz      short loc_140015729
0x140015715  mov     edi, 0C00002C5h
0x14001571a  xor     ebx, ebx
0x14001571c  xor     r14d, r14d
0x14001571f  xor     eax, eax
0x140015721  test    edi, edi
0x140015723  js      loc_1400157D6
0x140015729  cmp     [rbx], rbp
0x14001572c  jz      short loc_140015738
0x14001572e  mov     edi, 0C00000BBh
0x140015733  jmp     loc_1400157D6
0x140015738  test    r15d, r15d
0x14001573b  lea     r9, [rsp+68h+arg_0]
0x140015740  mov     r8d, 3
0x140015746  cmovnz  r9, [rsp+68h+arg_10]; unsigned __int8 *
0x14001574f  cmovnz  r8d, r15d; unsigned int
0x140015753  cmp     r8d, 3
0x140015757  jnz     short loc_1400157D1
0x140015759  mov     rcx, [rsi+10h]; struct _ADAPT *
0x14001575d  lea     ebx, [rax-8]
0x140015760  lea     rax, [rsp+68h+arg_18]
0x140015768  mov     qword ptr [rsp+68h+Priority], rax; struct DOT11_BYTE_ARRAY **
0x14001576d  mov     [rsp+68h+BugCheckOnFailure], ebx; unsigned int
0x140015771  call    ?NwfCallByteArray@@YAHPEAU_ADAPT@@KKPEAEKPEAPEAUDOT11_BYTE_ARRAY@@@Z; NwfCallByteArray(_ADAPT *,ulong,ulong,uchar *,ulong,DOT11_BYTE_ARRAY * *)
0x140015776  mov     rbp, [rsp+68h+arg_18]
0x14001577e  xor     edi, edi
0x140015780  mov     r15d, 80000005h
0x140015786  cmp     eax, r15d
0x140015789  cmovnz  edi, eax
0x14001578c  test    edi, edi
0x14001578e  jz      short loc_14001579A
0x140015790  mov     eax, 0C0000001h
0x140015795  cmovns  edi, eax
0x140015798  jmp     short loc_1400157D6
0x14001579a  mov     eax, [rbp+4]
0x14001579d  lea     rdx, [rbp+0Ch]; Src
0x1400157a1  cmp     eax, ebx
0x1400157a3  lea     rcx, [r14+8]; void *
0x1400157a7  cmovnb  eax, ebx
0x1400157aa  mov     r8d, eax; Size
0x1400157ad  mov     ebx, eax
0x1400157af  call    memmove
0x1400157b4  mov     [r14], ebx
0x1400157b7  lea     ecx, [rbx+8]
0x1400157ba  mov     eax, [rbp+8]
0x1400157bd  cmp     ebx, eax
0x1400157bf  mov     [r14+4], eax
0x1400157c3  sbb     edi, edi
0x1400157c5  and     edi, r15d
0x1400157c8  jmp     short loc_1400157D8
0x1400157ca  mov     edi, 0C0232002h
0x1400157cf  jmp     short loc_1400157D6
0x1400157d1  mov     edi, 0C000000Dh
0x1400157d6  xor     ecx, ecx
0x1400157d8  mov     [r13+0], ecx
0x1400157dc  test    rbp, rbp
0x1400157df  jz      short loc_140015810
0x1400157e1  lea     rcx, [rbp-10h]; P
0x1400157e5  mov     rax, [rcx]
0x1400157e8  test    rax, rax
0x1400157eb  jz      short loc_140015801
0x1400157ed  mov     rdx, rcx; Entry
0x1400157f0  mov     rcx, rax; Lookaside
0x1400157f3  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400157fa  nop     dword ptr [rax+rax+00h]
0x1400157ff  jmp     short loc_140015810
0x140015801  mov     edx, [rcx+8]; Tag
0x140015804  call    cs:__imp_ExFreePoolWithTag
0x14001580b  nop     dword ptr [rax+rax+00h]
0x140015810  test    r12d, r12d
0x140015813  jz      short loc_14001586E
0x140015815  lea     rbx, [rsi+1F70h]
0x14001581c  mov     qword ptr [rsp+68h+BugCheckOnFailure], 0; Timeout
0x140015825  mov     rcx, rbx; Object
0x140015828  xor     r9d, r9d; Alertable
0x14001582b  xor     r8d, r8d; WaitMode
0x14001582e  xor     edx, edx; WaitReason
0x140015830  call    cs:__imp_KeWaitForSingleObject
0x140015837  nop     dword ptr [rax+rax+00h]
0x14001583c  mov     r8, gs:188h
0x140015845  mov     rcx, rbx; Event
0x140015848  mov     [rbx+18h], r8
0x14001584c  xor     r8d, r8d; Wait
0x14001584f  lock dec dword ptr [rsi+15ECh]
0x140015856  mov     qword ptr [rbx+18h], 0
0x14001585e  lea     edx, [r8+1]; Increment
0x140015862  call    cs:__imp_KeSetEvent
0x140015869  nop     dword ptr [rax+rax+00h]
0x14001586e  mov     rbx, [rsp+68h+arg_8]
0x140015873  mov     eax, edi
0x140015875  add     rsp, 30h
0x140015879  pop     r15
0x14001587b  pop     r14
0x14001587d  pop     r13
0x14001587f  pop     r12
0x140015881  pop     rdi
0x140015882  pop     rsi
0x140015883  pop     rbp
0x140015884  retn
```
