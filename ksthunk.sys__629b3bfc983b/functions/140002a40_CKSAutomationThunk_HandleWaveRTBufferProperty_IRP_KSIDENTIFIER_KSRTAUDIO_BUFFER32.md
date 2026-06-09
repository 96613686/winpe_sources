# CKSAutomationThunk::HandleWaveRTBufferProperty(_IRP *,KSIDENTIFIER *,KSRTAUDIO_BUFFER32 *)

- ea: `0x140002a40`
- end: `0x140002b18`
- name: `?HandleWaveRTBufferProperty@CKSAutomationThunk@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAUKSRTAUDIO_BUFFER32@@@Z`
- size: `216`
- prototype: `NTSTATUS __fastcall(struct _IRP *, struct KSIDENTIFIER *, struct KSRTAUDIO_BUFFER32 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140002a40`

## import_xrefs

- `ks!KsSynchronousIoControlDevice` at `0x140002ad9`
- `ks!KsSynchronousIoControlDevice` at `0x140002ad9`

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
0x140002a40  mov     r11, rsp
0x140002a43  mov     [r11+10h], rbx
0x140002a47  mov     [r11+18h], rdi
0x140002a4b  push    rbp
0x140002a4c  mov     rbp, rsp
0x140002a4f  sub     rsp, 80h
0x140002a56  mov     eax, [rdx+10h]
0x140002a59  lea     r9, [rbp+InBuffer]; InBuffer
0x140002a5d  movups  xmm1, xmmword ptr [rdx]
0x140002a60  mov     rcx, [rcx+0B8h]
0x140002a67  mov     rbx, r8
0x140002a6a  mov     [rbp+var_20], eax
0x140002a6d  xorps   xmm0, xmm0
0x140002a70  mov     eax, [rdx+14h]
0x140002a73  mov     rdi, rdx
0x140002a76  mov     [rbp+var_1C], eax
0x140002a79  mov     r8d, 2F0003h; IoControl
0x140002a7f  mov     eax, [rdx+18h]
0x140002a82  mov     [rbp+var_18], rax
0x140002a86  mov     eax, [rdx+1Ch]
0x140002a89  xor     edx, edx; RequestorMode
0x140002a8b  mov     [rbp+var_10], eax
0x140002a8e  lea     rax, [rbp+arg_0]
0x140002a92  mov     [r11-50h], rax
0x140002a96  lea     rax, [rbp+var_40]
0x140002a9a  mov     qword ptr [rbp+InBuffer], 0
0x140002aa2  mov     qword ptr [rbp+InBuffer+8], 0
0x140002aaa  mov     [rbp+arg_0], 0
0x140002ab1  mov     [rbp+var_C], 0
0x140002ab8  movups  [rbp+var_40], xmm0
0x140002abc  mov     [rsp+80h+OutSize], 10h; OutSize
0x140002ac4  movdqu  [rbp+InBuffer], xmm1
0x140002ac9  mov     rcx, [rcx+30h]; FileObject
0x140002acd  mov     [r11-60h], rax
0x140002ad1  mov     [rsp+80h+InSize], 28h ; '('; InSize
0x140002ad9  call    cs:__imp_KsSynchronousIoControlDevice
0x140002ae0  nop     dword ptr [rax+rax+00h]
0x140002ae5  test    eax, eax
0x140002ae7  js      short loc_140002B02
0x140002ae9  mov     ecx, [rdi+14h]
0x140002aec  test    cl, 1
0x140002aef  jz      short loc_140002B02
0x140002af1  mov     ecx, dword ptr [rbp+var_40]
0x140002af4  mov     [rbx], ecx
0x140002af6  mov     ecx, dword ptr [rbp+var_40+8]
0x140002af9  mov     [rbx+4], ecx
0x140002afc  mov     ecx, dword ptr [rbp+var_40+0Ch]
0x140002aff  mov     [rbx+8], ecx
0x140002b02  lea     r11, [rsp+80h+var_s0]
0x140002b0a  mov     rbx, [r11+18h]
0x140002b0e  mov     rdi, [r11+20h]
0x140002b12  mov     rsp, r11
0x140002b15  pop     rbp
0x140002b16  retn
```
