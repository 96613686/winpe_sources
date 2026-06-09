# PmIoctlPassThroughQuerySectorWriteScsi(_IRP *,uchar,uchar *,__int64 *,unsigned __int64 *)

- ea: `0x14001e6f0`
- end: `0x14001eb9c`
- name: `?PmIoctlPassThroughQuerySectorWriteScsi@@YAJPEAU_IRP@@EPEAEPEA_JPEA_K@Z`
- size: `1196`
- prototype: `int(struct _IRP *, unsigned __int8, unsigned __int8 *, __int64 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400087c0`
- `0x14001ed38`

## callees

- `0x14000b36c`
- `0x140010f20`
- `0x14001e6f0`
- `0x14001ff00`
- `0x140023cb4`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x14001e752`
- `ntoskrnl!IoIs32bitProcess` at `0x14001e752`

## pseudocode

```c
__int64 __fastcall PmIoctlPassThroughQuerySectorWriteScsi(
        struct _IRP *a1,
        char a2,
        unsigned __int8 *a3,
        ULONGLONG *a4,
        unsigned __int64 *pullResult)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  struct _IRP *MasterIrp; // rbx
  ULONGLONG v10; // rdi
  BOOLEAN v11; // al
  unsigned int Options; // edx
  __int64 v13; // r8
  unsigned int v14; // ecx
  NTSTATUS DriveGeometry; // ecx
  unsigned int MdlAddress; // r9d
  unsigned int v17; // edx
  char v18; // si
  unsigned __int64 v19; // rcx
  unsigned int v20; // edx
  unsigned int v21; // edx
  unsigned int v22; // edx
  unsigned int v23; // edx
  unsigned int v24; // edx
  unsigned int v25; // edx
  unsigned int v26; // edx
  unsigned int v27; // edx
  unsigned int v28; // edx
  unsigned int v29; // edx
  char v30; // al
  unsigned int v31; // eax
  int v32; // edx
  ULONGLONG ullMultiplicand; // [rsp+40h] [rbp-40h]
  ULONGLONG v35; // [rsp+48h] [rbp-38h]
  ULONGLONG v36; // [rsp+50h] [rbp-30h] BYREF
  struct _DISK_GEOMETRY v37; // [rsp+58h] [rbp-28h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  *a3 = 0;
  MasterIrp = a1->AssociatedIrp.MasterIrp;
  memset(&v37, 0, sizeof(v37));
  v10 = 0;
  HIDWORD(v35) = 0;
  v36 = 0;
  ullMultiplicand = 0;
  v11 = IoIs32bitProcess(a1);
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( v11 )
  {
    v13 = 48;
    v14 = a2 != 0 ? 44 : 48;
    if ( Options < v14 )
      return (unsigned int)-1073741811;
    if ( a2 )
    {
      MdlAddress = *((unsigned __int8 *)&MasterIrp->Size + 4);
      v13 = 28;
    }
    else
    {
      MdlAddress = (unsigned int)MasterIrp->MdlAddress;
      v14 = MdlAddress + 48;
    }
  }
  else
  {
    v13 = 56;
    if ( Options < 0x38 )
      return (unsigned int)-1073741811;
    if ( a2 )
    {
      MdlAddress = *((unsigned __int8 *)&MasterIrp->Size + 4);
      v13 = 36;
      goto LABEL_12;
    }
    MdlAddress = (unsigned int)MasterIrp->MdlAddress;
    v14 = MdlAddress + 56;
  }
  if ( Options < v14 )
    return (unsigned int)-1073741811;
LABEL_12:
  v17 = *((unsigned __int8 *)&MasterIrp->Type + v13);
  v18 = 0;
  DriveGeometry = 0;
  if ( v17 > 0x53 )
  {
    v22 = v17 - 127;
    if ( !v22 )
    {
      if ( MdlAddress < 0x20 )
        return (unsigned int)-1073741811;
      v31 = *((unsigned __int8 *)&MasterIrp->MdlAddress + v13 + 1);
      if ( (unsigned __int8)v31 <= 0xEu )
      {
        v32 = 30928;
        if ( _bittest(&v32, v31) )
        {
          HIBYTE(ullMultiplicand) = *((_BYTE *)&MasterIrp->MdlAddress + v13 + 4);
          BYTE6(ullMultiplicand) = *((_BYTE *)&MasterIrp->MdlAddress + v13 + 5);
          BYTE5(ullMultiplicand) = *((_BYTE *)&MasterIrp->MdlAddress + v13 + 6);
          BYTE4(ullMultiplicand) = *((_BYTE *)&MasterIrp->MdlAddress + v13 + 7);
          BYTE3(ullMultiplicand) = *((_BYTE *)&MasterIrp->Flags + v13);
          BYTE2(ullMultiplicand) = *((_BYTE *)&MasterIrp->Flags + v13 + 1);
          BYTE1(ullMultiplicand) = *((_BYTE *)&MasterIrp->Flags + v13 + 2);
          LOBYTE(ullMultiplicand) = *((_BYTE *)&MasterIrp->Flags + v13 + 3);
          BYTE3(v35) = *((_BYTE *)&MasterIrp->AssociatedIrp.SystemBuffer + v13 + 4);
          BYTE2(v35) = *((_BYTE *)&MasterIrp->AssociatedIrp.SystemBuffer + v13 + 5);
          BYTE1(v35) = *((_BYTE *)&MasterIrp->AssociatedIrp.SystemBuffer + v13 + 6);
          LOBYTE(v35) = *((_BYTE *)&MasterIrp->AssociatedIrp.SystemBuffer + v13 + 7);
          v10 = v35;
          *a3 = 1;
        }
      }
      goto LABEL_57;
    }
    v23 = v22 - 1;
    if ( !v23 )
      return (unsigned int)-1073741808;
    v24 = v23 - 3;
    if ( v24 )
    {
      v25 = v24 - 7;
      if ( v25 && (v26 = v25 - 4) != 0 && (v27 = v26 - 5) != 0 )
      {
        v28 = v27 - 12;
        if ( !v28 )
        {
          if ( MdlAddress < 0x10 )
            return (unsigned int)-1073741811;
          if ( (*((_BYTE *)&MasterIrp->Type + v13 + 1) & 0x1F) == 0x11 )
          {
            v18 = 1;
            HIBYTE(ullMultiplicand) = *((_BYTE *)&MasterIrp->Size + v13);
            BYTE6(ullMultiplicand) = *((_BYTE *)&MasterIrp->Size + v13 + 1);
            BYTE5(ullMultiplicand) = *((_BYTE *)&MasterIrp->Size + v13 + 2);
            BYTE4(ullMultiplicand) = *((_BYTE *)&MasterIrp->Size + v13 + 3);
            BYTE3(ullMultiplicand) = *((_BYTE *)&MasterIrp->Size + v13 + 4);
            BYTE2(ullMultiplicand) = *((_BYTE *)&MasterIrp->Size + v13 + 5);
            BYTE1(ullMultiplicand) = *((_BYTE *)&MasterIrp->MdlAddress + v13);
            LOBYTE(ullMultiplicand) = *((_BYTE *)&MasterIrp->MdlAddress + v13 + 1);
            v10 = *((unsigned __int8 *)&MasterIrp->MdlAddress + v13 + 5)
                | ((unsigned __int64)*((unsigned __int8 *)&MasterIrp->MdlAddress + v13 + 4) << 8);
            *a3 = 1;
          }
          goto LABEL_57;
        }
        v29 = v28 - 11;
        if ( v29 && v29 != 4 )
        {
LABEL_57:
          if ( !*a3 )
            return (unsigned int)DriveGeometry;
          goto LABEL_58;
        }
        if ( MdlAddress < 0xC )
          return (unsigned int)-1073741811;
        BYTE3(ullMultiplicand) = *((_BYTE *)&MasterIrp->Size + v13);
        BYTE2(ullMultiplicand) = *((_BYTE *)&MasterIrp->Size + v13 + 1);
        BYTE1(ullMultiplicand) = *((_BYTE *)&MasterIrp->Size + v13 + 2);
        LOBYTE(ullMultiplicand) = *((_BYTE *)&MasterIrp->Size + v13 + 3);
        BYTE3(v35) = *((_BYTE *)&MasterIrp->Size + v13 + 4);
        BYTE2(v35) = *((_BYTE *)&MasterIrp->Size + v13 + 5);
        BYTE1(v35) = *((_BYTE *)&MasterIrp->MdlAddress + v13);
        v30 = *((_BYTE *)&MasterIrp->MdlAddress + v13 + 1);
      }
      else
      {
        if ( MdlAddress < 0x10 )
          return (unsigned int)-1073741811;
        HIBYTE(ullMultiplicand) = *((_BYTE *)&MasterIrp->Size + v13);
        BYTE6(ullMultiplicand) = *((_BYTE *)&MasterIrp->Size + v13 + 1);
        BYTE5(ullMultiplicand) = *((_BYTE *)&MasterIrp->Size + v13 + 2);
        BYTE4(ullMultiplicand) = *((_BYTE *)&MasterIrp->Size + v13 + 3);
        BYTE3(ullMultiplicand) = *((_BYTE *)&MasterIrp->Size + v13 + 4);
        BYTE2(ullMultiplicand) = *((_BYTE *)&MasterIrp->Size + v13 + 5);
        BYTE1(ullMultiplicand) = *((_BYTE *)&MasterIrp->MdlAddress + v13);
        LOBYTE(ullMultiplicand) = *((_BYTE *)&MasterIrp->MdlAddress + v13 + 1);
        BYTE3(v35) = *((_BYTE *)&MasterIrp->MdlAddress + v13 + 2);
        BYTE2(v35) = *((_BYTE *)&MasterIrp->MdlAddress + v13 + 3);
        BYTE1(v35) = *((_BYTE *)&MasterIrp->MdlAddress + v13 + 4);
        v30 = *((_BYTE *)&MasterIrp->MdlAddress + v13 + 5);
      }
      LOBYTE(v35) = v30;
      v10 = v35;
      *a3 = 1;
      goto LABEL_58;
    }
    if ( MdlAddress < 0x10 )
      return (unsigned int)-1073741811;
    if ( (*((_BYTE *)&MasterIrp->Type + v13 + 1) & 0x1F) != 0x11 )
      return (unsigned int)DriveGeometry;
  }
  else
  {
    if ( v17 == 83 )
      goto LABEL_29;
    if ( v17 <= 0x3F )
    {
      switch ( v17 )
      {
        case 0x3Fu:
          v18 = 1;
          break;
        case 0xAu:
          if ( MdlAddress < 6 )
            return (unsigned int)-1073741811;
          v10 = *((unsigned __int8 *)&MasterIrp->Size + v13 + 2);
          v19 = *((unsigned __int8 *)&MasterIrp->Size + v13 + 1)
              | ((*((unsigned __int8 *)&MasterIrp->Size + v13)
                | ((unsigned __int64)(*((_BYTE *)&MasterIrp->Type + v13 + 1) & 0x1F) << 8)) << 8);
          goto LABEL_24;
        case 0x18u:
          return (unsigned int)-1073741808;
        case 0x2Au:
        case 0x2Eu:
          break;
        case 0x3Au:
          return (unsigned int)-1073741808;
        default:
          goto LABEL_57;
      }
LABEL_29:
      if ( MdlAddress < 0xA )
        return (unsigned int)-1073741811;
      v19 = *((unsigned __int8 *)&MasterIrp->Size + v13 + 3)
          | (unsigned __int64)((*((unsigned __int8 *)&MasterIrp->Size + v13 + 2)
                              | ((*((unsigned __int8 *)&MasterIrp->Size + v13 + 1)
                                | (*((unsigned __int8 *)&MasterIrp->Size + v13) << 8)) << 8)) << 8);
      v10 = *((unsigned __int8 *)&MasterIrp->MdlAddress + v13)
          | ((unsigned __int64)*((unsigned __int8 *)&MasterIrp->Size + v13 + 5) << 8);
LABEL_24:
      ullMultiplicand = v19;
      *a3 = 1;
      goto LABEL_58;
    }
    v20 = v17 - 65;
    if ( !v20 )
      goto LABEL_29;
    v21 = v20 - 1;
    if ( v21 )
    {
      if ( v21 - 14 <= 1 )
        goto LABEL_29;
      goto LABEL_57;
    }
  }
  if ( MdlAddress < 0xA )
    return (unsigned int)-1073741811;
  DriveGeometry = PmSendDeviceControl(CurrentStackLocation->DeviceObject, 0x7405Cu, 0, 0, &v36, 8u, 0);
  if ( DriveGeometry < 0 )
    return (unsigned int)DriveGeometry;
  v10 = v36;
  v18 = 1;
  *a3 = 1;
LABEL_58:
  DriveGeometry = PmGetDriveGeometry(CurrentStackLocation->DeviceObject, &v37);
  if ( DriveGeometry >= 0 )
  {
    DriveGeometry = RtlULongLongMult(ullMultiplicand, v37.BytesPerSector, a4);
    if ( DriveGeometry >= 0 )
    {
      if ( v18 )
        *pullResult = v10;
      else
        return (unsigned int)RtlULongLongMult(v10, v37.BytesPerSector, pullResult);
    }
  }
  return (unsigned int)DriveGeometry;
}

```

## disassembly

```asm
0x14001e6f0  mov     [rsp-38h+arg_8], rbx
0x14001e6f5  push    rbp
0x14001e6f6  push    rsi
0x14001e6f7  push    rdi
0x14001e6f8  push    r12
0x14001e6fa  push    r13
0x14001e6fc  push    r14
0x14001e6fe  push    r15
0x14001e700  mov     rbp, rsp
0x14001e703  sub     rsp, 80h
0x14001e70a  mov     rax, cs:__security_cookie
0x14001e711  xor     rax, rsp
0x14001e714  mov     [rbp-10h], rax
0x14001e718  mov     r13, [rcx+0B8h]
0x14001e71f  mov     sil, dl
0x14001e722  mov     r15, [rbp+pullResult]
0x14001e726  xor     edx, edx
0x14001e728  xorps   xmm0, xmm0
0x14001e72b  mov     [r8], dl
0x14001e72e  mov     rbx, [rcx+18h]
0x14001e732  xor     eax, eax
0x14001e734  mov     r12, r9
0x14001e737  mov     dword ptr [rbp+var_28.Cylinders], edx
0x14001e73a  mov     r14, r8
0x14001e73d  mov     [rbp+var_28.BytesPerSector], eax
0x14001e740  movups  xmmword ptr [rbp+var_28.Cylinders+4], xmm0
0x14001e744  mov     edi, edx
0x14001e746  mov     [rbp+var_38], rdx
0x14001e74a  mov     [rbp+var_30], rdx
0x14001e74e  mov     [rbp+ullMultiplicand], rdx
0x14001e752  call    cs:__imp_IoIs32bitProcess
0x14001e759  nop     dword ptr [rax+rax+00h]
0x14001e75e  mov     edx, [r13+10h]
0x14001e762  test    al, al
0x14001e764  jz      short loc_14001E7A1
0x14001e766  mov     al, sil
0x14001e769  lea     r8d, [rdi+30h]
0x14001e76d  neg     al
0x14001e76f  sbb     ecx, ecx
0x14001e771  and     ecx, 0FFFFFFFCh
0x14001e774  add     ecx, r8d
0x14001e777  cmp     edx, ecx
0x14001e779  jnb     short loc_14001E785
0x14001e77b  mov     ecx, 0C000000Dh
0x14001e780  jmp     loc_14001EB72
0x14001e785  test    sil, sil
0x14001e788  jz      short loc_14001E797
0x14001e78a  movzx   r9d, byte ptr [rbx+6]
0x14001e78f  mov     r8d, 1Ch
0x14001e795  jmp     short loc_14001E7C6
0x14001e797  mov     r9d, [rbx+8]
0x14001e79b  lea     ecx, [r9+30h]
0x14001e79f  jmp     short loc_14001E7C6
0x14001e7a1  mov     r8d, 38h ; '8'
0x14001e7a7  cmp     edx, r8d
0x14001e7aa  jb      short loc_14001E77B
0x14001e7ac  test    sil, sil
0x14001e7af  jz      short loc_14001E7BE
0x14001e7b1  movzx   r9d, byte ptr [rbx+6]
0x14001e7b6  mov     r8d, 24h ; '$'
0x14001e7bc  jmp     short loc_14001E7CA
0x14001e7be  mov     r9d, [rbx+8]
0x14001e7c2  lea     ecx, [r9+38h]
0x14001e7c6  cmp     edx, ecx
0x14001e7c8  jb      short loc_14001E77B
0x14001e7ca  movzx   edx, byte ptr [rbx+r8]
0x14001e7cf  xor     sil, sil
0x14001e7d2  xor     ecx, ecx
0x14001e7d4  cmp     edx, 53h ; 'S'
0x14001e7d7  ja      loc_14001E8BC
0x14001e7dd  jz      loc_14001E872
0x14001e7e3  cmp     edx, 3Fh ; '?'
0x14001e7e6  ja      short loc_14001E856
0x14001e7e8  jz      short loc_14001E851
0x14001e7ea  cmp     edx, 0Ah
0x14001e7ed  jz      short loc_14001E811
0x14001e7ef  cmp     edx, 18h
0x14001e7f2  jz      short loc_14001E807
0x14001e7f4  cmp     edx, 2Ah ; '*'
0x14001e7f7  jz      short loc_14001E872
0x14001e7f9  cmp     edx, 2Eh ; '.'
0x14001e7fc  jz      short loc_14001E872
0x14001e7fe  cmp     edx, 3Ah ; ':'
0x14001e801  jnz     loc_14001EB2B
0x14001e807  mov     ecx, 0C0000010h
0x14001e80c  jmp     loc_14001EB72
0x14001e811  cmp     r9d, 6
0x14001e815  jb      loc_14001E77B
0x14001e81b  movzx   ecx, byte ptr [rbx+r8+1]
0x14001e821  movzx   eax, byte ptr [rbx+r8+2]
0x14001e827  and     ecx, 1Fh
0x14001e82a  movzx   edi, byte ptr [rbx+r8+4]
0x14001e830  shl     rcx, 8
0x14001e834  or      rcx, rax
0x14001e837  movzx   eax, byte ptr [rbx+r8+3]
0x14001e83d  shl     rcx, 8
0x14001e841  or      rcx, rax
0x14001e844  mov     [rbp+ullMultiplicand], rcx
0x14001e848  mov     byte ptr [r14], 1
0x14001e84c  jmp     loc_14001EB30
0x14001e851  mov     sil, 1
0x14001e854  jmp     short loc_14001E872
0x14001e856  sub     edx, 41h ; 'A'
0x14001e859  jz      short loc_14001E872
0x14001e85b  sub     edx, 1
0x14001e85e  jz      loc_14001EA58
0x14001e864  sub     edx, 0Eh
0x14001e867  jz      short loc_14001E872
0x14001e869  cmp     edx, 1
0x14001e86c  jnz     loc_14001EB2B
0x14001e872  cmp     r9d, 0Ah
0x14001e876  jb      loc_14001E77B
0x14001e87c  movzx   eax, byte ptr [rbx+r8+3]
0x14001e882  movzx   ecx, byte ptr [rbx+r8+2]
0x14001e888  movzx   edi, byte ptr [rbx+r8+7]
0x14001e88e  shl     ecx, 8
0x14001e891  or      ecx, eax
0x14001e893  shl     rdi, 8
0x14001e897  movzx   eax, byte ptr [rbx+r8+4]
0x14001e89d  shl     ecx, 8
0x14001e8a0  or      ecx, eax
0x14001e8a2  movzx   eax, byte ptr [rbx+r8+5]
0x14001e8a8  shl     ecx, 8
0x14001e8ab  movsxd  rcx, ecx
0x14001e8ae  or      rcx, rax
0x14001e8b1  movzx   eax, byte ptr [rbx+r8+8]
0x14001e8b7  or      rdi, rax
0x14001e8ba  jmp     short loc_14001E844
0x14001e8bc  sub     edx, 7Fh
0x14001e8bf  jz      loc_14001EAA5
0x14001e8c5  sub     edx, 1
0x14001e8c8  jz      loc_14001E807
0x14001e8ce  sub     edx, 3
0x14001e8d1  jz      loc_14001EA3F
0x14001e8d7  sub     edx, 7
0x14001e8da  jz      loc_14001E9D3
0x14001e8e0  sub     edx, 4
0x14001e8e3  jz      loc_14001E9D3
0x14001e8e9  sub     edx, 5
0x14001e8ec  jz      loc_14001E9D3
0x14001e8f2  sub     edx, 0Ch
0x14001e8f5  jz      short loc_14001E95C
0x14001e8f7  sub     edx, 0Bh
0x14001e8fa  jz      short loc_14001E905
0x14001e8fc  cmp     edx, 4
0x14001e8ff  jnz     loc_14001EB2B
0x14001e905  cmp     r9d, 0Ch
0x14001e909  jb      loc_14001E77B
0x14001e90f  mov     al, [rbx+r8+2]
0x14001e914  mov     byte ptr [rbp+ullMultiplicand+3], al
0x14001e917  mov     al, [rbx+r8+3]
0x14001e91c  mov     byte ptr [rbp+ullMultiplicand+2], al
0x14001e91f  mov     al, [rbx+r8+4]
0x14001e924  mov     byte ptr [rbp+ullMultiplicand+1], al
0x14001e927  mov     al, [rbx+r8+5]
0x14001e92c  mov     byte ptr [rbp+ullMultiplicand], al
0x14001e92f  mov     al, [rbx+r8+6]
0x14001e934  mov     byte ptr [rbp+var_38+3], al
0x14001e937  mov     al, [rbx+r8+7]
0x14001e93c  mov     byte ptr [rbp+var_38+2], al
0x14001e93f  mov     al, [rbx+r8+8]
0x14001e944  mov     byte ptr [rbp+var_38+1], al
0x14001e947  mov     al, [rbx+r8+9]
0x14001e94c  mov     byte ptr [rbp+var_38], al
0x14001e94f  mov     rdi, [rbp+var_38]
0x14001e953  mov     byte ptr [r14], 1
0x14001e957  jmp     loc_14001EB30
0x14001e95c  cmp     r9d, 10h
0x14001e960  jb      loc_14001E77B
0x14001e966  mov     al, [rbx+r8+1]
0x14001e96b  and     al, 1Fh
0x14001e96d  cmp     al, 11h
0x14001e96f  jnz     loc_14001EB2B
0x14001e975  mov     al, [rbx+r8+2]
0x14001e97a  mov     sil, 1
0x14001e97d  movzx   edi, byte ptr [rbx+r8+0Ch]
0x14001e983  mov     byte ptr [rbp+ullMultiplicand+7], al
0x14001e986  mov     al, [rbx+r8+3]
0x14001e98b  mov     byte ptr [rbp+ullMultiplicand+6], al
0x14001e98e  mov     al, [rbx+r8+4]
0x14001e993  mov     byte ptr [rbp+ullMultiplicand+5], al
0x14001e996  mov     al, [rbx+r8+5]
0x14001e99b  mov     byte ptr [rbp+ullMultiplicand+4], al
0x14001e99e  mov     al, [rbx+r8+6]
0x14001e9a3  mov     byte ptr [rbp+ullMultiplicand+3], al
0x14001e9a6  mov     al, [rbx+r8+7]
0x14001e9ab  mov     byte ptr [rbp+ullMultiplicand+2], al
0x14001e9ae  mov     al, [rbx+r8+8]
0x14001e9b3  mov     byte ptr [rbp+ullMultiplicand+1], al
0x14001e9b6  mov     al, [rbx+r8+9]
0x14001e9bb  mov     byte ptr [rbp+ullMultiplicand], al
0x14001e9be  movzx   eax, byte ptr [rbx+r8+0Dh]
0x14001e9c4  shl     rdi, 8
0x14001e9c8  or      rdi, rax
0x14001e9cb  mov     [r14], sil
0x14001e9ce  jmp     loc_14001EB2B
0x14001e9d3  cmp     r9d, 10h
0x14001e9d7  jb      loc_14001E77B
0x14001e9dd  mov     al, [rbx+r8+2]
0x14001e9e2  mov     byte ptr [rbp+ullMultiplicand+7], al
0x14001e9e5  mov     al, [rbx+r8+3]
0x14001e9ea  mov     byte ptr [rbp+ullMultiplicand+6], al
0x14001e9ed  mov     al, [rbx+r8+4]
0x14001e9f2  mov     byte ptr [rbp+ullMultiplicand+5], al
0x14001e9f5  mov     al, [rbx+r8+5]
0x14001e9fa  mov     byte ptr [rbp+ullMultiplicand+4], al
0x14001e9fd  mov     al, [rbx+r8+6]
0x14001ea02  mov     byte ptr [rbp+ullMultiplicand+3], al
0x14001ea05  mov     al, [rbx+r8+7]
0x14001ea0a  mov     byte ptr [rbp+ullMultiplicand+2], al
0x14001ea0d  mov     al, [rbx+r8+8]
0x14001ea12  mov     byte ptr [rbp+ullMultiplicand+1], al
0x14001ea15  mov     al, [rbx+r8+9]
0x14001ea1a  mov     byte ptr [rbp+ullMultiplicand], al
0x14001ea1d  mov     al, [rbx+r8+0Ah]
0x14001ea22  mov     byte ptr [rbp+var_38+3], al
0x14001ea25  mov     al, [rbx+r8+0Bh]
0x14001ea2a  mov     byte ptr [rbp+var_38+2], al
0x14001ea2d  mov     al, [rbx+r8+0Ch]
0x14001ea32  mov     byte ptr [rbp+var_38+1], al
0x14001ea35  mov     al, [rbx+r8+0Dh]
0x14001ea3a  jmp     loc_14001E94C
0x14001ea3f  cmp     r9d, 10h
0x14001ea43  jb      loc_14001E77B
0x14001ea49  mov     al, [rbx+r8+1]
0x14001ea4e  and     al, 1Fh
0x14001ea50  cmp     al, 11h
0x14001ea52  jnz     loc_14001EB72
0x14001ea58  cmp     r9d, 0Ah
0x14001ea5c  jb      loc_14001E77B
0x14001ea62  mov     [rsp+80h+var_50], cl; BOOLEAN
0x14001ea66  lea     rax, [rbp+var_30]
0x14001ea6a  mov     rcx, [r13+28h]; DeviceObject
0x14001ea6e  xor     r9d, r9d; InputBufferLength
0x14001ea71  mov     [rsp+80h+var_58], 8; ULONG
0x14001ea79  xor     r8d, r8d; InputBuffer
0x14001ea7c  mov     edx, 7405Ch; IoControlCode
0x14001ea81  mov     [rsp+80h+var_60], rax; PVOID
0x14001ea86  call    ?PmSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; PmSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x14001ea8b  mov     ecx, eax
0x14001ea8d  test    eax, eax
0x14001ea8f  js      loc_14001EB72
0x14001ea95  mov     rdi, [rbp+var_30]
0x14001ea99  mov     sil, 1
0x14001ea9c  mov     byte ptr [r14], 1
0x14001eaa0  jmp     loc_14001EB30
0x14001eaa5  cmp     r9d, 20h ; ' '
0x14001eaa9  jb      loc_14001E77B
0x14001eaaf  movzx   eax, byte ptr [rbx+r8+9]
0x14001eab5  cmp     al, 0Eh
0x14001eab7  ja      short loc_14001EB2B
0x14001eab9  mov     edx, 78D0h
0x14001eabe  bt      edx, eax
0x14001eac1  jnb     short loc_14001EB2B
0x14001eac3  mov     al, [rbx+r8+0Ch]
0x14001eac8  mov     byte ptr [rbp+ullMultiplicand+7], al
0x14001eacb  mov     al, [rbx+r8+0Dh]
0x14001ead0  mov     byte ptr [rbp+ullMultiplicand+6], al
0x14001ead3  mov     al, [rbx+r8+0Eh]
0x14001ead8  mov     byte ptr [rbp+ullMultiplicand+5], al
0x14001eadb  mov     al, [rbx+r8+0Fh]
0x14001eae0  mov     byte ptr [rbp+ullMultiplicand+4], al
0x14001eae3  mov     al, [rbx+r8+10h]
0x14001eae8  mov     byte ptr [rbp+ullMultiplicand+3], al
0x14001eaeb  mov     al, [rbx+r8+11h]
0x14001eaf0  mov     byte ptr [rbp+ullMultiplicand+2], al
0x14001eaf3  mov     al, [rbx+r8+12h]
0x14001eaf8  mov     byte ptr [rbp+ullMultiplicand+1], al
0x14001eafb  mov     al, [rbx+r8+13h]
0x14001eb00  mov     byte ptr [rbp+ullMultiplicand], al
0x14001eb03  mov     al, [rbx+r8+1Ch]
0x14001eb08  mov     byte ptr [rbp+var_38+3], al
0x14001eb0b  mov     al, [rbx+r8+1Dh]
0x14001eb10  mov     byte ptr [rbp+var_38+2], al
0x14001eb13  mov     al, [rbx+r8+1Eh]
0x14001eb18  mov     byte ptr [rbp+var_38+1], al
0x14001eb1b  mov     al, [rbx+r8+1Fh]
0x14001eb20  mov     byte ptr [rbp+var_38], al
0x14001eb23  mov     rdi, [rbp+var_38]
0x14001eb27  mov     byte ptr [r14], 1
0x14001eb2b  cmp     [r14], cl
0x14001eb2e  jz      short loc_14001EB72
0x14001eb30  mov     rcx, [r13+28h]; struct _DEVICE_OBJECT *
0x14001eb34  lea     rdx, [rbp+var_28]; struct _DISK_GEOMETRY *
0x14001eb38  call    ?PmGetDriveGeometry@@YAJPEAU_DEVICE_OBJECT@@PEAU_DISK_GEOMETRY@@@Z; PmGetDriveGeometry(_DEVICE_OBJECT *,_DISK_GEOMETRY *)
0x14001eb3d  mov     ecx, eax
0x14001eb3f  test    eax, eax
0x14001eb41  js      short loc_14001EB72
0x14001eb43  mov     edx, [rbp+var_28.BytesPerSector]; ullMultiplier
0x14001eb46  mov     r8, r12; pullResult
0x14001eb49  mov     rcx, [rbp+ullMultiplicand]; ullMultiplicand
0x14001eb4d  call    RtlULongLongMult
0x14001eb52  mov     ecx, eax
0x14001eb54  test    eax, eax
0x14001eb56  js      short loc_14001EB72
0x14001eb58  test    sil, sil
0x14001eb5b  jnz     short loc_14001EB6F
0x14001eb5d  mov     edx, [rbp+var_28.BytesPerSector]; ullMultiplier
0x14001eb60  mov     r8, r15; pullResult
0x14001eb63  mov     rcx, rdi; ullMultiplicand
  ... truncated ...
```
