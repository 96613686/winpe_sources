# CKSAutomationThunk::HandleWaveRTHWRegisterProperty(_IRP *,KSIDENTIFIER *,KSRTAUDIO_HWREGISTER32 *)

- ea: `0x140003560`
- end: `0x14000364a`
- name: `?HandleWaveRTHWRegisterProperty@CKSAutomationThunk@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAUKSRTAUDIO_HWREGISTER32@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, struct KSRTAUDIO_HWREGISTER32 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140003560`

## import_xrefs

- `ks!KsSynchronousIoControlDevice` at `0x1400035f7`
- `ks!KsSynchronousIoControlDevice` at `0x1400035f7`

## pseudocode

```c
__int64 __fastcall CKSAutomationThunk::HandleWaveRTHWRegisterProperty(
        struct _IRP *a1,
        struct KSIDENTIFIER *a2,
        struct KSRTAUDIO_HWREGISTER32 *a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  NTSTATUS v6; // edx
  ULONG v7; // eax
  GUID InBuffer; // [rsp+48h] [rbp+7h] BYREF
  ULONG Id; // [rsp+58h] [rbp+17h]
  ULONG Flags; // [rsp+5Ch] [rbp+1Bh]
  __int64 Data1; // [rsp+60h] [rbp+1Fh]
  __int128 v13; // [rsp+68h] [rbp+27h] BYREF
  __int128 v14; // [rsp+78h] [rbp+37h]
  __int64 v15; // [rsp+88h] [rbp+47h]
  ULONG v16; // [rsp+A8h] [rbp+67h] BYREF

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  InBuffer = (GUID)0LL;
  v15 = 0;
  Id = a2->Id;
  Flags = a2->Flags;
  Data1 = a2[1].Set.Data1;
  v13 = 0;
  v14 = 0;
  v16 = 0;
  InBuffer = a2->Set;
  v6 = KsSynchronousIoControlDevice(CurrentStackLocation->FileObject, 0, 0x2F0003u, &InBuffer, 0x20u, &v13, 0x28u, &v16);
  if ( v6 >= 0 && (a2->Flags & 1) != 0 )
  {
    v7 = v15;
    a3->Register = v13;
    a3->Width = DWORD2(v13);
    *(_OWORD *)&a3->Numerator = v14;
    a3->Accuracy = v7;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140003560  mov     r11, rsp
0x140003563  mov     [r11+10h], rbx
0x140003567  mov     [r11+18h], rdi
0x14000356b  push    rbp
0x14000356c  lea     rbp, [r11-5Fh]
0x140003570  sub     rsp, 90h
0x140003577  mov     rcx, [rcx+0B8h]
0x14000357e  lea     r9, [rbp+57h+InBuffer]; InBuffer
0x140003582  xor     eax, eax
0x140003584  mov     qword ptr [rbp+57h+InBuffer], 0
0x14000358c  mov     [rbp+57h+var_10], rax
0x140003590  xorps   xmm0, xmm0
0x140003593  mov     eax, [rdx+10h]
0x140003596  mov     rbx, r8
0x140003599  mov     [rbp+57h+var_40], eax
0x14000359c  mov     rdi, rdx
0x14000359f  mov     eax, [rdx+14h]
0x1400035a2  mov     r8d, 2F0003h; IoControl
0x1400035a8  mov     [rbp+57h+var_3C], eax
0x1400035ab  mov     eax, [rdx+18h]
0x1400035ae  mov     [rbp+57h+var_38], rax
0x1400035b2  lea     rax, [rbp+57h+arg_0]
0x1400035b6  mov     [r11-60h], rax
0x1400035ba  lea     rax, [rbp+57h+var_30]
0x1400035be  movups  [rbp+57h+var_30], xmm0
0x1400035c2  mov     qword ptr [rbp+57h+InBuffer+8], 0
0x1400035ca  movups  [rbp+57h+var_20], xmm0
0x1400035ce  mov     [rbp+57h+arg_0], 0
0x1400035d5  movups  xmm0, xmmword ptr [rdx]
0x1400035d8  mov     [rsp+90h+OutSize], 28h ; '('; OutSize
0x1400035e0  xor     edx, edx; RequestorMode
0x1400035e2  mov     [r11-70h], rax
0x1400035e6  movdqu  [rbp+57h+InBuffer], xmm0
0x1400035eb  mov     rcx, [rcx+30h]; FileObject
0x1400035ef  mov     [rsp+90h+InSize], 20h ; ' '; InSize
0x1400035f7  call    cs:__imp_KsSynchronousIoControlDevice
0x1400035fe  nop     dword ptr [rax+rax+00h]
0x140003603  mov     edx, eax
0x140003605  test    eax, eax
0x140003607  js      short loc_140003632
0x140003609  mov     ecx, [rdi+14h]
0x14000360c  test    cl, 1
0x14000360f  jz      short loc_140003632
0x140003611  mov     ecx, dword ptr [rbp+57h+var_30]
0x140003614  mov     eax, dword ptr [rbp+57h+var_10]
0x140003617  mov     [rbx], ecx
0x140003619  mov     ecx, dword ptr [rbp+57h+var_30+8]
0x14000361c  mov     [rbx+4], ecx
0x14000361f  mov     rcx, qword ptr [rbp+57h+var_20]
0x140003623  mov     [rbx+8], rcx
0x140003627  mov     rcx, qword ptr [rbp+57h+var_20+8]
0x14000362b  mov     [rbx+10h], rcx
0x14000362f  mov     [rbx+18h], eax
0x140003632  lea     r11, [rsp+90h+var_s0]
0x14000363a  mov     eax, edx
0x14000363c  mov     rbx, [r11+18h]
0x140003640  mov     rdi, [r11+20h]
0x140003644  mov     rsp, r11
0x140003647  pop     rbp
0x140003648  retn
```
