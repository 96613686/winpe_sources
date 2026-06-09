# CKSAutomationThunk::HandleWaveRTBufferProperty(_IRP *,KSIDENTIFIER *,KSRTAUDIO_BUFFER32 *)

- ea: `0x1400033a0`
- end: `0x140003478`
- name: `?HandleWaveRTBufferProperty@CKSAutomationThunk@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAUKSRTAUDIO_BUFFER32@@@Z`
- size: `216`
- prototype: `NTSTATUS __fastcall(struct _IRP *, struct KSIDENTIFIER *, struct KSRTAUDIO_BUFFER32 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1400033a0`

## import_xrefs

- `ks!KsSynchronousIoControlDevice` at `0x140003439`
- `ks!KsSynchronousIoControlDevice` at `0x140003439`

## pseudocode

```c
NTSTATUS __fastcall CKSAutomationThunk::HandleWaveRTBufferProperty(
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
  v15 = 0;
  v14 = 0;
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
0x1400033a0  mov     r11, rsp
0x1400033a3  mov     [r11+10h], rbx
0x1400033a7  mov     [r11+18h], rdi
0x1400033ab  push    rbp
0x1400033ac  mov     rbp, rsp
0x1400033af  sub     rsp, 80h
0x1400033b6  mov     eax, [rdx+10h]
0x1400033b9  lea     r9, [rbp+InBuffer]; InBuffer
0x1400033bd  movups  xmm1, xmmword ptr [rdx]
0x1400033c0  mov     rcx, [rcx+0B8h]
0x1400033c7  mov     rbx, r8
0x1400033ca  mov     [rbp+var_20], eax
0x1400033cd  xorps   xmm0, xmm0
0x1400033d0  mov     eax, [rdx+14h]
0x1400033d3  mov     rdi, rdx
0x1400033d6  mov     [rbp+var_1C], eax
0x1400033d9  mov     r8d, 2F0003h; IoControl
0x1400033df  mov     eax, [rdx+18h]
0x1400033e2  mov     [rbp+var_18], rax
0x1400033e6  mov     eax, [rdx+1Ch]
0x1400033e9  xor     edx, edx; RequestorMode
0x1400033eb  mov     [rbp+var_10], eax
0x1400033ee  lea     rax, [rbp+arg_0]
0x1400033f2  mov     [r11-50h], rax
0x1400033f6  lea     rax, [rbp+var_40]
0x1400033fa  mov     qword ptr [rbp+InBuffer], 0
0x140003402  mov     qword ptr [rbp+InBuffer+8], 0
0x14000340a  mov     [rbp+arg_0], 0
0x140003411  mov     [rbp+var_C], 0
0x140003418  movups  [rbp+var_40], xmm0
0x14000341c  mov     [rsp+80h+OutSize], 10h; OutSize
0x140003424  movdqu  [rbp+InBuffer], xmm1
0x140003429  mov     rcx, [rcx+30h]; FileObject
0x14000342d  mov     [r11-60h], rax
0x140003431  mov     [rsp+80h+InSize], 28h ; '('; InSize
0x140003439  call    cs:__imp_KsSynchronousIoControlDevice
0x140003440  nop     dword ptr [rax+rax+00h]
0x140003445  test    eax, eax
0x140003447  js      short loc_140003462
0x140003449  mov     ecx, [rdi+14h]
0x14000344c  test    cl, 1
0x14000344f  jz      short loc_140003462
0x140003451  mov     ecx, dword ptr [rbp+var_40]
0x140003454  mov     [rbx], ecx
0x140003456  mov     ecx, dword ptr [rbp+var_40+8]
0x140003459  mov     [rbx+4], ecx
0x14000345c  mov     ecx, dword ptr [rbp+var_40+0Ch]
0x14000345f  mov     [rbx+8], ecx
0x140003462  lea     r11, [rsp+80h+var_s0]
0x14000346a  mov     rbx, [r11+18h]
0x14000346e  mov     rdi, [r11+20h]
0x140003472  mov     rsp, r11
0x140003475  pop     rbp
0x140003476  retn
```
