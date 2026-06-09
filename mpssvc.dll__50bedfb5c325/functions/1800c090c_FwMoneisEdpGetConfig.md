# FwMoneisEdpGetConfig

- ea: `0x1800c090c`
- end: `0x1800c0c5c`
- name: `FwMoneisEdpGetConfig`
- size: `848`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800c3ea0`

## callees

- `0x18000a710`
- `0x1800192e0`
- `0x18002ad78`
- `0x1800c090c`
- `0x1800c0fd8`
- `0x1800c1c0c`

## import_xrefs

- `fwbase!FwArrayCopy` at `0x1800c09d7`
- `fwbase!FwArrayCopy` at `0x1800c0a3f`
- `fwbase!FwArrayCopy` at `0x1800c09d7`
- `fwbase!FwArrayCopy` at `0x1800c0a3f`
- `fwbase!FwHResultToWindowsError` at `0x1800c0c50`
- `fwbase!FwStringCopy` at `0x1800c0a85`
- `fwbase!FwStringCopy` at `0x1800c0ae3`
- `fwbase!FwStringCopy` at `0x1800c0a85`
- `fwbase!FwStringCopy` at `0x1800c0ae3`
- `fwbase!FwCriticalSectionLeave` at `0x1800c0b88`
- `fwbase!FwCriticalSectionLeave` at `0x1800c0b88`
- `fwbase!FwFree` at `0x1800c0a96`
- `fwbase!FwFree` at `0x1800c0be5`
- `fwbase!FwFree` at `0x1800c0c01`
- `fwbase!FwFree` at `0x1800c0a96`
- `fwbase!FwFree` at `0x1800c0be5`
- `fwbase!FwFree` at `0x1800c0c01`
- `FWPolicyIOMgr!FwDoNothingOnObject` at `0x1800c09b8`
- `FWPolicyIOMgr!FwDoNothingOnObject` at `0x1800c0a20`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800c0ba7`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800c0bc9`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800c0ba7`
- `FWPolicyIOMgr!FwBinariesFree` at `0x1800c0bc9`

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
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 146, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids);
  *a7 = 0;
  *a8 = 0;
  v12 = EdpFieldsLock();
  v13 = v12;
  if ( v12 >= 0 )
  {
    v14 = FwArrayCopy(8, FwDeepCopyCanonicalizedName, FwDoNothingOnObject, &dword_1801329A8, a1);
    v13 = v14;
    if ( v14 >= 0 )
    {
      v14 = FwArrayCopy(8, FwDeepCopyCanonicalizedName, FwDoNothingOnObject, &dword_180132980, a2);
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
        else if ( qword_180132948 && (v14 = FwStringCopy(qword_180132948, a8), v13 = v14, v14 < 0) )
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
          v20 = dword_180132998;
          v21 = dword_1801329B8;
          v22 = dword_1801329CC;
          *a5 = dword_1801329C8;
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
        WPP_SF_d(*(_QWORD *)(v15 + 16), v16, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids, v17);
      }
    }
    FwCriticalSectionLeave(qword_180132910);
    if ( v13 >= 0 )
      goto LABEL_42;
    goto LABEL_32;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      147,
      WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids,
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
      WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids,
      (unsigned int)v13);
  return FwHResultToWindowsError((unsigned int)v13);
}

```

## disassembly

```asm
0x1800c090c  push    rbx
0x1800c090e  push    rbp
0x1800c090f  push    rsi
0x1800c0910  push    rdi
0x1800c0911  push    r12
0x1800c0913  push    r13
0x1800c0915  push    r14
0x1800c0917  push    r15
0x1800c0919  sub     rsp, 48h
0x1800c091d  mov     r12, r9
0x1800c0920  mov     r13, r8
0x1800c0923  mov     r14, rdx
0x1800c0926  mov     rsi, rcx
0x1800c0929  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0930  lea     rdi, WPP_GLOBAL_Control
0x1800c0937  cmp     rcx, rdi
0x1800c093a  jz      short loc_1800C0957
0x1800c093c  test    byte ptr [rcx+1Ch], 8
0x1800c0940  jz      short loc_1800C0957
0x1800c0942  mov     rcx, [rcx+10h]
0x1800c0946  lea     r8, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids
0x1800c094d  mov     edx, 92h
0x1800c0952  call    WPP_SF_
0x1800c0957  mov     rbp, [rsp+88h+arg_30]
0x1800c095f  mov     r15, [rsp+88h+arg_38]
0x1800c0967  mov     qword ptr [rbp+0], 0
0x1800c096f  mov     qword ptr [r15], 0
0x1800c0976  call    EdpFieldsLock
0x1800c097b  mov     ebx, eax
0x1800c097d  test    eax, eax
0x1800c097f  jns     short loc_1800C09B8
0x1800c0981  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0988  cmp     rcx, rdi
0x1800c098b  jz      loc_1800C0B98
0x1800c0991  test    byte ptr [rcx+1Ch], 1
0x1800c0995  jz      loc_1800C0B98
0x1800c099b  mov     rcx, [rcx+10h]
0x1800c099f  lea     r8, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids
0x1800c09a6  mov     edx, 93h
0x1800c09ab  mov     r9d, eax
0x1800c09ae  call    WPP_SF_d
0x1800c09b3  jmp     loc_1800C0B98
0x1800c09b8  mov     r8, cs:__imp_FwDoNothingOnObject
0x1800c09bf  lea     r9, dword_1801329A8
0x1800c09c6  lea     rdx, FwDeepCopyCanonicalizedName
0x1800c09cd  mov     [rsp+88h+var_68], rsi
0x1800c09d2  mov     ecx, 8
0x1800c09d7  call    cs:__imp_FwArrayCopy
0x1800c09de  nop     dword ptr [rax+rax+00h]
0x1800c09e3  mov     ebx, eax
0x1800c09e5  test    eax, eax
0x1800c09e7  jns     short loc_1800C0A20
0x1800c09e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c09f0  cmp     rcx, rdi
0x1800c09f3  jz      loc_1800C0B81
0x1800c09f9  test    byte ptr [rcx+1Ch], 1
0x1800c09fd  jz      loc_1800C0B81
0x1800c0a03  mov     edx, 94h
0x1800c0a08  mov     r9d, eax
0x1800c0a0b  mov     rcx, [rcx+10h]
0x1800c0a0f  lea     r8, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids
0x1800c0a16  call    WPP_SF_d
0x1800c0a1b  jmp     loc_1800C0B81
0x1800c0a20  mov     r8, cs:__imp_FwDoNothingOnObject
0x1800c0a27  lea     r9, dword_180132980
0x1800c0a2e  lea     rdx, FwDeepCopyCanonicalizedName
0x1800c0a35  mov     [rsp+88h+var_68], r14
0x1800c0a3a  mov     ecx, 8
0x1800c0a3f  call    cs:__imp_FwArrayCopy
0x1800c0a46  nop     dword ptr [rax+rax+00h]
0x1800c0a4b  mov     ebx, eax
0x1800c0a4d  test    eax, eax
0x1800c0a4f  jns     short loc_1800C0A72
0x1800c0a51  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0a58  cmp     rcx, rdi
0x1800c0a5b  jz      loc_1800C0B81
0x1800c0a61  test    byte ptr [rcx+1Ch], 1
0x1800c0a65  jz      loc_1800C0B81
0x1800c0a6b  mov     edx, 95h
0x1800c0a70  jmp     short loc_1800C0A08
0x1800c0a72  call    FwMoneisGetEnterpriseIdReference
0x1800c0a77  mov     rdi, rax
0x1800c0a7a  test    rax, rax
0x1800c0a7d  jz      short loc_1800C0AD4
0x1800c0a7f  mov     rdx, rbp
0x1800c0a82  mov     rcx, rax
0x1800c0a85  call    cs:__imp_FwStringCopy
0x1800c0a8c  nop     dword ptr [rax+rax+00h]
0x1800c0a91  mov     rcx, rdi
0x1800c0a94  mov     ebx, eax
0x1800c0a96  call    cs:__imp_FwFree
0x1800c0a9d  nop     dword ptr [rax+rax+00h]
0x1800c0aa2  test    ebx, ebx
0x1800c0aa4  jns     short loc_1800C0AD4
0x1800c0aa6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0aad  lea     rdi, WPP_GLOBAL_Control
0x1800c0ab4  cmp     rcx, rdi
0x1800c0ab7  jz      loc_1800C0B81
0x1800c0abd  test    byte ptr [rcx+1Ch], 1
0x1800c0ac1  jz      loc_1800C0B81
0x1800c0ac7  mov     edx, 96h
0x1800c0acc  mov     r9d, ebx
0x1800c0acf  jmp     loc_1800C0A0B
0x1800c0ad4  mov     rcx, cs:qword_180132948
0x1800c0adb  test    rcx, rcx
0x1800c0ade  jz      short loc_1800C0B18
0x1800c0ae0  mov     rdx, r15
0x1800c0ae3  call    cs:__imp_FwStringCopy
0x1800c0aea  nop     dword ptr [rax+rax+00h]
0x1800c0aef  mov     ebx, eax
0x1800c0af1  test    eax, eax
0x1800c0af3  jns     short loc_1800C0B18
0x1800c0af5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0afc  lea     rdi, WPP_GLOBAL_Control
0x1800c0b03  cmp     rcx, rdi
0x1800c0b06  jz      short loc_1800C0B81
0x1800c0b08  test    byte ptr [rcx+1Ch], 1
0x1800c0b0c  jz      short loc_1800C0B81
0x1800c0b0e  mov     edx, 97h
0x1800c0b13  jmp     loc_1800C0A08
0x1800c0b18  mov     rax, [rsp+88h+arg_20]
0x1800c0b20  mov     r8d, cs:dword_1801329C8
0x1800c0b27  mov     r9d, cs:dword_180132998
0x1800c0b2e  mov     edx, cs:dword_1801329B8
0x1800c0b34  mov     r10d, cs:dword_1801329CC
0x1800c0b3b  mov     [rax], r8d
0x1800c0b3e  mov     rax, [rsp+88h+arg_28]
0x1800c0b46  mov     [r13+0], r9d
0x1800c0b4a  mov     [r12], edx
0x1800c0b4e  mov     [rax], r10d
0x1800c0b51  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0b58  lea     rdi, WPP_GLOBAL_Control
0x1800c0b5f  cmp     rcx, rdi
0x1800c0b62  jz      short loc_1800C0B81
0x1800c0b64  test    byte ptr [rcx+1Ch], 4
0x1800c0b68  jz      short loc_1800C0B81
0x1800c0b6a  mov     rcx, [rcx+10h]
0x1800c0b6e  mov     [rsp+88h+var_58], r10d
0x1800c0b73  mov     [rsp+88h+var_60], r8d
0x1800c0b78  mov     dword ptr [rsp+88h+var_68], edx
0x1800c0b7c  call    WPP_SF_lDlD
0x1800c0b81  lea     rcx, qword_180132910
0x1800c0b88  call    cs:__imp_FwCriticalSectionLeave
0x1800c0b8f  nop     dword ptr [rax+rax+00h]
0x1800c0b94  test    ebx, ebx
0x1800c0b96  jns     short loc_1800C0C14
0x1800c0b98  test    rsi, rsi
0x1800c0b9b  jz      short loc_1800C0BB9
0x1800c0b9d  mov     ecx, [rsi]
0x1800c0b9f  test    ecx, ecx
0x1800c0ba1  jz      short loc_1800C0BB9
0x1800c0ba3  mov     rdx, [rsi+8]
0x1800c0ba7  call    cs:__imp_FwBinariesFree
0x1800c0bae  nop     dword ptr [rax+rax+00h]
0x1800c0bb3  xorps   xmm0, xmm0
0x1800c0bb6  movups  xmmword ptr [rsi], xmm0
0x1800c0bb9  test    r14, r14
0x1800c0bbc  jz      short loc_1800C0BDC
0x1800c0bbe  mov     ecx, [r14]
0x1800c0bc1  test    ecx, ecx
0x1800c0bc3  jz      short loc_1800C0BDC
0x1800c0bc5  mov     rdx, [r14+8]
0x1800c0bc9  call    cs:__imp_FwBinariesFree
0x1800c0bd0  nop     dword ptr [rax+rax+00h]
0x1800c0bd5  xorps   xmm0, xmm0
0x1800c0bd8  movups  xmmword ptr [r14], xmm0
0x1800c0bdc  mov     rcx, [rbp+0]
0x1800c0be0  test    rcx, rcx
0x1800c0be3  jz      short loc_1800C0BF9
0x1800c0be5  call    cs:__imp_FwFree
0x1800c0bec  nop     dword ptr [rax+rax+00h]
0x1800c0bf1  mov     qword ptr [rbp+0], 0
0x1800c0bf9  mov     rcx, [r15]
0x1800c0bfc  test    rcx, rcx
0x1800c0bff  jz      short loc_1800C0C14
0x1800c0c01  call    cs:__imp_FwFree
0x1800c0c08  nop     dword ptr [rax+rax+00h]
0x1800c0c0d  mov     qword ptr [r15], 0
0x1800c0c14  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0c1b  cmp     rcx, rdi
0x1800c0c1e  jz      short loc_1800C0C3E
0x1800c0c20  test    byte ptr [rcx+1Ch], 8
0x1800c0c24  jz      short loc_1800C0C3E
0x1800c0c26  mov     rcx, [rcx+10h]
0x1800c0c2a  lea     r8, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids
0x1800c0c31  mov     edx, 99h
0x1800c0c36  mov     r9d, ebx
0x1800c0c39  call    WPP_SF_d
0x1800c0c3e  mov     ecx, ebx
0x1800c0c40  add     rsp, 48h
0x1800c0c44  pop     r15
0x1800c0c46  pop     r14
0x1800c0c48  pop     r13
0x1800c0c4a  pop     r12
0x1800c0c4c  pop     rdi
0x1800c0c4d  pop     rsi
0x1800c0c4e  pop     rbp
0x1800c0c4f  pop     rbx
0x1800c0c50  jmp     cs:__imp_FwHResultToWindowsError
```
