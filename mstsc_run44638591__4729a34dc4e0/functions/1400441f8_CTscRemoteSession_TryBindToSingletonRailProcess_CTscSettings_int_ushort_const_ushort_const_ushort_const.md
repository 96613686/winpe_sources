# CTscRemoteSession::TryBindToSingletonRailProcess(CTscSettings *,int,ushort const *,ushort const *,ushort const *)

- ea: `0x1400441f8`
- end: `0x14004466c`
- name: `?TryBindToSingletonRailProcess@CTscRemoteSession@@QEAAJPEAVCTscSettings@@HPEBG11@Z`
- size: `1140`
- prototype: `int(CTscRemoteSession *__hidden this, struct CTscSettings *, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400647f0`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000d078`
- `0x140038190`
- `0x1400441f8`
- `0x1400b4c1c`
- `0x1400b69b4`
- `0x140113390`

## import_xrefs

- `KERNEL32!GetCurrentDirectoryW` at `0x14004431e`
- `KERNEL32!GetCurrentDirectoryW` at `0x14004431e`
- `KERNEL32!GetLastError` at `0x140044347`
- `KERNEL32!GetLastError` at `0x140044377`
- `KERNEL32!GetLastError` at `0x140044347`
- `KERNEL32!GetLastError` at `0x140044377`
- `OLEAUT32!__imp_SysAllocString` at `0x140044398`
- `OLEAUT32!__imp_SysAllocString` at `0x140044405`
- `OLEAUT32!__imp_SysAllocString` at `0x140044472`
- `OLEAUT32!__imp_SysAllocString` at `0x1400444dd`
- `OLEAUT32!__imp_SysAllocString` at `0x140044545`
- `OLEAUT32!__imp_SysAllocString` at `0x140044398`
- `OLEAUT32!__imp_SysAllocString` at `0x140044405`
- `OLEAUT32!__imp_SysAllocString` at `0x140044472`
- `OLEAUT32!__imp_SysAllocString` at `0x1400444dd`
- `OLEAUT32!__imp_SysAllocString` at `0x140044545`
- `OLEAUT32!__imp_SysFreeString` at `0x140044620`
- `OLEAUT32!__imp_SysFreeString` at `0x140044629`
- `OLEAUT32!__imp_SysFreeString` at `0x140044632`
- `OLEAUT32!__imp_SysFreeString` at `0x14004463b`
- `OLEAUT32!__imp_SysFreeString` at `0x140044649`
- `OLEAUT32!__imp_SysFreeString` at `0x140044620`
- `OLEAUT32!__imp_SysFreeString` at `0x140044629`
- `OLEAUT32!__imp_SysFreeString` at `0x140044632`
- `OLEAUT32!__imp_SysFreeString` at `0x14004463b`
- `OLEAUT32!__imp_SysFreeString` at `0x140044649`

## string_xrefs

- `0x1400445e7`: `CTscComHelper::StartRemoteApplication failed!`

## pseudocode

```c
__int64 __fastcall CTscRemoteSession::TryBindToSingletonRailProcess(
        CTscRemoteSession *this,
        struct CTscSettings *a2,
        int a3,
        const unsigned __int16 *a4,
        OLECHAR *psz,
        OLECHAR *a6)
{
  signed int started; // ebx
  int v9; // r8d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  DWORD LastError; // ebx
  unsigned int v13; // eax
  signed int v14; // eax
  unsigned __int16 *v15; // r12
  unsigned int v16; // eax
  OLECHAR *v17; // rdi
  unsigned __int16 *v18; // r15
  unsigned int v19; // eax
  unsigned __int16 *v20; // r14
  unsigned int v21; // eax
  unsigned __int16 *v22; // rsi
  unsigned int v23; // eax
  unsigned __int16 *v24; // rax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+30h] [rbp-D0h] BYREF
  int v29[3]; // [rsp+34h] [rbp-CCh] BYREF
  OLECHAR v30[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp+150h] BYREF

  v28 = 0;
  v29[0] = 0;
  started = CTscSettings::LoadConnectionSharingSettings(a2, &v28, v29, v30, v27);
  if ( started < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        (unsigned int)WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"LoadConnectionSharingSettings failed",
        started);
    }
    goto LABEL_61;
  }
  if ( !a3 )
    return 0;
  if ( v28 )
  {
    if ( v29[0] )
      return 0;
  }
  else if ( !v30[0] )
  {
    return 0;
  }
  if ( GetCurrentDirectoryW(0x104u, Buffer) )
  {
    v15 = SysAllocString(a4);
    if ( !v15 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          (unsigned int)WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids,
          v16,
          (__int64)"BSTR");
      }
      started = -2147024882;
      goto LABEL_61;
    }
    v17 = 0;
    v18 = SysAllocString(psz);
    if ( v18 )
    {
      v20 = SysAllocString(Buffer);
      if ( v20 )
      {
        v22 = SysAllocString(v30);
        if ( v22 )
        {
          v24 = SysAllocString(a6);
          v17 = v24;
          if ( v24 )
          {
            started = CTscComHelper::StartRemoteApplication(v15, v18, v20, v22, v24);
            if ( started >= 0 )
            {
              started = 262656;
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v26 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                54,
                (unsigned int)WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids,
                v26,
                (__int64)"CTscComHelper::StartRemoteApplication failed!",
                started);
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v25 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Ds(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                53,
                (unsigned int)WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids,
                v25,
                (__int64)"BSTR");
            }
            started = -2147024882;
          }
          SysFreeString(v22);
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v23 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Ds(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              52,
              (unsigned int)WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids,
              v23,
              (__int64)"BSTR");
          }
          started = -2147024882;
        }
        SysFreeString(v20);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v21 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            (unsigned int)WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids,
            v21,
            (__int64)"BSTR");
        }
        started = -2147024882;
      }
      SysFreeString(v18);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          (unsigned int)WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids,
          v19,
          (__int64)"BSTR");
      }
      started = -2147024882;
    }
    SysFreeString(v15);
    if ( v17 )
      SysFreeString(v17);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids,
        v13,
        LastError);
    }
    v14 = GetLastError();
    started = v14;
    if ( v14 > 0 )
      started = (unsigned __int16)v14 | 0x80070000;
  }
  if ( started < 0 )
LABEL_61:
    CSharedSH::SH_DisplayMsgBox(0, 0x33F5u, v9, 1);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1400441f8  mov     [rsp-8+arg_0], rbx
0x1400441fd  push    rbp
0x1400441fe  push    rsi
0x1400441ff  push    rdi
0x140044200  push    r12
0x140044202  push    r13
0x140044204  push    r14
0x140044206  push    r15
0x140044208  lea     rbp, [rsp-370h]
0x140044210  sub     rsp, 470h
0x140044217  mov     rax, cs:__security_cookie
0x14004421e  xor     rax, rsp
0x140044221  mov     [rbp+3A0h+var_40], rax
0x140044228  mov     r14, [rbp+3A0h+psz]
0x14004422f  mov     rsi, r9
0x140044232  mov     r13, [rbp+3A0h+arg_28]
0x140044239  lea     r9, [rsp+4A0h+var_460]; unsigned __int16 *
0x14004423e  mov     edi, r8d
0x140044241  mov     rcx, rdx; this
0x140044244  xor     r15d, r15d
0x140044247  lea     r8, [rsp+4A0h+var_46C]; int *
0x14004424c  lea     rdx, [rsp+4A0h+var_470]; int *
0x140044251  mov     [rsp+4A0h+var_470], r15d
0x140044256  mov     [rsp+4A0h+var_46C], r15d
0x14004425b  call    ?LoadConnectionSharingSettings@CTscSettings@@QEAAJPEAH0PEAGI@Z; CTscSettings::LoadConnectionSharingSettings(int *,int *,ushort *,uint)
0x140044260  mov     ebx, eax
0x140044262  test    eax, eax
0x140044264  jns     short loc_1400442C9
0x140044266  mov     rcx, cs:WPP_GLOBAL_Control
0x14004426d  lea     rax, WPP_GLOBAL_Control
0x140044274  cmp     rcx, rax
0x140044277  jz      loc_140044657
0x14004427d  test    byte ptr [rcx+1Ch], 8
0x140044281  jz      loc_140044657
0x140044287  cmp     byte ptr [rcx+19h], 2
0x14004428b  jb      loc_140044657
0x140044291  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140044296  lea     rcx, aLoadconnection; "LoadConnectionSharingSettings failed"
0x14004429d  mov     [rsp+4A0h+var_478], ebx
0x1400442a1  mov     [rsp+4A0h+var_480], rcx
0x1400442a6  lea     edx, [r15+2Fh]
0x1400442aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400442b1  lea     r8, WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids
0x1400442b8  mov     r9d, eax
0x1400442bb  mov     rcx, [rcx+10h]
0x1400442bf  call    WPP_SF_DsD
0x1400442c4  jmp     loc_140044657
0x1400442c9  test    edi, edi
0x1400442cb  jz      short loc_1400442DB
0x1400442cd  cmp     [rsp+4A0h+var_470], r15d
0x1400442d2  jz      short loc_14004430A
0x1400442d4  cmp     [rsp+4A0h+var_46C], r15d
0x1400442d9  jz      short loc_140044312
0x1400442db  mov     ebx, r15d
0x1400442de  mov     eax, ebx
0x1400442e0  mov     rcx, [rbp+3A0h+var_40]
0x1400442e7  xor     rcx, rsp; StackCookie
0x1400442ea  call    __security_check_cookie
0x1400442ef  mov     rbx, [rsp+4A0h+arg_0]
0x1400442f7  add     rsp, 470h
0x1400442fe  pop     r15
0x140044300  pop     r14
0x140044302  pop     r13
0x140044304  pop     r12
0x140044306  pop     rdi
0x140044307  pop     rsi
0x140044308  pop     rbp
0x140044309  retn
0x14004430a  cmp     [rsp+4A0h+var_460], r15w
0x140044310  jz      short loc_1400442DB
0x140044312  lea     rdx, [rbp+3A0h+Buffer]; lpBuffer
0x140044319  mov     ecx, 104h; nBufferLength
0x14004431e  call    cs:__imp_GetCurrentDirectoryW
0x140044324  test    eax, eax
0x140044326  jnz     short loc_140044395
0x140044328  mov     rcx, cs:WPP_GLOBAL_Control
0x14004432f  lea     rax, WPP_GLOBAL_Control
0x140044336  cmp     rcx, rax
0x140044339  jz      short loc_140044377
0x14004433b  test    byte ptr [rcx+1Ch], 1
0x14004433f  jz      short loc_140044377
0x140044341  cmp     byte ptr [rcx+19h], 2
0x140044345  jb      short loc_140044377
0x140044347  call    cs:__imp_GetLastError
0x14004434d  mov     ebx, eax
0x14004434f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140044354  mov     rcx, cs:WPP_GLOBAL_Control
0x14004435b  lea     r8, WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids
0x140044362  mov     edx, 30h ; '0'
0x140044367  mov     dword ptr [rsp+4A0h+var_480], ebx
0x14004436b  mov     r9d, eax
0x14004436e  mov     rcx, [rcx+10h]
0x140044372  call    WPP_SF_Dd
0x140044377  call    cs:__imp_GetLastError
0x14004437d  mov     ebx, eax
0x14004437f  test    eax, eax
0x140044381  jle     loc_14004464F
0x140044387  movzx   ebx, ax
0x14004438a  or      ebx, 80070000h
0x140044390  jmp     loc_14004464F
0x140044395  mov     rcx, rsi; psz
0x140044398  call    cs:__imp_SysAllocString
0x14004439e  mov     r12, rax
0x1400443a1  test    rax, rax
0x1400443a4  jnz     short loc_1400443FF
0x1400443a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400443ad  lea     rax, WPP_GLOBAL_Control
0x1400443b4  cmp     rcx, rax
0x1400443b7  jz      short loc_1400443F5
0x1400443b9  test    byte ptr [rcx+1Ch], 8
0x1400443bd  jz      short loc_1400443F5
0x1400443bf  cmp     byte ptr [rcx+19h], 2
0x1400443c3  jb      short loc_1400443F5
0x1400443c5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400443ca  lea     rcx, aBstr; "BSTR"
0x1400443d1  mov     r9d, eax
0x1400443d4  mov     [rsp+4A0h+var_480], rcx
0x1400443d9  lea     edx, [r12+31h]
0x1400443de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400443e5  lea     r8, WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids
0x1400443ec  mov     rcx, [rcx+10h]
0x1400443f0  call    WPP_SF_Ds
0x1400443f5  mov     ebx, 8007000Eh
0x1400443fa  jmp     loc_140044657
0x1400443ff  mov     rcx, r14; psz
0x140044402  mov     rdi, r15
0x140044405  call    cs:__imp_SysAllocString
0x14004440b  mov     r15, rax
0x14004440e  test    rax, rax
0x140044411  jnz     short loc_14004446B
0x140044413  mov     rcx, cs:WPP_GLOBAL_Control
0x14004441a  lea     rax, WPP_GLOBAL_Control
0x140044421  cmp     rcx, rax
0x140044424  jz      short loc_140044461
0x140044426  test    byte ptr [rcx+1Ch], 8
0x14004442a  jz      short loc_140044461
0x14004442c  cmp     byte ptr [rcx+19h], 2
0x140044430  jb      short loc_140044461
0x140044432  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140044437  lea     rcx, aBstr; "BSTR"
0x14004443e  mov     r9d, eax
0x140044441  mov     [rsp+4A0h+var_480], rcx
0x140044446  lea     edx, [r15+32h]
0x14004444a  mov     rcx, cs:WPP_GLOBAL_Control
0x140044451  lea     r8, WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids
0x140044458  mov     rcx, [rcx+10h]
0x14004445c  call    WPP_SF_Ds
0x140044461  mov     ebx, 8007000Eh
0x140044466  jmp     loc_140044638
0x14004446b  lea     rcx, [rbp+3A0h+Buffer]; psz
0x140044472  call    cs:__imp_SysAllocString
0x140044478  mov     r14, rax
0x14004447b  test    rax, rax
0x14004447e  jnz     short loc_1400444D8
0x140044480  mov     rcx, cs:WPP_GLOBAL_Control
0x140044487  lea     rax, WPP_GLOBAL_Control
0x14004448e  cmp     rcx, rax
0x140044491  jz      short loc_1400444CE
0x140044493  test    byte ptr [rcx+1Ch], 8
0x140044497  jz      short loc_1400444CE
0x140044499  cmp     byte ptr [rcx+19h], 2
0x14004449d  jb      short loc_1400444CE
0x14004449f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400444a4  lea     rcx, aBstr; "BSTR"
0x1400444ab  mov     r9d, eax
0x1400444ae  mov     [rsp+4A0h+var_480], rcx
0x1400444b3  lea     edx, [r14+33h]
0x1400444b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400444be  lea     r8, WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids
0x1400444c5  mov     rcx, [rcx+10h]
0x1400444c9  call    WPP_SF_Ds
0x1400444ce  mov     ebx, 8007000Eh
0x1400444d3  jmp     loc_14004462F
0x1400444d8  lea     rcx, [rsp+4A0h+var_460]; psz
0x1400444dd  call    cs:__imp_SysAllocString
0x1400444e3  mov     rsi, rax
0x1400444e6  test    rax, rax
0x1400444e9  jnz     short loc_140044542
0x1400444eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400444f2  lea     rax, WPP_GLOBAL_Control
0x1400444f9  cmp     rcx, rax
0x1400444fc  jz      short loc_140044538
0x1400444fe  test    byte ptr [rcx+1Ch], 8
0x140044502  jz      short loc_140044538
0x140044504  cmp     byte ptr [rcx+19h], 2
0x140044508  jb      short loc_140044538
0x14004450a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004450f  lea     rcx, aBstr; "BSTR"
0x140044516  mov     r9d, eax
0x140044519  mov     [rsp+4A0h+var_480], rcx
0x14004451e  lea     edx, [rsi+34h]
0x140044521  mov     rcx, cs:WPP_GLOBAL_Control
0x140044528  lea     r8, WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids
0x14004452f  mov     rcx, [rcx+10h]
0x140044533  call    WPP_SF_Ds
0x140044538  mov     ebx, 8007000Eh
0x14004453d  jmp     loc_140044626
0x140044542  mov     rcx, r13; psz
0x140044545  call    cs:__imp_SysAllocString
0x14004454b  mov     rdi, rax
0x14004454e  test    rax, rax
0x140044551  jnz     short loc_1400445A7
0x140044553  mov     rcx, cs:WPP_GLOBAL_Control
0x14004455a  lea     rax, WPP_GLOBAL_Control
0x140044561  cmp     rcx, rax
0x140044564  jz      short loc_1400445A0
0x140044566  test    byte ptr [rcx+1Ch], 8
0x14004456a  jz      short loc_1400445A0
0x14004456c  cmp     byte ptr [rcx+19h], 2
0x140044570  jb      short loc_1400445A0
0x140044572  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140044577  lea     rcx, aBstr; "BSTR"
0x14004457e  mov     r9d, eax
0x140044581  mov     [rsp+4A0h+var_480], rcx
0x140044586  lea     edx, [rdi+35h]
0x140044589  mov     rcx, cs:WPP_GLOBAL_Control
0x140044590  lea     r8, WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids
0x140044597  mov     rcx, [rcx+10h]
0x14004459b  call    WPP_SF_Ds
0x1400445a0  mov     ebx, 8007000Eh
0x1400445a5  jmp     short loc_14004461D
0x1400445a7  mov     r9, rsi; unsigned __int16 *
0x1400445aa  mov     [rsp+4A0h+var_480], rax; unsigned __int16 *
0x1400445af  mov     r8, r14; unsigned __int16 *
0x1400445b2  mov     rdx, r15; unsigned __int16 *
0x1400445b5  mov     rcx, r12; unsigned __int16 *
0x1400445b8  call    ?StartRemoteApplication@CTscComHelper@@SAJPEAG0000@Z; CTscComHelper::StartRemoteApplication(ushort *,ushort *,ushort *,ushort *,ushort *)
0x1400445bd  mov     ebx, eax
0x1400445bf  test    eax, eax
0x1400445c1  jns     short loc_140044618
0x1400445c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400445ca  lea     rax, WPP_GLOBAL_Control
0x1400445d1  cmp     rcx, rax
0x1400445d4  jz      short loc_14004461D
0x1400445d6  test    byte ptr [rcx+1Ch], 8
0x1400445da  jz      short loc_14004461D
0x1400445dc  cmp     byte ptr [rcx+19h], 2
0x1400445e0  jb      short loc_14004461D
0x1400445e2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400445e7  lea     rcx, aCtsccomhelperS; "CTscComHelper::StartRemoteApplication f"...
0x1400445ee  mov     [rsp+4A0h+var_478], ebx
0x1400445f2  mov     [rsp+4A0h+var_480], rcx
0x1400445f7  lea     r8, WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids
0x1400445fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140044605  mov     edx, 36h ; '6'
0x14004460a  mov     r9d, eax
0x14004460d  mov     rcx, [rcx+10h]
0x140044611  call    WPP_SF_DsD
0x140044616  jmp     short loc_14004461D
0x140044618  mov     ebx, 40200h
0x14004461d  mov     rcx, rsi; bstrString
0x140044620  call    cs:__imp_SysFreeString
0x140044626  mov     rcx, r14; bstrString
0x140044629  call    cs:__imp_SysFreeString
0x14004462f  mov     rcx, r15; bstrString
0x140044632  call    cs:__imp_SysFreeString
0x140044638  mov     rcx, r12; bstrString
0x14004463b  call    cs:__imp_SysFreeString
0x140044641  test    rdi, rdi
0x140044644  jz      short loc_14004464F
0x140044646  mov     rcx, rdi; bstrString
0x140044649  call    cs:__imp_SysFreeString
0x14004464f  test    ebx, ebx
0x140044651  jns     loc_1400442DE
0x140044657  xor     ecx, ecx; hWnd
0x140044659  mov     edx, 33F5h; unsigned int
0x14004465e  lea     r9d, [rcx+1]; int
0x140044662  call    ?SH_DisplayMsgBox@CSharedSH@@SAHPEAUHWND__@@HHH@Z; CSharedSH::SH_DisplayMsgBox(HWND__ *,int,int,int)
0x140044667  jmp     loc_1400442DE
```
