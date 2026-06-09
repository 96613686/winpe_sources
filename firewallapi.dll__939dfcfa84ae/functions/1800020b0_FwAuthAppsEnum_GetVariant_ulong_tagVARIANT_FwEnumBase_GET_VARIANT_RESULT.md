# FwAuthAppsEnum::GetVariant(ulong,tagVARIANT *,FwEnumBase::GET_VARIANT_RESULT *)

- ea: `0x1800020b0`
- end: `0x1800022b3`
- name: `?GetVariant@FwAuthAppsEnum@@EEAAJKPEAUtagVARIANT@@PEAW4GET_VARIANT_RESULT@FwEnumBase@@@Z`
- size: `515`
- prototype: `__int64 __fastcall(FwAuthAppsEnum *__hidden this, unsigned int, struct tagVARIANT *, enum FwEnumBase::GET_VARIANT_RESULT *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800020b0`
- `0x18000265c`
- `0x1800294b0`

## import_xrefs

- `fwbase!FwBaseFree` at `0x1800021a7`
- `fwbase!FwBaseFree` at `0x1800021a7`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x18000215a`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x18000215a`
- `fwbase!IsRuleOldAuthApp` at `0x1800021e6`
- `fwbase!IsRuleOldAuthApp` at `0x1800021e6`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180002113`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180002113`
- `fwbase!FwReportReturnError` at `0x180002245`
- `fwbase!FwReportReturnError` at `0x1800022a0`
- `fwbase!FwReportReturnError` at `0x180002245`
- `fwbase!FwReportReturnError` at `0x1800022a0`

## pseudocode

```c
__int64 __fastcall FwAuthAppsEnum::GetVariant(
        FwAuthAppsEnum *this,
        int a2,
        struct tagVARIANT *a3,
        enum FwEnumBase::GET_VARIANT_RESULT *a4)
{
  _WORD *v4; // r13
  int v5; // r15d
  _QWORD **v8; // rbx
  int *v10; // r14
  int v11; // ebp
  _QWORD *v12; // rcx
  int ExpandedCanonicalLongPathName; // eax
  int v14; // ebx
  _WORD *v16; // rdx
  int v17; // ecx
  LONGLONG v19; // [rsp+28h] [rbp-60h] BYREF
  __int64 v20; // [rsp+30h] [rbp-58h] BYREF
  int v21; // [rsp+38h] [rbp-50h] BYREF

  v4 = 0;
  v5 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v8 = (_QWORD **)((char *)this + 104);
  v10 = (int *)((char *)this + 112);
  if ( !a2 )
  {
    *v8 = (_QWORD *)*((_QWORD *)this + 11);
    *v10 = 0;
    *((_DWORD *)this + 29) = 0;
  }
  v11 = *v10;
  if ( (unsigned int)*v10 >= *((_DWORD *)this + 24) )
  {
LABEL_25:
    *(_DWORD *)a4 = 2;
    goto LABEL_13;
  }
  while ( 1 )
  {
    if ( (unsigned int)IsRuleOpenPortOrAuthApp(*v8) )
    {
      if ( (unsigned int)IsRuleOldAuthApp(*v8) )
      {
        v16 = *v8;
        if ( *((_WORD *)*v8 + 24) == 6 )
        {
          v17 = *((_DWORD *)this + 29);
          *((_DWORD *)this + 29) = v17 + 1;
          if ( a2 == v17 )
          {
            v4 = v16;
            v5 = 1;
          }
        }
      }
    }
    v12 = (_QWORD *)**v8;
    ++*v10;
    *v8 = v12;
    if ( v5 == 1 )
      break;
    if ( (unsigned int)++v11 >= *((_DWORD *)this + 24) )
      goto LABEL_25;
  }
  ExpandedCanonicalLongPathName = FwGetExpandedCanonicalLongPathName(*((_QWORD *)v4 + 34), &v20, &v21);
  v14 = ExpandedCanonicalLongPathName;
  if ( ExpandedCanonicalLongPathName < 0 )
    goto LABEL_21;
  if ( !v21 )
    *(_DWORD *)a4 = 1;
  ExpandedCanonicalLongPathName = FwAuthApp::CreateInstance(*((unsigned int *)this + 18), v20, &v19);
  v14 = ExpandedCanonicalLongPathName;
  if ( ExpandedCanonicalLongPathName == -2147024883 || ExpandedCanonicalLongPathName == -2147024894 )
  {
    *(_DWORD *)a4 = 1;
LABEL_13:
    v14 = 0;
    goto LABEL_14;
  }
  if ( ExpandedCanonicalLongPathName < 0 )
  {
LABEL_21:
    FwReportReturnError("FwAuthAppsEnum::GetVariant", (unsigned int)ExpandedCanonicalLongPathName);
    goto LABEL_14;
  }
  a3->llVal = v19;
  a3->vt = 9;
  *(_DWORD *)a4 = 0;
LABEL_14:
  FwBaseFree(v20);
  if ( v14 < 0 )
    return (unsigned int)FwReportReturnError("FwAuthAppsEnum::GetVariant", (unsigned int)v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800020b0  mov     r11, rsp
0x1800020b3  mov     [r11+10h], rbx
0x1800020b7  push    rbp
0x1800020b8  push    rsi
0x1800020b9  push    rdi
0x1800020ba  push    r12
0x1800020bc  push    r13
0x1800020be  push    r14
0x1800020c0  push    r15
0x1800020c2  sub     rsp, 50h
0x1800020c6  mov     rax, cs:__security_cookie
0x1800020cd  xor     rax, rsp
0x1800020d0  mov     [rsp+88h+var_48], rax
0x1800020d5  xor     r13d, r13d
0x1800020d8  mov     [rsp+88h+var_68], edx
0x1800020dc  xor     r15d, r15d
0x1800020df  mov     [r11-60h], r13
0x1800020e3  mov     [r11-58h], r13
0x1800020e7  mov     rsi, r9
0x1800020ea  mov     [r11-50h], r13d
0x1800020ee  mov     r12, r8
0x1800020f1  lea     rbx, [rcx+68h]
0x1800020f5  mov     rdi, rcx
0x1800020f8  lea     r14, [rcx+70h]
0x1800020fc  test    edx, edx
0x1800020fe  jz      loc_180002229
0x180002104  mov     ebp, [r14]
0x180002107  cmp     ebp, [rcx+60h]
0x18000210a  jnb     loc_18000228C
0x180002110  mov     rcx, [rbx]
0x180002113  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x18000211a  nop     dword ptr [rax+rax+00h]
0x18000211f  test    eax, eax
0x180002121  jnz     loc_1800021E3
0x180002127  mov     rax, [rbx]
0x18000212a  mov     rcx, [rax]
0x18000212d  inc     dword ptr [r14]
0x180002130  mov     [rbx], rcx
0x180002133  cmp     r15d, 1
0x180002137  jz      short loc_180002149
0x180002139  inc     ebp
0x18000213b  cmp     ebp, [rdi+60h]
0x18000213e  jb      short loc_180002110
0x180002140  test    r15d, r15d
0x180002143  jz      loc_18000228C
0x180002149  mov     rcx, [r13+110h]
0x180002150  lea     r8, [rsp+88h+var_50]
0x180002155  lea     rdx, [rsp+88h+var_58]
0x18000215a  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x180002161  nop     dword ptr [rax+rax+00h]
0x180002166  mov     ebx, eax
0x180002168  test    eax, eax
0x18000216a  js      loc_18000223C
0x180002170  cmp     [rsp+88h+var_50], 0
0x180002175  jz      loc_180002256
0x18000217b  mov     rdx, [rsp+88h+var_58]
0x180002180  lea     r8, [rsp+88h+var_60]
0x180002185  mov     ecx, [rdi+48h]
0x180002188  call    ?CreateInstance@FwAuthApp@@SAJW4_tag_FW_PROFILE_TYPE@@PEBGPEAPEAV1@@Z; FwAuthApp::CreateInstance(_tag_FW_PROFILE_TYPE,ushort const *,FwAuthApp * *)
0x18000218d  mov     ebx, eax
0x18000218f  cmp     eax, 8007000Dh
0x180002194  jnz     loc_180002261
0x18000219a  mov     dword ptr [rsi], 1
0x1800021a0  xor     ebx, ebx
0x1800021a2  mov     rcx, [rsp+88h+var_58]
0x1800021a7  call    cs:__imp_FwBaseFree
0x1800021ae  nop     dword ptr [rax+rax+00h]
0x1800021b3  test    ebx, ebx
0x1800021b5  js      loc_180002297
0x1800021bb  mov     eax, ebx
0x1800021bd  mov     rcx, [rsp+88h+var_48]
0x1800021c2  xor     rcx, rsp; StackCookie
0x1800021c5  call    __security_check_cookie
0x1800021ca  mov     rbx, [rsp+88h+arg_8]
0x1800021d2  add     rsp, 50h
0x1800021d6  pop     r15
0x1800021d8  pop     r14
0x1800021da  pop     r13
0x1800021dc  pop     r12
0x1800021de  pop     rdi
0x1800021df  pop     rsi
0x1800021e0  pop     rbp
0x1800021e1  retn
0x1800021e3  mov     rcx, [rbx]
0x1800021e6  call    cs:__imp_IsRuleOldAuthApp
0x1800021ed  nop     dword ptr [rax+rax+00h]
0x1800021f2  test    eax, eax
0x1800021f4  jz      loc_180002127
0x1800021fa  mov     rdx, [rbx]
0x1800021fd  cmp     word ptr [rdx+30h], 6
0x180002202  jnz     loc_180002127
0x180002208  mov     ecx, [rdi+74h]
0x18000220b  lea     eax, [rcx+1]
0x18000220e  mov     [rdi+74h], eax
0x180002211  cmp     [rsp+88h+var_68], ecx
0x180002215  jnz     loc_180002127
0x18000221b  mov     r13, rdx
0x18000221e  mov     r15d, 1
0x180002224  jmp     loc_180002127
0x180002229  mov     rax, [rcx+58h]
0x18000222d  mov     [rbx], rax
0x180002230  mov     [r14], r13d
0x180002233  mov     [rcx+74h], r13d
0x180002237  jmp     loc_180002104
0x18000223c  mov     edx, eax
0x18000223e  lea     rcx, aFwauthappsenum_1; "FwAuthAppsEnum::GetVariant"
0x180002245  call    cs:__imp_FwReportReturnError
0x18000224c  nop     dword ptr [rax+rax+00h]
0x180002251  jmp     loc_1800021A2
0x180002256  mov     dword ptr [rsi], 1
0x18000225c  jmp     loc_18000217B
0x180002261  cmp     eax, 80070002h
0x180002266  jz      loc_18000219A
0x18000226c  test    eax, eax
0x18000226e  js      short loc_18000223C
0x180002270  mov     rax, [rsp+88h+var_60]
0x180002275  mov     [r12+8], rax
0x18000227a  mov     word ptr [r12], 9
0x180002281  mov     dword ptr [rsi], 0
0x180002287  jmp     loc_1800021A2
0x18000228c  mov     dword ptr [rsi], 2
0x180002292  jmp     loc_1800021A0
0x180002297  mov     edx, ebx
0x180002299  lea     rcx, aFwauthappsenum_1; "FwAuthAppsEnum::GetVariant"
0x1800022a0  call    cs:__imp_FwReportReturnError
0x1800022a7  nop     dword ptr [rax+rax+00h]
0x1800022ac  mov     ebx, eax
0x1800022ae  jmp     loc_1800021BB
```
