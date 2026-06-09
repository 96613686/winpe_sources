# ClasspEjectionControl

- ea: `0x14005e53c`
- end: `0x14005eb27`
- name: `ClasspEjectionControl`
- size: `1515`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140019de0`
- `0x14005fe50`

## callees

- `0x14000de10`
- `0x14000f3e0`
- `0x140016820`
- `0x140017fa0`
- `0x14001fbf4`
- `0x14001feac`
- `0x1400225b4`
- `0x140022748`
- `0x14003e940`
- `0x14005e53c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e57c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005e57c`
- `ntoskrnl!KeSetEvent` at `0x14005e9b4`
- `ntoskrnl!KeSetEvent` at `0x140061613`
- `ntoskrnl!KeSetEvent` at `0x14005e9b4`
- `ntoskrnl!KeSetEvent` at `0x140061613`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005e59d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005e59d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e9c0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006161f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005e9c0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006161f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005e673`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005e673`

## pseudocode

```c
__int64 __fastcall ClasspEjectionControl(__int64 a1, __int64 a2, int a3, char a4)
{
  __int64 v4; // r14
  __int64 v7; // rbx
  __int64 DictionaryEntry; // r13
  struct _SCSI_REQUEST_BLOCK *v9; // rsi
  char v10; // r12
  int v11; // edi
  char v12; // r15
  int v13; // eax
  unsigned __int8 *Cdb; // r8
  char v15; // r9
  __int64 j; // r11
  __int64 v17; // rcx
  unsigned __int64 v18; // r10
  __int64 v19; // rdx
  int v20; // ecx
  unsigned __int64 v21; // rcx
  unsigned int v22; // eax
  int v23; // ecx
  void **p_SenseInfoBuffer; // r8
  char v25; // r10
  __int64 i; // r8
  __int64 v27; // rcx
  unsigned __int64 DataTransferLength; // r9
  __int64 v29; // rdx
  int v30; // ecx
  unsigned __int64 v31; // rcx
  int v32; // ecx
  int v33; // eax
  int v35; // r14d
  int v36; // r14d

  v4 = a3;
  v7 = *(_QWORD *)(a1 + 64);
  DictionaryEntry = 0;
  v9 = 0;
  v10 = 0;
  KeEnterCriticalRegion();
  KeWaitForSingleObject((PVOID)(v7 + 616), UserRequest, 0, 0, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_s(
      WPP_GLOBAL_Control->AttachedDevice,
      26,
      WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids,
      LockTypeStrings[v4]);
  }
  if ( (_DWORD)v4 == 1 )
  {
    if ( *(_QWORD *)(*(_QWORD *)(a2 + 184) + 48LL) )
      DictionaryEntry = GetDictionaryEntry(v7 + 416);
    if ( !DictionaryEntry )
    {
      v11 = -1073741811;
LABEL_7:
      v12 = a4;
      goto LABEL_83;
    }
  }
  if ( !a4 )
  {
    if ( (_DWORD)v4 )
    {
      if ( (_DWORD)v4 == 1 )
      {
        v33 = *(_DWORD *)(DictionaryEntry + 16);
        if ( !v33 )
        {
          v11 = -1073741436;
          goto LABEL_7;
        }
        *(_DWORD *)(DictionaryEntry + 16) = v33 - 1;
        --*(_DWORD *)(v7 + 604);
      }
      else
      {
        if ( (_DWORD)v4 != 2 )
          goto LABEL_13;
        --*(_DWORD *)(v7 + 608);
      }
    }
    else
    {
      v13 = *(_DWORD *)(v7 + 600);
      if ( !v13 )
      {
LABEL_13:
        if ( *(_DWORD *)(v7 + 604) || *(_DWORD *)(v7 + 608) || *(_DWORD *)(v7 + 600) )
        {
          v11 = 0;
          goto LABEL_7;
        }
        goto LABEL_19;
      }
      *(_DWORD *)(v7 + 600) = v13 - 1;
    }
    v10 = 1;
    goto LABEL_13;
  }
  if ( (_DWORD)v4 )
  {
    if ( (_DWORD)v4 == 1 )
    {
      ++*(_DWORD *)(DictionaryEntry + 16);
      ++*(_DWORD *)(v7 + 604);
    }
    else
    {
      if ( (_DWORD)v4 != 2 )
        goto LABEL_19;
      ++*(_DWORD *)(v7 + 608);
    }
  }
  else
  {
    ++*(_DWORD *)(v7 + 600);
  }
  v10 = 1;
LABEL_19:
  v11 = 0;
  if ( (*(_DWORD *)(a1 + 52) & 1) == 0 )
    goto LABEL_7;
  v9 = (struct _SCSI_REQUEST_BLOCK *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v7 + 256));
  if ( !v9 )
  {
    v11 = -1073741670;
    goto LABEL_7;
  }
  if ( *(_BYTE *)(*(_QWORD *)(v7 + 528) + 30LL) == 1 )
  {
    v11 = InitializeStorageRequestBlock((__int64)v9);
    if ( v11 < 0 )
      goto LABEL_7;
  }
  else
  {
    memset(v9, 0, sizeof(struct _SCSI_REQUEST_BLOCK));
  }
  if ( v9->Function != 40 )
  {
    v9->CdbLength = 6;
    goto LABEL_25;
  }
  v25 = 0;
  if ( !v9->TimeOutValue )
  {
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= LODWORD(v9->SrbExtension) )
        goto LABEL_25;
      v27 = *((unsigned int *)&v9[1].SenseInfoBuffer + i);
      if ( (unsigned int)v27 >= 0x80 )
      {
        DataTransferLength = v9->DataTransferLength;
        if ( (unsigned int)v27 < (unsigned int)DataTransferLength )
          break;
      }
LABEL_67:
      ;
    }
    v29 = (unsigned int)v27;
    v30 = *(_DWORD *)((char *)&v9->Length + v27) - 64;
    if ( v30 )
    {
      v32 = v30 - 1;
      if ( v32 )
      {
        if ( v32 == 1 && v29 + 40 <= DataTransferLength )
          goto LABEL_25;
        goto LABEL_62;
      }
      v31 = v29 + 56;
    }
    else
    {
      v31 = v29 + 40;
    }
    if ( v31 <= DataTransferLength )
    {
      *(&v9->CdbLength + v29) = 6;
      v25 = 1;
    }
LABEL_62:
    if ( v25 )
      goto LABEL_25;
    goto LABEL_67;
  }
LABEL_25:
  if ( v9->Function == 40 )
  {
    Cdb = 0;
    v15 = 0;
    if ( !v9->TimeOutValue )
    {
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        if ( (unsigned int)j >= LODWORD(v9->SrbExtension) )
          goto LABEL_35;
        v17 = *((unsigned int *)&v9[1].SenseInfoBuffer + j);
        if ( (unsigned int)v17 >= 0x80 )
        {
          v18 = v9->DataTransferLength;
          if ( (unsigned int)v17 < (unsigned int)v18 )
            break;
        }
LABEL_52:
        ;
      }
      v19 = (unsigned int)v17;
      v20 = *(_DWORD *)((char *)&v9->Length + v17) - 64;
      if ( v20 )
      {
        v23 = v20 - 1;
        if ( v23 )
        {
          if ( v23 == 1 && v19 + 40 <= v18 )
          {
            v15 = 1;
            if ( *(unsigned int *)((char *)&v9->SrbFlags + v19) )
            {
              p_SenseInfoBuffer = &v9->SenseInfoBuffer;
LABEL_66:
              Cdb = (unsigned __int8 *)p_SenseInfoBuffer + v19;
            }
          }
LABEL_34:
          if ( v15 )
            goto LABEL_35;
          goto LABEL_52;
        }
        v21 = v19 + 56;
      }
      else
      {
        v21 = v19 + 40;
      }
      if ( v21 <= v18 )
      {
        v15 = 1;
        if ( *(&v9->CdbLength + v19) )
        {
          p_SenseInfoBuffer = &v9->DataBuffer;
          goto LABEL_66;
        }
      }
      goto LABEL_34;
    }
  }
  else
  {
    Cdb = v9->Cdb;
  }
LABEL_35:
  *Cdb = 30;
  v12 = a4;
  Cdb[4] ^= (a4 ^ Cdb[4]) & 1;
  v22 = *(_DWORD *)(v7 + 584);
  if ( v9->Function == 40 )
    LODWORD(v9->NextSrb) = v22;
  else
    v9->TimeOutValue = v22;
  v11 = ClassSendSrbSynchronous(*(PDEVICE_OBJECT *)(v7 + 8), v9, 0, 0, 0);
LABEL_83:
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids,
        (unsigned int)v11);
    }
    if ( v10 )
    {
      if ( v12 )
      {
        if ( (_DWORD)v4 )
        {
          v35 = v4 - 1;
          if ( v35 )
          {
            if ( v35 == 1 )
              --*(_DWORD *)(v7 + 608);
          }
          else
          {
            --*(_DWORD *)(DictionaryEntry + 16);
            --*(_DWORD *)(v7 + 604);
          }
        }
        else
        {
          --*(_DWORD *)(v7 + 600);
        }
      }
      else if ( (_DWORD)v4 )
      {
        v36 = v4 - 1;
        if ( v36 )
        {
          if ( v36 == 1 )
            ++*(_DWORD *)(v7 + 608);
        }
        else
        {
          ++*(_DWORD *)(DictionaryEntry + 16);
          ++*(_DWORD *)(v7 + 604);
        }
      }
      else
      {
        ++*(_DWORD *)(v7 + 600);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_DDD(
      WPP_GLOBAL_Control->AttachedDevice,
      29,
      WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids,
      *(unsigned int *)(v7 + 608),
      *(_DWORD *)(v7 + 604),
      *(_DWORD *)(v7 + 600));
  }
  KeSetEvent((PRKEVENT)(v7 + 616), 0, 0);
  KeLeaveCriticalRegion();
  if ( v9 )
    ClassFreeOrReuseSrb(v7, v9);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14005e53c  mov     rax, rsp
0x14005e53f  mov     [rax+20h], r9b
0x14005e543  mov     [rax+18h], r8d
0x14005e547  push    rbx
0x14005e548  push    rsi
0x14005e549  push    rdi
0x14005e54a  push    r12
0x14005e54c  push    r13
0x14005e54e  push    r14
0x14005e550  push    r15
0x14005e552  sub     rsp, 60h
0x14005e556  movsxd  r14, r8d
0x14005e559  mov     rdi, rdx
0x14005e55c  mov     r15, rcx
0x14005e55f  mov     rbx, [rcx+40h]
0x14005e563  mov     [rsp+98h+var_60], rbx
0x14005e568  xor     r13d, r13d
0x14005e56b  mov     [rax-48h], r13
0x14005e56f  xor     esi, esi
0x14005e571  mov     [rax-40h], rsi
0x14005e575  xor     r12b, r12b
0x14005e578  mov     [rax-68h], r12b
0x14005e57c  call    cs:__imp_KeEnterCriticalRegion
0x14005e583  nop     dword ptr [rax+rax+00h]
0x14005e588  lea     rcx, [rbx+268h]; Object
0x14005e58f  mov     [rsp+98h+Timeout], rsi; Timeout
0x14005e594  xor     r9d, r9d; Alertable
0x14005e597  xor     r8d, r8d; WaitMode
0x14005e59a  lea     edx, [rsi+6]; WaitReason
0x14005e59d  call    cs:__imp_KeWaitForSingleObject
0x14005e5a4  nop     dword ptr [rax+rax+00h]
0x14005e5a9  mov     [rsp+98h+var_64], eax
0x14005e5ad  lea     rax, WPP_GLOBAL_Control
0x14005e5b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e5bb  cmp     rcx, rax
0x14005e5be  jnz     loc_14005E9E8
0x14005e5c4  cmp     r14d, 1
0x14005e5c8  jnz     short loc_14005E5F9
0x14005e5ca  mov     rax, [rdi+0B8h]
0x14005e5d1  mov     rdx, [rax+30h]
0x14005e5d5  test    rdx, rdx
0x14005e5d8  jnz     loc_14005E90A
0x14005e5de  test    r13, r13
0x14005e5e1  jnz     short loc_14005E5F9
0x14005e5e3  mov     edi, 0C000000Dh
0x14005e5e8  mov     [rsp+98h+var_64], edi
0x14005e5ec  mov     r15b, [rsp+98h+arg_18]
0x14005e5f4  jmp     loc_14005E979
0x14005e5f9  mov     ecx, r14d
0x14005e5fc  cmp     [rsp+98h+arg_18], 0
0x14005e604  jnz     short loc_14005E643
0x14005e606  test    r14d, r14d
0x14005e609  jnz     loc_14005E93D
0x14005e60f  mov     eax, [rbx+258h]
0x14005e615  test    eax, eax
0x14005e617  jz      short loc_14005E629
0x14005e619  dec     eax
0x14005e61b  mov     [rbx+258h], eax
0x14005e621  mov     r12b, 1
0x14005e624  mov     [rsp+98h+var_68], r12b
0x14005e629  cmp     dword ptr [rbx+25Ch], 0
0x14005e630  jnz     short loc_14005E63F
0x14005e632  cmp     dword ptr [rbx+260h], 0
0x14005e639  jz      loc_14005E793
0x14005e63f  xor     edi, edi
0x14005e641  jmp     short loc_14005E5E8
0x14005e643  test    r14d, r14d
0x14005e646  jz      loc_14005E7A5
0x14005e64c  sub     ecx, 1
0x14005e64f  jz      loc_14005E92E
0x14005e655  cmp     ecx, 1
0x14005e658  jz      loc_14005E923
0x14005e65e  xor     edi, edi
0x14005e660  mov     [rsp+98h+var_64], edi
0x14005e664  mov     eax, [r15+34h]
0x14005e668  test    al, 1
0x14005e66a  jz      short loc_14005E5EC
0x14005e66c  lea     rcx, [rbx+100h]; Lookaside
0x14005e673  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14005e67a  nop     dword ptr [rax+rax+00h]
0x14005e67f  mov     rsi, rax
0x14005e682  mov     [rsp+98h+var_40], rax
0x14005e687  test    rax, rax
0x14005e68a  jz      loc_14005E7EF
0x14005e690  mov     rax, [rbx+210h]
0x14005e697  lea     r15d, [rdi+1]
0x14005e69b  mov     rcx, rsi; void *
0x14005e69e  cmp     [rax+1Eh], r15b
0x14005e6a2  jz      loc_14005E7B8
0x14005e6a8  xor     edx, edx; Val
0x14005e6aa  lea     r8d, [rdi+58h]; Size
0x14005e6ae  call    memset
0x14005e6b3  mov     [rsp+98h+arg_0], 6
0x14005e6bb  cmp     byte ptr [rsi+2], 28h ; '('
0x14005e6bf  jz      loc_14005E843
0x14005e6c5  mov     byte ptr [rsi+0Ah], 6
0x14005e6c9  cmp     byte ptr [rsi+2], 28h ; '('
0x14005e6cd  jnz     loc_14005E7E6
0x14005e6d3  xor     r8d, r8d
0x14005e6d6  mov     [rsp+98h+var_50], r8
0x14005e6db  mov     [rsp+98h+var_54], r8d
0x14005e6e0  xor     r9b, r9b
0x14005e6e3  mov     [rsp+98h+var_66], r9b
0x14005e6e8  cmp     [rsi+14h], r8d
0x14005e6ec  jnz     short loc_14005E740
0x14005e6ee  xor     r11d, r11d
0x14005e6f1  xor     edi, edi
0x14005e6f3  mov     [rsp+98h+var_54], r11d
0x14005e6f8  cmp     r11d, [rsi+38h]
0x14005e6fc  jnb     short loc_14005E740
0x14005e6fe  mov     ecx, [rsi+r11*4+78h]
0x14005e703  cmp     ecx, 80h
0x14005e709  jb      loc_14005E83B
0x14005e70f  mov     r10d, [rsi+10h]
0x14005e713  cmp     ecx, r10d
0x14005e716  jnb     loc_14005E83B
0x14005e71c  mov     edx, ecx
0x14005e71e  mov     ecx, [rcx+rsi]
0x14005e721  sub     ecx, 40h ; '@'
0x14005e724  jnz     loc_14005E801
0x14005e72a  lea     rcx, [rdx+28h]
0x14005e72e  cmp     rcx, r10
0x14005e731  jbe     loc_14005E8B0
0x14005e737  test    r9b, r9b
0x14005e73a  jz      loc_14005E905
0x14005e740  mov     byte ptr [r8], 1Eh
0x14005e744  mov     al, [r8+4]
0x14005e748  mov     cl, al
0x14005e74a  mov     r15b, [rsp+98h+arg_18]
0x14005e752  xor     cl, r15b
0x14005e755  and     cl, 1
0x14005e758  xor     cl, al
0x14005e75a  mov     [r8+4], cl
0x14005e75e  mov     eax, [rbx+248h]
0x14005e764  cmp     byte ptr [rsi+2], 28h ; '('
0x14005e768  jnz     loc_14005E7F9
0x14005e76e  mov     [rsi+28h], eax
0x14005e771  mov     byte ptr [rsp+98h+Timeout], 0; WriteToDevice
0x14005e776  xor     r9d, r9d; BufferLength
0x14005e779  xor     r8d, r8d; BufferAddress
0x14005e77c  mov     rdx, rsi; Srb
0x14005e77f  mov     rcx, [rbx+8]; DeviceObject
0x14005e783  call    ClassSendSrbSynchronous
0x14005e788  mov     edi, eax
0x14005e78a  mov     [rsp+98h+var_64], eax
0x14005e78e  jmp     loc_14005E979
0x14005e793  cmp     dword ptr [rbx+258h], 0
0x14005e79a  jz      loc_14005E65E
0x14005e7a0  jmp     loc_14005E63F
0x14005e7a5  inc     dword ptr [rbx+258h]
0x14005e7ab  mov     r12b, 1
0x14005e7ae  mov     [rsp+98h+var_68], r12b
0x14005e7b3  jmp     loc_14005E65E
0x14005e7b8  xor     eax, eax
0x14005e7ba  mov     dword ptr [rsp+98h+Timeout], 40h ; '@'
0x14005e7c2  mov     r9d, r15d
0x14005e7c5  mov     r8d, 0B8h
0x14005e7cb  movzx   edx, ax
0x14005e7ce  call    InitializeStorageRequestBlock
0x14005e7d3  mov     edi, eax
0x14005e7d5  mov     [rsp+98h+var_64], eax
0x14005e7d9  test    eax, eax
0x14005e7db  js      loc_14005E5EC
0x14005e7e1  jmp     loc_14005E6B3
0x14005e7e6  lea     r8, [rsi+48h]
0x14005e7ea  jmp     loc_14005E740
0x14005e7ef  mov     edi, 0C000009Ah
0x14005e7f4  jmp     loc_14005E5E8
0x14005e7f9  mov     [rsi+14h], eax
0x14005e7fc  jmp     loc_14005E771
0x14005e801  sub     ecx, r15d
0x14005e804  jz      loc_14005E8FC
0x14005e80a  cmp     ecx, r15d
0x14005e80d  jnz     loc_14005E737
0x14005e813  lea     rcx, [rdx+28h]
0x14005e817  cmp     rcx, r10
0x14005e81a  ja      loc_14005E737
0x14005e820  mov     r9b, r15b
0x14005e823  mov     [rsp+98h+var_66], r15b
0x14005e828  cmp     [rdx+rsi+0Ch], edi
0x14005e82c  jbe     loc_14005E737
0x14005e832  lea     r8, [rsi+20h]
0x14005e836  jmp     loc_14005E8C7
0x14005e83b  add     r11d, r15d
0x14005e83e  jmp     loc_14005E6F3
0x14005e843  mov     [rsp+98h+var_58], 0
0x14005e84b  xor     r10b, r10b
0x14005e84e  mov     [rsp+98h+var_67], r10b
0x14005e853  cmp     dword ptr [rsi+14h], 0
0x14005e857  jnz     loc_14005E6C9
0x14005e85d  xor     r8d, r8d
0x14005e860  mov     [rsp+98h+var_58], r8d
0x14005e865  cmp     r8d, [rsi+38h]
0x14005e869  jnb     loc_14005E6C9
0x14005e86f  mov     ecx, [rsi+r8*4+78h]
0x14005e874  cmp     ecx, 80h
0x14005e87a  jb      short loc_14005E8D4
0x14005e87c  mov     r9d, [rsi+10h]
0x14005e880  cmp     ecx, r9d
0x14005e883  jnb     short loc_14005E8D4
0x14005e885  mov     edx, ecx
0x14005e887  mov     ecx, [rcx+rsi]
0x14005e88a  sub     ecx, 40h ; '@'
0x14005e88d  jnz     short loc_14005E8D9
0x14005e88f  lea     rcx, [rdx+28h]
0x14005e893  cmp     rcx, r9
0x14005e896  ja      short loc_14005E8A5
0x14005e898  mov     byte ptr [rdx+rsi+0Ah], 6
0x14005e89d  mov     [rsp+98h+var_67], r15b
0x14005e8a2  mov     r10b, r15b
0x14005e8a5  test    r10b, r10b
0x14005e8a8  jnz     loc_14005E6C9
0x14005e8ae  jmp     short loc_14005E8D4
0x14005e8b0  cmp     [rdx+rsi+0Ah], dil
0x14005e8b5  mov     [rsp+98h+var_66], r15b
0x14005e8ba  mov     r9b, r15b
0x14005e8bd  jbe     loc_14005E737
0x14005e8c3  lea     r8, [rsi+18h]
0x14005e8c7  add     r8, rdx
0x14005e8ca  mov     [rsp+98h+var_50], r8
0x14005e8cf  jmp     loc_14005E737
0x14005e8d4  add     r8d, r15d
0x14005e8d7  jmp     short loc_14005E860
0x14005e8d9  sub     ecx, r15d
0x14005e8dc  jz      short loc_14005E8F6
0x14005e8de  cmp     ecx, r15d
0x14005e8e1  jnz     short loc_14005E8A5
0x14005e8e3  lea     rcx, [rdx+28h]
0x14005e8e7  cmp     rcx, r9
0x14005e8ea  ja      short loc_14005E8A5
0x14005e8ec  mov     [rsp+98h+var_67], r15b
0x14005e8f1  jmp     loc_14005E6C9
0x14005e8f6  lea     rcx, [rdx+38h]
0x14005e8fa  jmp     short loc_14005E893
0x14005e8fc  lea     rcx, [rdx+38h]
0x14005e900  jmp     loc_14005E72E
0x14005e905  jmp     loc_14005E83B
0x14005e90a  lea     rcx, [rbx+1A0h]
0x14005e911  call    GetDictionaryEntry
0x14005e916  mov     r13, rax
0x14005e919  mov     [rsp+98h+var_48], rax
0x14005e91e  jmp     loc_14005E5DE
0x14005e923  inc     dword ptr [rbx+260h]
0x14005e929  jmp     loc_14005E7AB
0x14005e92e  inc     dword ptr [r13+10h]
0x14005e932  inc     dword ptr [rbx+25Ch]
0x14005e938  jmp     loc_14005E7AB
0x14005e93d  sub     ecx, 1
0x14005e940  jz      short loc_14005E956
0x14005e942  cmp     ecx, 1
0x14005e945  jnz     loc_14005E629
0x14005e94b  dec     dword ptr [rbx+260h]
0x14005e951  jmp     loc_14005E621
0x14005e956  mov     eax, [r13+10h]
0x14005e95a  test    eax, eax
0x14005e95c  jnz     short loc_14005E968
0x14005e95e  mov     edi, 0C0000184h
0x14005e963  jmp     loc_14005E5E8
0x14005e968  dec     eax
0x14005e96a  mov     [r13+10h], eax
0x14005e96e  dec     dword ptr [rbx+25Ch]
0x14005e974  jmp     loc_14005E621
0x14005e979  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e980  test    edi, edi
0x14005e982  js      loc_14005EA9B
0x14005e988  lea     r14, WPP_GLOBAL_Control
0x14005e98f  cmp     rcx, r14
0x14005e992  jnz     loc_14005EA22
0x14005e998  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e99f  cmp     rcx, r14
0x14005e9a2  jnz     loc_14005EA51
0x14005e9a8  xor     r8d, r8d; Wait
0x14005e9ab  xor     edx, edx; Increment
0x14005e9ad  lea     rcx, [rbx+268h]; Event
0x14005e9b4  call    cs:__imp_KeSetEvent
0x14005e9bb  nop     dword ptr [rax+rax+00h]
0x14005e9c0  call    cs:__imp_KeLeaveCriticalRegion
0x14005e9c7  nop     dword ptr [rax+rax+00h]
0x14005e9cc  test    rsi, rsi
0x14005e9cf  jnz     loc_14005EB17
0x14005e9d5  mov     eax, edi
0x14005e9d7  add     rsp, 60h
0x14005e9db  pop     r15
0x14005e9dd  pop     r14
0x14005e9df  pop     r13
0x14005e9e1  pop     r12
0x14005e9e3  pop     rdi
0x14005e9e4  pop     rsi
0x14005e9e5  pop     rbx
0x14005e9e6  retn
0x14005e9e8  mov     eax, [rcx+2Ch]
0x14005e9eb  test    al, 10h
0x14005e9ed  jz      loc_14005E5C4
0x14005e9f3  cmp     byte ptr [rcx+29h], 4
0x14005e9f7  jb      loc_14005E5C4
0x14005e9fd  lea     rax, LockTypeStrings
0x14005ea04  mov     edx, 1Ah
0x14005ea09  mov     r9, [rax+r14*8]
0x14005ea0d  lea     r8, WPP_d9f3b2dd219d3d7d607ead7f0eae2067_Traceguids
0x14005ea14  mov     rcx, [rcx+18h]
  ... truncated ...
```
