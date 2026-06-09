# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14003751c`
- end: `0x14003769b`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400373b4`

## callees

- `0x14001fc30`
- `0x14003751c`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140037598`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140037598`

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
0x14003751c  mov     [rsp+arg_0], rbx
0x140037521  push    rsi
0x140037522  sub     rsp, 40h
0x140037526  mov     rax, cs:__security_cookie
0x14003752d  xor     rax, rsp
0x140037530  mov     [rsp+48h+var_10], rax
0x140037535  lea     rbx, wil_details_featureDescriptors_a
0x14003753c  lea     rsi, wil_details_featureDescriptors_a
0x140037543  jmp     short loc_140037553
0x140037545  cmp     qword ptr [rbx], 0
0x140037549  jnz     loc_14003763F
0x14003754f  add     rbx, 8
0x140037553  cmp     rbx, rsi
0x140037556  jb      short loc_140037545
0x140037558  jmp     loc_140037682
0x14003755d  xor     eax, eax
0x14003755f  mov     [rsp+48h+var_20], rax
0x140037564  mov     [rsp+48h+var_18], eax
0x140037568  mov     [rsp+48h+var_28], rax
0x14003756d  cmp     [rbx+1Dh], al
0x140037570  jnz     loc_14003760C
0x140037576  cmp     [rbx+1Eh], al
0x140037579  jnz     loc_14003760C
0x14003757f  mov     al, [rbx+1Ch]
0x140037582  lea     r9, [rsp+48h+var_20]
0x140037587  mov     ecx, [rbx+18h]
0x14003758a  lea     r8, [rsp+48h+var_28]
0x14003758f  xor     edx, edx
0x140037591  sub     al, 2
0x140037593  cmp     al, 1
0x140037595  setnbe  dl
0x140037598  call    cs:__imp_RtlQueryFeatureConfiguration
0x14003759f  nop     dword ptr [rax+rax+00h]
0x1400375a4  cmp     eax, 80000022h
0x1400375a9  jz      loc_14003764A
0x1400375af  cmp     eax, 0C0000225h
0x1400375b4  jz      short loc_14003760C
0x1400375b6  test    eax, eax
0x1400375b8  jz      short loc_1400375E1
0x1400375ba  cmp     eax, 117h
0x1400375bf  jnz     short loc_14003760C
0x1400375c1  mov     eax, dword ptr [rsp+48h+var_20+4]
0x1400375c5  and     eax, 80h
0x1400375ca  mov     [rsp+48h+var_28], 0
0x1400375d3  shl     eax, 3
0x1400375d6  or      eax, 206h
0x1400375db  mov     dword ptr [rsp+48h+var_28], eax
0x1400375df  jmp     short loc_14003761D
0x1400375e1  mov     eax, dword ptr [rsp+48h+var_20+4]
0x1400375e5  mov     ecx, eax
0x1400375e7  and     ecx, 40h
0x1400375ea  mov     [rsp+48h+var_28], 0
0x1400375f3  shl     ecx, 2
0x1400375f6  and     eax, 0B0h
0x1400375fb  or      ecx, eax
0x1400375fd  shl     ecx, 3
0x140037600  or      ecx, 206h
0x140037606  mov     dword ptr [rsp+48h+var_28], ecx
0x14003760a  jmp     short loc_14003761D
0x14003760c  mov     [rsp+48h+var_28], 0
0x140037615  mov     dword ptr [rsp+48h+var_28], 206h
0x14003761d  mov     rcx, [rbx]
0x140037620  add     rbx, 38h ; '8'
0x140037624  mov     rax, [rsp+48h+var_28]
0x140037629  mov     [rcx], rax
0x14003762c  jmp     short loc_140037638
0x14003762e  cmp     qword ptr [rbx], 0
0x140037632  jnz     short loc_14003763F
0x140037634  add     rbx, 8
0x140037638  cmp     rbx, rsi
0x14003763b  jb      short loc_14003762E
0x14003763d  jmp     short loc_140037682
0x14003763f  test    rbx, rbx
0x140037642  jnz     loc_14003755D
0x140037648  jmp     short loc_140037682
0x14003764a  mov     [rsp+48h+var_28], 0
0x140037653  mov     dword ptr [rsp+48h+var_28], 206h
0x14003765b  mov     rax, [rsp+48h+var_28]
0x140037660  mov     rcx, [rbx]
0x140037663  add     rbx, 38h ; '8'
0x140037667  mov     [rcx], rax
0x14003766a  jmp     short loc_140037676
0x14003766c  cmp     qword ptr [rbx], 0
0x140037670  jnz     short loc_14003767D
0x140037672  add     rbx, 8
0x140037676  cmp     rbx, rsi
0x140037679  jb      short loc_14003766C
0x14003767b  jmp     short loc_140037682
0x14003767d  test    rbx, rbx
0x140037680  jnz     short loc_140037660
0x140037682  mov     rcx, [rsp+48h+var_10]
0x140037687  xor     rcx, rsp; StackCookie
0x14003768a  call    __security_check_cookie
0x14003768f  mov     rbx, [rsp+48h+arg_0]
0x140037694  add     rsp, 40h
0x140037698  pop     rsi
0x140037699  retn
```
