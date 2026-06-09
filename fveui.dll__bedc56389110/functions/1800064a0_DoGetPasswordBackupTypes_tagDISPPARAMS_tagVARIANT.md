# DoGetPasswordBackupTypes(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x1800064a0`
- end: `0x180006577`
- name: `?DoGetPasswordBackupTypes@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001bb0`
- `0x1800064a0`

## import_xrefs

- `FVEAPI!FveGetRecoveryPasswordBackupInformation` at `0x18000652e`
- `FVEAPI!FveGetRecoveryPasswordBackupInformation` at `0x18000652e`
- `FVEAPI!FveCloseVolume` at `0x180006552`
- `FVEAPI!FveCloseVolume` at `0x180006552`
- `FVEAPI!FveOpenVolumeW` at `0x1800064ee`
- `FVEAPI!FveOpenVolumeW` at `0x1800064ee`
- `RPCRT4!UuidFromStringW` at `0x180006506`
- `RPCRT4!UuidFromStringW` at `0x180006506`

## pseudocode

```c
__int64 __fastcall DoGetPasswordBackupTypes(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  VARIANTARG *rgvarg; // rcx
  signed int RecoveryPasswordBackupInformation; // ebx
  RPC_STATUS v6; // eax
  unsigned __int16 v8; // [rsp+20h] [rbp-38h] BYREF
  __int64 v9; // [rsp+28h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-28h] BYREF

  v9 = -1;
  rgvarg = a1->rgvarg;
  Uuid = GUID_NULL;
  v8 = 0;
  RecoveryPasswordBackupInformation = FveOpenVolumeW(rgvarg->llVal, 0, &v9);
  if ( RecoveryPasswordBackupInformation >= 0 )
  {
    v6 = UuidFromStringW(a1->rgvarg[1].bstrVal, &Uuid);
    RecoveryPasswordBackupInformation = 0;
    if ( v6 )
      RecoveryPasswordBackupInformation = v6 | 0x80010000;
    if ( RecoveryPasswordBackupInformation >= 0 )
    {
      RecoveryPasswordBackupInformation = FveGetRecoveryPasswordBackupInformation(v9, &Uuid, &v8);
      if ( RecoveryPasswordBackupInformation >= 0 )
      {
        a2->lVal = v8;
        a2->vt = 19;
      }
    }
  }
  if ( v9 != -1 )
    FveCloseVolume(v9);
  return (unsigned int)RecoveryPasswordBackupInformation;
}

```

## disassembly

```asm
0x1800064a0  mov     r11, rsp
0x1800064a3  mov     [r11+18h], rbx
0x1800064a7  mov     [r11+20h], rsi
0x1800064ab  push    rdi
0x1800064ac  sub     rsp, 50h
0x1800064b0  mov     rax, cs:__security_cookie
0x1800064b7  xor     rax, rsp
0x1800064ba  mov     [rsp+58h+var_18], rax
0x1800064bf  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800064c6  mov     rsi, rcx
0x1800064c9  mov     qword ptr [r11-30h], 0FFFFFFFFFFFFFFFFh
0x1800064d1  mov     rcx, [rcx]
0x1800064d4  lea     r8, [r11-30h]
0x1800064d8  xor     eax, eax
0x1800064da  mov     rdi, rdx
0x1800064dd  movdqu  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x1800064e3  mov     [rsp+58h+var_38], ax
0x1800064e8  xor     edx, edx
0x1800064ea  mov     rcx, [rcx+8]
0x1800064ee  call    cs:__imp_FveOpenVolumeW
0x1800064f4  mov     ebx, eax
0x1800064f6  test    eax, eax
0x1800064f8  js      short loc_180006547
0x1800064fa  mov     rcx, [rsi]
0x1800064fd  lea     rdx, [rsp+58h+Uuid]; Uuid
0x180006502  mov     rcx, [rcx+20h]; StringUuid
0x180006506  call    cs:__imp_UuidFromStringW
0x18000650c  xor     ebx, ebx
0x18000650e  mov     ecx, eax
0x180006510  or      ecx, 80010000h
0x180006516  test    eax, eax
0x180006518  cmovnz  ebx, ecx
0x18000651b  test    ebx, ebx
0x18000651d  js      short loc_180006547
0x18000651f  mov     rcx, [rsp+58h+var_30]
0x180006524  lea     r8, [rsp+58h+var_38]
0x180006529  lea     rdx, [rsp+58h+Uuid]
0x18000652e  call    cs:__imp_FveGetRecoveryPasswordBackupInformation
0x180006534  mov     ebx, eax
0x180006536  test    eax, eax
0x180006538  js      short loc_180006547
0x18000653a  movzx   eax, [rsp+58h+var_38]
0x18000653f  mov     [rdi+8], eax
0x180006542  mov     word ptr [rdi], 13h
0x180006547  mov     rcx, [rsp+58h+var_30]
0x18000654c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180006550  jz      short loc_180006558
0x180006552  call    cs:__imp_FveCloseVolume
0x180006558  mov     eax, ebx
0x18000655a  mov     rcx, [rsp+58h+var_18]
0x18000655f  xor     rcx, rsp; StackCookie
0x180006562  call    __security_check_cookie
0x180006567  mov     rbx, [rsp+58h+arg_10]
0x18000656c  mov     rsi, [rsp+58h+arg_18]
0x180006571  add     rsp, 50h
0x180006575  pop     rdi
0x180006576  retn
```
