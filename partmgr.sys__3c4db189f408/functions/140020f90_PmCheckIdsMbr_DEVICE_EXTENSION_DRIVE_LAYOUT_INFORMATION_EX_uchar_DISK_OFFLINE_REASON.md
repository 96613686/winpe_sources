# PmCheckIdsMbr(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *,uchar *,_DISK_OFFLINE_REASON *)

- ea: `0x140020f90`
- end: `0x1400210a0`
- name: `?PmCheckIdsMbr@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAEPEAW4_DISK_OFFLINE_REASON@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _DRIVE_LAYOUT_INFORMATION_EX *, unsigned __int8 *, enum _DISK_OFFLINE_REASON *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x14000d6f4`

## callees

- `0x140020f90`
- `0x1400210a8`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140020ff4`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140020ff4`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140021048`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140021048`

## pseudocode

```c
__int64 __fastcall PmCheckIdsMbr(
        struct _DEVICE_EXTENSION *a1,
        struct _DRIVE_LAYOUT_INFORMATION_EX *a2,
        unsigned __int8 *a3,
        enum _DISK_OFFLINE_REASON *a4)
{
  ULONG Signature; // eax
  int IsRedundantPath; // ebx
  char *DeviceExtension; // r14
  struct _DEVICE_EXTENSION **v10; // rax
  struct _DEVICE_EXTENSION *inserted; // rax
  struct _DEVICE_EXTENSION **v12; // rdx
  __int64 Buffer; // [rsp+20h] [rbp-30h] BYREF
  __int128 v15; // [rsp+28h] [rbp-28h]
  __int128 v16; // [rsp+38h] [rbp-18h]
  unsigned __int8 v17; // [rsp+88h] [rbp+38h] BYREF
  unsigned __int8 NewElement; // [rsp+90h] [rbp+40h] BYREF

  Signature = a2->Mbr.Signature;
  IsRedundantPath = 0;
  v17 = 0;
  NewElement = 0;
  Buffer = 0;
  *a3 = 0;
  *(_DWORD *)a4 = 0;
  v15 = 0;
  v16 = 0;
  if ( Signature )
  {
    LODWORD(v16) = Signature;
    DeviceExtension = (char *)PmControlObject->DeviceExtension;
    v10 = (struct _DEVICE_EXTENSION **)RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(DeviceExtension + 200), &Buffer);
    if ( v10 )
    {
      IsRedundantPath = PmIsRedundantPath(a1, v10[2], &v17);
      if ( IsRedundantPath >= 0 )
        *(_DWORD *)a4 = v17 != 0 ? 2 : 4;
    }
    else
    {
      LODWORD(v16) = a2->Mbr.Signature;
      inserted = (struct _DEVICE_EXTENSION *)RtlInsertElementGenericTableAvl(
                                               (PRTL_AVL_TABLE)(DeviceExtension + 200),
                                               &Buffer,
                                               0x28u,
                                               &NewElement);
      if ( inserted )
      {
        v12 = (struct _DEVICE_EXTENSION **)*((_QWORD *)a1 + 78);
        if ( *v12 != (struct _DEVICE_EXTENSION *)((char *)a1 + 616) )
          __fastfail(3u);
        *(_QWORD *)inserted = (char *)a1 + 616;
        *((_QWORD *)inserted + 1) = v12;
        *v12 = inserted;
        *((_QWORD *)a1 + 78) = inserted;
        *((_QWORD *)inserted + 2) = a1;
      }
      else
      {
        return (unsigned int)-1073741670;
      }
    }
  }
  else
  {
    *a3 = 1;
  }
  return (unsigned int)IsRedundantPath;
}

```

## disassembly

```asm
0x140020f90  mov     [rsp-28h+arg_0], rbx
0x140020f95  push    rbp
0x140020f96  push    rsi
0x140020f97  push    rdi
0x140020f98  push    r14
0x140020f9a  push    r15
0x140020f9c  mov     rbp, rsp
0x140020f9f  sub     rsp, 50h
0x140020fa3  mov     eax, [rdx+8]
0x140020fa6  xor     ebx, ebx
0x140020fa8  mov     [rbp+arg_8], 0
0x140020fac  xorps   xmm0, xmm0
0x140020faf  mov     [rbp+NewElement], 0
0x140020fb3  mov     rsi, r9
0x140020fb6  mov     [rbp+Buffer], rbx
0x140020fba  mov     r15, rdx
0x140020fbd  mov     [r8], bl
0x140020fc0  mov     rdi, rcx
0x140020fc3  mov     [r9], ebx
0x140020fc6  movups  [rbp+var_28], xmm0
0x140020fca  movups  [rbp+var_18], xmm0
0x140020fce  test    eax, eax
0x140020fd0  jnz     short loc_140020FDB
0x140020fd2  mov     byte ptr [r8], 1
0x140020fd6  jmp     loc_140021089
0x140020fdb  mov     dword ptr [rbp+var_18], eax
0x140020fde  lea     rdx, [rbp+Buffer]; Buffer
0x140020fe2  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x140020fe9  mov     r14, [rax+40h]
0x140020fed  lea     rcx, [r14+0C8h]; Table
0x140020ff4  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140020ffb  nop     dword ptr [rax+rax+00h]
0x140021000  test    rax, rax
0x140021003  jz      short loc_14002102C
0x140021005  mov     rdx, [rax+10h]; struct _DEVICE_EXTENSION *
0x140021009  lea     r8, [rbp+arg_8]; unsigned __int8 *
0x14002100d  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140021010  call    ?PmIsRedundantPath@@YAJPEAU_DEVICE_EXTENSION@@0PEAE@Z; PmIsRedundantPath(_DEVICE_EXTENSION *,_DEVICE_EXTENSION *,uchar *)
0x140021015  mov     ebx, eax
0x140021017  test    eax, eax
0x140021019  js      short loc_140021089
0x14002101b  mov     cl, [rbp+arg_8]
0x14002101e  neg     cl
0x140021020  sbb     edx, edx
0x140021022  and     edx, 0FFFFFFFEh
0x140021025  add     edx, 4
0x140021028  mov     [rsi], edx
0x14002102a  jmp     short loc_140021089
0x14002102c  mov     eax, [r15+8]
0x140021030  lea     r9, [rbp+NewElement]; NewElement
0x140021034  mov     r8d, 28h ; '('; BufferSize
0x14002103a  mov     dword ptr [rbp+var_18], eax
0x14002103d  lea     rdx, [rbp+Buffer]; Buffer
0x140021041  lea     rcx, [r14+0C8h]; Table
0x140021048  call    cs:__imp_RtlInsertElementGenericTableAvl
0x14002104f  nop     dword ptr [rax+rax+00h]
0x140021054  test    rax, rax
0x140021057  jnz     short loc_140021060
0x140021059  mov     ebx, 0C000009Ah
0x14002105e  jmp     short loc_140021089
0x140021060  lea     rcx, [rdi+268h]
0x140021067  mov     rdx, [rcx+8]
0x14002106b  cmp     [rdx], rcx
0x14002106e  jz      short loc_140021077
0x140021070  mov     ecx, 3
0x140021075  int     29h; Win8: RtlFailFast(ecx)
0x140021077  mov     [rax], rcx
0x14002107a  mov     [rax+8], rdx
0x14002107e  mov     [rdx], rax
0x140021081  mov     [rcx+8], rax
0x140021085  mov     [rax+10h], rdi
0x140021089  mov     eax, ebx
0x14002108b  mov     rbx, [rsp+50h+arg_0]
0x140021093  add     rsp, 50h
0x140021097  pop     r15
0x140021099  pop     r14
0x14002109b  pop     rdi
0x14002109c  pop     rsi
0x14002109d  pop     rbp
0x14002109e  retn
```
