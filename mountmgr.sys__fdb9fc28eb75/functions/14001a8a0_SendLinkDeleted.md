# SendLinkDeleted

- ea: `0x14001a8a0`
- end: `0x14001aaaa`
- name: `SendLinkDeleted`
- size: `522`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140019e30`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140002f80`
- `0x140017bf0`
- `0x14001a8a0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14001aa7d`
- `ntoskrnl!ObfDereferenceObject` at `0x14001aa8e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001aa7d`
- `ntoskrnl!ObfDereferenceObject` at `0x14001aa8e`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14001a8d7`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14001a8d7`
- `ntoskrnl!ExAllocatePool2` at `0x14001a94b`
- `ntoskrnl!ExAllocatePool2` at `0x14001a94b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001aa6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001aa6a`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14001a92d`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14001a92d`

## pseudocode

```c
NTSTATUS __fastcall SendLinkDeleted(void *a1, void *a2, struct _UNICODE_STRING *a3, const void **a4)
{
  int v4; // esi
  NTSTATUS result; // eax
  __int64 v7; // r8
  int v8; // ebx
  ULONG v9; // esi
  _WORD *Pool2; // rbx
  NTSTATUS v11; // eax
  __int64 v12; // r8
  NTSTATUS v13; // eax
  __int64 v14; // r8
  PVOID v15; // [rsp+60h] [rbp+8h] BYREF
  PVOID Object; // [rsp+68h] [rbp+10h] BYREF

  Object = a2;
  v15 = a1;
  v4 = *(unsigned __int16 *)a4;
  v15 = 0;
  Object = 0;
  result = IoGetDeviceObjectPointer(a3, 0x80u, (PFILE_OBJECT *)&v15, (PDEVICE_OBJECT *)&Object);
  v8 = result;
  if ( result >= 0 )
  {
    v9 = v4 + 2;
    Object = IoGetAttachedDeviceReference(*((PDEVICE_OBJECT *)v15 + 1));
    Pool2 = (_WORD *)ExAllocatePool2(258, v9, 1098149453);
    if ( Pool2 )
    {
      *Pool2 = *(_WORD *)a4;
      memmove(Pool2 + 1, a4[1], *(unsigned __int16 *)a4);
      v11 = MountMgrSendDeviceControl((PDEVICE_OBJECT)Object, 0x4DC014u, Pool2, v9, 0, 0, (struct _FILE_OBJECT *)v15);
      if ( v11 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 219, v12, (unsigned int)v11);
      }
      v13 = MountMgrSendDeviceControl((PDEVICE_OBJECT)Object, 0x4D0014u, Pool2, v9, 0, 0, (struct _FILE_OBJECT *)v15);
      if ( v13 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 220, v14, (unsigned int)v13);
      }
      ExFreePoolWithTag(Pool2, 0);
      v8 = 0;
    }
    else
    {
      v8 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 218);
    }
    ObfDereferenceObject(Object);
    ObfDereferenceObject(v15);
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return result;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 217, v7, (unsigned int)result);
  }
  return v8;
}

```

## disassembly

```asm
0x14001a8a0  mov     rax, rsp
0x14001a8a3  mov     [rax+18h], rbx
0x14001a8a7  mov     [rax+10h], rdx
0x14001a8ab  mov     [rax+8], rcx
0x14001a8af  push    rbp
0x14001a8b0  push    rsi
0x14001a8b1  push    rdi
0x14001a8b2  sub     rsp, 40h
0x14001a8b6  movzx   esi, word ptr [r9]
0x14001a8ba  mov     rdi, r9
0x14001a8bd  mov     rcx, r8; ObjectName
0x14001a8c0  lea     r9, [rax+10h]; DeviceObject
0x14001a8c4  xor     ebp, ebp
0x14001a8c6  lea     r8, [rax+8]; FileObject
0x14001a8ca  mov     edx, 80h; DesiredAccess
0x14001a8cf  mov     [rax+8], rbp
0x14001a8d3  mov     [rax+10h], rbp
0x14001a8d7  call    cs:__imp_IoGetDeviceObjectPointer
0x14001a8de  nop     dword ptr [rax+rax+00h]
0x14001a8e3  mov     ebx, eax
0x14001a8e5  test    eax, eax
0x14001a8e7  jns     short loc_14001A921
0x14001a8e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a8f0  lea     rdi, WPP_GLOBAL_Control
0x14001a8f7  cmp     rcx, rdi
0x14001a8fa  jz      loc_14001AA9C
0x14001a900  mov     eax, [rcx+2Ch]
0x14001a903  test    al, 1
0x14001a905  jz      loc_14001AA9A
0x14001a90b  mov     rcx, [rcx+18h]
0x14001a90f  mov     edx, 0D9h
0x14001a914  mov     r9d, ebx
0x14001a917  call    WPP_SF_L
0x14001a91c  jmp     loc_14001AA9A
0x14001a921  mov     rcx, [rsp+58h+arg_0]
0x14001a926  add     esi, 2
0x14001a929  mov     rcx, [rcx+8]; DeviceObject
0x14001a92d  call    cs:__imp_IoGetAttachedDeviceReference
0x14001a934  nop     dword ptr [rax+rax+00h]
0x14001a939  mov     edx, esi
0x14001a93b  mov     ecx, 102h
0x14001a940  mov     r8d, 41746E4Dh
0x14001a946  mov     [rsp+58h+Object], rax
0x14001a94b  call    cs:__imp_ExAllocatePool2
0x14001a952  nop     dword ptr [rax+rax+00h]
0x14001a957  mov     rbx, rax
0x14001a95a  test    rax, rax
0x14001a95d  jnz     short loc_14001A999
0x14001a95f  mov     ebx, 0C000009Ah
0x14001a964  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a96b  lea     rdi, WPP_GLOBAL_Control
0x14001a972  cmp     rcx, rdi
0x14001a975  jz      loc_14001AA78
0x14001a97b  mov     eax, [rcx+2Ch]
0x14001a97e  test    al, 4
0x14001a980  jz      loc_14001AA78
0x14001a986  mov     rcx, [rcx+18h]
0x14001a98a  mov     edx, 0DAh
0x14001a98f  call    WPP_SF_
0x14001a994  jmp     loc_14001AA78
0x14001a999  movzx   eax, word ptr [rdi]
0x14001a99c  lea     rcx, [rbx+2]; void *
0x14001a9a0  mov     [rbx], ax
0x14001a9a3  movzx   r8d, word ptr [rdi]; Size
0x14001a9a7  mov     rdx, [rdi+8]; Src
0x14001a9ab  call    memmove
0x14001a9b0  mov     rax, [rsp+58h+arg_0]
0x14001a9b5  mov     r9d, esi; InputBufferLength
0x14001a9b8  mov     rcx, [rsp+58h+Object]; DeviceObject
0x14001a9bd  mov     r8, rbx; InputBuffer
0x14001a9c0  mov     [rsp+58h+var_28], rax; __int64
0x14001a9c5  mov     edx, 4DC014h; IoControlCode
0x14001a9ca  mov     [rsp+58h+var_30], ebp; ULONG
0x14001a9ce  mov     [rsp+58h+var_38], rbp; PVOID
0x14001a9d3  call    MountMgrSendDeviceControl
0x14001a9d8  lea     rdi, WPP_GLOBAL_Control
0x14001a9df  test    eax, eax
0x14001a9e1  jns     short loc_14001AA0E
0x14001a9e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a9ea  cmp     rcx, rdi
0x14001a9ed  jz      short loc_14001AA0E
0x14001a9ef  mov     edx, [rcx+2Ch]
0x14001a9f2  test    dl, 1
0x14001a9f5  jz      short loc_14001AA0E
0x14001a9f7  cmp     byte ptr [rcx+29h], 1
0x14001a9fb  jb      short loc_14001AA0E
0x14001a9fd  mov     rcx, [rcx+18h]
0x14001aa01  mov     edx, 0DBh
0x14001aa06  mov     r9d, eax
0x14001aa09  call    WPP_SF_L
0x14001aa0e  mov     rax, [rsp+58h+arg_0]
0x14001aa13  mov     r9d, esi; InputBufferLength
0x14001aa16  mov     rcx, [rsp+58h+Object]; DeviceObject
0x14001aa1b  mov     r8, rbx; InputBuffer
0x14001aa1e  mov     [rsp+58h+var_28], rax; __int64
0x14001aa23  mov     edx, 4D0014h; IoControlCode
0x14001aa28  mov     [rsp+58h+var_30], ebp; ULONG
0x14001aa2c  mov     [rsp+58h+var_38], rbp; PVOID
0x14001aa31  call    MountMgrSendDeviceControl
0x14001aa36  test    eax, eax
0x14001aa38  jns     short loc_14001AA65
0x14001aa3a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001aa41  cmp     rcx, rdi
0x14001aa44  jz      short loc_14001AA65
0x14001aa46  mov     edx, [rcx+2Ch]
0x14001aa49  test    dl, 1
0x14001aa4c  jz      short loc_14001AA65
0x14001aa4e  cmp     byte ptr [rcx+29h], 1
0x14001aa52  jb      short loc_14001AA65
0x14001aa54  mov     rcx, [rcx+18h]
0x14001aa58  mov     edx, 0DCh
0x14001aa5d  mov     r9d, eax
0x14001aa60  call    WPP_SF_L
0x14001aa65  xor     edx, edx; Tag
0x14001aa67  mov     rcx, rbx; P
0x14001aa6a  call    cs:__imp_ExFreePoolWithTag
0x14001aa71  nop     dword ptr [rax+rax+00h]
0x14001aa76  mov     ebx, ebp
0x14001aa78  mov     rcx, [rsp+58h+Object]; Object
0x14001aa7d  call    cs:__imp_ObfDereferenceObject
0x14001aa84  nop     dword ptr [rax+rax+00h]
0x14001aa89  mov     rcx, [rsp+58h+arg_0]; Object
0x14001aa8e  call    cs:__imp_ObfDereferenceObject
0x14001aa95  nop     dword ptr [rax+rax+00h]
0x14001aa9a  mov     eax, ebx
0x14001aa9c  mov     rbx, [rsp+58h+arg_10]
0x14001aaa1  add     rsp, 40h
0x14001aaa5  pop     rdi
0x14001aaa6  pop     rsi
0x14001aaa7  pop     rbp
0x14001aaa8  retn
```
