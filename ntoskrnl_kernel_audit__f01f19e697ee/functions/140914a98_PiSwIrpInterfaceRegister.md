# PiSwIrpInterfaceRegister

- ea: `0x140914a98`
- end: `0x140914f00`
- name: `PiSwIrpInterfaceRegister`
- size: `1128`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1409112d0`

## callees

- `0x140216db0`
- `0x1402c0a40`
- `0x14036f270`
- `0x1404033d0`
- `0x140471688`
- `0x140524cb4`
- `0x1405e62bc`
- `0x140906194`
- `0x140907f10`
- `0x140909564`
- `0x140911a5c`
- `0x140911cc8`
- `0x14091221c`
- `0x140914a98`
- `0x140916968`
- `0x140916ed4`
- `0x140917440`
- `0x140917488`
- `0x140bb19f0`

## import_xrefs

- `msrpc!MesDecodeBufferHandleCreate` at `0x140914b13`
- `msrpc!MesDecodeBufferHandleCreate` at `0x140914b13`
- `msrpc!RpcExceptionFilter` at `0x140b4478a`
- `msrpc!RpcExceptionFilter` at `0x140b4478a`
- `msrpc!MesHandleFree` at `0x140914c7a`
- `msrpc!MesHandleFree` at `0x140914c7a`
- `msrpc!NdrMesTypeDecode3` at `0x140914b55`
- `msrpc!NdrMesTypeDecode3` at `0x140914b55`

## pseudocode

```c
__int64 __fastcall PiSwIrpInterfaceRegister(PIRP Irp, __int64 a2, int a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  _QWORD *FsContext2; // rsi
  struct _IRP *MasterIrp; // rcx
  int updated; // edi
  __int64 v8; // r8
  int v9; // r9d
  NTSTRSAFE_PCWSTR v10; // r14
  __int64 v11; // rax
  int v12; // ecx
  int v13; // r8d
  int v15; // ecx
  int v16; // r8d
  __int64 v17; // rcx
  __int64 InterfaceEntry; // rax
  _QWORD *v19; // r14
  __int64 v20; // r8
  PVOID v21; // r8
  PVOID *v22; // rcx
  __int64 v23; // rax
  _QWORD *v24; // rcx
  _QWORD *v25; // r14
  PVOID P; // [rsp+30h] [rbp-78h] BYREF
  NTSTRSAFE_PCWSTR pszSrc; // [rsp+38h] [rbp-70h] BYREF
  PVOID v28; // [rsp+40h] [rbp-68h] BYREF
  _QWORD v29[12]; // [rsp+48h] [rbp-60h] BYREF
  char v30; // [rsp+B8h] [rbp+10h]
  int v31; // [rsp+C8h] [rbp+20h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v29[1] = CurrentStackLocation;
  FsContext2 = CurrentStackLocation->FileObject->FsContext2;
  v29[2] = FsContext2;
  v29[0] = 0;
  P = 0;
  v28 = 0;
  pszSrc = 0;
  v31 = 0;
  v30 = 0;
  if ( (byte_140ED9FEC & 0x40) != 0 )
    McTemplateK0zz_EtwWriteTransfer(
      (_DWORD)Irp,
      (unsigned int)KMPnPEvt_SwDevice_RegisterInterface_Start,
      a3,
      FsContext2[1],
      FsContext2[2]);
  v29[3] = &Irp->AssociatedIrp;
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  if ( !MasterIrp )
  {
    updated = -1073741811;
    goto LABEL_52;
  }
  updated = MesDecodeBufferHandleCreate(MasterIrp, CurrentStackLocation->Parameters.Create.Options, v29);
  if ( updated < 0 )
    goto LABEL_17;
  NdrMesTypeDecode3(v29[0], "TP 3\a", &off_140B7B268, &off_140E0A520, 2, &P);
  if ( P )
  {
    if ( *(_QWORD *)P )
    {
      v8 = *((_QWORD *)P + 3);
      if ( (v8 || !*((_DWORD *)P + 4)) && (*((_DWORD *)P + 4) || !v8) )
      {
        updated = PiSwValidatePropertyArray(*((_QWORD *)P + 3));
        if ( updated < 0 )
          goto LABEL_17;
        PiSwLock();
        if ( !(unsigned __int8)PiSwDeviceOperationsAllowed(FsContext2) || (FsContext2[8] & 8) != 0 )
        {
          updated = -1073741637;
        }
        else
        {
          LOBYTE(v9) = 1;
          updated = IopRegisterDeviceInterface(
                      FsContext2[10],
                      *(_QWORD *)P,
                      *((_QWORD *)P + 1),
                      v9,
                      (__int64)&pszSrc,
                      (__int64)&v31);
          if ( updated >= 0 )
          {
            if ( (byte_140ED9FEC & 0x40) != 0 )
              McTemplateK0zzz_EtwWriteTransfer(
                v15,
                (unsigned int)KMPnPEvt_SwDevice_InterfaceRegistered,
                v16,
                FsContext2[1],
                FsContext2[2],
                (__int64)pszSrc);
            v17 = FsContext2[15];
            if ( v17 )
              *(_DWORD *)(v17 + 48) |= v31;
            InterfaceEntry = PiSwDeviceFindInterfaceEntry(FsContext2, pszSrc);
            v19 = (_QWORD *)InterfaceEntry;
            v28 = (PVOID)InterfaceEntry;
            if ( InterfaceEntry )
            {
              updated = PiSwUpdateArrayProperties(
                          *(_QWORD *)(InterfaceEntry + 24),
                          *(unsigned int *)(InterfaceEntry + 32),
                          *((_QWORD *)P + 3),
                          *((unsigned int *)P + 4));
LABEL_35:
              ExReleaseResourceLite(&PiSwLockObj);
              KeLeaveCriticalRegion();
              if ( updated < 0 )
                goto LABEL_52;
              v20 = *((_QWORD *)P + 3);
              if ( v20 )
                updated = PiSwPropertySet(v19[2], 3, v20, *((unsigned int *)P + 4));
              if ( updated < 0 )
                goto LABEL_52;
              PiSwLock();
              v21 = P;
              LOBYTE(v21) = *((_BYTE *)P + 32);
              updated = PiSwDeviceInterfaceSetState(FsContext2, v28, v21);
              goto LABEL_12;
            }
            updated = PiSwInterfaceCreate(pszSrc, *((_QWORD *)P + 3), *((unsigned int *)P + 4), &v28);
            if ( updated >= 0 )
            {
              v22 = (PVOID *)FsContext2[24];
              if ( *v22 != FsContext2 + 23 )
                goto LABEL_44;
              v30 = 1;
              v19 = v28;
              *(_QWORD *)v28 = FsContext2 + 23;
              v19[1] = v22;
              *v22 = v19;
              FsContext2[24] = v19;
              goto LABEL_35;
            }
          }
        }
LABEL_12:
        ExReleaseResourceLite(&PiSwLockObj);
        KeLeaveCriticalRegion();
        if ( updated < 0 )
          goto LABEL_52;
        v10 = pszSrc;
        updated = RtlStringCbCopyW(
                    (NTSTRSAFE_PWSTR)Irp->AssociatedIrp.MasterIrp,
                    CurrentStackLocation->Parameters.Read.Length,
                    pszSrc);
        if ( updated >= 0 )
        {
          v11 = -1;
          do
            ++v11;
          while ( v10[v11] );
          Irp->IoStatus.Information = 2 * v11 + 2;
        }
        goto LABEL_17;
      }
    }
  }
  updated = -1073741811;
LABEL_17:
  if ( updated >= 0 )
    goto LABEL_18;
LABEL_52:
  v25 = v28;
  if ( v28 && v30 )
  {
    PiSwLock();
    v23 = *v25;
    if ( *(_QWORD **)(*v25 + 8LL) == v25 )
    {
      v24 = (_QWORD *)v25[1];
      if ( (_QWORD *)*v24 == v25 )
      {
        *v24 = v23;
        *(_QWORD *)(v23 + 8) = v24;
        ExReleaseResourceLite(&PiSwLockObj);
        KeLeaveCriticalRegion();
        PiSwInterfaceFree(v25);
        goto LABEL_18;
      }
    }
LABEL_44:
    __fastfail(3u);
  }
LABEL_18:
  if ( P )
    ExFreePoolWithTag(P, 0x6370726Bu);
  if ( pszSrc )
    ExFreePoolWithTag((PVOID)pszSrc, 0);
  if ( v29[0] )
    MesHandleFree();
  Irp->IoStatus.Status = updated;
  IofCompleteRequest(Irp, 0);
  if ( (byte_140ED9FEC & 0x40) != 0 )
    McTemplateK0zzd_EtwWriteTransfer(
      v12,
      (unsigned int)KMPnPEvt_SwDevice_RegisterInterface_Stop,
      v13,
      FsContext2[1],
      FsContext2[2],
      updated);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140914a98  mov     r11, rsp
0x140914a9b  mov     [r11+8], rcx
0x140914a9f  push    rbx
0x140914aa0  push    rsi
0x140914aa1  push    rdi
0x140914aa2  push    r12
0x140914aa4  push    r13
0x140914aa6  push    r14
0x140914aa8  push    r15
0x140914aaa  sub     rsp, 70h
0x140914aae  mov     r15, rcx
0x140914ab1  mov     r13, [rcx+0B8h]
0x140914ab8  mov     [rsp+0A8h+var_58], r13
0x140914abd  mov     rax, [r13+30h]
0x140914ac1  mov     rsi, [rax+20h]
0x140914ac5  mov     [rsp+0A8h+var_50], rsi
0x140914aca  xor     ebx, ebx
0x140914acc  mov     [r11-60h], rbx
0x140914ad0  mov     [r11-78h], rbx
0x140914ad4  mov     [r11-68h], rbx
0x140914ad8  mov     [r11-70h], rbx
0x140914adc  mov     [r11+20h], ebx
0x140914ae0  mov     [rsp+0A8h+arg_8], bl
0x140914ae7  test    cs:byte_140ED9FEC, 40h
0x140914aee  jnz     loc_140914E1A
0x140914af4  lea     r12, [r15+18h]
0x140914af8  mov     [rsp+0A8h+var_48], r12
0x140914afd  mov     rcx, [r12]
0x140914b01  test    rcx, rcx
0x140914b04  jz      loc_140914E94
0x140914b0a  lea     r8, [rsp+0A8h+var_60]
0x140914b0f  mov     edx, [r13+10h]
0x140914b13  call    cs:__imp_MesDecodeBufferHandleCreate
0x140914b1a  nop     dword ptr [rax+rax+00h]
0x140914b1f  mov     edi, eax
0x140914b21  test    eax, eax
0x140914b23  js      loc_140914C40
0x140914b29  lea     rax, [rsp+0A8h+P]
0x140914b2e  mov     [rsp+0A8h+var_80], rax
0x140914b33  mov     dword ptr [rsp+0A8h+var_88], 2
0x140914b3b  lea     r9, off_140E0A520
0x140914b42  lea     r8, off_140B7B268
0x140914b49  lea     rdx, aTp3_0; "TP 3\a"
0x140914b50  mov     rcx, [rsp+0A8h+var_60]
0x140914b55  call    cs:__imp_NdrMesTypeDecode3
0x140914b5c  nop     dword ptr [rax+rax+00h]
0x140914b61  jmp     short loc_140914B8E
0x140914b63  mov     edi, eax
0x140914b65  mov     [rsp+0A8h+P], 0
0x140914b6e  xor     ebx, ebx
0x140914b70  mov     r15, [rsp+0A8h+arg_0]
0x140914b78  mov     [rsp+0A8h+arg_8], bl
0x140914b7f  mov     r13, [rsp+0A8h+var_58]
0x140914b84  mov     rsi, [rsp+0A8h+var_50]
0x140914b89  mov     r12, [rsp+0A8h+var_48]
0x140914b8e  test    edi, edi
0x140914b90  js      loc_140914E99
0x140914b96  mov     rcx, [rsp+0A8h+P]
0x140914b9b  test    rcx, rcx
0x140914b9e  jz      loc_140914DB9
0x140914ba4  cmp     [rcx], rbx
0x140914ba7  jz      loc_140914DB9
0x140914bad  mov     r8, [rcx+18h]
0x140914bb1  test    r8, r8
0x140914bb4  jz      loc_140914DB0
0x140914bba  mov     rax, [rsp+0A8h+P]
0x140914bbf  mov     edx, [rax+10h]
0x140914bc2  test    edx, edx
0x140914bc4  jz      loc_140914E0F
0x140914bca  mov     rcx, r8
0x140914bcd  call    PiSwValidatePropertyArray
0x140914bd2  mov     edi, eax
0x140914bd4  test    eax, eax
0x140914bd6  js      short loc_140914C40
0x140914bd8  call    PiSwLock
0x140914bdd  mov     rcx, rsi
0x140914be0  call    PiSwDeviceOperationsAllowed
0x140914be5  test    al, al
0x140914be7  jnz     loc_140914CB4
0x140914bed  mov     edi, 0C00000BBh
0x140914bf2  lea     rcx, PiSwLockObj; Resource
0x140914bf9  call    ExReleaseResourceLite
0x140914bfe  call    KeLeaveCriticalRegion
0x140914c03  test    edi, edi
0x140914c05  js      loc_140914E99
0x140914c0b  mov     edx, [r13+8]; cbDest
0x140914c0f  mov     r14, [rsp+0A8h+pszSrc]
0x140914c14  mov     r8, r14; pszSrc
0x140914c17  mov     rcx, [r12]; pszDest
0x140914c1b  call    RtlStringCbCopyW
0x140914c20  mov     edi, eax
0x140914c22  test    eax, eax
0x140914c24  js      short loc_140914C40
0x140914c26  or      rax, 0FFFFFFFFFFFFFFFFh
0x140914c2a  inc     rax
0x140914c2d  cmp     [r14+rax*2], bx
0x140914c32  jnz     short loc_140914C2A
0x140914c34  lea     rax, ds:2[rax*2]
0x140914c3c  mov     [r15+38h], rax
0x140914c40  test    edi, edi
0x140914c42  js      loc_140914E99
0x140914c48  mov     rcx, [rsp+0A8h+P]; P
0x140914c4d  test    rcx, rcx
0x140914c50  jz      short loc_140914C5C
0x140914c52  mov     edx, 6370726Bh; Tag
0x140914c57  call    ExFreePoolWithTag
0x140914c5c  mov     r14, [rsp+0A8h+pszSrc]
0x140914c61  test    r14, r14
0x140914c64  jz      short loc_140914C70
0x140914c66  xor     edx, edx; Tag
0x140914c68  mov     rcx, r14; P
0x140914c6b  call    ExFreePoolWithTag
0x140914c70  mov     rcx, [rsp+0A8h+var_60]
0x140914c75  test    rcx, rcx
0x140914c78  jz      short loc_140914C86
0x140914c7a  call    cs:__imp_MesHandleFree
0x140914c81  nop     dword ptr [rax+rax+00h]
0x140914c86  mov     [r15+30h], edi
0x140914c8a  xor     edx, edx; PriorityBoost
0x140914c8c  mov     rcx, r15; Irp
0x140914c8f  call    IofCompleteRequest
0x140914c94  test    cs:byte_140ED9FEC, 40h
0x140914c9b  jnz     loc_140914EDE
0x140914ca1  mov     eax, edi
0x140914ca3  add     rsp, 70h
0x140914ca7  pop     r15
0x140914ca9  pop     r14
0x140914cab  pop     r13
0x140914cad  pop     r12
0x140914caf  pop     rdi
0x140914cb0  pop     rsi
0x140914cb1  pop     rbx
0x140914cb2  retn
0x140914cb4  mov     eax, [rsi+40h]
0x140914cb7  test    al, 8
0x140914cb9  jnz     loc_140914BED
0x140914cbf  lea     rax, [rsp+0A8h+arg_18]
0x140914cc7  mov     [rsp+0A8h+var_80], rax
0x140914ccc  lea     rax, [rsp+0A8h+pszSrc]
0x140914cd1  mov     [rsp+0A8h+var_88], rax
0x140914cd6  mov     r9b, 1
0x140914cd9  mov     rdx, [rsp+0A8h+P]
0x140914cde  mov     r8, [rdx+8]
0x140914ce2  mov     rdx, [rdx]
0x140914ce5  mov     rcx, [rsi+50h]
0x140914ce9  call    IopRegisterDeviceInterface
0x140914cee  mov     edi, eax
0x140914cf0  test    eax, eax
0x140914cf2  js      loc_140914BF2
0x140914cf8  test    cs:byte_140ED9FEC, 40h
0x140914cff  jnz     loc_140914EB6
0x140914d05  mov     rcx, [rsi+78h]
0x140914d09  test    rcx, rcx
0x140914d0c  jnz     loc_140914E00
0x140914d12  mov     rdx, [rsp+0A8h+pszSrc]
0x140914d17  mov     rcx, rsi
0x140914d1a  call    PiSwDeviceFindInterfaceEntry
0x140914d1f  mov     r14, rax
0x140914d22  mov     [rsp+0A8h+var_68], rax
0x140914d27  test    rax, rax
0x140914d2a  jz      loc_140914DC3
0x140914d30  mov     r8, [rsp+0A8h+P]
0x140914d35  mov     r9d, [r8+10h]
0x140914d39  mov     r8, [r8+18h]
0x140914d3d  mov     edx, [rax+20h]
0x140914d40  mov     rcx, [rax+18h]
0x140914d44  call    PiSwUpdateArrayProperties
0x140914d49  mov     edi, eax
0x140914d4b  lea     rcx, PiSwLockObj; Resource
0x140914d52  call    ExReleaseResourceLite
0x140914d57  call    KeLeaveCriticalRegion
0x140914d5c  test    edi, edi
0x140914d5e  js      loc_140914E99
0x140914d64  mov     rcx, [rsp+0A8h+P]
0x140914d69  mov     r8, [rcx+18h]
0x140914d6d  test    r8, r8
0x140914d70  jz      short loc_140914D86
0x140914d72  mov     r9d, [rcx+10h]
0x140914d76  mov     edx, 3
0x140914d7b  mov     rcx, [r14+10h]
0x140914d7f  call    PiSwPropertySet
0x140914d84  mov     edi, eax
0x140914d86  test    edi, edi
0x140914d88  js      loc_140914E99
0x140914d8e  call    PiSwLock
0x140914d93  mov     r8, [rsp+0A8h+P]
0x140914d98  mov     r8b, [r8+20h]
0x140914d9c  mov     rdx, [rsp+0A8h+var_68]
0x140914da1  mov     rcx, rsi
0x140914da4  call    PiSwDeviceInterfaceSetState
0x140914da9  mov     edi, eax
0x140914dab  jmp     loc_140914BF2
0x140914db0  cmp     [rcx+10h], ebx
0x140914db3  jz      loc_140914BBA
0x140914db9  mov     edi, 0C000000Dh
0x140914dbe  jmp     loc_140914C40
0x140914dc3  lea     r9, [rsp+0A8h+var_68]
0x140914dc8  mov     rdx, [rsp+0A8h+P]
0x140914dcd  mov     r8d, [rdx+10h]
0x140914dd1  mov     rdx, [rdx+18h]
0x140914dd5  mov     rcx, [rsp+0A8h+pszSrc]
0x140914dda  call    PiSwInterfaceCreate
0x140914ddf  mov     edi, eax
0x140914de1  test    eax, eax
0x140914de3  js      loc_140914BF2
0x140914de9  lea     rax, [rsi+0B8h]
0x140914df0  mov     rcx, [rax+8]
0x140914df4  cmp     [rcx], rax
0x140914df7  jz      short loc_140914E38
0x140914df9  mov     ecx, 3
0x140914dfe  int     29h; Win8: RtlFailFast(ecx)
0x140914e00  mov     eax, [rsp+0A8h+arg_18]
0x140914e07  or      [rcx+30h], eax
0x140914e0a  jmp     loc_140914D12
0x140914e0f  test    r8, r8
0x140914e12  jz      loc_140914BCA
0x140914e18  jmp     short loc_140914DB9
0x140914e1a  mov     rax, [rsi+10h]
0x140914e1e  mov     [rsp+0A8h+var_88], rax
0x140914e23  mov     r9, [rsi+8]
0x140914e27  lea     rdx, KMPnPEvt_SwDevice_RegisterInterface_Start
0x140914e2e  call    McTemplateK0zz_EtwWriteTransfer
0x140914e33  jmp     loc_140914AF4
0x140914e38  mov     [rsp+0A8h+arg_8], 1
0x140914e40  mov     r14, [rsp+0A8h+var_68]
0x140914e45  mov     [r14], rax
0x140914e48  mov     [r14+8], rcx
0x140914e4c  mov     [rcx], r14
0x140914e4f  mov     [rax+8], r14
0x140914e53  jmp     loc_140914D4B
0x140914e58  call    PiSwLock
0x140914e5d  mov     rax, [r14]
0x140914e60  cmp     [rax+8], r14
0x140914e64  jnz     short loc_140914DF9
0x140914e66  mov     rcx, [r14+8]
0x140914e6a  cmp     [rcx], r14
0x140914e6d  jnz     short loc_140914DF9
0x140914e6f  mov     [rcx], rax
0x140914e72  mov     [rax+8], rcx
0x140914e76  lea     rcx, PiSwLockObj; Resource
0x140914e7d  call    ExReleaseResourceLite
0x140914e82  call    KeLeaveCriticalRegion
0x140914e87  mov     rcx, r14; P
0x140914e8a  call    PiSwInterfaceFree
0x140914e8f  jmp     loc_140914C48
0x140914e94  mov     edi, 0C000000Dh
0x140914e99  mov     r14, [rsp+0A8h+var_68]
0x140914e9e  test    r14, r14
0x140914ea1  jz      loc_140914C48
0x140914ea7  cmp     [rsp+0A8h+arg_8], bl
0x140914eae  jz      loc_140914C48
0x140914eb4  jmp     short loc_140914E58
0x140914eb6  mov     rax, [rsp+0A8h+pszSrc]
0x140914ebb  mov     [rsp+0A8h+var_80], rax
0x140914ec0  mov     rax, [rsi+10h]
0x140914ec4  mov     [rsp+0A8h+var_88], rax
0x140914ec9  mov     r9, [rsi+8]
0x140914ecd  lea     rdx, KMPnPEvt_SwDevice_InterfaceRegistered
0x140914ed4  call    McTemplateK0zzz_EtwWriteTransfer
0x140914ed9  jmp     loc_140914D05
0x140914ede  mov     dword ptr [rsp+0A8h+var_80], edi
0x140914ee2  mov     rax, [rsi+10h]
0x140914ee6  mov     [rsp+0A8h+var_88], rax
0x140914eeb  mov     r9, [rsi+8]
0x140914eef  lea     rdx, KMPnPEvt_SwDevice_RegisterInterface_Stop
0x140914ef6  call    McTemplateK0zzd_EtwWriteTransfer
0x140914efb  jmp     loc_140914CA1
0x140b4477c  push    rbp
0x140b4477e  sub     rsp, 30h
0x140b44782  mov     rbp, rdx
0x140b44785  mov     rcx, [rcx]
0x140b44788  mov     ecx, [rcx]; ExceptionCode
0x140b4478a  call    cs:__imp_RpcExceptionFilter
0x140b44791  nop     dword ptr [rax+rax+00h]
0x140b44796  nop
0x140b44797  add     rsp, 30h
0x140b4479b  pop     rbp
0x140b4479c  retn
```
