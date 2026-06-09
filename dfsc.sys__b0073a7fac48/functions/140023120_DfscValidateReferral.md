# DfscValidateReferral

- ea: `0x140023120`
- end: `0x1400233fe`
- name: `DfscValidateReferral`
- size: `734`
- prototype: `__int64 __fastcall(char *, int, _QWORD *)`
- caller_count: `4`
- callee_count: `13`
- tags: ``

## callers

- `0x140011010`
- `0x140011f60`
- `0x14001a630`
- `0x140023010`

## callees

- `0x140002340`
- `0x1400025f4`
- `0x140002fcc`
- `0x140003020`
- `0x140005fb0`
- `0x14001109c`
- `0x1400110d8`
- `0x140011f50`
- `0x140020d10`
- `0x14002184c`
- `0x1400219c0`
- `0x140023120`
- `0x140028680`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140023190`
- `ntoskrnl!KeBugCheckEx` at `0x140023190`

## pseudocode

```c
__int64 __fastcall DfscValidateReferral(char *a1, int a2, _QWORD *a3)
{
  _QWORD *v3; // r10
  int v5; // r15d
  __int64 (__fastcall **v7)(); // rbx
  __int64 v8; // rcx
  int v9; // eax
  int v10; // ebx
  int i; // eax
  _QWORD *v12; // rdi
  PVOID v13; // rdx
  __int16 v14; // ax
  int v15; // ecx
  __int64 v16; // rdx
  PVOID P[2]; // [rsp+30h] [rbp-30h] BYREF
  PVOID v19[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v20; // [rsp+50h] [rbp-10h]

  v3 = (_QWORD *)*a3;
  v20 = 0;
  v5 = a2;
  *(_OWORD *)P = 0;
  *(_OWORD *)v19 = 0;
  if ( a2 == -1 )
    v5 = *(_DWORD *)(v3[2] + 8LL);
  P[0] = a1;
  v19[1] = v3;
  if ( v5 )
  {
    if ( v5 == 1 )
    {
      if ( v3 )
      {
        if ( (v3[1] & 8) == 0 || (v8 = v3[2], (*(_BYTE *)(v8 + 12) & 8) == 0) || *(_BYTE *)(v8 + 14) )
        {
          if ( (unsigned __int8)DfscIsKnownDomainName(a1, a1 + 104) )
          {
            if ( (unsigned __int8)DfscIsSpecialShare(a1 + 120) )
            {
              v9 = DfscValidateSysvolNetlogonReferral(P[0], &v19[1], v19);
              v10 = v9;
              if ( v9 >= 0 )
              {
                HIDWORD(v20) = v9;
                goto LABEL_21;
              }
            }
          }
        }
      }
      v7 = DfscValidateRootStatesTable;
    }
    else
    {
      if ( v5 != 2 )
        KeBugCheckEx(0x10Bu, 2u, (ULONG_PTR)a3, v5, 0);
      v7 = DfscValidateLinkStatesTable;
    }
  }
  else
  {
    v7 = DfscValidateDomainStatesTable;
  }
  for ( i = 0; i != -1; i = ((__int64 (__fastcall *)(PVOID *))v7[i])(P) )
    ;
  v10 = HIDWORD(v20);
LABEL_21:
  v12 = (_QWORD *)*a3;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_26fa6a0d37ad369cda189c6e0c147b04_Traceguids, P, v10);
    }
    if ( v5 || v10 != -1073741790 )
    {
      if ( !v19[1] )
        goto LABEL_51;
      if ( (*((_DWORD *)v19[1] + 2) & 0xE) != 0 )
        goto LABEL_51;
      v15 = *((_DWORD *)P[0] + 58);
      if ( v15 )
      {
        v16 = *((_QWORD *)v19[1] + 2);
        if ( (*(_BYTE *)(v16 + 12) & 8) == 0 && (~*(_DWORD *)(v16 + 20) & v15) != 0 )
          goto LABEL_51;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u) )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_26fa6a0d37ad369cda189c6e0c147b04_Traceguids, v19[1], v10);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_26fa6a0d37ad369cda189c6e0c147b04_Traceguids, v12);
      }
      DfscReferralRelease(v12);
      *a3 = 0;
    }
    v10 = 0;
    goto LABEL_51;
  }
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u) )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_26fa6a0d37ad369cda189c6e0c147b04_Traceguids, *a3, v19[0]);
    }
    DfscCopyTargetAccessStatus(v12, v19[0]);
    DfscSetMatchingTarget(v12, v19[0]);
    DfscReferralRelease(v12);
  }
  v13 = v19[0];
  if ( (*(_BYTE *)(*((_QWORD *)v19[0] + 2) + 12LL) & 4) != 0 )
  {
    v14 = *((_WORD *)v19[0] + 12);
    if ( (v14 & 4) == 0 )
    {
      *((_WORD *)v19[0] + 12) = v14 | 1;
      v13 = v19[0];
    }
  }
  *a3 = v13;
  v19[0] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x16u) )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_26fa6a0d37ad369cda189c6e0c147b04_Traceguids, v12);
  }
LABEL_51:
  if ( P[1] )
    DfscReferralRelease(P[1]);
  if ( v19[0] )
    DfscReferralRelease(v19[0]);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140023120  push    rbp
0x140023122  push    rbx
0x140023123  push    rsi
0x140023124  push    rdi
0x140023125  push    r13
0x140023127  push    r14
0x140023129  push    r15
0x14002312b  mov     rbp, rsp
0x14002312e  sub     rsp, 60h
0x140023132  mov     r10, [r8]
0x140023135  xor     eax, eax
0x140023137  mov     [rbp+var_10], rax
0x14002313b  xorps   xmm0, xmm0
0x14002313e  mov     r13, r8
0x140023141  mov     r15d, edx
0x140023144  mov     rbx, rcx
0x140023147  movups  xmmword ptr [rbp+P], xmm0
0x14002314b  movups  xmmword ptr [rbp+var_20], xmm0
0x14002314f  cmp     edx, 0FFFFFFFFh
0x140023152  jnz     short loc_14002315C
0x140023154  mov     rax, [r10+10h]
0x140023158  mov     r15d, [rax+8]
0x14002315c  mov     [rbp+P], rbx
0x140023160  mov     ecx, r15d
0x140023163  mov     [rbp+var_20+8], r10
0x140023167  test    r15d, r15d
0x14002316a  jz      loc_140023205
0x140023170  sub     ecx, 1
0x140023173  jz      short loc_1400231A6
0x140023175  cmp     ecx, 1
0x140023178  jz      short loc_14002319D
0x14002317a  movsxd  r9, r15d; BugCheckParameter3
0x14002317d  mov     edx, 2; BugCheckParameter1
0x140023182  mov     ecx, 10Bh; BugCheckCode
0x140023187  mov     [rsp+60h+BugCheckParameter4], 0; BugCheckParameter4
0x140023190  call    cs:__imp_KeBugCheckEx
0x14002319d  lea     rbx, DfscValidateLinkStatesTable
0x1400231a4  jmp     short loc_14002320C
0x1400231a6  test    r10, r10
0x1400231a9  jz      short loc_1400231FC
0x1400231ab  mov     eax, [r10+8]
0x1400231af  test    al, 8
0x1400231b1  jz      short loc_1400231C3
0x1400231b3  mov     rcx, [r10+10h]
0x1400231b7  test    byte ptr [rcx+0Ch], 8
0x1400231bb  jz      short loc_1400231C3
0x1400231bd  cmp     byte ptr [rcx+0Eh], 0
0x1400231c1  jz      short loc_1400231FC
0x1400231c3  lea     rdx, [rbx+68h]
0x1400231c7  mov     rcx, rbx
0x1400231ca  call    DfscIsKnownDomainName
0x1400231cf  test    al, al
0x1400231d1  jz      short loc_1400231FC
0x1400231d3  lea     rcx, [rbx+78h]
0x1400231d7  call    DfscIsSpecialShare
0x1400231dc  test    al, al
0x1400231de  jz      short loc_1400231FC
0x1400231e0  mov     rcx, [rbp+P]
0x1400231e4  lea     r8, [rbp+var_20]
0x1400231e8  lea     rdx, [rbp+var_20+8]
0x1400231ec  call    DfscValidateSysvolNetlogonReferral
0x1400231f1  mov     ebx, eax
0x1400231f3  test    eax, eax
0x1400231f5  js      short loc_1400231FC
0x1400231f7  mov     dword ptr [rbp+var_10+4], eax
0x1400231fa  jmp     short loc_140023225
0x1400231fc  lea     rbx, DfscValidateRootStatesTable
0x140023203  jmp     short loc_14002320C
0x140023205  lea     rbx, DfscValidateDomainStatesTable
0x14002320c  xor     eax, eax
0x14002320e  cdqe
0x140023210  lea     rcx, [rbp+P]
0x140023214  mov     rax, (DfscValidateDomainStatesTable - 14000C020h)[rbx+rax*8]
0x140023218  call    _guard_dispatch_icall
0x14002321d  cmp     eax, 0FFFFFFFFh
0x140023220  jnz     short loc_14002320E
0x140023222  mov     ebx, dword ptr [rbp+var_10+4]
0x140023225  mov     rdi, [r13+0]
0x140023229  lea     r14, WPP_GLOBAL_Control
0x140023230  test    ebx, ebx
0x140023232  js      loc_1400232F7
0x140023238  test    rdi, rdi
0x14002323b  jz      short loc_140023291
0x14002323d  mov     rcx, cs:WPP_GLOBAL_Control
0x140023244  cmp     rcx, r14
0x140023247  jz      short loc_140023271
0x140023249  bt      dword ptr [rcx+2Ch], 16h
0x14002324e  jnb     short loc_140023271
0x140023250  mov     rax, [rbp+var_20]
0x140023254  lea     r8, WPP_26fa6a0d37ad369cda189c6e0c147b04_Traceguids
0x14002325b  mov     rcx, [rcx+18h]
0x14002325f  mov     edx, 0Bh
0x140023264  mov     r9, rdi
0x140023267  mov     [rsp+60h+BugCheckParameter4], rax
0x14002326c  call    WPP_SF_qq
0x140023271  mov     rdx, [rbp+var_20]
0x140023275  mov     rcx, rdi
0x140023278  call    DfscCopyTargetAccessStatus
0x14002327d  mov     rdx, [rbp+var_20]
0x140023281  mov     rcx, rdi
0x140023284  call    DfscSetMatchingTarget
0x140023289  mov     rcx, rdi; P
0x14002328c  call    DfscReferralRelease
0x140023291  mov     rdx, [rbp+var_20]
0x140023295  mov     rax, [rdx+10h]
0x140023299  test    byte ptr [rax+0Ch], 4
0x14002329d  jz      short loc_1400232B3
0x14002329f  movzx   eax, word ptr [rdx+18h]
0x1400232a3  test    al, 4
0x1400232a5  jnz     short loc_1400232B3
0x1400232a7  or      ax, 1
0x1400232ab  mov     [rdx+18h], ax
0x1400232af  mov     rdx, [rbp+var_20]
0x1400232b3  mov     [r13+0], rdx
0x1400232b7  mov     [rbp+var_20], 0
0x1400232bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400232c6  cmp     rcx, r14
0x1400232c9  jz      loc_1400233D0
0x1400232cf  bt      dword ptr [rcx+2Ch], 16h
0x1400232d4  jnb     loc_1400233D0
0x1400232da  mov     rcx, [rcx+18h]
0x1400232de  lea     r8, WPP_26fa6a0d37ad369cda189c6e0c147b04_Traceguids
0x1400232e5  mov     edx, 0Ch
0x1400232ea  mov     r9, rdi
0x1400232ed  call    WPP_SF_q
0x1400232f2  jmp     loc_1400233D0
0x1400232f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400232fe  cmp     rcx, r14
0x140023301  jz      short loc_140023327
0x140023303  bt      dword ptr [rcx+2Ch], 16h
0x140023308  jnb     short loc_140023327
0x14002330a  mov     rcx, [rcx+18h]
0x14002330e  lea     r9, [rbp+P]
0x140023312  mov     edx, 0Dh
0x140023317  mov     dword ptr [rsp+60h+BugCheckParameter4], ebx
0x14002331b  lea     r8, WPP_26fa6a0d37ad369cda189c6e0c147b04_Traceguids
0x140023322  call    WPP_SF_qD
0x140023327  test    r15d, r15d
0x14002332a  jnz     short loc_140023370
0x14002332c  cmp     ebx, 0C0000022h
0x140023332  jnz     short loc_140023370
0x140023334  mov     rcx, cs:WPP_GLOBAL_Control
0x14002333b  cmp     rcx, r14
0x14002333e  jz      short loc_14002335E
0x140023340  bt      dword ptr [rcx+2Ch], 16h
0x140023345  jnb     short loc_14002335E
0x140023347  mov     rcx, [rcx+18h]
0x14002334b  lea     edx, [r15+0Eh]
0x14002334f  mov     r9, rdi
0x140023352  lea     r8, WPP_26fa6a0d37ad369cda189c6e0c147b04_Traceguids
0x140023359  call    WPP_SF_q
0x14002335e  mov     rcx, rdi; P
0x140023361  call    DfscReferralRelease
0x140023366  mov     qword ptr [r13+0], 0
0x14002336e  jmp     short loc_1400233CE
0x140023370  mov     r9, [rbp+var_20+8]
0x140023374  test    r9, r9
0x140023377  jz      short loc_1400233D0
0x140023379  mov     eax, [r9+8]
0x14002337d  test    al, 0Eh
0x14002337f  jnz     short loc_1400233D0
0x140023381  mov     rax, [rbp+P]
0x140023385  mov     ecx, [rax+0E8h]
0x14002338b  test    ecx, ecx
0x14002338d  jz      short loc_1400233A2
0x14002338f  mov     rdx, [r9+10h]
0x140023393  test    byte ptr [rdx+0Ch], 8
0x140023397  jnz     short loc_1400233A2
0x140023399  mov     eax, [rdx+14h]
0x14002339c  not     eax
0x14002339e  test    ecx, eax
0x1400233a0  jnz     short loc_1400233D0
0x1400233a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400233a9  cmp     rcx, r14
0x1400233ac  jz      short loc_1400233CE
0x1400233ae  bt      dword ptr [rcx+2Ch], 16h
0x1400233b3  jnb     short loc_1400233CE
0x1400233b5  mov     rcx, [rcx+18h]
0x1400233b9  lea     r8, WPP_26fa6a0d37ad369cda189c6e0c147b04_Traceguids
0x1400233c0  mov     edx, 0Fh
0x1400233c5  mov     dword ptr [rsp+60h+BugCheckParameter4], ebx
0x1400233c9  call    WPP_SF_qD
0x1400233ce  xor     ebx, ebx
0x1400233d0  mov     rcx, [rbp+P+8]; P
0x1400233d4  test    rcx, rcx
0x1400233d7  jz      short loc_1400233DE
0x1400233d9  call    DfscReferralRelease
0x1400233de  mov     rcx, [rbp+var_20]; P
0x1400233e2  test    rcx, rcx
0x1400233e5  jz      short loc_1400233EC
0x1400233e7  call    DfscReferralRelease
0x1400233ec  mov     eax, ebx
0x1400233ee  add     rsp, 60h
0x1400233f2  pop     r15
0x1400233f4  pop     r14
0x1400233f6  pop     r13
0x1400233f8  pop     rdi
0x1400233f9  pop     rsi
0x1400233fa  pop     rbx
0x1400233fb  pop     rbp
0x1400233fc  retn
```
