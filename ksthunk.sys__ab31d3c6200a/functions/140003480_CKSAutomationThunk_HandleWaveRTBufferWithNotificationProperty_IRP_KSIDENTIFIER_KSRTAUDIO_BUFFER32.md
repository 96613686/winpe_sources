# CKSAutomationThunk::HandleWaveRTBufferWithNotificationProperty(_IRP *,KSIDENTIFIER *,KSRTAUDIO_BUFFER32 *)

- ea: `0x140003480`
- end: `0x140003557`
- name: `?HandleWaveRTBufferWithNotificationProperty@CKSAutomationThunk@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAUKSRTAUDIO_BUFFER32@@@Z`
- size: `215`
- prototype: `NTSTATUS __fastcall(struct _IRP *, struct KSIDENTIFIER *, struct KSRTAUDIO_BUFFER32 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140003480`

## import_xrefs

- `ks!KsSynchronousIoControlDevice` at `0x140003518`
- `ks!KsSynchronousIoControlDevice` at `0x140003518`

## pseudocode

```c
NTSTATUS __fastcall CKSAutomationThunk::HandleWaveRTBufferWithNotificationProperty(
        struct _IRP *a1,
        struct KSIDENTIFIER *a2,
        struct KSRTAUDIO_BUFFER32 *a3)
{
  GUID Set; // xmm1
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  NTSTATUS result; // eax
  __int128 v8; // [rsp+40h] [rbp-40h] BYREF
  GUID InBuffer; // [rsp+50h] [rbp-30h] BYREF
  ULONG Id; // [rsp+60h] [rbp-20h]
  ULONG Flags; // [rsp+64h] [rbp-1Ch]
  __int64 Data1; // [rsp+68h] [rbp-18h]
  int Alignment_high; // [rsp+70h] [rbp-10h]
  int v14; // [rsp+74h] [rbp-Ch]
  ULONG v15; // [rsp+90h] [rbp+10h] BYREF

  Set = a2->Set;
  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  Id = a2->Id;
  Flags = a2->Flags;
  Data1 = a2[1].Set.Data1;
  Alignment_high = HIDWORD(a2[1].Alignment);
  v14 = *((_DWORD *)&a2[1].Alignment + 2);
  v15 = 0;
  v8 = 0;
  InBuffer = Set;
  result = KsSynchronousIoControlDevice(
             CurrentStackLocation->FileObject,
             0,
             0x2F0003u,
             &InBuffer,
             0x28u,
             &v8,
             0x10u,
             &v15);
  if ( result >= 0 && (a2->Flags & 1) != 0 )
  {
    a3->BufferAddress = v8;
    *(_QWORD *)&a3->ActualBufferSize = *((_QWORD *)&v8 + 1);
  }
  return result;
}

```

## disassembly

```asm
0x140003480  mov     r11, rsp
0x140003483  mov     [r11+10h], rbx
0x140003487  mov     [r11+18h], rdi
0x14000348b  push    rbp
0x14000348c  mov     rbp, rsp
0x14000348f  sub     rsp, 80h
0x140003496  mov     eax, [rdx+10h]
0x140003499  lea     r9, [rbp+InBuffer]; InBuffer
0x14000349d  movups  xmm1, xmmword ptr [rdx]
0x1400034a0  mov     rcx, [rcx+0B8h]
0x1400034a7  mov     rbx, r8
0x1400034aa  mov     [rbp+var_20], eax
0x1400034ad  xorps   xmm0, xmm0
0x1400034b0  mov     eax, [rdx+14h]
0x1400034b3  mov     rdi, rdx
0x1400034b6  mov     [rbp+var_1C], eax
0x1400034b9  mov     r8d, 2F0003h; IoControl
0x1400034bf  mov     eax, [rdx+18h]
0x1400034c2  mov     [rbp+var_18], rax
0x1400034c6  mov     eax, [rdx+1Ch]
0x1400034c9  mov     [rbp+var_10], eax
0x1400034cc  mov     eax, [rdx+20h]
0x1400034cf  xor     edx, edx; RequestorMode
0x1400034d1  mov     [rbp+var_C], eax
0x1400034d4  lea     rax, [rbp+arg_0]
0x1400034d8  mov     [r11-50h], rax
0x1400034dc  lea     rax, [rbp+var_40]
0x1400034e0  mov     qword ptr [rbp+InBuffer], 0
0x1400034e8  mov     qword ptr [rbp+InBuffer+8], 0
0x1400034f0  mov     [rbp+arg_0], 0
0x1400034f7  movups  [rbp+var_40], xmm0
0x1400034fb  mov     [rsp+80h+OutSize], 10h; OutSize
0x140003503  movdqu  [rbp+InBuffer], xmm1
0x140003508  mov     rcx, [rcx+30h]; FileObject
0x14000350c  mov     [r11-60h], rax
0x140003510  mov     [rsp+80h+InSize], 28h ; '('; InSize
0x140003518  call    cs:__imp_KsSynchronousIoControlDevice
0x14000351f  nop     dword ptr [rax+rax+00h]
0x140003524  test    eax, eax
0x140003526  js      short loc_140003541
0x140003528  mov     ecx, [rdi+14h]
0x14000352b  test    cl, 1
0x14000352e  jz      short loc_140003541
0x140003530  mov     ecx, dword ptr [rbp+var_40]
0x140003533  mov     [rbx], ecx
0x140003535  mov     ecx, dword ptr [rbp+var_40+8]
0x140003538  mov     [rbx+4], ecx
0x14000353b  mov     ecx, dword ptr [rbp+var_40+0Ch]
0x14000353e  mov     [rbx+8], ecx
0x140003541  lea     r11, [rsp+80h+var_s0]
0x140003549  mov     rbx, [r11+18h]
0x14000354d  mov     rdi, [r11+20h]
0x140003551  mov     rsp, r11
0x140003554  pop     rbp
0x140003555  retn
```
