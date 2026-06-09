# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14000e2c4`
- end: `0x14000e443`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `383`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000e15c`

## callees

- `0x140004110`
- `0x14000e2c4`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000e340`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000e340`

## pseudocode

```c
void wil_details_PopulateInitialConfiguredFeatureStates()
{
  __int64 **i; // rbx
  int v1; // eax
  __int64 *v2; // rcx
  __int64 *v3; // rcx
  __int64 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+28h] [rbp-20h] BYREF
  int v6; // [rsp+30h] [rbp-18h]

  for ( i = wil_details_featureDescriptors_a; ; ++i )
  {
    if ( i >= (__int64 **)wil_details_featureDescriptors_z )
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
    v2 = *i;
    i += 7;
    *v2 = v4;
    while ( i < (__int64 **)wil_details_featureDescriptors_z )
    {
      if ( *i )
        goto LABEL_20;
      ++i;
    }
    return;
  }
  v4 = 518;
LABEL_23:
  v3 = *i;
  i += 7;
  *v3 = 518;
  while ( i < (__int64 **)wil_details_featureDescriptors_z )
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
0x14000e2c4  mov     [rsp+arg_0], rbx
0x14000e2c9  push    rsi
0x14000e2ca  sub     rsp, 40h
0x14000e2ce  mov     rax, cs:__security_cookie
0x14000e2d5  xor     rax, rsp
0x14000e2d8  mov     [rsp+48h+var_10], rax
0x14000e2dd  lea     rbx, wil_details_featureDescriptors_a
0x14000e2e4  lea     rsi, wil_details_featureDescriptors_z
0x14000e2eb  jmp     short loc_14000E2FB
0x14000e2ed  cmp     qword ptr [rbx], 0
0x14000e2f1  jnz     loc_14000E3E7
0x14000e2f7  add     rbx, 8
0x14000e2fb  cmp     rbx, rsi
0x14000e2fe  jb      short loc_14000E2ED
0x14000e300  jmp     loc_14000E42A
0x14000e305  xor     eax, eax
0x14000e307  mov     [rsp+48h+var_20], rax
0x14000e30c  mov     [rsp+48h+var_18], eax
0x14000e310  mov     [rsp+48h+var_28], rax
0x14000e315  cmp     [rbx+1Dh], al
0x14000e318  jnz     loc_14000E3B4
0x14000e31e  cmp     [rbx+1Eh], al
0x14000e321  jnz     loc_14000E3B4
0x14000e327  mov     al, [rbx+1Ch]
0x14000e32a  lea     r9, [rsp+48h+var_20]
0x14000e32f  mov     ecx, [rbx+18h]
0x14000e332  lea     r8, [rsp+48h+var_28]
0x14000e337  xor     edx, edx
0x14000e339  sub     al, 2
0x14000e33b  cmp     al, 1
0x14000e33d  setnbe  dl
0x14000e340  call    cs:__imp_RtlQueryFeatureConfiguration
0x14000e347  nop     dword ptr [rax+rax+00h]
0x14000e34c  cmp     eax, 80000022h
0x14000e351  jz      loc_14000E3F2
0x14000e357  cmp     eax, 0C0000225h
0x14000e35c  jz      short loc_14000E3B4
0x14000e35e  test    eax, eax
0x14000e360  jz      short loc_14000E389
0x14000e362  cmp     eax, 117h
0x14000e367  jnz     short loc_14000E3B4
0x14000e369  mov     eax, dword ptr [rsp+48h+var_20+4]
0x14000e36d  and     eax, 80h
0x14000e372  mov     [rsp+48h+var_28], 0
0x14000e37b  shl     eax, 3
0x14000e37e  or      eax, 206h
0x14000e383  mov     dword ptr [rsp+48h+var_28], eax
0x14000e387  jmp     short loc_14000E3C5
0x14000e389  mov     eax, dword ptr [rsp+48h+var_20+4]
0x14000e38d  mov     ecx, eax
0x14000e38f  and     ecx, 40h
0x14000e392  mov     [rsp+48h+var_28], 0
0x14000e39b  shl     ecx, 2
0x14000e39e  and     eax, 0B0h
0x14000e3a3  or      ecx, eax
0x14000e3a5  shl     ecx, 3
0x14000e3a8  or      ecx, 206h
0x14000e3ae  mov     dword ptr [rsp+48h+var_28], ecx
0x14000e3b2  jmp     short loc_14000E3C5
0x14000e3b4  mov     [rsp+48h+var_28], 0
0x14000e3bd  mov     dword ptr [rsp+48h+var_28], 206h
0x14000e3c5  mov     rcx, [rbx]
0x14000e3c8  add     rbx, 38h ; '8'
0x14000e3cc  mov     rax, [rsp+48h+var_28]
0x14000e3d1  mov     [rcx], rax
0x14000e3d4  jmp     short loc_14000E3E0
0x14000e3d6  cmp     qword ptr [rbx], 0
0x14000e3da  jnz     short loc_14000E3E7
0x14000e3dc  add     rbx, 8
0x14000e3e0  cmp     rbx, rsi
0x14000e3e3  jb      short loc_14000E3D6
0x14000e3e5  jmp     short loc_14000E42A
0x14000e3e7  test    rbx, rbx
0x14000e3ea  jnz     loc_14000E305
0x14000e3f0  jmp     short loc_14000E42A
0x14000e3f2  mov     [rsp+48h+var_28], 0
0x14000e3fb  mov     dword ptr [rsp+48h+var_28], 206h
0x14000e403  mov     rax, [rsp+48h+var_28]
0x14000e408  mov     rcx, [rbx]
0x14000e40b  add     rbx, 38h ; '8'
0x14000e40f  mov     [rcx], rax
0x14000e412  jmp     short loc_14000E41E
0x14000e414  cmp     qword ptr [rbx], 0
0x14000e418  jnz     short loc_14000E425
0x14000e41a  add     rbx, 8
0x14000e41e  cmp     rbx, rsi
0x14000e421  jb      short loc_14000E414
0x14000e423  jmp     short loc_14000E42A
0x14000e425  test    rbx, rbx
0x14000e428  jnz     short loc_14000E408
0x14000e42a  mov     rcx, [rsp+48h+var_10]
0x14000e42f  xor     rcx, rsp; StackCookie
0x14000e432  call    __security_check_cookie
0x14000e437  mov     rbx, [rsp+48h+arg_0]
0x14000e43c  add     rsp, 40h
0x14000e440  pop     rsi
0x14000e441  retn
```
