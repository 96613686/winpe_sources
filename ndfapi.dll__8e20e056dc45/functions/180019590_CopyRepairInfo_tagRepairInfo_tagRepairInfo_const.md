# CopyRepairInfo(tagRepairInfo *,tagRepairInfo const *)

- ea: `0x180019590`
- end: `0x180019773`
- name: `?CopyRepairInfo@@YAJPEAUtagRepairInfo@@PEBU1@@Z`
- size: `483`
- prototype: `__int64 __fastcall(struct tagRepairInfo *, const struct tagRepairInfo *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001922c`
- `0x18001977c`

## callees

- `0x180008b08`
- `0x180009a9c`
- `0x180019590`
- `0x18001ad20`
- `0x18001f690`

## pseudocode

```c
__int64 __fastcall CopyRepairInfo(struct tagRepairInfo *a1, const struct tagRepairInfo *a2, const unsigned __int16 *a3)
{
  __int64 v5; // rcx
  UiInfo *p_UiInfo; // rax
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm0
  const unsigned __int16 *pwszClassName; // r9
  int v13; // ebx
  const unsigned __int16 *pwszDescription; // r8
  UI_INFO_TYPE type; // eax
  const unsigned __int16 *pwszDirectory; // r9
  const unsigned __int16 *pwszFile; // r9
  const unsigned __int16 *pwzNull; // r9
  const unsigned __int16 *pwszParameters; // r9
  const unsigned __int16 *v21; // r9
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  unsigned __int8 v28; // [rsp+20h] [rbp-49h]
  unsigned int v29; // [rsp+28h] [rbp-41h]
  tagRepairInfo pv; // [rsp+30h] [rbp-39h] BYREF

  if ( a1 && a2 )
  {
    v5 = 48;
    p_UiInfo = &pv.UiInfo;
    v7 = *(_OWORD *)&a2->risk;
    pv.guid = a2->guid;
    v8 = *(_OWORD *)&a2->sidType;
    *(_OWORD *)&pv.risk = v7;
    v9 = *((_OWORD *)&a2->UiInfo.pwzDui + 1);
    *(_OWORD *)&pv.sidType = v8;
    v10 = *(_OWORD *)&a2->UiInfo.pwzNull;
    *((_OWORD *)&pv.UiInfo.pwzDui + 1) = v9;
    *(_OWORD *)&pv.UiInfo.pwzNull = v10;
    v11 = *((_OWORD *)&a2->UiInfo.pwzDui + 2);
    *(_OWORD *)&pv.pwszClassName = 0;
    *((_OWORD *)&pv.UiInfo.pwzDui + 2) = v11;
    do
    {
      LOBYTE(p_UiInfo->type) = 0;
      p_UiInfo = (UiInfo *)((char *)p_UiInfo + 1);
      --v5;
    }
    while ( v5 );
    pwszClassName = a2->pwszClassName;
    v13 = 0;
    if ( !pwszClassName
      || (v13 = UtilAssembleStringsWithAlloc(&pv.pwszClassName, (unsigned int)a2, a3, pwszClassName, v28, v29), v13 >= 0) )
    {
      pwszDescription = a2->pwszDescription;
      if ( !pwszDescription || (v13 = UtilStringCopyWithAlloc(&pv.pwszDescription, 0xFFFFu, pwszDescription), v13 >= 0) )
      {
        type = a2->UiInfo.type;
        pv.UiInfo.type = type;
        if ( type == UIT_SHELL_COMMAND )
        {
          pwszDirectory = a2->UiInfo.ShellInfo.pwszDirectory;
          if ( !pwszDirectory
            || (v13 = UtilAssembleStringsWithAlloc(
                        &pv.UiInfo.ShellInfo.pwszDirectory,
                        (unsigned int)a2,
                        pwszDescription,
                        pwszDirectory,
                        v28,
                        v29),
                v13 >= 0) )
          {
            pwszFile = a2->UiInfo.ShellInfo.pwszFile;
            if ( !pwszFile
              || (v13 = UtilAssembleStringsWithAlloc(
                          &pv.UiInfo.ShellInfo.pwszFile,
                          (unsigned int)a2,
                          pwszDescription,
                          pwszFile,
                          v28,
                          v29),
                  v13 >= 0) )
            {
              pwzNull = a2->UiInfo.pwzNull;
              if ( !pwzNull
                || (v13 = UtilAssembleStringsWithAlloc(
                            &pv.UiInfo.pwzNull,
                            (unsigned int)a2,
                            pwszDescription,
                            pwzNull,
                            v28,
                            v29),
                    v13 >= 0) )
              {
                pwszParameters = a2->UiInfo.ShellInfo.pwszParameters;
                if ( !pwszParameters
                  || (v13 = UtilAssembleStringsWithAlloc(
                              &pv.UiInfo.ShellInfo.pwszParameters,
                              (unsigned int)a2,
                              pwszDescription,
                              pwszParameters,
                              v28,
                              v29),
                      v13 >= 0) )
                {
                  pv.UiInfo.ShellInfo.nShowCmd = a2->UiInfo.ShellInfo.nShowCmd;
LABEL_26:
                  v22 = *(_OWORD *)&pv.pwszClassName;
                  a1->guid = pv.guid;
                  v23 = *(_OWORD *)&pv.sidType;
                  *(_OWORD *)&a1->pwszClassName = v22;
                  v24 = *(_OWORD *)&pv.risk;
                  *(_OWORD *)&a1->sidType = v23;
                  v25 = *(_OWORD *)&pv.UiInfo.pwzNull;
                  *(_OWORD *)&a1->risk = v24;
                  v26 = *((_OWORD *)&pv.UiInfo.pwzDui + 1);
                  *(_OWORD *)&a1->UiInfo.pwzNull = v25;
                  v27 = *((_OWORD *)&pv.UiInfo.pwzDui + 2);
                  *((_OWORD *)&a1->UiInfo.pwzDui + 1) = v26;
                  *((_OWORD *)&a1->UiInfo.pwzDui + 2) = v27;
                  return (unsigned int)v13;
                }
              }
            }
          }
        }
        else
        {
          if ( type != UIT_HELP_PANE && type != UIT_DUI )
            goto LABEL_26;
          v21 = a2->UiInfo.pwzNull;
          if ( !v21 )
            goto LABEL_26;
          v13 = UtilAssembleStringsWithAlloc(&pv.UiInfo.pwzNull, (unsigned int)a2, pwszDescription, v21, v28, v29);
          if ( v13 >= 0 )
            goto LABEL_26;
        }
      }
    }
    FreeRepairInfos(&pv, 1u, 0);
    return (unsigned int)v13;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180019590  mov     [rsp-8+arg_10], rbx
0x180019595  mov     [rsp-8+arg_18], rsi
0x18001959a  push    rbp
0x18001959b  push    rdi
0x18001959c  push    r14
0x18001959e  lea     rbp, [rsp-47h]
0x1800195a3  sub     rsp, 0B0h
0x1800195aa  mov     rax, cs:__security_cookie
0x1800195b1  xor     rax, rsp
0x1800195b4  mov     [rbp+57h+var_20], rax
0x1800195b8  mov     rdi, rdx
0x1800195bb  mov     rsi, rcx
0x1800195be  test    rcx, rcx
0x1800195c1  jz      loc_18001974A
0x1800195c7  test    rdx, rdx
0x1800195ca  jz      loc_18001974A
0x1800195d0  movups  xmm0, xmmword ptr [rdx]
0x1800195d3  mov     ecx, 30h ; '0'
0x1800195d8  lea     rax, [rbp+57h+pv.UiInfo]
0x1800195dc  movups  xmm1, xmmword ptr [rdx+30h]
0x1800195e0  movaps  xmmword ptr [rbp+57h+pv.guid.Data1], xmm0
0x1800195e4  movups  xmm0, xmmword ptr [rdx+20h]
0x1800195e8  lea     r14d, [rcx-2Fh]
0x1800195ec  movaps  xmmword ptr [rbp-9], xmm1
0x1800195f0  movups  xmm1, xmmword ptr [rdx+50h]
0x1800195f4  movaps  xmmword ptr [rbp+57h+pv.sidType], xmm0
0x1800195f8  movups  xmm0, xmmword ptr [rdx+40h]
0x1800195fc  movaps  xmmword ptr [rbp+57h+pv.UiInfo.8+10h], xmm1
0x180019600  xorps   xmm1, xmm1
0x180019603  movaps  xmmword ptr [rbp+57h+pv.UiInfo.8], xmm0
0x180019607  movups  xmm0, xmmword ptr [rdx+60h]
0x18001960b  movdqa  xmmword ptr [rbp+57h+pv.pwszClassName], xmm1
0x180019610  movaps  xmmword ptr [rbp+57h+pv.UiInfo.8+20h], xmm0
0x180019614  mov     byte ptr [rax], 0
0x180019617  add     rax, r14
0x18001961a  sub     rcx, r14
0x18001961d  jnz     short loc_180019614
0x18001961f  mov     r9, [rdx+10h]; unsigned __int16 *
0x180019623  xor     ebx, ebx
0x180019625  test    r9, r9
0x180019628  jz      short loc_18001964F
0x18001962a  lea     rcx, [rbp+57h+pv.pwszClassName]; unsigned __int16 **
0x18001962e  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x180019633  mov     ebx, eax
0x180019635  test    eax, eax
0x180019637  jns     short loc_18001964F
0x180019639  xor     r8d, r8d; int
0x18001963c  lea     rcx, [rbp+57h+pv]; pv
0x180019640  mov     edx, r14d; unsigned int
0x180019643  call    ?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z; FreeRepairInfos(tagRepairInfo *,ulong,int)
0x180019648  mov     eax, ebx
0x18001964a  jmp     loc_18001974F
0x18001964f  mov     r8, [rdi+18h]; unsigned __int16 *
0x180019653  test    r8, r8
0x180019656  jz      short loc_18001966C
0x180019658  mov     edx, 0FFFFh; unsigned int
0x18001965d  lea     rcx, [rbp+57h+pv.pwszDescription]; unsigned __int16 **
0x180019661  call    ?UtilStringCopyWithAlloc@@YAJPEAPEAGIPEBG@Z; UtilStringCopyWithAlloc(ushort * *,uint,ushort const *)
0x180019666  mov     ebx, eax
0x180019668  test    eax, eax
0x18001966a  js      short loc_180019639
0x18001966c  mov     eax, [rdi+38h]
0x18001966f  mov     [rbp+57h+pv.UiInfo.type], eax
0x180019672  cmp     eax, 2
0x180019675  jnz     short loc_1800196E7
0x180019677  mov     r9, [rdi+58h]; unsigned __int16 *
0x18001967b  test    r9, r9
0x18001967e  jz      short loc_18001968F
0x180019680  lea     rcx, [rbp+57h+pv.UiInfo.8+18h]; unsigned __int16 **
0x180019684  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x180019689  mov     ebx, eax
0x18001968b  test    eax, eax
0x18001968d  js      short loc_180019639
0x18001968f  mov     r9, [rdi+48h]; unsigned __int16 *
0x180019693  test    r9, r9
0x180019696  jz      short loc_1800196A7
0x180019698  lea     rcx, [rbp+57h+pv.UiInfo.8+8]; unsigned __int16 **
0x18001969c  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x1800196a1  mov     ebx, eax
0x1800196a3  test    eax, eax
0x1800196a5  js      short loc_180019639
0x1800196a7  mov     r9, [rdi+40h]; unsigned __int16 *
0x1800196ab  test    r9, r9
0x1800196ae  jz      short loc_1800196C3
0x1800196b0  lea     rcx, [rbp+57h+pv.UiInfo.8]; unsigned __int16 **
0x1800196b4  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x1800196b9  mov     ebx, eax
0x1800196bb  test    eax, eax
0x1800196bd  js      loc_180019639
0x1800196c3  mov     r9, [rdi+50h]; unsigned __int16 *
0x1800196c7  test    r9, r9
0x1800196ca  jz      short loc_1800196DF
0x1800196cc  lea     rcx, [rbp+57h+pv.UiInfo.8+10h]; unsigned __int16 **
0x1800196d0  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x1800196d5  mov     ebx, eax
0x1800196d7  test    eax, eax
0x1800196d9  js      loc_180019639
0x1800196df  mov     eax, [rdi+60h]
0x1800196e2  mov     dword ptr [rbp+57h+pv.UiInfo.8+20h], eax
0x1800196e5  jmp     short loc_18001970E
0x1800196e7  cmp     eax, 3
0x1800196ea  jnz     short loc_180019709
0x1800196ec  mov     r9, [rdi+40h]; unsigned __int16 *
0x1800196f0  test    r9, r9
0x1800196f3  jz      short loc_18001970E
0x1800196f5  lea     rcx, [rbp+57h+pv.UiInfo.8]; unsigned __int16 **
0x1800196f9  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x1800196fe  mov     ebx, eax
0x180019700  test    eax, eax
0x180019702  jns     short loc_18001970E
0x180019704  jmp     loc_180019639
0x180019709  cmp     eax, 4
0x18001970c  jz      short loc_1800196EC
0x18001970e  movaps  xmm0, xmmword ptr [rbp+57h+pv.guid.Data1]
0x180019712  movaps  xmm1, xmmword ptr [rbp+57h+pv.pwszClassName]
0x180019716  movups  xmmword ptr [rsi], xmm0
0x180019719  movaps  xmm0, xmmword ptr [rbp+57h+pv.sidType]
0x18001971d  movups  xmmword ptr [rsi+10h], xmm1
0x180019721  movaps  xmm1, xmmword ptr [rbp-9]
0x180019725  movups  xmmword ptr [rsi+20h], xmm0
0x180019729  movaps  xmm0, xmmword ptr [rbp+57h+pv.UiInfo.8]
0x18001972d  movups  xmmword ptr [rsi+30h], xmm1
0x180019731  movaps  xmm1, xmmword ptr [rbp+57h+pv.UiInfo.8+10h]
0x180019735  movups  xmmword ptr [rsi+40h], xmm0
0x180019739  movaps  xmm0, xmmword ptr [rbp+57h+pv.UiInfo.8+20h]
0x18001973d  movups  xmmword ptr [rsi+50h], xmm1
0x180019741  movups  xmmword ptr [rsi+60h], xmm0
0x180019745  jmp     loc_180019648
0x18001974a  mov     eax, 80070057h
0x18001974f  mov     rcx, [rbp+57h+var_20]
0x180019753  xor     rcx, rsp; StackCookie
0x180019756  call    __security_check_cookie
0x18001975b  lea     r11, [rsp+0C0h+var_10]
0x180019763  mov     rbx, [r11+30h]
0x180019767  mov     rsi, [r11+38h]
0x18001976b  mov     rsp, r11
0x18001976e  pop     r14
0x180019770  pop     rdi
0x180019771  pop     rbp
0x180019772  retn
```
