# ClassScanForSpecial

- ea: `0x14005f800`
- end: `0x14005f9a1`
- name: `ClassScanForSpecial`
- size: `417`
- prototype: `void __stdcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, CLASSPNP_SCAN_FOR_SPECIAL_INFO DeviceList[], PCLASS_SCAN_FOR_SPECIAL_HANDLER Function)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400579b4`

## callees

- `0x14001fc38`
- `0x14001feac`
- `0x140037cc4`
- `0x14003e470`
- `0x14005f800`
- `0x14005f9a8`

## pseudocode

```c
void __stdcall ClassScanForSpecial(
        PFUNCTIONAL_DEVICE_EXTENSION FdoExtension,
        CLASSPNP_SCAN_FOR_SPECIAL_INFO DeviceList[],
        PCLASS_SCAN_FOR_SPECIAL_HANDLER Function)
{
  CLASSPNP_SCAN_FOR_SPECIAL_INFO *__attribute__((__org_arrdim(0,0))) v4; // rbx
  _STORAGE_DEVICE_DESCRIPTOR *DeviceDescriptor; // rdx
  unsigned int VendorIdOffset; // r9d
  char *v8; // r15
  __int64 ProductIdOffset; // rcx
  char *v10; // r14
  __int64 ProductRevisionOffset; // rcx
  char *v12; // rbp
  int v13; // edx
  int v14; // r8d
  char v15; // [rsp+60h] [rbp+8h] BYREF

  if ( DeviceList )
  {
    v15 = 0;
    v4 = DeviceList;
    if ( Function )
    {
      DeviceDescriptor = FdoExtension->DeviceDescriptor;
      VendorIdOffset = DeviceDescriptor->VendorIdOffset;
      LODWORD(v8) = (_DWORD)DeviceDescriptor + VendorIdOffset;
      if ( VendorIdOffset - 1 > 0xFFFFFFFD )
        v8 = &v15;
      ProductIdOffset = DeviceDescriptor->ProductIdOffset;
      v10 = (char *)DeviceDescriptor + ProductIdOffset;
      if ( (unsigned int)(ProductIdOffset - 1) > 0xFFFFFFFD )
        v10 = &v15;
      ProductRevisionOffset = DeviceDescriptor->ProductRevisionOffset;
      v12 = (char *)DeviceDescriptor + ProductRevisionOffset;
      if ( (unsigned int)(ProductRevisionOffset - 1) > 0xFFFFFFFD )
        v12 = &v15;
      while ( v4->VendorId || v4->ProductId || v4->ProductRevision )
      {
        if ( (unsigned __int8)ClasspMyStringMatches(v4->VendorId)
          && (unsigned __int8)ClasspMyStringMatches(v4->ProductId)
          && (unsigned __int8)ClasspMyStringMatches(v4->ProductRevision) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_sss(WPP_GLOBAL_Control->AttachedDevice, v13, v14, (_DWORD)v8, (__int64)v10, (__int64)v12);
          }
          ((void (__fastcall *)(PFUNCTIONAL_DEVICE_EXTENSION, ULONG_PTR))Function)(FdoExtension, v4->Data);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids);
          }
          return;
        }
        ++v4;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
          FdoExtension->DeviceObject);
      }
    }
  }
}

```

## disassembly

```asm
0x14005f800  test    rdx, rdx
0x14005f803  jz      locret_14005F99F
0x14005f809  mov     [rsp+arg_8], rbx
0x14005f80e  mov     [rsp+arg_10], rbp
0x14005f813  push    rsi
0x14005f814  push    r12
0x14005f816  push    r13
0x14005f818  push    r14
0x14005f81a  push    r15
0x14005f81c  sub     rsp, 30h
0x14005f820  mov     [rsp+58h+arg_0], 0
0x14005f825  mov     r12, r8
0x14005f828  mov     rbx, rdx
0x14005f82b  mov     r13, rcx
0x14005f82e  test    r8, r8
0x14005f831  jz      loc_14005F988
0x14005f837  mov     rdx, [rcx+208h]
0x14005f83e  mov     r8d, 0FFFFFFFDh
0x14005f844  mov     r9d, [rdx+0Ch]
0x14005f848  lea     eax, [r9-1]
0x14005f84c  lea     r15, [rdx+r9]
0x14005f850  cmp     eax, r8d
0x14005f853  jbe     short loc_14005F85A
0x14005f855  lea     r15, [rsp+58h+arg_0]
0x14005f85a  mov     ecx, [rdx+10h]
0x14005f85d  lea     eax, [rcx-1]
0x14005f860  lea     r14, [rdx+rcx]
0x14005f864  cmp     eax, r8d
0x14005f867  jbe     short loc_14005F86E
0x14005f869  lea     r14, [rsp+58h+arg_0]
0x14005f86e  mov     ecx, [rdx+14h]
0x14005f871  lea     eax, [rcx-1]
0x14005f874  lea     rbp, [rdx+rcx]
0x14005f878  cmp     eax, r8d
0x14005f87b  jbe     short loc_14005F882
0x14005f87d  lea     rbp, [rsp+58h+arg_0]
0x14005f882  mov     rcx, [rbx]
0x14005f885  test    rcx, rcx
0x14005f888  jnz     short loc_14005F896
0x14005f88a  cmp     [rbx+8], rcx
0x14005f88e  jnz     short loc_14005F896
0x14005f890  cmp     [rbx+10h], rcx
0x14005f894  jz      short loc_14005F8C8
0x14005f896  mov     rdx, r15
0x14005f899  call    ClasspMyStringMatches
0x14005f89e  test    al, al
0x14005f8a0  jz      short loc_14005F8C2
0x14005f8a2  mov     rcx, [rbx+8]
0x14005f8a6  mov     rdx, r14
0x14005f8a9  call    ClasspMyStringMatches
0x14005f8ae  test    al, al
0x14005f8b0  jz      short loc_14005F8C2
0x14005f8b2  mov     rcx, [rbx+10h]
0x14005f8b6  mov     rdx, rbp
0x14005f8b9  call    ClasspMyStringMatches
0x14005f8be  test    al, al
0x14005f8c0  jnz     short loc_14005F911
0x14005f8c2  add     rbx, 20h ; ' '
0x14005f8c6  jmp     short loc_14005F882
0x14005f8c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f8cf  lea     rsi, WPP_GLOBAL_Control
0x14005f8d6  cmp     rcx, rsi
0x14005f8d9  jz      loc_14005F988
0x14005f8df  test    dword ptr [rcx+2Ch], 100h
0x14005f8e6  jz      loc_14005F988
0x14005f8ec  cmp     byte ptr [rcx+29h], 4
0x14005f8f0  jb      loc_14005F988
0x14005f8f6  mov     r9, [r13+8]
0x14005f8fa  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14005f901  mov     rcx, [rcx+18h]
0x14005f905  mov     edx, 0Ch
0x14005f90a  call    WPP_SF_q
0x14005f90f  jmp     short loc_14005F988
0x14005f911  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f918  lea     rsi, WPP_GLOBAL_Control
0x14005f91f  cmp     rcx, rsi
0x14005f922  jz      short loc_14005F949
0x14005f924  test    dword ptr [rcx+2Ch], 100h
0x14005f92b  jz      short loc_14005F949
0x14005f92d  cmp     byte ptr [rcx+29h], 4
0x14005f931  jb      short loc_14005F949
0x14005f933  mov     rcx, [rcx+18h]
0x14005f937  mov     r9, r15
0x14005f93a  mov     [rsp+58h+var_30], rbp
0x14005f93f  mov     [rsp+58h+var_38], r14
0x14005f944  call    WPP_SF_sss
0x14005f949  mov     rdx, [rbx+18h]
0x14005f94d  mov     rcx, r13
0x14005f950  mov     rax, r12
0x14005f953  call    _guard_dispatch_icall
0x14005f958  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f95f  cmp     rcx, rsi
0x14005f962  jz      short loc_14005F988
0x14005f964  test    dword ptr [rcx+2Ch], 100h
0x14005f96b  jz      short loc_14005F988
0x14005f96d  cmp     byte ptr [rcx+29h], 4
0x14005f971  jb      short loc_14005F988
0x14005f973  mov     rcx, [rcx+18h]
0x14005f977  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14005f97e  mov     edx, 0Bh
0x14005f983  call    WPP_SF_
0x14005f988  mov     rbx, [rsp+58h+arg_8]
0x14005f98d  mov     rbp, [rsp+58h+arg_10]
0x14005f992  add     rsp, 30h
0x14005f996  pop     r15
0x14005f998  pop     r14
0x14005f99a  pop     r13
0x14005f99c  pop     r12
0x14005f99e  pop     rsi
0x14005f99f  retn
```
