# LipsFilterCondition5TupleCreate

- ea: `0x18004a854`
- end: `0x18004ae20`
- name: `LipsFilterCondition5TupleCreate`
- size: `1484`
- prototype: `__int64(__int16, __int64, __int64, __int64, __int64, char, __int16, ...)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18004b410`

## callees

- `0x180006f00`
- `0x18000c4d0`
- `0x18000e510`
- `0x18004a854`
- `0x18004ae28`
- `0x18004aec0`
- `0x18004b2ec`
- `0x18004b6f0`
- `0x18004b80c`
- `0x18004d05e`

## string_xrefs

- `0x18004adfd`: `LipsFilterCondition5TupleCreate`

## pseudocode

```c
__int64 LipsFilterCondition5TupleCreate(
        __int16 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char a6,
        __int16 a7,
        ...)
{
  unsigned int v10; // edi
  int v11; // esi
  unsigned int v12; // r13d
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  unsigned int v19; // r10d
  unsigned int v20; // r9d
  unsigned int v21; // r10d
  __int64 v22; // r11
  char v23; // r14
  SIZE_T v24; // r15
  void *v25; // rax
  _QWORD *v26; // rbx
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  int v29; // r12d
  char *v30; // r8
  char *v31; // r8
  __int64 v32; // rcx
  char *v33; // r9
  __int64 v34; // rcx
  char *v35; // r9
  __int64 v36; // rcx
  char v37; // al
  int v38; // eax
  __int64 v39; // rcx
  __int64 v40; // rcx
  GUID v41; // xmm0
  __int64 v42; // rcx
  unsigned int v44; // [rsp+20h] [rbp-38h]
  unsigned int v45; // [rsp+24h] [rbp-34h]
  unsigned int v46; // [rsp+28h] [rbp-30h]
  unsigned int v47; // [rsp+2Ch] [rbp-2Ch]
  unsigned int v48; // [rsp+30h] [rbp-28h]
  unsigned int v49; // [rsp+34h] [rbp-24h]
  int v50; // [rsp+38h] [rbp-20h]
  void *v51; // [rsp+40h] [rbp-18h] BYREF
  char v52; // [rsp+A0h] [rbp+48h]
  unsigned int v56; // [rsp+C8h] [rbp+70h]
  __int64 v57; // [rsp+D8h] [rbp+80h] BYREF
  va_list va; // [rsp+D8h] [rbp+80h]
  _QWORD *v59; // [rsp+E0h] [rbp+88h]
  int *v60; // [rsp+E8h] [rbp+90h]
  va_list va1; // [rsp+F0h] [rbp+98h] BYREF

  va_start(va1, a7);
  va_start(va, a7);
  v57 = va_arg(va1, _QWORD);
  v59 = va_arg(va1, _QWORD *);
  v60 = va_arg(va1, int *);
  v52 = a1;
  LODWORD(v57) = 0;
  v48 = 0xFFFF;
  *v59 = 0;
  v10 = 0;
  v11 = 0;
  *v60 = 0;
  if ( (unsigned int)LipsFilterIsNullAddressInfo(a2) )
  {
    v12 = 0xFFFF;
  }
  else
  {
    v11 = 1;
    LODWORD(v57) = 1;
    v12 = 0;
  }
  if ( (unsigned int)LipsFilterIsNullAddressInfo(a3) )
  {
    v44 = 0xFFFF;
  }
  else
  {
    v11 = v15 + 1;
    v44 = v15;
    LODWORD(v57) = v15 + 1;
    v15 = (unsigned int)(v15 + 1);
  }
  if ( (unsigned int)LipsFilterIsNullPort(a4, v13, v14, v15) )
  {
    v45 = v19;
  }
  else
  {
    v11 = v18 + 1;
    v45 = v18;
    LODWORD(v57) = v18 + 1;
    v18 = (unsigned int)(v18 + 1);
  }
  if ( (unsigned int)LipsFilterIsNullPort(a5, v16, v17, v18) )
  {
    v46 = v21;
  }
  else
  {
    v11 = v20 + 1;
    v46 = v20;
    LODWORD(v57) = ++v20;
  }
  v23 = a6;
  if ( a6 )
  {
    v11 = v20 + 1;
    v56 = v20;
    LODWORD(v57) = ++v20;
  }
  else
  {
    v56 = v21;
  }
  if ( a7 )
  {
    v11 = v20 + 1;
    v47 = v20;
    LODWORD(v57) = ++v20;
  }
  else
  {
    v47 = v21;
  }
  if ( (a1 & 0x100) != 0 )
  {
    v11 = v20 + 1;
    v49 = v20;
    LODWORD(v57) = ++v20;
  }
  else
  {
    v49 = v21;
  }
  if ( gcExemptMcastBcast && (a1 & 0x83) != 0 )
  {
    v11 = v20 + 1;
    v48 = v20;
    LODWORD(v57) = ++v20;
  }
  if ( v20 )
  {
    v50 = *(_DWORD *)(v22 + 4);
    v24 = 40LL * v20;
    v25 = IpsecAllocMem(v24);
    v51 = v25;
    v26 = v25;
    if ( !v25 )
    {
      v10 = 8;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_92;
      v28 = 21;
LABEL_30:
      WPP_SF_d(v27[2], v28, WPP_b2a5e40790a73c32bbd4ebb8c897c7db_Traceguids, v10);
LABEL_92:
      LipsFilterConditionDestroy(&v51, (__int64 *)va);
      return (unsigned int)LipsReportError(v10, "LipsFilterCondition5TupleCreate");
    }
    v29 = a1 & 2;
    memset_0(v25, 0, v24);
    if ( v12 != 0xFFFF )
    {
      v30 = (char *)&v26[5 * v12];
      if ( v29 )
      {
        v10 = LipsFilterConditionIpAddressFill(&FWPM_CONDITION_IP_LOCAL_ADDRESS, a2, v30);
        if ( v10 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            goto LABEL_92;
          }
          v28 = 22;
          goto LABEL_30;
        }
      }
      else
      {
        v10 = LipsFilterConditionIpAddressFill(&FWPM_CONDITION_IP_REMOTE_ADDRESS, a2, v30);
        if ( v10 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            goto LABEL_92;
          }
          v28 = 23;
          goto LABEL_30;
        }
      }
    }
    if ( v44 != 0xFFFF )
    {
      v31 = (char *)&v26[5 * v44];
      if ( v29 )
      {
        v10 = LipsFilterConditionIpAddressFill(&FWPM_CONDITION_IP_REMOTE_ADDRESS, a3, v31);
        if ( v10 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            goto LABEL_92;
          }
          v28 = 24;
          goto LABEL_30;
        }
      }
      else
      {
        v10 = LipsFilterConditionIpAddressFill(&FWPM_CONDITION_IP_LOCAL_ADDRESS, a3, v31);
        if ( v10 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            goto LABEL_92;
          }
          v28 = 25;
          goto LABEL_30;
        }
      }
    }
    if ( v45 != 0xFFFF )
    {
      v32 = 5LL * v45;
      v33 = (char *)&v26[5 * v45];
      if ( v29 )
      {
        v10 = LipsFilterConditionPortFill(v32, &FWPM_CONDITION_IP_LOCAL_PORT, a4, v33);
        if ( v10 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            goto LABEL_92;
          }
          v28 = 26;
          goto LABEL_30;
        }
      }
      else
      {
        v10 = LipsFilterConditionPortFill(v32, &FWPM_CONDITION_IP_REMOTE_PORT, a4, v33);
        if ( v10 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            goto LABEL_92;
          }
          v28 = 27;
          goto LABEL_30;
        }
      }
    }
    if ( v46 != 0xFFFF )
    {
      v34 = 5LL * v46;
      v35 = (char *)&v26[5 * v46];
      if ( v29 )
      {
        v10 = LipsFilterConditionPortFill(v34, &FWPM_CONDITION_IP_REMOTE_PORT, a5, v35);
        if ( v10 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            goto LABEL_92;
          }
          v28 = 28;
          goto LABEL_30;
        }
      }
      else
      {
        v10 = LipsFilterConditionPortFill(v34, &FWPM_CONDITION_IP_LOCAL_PORT, a5, v35);
        if ( v10 )
        {
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            goto LABEL_92;
          }
          v28 = 29;
          goto LABEL_30;
        }
      }
    }
    if ( v56 != 0xFFFF )
    {
      v36 = 5LL * v56;
      *(_OWORD *)&v26[v36] = 0;
      *(_OWORD *)&v26[v36 + 2] = 0;
      v26[v36 + 4] = 0;
      *(GUID *)&v26[v36] = FWPM_CONDITION_IP_PROTOCOL;
      if ( v23 )
      {
        if ( v50 )
        {
          if ( v23 == 1 )
            v23 = 58;
        }
        else
        {
          v37 = v23;
          if ( v23 == 58 )
            v37 = 1;
          v23 = v37;
        }
        v38 = 0;
      }
      else
      {
        v38 = 3;
      }
      LODWORD(v26[5 * v56 + 2]) = v38;
      LODWORD(v26[5 * v56 + 3]) = 1;
      LOBYTE(v26[5 * v56 + 4]) = v23;
    }
    if ( v47 != 0xFFFF )
    {
      v39 = 5LL * v47;
      *(_OWORD *)&v26[v39] = 0;
      *(_OWORD *)&v26[v39 + 2] = 0;
      v26[v39 + 4] = 0;
      LODWORD(v26[v39 + 3]) = 2;
      *(GUID *)&v26[v39] = FWPM_CONDITION_IP_LOCAL_PORT;
      LOWORD(v26[v39 + 4]) = a7;
    }
    if ( v48 != 0xFFFF )
    {
      v40 = 5LL * v48;
      *(_OWORD *)&v26[v40] = 0;
      *(_OWORD *)&v26[v40 + 2] = 0;
      v26[v40 + 4] = 0;
      if ( (v52 & 0x81) != 0 )
        v41 = FWPM_CONDITION_IP_LOCAL_ADDRESS_TYPE;
      else
        v41 = FWPM_CONDITION_IP_DESTINATION_ADDRESS_TYPE;
      *(GUID *)&v26[5 * v48] = v41;
      LODWORD(v26[5 * v48 + 3]) = 1;
      LOBYTE(v26[5 * v48 + 4]) = 1;
    }
    if ( v49 != 0xFFFF )
    {
      v42 = 5LL * v49;
      *(_OWORD *)&v26[v42] = 0;
      *(_OWORD *)&v26[v42 + 2] = 0;
      v26[v42 + 4] = 0;
      LODWORD(v26[v42 + 2]) = 1;
      LODWORD(v26[v42 + 3]) = 3;
      *(GUID *)&v26[v42] = FWPM_CONDITION_ALE_NAP_CONTEXT;
    }
    *v59 = v26;
    *v60 = v11;
  }
  return v10;
}

```

## disassembly

```asm
0x18004a854  mov     rax, rsp
0x18004a857  mov     [rax+20h], r9
0x18004a85b  mov     [rax+18h], r8
0x18004a85f  mov     [rax+10h], rdx
0x18004a863  mov     [rax+8], ecx
0x18004a866  push    rbp
0x18004a867  push    rbx
0x18004a868  push    rsi
0x18004a869  push    rdi
0x18004a86a  push    r12
0x18004a86c  push    r13
0x18004a86e  push    r14
0x18004a870  push    r15
0x18004a872  mov     rbp, rsp
0x18004a875  sub     rsp, 58h
0x18004a879  mov     rax, [rbp+arg_40]
0x18004a880  xor     r15d, r15d
0x18004a883  mov     r12d, ecx
0x18004a886  mov     dword ptr [rbp+arg_38], r15d
0x18004a88d  mov     rcx, rdx
0x18004a890  mov     [rbp+var_28], 0FFFFh
0x18004a897  mov     r14, r9
0x18004a89a  mov     rbx, r8
0x18004a89d  mov     [rax], r15
0x18004a8a0  mov     r11, rdx
0x18004a8a3  mov     rax, [rbp+arg_48]
0x18004a8aa  mov     edi, r15d
0x18004a8ad  mov     esi, r15d
0x18004a8b0  mov     [rax], r15d
0x18004a8b3  call    LipsFilterIsNullAddressInfo
0x18004a8b8  lea     ecx, [r15+1]
0x18004a8bc  test    eax, eax
0x18004a8be  jnz     short loc_18004A8D0
0x18004a8c0  mov     esi, ecx
0x18004a8c2  mov     dword ptr [rbp+arg_38], ecx
0x18004a8c8  mov     r13d, r15d
0x18004a8cb  mov     r9d, ecx
0x18004a8ce  jmp     short loc_18004A8D9
0x18004a8d0  mov     r13d, 0FFFFh
0x18004a8d6  mov     r9d, r15d
0x18004a8d9  mov     rcx, rbx
0x18004a8dc  call    LipsFilterIsNullAddressInfo
0x18004a8e1  mov     r10d, 0FFFFh
0x18004a8e7  test    eax, eax
0x18004a8e9  jnz     short loc_18004A8FE
0x18004a8eb  lea     esi, [r9+1]
0x18004a8ef  mov     [rbp+var_38], r9d
0x18004a8f3  mov     dword ptr [rbp+arg_38], esi
0x18004a8f9  mov     r9d, esi
0x18004a8fc  jmp     short loc_18004A902
0x18004a8fe  mov     [rbp+var_38], r10d
0x18004a902  mov     rcx, r14
0x18004a905  call    LipsFilterIsNullPort
0x18004a90a  test    eax, eax
0x18004a90c  jnz     short loc_18004A921
0x18004a90e  lea     esi, [r9+1]
0x18004a912  mov     [rbp+var_34], r9d
0x18004a916  mov     dword ptr [rbp+arg_38], esi
0x18004a91c  mov     r9d, esi
0x18004a91f  jmp     short loc_18004A925
0x18004a921  mov     [rbp+var_34], r10d
0x18004a925  mov     rcx, [rbp+arg_20]
0x18004a929  call    LipsFilterIsNullPort
0x18004a92e  test    eax, eax
0x18004a930  jnz     short loc_18004A945
0x18004a932  lea     esi, [r9+1]
0x18004a936  mov     [rbp+var_30], r9d
0x18004a93a  mov     dword ptr [rbp+arg_38], esi
0x18004a940  mov     r9d, esi
0x18004a943  jmp     short loc_18004A949
0x18004a945  mov     [rbp+var_30], r10d
0x18004a949  movzx   r14d, byte ptr [rbp+arg_28]
0x18004a94e  test    r14b, r14b
0x18004a951  jz      short loc_18004A966
0x18004a953  lea     esi, [r9+1]
0x18004a957  mov     [rbp+arg_28], r9d
0x18004a95b  mov     dword ptr [rbp+arg_38], esi
0x18004a961  mov     r9d, esi
0x18004a964  jmp     short loc_18004A96A
0x18004a966  mov     [rbp+arg_28], r10d
0x18004a96a  cmp     [rbp+arg_30], r15w
0x18004a96f  jz      short loc_18004A984
0x18004a971  lea     esi, [r9+1]
0x18004a975  mov     [rbp+var_2C], r9d
0x18004a979  mov     dword ptr [rbp+arg_38], esi
0x18004a97f  mov     r9d, esi
0x18004a982  jmp     short loc_18004A988
0x18004a984  mov     [rbp+var_2C], r10d
0x18004a988  bt      r12d, 8
0x18004a98d  jnb     short loc_18004A9A2
0x18004a98f  lea     esi, [r9+1]
0x18004a993  mov     [rbp+var_24], r9d
0x18004a997  mov     dword ptr [rbp+arg_38], esi
0x18004a99d  mov     r9d, esi
0x18004a9a0  jmp     short loc_18004A9A6
0x18004a9a2  mov     [rbp+var_24], r10d
0x18004a9a6  cmp     cs:gcExemptMcastBcast, r15d
0x18004a9ad  jz      short loc_18004A9C6
0x18004a9af  test    r12b, 83h
0x18004a9b3  jz      short loc_18004A9C6
0x18004a9b5  lea     esi, [r9+1]
0x18004a9b9  mov     [rbp+var_28], r9d
0x18004a9bd  mov     dword ptr [rbp+arg_38], esi
0x18004a9c3  mov     r9d, esi
0x18004a9c6  test    r9d, r9d
0x18004a9c9  jz      loc_18004AE0D
0x18004a9cf  mov     eax, [r11+4]
0x18004a9d3  mov     [rbp+var_20], eax
0x18004a9d6  mov     eax, r9d
0x18004a9d9  lea     r15, [rax+rax*4]
0x18004a9dd  shl     r15, 3
0x18004a9e1  mov     rcx, r15
0x18004a9e4  call    IpsecAllocMem
0x18004a9e9  mov     [rbp+var_18], rax
0x18004a9ed  mov     rbx, rax
0x18004a9f0  test    rax, rax
0x18004a9f3  jnz     short loc_18004AA34
0x18004a9f5  lea     edi, [rax+8]
0x18004a9f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a9ff  lea     rax, WPP_GLOBAL_Control
0x18004aa06  cmp     rcx, rax
0x18004aa09  jz      loc_18004ADED
0x18004aa0f  test    byte ptr [rcx+1Ch], 10h
0x18004aa13  jz      loc_18004ADED
0x18004aa19  lea     edx, [rbx+15h]
0x18004aa1c  mov     rcx, [rcx+10h]
0x18004aa20  lea     r8, WPP_b2a5e40790a73c32bbd4ebb8c897c7db_Traceguids
0x18004aa27  mov     r9d, edi
0x18004aa2a  call    WPP_SF_d
0x18004aa2f  jmp     loc_18004ADED
0x18004aa34  mov     r8, r15; Size
0x18004aa37  xor     edx, edx; Val
0x18004aa39  mov     rcx, rbx; void *
0x18004aa3c  and     r12d, 2
0x18004aa40  call    memset_0
0x18004aa45  xor     r15d, r15d
0x18004aa48  cmp     r13d, 0FFFFh
0x18004aa4f  jz      loc_18004AAE2
0x18004aa55  mov     rdx, [rbp+arg_8]
0x18004aa59  mov     eax, r13d
0x18004aa5c  lea     rcx, [rax+rax*4]
0x18004aa60  lea     r8, [rbx+rcx*8]
0x18004aa64  test    r12d, r12d
0x18004aa67  jz      short loc_18004AAA5
0x18004aa69  lea     rcx, FWPM_CONDITION_IP_LOCAL_ADDRESS
0x18004aa70  call    LipsFilterConditionIpAddressFill
0x18004aa75  mov     edi, eax
0x18004aa77  test    eax, eax
0x18004aa79  jz      short loc_18004AAE2
0x18004aa7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aa82  lea     rax, WPP_GLOBAL_Control
0x18004aa89  cmp     rcx, rax
0x18004aa8c  jz      loc_18004ADED
0x18004aa92  test    byte ptr [rcx+1Ch], 10h
0x18004aa96  jz      loc_18004ADED
0x18004aa9c  lea     edx, [r15+16h]
0x18004aaa0  jmp     loc_18004AA1C
0x18004aaa5  lea     rcx, FWPM_CONDITION_IP_REMOTE_ADDRESS
0x18004aaac  call    LipsFilterConditionIpAddressFill
0x18004aab1  mov     edi, eax
0x18004aab3  test    eax, eax
0x18004aab5  jz      short loc_18004AAE2
0x18004aab7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004aabe  lea     rax, WPP_GLOBAL_Control
0x18004aac5  cmp     rcx, rax
0x18004aac8  jz      loc_18004ADED
0x18004aace  test    byte ptr [rcx+1Ch], 10h
0x18004aad2  jz      loc_18004ADED
0x18004aad8  mov     edx, 17h
0x18004aadd  jmp     loc_18004AA1C
0x18004aae2  mov     eax, [rbp+var_38]
0x18004aae5  mov     r13d, 0FFFFh
0x18004aaeb  cmp     eax, r13d
0x18004aaee  jz      loc_18004AB7F
0x18004aaf4  lea     rdx, [rax+rax*4]
0x18004aaf8  lea     r8, [rbx+rdx*8]
0x18004aafc  mov     rdx, [rbp+arg_10]
0x18004ab00  test    r12d, r12d
0x18004ab03  jz      short loc_18004AB42
0x18004ab05  lea     rcx, FWPM_CONDITION_IP_REMOTE_ADDRESS
0x18004ab0c  call    LipsFilterConditionIpAddressFill
0x18004ab11  mov     edi, eax
0x18004ab13  test    eax, eax
0x18004ab15  jz      short loc_18004AB7F
0x18004ab17  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ab1e  lea     rax, WPP_GLOBAL_Control
0x18004ab25  cmp     rcx, rax
0x18004ab28  jz      loc_18004ADED
0x18004ab2e  test    byte ptr [rcx+1Ch], 10h
0x18004ab32  jz      loc_18004ADED
0x18004ab38  mov     edx, 18h
0x18004ab3d  jmp     loc_18004AA1C
0x18004ab42  lea     rcx, FWPM_CONDITION_IP_LOCAL_ADDRESS
0x18004ab49  call    LipsFilterConditionIpAddressFill
0x18004ab4e  mov     edi, eax
0x18004ab50  test    eax, eax
0x18004ab52  jz      short loc_18004AB7F
0x18004ab54  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ab5b  lea     rax, WPP_GLOBAL_Control
0x18004ab62  cmp     rcx, rax
0x18004ab65  jz      loc_18004ADED
0x18004ab6b  test    byte ptr [rcx+1Ch], 10h
0x18004ab6f  jz      loc_18004ADED
0x18004ab75  mov     edx, 19h
0x18004ab7a  jmp     loc_18004AA1C
0x18004ab7f  mov     eax, [rbp+var_34]
0x18004ab82  cmp     eax, r13d
0x18004ab85  jz      loc_18004AC16
0x18004ab8b  mov     r8, [rbp+arg_18]
0x18004ab8f  lea     rcx, [rax+rax*4]
0x18004ab93  lea     r9, [rbx+rcx*8]
0x18004ab97  test    r12d, r12d
0x18004ab9a  jz      short loc_18004ABD9
0x18004ab9c  lea     rdx, FWPM_CONDITION_IP_LOCAL_PORT
0x18004aba3  call    LipsFilterConditionPortFill
0x18004aba8  mov     edi, eax
0x18004abaa  test    eax, eax
0x18004abac  jz      short loc_18004AC16
0x18004abae  mov     rcx, cs:WPP_GLOBAL_Control
0x18004abb5  lea     rax, WPP_GLOBAL_Control
0x18004abbc  cmp     rcx, rax
0x18004abbf  jz      loc_18004ADED
0x18004abc5  test    byte ptr [rcx+1Ch], 10h
0x18004abc9  jz      loc_18004ADED
0x18004abcf  mov     edx, 1Ah
0x18004abd4  jmp     loc_18004AA1C
0x18004abd9  lea     rdx, FWPM_CONDITION_IP_REMOTE_PORT
0x18004abe0  call    LipsFilterConditionPortFill
0x18004abe5  mov     edi, eax
0x18004abe7  test    eax, eax
0x18004abe9  jz      short loc_18004AC16
0x18004abeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004abf2  lea     rax, WPP_GLOBAL_Control
0x18004abf9  cmp     rcx, rax
0x18004abfc  jz      loc_18004ADED
0x18004ac02  test    byte ptr [rcx+1Ch], 10h
0x18004ac06  jz      loc_18004ADED
0x18004ac0c  mov     edx, 1Bh
0x18004ac11  jmp     loc_18004AA1C
0x18004ac16  mov     eax, [rbp+var_30]
0x18004ac19  cmp     eax, r13d
0x18004ac1c  jz      loc_18004ACAD
0x18004ac22  mov     r8, [rbp+arg_20]
0x18004ac26  lea     rcx, [rax+rax*4]
0x18004ac2a  lea     r9, [rbx+rcx*8]
0x18004ac2e  test    r12d, r12d
0x18004ac31  jz      short loc_18004AC70
0x18004ac33  lea     rdx, FWPM_CONDITION_IP_REMOTE_PORT
0x18004ac3a  call    LipsFilterConditionPortFill
0x18004ac3f  mov     edi, eax
0x18004ac41  test    eax, eax
0x18004ac43  jz      short loc_18004ACAD
0x18004ac45  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ac4c  lea     rax, WPP_GLOBAL_Control
0x18004ac53  cmp     rcx, rax
0x18004ac56  jz      loc_18004ADED
0x18004ac5c  test    byte ptr [rcx+1Ch], 10h
0x18004ac60  jz      loc_18004ADED
0x18004ac66  mov     edx, 1Ch
0x18004ac6b  jmp     loc_18004AA1C
0x18004ac70  lea     rdx, FWPM_CONDITION_IP_LOCAL_PORT
0x18004ac77  call    LipsFilterConditionPortFill
0x18004ac7c  mov     edi, eax
0x18004ac7e  test    eax, eax
0x18004ac80  jz      short loc_18004ACAD
0x18004ac82  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ac89  lea     rax, WPP_GLOBAL_Control
0x18004ac90  cmp     rcx, rax
0x18004ac93  jz      loc_18004ADED
0x18004ac99  test    byte ptr [rcx+1Ch], 10h
0x18004ac9d  jz      loc_18004ADED
0x18004aca3  mov     edx, 1Dh
0x18004aca8  jmp     loc_18004AA1C
0x18004acad  mov     eax, [rbp+arg_28]
0x18004acb0  mov     r8d, 3
0x18004acb6  cmp     eax, r13d
0x18004acb9  jz      short loc_18004AD1F
0x18004acbb  lea     rcx, [rax+rax*4]
0x18004acbf  xorps   xmm0, xmm0
0x18004acc2  movups  xmmword ptr [rbx+rcx*8], xmm0
0x18004acc6  xor     eax, eax
0x18004acc8  movups  xmmword ptr [rbx+rcx*8+10h], xmm0
0x18004accd  mov     [rbx+rcx*8+20h], rax
0x18004acd2  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_PROTOCOL.Data1
0x18004acd9  movdqu  xmmword ptr [rbx+rcx*8], xmm0
0x18004acde  test    r14b, r14b
0x18004ace1  jz      short loc_18004AD08
0x18004ace3  lea     edx, [rax+1]
0x18004ace6  cmp     [rbp+var_20], r15d
0x18004acea  jz      short loc_18004ACF6
0x18004acec  cmp     r14b, dl
0x18004acef  jnz     short loc_18004AD03
0x18004acf1  mov     r14b, 3Ah ; ':'
0x18004acf4  jmp     short loc_18004AD03
0x18004acf6  cmp     r14b, 3Ah ; ':'
0x18004acfa  mov     eax, r14d
0x18004acfd  cmovz   eax, edx
0x18004ad00  mov     r14b, al
0x18004ad03  mov     eax, r15d
0x18004ad06  jmp     short loc_18004AD0B
  ... truncated ...
```
