# PmCheckIdsGpt(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,uchar *,_DISK_OFFLINE_REASON *)

- ea: `0x140023f38`
- end: `0x1400241af`
- name: `?PmCheckIdsGpt@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAEPEAW4_DISK_OFFLINE_REASON@@@Z`
- size: `631`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *, unsigned __int8 *, enum _DISK_OFFLINE_REASON *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x14000d6f4`

## callees

- `0x1400210a8`
- `0x140023f38`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140023fd0`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400240cf`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140023fd0`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400240cf`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140024120`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140024189`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140024120`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140024189`

## pseudocode

```c
__int64 __fastcall PmCheckIdsGpt(
        struct _DEVICE_EXTENSION *a1,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a2,
        unsigned __int8 *a3,
        enum _DISK_OFFLINE_REASON *a4)
{
  PDEVICE_OBJECT v4; // rax
  __int64 v7; // r8
  char *DeviceExtension; // r9
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  struct _RTL_AVL_TABLE *v14; // r12
  struct _DEVICE_EXTENSION **v15; // rax
  unsigned int IsRedundantPath; // edi
  __int64 v18; // rbx
  DWORD PartitionCount; // r10d
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rcx
  DWORD i; // r8d
  __int64 v24; // r9
  __int64 v25; // rcx
  struct _DEVICE_EXTENSION *inserted; // rax
  struct _DEVICE_EXTENSION *v27; // rbx
  struct _DEVICE_EXTENSION **v28; // rcx
  __int64 j; // r14
  __int64 Buffer; // [rsp+20h] [rbp-30h] BYREF
  __int128 v31; // [rsp+28h] [rbp-28h]
  GUID PartitionId; // [rsp+38h] [rbp-18h]
  unsigned __int8 v33; // [rsp+98h] [rbp+48h] BYREF
  unsigned __int8 NewElement; // [rsp+A0h] [rbp+50h] BYREF
  char *v35; // [rsp+A8h] [rbp+58h]

  v4 = PmControlObject;
  *a3 = 0;
  v33 = 0;
  v7 = *(_QWORD *)&GUID_NULL.Data1;
  DeviceExtension = (char *)v4->DeviceExtension;
  v11 = *(_QWORD *)&a2->Mbr.Signature;
  v12 = *(_QWORD *)GUID_NULL.Data4;
  v35 = DeviceExtension;
  NewElement = 0;
  Buffer = 0;
  *(_DWORD *)a4 = 4;
  v31 = 0;
  PartitionId = 0;
  v13 = v11 - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v13 )
    v13 = *(_QWORD *)a2->Gpt.DiskId.Data4 - *(_QWORD *)GUID_NULL.Data4;
  v14 = (struct _RTL_AVL_TABLE *)(DeviceExtension + 304);
  if ( v13 )
  {
    PartitionId = *(GUID *)&a2->Mbr.Signature;
    v15 = (struct _DEVICE_EXTENSION **)RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(DeviceExtension + 304), &Buffer);
    if ( v15 )
    {
      IsRedundantPath = PmIsRedundantPath(a1, v15[2], &v33);
      if ( (IsRedundantPath & 0x80000000) == 0 && v33 )
        *(_DWORD *)a4 = 2;
      return IsRedundantPath;
    }
    v12 = *(_QWORD *)GUID_NULL.Data4;
    v7 = *(_QWORD *)&GUID_NULL.Data1;
  }
  else
  {
    *a3 = 1;
  }
  IsRedundantPath = 0;
  v18 = 0;
  while ( 1 )
  {
    PartitionCount = a2->PartitionCount;
    if ( (unsigned int)v18 >= PartitionCount )
      break;
    v20 = v18;
    v21 = *(_QWORD *)&a2->PartitionEntry[v18].Gpt.PartitionId.Data1 - v7;
    if ( !v21 )
      v21 = *(_QWORD *)a2->PartitionEntry[v18].Gpt.PartitionId.Data4 - v12;
    if ( v21 )
    {
      v22 = *(_QWORD *)&a2->PartitionEntry[v18].Gpt.PartitionId.Data1 - *(_QWORD *)&a2->Mbr.Signature;
      if ( !v22 )
        v22 = *(_QWORD *)a2->PartitionEntry[v18].Gpt.PartitionId.Data4 - *(_QWORD *)a2->Gpt.DiskId.Data4;
      if ( !v22 )
        return IsRedundantPath;
      v18 = (unsigned int)(v18 + 1);
      for ( i = v18; i < PartitionCount; ++i )
      {
        v24 = i;
        v25 = *(_QWORD *)&a2->PartitionEntry[v20].Gpt.PartitionId.Data1
            - *(_QWORD *)&a2->PartitionEntry[v24].Gpt.PartitionId.Data1;
        if ( !v25 )
          v25 = *(_QWORD *)a2->PartitionEntry[v20].Gpt.PartitionId.Data4
              - *(_QWORD *)a2->PartitionEntry[v24].Gpt.PartitionId.Data4;
        if ( !v25 )
          return IsRedundantPath;
      }
      PartitionId = a2->PartitionEntry[v20].Gpt.PartitionId;
      if ( RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(v35 + 304), &Buffer) )
        return IsRedundantPath;
      v12 = *(_QWORD *)GUID_NULL.Data4;
      v7 = *(_QWORD *)&GUID_NULL.Data1;
    }
    else
    {
      *a3 = 1;
      v18 = (unsigned int)(v18 + 1);
    }
  }
  *(_DWORD *)a4 = 0;
  if ( !*a3 )
  {
    PartitionId = *(GUID *)&a2->Mbr.Signature;
    inserted = (struct _DEVICE_EXTENSION *)RtlInsertElementGenericTableAvl(v14, &Buffer, 0x28u, &NewElement);
    if ( inserted )
    {
      v27 = (struct _DEVICE_EXTENSION *)((char *)a1 + 632);
      v28 = (struct _DEVICE_EXTENSION **)*((_QWORD *)a1 + 80);
      if ( *v28 != (struct _DEVICE_EXTENSION *)((char *)a1 + 632) )
LABEL_37:
        __fastfail(3u);
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        *(_QWORD *)inserted = v27;
        *((_QWORD *)inserted + 1) = v28;
        *v28 = inserted;
        *((_QWORD *)a1 + 80) = inserted;
        *((_QWORD *)inserted + 2) = a1;
        if ( (unsigned int)j >= a2->PartitionCount )
          break;
        PartitionId = a2->PartitionEntry[j].Gpt.PartitionId;
        inserted = (struct _DEVICE_EXTENSION *)RtlInsertElementGenericTableAvl(v14, &Buffer, 0x28u, &NewElement);
        if ( !inserted )
          return (unsigned int)-1073741670;
        v28 = (struct _DEVICE_EXTENSION **)*((_QWORD *)a1 + 80);
        if ( *v28 != v27 )
          goto LABEL_37;
      }
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return IsRedundantPath;
}

```

## disassembly

```asm
0x140023f38  mov     [rsp-38h+arg_0], rbx
0x140023f3d  push    rbp
0x140023f3e  push    rsi
0x140023f3f  push    rdi
0x140023f40  push    r12
0x140023f42  push    r13
0x140023f44  push    r14
0x140023f46  push    r15
0x140023f48  mov     rbp, rsp
0x140023f4b  sub     rsp, 50h
0x140023f4f  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x140023f56  mov     r15, r9
0x140023f59  xorps   xmm0, xmm0
0x140023f5c  mov     byte ptr [r8], 0
0x140023f60  mov     r14, r8
0x140023f63  mov     [rbp+arg_8], 0
0x140023f67  mov     r8, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x140023f6e  mov     r13, rcx
0x140023f71  mov     r9, [rax+40h]
0x140023f75  mov     rsi, rdx
0x140023f78  mov     rax, [rdx+8]
0x140023f7c  mov     rcx, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data4; _GUID const GUID_NULL ...
0x140023f83  mov     [rbp+arg_18], r9
0x140023f87  mov     [rbp+NewElement], 0
0x140023f8b  mov     [rbp+Buffer], 0
0x140023f93  mov     dword ptr [r15], 4
0x140023f9a  movups  [rbp+var_28], xmm0
0x140023f9e  movups  [rbp+var_18], xmm0
0x140023fa2  sub     rax, r8
0x140023fa5  jnz     short loc_140023FAE
0x140023fa7  mov     rax, [rdx+10h]
0x140023fab  sub     rax, rcx
0x140023fae  lea     r12, [r9+130h]
0x140023fb5  test    rax, rax
0x140023fb8  jnz     short loc_140023FC0
0x140023fba  mov     byte ptr [r14], 1
0x140023fbe  jmp     short loc_14002402D
0x140023fc0  movups  xmm0, xmmword ptr [rdx+8]
0x140023fc4  lea     rdx, [rbp+Buffer]; Buffer
0x140023fc8  mov     rcx, r12; Table
0x140023fcb  movdqu  [rbp+var_18], xmm0
0x140023fd0  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140023fd7  nop     dword ptr [rax+rax+00h]
0x140023fdc  test    rax, rax
0x140023fdf  jz      short loc_14002401F
0x140023fe1  mov     rdx, [rax+10h]; struct _DEVICE_EXTENSION *
0x140023fe5  lea     r8, [rbp+arg_8]; unsigned __int8 *
0x140023fe9  mov     rcx, r13; struct _DEVICE_EXTENSION *
0x140023fec  call    ?PmIsRedundantPath@@YAJPEAU_DEVICE_EXTENSION@@0PEAE@Z; PmIsRedundantPath(_DEVICE_EXTENSION *,_DEVICE_EXTENSION *,uchar *)
0x140023ff1  mov     edi, eax
0x140023ff3  test    eax, eax
0x140023ff5  js      short loc_140024004
0x140023ff7  cmp     [rbp+arg_8], 0
0x140023ffb  jz      short loc_140024004
0x140023ffd  mov     dword ptr [r15], 2
0x140024004  mov     rbx, [rsp+50h+arg_0]
0x14002400c  mov     eax, edi
0x14002400e  add     rsp, 50h
0x140024012  pop     r15
0x140024014  pop     r14
0x140024016  pop     r13
0x140024018  pop     r12
0x14002401a  pop     rdi
0x14002401b  pop     rsi
0x14002401c  pop     rbp
0x14002401d  retn
0x14002401f  mov     rcx, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data4; _GUID const GUID_NULL ...
0x140024026  mov     r8, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x14002402d  xor     edi, edi
0x14002402f  xor     ebx, ebx
0x140024031  mov     r10d, [rsi+4]
0x140024035  cmp     ebx, r10d
0x140024038  jnb     loc_1400240F7
0x14002403e  lea     rdx, [rbx+rbx*8]
0x140024042  add     rdx, rdx
0x140024045  mov     rax, [rsi+rdx*8+60h]
0x14002404a  sub     rax, r8
0x14002404d  jnz     short loc_140024057
0x14002404f  mov     rax, [rsi+rdx*8+68h]
0x140024054  sub     rax, rcx
0x140024057  test    rax, rax
0x14002405a  jnz     short loc_140024064
0x14002405c  mov     byte ptr [r14], 1
0x140024060  inc     ebx
0x140024062  jmp     short loc_140024031
0x140024064  mov     rcx, [rsi+rdx*8+60h]
0x140024069  sub     rcx, [rsi+8]
0x14002406d  jnz     short loc_140024078
0x14002406f  mov     rcx, [rsi+rdx*8+68h]
0x140024074  sub     rcx, [rsi+10h]
0x140024078  test    rcx, rcx
0x14002407b  jz      short loc_140024004
0x14002407d  inc     ebx
0x14002407f  mov     r8d, ebx
0x140024082  cmp     r8d, r10d
0x140024085  jnb     short loc_1400240B6
0x140024087  mov     rcx, [rsi+rdx*8+60h]
0x14002408c  mov     eax, r8d
0x14002408f  lea     r9, [rax+rax*8]
0x140024093  shl     r9, 4
0x140024097  sub     rcx, [r9+rsi+60h]
0x14002409c  jnz     short loc_1400240A8
0x14002409e  mov     rcx, [rsi+rdx*8+68h]
0x1400240a3  sub     rcx, [r9+rsi+68h]
0x1400240a8  test    rcx, rcx
0x1400240ab  jz      loc_140024004
0x1400240b1  inc     r8d
0x1400240b4  jmp     short loc_140024082
0x1400240b6  movups  xmm0, xmmword ptr [rsi+rdx*8+60h]
0x1400240bb  mov     rcx, [rbp+arg_18]
0x1400240bf  lea     rdx, [rbp+Buffer]; Buffer
0x1400240c3  add     rcx, 130h; Table
0x1400240ca  movdqu  [rbp+var_18], xmm0
0x1400240cf  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1400240d6  nop     dword ptr [rax+rax+00h]
0x1400240db  test    rax, rax
0x1400240de  jnz     loc_140024004
0x1400240e4  mov     rcx, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data4; _GUID const GUID_NULL ...
0x1400240eb  mov     r8, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x1400240f2  jmp     loc_140024031
0x1400240f7  mov     [r15], edi
0x1400240fa  cmp     [r14], dil
0x1400240fd  jnz     loc_140024004
0x140024103  movups  xmm0, xmmword ptr [rsi+8]
0x140024107  mov     r15d, 28h ; '('
0x14002410d  lea     r9, [rbp+NewElement]; NewElement
0x140024111  mov     r8d, r15d; BufferSize
0x140024114  lea     rdx, [rbp+Buffer]; Buffer
0x140024118  mov     rcx, r12; Table
0x14002411b  movdqu  [rbp+var_18], xmm0
0x140024120  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140024127  nop     dword ptr [rax+rax+00h]
0x14002412c  test    rax, rax
0x14002412f  jnz     short loc_14002413B
0x140024131  mov     edi, 0C000009Ah
0x140024136  jmp     loc_140024004
0x14002413b  lea     rbx, [r13+278h]
0x140024142  mov     rcx, [rbx+8]
0x140024146  cmp     [rcx], rbx
0x140024149  jnz     short loc_1400241A8
0x14002414b  xor     r14d, r14d
0x14002414e  mov     [rax], rbx
0x140024151  mov     [rax+8], rcx
0x140024155  mov     [rcx], rax
0x140024158  mov     [rbx+8], rax
0x14002415c  mov     [rax+10h], r13
0x140024160  cmp     r14d, [rsi+4]
0x140024164  jnb     loc_140024004
0x14002416a  lea     rcx, [r14+r14*8]
0x14002416e  mov     r8d, r15d; BufferSize
0x140024171  add     rcx, rcx
0x140024174  lea     r9, [rbp+NewElement]; NewElement
0x140024178  lea     rdx, [rbp+Buffer]; Buffer
0x14002417c  movups  xmm0, xmmword ptr [rsi+rcx*8+60h]
0x140024181  mov     rcx, r12; Table
0x140024184  movdqu  [rbp+var_18], xmm0
0x140024189  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140024190  nop     dword ptr [rax+rax+00h]
0x140024195  test    rax, rax
0x140024198  jz      short loc_140024131
0x14002419a  mov     rcx, [rbx+8]
0x14002419e  cmp     [rcx], rbx
0x1400241a1  jnz     short loc_1400241A8
0x1400241a3  inc     r14d
0x1400241a6  jmp     short loc_14002414E
0x1400241a8  mov     ecx, 3
0x1400241ad  int     29h; Win8: RtlFailFast(ecx)
```
