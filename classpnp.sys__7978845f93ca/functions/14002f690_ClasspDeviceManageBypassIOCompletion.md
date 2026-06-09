# ClasspDeviceManageBypassIOCompletion

- ea: `0x14002f690`
- end: `0x14002f7eb`
- name: `ClasspDeviceManageBypassIOCompletion`
- size: `347`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PVOID Tag)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400134a0`
- `0x140027a24`
- `0x14002f690`
- `0x140037880`
- `0x1400378f8`

## pseudocode

```c
__int64 __fastcall ClasspDeviceManageBypassIOCompletion(PDEVICE_OBJECT DeviceObject, int *Tag, __int64 a3)
{
  _WORD *DeviceExtension; // rdi
  __int64 v7; // rcx
  unsigned int *v8; // rdx
  __int64 v9; // r8
  __int16 v10; // ax
  __int64 v11; // r8

  DeviceExtension = DeviceObject->DeviceExtension;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 160, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids);
  }
  if ( Tag[12] >= 0 && *((_QWORD *)Tag + 7) >= 0x18u )
  {
    v7 = *((_QWORD *)Tag + 3);
    v8 = (unsigned int *)(v7 + 8);
    if ( *((_QWORD *)Tag + 7) == 24 )
    {
      v9 = *v8;
      if ( (_DWORD)v9 == 2 )
      {
        v10 = DeviceExtension[320] & 0xFEFF;
LABEL_17:
        DeviceExtension[320] = v10;
        goto LABEL_22;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqd(WPP_GLOBAL_Control->AttachedDevice, v8, v9, DeviceObject, Tag, a3, *v8);
      }
    }
    else
    {
      v11 = *(unsigned int *)(v7 + 24);
      if ( (int)v11 >= 0 && *v8 == 1 )
      {
        v10 = DeviceExtension[320] | 0x100;
        goto LABEL_17;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqdL(WPP_GLOBAL_Control->AttachedDevice, v8, v11, DeviceObject, Tag, a3, *v8, v11);
      }
    }
  }
LABEL_22:
  if ( *((_BYTE *)Tag + 65) )
    *(_BYTE *)(*((_QWORD *)Tag + 23) + 3LL) |= 1u;
  ClassReleaseRemoveLock(DeviceObject, Tag);
  return 0;
}

```

## disassembly

```asm
0x14002f690  push    rbx
0x14002f692  push    rbp
0x14002f693  push    rsi
0x14002f694  push    rdi
0x14002f695  push    r15
0x14002f697  sub     rsp, 40h
0x14002f69b  mov     rdi, [rcx+40h]
0x14002f69f  mov     rbp, r8
0x14002f6a2  mov     rbx, rdx
0x14002f6a5  mov     rsi, rcx
0x14002f6a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f6af  lea     r15, WPP_GLOBAL_Control
0x14002f6b6  cmp     rcx, r15
0x14002f6b9  jz      short loc_14002F6EA
0x14002f6bb  mov     eax, [rcx+2Ch]
0x14002f6be  test    al, 10h
0x14002f6c0  jz      short loc_14002F6EA
0x14002f6c2  cmp     byte ptr [rcx+29h], 4
0x14002f6c6  jb      short loc_14002F6EA
0x14002f6c8  mov     rcx, [rcx+18h]
0x14002f6cc  mov     edx, 0A0h
0x14002f6d1  mov     [rsp+68h+var_40], r8
0x14002f6d6  mov     r9, rsi
0x14002f6d9  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14002f6e0  mov     [rsp+68h+var_48], rbx
0x14002f6e5  call    WPP_SF_qqq
0x14002f6ea  cmp     dword ptr [rbx+30h], 0
0x14002f6ee  jl      loc_14002F7C1
0x14002f6f4  cmp     qword ptr [rbx+38h], 18h
0x14002f6f9  jb      loc_14002F7C1
0x14002f6ff  mov     rcx, [rbx+18h]
0x14002f703  lea     rdx, [rcx+8]
0x14002f707  jnz     short loc_14002F761
0x14002f709  mov     r8d, [rdx]
0x14002f70c  cmp     r8d, 2
0x14002f710  jnz     short loc_14002F723
0x14002f712  movzx   eax, word ptr [rdi+280h]
0x14002f719  mov     ecx, 0FFFFFEFFh
0x14002f71e  and     ax, cx
0x14002f721  jmp     short loc_14002F77E
0x14002f723  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f72a  cmp     rcx, r15
0x14002f72d  jz      loc_14002F7C1
0x14002f733  mov     eax, [rcx+2Ch]
0x14002f736  test    al, 10h
0x14002f738  jz      loc_14002F7C1
0x14002f73e  cmp     byte ptr [rcx+29h], 2
0x14002f742  jb      short loc_14002F7C1
0x14002f744  mov     rcx, [rcx+18h]
0x14002f748  mov     r9, rsi
0x14002f74b  mov     [rsp+68h+var_38], r8d
0x14002f750  mov     [rsp+68h+var_40], rbp
0x14002f755  mov     [rsp+68h+var_48], rbx
0x14002f75a  call    WPP_SF_qqqd
0x14002f75f  jmp     short loc_14002F7C1
0x14002f761  mov     r8d, [rcx+18h]
0x14002f765  test    r8d, r8d
0x14002f768  js      short loc_14002F787
0x14002f76a  cmp     dword ptr [rdx], 1
0x14002f76d  jnz     short loc_14002F787
0x14002f76f  movzx   eax, word ptr [rdi+280h]
0x14002f776  mov     ecx, 100h
0x14002f77b  or      ax, cx
0x14002f77e  mov     [rdi+280h], ax
0x14002f785  jmp     short loc_14002F7C1
0x14002f787  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f78e  cmp     rcx, r15
0x14002f791  jz      short loc_14002F7C1
0x14002f793  mov     eax, [rcx+2Ch]
0x14002f796  test    al, 10h
0x14002f798  jz      short loc_14002F7C1
0x14002f79a  cmp     byte ptr [rcx+29h], 2
0x14002f79e  jb      short loc_14002F7C1
0x14002f7a0  mov     eax, [rdx]
0x14002f7a2  mov     r9, rsi
0x14002f7a5  mov     rcx, [rcx+18h]
0x14002f7a9  mov     [rsp+68h+var_30], r8d
0x14002f7ae  mov     [rsp+68h+var_38], eax
0x14002f7b2  mov     [rsp+68h+var_40], rbp
0x14002f7b7  mov     [rsp+68h+var_48], rbx
0x14002f7bc  call    WPP_SF_qqqdL
0x14002f7c1  cmp     byte ptr [rbx+41h], 0
0x14002f7c5  jz      short loc_14002F7D2
0x14002f7c7  mov     rax, [rbx+0B8h]
0x14002f7ce  or      byte ptr [rax+3], 1
0x14002f7d2  mov     rdx, rbx; Tag
0x14002f7d5  mov     rcx, rsi; DeviceObject
0x14002f7d8  call    ClassReleaseRemoveLock
0x14002f7dd  xor     eax, eax
0x14002f7df  add     rsp, 40h
0x14002f7e3  pop     r15
0x14002f7e5  pop     rdi
0x14002f7e6  pop     rsi
0x14002f7e7  pop     rbp
0x14002f7e8  pop     rbx
0x14002f7e9  retn
```
