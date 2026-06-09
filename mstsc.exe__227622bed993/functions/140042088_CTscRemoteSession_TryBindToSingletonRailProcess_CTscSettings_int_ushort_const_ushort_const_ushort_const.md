# CTscRemoteSession::TryBindToSingletonRailProcess(CTscSettings *,int,ushort const *,ushort const *,ushort const *)

- ea: `0x140042088`
- end: `0x1400424fc`
- name: `?TryBindToSingletonRailProcess@CTscRemoteSession@@QEAAJPEAVCTscSettings@@HPEBG11@Z`
- size: `1140`
- prototype: `int(CTscRemoteSession *__hidden this, struct CTscSettings *, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140062680`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000d078`
- `0x1400368a0`
- `0x140042088`
- `0x1400b2aac`
- `0x1400b4844`
- `0x140111220`

## import_xrefs

- `KERNEL32!GetCurrentDirectoryW` at `0x1400421ae`
- `KERNEL32!GetCurrentDirectoryW` at `0x1400421ae`
- `KERNEL32!GetLastError` at `0x1400421d7`
- `KERNEL32!GetLastError` at `0x140042207`
- `KERNEL32!GetLastError` at `0x1400421d7`
- `KERNEL32!GetLastError` at `0x140042207`
- `OLEAUT32!__imp_SysAllocString` at `0x140042228`
- `OLEAUT32!__imp_SysAllocString` at `0x140042295`
- `OLEAUT32!__imp_SysAllocString` at `0x140042302`
- `OLEAUT32!__imp_SysAllocString` at `0x14004236d`
- `OLEAUT32!__imp_SysAllocString` at `0x1400423d5`
- `OLEAUT32!__imp_SysAllocString` at `0x140042228`
- `OLEAUT32!__imp_SysAllocString` at `0x140042295`
- `OLEAUT32!__imp_SysAllocString` at `0x140042302`
- `OLEAUT32!__imp_SysAllocString` at `0x14004236d`
- `OLEAUT32!__imp_SysAllocString` at `0x1400423d5`
- `OLEAUT32!__imp_SysFreeString` at `0x1400424b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1400424b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1400424c2`
- `OLEAUT32!__imp_SysFreeString` at `0x1400424cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1400424d9`
- `OLEAUT32!__imp_SysFreeString` at `0x1400424b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1400424b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1400424c2`
- `OLEAUT32!__imp_SysFreeString` at `0x1400424cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1400424d9`

## string_xrefs

- `0x140042477`: `CTscComHelper::StartRemoteApplication failed!`

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
0x140042088  mov     [rsp-8+arg_0], rbx
0x14004208d  push    rbp
0x14004208e  push    rsi
0x14004208f  push    rdi
0x140042090  push    r12
0x140042092  push    r13
0x140042094  push    r14
0x140042096  push    r15
0x140042098  lea     rbp, [rsp-370h]
0x1400420a0  sub     rsp, 470h
0x1400420a7  mov     rax, cs:__security_cookie
0x1400420ae  xor     rax, rsp
0x1400420b1  mov     [rbp+3A0h+var_40], rax
0x1400420b8  mov     r14, [rbp+3A0h+psz]
0x1400420bf  mov     rsi, r9
0x1400420c2  mov     r13, [rbp+3A0h+arg_28]
0x1400420c9  lea     r9, [rsp+4A0h+var_460]; unsigned __int16 *
0x1400420ce  mov     edi, r8d
0x1400420d1  mov     rcx, rdx; this
0x1400420d4  xor     r15d, r15d
0x1400420d7  lea     r8, [rsp+4A0h+var_46C]; int *
0x1400420dc  lea     rdx, [rsp+4A0h+var_470]; int *
0x1400420e1  mov     [rsp+4A0h+var_470], r15d
0x1400420e6  mov     [rsp+4A0h+var_46C], r15d
0x1400420eb  call    ?LoadConnectionSharingSettings@CTscSettings@@QEAAJPEAH0PEAGI@Z; CTscSettings::LoadConnectionSharingSettings(int *,int *,ushort *,uint)
0x1400420f0  mov     ebx, eax
0x1400420f2  test    eax, eax
0x1400420f4  jns     short loc_140042159
0x1400420f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400420fd  lea     rax, WPP_GLOBAL_Control
0x140042104  cmp     rcx, rax
0x140042107  jz      loc_1400424E7
0x14004210d  test    byte ptr [rcx+1Ch], 8
0x140042111  jz      loc_1400424E7
0x140042117  cmp     byte ptr [rcx+19h], 2
0x14004211b  jb      loc_1400424E7
0x140042121  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140042126  lea     rcx, aLoadconnection; "LoadConnectionSharingSettings failed"
0x14004212d  mov     [rsp+4A0h+var_478], ebx
0x140042131  mov     [rsp+4A0h+var_480], rcx
0x140042136  lea     edx, [r15+2Fh]
0x14004213a  mov     rcx, cs:WPP_GLOBAL_Control
0x140042141  lea     r8, WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids
0x140042148  mov     r9d, eax
0x14004214b  mov     rcx, [rcx+10h]
0x14004214f  call    WPP_SF_DsD
0x140042154  jmp     loc_1400424E7
0x140042159  test    edi, edi
0x14004215b  jz      short loc_14004216B
0x14004215d  cmp     [rsp+4A0h+var_470], r15d
0x140042162  jz      short loc_14004219A
0x140042164  cmp     [rsp+4A0h+var_46C], r15d
0x140042169  jz      short loc_1400421A2
0x14004216b  mov     ebx, r15d
0x14004216e  mov     eax, ebx
0x140042170  mov     rcx, [rbp+3A0h+var_40]
0x140042177  xor     rcx, rsp; StackCookie
0x14004217a  call    __security_check_cookie
0x14004217f  mov     rbx, [rsp+4A0h+arg_0]
0x140042187  add     rsp, 470h
0x14004218e  pop     r15
0x140042190  pop     r14
0x140042192  pop     r13
0x140042194  pop     r12
0x140042196  pop     rdi
0x140042197  pop     rsi
0x140042198  pop     rbp
0x140042199  retn
0x14004219a  cmp     [rsp+4A0h+var_460], r15w
0x1400421a0  jz      short loc_14004216B
0x1400421a2  lea     rdx, [rbp+3A0h+Buffer]; lpBuffer
0x1400421a9  mov     ecx, 104h; nBufferLength
0x1400421ae  call    cs:__imp_GetCurrentDirectoryW
0x1400421b4  test    eax, eax
0x1400421b6  jnz     short loc_140042225
0x1400421b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400421bf  lea     rax, WPP_GLOBAL_Control
0x1400421c6  cmp     rcx, rax
0x1400421c9  jz      short loc_140042207
0x1400421cb  test    byte ptr [rcx+1Ch], 1
0x1400421cf  jz      short loc_140042207
0x1400421d1  cmp     byte ptr [rcx+19h], 2
0x1400421d5  jb      short loc_140042207
0x1400421d7  call    cs:__imp_GetLastError
0x1400421dd  mov     ebx, eax
0x1400421df  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400421e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400421eb  lea     r8, WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids
0x1400421f2  mov     edx, 30h ; '0'
0x1400421f7  mov     dword ptr [rsp+4A0h+var_480], ebx
0x1400421fb  mov     r9d, eax
0x1400421fe  mov     rcx, [rcx+10h]
0x140042202  call    WPP_SF_Dd
0x140042207  call    cs:__imp_GetLastError
0x14004220d  mov     ebx, eax
0x14004220f  test    eax, eax
0x140042211  jle     loc_1400424DF
0x140042217  movzx   ebx, ax
0x14004221a  or      ebx, 80070000h
0x140042220  jmp     loc_1400424DF
0x140042225  mov     rcx, rsi; psz
0x140042228  call    cs:__imp_SysAllocString
0x14004222e  mov     r12, rax
0x140042231  test    rax, rax
0x140042234  jnz     short loc_14004228F
0x140042236  mov     rcx, cs:WPP_GLOBAL_Control
0x14004223d  lea     rax, WPP_GLOBAL_Control
0x140042244  cmp     rcx, rax
0x140042247  jz      short loc_140042285
0x140042249  test    byte ptr [rcx+1Ch], 8
0x14004224d  jz      short loc_140042285
0x14004224f  cmp     byte ptr [rcx+19h], 2
0x140042253  jb      short loc_140042285
0x140042255  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004225a  lea     rcx, aBstr; "BSTR"
0x140042261  mov     r9d, eax
0x140042264  mov     [rsp+4A0h+var_480], rcx
0x140042269  lea     edx, [r12+31h]
0x14004226e  mov     rcx, cs:WPP_GLOBAL_Control
0x140042275  lea     r8, WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids
0x14004227c  mov     rcx, [rcx+10h]
0x140042280  call    WPP_SF_Ds
0x140042285  mov     ebx, 8007000Eh
0x14004228a  jmp     loc_1400424E7
0x14004228f  mov     rcx, r14; psz
0x140042292  mov     rdi, r15
0x140042295  call    cs:__imp_SysAllocString
0x14004229b  mov     r15, rax
0x14004229e  test    rax, rax
0x1400422a1  jnz     short loc_1400422FB
0x1400422a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400422aa  lea     rax, WPP_GLOBAL_Control
0x1400422b1  cmp     rcx, rax
0x1400422b4  jz      short loc_1400422F1
0x1400422b6  test    byte ptr [rcx+1Ch], 8
0x1400422ba  jz      short loc_1400422F1
0x1400422bc  cmp     byte ptr [rcx+19h], 2
0x1400422c0  jb      short loc_1400422F1
0x1400422c2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400422c7  lea     rcx, aBstr; "BSTR"
0x1400422ce  mov     r9d, eax
0x1400422d1  mov     [rsp+4A0h+var_480], rcx
0x1400422d6  lea     edx, [r15+32h]
0x1400422da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400422e1  lea     r8, WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids
0x1400422e8  mov     rcx, [rcx+10h]
0x1400422ec  call    WPP_SF_Ds
0x1400422f1  mov     ebx, 8007000Eh
0x1400422f6  jmp     loc_1400424C8
0x1400422fb  lea     rcx, [rbp+3A0h+Buffer]; psz
0x140042302  call    cs:__imp_SysAllocString
0x140042308  mov     r14, rax
0x14004230b  test    rax, rax
0x14004230e  jnz     short loc_140042368
0x140042310  mov     rcx, cs:WPP_GLOBAL_Control
0x140042317  lea     rax, WPP_GLOBAL_Control
0x14004231e  cmp     rcx, rax
0x140042321  jz      short loc_14004235E
0x140042323  test    byte ptr [rcx+1Ch], 8
0x140042327  jz      short loc_14004235E
0x140042329  cmp     byte ptr [rcx+19h], 2
0x14004232d  jb      short loc_14004235E
0x14004232f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140042334  lea     rcx, aBstr; "BSTR"
0x14004233b  mov     r9d, eax
0x14004233e  mov     [rsp+4A0h+var_480], rcx
0x140042343  lea     edx, [r14+33h]
0x140042347  mov     rcx, cs:WPP_GLOBAL_Control
0x14004234e  lea     r8, WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids
0x140042355  mov     rcx, [rcx+10h]
0x140042359  call    WPP_SF_Ds
0x14004235e  mov     ebx, 8007000Eh
0x140042363  jmp     loc_1400424BF
0x140042368  lea     rcx, [rsp+4A0h+var_460]; psz
0x14004236d  call    cs:__imp_SysAllocString
0x140042373  mov     rsi, rax
0x140042376  test    rax, rax
0x140042379  jnz     short loc_1400423D2
0x14004237b  mov     rcx, cs:WPP_GLOBAL_Control
0x140042382  lea     rax, WPP_GLOBAL_Control
0x140042389  cmp     rcx, rax
0x14004238c  jz      short loc_1400423C8
0x14004238e  test    byte ptr [rcx+1Ch], 8
0x140042392  jz      short loc_1400423C8
0x140042394  cmp     byte ptr [rcx+19h], 2
0x140042398  jb      short loc_1400423C8
0x14004239a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004239f  lea     rcx, aBstr; "BSTR"
0x1400423a6  mov     r9d, eax
0x1400423a9  mov     [rsp+4A0h+var_480], rcx
0x1400423ae  lea     edx, [rsi+34h]
0x1400423b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400423b8  lea     r8, WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids
0x1400423bf  mov     rcx, [rcx+10h]
0x1400423c3  call    WPP_SF_Ds
0x1400423c8  mov     ebx, 8007000Eh
0x1400423cd  jmp     loc_1400424B6
0x1400423d2  mov     rcx, r13; psz
0x1400423d5  call    cs:__imp_SysAllocString
0x1400423db  mov     rdi, rax
0x1400423de  test    rax, rax
0x1400423e1  jnz     short loc_140042437
0x1400423e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400423ea  lea     rax, WPP_GLOBAL_Control
0x1400423f1  cmp     rcx, rax
0x1400423f4  jz      short loc_140042430
0x1400423f6  test    byte ptr [rcx+1Ch], 8
0x1400423fa  jz      short loc_140042430
0x1400423fc  cmp     byte ptr [rcx+19h], 2
0x140042400  jb      short loc_140042430
0x140042402  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140042407  lea     rcx, aBstr; "BSTR"
0x14004240e  mov     r9d, eax
0x140042411  mov     [rsp+4A0h+var_480], rcx
0x140042416  lea     edx, [rdi+35h]
0x140042419  mov     rcx, cs:WPP_GLOBAL_Control
0x140042420  lea     r8, WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids
0x140042427  mov     rcx, [rcx+10h]
0x14004242b  call    WPP_SF_Ds
0x140042430  mov     ebx, 8007000Eh
0x140042435  jmp     short loc_1400424AD
0x140042437  mov     r9, rsi; unsigned __int16 *
0x14004243a  mov     [rsp+4A0h+var_480], rax; unsigned __int16 *
0x14004243f  mov     r8, r14; unsigned __int16 *
0x140042442  mov     rdx, r15; unsigned __int16 *
0x140042445  mov     rcx, r12; unsigned __int16 *
0x140042448  call    ?StartRemoteApplication@CTscComHelper@@SAJPEAG0000@Z; CTscComHelper::StartRemoteApplication(ushort *,ushort *,ushort *,ushort *,ushort *)
0x14004244d  mov     ebx, eax
0x14004244f  test    eax, eax
0x140042451  jns     short loc_1400424A8
0x140042453  mov     rcx, cs:WPP_GLOBAL_Control
0x14004245a  lea     rax, WPP_GLOBAL_Control
0x140042461  cmp     rcx, rax
0x140042464  jz      short loc_1400424AD
0x140042466  test    byte ptr [rcx+1Ch], 8
0x14004246a  jz      short loc_1400424AD
0x14004246c  cmp     byte ptr [rcx+19h], 2
0x140042470  jb      short loc_1400424AD
0x140042472  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140042477  lea     rcx, aCtsccomhelperS; "CTscComHelper::StartRemoteApplication f"...
0x14004247e  mov     [rsp+4A0h+var_478], ebx
0x140042482  mov     [rsp+4A0h+var_480], rcx
0x140042487  lea     r8, WPP_ebc8717e7bb833426c5f05df3662b008_Traceguids
0x14004248e  mov     rcx, cs:WPP_GLOBAL_Control
0x140042495  mov     edx, 36h ; '6'
0x14004249a  mov     r9d, eax
0x14004249d  mov     rcx, [rcx+10h]
0x1400424a1  call    WPP_SF_DsD
0x1400424a6  jmp     short loc_1400424AD
0x1400424a8  mov     ebx, 40200h
0x1400424ad  mov     rcx, rsi; bstrString
0x1400424b0  call    cs:__imp_SysFreeString
0x1400424b6  mov     rcx, r14; bstrString
0x1400424b9  call    cs:__imp_SysFreeString
0x1400424bf  mov     rcx, r15; bstrString
0x1400424c2  call    cs:__imp_SysFreeString
0x1400424c8  mov     rcx, r12; bstrString
0x1400424cb  call    cs:__imp_SysFreeString
0x1400424d1  test    rdi, rdi
0x1400424d4  jz      short loc_1400424DF
0x1400424d6  mov     rcx, rdi; bstrString
0x1400424d9  call    cs:__imp_SysFreeString
0x1400424df  test    ebx, ebx
0x1400424e1  jns     loc_14004216E
0x1400424e7  xor     ecx, ecx; hWnd
0x1400424e9  mov     edx, 33F5h; unsigned int
0x1400424ee  lea     r9d, [rcx+1]; int
0x1400424f2  call    ?SH_DisplayMsgBox@CSharedSH@@SAHPEAUHWND__@@HHH@Z; CSharedSH::SH_DisplayMsgBox(HWND__ *,int,int,int)
0x1400424f7  jmp     loc_14004216E
```
