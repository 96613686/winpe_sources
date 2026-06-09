# FatInvalidateVolumes

- ea: `0x140005604`
- end: `0x14000591c`
- name: `FatInvalidateVolumes`
- size: `792`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003f2c0`

## callees

- `0x140005604`
- `0x140006350`
- `0x14000c680`
- `0x140038eb4`
- `0x14003dae0`
- `0x1400465f4`
- `0x1400466c8`
- `0x140048740`
- `0x140049bd4`

## import_xrefs

- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140005787`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140005787`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400057e9`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x1400057e9`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x140005640`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x140005640`
- `ntoskrnl!IoIs32bitProcess` at `0x14000566c`
- `ntoskrnl!IoIs32bitProcess` at `0x14000566c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400056c7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400056c7`
- `ntoskrnl!IoFileObjectType` at `0x1400056a6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005721`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140005721`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000585f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005889`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400058ce`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400058ee`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000585f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005889`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400058ce`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400058ee`
- `ntoskrnl!ObfDereferenceObject` at `0x1400056e1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400056e1`

## pseudocode

```c
__int64 __fastcall FatInvalidateVolumes(PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  PIRP v2; // rdi
  KPROCESSOR_MODE RequestorMode; // dl
  __int64 v4; // r9
  NTSTATUS v5; // ebx
  BOOLEAN v7; // al
  ULONG Options; // ecx
  void *v9; // rcx
  __int64 v10; // r15
  __int64 v11; // r9
  __int64 *v12; // r14
  __int64 v13; // rsi
  __int64 v14; // r9
  _DWORD *v15; // rbx
  bool v16; // zf
  __int64 v17; // rcx
  __int64 i; // rdx
  __int64 NextFcbBottomUp; // rax
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // r10
  __int64 v24; // rbx
  __int64 v25; // rcx
  __int64 j; // rdx
  __int64 v27; // rax
  __int64 v28; // rbx
  __int64 v29; // rdx
  __int64 v30; // r9
  _DWORD v31[48]; // [rsp+30h] [rbp-69h] BYREF
  LUID PrivilegeValue; // [rsp+108h] [rbp+6Fh] BYREF
  PVOID Object; // [rsp+110h] [rbp+77h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v2 = Irp;
  RequestorMode = Irp->RequestorMode;
  PrivilegeValue = (LUID)7LL;
  Object = 0;
  if ( !SeSinglePrivilegeCheck((LUID)7LL, RequestorMode) )
  {
    v5 = -1073741727;
LABEL_3:
    FatCompleteRequest_Real(0, v2, (unsigned int)v5, v4);
    return (unsigned int)v5;
  }
  v7 = IoIs32bitProcess(v2);
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( v7 )
  {
    if ( Options == 4 )
    {
      v9 = (void *)*(int *)v2->AssociatedIrp.MasterIrp;
      goto LABEL_10;
    }
LABEL_8:
    v5 = -1073741811;
    goto LABEL_3;
  }
  if ( Options != 8 )
    goto LABEL_8;
  v9 = *(void **)v2->AssociatedIrp.MasterIrp;
LABEL_10:
  v5 = ObReferenceObjectByHandle(v9, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
  if ( v5 < 0 )
    goto LABEL_3;
  ObfDereferenceObject(Object);
  v10 = *((_QWORD *)Object + 1);
  memset(v31, 0, 0x90u);
  LOWORD(v31[16]) = *(_WORD *)&CurrentStackLocation->MajorFunction;
  v31[17] = 2;
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  v12 = (__int64 *)qword_140017CB0;
  if ( (__int64 *)qword_140017CB0 != &qword_140017CB0 )
  {
    do
    {
      v13 = (__int64)(v12 - 15);
      v12 = (__int64 *)*v12;
      if ( *(_QWORD *)(*(_QWORD *)(v13 + 192) + 16LL) == v10 )
      {
        FatAcquireExclusiveVcb_Real(v31, v13, 0, v11);
        if ( *(_QWORD *)(v13 + 192) == *(_QWORD *)(v10 + 56) )
        {
          LOBYTE(PrivilegeValue.LowPart) = 0;
          IoAcquireVpbSpinLock((PKIRQL)&PrivilegeValue);
          if ( (*(_BYTE *)(*(_QWORD *)(v10 + 56) + 4LL) & 1) != 0 )
          {
            v15 = *(_DWORD **)(v13 + 1128);
            *(_QWORD *)(v13 + 1128) = 0;
            _InterlockedOr((volatile signed __int32 *)(v13 + 200), 0x40000u);
            memset(v15, 0, 0x60u);
            *v15 = 6291466;
            *((_QWORD *)v15 + 2) = v10;
            *((_WORD *)v15 + 2) = *(_WORD *)(*(_QWORD *)(v10 + 56) + 4LL) & 8;
            *(_QWORD *)(v10 + 56) = v15;
          }
          IoReleaseVpbSpinLock(PrivilegeValue.LowPart);
        }
        v16 = *(_QWORD *)(v13 + 208) == 0;
        *(_DWORD *)(v13 + 204) = 3;
        if ( v16 )
          goto LABEL_25;
        FatAcquireExclusiveVcb_Real(v31, v13, 0, v14);
        for ( i = 0; ; i = v24 )
        {
          NextFcbBottomUp = FatGetNextFcbBottomUp(v17, i, *(_QWORD *)(v13 + 208));
          v24 = NextFcbBottomUp;
          if ( !NextFcbBottomUp )
            break;
          FatAcquireExclusiveFcb(v31, NextFcbBottomUp, v21, v22);
        }
        LOBYTE(v22) = 1;
        FatMarkFcbCondition(v20, v23, 2, v22);
        for ( j = 0; ; j = v28 )
        {
          v27 = FatGetNextFcbBottomUp(v25, j, *(_QWORD *)(v13 + 208));
          v28 = v27;
          if ( !v27 )
            break;
          ExReleaseResourceLite(*(PERESOURCE *)(v27 + 8));
        }
        ExReleaseResourceLite((PERESOURCE)(v13 + 520));
        v29 = *(_QWORD *)(v13 + 208);
        ++*(_DWORD *)(v13 + 272);
        FatPurgeReferencedFileObjects(v31, v29, 0);
        --*(_DWORD *)(v13 + 272);
        if ( !FatCheckForDismount((__int64)v31, v13, 0) )
LABEL_25:
          ExReleaseResourceLite((PERESOURCE)(v13 + 520));
      }
    }
    while ( v12 != &qword_140017CB0 );
    v2 = Irp;
  }
  ExReleaseResourceLite(&Resource);
  FatCompleteRequest_Real(0, v2, 0, v30);
  return 0;
}

```

## disassembly

```asm
0x140005604  mov     [rsp-8+arg_0], rcx
0x140005609  push    rbp
0x14000560a  push    rbx
0x14000560b  push    rsi
0x14000560c  push    rdi
0x14000560d  push    r13
0x14000560f  push    r14
0x140005611  push    r15
0x140005613  lea     rbp, [rsp-27h]
0x140005618  sub     rsp, 0C0h
0x14000561f  mov     rsi, [rcx+0B8h]
0x140005626  mov     rdi, rcx
0x140005629  mov     dl, [rcx+40h]; PreviousMode
0x14000562c  mov     qword ptr [rbp+57h+PrivilegeValue.LowPart], 7
0x140005634  mov     rcx, qword ptr [rbp+57h+PrivilegeValue.LowPart]; PrivilegeValue
0x140005638  mov     [rbp+57h+arg_10], 0
0x140005640  call    cs:__imp_SeSinglePrivilegeCheck
0x140005647  nop     dword ptr [rax+rax+00h]
0x14000564c  test    al, al
0x14000564e  jnz     short loc_140005669
0x140005650  mov     ebx, 0C0000061h
0x140005655  mov     r8d, ebx
0x140005658  mov     rdx, rdi; Irp
0x14000565b  xor     ecx, ecx; Entry
0x14000565d  call    FatCompleteRequest_Real
0x140005662  mov     eax, ebx
0x140005664  jmp     loc_140005909
0x140005669  mov     rcx, rdi; Irp
0x14000566c  call    cs:__imp_IoIs32bitProcess
0x140005673  nop     dword ptr [rax+rax+00h]
0x140005678  mov     ecx, [rsi+10h]
0x14000567b  mov     r13d, 8
0x140005681  test    al, al
0x140005683  jz      short loc_140005693
0x140005685  cmp     ecx, 4
0x140005688  jnz     short loc_140005698
0x14000568a  mov     rax, [rdi+18h]
0x14000568e  movsxd  rcx, dword ptr [rax]
0x140005691  jmp     short loc_1400056A6
0x140005693  cmp     ecx, r13d
0x140005696  jz      short loc_14000569F
0x140005698  mov     ebx, 0C000000Dh
0x14000569d  jmp     short loc_140005655
0x14000569f  mov     rax, [rdi+18h]
0x1400056a3  mov     rcx, [rax]; Handle
0x1400056a6  mov     r8, cs:__imp_IoFileObjectType
0x1400056ad  lea     rax, [rbp+57h+arg_10]
0x1400056b1  mov     [rsp+0F0h+HandleInformation], 0; HandleInformation
0x1400056ba  xor     r9d, r9d; AccessMode
0x1400056bd  xor     edx, edx; DesiredAccess
0x1400056bf  mov     [rsp+0F0h+Object], rax; Object
0x1400056c4  mov     r8, [r8]; ObjectType
0x1400056c7  call    cs:__imp_ObReferenceObjectByHandle
0x1400056ce  nop     dword ptr [rax+rax+00h]
0x1400056d3  mov     ebx, eax
0x1400056d5  test    eax, eax
0x1400056d7  js      loc_140005655
0x1400056dd  mov     rcx, [rbp+57h+arg_10]; Object
0x1400056e1  call    cs:__imp_ObfDereferenceObject
0x1400056e8  nop     dword ptr [rax+rax+00h]
0x1400056ed  mov     rax, [rbp+57h+arg_10]
0x1400056f1  lea     rcx, [rbp+57h+var_C0]; void *
0x1400056f5  xor     edx, edx; Val
0x1400056f7  mov     r8d, 90h; Size
0x1400056fd  mov     r15, [rax+8]
0x140005701  call    memset
0x140005706  mov     al, [rsi]
0x140005708  lea     rcx, Resource; Resource
0x14000570f  mov     [rbp+57h+var_80], al
0x140005712  mov     dl, 1; Wait
0x140005714  mov     al, [rsi+1]
0x140005717  mov     [rbp+57h+var_7F], al
0x14000571a  mov     [rbp+57h+var_7C], 2
0x140005721  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140005728  nop     dword ptr [rax+rax+00h]
0x14000572d  mov     r14, cs:qword_140017CB0
0x140005734  lea     rax, qword_140017CB0
0x14000573b  cmp     r14, rax
0x14000573e  jz      loc_1400058E7
0x140005744  lea     rdi, qword_140017CB0
0x14000574b  lea     rsi, [r14-78h]
0x14000574f  mov     r14, [r14]
0x140005752  mov     rax, [rsi+0C0h]
0x140005759  cmp     [rax+10h], r15
0x14000575d  jnz     loc_1400058DA
0x140005763  xor     r8d, r8d
0x140005766  lea     rcx, [rbp+57h+var_C0]
0x14000576a  mov     rdx, rsi
0x14000576d  call    FatAcquireExclusiveVcb_Real
0x140005772  mov     rax, [r15+38h]
0x140005776  cmp     [rsi+0C0h], rax
0x14000577d  jnz     short loc_1400057F5
0x14000577f  lea     rcx, [rbp+57h+PrivilegeValue]; Irql
0x140005783  mov     byte ptr [rbp+57h+PrivilegeValue.LowPart], 0
0x140005787  call    cs:__imp_IoAcquireVpbSpinLock
0x14000578e  nop     dword ptr [rax+rax+00h]
0x140005793  mov     rax, [r15+38h]
0x140005797  test    byte ptr [rax+4], 1
0x14000579b  jz      short loc_1400057E6
0x14000579d  mov     rbx, [rsi+468h]
0x1400057a4  mov     qword ptr [rsi+468h], 0
0x1400057af  lock or dword ptr [rsi+0C8h], 40000h
0x1400057ba  xor     edx, edx; Val
0x1400057bc  mov     rcx, rbx; void *
0x1400057bf  lea     r8d, [rdx+60h]; Size
0x1400057c3  call    memset
0x1400057c8  mov     dword ptr [rbx], 60000Ah
0x1400057ce  mov     [rbx+10h], r15
0x1400057d2  mov     rax, [r15+38h]
0x1400057d6  movzx   ecx, word ptr [rax+4]
0x1400057da  and     cx, r13w
0x1400057de  mov     [rbx+4], cx
0x1400057e2  mov     [r15+38h], rbx
0x1400057e6  mov     cl, byte ptr [rbp+57h+PrivilegeValue.LowPart]; Irql
0x1400057e9  call    cs:__imp_IoReleaseVpbSpinLock
0x1400057f0  nop     dword ptr [rax+rax+00h]
0x1400057f5  cmp     qword ptr [rsi+0D0h], 0
0x1400057fd  mov     dword ptr [rsi+0CCh], 3
0x140005807  jz      loc_1400058C7
0x14000580d  xor     r8d, r8d
0x140005810  lea     rcx, [rbp+57h+var_C0]
0x140005814  mov     rdx, rsi
0x140005817  call    FatAcquireExclusiveVcb_Real
0x14000581c  xor     edx, edx
0x14000581e  jmp     short loc_14000582F
0x140005820  mov     rdx, rbx
0x140005823  lea     rcx, [rbp+57h+var_C0]
0x140005827  call    FatAcquireExclusiveFcb
0x14000582c  mov     rdx, rbx
0x14000582f  mov     r10, [rsi+0D0h]
0x140005836  mov     r8, r10
0x140005839  call    FatGetNextFcbBottomUp
0x14000583e  mov     rbx, rax
0x140005841  test    rax, rax
0x140005844  jnz     short loc_140005820
0x140005846  mov     r9b, 1
0x140005849  mov     r8d, 2
0x14000584f  mov     rdx, r10
0x140005852  call    FatMarkFcbCondition
0x140005857  xor     edx, edx
0x140005859  jmp     short loc_14000586E
0x14000585b  mov     rcx, [rbx+8]; Resource
0x14000585f  call    cs:__imp_ExReleaseResourceLite
0x140005866  nop     dword ptr [rax+rax+00h]
0x14000586b  mov     rdx, rbx
0x14000586e  mov     r8, [rsi+0D0h]
0x140005875  call    FatGetNextFcbBottomUp
0x14000587a  mov     rbx, rax
0x14000587d  test    rax, rax
0x140005880  jnz     short loc_14000585B
0x140005882  lea     rcx, [rsi+208h]; Resource
0x140005889  call    cs:__imp_ExReleaseResourceLite
0x140005890  nop     dword ptr [rax+rax+00h]
0x140005895  mov     rdx, [rsi+0D0h]
0x14000589c  lea     rcx, [rbp+57h+var_C0]
0x1400058a0  inc     dword ptr [rsi+110h]
0x1400058a6  xor     r8d, r8d
0x1400058a9  call    FatPurgeReferencedFileObjects
0x1400058ae  dec     dword ptr [rsi+110h]
0x1400058b4  lea     rcx, [rbp+57h+var_C0]
0x1400058b8  xor     r8d, r8d
0x1400058bb  mov     rdx, rsi
0x1400058be  call    FatCheckForDismount
0x1400058c3  test    al, al
0x1400058c5  jnz     short loc_1400058DA
0x1400058c7  lea     rcx, [rsi+208h]; Resource
0x1400058ce  call    cs:__imp_ExReleaseResourceLite
0x1400058d5  nop     dword ptr [rax+rax+00h]
0x1400058da  cmp     r14, rdi
0x1400058dd  jnz     loc_14000574B
0x1400058e3  mov     rdi, [rbp+57h+arg_0]
0x1400058e7  lea     rcx, Resource; Resource
0x1400058ee  call    cs:__imp_ExReleaseResourceLite
0x1400058f5  nop     dword ptr [rax+rax+00h]
0x1400058fa  xor     r8d, r8d
0x1400058fd  mov     rdx, rdi; Irp
0x140005900  xor     ecx, ecx; Entry
0x140005902  call    FatCompleteRequest_Real
0x140005907  xor     eax, eax
0x140005909  add     rsp, 0C0h
0x140005910  pop     r15
0x140005912  pop     r14
0x140005914  pop     r13
0x140005916  pop     rdi
0x140005917  pop     rsi
0x140005918  pop     rbx
0x140005919  pop     rbp
0x14000591a  retn
```
