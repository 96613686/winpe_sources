# RxCreateVNetRoot

- ea: `0x140078a90`
- end: `0x140078e20`
- name: `RxCreateVNetRoot`
- size: `912`
- prototype: `PV_NET_ROOT __stdcall(PRX_CONTEXT RxContext, PNET_ROOT NetRoot, PUNICODE_STRING CanonicalName, PUNICODE_STRING LocalNetRootName, PUNICODE_STRING FilePath, PRX_CONNECTION_ID RxConnectionId)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14004d498`
- `0x14005f400`

## callees

- `0x14000edd0`
- `0x140012840`
- `0x140013ec0`
- `0x140016e20`
- `0x140017370`
- `0x1400210b8`
- `0x14002306c`
- `0x1400597e0`
- `0x14005f110`
- `0x140072450`
- `0x140072630`
- `0x140073a50`
- `0x140078a90`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140078be5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140078be5`

## pseudocode

```c
PV_NET_ROOT __stdcall RxCreateVNetRoot(
        PRX_CONTEXT RxContext,
        PNET_ROOT NetRoot,
        PUNICODE_STRING CanonicalName,
        PUNICODE_STRING LocalNetRootName,
        PUNICODE_STRING FilePath,
        PRX_CONNECTION_ID RxConnectionId)
{
  unsigned int v10; // edi
  char *Object; // rax
  char *v13; // r15
  _QWORD *v14; // rax
  ULONG *v15; // r8
  PUNICODE_STRING *v16; // r9
  NTSTATUS v17; // eax
  __int64 v18; // rcx
  __int64 v19; // r9
  unsigned int v20; // ecx
  __int16 v21; // ax
  __int64 v22; // rcx
  int v23; // eax
  __int16 SerialNumberForEnum; // di
  int v25; // r8d
  BOOLEAN *p_PurgeInProgress; // rbx
  BOOLEAN **v27; // rcx
  int v28; // eax
  PUNICODE_STRING *UserDomainNamePtr; // [rsp+20h] [rbp-58h]
  PUNICODE_STRING *ConnectionId; // [rsp+28h] [rbp-50h]
  ULONG *v31; // [rsp+30h] [rbp-48h]
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF

  DestinationString = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_ZZ(
      WPP_GLOBAL_Control->AttachedDevice,
      45,
      (unsigned int)&WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids,
      (_DWORD)CanonicalName,
      (__int64)LocalNetRootName);
  }
  v10 = NetRoot->PrefixEntry.NodeTypeCode + LocalNetRootName->Length;
  if ( v10 > 0xFFFE )
    return 0;
  Object = (char *)RxAllocateObject(
                     0xEB12u,
                     *(PMINIRDR_DISPATCH *)(*(_QWORD *)(*((_QWORD *)&NetRoot->1 + 4) + 48LL) + 352LL),
                     v10);
  v13 = Object;
  if ( Object )
  {
    v14 = (_QWORD *)(RfsInitializeRundownProtection(Object + 440) + 360);
    v14[1] = v14;
    *v14 = v14;
    *((_QWORD *)v13 + 3) = v13 + 16;
    *((_QWORD *)v13 + 2) = v13 + 16;
    if ( RxConnectionId )
      v17 = RxCopyVNetRootParameters(v13);
    else
      v17 = RxInitializeVNetRootParameters(RxContext, (LUID *)v13, v15, v16, UserDomainNamePtr, ConnectionId, v31);
    if ( v17 )
    {
      RxFinalizeSecurityContext(v13 + 72);
      RxFreeObject(v13);
      v13 = 0;
    }
    else
    {
      v18 = *((_QWORD *)&NetRoot->1 + 4);
      if ( (*(_DWORD *)(v18 + 96) & 0x80u) != 0
        || RxEnableLinkedConnections == (_BYTE)v17
        || (*(_DWORD *)(*(_QWORD *)(v18 + 48) + 336LL) & 0x80u) == 0 )
      {
        *((_QWORD *)v13 + 10) = *((_QWORD *)v13 + 9);
      }
      DestinationString = (UNICODE_STRING)*((_OWORD *)v13 + 14);
      RtlCopyUnicodeString(&DestinationString, CanonicalName);
      v19 = NetRoot->PrefixEntry.NodeTypeCode + (unsigned int)LocalNetRootName->Length;
      *((_DWORD *)v13 + 82) = v19;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, &WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids, v19);
      }
      v20 = *((_DWORD *)v13 + 82);
      *((_QWORD *)v13 + 40) = (char *)DestinationString.Buffer + v20;
      v21 = DestinationString.Length - v20;
      *((_WORD *)v13 + 157) = DestinationString.Length - v20;
      *((_WORD *)v13 + 156) = v21;
      *((_WORD *)v13 + 152) = LocalNetRootName->Length >> 1;
      v22 = *((_QWORD *)&NetRoot->1 + 4);
      v23 = *(_DWORD *)(v22 + 96);
      if ( (v23 & 8) == 0 )
      {
        if ( (v23 & 4) != 0 )
          SerialNumberForEnum = NetRoot->SerialNumberForEnum;
        else
          SerialNumberForEnum = *(_WORD *)(v22 + 140);
        LOWORD(v10) = LocalNetRootName->Length + SerialNumberForEnum;
      }
      RxPrefixTableInsertName(
        (PRX_PREFIX_TABLE)RxContext->NonPagedFcb[1].HeaderResource.SystemResourcesList.Flink,
        (PRX_PREFIX_ENTRY)(v13 + 216),
        v13,
        (PULONG)v13 + 1,
        v10,
        (PRX_CONNECTION_ID)FilePath);
      RxReference(NetRoot);
      if ( ((__int64)RxContext->RdbssDbgExtension & 0x800) != 0 )
        *((_DWORD *)v13 + 14) |= 0x40u;
      *((_QWORD *)v13 + 4) = NetRoot;
      ++*((_DWORD *)&NetRoot->1 + 17);
      if ( (*((_DWORD *)v13 + 14) & 0x40) != 0 )
        ++*((_DWORD *)&NetRoot->1 + 18);
      p_PurgeInProgress = &NetRoot->PurgeSyncronizationContext.PurgeInProgress;
      v27 = (BOOLEAN **)*((_QWORD *)p_PurgeInProgress + 1);
      if ( *v27 != p_PurgeInProgress )
        __fastfail(3u);
      *((_QWORD *)v13 + 42) = p_PurgeInProgress;
      *((_QWORD *)v13 + 43) = v27;
      *v27 = (BOOLEAN *)(v13 + 336);
      *((_QWORD *)p_PurgeInProgress + 1) = v13 + 336;
      v28 = SerialNumber;
      *((_DWORD *)v13 + 88) = SerialNumber;
      SerialNumber = v28 + 1;
      *((_WORD *)v13 + 100) = 0;
      v13[202] = 0;
      *((_DWORD *)v13 + 53) = 0;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return (PV_NET_ROOT)v13;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_qiiZ(
          WPP_GLOBAL_Control->AttachedDevice,
          47,
          v25,
          (_DWORD)v13,
          *(_QWORD *)&FilePath->Length,
          (char)FilePath->Buffer,
          (__int64)(v13 + 224));
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 48, &WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids);
  }
  return (PV_NET_ROOT)v13;
}

```

## disassembly

```asm
0x140078a90  push    rbx
0x140078a92  push    rbp
0x140078a93  push    rsi
0x140078a94  push    rdi
0x140078a95  push    r14
0x140078a97  sub     rsp, 50h
0x140078a9b  xorps   xmm0, xmm0
0x140078a9e  mov     rsi, r9
0x140078aa1  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x140078aa6  mov     rbp, r8
0x140078aa9  mov     rbx, rdx
0x140078aac  mov     r14, rcx
0x140078aaf  mov     rcx, cs:WPP_GLOBAL_Control
0x140078ab6  lea     rax, WPP_GLOBAL_Control
0x140078abd  cmp     rcx, rax
0x140078ac0  jz      short loc_140078AEC
0x140078ac2  mov     eax, [rcx+2Ch]
0x140078ac5  test    al, al
0x140078ac7  jns     short loc_140078AEC
0x140078ac9  cmp     byte ptr [rcx+29h], 2
0x140078acd  jb      short loc_140078AEC
0x140078acf  mov     rcx, [rcx+18h]
0x140078ad3  mov     edx, 2Dh ; '-'
0x140078ad8  mov     [rsp+78h+UserDomainNamePtr], r9; UserDomainNamePtr
0x140078add  mov     r9, r8
0x140078ae0  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x140078ae7  call    WPP_SF_ZZ
0x140078aec  movzx   edi, word ptr [rsi]
0x140078aef  movzx   eax, word ptr [rbx+0D8h]
0x140078af6  add     edi, eax
0x140078af8  cmp     edi, 0FFFEh
0x140078afe  jbe     short loc_140078B0E
0x140078b00  xor     eax, eax
0x140078b02  add     rsp, 50h
0x140078b06  pop     r14
0x140078b08  pop     rdi
0x140078b09  pop     rsi
0x140078b0a  pop     rbp
0x140078b0b  pop     rbx
0x140078b0c  retn
0x140078b0e  mov     rax, [rbx+20h]
0x140078b12  mov     ecx, 0EB12h; NodeType
0x140078b17  mov     [rsp+78h+arg_0], r12
0x140078b1f  mov     r8d, edi; NameLength
0x140078b22  mov     [rsp+78h+arg_8], r13
0x140078b2a  xor     r12d, r12d
0x140078b2d  mov     [rsp+78h+arg_10], r15
0x140078b35  mov     rdx, [rax+30h]
0x140078b39  mov     rdx, [rdx+160h]; MRxDispatch
0x140078b40  call    RxAllocateObject
0x140078b45  mov     r15, rax
0x140078b48  test    rax, rax
0x140078b4b  jz      loc_140078DA9
0x140078b51  lea     rcx, [rax+1B8h]
0x140078b58  call    RfsInitializeRundownProtection
0x140078b5d  mov     rdx, [rsp+78h+RxConnectionId]
0x140078b65  add     rax, 168h
0x140078b6b  mov     [rax+8], rax
0x140078b6f  mov     [rax], rax
0x140078b72  lea     rax, [r15+10h]
0x140078b76  mov     [rax+8], rax
0x140078b7a  mov     [rax], rax
0x140078b7d  test    rdx, rdx
0x140078b80  jnz     short loc_140078B8F
0x140078b82  mov     rdx, r15; LogonId
0x140078b85  mov     rcx, r14; RxContext
0x140078b88  call    RxInitializeVNetRootParameters
0x140078b8d  jmp     short loc_140078B97
0x140078b8f  mov     rcx, r15
0x140078b92  call    RxCopyVNetRootParameters
0x140078b97  mov     r12d, eax
0x140078b9a  test    eax, eax
0x140078b9c  jnz     loc_140078D95
0x140078ba2  mov     rcx, [rbx+20h]
0x140078ba6  mov     eax, [rcx+60h]
0x140078ba9  test    al, al
0x140078bab  js      short loc_140078BC4
0x140078bad  cmp     cs:RxEnableLinkedConnections, r12b
0x140078bb4  jz      short loc_140078BC4
0x140078bb6  mov     rax, [rcx+30h]
0x140078bba  mov     ecx, [rax+150h]
0x140078bc0  test    cl, cl
0x140078bc2  js      short loc_140078BCC
0x140078bc4  mov     rax, [r15+48h]
0x140078bc8  mov     [r15+50h], rax
0x140078bcc  lea     r13, [r15+0E0h]
0x140078bd3  mov     rdx, rbp; SourceString
0x140078bd6  movups  xmm0, xmmword ptr [r13+0]
0x140078bdb  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x140078be0  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x140078be5  call    cs:__imp_RtlCopyUnicodeString
0x140078bec  nop     dword ptr [rax+rax+00h]
0x140078bf1  movzx   r9d, word ptr [rsi]
0x140078bf5  movzx   eax, word ptr [rbx+0D8h]
0x140078bfc  add     r9d, eax
0x140078bff  mov     [r15+148h], r9d
0x140078c06  mov     rcx, cs:WPP_GLOBAL_Control
0x140078c0d  lea     rbp, WPP_GLOBAL_Control
0x140078c14  cmp     rcx, rbp
0x140078c17  jz      short loc_140078C3B
0x140078c19  mov     eax, [rcx+2Ch]
0x140078c1c  test    al, al
0x140078c1e  jns     short loc_140078C3B
0x140078c20  cmp     byte ptr [rcx+29h], 4
0x140078c24  jb      short loc_140078C3B
0x140078c26  mov     rcx, [rcx+18h]
0x140078c2a  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x140078c31  mov     edx, 2Eh ; '.'
0x140078c36  call    WPP_SF_d
0x140078c3b  mov     ecx, [r15+148h]
0x140078c42  mov     eax, ecx
0x140078c44  add     rax, [rsp+78h+DestinationString.Buffer]
0x140078c49  mov     [r15+140h], rax
0x140078c50  movzx   eax, [rsp+78h+DestinationString.Length]
0x140078c55  sub     ax, cx
0x140078c58  mov     [r15+13Ah], ax
0x140078c60  mov     [r15+138h], ax
0x140078c68  movzx   eax, word ptr [rsi]
0x140078c6b  shr     ax, 1
0x140078c6e  mov     [r15+130h], ax
0x140078c76  mov     rcx, [rbx+20h]
0x140078c7a  mov     eax, [rcx+60h]
0x140078c7d  test    al, 8
0x140078c7f  jnz     short loc_140078C98
0x140078c81  test    al, 4
0x140078c83  jz      short loc_140078C8E
0x140078c85  movzx   edi, word ptr [rbx+0D4h]
0x140078c8c  jmp     short loc_140078C95
0x140078c8e  movzx   edi, word ptr [rcx+8Ch]
0x140078c95  add     di, [rsi]
0x140078c98  mov     rcx, [r14+50h]
0x140078c9c  lea     r9, [r15+4]; ContainerRefCount
0x140078ca0  mov     rsi, [rsp+78h+FilePath]
0x140078ca8  lea     rdx, [r15+0D8h]; ThisEntry
0x140078caf  mov     [rsp+78h+ConnectionId], rsi; ConnectionId
0x140078cb4  mov     r8, r15; Container
0x140078cb7  mov     word ptr [rsp+78h+UserDomainNamePtr], di; CaseInsensitiveLength
0x140078cbc  mov     rcx, [rcx+1F8h]; ThisTable
0x140078cc3  call    RxPrefixTableInsertName
0x140078cc8  mov     rcx, rbx; Instance
0x140078ccb  call    RxReference
0x140078cd0  test    dword ptr [r14+78h], 800h
0x140078cd8  jz      short loc_140078CDF
0x140078cda  or      dword ptr [r15+38h], 40h
0x140078cdf  mov     [r15+20h], rbx
0x140078ce3  inc     dword ptr [rbx+44h]
0x140078ce6  mov     eax, [r15+38h]
0x140078cea  test    al, 40h
0x140078cec  jz      short loc_140078CF1
0x140078cee  inc     dword ptr [rbx+48h]
0x140078cf1  add     rbx, 0B0h
0x140078cf8  mov     rcx, [rbx+8]
0x140078cfc  cmp     [rcx], rbx
0x140078cff  jz      short loc_140078D08
0x140078d01  mov     ecx, 3
0x140078d06  int     29h; Win8: RtlFailFast(ecx)
0x140078d08  lea     rax, [r15+150h]
0x140078d0f  mov     [rax], rbx
0x140078d12  mov     [rax+8], rcx
0x140078d16  mov     [rcx], rax
0x140078d19  mov     [rbx+8], rax
0x140078d1d  mov     eax, cs:SerialNumber
0x140078d23  mov     [r15+160h], eax
0x140078d2a  inc     eax
0x140078d2c  mov     cs:SerialNumber, eax
0x140078d32  mov     word ptr [r15+0C8h], 0
0x140078d3c  mov     byte ptr [r15+0CAh], 0
0x140078d44  mov     dword ptr [r15+0D4h], 0
0x140078d4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140078d56  cmp     rcx, rbp
0x140078d59  jz      loc_140078DE6
0x140078d5f  mov     eax, [rcx+2Ch]
0x140078d62  test    al, al
0x140078d64  jns     short loc_140078DB0
0x140078d66  cmp     byte ptr [rcx+29h], 2
0x140078d6a  jb      short loc_140078DB0
0x140078d6c  mov     rax, [rsi+8]
0x140078d70  mov     edx, 2Fh ; '/'
0x140078d75  mov     rcx, [rcx+18h]
0x140078d79  mov     r9, r15
0x140078d7c  mov     [rsp+78h+var_48], r13
0x140078d81  mov     [rsp+78h+ConnectionId], rax
0x140078d86  mov     rax, [rsi]
0x140078d89  mov     [rsp+78h+UserDomainNamePtr], rax
0x140078d8e  call    WPP_SF_qiiZ
0x140078d93  jmp     short loc_140078DB0
0x140078d95  lea     rcx, [r15+48h]
0x140078d99  call    RxFinalizeSecurityContext
0x140078d9e  mov     rcx, r15; pObject
0x140078da1  call    RxFreeObject
0x140078da6  xor     r15d, r15d
0x140078da9  lea     rbp, WPP_GLOBAL_Control
0x140078db0  mov     rcx, cs:WPP_GLOBAL_Control
0x140078db7  cmp     rcx, rbp
0x140078dba  jz      short loc_140078DE6
0x140078dbc  mov     eax, [rcx+2Ch]
0x140078dbf  test    al, al
0x140078dc1  jns     short loc_140078DE6
0x140078dc3  cmp     byte ptr [rcx+29h], 4
0x140078dc7  jb      short loc_140078DE6
0x140078dc9  mov     rcx, [rcx+18h]
0x140078dcd  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x140078dd4  mov     edx, 30h ; '0'
0x140078dd9  mov     dword ptr [rsp+78h+UserDomainNamePtr], r12d
0x140078dde  mov     r9, r15
0x140078de1  call    WPP_SF_qD
0x140078de6  mov     r13, [rsp+78h+arg_8]
0x140078dee  mov     rax, r15
0x140078df1  mov     r15, [rsp+78h+arg_10]
0x140078df9  mov     r12, [rsp+78h+arg_0]
0x140078e01  add     rsp, 50h
0x140078e05  pop     r14
0x140078e07  pop     rdi
0x140078e08  pop     rsi
0x140078e09  pop     rbp
0x140078e0a  pop     rbx
0x140078e0b  retn
```
