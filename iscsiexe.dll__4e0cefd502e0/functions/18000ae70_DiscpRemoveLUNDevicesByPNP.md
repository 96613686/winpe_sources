# DiscpRemoveLUNDevicesByPNP

- ea: `0x18000ae70`
- end: `0x18000b173`
- name: `DiscpRemoveLUNDevicesByPNP`
- size: `771`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180003da0`

## callees

- `0x180001410`
- `0x18000ae70`
- `0x18000b2dc`
- `0x18000bdb0`
- `0x1800180ec`
- `0x18001827c`
- `0x18001afc0`
- `0x18001b0b0`

## import_xrefs

- `ISCSIUM!DiscpReportEventlog` at `0x18000b0dd`
- `ISCSIUM!DiscpReportEventlog` at `0x18000b0dd`
- `ISCSIUM!DiscpGetPnpDeviceId` at `0x18000b013`
- `ISCSIUM!DiscpGetPnpDeviceId` at `0x18000b013`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b10f`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b11d`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b12b`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b13b`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b10f`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b11d`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b12b`
- `ISCSIUM!DiscpFreeMemory` at `0x18000b13b`
- `api-ms-win-devices-config-l1-1-1!CM_Query_And_Remove_SubTreeW` at `0x18000b040`
- `api-ms-win-devices-config-l1-1-1!CM_Query_And_Remove_SubTreeW` at `0x18000b040`

## pseudocode

```c
__int64 __fastcall DiscpRemoveLUNDevicesByPNP(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rsi
  __int64 v3; // rdi
  unsigned int TargetMappingsForSession; // eax
  __int64 v6; // r15
  unsigned int TargetMappingsForAdapter; // ebx
  int TargetMappingsForMPIO; // eax
  char v9; // r14
  unsigned int v10; // r13d
  unsigned int v11; // edx
  __int64 v12; // r8
  int v13; // ebx
  __int64 v14; // rcx
  int v15; // r11d
  int v16; // r10d
  int v17; // r9d
  DEVINST v18; // r12d
  unsigned int v19; // ecx
  __int64 v20; // r14
  char v22; // [rsp+50h] [rbp-B0h]
  unsigned int v23; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v24; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v25; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v26; // [rsp+60h] [rbp-A0h] BYREF
  _PNP_VETO_TYPE pVetoType; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+78h] [rbp-88h] BYREF
  __int64 v31; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+90h] [rbp-70h]
  wchar_t pszDest[40]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR pszVetoName[264]; // [rsp+F0h] [rbp-10h] BYREF

  v32 = a2;
  v25 = 0;
  v23 = 0;
  v24 = 0;
  v2 = 0;
  pVetoType = PNP_VetoTypeUnknown;
  v3 = 0;
  v26 = 0;
  v30 = 0;
  v29 = 0;
  v31 = 0;
  v28 = 0;
  v33 = a1;
  TargetMappingsForSession = DiscpGetTargetMappingsForSession(a1, a2, &v25, &v30);
  v6 = v30;
  TargetMappingsForAdapter = TargetMappingsForSession;
  if ( TargetMappingsForSession )
    goto LABEL_35;
  TargetMappingsForAdapter = DiscpGetTargetMappingsForAdapter(a1, &v23, &v29);
  if ( TargetMappingsForAdapter )
  {
    v2 = v29;
    goto LABEL_35;
  }
  TargetMappingsForMPIO = DiscpGetTargetMappingsForMPIO(&v24, &v31);
  v2 = v29;
  v3 = v31;
  if ( TargetMappingsForMPIO || (v9 = 0, v22 = 0, v10 = 0, !v25) )
  {
LABEL_30:
    TargetMappingsForAdapter = 0;
    goto LABEL_35;
  }
  while ( !v23 )
  {
LABEL_29:
    if ( ++v10 >= v25 )
      goto LABEL_30;
  }
  v11 = 0;
  v12 = 28LL * v10;
  v13 = *(_DWORD *)(v12 + v6 + 4);
  while ( 1 )
  {
    v14 = 28LL * v11;
    if ( v13 == *(_DWORD *)(v14 + v2 + 4) )
    {
      v15 = *(_DWORD *)(v12 + v6 + 8);
      if ( v15 == *(_DWORD *)(v14 + v2 + 8) )
      {
        v16 = *(_DWORD *)(v12 + v6 + 12);
        if ( v16 == *(_DWORD *)(v14 + v2 + 12) )
        {
          v17 = *(_DWORD *)(v12 + v6 + 16);
          if ( v17 == *(_DWORD *)(v14 + v2 + 16) )
            break;
        }
      }
    }
    if ( ++v11 >= v23 )
      goto LABEL_29;
  }
  v18 = *(_DWORD *)(v14 + v2);
  if ( v3 )
  {
    v19 = 0;
    if ( v24 )
    {
      while ( 1 )
      {
        v20 = 28LL * v19;
        if ( v13 == *(_DWORD *)(v20 + v3 + 4)
          && v15 == *(_DWORD *)(v20 + v3 + 8)
          && v16 == *(_DWORD *)(v20 + v3 + 12)
          && v17 == *(_DWORD *)(v20 + v3 + 16) )
        {
          break;
        }
        if ( ++v19 >= v24 )
          goto LABEL_24;
      }
      TargetMappingsForAdapter = DiscpGetDSMPathCount(*(_DWORD *)(v20 + v3), &v26);
      if ( TargetMappingsForAdapter )
        goto LABEL_35;
      if ( v26 <= 1 )
        v18 = *(_DWORD *)(v20 + v3);
LABEL_24:
      v9 = v22;
    }
  }
  if ( (unsigned int)DiscpGetPnpDeviceId(&v28, v18) )
    v28 = 0;
  if ( !CM_Query_And_Remove_SubTreeW(v18, &pVetoType, pszVetoName, 0x104u, 0) )
  {
    v9 = 1;
    v22 = 1;
    goto LABEL_29;
  }
  StringCchPrintfW(pszDest, 0x28u, L"%I64x-%I64x", *v32, v32[1]);
  DiscpReportEventlog(116, 0, 0, 4, &pVetoType, 3);
  if ( v9 )
    DiscpRescanInitiator(v33);
  TargetMappingsForAdapter = -268500928;
LABEL_35:
  if ( v6 )
    DiscpFreeMemory(v6);
  if ( v2 )
    DiscpFreeMemory(v2);
  if ( v3 )
    DiscpFreeMemory(v3);
  if ( v28 )
    DiscpFreeMemory(v28);
  if ( TargetMappingsForAdapter )
    return (unsigned int)-268500928;
  return TargetMappingsForAdapter;
}

```

## disassembly

```asm
0x18000ae70  mov     [rsp-8+arg_10], rbx
0x18000ae75  push    rbp
0x18000ae76  push    rsi
0x18000ae77  push    rdi
0x18000ae78  push    r12
0x18000ae7a  push    r13
0x18000ae7c  push    r14
0x18000ae7e  push    r15
0x18000ae80  lea     rbp, [rsp-210h]
0x18000ae88  sub     rsp, 310h
0x18000ae8f  mov     rax, cs:__security_cookie
0x18000ae96  xor     rax, rsp
0x18000ae99  mov     [rbp+240h+var_40], rax
0x18000aea0  xor     r12d, r12d
0x18000aea3  mov     [rbp+240h+var_2B8], rdx
0x18000aea7  lea     r9, [rsp+340h+var_2C8]
0x18000aeac  mov     [rsp+340h+var_2E4], r12d
0x18000aeb1  lea     r8, [rsp+340h+var_2E4]
0x18000aeb6  mov     [rsp+340h+var_2EC], r12d
0x18000aebb  mov     [rsp+340h+var_2E8], r12d
0x18000aec0  mov     esi, r12d
0x18000aec3  mov     [rsp+340h+pVetoType], r12d
0x18000aec8  mov     edi, r12d
0x18000aecb  mov     [rsp+340h+var_2E0], r12d
0x18000aed0  mov     r14, rcx
0x18000aed3  mov     [rsp+340h+var_2C8], r12
0x18000aed8  mov     [rsp+340h+var_2D0], r12
0x18000aedd  mov     [rbp+240h+var_2C0], r12
0x18000aee1  mov     [rsp+340h+var_2D8], r12
0x18000aee6  mov     [rbp+240h+var_2B0], rcx
0x18000aeea  call    DiscpGetTargetMappingsForSession
0x18000aeef  mov     r15, [rsp+340h+var_2C8]
0x18000aef4  mov     ebx, eax
0x18000aef6  test    eax, eax
0x18000aef8  jnz     loc_18000B101
0x18000aefe  lea     r8, [rsp+340h+var_2D0]
0x18000af03  mov     rcx, r14
0x18000af06  lea     rdx, [rsp+340h+var_2EC]
0x18000af0b  call    DiscpGetTargetMappingsForAdapter
0x18000af10  mov     ebx, eax
0x18000af12  test    eax, eax
0x18000af14  jnz     loc_18000B0FC
0x18000af1a  lea     rdx, [rbp+240h+var_2C0]
0x18000af1e  lea     rcx, [rsp+340h+var_2E8]
0x18000af23  call    DiscpGetTargetMappingsForMPIO
0x18000af28  mov     rsi, [rsp+340h+var_2D0]
0x18000af2d  mov     rdi, [rbp+240h+var_2C0]
0x18000af31  test    eax, eax
0x18000af33  jnz     loc_18000B063
0x18000af39  mov     r14b, r12b
0x18000af3c  mov     [rsp+340h+var_2F0], r12b
0x18000af41  mov     r13d, r12d
0x18000af44  cmp     [rsp+340h+var_2E4], r12d
0x18000af49  jbe     loc_18000B063
0x18000af4f  cmp     [rsp+340h+var_2EC], r12d
0x18000af54  jbe     loc_18000B055
0x18000af5a  mov     eax, r13d
0x18000af5d  mov     edx, r12d
0x18000af60  imul    r8, rax, 1Ch
0x18000af64  mov     ebx, [r8+r15+4]
0x18000af69  mov     eax, edx
0x18000af6b  imul    rcx, rax, 1Ch
0x18000af6f  cmp     ebx, [rcx+rsi+4]
0x18000af73  jnz     short loc_18000AF99
0x18000af75  mov     r11d, [r8+r15+8]
0x18000af7a  cmp     r11d, [rcx+rsi+8]
0x18000af7f  jnz     short loc_18000AF99
0x18000af81  mov     r10d, [r8+r15+0Ch]
0x18000af86  cmp     r10d, [rcx+rsi+0Ch]
0x18000af8b  jnz     short loc_18000AF99
0x18000af8d  mov     r9d, [r8+r15+10h]
0x18000af92  cmp     r9d, [rcx+rsi+10h]
0x18000af97  jz      short loc_18000AFA6
0x18000af99  inc     edx
0x18000af9b  cmp     edx, [rsp+340h+var_2EC]
0x18000af9f  jb      short loc_18000AF69
0x18000afa1  jmp     loc_18000B055
0x18000afa6  mov     r12d, [rcx+rsi]
0x18000afaa  test    rdi, rdi
0x18000afad  jz      short loc_18000B00B
0x18000afaf  xor     ecx, ecx
0x18000afb1  cmp     [rsp+340h+var_2E8], ecx
0x18000afb5  jbe     short loc_18000B00B
0x18000afb7  mov     eax, ecx
0x18000afb9  imul    r14, rax, 1Ch
0x18000afbd  cmp     ebx, [r14+rdi+4]
0x18000afc2  jnz     short loc_18000AFD9
0x18000afc4  cmp     r11d, [r14+rdi+8]
0x18000afc9  jnz     short loc_18000AFD9
0x18000afcb  cmp     r10d, [r14+rdi+0Ch]
0x18000afd0  jnz     short loc_18000AFD9
0x18000afd2  cmp     r9d, [r14+rdi+10h]
0x18000afd7  jz      short loc_18000AFE3
0x18000afd9  inc     ecx
0x18000afdb  cmp     ecx, [rsp+340h+var_2E8]
0x18000afdf  jb      short loc_18000AFB7
0x18000afe1  jmp     short loc_18000B006
0x18000afe3  mov     ecx, [r14+rdi]
0x18000afe7  lea     rdx, [rsp+340h+var_2E0]
0x18000afec  call    DiscpGetDSMPathCount
0x18000aff1  mov     ebx, eax
0x18000aff3  test    eax, eax
0x18000aff5  jnz     loc_18000B101
0x18000affb  cmp     [rsp+340h+var_2E0], 1
0x18000b000  ja      short loc_18000B006
0x18000b002  mov     r12d, [r14+rdi]
0x18000b006  mov     r14b, [rsp+340h+var_2F0]
0x18000b00b  mov     edx, r12d
0x18000b00e  lea     rcx, [rsp+340h+var_2D8]
0x18000b013  call    cs:__imp_DiscpGetPnpDeviceId
0x18000b019  test    eax, eax
0x18000b01b  jz      short loc_18000B026
0x18000b01d  mov     [rsp+340h+var_2D8], 0
0x18000b026  mov     r9d, 104h; ulNameLength
0x18000b02c  mov     [rsp+340h+ulFlags], 0; ulFlags
0x18000b034  lea     r8, [rbp+240h+pszVetoName]; pszVetoName
0x18000b038  mov     ecx, r12d; dnAncestor
0x18000b03b  lea     rdx, [rsp+340h+pVetoType]; pVetoType
0x18000b040  call    cs:__imp_CM_Query_And_Remove_SubTreeW
0x18000b046  xor     r12d, r12d
0x18000b049  test    eax, eax
0x18000b04b  jnz     short loc_18000B06B
0x18000b04d  mov     r14b, 1
0x18000b050  mov     [rsp+340h+var_2F0], r14b
0x18000b055  inc     r13d
0x18000b058  cmp     r13d, [rsp+340h+var_2E4]
0x18000b05d  jb      loc_18000AF4F
0x18000b063  mov     ebx, r12d
0x18000b066  jmp     loc_18000B101
0x18000b06b  mov     r9, [rbp+240h+var_2B8]
0x18000b06f  lea     r8, aI64xI64x; "%I64x-%I64x"
0x18000b076  mov     edx, 28h ; '('; cchDest
0x18000b07b  lea     rcx, [rbp+240h+pszDest]; pszDest
0x18000b07f  mov     rax, [r9+8]
0x18000b083  mov     r9, [r9]
0x18000b086  mov     qword ptr [rsp+340h+ulFlags], rax
0x18000b08b  call    StringCchPrintfW
0x18000b090  mov     rax, [rsp+340h+var_2D8]
0x18000b095  lea     rcx, [rbp+240h+pszVetoName]
0x18000b099  mov     [rsp+340h+var_300], rcx
0x18000b09e  lea     r8, dword_1800211CC
0x18000b0a5  test    rax, rax
0x18000b0a8  movzx   edx, r12w
0x18000b0ac  lea     rcx, [rbp+240h+pszDest]
0x18000b0b0  mov     r9d, 4
0x18000b0b6  mov     [rsp+340h+var_308], rcx
0x18000b0bb  cmovnz  r8, rax
0x18000b0bf  mov     [rsp+340h+var_310], r8
0x18000b0c4  lea     rcx, [rsp+340h+pVetoType]
0x18000b0c9  mov     [rsp+340h+var_318], 3
0x18000b0d0  mov     qword ptr [rsp+340h+ulFlags], rcx
0x18000b0d5  lea     ecx, [r9+70h]
0x18000b0d9  movzx   r8d, r12w
0x18000b0dd  call    cs:__imp_DiscpReportEventlog
0x18000b0e3  test    r14b, r14b
0x18000b0e6  jz      short loc_18000B0F1
0x18000b0e8  mov     rcx, [rbp+240h+var_2B0]
0x18000b0ec  call    DiscpRescanInitiator
0x18000b0f1  mov     r14d, 0EFFF0040h
0x18000b0f7  mov     ebx, r14d
0x18000b0fa  jmp     short loc_18000B107
0x18000b0fc  mov     rsi, [rsp+340h+var_2D0]
0x18000b101  mov     r14d, 0EFFF0040h
0x18000b107  test    r15, r15
0x18000b10a  jz      short loc_18000B115
0x18000b10c  mov     rcx, r15
0x18000b10f  call    cs:__imp_DiscpFreeMemory
0x18000b115  test    rsi, rsi
0x18000b118  jz      short loc_18000B123
0x18000b11a  mov     rcx, rsi
0x18000b11d  call    cs:__imp_DiscpFreeMemory
0x18000b123  test    rdi, rdi
0x18000b126  jz      short loc_18000B131
0x18000b128  mov     rcx, rdi
0x18000b12b  call    cs:__imp_DiscpFreeMemory
0x18000b131  mov     rcx, [rsp+340h+var_2D8]
0x18000b136  test    rcx, rcx
0x18000b139  jz      short loc_18000B141
0x18000b13b  call    cs:__imp_DiscpFreeMemory
0x18000b141  test    ebx, ebx
0x18000b143  cmovnz  ebx, r14d
0x18000b147  mov     eax, ebx
0x18000b149  mov     rcx, [rbp+240h+var_40]
0x18000b150  xor     rcx, rsp; StackCookie
0x18000b153  call    __security_check_cookie
0x18000b158  mov     rbx, [rsp+340h+arg_10]
0x18000b160  add     rsp, 310h
0x18000b167  pop     r15
0x18000b169  pop     r14
0x18000b16b  pop     r13
0x18000b16d  pop     r12
0x18000b16f  pop     rdi
0x18000b170  pop     rsi
0x18000b171  pop     rbp
0x18000b172  retn
```
