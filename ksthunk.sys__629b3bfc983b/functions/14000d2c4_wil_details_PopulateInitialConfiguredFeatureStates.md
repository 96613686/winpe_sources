# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14000d2c4`
- end: `0x14000d443`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000d15c`

## callees

- `0x140003690`
- `0x14000d2c4`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000d340`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000d340`

## pseudocode

```c
void wil_details_PopulateInitialConfiguredFeatureStates()
{
  __int64 *i; // rbx
  int v1; // eax
  _QWORD *v2; // rcx
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
    v2 = (_QWORD *)*i;
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
0x14000d2c4  mov     [rsp+arg_0], rbx
0x14000d2c9  push    rsi
0x14000d2ca  sub     rsp, 40h
0x14000d2ce  mov     rax, cs:__security_cookie
0x14000d2d5  xor     rax, rsp
0x14000d2d8  mov     [rsp+48h+var_10], rax
0x14000d2dd  lea     rbx, wil_details_featureDescriptors_a
0x14000d2e4  lea     rsi, wil_details_featureDescriptors_a
0x14000d2eb  jmp     short loc_14000D2FB
0x14000d2ed  cmp     qword ptr [rbx], 0
0x14000d2f1  jnz     loc_14000D3E7
0x14000d2f7  add     rbx, 8
0x14000d2fb  cmp     rbx, rsi
0x14000d2fe  jb      short loc_14000D2ED
0x14000d300  jmp     loc_14000D42A
0x14000d305  xor     eax, eax
0x14000d307  mov     [rsp+48h+var_20], rax
0x14000d30c  mov     [rsp+48h+var_18], eax
0x14000d310  mov     [rsp+48h+var_28], rax
0x14000d315  cmp     [rbx+1Dh], al
0x14000d318  jnz     loc_14000D3B4
0x14000d31e  cmp     [rbx+1Eh], al
0x14000d321  jnz     loc_14000D3B4
0x14000d327  mov     al, [rbx+1Ch]
0x14000d32a  lea     r9, [rsp+48h+var_20]
0x14000d32f  mov     ecx, [rbx+18h]
0x14000d332  lea     r8, [rsp+48h+var_28]
0x14000d337  xor     edx, edx
0x14000d339  sub     al, 2
0x14000d33b  cmp     al, 1
0x14000d33d  setnbe  dl
0x14000d340  call    cs:__imp_RtlQueryFeatureConfiguration
0x14000d347  nop     dword ptr [rax+rax+00h]
0x14000d34c  cmp     eax, 80000022h
0x14000d351  jz      loc_14000D3F2
0x14000d357  cmp     eax, 0C0000225h
0x14000d35c  jz      short loc_14000D3B4
0x14000d35e  test    eax, eax
0x14000d360  jz      short loc_14000D389
0x14000d362  cmp     eax, 117h
0x14000d367  jnz     short loc_14000D3B4
0x14000d369  mov     eax, dword ptr [rsp+48h+var_20+4]
0x14000d36d  and     eax, 80h
0x14000d372  mov     [rsp+48h+var_28], 0
0x14000d37b  shl     eax, 3
0x14000d37e  or      eax, 206h
0x14000d383  mov     dword ptr [rsp+48h+var_28], eax
0x14000d387  jmp     short loc_14000D3C5
0x14000d389  mov     eax, dword ptr [rsp+48h+var_20+4]
0x14000d38d  mov     ecx, eax
0x14000d38f  and     ecx, 40h
0x14000d392  mov     [rsp+48h+var_28], 0
0x14000d39b  shl     ecx, 2
0x14000d39e  and     eax, 0B0h
0x14000d3a3  or      ecx, eax
0x14000d3a5  shl     ecx, 3
0x14000d3a8  or      ecx, 206h
0x14000d3ae  mov     dword ptr [rsp+48h+var_28], ecx
0x14000d3b2  jmp     short loc_14000D3C5
0x14000d3b4  mov     [rsp+48h+var_28], 0
0x14000d3bd  mov     dword ptr [rsp+48h+var_28], 206h
0x14000d3c5  mov     rcx, [rbx]
0x14000d3c8  add     rbx, 38h ; '8'
0x14000d3cc  mov     rax, [rsp+48h+var_28]
0x14000d3d1  mov     [rcx], rax
0x14000d3d4  jmp     short loc_14000D3E0
0x14000d3d6  cmp     qword ptr [rbx], 0
0x14000d3da  jnz     short loc_14000D3E7
0x14000d3dc  add     rbx, 8
0x14000d3e0  cmp     rbx, rsi
0x14000d3e3  jb      short loc_14000D3D6
0x14000d3e5  jmp     short loc_14000D42A
0x14000d3e7  test    rbx, rbx
0x14000d3ea  jnz     loc_14000D305
0x14000d3f0  jmp     short loc_14000D42A
0x14000d3f2  mov     [rsp+48h+var_28], 0
0x14000d3fb  mov     dword ptr [rsp+48h+var_28], 206h
0x14000d403  mov     rax, [rsp+48h+var_28]
0x14000d408  mov     rcx, [rbx]
0x14000d40b  add     rbx, 38h ; '8'
0x14000d40f  mov     [rcx], rax
0x14000d412  jmp     short loc_14000D41E
0x14000d414  cmp     qword ptr [rbx], 0
0x14000d418  jnz     short loc_14000D425
0x14000d41a  add     rbx, 8
0x14000d41e  cmp     rbx, rsi
0x14000d421  jb      short loc_14000D414
0x14000d423  jmp     short loc_14000D42A
0x14000d425  test    rbx, rbx
0x14000d428  jnz     short loc_14000D408
0x14000d42a  mov     rcx, [rsp+48h+var_10]
0x14000d42f  xor     rcx, rsp; StackCookie
0x14000d432  call    __security_check_cookie
0x14000d437  mov     rbx, [rsp+48h+arg_0]
0x14000d43c  add     rsp, 40h
0x14000d440  pop     rsi
0x14000d441  retn
```
