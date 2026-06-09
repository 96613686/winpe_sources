# CKSAutomationThunk::HandleNotificationEventRegistrationProperty(_IRP *,KSIDENTIFIER *)

- ea: `0x140002920`
- end: `0x14000298d`
- name: `?HandleNotificationEventRegistrationProperty@CKSAutomationThunk@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@@Z`
- size: `109`
- prototype: `NTSTATUS __fastcall(struct _IRP *, struct KSIDENTIFIER *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `ks!KsSynchronousIoControlDevice` at `0x14000297b`
- `ks!KsSynchronousIoControlDevice` at `0x14000297b`

## pseudocode

```c
NTSTATUS __fastcall CKSAutomationThunk::HandleNotificationEventRegistrationProperty(
        struct _IRP *a1,
        struct KSIDENTIFIER *a2)
{
  GUID Set; // xmm0
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  __int64 Data1; // rax
  GUID v6; // [rsp+40h] [rbp-28h] BYREF
  __int64 v7; // [rsp+50h] [rbp-18h]
  __int64 v8; // [rsp+58h] [rbp-10h]
  ULONG v9; // [rsp+70h] [rbp+8h] BYREF

  Set = a2->Set;
  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  v7 = *(&a2->Alignment + 2);
  Data1 = a2[1].Set.Data1;
  v6 = Set;
  v8 = Data1;
  v9 = 0;
  return KsSynchronousIoControlDevice(CurrentStackLocation->FileObject, 0, 0x2F0003u, &v6, 0x20u, 0, 0, &v9);
}

```

## disassembly

```asm
0x140002920  mov     r11, rsp
0x140002923  sub     rsp, 68h
0x140002927  mov     eax, [rdx+10h]
0x14000292a  lea     r9, [r11-28h]; InBuffer
0x14000292e  movups  xmm0, xmmword ptr [rdx]
0x140002931  mov     rcx, [rcx+0B8h]
0x140002938  xor     r8d, r8d
0x14000293b  mov     [rsp+68h+var_18], eax
0x14000293f  mov     eax, [rdx+14h]
0x140002942  mov     [rsp+68h+var_14], eax
0x140002946  mov     eax, [rdx+18h]
0x140002949  xor     edx, edx; RequestorMode
0x14000294b  movdqu  [rsp+68h+var_28], xmm0
0x140002951  mov     [r11-10h], rax
0x140002955  lea     rax, [r11+8]
0x140002959  mov     [r11-30h], rax
0x14000295d  mov     [r11-38h], r8d
0x140002961  mov     [r11-40h], r8
0x140002965  mov     [r11+8], r8d
0x140002969  mov     r8d, 2F0003h; IoControl
0x14000296f  mov     rcx, [rcx+30h]; FileObject
0x140002973  mov     [rsp+68h+InSize], 20h ; ' '; InSize
0x14000297b  call    cs:__imp_KsSynchronousIoControlDevice
0x140002982  nop     dword ptr [rax+rax+00h]
0x140002987  add     rsp, 68h
0x14000298b  retn
```
