# CKsPin::Property_StreamAllocator(_IRP *,KSIDENTIFIER *,void * *)

- ea: `0x180041220`
- end: `0x1800414b0`
- name: `?Property_StreamAllocator@CKsPin@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAPEAX@Z`
- size: `656`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000b7bc`
- `0x18000c058`
- `0x18000da50`
- `0x18000dddc`
- `0x180041220`
- `0x1800511c0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x180041446`
- `ntoskrnl!ObfDereferenceObject` at `0x180041460`
- `ntoskrnl!ObfDereferenceObject` at `0x180041446`
- `ntoskrnl!ObfDereferenceObject` at `0x180041460`
- `ntoskrnl!ExGetPreviousMode` at `0x180041393`
- `ntoskrnl!ExGetPreviousMode` at `0x180041393`
- `ntoskrnl!KeReleaseMutex` at `0x180041489`
- `ntoskrnl!KeReleaseMutex` at `0x180041489`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1800413c2`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1800413c2`
- `ntoskrnl!IoFileObjectType` at `0x18004139f`
- `ntoskrnl!KeWaitForSingleObject` at `0x180041331`
- `ntoskrnl!KeWaitForSingleObject` at `0x180041331`

## pseudocode

```c
__int64 __fastcall CKsPin::Property_StreamAllocator(struct _IRP *a1, struct KSIDENTIFIER *a2, void **a3)
{
  struct KSIDENTIFIER *v4; // rbx
  __int64 v6; // r14
  __int64 v7; // rdi
  NTSTATUS v8; // ebx
  int v9; // edx
  int v10; // r8d
  KPROCESSOR_MODE PreviousMode; // al
  void *v12; // rcx
  __int128 OutBuffer; // [rsp+40h] [rbp-30h] BYREF
  GUID InBuffer; // [rsp+50h] [rbp-20h] BYREF
  int v16; // [rsp+60h] [rbp-10h]
  int v17; // [rsp+64h] [rbp-Ch]
  ULONG BytesReturned; // [rsp+B0h] [rbp+40h] BYREF
  PVOID Object; // [rsp+B8h] [rbp+48h] BYREF

  v4 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      136,
      (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
  }
  v6 = *(_QWORD *)(*(_QWORD *)a1->Tail.Overlay.CurrentStackLocation->FileObject->FsContext + 112LL);
  v7 = v6 - 128;
  if ( (v4->Flags & 1) == 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_qq(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        (_DWORD)a3,
        138,
        (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
        v6 + 0x80,
        (char)*a3);
    }
    KeWaitForSingleObject(*(PVOID *)(v6 + 88), Executive, 0, 0, 0);
    if ( *(_DWORD *)(v6 + 248) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v9) = 5;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          v10,
          139,
          (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
          *(_DWORD *)(v6 + 248));
      }
      v8 = -1073741436;
      goto LABEL_27;
    }
    v8 = 0;
    Object = 0;
    if ( *a3 )
    {
      PreviousMode = ExGetPreviousMode();
      v8 = ObReferenceObjectByHandle(*a3, 0x100001u, (POBJECT_TYPE)IoFileObjectType, PreviousMode, &Object, 0);
      if ( v8 < 0 )
      {
LABEL_27:
        KeReleaseMutex(*(PRKMUTEX *)(v6 + 88), 0);
        return (unsigned int)v8;
      }
      InBuffer = GUID_cf6e4342_ec87_11cf_a130_0020afd156e4;
      v16 = 0;
      v17 = 1;
      OutBuffer = 0;
      BytesReturned = 0;
      v8 = KsSynchronousIoControlDevice(
             (PFILE_OBJECT)Object,
             0,
             0x2F0003u,
             &InBuffer,
             0x18u,
             &OutBuffer,
             0x10u,
             &BytesReturned);
      if ( v8 < 0 )
      {
LABEL_22:
        ObfDereferenceObject(Object);
        goto LABEL_27;
      }
      if ( BytesReturned != 16 )
      {
        v8 = -1073741306;
        goto LABEL_22;
      }
    }
    v12 = *(void **)(v7 + 600);
    if ( v12 )
    {
      ObfDereferenceObject(v12);
      *(_QWORD *)(v7 + 600) = 0;
    }
    if ( *a3 )
      *(_QWORD *)(v7 + 600) = Object;
    goto LABEL_27;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      137,
      (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
      v6 + 0x80);
  }
  *a3 = 0;
  return 0;
}

```

## disassembly

```asm
0x180041220  mov     [rsp-38h+arg_10], rbx
0x180041225  push    rbp
0x180041226  push    rsi
0x180041227  push    rdi
0x180041228  push    r12
0x18004122a  push    r13
0x18004122c  push    r14
0x18004122e  push    r15
0x180041230  mov     rbp, rsp
0x180041233  sub     rsp, 70h
0x180041237  mov     rsi, r8
0x18004123a  mov     rbx, rdx
0x18004123d  mov     rdi, rcx
0x180041240  lea     r12, WPP_RECORDER_INITIALIZED
0x180041247  xor     r15d, r15d
0x18004124a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180041251  lea     r13, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x180041258  jz      short loc_180041282
0x18004125a  mov     rcx, cs:WPP_GLOBAL_Control
0x180041261  cmp     [rcx+48h], r15w
0x180041266  jz      short loc_180041282
0x180041268  mov     rcx, [rcx+40h]
0x18004126c  lea     r8d, [r15+1]
0x180041270  mov     r9d, 88h
0x180041276  mov     [rsp+70h+Timeout], r13
0x18004127b  mov     dl, 5
0x18004127d  call    WPP_RECORDER_SF_
0x180041282  mov     rax, [rdi+0B8h]
0x180041289  mov     rcx, [rax+30h]
0x18004128d  mov     rax, [rcx+18h]
0x180041291  mov     rcx, [rax]
0x180041294  mov     eax, [rbx+14h]
0x180041297  mov     r14, [rcx+70h]
0x18004129b  lea     rdi, [r14-80h]
0x18004129f  test    al, 1
0x1800412a1  jz      short loc_1800412E6
0x1800412a3  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800412aa  jz      short loc_1800412DB
0x1800412ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800412b3  cmp     [rcx+48h], r15w
0x1800412b8  jz      short loc_1800412DB
0x1800412ba  mov     rcx, [rcx+40h]
0x1800412be  mov     r9d, 89h
0x1800412c4  mov     [rsp+70h+HandleInformation], rdi
0x1800412c9  mov     r8d, 1
0x1800412cf  mov     dl, 5
0x1800412d1  mov     [rsp+70h+Timeout], r13
0x1800412d6  call    WPP_RECORDER_SF_q
0x1800412db  mov     [rsi], r15
0x1800412de  mov     ebx, r15d
0x1800412e1  jmp     loc_180041495
0x1800412e6  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800412ed  jz      short loc_180041320
0x1800412ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800412f6  cmp     [rcx+48h], r15w
0x1800412fb  jz      short loc_180041320
0x1800412fd  mov     rax, [rsi]
0x180041300  mov     r9d, 8Ah
0x180041306  mov     rcx, [rcx+40h]
0x18004130a  mov     dl, 5
0x18004130c  mov     qword ptr [rsp+70h+OutSize], rax
0x180041311  mov     [rsp+70h+HandleInformation], rdi
0x180041316  mov     [rsp+70h+Timeout], r13
0x18004131b  call    WPP_RECORDER_SF_qq
0x180041320  mov     rcx, [r14+58h]; Object
0x180041324  xor     r9d, r9d; Alertable
0x180041327  xor     r8d, r8d; WaitMode
0x18004132a  mov     [rsp+70h+Timeout], r15; Timeout
0x18004132f  xor     edx, edx; WaitReason
0x180041331  call    cs:__imp_KeWaitForSingleObject
0x180041338  nop     dword ptr [rax+rax+00h]
0x18004133d  mov     eax, [r14+0F8h]
0x180041344  test    eax, eax
0x180041346  jz      short loc_180041383
0x180041348  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18004134f  jz      short loc_180041379
0x180041351  mov     rcx, cs:WPP_GLOBAL_Control
0x180041358  cmp     [rcx+48h], r15w
0x18004135d  jz      short loc_180041379
0x18004135f  mov     rcx, [rcx+40h]
0x180041363  mov     r9d, 8Bh
0x180041369  mov     dword ptr [rsp+70h+HandleInformation], eax
0x18004136d  mov     dl, 5
0x18004136f  mov     [rsp+70h+Timeout], r13
0x180041374  call    WPP_RECORDER_SF_d
0x180041379  mov     ebx, 0C0000184h
0x18004137e  jmp     loc_180041483
0x180041383  mov     ebx, r15d
0x180041386  mov     [rbp+Object], r15
0x18004138a  cmp     [rsi], r15
0x18004138d  jz      loc_180041454
0x180041393  call    cs:__imp_ExGetPreviousMode
0x18004139a  nop     dword ptr [rax+rax+00h]
0x18004139f  mov     r8, cs:__imp_IoFileObjectType
0x1800413a6  lea     rcx, [rbp+Object]
0x1800413aa  mov     [rsp+70h+HandleInformation], r15; HandleInformation
0x1800413af  mov     r9b, al; AccessMode
0x1800413b2  mov     [rsp+70h+Timeout], rcx; Object
0x1800413b7  mov     edx, 100001h; DesiredAccess
0x1800413bc  mov     rcx, [rsi]; Handle
0x1800413bf  mov     r8, [r8]; ObjectType
0x1800413c2  call    cs:__imp_ObReferenceObjectByHandle
0x1800413c9  nop     dword ptr [rax+rax+00h]
0x1800413ce  mov     ebx, eax
0x1800413d0  test    eax, eax
0x1800413d2  js      loc_180041483
0x1800413d8  movups  xmm0, xmmword ptr cs:_GUID_cf6e4342_ec87_11cf_a130_0020afd156e4.Data1
0x1800413df  mov     rcx, [rbp+Object]; FileObject
0x1800413e3  lea     rax, [rbp+arg_0]
0x1800413e7  mov     [rsp+70h+BytesReturned], rax; BytesReturned
0x1800413ec  lea     r9, [rbp+InBuffer]; InBuffer
0x1800413f0  movdqu  [rbp+InBuffer], xmm0
0x1800413f5  lea     rax, [rbp+OutBuffer]
0x1800413f9  mov     [rsp+70h+OutSize], 10h; OutSize
0x180041401  xorps   xmm0, xmm0
0x180041404  mov     [rsp+70h+HandleInformation], rax; OutBuffer
0x180041409  xor     edx, edx; RequestorMode
0x18004140b  mov     [rbp+var_10], r15d
0x18004140f  mov     r8d, 2F0003h; IoControl
0x180041415  mov     [rbp+var_C], 1
0x18004141c  movups  [rbp+OutBuffer], xmm0
0x180041420  mov     [rbp+arg_0], r15d
0x180041424  mov     dword ptr [rsp+70h+Timeout], 18h; InSize
0x18004142c  call    KsSynchronousIoControlDevice
0x180041431  mov     ebx, eax
0x180041433  test    eax, eax
0x180041435  js      short loc_180041442
0x180041437  cmp     [rbp+arg_0], 10h
0x18004143b  jz      short loc_180041454
0x18004143d  mov     ebx, 0C0000206h
0x180041442  mov     rcx, [rbp+Object]; Object
0x180041446  call    cs:__imp_ObfDereferenceObject
0x18004144d  nop     dword ptr [rax+rax+00h]
0x180041452  jmp     short loc_180041483
0x180041454  mov     rcx, [rdi+258h]; Object
0x18004145b  test    rcx, rcx
0x18004145e  jz      short loc_180041473
0x180041460  call    cs:__imp_ObfDereferenceObject
0x180041467  nop     dword ptr [rax+rax+00h]
0x18004146c  mov     [rdi+258h], r15
0x180041473  cmp     [rsi], r15
0x180041476  jz      short loc_180041483
0x180041478  mov     rax, [rbp+Object]
0x18004147c  mov     [rdi+258h], rax
0x180041483  mov     rcx, [r14+58h]; Mutex
0x180041487  xor     edx, edx; Wait
0x180041489  call    cs:__imp_KeReleaseMutex
0x180041490  nop     dword ptr [rax+rax+00h]
0x180041495  mov     eax, ebx
0x180041497  mov     rbx, [rsp+70h+arg_10]
0x18004149f  add     rsp, 70h
0x1800414a3  pop     r15
0x1800414a5  pop     r14
0x1800414a7  pop     r13
0x1800414a9  pop     r12
0x1800414ab  pop     rdi
0x1800414ac  pop     rsi
0x1800414ad  pop     rbp
0x1800414ae  retn
```
