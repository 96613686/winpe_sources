# ReferenceRdpExtensionChannel(void * *,void *,ulong,char const *)

- ea: `0x14001b4d0`
- end: `0x14001b5ff`
- name: `?ReferenceRdpExtensionChannel@@YAJPEAPEAXPEAXKPEBD@Z`
- size: `303`
- prototype: `__int64 __fastcall(PHANDLE Handle, HANDLE, unsigned int, const char *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14001b144`
- `0x14001bf2c`

## callees

- `0x14000327c`
- `0x14001b4d0`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001b51a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001b51a`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b5e0`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b5e0`
- `ntoskrnl!IoFileObjectType` at `0x14001b4ef`
- `ntoskrnl!IoFileObjectType` at `0x14001b567`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14001b593`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14001b593`

## pseudocode

```c
__int64 __fastcall ReferenceRdpExtensionChannel(PHANDLE Handle, HANDLE a2, unsigned int a3, const char *a4)
{
  NTSTATUS v6; // ebx
  NTSTATUS v7; // eax
  PVOID Object; // [rsp+68h] [rbp+20h] BYREF

  Object = 0;
  v6 = ObReferenceObjectByHandle(a2, 3u, (POBJECT_TYPE)IoFileObjectType, 1, &Object, 0);
  if ( v6 >= 0 )
  {
    v7 = ObOpenObjectByPointer(Object, 0x240u, 0, 0xC0100000, (POBJECT_TYPE)IoFileObjectType, 0, Handle);
    v6 = v7;
    if ( v7 < 0 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        WPP_8ecd16b07aab3e5d2130d6f744ebb8b4_Traceguids,
        (unsigned int)v7);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_8ecd16b07aab3e5d2130d6f744ebb8b4_Traceguids, a3);
  }
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001b4d0  mov     r11, rsp
0x14001b4d3  mov     [r11+8], rbx
0x14001b4d7  mov     [r11+10h], rsi
0x14001b4db  mov     [r11+20h], r9
0x14001b4df  push    rdi
0x14001b4e0  sub     rsp, 40h
0x14001b4e4  mov     esi, r8d
0x14001b4e7  mov     qword ptr [r11-20h], 0
0x14001b4ef  mov     r8, cs:__imp_IoFileObjectType
0x14001b4f6  mov     rdi, rcx
0x14001b4f9  lea     rcx, [r11+20h]
0x14001b4fd  mov     qword ptr [r11+20h], 0
0x14001b505  mov     rax, rdx
0x14001b508  mov     [r11-28h], rcx
0x14001b50c  mov     r9b, 1; AccessMode
0x14001b50f  mov     edx, 3; DesiredAccess
0x14001b514  mov     r8, [r8]; ObjectType
0x14001b517  mov     rcx, rax; Handle
0x14001b51a  call    cs:__imp_ObReferenceObjectByHandle
0x14001b521  nop     dword ptr [rax+rax+00h]
0x14001b526  mov     ebx, eax
0x14001b528  test    eax, eax
0x14001b52a  jns     short loc_14001B567
0x14001b52c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b533  lea     rdx, WPP_GLOBAL_Control
0x14001b53a  cmp     rcx, rdx
0x14001b53d  jz      loc_14001B5D6
0x14001b543  cmp     byte ptr [rcx+29h], 2
0x14001b547  jb      loc_14001B5D6
0x14001b54d  mov     rcx, [rcx+18h]
0x14001b551  lea     r8, WPP_8ecd16b07aab3e5d2130d6f744ebb8b4_Traceguids
0x14001b558  mov     edx, 13h
0x14001b55d  mov     r9d, esi
0x14001b560  call    WPP_SF_d
0x14001b565  jmp     short loc_14001B5D6
0x14001b567  mov     rax, cs:__imp_IoFileObjectType
0x14001b56e  mov     r9d, 0C0100000h; DesiredAccess
0x14001b574  mov     [rsp+48h+Handle], rdi; Handle
0x14001b579  xor     r8d, r8d; PassedAccessState
0x14001b57c  mov     [rsp+48h+AccessMode], 0; AccessMode
0x14001b581  mov     edx, 240h; HandleAttributes
0x14001b586  mov     rcx, [rax]
0x14001b589  mov     [rsp+48h+ObjectType], rcx; ObjectType
0x14001b58e  mov     rcx, [rsp+48h+Object]; Object
0x14001b593  call    cs:__imp_ObOpenObjectByPointer
0x14001b59a  nop     dword ptr [rax+rax+00h]
0x14001b59f  mov     ebx, eax
0x14001b5a1  test    eax, eax
0x14001b5a3  jns     short loc_14001B5D6
0x14001b5a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b5ac  lea     rdx, WPP_GLOBAL_Control
0x14001b5b3  cmp     rcx, rdx
0x14001b5b6  jz      short loc_14001B5D6
0x14001b5b8  cmp     byte ptr [rcx+29h], 2
0x14001b5bc  jb      short loc_14001B5D6
0x14001b5be  mov     rcx, [rcx+18h]
0x14001b5c2  lea     r8, WPP_8ecd16b07aab3e5d2130d6f744ebb8b4_Traceguids
0x14001b5c9  mov     edx, 14h
0x14001b5ce  mov     r9d, eax
0x14001b5d1  call    WPP_SF_d
0x14001b5d6  mov     rcx, [rsp+48h+Object]; Object
0x14001b5db  test    rcx, rcx
0x14001b5de  jz      short loc_14001B5EC
0x14001b5e0  call    cs:__imp_ObfDereferenceObject
0x14001b5e7  nop     dword ptr [rax+rax+00h]
0x14001b5ec  mov     rsi, [rsp+48h+arg_8]
0x14001b5f1  mov     eax, ebx
0x14001b5f3  mov     rbx, [rsp+48h+arg_0]
0x14001b5f8  add     rsp, 40h
0x14001b5fc  pop     rdi
0x14001b5fd  retn
```
