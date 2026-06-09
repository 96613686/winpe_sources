# DoAttemptAutoUnlock(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180005b60`
- end: `0x180005be4`
- name: `?DoAttemptAutoUnlock@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `132`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005b60`

## import_xrefs

- `FVEAPI!FveSetAllowKeyExport` at `0x180005b83`
- `FVEAPI!FveSetAllowKeyExport` at `0x180005b83`
- `FVEAPI!FveAttemptAutoUnlock` at `0x180005bb1`
- `FVEAPI!FveAttemptAutoUnlock` at `0x180005bb1`
- `FVEAPI!FveCloseVolume` at `0x180005bc4`
- `FVEAPI!FveCloseVolume` at `0x180005bc4`
- `FVEAPI!FveOpenVolumeW` at `0x180005ba0`
- `FVEAPI!FveOpenVolumeW` at `0x180005ba0`

## pseudocode

```c
__int64 __fastcall DoAttemptAutoUnlock(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  LONG v4; // ebx
  __int64 result; // rax
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = -1;
  v4 = FveSetAllowKeyExport(1);
  if ( v4 >= 0 )
  {
    v4 = FveOpenVolumeW(a1->rgvarg->llVal, 1, &v6);
    if ( v4 >= 0 )
      v4 = FveAttemptAutoUnlock(v6);
  }
  if ( v6 != -1 )
    FveCloseVolume();
  result = 0;
  a2->lVal = v4;
  a2->vt = 19;
  return result;
}

```

## disassembly

```asm
0x180005b60  mov     [rsp+arg_0], rbx
0x180005b65  mov     [rsp+arg_10], rsi
0x180005b6a  push    rdi
0x180005b6b  sub     rsp, 20h
0x180005b6f  mov     rsi, rcx
0x180005b72  mov     [rsp+28h+arg_8], 0FFFFFFFFFFFFFFFFh
0x180005b7b  mov     ecx, 1
0x180005b80  mov     rdi, rdx
0x180005b83  call    cs:__imp_FveSetAllowKeyExport
0x180005b89  mov     ebx, eax
0x180005b8b  test    eax, eax
0x180005b8d  js      short loc_180005BB9
0x180005b8f  mov     rcx, [rsi]
0x180005b92  lea     r8, [rsp+28h+arg_8]
0x180005b97  mov     edx, 1
0x180005b9c  mov     rcx, [rcx+8]
0x180005ba0  call    cs:__imp_FveOpenVolumeW
0x180005ba6  mov     ebx, eax
0x180005ba8  test    eax, eax
0x180005baa  js      short loc_180005BB9
0x180005bac  mov     rcx, [rsp+28h+arg_8]
0x180005bb1  call    cs:__imp_FveAttemptAutoUnlock
0x180005bb7  mov     ebx, eax
0x180005bb9  mov     rcx, [rsp+28h+arg_8]
0x180005bbe  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180005bc2  jz      short loc_180005BCA
0x180005bc4  call    cs:__imp_FveCloseVolume
0x180005bca  mov     rsi, [rsp+28h+arg_10]
0x180005bcf  xor     eax, eax
0x180005bd1  mov     [rdi+8], ebx
0x180005bd4  mov     rbx, [rsp+28h+arg_0]
0x180005bd9  mov     word ptr [rdi], 13h
0x180005bde  add     rsp, 20h
0x180005be2  pop     rdi
0x180005be3  retn
```
