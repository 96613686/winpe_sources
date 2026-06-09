# ndisCmSetThreadState

- ea: `0x1400436b0`
- end: `0x140043897`
- name: `ndisCmSetThreadState`
- size: `487`
- prototype: `__int64 __fastcall(PETHREAD Thread)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400c9740`
- `0x140164260`
- `0x140168ef0`

## callees

- `0x1400436b0`
- `0x1400438a0`
- `0x140043940`
- `0x1400439a0`
- `0x140043c50`
- `0x1400cc3ac`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14004379d`
- `ntoskrnl!ObfDereferenceObject` at `0x140043805`
- `ntoskrnl!ObfDereferenceObject` at `0x14004379d`
- `ntoskrnl!ObfDereferenceObject` at `0x140043805`
- `ntoskrnl!PsGetThreadProperty` at `0x140043710`
- `ntoskrnl!PsGetThreadProperty` at `0x140043710`
- `ntoskrnl!PsSetThreadProperty` at `0x1400437c6`
- `ntoskrnl!PsSetThreadProperty` at `0x1400437c6`

## pseudocode

```c
__int64 __fastcall ndisCmSetThreadState(PETHREAD Thread, unsigned int *a2, _DWORD *a3)
{
  char v3; // di
  void *v7; // rbp
  int StateObject; // edi
  char v9; // r15
  unsigned int v11; // r15d
  PVOID Object; // [rsp+20h] [rbp-38h] BYREF
  unsigned int v13; // [rsp+68h] [rbp+10h] BYREF
  int v14; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  v7 = 0;
  Object = 0;
  if ( a2 )
  {
    v11 = *a2;
    if ( *a2 )
    {
      v13 = 0;
      ndisCmGetThreadState(Thread, &v13, &v14);
      v7 = ndisCmValidateCompartmentChange(v13, v11);
      if ( !v7 )
      {
        StateObject = -1073741275;
        goto LABEL_23;
      }
      v3 = 1;
    }
  }
  if ( a3 )
  {
    if ( *a3 == -1 )
    {
      v3 = 1;
    }
    else if ( *a3 )
    {
      StateObject = -1073741811;
      goto LABEL_21;
    }
  }
  Object = PsGetThreadProperty(Thread, 0x6D43644Eu, 1u);
  if ( Object )
  {
    v9 = 0;
    if ( a2 )
    {
      *(_DWORD *)Object = *a2;
      ndisCmAssignCompartmentHandleToCmState((struct _NDIS_CM_STATE *)Object, v7);
    }
    if ( a3 )
      *((_DWORD *)Object + 1) = *a3;
    if ( !*(_DWORD *)Object && !*((_DWORD *)Object + 1) )
    {
      ObfDereferenceObject(Object);
      Object = 0;
      v9 = 1;
    }
    StateObject = 0;
    if ( !v9 )
      goto LABEL_21;
LABEL_20:
    StateObject = PsSetThreadProperty(Thread, 1833133134, Object);
    goto LABEL_21;
  }
  if ( v3 )
  {
    StateObject = ndisCmCreateStateObject((struct _NDIS_CM_STATE **)&Object);
    if ( StateObject < 0 )
      goto LABEL_21;
    if ( a2 )
    {
      *(_DWORD *)Object = *a2;
      ndisCmAssignCompartmentHandleToCmState((struct _NDIS_CM_STATE *)Object, v7);
    }
    if ( a3 )
      *((_DWORD *)Object + 1) = *a3;
    goto LABEL_20;
  }
  StateObject = 0;
LABEL_21:
  if ( v7 )
    ndisIfDereferenceCompartmentForUser(v7);
LABEL_23:
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)StateObject;
}

```

## disassembly

```asm
0x1400436b0  mov     rax, rsp
0x1400436b3  push    rdi
0x1400436b4  sub     rsp, 50h
0x1400436b8  mov     [rax+8], rbx
0x1400436bc  xor     dil, dil
0x1400436bf  mov     [rax+18h], rbp
0x1400436c3  mov     rbx, r8
0x1400436c6  mov     [rax-10h], rsi
0x1400436ca  mov     rsi, rdx
0x1400436cd  mov     [rax-18h], r12
0x1400436d1  xor     r12d, r12d
0x1400436d4  mov     [rax-20h], r14
0x1400436d8  mov     r14, rcx
0x1400436db  mov     [rax-28h], r15
0x1400436df  mov     ebp, r12d
0x1400436e2  mov     [rax-38h], r12
0x1400436e6  test    rdx, rdx
0x1400436e9  jnz     loc_14004382E
0x1400436ef  test    rbx, rbx
0x1400436f2  jz      short loc_140043702
0x1400436f4  mov     eax, [rbx]
0x1400436f6  cmp     eax, 0FFFFFFFFh
0x1400436f9  jnz     loc_14004381A
0x1400436ff  mov     dil, 1
0x140043702  mov     edx, 6D43644Eh; Key
0x140043707  mov     r8d, 1; Flags
0x14004370d  mov     rcx, r14; Thread
0x140043710  call    cs:__imp_PsGetThreadProperty
0x140043717  nop     dword ptr [rax+rax+00h]
0x14004371c  mov     [rsp+58h+Object], rax
0x140043721  mov     rcx, rax
0x140043724  test    rax, rax
0x140043727  jnz     short loc_140043772
0x140043729  test    dil, dil
0x14004372c  jz      loc_140043829
0x140043732  lea     rcx, [rsp+58h+Object]; struct _NDIS_CM_STATE **
0x140043737  call    ?ndisCmCreateStateObject@@YAJPEAPEAU_NDIS_CM_STATE@@@Z; ndisCmCreateStateObject(_NDIS_CM_STATE * *)
0x14004373c  mov     edi, eax
0x14004373e  test    eax, eax
0x140043740  js      loc_1400437D4
0x140043746  test    rsi, rsi
0x140043749  jz      short loc_140043761
0x14004374b  mov     ecx, [rsi]
0x14004374d  mov     rdx, rbp; void *
0x140043750  mov     rax, [rsp+58h+Object]
0x140043755  mov     [rax], ecx
0x140043757  mov     rcx, [rsp+58h+Object]; struct _NDIS_CM_STATE *
0x14004375c  call    ?ndisCmAssignCompartmentHandleToCmState@@YAXPEAU_NDIS_CM_STATE@@PEAX@Z; ndisCmAssignCompartmentHandleToCmState(_NDIS_CM_STATE *,void *)
0x140043761  test    rbx, rbx
0x140043764  jz      short loc_1400437B9
0x140043766  mov     rax, [rsp+58h+Object]
0x14004376b  mov     ecx, [rbx]
0x14004376d  mov     [rax+4], ecx
0x140043770  jmp     short loc_1400437B9
0x140043772  xor     r15b, r15b
0x140043775  test    rsi, rsi
0x140043778  jnz     loc_140043874
0x14004377e  test    rbx, rbx
0x140043781  jz      short loc_14004378D
0x140043783  mov     rax, [rsp+58h+Object]
0x140043788  mov     ecx, [rbx]
0x14004378a  mov     [rax+4], ecx
0x14004378d  mov     rcx, [rsp+58h+Object]; Object
0x140043792  cmp     [rcx], r12d
0x140043795  jnz     short loc_1400437B1
0x140043797  cmp     [rcx+4], r12d
0x14004379b  jnz     short loc_1400437B1
0x14004379d  call    cs:__imp_ObfDereferenceObject
0x1400437a4  nop     dword ptr [rax+rax+00h]
0x1400437a9  mov     [rsp+58h+Object], r12
0x1400437ae  mov     r15b, 1
0x1400437b1  mov     edi, r12d
0x1400437b4  test    r15b, r15b
0x1400437b7  jz      short loc_1400437D4
0x1400437b9  mov     r8, [rsp+58h+Object]
0x1400437be  mov     edx, 6D43644Eh
0x1400437c3  mov     rcx, r14
0x1400437c6  call    cs:__imp_PsSetThreadProperty
0x1400437cd  nop     dword ptr [rax+rax+00h]
0x1400437d2  mov     edi, eax
0x1400437d4  test    rbp, rbp
0x1400437d7  jnz     loc_14004388A
0x1400437dd  mov     rcx, [rsp+58h+Object]; Object
0x1400437e2  mov     r15, [rsp+58h+var_28]
0x1400437e7  mov     r14, [rsp+58h+var_20]
0x1400437ec  mov     r12, [rsp+58h+var_18]
0x1400437f1  mov     rsi, [rsp+58h+var_10]
0x1400437f6  mov     rbp, [rsp+58h+arg_10]
0x1400437fb  mov     rbx, [rsp+58h+arg_0]
0x140043800  test    rcx, rcx
0x140043803  jz      short loc_140043811
0x140043805  call    cs:__imp_ObfDereferenceObject
0x14004380c  nop     dword ptr [rax+rax+00h]
0x140043811  mov     eax, edi
0x140043813  add     rsp, 50h
0x140043817  pop     rdi
0x140043818  retn
0x14004381a  test    eax, eax
0x14004381c  jz      loc_140043702
0x140043822  mov     edi, 0C000000Dh
0x140043827  jmp     short loc_1400437D4
0x140043829  mov     edi, r12d
0x14004382c  jmp     short loc_1400437D4
0x14004382e  mov     r15d, [rdx]
0x140043831  test    r15d, r15d
0x140043834  jz      loc_1400436EF
0x14004383a  lea     r8, [rsp+58h+arg_18]
0x14004383f  mov     [rsp+58h+arg_8], r12d
0x140043844  lea     rdx, [rsp+58h+arg_8]
0x140043849  call    ndisCmGetThreadState
0x14004384e  mov     ecx, [rsp+58h+arg_8]; unsigned int
0x140043852  mov     edx, r15d; unsigned int
0x140043855  call    ?ndisCmValidateCompartmentChange@@YAPEAXII@Z; ndisCmValidateCompartmentChange(uint,uint)
0x14004385a  mov     rbp, rax
0x14004385d  test    rax, rax
0x140043860  jnz     short loc_14004386C
0x140043862  mov     edi, 0C0000225h
0x140043867  jmp     loc_1400437DD
0x14004386c  mov     dil, 1
0x14004386f  jmp     loc_1400436EF
0x140043874  mov     eax, [rsi]
0x140043876  mov     rdx, rbp; void *
0x140043879  mov     [rcx], eax
0x14004387b  mov     rcx, [rsp+58h+Object]; struct _NDIS_CM_STATE *
0x140043880  call    ?ndisCmAssignCompartmentHandleToCmState@@YAXPEAU_NDIS_CM_STATE@@PEAX@Z; ndisCmAssignCompartmentHandleToCmState(_NDIS_CM_STATE *,void *)
0x140043885  jmp     loc_14004377E
0x14004388a  mov     rcx, rbp; void *
0x14004388d  call    ?ndisIfDereferenceCompartmentForUser@@YAJPEAX@Z; ndisIfDereferenceCompartmentForUser(void *)
0x140043892  jmp     loc_1400437DD
```
