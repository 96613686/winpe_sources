# CKSAutomationThunk::HandleWaveRTHWRegisterProperty(_IRP *,KSIDENTIFIER *,KSRTAUDIO_HWREGISTER32 *)

- ea: `0x140002c00`
- end: `0x140002cea`
- name: `?HandleWaveRTHWRegisterProperty@CKSAutomationThunk@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAUKSRTAUDIO_HWREGISTER32@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, struct KSRTAUDIO_HWREGISTER32 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140002c00`

## import_xrefs

- `ks!KsSynchronousIoControlDevice` at `0x140002c97`
- `ks!KsSynchronousIoControlDevice` at `0x140002c97`

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
0x140002c00  mov     r11, rsp
0x140002c03  mov     [r11+10h], rbx
0x140002c07  mov     [r11+18h], rdi
0x140002c0b  push    rbp
0x140002c0c  lea     rbp, [r11-5Fh]
0x140002c10  sub     rsp, 90h
0x140002c17  mov     rcx, [rcx+0B8h]
0x140002c1e  lea     r9, [rbp+57h+InBuffer]; InBuffer
0x140002c22  xor     eax, eax
0x140002c24  mov     qword ptr [rbp+57h+InBuffer], 0
0x140002c2c  mov     [rbp+57h+var_10], rax
0x140002c30  xorps   xmm0, xmm0
0x140002c33  mov     eax, [rdx+10h]
0x140002c36  mov     rbx, r8
0x140002c39  mov     [rbp+57h+var_40], eax
0x140002c3c  mov     rdi, rdx
0x140002c3f  mov     eax, [rdx+14h]
0x140002c42  mov     r8d, 2F0003h; IoControl
0x140002c48  mov     [rbp+57h+var_3C], eax
0x140002c4b  mov     eax, [rdx+18h]
0x140002c4e  mov     [rbp+57h+var_38], rax
0x140002c52  lea     rax, [rbp+57h+arg_0]
0x140002c56  mov     [r11-60h], rax
0x140002c5a  lea     rax, [rbp+57h+var_30]
0x140002c5e  movups  [rbp+57h+var_30], xmm0
0x140002c62  mov     qword ptr [rbp+57h+InBuffer+8], 0
0x140002c6a  movups  [rbp+57h+var_20], xmm0
0x140002c6e  mov     [rbp+57h+arg_0], 0
0x140002c75  movups  xmm0, xmmword ptr [rdx]
0x140002c78  mov     [rsp+90h+OutSize], 28h ; '('; OutSize
0x140002c80  xor     edx, edx; RequestorMode
0x140002c82  mov     [r11-70h], rax
0x140002c86  movdqu  [rbp+57h+InBuffer], xmm0
0x140002c8b  mov     rcx, [rcx+30h]; FileObject
0x140002c8f  mov     [rsp+90h+InSize], 20h ; ' '; InSize
0x140002c97  call    cs:__imp_KsSynchronousIoControlDevice
0x140002c9e  nop     dword ptr [rax+rax+00h]
0x140002ca3  mov     edx, eax
0x140002ca5  test    eax, eax
0x140002ca7  js      short loc_140002CD2
0x140002ca9  mov     ecx, [rdi+14h]
0x140002cac  test    cl, 1
0x140002caf  jz      short loc_140002CD2
0x140002cb1  mov     ecx, dword ptr [rbp+57h+var_30]
0x140002cb4  mov     eax, dword ptr [rbp+57h+var_10]
0x140002cb7  mov     [rbx], ecx
0x140002cb9  mov     ecx, dword ptr [rbp+57h+var_30+8]
0x140002cbc  mov     [rbx+4], ecx
0x140002cbf  mov     rcx, qword ptr [rbp+57h+var_20]
0x140002cc3  mov     [rbx+8], rcx
0x140002cc7  mov     rcx, qword ptr [rbp+57h+var_20+8]
0x140002ccb  mov     [rbx+10h], rcx
0x140002ccf  mov     [rbx+18h], eax
0x140002cd2  lea     r11, [rsp+90h+var_s0]
0x140002cda  mov     eax, edx
0x140002cdc  mov     rbx, [r11+18h]
0x140002ce0  mov     rdi, [r11+20h]
0x140002ce4  mov     rsp, r11
0x140002ce7  pop     rbp
0x140002ce8  retn
```
