# ClasspDeviceSanitize

- ea: `0x14002fdd8`
- end: `0x140030330`
- name: `ClasspDeviceSanitize`
- size: `1368`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, IRP *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140019de0`

## callees

- `0x140001008`
- `0x1400010f8`
- `0x140005190`
- `0x14000de10`
- `0x14000f3e0`
- `0x1400134a0`
- `0x14002fdd8`
- `0x14003e430`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002fe8e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002fe8e`
- `ntoskrnl!ZwClose` at `0x14002ff48`
- `ntoskrnl!ZwClose` at `0x14002ff48`
- `ntoskrnl!ZwOpenKey` at `0x14002fecd`
- `ntoskrnl!ZwOpenKey` at `0x14002fecd`

## string_xrefs

- `0x14002fe74`: `\Registry\Machine\System\CurrentControlSet\Control\MiniNT`

## pseudocode

```c
__int64 __fastcall ClasspDeviceSanitize(struct _DEVICE_OBJECT *a1, IRP *a2, __int64 a3)
{
  void *DeviceExtension; // r15
  NTSTATUS v6; // edi
  __int64 v7; // rax
  int v8; // ecx
  _IO_STACK_LOCATION *CurrentStackLocation; // r12
  _IRP *MasterIrp; // r14
  __int64 v11; // rcx
  __int64 v12; // r8
  int v13; // ecx
  __int64 v14; // r8
  int v15; // r9d
  __int16 *v16; // rdx
  __int64 v17; // rax
  char v18; // al
  int v19; // r8d
  bool v20; // zf
  char v21; // r10
  __int64 i; // r9
  __int64 v23; // rcx
  unsigned __int64 v24; // r8
  __int64 v25; // rdx
  int v26; // ecx
  int v27; // ecx
  __int64 v28; // rsi
  unsigned int v29; // r11d
  __int64 v30; // r9
  char v31; // r10
  __int64 v32; // rcx
  unsigned __int64 v33; // r8
  __int64 v34; // rdx
  int v35; // ecx
  int v36; // ecx
  __int64 v37; // rsi
  int MdlAddress; // ecx
  int v39; // r9d
  bool v40; // dl
  char v41; // al
  __int64 v42; // rax
  __int64 v43; // r14
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // rax
  struct _DEVICE_OBJECT *v47; // rcx
  ULONG WriteToDevice; // [rsp+20h] [rbp-B9h]
  char v50; // [rsp+30h] [rbp-A9h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-A1h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-99h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+50h] [rbp-89h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-81h] BYREF
  __int64 v55[4]; // [rsp+90h] [rbp-49h] BYREF
  __int64 v56; // [rsp+B0h] [rbp-29h]
  __int64 v57; // [rsp+B8h] [rbp-21h]
  char *v58; // [rsp+C0h] [rbp-19h]
  __int64 v59; // [rsp+C8h] [rbp-11h]
  struct _UNICODE_STRING *p_DestinationString; // [rsp+D0h] [rbp-9h]
  __int64 v61; // [rsp+D8h] [rbp-1h]
  void **p_KeyHandle; // [rsp+E0h] [rbp+7h]
  __int64 v63; // [rsp+E8h] [rbp+Fh]

  DeviceExtension = a1->DeviceExtension;
  DeviceObject = a1;
  if ( !DeviceExtension )
  {
LABEL_2:
    v6 = -1073741823;
    goto LABEL_89;
  }
  v7 = *((_QWORD *)DeviceExtension + 145);
  if ( !v7 )
    goto LABEL_88;
  v8 = *(_DWORD *)(v7 + 8);
  if ( v8 != 7 && v8 != 1 )
    goto LABEL_88;
  v6 = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  if ( *(_BYTE *)(*((_QWORD *)DeviceExtension + 143) + 717LL) )
  {
    KeyHandle = 0;
    DestinationString = 0;
    memset(&ObjectAttributes, 0, 44);
    RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MiniNT");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( v6 < 0 )
    {
      v6 = -1073741637;
      if ( (unsigned int)dword_14004D060 > 5 && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL, v12) )
      {
        v16 = (__int16 *)&unk_140048BA0;
        v56 = *((_QWORD *)DeviceExtension + 146) + 4LL;
        WriteToDevice = 3;
LABEL_11:
        v57 = 16;
        tlgWriteTransfer_EtwWriteTransfer(v13, (int)v16, v14, v15, WriteToDevice, (__int64)v55);
        goto LABEL_89;
      }
      goto LABEL_89;
    }
    ZwClose(KeyHandle);
  }
  v17 = *((_QWORD *)DeviceExtension + 66);
  if ( *(_BYTE *)(v17 + 30) == 1 )
  {
    v18 = *(_BYTE *)(v17 + 31);
    v19 = 308;
    if ( v18 != 1 )
      v19 = 184;
    v6 = InitializeStorageRequestBlock(a3, v18 == 1, v19, 1, 64);
    if ( v6 >= 0 )
      *(_DWORD *)(a3 + 20) = 0;
  }
  else
  {
    memset((void *)(a3 + 3), 0, 0x55u);
    *(_WORD *)a3 = 88;
    *(_BYTE *)(a3 + 2) = 0;
  }
  if ( v6 < 0 )
    goto LABEL_89;
  if ( *(_BYTE *)(a3 + 2) == 40 )
  {
    v20 = *(_DWORD *)(a3 + 20) == 0;
    *(_DWORD *)(a3 + 32) = 255;
    *(_WORD *)(a3 + 38) = 33;
    *(_DWORD *)(a3 + 24) = 268;
    *(_QWORD *)(a3 + 64) = 0;
    *(_DWORD *)(a3 + 60) = 0;
    if ( v20 )
    {
      v21 = 0;
      for ( i = 0; (unsigned int)i < *(_DWORD *)(a3 + 56); i = (unsigned int)(i + 1) )
      {
        v23 = *(unsigned int *)(a3 + 4 * i + 120);
        if ( (unsigned int)v23 >= 0x80 )
        {
          v24 = *(unsigned int *)(a3 + 16);
          if ( (unsigned int)v23 < (unsigned int)v24 )
          {
            v25 = (unsigned int)v23;
            v26 = *(_DWORD *)(v23 + a3) - 64;
            if ( v26 )
            {
              v27 = v26 - 1;
              if ( v27 )
              {
                if ( v27 == 1 && v25 + 40 <= v24 )
                  break;
              }
              else if ( v25 + 56 <= v24 )
              {
                v21 = 1;
                *(_BYTE *)(v25 + a3 + 10) = 10;
              }
            }
            else if ( v25 + 40 <= v24 )
            {
              *(_BYTE *)(v25 + a3 + 10) = 10;
              break;
            }
            if ( v21 )
              break;
          }
        }
      }
    }
  }
  else
  {
    *(_WORD *)(a3 + 8) = 8703;
    *(_QWORD *)(a3 + 12) = 268;
    *(_QWORD *)(a3 + 24) = 0;
    *(_BYTE *)(a3 + 10) = 10;
  }
  if ( *(_BYTE *)(a3 + 2) != 40 )
  {
    v28 = a3 + 72;
    goto LABEL_61;
  }
  v28 = 0;
  if ( !*(_DWORD *)(a3 + 20) )
  {
    v29 = *(_DWORD *)(a3 + 56);
    if ( v29 )
    {
      v30 = 0;
      v31 = 0;
      do
      {
        v32 = *(unsigned int *)(a3 + 4 * v30 + 120);
        if ( (unsigned int)v32 >= 0x80 )
        {
          v33 = *(unsigned int *)(a3 + 16);
          if ( (unsigned int)v32 < (unsigned int)v33 )
          {
            v34 = (unsigned int)v32;
            v35 = *(_DWORD *)(v32 + a3) - 64;
            if ( v35 )
            {
              v36 = v35 - 1;
              if ( v36 )
              {
                if ( v36 == 1 && v34 + 40 <= v33 )
                {
                  if ( !*(_DWORD *)(v34 + a3 + 12) )
                    break;
                  v37 = a3 + 32;
                  goto LABEL_59;
                }
              }
              else if ( v34 + 56 <= v33 )
              {
                if ( !*(_BYTE *)(v34 + a3 + 10) )
                  break;
                v31 = 1;
                v28 = v34 + a3 + 24;
              }
            }
            else if ( v34 + 40 <= v33 )
            {
              if ( !*(_BYTE *)(v34 + a3 + 10) )
                break;
              v37 = a3 + 24;
LABEL_59:
              v28 = v34 + v37;
              break;
            }
            if ( v31 )
              break;
          }
        }
        v30 = (unsigned int)(v30 + 1);
      }
      while ( (unsigned int)v30 < v29 );
    }
  }
LABEL_61:
  if ( !v28 )
    goto LABEL_2;
  MdlAddress = 0;
  *(_QWORD *)v28 = 0;
  v39 = 0;
  *(_WORD *)(v28 + 8) = 0;
  v40 = 1;
  *(_BYTE *)v28 = 72;
  if ( CurrentStackLocation->Parameters.Create.Options >= 0x10
    && MasterIrp
    && *(_DWORD *)&MasterIrp->Type == 16
    && *(_DWORD *)(&MasterIrp->Size + 1) == 16 )
  {
    MdlAddress = (int)MasterIrp->MdlAddress;
    v39 = HIDWORD(MasterIrp->MdlAddress) & 0xF;
    v40 = (HIDWORD(MasterIrp->MdlAddress) & 0x10) == 0;
  }
  *(_BYTE *)(v28 + 1) |= 0x20u;
  if ( *(_DWORD *)(*((_QWORD *)DeviceExtension + 145) + 8LL) == 7 )
    goto LABEL_68;
  v42 = *((_QWORD *)DeviceExtension + 66);
  if ( v42 )
  {
    if ( *(_BYTE *)(v42 + 24) == 17 )
    {
      *(_BYTE *)(v28 + 1) = (32 * v40) | *(_BYTE *)(v28 + 1) & 0xDF;
      if ( v39 )
      {
        if ( v39 == 1 )
        {
LABEL_68:
          if ( !MdlAddress )
            MdlAddress = 1800;
          if ( *(_BYTE *)(a3 + 2) == 40 )
            *(_DWORD *)(a3 + 40) = MdlAddress;
          else
            *(_DWORD *)(a3 + 20) = MdlAddress;
          v41 = *(_BYTE *)(v28 + 1) & 0xE0 | 2;
          goto LABEL_85;
        }
        if ( v39 != 2 )
        {
LABEL_88:
          v6 = -1073741637;
          goto LABEL_89;
        }
      }
    }
  }
  if ( !MdlAddress )
    MdlAddress = 60;
  if ( *(_BYTE *)(a3 + 2) == 40 )
    *(_DWORD *)(a3 + 40) = MdlAddress;
  else
    *(_DWORD *)(a3 + 20) = MdlAddress;
  v41 = *(_BYTE *)(v28 + 1) & 0xE0 | 3;
LABEL_85:
  *(_BYTE *)(v28 + 1) = v41 & 0x7F;
  v43 = MEMORY[0xFFFFF78000000008];
  v6 = ClassSendSrbSynchronous(*((PDEVICE_OBJECT *)DeviceExtension + 1), (PSCSI_REQUEST_BLOCK)a3, 0, 0, 0);
  if ( (unsigned int)dword_14004D060 > 5
    && (unsigned __int8)tlgKeywordOn(v44, 0x200000000000LL, MEMORY[0xFFFFF78000000008]) )
  {
    v16 = word_140048E6A;
    v46 = *((_QWORD *)DeviceExtension + 146) + 4LL;
    v59 = 1;
    v56 = v46;
    LOBYTE(v46) = *(_BYTE *)(v28 + 1) & 0x1F;
    v61 = 8;
    v50 = v46;
    v14 = v45 - v43;
    *(_QWORD *)&DestinationString.Length = v14;
    v58 = &v50;
    p_DestinationString = &DestinationString;
    p_KeyHandle = &KeyHandle;
    WriteToDevice = 6;
    LODWORD(KeyHandle) = v6;
    v63 = 4;
    goto LABEL_11;
  }
LABEL_89:
  v47 = DeviceObject;
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = v6;
  ClassReleaseRemoveLock(v47, a2);
  ClassCompleteRequest(DeviceObject, a2, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14002fdd8  mov     [rsp-8+arg_18], rbx
0x14002fddd  push    rbp
0x14002fdde  push    rsi
0x14002fddf  push    rdi
0x14002fde0  push    r12
0x14002fde2  push    r13
0x14002fde4  push    r14
0x14002fde6  push    r15
0x14002fde8  lea     rbp, [rsp-27h]
0x14002fded  sub     rsp, 100h
0x14002fdf4  mov     rax, cs:__security_cookie
0x14002fdfb  xor     rax, rsp
0x14002fdfe  mov     [rbp+57h+var_40], rax
0x14002fe02  mov     r15, [rcx+40h]
0x14002fe06  mov     rbx, r8
0x14002fe09  mov     [rsp+130h+DeviceObject], rcx
0x14002fe0e  mov     r13, rdx
0x14002fe11  test    r15, r15
0x14002fe14  jnz     short loc_14002FE20
0x14002fe16  mov     edi, 0C0000001h
0x14002fe1b  jmp     loc_1400302DD
0x14002fe20  mov     rax, [r15+488h]
0x14002fe27  test    rax, rax
0x14002fe2a  jz      loc_1400302D8
0x14002fe30  mov     ecx, [rax+8]
0x14002fe33  mov     esi, 1
0x14002fe38  cmp     ecx, 7
0x14002fe3b  jz      short loc_14002FE45
0x14002fe3d  cmp     ecx, esi
0x14002fe3f  jnz     loc_1400302D8
0x14002fe45  mov     rax, [r15+478h]
0x14002fe4c  xor     edi, edi
0x14002fe4e  mov     r12, [rdx+0B8h]
0x14002fe55  mov     r14, [rdx+18h]
0x14002fe59  cmp     [rax+2CDh], dil
0x14002fe60  jz      loc_14002FF54
0x14002fe66  xorps   xmm0, xmm0
0x14002fe69  mov     [rsp+130h+KeyHandle], rdi
0x14002fe6e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14002fe72  xor     eax, eax
0x14002fe74  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x14002fe7b  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x14002fe80  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14002fe84  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x14002fe89  movups  xmmword ptr [rsp+130h+ObjectAttributes.Length], xmm0
0x14002fe8e  call    cs:__imp_RtlInitUnicodeString
0x14002fe95  nop     dword ptr [rax+rax+00h]
0x14002fe9a  lea     rax, [rsp+130h+DestinationString]
0x14002fe9f  mov     [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x14002fea7  xorps   xmm0, xmm0
0x14002feaa  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14002feae  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x14002feb3  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x14002feb7  mov     edx, 20019h; DesiredAccess
0x14002febc  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14002fec3  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x14002fec8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002fecd  call    cs:__imp_ZwOpenKey
0x14002fed4  nop     dword ptr [rax+rax+00h]
0x14002fed9  mov     edi, eax
0x14002fedb  test    eax, eax
0x14002fedd  jns     short loc_14002FF43
0x14002fedf  mov     eax, cs:dword_14004D060
0x14002fee5  mov     edi, 0C00000BBh
0x14002feea  cmp     eax, 5
0x14002feed  jbe     loc_1400302DD
0x14002fef3  mov     rdx, 200000000000h
0x14002fefd  call    _tlgKeywordOn
0x14002ff02  test    al, al
0x14002ff04  jz      loc_1400302DD
0x14002ff0a  mov     rax, [r15+490h]
0x14002ff11  lea     rdx, unk_140048BA0; int
0x14002ff18  add     rax, 4
0x14002ff1c  mov     [rbp+57h+var_80], rax
0x14002ff20  lea     rax, [rbp+57h+var_A0]
0x14002ff24  mov     [rsp+130h+var_108], rax; __int64
0x14002ff29  mov     dword ptr [rsp+130h+WriteToDevice], 3; ULONG
0x14002ff31  mov     [rbp+57h+var_78], 10h
0x14002ff39  call    _tlgWriteTransfer_EtwWriteTransfer
0x14002ff3e  jmp     loc_1400302DD
0x14002ff43  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x14002ff48  call    cs:__imp_ZwClose
0x14002ff4f  nop     dword ptr [rax+rax+00h]
0x14002ff54  mov     rax, [r15+210h]
0x14002ff5b  cmp     [rax+1Eh], sil
0x14002ff5f  jnz     short loc_14002FFA1
0x14002ff61  mov     al, [rax+1Fh]
0x14002ff64  mov     ecx, 0B8h
0x14002ff69  cmp     al, sil
0x14002ff6c  mov     dword ptr [rsp+130h+WriteToDevice], 40h ; '@'
0x14002ff74  mov     r9d, esi
0x14002ff77  lea     r8d, [rcx+7Ch]
0x14002ff7b  cmovnz  r8d, ecx
0x14002ff7f  xor     ecx, ecx
0x14002ff81  cmp     al, sil
0x14002ff84  setz    cl
0x14002ff87  movzx   edx, cx
0x14002ff8a  mov     rcx, rbx
0x14002ff8d  call    InitializeStorageRequestBlock
0x14002ff92  mov     edi, eax
0x14002ff94  test    eax, eax
0x14002ff96  js      short loc_14002FFB9
0x14002ff98  mov     dword ptr [rbx+14h], 0
0x14002ff9f  jmp     short loc_14002FFB9
0x14002ffa1  xor     edx, edx; Val
0x14002ffa3  lea     rcx, [rbx+3]; void *
0x14002ffa7  lea     r8d, [rdx+55h]; Size
0x14002ffab  call    memset
0x14002ffb0  mov     word ptr [rbx], 58h ; 'X'
0x14002ffb5  mov     byte ptr [rbx+2], 0
0x14002ffb9  test    edi, edi
0x14002ffbb  js      loc_1400302DD
0x14002ffc1  mov     dil, 28h ; '('
0x14002ffc4  cmp     [rbx+2], dil
0x14002ffc8  jnz     loc_140030071
0x14002ffce  cmp     dword ptr [rbx+14h], 0
0x14002ffd2  mov     dword ptr [rbx+20h], 0FFh
0x14002ffd9  mov     word ptr [rbx+26h], 21h ; '!'
0x14002ffdf  mov     dword ptr [rbx+18h], 10Ch
0x14002ffe6  mov     qword ptr [rbx+40h], 0
0x14002ffee  mov     dword ptr [rbx+3Ch], 0
0x14002fff5  jnz     loc_14003008B
0x14002fffb  xor     r10b, r10b
0x14002fffe  xor     r9d, r9d
0x140030001  cmp     [rbx+38h], r9d
0x140030005  jbe     loc_14003008B
0x14003000b  mov     ecx, [rbx+r9*4+78h]
0x140030010  cmp     ecx, 80h
0x140030016  jb      short loc_14003005F
0x140030018  mov     r8d, [rbx+10h]
0x14003001c  cmp     ecx, r8d
0x14003001f  jnb     short loc_14003005F
0x140030021  mov     edx, ecx
0x140030023  mov     ecx, [rcx+rbx]
0x140030026  sub     ecx, 40h ; '@'
0x140030029  jz      short loc_140030051
0x14003002b  sub     ecx, esi
0x14003002d  jz      short loc_14003003E
0x14003002f  cmp     ecx, esi
0x140030031  jnz     short loc_14003005A
0x140030033  lea     rcx, [rdx+28h]
0x140030037  cmp     rcx, r8
0x14003003a  jbe     short loc_14003008B
0x14003003c  jmp     short loc_14003005A
0x14003003e  lea     rcx, [rdx+38h]
0x140030042  cmp     rcx, r8
0x140030045  ja      short loc_14003005A
0x140030047  mov     r10b, sil
0x14003004a  mov     byte ptr [rdx+rbx+0Ah], 0Ah
0x14003004f  jmp     short loc_14003005A
0x140030051  lea     rcx, [rdx+28h]
0x140030055  cmp     rcx, r8
0x140030058  jbe     short loc_14003006A
0x14003005a  test    r10b, r10b
0x14003005d  jnz     short loc_14003008B
0x14003005f  add     r9d, esi
0x140030062  cmp     r9d, [rbx+38h]
0x140030066  jb      short loc_14003000B
0x140030068  jmp     short loc_14003008B
0x14003006a  mov     byte ptr [rdx+rbx+0Ah], 0Ah
0x14003006f  jmp     short loc_14003008B
0x140030071  mov     word ptr [rbx+8], 21FFh
0x140030077  mov     qword ptr [rbx+0Ch], 10Ch
0x14003007f  mov     qword ptr [rbx+18h], 0
0x140030087  mov     byte ptr [rbx+0Ah], 0Ah
0x14003008b  cmp     [rbx+2], dil
0x14003008f  jnz     loc_140030137
0x140030095  xor     esi, esi
0x140030097  cmp     [rbx+14h], esi
0x14003009a  jnz     loc_14003013B
0x1400300a0  mov     r11d, [rbx+38h]
0x1400300a4  test    r11d, r11d
0x1400300a7  jz      loc_14003013B
0x1400300ad  xor     r9d, r9d
0x1400300b0  xor     r10b, r10b
0x1400300b3  mov     ecx, [rbx+r9*4+78h]
0x1400300b8  cmp     ecx, 80h
0x1400300be  jb      short loc_14003011D
0x1400300c0  mov     r8d, [rbx+10h]
0x1400300c4  cmp     ecx, r8d
0x1400300c7  jnb     short loc_14003011D
0x1400300c9  mov     edx, ecx
0x1400300cb  mov     ecx, [rcx+rbx]
0x1400300ce  sub     ecx, 40h ; '@'
0x1400300d1  jz      short loc_14003010F
0x1400300d3  sub     ecx, 1
0x1400300d6  jz      short loc_1400300F3
0x1400300d8  cmp     ecx, 1
0x1400300db  jnz     short loc_140030118
0x1400300dd  lea     rcx, [rdx+28h]
0x1400300e1  cmp     rcx, r8
0x1400300e4  ja      short loc_140030118
0x1400300e6  cmp     dword ptr [rdx+rbx+0Ch], 0
0x1400300eb  jbe     short loc_14003013B
0x1400300ed  lea     rsi, [rbx+20h]
0x1400300f1  jmp     short loc_140030132
0x1400300f3  lea     rcx, [rdx+38h]
0x1400300f7  cmp     rcx, r8
0x1400300fa  ja      short loc_140030118
0x1400300fc  cmp     byte ptr [rdx+rbx+0Ah], 0
0x140030101  jbe     short loc_14003013B
0x140030103  lea     rsi, [rbx+18h]
0x140030107  mov     r10b, 1
0x14003010a  add     rsi, rdx
0x14003010d  jmp     short loc_140030118
0x14003010f  lea     rcx, [rdx+28h]
0x140030113  cmp     rcx, r8
0x140030116  jbe     short loc_140030127
0x140030118  test    r10b, r10b
0x14003011b  jnz     short loc_14003013B
0x14003011d  inc     r9d
0x140030120  cmp     r9d, r11d
0x140030123  jb      short loc_1400300B3
0x140030125  jmp     short loc_14003013B
0x140030127  cmp     byte ptr [rdx+rbx+0Ah], 0
0x14003012c  jbe     short loc_14003013B
0x14003012e  lea     rsi, [rbx+18h]
0x140030132  add     rsi, rdx
0x140030135  jmp     short loc_14003013B
0x140030137  lea     rsi, [rbx+48h]
0x14003013b  test    rsi, rsi
0x14003013e  jz      loc_14002FE16
0x140030144  xor     eax, eax
0x140030146  xor     ecx, ecx
0x140030148  mov     [rsi], rax
0x14003014b  xor     r9d, r9d
0x14003014e  mov     [rsi+8], ax
0x140030152  mov     dl, 1
0x140030154  mov     byte ptr [rsi], 48h ; 'H'
0x140030157  cmp     dword ptr [r12+10h], 10h
0x14003015d  jb      short loc_140030188
0x14003015f  test    r14, r14
0x140030162  jz      short loc_140030188
0x140030164  cmp     dword ptr [r14], 10h
0x140030168  jnz     short loc_140030188
0x14003016a  cmp     dword ptr [r14+4], 10h
0x14003016f  jnz     short loc_140030188
0x140030171  mov     edx, [r14+0Ch]
0x140030175  mov     r9d, edx
0x140030178  mov     ecx, [r14+8]
0x14003017c  and     r9d, 0Fh
0x140030180  shr     dl, 4
0x140030183  not     dl
0x140030185  and     dl, 1
0x140030188  or      byte ptr [rsi+1], 20h
0x14003018c  mov     rax, [r15+488h]
0x140030193  mov     r8b, [rsi+1]
0x140030197  cmp     dword ptr [rax+8], 7
0x14003019b  jnz     short loc_1400301BE
0x14003019d  test    ecx, ecx
0x14003019f  mov     eax, 708h
0x1400301a4  cmovz   ecx, eax
0x1400301a7  cmp     [rbx+2], dil
0x1400301ab  jnz     short loc_1400301B2
0x1400301ad  mov     [rbx+28h], ecx
0x1400301b0  jmp     short loc_1400301B5
0x1400301b2  mov     [rbx+14h], ecx
0x1400301b5  mov     al, [rsi+1]
0x1400301b8  and     al, 0E2h
0x1400301ba  or      al, 2
0x1400301bc  jmp     short loc_140030212
0x1400301be  mov     rax, [r15+210h]
0x1400301c5  test    rax, rax
0x1400301c8  jz      short loc_1400301F3
0x1400301ca  cmp     byte ptr [rax+18h], 11h
0x1400301ce  jnz     short loc_1400301F3
0x1400301d0  and     r8b, 0DFh
0x1400301d4  shl     dl, 5
0x1400301d7  or      r8b, dl
0x1400301da  mov     [rsi+1], r8b
0x1400301de  test    r9d, r9d
0x1400301e1  jz      short loc_1400301F3
0x1400301e3  cmp     r9d, 1
0x1400301e7  jz      short loc_14003019D
0x1400301e9  cmp     r9d, 2
0x1400301ed  jnz     loc_1400302D8
0x1400301f3  test    ecx, ecx
0x1400301f5  mov     eax, 3Ch ; '<'
0x1400301fa  cmovz   ecx, eax
0x1400301fd  cmp     [rbx+2], dil
0x140030201  jnz     short loc_140030208
0x140030203  mov     [rbx+28h], ecx
0x140030206  jmp     short loc_14003020B
0x140030208  mov     [rbx+14h], ecx
0x14003020b  mov     al, [rsi+1]
0x14003020e  and     al, 0E3h
0x140030210  or      al, 3
0x140030212  and     al, 7Fh
0x140030214  mov     [rsp+130h+WriteToDevice], 0; WriteToDevice
0x140030219  mov     [rsi+1], al
0x14003021c  mov     r12, 0FFFFF78000000008h
0x140030226  xor     r9d, r9d; BufferLength
0x140030229  xor     r8d, r8d; BufferAddress
0x14003022c  mov     rdx, rbx; Srb
0x14003022f  mov     r14, [r12]
0x140030233  mov     rcx, [r15+8]; DeviceObject
0x140030237  call    ClassSendSrbSynchronous
0x14003023c  mov     r8, [r12]
0x140030240  mov     edi, eax
0x140030242  mov     eax, cs:dword_14004D060
  ... truncated ...
```
