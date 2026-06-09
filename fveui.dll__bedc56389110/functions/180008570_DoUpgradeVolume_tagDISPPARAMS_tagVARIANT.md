# DoUpgradeVolume(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180008570`
- end: `0x1800085e7`
- name: `?DoUpgradeVolume@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `119`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008570`

## import_xrefs

- `FVEAPI!FveCloseVolume` at `0x1800085cc`
- `FVEAPI!FveCloseVolume` at `0x1800085cc`
- `FVEAPI!FveCommitChanges` at `0x1800085b9`
- `FVEAPI!FveCommitChanges` at `0x1800085b9`
- `FVEAPI!FveOpenVolumeW` at `0x180008597`
- `FVEAPI!FveOpenVolumeW` at `0x180008597`
- `FVEAPI!FveUpgradeVolume` at `0x1800085a8`
- `FVEAPI!FveUpgradeVolume` at `0x1800085a8`

## pseudocode

```c
__int64 __fastcall DoUpgradeVolume(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  VARIANTARG *rgvarg; // rcx
  LONG v4; // ebx
  __int64 result; // rax
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  rgvarg = a1->rgvarg;
  v6 = -1;
  v4 = FveOpenVolumeW(rgvarg->llVal, 1, &v6);
  if ( v4 >= 0 )
  {
    v4 = FveUpgradeVolume(v6);
    if ( v4 >= 0 )
      v4 = FveCommitChanges(v6);
  }
  if ( v6 != -1 )
    FveCloseVolume(v6);
  a2->lVal = v4;
  result = (unsigned int)v4;
  a2->vt = 19;
  return result;
}

```

## disassembly

```asm
0x180008570  mov     [rsp+arg_8], rbx
0x180008575  push    rdi
0x180008576  sub     rsp, 20h
0x18000857a  mov     rcx, [rcx]
0x18000857d  lea     r8, [rsp+28h+arg_0]
0x180008582  mov     rdi, rdx
0x180008585  mov     [rsp+28h+arg_0], 0FFFFFFFFFFFFFFFFh
0x18000858e  mov     edx, 1
0x180008593  mov     rcx, [rcx+8]
0x180008597  call    cs:__imp_FveOpenVolumeW
0x18000859d  mov     ebx, eax
0x18000859f  test    eax, eax
0x1800085a1  js      short loc_1800085C1
0x1800085a3  mov     rcx, [rsp+28h+arg_0]
0x1800085a8  call    cs:__imp_FveUpgradeVolume
0x1800085ae  mov     ebx, eax
0x1800085b0  test    eax, eax
0x1800085b2  js      short loc_1800085C1
0x1800085b4  mov     rcx, [rsp+28h+arg_0]
0x1800085b9  call    cs:__imp_FveCommitChanges
0x1800085bf  mov     ebx, eax
0x1800085c1  mov     rcx, [rsp+28h+arg_0]
0x1800085c6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800085ca  jz      short loc_1800085D2
0x1800085cc  call    cs:__imp_FveCloseVolume
0x1800085d2  mov     [rdi+8], ebx
0x1800085d5  mov     eax, ebx
0x1800085d7  mov     rbx, [rsp+28h+arg_8]
0x1800085dc  mov     word ptr [rdi], 13h
0x1800085e1  add     rsp, 20h
0x1800085e5  pop     rdi
0x1800085e6  retn
```
