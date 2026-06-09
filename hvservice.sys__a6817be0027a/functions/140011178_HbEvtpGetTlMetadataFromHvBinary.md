# HbEvtpGetTlMetadataFromHvBinary

- ea: `0x140011178`
- end: `0x140011413`
- name: `HbEvtpGetTlMetadataFromHvBinary`
- size: `667`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140011760`

## callees

- `0x1400023b8`
- `0x1400023e8`
- `0x140002458`
- `0x1400024bc`
- `0x140002c00`
- `0x140002f00`
- `0x140011178`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14001138e`
- `ntoskrnl!ZwClose` at `0x14001138e`
- `ntoskrnl!ExAllocatePool2` at `0x1400113ca`
- `ntoskrnl!ExAllocatePool2` at `0x1400113ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011344`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011344`
- `ntoskrnl!ObfDereferenceObject` at `0x140011379`
- `ntoskrnl!ObfDereferenceObject` at `0x140011379`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x140011364`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x140011364`
- `ntoskrnl!ZwCreateSection` at `0x14001123b`
- `ntoskrnl!ZwCreateSection` at `0x14001123b`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x14001129b`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x14001129b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140011271`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140011271`

## pseudocode

```c
__int64 __fastcall HbEvtpGetTlMetadataFromHvBinary(__int64 a1)
{
  void *FileHandle; // rax
  NTSTATUS v3; // ebx
  unsigned __int64 v4; // rbx
  unsigned int v5; // r11d
  int v6; // r11d
  char *v8; // rbx
  void *Pool2; // rax
  __int64 v10; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v11; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v13; // [rsp+88h] [rbp-78h] BYREF
  __int128 v14; // [rsp+98h] [rbp-68h]
  __int128 v15; // [rsp+A8h] [rbp-58h]
  char v16; // [rsp+B8h] [rbp-48h]
  _QWORD v17[10]; // [rsp+C0h] [rbp-40h] BYREF
  ULONG_PTR ViewSize; // [rsp+120h] [rbp+20h] BYREF
  PVOID MappedBase; // [rsp+128h] [rbp+28h] BYREF
  PVOID Object; // [rsp+130h] [rbp+30h] BYREF
  void *SectionHandle; // [rsp+138h] [rbp+38h] BYREF

  v11 = 0;
  memset(v17, 0, 0x40u);
  v16 = 0;
  ViewSize = 0;
  Object = 0;
  SectionHandle = 0;
  MappedBase = 0;
  FileHandle = *(void **)(a1 + 192);
  v13 = 0;
  v14 = 0;
  v15 = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( FileHandle )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v3 = ZwCreateSection(&SectionHandle, 4u, &ObjectAttributes, 0, 2u, 0x8000000u, FileHandle);
    if ( v3 >= 0 )
    {
      v3 = ObReferenceObjectByHandle(SectionHandle, 4u, 0, 0, &Object, 0);
      if ( v3 >= 0 )
      {
        ViewSize = 0;
        v3 = MmMapViewInSystemSpace(Object, &MappedBase, &ViewSize);
        if ( v3 >= 0 )
        {
          v10 = 0;
          *(_OWORD *)&MaxDataSize = 0;
          if ( (unsigned __int8)ImageValidateAndProcess(MappedBase, ViewSize, &v10, &v11) )
          {
            ImageGetInfo(&v11, v17);
            v4 = v17[2];
            v5 = 0;
            if ( !v17[2] )
              goto LABEL_11;
            while ( 1 )
            {
              ImageGetSectionByIndex(&v11, v5, &v13);
              if ( (unsigned __int8)ImageCompareSectionNames(&v13) )
                break;
              v5 = v6 + 1;
              if ( v5 >= v4 )
                goto LABEL_11;
            }
            *((_QWORD *)&MaxDataSize + 1) = v14;
            v8 = (char *)MappedBase + DWORD2(v14);
            if ( v8 )
            {
              Pool2 = (void *)ExAllocatePool2(64, v14, 1967284808);
              *(_QWORD *)&MaxDataSize = Pool2;
              if ( Pool2 )
              {
                memmove(Pool2, v8, *((size_t *)&MaxDataSize + 1));
                v3 = 0;
                dword_1400094A8 = *(_DWORD *)(*((_QWORD *)&v11 + 1) + 8LL);
                goto LABEL_14;
              }
              v3 = -1073741670;
            }
            else
            {
LABEL_11:
              v3 = -1073741275;
            }
          }
          else
          {
            v3 = -1073741823;
          }
        }
      }
    }
  }
  else
  {
    v3 = -1073741672;
  }
  if ( *(_QWORD *)&MaxDataSize )
  {
    ExFreePoolWithTag(*(PVOID *)&MaxDataSize, 0x75426248u);
    *(_QWORD *)&MaxDataSize = 0;
  }
LABEL_14:
  if ( MappedBase )
    MmUnmapViewInSystemSpace(MappedBase);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( SectionHandle )
    ZwClose(SectionHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140011178  mov     [rsp-8+MappedBase], rdx
0x14001117d  push    rbp
0x14001117e  push    rbx
0x14001117f  lea     rbp, [rsp-8]
0x140011184  sub     rsp, 108h
0x14001118b  xor     edx, edx; Val
0x14001118d  mov     rbx, rcx
0x140011190  xorps   xmm0, xmm0
0x140011193  lea     rcx, [rbp+10h+var_50]; void *
0x140011197  movups  [rsp+110h+var_C8], xmm0
0x14001119c  lea     r8d, [rdx+40h]; Size
0x1400111a0  call    memset
0x1400111a5  xor     eax, eax
0x1400111a7  xorps   xmm0, xmm0
0x1400111aa  mov     [rbp+10h+var_58], al
0x1400111ad  mov     [rbp+10h+ViewSize], rax
0x1400111b1  mov     [rbp+10h+Object], rax
0x1400111b5  mov     [rbp+10h+SectionHandle], rax
0x1400111b9  mov     [rbp+10h+MappedBase], rax
0x1400111bd  mov     rax, [rbx+0C0h]
0x1400111c4  movups  xmmword ptr [rsp+110h+ObjectAttributes.ObjectName], xmm0
0x1400111c9  movups  [rbp+10h+var_88], xmm0
0x1400111cd  movups  [rbp+10h+var_78], xmm0
0x1400111d1  movups  [rbp+10h+var_68], xmm0
0x1400111d5  movups  xmmword ptr [rsp+110h+ObjectAttributes.Length], xmm0
0x1400111da  movups  xmmword ptr [rsp+110h+ObjectAttributes+1Ch], xmm0
0x1400111df  test    rax, rax
0x1400111e2  jnz     short loc_1400111EE
0x1400111e4  mov     ebx, 0C0000098h
0x1400111e9  jmp     loc_140011333
0x1400111ee  mov     [rsp+110h+FileHandle], rax; FileHandle
0x1400111f3  lea     r8, [rsp+110h+ObjectAttributes]; ObjectAttributes
0x1400111f8  xor     r9d, r9d; MaximumSize
0x1400111fb  mov     [rsp+110h+AllocationAttributes], 8000000h; AllocationAttributes
0x140011203  lea     rcx, [rbp+10h+SectionHandle]; SectionHandle
0x140011207  mov     [rsp+110h+ObjectAttributes.Length], 30h ; '0'
0x14001120f  mov     [rsp+110h+ObjectAttributes.RootDirectory], 0
0x140011218  mov     [rsp+110h+ObjectAttributes.Attributes], 200h
0x140011220  lea     edx, [r9+4]; DesiredAccess
0x140011224  mov     [rsp+110h+ObjectAttributes.ObjectName], 0
0x14001122d  movdqu  xmmword ptr [rsp+110h+ObjectAttributes.SecurityDescriptor], xmm0
0x140011233  mov     [rsp+110h+SectionPageProtection], 2; SectionPageProtection
0x14001123b  call    cs:__imp_ZwCreateSection
0x140011242  nop     dword ptr [rax+rax+00h]
0x140011247  mov     ebx, eax
0x140011249  test    eax, eax
0x14001124b  js      loc_140011333
0x140011251  mov     rcx, [rbp+10h+SectionHandle]; Handle
0x140011255  lea     rax, [rbp+10h+Object]
0x140011259  xor     r9d, r9d; AccessMode
0x14001125c  mov     qword ptr [rsp+110h+AllocationAttributes], 0; HandleInformation
0x140011265  xor     r8d, r8d; ObjectType
0x140011268  mov     qword ptr [rsp+110h+SectionPageProtection], rax; Object
0x14001126d  lea     edx, [r9+4]; DesiredAccess
0x140011271  call    cs:__imp_ObReferenceObjectByHandle
0x140011278  nop     dword ptr [rax+rax+00h]
0x14001127d  mov     ebx, eax
0x14001127f  test    eax, eax
0x140011281  js      loc_140011333
0x140011287  mov     rcx, [rbp+10h+Object]; Section
0x14001128b  lea     r8, [rbp+10h+ViewSize]; ViewSize
0x14001128f  lea     rdx, [rbp+10h+MappedBase]; MappedBase
0x140011293  mov     [rbp+10h+ViewSize], 0
0x14001129b  call    cs:__imp_MmMapViewInSystemSpace
0x1400112a2  nop     dword ptr [rax+rax+00h]
0x1400112a7  mov     ebx, eax
0x1400112a9  test    eax, eax
0x1400112ab  js      loc_140011333
0x1400112b1  mov     rdx, [rbp+10h+ViewSize]
0x1400112b5  lea     r9, [rsp+110h+var_C8]
0x1400112ba  mov     rcx, [rbp+10h+MappedBase]
0x1400112be  lea     r8, [rsp+110h+var_D0]
0x1400112c3  xorps   xmm0, xmm0
0x1400112c6  mov     [rsp+110h+var_D0], 0
0x1400112cf  movdqu  cs:MaxDataSize, xmm0
0x1400112d7  call    ImageValidateAndProcess
0x1400112dc  test    al, al
0x1400112de  jnz     short loc_1400112E7
0x1400112e0  mov     ebx, 0C0000001h
0x1400112e5  jmp     short loc_140011333
0x1400112e7  lea     rdx, [rbp+10h+var_50]
0x1400112eb  lea     rcx, [rsp+110h+var_C8]
0x1400112f0  call    ImageGetInfo
0x1400112f5  mov     rbx, [rbp+10h+var_40]
0x1400112f9  xor     r11d, r11d
0x1400112fc  test    rbx, rbx
0x1400112ff  jz      short loc_14001132E
0x140011301  mov     edx, r11d
0x140011304  lea     r8, [rbp+10h+var_88]
0x140011308  lea     rcx, [rsp+110h+var_C8]
0x14001130d  call    ImageGetSectionByIndex
0x140011312  lea     rcx, [rbp+10h+var_88]
0x140011316  call    ImageCompareSectionNames
0x14001131b  test    al, al
0x14001131d  jnz     loc_1400113A7
0x140011323  inc     r11d
0x140011326  mov     eax, r11d
0x140011329  cmp     rax, rbx
0x14001132c  jb      short loc_140011301
0x14001132e  mov     ebx, 0C0000225h
0x140011333  mov     rcx, qword ptr cs:MaxDataSize; P
0x14001133a  test    rcx, rcx
0x14001133d  jz      short loc_14001135B
0x14001133f  mov     edx, 75426248h; Tag
0x140011344  call    cs:__imp_ExFreePoolWithTag
0x14001134b  nop     dword ptr [rax+rax+00h]
0x140011350  mov     qword ptr cs:MaxDataSize, 0
0x14001135b  mov     rcx, [rbp+10h+MappedBase]; MappedBase
0x14001135f  test    rcx, rcx
0x140011362  jz      short loc_140011370
0x140011364  call    cs:__imp_MmUnmapViewInSystemSpace
0x14001136b  nop     dword ptr [rax+rax+00h]
0x140011370  mov     rcx, [rbp+10h+Object]; Object
0x140011374  test    rcx, rcx
0x140011377  jz      short loc_140011385
0x140011379  call    cs:__imp_ObfDereferenceObject
0x140011380  nop     dword ptr [rax+rax+00h]
0x140011385  mov     rcx, [rbp+10h+SectionHandle]; Handle
0x140011389  test    rcx, rcx
0x14001138c  jz      short loc_14001139A
0x14001138e  call    cs:__imp_ZwClose
0x140011395  nop     dword ptr [rax+rax+00h]
0x14001139a  mov     eax, ebx
0x14001139c  add     rsp, 108h
0x1400113a3  pop     rbx
0x1400113a4  pop     rbp
0x1400113a5  retn
0x1400113a7  mov     ebx, dword ptr [rbp+10h+var_78+8]
0x1400113aa  mov     rdx, qword ptr [rbp+10h+var_78]
0x1400113ae  mov     qword ptr cs:MaxDataSize+8, rdx
0x1400113b5  add     rbx, [rbp+10h+MappedBase]
0x1400113b9  jz      loc_14001132E
0x1400113bf  mov     ecx, 40h ; '@'
0x1400113c4  mov     r8d, 75426248h
0x1400113ca  call    cs:__imp_ExAllocatePool2
0x1400113d1  nop     dword ptr [rax+rax+00h]
0x1400113d6  mov     qword ptr cs:MaxDataSize, rax
0x1400113dd  test    rax, rax
0x1400113e0  jnz     short loc_1400113EC
0x1400113e2  mov     ebx, 0C000009Ah
0x1400113e7  jmp     loc_140011333
0x1400113ec  mov     r8, qword ptr cs:MaxDataSize+8; Size
0x1400113f3  mov     rdx, rbx; Src
0x1400113f6  mov     rcx, rax; void *
0x1400113f9  call    memmove
0x1400113fe  mov     rax, qword ptr [rsp+110h+var_C8+8]
0x140011403  xor     ebx, ebx
0x140011405  mov     ecx, [rax+8]
0x140011408  mov     cs:dword_1400094A8, ecx
0x14001140e  jmp     loc_14001135B
```
