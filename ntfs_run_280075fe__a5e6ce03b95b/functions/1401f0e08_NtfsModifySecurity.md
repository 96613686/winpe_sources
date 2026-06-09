# NtfsModifySecurity

- ea: `0x1401f0e08`
- end: `0x1401f12ad`
- name: `NtfsModifySecurity`
- size: `1189`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, PSECURITY_DESCRIPTOR ModificationDescriptor)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14017a590`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x140025a40`
- `0x1400596c0`
- `0x1401250b0`
- `0x14012baf8`
- `0x140140380`
- `0x1401419ec`
- `0x14015a570`
- `0x14018751c`
- `0x14018dd88`
- `0x14019a718`
- `0x1401e0660`
- `0x1401ef280`
- `0x1401f0e08`
- `0x1401f12b4`
- `0x1401f1590`
- `0x1401f1628`
- `0x14026e5e0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401f0f11`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401f100c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401f0f11`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401f100c`
- `ntoskrnl!SeDeassignSecurity` at `0x1401f11eb`
- `ntoskrnl!SeDeassignSecurity` at `0x1402b1c3e`
- `ntoskrnl!SeDeassignSecurity` at `0x1401f11eb`
- `ntoskrnl!SeDeassignSecurity` at `0x1402b1c3e`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1401f0eb8`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1401f0eb8`
- `ntoskrnl!SeSetSecurityDescriptorInfoEx` at `0x1401f0e92`
- `ntoskrnl!SeSetSecurityDescriptorInfoEx` at `0x1401f0e92`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401f0e5d`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1401f0e5d`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401f0f4c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401f1194`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b1bb8`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b1c59`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401f0f4c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401f1194`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b1bb8`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b1c59`

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
0x1401f0e08  mov     rax, rsp
0x1401f0e0b  mov     [rax+8], rbx
0x1401f0e0f  mov     [rax+20h], rsi
0x1401f0e13  mov     [rax+18h], r8
0x1401f0e17  mov     [rax+10h], rdx
0x1401f0e1b  push    rdi
0x1401f0e1c  push    r12
0x1401f0e1e  push    r13
0x1401f0e20  push    r14
0x1401f0e22  push    r15
0x1401f0e24  sub     rsp, 110h
0x1401f0e2b  mov     rbx, r9
0x1401f0e2e  mov     rdi, r8
0x1401f0e31  mov     rsi, rcx
0x1401f0e34  xor     r12d, r12d
0x1401f0e37  mov     [rsp+138h+ObjectsSecurityDescriptor], r12
0x1401f0e3c  mov     [rsp+138h+var_C8], r12
0x1401f0e41  lea     r15, [r8+0D0h]
0x1401f0e48  cmp     [r15], r12
0x1401f0e4b  jz      loc_1401F1281
0x1401f0e51  mov     rax, [r15]
0x1401f0e54  add     rax, 1Ch
0x1401f0e58  mov     [rsp+138h+ObjectsSecurityDescriptor], rax
0x1401f0e5d  call    cs:__imp_IoGetFileObjectGenericMapping
0x1401f0e64  nop     dword ptr [rax+rax+00h]
0x1401f0e69  mov     [rsp+138h+GenericMapping], rax; GenericMapping
0x1401f0e6e  mov     eax, cs:PoolType
0x1401f0e74  mov     [rsp+138h+PoolType], eax; PoolType
0x1401f0e78  mov     [rsp+138h+AutoInheritFlags], 4000h; AutoInheritFlags
0x1401f0e80  lea     r9, [rsp+138h+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x1401f0e85  mov     r8, [rsp+138h+ModificationDescriptor]; ModificationDescriptor
0x1401f0e8d  mov     rdx, rbx; SecurityInformation
0x1401f0e90  xor     ecx, ecx; Object
0x1401f0e92  call    cs:__imp_SeSetSecurityDescriptorInfoEx
0x1401f0e99  nop     dword ptr [rax+rax+00h]
0x1401f0e9e  mov     r14d, eax
0x1401f0ea1  test    eax, eax
0x1401f0ea3  js      loc_1401F1220
0x1401f0ea9  mov     [rsp+138h+var_D4], r12d
0x1401f0eae  mov     [rsp+138h+var_E8], r12b
0x1401f0eb3  mov     rcx, [rsp+138h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x1401f0eb8  call    cs:__imp_RtlLengthSecurityDescriptor
0x1401f0ebf  nop     dword ptr [rax+rax+00h]
0x1401f0ec4  mov     r13d, eax
0x1401f0ec7  test    eax, eax
0x1401f0ec9  jz      loc_1401F11A2
0x1401f0ecf  mov     r12, [rdi+78h]
0x1401f0ed3  mov     [rsp+138h+var_C8], r12
0x1401f0ed8  mov     ebx, [rdi+108h]
0x1401f0ede  mov     [rsp+138h+var_D4], ebx
0x1401f0ee2  mov     rax, [rdi+60h]
0x1401f0ee6  xor     ecx, ecx
0x1401f0ee8  cmp     [rax+68h], rcx
0x1401f0eec  jnz     loc_1401F0F89
0x1401f0ef2  xor     r9d, r9d
0x1401f0ef5  mov     r8, [rsp+138h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x1401f0efa  mov     rdx, rdi; int
0x1401f0efd  mov     rcx, rsi; int
0x1401f0f00  call    NtfsMoveQuotaOwner
0x1401f0f05  lea     rbx, [rdi+0D8h]
0x1401f0f0c  xor     edx, edx
0x1401f0f0e  mov     rcx, rbx
0x1401f0f11  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401f0f18  nop     dword ptr [rax+rax+00h]
0x1401f0f1d  mov     [rsp+138h+var_E8], 1
0x1401f0f22  mov     rcx, r15
0x1401f0f25  call    NtfsDereferenceSharedSecurity
0x1401f0f2a  mov     byte ptr [rsp+138h+PoolType], 1
0x1401f0f2f  mov     byte ptr [rsp+138h+AutoInheritFlags], 1
0x1401f0f34  mov     r9d, r13d
0x1401f0f37  mov     r8, [rsp+138h+ObjectsSecurityDescriptor]
0x1401f0f3c  mov     rdx, rdi
0x1401f0f3f  mov     rcx, rsi
0x1401f0f42  call    NtfsSetFcbSecurityFromDescriptor
0x1401f0f47  xor     edx, edx
0x1401f0f49  mov     rcx, rbx
0x1401f0f4c  call    cs:__imp_ExReleasePushLockEx
0x1401f0f53  nop     dword ptr [rax+rax+00h]
0x1401f0f58  xor     r15d, r15d
0x1401f0f5b  mov     [rsp+138h+var_E8], r15b
0x1401f0f60  mov     r8b, 1
0x1401f0f63  mov     rdx, rdi; int
0x1401f0f66  mov     rcx, rsi; int
0x1401f0f69  call    NtfsStoreSecurityDescriptor
0x1401f0f6e  xor     r8d, r8d
0x1401f0f71  mov     rdx, rdi
0x1401f0f74  mov     rcx, rsi
0x1401f0f77  call    NtfsUpdateStandardInformation
0x1401f0f7c  mov     rcx, rsi
0x1401f0f7f  call    NtfsCheckpointCurrentTransaction
0x1401f0f84  jmp     loc_1401F11DC
0x1401f0f89  mov     [rsp+138h+var_C0], rcx
0x1401f0f8e  mov     [rsp+138h+var_D0], rcx
0x1401f0f93  mov     [rsp+138h+var_D8], ecx
0x1401f0f97  xor     edx, edx; Val
0x1401f0f99  lea     r8d, [rdx+58h]; Size
0x1401f0f9d  lea     rcx, [rsp+138h+var_88]; void *
0x1401f0fa5  call    memset
0x1401f0faa  xorps   xmm0, xmm0
0x1401f0fad  xor     eax, eax
0x1401f0faf  movups  [rsp+138h+var_A8], xmm0
0x1401f0fb7  mov     [rsp+138h+var_98], rax
0x1401f0fbf  mov     byte ptr [rsp+138h+AutoInheritFlags], 1; char
0x1401f0fc4  mov     r9b, 1
0x1401f0fc7  mov     r8d, r13d; Length
0x1401f0fca  mov     rdx, [rsp+138h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x1401f0fcf  mov     rcx, rsi; int
0x1401f0fd2  call    NtfsCacheSharedSecurityByDescriptor
0x1401f0fd7  mov     [rsp+138h+var_C0], rax
0x1401f0fdc  xor     edx, edx; Val
0x1401f0fde  lea     r8d, [rdx+58h]; Size
0x1401f0fe2  lea     rcx, [rsp+138h+var_88]; void *
0x1401f0fea  call    memset
0x1401f0fef  mov     rcx, [r15]
0x1401f0ff2  mov     [rsp+138h+var_D0], rcx
0x1401f0ff7  mov     r13d, [rdi+118h]
0x1401f0ffe  mov     [rsp+138h+var_D8], r13d
0x1401f1003  lea     rcx, [rdi+0D8h]
0x1401f100a  xor     edx, edx
0x1401f100c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401f1013  nop     dword ptr [rax+rax+00h]
0x1401f1018  mov     rax, [rsi+190h]
0x1401f101f  neg     rax
0x1401f1022  sbb     r9, r9
0x1401f1025  lea     rax, [rsp+138h+var_A8]
0x1401f102d  and     r9, rax
0x1401f1030  mov     r8, [rsp+138h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x1401f1035  mov     rdx, rdi; int
0x1401f1038  mov     rcx, rsi; int
0x1401f103b  call    NtfsMoveQuotaOwner
0x1401f1040  mov     rax, [rsp+138h+var_C0]
0x1401f1045  mov     [r15], rax
0x1401f1048  mov     eax, [rax+0Ch]
0x1401f104b  mov     [rdi+118h], eax
0x1401f1051  test    dword ptr [rdi+4], 800h
0x1401f1058  jz      short loc_1401F109C
0x1401f105a  xor     r15d, r15d
0x1401f105d  test    r13d, r13d
0x1401f1060  jz      short loc_1401F10A9
0x1401f1062  cmp     [rsi+190h], r15
0x1401f1069  jz      loc_1401F115D
0x1401f106f  lea     rax, [rsp+138h+var_A8]
0x1401f1077  mov     qword ptr [rsp+138h+PoolType], rax
0x1401f107c  mov     [rsp+138h+AutoInheritFlags], r13d
0x1401f1081  mov     r9d, ebx
0x1401f1084  mov     r8, rdi
0x1401f1087  mov     rdx, [rsp+138h+arg_8]
0x1401f108f  mov     rcx, rsi
0x1401f1092  call    TxfModifySecurity
0x1401f1097  jmp     loc_1401F115D
0x1401f109c  mov     rdx, rdi; int
0x1401f109f  mov     rcx, rsi; int
0x1401f10a2  call    NtfsGrowStandardInformation
0x1401f10a7  jmp     short loc_1401F105A
0x1401f10a9  lea     r8, [rdi+8]
0x1401f10ad  lea     rax, [rsp+138h+var_88]
0x1401f10b5  mov     [rsp+138h+var_F0], rax
0x1401f10ba  mov     [rsp+138h+var_F8], r15d
0x1401f10bf  mov     [rsp+138h+var_100], r15
0x1401f10c4  mov     byte ptr [rsp+138h+GenericMapping], r15b
0x1401f10c9  mov     qword ptr [rsp+138h+PoolType], r15
0x1401f10ce  mov     qword ptr [rsp+138h+AutoInheritFlags], r15
0x1401f10d3  mov     r9d, 50h ; 'P'
0x1401f10d9  mov     rdx, rdi
0x1401f10dc  mov     rcx, rsi
0x1401f10df  call    NtfsLookupInFileRecord
0x1401f10e4  test    al, al
0x1401f10e6  jz      loc_1401F1062
0x1401f10ec  mov     [rsp+138h+var_B8], 20000h
0x1401f10f8  lea     rax, word_140064400
0x1401f10ff  mov     [rsp+138h+var_B0], rax
0x1401f1107  lea     r9, [rsp+138h+var_88]
0x1401f110f  mov     r8d, 7
0x1401f1115  mov     rdx, rdi
0x1401f1118  mov     rcx, rsi
0x1401f111b  call    NtfsDeleteAttributeRecord
0x1401f1120  mov     [rsp+138h+GenericMapping], r15
0x1401f1125  mov     qword ptr [rsp+138h+PoolType], r15
0x1401f112a  mov     byte ptr [rsp+138h+AutoInheritFlags], 1
0x1401f112f  lea     r9, [rsp+138h+var_B8]
0x1401f1137  mov     r8d, 50h ; 'P'
0x1401f113d  mov     rdx, rdi
0x1401f1140  mov     rcx, rsi
0x1401f1143  call    NtfsCreateScb
0x1401f1148  test    rax, rax
0x1401f114b  jz      loc_1401F1062
0x1401f1151  or      dword ptr [rax+200h], 40h
0x1401f1158  jmp     loc_1401F1062
0x1401f115d  xor     r8d, r8d
0x1401f1160  mov     rdx, rdi
0x1401f1163  mov     rcx, rsi
0x1401f1166  call    NtfsUpdateStandardInformation
0x1401f116b  mov     rcx, rsi
0x1401f116e  call    NtfsCheckpointCurrentTransaction
0x1401f1173  nop
0x1401f1174  lea     rdx, [rsp+138h+var_88]
0x1401f117c  call    NtfsCleanupAttributeContext
0x1401f1181  lea     rcx, [rsp+138h+var_D0]
0x1401f1186  call    NtfsDereferenceSharedSecurity
0x1401f118b  xor     edx, edx
0x1401f118d  lea     rcx, [rdi+0D8h]
0x1401f1194  call    cs:__imp_ExReleasePushLockEx
0x1401f119b  nop     dword ptr [rax+rax+00h]
0x1401f11a0  jmp     short loc_1401F11DC
0x1401f11a2  mov     al, cs:NtfsStatusDebugFlags
0x1401f11a8  test    al, al
0x1401f11aa  jz      short loc_1401F11BF
0x1401f11ac  mov     edx, 0C000000Dh
0x1401f11b1  mov     r8d, 1F04CBh
0x1401f11b7  mov     rcx, rsi
0x1401f11ba  call    NtfsStatusTraceAndDebugInternal
0x1401f11bf  mov     qword ptr [rsp+138h+AutoInheritFlags], 1F04CBh
0x1401f11c8  xor     r9d, r9d
0x1401f11cb  xor     r8d, r8d
0x1401f11ce  mov     edx, 0C000000Dh
0x1401f11d3  mov     rcx, rsi
0x1401f11d6  call    NtfsRaiseStatusInternal
0x1401f11db  nop
0x1401f11dc  cmp     [rdi+78h], r12
0x1401f11e0  jnz     loc_1401F128E
0x1401f11e6  lea     rcx, [rsp+138h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x1401f11eb  call    cs:__imp_SeDeassignSecurity
0x1401f11f2  nop     dword ptr [rax+rax+00h]
0x1401f11f7  bts     dword ptr [rdi+0B8h], 8
0x1401f11ff  mov     eax, r14d
0x1401f1202  lea     r11, [rsp+138h+var_28]
0x1401f120a  mov     rbx, [r11+30h]
0x1401f120e  mov     rsi, [r11+48h]
0x1401f1212  mov     rsp, r11
0x1401f1215  pop     r15
0x1401f1217  pop     r14
0x1401f1219  pop     r13
0x1401f121b  pop     r12
0x1401f121d  pop     rdi
0x1401f121e  retn
0x1401f1220  mov     cl, cs:NtfsStatusDebugFlags
0x1401f1226  test    cl, cl
0x1401f1228  jz      short loc_1401F1266
0x1401f122a  cmp     r14d, 0FFFFFFEDh
0x1401f122e  jnb     short loc_1401F1266
0x1401f1230  cmp     r14d, 0C0000016h
0x1401f1237  jz      short loc_1401F1266
0x1401f1239  cmp     r14d, 0C0000011h
0x1401f1240  jz      short loc_1401F1266
0x1401f1242  add     eax, 7FFFFFFBh
0x1401f1247  cmp     eax, 1
0x1401f124a  jbe     short loc_1401F1266
0x1401f124c  cmp     r14d, 0C00000D8h
0x1401f1253  jz      short loc_1401F1266
0x1401f1255  mov     r8d, 1F04B8h
0x1401f125b  mov     edx, r14d
0x1401f125e  mov     rcx, rsi
0x1401f1261  call    NtfsStatusTraceAndDebugInternal
0x1401f1266  mov     qword ptr [rsp+138h+AutoInheritFlags], 1F04B8h
0x1401f126f  xor     r9d, r9d
0x1401f1272  xor     r8d, r8d
0x1401f1275  mov     edx, r14d
0x1401f1278  mov     rcx, rsi
0x1401f127b  call    NtfsRaiseStatusInternal
0x1401f1280  int     3; Trap to Debugger
0x1401f1281  mov     rdx, rdi
0x1401f1284  call    NtfsLoadSecurityDescriptor
0x1401f1289  jmp     loc_1401F0E51
0x1401f128e  test    r12, r12
0x1401f1291  jz      loc_1401F11E6
0x1401f1297  xor     r8d, r8d
0x1401f129a  lea     rdx, [rsp+138h+var_C8]
0x1401f129f  mov     rcx, [rdi+60h]
0x1401f12a3  call    NtfsDereferenceQuotaControlBlock
0x1401f12a8  jmp     loc_1401F11E6
0x1402b1b4e  push    rbx
0x1402b1b50  push    rbp
0x1402b1b51  sub     rsp, 58h
0x1402b1b55  mov     rbp, rdx
0x1402b1b58  movzx   ebx, cl
0x1402b1b5b  test    cl, cl
0x1402b1b5d  jz      short loc_1402B1B65
0x1402b1b5f  mov     al, cs:NtfsStatusDebugFlags
0x1402b1b65  lea     rdx, [rbp+0B0h]
0x1402b1b6c  call    NtfsCleanupAttributeContext
0x1402b1b71  mov     eax, ebx
0x1402b1b73  test    bl, bl
0x1402b1b75  jz      short loc_1402B1B9F
0x1402b1b77  mov     rax, [rbp+68h]
0x1402b1b7b  test    rax, rax
0x1402b1b7e  jz      short loc_1402B1B97
0x1402b1b80  mov     rcx, [rbp+150h]
0x1402b1b87  mov     [rcx+0D0h], rax
0x1402b1b8e  mov     eax, [rbp+60h]
0x1402b1b91  mov     [rcx+118h], eax
0x1402b1b97  mov     rax, [rbp+78h]
0x1402b1b9b  mov     [rbp+68h], rax
0x1402b1b9f  lea     rcx, [rbp+68h]
0x1402b1ba3  call    NtfsDereferenceSharedSecurity
0x1402b1ba8  mov     rcx, [rbp+150h]
0x1402b1baf  add     rcx, 0D8h
0x1402b1bb6  xor     edx, edx
0x1402b1bb8  call    cs:__imp_ExReleasePushLockEx
0x1402b1bbf  nop     dword ptr [rax+rax+00h]
0x1402b1bc4  nop
  ... truncated ...
```
