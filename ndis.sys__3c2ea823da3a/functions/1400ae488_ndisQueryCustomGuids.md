# ndisQueryCustomGuids

- ea: `0x1400ae488`
- end: `0x1400ae839`
- name: `ndisQueryCustomGuids`
- size: `945`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _NDIS_OID_REQUEST *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005b690`

## callees

- `0x14001cf50`
- `0x14001d350`
- `0x14003c930`
- `0x1400837ac`
- `0x1400ae488`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400ae778`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ae778`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400ae762`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x1400ae762`
- `ntoskrnl!IoWMIOpenBlock` at `0x1400ae740`
- `ntoskrnl!IoWMIOpenBlock` at `0x1400ae740`
- `ntoskrnl!EtwActivityIdControl` at `0x1400ae51e`
- `ntoskrnl!EtwActivityIdControl` at `0x1400ae51e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ae7a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ae7a6`
- `ntoskrnl!ExAllocatePool2` at `0x1400ae5ac`
- `ntoskrnl!ExAllocatePool2` at `0x1400ae5ac`

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
0x1400ae488  mov     r11, rsp
0x1400ae48b  push    rbx
0x1400ae48c  push    rbp
0x1400ae48d  push    rsi
0x1400ae48e  push    rdi
0x1400ae48f  push    r12
0x1400ae491  push    r13
0x1400ae493  push    r14
0x1400ae495  push    r15
0x1400ae497  sub     rsp, 48h
0x1400ae49b  xor     r15d, r15d
0x1400ae49e  mov     r12, r9
0x1400ae4a1  mov     [r11+10h], r15
0x1400ae4a5  mov     r13, r8
0x1400ae4a8  mov     rdi, rdx
0x1400ae4ab  mov     rsi, rcx
0x1400ae4ae  lea     rax, WPP_RECORDER_INITIALIZED
0x1400ae4b5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400ae4bc  lea     rbp, WPP_016ec685c1db3aefc7ddcf22ff746e69_Traceguids
0x1400ae4c3  jz      short loc_1400AE4E7
0x1400ae4c5  mov     [r11-60h], rcx
0x1400ae4c9  lea     r9d, [r15+0Dh]; int
0x1400ae4cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ae4d4  lea     r8d, [r15+12h]; int
0x1400ae4d8  mov     dl, 4; int
0x1400ae4da  mov     [r11-68h], rbp
0x1400ae4de  mov     rcx, [rcx+40h]; int
0x1400ae4e2  call    WPP_RECORDER_SF_q
0x1400ae4e7  xor     edx, edx; Val
0x1400ae4e9  mov     [r13+0], r15
0x1400ae4ed  mov     r8d, 0F8h; Size
0x1400ae4f3  mov     [r12], r15w
0x1400ae4f8  mov     rcx, rdi; void *
0x1400ae4fb  call    memset
0x1400ae500  lea     rax, ?ndisIntReqWmi@@3U_NDIS_INTERNAL_REQUEST_OBJECT@@A; _NDIS_INTERNAL_REQUEST_OBJECT ndisIntReqWmi
0x1400ae507  mov     dword ptr [rdi+58h], 8
0x1400ae50e  lea     rdx, [rdi+0A8h]; ActivityId
0x1400ae515  mov     [rdi+68h], rax
0x1400ae519  mov     ecx, 3; ControlCode
0x1400ae51e  call    cs:__imp_EtwActivityIdControl
0x1400ae525  nop     dword ptr [rax+rax+00h]
0x1400ae52a  xor     r9d, r9d; unsigned __int8
0x1400ae52d  mov     qword ptr [rdi], 0EC0196h
0x1400ae534  mov     r8, rdi; struct _NDIS_OID_REQUEST *
0x1400ae537  mov     dword ptr [rdi+20h], 10117h
0x1400ae53e  xor     edx, edx; struct _NDIS_CO_VC_PTR_BLOCK *
0x1400ae540  mov     [rdi+8], r15d
0x1400ae544  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x1400ae547  mov     [rdi+28h], r15
0x1400ae54b  mov     [rdi+30h], r15d
0x1400ae54f  mov     [rsp+88h+var_68], r15; struct _NDIS_FILTER_BLOCK *
0x1400ae554  call    ?ndisQuerySetMiniport@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_CO_VC_PTR_BLOCK@@PEAU_NDIS_OID_REQUEST@@EPEAU_NDIS_FILTER_BLOCK@@@Z; ndisQuerySetMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_CO_VC_PTR_BLOCK *,_NDIS_OID_REQUEST *,uchar,_NDIS_FILTER_BLOCK *)
0x1400ae559  add     eax, 3FFEFFECh
0x1400ae55e  test    eax, 0FFFFFFFDh
0x1400ae563  jnz     loc_1400AE7B7
0x1400ae569  movzx   r14d, word ptr [rdi+38h]
0x1400ae56e  cmp     r15w, r14w
0x1400ae572  jz      loc_1400AE7B7
0x1400ae578  mov     rax, 2492492492492493h
0x1400ae582  mov     ebx, r14d
0x1400ae585  mul     r14
0x1400ae588  sub     rbx, rdx
0x1400ae58b  shr     rbx, 1
0x1400ae58e  add     rbx, rdx
0x1400ae591  shr     rbx, 4
0x1400ae595  test    bx, bx
0x1400ae598  jz      loc_1400AE7B7
0x1400ae59e  mov     r8d, 3177444Eh
0x1400ae5a4  mov     edx, r14d
0x1400ae5a7  mov     ecx, 40h ; '@'
0x1400ae5ac  call    cs:__imp_ExAllocatePool2
0x1400ae5b3  nop     dword ptr [rax+rax+00h]
0x1400ae5b8  mov     rbp, rax
0x1400ae5bb  test    rax, rax
0x1400ae5be  jnz     short loc_1400AE605
0x1400ae5c0  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400ae5c7  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400ae5ce  lea     rbp, WPP_016ec685c1db3aefc7ddcf22ff746e69_Traceguids
0x1400ae5d5  jz      short loc_1400AE5FB
0x1400ae5d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ae5de  lea     r9d, [rax+0Fh]; int
0x1400ae5e2  mov     qword ptr [rsp+88h+var_60], rsi; char
0x1400ae5e7  lea     r8d, [rax+12h]; int
0x1400ae5eb  mov     dl, 2; int
0x1400ae5ed  mov     [rsp+88h+var_68], rbp; struct _GUID *
0x1400ae5f2  mov     rcx, [rcx+40h]; int
0x1400ae5f6  call    WPP_RECORDER_SF_q
0x1400ae5fb  mov     edi, 0C000009Ah
0x1400ae600  jmp     loc_1400AE7F2
0x1400ae605  xor     r9d, r9d; unsigned __int8
0x1400ae608  mov     [rdi+28h], rbp
0x1400ae60c  mov     r8, rdi; struct _NDIS_OID_REQUEST *
0x1400ae60f  mov     [rdi+30h], r14d
0x1400ae613  xor     edx, edx; struct _NDIS_CO_VC_PTR_BLOCK *
0x1400ae615  mov     [rsp+88h+var_68], r15; struct _NDIS_FILTER_BLOCK *
0x1400ae61a  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x1400ae61d  call    ?ndisQuerySetMiniport@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_CO_VC_PTR_BLOCK@@PEAU_NDIS_OID_REQUEST@@EPEAU_NDIS_FILTER_BLOCK@@@Z; ndisQuerySetMiniport(_NDIS_MINIPORT_BLOCK *,_NDIS_CO_VC_PTR_BLOCK *,_NDIS_OID_REQUEST *,uchar,_NDIS_FILTER_BLOCK *)
0x1400ae622  mov     edi, eax
0x1400ae624  test    eax, eax
0x1400ae626  jz      short loc_1400AE66E
0x1400ae628  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400ae62f  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400ae636  jz      loc_1400AE7A1
0x1400ae63c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ae643  lea     rax, WPP_016ec685c1db3aefc7ddcf22ff746e69_Traceguids
0x1400ae64a  mov     r9d, 10h; int
0x1400ae650  mov     qword ptr [rsp+88h+var_60], rsi; char
0x1400ae655  mov     dl, 2; int
0x1400ae657  mov     [rsp+88h+var_68], rax; struct _GUID *
0x1400ae65c  mov     rcx, [rcx+40h]; int
0x1400ae660  lea     r8d, [r9+2]; int
0x1400ae664  call    WPP_RECORDER_SF_q
0x1400ae669  jmp     loc_1400AE7A1
0x1400ae66e  mov     edx, 20000h; unsigned int
0x1400ae673  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x1400ae676  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1400ae67b  test    al, al
0x1400ae67d  jz      short loc_1400AE69D
0x1400ae67f  mov     edx, r15d
0x1400ae682  cmp     r15w, bx
0x1400ae686  jnb     short loc_1400AE69D
0x1400ae688  movzx   eax, dx
0x1400ae68b  inc     dx
0x1400ae68e  imul    rcx, rax, 1Ch
0x1400ae692  bts     dword ptr [rcx+rbp+18h], 1Ch
0x1400ae698  cmp     dx, bx
0x1400ae69b  jb      short loc_1400AE688
0x1400ae69d  cmp     byte ptr [rsi+20h], 6
0x1400ae6a1  jb      short loc_1400AE6DD
0x1400ae6a3  mov     edx, r15d
0x1400ae6a6  cmp     r15w, bx
0x1400ae6aa  jnb     short loc_1400AE6C1
0x1400ae6ac  movzx   eax, dx
0x1400ae6af  inc     dx
0x1400ae6b2  imul    rcx, rax, 1Ch
0x1400ae6b6  bts     dword ptr [rcx+rbp+18h], 1Bh
0x1400ae6bc  cmp     dx, bx
0x1400ae6bf  jb      short loc_1400AE6AC
0x1400ae6c1  mov     [r12], bx
0x1400ae6c6  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400ae6cd  mov     [r13+0], rbp
0x1400ae6d1  lea     rbp, WPP_016ec685c1db3aefc7ddcf22ff746e69_Traceguids
0x1400ae6d8  jmp     loc_1400AE7F2
0x1400ae6dd  xor     eax, eax
0x1400ae6df  cmp     ax, bx
0x1400ae6e2  jnb     short loc_1400AE6C1
0x1400ae6e4  movzx   eax, r15w
0x1400ae6e8  imul    r9, rax, 1Ch
0x1400ae6ec  add     r9, rbp
0x1400ae6ef  mov     ecx, [r9+18h]
0x1400ae6f3  mov     eax, ecx
0x1400ae6f5  and     eax, 60h
0x1400ae6f8  cmp     al, 60h ; '`'
0x1400ae6fa  jnz     short loc_1400AE705
0x1400ae6fc  lea     r14, ?AllUsersReadWriteSecurityDescriptor@@3PADA; char near * AllUsersReadWriteSecurityDescriptor
0x1400ae703  jmp     short loc_1400AE728
0x1400ae705  test    cl, 20h
0x1400ae708  jz      short loc_1400AE713
0x1400ae70a  lea     r14, ?AllUsersReadSecurityDescriptor@@3PADA; char near * AllUsersReadSecurityDescriptor
0x1400ae711  jmp     short loc_1400AE728
0x1400ae713  test    cl, 40h
0x1400ae716  lea     r14, ?AllUsersWriteSecurityDescriptor@@3PADA; char near * AllUsersWriteSecurityDescriptor
0x1400ae71d  lea     rax, ?AdminsSecurityDescriptor@@3PADA; char near * AdminsSecurityDescriptor
0x1400ae724  cmovz   r14, rax
0x1400ae728  bts     ecx, 1Bh
0x1400ae72c  lea     r8, [rsp+88h+DataBlockObject]; DataBlockObject
0x1400ae734  mov     [r9+18h], ecx
0x1400ae738  mov     edx, 40000h; DesiredAccess
0x1400ae73d  mov     rcx, r9; Guid
0x1400ae740  call    cs:__imp_IoWMIOpenBlock
0x1400ae747  nop     dword ptr [rax+rax+00h]
0x1400ae74c  mov     edi, eax
0x1400ae74e  test    eax, eax
0x1400ae750  js      short loc_1400AE784
0x1400ae752  mov     rcx, [rsp+88h+DataBlockObject]
0x1400ae75a  mov     r8, r14
0x1400ae75d  mov     edx, 7
0x1400ae762  call    cs:__imp_ObSetSecurityObjectByPointer
0x1400ae769  nop     dword ptr [rax+rax+00h]
0x1400ae76e  mov     rcx, [rsp+88h+DataBlockObject]; Object
0x1400ae776  mov     edi, eax
0x1400ae778  call    cs:__imp_ObfDereferenceObject
0x1400ae77f  nop     dword ptr [rax+rax+00h]
0x1400ae784  inc     r15w
0x1400ae788  cmp     r15w, bx
0x1400ae78c  jb      loc_1400AE6E4
0x1400ae792  test    edi, edi
0x1400ae794  jz      loc_1400AE6C1
0x1400ae79a  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400ae7a1  xor     edx, edx; Tag
0x1400ae7a3  mov     rcx, rbp; P
0x1400ae7a6  call    cs:__imp_ExFreePoolWithTag
0x1400ae7ad  nop     dword ptr [rax+rax+00h]
0x1400ae7b2  jmp     loc_1400AE6D1
0x1400ae7b7  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400ae7be  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400ae7c5  jz      short loc_1400AE7ED
0x1400ae7c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ae7ce  mov     r9d, 0Eh; int
0x1400ae7d4  mov     qword ptr [rsp+88h+var_60], rsi; char
0x1400ae7d9  mov     dl, 4; int
0x1400ae7db  mov     [rsp+88h+var_68], rbp; struct _GUID *
0x1400ae7e0  mov     rcx, [rcx+40h]; int
0x1400ae7e4  lea     r8d, [r9+4]; int
0x1400ae7e8  call    WPP_RECORDER_SF_q
0x1400ae7ed  mov     edi, 0C00000BBh
0x1400ae7f2  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400ae7f9  jz      short loc_1400AE825
0x1400ae7fb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ae802  mov     r9d, 11h; int
0x1400ae808  mov     dword ptr [rsp+88h+var_58], edi; char
0x1400ae80c  mov     dl, 4; int
0x1400ae80e  mov     qword ptr [rsp+88h+var_60], rsi; char
0x1400ae813  mov     [rsp+88h+var_68], rbp; struct _GUID *
0x1400ae818  mov     rcx, [rcx+40h]; int
0x1400ae81c  lea     r8d, [r9+1]; int
0x1400ae820  call    WPP_RECORDER_SF_qL
0x1400ae825  mov     eax, edi
0x1400ae827  add     rsp, 48h
0x1400ae82b  pop     r15
0x1400ae82d  pop     r14
0x1400ae82f  pop     r13
0x1400ae831  pop     r12
0x1400ae833  pop     rdi
0x1400ae834  pop     rsi
0x1400ae835  pop     rbp
0x1400ae836  pop     rbx
0x1400ae837  retn
```
