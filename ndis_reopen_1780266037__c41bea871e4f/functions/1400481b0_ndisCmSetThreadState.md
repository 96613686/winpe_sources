# ndisCmSetThreadState

- ea: `0x1400481b0`
- end: `0x140048397`
- name: `ndisCmSetThreadState`
- size: `487`
- prototype: `__int64 __fastcall(PETHREAD Thread)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400ce8f0`
- `0x14016b1f0`
- `0x14016fde0`

## callees

- `0x1400481b0`
- `0x1400483a0`
- `0x140048440`
- `0x1400484a0`
- `0x140048750`
- `0x1400d155c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14004829d`
- `ntoskrnl!ObfDereferenceObject` at `0x140048305`
- `ntoskrnl!ObfDereferenceObject` at `0x14004829d`
- `ntoskrnl!ObfDereferenceObject` at `0x140048305`
- `ntoskrnl!PsGetThreadProperty` at `0x140048210`
- `ntoskrnl!PsGetThreadProperty` at `0x140048210`
- `ntoskrnl!PsSetThreadProperty` at `0x1400482c6`
- `ntoskrnl!PsSetThreadProperty` at `0x1400482c6`

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
0x1400481b0  mov     rax, rsp
0x1400481b3  push    rdi
0x1400481b4  sub     rsp, 50h
0x1400481b8  mov     [rax+8], rbx
0x1400481bc  xor     dil, dil
0x1400481bf  mov     [rax+18h], rbp
0x1400481c3  mov     rbx, r8
0x1400481c6  mov     [rax-10h], rsi
0x1400481ca  mov     rsi, rdx
0x1400481cd  mov     [rax-18h], r12
0x1400481d1  xor     r12d, r12d
0x1400481d4  mov     [rax-20h], r14
0x1400481d8  mov     r14, rcx
0x1400481db  mov     [rax-28h], r15
0x1400481df  mov     ebp, r12d
0x1400481e2  mov     [rax-38h], r12
0x1400481e6  test    rdx, rdx
0x1400481e9  jnz     loc_14004832E
0x1400481ef  test    rbx, rbx
0x1400481f2  jz      short loc_140048202
0x1400481f4  mov     eax, [rbx]
0x1400481f6  cmp     eax, 0FFFFFFFFh
0x1400481f9  jnz     loc_14004831A
0x1400481ff  mov     dil, 1
0x140048202  mov     edx, 6D43644Eh; Key
0x140048207  mov     r8d, 1; Flags
0x14004820d  mov     rcx, r14; Thread
0x140048210  call    cs:__imp_PsGetThreadProperty
0x140048217  nop     dword ptr [rax+rax+00h]
0x14004821c  mov     [rsp+58h+Object], rax
0x140048221  mov     rcx, rax
0x140048224  test    rax, rax
0x140048227  jnz     short loc_140048272
0x140048229  test    dil, dil
0x14004822c  jz      loc_140048329
0x140048232  lea     rcx, [rsp+58h+Object]; struct _NDIS_CM_STATE **
0x140048237  call    ?ndisCmCreateStateObject@@YAJPEAPEAU_NDIS_CM_STATE@@@Z; ndisCmCreateStateObject(_NDIS_CM_STATE * *)
0x14004823c  mov     edi, eax
0x14004823e  test    eax, eax
0x140048240  js      loc_1400482D4
0x140048246  test    rsi, rsi
0x140048249  jz      short loc_140048261
0x14004824b  mov     ecx, [rsi]
0x14004824d  mov     rdx, rbp; void *
0x140048250  mov     rax, [rsp+58h+Object]
0x140048255  mov     [rax], ecx
0x140048257  mov     rcx, [rsp+58h+Object]; struct _NDIS_CM_STATE *
0x14004825c  call    ?ndisCmAssignCompartmentHandleToCmState@@YAXPEAU_NDIS_CM_STATE@@PEAX@Z; ndisCmAssignCompartmentHandleToCmState(_NDIS_CM_STATE *,void *)
0x140048261  test    rbx, rbx
0x140048264  jz      short loc_1400482B9
0x140048266  mov     rax, [rsp+58h+Object]
0x14004826b  mov     ecx, [rbx]
0x14004826d  mov     [rax+4], ecx
0x140048270  jmp     short loc_1400482B9
0x140048272  xor     r15b, r15b
0x140048275  test    rsi, rsi
0x140048278  jnz     loc_140048374
0x14004827e  test    rbx, rbx
0x140048281  jz      short loc_14004828D
0x140048283  mov     rax, [rsp+58h+Object]
0x140048288  mov     ecx, [rbx]
0x14004828a  mov     [rax+4], ecx
0x14004828d  mov     rcx, [rsp+58h+Object]; Object
0x140048292  cmp     [rcx], r12d
0x140048295  jnz     short loc_1400482B1
0x140048297  cmp     [rcx+4], r12d
0x14004829b  jnz     short loc_1400482B1
0x14004829d  call    cs:__imp_ObfDereferenceObject
0x1400482a4  nop     dword ptr [rax+rax+00h]
0x1400482a9  mov     [rsp+58h+Object], r12
0x1400482ae  mov     r15b, 1
0x1400482b1  mov     edi, r12d
0x1400482b4  test    r15b, r15b
0x1400482b7  jz      short loc_1400482D4
0x1400482b9  mov     r8, [rsp+58h+Object]
0x1400482be  mov     edx, 6D43644Eh
0x1400482c3  mov     rcx, r14
0x1400482c6  call    cs:__imp_PsSetThreadProperty
0x1400482cd  nop     dword ptr [rax+rax+00h]
0x1400482d2  mov     edi, eax
0x1400482d4  test    rbp, rbp
0x1400482d7  jnz     loc_14004838A
0x1400482dd  mov     rcx, [rsp+58h+Object]; Object
0x1400482e2  mov     r15, [rsp+58h+var_28]
0x1400482e7  mov     r14, [rsp+58h+var_20]
0x1400482ec  mov     r12, [rsp+58h+var_18]
0x1400482f1  mov     rsi, [rsp+58h+var_10]
0x1400482f6  mov     rbp, [rsp+58h+arg_10]
0x1400482fb  mov     rbx, [rsp+58h+arg_0]
0x140048300  test    rcx, rcx
0x140048303  jz      short loc_140048311
0x140048305  call    cs:__imp_ObfDereferenceObject
0x14004830c  nop     dword ptr [rax+rax+00h]
0x140048311  mov     eax, edi
0x140048313  add     rsp, 50h
0x140048317  pop     rdi
0x140048318  retn
0x14004831a  test    eax, eax
0x14004831c  jz      loc_140048202
0x140048322  mov     edi, 0C000000Dh
0x140048327  jmp     short loc_1400482D4
0x140048329  mov     edi, r12d
0x14004832c  jmp     short loc_1400482D4
0x14004832e  mov     r15d, [rdx]
0x140048331  test    r15d, r15d
0x140048334  jz      loc_1400481EF
0x14004833a  lea     r8, [rsp+58h+arg_18]
0x14004833f  mov     [rsp+58h+arg_8], r12d
0x140048344  lea     rdx, [rsp+58h+arg_8]
0x140048349  call    ndisCmGetThreadState
0x14004834e  mov     ecx, [rsp+58h+arg_8]; unsigned int
0x140048352  mov     edx, r15d; unsigned int
0x140048355  call    ?ndisCmValidateCompartmentChange@@YAPEAXII@Z; ndisCmValidateCompartmentChange(uint,uint)
0x14004835a  mov     rbp, rax
0x14004835d  test    rax, rax
0x140048360  jnz     short loc_14004836C
0x140048362  mov     edi, 0C0000225h
0x140048367  jmp     loc_1400482DD
0x14004836c  mov     dil, 1
0x14004836f  jmp     loc_1400481EF
0x140048374  mov     eax, [rsi]
0x140048376  mov     rdx, rbp; void *
0x140048379  mov     [rcx], eax
0x14004837b  mov     rcx, [rsp+58h+Object]; struct _NDIS_CM_STATE *
0x140048380  call    ?ndisCmAssignCompartmentHandleToCmState@@YAXPEAU_NDIS_CM_STATE@@PEAX@Z; ndisCmAssignCompartmentHandleToCmState(_NDIS_CM_STATE *,void *)
0x140048385  jmp     loc_14004827E
0x14004838a  mov     rcx, rbp; void *
0x14004838d  call    ?ndisIfDereferenceCompartmentForUser@@YAJPEAX@Z; ndisIfDereferenceCompartmentForUser(void *)
0x140048392  jmp     loc_1400482DD
```
