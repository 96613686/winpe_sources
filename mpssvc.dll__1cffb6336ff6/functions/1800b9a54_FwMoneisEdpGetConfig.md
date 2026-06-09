# FwMoneisEdpGetConfig

- ea: `0x1800b9a54`
- end: `0x1800b9d63`
- name: `FwMoneisEdpGetConfig`
- size: `783`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800bcae0`

## callees

- `0x180006ce0`
- `0x18000af3c`
- `0x180017110`
- `0x1800b9a54`
- `0x1800ba0a4`
- `0x1800bac34`

## import_xrefs

- `fwbase!FwArrayCopy` at `0x1800b9b1f`
- `fwbase!FwArrayCopy` at `0x1800b9b81`
- `fwbase!FwArrayCopy` at `0x1800b9b1f`
- `fwbase!FwArrayCopy` at `0x1800b9b81`
- `fwbase!FwHResultToWindowsError` at `0x1800b9d5c`
- `fwbase!FwStringCopy` at `0x1800b9bc1`
- `fwbase!FwStringCopy` at `0x1800b9c13`
- `fwbase!FwStringCopy` at `0x1800b9bc1`
- `fwbase!FwStringCopy` at `0x1800b9c13`
- `fwbase!FwCriticalSectionLeave` at `0x1800b9cb2`
- `fwbase!FwCriticalSectionLeave` at `0x1800b9cb2`
- `fwbase!FwFree` at `0x1800b9bcc`
- `fwbase!FwFree` at `0x1800b9cfd`
- `fwbase!FwFree` at `0x1800b9d13`
- `fwbase!FwFree` at `0x1800b9bcc`
- `fwbase!FwFree` at `0x1800b9cfd`
- `fwbase!FwFree` at `0x1800b9d13`
- `FWPolicyIOMgr!FwDoNothingOnObject` at `0x1800b9b00`
- `FWPolicyIOMgr!FwDoNothingOnObject` at `0x1800b9b62`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800b9ccb`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800b9ce7`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800b9ccb`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800b9ce7`

## pseudocode

```c
__int64 __fastcall FwMoneisEdpGetConfig(
        unsigned int *a1,
        unsigned int *a2,
        int *a3,
        int *a4,
        _DWORD *a5,
        int *a6,
        _QWORD *a7,
        _QWORD *a8)
{
  int v12; // eax
  int v13; // ebx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  __int64 EnterpriseIdReference; // rax
  __int64 v19; // rdi
  int v20; // r9d
  int v21; // edx
  int v22; // r10d
  __int64 v23; // rcx
  __int64 v24; // rcx

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 146, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids);
  *a7 = 0;
  *a8 = 0;
  v12 = EdpFieldsLock();
  v13 = v12;
  if ( v12 >= 0 )
  {
    v14 = FwArrayCopy(8, FwDeepCopyCanonicalizedName, FwDoNothingOnObject, &dword_18012C7D8, a1);
    v13 = v14;
    if ( v14 >= 0 )
    {
      v14 = FwArrayCopy(8, FwDeepCopyCanonicalizedName, FwDoNothingOnObject, &dword_18012C7B0, a2);
      v13 = v14;
      if ( v14 >= 0 )
      {
        EnterpriseIdReference = FwMoneisGetEnterpriseIdReference();
        v19 = EnterpriseIdReference;
        if ( EnterpriseIdReference && (v13 = FwStringCopy(EnterpriseIdReference, a7), FwFree(v19), v13 < 0) )
        {
          v15 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v16 = 150;
            v17 = (unsigned int)v13;
            goto LABEL_13;
          }
        }
        else if ( qword_18012C778 && (v14 = FwStringCopy(qword_18012C778, a8), v13 = v14, v14 < 0) )
        {
          v15 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v16 = 151;
            goto LABEL_12;
          }
        }
        else
        {
          v20 = dword_18012C7C8;
          v21 = dword_18012C7E8;
          v22 = dword_18012C7FC;
          *a5 = dword_18012C7F8;
          *a3 = v20;
          *a4 = v21;
          *a6 = v22;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            WPP_SF_lDlD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL));
        }
      }
      else
      {
        v15 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v16 = 149;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v16 = 148;
LABEL_12:
        v17 = (unsigned int)v14;
LABEL_13:
        WPP_SF_d(*(_QWORD *)(v15 + 16), v16, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, v17);
      }
    }
    FwCriticalSectionLeave(qword_18012C740);
    if ( v13 >= 0 )
      goto LABEL_42;
    goto LABEL_32;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      147,
      WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids,
      (unsigned int)v12);
LABEL_32:
  if ( a1 )
  {
    v23 = *a1;
    if ( (_DWORD)v23 )
    {
      FwBinariesFree(v23, *((_QWORD *)a1 + 1));
      *(_OWORD *)a1 = 0;
    }
  }
  if ( a2 )
  {
    v24 = *a2;
    if ( (_DWORD)v24 )
    {
      FwBinariesFree(v24, *((_QWORD *)a2 + 1));
      *(_OWORD *)a2 = 0;
    }
  }
  if ( *a7 )
  {
    FwFree(*a7);
    *a7 = 0;
  }
  if ( *a8 )
  {
    FwFree(*a8);
    *a8 = 0;
  }
LABEL_42:
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      153,
      WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids,
      (unsigned int)v13);
  return FwHResultToWindowsError((unsigned int)v13);
}

```

## disassembly

```asm
0x1800b9a54  push    rbx
0x1800b9a56  push    rbp
0x1800b9a57  push    rsi
0x1800b9a58  push    rdi
0x1800b9a59  push    r12
0x1800b9a5b  push    r13
0x1800b9a5d  push    r14
0x1800b9a5f  push    r15
0x1800b9a61  sub     rsp, 48h
0x1800b9a65  mov     r12, r9
0x1800b9a68  mov     r13, r8
0x1800b9a6b  mov     r14, rdx
0x1800b9a6e  mov     rsi, rcx
0x1800b9a71  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9a78  lea     rdi, WPP_GLOBAL_Control
0x1800b9a7f  cmp     rcx, rdi
0x1800b9a82  jz      short loc_1800B9A9F
0x1800b9a84  test    byte ptr [rcx+1Ch], 8
0x1800b9a88  jz      short loc_1800B9A9F
0x1800b9a8a  mov     rcx, [rcx+10h]
0x1800b9a8e  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x1800b9a95  mov     edx, 92h
0x1800b9a9a  call    WPP_SF_
0x1800b9a9f  mov     rbp, [rsp+88h+arg_30]
0x1800b9aa7  mov     r15, [rsp+88h+arg_38]
0x1800b9aaf  mov     qword ptr [rbp+0], 0
0x1800b9ab7  mov     qword ptr [r15], 0
0x1800b9abe  call    EdpFieldsLock
0x1800b9ac3  mov     ebx, eax
0x1800b9ac5  test    eax, eax
0x1800b9ac7  jns     short loc_1800B9B00
0x1800b9ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9ad0  cmp     rcx, rdi
0x1800b9ad3  jz      loc_1800B9CBC
0x1800b9ad9  test    byte ptr [rcx+1Ch], 1
0x1800b9add  jz      loc_1800B9CBC
0x1800b9ae3  mov     rcx, [rcx+10h]
0x1800b9ae7  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x1800b9aee  mov     edx, 93h
0x1800b9af3  mov     r9d, eax
0x1800b9af6  call    WPP_SF_d
0x1800b9afb  jmp     loc_1800B9CBC
0x1800b9b00  mov     r8, cs:__imp_FwDoNothingOnObject
0x1800b9b07  lea     r9, dword_18012C7D8
0x1800b9b0e  lea     rdx, FwDeepCopyCanonicalizedName
0x1800b9b15  mov     [rsp+88h+var_68], rsi
0x1800b9b1a  mov     ecx, 8
0x1800b9b1f  call    cs:__imp_FwArrayCopy
0x1800b9b25  mov     ebx, eax
0x1800b9b27  test    eax, eax
0x1800b9b29  jns     short loc_1800B9B62
0x1800b9b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9b32  cmp     rcx, rdi
0x1800b9b35  jz      loc_1800B9CAB
0x1800b9b3b  test    byte ptr [rcx+1Ch], 1
0x1800b9b3f  jz      loc_1800B9CAB
0x1800b9b45  mov     edx, 94h
0x1800b9b4a  mov     r9d, eax
0x1800b9b4d  mov     rcx, [rcx+10h]
0x1800b9b51  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x1800b9b58  call    WPP_SF_d
0x1800b9b5d  jmp     loc_1800B9CAB
0x1800b9b62  mov     r8, cs:__imp_FwDoNothingOnObject
0x1800b9b69  lea     r9, dword_18012C7B0
0x1800b9b70  lea     rdx, FwDeepCopyCanonicalizedName
0x1800b9b77  mov     [rsp+88h+var_68], r14
0x1800b9b7c  mov     ecx, 8
0x1800b9b81  call    cs:__imp_FwArrayCopy
0x1800b9b87  mov     ebx, eax
0x1800b9b89  test    eax, eax
0x1800b9b8b  jns     short loc_1800B9BAE
0x1800b9b8d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9b94  cmp     rcx, rdi
0x1800b9b97  jz      loc_1800B9CAB
0x1800b9b9d  test    byte ptr [rcx+1Ch], 1
0x1800b9ba1  jz      loc_1800B9CAB
0x1800b9ba7  mov     edx, 95h
0x1800b9bac  jmp     short loc_1800B9B4A
0x1800b9bae  call    FwMoneisGetEnterpriseIdReference
0x1800b9bb3  mov     rdi, rax
0x1800b9bb6  test    rax, rax
0x1800b9bb9  jz      short loc_1800B9C04
0x1800b9bbb  mov     rdx, rbp
0x1800b9bbe  mov     rcx, rax
0x1800b9bc1  call    cs:__imp_FwStringCopy
0x1800b9bc7  mov     rcx, rdi
0x1800b9bca  mov     ebx, eax
0x1800b9bcc  call    cs:__imp_FwFree
0x1800b9bd2  test    ebx, ebx
0x1800b9bd4  jns     short loc_1800B9C04
0x1800b9bd6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9bdd  lea     rdi, WPP_GLOBAL_Control
0x1800b9be4  cmp     rcx, rdi
0x1800b9be7  jz      loc_1800B9CAB
0x1800b9bed  test    byte ptr [rcx+1Ch], 1
0x1800b9bf1  jz      loc_1800B9CAB
0x1800b9bf7  mov     edx, 96h
0x1800b9bfc  mov     r9d, ebx
0x1800b9bff  jmp     loc_1800B9B4D
0x1800b9c04  mov     rcx, cs:qword_18012C778
0x1800b9c0b  test    rcx, rcx
0x1800b9c0e  jz      short loc_1800B9C42
0x1800b9c10  mov     rdx, r15
0x1800b9c13  call    cs:__imp_FwStringCopy
0x1800b9c19  mov     ebx, eax
0x1800b9c1b  test    eax, eax
0x1800b9c1d  jns     short loc_1800B9C42
0x1800b9c1f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9c26  lea     rdi, WPP_GLOBAL_Control
0x1800b9c2d  cmp     rcx, rdi
0x1800b9c30  jz      short loc_1800B9CAB
0x1800b9c32  test    byte ptr [rcx+1Ch], 1
0x1800b9c36  jz      short loc_1800B9CAB
0x1800b9c38  mov     edx, 97h
0x1800b9c3d  jmp     loc_1800B9B4A
0x1800b9c42  mov     rax, [rsp+88h+arg_20]
0x1800b9c4a  mov     r8d, cs:dword_18012C7F8
0x1800b9c51  mov     r9d, cs:dword_18012C7C8
0x1800b9c58  mov     edx, cs:dword_18012C7E8
0x1800b9c5e  mov     r10d, cs:dword_18012C7FC
0x1800b9c65  mov     [rax], r8d
0x1800b9c68  mov     rax, [rsp+88h+arg_28]
0x1800b9c70  mov     [r13+0], r9d
0x1800b9c74  mov     [r12], edx
0x1800b9c78  mov     [rax], r10d
0x1800b9c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9c82  lea     rdi, WPP_GLOBAL_Control
0x1800b9c89  cmp     rcx, rdi
0x1800b9c8c  jz      short loc_1800B9CAB
0x1800b9c8e  test    byte ptr [rcx+1Ch], 4
0x1800b9c92  jz      short loc_1800B9CAB
0x1800b9c94  mov     rcx, [rcx+10h]
0x1800b9c98  mov     [rsp+88h+var_58], r10d
0x1800b9c9d  mov     [rsp+88h+var_60], r8d
0x1800b9ca2  mov     dword ptr [rsp+88h+var_68], edx
0x1800b9ca6  call    WPP_SF_lDlD
0x1800b9cab  lea     rcx, qword_18012C740
0x1800b9cb2  call    cs:__imp_FwCriticalSectionLeave
0x1800b9cb8  test    ebx, ebx
0x1800b9cba  jns     short loc_1800B9D20
0x1800b9cbc  test    rsi, rsi
0x1800b9cbf  jz      short loc_1800B9CD7
0x1800b9cc1  mov     ecx, [rsi]
0x1800b9cc3  test    ecx, ecx
0x1800b9cc5  jz      short loc_1800B9CD7
0x1800b9cc7  mov     rdx, [rsi+8]
0x1800b9ccb  call    cs:__imp_FwBinariesFree
0x1800b9cd1  xorps   xmm0, xmm0
0x1800b9cd4  movups  xmmword ptr [rsi], xmm0
0x1800b9cd7  test    r14, r14
0x1800b9cda  jz      short loc_1800B9CF4
0x1800b9cdc  mov     ecx, [r14]
0x1800b9cdf  test    ecx, ecx
0x1800b9ce1  jz      short loc_1800B9CF4
0x1800b9ce3  mov     rdx, [r14+8]
0x1800b9ce7  call    cs:__imp_FwBinariesFree
0x1800b9ced  xorps   xmm0, xmm0
0x1800b9cf0  movups  xmmword ptr [r14], xmm0
0x1800b9cf4  mov     rcx, [rbp+0]
0x1800b9cf8  test    rcx, rcx
0x1800b9cfb  jz      short loc_1800B9D0B
0x1800b9cfd  call    cs:__imp_FwFree
0x1800b9d03  mov     qword ptr [rbp+0], 0
0x1800b9d0b  mov     rcx, [r15]
0x1800b9d0e  test    rcx, rcx
0x1800b9d11  jz      short loc_1800B9D20
0x1800b9d13  call    cs:__imp_FwFree
0x1800b9d19  mov     qword ptr [r15], 0
0x1800b9d20  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9d27  cmp     rcx, rdi
0x1800b9d2a  jz      short loc_1800B9D4A
0x1800b9d2c  test    byte ptr [rcx+1Ch], 8
0x1800b9d30  jz      short loc_1800B9D4A
0x1800b9d32  mov     rcx, [rcx+10h]
0x1800b9d36  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x1800b9d3d  mov     edx, 99h
0x1800b9d42  mov     r9d, ebx
0x1800b9d45  call    WPP_SF_d
0x1800b9d4a  mov     ecx, ebx
0x1800b9d4c  add     rsp, 48h
0x1800b9d50  pop     r15
0x1800b9d52  pop     r14
0x1800b9d54  pop     r13
0x1800b9d56  pop     r12
0x1800b9d58  pop     rdi
0x1800b9d59  pop     rsi
0x1800b9d5a  pop     rbp
0x1800b9d5b  pop     rbx
0x1800b9d5c  jmp     cs:__imp_FwHResultToWindowsError
```
