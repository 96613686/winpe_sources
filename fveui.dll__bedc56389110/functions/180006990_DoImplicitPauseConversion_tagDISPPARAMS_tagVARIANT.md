# DoImplicitPauseConversion(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180006990`
- end: `0x180006a09`
- name: `?DoImplicitPauseConversion@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `121`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006990`

## import_xrefs

- `FVEAPI!FveConversionStopEx` at `0x1800069db`
- `FVEAPI!FveConversionStopEx` at `0x1800069db`
- `FVEAPI!FveCloseVolume` at `0x1800069ee`
- `FVEAPI!FveCloseVolume` at `0x1800069ee`
- `FVEAPI!FveOpenVolumeW` at `0x1800069c8`
- `FVEAPI!FveOpenVolumeW` at `0x1800069c8`

## pseudocode

```c
__int64 __fastcall DoImplicitPauseConversion(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  LONG v3; // ebx
  LONGLONG llVal; // rcx
  __int64 v5; // rdx
  __int64 result; // rax
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  v7 = -1;
  if ( a1 && (llVal = a1->rgvarg->llVal) != 0 )
  {
    v3 = FveOpenVolumeW(llVal, 1, &v7);
    if ( v3 >= 0 )
    {
      LOBYTE(v5) = 1;
      v3 = FveConversionStopEx(v7, v5);
    }
    if ( v7 != -1 )
      FveCloseVolume(v7);
  }
  else
  {
    v3 = -2147467261;
  }
  a2->lVal = v3;
  result = 0;
  a2->vt = 19;
  return result;
}

```

## disassembly

```asm
0x180006990  mov     [rsp+arg_8], rbx
0x180006995  push    rdi
0x180006996  sub     rsp, 20h
0x18000699a  mov     [rsp+28h+arg_0], 0FFFFFFFFFFFFFFFFh
0x1800069a3  mov     rdi, rdx
0x1800069a6  test    rcx, rcx
0x1800069a9  jnz     short loc_1800069B2
0x1800069ab  mov     ebx, 80004003h
0x1800069b0  jmp     short loc_1800069F4
0x1800069b2  mov     rax, [rcx]
0x1800069b5  mov     rcx, [rax+8]
0x1800069b9  test    rcx, rcx
0x1800069bc  jz      short loc_1800069AB
0x1800069be  lea     r8, [rsp+28h+arg_0]
0x1800069c3  mov     edx, 1
0x1800069c8  call    cs:__imp_FveOpenVolumeW
0x1800069ce  mov     ebx, eax
0x1800069d0  test    eax, eax
0x1800069d2  js      short loc_1800069E3
0x1800069d4  mov     rcx, [rsp+28h+arg_0]
0x1800069d9  mov     dl, 1
0x1800069db  call    cs:__imp_FveConversionStopEx
0x1800069e1  mov     ebx, eax
0x1800069e3  mov     rcx, [rsp+28h+arg_0]
0x1800069e8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800069ec  jz      short loc_1800069F4
0x1800069ee  call    cs:__imp_FveCloseVolume
0x1800069f4  mov     [rdi+8], ebx
0x1800069f7  xor     eax, eax
0x1800069f9  mov     rbx, [rsp+28h+arg_8]
0x1800069fe  mov     word ptr [rdi], 13h
0x180006a03  add     rsp, 20h
0x180006a07  pop     rdi
0x180006a08  retn
```
