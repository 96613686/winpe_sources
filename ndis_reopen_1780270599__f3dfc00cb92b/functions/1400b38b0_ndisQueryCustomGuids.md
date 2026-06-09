# ndisQueryCustomGuids

- ea: `0x1400b38b0`
- end: `0x1400b3c61`
- name: `ndisQueryCustomGuids`
- size: `945`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_OID_REQUEST *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005fc80`

## callees

- `0x1400110b0`
- `0x1400114b0`
- `0x14003f0e0`
- `0x140088a2c`
- `0x1400b38b0`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400b3ba0`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b3ba0`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400b3b8a`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400b3b8a`
- `ntoskrnl!IoWMIOpenBlock` at `0x1400b3b68`
- `ntoskrnl!IoWMIOpenBlock` at `0x1400b3b68`
- `ntoskrnl!EtwActivityIdControl` at `0x1400b3946`
- `ntoskrnl!EtwActivityIdControl` at `0x1400b3946`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3bce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3bce`
- `ntoskrnl!ExAllocatePool2` at `0x1400b39d4`
- `ntoskrnl!ExAllocatePool2` at `0x1400b39d4`

## pseudocode

```c
__int64 __fastcall ndisQueryCustomGuids(
        struct _NDIS_MINIPORT_BLOCK *a1,
        struct _NDIS_OID_REQUEST *a2,
        _QWORD *a3,
        _WORD *a4)
{
  unsigned __int16 v4; // r15
  struct _NDIS_OID_REQUEST *v7; // rdi
  unsigned __int128 v9; // rax
  UINT MethodId_low; // r14d
  unsigned __int64 v11; // rbx
  char *v12; // rbp
  NTSTATUS SetMiniport; // edi
  int v14; // edx
  unsigned __int16 v15; // dx
  __int64 v16; // rax
  char *v17; // r9
  int v18; // ecx
  char near **v19; // r14
  PVOID DataBlockObject; // [rsp+98h] [rbp+10h] BYREF

  v4 = 0;
  DataBlockObject = 0;
  v7 = a2;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)a2,
      18,
      13,
      (struct _GUID *)&WPP_016ec685c1db3aefc7ddcf22ff746e69_Traceguids,
      (char)a1);
  }
  *a3 = 0;
  *a4 = 0;
  memset(v7, 0, 0xF8u);
  *(_DWORD *)&v7->NdisReserved[16] = 8;
  *(_QWORD *)&v7->NdisReserved[32] = &ndisIntReqWmi;
  EtwActivityIdControl(3u, (LPGUID)&v7->NdisReserved[96]);
  *(_QWORD *)&v7->Header.Type = 15466902;
  v7->DATA.QUERY_INFORMATION.Oid = 65815;
  v7->PortNumber = 0;
  v7->DATA.QUERY_INFORMATION.InformationBuffer = 0;
  v7->DATA.QUERY_INFORMATION.InformationBufferLength = 0;
  if ( (((unsigned int)ndisQuerySetMiniport(a1, 0, v7, 0, 0) + 1073676268) & 0xFFFFFFFD) == 0 )
  {
    MethodId_low = LOWORD(v7->DATA.METHOD_INFORMATION.MethodId);
    if ( (_WORD)MethodId_low )
    {
      v9 = LOWORD(v7->DATA.METHOD_INFORMATION.MethodId) * (unsigned __int128)0x2492492492492493uLL;
      v11 = (*((_QWORD *)&v9 + 1)
           + (((unsigned __int64)LOWORD(v7->DATA.METHOD_INFORMATION.MethodId) - *((_QWORD *)&v9 + 1)) >> 1)) >> 4;
      if ( (_WORD)v11 )
      {
        *(_QWORD *)&v9 = ExAllocatePool2(64, LOWORD(v7->DATA.METHOD_INFORMATION.MethodId), 829899854);
        v12 = (char *)v9;
        if ( !(_QWORD)v9 )
        {
          if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            BYTE8(v9) = 2;
            WPP_RECORDER_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              SDWORD2(v9),
              18,
              15,
              (struct _GUID *)&WPP_016ec685c1db3aefc7ddcf22ff746e69_Traceguids,
              (char)a1);
          }
          SetMiniport = -1073741670;
          goto LABEL_34;
        }
        v7->DATA.QUERY_INFORMATION.InformationBuffer = (PVOID)v9;
        v7->DATA.QUERY_INFORMATION.InformationBufferLength = MethodId_low;
        SetMiniport = ndisQuerySetMiniport(a1, 0, v7, 0, 0);
        if ( SetMiniport )
        {
          if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v14) = 2;
            WPP_RECORDER_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              v14,
              18,
              16,
              (struct _GUID *)&WPP_016ec685c1db3aefc7ddcf22ff746e69_Traceguids,
              (char)a1);
          }
LABEL_30:
          ExFreePoolWithTag(v12, 0);
          goto LABEL_34;
        }
        if ( MINIPORT_TEST_FLAG(a1, 0x20000u) )
        {
          v15 = 0;
          do
          {
            v16 = v15++;
            *(_DWORD *)&v12[28 * v16 + 24] |= 0x10000000u;
          }
          while ( v15 < (unsigned __int16)v11 );
        }
        if ( a1->MajorNdisVersion < 6u )
        {
          do
          {
            v17 = &v12[28 * v4];
            v18 = *((_DWORD *)v17 + 6);
            if ( (v17[24] & 0x60) == 0x60 )
            {
              v19 = &AllUsersReadWriteSecurityDescriptor;
            }
            else if ( (v18 & 0x20) != 0 )
            {
              v19 = &AllUsersReadSecurityDescriptor;
            }
            else
            {
              v19 = &AllUsersWriteSecurityDescriptor;
              if ( (v18 & 0x40) == 0 )
                v19 = &AdminsSecurityDescriptor;
            }
            *((_DWORD *)v17 + 6) = v18 | 0x8000000;
            SetMiniport = IoWMIOpenBlock((LPCGUID)&v12[28 * v4], 0x40000u, &DataBlockObject);
            if ( SetMiniport >= 0 )
            {
              SetMiniport = ObSetSecurityObjectByPointer(DataBlockObject, 7, v19);
              ObfDereferenceObject(DataBlockObject);
            }
            ++v4;
          }
          while ( v4 < (unsigned __int16)v11 );
          if ( SetMiniport )
            goto LABEL_30;
        }
        else
        {
          DWORD2(v9) = 0;
          do
          {
            *(_QWORD *)&v9 = WORD4(v9);
            ++WORD4(v9);
            *(_DWORD *)&v12[28 * v9 + 24] |= 0x8000000u;
          }
          while ( WORD4(v9) < (unsigned __int16)v11 );
        }
        *a4 = v11;
        *a3 = v12;
        goto LABEL_34;
      }
    }
  }
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    BYTE8(v9) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      SDWORD2(v9),
      18,
      14,
      (struct _GUID *)&WPP_016ec685c1db3aefc7ddcf22ff746e69_Traceguids,
      (char)a1);
  }
  SetMiniport = -1073741637;
LABEL_34:
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    BYTE8(v9) = 4;
    WPP_RECORDER_SF_qL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      SDWORD2(v9),
      18,
      17,
      (struct _GUID *)&WPP_016ec685c1db3aefc7ddcf22ff746e69_Traceguids,
      (char)a1,
      SetMiniport);
  }
  return (unsigned int)SetMiniport;
}

```

## disassembly

```asm
0x1400b38b0  mov     r11, rsp
0x1400b38b3  push    rbx
0x1400b38b4  push    rbp
0x1400b38b5  push    rsi
0x1400b38b6  push    rdi
0x1400b38b7  push    r12
0x1400b38b9  push    r13
0x1400b38bb  push    r14
0x1400b38bd  push    r15
0x1400b38bf  sub     rsp, 48h
0x1400b38c3  xor     r15d, r15d
0x1400b38c6  mov     r12, r9
0x1400b38c9  mov     [r11+10h], r15
0x1400b38cd  mov     r13, r8
0x1400b38d0  mov     rdi, rdx
0x1400b38d3  mov     rsi, rcx
0x1400b38d6  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b38dd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b38e4  lea     rbp, WPP_016ec685c1db3aefc7ddcf22ff746e69_Traceguids
0x1400b38eb  jz      short loc_1400B390F
0x1400b38ed  mov     [r11-60h], rcx
0x1400b38f1  lea     r9d, [r15+0Dh]; int
0x1400b38f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b38fc  lea     r8d, [r15+12h]; int
0x1400b3900  mov     dl, 4; int
0x1400b3902  mov     [r11-68h], rbp
0x1400b3906  mov     rcx, [rcx+40h]; int
0x1400b390a  call    WPP_RECORDER_SF_q
0x1400b390f  xor     edx, edx; Val
0x1400b3911  mov     [r13+0], r15
0x1400b3915  mov     r8d, 0F8h; Size
0x1400b391b  mov     [r12], r15w
0x1400b3920  mov     rcx, rdi; void *
0x1400b3923  call    memset
0x1400b3928  lea     rax, ?ndisIntReqWmi@@3U_NDIS_INTERNAL_REQUEST_OBJECT@@A; _NDIS_INTERNAL_REQUEST_OBJECT ndisIntReqWmi
0x1400b392f  mov     dword ptr [rdi+58h], 8
0x1400b3936  lea     rdx, [rdi+0A8h]; ActivityId
0x1400b393d  mov     [rdi+68h], rax
0x1400b3941  mov     ecx, 3; ControlCode
0x1400b3946  call    cs:__imp_EtwActivityIdControl
0x1400b394d  nop     dword ptr [rax+rax+00h]
0x1400b3952  xor     r9d, r9d; unsigned __int8
0x1400b3955  mov     qword ptr [rdi], 0EC0196h
0x1400b395c  mov     r8, rdi; struct _NDIS_OID_REQUEST *
0x1400b395f  mov     dword ptr [rdi+20h], 10117h
0x1400b3966  xor     edx, edx; struct _NDIS_CO_VC_PTR_BLOCK *
0x1400b3968  mov     [rdi+8], r15d
0x1400b396c  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x1400b396f  mov     [rdi+28h], r15
0x1400b3973  mov     [rdi+30h], r15d
0x1400b3977  mov     [rsp+88h+var_68], r15; struct _NDIS_FILTER_BLOCK *
0x1400b397c  call    ?ndisQuerySetMiniport@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_CO_VC_PTR_BLOCK@@PEAU_NDIS_OID_REQUEST@@EPEAU_NDIS_FILTER_BLOCK@@@Z; ndisQuerySetMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_CO_VC_PTR_BLOCK *,_NDIS_OID_REQUEST *,uchar,_NDIS_FILTER_BLOCK *)
0x1400b3981  add     eax, 3FFEFFECh
0x1400b3986  test    eax, 0FFFFFFFDh
0x1400b398b  jnz     loc_1400B3BDF
0x1400b3991  movzx   r14d, word ptr [rdi+38h]
0x1400b3996  cmp     r15w, r14w
0x1400b399a  jz      loc_1400B3BDF
0x1400b39a0  mov     rax, 2492492492492493h
0x1400b39aa  mov     ebx, r14d
0x1400b39ad  mul     r14
0x1400b39b0  sub     rbx, rdx
0x1400b39b3  shr     rbx, 1
0x1400b39b6  add     rbx, rdx
0x1400b39b9  shr     rbx, 4
0x1400b39bd  test    bx, bx
0x1400b39c0  jz      loc_1400B3BDF
0x1400b39c6  mov     r8d, 3177444Eh
0x1400b39cc  mov     edx, r14d
0x1400b39cf  mov     ecx, 40h ; '@'
0x1400b39d4  call    cs:__imp_ExAllocatePool2
0x1400b39db  nop     dword ptr [rax+rax+00h]
0x1400b39e0  mov     rbp, rax
0x1400b39e3  test    rax, rax
0x1400b39e6  jnz     short loc_1400B3A2D
0x1400b39e8  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400b39ef  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400b39f6  lea     rbp, WPP_016ec685c1db3aefc7ddcf22ff746e69_Traceguids
0x1400b39fd  jz      short loc_1400B3A23
0x1400b39ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3a06  lea     r9d, [rax+0Fh]; int
0x1400b3a0a  mov     qword ptr [rsp+88h+var_60], rsi; char
0x1400b3a0f  lea     r8d, [rax+12h]; int
0x1400b3a13  mov     dl, 2; int
0x1400b3a15  mov     [rsp+88h+var_68], rbp; struct _GUID *
0x1400b3a1a  mov     rcx, [rcx+40h]; int
0x1400b3a1e  call    WPP_RECORDER_SF_q
0x1400b3a23  mov     edi, 0C000009Ah
0x1400b3a28  jmp     loc_1400B3C1A
0x1400b3a2d  xor     r9d, r9d; unsigned __int8
0x1400b3a30  mov     [rdi+28h], rbp
0x1400b3a34  mov     r8, rdi; struct _NDIS_OID_REQUEST *
0x1400b3a37  mov     [rdi+30h], r14d
0x1400b3a3b  xor     edx, edx; struct _NDIS_CO_VC_PTR_BLOCK *
0x1400b3a3d  mov     [rsp+88h+var_68], r15; struct _NDIS_FILTER_BLOCK *
0x1400b3a42  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x1400b3a45  call    ?ndisQuerySetMiniport@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_CO_VC_PTR_BLOCK@@PEAU_NDIS_OID_REQUEST@@EPEAU_NDIS_FILTER_BLOCK@@@Z; ndisQuerySetMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_CO_VC_PTR_BLOCK *,_NDIS_OID_REQUEST *,uchar,_NDIS_FILTER_BLOCK *)
0x1400b3a4a  mov     edi, eax
0x1400b3a4c  test    eax, eax
0x1400b3a4e  jz      short loc_1400B3A96
0x1400b3a50  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400b3a57  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400b3a5e  jz      loc_1400B3BC9
0x1400b3a64  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3a6b  lea     rax, WPP_016ec685c1db3aefc7ddcf22ff746e69_Traceguids
0x1400b3a72  mov     r9d, 10h; int
0x1400b3a78  mov     qword ptr [rsp+88h+var_60], rsi; char
0x1400b3a7d  mov     dl, 2; int
0x1400b3a7f  mov     [rsp+88h+var_68], rax; struct _GUID *
0x1400b3a84  mov     rcx, [rcx+40h]; int
0x1400b3a88  lea     r8d, [r9+2]; int
0x1400b3a8c  call    WPP_RECORDER_SF_q
0x1400b3a91  jmp     loc_1400B3BC9
0x1400b3a96  mov     edx, 20000h; unsigned int
0x1400b3a9b  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x1400b3a9e  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1400b3aa3  test    al, al
0x1400b3aa5  jz      short loc_1400B3AC5
0x1400b3aa7  mov     edx, r15d
0x1400b3aaa  cmp     r15w, bx
0x1400b3aae  jnb     short loc_1400B3AC5
0x1400b3ab0  movzx   eax, dx
0x1400b3ab3  inc     dx
0x1400b3ab6  imul    rcx, rax, 1Ch
0x1400b3aba  bts     dword ptr [rcx+rbp+18h], 1Ch
0x1400b3ac0  cmp     dx, bx
0x1400b3ac3  jb      short loc_1400B3AB0
0x1400b3ac5  cmp     byte ptr [rsi+20h], 6
0x1400b3ac9  jb      short loc_1400B3B05
0x1400b3acb  mov     edx, r15d
0x1400b3ace  cmp     r15w, bx
0x1400b3ad2  jnb     short loc_1400B3AE9
0x1400b3ad4  movzx   eax, dx
0x1400b3ad7  inc     dx
0x1400b3ada  imul    rcx, rax, 1Ch
0x1400b3ade  bts     dword ptr [rcx+rbp+18h], 1Bh
0x1400b3ae4  cmp     dx, bx
0x1400b3ae7  jb      short loc_1400B3AD4
0x1400b3ae9  mov     [r12], bx
0x1400b3aee  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400b3af5  mov     [r13+0], rbp
0x1400b3af9  lea     rbp, WPP_016ec685c1db3aefc7ddcf22ff746e69_Traceguids
0x1400b3b00  jmp     loc_1400B3C1A
0x1400b3b05  xor     eax, eax
0x1400b3b07  cmp     ax, bx
0x1400b3b0a  jnb     short loc_1400B3AE9
0x1400b3b0c  movzx   eax, r15w
0x1400b3b10  imul    r9, rax, 1Ch
0x1400b3b14  add     r9, rbp
0x1400b3b17  mov     ecx, [r9+18h]
0x1400b3b1b  mov     eax, ecx
0x1400b3b1d  and     eax, 60h
0x1400b3b20  cmp     al, 60h ; '`'
0x1400b3b22  jnz     short loc_1400B3B2D
0x1400b3b24  lea     r14, ?AllUsersReadWriteSecurityDescriptor@@3PADA; char near * AllUsersReadWriteSecurityDescriptor
0x1400b3b2b  jmp     short loc_1400B3B50
0x1400b3b2d  test    cl, 20h
0x1400b3b30  jz      short loc_1400B3B3B
0x1400b3b32  lea     r14, ?AllUsersReadSecurityDescriptor@@3PADA; char near * AllUsersReadSecurityDescriptor
0x1400b3b39  jmp     short loc_1400B3B50
0x1400b3b3b  test    cl, 40h
0x1400b3b3e  lea     r14, ?AllUsersWriteSecurityDescriptor@@3PADA; char near * AllUsersWriteSecurityDescriptor
0x1400b3b45  lea     rax, ?AdminsSecurityDescriptor@@3PADA; char near * AdminsSecurityDescriptor
0x1400b3b4c  cmovz   r14, rax
0x1400b3b50  bts     ecx, 1Bh
0x1400b3b54  lea     r8, [rsp+88h+DataBlockObject]; DataBlockObject
0x1400b3b5c  mov     [r9+18h], ecx
0x1400b3b60  mov     edx, 40000h; DesiredAccess
0x1400b3b65  mov     rcx, r9; Guid
0x1400b3b68  call    cs:__imp_IoWMIOpenBlock
0x1400b3b6f  nop     dword ptr [rax+rax+00h]
0x1400b3b74  mov     edi, eax
0x1400b3b76  test    eax, eax
0x1400b3b78  js      short loc_1400B3BAC
0x1400b3b7a  mov     rcx, [rsp+88h+DataBlockObject]
0x1400b3b82  mov     r8, r14
0x1400b3b85  mov     edx, 7
0x1400b3b8a  call    cs:__imp_ObSetSecurityObjectByPointer
0x1400b3b91  nop     dword ptr [rax+rax+00h]
0x1400b3b96  mov     rcx, [rsp+88h+DataBlockObject]; Object
0x1400b3b9e  mov     edi, eax
0x1400b3ba0  call    cs:__imp_ObfDereferenceObject
0x1400b3ba7  nop     dword ptr [rax+rax+00h]
0x1400b3bac  inc     r15w
0x1400b3bb0  cmp     r15w, bx
0x1400b3bb4  jb      loc_1400B3B0C
0x1400b3bba  test    edi, edi
0x1400b3bbc  jz      loc_1400B3AE9
0x1400b3bc2  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400b3bc9  xor     edx, edx; Tag
0x1400b3bcb  mov     rcx, rbp; P
0x1400b3bce  call    cs:__imp_ExFreePoolWithTag
0x1400b3bd5  nop     dword ptr [rax+rax+00h]
0x1400b3bda  jmp     loc_1400B3AF9
0x1400b3bdf  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400b3be6  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400b3bed  jz      short loc_1400B3C15
0x1400b3bef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3bf6  mov     r9d, 0Eh; int
0x1400b3bfc  mov     qword ptr [rsp+88h+var_60], rsi; char
0x1400b3c01  mov     dl, 4; int
0x1400b3c03  mov     [rsp+88h+var_68], rbp; struct _GUID *
0x1400b3c08  mov     rcx, [rcx+40h]; int
0x1400b3c0c  lea     r8d, [r9+4]; int
0x1400b3c10  call    WPP_RECORDER_SF_q
0x1400b3c15  mov     edi, 0C00000BBh
0x1400b3c1a  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400b3c21  jz      short loc_1400B3C4D
0x1400b3c23  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b3c2a  mov     r9d, 11h; int
0x1400b3c30  mov     dword ptr [rsp+88h+var_58], edi; char
0x1400b3c34  mov     dl, 4; int
0x1400b3c36  mov     qword ptr [rsp+88h+var_60], rsi; char
0x1400b3c3b  mov     [rsp+88h+var_68], rbp; struct _GUID *
0x1400b3c40  mov     rcx, [rcx+40h]; int
0x1400b3c44  lea     r8d, [r9+1]; int
0x1400b3c48  call    WPP_RECORDER_SF_qL
0x1400b3c4d  mov     eax, edi
0x1400b3c4f  add     rsp, 48h
0x1400b3c53  pop     r15
0x1400b3c55  pop     r14
0x1400b3c57  pop     r13
0x1400b3c59  pop     r12
0x1400b3c5b  pop     rdi
0x1400b3c5c  pop     rsi
0x1400b3c5d  pop     rbp
0x1400b3c5e  pop     rbx
0x1400b3c5f  retn
```
