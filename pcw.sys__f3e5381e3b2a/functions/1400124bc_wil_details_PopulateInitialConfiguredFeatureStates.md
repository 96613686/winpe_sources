# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x1400124bc`
- end: `0x14001263b`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140012354`

## callees

- `0x140001370`
- `0x1400124bc`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140012538`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140012538`

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
0x1400124bc  mov     [rsp+arg_0], rbx
0x1400124c1  push    rsi
0x1400124c2  sub     rsp, 40h
0x1400124c6  mov     rax, cs:__security_cookie
0x1400124cd  xor     rax, rsp
0x1400124d0  mov     [rsp+48h+var_10], rax
0x1400124d5  lea     rbx, wil_details_featureDescriptors_a
0x1400124dc  lea     rsi, wil_details_featureDescriptors_a
0x1400124e3  jmp     short loc_1400124F3
0x1400124e5  cmp     qword ptr [rbx], 0
0x1400124e9  jnz     loc_1400125DF
0x1400124ef  add     rbx, 8
0x1400124f3  cmp     rbx, rsi
0x1400124f6  jb      short loc_1400124E5
0x1400124f8  jmp     loc_140012622
0x1400124fd  xor     eax, eax
0x1400124ff  mov     [rsp+48h+var_20], rax
0x140012504  mov     [rsp+48h+var_18], eax
0x140012508  mov     [rsp+48h+var_28], rax
0x14001250d  cmp     [rbx+1Dh], al
0x140012510  jnz     loc_1400125AC
0x140012516  cmp     [rbx+1Eh], al
0x140012519  jnz     loc_1400125AC
0x14001251f  mov     al, [rbx+1Ch]
0x140012522  lea     r9, [rsp+48h+var_20]
0x140012527  mov     ecx, [rbx+18h]
0x14001252a  lea     r8, [rsp+48h+var_28]
0x14001252f  xor     edx, edx
0x140012531  sub     al, 2
0x140012533  cmp     al, 1
0x140012535  setnbe  dl
0x140012538  call    cs:__imp_RtlQueryFeatureConfiguration
0x14001253f  nop     dword ptr [rax+rax+00h]
0x140012544  cmp     eax, 80000022h
0x140012549  jz      loc_1400125EA
0x14001254f  cmp     eax, 0C0000225h
0x140012554  jz      short loc_1400125AC
0x140012556  test    eax, eax
0x140012558  jz      short loc_140012581
0x14001255a  cmp     eax, 117h
0x14001255f  jnz     short loc_1400125AC
0x140012561  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140012565  and     eax, 80h
0x14001256a  mov     [rsp+48h+var_28], 0
0x140012573  shl     eax, 3
0x140012576  or      eax, 206h
0x14001257b  mov     dword ptr [rsp+48h+var_28], eax
0x14001257f  jmp     short loc_1400125BD
0x140012581  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140012585  mov     ecx, eax
0x140012587  and     ecx, 40h
0x14001258a  mov     [rsp+48h+var_28], 0
0x140012593  shl     ecx, 2
0x140012596  and     eax, 0B0h
0x14001259b  or      ecx, eax
0x14001259d  shl     ecx, 3
0x1400125a0  or      ecx, 206h
0x1400125a6  mov     dword ptr [rsp+48h+var_28], ecx
0x1400125aa  jmp     short loc_1400125BD
0x1400125ac  mov     [rsp+48h+var_28], 0
0x1400125b5  mov     dword ptr [rsp+48h+var_28], 206h
0x1400125bd  mov     rcx, [rbx]
0x1400125c0  add     rbx, 38h ; '8'
0x1400125c4  mov     rax, [rsp+48h+var_28]
0x1400125c9  mov     [rcx], rax
0x1400125cc  jmp     short loc_1400125D8
0x1400125ce  cmp     qword ptr [rbx], 0
0x1400125d2  jnz     short loc_1400125DF
0x1400125d4  add     rbx, 8
0x1400125d8  cmp     rbx, rsi
0x1400125db  jb      short loc_1400125CE
0x1400125dd  jmp     short loc_140012622
0x1400125df  test    rbx, rbx
0x1400125e2  jnz     loc_1400124FD
0x1400125e8  jmp     short loc_140012622
0x1400125ea  mov     [rsp+48h+var_28], 0
0x1400125f3  mov     dword ptr [rsp+48h+var_28], 206h
0x1400125fb  mov     rax, [rsp+48h+var_28]
0x140012600  mov     rcx, [rbx]
0x140012603  add     rbx, 38h ; '8'
0x140012607  mov     [rcx], rax
0x14001260a  jmp     short loc_140012616
0x14001260c  cmp     qword ptr [rbx], 0
0x140012610  jnz     short loc_14001261D
0x140012612  add     rbx, 8
0x140012616  cmp     rbx, rsi
0x140012619  jb      short loc_14001260C
0x14001261b  jmp     short loc_140012622
0x14001261d  test    rbx, rbx
0x140012620  jnz     short loc_140012600
0x140012622  mov     rcx, [rsp+48h+var_10]
0x140012627  xor     rcx, rsp; StackCookie
0x14001262a  call    __security_check_cookie
0x14001262f  mov     rbx, [rsp+48h+arg_0]
0x140012634  add     rsp, 40h
0x140012638  pop     rsi
0x140012639  retn
```
