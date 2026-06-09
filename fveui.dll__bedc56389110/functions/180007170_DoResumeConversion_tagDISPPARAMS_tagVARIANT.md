# DoResumeConversion(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180007170`
- end: `0x1800071ff`
- name: `?DoResumeConversion@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007170`

## import_xrefs

- `FVEAPI!FveConversionResume` at `0x1800071cd`
- `FVEAPI!FveConversionResume` at `0x1800071cd`
- `FVEAPI!FveCloseVolume` at `0x1800071e4`
- `FVEAPI!FveCloseVolume` at `0x18002c52b`
- `FVEAPI!FveCloseVolume` at `0x1800071e4`
- `FVEAPI!FveCloseVolume` at `0x18002c52b`
- `FVEAPI!FveOpenVolumeW` at `0x1800071b8`
- `FVEAPI!FveOpenVolumeW` at `0x1800071b8`

## pseudocode

```c
__int64 __fastcall DoResumeConversion(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  LONG v3; // ebx
  LONGLONG llVal; // rcx
  __int64 v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = -1;
  if ( a1 && (llVal = a1->rgvarg->llVal) != 0 )
  {
    v3 = FveOpenVolumeW(llVal, 1, &v6);
    if ( v3 >= 0 )
      v3 = FveConversionResume(v6);
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
0x180007170  mov     rax, rsp
0x180007173  mov     [rax+8], rbx
0x180007177  mov     [rax+10h], rdx
0x18000717b  push    rdi
0x18000717c  sub     rsp, 30h
0x180007180  mov     rdi, rdx
0x180007183  mov     dword ptr [rax-18h], 0
0x18000718a  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180007192  test    rcx, rcx
0x180007195  jnz     short loc_1800071A2
0x180007197  mov     ebx, 80004003h
0x18000719c  mov     [rsp+38h+var_18], ebx
0x1800071a0  jmp     short loc_1800071D9
0x1800071a2  mov     rax, [rcx]
0x1800071a5  mov     rcx, [rax+8]
0x1800071a9  test    rcx, rcx
0x1800071ac  jz      short loc_180007197
0x1800071ae  lea     r8, [rsp+38h+arg_10]
0x1800071b3  mov     edx, 1
0x1800071b8  call    cs:__imp_FveOpenVolumeW
0x1800071be  mov     ebx, eax
0x1800071c0  mov     [rsp+38h+var_18], eax
0x1800071c4  test    eax, eax
0x1800071c6  js      short loc_1800071D9
0x1800071c8  mov     rcx, [rsp+38h+arg_10]
0x1800071cd  call    cs:__imp_FveConversionResume
0x1800071d3  mov     ebx, eax
0x1800071d5  mov     [rsp+38h+var_18], eax
0x1800071d9  mov     rcx, [rsp+38h+arg_10]
0x1800071de  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800071e2  jz      short loc_1800071EA
0x1800071e4  call    cs:__imp_FveCloseVolume
0x1800071ea  mov     word ptr [rdi], 13h
0x1800071ef  mov     [rdi+8], ebx
0x1800071f2  xor     eax, eax
0x1800071f4  mov     rbx, [rsp+38h+arg_0]
0x1800071f9  add     rsp, 30h
0x1800071fd  pop     rdi
0x1800071fe  retn
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
