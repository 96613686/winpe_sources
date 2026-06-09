# IsUsingWinlogonCreds

- ea: `0x180001260`
- end: `0x1800014b7`
- name: `IsUsingWinlogonCreds`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180017400`

## callees

- `0x180001260`
- `0x1800014c0`
- `0x180003bd0`
- `0x180004df0`
- `0x180006a20`
- `0x1800147cc`
- `0x180025efc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800013bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001480`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001498`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800013bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001480`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001498`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001327`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000137f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001327`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000137f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000138d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000138d`
- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_GetConfigForceNotDomainJoined` at `0x180001406`
- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_GetConfigForceNotDomainJoined` at `0x180001406`

## pseudocode

```c
__int64 __fastcall IsUsingWinlogonCreds(unsigned int a1, char a2, const void *a3, unsigned int a4, int *a5)
{
  SIZE_T v5; // rdi
  _DWORD *v9; // rbx
  _QWORD *v10; // rcx
  unsigned int v11; // edi
  _DWORD *v12; // rax
  _DWORD *v13; // r14
  DWORD LastError; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  _DWORD *v17; // rax

  v5 = a4;
  v9 = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 220, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  if ( !a5 )
  {
    v11 = 87;
    goto LABEL_38;
  }
  if ( a1 != 26 )
  {
    v11 = 50;
    if ( v10 != &WPP_GLOBAL_Control )
      WPP_SF_d(v10[2], 221, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids, a1);
    goto LABEL_38;
  }
  if ( v10 != &WPP_GLOBAL_Control )
    WPP_SF_(v10[2], 10, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
  if ( (unsigned int)v5 >= 8 && a3 )
  {
    v12 = LocalAlloc(0x40u, v5);
    v13 = v12;
    if ( !v12 )
    {
      LastError = GetLastError();
      v11 = LastError;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_21;
      v16 = 14;
      goto LABEL_20;
    }
    memcpy_0(v12, a3, v5);
    if ( !(unsigned int)IsLogonCredAllowed() )
      v13[1] &= ~2u;
LABEL_36:
    v9 = v13;
    LocalFree(0);
    v11 = 0;
    goto LABEL_37;
  }
  v17 = LocalAlloc(0x40u, 8u);
  v13 = v17;
  if ( v17 )
  {
    *v17 = 1;
    if ( (unsigned __int8)IsRasChapExt_GetConfigIgnoreIASLogonPresent() )
    {
      if ( !(unsigned int)RasChapExt_GetConfigForceNotDomainJoined() )
        LODWORD(v9) = isMachineJoinedToDomain();
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
    }
    if ( a2 < 0 && ((a2 & 0x20) != 0 || (_DWORD)v9) && (unsigned int)IsLogonCredAllowed() )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
      v13[1] = 2;
    }
    goto LABEL_36;
  }
  LastError = GetLastError();
  v11 = LastError;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_21;
  v16 = 11;
LABEL_20:
  WPP_SF_d(v15[2], v16, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids, LastError);
LABEL_21:
  LocalFree(0);
  if ( !v11 )
  {
LABEL_37:
    *a5 = v9[1] & 2;
    goto LABEL_38;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids, v11);
LABEL_38:
  LocalFree(v9);
  return v11;
}

```

## disassembly

```asm
0x180001260  mov     [rsp+arg_8], rbx
0x180001265  mov     [rsp+arg_10], rbp
0x18000126a  push    rsi
0x18000126b  push    rdi
0x18000126c  push    r12
0x18000126e  push    r13
0x180001270  push    r15
0x180001272  sub     rsp, 20h
0x180001276  mov     edi, r9d
0x180001279  mov     r12, r8
0x18000127c  mov     r15d, edx
0x18000127f  mov     ebp, ecx
0x180001281  xor     ebx, ebx
0x180001283  mov     rcx, cs:WPP_GLOBAL_Control
0x18000128a  lea     r13, WPP_GLOBAL_Control
0x180001291  cmp     rcx, r13
0x180001294  jz      short loc_1800012B2
0x180001296  mov     rcx, [rcx+10h]
0x18000129a  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x1800012a1  mov     edx, 0DCh
0x1800012a6  call    WPP_SF_
0x1800012ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800012b2  mov     rsi, [rsp+48h+arg_20]
0x1800012b7  test    rsi, rsi
0x1800012ba  jnz     short loc_1800012C6
0x1800012bc  mov     edi, 57h ; 'W'
0x1800012c1  jmp     loc_180001495
0x1800012c6  cmp     ebp, 1Ah
0x1800012c9  jz      short loc_1800012F6
0x1800012cb  mov     edi, 32h ; '2'
0x1800012d0  cmp     rcx, r13
0x1800012d3  jz      loc_180001495
0x1800012d9  mov     rcx, [rcx+10h]
0x1800012dd  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x1800012e4  mov     edx, 0DDh
0x1800012e9  mov     r9d, ebp
0x1800012ec  call    WPP_SF_d
0x1800012f1  jmp     loc_180001495
0x1800012f6  cmp     rcx, r13
0x1800012f9  jz      short loc_180001310
0x1800012fb  mov     rcx, [rcx+10h]
0x1800012ff  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x180001306  mov     edx, 0Ah
0x18000130b  call    WPP_SF_
0x180001310  mov     [rsp+48h+arg_0], r14
0x180001315  cmp     edi, 8
0x180001318  jb      short loc_180001375
0x18000131a  test    r12, r12
0x18000131d  jz      short loc_180001375
0x18000131f  mov     rdx, rdi; uBytes
0x180001322  mov     ecx, 40h ; '@'; uFlags
0x180001327  call    cs:__imp_LocalAlloc
0x18000132d  mov     r14, rax
0x180001330  test    rax, rax
0x180001333  jnz     short loc_180001350
0x180001335  call    cs:__imp_GetLastError
0x18000133b  mov     edi, eax
0x18000133d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001344  cmp     rcx, r13
0x180001347  jz      short loc_1800013B9
0x180001349  mov     edx, 0Eh
0x18000134e  jmp     short loc_1800013A6
0x180001350  mov     r8, rdi; Size
0x180001353  mov     rdx, r12; Src
0x180001356  mov     rcx, r14; void *
0x180001359  call    memcpy_0
0x18000135e  call    IsLogonCredAllowed
0x180001363  test    eax, eax
0x180001365  jnz     loc_18000147B
0x18000136b  and     dword ptr [r14+4], 0FFFFFFFDh
0x180001370  jmp     loc_18000147B
0x180001375  mov     edx, 8; uBytes
0x18000137a  mov     ecx, 40h ; '@'; uFlags
0x18000137f  call    cs:__imp_LocalAlloc
0x180001385  mov     r14, rax
0x180001388  test    rax, rax
0x18000138b  jnz     short loc_1800013F7
0x18000138d  call    cs:__imp_GetLastError
0x180001393  mov     edi, eax
0x180001395  mov     rcx, cs:WPP_GLOBAL_Control
0x18000139c  cmp     rcx, r13
0x18000139f  jz      short loc_1800013B9
0x1800013a1  mov     edx, 0Bh
0x1800013a6  mov     rcx, [rcx+10h]
0x1800013aa  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x1800013b1  mov     r9d, eax
0x1800013b4  call    WPP_SF_d
0x1800013b9  mov     rcx, r14; hMem
0x1800013bc  call    cs:__imp_LocalFree
0x1800013c2  test    edi, edi
0x1800013c4  jz      loc_180001488
0x1800013ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800013d1  cmp     rcx, r13
0x1800013d4  jz      loc_180001490
0x1800013da  mov     rcx, [rcx+10h]
0x1800013de  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x1800013e5  mov     edx, 0DEh
0x1800013ea  mov     r9d, edi
0x1800013ed  call    WPP_SF_d
0x1800013f2  jmp     loc_180001490
0x1800013f7  mov     dword ptr [rax], 1
0x1800013fd  call    IsRasChapExt_GetConfigIgnoreIASLogonPresent
0x180001402  test    al, al
0x180001404  jz      short loc_180001419
0x180001406  call    cs:__imp_RasChapExt_GetConfigForceNotDomainJoined
0x18000140c  test    eax, eax
0x18000140e  jnz     short loc_18000143A
0x180001410  call    isMachineJoinedToDomain
0x180001415  mov     ebx, eax
0x180001417  jmp     short loc_18000143A
0x180001419  mov     rcx, cs:WPP_GLOBAL_Control
0x180001420  cmp     rcx, r13
0x180001423  jz      short loc_18000143A
0x180001425  mov     rcx, [rcx+10h]
0x180001429  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x180001430  mov     edx, 0Ch
0x180001435  call    WPP_SF_
0x18000143a  test    r15b, r15b
0x18000143d  jns     short loc_18000147B
0x18000143f  test    r15b, 20h
0x180001443  jnz     short loc_180001449
0x180001445  test    ebx, ebx
0x180001447  jz      short loc_18000147B
0x180001449  call    IsLogonCredAllowed
0x18000144e  test    eax, eax
0x180001450  jz      short loc_18000147B
0x180001452  mov     rcx, cs:WPP_GLOBAL_Control
0x180001459  cmp     rcx, r13
0x18000145c  jz      short loc_180001473
0x18000145e  mov     rcx, [rcx+10h]
0x180001462  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x180001469  mov     edx, 0Dh
0x18000146e  call    WPP_SF_
0x180001473  mov     dword ptr [r14+4], 2
0x18000147b  xor     ecx, ecx; hMem
0x18000147d  mov     rbx, r14
0x180001480  call    cs:__imp_LocalFree
0x180001486  xor     edi, edi
0x180001488  mov     ecx, [rbx+4]
0x18000148b  and     ecx, 2
0x18000148e  mov     [rsi], ecx
0x180001490  mov     r14, [rsp+48h+arg_0]
0x180001495  mov     rcx, rbx; hMem
0x180001498  call    cs:__imp_LocalFree
0x18000149e  mov     rbx, [rsp+48h+arg_8]
0x1800014a3  mov     eax, edi
0x1800014a5  mov     rbp, [rsp+48h+arg_10]
0x1800014aa  add     rsp, 20h
0x1800014ae  pop     r15
0x1800014b0  pop     r13
0x1800014b2  pop     r12
0x1800014b4  pop     rdi
0x1800014b5  pop     rsi
0x1800014b6  retn
```
