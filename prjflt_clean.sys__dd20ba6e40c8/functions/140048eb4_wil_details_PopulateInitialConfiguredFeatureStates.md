# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140048eb4`
- end: `0x140049033`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140048d4c`

## callees

- `0x14000ba20`
- `0x140048eb4`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140048f30`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140048f30`

## pseudocode

```c
void wil_details_PopulateInitialConfiguredFeatureStates()
{
  _QWORD *i; // rbx
  int v1; // eax
  __int64 *v2; // rcx
  _QWORD *v3; // rcx
  __int64 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+28h] [rbp-20h] BYREF
  int v6; // [rsp+30h] [rbp-18h]

  for ( i = wil_details_featureDescriptors_a; ; ++i )
  {
    if ( i >= wil_details_featureDescriptors_a )
      return;
    if ( *i )
      break;
  }
LABEL_20:
  if ( !i )
    return;
  v5 = 0;
  v6 = 0;
  v4 = 0;
  if ( *((_BYTE *)i + 29) || *((_BYTE *)i + 30) )
    goto LABEL_14;
  v1 = ((__int64 (__fastcall *)(_QWORD, bool, __int64 *, __int64 *))RtlQueryFeatureConfiguration)(
         *((unsigned int *)i + 6),
         (unsigned __int8)(*((_BYTE *)i + 28) - 2) > 1u,
         &v4,
         &v5);
  if ( v1 != -2147483614 )
  {
    if ( v1 != -1073741275 )
    {
      if ( !v1 )
      {
        v4 = (8 * (BYTE4(v5) & 0xB0 | (4 * (BYTE4(v5) & 0x40u)))) | 0x206LL;
        goto LABEL_15;
      }
      if ( v1 == 279 )
      {
        v4 = (8 * (BYTE4(v5) & 0x80u)) | 0x206LL;
        goto LABEL_15;
      }
    }
LABEL_14:
    v4 = 518;
LABEL_15:
    v2 = (__int64 *)*i;
    i += 7;
    *v2 = v4;
    while ( i < wil_details_featureDescriptors_a )
    {
      if ( *i )
        goto LABEL_20;
      ++i;
    }
    return;
  }
  v4 = 518;
LABEL_23:
  v3 = (_QWORD *)*i;
  i += 7;
  *v3 = 518;
  while ( i < wil_details_featureDescriptors_a )
  {
    if ( *i )
    {
      if ( i )
        goto LABEL_23;
      return;
    }
    ++i;
  }
}

```

## disassembly

```asm
0x140048eb4  mov     [rsp+arg_0], rbx
0x140048eb9  push    rsi
0x140048eba  sub     rsp, 40h
0x140048ebe  mov     rax, cs:__security_cookie
0x140048ec5  xor     rax, rsp
0x140048ec8  mov     [rsp+48h+var_10], rax
0x140048ecd  lea     rbx, wil_details_featureDescriptors_a
0x140048ed4  lea     rsi, wil_details_featureDescriptors_a
0x140048edb  jmp     short loc_140048EEB
0x140048edd  cmp     qword ptr [rbx], 0
0x140048ee1  jnz     loc_140048FD7
0x140048ee7  add     rbx, 8
0x140048eeb  cmp     rbx, rsi
0x140048eee  jb      short loc_140048EDD
0x140048ef0  jmp     loc_14004901A
0x140048ef5  xor     eax, eax
0x140048ef7  mov     [rsp+48h+var_20], rax
0x140048efc  mov     [rsp+48h+var_18], eax
0x140048f00  mov     [rsp+48h+var_28], rax
0x140048f05  cmp     [rbx+1Dh], al
0x140048f08  jnz     loc_140048FA4
0x140048f0e  cmp     [rbx+1Eh], al
0x140048f11  jnz     loc_140048FA4
0x140048f17  mov     al, [rbx+1Ch]
0x140048f1a  lea     r9, [rsp+48h+var_20]
0x140048f1f  mov     ecx, [rbx+18h]
0x140048f22  lea     r8, [rsp+48h+var_28]
0x140048f27  xor     edx, edx
0x140048f29  sub     al, 2
0x140048f2b  cmp     al, 1
0x140048f2d  setnbe  dl
0x140048f30  call    cs:__imp_RtlQueryFeatureConfiguration
0x140048f37  nop     dword ptr [rax+rax+00h]
0x140048f3c  cmp     eax, 80000022h
0x140048f41  jz      loc_140048FE2
0x140048f47  cmp     eax, 0C0000225h
0x140048f4c  jz      short loc_140048FA4
0x140048f4e  test    eax, eax
0x140048f50  jz      short loc_140048F79
0x140048f52  cmp     eax, 117h
0x140048f57  jnz     short loc_140048FA4
0x140048f59  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140048f5d  and     eax, 80h
0x140048f62  mov     [rsp+48h+var_28], 0
0x140048f6b  shl     eax, 3
0x140048f6e  or      eax, 206h
0x140048f73  mov     dword ptr [rsp+48h+var_28], eax
0x140048f77  jmp     short loc_140048FB5
0x140048f79  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140048f7d  mov     ecx, eax
0x140048f7f  and     ecx, 40h
0x140048f82  mov     [rsp+48h+var_28], 0
0x140048f8b  shl     ecx, 2
0x140048f8e  and     eax, 0B0h
0x140048f93  or      ecx, eax
0x140048f95  shl     ecx, 3
0x140048f98  or      ecx, 206h
0x140048f9e  mov     dword ptr [rsp+48h+var_28], ecx
0x140048fa2  jmp     short loc_140048FB5
0x140048fa4  mov     [rsp+48h+var_28], 0
0x140048fad  mov     dword ptr [rsp+48h+var_28], 206h
0x140048fb5  mov     rcx, [rbx]
0x140048fb8  add     rbx, 38h ; '8'
0x140048fbc  mov     rax, [rsp+48h+var_28]
0x140048fc1  mov     [rcx], rax
0x140048fc4  jmp     short loc_140048FD0
0x140048fc6  cmp     qword ptr [rbx], 0
0x140048fca  jnz     short loc_140048FD7
0x140048fcc  add     rbx, 8
0x140048fd0  cmp     rbx, rsi
0x140048fd3  jb      short loc_140048FC6
0x140048fd5  jmp     short loc_14004901A
0x140048fd7  test    rbx, rbx
0x140048fda  jnz     loc_140048EF5
0x140048fe0  jmp     short loc_14004901A
0x140048fe2  mov     [rsp+48h+var_28], 0
0x140048feb  mov     dword ptr [rsp+48h+var_28], 206h
0x140048ff3  mov     rax, [rsp+48h+var_28]
0x140048ff8  mov     rcx, [rbx]
0x140048ffb  add     rbx, 38h ; '8'
0x140048fff  mov     [rcx], rax
0x140049002  jmp     short loc_14004900E
0x140049004  cmp     qword ptr [rbx], 0
0x140049008  jnz     short loc_140049015
0x14004900a  add     rbx, 8
0x14004900e  cmp     rbx, rsi
0x140049011  jb      short loc_140049004
0x140049013  jmp     short loc_14004901A
0x140049015  test    rbx, rbx
0x140049018  jnz     short loc_140048FF8
0x14004901a  mov     rcx, [rsp+48h+var_10]
0x14004901f  xor     rcx, rsp; StackCookie
0x140049022  call    __security_check_cookie
0x140049027  mov     rbx, [rsp+48h+arg_0]
0x14004902c  add     rsp, 40h
0x140049030  pop     rsi
0x140049031  retn
```
