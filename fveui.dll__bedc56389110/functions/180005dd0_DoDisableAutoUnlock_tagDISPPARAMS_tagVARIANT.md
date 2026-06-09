# DoDisableAutoUnlock(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180005dd0`
- end: `0x180005ea3`
- name: `?DoDisableAutoUnlock@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `211`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001bb0`
- `0x180005dd0`

## import_xrefs

- `FVEAPI!FveIsBoundDataVolume` at `0x180005e31`
- `FVEAPI!FveIsBoundDataVolume` at `0x180005e31`
- `FVEAPI!FveUnbindDataVolume` at `0x180005e47`
- `FVEAPI!FveUnbindDataVolume` at `0x180005e47`
- `FVEAPI!FveDeleteAuthMethod` at `0x180005e5b`
- `FVEAPI!FveDeleteAuthMethod` at `0x180005e5b`
- `FVEAPI!FveCloseVolume` at `0x180005e77`
- `FVEAPI!FveCloseVolume` at `0x180005e77`
- `FVEAPI!FveCommitChanges` at `0x180005e65`
- `FVEAPI!FveCommitChanges` at `0x180005e65`
- `FVEAPI!FveOpenVolumeW` at `0x180005e19`
- `FVEAPI!FveOpenVolumeW` at `0x180005e19`

## pseudocode

```c
__int64 __fastcall DoDisableAutoUnlock(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  VARIANTARG *rgvarg; // rcx
  LONG IsBoundDataVolume; // ebx
  __int64 result; // rax
  __int64 v6; // [rsp+20h] [rbp-30h] BYREF
  int v7; // [rsp+28h] [rbp-28h] BYREF
  __int128 v8; // [rsp+30h] [rbp-20h] BYREF

  rgvarg = a1->rgvarg;
  v6 = -1;
  v7 = 0;
  v8 = 0;
  IsBoundDataVolume = FveOpenVolumeW(rgvarg->llVal, 1, &v6);
  if ( IsBoundDataVolume >= 0 )
  {
    IsBoundDataVolume = FveIsBoundDataVolume(v6, &v7, &v8);
    if ( IsBoundDataVolume >= 0 )
    {
      if ( v7 )
      {
        IsBoundDataVolume = FveUnbindDataVolume(v6);
        if ( IsBoundDataVolume >= 0 )
        {
          FveDeleteAuthMethod(v6, &v8);
          IsBoundDataVolume = FveCommitChanges(v6);
        }
      }
    }
  }
  if ( v6 != -1 )
    FveCloseVolume();
  a2->vt = 19;
  result = 0;
  a2->lVal = IsBoundDataVolume;
  return result;
}

```

## disassembly

```asm
0x180005dd0  mov     [rsp-8+arg_10], rbx
0x180005dd5  mov     [rsp-8+arg_18], rdi
0x180005dda  push    rbp
0x180005ddb  mov     rbp, rsp
0x180005dde  sub     rsp, 50h
0x180005de2  mov     rax, cs:__security_cookie
0x180005de9  xor     rax, rsp
0x180005dec  mov     [rbp+var_10], rax
0x180005df0  mov     rcx, [rcx]
0x180005df3  lea     r8, [rbp+var_30]
0x180005df7  xorps   xmm0, xmm0
0x180005dfa  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFFh
0x180005e02  mov     rdi, rdx
0x180005e05  mov     [rbp+var_28], 0
0x180005e0c  movups  [rbp+var_20], xmm0
0x180005e10  mov     rcx, [rcx+8]
0x180005e14  mov     edx, 1
0x180005e19  call    cs:__imp_FveOpenVolumeW
0x180005e1f  mov     ebx, eax
0x180005e21  test    eax, eax
0x180005e23  js      short loc_180005E6D
0x180005e25  mov     rcx, [rbp+var_30]
0x180005e29  lea     r8, [rbp+var_20]
0x180005e2d  lea     rdx, [rbp+var_28]
0x180005e31  call    cs:__imp_FveIsBoundDataVolume
0x180005e37  mov     ebx, eax
0x180005e39  test    eax, eax
0x180005e3b  js      short loc_180005E6D
0x180005e3d  cmp     [rbp+var_28], 0
0x180005e41  jz      short loc_180005E6D
0x180005e43  mov     rcx, [rbp+var_30]
0x180005e47  call    cs:__imp_FveUnbindDataVolume
0x180005e4d  mov     ebx, eax
0x180005e4f  test    eax, eax
0x180005e51  js      short loc_180005E6D
0x180005e53  mov     rcx, [rbp+var_30]
0x180005e57  lea     rdx, [rbp+var_20]
0x180005e5b  call    cs:__imp_FveDeleteAuthMethod
0x180005e61  mov     rcx, [rbp+var_30]
0x180005e65  call    cs:__imp_FveCommitChanges
0x180005e6b  mov     ebx, eax
0x180005e6d  mov     rcx, [rbp+var_30]
0x180005e71  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180005e75  jz      short loc_180005E7D
0x180005e77  call    cs:__imp_FveCloseVolume
0x180005e7d  mov     word ptr [rdi], 13h
0x180005e82  xor     eax, eax
0x180005e84  mov     [rdi+8], ebx
0x180005e87  mov     rcx, [rbp+var_10]
0x180005e8b  xor     rcx, rsp; StackCookie
0x180005e8e  call    __security_check_cookie
0x180005e93  mov     rbx, [rsp+50h+arg_10]
0x180005e98  mov     rdi, [rsp+50h+arg_18]
0x180005e9d  add     rsp, 50h
0x180005ea1  pop     rbp
0x180005ea2  retn
```
