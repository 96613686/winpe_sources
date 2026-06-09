# DoPauseConversion(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180006b90`
- end: `0x180006c1f`
- name: `?DoPauseConversion@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006b90`
- `0x180007170`

## import_xrefs

- `FVEAPI!FveConversionStop` at `0x180006bed`
- `FVEAPI!FveConversionStop` at `0x180006bed`
- `FVEAPI!FveCloseVolume` at `0x180006c04`
- `FVEAPI!FveCloseVolume` at `0x180006c04`
- `FVEAPI!FveOpenVolumeW` at `0x180006bd8`
- `FVEAPI!FveOpenVolumeW` at `0x180006bd8`

## pseudocode

```c
__int64 __fastcall DoPauseConversion(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  LONG v3; // ebx
  LONGLONG llVal; // rcx
  __int64 v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = -1;
  if ( a1 && (llVal = a1->rgvarg->llVal) != 0 )
  {
    v3 = FveOpenVolumeW(llVal, 1, &v6);
    if ( v3 >= 0 )
      v3 = FveConversionStop(v6);
  }
  else
  {
    v3 = -2147467261;
  }
  if ( v6 != -1 )
    FveCloseVolume(v6);
  a2->vt = 19;
  a2->lVal = v3;
  return 0;
}

```

## disassembly

```asm
0x180006b90  mov     rax, rsp
0x180006b93  mov     [rax+8], rbx
0x180006b97  mov     [rax+10h], rdx
0x180006b9b  push    rdi
0x180006b9c  sub     rsp, 30h
0x180006ba0  mov     rdi, rdx
0x180006ba3  mov     dword ptr [rax-18h], 0
0x180006baa  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180006bb2  test    rcx, rcx
0x180006bb5  jnz     short loc_180006BC2
0x180006bb7  mov     ebx, 80004003h
0x180006bbc  mov     [rsp+38h+var_18], ebx
0x180006bc0  jmp     short loc_180006BF9
0x180006bc2  mov     rax, [rcx]
0x180006bc5  mov     rcx, [rax+8]
0x180006bc9  test    rcx, rcx
0x180006bcc  jz      short loc_180006BB7
0x180006bce  lea     r8, [rsp+38h+arg_10]
0x180006bd3  mov     edx, 1
0x180006bd8  call    cs:__imp_FveOpenVolumeW
0x180006bde  mov     ebx, eax
0x180006be0  mov     [rsp+38h+var_18], eax
0x180006be4  test    eax, eax
0x180006be6  js      short loc_180006BF9
0x180006be8  mov     rcx, [rsp+38h+arg_10]
0x180006bed  call    cs:__imp_FveConversionStop
0x180006bf3  mov     ebx, eax
0x180006bf5  mov     [rsp+38h+var_18], eax
0x180006bf9  mov     rcx, [rsp+38h+arg_10]
0x180006bfe  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180006c02  jz      short loc_180006C0A
0x180006c04  call    cs:__imp_FveCloseVolume
0x180006c0a  mov     word ptr [rdi], 13h
0x180006c0f  mov     [rdi+8], ebx
0x180006c12  xor     eax, eax
0x180006c14  mov     rbx, [rsp+38h+arg_0]
0x180006c19  add     rsp, 30h
0x180006c1d  pop     rdi
0x180006c1e  retn
0x18002c518  push    rbp
0x18002c51a  sub     rsp, 20h
0x18002c51e  mov     rbp, rdx
0x18002c521  mov     rcx, [rbp+50h]
0x18002c525  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002c529  jz      short loc_18002C532
0x18002c52b  call    cs:__imp_FveCloseVolume
0x18002c531  nop
0x18002c532  mov     eax, 13h
0x18002c537  mov     rcx, [rbp+48h]
0x18002c53b  mov     [rcx], ax
0x18002c53e  mov     eax, [rbp+20h]
0x18002c541  mov     [rcx+8], eax
0x18002c544  add     rsp, 20h
0x18002c548  pop     rbp
0x18002c549  retn
```
