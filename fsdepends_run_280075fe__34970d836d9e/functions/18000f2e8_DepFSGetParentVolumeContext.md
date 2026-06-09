# DepFSGetParentVolumeContext

- ea: `0x18000f2e8`
- end: `0x18000f4b4`
- name: `DepFSGetParentVolumeContext`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000db70`

## callees

- `0x1800015a8`
- `0x18000f2e8`
- `0x18000f91c`
- `0x18000f970`

## import_xrefs

- `FLTMGR!FltGetVolumeFromFileObject` at `0x18000f331`
- `FLTMGR!FltGetVolumeFromFileObject` at `0x18000f331`
- `FLTMGR!FltObjectDereference` at `0x18000f3f9`
- `FLTMGR!FltObjectDereference` at `0x18000f451`
- `FLTMGR!FltObjectDereference` at `0x18000f3f9`
- `FLTMGR!FltObjectDereference` at `0x18000f451`
- `FLTMGR!FltGetVolumeInstanceFromName` at `0x18000f357`
- `FLTMGR!FltGetVolumeInstanceFromName` at `0x18000f357`
- `FLTMGR!FltReleaseContext` at `0x18000f3a1`
- `FLTMGR!FltReleaseContext` at `0x18000f3a1`
- `FLTMGR!FltGetInstanceContext` at `0x18000f375`
- `FLTMGR!FltGetInstanceContext` at `0x18000f375`

## pseudocode

```c
__int64 __fastcall DepFSGetParentVolumeContext(struct _FLT_INSTANCE *a1, __int64 a2)
{
  PFLT_CONTEXT *v2; // rdi
  bool v3; // zf
  struct _FLT_FILTER *v6; // rbp
  NTSTATUS VolumeFromFileObject; // ebx
  int v8; // eax
  PFLT_CONTEXT v9; // rcx
  PFLT_INSTANCE RetInstance; // [rsp+50h] [rbp+8h] BYREF
  PFLT_VOLUME RetVolume; // [rsp+58h] [rbp+10h] BYREF

  RetInstance = a1;
  v2 = (PFLT_CONTEXT *)(a2 + 112);
  RetVolume = 0;
  v3 = *(_QWORD *)(a2 + 112) == 0;
  RetInstance = 0;
  if ( !v3 )
    return 0;
  v6 = (struct _FLT_FILTER *)Filter;
  VolumeFromFileObject = FltGetVolumeFromFileObject((PFLT_FILTER)Filter, *(PFILE_OBJECT *)(a2 + 104), &RetVolume);
  if ( VolumeFromFileObject < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids,
        v6,
        *(_QWORD *)(a2 + 104),
        VolumeFromFileObject);
    }
  }
  else
  {
    VolumeFromFileObject = FltGetVolumeInstanceFromName(v6, RetVolume, 0, &RetInstance);
    if ( VolumeFromFileObject < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqD(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids,
          v6,
          *(_QWORD *)(a2 + 104),
          VolumeFromFileObject);
      }
    }
    else
    {
      VolumeFromFileObject = FltGetInstanceContext(RetInstance, v2);
      if ( VolumeFromFileObject < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqD(
            WPP_GLOBAL_Control->AttachedDevice,
            10,
            WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids,
            v6,
            *(_QWORD *)(a2 + 104),
            VolumeFromFileObject);
        }
      }
      else
      {
        v8 = ReferenceVolumeContext(*v2, 1);
        v9 = *v2;
        VolumeFromFileObject = v8;
        if ( v8 < 0 )
          FltReleaseContext(v9);
        else
          DereferenceVolumeContext((__int64)v9);
      }
      FltObjectDereference(RetInstance);
    }
    FltObjectDereference(RetVolume);
  }
  return (unsigned int)VolumeFromFileObject;
}

```

## disassembly

```asm
0x18000f2e8  mov     rax, rsp
0x18000f2eb  mov     [rax+18h], rbx
0x18000f2ef  mov     [rax+8], rcx
0x18000f2f3  push    rbp
0x18000f2f4  push    rsi
0x18000f2f5  push    rdi
0x18000f2f6  sub     rsp, 30h
0x18000f2fa  lea     rdi, [rdx+70h]
0x18000f2fe  mov     qword ptr [rax+10h], 0
0x18000f306  cmp     qword ptr [rdi], 0
0x18000f30a  mov     rsi, rdx
0x18000f30d  mov     qword ptr [rax+8], 0
0x18000f315  jz      short loc_18000F31E
0x18000f317  xor     eax, eax
0x18000f319  jmp     loc_18000F4A6
0x18000f31e  mov     rbp, cs:Filter
0x18000f325  lea     r8, [rsp+48h+RetVolume]; RetVolume
0x18000f32a  mov     rdx, [rdx+68h]; FileObject
0x18000f32e  mov     rcx, rbp; Filter
0x18000f331  call    cs:__imp_FltGetVolumeFromFileObject
0x18000f338  nop     dword ptr [rax+rax+00h]
0x18000f33d  mov     ebx, eax
0x18000f33f  test    eax, eax
0x18000f341  js      loc_18000F45F
0x18000f347  mov     rdx, [rsp+48h+RetVolume]; Volume
0x18000f34c  lea     r9, [rsp+48h+RetInstance]; RetInstance
0x18000f351  xor     r8d, r8d; InstanceName
0x18000f354  mov     rcx, rbp; Filter
0x18000f357  call    cs:__imp_FltGetVolumeInstanceFromName
0x18000f35e  nop     dword ptr [rax+rax+00h]
0x18000f363  mov     ebx, eax
0x18000f365  test    eax, eax
0x18000f367  js      loc_18000F407
0x18000f36d  mov     rcx, [rsp+48h+RetInstance]; Instance
0x18000f372  mov     rdx, rdi; Context
0x18000f375  call    cs:__imp_FltGetInstanceContext
0x18000f37c  nop     dword ptr [rax+rax+00h]
0x18000f381  mov     ebx, eax
0x18000f383  test    eax, eax
0x18000f385  js      short loc_18000F3AF
0x18000f387  mov     rcx, [rdi]; Context
0x18000f38a  mov     dl, 1
0x18000f38c  call    ReferenceVolumeContext
0x18000f391  mov     rcx, [rdi]; Context
0x18000f394  mov     ebx, eax
0x18000f396  test    eax, eax
0x18000f398  js      short loc_18000F3A1
0x18000f39a  call    DereferenceVolumeContext
0x18000f39f  jmp     short loc_18000F3F4
0x18000f3a1  call    cs:__imp_FltReleaseContext
0x18000f3a8  nop     dword ptr [rax+rax+00h]
0x18000f3ad  jmp     short loc_18000F3F4
0x18000f3af  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3b6  lea     rax, WPP_GLOBAL_Control
0x18000f3bd  cmp     rcx, rax
0x18000f3c0  jz      short loc_18000F3F4
0x18000f3c2  mov     eax, [rcx+2Ch]
0x18000f3c5  test    al, 1
0x18000f3c7  jz      short loc_18000F3F4
0x18000f3c9  cmp     byte ptr [rcx+29h], 2
0x18000f3cd  jb      short loc_18000F3F4
0x18000f3cf  mov     rax, [rsi+68h]
0x18000f3d3  lea     r8, WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids
0x18000f3da  mov     rcx, [rcx+18h]
0x18000f3de  mov     edx, 0Ah
0x18000f3e3  mov     [rsp+48h+var_20], ebx
0x18000f3e7  mov     r9, rbp
0x18000f3ea  mov     [rsp+48h+var_28], rax
0x18000f3ef  call    WPP_SF_qqD
0x18000f3f4  mov     rcx, [rsp+48h+RetInstance]; FltObject
0x18000f3f9  call    cs:__imp_FltObjectDereference
0x18000f400  nop     dword ptr [rax+rax+00h]
0x18000f405  jmp     short loc_18000F44C
0x18000f407  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f40e  lea     rax, WPP_GLOBAL_Control
0x18000f415  cmp     rcx, rax
0x18000f418  jz      short loc_18000F44C
0x18000f41a  mov     eax, [rcx+2Ch]
0x18000f41d  test    al, 1
0x18000f41f  jz      short loc_18000F44C
0x18000f421  cmp     byte ptr [rcx+29h], 2
0x18000f425  jb      short loc_18000F44C
0x18000f427  mov     rax, [rsi+68h]
0x18000f42b  lea     r8, WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids
0x18000f432  mov     rcx, [rcx+18h]
0x18000f436  mov     edx, 0Bh
0x18000f43b  mov     [rsp+48h+var_20], ebx
0x18000f43f  mov     r9, rbp
0x18000f442  mov     [rsp+48h+var_28], rax
0x18000f447  call    WPP_SF_qqD
0x18000f44c  mov     rcx, [rsp+48h+RetVolume]; FltObject
0x18000f451  call    cs:__imp_FltObjectDereference
0x18000f458  nop     dword ptr [rax+rax+00h]
0x18000f45d  jmp     short loc_18000F4A4
0x18000f45f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f466  lea     rax, WPP_GLOBAL_Control
0x18000f46d  cmp     rcx, rax
0x18000f470  jz      short loc_18000F4A4
0x18000f472  mov     eax, [rcx+2Ch]
0x18000f475  test    al, 1
0x18000f477  jz      short loc_18000F4A4
0x18000f479  cmp     byte ptr [rcx+29h], 2
0x18000f47d  jb      short loc_18000F4A4
0x18000f47f  mov     rax, [rsi+68h]
0x18000f483  lea     r8, WPP_a3c4d1782baa35d2d3c4179a15ae3a1d_Traceguids
0x18000f48a  mov     rcx, [rcx+18h]
0x18000f48e  mov     edx, 0Ch
0x18000f493  mov     [rsp+48h+var_20], ebx
0x18000f497  mov     r9, rbp
0x18000f49a  mov     [rsp+48h+var_28], rax
0x18000f49f  call    WPP_SF_qqD
0x18000f4a4  mov     eax, ebx
0x18000f4a6  mov     rbx, [rsp+48h+arg_10]
0x18000f4ab  add     rsp, 30h
0x18000f4af  pop     rdi
0x18000f4b0  pop     rsi
0x18000f4b1  pop     rbp
0x18000f4b2  retn
```
