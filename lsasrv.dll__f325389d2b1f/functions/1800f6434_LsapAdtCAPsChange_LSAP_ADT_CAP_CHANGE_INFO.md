# LsapAdtCAPsChange(_LSAP_ADT_CAP_CHANGE_INFO *)

- ea: `0x1800f6434`
- end: `0x1800f6895`
- name: `?LsapAdtCAPsChange@@YAJPEAU_LSAP_ADT_CAP_CHANGE_INFO@@@Z`
- size: `1121`
- prototype: `__int64 __fastcall(struct _LSAP_ADT_CAP_CHANGE_INFO *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800f8218`

## callees

- `0x18000c300`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bc2c4`
- `0x1800bd6e0`
- `0x1800f63fc`
- `0x1800f6434`

## import_xrefs

- `LSAADT!__imp_LsapAdtWriteLog` at `0x1800f6803`
- `LSAADT!__imp_LsapAdtWriteLog` at `0x1800f6803`
- `LSAADT!__imp_LsapAuditFailed` at `0x1800f684c`
- `LSAADT!__imp_LsapAuditFailed` at `0x1800f684c`
- `LSAADT!__imp_LsapQueryClientInfo` at `0x1800f65ce`
- `LSAADT!__imp_LsapQueryClientInfo` at `0x1800f65ce`
- `LSAADT!__imp_?LsapSubsystemName@@3U_UNICODE_STRING@@A` at `0x1800f6658`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f6826`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f6826`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f6569`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f6569`
- `ntdll!RtlLengthSid` at `0x1800f6606`
- `ntdll!RtlLengthSid` at `0x1800f6637`
- `ntdll!RtlLengthSid` at `0x1800f6606`
- `ntdll!RtlLengthSid` at `0x1800f6637`

## pseudocode

```c
__int64 __fastcall LsapAdtCAPsChange(struct _LSAP_ADT_CAP_CHANGE_INFO *a1, __int64 a2, __int64 a3)
{
  SIZE_T v5; // rdx
  int v6; // ebx
  int i; // ecx
  int j; // edi
  unsigned __int64 v9; // rcx
  HLOCAL v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rdx
  unsigned int v13; // ecx
  __int64 k; // r14
  _QWORD *v15; // r15
  __int16 *v16; // rdi
  char *v17; // rbx
  char *v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // ecx
  __int64 m; // rdi
  void *v23; // rcx
  struct _RTL_BALANCED_NODE *v24; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v25; // [rsp+28h] [rbp-D8h] BYREF
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+34h] [rbp-CCh]
  int v28; // [rsp+40h] [rbp-C0h]
  _DWORD v29[258]; // [rsp+48h] [rbp-B8h]
  __int16 v30; // [rsp+450h] [rbp+350h] BYREF
  HLOCAL hMem[2]; // [rsp+452h] [rbp+352h]
  __int128 v32; // [rsp+462h] [rbp+362h]
  _BYTE v33[30]; // [rsp+472h] [rbp+372h] BYREF

  if ( !(unsigned __int8)IsLsapAdtInitParametersArrayPresent(a1, a2, a3) )
    return 0;
  v24 = 0;
  v25 = 0;
  memset_0(&v26, 0, 0x418u);
  v30 = 0;
  memset(v33, 0, sizeof(v33));
  *(_OWORD *)hMem = 0;
  v32 = 0;
  if ( a1 )
  {
    for ( i = 0; i < 4; ++i )
    {
      if ( (unsigned int)i < 2 || (v5 = (unsigned int)(i - 2), i == 2) )
      {
        if ( *((_DWORD *)a1 + i + 12) )
          i = 4;
      }
      else if ( i == 3 )
      {
        if ( dword_18019EF08 == *((_DWORD *)a1 + 15) )
          goto LABEL_12;
      }
      else
      {
        i = 4;
      }
    }
    if ( !LsapAdtCAPChangeEnabled() )
    {
LABEL_12:
      v6 = 0;
      goto LABEL_36;
    }
    for ( j = 0; j < 4; ++j )
    {
      v9 = 4LL * *((unsigned int *)a1 + j + 12);
      if ( v9 > 0xFFFFFFFF
        || (v5 = (unsigned int)(v9 + *((_DWORD *)a1 + j + 8) + 2), (unsigned int)v5 < (unsigned int)v9) )
      {
        v6 = -1073741675;
        goto LABEL_36;
      }
      if ( (unsigned int)v5 > 0xFFFF
        || (LOWORD(hMem[2 * j]) = v9 + *((_WORD *)a1 + 2 * j + 16) + 2,
            v10 = LocalAlloc(0, v5),
            (*(HLOCAL *)((char *)&hMem[2 * j] + 6) = v10) == 0) )
      {
        v6 = -1073741801;
        goto LABEL_36;
      }
      *(&v30 + 8 * j) = 0;
    }
    v26 = 6;
    v28 = 524433;
    v27 = 4819;
    v6 = LsapQueryClientInfo(&v24, &v25);
    if ( v6 >= 0 )
    {
      v29[8 * HIDWORD(v27)] = 4;
      v11 = 8LL * HIDWORD(v27);
      if ( v24->Children[0] )
      {
        v29[v11 + 1] = RtlLengthSid(v24->Children[0]);
        *(_QWORD *)&v29[8 * HIDWORD(v27) + 6] = v24->Children[0];
      }
      else
      {
        v29[v11 + 1] = RtlLengthSid(&AdtpNullSid);
        *(_QWORD *)&v29[8 * HIDWORD(v27) + 6] = &AdtpNullSid;
      }
      v12 = *(_QWORD *)&LsapSubsystemName.Length;
      ++HIDWORD(v27);
      v29[8 * HIDWORD(v27)] = 1;
      v29[8 * HIDWORD(v27) + 1] = LsapSubsystemName.Length + 16;
      *(_QWORD *)&v29[8 * HIDWORD(v27) + 6] = *(_QWORD *)&LsapSubsystemName.Length;
      ++HIDWORD(v27);
      v29[8 * HIDWORD(v27)] = 5;
      v29[8 * HIDWORD(v27) + 1] = 8;
      *(_QWORD *)&v29[8 * HIDWORD(v27) + 2] = v25;
      ++HIDWORD(v27);
      v29[8 * HIDWORD(v27)] = 1;
      v29[8 * HIDWORD(v27) + 1] = LsapSubsystemName.Length + 16;
      *(_QWORD *)&v29[8 * HIDWORD(v27) + 6] = *(_QWORD *)&LsapSubsystemName.Length;
      ++HIDWORD(v27);
      v29[8 * HIDWORD(v27)] = 1;
      v29[8 * HIDWORD(v27) + 1] = CAPsObjectTypeName.Length + 16;
      *(_QWORD *)&v29[8 * HIDWORD(v27) + 6] = &CAPsObjectTypeName;
      v13 = ++HIDWORD(v27);
      for ( k = 0; k != 4; ++k )
      {
        v15 = (_QWORD *)*((_QWORD *)a1 + k);
        v16 = &v30 + 8 * k;
        v17 = *(char **)((char *)&hMem[2 * k] + 6);
        if ( v15 )
        {
          do
          {
            *(_DWORD *)v17 = 589834;
            v18 = v17 + 4;
            *v16 += 4;
            memcpy_0(v18, *(const void **)(v15[1] + 16LL), *(unsigned __int16 *)(v15[1] + 8LL));
            *v16 += *(_WORD *)(v15[1] + 8LL);
            v19 = v15[1];
            v15 = (_QWORD *)*v15;
            v17 = &v18[2 * ((unsigned __int64)*(unsigned __int16 *)(v19 + 8) >> 1)];
          }
          while ( v15 );
          v13 = HIDWORD(v27);
        }
        v20 = v13;
        v21 = (unsigned __int16)*v16 + 16;
        v29[8 * v20] = 1;
        v29[8 * HIDWORD(v27) + 1] = v21;
        *(_QWORD *)&v29[8 * HIDWORD(v27) + 6] = v16;
        v13 = ++HIDWORD(v27);
      }
      v6 = LsapAdtWriteLog(&v26, v12);
    }
  }
  else
  {
    v6 = -1073741811;
  }
LABEL_36:
  for ( m = 0; m != 4; ++m )
  {
    v23 = *(HLOCAL *)((char *)&hMem[2 * m] + 6);
    if ( v23 )
    {
      LocalFree(v23);
      *(HLOCAL *)((char *)&hMem[2 * m] + 6) = 0;
    }
  }
  if ( v6 < 0 )
    LsapAuditFailed((unsigned int)v6);
  if ( v24 )
    LsapSubProv_FreeRoutine(v24, (void *)v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800f6434  mov     [rsp-8+arg_8], rbx
0x1800f6439  mov     [rsp-8+arg_10], rsi
0x1800f643e  push    rbp
0x1800f643f  push    rdi
0x1800f6440  push    r13
0x1800f6442  push    r14
0x1800f6444  push    r15
0x1800f6446  lea     rbp, [rsp-3A0h]
0x1800f644e  sub     rsp, 4A0h
0x1800f6455  mov     rax, cs:__security_cookie
0x1800f645c  xor     rax, rsp
0x1800f645f  mov     [rbp+3C0h+var_30], rax
0x1800f6466  mov     rsi, rcx
0x1800f6469  call    IsLsapAdtInitParametersArrayPresent
0x1800f646e  test    al, al
0x1800f6470  jnz     short loc_1800F6479
0x1800f6472  xor     eax, eax
0x1800f6474  jmp     loc_1800F6869
0x1800f6479  xor     edx, edx; Val
0x1800f647b  mov     [rsp+4C0h+var_4A0], 0
0x1800f6484  mov     r8d, 418h; Size
0x1800f648a  mov     [rsp+4C0h+var_498], 0
0x1800f6493  lea     rcx, [rsp+4C0h+var_490]; void *
0x1800f6498  call    memset_0
0x1800f649d  xor     eax, eax
0x1800f649f  xorps   xmm0, xmm0
0x1800f64a2  mov     [rbp+3C0h+var_70], ax
0x1800f64a9  movups  xmmword ptr [rbp+3C0h+var_4E], xmm0
0x1800f64b0  lea     r13d, [rax+4]
0x1800f64b4  lea     r15d, [rax+1]
0x1800f64b8  movups  xmmword ptr [rbp+3C0h+hMem], xmm0
0x1800f64bf  movups  [rbp+3C0h+var_5E], xmm0
0x1800f64c6  movups  xmmword ptr [rbp+3C0h+var_4E+0Eh], xmm0
0x1800f64cd  test    rsi, rsi
0x1800f64d0  jnz     short loc_1800F64DC
0x1800f64d2  mov     ebx, 0C000000Dh
0x1800f64d7  jmp     loc_1800F6811
0x1800f64dc  mov     r8d, cs:dword_18019EF08
0x1800f64e3  xor     ecx, ecx
0x1800f64e5  cmp     ecx, r13d
0x1800f64e8  jge     short loc_1800F6522
0x1800f64ea  mov     edx, ecx
0x1800f64ec  test    ecx, ecx
0x1800f64ee  jz      short loc_1800F6511
0x1800f64f0  sub     edx, r15d
0x1800f64f3  jz      short loc_1800F6511
0x1800f64f5  sub     edx, r15d
0x1800f64f8  jz      short loc_1800F6511
0x1800f64fa  cmp     edx, r15d
0x1800f64fd  jz      short loc_1800F6504
0x1800f64ff  mov     ecx, r13d
0x1800f6502  jmp     short loc_1800F651D
0x1800f6504  cmp     r8d, [rsi+3Ch]
0x1800f6508  jnz     short loc_1800F651D
0x1800f650a  xor     ebx, ebx
0x1800f650c  jmp     loc_1800F6811
0x1800f6511  movsxd  rax, ecx
0x1800f6514  cmp     dword ptr [rsi+rax*4+30h], 0
0x1800f6519  cmovnz  ecx, r13d
0x1800f651d  add     ecx, r15d
0x1800f6520  jmp     short loc_1800F64E5
0x1800f6522  call    ?LsapAdtCAPChangeEnabled@@YAEXZ; LsapAdtCAPChangeEnabled(void)
0x1800f6527  test    al, al
0x1800f6529  jz      short loc_1800F650A
0x1800f652b  xor     edi, edi
0x1800f652d  cmp     edi, r13d
0x1800f6530  jge     short loc_1800F65A5
0x1800f6532  movsxd  rbx, edi
0x1800f6535  mov     eax, 0FFFFFFFFh
0x1800f653a  mov     ecx, [rsi+rbx*4+30h]
0x1800f653e  shl     rcx, 2
0x1800f6542  cmp     rcx, rax
0x1800f6545  ja      short loc_1800F659B
0x1800f6547  mov     edx, [rsi+rbx*4+20h]
0x1800f654b  add     edx, 2
0x1800f654e  add     edx, ecx; uBytes
0x1800f6550  cmp     edx, ecx
0x1800f6552  jb      short loc_1800F659B
0x1800f6554  cmp     edx, 0FFFFh
0x1800f655a  ja      short loc_1800F6591
0x1800f655c  add     rbx, rbx
0x1800f655f  xor     ecx, ecx; uFlags
0x1800f6561  mov     word ptr [rbp+rbx*8+3C0h+hMem], dx
0x1800f6569  call    cs:__imp_LocalAlloc
0x1800f6570  nop     dword ptr [rax+rax+00h]
0x1800f6575  mov     [rbp+rbx*8+3C0h+hMem+6], rax
0x1800f657d  test    rax, rax
0x1800f6580  jz      short loc_1800F6591
0x1800f6582  xor     eax, eax
0x1800f6584  mov     [rbp+rbx*8+3C0h+var_70], ax
0x1800f658c  add     edi, r15d
0x1800f658f  jmp     short loc_1800F652D
0x1800f6591  mov     ebx, 0C0000017h
0x1800f6596  jmp     loc_1800F6811
0x1800f659b  mov     ebx, 0C0000095h
0x1800f65a0  jmp     loc_1800F6811
0x1800f65a5  lea     rdx, [rsp+4C0h+var_498]
0x1800f65aa  mov     [rsp+4C0h+var_490], 6
0x1800f65b2  lea     rcx, [rsp+4C0h+var_4A0]
0x1800f65b7  mov     [rsp+4C0h+var_480], 80091h
0x1800f65bf  mov     [rsp+4C0h+var_48C], 12D3h
0x1800f65c8  mov     r14d, 8
0x1800f65ce  call    cs:__imp_LsapQueryClientInfo
0x1800f65d5  nop     dword ptr [rax+rax+00h]
0x1800f65da  mov     ebx, eax
0x1800f65dc  test    eax, eax
0x1800f65de  js      loc_1800F6811
0x1800f65e4  mov     eax, dword ptr [rsp+4C0h+var_48C+4]
0x1800f65e8  shl     rax, 5
0x1800f65ec  mov     [rsp+rax+4C0h+var_478], r13d
0x1800f65f1  mov     rax, [rsp+4C0h+var_4A0]
0x1800f65f6  mov     ebx, dword ptr [rsp+4C0h+var_48C+4]
0x1800f65fa  shl     rbx, 5
0x1800f65fe  mov     rcx, [rax]; Sid
0x1800f6601  test    rcx, rcx
0x1800f6604  jz      short loc_1800F662D
0x1800f6606  call    cs:__imp_RtlLengthSid
0x1800f660d  nop     dword ptr [rax+rax+00h]
0x1800f6612  mov     [rsp+rbx+4C0h+var_474], eax
0x1800f6616  mov     edx, dword ptr [rsp+4C0h+var_48C+4]
0x1800f661a  mov     rax, [rsp+4C0h+var_4A0]
0x1800f661f  shl     rdx, 5
0x1800f6623  mov     rcx, [rax]
0x1800f6626  mov     [rsp+rdx+4C0h+var_460], rcx
0x1800f662b  jmp     short loc_1800F6654
0x1800f662d  lea     rdi, AdtpNullSid
0x1800f6634  mov     rcx, rdi; Sid
0x1800f6637  call    cs:__imp_RtlLengthSid
0x1800f663e  nop     dword ptr [rax+rax+00h]
0x1800f6643  mov     [rsp+rbx+4C0h+var_474], eax
0x1800f6647  mov     eax, dword ptr [rsp+4C0h+var_48C+4]
0x1800f664b  shl     rax, 5
0x1800f664f  mov     [rsp+rax+4C0h+var_460], rdi
0x1800f6654  mov     eax, dword ptr [rsp+4C0h+var_48C+4]
0x1800f6658  mov     rdx, cs:__imp_?LsapSubsystemName@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING LsapSubsystemName
0x1800f665f  add     eax, r15d
0x1800f6662  mov     dword ptr [rsp+4C0h+var_48C+4], eax
0x1800f6666  mov     ecx, eax
0x1800f6668  shl     rcx, 5
0x1800f666c  mov     [rsp+rcx+4C0h+var_478], r15d
0x1800f6671  movzx   ecx, word ptr [rdx]
0x1800f6674  mov     eax, dword ptr [rsp+4C0h+var_48C+4]
0x1800f6678  add     ecx, 10h
0x1800f667b  shl     rax, 5
0x1800f667f  mov     [rsp+rax+4C0h+var_474], ecx
0x1800f6683  mov     eax, dword ptr [rsp+4C0h+var_48C+4]
0x1800f6687  shl     rax, 5
0x1800f668b  mov     [rsp+rax+4C0h+var_460], rdx
0x1800f6690  mov     eax, dword ptr [rsp+4C0h+var_48C+4]
0x1800f6694  add     eax, r15d
0x1800f6697  mov     dword ptr [rsp+4C0h+var_48C+4], eax
0x1800f669b  mov     ecx, eax
0x1800f669d  shl     rcx, 5
0x1800f66a1  mov     [rsp+rcx+4C0h+var_478], 5
0x1800f66a9  mov     eax, dword ptr [rsp+4C0h+var_48C+4]
0x1800f66ad  shl     rax, 5
0x1800f66b1  mov     [rsp+rax+4C0h+var_474], r14d
0x1800f66b6  mov     ecx, dword ptr [rsp+4C0h+var_48C+4]
0x1800f66ba  mov     rax, [rsp+4C0h+var_498]
0x1800f66bf  shl     rcx, 5
0x1800f66c3  mov     [rsp+rcx+4C0h+var_470], rax
0x1800f66c8  mov     eax, dword ptr [rsp+4C0h+var_48C+4]
0x1800f66cc  add     eax, r15d
0x1800f66cf  mov     dword ptr [rsp+4C0h+var_48C+4], eax
0x1800f66d3  mov     ecx, eax
0x1800f66d5  shl     rcx, 5
0x1800f66d9  mov     [rsp+rcx+4C0h+var_478], r15d
0x1800f66de  movzx   ecx, word ptr [rdx]
0x1800f66e1  mov     eax, dword ptr [rsp+4C0h+var_48C+4]
0x1800f66e5  add     ecx, 10h
0x1800f66e8  shl     rax, 5
0x1800f66ec  mov     [rsp+rax+4C0h+var_474], ecx
0x1800f66f0  mov     eax, dword ptr [rsp+4C0h+var_48C+4]
0x1800f66f4  shl     rax, 5
0x1800f66f8  mov     [rsp+rax+4C0h+var_460], rdx
0x1800f66fd  mov     eax, dword ptr [rsp+4C0h+var_48C+4]
0x1800f6701  add     eax, r15d
0x1800f6704  mov     dword ptr [rsp+4C0h+var_48C+4], eax
0x1800f6708  mov     ecx, eax
0x1800f670a  shl     rcx, 5
0x1800f670e  mov     [rsp+rcx+4C0h+var_478], r15d
0x1800f6713  mov     eax, dword ptr [rsp+4C0h+var_48C+4]
0x1800f6717  movzx   ecx, word ptr cs:?CAPsObjectTypeName@@3U_UNICODE_STRING@@A; ".0"
0x1800f671e  add     ecx, 10h
0x1800f6721  shl     rax, 5
0x1800f6725  mov     [rsp+rax+4C0h+var_474], ecx
0x1800f6729  lea     rcx, ?CAPsObjectTypeName@@3U_UNICODE_STRING@@A; ".0"
0x1800f6730  mov     eax, dword ptr [rsp+4C0h+var_48C+4]
0x1800f6734  shl     rax, 5
0x1800f6738  mov     [rsp+rax+4C0h+var_460], rcx
0x1800f673d  mov     ecx, dword ptr [rsp+4C0h+var_48C+4]
0x1800f6741  add     ecx, r15d
0x1800f6744  mov     dword ptr [rsp+4C0h+var_48C+4], ecx
0x1800f6748  xor     r14d, r14d
0x1800f674b  mov     r15, [rsi+r14*8]
0x1800f674f  lea     rdi, [rbp+3C0h+var_70]
0x1800f6756  mov     rax, r14
0x1800f6759  shl     rax, 4
0x1800f675d  add     rdi, rax
0x1800f6760  mov     rbx, [rbp+rax+3C0h+hMem+6]
0x1800f6768  test    r15, r15
0x1800f676b  jz      short loc_1800F67B7
0x1800f676d  mov     eax, cs:dword_18016C518
0x1800f6773  mov     [rbx], eax
0x1800f6775  add     rbx, r13
0x1800f6778  add     [rdi], r13w
0x1800f677c  mov     rcx, rbx; void *
0x1800f677f  mov     rdx, [r15+8]
0x1800f6783  movzx   r8d, word ptr [rdx+8]; Size
0x1800f6788  mov     rdx, [rdx+10h]; Src
0x1800f678c  call    memcpy_0
0x1800f6791  mov     rax, [r15+8]
0x1800f6795  movzx   ecx, word ptr [rax+8]
0x1800f6799  add     [rdi], cx
0x1800f679c  mov     rax, [r15+8]
0x1800f67a0  mov     r15, [r15]
0x1800f67a3  movzx   ecx, word ptr [rax+8]
0x1800f67a7  shr     rcx, 1
0x1800f67aa  lea     rbx, [rbx+rcx*2]
0x1800f67ae  test    r15, r15
0x1800f67b1  jnz     short loc_1800F676D
0x1800f67b3  mov     ecx, dword ptr [rsp+4C0h+var_48C+4]
0x1800f67b7  mov     eax, ecx
0x1800f67b9  mov     r15d, 1
0x1800f67bf  movzx   ecx, word ptr [rdi]
0x1800f67c2  shl     rax, 5
0x1800f67c6  add     ecx, 10h
0x1800f67c9  mov     [rsp+rax+4C0h+var_478], r15d
0x1800f67ce  mov     eax, dword ptr [rsp+4C0h+var_48C+4]
0x1800f67d2  shl     rax, 5
0x1800f67d6  mov     [rsp+rax+4C0h+var_474], ecx
0x1800f67da  mov     eax, dword ptr [rsp+4C0h+var_48C+4]
0x1800f67de  shl     rax, 5
0x1800f67e2  mov     [rsp+rax+4C0h+var_460], rdi
0x1800f67e7  mov     ecx, dword ptr [rsp+4C0h+var_48C+4]
0x1800f67eb  add     ecx, r15d
0x1800f67ee  inc     r14
0x1800f67f1  mov     dword ptr [rsp+4C0h+var_48C+4], ecx
0x1800f67f5  cmp     r14, r13
0x1800f67f8  jnz     loc_1800F674B
0x1800f67fe  lea     rcx, [rsp+4C0h+var_490]
0x1800f6803  call    cs:__imp_LsapAdtWriteLog
0x1800f680a  nop     dword ptr [rax+rax+00h]
0x1800f680f  mov     ebx, eax
0x1800f6811  xor     edi, edi
0x1800f6813  mov     rsi, rdi
0x1800f6816  add     rsi, rsi
0x1800f6819  mov     rcx, [rbp+rsi*8+3C0h+hMem+6]; hMem
0x1800f6821  test    rcx, rcx
0x1800f6824  jz      short loc_1800F683E
0x1800f6826  call    cs:__imp_LocalFree
0x1800f682d  nop     dword ptr [rax+rax+00h]
0x1800f6832  mov     [rbp+rsi*8+3C0h+hMem+6], 0
0x1800f683e  add     rdi, r15
0x1800f6841  cmp     rdi, r13
0x1800f6844  jnz     short loc_1800F6813
0x1800f6846  test    ebx, ebx
0x1800f6848  jns     short loc_1800F6858
0x1800f684a  mov     ecx, ebx
0x1800f684c  call    cs:__imp_LsapAuditFailed
0x1800f6853  nop     dword ptr [rax+rax+00h]
0x1800f6858  mov     rcx, [rsp+4C0h+var_4A0]; struct _RTL_BALANCED_NODE *
0x1800f685d  test    rcx, rcx
0x1800f6860  jz      short loc_1800F6867
0x1800f6862  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800f6867  mov     eax, ebx
0x1800f6869  mov     rcx, [rbp+3C0h+var_30]
0x1800f6870  xor     rcx, rsp; StackCookie
0x1800f6873  call    __security_check_cookie
0x1800f6878  lea     r11, [rsp+4C0h+var_20]
0x1800f6880  mov     rbx, [r11+38h]
0x1800f6884  mov     rsi, [r11+40h]
0x1800f6888  mov     rsp, r11
0x1800f688b  pop     r15
0x1800f688d  pop     r14
0x1800f688f  pop     r13
0x1800f6891  pop     rdi
0x1800f6892  pop     rbp
0x1800f6893  retn
```
