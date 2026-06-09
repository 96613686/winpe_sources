# NtfsModifySecurity

- ea: `0x1401f0e58`
- end: `0x1401f12fd`
- name: `NtfsModifySecurity`
- size: `1189`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, PSECURITY_DESCRIPTOR ModificationDescriptor)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14017a5e0`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x140025a40`
- `0x140059740`
- `0x140125100`
- `0x14012bb48`
- `0x1401403d0`
- `0x140141a3c`
- `0x14015a5c0`
- `0x14018756c`
- `0x14018ddd8`
- `0x14019a768`
- `0x1401e06b0`
- `0x1401ef2d0`
- `0x1401f0e58`
- `0x1401f1304`
- `0x1401f15e0`
- `0x1401f1678`
- `0x14026e630`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401f0f61`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401f105c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401f0f61`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401f105c`
- `ntoskrnl!SeDeassignSecurity` at `0x1401f123b`
- `ntoskrnl!SeDeassignSecurity` at `0x1402b1c8e`
- `ntoskrnl!SeDeassignSecurity` at `0x1401f123b`
- `ntoskrnl!SeDeassignSecurity` at `0x1402b1c8e`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1401f0f08`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1401f0f08`
- `ntoskrnl!SeSetSecurityDescriptorInfoEx` at `0x1401f0ee2`
- `ntoskrnl!SeSetSecurityDescriptorInfoEx` at `0x1401f0ee2`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401f0ead`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401f0ead`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401f0f9c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401f11e4`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b1c08`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b1ca9`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401f0f9c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401f11e4`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b1c08`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b1ca9`

## pseudocode

```c
__int64 __fastcall NtfsModifySecurity(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        DWORD *a4,
        PSECURITY_DESCRIPTOR ModificationDescriptor)
{
  __int64 v8; // r12
  __int64 v9; // r15
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  NTSTATUS v11; // eax
  unsigned int v12; // r14d
  ULONG v13; // r13d
  int v14; // r13d
  __int64 v15; // rax
  __int16 *v16; // rax
  __int64 v17; // rcx
  int GenericMapping; // [rsp+30h] [rbp-108h]
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+58h] [rbp-E0h] BYREF
  int v21; // [rsp+60h] [rbp-D8h]
  int v22; // [rsp+64h] [rbp-D4h]
  __int64 v23; // [rsp+68h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+70h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+78h] [rbp-C0h]
  UNICODE_STRING v26; // [rsp+80h] [rbp-B8h] BYREF
  __int128 v27; // [rsp+90h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+A0h] [rbp-98h]
  _BYTE v29[96]; // [rsp+B0h] [rbp-88h] BYREF

  v8 = 0;
  ObjectsSecurityDescriptor = 0;
  v24 = 0;
  v9 = a3 + 208;
  if ( !*(_QWORD *)(a3 + 208) )
    NtfsLoadSecurityDescriptor(a1, a3);
  ObjectsSecurityDescriptor = (PSECURITY_DESCRIPTOR)(*(_QWORD *)v9 + 28LL);
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  v11 = SeSetSecurityDescriptorInfoEx(
          0,
          a4,
          ModificationDescriptor,
          &ObjectsSecurityDescriptor,
          0x4000u,
          PoolType,
          FileObjectGenericMapping);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( NtfsStatusDebugFlags
      && (unsigned int)v11 < 0xFFFFFFED
      && v11 != -1073741802
      && v11 != -1073741807
      && (unsigned int)(v11 + 2147483643) > 1
      && v11 != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(a1, (unsigned int)v11, 2032824);
    }
    NtfsRaiseStatusInternal(a1, v12, 0, 0, 2032824);
    __debugbreak();
  }
  v22 = 0;
  v13 = RtlLengthSecurityDescriptor(ObjectsSecurityDescriptor);
  if ( v13 )
  {
    v8 = *(_QWORD *)(a3 + 120);
    v24 = v8;
    v22 = *(_DWORD *)(a3 + 264);
    if ( *(_QWORD *)(*(_QWORD *)(a3 + 96) + 104LL) )
    {
      v25 = 0;
      v23 = 0;
      v21 = 0;
      memset(v29, 0, 0x58u);
      v27 = 0;
      v28 = 0;
      v25 = NtfsCacheSharedSecurityByDescriptor(a1, ObjectsSecurityDescriptor, v13, 1);
      memset(v29, 0, 0x58u);
      v23 = *(_QWORD *)v9;
      v14 = *(_DWORD *)(a3 + 280);
      v21 = v14;
      ExAcquirePushLockExclusiveEx(a3 + 216, 0);
      NtfsMoveQuotaOwner(a1, a3, ObjectsSecurityDescriptor);
      v15 = v25;
      *(_QWORD *)v9 = v25;
      *(_DWORD *)(a3 + 280) = *(_DWORD *)(v15 + 12);
      if ( (*(_DWORD *)(a3 + 4) & 0x800) == 0 )
        NtfsGrowStandardInformation(a1, a3);
      if ( !v14 )
      {
        LOBYTE(GenericMapping) = 0;
        if ( (unsigned __int8)NtfsLookupInFileRecord(a1, a3, a3 + 8, 80, 0, 0, GenericMapping, 0, 0, v29) )
        {
          *(_QWORD *)&v26.Length = 0x20000;
          v26.Buffer = (PWSTR)&word_140064400;
          NtfsDeleteAttributeRecord(a1, a3, 7, v29);
          v16 = NtfsCreateScb(a1, a3, 80, &v26, 1, 0, 0);
          if ( v16 )
            *((_DWORD *)v16 + 128) |= 0x40u;
        }
      }
      if ( *(_QWORD *)(a1 + 400) )
        TxfModifySecurity(a1, v14, (__int64)&v27);
      NtfsUpdateStandardInformation(a1, a3);
      NtfsCheckpointCurrentTransaction(a1);
      NtfsCleanupAttributeContext(v17, v29);
      NtfsDereferenceSharedSecurity(&v23);
      ExReleasePushLockEx(a3 + 216, 0);
    }
    else
    {
      NtfsMoveQuotaOwner(a1, a3, ObjectsSecurityDescriptor);
      ExAcquirePushLockExclusiveEx(a3 + 216, 0);
      NtfsDereferenceSharedSecurity(v9);
      NtfsSetFcbSecurityFromDescriptor(a1, a3, (_DWORD)ObjectsSecurityDescriptor, v13, 1, 1);
      ExReleasePushLockEx(a3 + 216, 0);
      NtfsStoreSecurityDescriptor(a1, a3);
      NtfsUpdateStandardInformation(a1, a3);
      NtfsCheckpointCurrentTransaction(a1);
    }
  }
  else
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 2032843);
    NtfsRaiseStatusInternal(a1, -1073741811, 0, 0, 2032843);
  }
  if ( *(_QWORD *)(a3 + 120) != v8 && v8 )
    NtfsDereferenceQuotaControlBlock(*(_QWORD *)(a3 + 96), &v24, 0);
  SeDeassignSecurity(&ObjectsSecurityDescriptor);
  *(_DWORD *)(a3 + 184) |= 0x100u;
  return v12;
}

```

## disassembly

```asm
0x1401f0e58  mov     rax, rsp
0x1401f0e5b  mov     [rax+8], rbx
0x1401f0e5f  mov     [rax+20h], rsi
0x1401f0e63  mov     [rax+18h], r8
0x1401f0e67  mov     [rax+10h], rdx
0x1401f0e6b  push    rdi
0x1401f0e6c  push    r12
0x1401f0e6e  push    r13
0x1401f0e70  push    r14
0x1401f0e72  push    r15
0x1401f0e74  sub     rsp, 110h
0x1401f0e7b  mov     rbx, r9
0x1401f0e7e  mov     rdi, r8
0x1401f0e81  mov     rsi, rcx
0x1401f0e84  xor     r12d, r12d
0x1401f0e87  mov     [rsp+138h+ObjectsSecurityDescriptor], r12
0x1401f0e8c  mov     [rsp+138h+var_C8], r12
0x1401f0e91  lea     r15, [r8+0D0h]
0x1401f0e98  cmp     [r15], r12
0x1401f0e9b  jz      loc_1401F12D1
0x1401f0ea1  mov     rax, [r15]
0x1401f0ea4  add     rax, 1Ch
0x1401f0ea8  mov     [rsp+138h+ObjectsSecurityDescriptor], rax
0x1401f0ead  call    cs:__imp_IoGetFileObjectGenericMapping
0x1401f0eb4  nop     dword ptr [rax+rax+00h]
0x1401f0eb9  mov     [rsp+138h+GenericMapping], rax; GenericMapping
0x1401f0ebe  mov     eax, cs:PoolType
0x1401f0ec4  mov     [rsp+138h+PoolType], eax; PoolType
0x1401f0ec8  mov     [rsp+138h+AutoInheritFlags], 4000h; AutoInheritFlags
0x1401f0ed0  lea     r9, [rsp+138h+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x1401f0ed5  mov     r8, [rsp+138h+ModificationDescriptor]; ModificationDescriptor
0x1401f0edd  mov     rdx, rbx; SecurityInformation
0x1401f0ee0  xor     ecx, ecx; Object
0x1401f0ee2  call    cs:__imp_SeSetSecurityDescriptorInfoEx
0x1401f0ee9  nop     dword ptr [rax+rax+00h]
0x1401f0eee  mov     r14d, eax
0x1401f0ef1  test    eax, eax
0x1401f0ef3  js      loc_1401F1270
0x1401f0ef9  mov     [rsp+138h+var_D4], r12d
0x1401f0efe  mov     [rsp+138h+var_E8], r12b
0x1401f0f03  mov     rcx, [rsp+138h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x1401f0f08  call    cs:__imp_RtlLengthSecurityDescriptor
0x1401f0f0f  nop     dword ptr [rax+rax+00h]
0x1401f0f14  mov     r13d, eax
0x1401f0f17  test    eax, eax
0x1401f0f19  jz      loc_1401F11F2
0x1401f0f1f  mov     r12, [rdi+78h]
0x1401f0f23  mov     [rsp+138h+var_C8], r12
0x1401f0f28  mov     ebx, [rdi+108h]
0x1401f0f2e  mov     [rsp+138h+var_D4], ebx
0x1401f0f32  mov     rax, [rdi+60h]
0x1401f0f36  xor     ecx, ecx
0x1401f0f38  cmp     [rax+68h], rcx
0x1401f0f3c  jnz     loc_1401F0FD9
0x1401f0f42  xor     r9d, r9d
0x1401f0f45  mov     r8, [rsp+138h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x1401f0f4a  mov     rdx, rdi; int
0x1401f0f4d  mov     rcx, rsi; int
0x1401f0f50  call    NtfsMoveQuotaOwner
0x1401f0f55  lea     rbx, [rdi+0D8h]
0x1401f0f5c  xor     edx, edx
0x1401f0f5e  mov     rcx, rbx
0x1401f0f61  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401f0f68  nop     dword ptr [rax+rax+00h]
0x1401f0f6d  mov     [rsp+138h+var_E8], 1
0x1401f0f72  mov     rcx, r15
0x1401f0f75  call    NtfsDereferenceSharedSecurity
0x1401f0f7a  mov     byte ptr [rsp+138h+PoolType], 1
0x1401f0f7f  mov     byte ptr [rsp+138h+AutoInheritFlags], 1
0x1401f0f84  mov     r9d, r13d
0x1401f0f87  mov     r8, [rsp+138h+ObjectsSecurityDescriptor]
0x1401f0f8c  mov     rdx, rdi
0x1401f0f8f  mov     rcx, rsi
0x1401f0f92  call    NtfsSetFcbSecurityFromDescriptor
0x1401f0f97  xor     edx, edx
0x1401f0f99  mov     rcx, rbx
0x1401f0f9c  call    cs:__imp_ExReleasePushLockEx
0x1401f0fa3  nop     dword ptr [rax+rax+00h]
0x1401f0fa8  xor     r15d, r15d
0x1401f0fab  mov     [rsp+138h+var_E8], r15b
0x1401f0fb0  mov     r8b, 1
0x1401f0fb3  mov     rdx, rdi; int
0x1401f0fb6  mov     rcx, rsi; int
0x1401f0fb9  call    NtfsStoreSecurityDescriptor
0x1401f0fbe  xor     r8d, r8d
0x1401f0fc1  mov     rdx, rdi
0x1401f0fc4  mov     rcx, rsi
0x1401f0fc7  call    NtfsUpdateStandardInformation
0x1401f0fcc  mov     rcx, rsi
0x1401f0fcf  call    NtfsCheckpointCurrentTransaction
0x1401f0fd4  jmp     loc_1401F122C
0x1401f0fd9  mov     [rsp+138h+var_C0], rcx
0x1401f0fde  mov     [rsp+138h+var_D0], rcx
0x1401f0fe3  mov     [rsp+138h+var_D8], ecx
0x1401f0fe7  xor     edx, edx; Val
0x1401f0fe9  lea     r8d, [rdx+58h]; Size
0x1401f0fed  lea     rcx, [rsp+138h+var_88]; void *
0x1401f0ff5  call    memset
0x1401f0ffa  xorps   xmm0, xmm0
0x1401f0ffd  xor     eax, eax
0x1401f0fff  movups  [rsp+138h+var_A8], xmm0
0x1401f1007  mov     [rsp+138h+var_98], rax
0x1401f100f  mov     byte ptr [rsp+138h+AutoInheritFlags], 1; char
0x1401f1014  mov     r9b, 1
0x1401f1017  mov     r8d, r13d; Length
0x1401f101a  mov     rdx, [rsp+138h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x1401f101f  mov     rcx, rsi; int
0x1401f1022  call    NtfsCacheSharedSecurityByDescriptor
0x1401f1027  mov     [rsp+138h+var_C0], rax
0x1401f102c  xor     edx, edx; Val
0x1401f102e  lea     r8d, [rdx+58h]; Size
0x1401f1032  lea     rcx, [rsp+138h+var_88]; void *
0x1401f103a  call    memset
0x1401f103f  mov     rcx, [r15]
0x1401f1042  mov     [rsp+138h+var_D0], rcx
0x1401f1047  mov     r13d, [rdi+118h]
0x1401f104e  mov     [rsp+138h+var_D8], r13d
0x1401f1053  lea     rcx, [rdi+0D8h]
0x1401f105a  xor     edx, edx
0x1401f105c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401f1063  nop     dword ptr [rax+rax+00h]
0x1401f1068  mov     rax, [rsi+190h]
0x1401f106f  neg     rax
0x1401f1072  sbb     r9, r9
0x1401f1075  lea     rax, [rsp+138h+var_A8]
0x1401f107d  and     r9, rax
0x1401f1080  mov     r8, [rsp+138h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x1401f1085  mov     rdx, rdi; int
0x1401f1088  mov     rcx, rsi; int
0x1401f108b  call    NtfsMoveQuotaOwner
0x1401f1090  mov     rax, [rsp+138h+var_C0]
0x1401f1095  mov     [r15], rax
0x1401f1098  mov     eax, [rax+0Ch]
0x1401f109b  mov     [rdi+118h], eax
0x1401f10a1  test    dword ptr [rdi+4], 800h
0x1401f10a8  jz      short loc_1401F10EC
0x1401f10aa  xor     r15d, r15d
0x1401f10ad  test    r13d, r13d
0x1401f10b0  jz      short loc_1401F10F9
0x1401f10b2  cmp     [rsi+190h], r15
0x1401f10b9  jz      loc_1401F11AD
0x1401f10bf  lea     rax, [rsp+138h+var_A8]
0x1401f10c7  mov     qword ptr [rsp+138h+PoolType], rax
0x1401f10cc  mov     [rsp+138h+AutoInheritFlags], r13d
0x1401f10d1  mov     r9d, ebx
0x1401f10d4  mov     r8, rdi
0x1401f10d7  mov     rdx, [rsp+138h+arg_8]
0x1401f10df  mov     rcx, rsi
0x1401f10e2  call    TxfModifySecurity
0x1401f10e7  jmp     loc_1401F11AD
0x1401f10ec  mov     rdx, rdi; int
0x1401f10ef  mov     rcx, rsi; int
0x1401f10f2  call    NtfsGrowStandardInformation
0x1401f10f7  jmp     short loc_1401F10AA
0x1401f10f9  lea     r8, [rdi+8]
0x1401f10fd  lea     rax, [rsp+138h+var_88]
0x1401f1105  mov     [rsp+138h+var_F0], rax
0x1401f110a  mov     [rsp+138h+var_F8], r15d
0x1401f110f  mov     [rsp+138h+var_100], r15
0x1401f1114  mov     byte ptr [rsp+138h+GenericMapping], r15b
0x1401f1119  mov     qword ptr [rsp+138h+PoolType], r15
0x1401f111e  mov     qword ptr [rsp+138h+AutoInheritFlags], r15
0x1401f1123  mov     r9d, 50h ; 'P'
0x1401f1129  mov     rdx, rdi
0x1401f112c  mov     rcx, rsi
0x1401f112f  call    NtfsLookupInFileRecord
0x1401f1134  test    al, al
0x1401f1136  jz      loc_1401F10B2
0x1401f113c  mov     [rsp+138h+var_B8], 20000h
0x1401f1148  lea     rax, word_140064400
0x1401f114f  mov     [rsp+138h+var_B0], rax
0x1401f1157  lea     r9, [rsp+138h+var_88]
0x1401f115f  mov     r8d, 7
0x1401f1165  mov     rdx, rdi
0x1401f1168  mov     rcx, rsi
0x1401f116b  call    NtfsDeleteAttributeRecord
0x1401f1170  mov     [rsp+138h+GenericMapping], r15
0x1401f1175  mov     qword ptr [rsp+138h+PoolType], r15
0x1401f117a  mov     byte ptr [rsp+138h+AutoInheritFlags], 1
0x1401f117f  lea     r9, [rsp+138h+var_B8]
0x1401f1187  mov     r8d, 50h ; 'P'
0x1401f118d  mov     rdx, rdi
0x1401f1190  mov     rcx, rsi
0x1401f1193  call    NtfsCreateScb
0x1401f1198  test    rax, rax
0x1401f119b  jz      loc_1401F10B2
0x1401f11a1  or      dword ptr [rax+200h], 40h
0x1401f11a8  jmp     loc_1401F10B2
0x1401f11ad  xor     r8d, r8d
0x1401f11b0  mov     rdx, rdi
0x1401f11b3  mov     rcx, rsi
0x1401f11b6  call    NtfsUpdateStandardInformation
0x1401f11bb  mov     rcx, rsi
0x1401f11be  call    NtfsCheckpointCurrentTransaction
0x1401f11c3  nop
0x1401f11c4  lea     rdx, [rsp+138h+var_88]
0x1401f11cc  call    NtfsCleanupAttributeContext
0x1401f11d1  lea     rcx, [rsp+138h+var_D0]
0x1401f11d6  call    NtfsDereferenceSharedSecurity
0x1401f11db  xor     edx, edx
0x1401f11dd  lea     rcx, [rdi+0D8h]
0x1401f11e4  call    cs:__imp_ExReleasePushLockEx
0x1401f11eb  nop     dword ptr [rax+rax+00h]
0x1401f11f0  jmp     short loc_1401F122C
0x1401f11f2  mov     al, cs:NtfsStatusDebugFlags
0x1401f11f8  test    al, al
0x1401f11fa  jz      short loc_1401F120F
0x1401f11fc  mov     edx, 0C000000Dh
0x1401f1201  mov     r8d, 1F04CBh
0x1401f1207  mov     rcx, rsi
0x1401f120a  call    NtfsStatusTraceAndDebugInternal
0x1401f120f  mov     qword ptr [rsp+138h+AutoInheritFlags], 1F04CBh
0x1401f1218  xor     r9d, r9d
0x1401f121b  xor     r8d, r8d
0x1401f121e  mov     edx, 0C000000Dh
0x1401f1223  mov     rcx, rsi
0x1401f1226  call    NtfsRaiseStatusInternal
0x1401f122b  nop
0x1401f122c  cmp     [rdi+78h], r12
0x1401f1230  jnz     loc_1401F12DE
0x1401f1236  lea     rcx, [rsp+138h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x1401f123b  call    cs:__imp_SeDeassignSecurity
0x1401f1242  nop     dword ptr [rax+rax+00h]
0x1401f1247  bts     dword ptr [rdi+0B8h], 8
0x1401f124f  mov     eax, r14d
0x1401f1252  lea     r11, [rsp+138h+var_28]
0x1401f125a  mov     rbx, [r11+30h]
0x1401f125e  mov     rsi, [r11+48h]
0x1401f1262  mov     rsp, r11
0x1401f1265  pop     r15
0x1401f1267  pop     r14
0x1401f1269  pop     r13
0x1401f126b  pop     r12
0x1401f126d  pop     rdi
0x1401f126e  retn
0x1401f1270  mov     cl, cs:NtfsStatusDebugFlags
0x1401f1276  test    cl, cl
0x1401f1278  jz      short loc_1401F12B6
0x1401f127a  cmp     r14d, 0FFFFFFEDh
0x1401f127e  jnb     short loc_1401F12B6
0x1401f1280  cmp     r14d, 0C0000016h
0x1401f1287  jz      short loc_1401F12B6
0x1401f1289  cmp     r14d, 0C0000011h
0x1401f1290  jz      short loc_1401F12B6
0x1401f1292  add     eax, 7FFFFFFBh
0x1401f1297  cmp     eax, 1
0x1401f129a  jbe     short loc_1401F12B6
0x1401f129c  cmp     r14d, 0C00000D8h
0x1401f12a3  jz      short loc_1401F12B6
0x1401f12a5  mov     r8d, 1F04B8h
0x1401f12ab  mov     edx, r14d
0x1401f12ae  mov     rcx, rsi
0x1401f12b1  call    NtfsStatusTraceAndDebugInternal
0x1401f12b6  mov     qword ptr [rsp+138h+AutoInheritFlags], 1F04B8h
0x1401f12bf  xor     r9d, r9d
0x1401f12c2  xor     r8d, r8d
0x1401f12c5  mov     edx, r14d
0x1401f12c8  mov     rcx, rsi
0x1401f12cb  call    NtfsRaiseStatusInternal
0x1401f12d0  int     3; Trap to Debugger
0x1401f12d1  mov     rdx, rdi
0x1401f12d4  call    NtfsLoadSecurityDescriptor
0x1401f12d9  jmp     loc_1401F0EA1
0x1401f12de  test    r12, r12
0x1401f12e1  jz      loc_1401F1236
0x1401f12e7  xor     r8d, r8d
0x1401f12ea  lea     rdx, [rsp+138h+var_C8]
0x1401f12ef  mov     rcx, [rdi+60h]
0x1401f12f3  call    NtfsDereferenceQuotaControlBlock
0x1401f12f8  jmp     loc_1401F1236
0x1402b1b9e  push    rbx
0x1402b1ba0  push    rbp
0x1402b1ba1  sub     rsp, 58h
0x1402b1ba5  mov     rbp, rdx
0x1402b1ba8  movzx   ebx, cl
0x1402b1bab  test    cl, cl
0x1402b1bad  jz      short loc_1402B1BB5
0x1402b1baf  mov     al, cs:NtfsStatusDebugFlags
0x1402b1bb5  lea     rdx, [rbp+0B0h]
0x1402b1bbc  call    NtfsCleanupAttributeContext
0x1402b1bc1  mov     eax, ebx
0x1402b1bc3  test    bl, bl
0x1402b1bc5  jz      short loc_1402B1BEF
0x1402b1bc7  mov     rax, [rbp+68h]
0x1402b1bcb  test    rax, rax
0x1402b1bce  jz      short loc_1402B1BE7
0x1402b1bd0  mov     rcx, [rbp+150h]
0x1402b1bd7  mov     [rcx+0D0h], rax
0x1402b1bde  mov     eax, [rbp+60h]
0x1402b1be1  mov     [rcx+118h], eax
0x1402b1be7  mov     rax, [rbp+78h]
0x1402b1beb  mov     [rbp+68h], rax
0x1402b1bef  lea     rcx, [rbp+68h]
0x1402b1bf3  call    NtfsDereferenceSharedSecurity
0x1402b1bf8  mov     rcx, [rbp+150h]
0x1402b1bff  add     rcx, 0D8h
0x1402b1c06  xor     edx, edx
0x1402b1c08  call    cs:__imp_ExReleasePushLockEx
0x1402b1c0f  nop     dword ptr [rax+rax+00h]
0x1402b1c14  nop
  ... truncated ...
```
