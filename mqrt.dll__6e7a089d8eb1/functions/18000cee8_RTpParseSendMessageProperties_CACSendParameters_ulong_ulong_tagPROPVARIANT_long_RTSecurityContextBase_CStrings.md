# RTpParseSendMessageProperties(CACSendParameters &,ulong,ulong *,tagPROPVARIANT *,long *,RTSecurityContextBase * *,CStringsToFree &,CStringsToFree &,ITransaction *)

- ea: `0x18000cee8`
- end: `0x18000d15e`
- name: `?RTpParseSendMessageProperties@@YAJAEAVCACSendParameters@@KPEAKPEAUtagPROPVARIANT@@PEAJPEAPEAVRTSecurityContextBase@@AEAVCStringsToFree@@5PEAUITransaction@@@Z`
- size: `630`
- prototype: `__int64 __fastcall(struct CACSendParameters *, unsigned int, unsigned int *, struct tagPROPVARIANT *, int *, struct RTSecurityContextBase **, struct CStringsToFree *, struct CStringsToFree *, struct ITransaction *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001bb44`

## callees

- `0x18000b054`
- `0x18000b080`
- `0x18000b298`
- `0x18000cee8`
- `0x180013c74`

## pseudocode

```c
__int64 __fastcall RTpParseSendMessageProperties(
        struct CACSendParameters *a1,
        int a2,
        unsigned int *a3,
        struct tagPROPVARIANT *a4,
        int *a5,
        struct RTSecurityContextBase **a6,
        struct CStringsToFree *a7,
        struct CStringsToFree *a8,
        struct ITransaction *a9)
{
  int v9; // r10d
  int v10; // r11d
  int v12; // eax
  int v14; // eax
  unsigned int v15; // edi
  unsigned __int16 v16; // r8
  unsigned int v17; // ebx
  __int64 v19; // rax
  unsigned int v20; // ecx
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // r8d
  char v24; // cl
  _BYTE *v25; // rax
  struct RTSecurityContextBase *v26; // [rsp+60h] [rbp-58h] BYREF
  int v27; // [rsp+68h] [rbp-50h]
  struct CACSendParameters *v28; // [rsp+70h] [rbp-48h]
  struct CStringsToFree *v29; // [rsp+78h] [rbp-40h]
  struct CStringsToFree *v30; // [rsp+80h] [rbp-38h]

  v29 = a7;
  v9 = (int)a4;
  v10 = (int)a3;
  v30 = a8;
  v12 = dword_18003C720;
  *a6 = 0;
  v27 = 1;
  v28 = a1;
  if ( v12 == 0xFFFF )
  {
    v12 = CalNumberOfMust(&MessageSendValidation, 76);
    dword_18003C720 = v12;
  }
  *((_DWORD *)a1 + 36) = -1;
  *((_DWORD *)a1 + 32) = g_dwTimeToReachQueueDefault;
  v14 = CheckProps(
          a2,
          v10,
          v9,
          (_DWORD)a5,
          0,
          75,
          (__int64)&MessageSendValidation,
          (__int64)&MessageVarTypes,
          1,
          v12,
          (__int64)&v26);
  v15 = v14;
  if ( v14 < 0 )
  {
    LogMsgHR(v14, (wchar_t *)L"rt/property", 0x2D6u);
    return v15;
  }
  if ( (*(_QWORD *)a1 || *((_QWORD *)a1 + 22) || *((_QWORD *)a1 + 37) || *((_QWORD *)a1 + 41) || *((_QWORD *)a1 + 32))
    && !*((_QWORD *)a1 + 49) )
  {
    v16 = 470;
    v17 = -1072824235;
LABEL_11:
    LogMsgHR(v17, (wchar_t *)L"rt/property", v16);
    return v17;
  }
  v19 = *((_QWORD *)a1 + 35);
  if ( *((_QWORD *)a1 + 32) )
  {
    if ( v19 )
      goto LABEL_14;
LABEL_20:
    v16 = 480;
LABEL_21:
    v17 = -1072824257;
    goto LABEL_11;
  }
  if ( v19 )
    goto LABEL_20;
LABEL_14:
  v20 = *((_DWORD *)a1 + 32);
  if ( v20 >= 0xFFFFFFFE )
  {
    *((_DWORD *)a1 + 32) = g_dwTimeToReachQueueDefault;
    v20 = g_dwTimeToReachQueueDefault;
  }
  v21 = *((_DWORD *)a1 + 36);
  if ( v21 != -1 )
  {
    if ( v20 <= v21 )
    {
      *((_DWORD *)a1 + 36) = v21 - v20;
    }
    else
    {
      *((_DWORD *)a1 + 32) = v21;
      *((_DWORD *)a1 + 36) = 0;
    }
  }
  v22 = MqSysTime();
  v23 = v22 + *((_DWORD *)a1 + 32);
  if ( v22 > v23 || (*((_DWORD *)a1 + 32) = v23, v23 > 0x7FFFFFFF) )
  {
    *((_DWORD *)a1 + 32) = 0x7FFFFFFF;
    *((_DWORD *)a1 + 36) = 0;
  }
  else if ( v23 + *((_DWORD *)a1 + 36) > 0x7FFFFFFF )
  {
    *((_DWORD *)a1 + 36) = 0x7FFFFFFF - v23;
  }
  v24 = v27;
  if ( (v27 & 2) != 0 )
    *a6 = v26;
  if ( (v24 & 0x14) == 0 )
  {
    *((_QWORD *)a1 + 75) = 0;
    *((_DWORD *)a1 + 152) = 0;
  }
  if ( (v24 & 8) == 0 )
  {
    *((_QWORD *)a1 + 73) = 0;
    *((_DWORD *)a1 + 148) = 0;
  }
  if ( !*((_QWORD *)a1 + 83) )
    return v15;
  v25 = (_BYTE *)*((_QWORD *)a1 + 8);
  if ( !v25 || (*v25 & 1) == 0 )
  {
    v16 = 9903;
    goto LABEL_21;
  }
  if ( !a9 )
  {
    v16 = 9904;
    v17 = -1072824314;
    goto LABEL_11;
  }
  return v15;
}

```

## disassembly

```asm
0x18000cee8  push    rbx
0x18000ceea  push    rbp
0x18000ceeb  push    rsi
0x18000ceec  push    rdi
0x18000ceed  push    r14
0x18000ceef  sub     rsp, 90h
0x18000cef6  mov     rax, [rsp+0B8h+arg_30]
0x18000cefe  lea     r14, ?MessageSendValidation@@3PAUpropValidity@@A; propValidity near * MessageSendValidation
0x18000cf05  mov     rsi, [rsp+0B8h+arg_28]
0x18000cf0d  xor     ebp, ebp
0x18000cf0f  mov     [rsp+0B8h+var_40], rax
0x18000cf14  mov     r10, r9
0x18000cf17  mov     rax, [rsp+0B8h+arg_38]
0x18000cf1f  mov     r11, r8
0x18000cf22  mov     [rsp+0B8h+var_38], rax
0x18000cf2a  mov     edi, edx
0x18000cf2c  mov     eax, cs:dword_18003C720
0x18000cf32  mov     rbx, rcx
0x18000cf35  mov     [rsi], rbp
0x18000cf38  mov     [rsp+0B8h+var_50], 1
0x18000cf40  mov     [rsp+0B8h+var_48], rcx
0x18000cf45  cmp     eax, 0FFFFh
0x18000cf4a  jnz     short loc_18000CF5D
0x18000cf4c  lea     edx, [rbp+4Ch]
0x18000cf4f  mov     rcx, r14
0x18000cf52  call    CalNumberOfMust
0x18000cf57  mov     cs:dword_18003C720, eax
0x18000cf5d  mov     r9, [rsp+0B8h+arg_20]
0x18000cf65  mov     r8, r10
0x18000cf68  mov     dword ptr [rbx+90h], 0FFFFFFFFh
0x18000cf72  mov     rdx, r11
0x18000cf75  mov     ecx, cs:?g_dwTimeToReachQueueDefault@@3KA; ulong g_dwTimeToReachQueueDefault
0x18000cf7b  mov     [rbx+80h], ecx
0x18000cf81  lea     rcx, [rsp+0B8h+var_58]
0x18000cf86  mov     [rsp+0B8h+var_68], rcx
0x18000cf8b  mov     ecx, edi
0x18000cf8d  mov     [rsp+0B8h+var_70], eax
0x18000cf91  lea     rax, ?MessageVarTypes@@3PAGA; ushort near * MessageVarTypes
0x18000cf98  mov     [rsp+0B8h+var_78], 1
0x18000cfa0  mov     [rsp+0B8h+var_80], rax
0x18000cfa5  mov     [rsp+0B8h+var_88], r14
0x18000cfaa  mov     [rsp+0B8h+var_90], 4Bh ; 'K'
0x18000cfb2  mov     [rsp+0B8h+var_98], ebp
0x18000cfb6  call    CheckProps
0x18000cfbb  mov     edi, eax
0x18000cfbd  test    eax, eax
0x18000cfbf  js      loc_18000D13A
0x18000cfc5  cmp     [rbx], rbp
0x18000cfc8  jnz     short loc_18000CFEE
0x18000cfca  cmp     [rbx+0B0h], rbp
0x18000cfd1  jnz     short loc_18000CFEE
0x18000cfd3  cmp     [rbx+128h], rbp
0x18000cfda  jnz     short loc_18000CFEE
0x18000cfdc  cmp     [rbx+148h], rbp
0x18000cfe3  jnz     short loc_18000CFEE
0x18000cfe5  cmp     [rbx+100h], rbp
0x18000cfec  jz      short loc_18000D017
0x18000cfee  cmp     [rbx+188h], rbp
0x18000cff5  jnz     short loc_18000D017
0x18000cff7  mov     r8d, 1D6h; unsigned __int16
0x18000cffd  mov     ebx, 0C00E0055h
0x18000d002  lea     rdx, aRtProperty; "rt/property"
0x18000d009  mov     ecx, ebx; int
0x18000d00b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000d010  mov     eax, ebx
0x18000d012  jmp     loc_18000D150
0x18000d017  mov     rax, [rbx+118h]
0x18000d01e  cmp     [rbx+100h], rbp
0x18000d025  jz      short loc_18000D066
0x18000d027  test    rax, rax
0x18000d02a  jz      short loc_18000D06B
0x18000d02c  mov     ecx, [rbx+80h]
0x18000d032  cmp     ecx, 0FFFFFFFEh
0x18000d035  jb      short loc_18000D049
0x18000d037  mov     eax, cs:?g_dwTimeToReachQueueDefault@@3KA; ulong g_dwTimeToReachQueueDefault
0x18000d03d  mov     [rbx+80h], eax
0x18000d043  mov     ecx, cs:?g_dwTimeToReachQueueDefault@@3KA; ulong g_dwTimeToReachQueueDefault
0x18000d049  mov     eax, [rbx+90h]
0x18000d04f  cmp     eax, 0FFFFFFFFh
0x18000d052  jz      short loc_18000D080
0x18000d054  cmp     ecx, eax
0x18000d056  jbe     short loc_18000D078
0x18000d058  mov     [rbx+80h], eax
0x18000d05e  mov     [rbx+90h], ebp
0x18000d064  jmp     short loc_18000D080
0x18000d066  test    rax, rax
0x18000d069  jz      short loc_18000D02C
0x18000d06b  mov     r8d, 1E0h
0x18000d071  mov     ebx, 0C00E003Fh
0x18000d076  jmp     short loc_18000D002
0x18000d078  sub     eax, ecx
0x18000d07a  mov     [rbx+90h], eax
0x18000d080  call    ?MqSysTime@@YAKXZ; MqSysTime(void)
0x18000d085  mov     r8d, [rbx+80h]
0x18000d08c  mov     edx, 7FFFFFFFh
0x18000d091  add     r8d, eax
0x18000d094  cmp     eax, r8d
0x18000d097  ja      short loc_18000D0BD
0x18000d099  mov     [rbx+80h], r8d
0x18000d0a0  cmp     r8d, edx
0x18000d0a3  ja      short loc_18000D0BD
0x18000d0a5  mov     ecx, [rbx+90h]
0x18000d0ab  add     ecx, r8d
0x18000d0ae  cmp     ecx, edx
0x18000d0b0  jbe     short loc_18000D0C9
0x18000d0b2  sub     edx, r8d
0x18000d0b5  mov     [rbx+90h], edx
0x18000d0bb  jmp     short loc_18000D0C9
0x18000d0bd  mov     [rbx+80h], edx
0x18000d0c3  mov     [rbx+90h], ebp
0x18000d0c9  mov     ecx, [rsp+0B8h+var_50]
0x18000d0cd  test    cl, 2
0x18000d0d0  jz      short loc_18000D0DA
0x18000d0d2  mov     rax, [rsp+0B8h+var_58]
0x18000d0d7  mov     [rsi], rax
0x18000d0da  test    cl, 14h
0x18000d0dd  jnz     short loc_18000D0EC
0x18000d0df  mov     [rbx+258h], rbp
0x18000d0e6  mov     [rbx+260h], ebp
0x18000d0ec  test    cl, 8
0x18000d0ef  jnz     short loc_18000D0FE
0x18000d0f1  mov     [rbx+248h], rbp
0x18000d0f8  mov     [rbx+250h], ebp
0x18000d0fe  cmp     [rbx+298h], rbp
0x18000d105  jz      short loc_18000D14E
0x18000d107  mov     rax, [rbx+40h]
0x18000d10b  test    rax, rax
0x18000d10e  jz      short loc_18000D12F
0x18000d110  test    byte ptr [rax], 1
0x18000d113  jz      short loc_18000D12F
0x18000d115  cmp     [rsp+0B8h+arg_40], rbp
0x18000d11d  jnz     short loc_18000D14E
0x18000d11f  mov     r8d, 26B0h
0x18000d125  mov     ebx, 0C00E0006h
0x18000d12a  jmp     loc_18000D002
0x18000d12f  mov     r8d, 26AFh
0x18000d135  jmp     loc_18000D071
0x18000d13a  mov     r8d, 2D6h; unsigned __int16
0x18000d140  lea     rdx, aRtProperty; "rt/property"
0x18000d147  mov     ecx, edi; int
0x18000d149  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000d14e  mov     eax, edi
0x18000d150  add     rsp, 90h
0x18000d157  pop     r14
0x18000d159  pop     rdi
0x18000d15a  pop     rsi
0x18000d15b  pop     rbp
0x18000d15c  pop     rbx
0x18000d15d  retn
```
