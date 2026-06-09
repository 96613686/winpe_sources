# EfslpValidatePublicKeyInfo

- ea: `0x180006f60`
- end: `0x1800070cd`
- name: `EfslpValidatePublicKeyInfo`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006c1c`

## callees

- `0x1800064f4`
- `0x180006590`
- `0x180006a98`
- `0x180006f60`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18000702c`
- `ntdll!RtlLengthSid` at `0x18000702c`
- `ntdll!RtlValidSid` at `0x180007015`
- `ntdll!RtlValidSid` at `0x180007015`

## pseudocode

```c
__int64 __fastcall EfslpValidatePublicKeyInfo(__int64 a1, unsigned int a2, _BYTE *a3)
{
  unsigned int v3; // ebp
  __int64 v6; // rsi
  __int64 *v7; // rdx
  int v8; // r9d
  int v9; // r8d
  unsigned __int64 v10; // rdi
  void *v11; // r15
  __int64 v12; // rax
  unsigned int v13; // eax
  int v14; // ecx
  char v16; // [rsp+28h] [rbp-30h]
  char v17; // [rsp+68h] [rbp+10h] BYREF

  v3 = 0;
  v17 = 1;
  v6 = a1;
  *a3 = 0;
  if ( a2 < 0x1C )
  {
    v16 = -6;
    v7 = EFS_SECURITY_DATA_TOO_SMALL;
    v8 = a2;
    v9 = 28;
LABEL_3:
    fnEfsLogTrace2(a1, (_DWORD)v7, v9, v8, 28, v16);
    return v3;
  }
  v8 = *(_DWORD *)(a1 + 8);
  if ( v8 != 3 )
  {
    v16 = 5;
LABEL_6:
    v9 = 13;
    v7 = EFS_API_ERROR_1;
    goto LABEL_3;
  }
  v10 = *(unsigned int *)(a1 + 4);
  if ( (_DWORD)v10 )
  {
    if ( (unsigned int)v10 < 0x1C )
    {
      v16 = 26;
LABEL_10:
      v8 = v10;
      goto LABEL_6;
    }
    if ( v10 > (unsigned __int64)a2 - 12 )
    {
      v16 = 45;
      v8 = *(_DWORD *)(a1 + 4);
LABEL_13:
      v9 = a2;
      v7 = EFS_SECURITY_DATA_TOO_LARGE;
      goto LABEL_3;
    }
    v11 = (void *)(v10 + a1);
    if ( !RtlValidSid((PSID)(v10 + a1)) )
    {
      v16 = 58;
      goto LABEL_10;
    }
    LODWORD(v12) = RtlLengthSid(v11);
    LODWORD(a1) = v10 + v12;
    if ( (int)v10 + (int)v12 < (unsigned int)v10 )
    {
      v16 = 76;
LABEL_18:
      v8 = v12;
      goto LABEL_13;
    }
    if ( (unsigned int)a1 > a2 )
    {
      v16 = 88;
      goto LABEL_18;
    }
  }
  v12 = *(unsigned int *)(v6 + 16);
  if ( a2 < (unsigned int)v12 )
  {
    v16 = 99;
    goto LABEL_18;
  }
  v13 = EfslpValidateCertHashData(v6 + v12, a2 - (unsigned int)v12, &v17);
  v3 = v13;
  if ( v13 )
  {
    fnEfsLogTrace1(v14, (unsigned int)EFS_API_ERROR, v13, 28, 111);
  }
  else if ( v17 )
  {
    *a3 = 1;
  }
  else
  {
    fnEfsLogTrace1(v14, (unsigned int)EFS_API_ERROR, 13, 28, 117);
  }
  return v3;
}

```

## disassembly

```asm
0x180006f60  mov     rax, rsp
0x180006f63  mov     [rax+8], rbx
0x180006f67  mov     [rax+18h], rbp
0x180006f6b  push    rsi
0x180006f6c  push    rdi
0x180006f6d  push    r12
0x180006f6f  push    r14
0x180006f71  push    r15
0x180006f73  sub     rsp, 30h
0x180006f77  xor     ebp, ebp
0x180006f79  mov     ebx, edx
0x180006f7b  mov     r14, r8
0x180006f7e  mov     byte ptr [rax+10h], 1
0x180006f82  mov     rsi, rcx
0x180006f85  mov     [r8], bpl
0x180006f88  lea     r12d, [rbp+1Ch]
0x180006f8c  cmp     edx, r12d
0x180006f8f  jnb     short loc_180006FB4
0x180006f91  mov     dword ptr [rax-30h], 2FAh
0x180006f98  lea     rdx, EFS_SECURITY_DATA_TOO_SMALL
0x180006f9f  mov     r9d, ebx
0x180006fa2  mov     r8d, r12d
0x180006fa5  mov     [rsp+58h+var_38], r12d
0x180006faa  call    fnEfsLogTrace2
0x180006faf  jmp     loc_1800070B4
0x180006fb4  mov     r9d, [rcx+8]
0x180006fb8  cmp     r9d, 3
0x180006fbc  jz      short loc_180006FD5
0x180006fbe  mov     dword ptr [rsp+58h+var_30], 305h
0x180006fc6  mov     r8d, 0Dh
0x180006fcc  lea     rdx, EFS_API_ERROR_1
0x180006fd3  jmp     short loc_180006FA5
0x180006fd5  mov     edi, [rcx+4]
0x180006fd8  test    edi, edi
0x180006fda  jz      short loc_180007054
0x180006fdc  cmp     edi, r12d
0x180006fdf  jnb     short loc_180006FEE
0x180006fe1  mov     dword ptr [rsp+58h+var_30], 31Ah
0x180006fe9  mov     r9d, edi
0x180006fec  jmp     short loc_180006FC6
0x180006fee  lea     rax, [rbx-0Ch]
0x180006ff2  cmp     rdi, rax
0x180006ff5  jbe     short loc_18000700E
0x180006ff7  mov     dword ptr [rsp+58h+var_30], 32Dh
0x180006fff  mov     r9d, edi
0x180007002  mov     r8d, ebx
0x180007005  lea     rdx, EFS_SECURITY_DATA_TOO_LARGE
0x18000700c  jmp     short loc_180006FA5
0x18000700e  lea     r15, [rdi+rcx]
0x180007012  mov     rcx, r15; Sid
0x180007015  call    cs:__imp_RtlValidSid
0x18000701b  test    al, al
0x18000701d  jnz     short loc_180007029
0x18000701f  mov     dword ptr [rsp+58h+var_30], 33Ah
0x180007027  jmp     short loc_180006FE9
0x180007029  mov     rcx, r15; Sid
0x18000702c  call    cs:__imp_RtlLengthSid
0x180007032  lea     ecx, [rdi+rax]
0x180007035  cmp     ecx, edi
0x180007037  jnb     short loc_180007046
0x180007039  mov     dword ptr [rsp+58h+var_30], 34Ch
0x180007041  mov     r9d, eax
0x180007044  jmp     short loc_180007002
0x180007046  cmp     ecx, ebx
0x180007048  jbe     short loc_180007054
0x18000704a  mov     dword ptr [rsp+58h+var_30], 358h
0x180007052  jmp     short loc_180007041
0x180007054  mov     eax, [rsi+10h]
0x180007057  cmp     ebx, eax
0x180007059  jnb     short loc_180007065
0x18000705b  mov     dword ptr [rsp+58h+var_30], 363h
0x180007063  jmp     short loc_180007041
0x180007065  sub     ebx, eax
0x180007067  lea     rcx, [rsi+rax]
0x18000706b  mov     edx, ebx
0x18000706d  lea     r8, [rsp+58h+arg_8]
0x180007072  call    EfslpValidateCertHashData
0x180007077  mov     ebp, eax
0x180007079  test    eax, eax
0x18000707b  jz      short loc_180007099
0x18000707d  mov     [rsp+58h+var_38], 36Fh
0x180007085  mov     r8d, eax
0x180007088  mov     r9d, r12d
0x18000708b  lea     rdx, EFS_API_ERROR
0x180007092  call    fnEfsLogTrace1
0x180007097  jmp     short loc_1800070B4
0x180007099  cmp     [rsp+58h+arg_8], 0
0x18000709e  jnz     short loc_1800070B0
0x1800070a0  mov     [rsp+58h+var_38], 375h
0x1800070a8  mov     r8d, 0Dh
0x1800070ae  jmp     short loc_180007088
0x1800070b0  mov     byte ptr [r14], 1
0x1800070b4  mov     rbx, [rsp+58h+arg_0]
0x1800070b9  mov     eax, ebp
0x1800070bb  mov     rbp, [rsp+58h+arg_10]
0x1800070c0  add     rsp, 30h
0x1800070c4  pop     r15
0x1800070c6  pop     r14
0x1800070c8  pop     r12
0x1800070ca  pop     rdi
0x1800070cb  pop     rsi
0x1800070cc  retn
```
