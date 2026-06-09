# DoIsAutoUnlockEnabled(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180006a10`
- end: `0x180006ab6`
- name: `?DoIsAutoUnlockEnabled@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001bb0`
- `0x180006a10`

## import_xrefs

- `FVEAPI!FveIsBoundDataVolume` at `0x180006a6e`
- `FVEAPI!FveIsBoundDataVolume` at `0x180006a6e`
- `FVEAPI!FveCloseVolume` at `0x180006a81`
- `FVEAPI!FveCloseVolume` at `0x180006a81`
- `FVEAPI!FveOpenVolumeW` at `0x180006a53`
- `FVEAPI!FveOpenVolumeW` at `0x180006a53`

## pseudocode

```c
__int64 __fastcall DoIsAutoUnlockEnabled(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  VARIANTARG *rgvarg; // rcx
  LONG IsBoundDataVolume; // ebx
  int v6; // [rsp+20h] [rbp-38h] BYREF
  __int64 v7; // [rsp+28h] [rbp-30h] BYREF
  __int128 v8; // [rsp+30h] [rbp-28h] BYREF

  rgvarg = a1->rgvarg;
  v6 = 0;
  v7 = -1;
  v8 = 0;
  IsBoundDataVolume = FveOpenVolumeW(rgvarg->llVal, 0, &v7);
  if ( IsBoundDataVolume >= 0 )
    IsBoundDataVolume = FveIsBoundDataVolume(v7, &v6, &v8);
  if ( v7 != -1 )
    FveCloseVolume(v7);
  a2->vt = 19;
  if ( IsBoundDataVolume >= 0 )
    IsBoundDataVolume = v6 == 0;
  a2->lVal = IsBoundDataVolume;
  return 0;
}

```

## disassembly

```asm
0x180006a10  mov     [rsp+arg_10], rbx
0x180006a15  push    rdi
0x180006a16  sub     rsp, 50h
0x180006a1a  mov     rax, cs:__security_cookie
0x180006a21  xor     rax, rsp
0x180006a24  mov     [rsp+58h+var_18], rax
0x180006a29  mov     rcx, [rcx]
0x180006a2c  lea     r8, [rsp+58h+var_30]
0x180006a31  xorps   xmm0, xmm0
0x180006a34  mov     [rsp+58h+var_38], 0
0x180006a3c  mov     rdi, rdx
0x180006a3f  mov     [rsp+58h+var_30], 0FFFFFFFFFFFFFFFFh
0x180006a48  movups  [rsp+58h+var_28], xmm0
0x180006a4d  mov     rcx, [rcx+8]
0x180006a51  xor     edx, edx
0x180006a53  call    cs:__imp_FveOpenVolumeW
0x180006a59  mov     ebx, eax
0x180006a5b  test    eax, eax
0x180006a5d  js      short loc_180006A76
0x180006a5f  mov     rcx, [rsp+58h+var_30]
0x180006a64  lea     r8, [rsp+58h+var_28]
0x180006a69  lea     rdx, [rsp+58h+var_38]
0x180006a6e  call    cs:__imp_FveIsBoundDataVolume
0x180006a74  mov     ebx, eax
0x180006a76  mov     rcx, [rsp+58h+var_30]
0x180006a7b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180006a7f  jz      short loc_180006A87
0x180006a81  call    cs:__imp_FveCloseVolume
0x180006a87  mov     word ptr [rdi], 13h
0x180006a8c  test    ebx, ebx
0x180006a8e  js      short loc_180006A99
0x180006a90  xor     ebx, ebx
0x180006a92  cmp     [rsp+58h+var_38], ebx
0x180006a96  setz    bl
0x180006a99  mov     [rdi+8], ebx
0x180006a9c  xor     eax, eax
0x180006a9e  mov     rcx, [rsp+58h+var_18]
0x180006aa3  xor     rcx, rsp; StackCookie
0x180006aa6  call    __security_check_cookie
0x180006aab  mov     rbx, [rsp+58h+arg_10]
0x180006ab0  add     rsp, 50h
0x180006ab4  pop     rdi
0x180006ab5  retn
```
