# NbtTdiOpenAddress

- ea: `0x14004c4a8`
- end: `0x14004c9a2`
- name: `NbtTdiOpenAddress`
- size: `1274`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140012a10`
- `0x14004c1a4`

## callees

- `0x140031140`
- `0x1400400a4`
- `0x140040214`
- `0x140040294`
- `0x140042330`
- `0x14004c4a8`
- `0x14004c9a8`
- `0x14004cb60`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14004c735`
- `ntoskrnl!ZwClose` at `0x14004c735`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14004c79e`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14004c79e`
- `ntoskrnl!ZwCreateFile` at `0x14004c6d2`
- `ntoskrnl!ZwCreateFile` at `0x14004c6d2`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004c776`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004c776`
- `ntoskrnl!ObfDereferenceObject` at `0x14004c826`
- `ntoskrnl!ObfDereferenceObject` at `0x14004c826`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c6f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c703`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c715`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c89f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c8b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c6f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c703`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c715`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c89f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004c8b0`
- `ntoskrnl!ExAllocatePool2` at `0x14004c547`
- `ntoskrnl!ExAllocatePool2` at `0x14004c577`
- `ntoskrnl!ExAllocatePool2` at `0x14004c547`
- `ntoskrnl!ExAllocatePool2` at `0x14004c577`

## pseudocode

```c
__int64 __fastcall NbtTdiOpenAddress(
        void **a1,
        PDEVICE_OBJECT *a2,
        struct _FILE_OBJECT **a3,
        __int64 a4,
        __int16 a5,
        unsigned int a6,
        int a7,
        char a8)
{
  int v8; // r13d
  const WCHAR *v10; // rcx
  __int64 result; // rax
  unsigned int v14; // ebx
  __int64 EaBuffer; // rsi
  _QWORD *Pool2; // r15
  __int64 v17; // r10
  unsigned int v18; // eax
  __int16 v19; // r9
  __int64 v20; // r8
  size_t v21; // r8
  NTSTATUS v22; // eax
  NTSTATUS Status; // ebx
  void **v24; // r15
  NTSTATUS v25; // eax
  PVOID v26; // rsi
  struct _FILE_OBJECT *v27; // rcx
  PDEVICE_OBJECT RelatedDeviceObject; // rax
  struct _FILE_OBJECT *v29; // rdx
  PDEVICE_OBJECT v30; // rcx
  __int64 v31; // r8
  __int64 (__fastcall *v32)(int, int, int, int, int, int, int, __int64, __int64); // r9
  PVOID Buffer; // rcx
  unsigned int v34; // ecx
  __int64 v35; // rdx
  __int64 v36; // [rsp+60h] [rbp-91h]
  void *FileHandle; // [rsp+70h] [rbp-81h] BYREF
  PVOID Object; // [rsp+78h] [rbp-79h] BYREF
  void **v39; // [rsp+80h] [rbp-71h]
  struct _UNICODE_STRING P; // [rsp+88h] [rbp-69h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-49h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-41h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-11h] BYREF

  v39 = a1;
  *a3 = 0;
  v8 = a8 & 1;
  *a2 = 0;
  FileHandle = 0;
  LODWORD(Object) = v8;
  *(_OWORD *)&ObjectAttributes.ObjectName = 0;
  v10 = L"Tcp";
  if ( (a8 & 1) == 0 )
    v10 = L"Udp";
  *(_OWORD *)&ObjectAttributes.Length = 0;
  *(_OWORD *)(&ObjectAttributes.Attributes + 1) = 0;
  IoStatusBlock = 0;
  P = 0;
  result = CreateDeviceString(v10, &P);
  if ( (int)result >= 0 )
  {
    v14 = *(_DWORD *)(a4 + 556) + 1;
    EaBuffer = ExAllocatePool2(64, 14 * v14 + 40, 1786012238);
    if ( EaBuffer )
    {
      v41 = 14LL * v14;
      Pool2 = (_QWORD *)ExAllocatePool2(64, v41 + 12, 1802789454);
      if ( Pool2 )
      {
        *(_DWORD *)EaBuffer = 0;
        *(_WORD *)(EaBuffer + 4) = 4096;
        *(_WORD *)(EaBuffer + 6) = 14 * v14 + 11;
        memmove((void *)(EaBuffer + 8), "TransportAddress", 0x11u);
        if ( (xmmword_140038420 & 0x10) != 0 )
          WPP_SF_d(1028, 11, WPP_7ae8357478e63d53ee3c3e10bf466ad5_Traceguids, *(unsigned __int16 *)(EaBuffer + 6));
        v17 = *(unsigned __int8 *)(EaBuffer + 5);
        v18 = 0;
        v19 = __ROR2__(a5, 8);
        LOWORD(v36) = v19;
        if ( *(_DWORD *)(a4 + 340) != 1 )
          v18 = a6;
        v20 = 0;
        *(_DWORD *)((char *)&v36 + 2) = _byteswap_ulong(v18);
        HIWORD(v36) = 0;
        Pool2[1] = v36;
        *((_DWORD *)Pool2 + 4) = 0;
        *((_WORD *)Pool2 + 10) = 0;
        *((_DWORD *)Pool2 + 1) = 131086;
        if ( *(_DWORD *)(a4 + 556) )
        {
          do
          {
            v34 = *(_DWORD *)(a4 + 4 * v20 + 912);
            v20 = (unsigned int)(v20 + 1);
            LOWORD(v36) = v19;
            *(_DWORD *)((char *)&v36 + 2) = _byteswap_ulong(v34);
            v35 = 3 * v20;
            *(_QWORD *)((char *)Pool2 + 2 * v35 + 8) = v36;
            *(_DWORD *)((char *)Pool2 + 2 * v35 + 16) = 0;
            *((_WORD *)Pool2 + v35 + 10) = 0;
            *(_DWORD *)((char *)Pool2 + 2 * v35 + 4) = 131086;
          }
          while ( (unsigned int)v20 < *(_DWORD *)(a4 + 556) );
          v8 = (int)Object;
        }
        v21 = v41 + 11;
        *(_DWORD *)Pool2 = v14;
        memmove((void *)(EaBuffer + v17 + 9), Pool2, v21);
        if ( (xmmword_140038420 & 0x10) != 0 )
          WPP_SF_S(1028, 12, WPP_7ae8357478e63d53ee3c3e10bf466ad5_Traceguids, P.Buffer);
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.ObjectName = &P;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        ObjectAttributes.Attributes = 576;
        v22 = ZwCreateFile(
                &FileHandle,
                0xC0100000,
                &ObjectAttributes,
                &IoStatusBlock,
                0,
                0x80u,
                a5 == 0 ? 3 : 0,
                3u,
                0,
                (PVOID)EaBuffer,
                *(unsigned __int8 *)(EaBuffer + 5) + 12 + *(unsigned __int16 *)(EaBuffer + 6));
        Status = v22;
        if ( (BYTE2(xmmword_140038420) & 2) != 0 )
          WPP_SF_qD(1041, 13, WPP_7ae8357478e63d53ee3c3e10bf466ad5_Traceguids, FileHandle, v22);
        ExFreePoolWithTag(Pool2, 0);
        ExFreePoolWithTag((PVOID)EaBuffer, 0);
        ExFreePoolWithTag(P.Buffer, 0);
        if ( Status < 0 || (Status = IoStatusBlock.Status, IoStatusBlock.Status < 0) )
        {
          v24 = v39;
        }
        else
        {
          Object = 0;
          v25 = ObReferenceObjectByHandle(FileHandle, 0, 0, 0, &Object, 0);
          v24 = v39;
          Status = v25;
          if ( v25 >= 0 )
          {
            v26 = Object;
            v27 = (struct _FILE_OBJECT *)Object;
            *v39 = FileHandle;
            *a3 = v27;
            RelatedDeviceObject = IoGetRelatedDeviceObject(v27);
            *a2 = RelatedDeviceObject;
            Status = SetEventHandler(RelatedDeviceObject, *a3, 2, TdiErrorHandler, a4);
            if ( Status >= 0 )
            {
              v29 = *a3;
              v30 = *a2;
              if ( !v8 )
              {
                v31 = 4;
                v32 = (__int64 (__fastcall *)(int, int, int, int, int, int, int, __int64, __int64))TdiRcvDatagramHandler;
                if ( a5 != *(_WORD *)(a4 + 876) )
                  v32 = (__int64 (__fastcall *)(int, int, int, int, int, int, int, __int64, __int64))&TdiRcvNameSrvHandler;
                goto LABEL_26;
              }
              Status = SetEventHandler(v30, v29, 3, TdiReceiveHandler, a4);
              if ( Status >= 0 )
              {
                Status = SetEventHandler(*a2, *a3, 1, TdiDisconnectHandler, a4);
                if ( Status >= 0 )
                {
                  if ( (a8 & 2) == 0 )
                    return (unsigned int)Status;
                  v29 = *a3;
                  v32 = TdiConnectHandler;
                  v30 = *a2;
                  v31 = 0;
LABEL_26:
                  Status = SetEventHandler(v30, v29, v31, v32, a4);
                  if ( Status >= 0 )
                    return (unsigned int)Status;
                }
              }
            }
            ObfDereferenceObject(v26);
          }
        }
        if ( FileHandle )
          ZwClose(FileHandle);
        *v24 = 0;
        *a3 = 0;
        *a2 = 0;
        return (unsigned int)Status;
      }
      ExFreePoolWithTag(P.Buffer, 0);
      Buffer = (PVOID)EaBuffer;
    }
    else
    {
      if ( (xmmword_140038420 & 0x10) != 0 )
        WPP_SF_(1028, 10, WPP_7ae8357478e63d53ee3c3e10bf466ad5_Traceguids);
      Buffer = P.Buffer;
    }
    ExFreePoolWithTag(Buffer, 0);
    return 3221225626LL;
  }
  return result;
}

```

## disassembly

```asm
0x14004c4a8  push    rbp
0x14004c4aa  push    rbx
0x14004c4ab  push    rsi
0x14004c4ac  push    rdi
0x14004c4ad  push    r12
0x14004c4af  push    r13
0x14004c4b1  push    r14
0x14004c4b3  push    r15
0x14004c4b5  lea     rbp, [rsp-7]
0x14004c4ba  sub     rsp, 0F8h
0x14004c4c1  mov     r13d, [rbp+3Fh+arg_38]
0x14004c4c8  xor     r15d, r15d
0x14004c4cb  xorps   xmm0, xmm0
0x14004c4ce  mov     [rbp+3Fh+var_B0], rcx
0x14004c4d2  xor     eax, eax
0x14004c4d4  mov     [r8], r15
0x14004c4d7  and     r13d, 1
0x14004c4db  mov     [rdx], r15
0x14004c4de  lea     rax, aUdp; "Udp"
0x14004c4e5  mov     [rsp+130h+var_D0+6], r15
0x14004c4ea  mov     r12, rdx
0x14004c4ed  mov     [rsp+130h+FileHandle], r15
0x14004c4f2  xorps   xmm1, xmm1
0x14004c4f5  mov     dword ptr [rbp+3Fh+Object], r13d
0x14004c4f9  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x14004c4fd  lea     rcx, aTcp; "Tcp"
0x14004c504  mov     rdi, r9
0x14004c507  cmovz   rcx, rax; Source
0x14004c50b  lea     rdx, [rbp+3Fh+P]; Destination
0x14004c50f  mov     r14, r8
0x14004c512  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x14004c516  movups  xmmword ptr [rbp+3Fh+ObjectAttributes+1Ch], xmm0
0x14004c51a  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x14004c51e  movups  xmmword ptr [rbp+3Fh+P.Length], xmm1
0x14004c522  call    CreateDeviceString
0x14004c527  test    eax, eax
0x14004c529  js      loc_14004C80E
0x14004c52f  mov     ebx, [rdi+22Ch]
0x14004c535  lea     ecx, [r15+40h]
0x14004c539  inc     ebx
0x14004c53b  mov     r8d, 6A74624Eh
0x14004c541  imul    edx, ebx, 0Eh
0x14004c544  add     edx, 28h ; '('
0x14004c547  call    cs:__imp_ExAllocatePool2
0x14004c54e  nop     dword ptr [rax+rax+00h]
0x14004c553  mov     rsi, rax
0x14004c556  test    rax, rax
0x14004c559  jz      loc_14004C8C6
0x14004c55f  mov     eax, ebx
0x14004c561  lea     ecx, [r15+40h]
0x14004c565  imul    rax, 0Eh
0x14004c569  mov     r8d, 6B74624Eh
0x14004c56f  mov     [rbp+3Fh+var_88], rax
0x14004c573  lea     rdx, [rax+0Ch]
0x14004c577  call    cs:__imp_ExAllocatePool2
0x14004c57e  nop     dword ptr [rax+rax+00h]
0x14004c583  mov     r15, rax
0x14004c586  test    rax, rax
0x14004c589  jz      loc_14004C899
0x14004c58f  movzx   eax, bx
0x14004c592  lea     rdx, aTransportaddre; "TransportAddress"
0x14004c599  imul    ecx, eax, 0Eh
0x14004c59c  mov     r8d, 11h; Size
0x14004c5a2  mov     dword ptr [rsi], 0
0x14004c5a8  mov     word ptr [rsi+4], 1000h
0x14004c5ae  add     cx, 0Bh
0x14004c5b2  mov     [rsi+6], cx
0x14004c5b6  lea     rcx, [rsi+8]; void *
0x14004c5ba  call    memmove
0x14004c5bf  test    byte ptr cs:xmmword_140038420, 10h
0x14004c5c6  jnz     loc_14004C8EB
0x14004c5cc  movzx   r10d, byte ptr [rsi+5]
0x14004c5d1  xor     eax, eax
0x14004c5d3  movzx   r9d, [rbp+3Fh+arg_20]
0x14004c5d8  ror     r9w, 8
0x14004c5dd  cmp     dword ptr [rdi+154h], 1
0x14004c5e4  mov     word ptr [rsp+130h+var_D0], r9w
0x14004c5ea  cmovnz  eax, [rbp+3Fh+arg_28]
0x14004c5ee  xor     r8d, r8d
0x14004c5f1  bswap   eax
0x14004c5f3  mov     dword ptr [rsp+130h+var_D0+2], eax
0x14004c5f7  xor     eax, eax
0x14004c5f9  mov     [rsp+130h+var_D0+6], rax
0x14004c5fe  movsd   xmm0, [rsp+130h+var_D0]
0x14004c604  mov     r11d, [rsp+130h+var_C8]
0x14004c609  movzx   eax, [rsp+130h+var_C4]
0x14004c60e  movsd   qword ptr [r15+8], xmm0
0x14004c614  mov     [r15+10h], r11d
0x14004c618  mov     [r15+14h], ax
0x14004c61d  mov     dword ptr [r15+4], 2000Eh
0x14004c625  cmp     [rdi+22Ch], r8d
0x14004c62c  ja      loc_14004C90B
0x14004c632  mov     r8, [rbp+3Fh+var_88]
0x14004c636  lea     rcx, [r10+9]
0x14004c63a  add     r8, 0Bh; Size
0x14004c63e  mov     [r15], ebx
0x14004c641  add     rcx, rsi; void *
0x14004c644  mov     rdx, r15; Src
0x14004c647  call    memmove
0x14004c64c  test    byte ptr cs:xmmword_140038420, 10h
0x14004c653  jnz     loc_14004C95F
0x14004c659  xor     r8d, r8d
0x14004c65c  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x14004c663  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r8
0x14004c667  lea     rax, [rbp+3Fh+P]
0x14004c66b  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x14004c66f  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x14004c673  movzx   eax, [rbp+3Fh+arg_20]
0x14004c677  xorps   xmm0, xmm0
0x14004c67a  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14004c67f  mov     [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x14004c686  movzx   ecx, byte ptr [rsi+5]
0x14004c68a  movzx   edx, word ptr [rsi+6]
0x14004c68e  add     ecx, 0Ch
0x14004c691  add     edx, ecx
0x14004c693  mov     [rsp+130h+EaLength], edx; EaLength
0x14004c697  neg     ax
0x14004c69a  mov     [rsp+130h+EaBuffer], rsi; EaBuffer
0x14004c69f  mov     edx, 0C0100000h; DesiredAccess
0x14004c6a4  mov     [rsp+130h+CreateOptions], r8d; CreateOptions
0x14004c6a9  sbb     ecx, ecx
0x14004c6ab  not     ecx
0x14004c6ad  mov     [rsp+130h+CreateDisposition], 3; CreateDisposition
0x14004c6b5  and     ecx, 3
0x14004c6b8  mov     [rsp+130h+ShareAccess], ecx; ShareAccess
0x14004c6bc  lea     rcx, [rsp+130h+FileHandle]; FileHandle
0x14004c6c1  mov     [rsp+130h+FileAttributes], 80h; FileAttributes
0x14004c6c9  mov     [rsp+130h+AllocationSize], r8; AllocationSize
0x14004c6ce  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x14004c6d2  call    cs:__imp_ZwCreateFile
0x14004c6d9  nop     dword ptr [rax+rax+00h]
0x14004c6de  mov     ebx, eax
0x14004c6e0  test    byte ptr cs:xmmword_140038420+2, 2
0x14004c6e7  jnz     loc_14004C97E
0x14004c6ed  xor     edx, edx; Tag
0x14004c6ef  mov     rcx, r15; P
0x14004c6f2  call    cs:__imp_ExFreePoolWithTag
0x14004c6f9  nop     dword ptr [rax+rax+00h]
0x14004c6fe  xor     edx, edx; Tag
0x14004c700  mov     rcx, rsi; P
0x14004c703  call    cs:__imp_ExFreePoolWithTag
0x14004c70a  nop     dword ptr [rax+rax+00h]
0x14004c70f  mov     rcx, [rbp+3Fh+P.Buffer]; P
0x14004c713  xor     edx, edx; Tag
0x14004c715  call    cs:__imp_ExFreePoolWithTag
0x14004c71c  nop     dword ptr [rax+rax+00h]
0x14004c721  xor     esi, esi
0x14004c723  test    ebx, ebx
0x14004c725  jns     short loc_14004C750
0x14004c727  mov     r15, [rbp+3Fh+var_B0]
0x14004c72b  mov     rcx, [rsp+130h+FileHandle]; Handle
0x14004c730  test    rcx, rcx
0x14004c733  jz      short loc_14004C741
0x14004c735  call    cs:__imp_ZwClose
0x14004c73c  nop     dword ptr [rax+rax+00h]
0x14004c741  mov     [r15], rsi
0x14004c744  mov     [r14], rsi
0x14004c747  mov     [r12], rsi
0x14004c74b  jmp     loc_14004C80C
0x14004c750  mov     ebx, dword ptr [rbp+3Fh+IoStatusBlock]
0x14004c753  test    ebx, ebx
0x14004c755  js      short loc_14004C727
0x14004c757  mov     rcx, [rsp+130h+FileHandle]; Handle
0x14004c75c  lea     rax, [rbp+3Fh+Object]
0x14004c760  mov     qword ptr [rsp+130h+FileAttributes], rsi; HandleInformation
0x14004c765  xor     r9d, r9d; AccessMode
0x14004c768  xor     r8d, r8d; ObjectType
0x14004c76b  mov     [rsp+130h+AllocationSize], rax; Object
0x14004c770  xor     edx, edx; DesiredAccess
0x14004c772  mov     [rbp+3Fh+Object], rsi
0x14004c776  call    cs:__imp_ObReferenceObjectByHandle
0x14004c77d  nop     dword ptr [rax+rax+00h]
0x14004c782  mov     r15, [rbp+3Fh+var_B0]
0x14004c786  mov     ebx, eax
0x14004c788  test    eax, eax
0x14004c78a  js      short loc_14004C72B
0x14004c78c  mov     rsi, [rbp+3Fh+Object]
0x14004c790  mov     rax, [rsp+130h+FileHandle]
0x14004c795  mov     rcx, rsi; FileObject
0x14004c798  mov     [r15], rax
0x14004c79b  mov     [r14], rsi
0x14004c79e  call    cs:__imp_IoGetRelatedDeviceObject
0x14004c7a5  nop     dword ptr [rax+rax+00h]
0x14004c7aa  lea     r9, TdiErrorHandler
0x14004c7b1  mov     [rsp+130h+AllocationSize], rdi
0x14004c7b6  mov     [r12], rax
0x14004c7ba  mov     r8d, 2
0x14004c7c0  mov     rdx, [r14]
0x14004c7c3  mov     rcx, rax
0x14004c7c6  call    SetEventHandler
0x14004c7cb  mov     ebx, eax
0x14004c7cd  test    eax, eax
0x14004c7cf  js      short loc_14004C823
0x14004c7d1  mov     rdx, [r14]
0x14004c7d4  mov     rcx, [r12]
0x14004c7d8  test    r13d, r13d
0x14004c7db  jnz     short loc_14004C839
0x14004c7dd  movzx   eax, [rbp+3Fh+arg_20]
0x14004c7e1  lea     r8d, [r13+4]
0x14004c7e5  lea     r9, TdiRcvDatagramHandler
0x14004c7ec  cmp     ax, [rdi+36Ch]
0x14004c7f3  jz      short loc_14004C7FC
0x14004c7f5  lea     r9, TdiRcvNameSrvHandler
0x14004c7fc  mov     [rsp+130h+AllocationSize], rdi
0x14004c801  call    SetEventHandler
0x14004c806  mov     ebx, eax
0x14004c808  test    eax, eax
0x14004c80a  js      short loc_14004C823
0x14004c80c  mov     eax, ebx
0x14004c80e  add     rsp, 0F8h
0x14004c815  pop     r15
0x14004c817  pop     r14
0x14004c819  pop     r13
0x14004c81b  pop     r12
0x14004c81d  pop     rdi
0x14004c81e  pop     rsi
0x14004c81f  pop     rbx
0x14004c820  pop     rbp
0x14004c821  retn
0x14004c823  mov     rcx, rsi; Object
0x14004c826  call    cs:__imp_ObfDereferenceObject
0x14004c82d  nop     dword ptr [rax+rax+00h]
0x14004c832  xor     esi, esi
0x14004c834  jmp     loc_14004C72B
0x14004c839  lea     r9, TdiReceiveHandler
0x14004c840  mov     [rsp+130h+AllocationSize], rdi
0x14004c845  mov     r8d, 3
0x14004c84b  call    SetEventHandler
0x14004c850  mov     ebx, eax
0x14004c852  test    eax, eax
0x14004c854  js      short loc_14004C823
0x14004c856  mov     rdx, [r14]
0x14004c859  lea     r9, TdiDisconnectHandler
0x14004c860  mov     rcx, [r12]
0x14004c864  mov     r8d, 1
0x14004c86a  mov     [rsp+130h+AllocationSize], rdi
0x14004c86f  call    SetEventHandler
0x14004c874  mov     ebx, eax
0x14004c876  test    eax, eax
0x14004c878  js      short loc_14004C823
0x14004c87a  test    byte ptr [rbp+3Fh+arg_38], 2
0x14004c881  jz      short loc_14004C80C
0x14004c883  mov     rdx, [r14]
0x14004c886  lea     r9, TdiConnectHandler
0x14004c88d  mov     rcx, [r12]
0x14004c891  xor     r8d, r8d
0x14004c894  jmp     loc_14004C7FC
0x14004c899  mov     rcx, [rbp+3Fh+P.Buffer]; P
0x14004c89d  xor     edx, edx; Tag
0x14004c89f  call    cs:__imp_ExFreePoolWithTag
0x14004c8a6  nop     dword ptr [rax+rax+00h]
0x14004c8ab  mov     rcx, rsi; P
0x14004c8ae  xor     edx, edx; Tag
0x14004c8b0  call    cs:__imp_ExFreePoolWithTag
0x14004c8b7  nop     dword ptr [rax+rax+00h]
0x14004c8bc  mov     eax, 0C000009Ah
0x14004c8c1  jmp     loc_14004C80E
0x14004c8c6  test    byte ptr cs:xmmword_140038420, 10h
0x14004c8cd  jz      short loc_14004C8E5
0x14004c8cf  mov     edx, 0Ah
0x14004c8d4  lea     r8, WPP_7ae8357478e63d53ee3c3e10bf466ad5_Traceguids
0x14004c8db  mov     ecx, 404h
0x14004c8e0  call    WPP_SF_
0x14004c8e5  mov     rcx, [rbp+3Fh+P.Buffer]
0x14004c8e9  jmp     short loc_14004C8AE
0x14004c8eb  movzx   r9d, word ptr [rsi+6]
0x14004c8f0  lea     r8, WPP_7ae8357478e63d53ee3c3e10bf466ad5_Traceguids
0x14004c8f7  mov     edx, 0Bh
0x14004c8fc  mov     ecx, 404h
0x14004c901  call    WPP_SF_d
0x14004c906  jmp     loc_14004C5CC
0x14004c90b  movzx   r13d, [rsp+130h+var_C4]
0x14004c911  mov     ecx, [rdi+r8*4+390h]
0x14004c919  inc     r8d
0x14004c91c  bswap   ecx
0x14004c91e  mov     word ptr [rsp+130h+var_D0], r9w
0x14004c924  mov     dword ptr [rsp+130h+var_D0+2], ecx
0x14004c928  movsd   xmm0, [rsp+130h+var_D0]
0x14004c92e  lea     rdx, [r8+r8*2]
0x14004c932  movsd   qword ptr [r15+rdx*2+8], xmm0
0x14004c939  mov     [r15+rdx*2+10h], r11d
0x14004c93e  mov     [r15+rdx*2+14h], r13w
0x14004c944  mov     dword ptr [r15+rdx*2+4], 2000Eh
0x14004c94d  cmp     r8d, [rdi+22Ch]
0x14004c954  jb      short loc_14004C911
0x14004c956  mov     r13d, dword ptr [rbp+3Fh+Object]
0x14004c95a  jmp     loc_14004C632
0x14004c95f  mov     r9, [rbp+3Fh+P.Buffer]
0x14004c963  lea     r8, WPP_7ae8357478e63d53ee3c3e10bf466ad5_Traceguids
0x14004c96a  mov     edx, 0Ch
0x14004c96f  mov     ecx, 404h
0x14004c974  call    WPP_SF_S
0x14004c979  jmp     loc_14004C659
0x14004c97e  mov     r9, [rsp+130h+FileHandle]
0x14004c983  lea     r8, WPP_7ae8357478e63d53ee3c3e10bf466ad5_Traceguids
0x14004c98a  mov     edx, 0Dh
0x14004c98f  mov     dword ptr [rsp+130h+AllocationSize], ebx
0x14004c993  mov     ecx, 411h
0x14004c998  call    WPP_SF_qD
0x14004c99d  jmp     loc_14004C6ED
  ... truncated ...
```
