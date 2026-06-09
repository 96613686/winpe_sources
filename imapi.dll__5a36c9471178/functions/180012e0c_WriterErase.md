# WriterErase

- ea: `0x180012e0c`
- end: `0x1800130ff`
- name: `WriterErase`
- size: `755`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000ee40`

## callees

- `0x180007bd4`
- `0x180007c60`
- `0x180007d80`
- `0x18000c330`
- `0x1800127ec`
- `0x180012e0c`
- `0x180019010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180012e9a`
- `ole32!CoCreateInstance` at `0x180012e9a`
- `OLEAUT32!__imp_SysAllocString` at `0x180012eec`
- `OLEAUT32!__imp_SysAllocString` at `0x180012eec`
- `OLEAUT32!__imp_SysFreeString` at `0x180012f65`
- `OLEAUT32!__imp_SysFreeString` at `0x180012f77`
- `OLEAUT32!__imp_SysFreeString` at `0x180012f65`
- `OLEAUT32!__imp_SysFreeString` at `0x180012f77`

## pseudocode

```c
__int64 __fastcall WriterErase(_QWORD *a1, unsigned __int8 a2)
{
  char v2; // di
  _QWORD *v5; // r10
  HRESULT v6; // eax
  int v7; // ebx
  OLECHAR *v8; // rbp
  __int64 *LastComError; // rax
  int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  LPVOID ppv; // [rsp+60h] [rbp+8h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  ppv = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a1, a2);
    v5 = WPP_GLOBAL_Control;
  }
  if ( a1 && *a1 )
  {
    v6 = CoCreateInstance(
           &GUID_2735412b_7f64_5b0f_8f00_5d77afbe261e,
           0,
           0x17u,
           &GUID_27354156_8f64_5b0f_8f00_5d77afbe261e,
           &ppv);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v8 = SysAllocString(L"IMAPIv1 Shim");
      v7 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)ppv + 136LL))(ppv, v8);
      if ( v7 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          LastComError = (__int64 *)GetLastComError(&bstrString);
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            17,
            (unsigned int)&WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
            v7,
            *LastComError);
          v2 = 1;
        }
        if ( (v2 & 1) != 0 )
          SysFreeString(bstrString);
        v7 = TranslateIMAPI2Error((unsigned int)v7);
      }
      SysFreeString(v8);
      if ( v7 < 0 )
        goto LABEL_10;
      v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 96LL))(ppv, *a1);
      v12 = v10;
      if ( v10 >= 0 )
        goto LABEL_43;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          18,
          &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
          (unsigned int)v10);
      v7 = TranslateIMAPI2Error(v12);
      if ( v7 >= 0 )
      {
LABEL_43:
        LOWORD(v11) = -(a2 != 0);
        v13 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 112LL))(ppv, v11);
        v14 = v13;
        if ( v13 >= 0 )
          goto LABEL_29;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            19,
            &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
            (unsigned int)v13);
        v7 = TranslateIMAPI2Error(v14);
        if ( v7 >= 0 )
        {
LABEL_29:
          v15 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 152LL))(ppv);
          v7 = v15;
          if ( v15 >= 0 )
            goto LABEL_10;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              20,
              &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
              (unsigned int)v15);
          v7 = TranslateIMAPI2Error((unsigned int)v7);
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          16,
          &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
          (unsigned int)v6);
LABEL_10:
        v5 = WPP_GLOBAL_Control;
      }
    }
  }
  else
  {
    v7 = -2147024809;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v5 = WPP_GLOBAL_Control;
    ppv = 0;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 68) & 1) != 0 )
    WPP_SF_qD(v5[7], 21, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a1, v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180012e0c  mov     [rsp+arg_8], rbx
0x180012e11  push    rbp
0x180012e12  push    rsi
0x180012e13  push    rdi
0x180012e14  push    r13
0x180012e16  push    r14
0x180012e18  sub     rsp, 30h
0x180012e1c  xor     edi, edi
0x180012e1e  movzx   r14d, dl
0x180012e22  mov     dword ptr [rsp+58h+arg_0], edi
0x180012e26  mov     rsi, rcx
0x180012e29  mov     [rsp+58h+arg_0], rdi
0x180012e2e  mov     r10, cs:WPP_GLOBAL_Control
0x180012e35  lea     r13, WPP_GLOBAL_Control
0x180012e3c  cmp     r10, r13
0x180012e3f  jz      short loc_180012E6A
0x180012e41  test    byte ptr [r10+44h], 1
0x180012e46  jz      short loc_180012E6A
0x180012e48  mov     r9, rcx
0x180012e4b  mov     dword ptr [rsp+58h+ppv], r14d
0x180012e50  mov     rcx, [r10+38h]
0x180012e54  lea     edx, [rdi+0Fh]
0x180012e57  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180012e5e  call    WPP_SF_qD
0x180012e63  mov     r10, cs:WPP_GLOBAL_Control
0x180012e6a  test    rsi, rsi
0x180012e6d  jz      loc_180013099
0x180012e73  cmp     [rsi], rdi
0x180012e76  jz      loc_180013099
0x180012e7c  xor     edx, edx; pUnkOuter
0x180012e7e  lea     rax, [rsp+58h+arg_0]
0x180012e83  lea     r9, _GUID_27354156_8f64_5b0f_8f00_5d77afbe261e; riid
0x180012e8a  mov     [rsp+58h+ppv], rax; ppv
0x180012e8f  lea     rcx, _GUID_2735412b_7f64_5b0f_8f00_5d77afbe261e; rclsid
0x180012e96  lea     r8d, [rdx+17h]; dwClsContext
0x180012e9a  call    cs:__imp_CoCreateInstance
0x180012ea0  mov     ebx, eax
0x180012ea2  test    eax, eax
0x180012ea4  jns     short loc_180012EE5
0x180012ea6  mov     r10, cs:WPP_GLOBAL_Control
0x180012ead  cmp     r10, r13
0x180012eb0  jz      loc_18001309E
0x180012eb6  test    byte ptr [r10+44h], 1
0x180012ebb  jz      loc_18001309E
0x180012ec1  mov     rcx, [r10+38h]
0x180012ec5  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180012ecc  mov     edx, 10h
0x180012ed1  mov     r9d, eax
0x180012ed4  call    WPP_SF_d
0x180012ed9  mov     r10, cs:WPP_GLOBAL_Control
0x180012ee0  jmp     loc_18001309E
0x180012ee5  lea     rcx, psz; "IMAPIv1 Shim"
0x180012eec  call    cs:__imp_SysAllocString
0x180012ef2  mov     rcx, [rsp+58h+arg_0]
0x180012ef7  mov     rbp, rax
0x180012efa  mov     rdx, [rcx]
0x180012efd  mov     rax, [rdx+88h]
0x180012f04  mov     rdx, rbp
0x180012f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f0c  mov     ebx, eax
0x180012f0e  test    eax, eax
0x180012f10  jns     short loc_180012F74
0x180012f12  mov     rax, cs:WPP_GLOBAL_Control
0x180012f19  cmp     rax, r13
0x180012f1c  jz      short loc_180012F5A
0x180012f1e  test    byte ptr [rax+44h], 1
0x180012f22  jz      short loc_180012F5A
0x180012f24  lea     rcx, [rsp+58h+bstrString]
0x180012f29  call    ?GetLastComError@@YA?AVCComBSTR@ATL@@XZ; GetLastComError(void)
0x180012f2e  mov     edx, 11h
0x180012f33  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180012f3a  mov     r9d, ebx
0x180012f3d  mov     rcx, [rax]
0x180012f40  mov     [rsp+58h+ppv], rcx
0x180012f45  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f4c  mov     rcx, [rcx+38h]
0x180012f50  call    WPP_SF_DS
0x180012f55  mov     edi, 1
0x180012f5a  test    dil, 1
0x180012f5e  jz      short loc_180012F6B
0x180012f60  mov     rcx, [rsp+58h+bstrString]; bstrString
0x180012f65  call    cs:__imp_SysFreeString
0x180012f6b  mov     ecx, ebx
0x180012f6d  call    TranslateIMAPI2Error
0x180012f72  mov     ebx, eax
0x180012f74  mov     rcx, rbp; bstrString
0x180012f77  call    cs:__imp_SysFreeString
0x180012f7d  test    ebx, ebx
0x180012f7f  js      loc_180012ED9
0x180012f85  mov     rcx, [rsp+58h+arg_0]
0x180012f8a  mov     rdx, [rsi]
0x180012f8d  mov     rax, [rcx]
0x180012f90  mov     rax, [rax+60h]
0x180012f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f99  mov     ebx, eax
0x180012f9b  test    eax, eax
0x180012f9d  jns     short loc_180012FE2
0x180012f9f  mov     r10, cs:WPP_GLOBAL_Control
0x180012fa6  cmp     r10, r13
0x180012fa9  jz      short loc_180012FD1
0x180012fab  test    byte ptr [r10+44h], 1
0x180012fb0  jz      short loc_180012FD1
0x180012fb2  mov     rcx, [r10+38h]
0x180012fb6  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180012fbd  mov     edx, 12h
0x180012fc2  mov     r9d, eax
0x180012fc5  call    WPP_SF_d
0x180012fca  mov     r10, cs:WPP_GLOBAL_Control
0x180012fd1  mov     ecx, ebx
0x180012fd3  call    TranslateIMAPI2Error
0x180012fd8  mov     ebx, eax
0x180012fda  test    eax, eax
0x180012fdc  js      loc_18001309E
0x180012fe2  mov     rcx, [rsp+58h+arg_0]
0x180012fe7  neg     r14b
0x180012fea  sbb     dx, dx
0x180012fed  mov     rax, [rcx]
0x180012ff0  mov     rax, [rax+70h]
0x180012ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ff9  mov     ebx, eax
0x180012ffb  test    eax, eax
0x180012ffd  jns     short loc_18001303E
0x180012fff  mov     r10, cs:WPP_GLOBAL_Control
0x180013006  cmp     r10, r13
0x180013009  jz      short loc_180013031
0x18001300b  test    byte ptr [r10+44h], 1
0x180013010  jz      short loc_180013031
0x180013012  mov     rcx, [r10+38h]
0x180013016  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x18001301d  mov     edx, 13h
0x180013022  mov     r9d, eax
0x180013025  call    WPP_SF_d
0x18001302a  mov     r10, cs:WPP_GLOBAL_Control
0x180013031  mov     ecx, ebx
0x180013033  call    TranslateIMAPI2Error
0x180013038  mov     ebx, eax
0x18001303a  test    eax, eax
0x18001303c  js      short loc_18001309E
0x18001303e  mov     rcx, [rsp+58h+arg_0]
0x180013043  mov     rax, [rcx]
0x180013046  mov     rax, [rax+98h]
0x18001304d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013052  mov     ebx, eax
0x180013054  test    eax, eax
0x180013056  jns     loc_180012ED9
0x18001305c  mov     r10, cs:WPP_GLOBAL_Control
0x180013063  cmp     r10, r13
0x180013066  jz      short loc_18001308E
0x180013068  test    byte ptr [r10+44h], 1
0x18001306d  jz      short loc_18001308E
0x18001306f  mov     rcx, [r10+38h]
0x180013073  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x18001307a  mov     edx, 14h
0x18001307f  mov     r9d, eax
0x180013082  call    WPP_SF_d
0x180013087  mov     r10, cs:WPP_GLOBAL_Control
0x18001308e  mov     ecx, ebx
0x180013090  call    TranslateIMAPI2Error
0x180013095  mov     ebx, eax
0x180013097  jmp     short loc_18001309E
0x180013099  mov     ebx, 80070057h
0x18001309e  mov     rcx, [rsp+58h+arg_0]
0x1800130a3  test    rcx, rcx
0x1800130a6  jz      short loc_1800130C4
0x1800130a8  mov     rax, [rcx]
0x1800130ab  mov     rax, [rax+10h]
0x1800130af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130b4  mov     r10, cs:WPP_GLOBAL_Control
0x1800130bb  mov     [rsp+58h+arg_0], 0
0x1800130c4  cmp     r10, r13
0x1800130c7  jz      short loc_1800130EC
0x1800130c9  test    byte ptr [r10+44h], 1
0x1800130ce  jz      short loc_1800130EC
0x1800130d0  mov     rcx, [r10+38h]
0x1800130d4  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x1800130db  mov     edx, 15h
0x1800130e0  mov     dword ptr [rsp+58h+ppv], ebx
0x1800130e4  mov     r9, rsi
0x1800130e7  call    WPP_SF_qD
0x1800130ec  mov     eax, ebx
0x1800130ee  mov     rbx, [rsp+58h+arg_8]
0x1800130f3  add     rsp, 30h
0x1800130f7  pop     r14
0x1800130f9  pop     r13
0x1800130fb  pop     rdi
0x1800130fc  pop     rsi
0x1800130fd  pop     rbp
0x1800130fe  retn
```
