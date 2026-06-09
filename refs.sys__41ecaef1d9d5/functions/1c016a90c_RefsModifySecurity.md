# RefsModifySecurity

- ea: `0x1c016a90c`
- end: `0x1c016aac7`
- name: `RefsModifySecurity`
- size: `443`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1c0168d30`
- `0x1c016abac`
- `0x1c0171df4`
- `0x1c01c5714`

## callees

- `0x1c0003b94`
- `0x1c0003fb0`
- `0x1c0005430`
- `0x1c000f770`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c0151410`
- `0x1c015dfe8`
- `0x1c01632d4`
- `0x1c016a90c`
- `0x1c016aad0`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c016a960`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c016a960`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1c016a9a1`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1c016a9a1`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x1c016a986`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x1c016a986`
- `ntoskrnl!SeDeassignSecurity` at `0x1c016aa9a`
- `ntoskrnl!SeDeassignSecurity` at `0x1c017fda0`
- `ntoskrnl!SeDeassignSecurity` at `0x1c016aa9a`
- `ntoskrnl!SeDeassignSecurity` at `0x1c017fda0`

## pseudocode

```c
__int64 __fastcall RefsModifySecurity(__int64 a1, __int64 a2, DWORD *a3, void *a4)
{
  struct _GENERIC_MAPPING *GenericMapping; // rax
  NTSTATUS v9; // eax
  unsigned int v10; // esi
  ULONG v11; // eax
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 v15; // rcx
  __int64 v16; // [rsp+30h] [rbp-28h] BYREF
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+38h] [rbp-20h] BYREF
  __int64 v18; // [rsp+40h] [rbp-18h]
  __int64 v19; // [rsp+48h] [rbp-10h]

  if ( !*(_QWORD *)(a2 + 184) )
    RefsLoadSecurityDescriptor(a1, a2);
  if ( (unsigned __int8)RefsIsMinstoreTransactionActive(a1) && !(unsigned __int8)RefsIsModifyingTransactionActive() )
    RefsCheckpointCurrentTransaction(v15);
  ObjectsSecurityDescriptor = (PSECURITY_DESCRIPTOR)(*(_QWORD *)(a2 + 184) + 20LL);
  GenericMapping = IoGetFileObjectGenericMapping();
  v9 = SeSetSecurityDescriptorInfo(0, a3, a4, &ObjectsSecurityDescriptor, PagedPool, GenericMapping);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_838d735f45793e0c3968f803c105c9c3_Traceguids,
        (unsigned int)v9);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(v10);
    RefsRaiseStatusInternal(a1, v10);
    JUMPOUT(0x1C018671DLL);
  }
  v11 = RtlLengthSecurityDescriptor(ObjectsSecurityDescriptor);
  v19 = 0;
  v16 = 0;
  v18 = 0;
  if ( v11 )
  {
    LOBYTE(v12) = 1;
    v13 = RefsCacheSharedSecurityByDescriptor(a1, ObjectsSecurityDescriptor, v11, v12);
    v19 = v13;
    v16 = *(_QWORD *)(a2 + 184);
    v18 = *(_QWORD *)(a2 + 196);
    *(_QWORD *)(a2 + 184) = v13;
    *(_QWORD *)(a2 + 196) = *(_QWORD *)(v13 + 8);
    RefsUpdateStandardInformation(a1, a2);
    RefsCheckpointCurrentTransaction(a1);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_838d735f45793e0c3968f803c105c9c3_Traceguids, 3221225485LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    RefsRaiseStatusInternal(a1, 3221225485LL);
  }
  RefsDereferenceSharedSecurity(*(_QWORD *)(a2 + 88), &v16);
  SeDeassignSecurity(&ObjectsSecurityDescriptor);
  *(_DWORD *)(a2 + 168) |= 0x100u;
  return v10;
}

```

## disassembly

```asm
0x1c016a90c  mov     rax, rsp
0x1c016a90f  mov     [rax+8], rbx
0x1c016a913  mov     [rax+18h], rsi
0x1c016a917  mov     [rax+20h], rdi
0x1c016a91b  mov     [rax+10h], rdx
0x1c016a91f  push    r14
0x1c016a921  sub     rsp, 50h
0x1c016a925  mov     rsi, r9
0x1c016a928  mov     r14, r8
0x1c016a92b  mov     rbx, rdx
0x1c016a92e  mov     rdi, rcx
0x1c016a931  cmp     qword ptr [rdx+0B8h], 0
0x1c016a939  jnz     short loc_1C016A940
0x1c016a93b  call    RefsLoadSecurityDescriptor
0x1c016a940  mov     rcx, rdi
0x1c016a943  call    RefsIsMinstoreTransactionActive
0x1c016a948  test    al, al
0x1c016a94a  jnz     loc_1C01866A2
0x1c016a950  mov     rax, [rbx+0B8h]
0x1c016a957  add     rax, 14h
0x1c016a95b  mov     [rsp+58h+ObjectsSecurityDescriptor], rax
0x1c016a960  call    cs:__imp_IoGetFileObjectGenericMapping
0x1c016a967  nop     dword ptr [rax+rax+00h]
0x1c016a96c  mov     [rsp+58h+GenericMapping], rax; GenericMapping
0x1c016a971  mov     [rsp+58h+PoolType], 1; PoolType
0x1c016a979  lea     r9, [rsp+58h+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x1c016a97e  mov     r8, rsi; ModificationDescriptor
0x1c016a981  mov     rdx, r14; SecurityInformation
0x1c016a984  xor     ecx, ecx; Object
0x1c016a986  call    cs:__imp_SeSetSecurityDescriptorInfo
0x1c016a98d  nop     dword ptr [rax+rax+00h]
0x1c016a992  mov     esi, eax
0x1c016a994  test    eax, eax
0x1c016a996  js      loc_1C01866BA
0x1c016a99c  mov     rcx, [rsp+58h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x1c016a9a1  call    cs:__imp_RtlLengthSecurityDescriptor
0x1c016a9a8  nop     dword ptr [rax+rax+00h]
0x1c016a9ad  nop
0x1c016a9ae  and     [rsp+58h+var_10], 0
0x1c016a9b4  and     [rsp+58h+var_28], 0
0x1c016a9ba  and     [rsp+58h+var_18], 0
0x1c016a9c0  test    eax, eax
0x1c016a9c2  jz      short loc_1C016AA1B
0x1c016a9c4  mov     r9b, 1
0x1c016a9c7  mov     r8d, eax
0x1c016a9ca  mov     rdx, [rsp+58h+ObjectsSecurityDescriptor]
0x1c016a9cf  mov     rcx, rdi
0x1c016a9d2  call    RefsCacheSharedSecurityByDescriptor
0x1c016a9d7  mov     [rsp+58h+var_10], rax
0x1c016a9dc  mov     rcx, [rbx+0B8h]
0x1c016a9e3  mov     [rsp+58h+var_28], rcx
0x1c016a9e8  mov     rcx, [rbx+0C4h]
0x1c016a9ef  mov     [rsp+58h+var_18], rcx
0x1c016a9f4  mov     [rbx+0B8h], rax
0x1c016a9fb  mov     rax, [rax+8]
0x1c016a9ff  mov     [rbx+0C4h], rax
0x1c016aa06  mov     rdx, rbx
0x1c016aa09  mov     rcx, rdi
0x1c016aa0c  call    RefsUpdateStandardInformation
0x1c016aa11  mov     rcx, rdi
0x1c016aa14  call    RefsCheckpointCurrentTransaction
0x1c016aa19  jmp     short loc_1C016AA86
0x1c016aa1b  lea     rdx, WPP_GLOBAL_Control
0x1c016aa22  mov     rcx, cs:WPP_GLOBAL_Control
0x1c016aa29  cmp     rcx, rdx
0x1c016aa2c  jz      short loc_1C016AA58
0x1c016aa2e  mov     eax, [rcx+2Ch]
0x1c016aa31  bt      eax, 8
0x1c016aa35  jnb     short loc_1C016AA58
0x1c016aa37  cmp     byte ptr [rcx+29h], 4
0x1c016aa3b  jb      short loc_1C016AA58
0x1c016aa3d  mov     edx, 0Bh
0x1c016aa42  mov     r9d, 0C000000Dh
0x1c016aa48  lea     r8, WPP_838d735f45793e0c3968f803c105c9c3_Traceguids
0x1c016aa4f  mov     rcx, [rcx+18h]
0x1c016aa53  call    WPP_SF_D
0x1c016aa58  mov     al, cs:RefsStatusDebugEnabled
0x1c016aa5e  test    al, al
0x1c016aa60  jz      short loc_1C016AA79
0x1c016aa62  mov     r8d, 325h
0x1c016aa68  lea     rdx, aSecursupC; "SecurSup.c"
0x1c016aa6f  mov     ecx, 0C000000Dh; Status
0x1c016aa74  call    RefsStatusDebug
0x1c016aa79  mov     edx, 0C000000Dh
0x1c016aa7e  mov     rcx, rdi
0x1c016aa81  call    RefsRaiseStatusInternal
0x1c016aa86  lea     rdx, [rsp+58h+var_28]
0x1c016aa8b  mov     rcx, [rbx+58h]
0x1c016aa8f  call    RefsDereferenceSharedSecurity
0x1c016aa94  nop
0x1c016aa95  lea     rcx, [rsp+58h+ObjectsSecurityDescriptor]; SecurityDescriptor
0x1c016aa9a  call    cs:__imp_SeDeassignSecurity
0x1c016aaa1  nop     dword ptr [rax+rax+00h]
0x1c016aaa6  bts     dword ptr [rbx+0A8h], 8
0x1c016aaae  mov     eax, esi
0x1c016aab0  mov     rbx, [rsp+58h+arg_0]
0x1c016aab5  mov     rsi, [rsp+58h+arg_10]
0x1c016aaba  mov     rdi, [rsp+58h+arg_18]
0x1c016aabf  add     rsp, 50h
0x1c016aac3  pop     r14
0x1c016aac5  retn
0x1c017fd43  push    rbp
0x1c017fd45  sub     rsp, 30h
0x1c017fd49  mov     rbp, rdx
0x1c017fd4c  movzx   eax, cl
0x1c017fd4f  test    cl, cl
0x1c017fd51  jz      short loc_1C017FD7A
0x1c017fd53  mov     rax, [rbp+30h]
0x1c017fd57  test    rax, rax
0x1c017fd5a  jz      short loc_1C017FD72
0x1c017fd5c  mov     rcx, [rbp+68h]
0x1c017fd60  mov     [rcx+0B8h], rax
0x1c017fd67  mov     rax, [rbp+40h]
0x1c017fd6b  mov     [rcx+0C4h], rax
0x1c017fd72  mov     rax, [rbp+48h]
0x1c017fd76  mov     [rbp+30h], rax
0x1c017fd7a  lea     rdx, [rbp+30h]
0x1c017fd7e  mov     rcx, [rbp+68h]
0x1c017fd82  mov     rcx, [rcx+58h]
0x1c017fd86  call    RefsDereferenceSharedSecurity
0x1c017fd8b  nop
0x1c017fd8c  add     rsp, 30h
0x1c017fd90  pop     rbp
0x1c017fd91  retn
0x1c017fd93  push    rbp
0x1c017fd95  sub     rsp, 30h
0x1c017fd99  mov     rbp, rdx
0x1c017fd9c  lea     rcx, [rbp+38h]; SecurityDescriptor
0x1c017fda0  call    cs:__imp_SeDeassignSecurity
0x1c017fda7  nop     dword ptr [rax+rax+00h]
0x1c017fdac  nop
0x1c017fdad  add     rsp, 30h
0x1c017fdb1  pop     rbp
0x1c017fdb2  retn
0x1c01866a2  call    RefsIsModifyingTransactionActive
0x1c01866a7  test    al, al
0x1c01866a9  jnz     loc_1C016A950
0x1c01866af  call    RefsCheckpointCurrentTransaction
0x1c01866b4  nop
0x1c01866b5  jmp     loc_1C016A950
0x1c01866ba  lea     rdx, WPP_GLOBAL_Control
0x1c01866c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01866c8  cmp     rcx, rdx
0x1c01866cb  jz      short loc_1C01866F4
0x1c01866cd  test    dword ptr [rcx+2Ch], 100h
0x1c01866d4  jz      short loc_1C01866F4
0x1c01866d6  cmp     byte ptr [rcx+29h], 4
0x1c01866da  jb      short loc_1C01866F4
0x1c01866dc  mov     edx, 0Ah
0x1c01866e1  mov     r9d, esi
0x1c01866e4  lea     r8, WPP_838d735f45793e0c3968f803c105c9c3_Traceguids
0x1c01866eb  mov     rcx, [rcx+18h]
0x1c01866ef  call    WPP_SF_D
0x1c01866f4  mov     al, cs:RefsStatusDebugEnabled
0x1c01866fa  test    al, al
0x1c01866fc  jz      short loc_1C0186712
0x1c01866fe  mov     r8d, 314h
0x1c0186704  lea     rdx, aSecursupC; "SecurSup.c"
0x1c018670b  mov     ecx, esi; Status
0x1c018670d  call    RefsStatusDebug
0x1c0186712  mov     edx, esi
0x1c0186714  mov     rcx, rdi
0x1c0186717  call    RefsRaiseStatusInternal
0x1c018671c  nop
```
