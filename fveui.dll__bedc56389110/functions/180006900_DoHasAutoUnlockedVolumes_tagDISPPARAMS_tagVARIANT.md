# DoHasAutoUnlockedVolumes(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180006900`
- end: `0x180006985`
- name: `?DoHasAutoUnlockedVolumes@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006900`

## import_xrefs

- `FVEAPI!FveIsAnyDataVolumeBoundToOSVolume` at `0x180006948`
- `FVEAPI!FveIsAnyDataVolumeBoundToOSVolume` at `0x180006948`
- `FVEAPI!FveCloseVolume` at `0x180006972`
- `FVEAPI!FveCloseVolume` at `0x18002c504`
- `FVEAPI!FveCloseVolume` at `0x180006972`
- `FVEAPI!FveCloseVolume` at `0x18002c504`
- `FVEAPI!FveOpenVolumeW` at `0x18000692e`
- `FVEAPI!FveOpenVolumeW` at `0x18000692e`

## pseudocode

```c
__int64 __fastcall DoHasAutoUnlockedVolumes(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  int IsAnyDataVolumeBoundToOSVolume; // ebx
  LONG v5; // [rsp+50h] [rbp+18h] BYREF
  __int64 v6; // [rsp+58h] [rbp+20h] BYREF

  v5 = 0;
  v6 = -1;
  IsAnyDataVolumeBoundToOSVolume = FveOpenVolumeW(a1->rgvarg->llVal, 1, &v6);
  if ( IsAnyDataVolumeBoundToOSVolume >= 0 )
  {
    IsAnyDataVolumeBoundToOSVolume = FveIsAnyDataVolumeBoundToOSVolume(v6, &v5);
    if ( IsAnyDataVolumeBoundToOSVolume >= 0 )
    {
      a2->vt = 19;
      a2->lVal = v5;
    }
  }
  if ( v6 != -1 )
    FveCloseVolume(v6);
  return (unsigned int)IsAnyDataVolumeBoundToOSVolume;
}

```

## disassembly

```asm
0x180006900  mov     rax, rsp
0x180006903  mov     [rax+8], rbx
0x180006907  push    rdi
0x180006908  sub     rsp, 30h
0x18000690c  mov     rdi, rdx
0x18000690f  mov     dword ptr [rax+18h], 0
0x180006916  mov     qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x18000691e  mov     rcx, [rcx]
0x180006921  lea     r8, [rax+20h]
0x180006925  mov     edx, 1
0x18000692a  mov     rcx, [rcx+8]
0x18000692e  call    cs:__imp_FveOpenVolumeW
0x180006934  mov     ebx, eax
0x180006936  mov     [rsp+38h+var_18], eax
0x18000693a  test    eax, eax
0x18000693c  js      short loc_180006967
0x18000693e  lea     rdx, [rsp+38h+arg_10]
0x180006943  mov     rcx, [rsp+38h+arg_18]
0x180006948  call    cs:__imp_FveIsAnyDataVolumeBoundToOSVolume
0x18000694e  mov     ebx, eax
0x180006950  mov     [rsp+38h+var_18], eax
0x180006954  test    eax, eax
0x180006956  js      short loc_180006967
0x180006958  mov     eax, 13h
0x18000695d  mov     [rdi], ax
0x180006960  mov     eax, [rsp+38h+arg_10]
0x180006964  mov     [rdi+8], eax
0x180006967  mov     rcx, [rsp+38h+arg_18]
0x18000696c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180006970  jz      short loc_180006978
0x180006972  call    cs:__imp_FveCloseVolume
0x180006978  mov     eax, ebx
0x18000697a  mov     rbx, [rsp+38h+arg_0]
0x18000697f  add     rsp, 30h
0x180006983  pop     rdi
0x180006984  retn
0x18002c4f1  push    rbp
0x18002c4f3  sub     rsp, 20h
0x18002c4f7  mov     rbp, rdx
0x18002c4fa  mov     rcx, [rbp+58h]
0x18002c4fe  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002c502  jz      short loc_18002C50B
0x18002c504  call    cs:__imp_FveCloseVolume
0x18002c50a  nop
0x18002c50b  add     rsp, 20h
0x18002c50f  pop     rbp
0x18002c510  retn
```
