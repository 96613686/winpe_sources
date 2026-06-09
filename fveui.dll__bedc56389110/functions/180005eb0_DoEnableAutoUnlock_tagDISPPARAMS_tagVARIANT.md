# DoEnableAutoUnlock(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180005eb0`
- end: `0x180005fc3`
- name: `?DoEnableAutoUnlock@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001bb0`
- `0x180005eb0`

## import_xrefs

- `FVEAPI!FveSetAllowKeyExport` at `0x180005f17`
- `FVEAPI!FveSetAllowKeyExport` at `0x180005f17`
- `FVEAPI!FveBindDataVolume` at `0x180005f5d`
- `FVEAPI!FveBindDataVolume` at `0x180005f5d`
- `FVEAPI!FveCloseVolume` at `0x180005f8f`
- `FVEAPI!FveCloseVolume` at `0x180005f8f`
- `FVEAPI!FveCommitChanges` at `0x180005f6d`
- `FVEAPI!FveCommitChanges` at `0x180005f6d`
- `FVEAPI!FveAddAuthMethodInformation` at `0x180005f49`
- `FVEAPI!FveAddAuthMethodInformation` at `0x180005f49`
- `FVEAPI!FveOpenVolumeW` at `0x180005f31`
- `FVEAPI!FveOpenVolumeW` at `0x180005f31`

## pseudocode

```c
__int64 __fastcall DoEnableAutoUnlock(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  __int64 v2; // rsi
  LONG v5; // ebx
  _BYTE *v6; // rax
  __int64 result; // rax
  __int64 v8; // [rsp+20h] [rbp-60h] BYREF
  _DWORD v9[2]; // [rsp+28h] [rbp-58h] BYREF
  __int64 v10; // [rsp+30h] [rbp-50h]
  __int128 v11; // [rsp+38h] [rbp-48h]
  __int128 v12; // [rsp+48h] [rbp-38h]
  __int64 v13; // [rsp+58h] [rbp-28h]
  __int128 v14; // [rsp+60h] [rbp-20h] BYREF

  v9[1] = 1;
  v2 = 56;
  v10 = 0x40000;
  v9[0] = 56;
  v8 = -1;
  v13 = 0;
  v14 = 0;
  v11 = 0;
  v12 = 0;
  v5 = FveSetAllowKeyExport(1);
  if ( v5 >= 0 )
  {
    v5 = FveOpenVolumeW(a1->rgvarg->llVal, 1, &v8);
    if ( v5 >= 0 )
    {
      v5 = FveAddAuthMethodInformation(v8, v9, &v14);
      if ( v5 >= 0 )
      {
        v5 = FveBindDataVolume(v8, &v14);
        if ( v5 >= 0 )
          v5 = FveCommitChanges(v8);
      }
    }
  }
  v6 = v9;
  do
  {
    *v6++ = 0;
    --v2;
  }
  while ( v2 );
  if ( v8 != -1 )
    FveCloseVolume();
  a2->vt = 19;
  result = 0;
  a2->lVal = v5;
  return result;
}

```

## disassembly

```asm
0x180005eb0  mov     [rsp-18h+arg_10], rbx
0x180005eb5  mov     [rsp-18h+arg_18], rsi
0x180005eba  push    rbp
0x180005ebb  push    rdi
0x180005ebc  push    r14
0x180005ebe  mov     rbp, rsp
0x180005ec1  sub     rsp, 80h
0x180005ec8  mov     rax, cs:__security_cookie
0x180005ecf  xor     rax, rsp
0x180005ed2  mov     [rbp+var_10], rax
0x180005ed6  xorps   xmm0, xmm0
0x180005ed9  mov     [rbp+var_54], 1
0x180005ee0  mov     esi, 38h ; '8'
0x180005ee5  mov     [rbp+var_50], 40000h
0x180005eed  mov     r14, rcx
0x180005ef0  mov     [rbp+var_58], esi
0x180005ef3  xorps   xmm1, xmm1
0x180005ef6  mov     [rbp+var_60], 0FFFFFFFFFFFFFFFFh
0x180005efe  xor     eax, eax
0x180005f00  mov     rdi, rdx
0x180005f03  lea     ecx, [rsi-37h]
0x180005f06  mov     [rbp+var_28], rax
0x180005f0a  movups  [rbp+var_20], xmm0
0x180005f0e  movdqu  [rbp+var_48], xmm0
0x180005f13  movups  [rbp+var_38], xmm1
0x180005f17  call    cs:__imp_FveSetAllowKeyExport
0x180005f1d  mov     ebx, eax
0x180005f1f  test    eax, eax
0x180005f21  js      short loc_180005F75
0x180005f23  mov     rcx, [r14]
0x180005f26  lea     r8, [rbp+var_60]
0x180005f2a  lea     edx, [rsi-37h]
0x180005f2d  mov     rcx, [rcx+8]
0x180005f31  call    cs:__imp_FveOpenVolumeW
0x180005f37  mov     ebx, eax
0x180005f39  test    eax, eax
0x180005f3b  js      short loc_180005F75
0x180005f3d  mov     rcx, [rbp+var_60]
0x180005f41  lea     r8, [rbp+var_20]
0x180005f45  lea     rdx, [rbp+var_58]
0x180005f49  call    cs:__imp_FveAddAuthMethodInformation
0x180005f4f  mov     ebx, eax
0x180005f51  test    eax, eax
0x180005f53  js      short loc_180005F75
0x180005f55  mov     rcx, [rbp+var_60]
0x180005f59  lea     rdx, [rbp+var_20]
0x180005f5d  call    cs:__imp_FveBindDataVolume
0x180005f63  mov     ebx, eax
0x180005f65  test    eax, eax
0x180005f67  js      short loc_180005F75
0x180005f69  mov     rcx, [rbp+var_60]
0x180005f6d  call    cs:__imp_FveCommitChanges
0x180005f73  mov     ebx, eax
0x180005f75  lea     rax, [rbp+var_58]
0x180005f79  mov     byte ptr [rax], 0
0x180005f7c  inc     rax
0x180005f7f  sub     rsi, 1
0x180005f83  jnz     short loc_180005F79
0x180005f85  mov     rcx, [rbp+var_60]
0x180005f89  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180005f8d  jz      short loc_180005F95
0x180005f8f  call    cs:__imp_FveCloseVolume
0x180005f95  mov     word ptr [rdi], 13h
0x180005f9a  xor     eax, eax
0x180005f9c  mov     [rdi+8], ebx
0x180005f9f  mov     rcx, [rbp+var_10]
0x180005fa3  xor     rcx, rsp; StackCookie
0x180005fa6  call    __security_check_cookie
0x180005fab  lea     r11, [rsp+80h+var_s0]
0x180005fb3  mov     rbx, [r11+30h]
0x180005fb7  mov     rsi, [r11+38h]
0x180005fbb  mov     rsp, r11
0x180005fbe  pop     r14
0x180005fc0  pop     rdi
0x180005fc1  pop     rbp
0x180005fc2  retn
```
