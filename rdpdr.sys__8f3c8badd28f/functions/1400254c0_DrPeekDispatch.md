# DrPeekDispatch

- ea: `0x1400254c0`
- end: `0x140025c2c`
- name: `DrPeekDispatch`
- size: `1900`
- prototype: `int __fastcall(struct _KDPC *, IRP *)`
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001660`
- `0x140001890`
- `0x140002284`
- `0x14000324c`
- `0x14000327c`
- `0x1400035a0`
- `0x140003b2c`
- `0x140006560`
- `0x140020a7c`
- `0x140020d64`
- `0x1400254c0`
- `0x140027c70`
- `0x14002a1e0`
- `0x14002ac20`
- `0x14002b930`
- `0x14002c618`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400258cc`
- `ntoskrnl!ExAllocatePool2` at `0x1400258cc`
- `ntoskrnl!_wcsnicmp` at `0x1400256e7`
- `ntoskrnl!_wcsnicmp` at `0x1400256e7`
- `ntoskrnl!IofCompleteRequest` at `0x1400255e7`
- `ntoskrnl!IofCompleteRequest` at `0x140025682`
- `ntoskrnl!IofCompleteRequest` at `0x14002573a`
- `ntoskrnl!IofCompleteRequest` at `0x140025822`
- `ntoskrnl!IofCompleteRequest` at `0x140025923`
- `ntoskrnl!IofCompleteRequest` at `0x14002595a`
- `ntoskrnl!IofCompleteRequest` at `0x140025b41`
- `ntoskrnl!IofCompleteRequest` at `0x140025bfb`
- `ntoskrnl!IofCompleteRequest` at `0x1400255e7`
- `ntoskrnl!IofCompleteRequest` at `0x140025682`
- `ntoskrnl!IofCompleteRequest` at `0x14002573a`
- `ntoskrnl!IofCompleteRequest` at `0x140025822`
- `ntoskrnl!IofCompleteRequest` at `0x140025923`
- `ntoskrnl!IofCompleteRequest` at `0x14002595a`
- `ntoskrnl!IofCompleteRequest` at `0x140025b41`
- `ntoskrnl!IofCompleteRequest` at `0x140025bfb`
- `ntoskrnl!IoGetRequestorSessionId` at `0x14002576e`
- `ntoskrnl!IoGetRequestorSessionId` at `0x14002576e`
- `rdbss!RxFsdDispatch` at `0x14002559b`
- `rdbss!RxFsdDispatch` at `0x14002559b`

## pseudocode

```c
int __fastcall DrPeekDispatch(struct _KDPC *a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  UCHAR MajorFunction; // si
  unsigned int i; // eax
  struct _FILE_OBJECT *FileObject; // rbp
  NTSTATUS v8; // ebx
  DWORD LowPart; // ecx
  _WORD *Parameters; // rdx
  unsigned __int16 *v12; // rsi
  _DWORD *UserBuffer; // r14
  unsigned int v14; // eax
  const wchar_t *v15; // rcx
  const wchar_t *v16; // rdx
  PFILE_OBJECT v17; // rcx
  NTSTATUS RequestorSessionId; // eax
  NTSTATUS v19; // r14d
  struct _IO_STACK_LOCATION *v20; // rcx
  UCHAR v21; // al
  __int64 Pool2; // rax
  RefCount *v23; // rbx
  struct _IO_STACK_LOCATION *v24; // rdx
  int v25; // ebx
  IRP *v26; // rcx
  RefCount *FsContext2; // rsi
  int v28; // ebx
  struct _DEVICE_OBJECT *v29; // rcx
  PDEVICE_OBJECT v30; // rcx
  PFILE_OBJECT v31; // rdx
  __int128 v32; // [rsp+20h] [rbp-38h] BYREF
  ULONG pSessionId; // [rsp+68h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  pSessionId = 0;
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( !CurrentStackLocation->MajorFunction && WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.SortKey || !DrReferenceCount )
  {
    a2->IoStatus.Status = -1073741436;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 0);
    return -1073741436;
  }
  if ( a1 == WPP_MAIN_CB.Queue.Wcb.DeviceObject )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
    v20 = a2->Tail.Overlay.CurrentStackLocation;
    v21 = v20->MajorFunction;
    if ( v20->MajorFunction )
    {
      if ( v21 == 2 )
      {
        FsContext2 = (RefCount *)v20->FileObject->FsContext2;
        if ( FsContext2 )
        {
          v28 = CFileVC::Close((CFileVC *)v20, a2);
          RefCount::Release(FsContext2);
          return v28;
        }
        return -1073741585;
      }
      if ( v21 == 14 )
        return CFileVC::DeviceIoControl((CFileVC *)v20, a2);
      v26 = a2;
      if ( v21 == 20 )
      {
        v25 = -1073741808;
        goto LABEL_66;
      }
      v25 = -1073741822;
    }
    else
    {
      Pool2 = ExAllocatePool2(64, 24, 1816552278);
      v23 = (RefCount *)Pool2;
      if ( Pool2 )
      {
        *(_BYTE *)(Pool2 + 8) = 1;
        *(_QWORD *)(Pool2 + 12) = 0;
        *(_QWORD *)Pool2 = &CFileVC::`vftable';
        RefCount::AddRef((RefCount *)Pool2);
        v24 = a2->Tail.Overlay.CurrentStackLocation;
        v24->FileObject->FsContext2 = v23;
        RefCount::AddRef((RefCount *)v24->FileObject->FsContext2);
        a2->IoStatus.Status = 0;
        a2->IoStatus.Information = 0;
        IofCompleteRequest(a2, 0);
        RefCount::Release(v23);
        return 0;
      }
      v25 = -1073741801;
      v26 = a2;
    }
    a2->IoStatus.Information = 0;
LABEL_66:
    a2->IoStatus.Status = v25;
    IofCompleteRequest(v26, 0);
    return v25;
  }
  for ( i = 0; i < 0x10; ++i )
  {
    if ( a1 == (struct _KDPC *)(&DrFakeVidDeviceObject)[i] )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
      return FAKEVID_Dispatch(v29, a2);
    }
  }
  if ( MajorFunction == 14 )
  {
    LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
    if ( ((LowPart - 1311119) & 0xFFFFFFFB) == 0 && !a2->RequestorMode )
    {
      Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
      v32 = 0;
      if ( Parameters )
      {
        if ( LowPart == 1311119 )
        {
          v12 = (unsigned __int16 *)&v32;
          LOWORD(v32) = *Parameters;
          WORD1(v32) = *Parameters;
          *((_QWORD *)&v32 + 1) = Parameters + 8;
        }
        else
        {
          v12 = Parameters + 12;
        }
        UserBuffer = a2->UserBuffer;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids, v12);
        v14 = *v12;
        if ( v14 < 0x12 )
          goto LABEL_30;
        v15 = (const wchar_t *)(*((_QWORD *)v12 + 1) + 2LL);
        v16 = v15;
        if ( v14 >> 1 != 1 )
        {
          do
          {
            if ( *v16 == 92 )
              break;
            ++v16;
          }
          while ( (unsigned int)(v16 - v15) < (v14 >> 1) - 1 );
        }
        if ( (unsigned int)(v16 - v15) != 8 || _wcsnicmp(v15, L"tsclient", 8u) )
        {
LABEL_30:
          a2->IoStatus.Status = -1073741634;
          a2->IoStatus.Information = 0;
          IofCompleteRequest(a2, 0);
          return -1073741634;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
          *UserBuffer = 18;
          a2->IoStatus.Status = 0;
          a2->IoStatus.Information = 4;
          IofCompleteRequest(a2, 0);
          return 0;
        }
      }
    }
  }
  FileObject = CurrentStackLocation->FileObject;
  if ( !MajorFunction
    && !a2->RequestorMode
    && FileObject
    && FileObject->FileName.Length
    && (unsigned int)DrQueryServerName(&FileObject->FileName)
    && (unsigned int)DrQuerySpecialShare(FileObject->FileName.Buffer, FileObject->FileName.Length) )
  {
    a2->IoStatus.Status = -1073741620;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_S(
        WPP_GLOBAL_Control->AttachedDevice,
        77,
        WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids,
        FileObject->FileName.Buffer);
    return -1073741620;
  }
  if ( a1 != WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc && a1 != WPP_MAIN_CB.Queue.Wcb.CurrentIrp )
  {
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
    return RDPDYN_Dispatch(v30, a2);
  }
  if ( a1 == WPP_MAIN_CB.Queue.Wcb.CurrentIrp )
  {
    if ( a1->DeferredRoutine
      || (v31 = CurrentStackLocation->FileObject) != 0 && v31->DeviceObject != WPP_MAIN_CB.Queue.Wcb.CurrentIrp )
    {
      a2->IoStatus.Status = -1073741790;
      a2->IoStatus.Information = 0;
      IofCompleteRequest(a2, 0);
      return -1073741790;
    }
    CurrentStackLocation->DeviceObject = (PDEVICE_OBJECT)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc;
    if ( !CurrentStackLocation->MajorFunction )
      CurrentStackLocation->Parameters.Create.ShareAccess = 7;
  }
  if ( CurrentStackLocation->MajorFunction
    || (v17 = CurrentStackLocation->FileObject, v17->FileName.Length)
    || v17->RelatedFileObject )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        84,
        WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids,
        CurrentStackLocation->MajorFunction);
LABEL_16:
    v8 = RxFsdDispatch((PRDBSS_DEVICE_OBJECT)WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc, a2);
    if ( MajorFunction )
    {
      if ( MajorFunction == 2 && v8 != 259 )
        DrRemoveOpenHandle(FileObject);
    }
    else if ( !v8 )
    {
      ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Blink[2].Flink[1].Blink)(&WPP_MAIN_CB.Queue.ListEntry.Blink[2]);
      DoubleList::CreateEntry((DoubleList *)WPP_MAIN_CB.Queue.ListEntry.Blink, FileObject);
      ++DrReferenceCount;
      ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Blink[2].Flink[2].Flink)(&WPP_MAIN_CB.Queue.ListEntry.Blink[2]);
      return 0;
    }
    return v8;
  }
  RequestorSessionId = IoGetRequestorSessionId(a2, &pSessionId);
  v19 = RequestorSessionId;
  if ( RequestorSessionId >= 0 )
  {
    if ( pSessionId )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids, pSessionId);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
    }
    goto LABEL_16;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      83,
      WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids,
      (unsigned int)RequestorSessionId);
  a2->IoStatus.Status = v19;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  return v19;
}

```

## disassembly

```asm
0x1400254c0  push    rbx
0x1400254c2  push    rsi
0x1400254c3  push    rdi
0x1400254c4  push    r12
0x1400254c6  push    r14
0x1400254c8  sub     rsp, 30h
0x1400254cc  mov     r14, [rdx+0B8h]
0x1400254d3  xor     r12d, r12d
0x1400254d6  mov     [rsp+58h+pSessionId], r12d
0x1400254db  mov     rdi, rdx
0x1400254de  mov     rbx, rcx
0x1400254e1  movzx   esi, byte ptr [r14]
0x1400254e5  test    sil, sil
0x1400254e8  jz      loc_1400255CA
0x1400254ee  cmp     cs:?DrReferenceCount@@3HA, r12d; int DrReferenceCount
0x1400254f5  jz      loc_1400255D7
0x1400254fb  cmp     rbx, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140025502  jz      loc_14002588D
0x140025508  mov     eax, r12d
0x14002550b  lea     rdx, ?DrFakeVidDeviceObject@@3PAPEAU_DEVICE_OBJECT@@A; _DEVICE_OBJECT * near * DrFakeVidDeviceObject
0x140025512  cmp     eax, 10h
0x140025515  jnb     short loc_140025527
0x140025517  mov     ecx, eax
0x140025519  cmp     rbx, [rdx+rcx*8]
0x14002551d  jz      loc_140025A63
0x140025523  inc     eax
0x140025525  jmp     short loc_140025512
0x140025527  cmp     sil, 0Eh
0x14002552b  jz      loc_140025605
0x140025531  mov     [rsp+58h+arg_0], rbp
0x140025536  mov     rbp, [r14+30h]
0x14002553a  mov     [rsp+58h+arg_10], r15
0x14002553f  test    sil, sil
0x140025542  jz      loc_1400257CE
0x140025548  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14002554f  cmp     rbx, rax
0x140025552  jnz     loc_140025ABB
0x140025558  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14002555f  cmp     rbx, rcx
0x140025562  jz      loc_140025B03
0x140025568  movzx   eax, byte ptr [r14]
0x14002556c  test    al, al
0x14002556e  jz      loc_14002574D
0x140025574  mov     rcx, cs:WPP_GLOBAL_Control
0x14002557b  lea     rbx, WPP_GLOBAL_Control
0x140025582  cmp     rcx, rbx
0x140025585  jz      short loc_140025591
0x140025587  cmp     byte ptr [rcx+29h], 4
0x14002558b  jnb     loc_140025C0F
0x140025591  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h; RxDeviceObject
0x140025598  mov     rdx, rdi; Irp
0x14002559b  call    cs:__imp_RxFsdDispatch
0x1400255a2  nop     dword ptr [rax+rax+00h]
0x1400255a7  mov     ebx, eax
0x1400255a9  test    sil, sil
0x1400255ac  jz      loc_140025968
0x1400255b2  cmp     sil, 2
0x1400255b6  jz      loc_1400259C4
0x1400255bc  mov     eax, ebx
0x1400255be  mov     rbp, [rsp+58h+arg_0]
0x1400255c3  mov     r15, [rsp+58h+arg_10]
0x1400255c8  jmp     short loc_1400255F8
0x1400255ca  cmp     dword ptr cs:WPP_MAIN_CB.Queue+10h, r12d
0x1400255d1  jz      loc_1400254EE
0x1400255d7  mov     dword ptr [rdx+30h], 0C0000184h
0x1400255de  mov     rcx, rdi; Irp
0x1400255e1  mov     [rdx+38h], r12
0x1400255e5  xor     edx, edx; PriorityBoost
0x1400255e7  call    cs:__imp_IofCompleteRequest
0x1400255ee  nop     dword ptr [rax+rax+00h]
0x1400255f3  mov     eax, 0C0000184h
0x1400255f8  add     rsp, 30h
0x1400255fc  pop     r14
0x1400255fe  pop     r12
0x140025600  pop     rdi
0x140025601  pop     rsi
0x140025602  pop     rbx
0x140025603  retn
0x140025605  mov     ecx, [r14+18h]
0x140025609  lea     eax, [rcx-14018Fh]
0x14002560f  test    eax, 0FFFFFFFBh
0x140025614  jnz     loc_140025531
0x14002561a  cmp     [rdi+40h], r12b
0x14002561e  jnz     loc_140025531
0x140025624  mov     rdx, [r14+20h]
0x140025628  xorps   xmm0, xmm0
0x14002562b  movups  [rsp+58h+var_38], xmm0
0x140025630  test    rdx, rdx
0x140025633  jz      loc_140025531
0x140025639  cmp     ecx, 14018Fh
0x14002563f  jz      loc_14002586A
0x140025645  lea     rsi, [rdx+18h]
0x140025649  mov     r14, [rdi+70h]
0x14002564d  mov     rcx, cs:WPP_GLOBAL_Control
0x140025654  lea     rbx, WPP_GLOBAL_Control
0x14002565b  cmp     rcx, rbx
0x14002565e  jz      short loc_14002566A
0x140025660  cmp     byte ptr [rcx+29h], 4
0x140025664  jnb     loc_140025A9E
0x14002566a  movzx   eax, word ptr [rsi]
0x14002566d  cmp     eax, 12h
0x140025670  jnb     short loc_1400256A0
0x140025672  xor     edx, edx; PriorityBoost
0x140025674  mov     dword ptr [rdi+30h], 0C00000BEh
0x14002567b  mov     rcx, rdi; Irp
0x14002567e  mov     [rdi+38h], r12
0x140025682  call    cs:__imp_IofCompleteRequest
0x140025689  nop     dword ptr [rax+rax+00h]
0x14002568e  mov     eax, 0C00000BEh
0x140025693  add     rsp, 30h
0x140025697  pop     r14
0x140025699  pop     r12
0x14002569b  pop     rdi
0x14002569c  pop     rsi
0x14002569d  pop     rbx
0x14002569e  retn
0x1400256a0  mov     rcx, [rsi+8]
0x1400256a4  mov     r8d, eax
0x1400256a7  add     rcx, 2; Str1
0x1400256ab  shr     r8d, 1
0x1400256ae  mov     rdx, rcx
0x1400256b1  sub     r8d, 1
0x1400256b5  jz      short loc_1400256CF
0x1400256b7  cmp     word ptr [rdx], 5Ch ; '\'
0x1400256bb  jz      short loc_1400256CF
0x1400256bd  add     rdx, 2
0x1400256c1  mov     rax, rdx
0x1400256c4  sub     rax, rcx
0x1400256c7  sar     rax, 1
0x1400256ca  cmp     eax, r8d
0x1400256cd  jb      short loc_1400256B7
0x1400256cf  sub     rdx, rcx
0x1400256d2  sar     rdx, 1
0x1400256d5  cmp     edx, 8
0x1400256d8  jnz     short loc_140025672
0x1400256da  mov     r8d, 8; MaxCount
0x1400256e0  lea     rdx, aTsclient; "tsclient"
0x1400256e7  call    cs:__imp__wcsnicmp
0x1400256ee  nop     dword ptr [rax+rax+00h]
0x1400256f3  test    eax, eax
0x1400256f5  jnz     loc_140025672
0x1400256fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140025702  cmp     rcx, rbx
0x140025705  jz      short loc_140025722
0x140025707  cmp     byte ptr [rcx+29h], 4
0x14002570b  jb      short loc_140025722
0x14002570d  mov     rcx, [rcx+18h]
0x140025711  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x140025718  mov     edx, 47h ; 'G'
0x14002571d  call    WPP_SF_
0x140025722  mov     dword ptr [r14], 12h
0x140025729  xor     edx, edx; PriorityBoost
0x14002572b  mov     rcx, rdi; Irp
0x14002572e  mov     [rdi+30h], r12d
0x140025732  mov     qword ptr [rdi+38h], 4
0x14002573a  call    cs:__imp_IofCompleteRequest
0x140025741  nop     dword ptr [rax+rax+00h]
0x140025746  xor     eax, eax
0x140025748  jmp     loc_1400255F8
0x14002574d  mov     rcx, [r14+30h]
0x140025751  cmp     [rcx+58h], r12w
0x140025756  jnz     loc_140025574
0x14002575c  cmp     [rcx+40h], r12
0x140025760  jnz     loc_140025574
0x140025766  lea     rdx, [rsp+58h+pSessionId]; pSessionId
0x14002576b  mov     rcx, rdi; Irp
0x14002576e  call    cs:__imp_IoGetRequestorSessionId
0x140025775  nop     dword ptr [rax+rax+00h]
0x14002577a  mov     r14d, eax
0x14002577d  test    eax, eax
0x14002577f  js      loc_140025BBD
0x140025785  mov     r9d, [rsp+58h+pSessionId]
0x14002578a  test    r9d, r9d
0x14002578d  jz      loc_140025B57
0x140025793  mov     rcx, cs:WPP_GLOBAL_Control
0x14002579a  lea     rbx, WPP_GLOBAL_Control
0x1400257a1  cmp     rcx, rbx
0x1400257a4  jz      loc_140025591
0x1400257aa  cmp     byte ptr [rcx+29h], 5
0x1400257ae  jb      loc_140025591
0x1400257b4  mov     rcx, [rcx+18h]
0x1400257b8  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x1400257bf  mov     edx, 52h ; 'R'
0x1400257c4  call    WPP_SF_d
0x1400257c9  jmp     loc_140025591
0x1400257ce  cmp     [rdi+40h], r12b
0x1400257d2  jnz     loc_140025548
0x1400257d8  test    rbp, rbp
0x1400257db  jz      loc_140025548
0x1400257e1  cmp     [rbp+58h], r12w
0x1400257e6  jz      loc_140025548
0x1400257ec  lea     rcx, [rbp+58h]; struct _UNICODE_STRING *
0x1400257f0  call    ?DrQueryServerName@@YAHPEAU_UNICODE_STRING@@@Z; DrQueryServerName(_UNICODE_STRING *)
0x1400257f5  test    eax, eax
0x1400257f7  jz      loc_140025548
0x1400257fd  movzx   edx, word ptr [rbp+58h]; unsigned int
0x140025801  mov     rcx, [rbp+60h]; unsigned __int16 *
0x140025805  call    ?DrQuerySpecialShare@@YAHPEBGK@Z; DrQuerySpecialShare(ushort const *,ulong)
0x14002580a  test    eax, eax
0x14002580c  jz      loc_140025548
0x140025812  xor     edx, edx; PriorityBoost
0x140025814  mov     dword ptr [rdi+30h], 0C00000CCh
0x14002581b  mov     rcx, rdi; Irp
0x14002581e  mov     [rdi+38h], r12
0x140025822  call    cs:__imp_IofCompleteRequest
0x140025829  nop     dword ptr [rax+rax+00h]
0x14002582e  mov     rcx, cs:WPP_GLOBAL_Control
0x140025835  lea     rbx, WPP_GLOBAL_Control
0x14002583c  cmp     rcx, rbx
0x14002583f  jz      short loc_140025860
0x140025841  cmp     byte ptr [rcx+29h], 5
0x140025845  jb      short loc_140025860
0x140025847  mov     r9, [rbp+60h]
0x14002584b  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x140025852  mov     rcx, [rcx+18h]
0x140025856  mov     edx, 4Dh ; 'M'
0x14002585b  call    WPP_SF_S
0x140025860  mov     eax, 0C00000CCh
0x140025865  jmp     loc_1400255BE
0x14002586a  movzx   eax, word ptr [rdx]
0x14002586d  lea     rsi, [rsp+58h+var_38]
0x140025872  mov     word ptr [rsp+58h+var_38], ax
0x140025877  movzx   eax, word ptr [rdx]
0x14002587a  mov     word ptr [rsp+58h+var_38+2], ax
0x14002587f  lea     rax, [rdx+10h]
0x140025883  mov     qword ptr [rsp+58h+var_38+8], rax
0x140025888  jmp     loc_140025649
0x14002588d  mov     rcx, cs:WPP_GLOBAL_Control
0x140025894  lea     rbx, WPP_GLOBAL_Control
0x14002589b  cmp     rcx, rbx
0x14002589e  jz      short loc_1400258AA
0x1400258a0  cmp     byte ptr [rcx+29h], 4
0x1400258a4  jnb     loc_140025A0B
0x1400258aa  mov     rcx, [rdi+0B8h]; this
0x1400258b1  movzx   eax, byte ptr [rcx]
0x1400258b4  test    al, al
0x1400258b6  jnz     loc_140025A25
0x1400258bc  mov     edx, 18h
0x1400258c1  mov     ecx, 40h ; '@'
0x1400258c6  mov     r8d, 6C466356h
0x1400258cc  call    cs:__imp_ExAllocatePool2
0x1400258d3  nop     dword ptr [rax+rax+00h]
0x1400258d8  mov     rbx, rax
0x1400258db  test    rax, rax
0x1400258de  jz      short loc_140025949
0x1400258e0  mov     byte ptr [rax+8], 1
0x1400258e4  mov     rcx, rbx; this
0x1400258e7  mov     [rax+0Ch], r12
0x1400258eb  lea     rax, ??_7CFileVC@@6B@; const CFileVC::`vftable'
0x1400258f2  mov     [rbx], rax
0x1400258f5  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x1400258fa  mov     rdx, [rdi+0B8h]
0x140025901  mov     rcx, [rdx+30h]
0x140025905  mov     [rcx+20h], rbx
0x140025909  mov     rcx, [rdx+30h]
0x14002590d  mov     rcx, [rcx+20h]; this
0x140025911  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140025916  xor     edx, edx; PriorityBoost
0x140025918  mov     [rdi+30h], r12d
0x14002591c  mov     rcx, rdi; Irp
0x14002591f  mov     [rdi+38h], r12
0x140025923  call    cs:__imp_IofCompleteRequest
0x14002592a  nop     dword ptr [rax+rax+00h]
0x14002592f  mov     rcx, rbx; this
0x140025932  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140025937  mov     ebx, r12d
0x14002593a  mov     eax, ebx
0x14002593c  add     rsp, 30h
0x140025940  pop     r14
0x140025942  pop     r12
0x140025944  pop     rdi
0x140025945  pop     rsi
0x140025946  pop     rbx
0x140025947  retn
0x140025949  mov     ebx, 0C0000017h
0x14002594e  xor     edx, edx; PriorityBoost
0x140025950  mov     rcx, rdi; Irp
0x140025953  mov     [rdi+38h], r12
0x140025957  mov     [rdi+30h], ebx
0x14002595a  call    cs:__imp_IofCompleteRequest
0x140025961  nop     dword ptr [rax+rax+00h]
0x140025966  jmp     short loc_14002593A
0x140025968  test    ebx, ebx
0x14002596a  jnz     loc_1400255BC
0x140025970  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140025977  add     rcx, 20h ; ' '
0x14002597b  mov     rax, [rcx]
0x14002597e  mov     rax, [rax+18h]
0x140025982  call    _guard_dispatch_icall
0x140025987  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8; this
0x14002598e  mov     rdx, rbp; void *
0x140025991  call    ?CreateEntry@DoubleList@@QEAAHPEAX@Z; DoubleList::CreateEntry(void *)
0x140025996  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14002599d  inc     cs:?DrReferenceCount@@3HA; int DrReferenceCount
0x1400259a3  add     rcx, 20h ; ' '
0x1400259a7  mov     rax, [rcx]
0x1400259aa  mov     rax, [rax+20h]
0x1400259ae  call    _guard_dispatch_icall
0x1400259b3  mov     rbp, [rsp+58h+arg_0]
0x1400259b8  mov     eax, ebx
  ... truncated ...
```
