# RxTryUpdateFileSizeAfterQuery

- ea: `0x14006ae70`
- end: `0x14006aee0`
- name: `RxTryUpdateFileSizeAfterQuery`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x140056510`

## callees

- `0x140008030`
- `0x140008190`
- `0x140016e20`
- `0x1400197b0`
- `0x1400198a0`
- `0x14006ae70`

## import_xrefs

- `ntoskrnl!CcSetFileSizes` at `0x14007ecb6`
- `ntoskrnl!CcSetFileSizes` at `0x14007ecb6`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14006aeb8`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14006aeb8`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14007ec60`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14007ec60`

## pseudocode

```c
char __fastcall RxTryUpdateFileSizeAfterQuery(__int64 a1, struct _FILE_OBJECT *a2, __int64 a3)
{
  int Timer_high; // eax
  __int64 v6; // rsi
  __int64 v7; // r8
  _QWORD *v8; // r14
  _QWORD *v9; // r12
  _QWORD *v10; // r15
  SECTION_OBJECT_POINTERS *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+78h] [rbp-50h] BYREF

  IoStatus = 0;
  Timer_high = *(_DWORD *)(a1 + 164);
  if ( (Timer_high & 8) == 0 || (*(_DWORD *)(a1 + 160) & 0x100000) == 0 )
  {
    v6 = *(_QWORD *)(a3 + 8);
    LOBYTE(Timer_high) = ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(a1 + 8));
    if ( (_BYTE)Timer_high )
    {
      v8 = (_QWORD *)(a1 + 32);
      if ( *(_QWORD *)(a1 + 32) != v6 )
      {
        LOBYTE(v7) = 1;
        RxAcquirePagingIoResource(0, a1, v7);
        v9 = (_QWORD *)(a1 + 40);
        v10 = (_QWORD *)(a1 + 24);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qiiii(
            WPP_GLOBAL_Control->AttachedDevice,
            76,
            *(_QWORD *)(a1 + 40),
            a1,
            *v8,
            v6,
            *(_QWORD *)(a1 + 24),
            *(_QWORD *)(a1 + 40),
            *(_QWORD *)(a1 + 24));
        }
        v11 = (SECTION_OBJECT_POINTERS *)(*(_QWORD *)(a1 + 304) + 8LL);
        if ( v11->DataSectionObject )
        {
          CcCoherencyFlushAndPurgeCache(v11, 0, 0, &IoStatus, 3u);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              77,
              &WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids,
              (unsigned int)IoStatus.Status);
          }
        }
        *v8 = v6;
        *v9 = v6;
        *v10 = v6;
        CcSetFileSizes(a2, (PCC_FILE_SIZES)(a1 + 24));
        LOBYTE(Timer_high) = RxReleasePagingIoResource(0, a1);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
          if ( (Timer_high & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            LOBYTE(Timer_high) = WPP_SF_dqiii(WPP_GLOBAL_Control->AttachedDevice, v12, v13, 0, a1, *v8, *v10, *v9);
        }
      }
    }
  }
  return Timer_high;
}

```

## disassembly

```asm
0x14006ae70  mov     [rsp+arg_8], rdx
0x14006ae75  mov     [rsp+arg_0], rcx
0x14006ae7a  push    rbx
0x14006ae7b  push    rsi
0x14006ae7c  push    rdi
0x14006ae7d  push    r12
0x14006ae7f  push    r13
0x14006ae81  push    r14
0x14006ae83  push    r15
0x14006ae85  sub     rsp, 90h
0x14006ae8c  mov     rdi, rdx
0x14006ae8f  mov     rbx, rcx
0x14006ae92  xorps   xmm0, xmm0
0x14006ae95  movups  xmmword ptr [rsp+0C8h+IoStatus], xmm0
0x14006ae9a  mov     eax, [rcx+0A4h]
0x14006aea0  test    al, 8
0x14006aea2  jz      short loc_14006AEB0
0x14006aea4  test    dword ptr [rcx+0A0h], 100000h
0x14006aeae  jnz     short loc_14006AECC
0x14006aeb0  mov     rsi, [r8+8]
0x14006aeb4  mov     rcx, [rcx+8]; Resource
0x14006aeb8  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14006aebf  nop     dword ptr [rax+rax+00h]
0x14006aec4  test    al, al
0x14006aec6  jnz     loc_14007EB96
0x14006aecc  add     rsp, 90h
0x14006aed3  pop     r15
0x14006aed5  pop     r14
0x14006aed7  pop     r13
0x14006aed9  pop     r12
0x14006aedb  pop     rdi
0x14006aedc  pop     rsi
0x14006aedd  pop     rbx
0x14006aede  retn
0x14007eb96  lea     r14, [rbx+20h]
0x14007eb9a  mov     [rsp+0C8h+var_80], r14
0x14007eb9f  cmp     [r14], rsi
0x14007eba2  jz      loc_14006AECC
0x14007eba8  mov     [rsp+0C8h+arg_10], 0
0x14007ebb3  mov     r8b, 1
0x14007ebb6  mov     rdx, rbx
0x14007ebb9  xor     ecx, ecx
0x14007ebbb  call    RxAcquirePagingIoResource
0x14007ebc0  lea     r12, [rbx+28h]
0x14007ebc4  mov     [rsp+0C8h+var_70], r12
0x14007ebc9  mov     r8, [r12]
0x14007ebcd  mov     [rsp+0C8h+arg_18], r8
0x14007ebd5  mov     [rsp+0C8h+var_68], r8
0x14007ebda  mov     r13, [r14]
0x14007ebdd  mov     [rsp+0C8h+var_78], r13
0x14007ebe2  lea     r15, [rbx+18h]
0x14007ebe6  mov     [rsp+0C8h+var_60], r15
0x14007ebeb  mov     r9, [r15]
0x14007ebee  mov     [rsp+0C8h+var_88], r9
0x14007ebf3  mov     [rsp+0C8h+var_58], r9
0x14007ebf8  lea     rax, WPP_GLOBAL_Control
0x14007ebff  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ec06  cmp     rcx, rax
0x14007ec09  jz      short loc_14007EC3D
0x14007ec0b  mov     eax, [rcx+2Ch]
0x14007ec0e  test    al, 20h
0x14007ec10  jz      short loc_14007EC3D
0x14007ec12  cmp     byte ptr [rcx+29h], 2
0x14007ec16  jb      short loc_14007EC3D
0x14007ec18  mov     edx, 4Ch ; 'L'
0x14007ec1d  mov     [rsp+0C8h+var_90], r8
0x14007ec22  mov     [rsp+0C8h+var_98], r9
0x14007ec27  mov     [rsp+0C8h+var_A0], rsi
0x14007ec2c  mov     qword ptr [rsp+0C8h+Flags], r13
0x14007ec31  mov     r9, rbx
0x14007ec34  mov     rcx, [rcx+18h]
0x14007ec38  call    WPP_SF_qiiii
0x14007ec3d  mov     rcx, [rbx+130h]
0x14007ec44  add     rcx, 8; SectionObjectPointer
0x14007ec48  cmp     qword ptr [rcx], 0
0x14007ec4c  jz      short loc_14007ECA6
0x14007ec4e  mov     [rsp+0C8h+Flags], 3; Flags
0x14007ec56  lea     r9, [rsp+0C8h+IoStatus]; IoStatus
0x14007ec5b  xor     r8d, r8d; Length
0x14007ec5e  xor     edx, edx; FileOffset
0x14007ec60  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x14007ec67  nop     dword ptr [rax+rax+00h]
0x14007ec6c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ec73  lea     rax, WPP_GLOBAL_Control
0x14007ec7a  cmp     rcx, rax
0x14007ec7d  jz      short loc_14007ECA6
0x14007ec7f  mov     eax, [rcx+2Ch]
0x14007ec82  test    al, 20h
0x14007ec84  jz      short loc_14007ECA6
0x14007ec86  cmp     byte ptr [rcx+29h], 2
0x14007ec8a  jb      short loc_14007ECA6
0x14007ec8c  mov     edx, 4Dh ; 'M'
0x14007ec91  mov     r9d, dword ptr [rsp+0C8h+IoStatus]
0x14007ec96  lea     r8, WPP_b56a177ad84538bb1b408203bbe5bef7_Traceguids
0x14007ec9d  mov     rcx, [rcx+18h]
0x14007eca1  call    WPP_SF_d
0x14007eca6  mov     [r14], rsi
0x14007eca9  mov     [r12], rsi
0x14007ecad  mov     [r15], rsi
0x14007ecb0  mov     rdx, r15; FileSizes
0x14007ecb3  mov     rcx, rdi; FileObject
0x14007ecb6  call    cs:__imp_CcSetFileSizes
0x14007ecbd  nop     dword ptr [rax+rax+00h]
0x14007ecc2  mov     rax, [rsp+0C8h+arg_18]
0x14007ecca  mov     rcx, [rsp+0C8h+var_88]
0x14007eccf  lea     rsi, WPP_GLOBAL_Control
0x14007ecd6  jmp     short loc_14007ED14
0x14007ecd8  mov     [rsp+0C8h+arg_10], eax
0x14007ecdf  lea     rsi, WPP_GLOBAL_Control
0x14007ece6  mov     rdi, [rsp+0C8h+arg_8]
0x14007ecee  mov     rbx, [rsp+0C8h+arg_0]
0x14007ecf6  mov     r14, [rsp+0C8h+var_80]
0x14007ecfb  mov     r13, [rsp+0C8h+var_78]
0x14007ed00  mov     r12, [rsp+0C8h+var_70]
0x14007ed05  mov     rax, [rsp+0C8h+var_68]
0x14007ed0a  mov     r15, [rsp+0C8h+var_60]
0x14007ed0f  mov     rcx, [rsp+0C8h+var_58]
0x14007ed14  cmp     [rsp+0C8h+arg_10], 0
0x14007ed1c  jge     short loc_14007ED39
0x14007ed1e  mov     [r14], r13
0x14007ed21  mov     [r12], rax
0x14007ed25  mov     [r15], rcx
0x14007ed28  mov     rax, [rdi+28h]
0x14007ed2c  mov     rcx, [rax+8]
0x14007ed30  test    rcx, rcx
0x14007ed33  jz      short loc_14007ED39
0x14007ed35  mov     [rcx+8], r13
0x14007ed39  mov     rdx, rbx
0x14007ed3c  xor     ecx, ecx
0x14007ed3e  call    RxReleasePagingIoResource
0x14007ed43  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ed4a  cmp     rcx, rsi
0x14007ed4d  jz      loc_14006AECC
0x14007ed53  mov     eax, [rcx+2Ch]
0x14007ed56  test    al, 20h
0x14007ed58  jz      loc_14006AECC
0x14007ed5e  cmp     byte ptr [rcx+29h], 2
0x14007ed62  jb      loc_14006AECC
0x14007ed68  mov     rax, [r12]
0x14007ed6c  mov     [rsp+0C8h+var_90], rax
0x14007ed71  mov     rax, [r15]
0x14007ed74  mov     [rsp+0C8h+var_98], rax
0x14007ed79  mov     rax, [r14]
0x14007ed7c  mov     [rsp+0C8h+var_A0], rax
0x14007ed81  mov     qword ptr [rsp+0C8h+Flags], rbx
0x14007ed86  mov     r9d, [rsp+0C8h+arg_10]
0x14007ed8e  mov     rcx, [rcx+18h]
0x14007ed92  call    WPP_SF_dqiii
0x14007ed97  nop
0x14007ed98  jmp     loc_14006AECC
```
