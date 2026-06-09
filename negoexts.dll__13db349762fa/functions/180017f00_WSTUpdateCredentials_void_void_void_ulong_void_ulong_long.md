# WSTUpdateCredentials(void * *,void *,void *,ulong,void * *,ulong *,long *)

- ea: `0x180017f00`
- end: `0x18001830e`
- name: `?WSTUpdateCredentials@@YAJPEAPEAXPEAX1K0PEAKPEAJ@Z`
- size: `1038`
- prototype: `__int64 __fastcall(void **, _QWORD *, void *, unsigned int, void **, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update`

## callees

- `0x180008544`
- `0x180008c58`
- `0x18000ca08`
- `0x18000ebcc`
- `0x18000ec28`
- `0x18000ffa4`
- `0x1800157d8`
- `0x180017f00`
- `0x180018464`
- `0x18001a390`
- `0x18001d138`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall WSTUpdateCredentials(
        void **a1,
        _QWORD *a2,
        void *a3,
        unsigned int a4,
        void **a5,
        unsigned int *a6,
        int *a7)
{
  struct _WST_CONTEXT *v9; // r14
  struct _WST_SSP_PACKAGE *v10; // r15
  PVOID *v11; // rcx
  int v12; // ebx
  void *v13; // rcx
  __int64 v14; // rdx
  struct _WST_CONTEXT *v15; // rax
  int v16; // r8d
  __int64 *i; // rdi
  struct _WST_SSP_PACKAGE *v18; // rax
  __int64 (__fastcall *v19)(__int64, _QWORD *, _QWORD, char *); // rax
  _QWORD v21[2]; // [rsp+40h] [rbp-98h] BYREF
  unsigned int *v22; // [rsp+50h] [rbp-88h]
  __int64 *v23; // [rsp+58h] [rbp-80h]
  struct _WST_CONTEXT *v24; // [rsp+60h] [rbp-78h]
  _QWORD *v25; // [rsp+68h] [rbp-70h]
  struct _WST_SSP_PACKAGE *v26; // [rsp+70h] [rbp-68h]
  char *v27; // [rsp+78h] [rbp-60h]
  char *v28; // [rsp+80h] [rbp-58h]
  _OWORD v29[2]; // [rsp+88h] [rbp-50h] BYREF

  memset(v29, 0, sizeof(v29));
  v9 = 0;
  v10 = 0;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a4 >= 0x28
    && *(_DWORD *)a2 == 3
    && *((_WORD *)a2 + 2) >= 0x28u
    && (v22 = (unsigned int *)a2 + 9, *((_DWORD *)a2 + 9) >= (unsigned int)*((unsigned __int16 *)a2 + 2))
    && *((_DWORD *)a2 + 8) <= a4
    && a4 - *((_DWORD *)a2 + 8) >= *((_DWORD *)a2 + 9) )
  {
    v12 = ((__int64 (__fastcall *)(_OWORD *, _QWORD *, void *))basessp::WSTGlobalLsaFunctions->GetClientInfo)(
            v29,
            a2,
            a3);
    if ( v12 < 0 )
    {
LABEL_16:
      v11 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_47;
    }
    v13 = (void *)a2[1];
    if ( v13 )
    {
      v15 = WSTLocateAndReferenceContextByPointer(v13, (struct _LUID *)v29);
      v9 = v15;
      v24 = v15;
      if ( v15 )
      {
        if ( *((_DWORD *)v15 + 39) )
        {
          if ( *(_QWORD *)&v29[0] == *(_QWORD *)(*((_QWORD *)v15 + 3) + 40LL) )
          {
            v25 = a2;
            v28 = (char *)a2 + 36;
            v27 = (char *)(a2 + 4);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              v21[0] = a2 + 2;
              v21[1] = 16;
              WPP_SF_q_HEX_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v16, (_DWORD)v15, (__int64)v21);
            }
            *((_DWORD *)v9 + 64) = 1;
            v21[0] = (char *)v9 + 56;
            for ( i = (__int64 *)*((_QWORD *)v9 + 7); ; i = (__int64 *)*i )
            {
              v23 = i;
              if ( i == (__int64 *)((char *)v9 + 56) )
                break;
              if ( v10 )
                WSTDereferencePackage(v10);
              v18 = WSTLocatePackageByAuthScheme((struct _GUID *)(i + 3));
              v10 = v18;
              v26 = v18;
              if ( v18 )
              {
                v19 = (__int64 (__fastcall *)(__int64, _QWORD *, _QWORD, char *))*((_QWORD *)v18 + 37);
                if ( v19 )
                {
                  v12 = v19(i[5], a2 + 2, *((unsigned int *)a2 + 8), (char *)a2 + *v22);
                  if ( v12 >= 0 )
                  {
                    *((_DWORD *)i + 34) = 0;
                    break;
                  }
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      36,
                      &WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids,
                      (unsigned int)v12,
                      *((_DWORD *)v10 + 6));
                }
              }
            }
            *a5 = 0;
            *a6 = 0;
            goto LABEL_16;
          }
          v11 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids);
            v11 = (PVOID *)WPP_GLOBAL_Control;
          }
          v12 = -1073741816;
        }
        else
        {
          v12 = -1073741811;
          v11 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v14 = 32;
            goto LABEL_15;
          }
        }
      }
      else
      {
        v12 = -1073740755;
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids, a2[1]);
          goto LABEL_16;
        }
      }
    }
    else
    {
      v12 = -1073740755;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v14 = 30;
LABEL_15:
        WPP_SF_(v11[2], v14, &WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids);
        goto LABEL_16;
      }
    }
  }
  else
  {
    v12 = -1073741811;
  }
LABEL_47:
  if ( v9 )
  {
    WSTDereferenceContext(v9);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 )
  {
    WSTDereferencePackage(v10);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
    WPP_SF_d(v11[2], 37, &WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids, (unsigned int)v12);
  *a7 = v12;
  return 0;
}

```

## disassembly

```asm
0x180017f00  mov     rax, rsp
0x180017f03  mov     [rax+8], rbx
0x180017f07  mov     [rax+18h], rsi
0x180017f0b  push    rdi
0x180017f0c  push    r12
0x180017f0e  push    r13
0x180017f10  push    r14
0x180017f12  push    r15
0x180017f14  sub     rsp, 0B0h
0x180017f1b  mov     ebx, r9d
0x180017f1e  mov     rsi, rdx
0x180017f21  xorps   xmm0, xmm0
0x180017f24  movups  xmmword ptr [rax-50h], xmm0
0x180017f28  movups  xmmword ptr [rax-40h], xmm0
0x180017f2c  xor     r14d, r14d
0x180017f2f  xor     r15d, r15d
0x180017f32  lea     r12, WPP_GLOBAL_Control
0x180017f39  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f40  cmp     rcx, r12
0x180017f43  jz      short loc_180017F66
0x180017f45  test    byte ptr [rcx+1Ch], 8
0x180017f49  jz      short loc_180017F66
0x180017f4b  lea     edx, [r14+1Dh]
0x180017f4f  lea     r8, WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids
0x180017f56  mov     rcx, [rcx+10h]
0x180017f5a  call    WPP_SF_
0x180017f5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f66  mov     eax, 28h ; '('
0x180017f6b  cmp     ebx, eax
0x180017f6d  jb      loc_180018295
0x180017f73  cmp     dword ptr [rsi], 3
0x180017f76  jnz     loc_180018295
0x180017f7c  cmp     [rsi+4], ax
0x180017f80  jb      loc_180018295
0x180017f86  lea     r13, [rsi+24h]
0x180017f8a  mov     [rsp+0D8h+var_88], r13
0x180017f8f  movzx   eax, word ptr [rsi+4]
0x180017f93  cmp     [r13+0], eax
0x180017f97  jb      loc_180018295
0x180017f9d  lea     rdi, [rsi+20h]
0x180017fa1  mov     [rsp+0D8h+arg_8], rdi
0x180017fa9  cmp     [rdi], ebx
0x180017fab  ja      loc_180018295
0x180017fb1  sub     ebx, [rdi]
0x180017fb3  cmp     ebx, [r13+0]
0x180017fb7  jb      loc_180018295
0x180017fbd  mov     rax, cs:?WSTGlobalLsaFunctions@basessp@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * basessp::WSTGlobalLsaFunctions
0x180017fc4  lea     rcx, [rsp+0D8h+var_50]
0x180017fcc  mov     rax, [rax+80h]
0x180017fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fd8  mov     ebx, eax
0x180017fda  test    eax, eax
0x180017fdc  js      short loc_18001801B
0x180017fde  mov     rcx, [rsi+8]; void *
0x180017fe2  test    rcx, rcx
0x180017fe5  jnz     short loc_180018027
0x180017fe7  mov     ebx, 0C000042Dh
0x180017fec  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ff3  cmp     rcx, r12
0x180017ff6  jz      loc_18001829A
0x180017ffc  test    byte ptr [rcx+1Ch], 4
0x180018000  jz      loc_18001829A
0x180018006  mov     edx, 1Eh
0x18001800b  lea     r8, WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids
0x180018012  mov     rcx, [rcx+10h]
0x180018016  call    WPP_SF_
0x18001801b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018022  jmp     loc_18001829A
0x180018027  lea     rdx, [rsp+0D8h+var_50]; struct _LUID *
0x18001802f  call    ?WSTLocateAndReferenceContextByPointer@@YAPEAU_WST_CONTEXT@@PEAXPEAU_LUID@@@Z; WSTLocateAndReferenceContextByPointer(void *,_LUID *)
0x180018034  mov     r14, rax
0x180018037  mov     [rsp+0D8h+var_78], rax
0x18001803c  test    rax, rax
0x18001803f  jnz     short loc_180018079
0x180018041  mov     ebx, 0C000042Dh
0x180018046  mov     rcx, cs:WPP_GLOBAL_Control
0x18001804d  cmp     rcx, r12
0x180018050  jz      loc_18001829A
0x180018056  test    byte ptr [rcx+1Ch], 4
0x18001805a  jz      loc_18001829A
0x180018060  lea     edx, [rax+1Fh]
0x180018063  mov     r9, [rsi+8]
0x180018067  lea     r8, WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids
0x18001806e  mov     rcx, [rcx+10h]
0x180018072  call    WPP_SF_q
0x180018077  jmp     short loc_18001801B
0x180018079  cmp     [rax+9Ch], r15d
0x180018080  jnz     short loc_1800180AB
0x180018082  mov     ebx, 0C000000Dh
0x180018087  mov     rcx, cs:WPP_GLOBAL_Control
0x18001808e  cmp     rcx, r12
0x180018091  jz      loc_18001829A
0x180018097  test    byte ptr [rcx+1Ch], 1
0x18001809b  jz      loc_18001829A
0x1800180a1  mov     edx, 20h ; ' '
0x1800180a6  jmp     loc_18001800B
0x1800180ab  mov     rcx, [rax+18h]
0x1800180af  mov     eax, dword ptr [rsp+0D8h+var_50]
0x1800180b6  cmp     eax, [rcx+28h]
0x1800180b9  jnz     loc_180018260
0x1800180bf  mov     eax, dword ptr [rsp+0D8h+var_50+4]
0x1800180c6  cmp     eax, [rcx+2Ch]
0x1800180c9  jnz     loc_180018260
0x1800180cf  mov     [rsp+0D8h+var_70], rsi
0x1800180d4  mov     [rsp+0D8h+var_58], r13
0x1800180dc  mov     [rsp+0D8h+var_60], rdi
0x1800180e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800180e8  cmp     rcx, r12
0x1800180eb  jz      short loc_18001812E
0x1800180ed  mov     edx, 10h
0x1800180f2  test    [rcx+1Ch], dl
0x1800180f5  jz      short loc_18001812E
0x1800180f7  xorps   xmm0, xmm0
0x1800180fa  movups  [rsp+0D8h+var_98], xmm0
0x1800180ff  lea     rax, [rsi+10h]
0x180018103  mov     qword ptr [rsp+0D8h+var_98], rax
0x180018108  mov     word ptr [rsp+0D8h+var_98+8], dx
0x18001810d  movaps  xmm0, [rsp+0D8h+var_98]
0x180018112  movdqa  [rsp+0D8h+var_98], xmm0
0x180018118  lea     rax, [rsp+0D8h+var_98]
0x18001811d  mov     [rsp+0D8h+var_B8], rax
0x180018122  mov     r9, r14
0x180018125  mov     rcx, [rcx+10h]
0x180018129  call    WPP_SF_q_HEX_
0x18001812e  mov     dword ptr [r14+100h], 1
0x180018139  lea     r13, [r14+38h]
0x18001813d  mov     qword ptr [rsp+0D8h+var_98], r13
0x180018142  mov     rdi, [r13+0]
0x180018146  mov     [rsp+0D8h+var_80], rdi
0x18001814b  cmp     rdi, r13
0x18001814e  jz      loc_180018204
0x180018154  test    r15, r15
0x180018157  jz      short loc_180018161
0x180018159  mov     rcx, r15; struct _WST_SSP_PACKAGE *
0x18001815c  call    ?WSTDereferencePackage@@YAXPEAU_WST_SSP_PACKAGE@@@Z; WSTDereferencePackage(_WST_SSP_PACKAGE *)
0x180018161  lea     rcx, [rdi+18h]; struct _GUID *
0x180018165  call    ?WSTLocatePackageByAuthScheme@@YAPEAU_WST_SSP_PACKAGE@@PEAU_GUID@@@Z; WSTLocatePackageByAuthScheme(_GUID *)
0x18001816a  mov     r15, rax
0x18001816d  mov     [rsp+0D8h+var_68], rax
0x180018172  test    rax, rax
0x180018175  jz      loc_180018258
0x18001817b  mov     rax, [rax+128h]
0x180018182  test    rax, rax
0x180018185  jz      loc_180018258
0x18001818b  mov     rcx, [rsp+0D8h+var_88]
0x180018190  mov     r9d, [rcx]
0x180018193  add     r9, rsi
0x180018196  lea     rdx, [rsi+10h]
0x18001819a  mov     rcx, [rsp+0D8h+arg_8]
0x1800181a2  mov     r8d, [rcx]
0x1800181a5  mov     rcx, [rdi+28h]
0x1800181a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181ae  mov     ebx, eax
0x1800181b0  mov     [rsp+0D8h+var_A8], eax
0x1800181b4  jmp     short loc_1800181F6
0x1800181b6  mov     ebx, eax
0x1800181b8  mov     [rsp+0D8h+var_A8], eax
0x1800181bc  lea     r12, WPP_GLOBAL_Control
0x1800181c3  mov     r14, [rsp+0D8h+var_78]
0x1800181c8  mov     rsi, [rsp+0D8h+var_70]
0x1800181cd  mov     r15, [rsp+0D8h+var_68]
0x1800181d2  mov     rdi, [rsp+0D8h+var_80]
0x1800181d7  mov     r13, qword ptr [rsp+0D8h+var_98]
0x1800181dc  mov     rax, [rsp+0D8h+var_60]
0x1800181e1  mov     [rsp+0D8h+arg_8], rax
0x1800181e9  mov     rax, [rsp+0D8h+var_58]
0x1800181f1  mov     [rsp+0D8h+var_88], rax
0x1800181f6  test    ebx, ebx
0x1800181f8  js      short loc_180018226
0x1800181fa  mov     dword ptr [rdi+88h], 0
0x180018204  mov     rax, [rsp+0D8h+arg_20]
0x18001820c  mov     qword ptr [rax], 0
0x180018213  mov     rax, [rsp+0D8h+arg_28]
0x18001821b  mov     dword ptr [rax], 0
0x180018221  jmp     loc_18001801B
0x180018226  mov     rcx, cs:WPP_GLOBAL_Control
0x18001822d  cmp     rcx, r12
0x180018230  jz      short loc_180018258
0x180018232  test    byte ptr [rcx+1Ch], 2
0x180018236  jz      short loc_180018258
0x180018238  mov     edx, 24h ; '$'
0x18001823d  mov     eax, [r15+18h]
0x180018241  mov     dword ptr [rsp+0D8h+var_B8], eax
0x180018245  mov     r9d, ebx
0x180018248  lea     r8, WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids
0x18001824f  mov     rcx, [rcx+10h]
0x180018253  call    WPP_SF_Dd
0x180018258  mov     rdi, [rdi]
0x18001825b  jmp     loc_180018146
0x180018260  mov     rcx, cs:WPP_GLOBAL_Control
0x180018267  cmp     rcx, r12
0x18001826a  jz      short loc_18001828E
0x18001826c  test    byte ptr [rcx+1Ch], 1
0x180018270  jz      short loc_18001828E
0x180018272  mov     edx, 21h ; '!'
0x180018277  lea     r8, WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids
0x18001827e  mov     rcx, [rcx+10h]
0x180018282  call    WPP_SF_
0x180018287  mov     rcx, cs:WPP_GLOBAL_Control
0x18001828e  mov     ebx, 0C0000008h
0x180018293  jmp     short loc_18001829A
0x180018295  mov     ebx, 0C000000Dh
0x18001829a  test    r14, r14
0x18001829d  jz      short loc_1800182AE
0x18001829f  mov     rcx, r14; struct _WST_CONTEXT *
0x1800182a2  call    ?WSTDereferenceContext@@YAXPEAU_WST_CONTEXT@@@Z; WSTDereferenceContext(_WST_CONTEXT *)
0x1800182a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182ae  test    r15, r15
0x1800182b1  jz      short loc_1800182C2
0x1800182b3  mov     rcx, r15; struct _WST_SSP_PACKAGE *
0x1800182b6  call    ?WSTDereferencePackage@@YAXPEAU_WST_SSP_PACKAGE@@@Z; WSTDereferencePackage(_WST_SSP_PACKAGE *)
0x1800182bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182c2  cmp     rcx, r12
0x1800182c5  jz      short loc_1800182E5
0x1800182c7  test    byte ptr [rcx+1Ch], 8
0x1800182cb  jz      short loc_1800182E5
0x1800182cd  mov     edx, 25h ; '%'
0x1800182d2  mov     r9d, ebx
0x1800182d5  lea     r8, WPP_79cd0cb52f28304afeecba35f69b4115_Traceguids
0x1800182dc  mov     rcx, [rcx+10h]
0x1800182e0  call    WPP_SF_d
0x1800182e5  mov     rax, [rsp+0D8h+arg_30]
0x1800182ed  mov     [rax], ebx
0x1800182ef  xor     eax, eax
0x1800182f1  lea     r11, [rsp+0D8h+var_28]
0x1800182f9  mov     rbx, [r11+30h]
0x1800182fd  mov     rsi, [r11+40h]
0x180018301  mov     rsp, r11
0x180018304  pop     r15
0x180018306  pop     r14
0x180018308  pop     r13
0x18001830a  pop     r12
0x18001830c  pop     rdi
0x18001830d  retn
0x18001f2e6  push    rbp
0x18001f2e8  sub     rsp, 30h
0x18001f2ec  mov     rbp, rdx
0x18001f2ef  call    ?WSTExceptionFilter@@YAKXZ; WSTExceptionFilter(void)
0x18001f2f4  nop
0x18001f2f5  add     rsp, 30h
0x18001f2f9  pop     rbp
0x18001f2fa  retn
```
