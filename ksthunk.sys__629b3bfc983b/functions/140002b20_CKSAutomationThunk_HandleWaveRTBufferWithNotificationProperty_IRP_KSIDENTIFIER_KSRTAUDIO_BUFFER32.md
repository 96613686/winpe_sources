# CKSAutomationThunk::HandleWaveRTBufferWithNotificationProperty(_IRP *,KSIDENTIFIER *,KSRTAUDIO_BUFFER32 *)

- ea: `0x140002b20`
- end: `0x140002bf7`
- name: `?HandleWaveRTBufferWithNotificationProperty@CKSAutomationThunk@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAUKSRTAUDIO_BUFFER32@@@Z`
- size: `215`
- prototype: `NTSTATUS __fastcall(struct _IRP *, struct KSIDENTIFIER *, struct KSRTAUDIO_BUFFER32 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x140002b20`

## import_xrefs

- `ks!KsSynchronousIoControlDevice` at `0x140002bb8`
- `ks!KsSynchronousIoControlDevice` at `0x140002bb8`

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
0x140002b20  mov     r11, rsp
0x140002b23  mov     [r11+10h], rbx
0x140002b27  mov     [r11+18h], rdi
0x140002b2b  push    rbp
0x140002b2c  mov     rbp, rsp
0x140002b2f  sub     rsp, 80h
0x140002b36  mov     eax, [rdx+10h]
0x140002b39  lea     r9, [rbp+InBuffer]; InBuffer
0x140002b3d  movups  xmm1, xmmword ptr [rdx]
0x140002b40  mov     rcx, [rcx+0B8h]
0x140002b47  mov     rbx, r8
0x140002b4a  mov     [rbp+var_20], eax
0x140002b4d  xorps   xmm0, xmm0
0x140002b50  mov     eax, [rdx+14h]
0x140002b53  mov     rdi, rdx
0x140002b56  mov     [rbp+var_1C], eax
0x140002b59  mov     r8d, 2F0003h; IoControl
0x140002b5f  mov     eax, [rdx+18h]
0x140002b62  mov     [rbp+var_18], rax
0x140002b66  mov     eax, [rdx+1Ch]
0x140002b69  mov     [rbp+var_10], eax
0x140002b6c  mov     eax, [rdx+20h]
0x140002b6f  xor     edx, edx; RequestorMode
0x140002b71  mov     [rbp+var_C], eax
0x140002b74  lea     rax, [rbp+arg_0]
0x140002b78  mov     [r11-50h], rax
0x140002b7c  lea     rax, [rbp+var_40]
0x140002b80  mov     qword ptr [rbp+InBuffer], 0
0x140002b88  mov     qword ptr [rbp+InBuffer+8], 0
0x140002b90  mov     [rbp+arg_0], 0
0x140002b97  movups  [rbp+var_40], xmm0
0x140002b9b  mov     [rsp+80h+OutSize], 10h; OutSize
0x140002ba3  movdqu  [rbp+InBuffer], xmm1
0x140002ba8  mov     rcx, [rcx+30h]; FileObject
0x140002bac  mov     [r11-60h], rax
0x140002bb0  mov     [rsp+80h+InSize], 28h ; '('; InSize
0x140002bb8  call    cs:__imp_KsSynchronousIoControlDevice
0x140002bbf  nop     dword ptr [rax+rax+00h]
0x140002bc4  test    eax, eax
0x140002bc6  js      short loc_140002BE1
0x140002bc8  mov     ecx, [rdi+14h]
0x140002bcb  test    cl, 1
0x140002bce  jz      short loc_140002BE1
0x140002bd0  mov     ecx, dword ptr [rbp+var_40]
0x140002bd3  mov     [rbx], ecx
0x140002bd5  mov     ecx, dword ptr [rbp+var_40+8]
0x140002bd8  mov     [rbx+4], ecx
0x140002bdb  mov     ecx, dword ptr [rbp+var_40+0Ch]
0x140002bde  mov     [rbx+8], ecx
0x140002be1  lea     r11, [rsp+80h+var_s0]
0x140002be9  mov     rbx, [r11+18h]
0x140002bed  mov     rdi, [r11+20h]
0x140002bf1  mov     rsp, r11
0x140002bf4  pop     rbp
0x140002bf5  retn
```
