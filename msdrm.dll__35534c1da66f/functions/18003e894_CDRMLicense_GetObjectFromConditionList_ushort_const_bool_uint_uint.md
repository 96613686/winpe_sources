# CDRMLicense::GetObjectFromConditionList(ushort const *,bool,uint *,uint)

- ea: `0x18003e894`
- end: `0x18003ea54`
- name: `?GetObjectFromConditionList@CDRMLicense@@AEAAJPEBG_NPEAII@Z`
- size: `448`
- prototype: `__int64 __usercall@<rax>(CDRMLicense *__hidden this@<rcx>, wchar_t *String1@<rdx>, bool@<r8b>, unsigned int *@<r9>, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18003db94`
- `0x18003dcb4`

## callees

- `0x180001284`
- `0x18003dfdc`
- `0x18003e894`
- `0x18003fde4`
- `0x180040a34`
- `0x1800411e8`
- `0x18005bd8a`

## string_xrefs

- `0x18003e8e2`: `access-condition`
- `0x18003e8f9`: `ACCESS`

## pseudocode

```c
__int64 __fastcall CDRMLicense::GetObjectFromConditionList(
        CDRMLicense *this,
        wchar_t *String1,
        char a3,
        unsigned int *a4,
        unsigned int a5)
{
  int ChildrenCount; // ebx
  CDRMXML *v10; // rcx
  const unsigned __int16 *v11; // rdx
  int v12; // eax
  int TimeCondition; // eax
  int OSExclusionCondition; // eax
  unsigned int v16[4]; // [rsp+20h] [rbp-10h] BYREF
  int v17; // [rsp+58h] [rbp+28h] BYREF
  bool v18; // [rsp+60h] [rbp+30h] BYREF

  v18 = 0;
  v17 = 0;
  v16[0] = 0;
  if ( a3 )
    *a4 = 0;
  if ( String1 )
  {
    if ( !wcscmp_0(String1, L"access-condition") )
    {
      v10 = (CDRMLicense *)((char *)this + 8);
      v11 = L"ACCESS";
      if ( a3 )
      {
LABEL_7:
        ChildrenCount = CDRMXML::GetChildrenCount(v10, v11, &v17);
        if ( ChildrenCount < 0 )
          goto LABEL_33;
        v12 = v17;
        goto LABEL_9;
      }
      ChildrenCount = CDRMXML::Child(v10, L"ACCESS", a5, &v18);
      if ( ChildrenCount < 0 )
        goto LABEL_33;
      if ( v18 )
      {
        *(_DWORD *)this = 6;
        goto LABEL_33;
      }
LABEL_10:
      ChildrenCount = -2147168490;
      goto LABEL_33;
    }
    if ( !wcscmp_0(String1, L"revocation-condition") )
    {
      v10 = (CDRMLicense *)((char *)this + 8);
      v11 = L"REFRESH";
      if ( a3 )
        goto LABEL_7;
      ChildrenCount = CDRMXML::Child(v10, L"REFRESH", a5, &v18);
      if ( ChildrenCount < 0 )
        goto LABEL_33;
      if ( v18 )
      {
        *(_DWORD *)this = 7;
        goto LABEL_33;
      }
      goto LABEL_10;
    }
    if ( !wcscmp_0(String1, L"rangetime-condition") || !wcscmp_0(String1, L"intervaltime-condition") )
    {
      if ( a3 )
      {
        TimeCondition = CDRMLicense::GetTimeCondition(this, String1, 0, v16);
        goto LABEL_29;
      }
      OSExclusionCondition = CDRMLicense::GetTimeCondition(this, String1, a5, 0);
    }
    else
    {
      if ( wcscmp_0(String1, L"os-exclusion-condition") )
      {
        ChildrenCount = -2147168494;
        goto LABEL_33;
      }
      if ( a3 )
      {
        TimeCondition = CDRMLicense::GetOSExclusionCondition(this, 0, v16);
LABEL_29:
        ChildrenCount = TimeCondition;
        if ( TimeCondition < 0 )
          goto LABEL_33;
        v12 = v16[0];
LABEL_9:
        if ( v12 )
        {
          *a4 = v12;
          goto LABEL_33;
        }
        goto LABEL_10;
      }
      OSExclusionCondition = CDRMLicense::GetOSExclusionCondition(this, a5, 0);
    }
    ChildrenCount = OSExclusionCondition;
    goto LABEL_33;
  }
  ChildrenCount = -2147024809;
LABEL_33:
  operator delete(0);
  return (unsigned int)ChildrenCount;
}

```

## disassembly

```asm
0x18003e894  mov     [rsp-18h+arg_0], rbx
0x18003e899  mov     [rsp-18h+arg_18], rsi
0x18003e89e  push    rbp
0x18003e89f  push    rdi
0x18003e8a0  push    r14
0x18003e8a2  mov     rbp, rsp
0x18003e8a5  sub     rsp, 30h
0x18003e8a9  mov     [rbp+arg_10], 0
0x18003e8ad  mov     rsi, r9
0x18003e8b0  mov     [rbp+arg_8], 0
0x18003e8b7  mov     r14b, r8b
0x18003e8ba  mov     [rbp+var_10], 0
0x18003e8c1  mov     rbx, rdx
0x18003e8c4  mov     rdi, rcx
0x18003e8c7  test    r8b, r8b
0x18003e8ca  jz      short loc_18003E8D3
0x18003e8cc  mov     dword ptr [r9], 0
0x18003e8d3  test    rbx, rbx
0x18003e8d6  jnz     short loc_18003E8E2
0x18003e8d8  mov     ebx, 80070057h
0x18003e8dd  jmp     loc_18003EA38
0x18003e8e2  lea     rdx, aAccessConditio; "access-condition"
0x18003e8e9  mov     rcx, rbx; String1
0x18003e8ec  call    wcscmp_0
0x18003e8f1  test    eax, eax
0x18003e8f3  jnz     short loc_18003E958
0x18003e8f5  lea     rcx, [rdi+8]; this
0x18003e8f9  lea     rdx, aAccess; "ACCESS"
0x18003e900  test    r14b, r14b
0x18003e903  jz      short loc_18003E930
0x18003e905  lea     r8, [rbp+arg_8]; int *
0x18003e909  call    ?GetChildrenCount@CDRMXML@@QEAAJPEBGPEAJ@Z; CDRMXML::GetChildrenCount(ushort const *,long *)
0x18003e90e  mov     ebx, eax
0x18003e910  test    eax, eax
0x18003e912  js      loc_18003EA38
0x18003e918  mov     eax, [rbp+arg_8]
0x18003e91b  test    eax, eax
0x18003e91d  jnz     short loc_18003E929
0x18003e91f  mov     ebx, 8004CF16h
0x18003e924  jmp     loc_18003EA38
0x18003e929  mov     [rsi], eax
0x18003e92b  jmp     loc_18003EA38
0x18003e930  mov     r8d, [rbp+arg_20]; int
0x18003e934  lea     r9, [rbp+arg_10]; bool *
0x18003e938  call    ?Child@CDRMXML@@QEAAJPEBGJPEA_N@Z; CDRMXML::Child(ushort const *,long,bool *)
0x18003e93d  mov     ebx, eax
0x18003e93f  test    eax, eax
0x18003e941  js      loc_18003EA38
0x18003e947  cmp     [rbp+arg_10], 0
0x18003e94b  jz      short loc_18003E91F
0x18003e94d  mov     dword ptr [rdi], 6
0x18003e953  jmp     loc_18003EA38
0x18003e958  lea     rdx, aRevocationCond; "revocation-condition"
0x18003e95f  mov     rcx, rbx; String1
0x18003e962  call    wcscmp_0
0x18003e967  test    eax, eax
0x18003e969  jnz     short loc_18003E9A3
0x18003e96b  lea     rcx, [rdi+8]; this
0x18003e96f  lea     rdx, aRefresh; "REFRESH"
0x18003e976  test    r14b, r14b
0x18003e979  jnz     short loc_18003E905
0x18003e97b  mov     r8d, [rbp+arg_20]; int
0x18003e97f  lea     r9, [rbp+arg_10]; bool *
0x18003e983  call    ?Child@CDRMXML@@QEAAJPEBGJPEA_N@Z; CDRMXML::Child(ushort const *,long,bool *)
0x18003e988  mov     ebx, eax
0x18003e98a  test    eax, eax
0x18003e98c  js      loc_18003EA38
0x18003e992  cmp     [rbp+arg_10], r14b
0x18003e996  jz      short loc_18003E91F
0x18003e998  mov     dword ptr [rdi], 7
0x18003e99e  jmp     loc_18003EA38
0x18003e9a3  lea     rdx, aRangetimeCondi; "rangetime-condition"
0x18003e9aa  mov     rcx, rbx; String1
0x18003e9ad  call    wcscmp_0
0x18003e9b2  test    eax, eax
0x18003e9b4  jz      short loc_18003EA05
0x18003e9b6  lea     rdx, aIntervaltimeCo; "intervaltime-condition"
0x18003e9bd  mov     rcx, rbx; String1
0x18003e9c0  call    wcscmp_0
0x18003e9c5  test    eax, eax
0x18003e9c7  jz      short loc_18003EA05
0x18003e9c9  lea     rdx, aOsExclusionCon; "os-exclusion-condition"
0x18003e9d0  mov     rcx, rbx; String1
0x18003e9d3  call    wcscmp_0
0x18003e9d8  test    eax, eax
0x18003e9da  jnz     short loc_18003E9FE
0x18003e9dc  mov     rcx, rdi; this
0x18003e9df  test    r14b, r14b
0x18003e9e2  jz      short loc_18003E9F1
0x18003e9e4  lea     r8, [rbp+var_10]; unsigned int *
0x18003e9e8  xor     edx, edx; unsigned int
0x18003e9ea  call    ?GetOSExclusionCondition@CDRMLicense@@AEAAJIPEAI@Z; CDRMLicense::GetOSExclusionCondition(uint,uint *)
0x18003e9ef  jmp     short loc_18003EA1C
0x18003e9f1  mov     edx, [rbp+arg_20]; unsigned int
0x18003e9f4  xor     r8d, r8d; unsigned int *
0x18003e9f7  call    ?GetOSExclusionCondition@CDRMLicense@@AEAAJIPEAI@Z; CDRMLicense::GetOSExclusionCondition(uint,uint *)
0x18003e9fc  jmp     short loc_18003EA36
0x18003e9fe  mov     ebx, 8004CF12h
0x18003ea03  jmp     short loc_18003EA38
0x18003ea05  mov     rdx, rbx; unsigned __int16 *
0x18003ea08  mov     rcx, rdi; this
0x18003ea0b  test    r14b, r14b
0x18003ea0e  jz      short loc_18003EA2A
0x18003ea10  lea     r9, [rbp+var_10]; unsigned int *
0x18003ea14  xor     r8d, r8d; unsigned int
0x18003ea17  call    ?GetTimeCondition@CDRMLicense@@AEAAJPEBGIPEAI@Z; CDRMLicense::GetTimeCondition(ushort const *,uint,uint *)
0x18003ea1c  mov     ebx, eax
0x18003ea1e  test    eax, eax
0x18003ea20  js      short loc_18003EA38
0x18003ea22  mov     eax, [rbp+var_10]
0x18003ea25  jmp     loc_18003E91B
0x18003ea2a  mov     r8d, [rbp+arg_20]; unsigned int
0x18003ea2e  xor     r9d, r9d; unsigned int *
0x18003ea31  call    ?GetTimeCondition@CDRMLicense@@AEAAJPEBGIPEAI@Z; CDRMLicense::GetTimeCondition(ushort const *,uint,uint *)
0x18003ea36  mov     ebx, eax
0x18003ea38  xor     ecx, ecx; Block
0x18003ea3a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003ea3f  mov     rsi, [rsp+30h+arg_18]
0x18003ea44  mov     eax, ebx
0x18003ea46  mov     rbx, [rsp+30h+arg_0]
0x18003ea4b  add     rsp, 30h
0x18003ea4f  pop     r14
0x18003ea51  pop     rdi
0x18003ea52  pop     rbp
0x18003ea53  retn
```
