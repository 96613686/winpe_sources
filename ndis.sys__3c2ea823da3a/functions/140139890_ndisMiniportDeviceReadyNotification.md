# ndisMiniportDeviceReadyNotification

- ea: `0x140139890`
- end: `0x140139a34`
- name: `ndisMiniportDeviceReadyNotification`
- size: `420`
- prototype: `DRIVER_NOTIFICATION_CALLBACK_ROUTINE`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x14001cf50`
- `0x140056570`
- `0x140062de0`
- `0x1400837ac`
- `0x140139890`
- `0x140156e50`
- `0x140166dc0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140139a13`
- `ntoskrnl!ZwClose` at `0x140139a13`
- `ntoskrnl!ObfDereferenceObject` at `0x140139a03`
- `ntoskrnl!ObfDereferenceObject` at `0x140139a03`
- `ntoskrnl!ZwOpenFile` at `0x14013992b`
- `ntoskrnl!ZwOpenFile` at `0x14013992b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14013996c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14013996c`
- `ntoskrnl!IoFileObjectType` at `0x14013993f`

## pseudocode

```c
__int64 __fastcall ndisMiniportDeviceReadyNotification(char *NotificationStructure, PVOID Context)
{
  __int64 v3; // rax
  PVOID v4; // rdi
  const struct _NDIS_MINIPORT_BLOCK *MiniportByPdo; // rax
  struct _NDIS_MINIPORT_BLOCK *v6; // rbx
  int v7; // edx
  char v8; // cl
  int v9; // r9d
  int v10; // r8d
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *FileHandle; // [rsp+80h] [rbp+10h] BYREF
  PVOID Object; // [rsp+90h] [rbp+20h] BYREF

  v3 = *(_QWORD *)(NotificationStructure + 4) - *(_QWORD *)&GUID_DEVICE_INTERFACE_ARRIVAL.Data1;
  if ( !v3 )
    v3 = *(_QWORD *)(NotificationStructure + 12) - *(_QWORD *)GUID_DEVICE_INTERFACE_ARRIVAL.Data4;
  if ( !v3 )
  {
    CopyPartialStringToBuffer<64>(NotificationStructure, *((_QWORD *)NotificationStructure + 5));
    ObjectAttributes.ObjectName = (PUNICODE_STRING)*((_QWORD *)NotificationStructure + 5);
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.RootDirectory = 0;
    IoStatusBlock = 0;
    FileHandle = 0;
    if ( ZwOpenFile(&FileHandle, 0, &ObjectAttributes, &IoStatusBlock, 3u, 1u) >= 0 )
    {
      Object = 0;
      if ( ObReferenceObjectByHandle(FileHandle, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0) >= 0 )
      {
        v4 = Object;
        MiniportByPdo = (const struct _NDIS_MINIPORT_BLOCK *)ndisFindMiniportByPdo(*((_QWORD *)Object + 1));
        v6 = (struct _NDIS_MINIPORT_BLOCK *)MiniportByPdo;
        if ( MiniportByPdo && !MINIPORT_TEST_FLAG(MiniportByPdo, 0x80u) )
        {
          if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v9 = v7 - 118;
            v10 = v7 - 127;
            LOBYTE(v7) = 4;
            WPP_RECORDER_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              v7,
              v10,
              v9,
              (struct _GUID *)&WPP_afd79cac345434603fc4697a366a014e_Traceguids,
              v8);
          }
          ndisMSetMiniportReadyForBinding(v6, 1, Reason_MiniportDeviceNotStarted, RunAsynchronous);
          ndisNotifyWmiAdapterArrival(v6);
        }
        ObfDereferenceObject(v4);
      }
      ZwClose(FileHandle);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140139890  mov     [rsp-8+arg_8], rbx
0x140139895  mov     [rsp-8+arg_18], rdi
0x14013989a  push    rbp
0x14013989b  mov     rbp, rsp
0x14013989e  sub     rsp, 70h
0x1401398a2  mov     rax, [rcx+4]
0x1401398a6  mov     rbx, rcx
0x1401398a9  sub     rax, qword ptr cs:GUID_DEVICE_INTERFACE_ARRIVAL.Data1
0x1401398b0  jnz     short loc_1401398BD
0x1401398b2  mov     rax, [rcx+0Ch]
0x1401398b6  sub     rax, qword ptr cs:GUID_DEVICE_INTERFACE_ARRIVAL.Data4
0x1401398bd  test    rax, rax
0x1401398c0  jnz     loc_140139A1F
0x1401398c6  mov     rax, ds:0FFFFF78000000008h
0x1401398d0  mov     rdx, [rcx+28h]
0x1401398d4  call    ??$CopyPartialStringToBuffer@$0EA@@@YAXAEAY0EA@_WPEBU_UNICODE_STRING@@@Z; CopyPartialStringToBuffer<64>(wchar_t (&)[64],_UNICODE_STRING const *)
0x1401398d9  mov     rax, [rbx+28h]
0x1401398dd  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1401398e1  xorps   xmm0, xmm0
0x1401398e4  mov     [rsp+70h+OpenOptions], 1; OpenOptions
0x1401398ec  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1401398f0  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1401398f4  xor     edx, edx; DesiredAccess
0x1401398f6  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1401398fe  lea     rcx, [rbp+FileHandle]; FileHandle
0x140139902  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14013990a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14013990f  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140139917  movups  xmmword ptr [rbp+IoStatusBlock.___u0], xmm0
0x14013991b  mov     [rbp+FileHandle], 0
0x140139923  mov     [rsp+70h+ShareAccess], 3; ShareAccess
0x14013992b  call    cs:__imp_ZwOpenFile
0x140139932  nop     dword ptr [rax+rax+00h]
0x140139937  test    eax, eax
0x140139939  js      loc_140139A1F
0x14013993f  mov     r8, cs:__imp_IoFileObjectType
0x140139946  lea     rax, [rbp+Object]
0x14013994a  mov     rcx, [rbp+FileHandle]; Handle
0x14013994e  xor     r9d, r9d; AccessMode
0x140139951  mov     qword ptr [rsp+70h+OpenOptions], 0; HandleInformation
0x14013995a  xor     edx, edx; DesiredAccess
0x14013995c  mov     [rbp+Object], 0
0x140139964  mov     r8, [r8]; ObjectType
0x140139967  mov     qword ptr [rsp+70h+ShareAccess], rax; Object
0x14013996c  call    cs:__imp_ObReferenceObjectByHandle
0x140139973  nop     dword ptr [rax+rax+00h]
0x140139978  test    eax, eax
0x14013997a  js      loc_140139A0F
0x140139980  mov     rdi, [rbp+Object]
0x140139984  mov     rcx, [rdi+8]
0x140139988  call    ndisFindMiniportByPdo
0x14013998d  mov     rbx, rax
0x140139990  test    rax, rax
0x140139993  jz      short loc_140139A00
0x140139995  mov     edx, 80h; unsigned int
0x14013999a  mov     rcx, rax; struct _NDIS_MINIPORT_BLOCK *
0x14013999d  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1401399a2  test    al, al
0x1401399a4  jnz     short loc_140139A00
0x1401399a6  lea     rax, WPP_RECORDER_INITIALIZED
0x1401399ad  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401399b4  jz      short loc_1401399E1
0x1401399b6  mov     qword ptr [rsp+70h+OpenOptions], rcx; char
0x1401399bb  lea     r9d, [rdx-76h]; int
0x1401399bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1401399c6  lea     rax, WPP_afd79cac345434603fc4697a366a014e_Traceguids
0x1401399cd  lea     r8d, [rdx-7Fh]; int
0x1401399d1  mov     qword ptr [rsp+70h+ShareAccess], rax; struct _GUID *
0x1401399d6  mov     dl, 4; int
0x1401399d8  mov     rcx, [rcx+40h]; int
0x1401399dc  call    WPP_RECORDER_SF_q
0x1401399e1  mov     r9d, 1; enum CallRunMode
0x1401399e7  mov     r8d, 80000h; enum NDIS_DO_NOT_BIND_REASON
0x1401399ed  mov     dl, r9b; bool
0x1401399f0  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401399f3  call    ?ndisMSetMiniportReadyForBinding@@YAXPEAU_NDIS_MINIPORT_BLOCK@@_NW4NDIS_DO_NOT_BIND_REASON@@W4CallRunMode@@@Z; ndisMSetMiniportReadyForBinding(_NDIS_MINIPORT_BLOCK *,bool,NDIS_DO_NOT_BIND_REASON,CallRunMode)
0x1401399f8  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401399fb  call    ?ndisNotifyWmiAdapterArrival@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisNotifyWmiAdapterArrival(_NDIS_MINIPORT_BLOCK *)
0x140139a00  mov     rcx, rdi; Object
0x140139a03  call    cs:__imp_ObfDereferenceObject
0x140139a0a  nop     dword ptr [rax+rax+00h]
0x140139a0f  mov     rcx, [rbp+FileHandle]; Handle
0x140139a13  call    cs:__imp_ZwClose
0x140139a1a  nop     dword ptr [rax+rax+00h]
0x140139a1f  lea     r11, [rsp+70h+var_s0]
0x140139a24  xor     eax, eax
0x140139a26  mov     rbx, [r11+18h]
0x140139a2a  mov     rdi, [r11+28h]
0x140139a2e  mov     rsp, r11
0x140139a31  pop     rbp
0x140139a32  retn
```
