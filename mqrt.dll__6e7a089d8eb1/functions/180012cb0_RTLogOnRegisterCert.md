# RTLogOnRegisterCert

- ea: `0x180012cb0`
- end: `0x180012e80`
- name: `RTLogOnRegisterCert`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180011ff0`

## callees

- `0x1800087f8`
- `0x18000a33c`
- `0x180010a58`
- `0x1800113d8`
- `0x180011b8c`
- `0x180012000`
- `0x180012cb0`
- `0x180013c74`
- `0x180014458`

## import_xrefs

- `KERNEL32!Sleep` at `0x180012e11`
- `KERNEL32!Sleep` at `0x180012e11`
- `mqsec!GetFalconKeyValue` at `0x180012d23`
- `mqsec!GetFalconKeyValue` at `0x180012dde`
- `mqsec!GetFalconKeyValue` at `0x180012d23`
- `mqsec!GetFalconKeyValue` at `0x180012dde`

## string_xrefs

- `0x180012d1c`: `security\AutoRegisterIntCert`
- `0x180012dd1`: `security\AutoIntCertWaitIntervals`

## pseudocode

```c
__int64 __fastcall RTLogOnRegisterCert(char a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  unsigned int i; // edi
  HRESULT v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // [rsp+30h] [rbp-10h] BYREF
  int v11; // [rsp+34h] [rbp-Ch] BYREF
  unsigned int v12; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v13; // [rsp+3Ch] [rbp-4h] BYREF
  int v14; // [rsp+68h] [rbp+28h] BYREF
  unsigned int v15; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v16; // [rsp+78h] [rbp+38h] BYREF

  v2 = RtpOneTimeThreadInit();
  v3 = v2;
  if ( v2 < 0 )
  {
    LogMsgHR(v2, (wchar_t *)L"rt/rtintcrt", 0x477u);
    return v3;
  }
  if ( !IsWorkGroupMode() )
  {
    v14 = 1;
    v15 = 4;
    v16 = 4;
    if ( !GetFalconKeyValue(L"security\\AutoRegisterIntCert", &v15, &v14, &v16, 0) && !v14 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) == 0 )
        return 0;
      v6 = 29;
      goto LABEL_13;
    }
    if ( (unsigned int)GetDWORDKeyValue(L"CertificateRegistered") != 1 )
    {
      v15 = 4;
      v11 = 40;
      v10 = 40;
      v16 = 4;
      v12 = 4;
      v13 = 4;
      GetFalconKeyValue(L"security\\AutoIntCertWaitIntervals", &v13, &v10, &v12, (const wchar_t *)&v11);
      for ( i = 0; ; ++i )
      {
        v8 = MQRegisterCertificate(2u, 0, 0);
        v9 = v8;
        if ( v8 >= 0 )
        {
          SetDWORDKeyValue(L"CertificateRegistered", 1);
          return 0;
        }
        if ( v8 != -1072824301 || !a1 || i >= v10 )
          break;
        Sleep(0x3A98u);
      }
      SetDWORDKeyValue(L"AutoRegisterError", v8);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 31, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids, v9);
      return 0;
    }
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
    {
      v6 = 30;
LABEL_13:
      WPP_SF_(v5[32], v6, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180012cb0  mov     [rsp-18h+arg_0], rbx
0x180012cb5  push    rbp
0x180012cb6  push    rsi
0x180012cb7  push    rdi
0x180012cb8  mov     rbp, rsp
0x180012cbb  sub     rsp, 40h
0x180012cbf  mov     sil, cl
0x180012cc2  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x180012cc7  mov     ebx, eax
0x180012cc9  test    eax, eax
0x180012ccb  jns     short loc_180012CE8
0x180012ccd  mov     r8d, 477h; unsigned __int16
0x180012cd3  lea     rdx, aRtRtintcrt; "rt/rtintcrt"
0x180012cda  mov     ecx, eax; int
0x180012cdc  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180012ce1  mov     eax, ebx
0x180012ce3  jmp     loc_180012E73
0x180012ce8  call    ?IsWorkGroupMode@@YA_NXZ; IsWorkGroupMode(void)
0x180012ced  test    al, al
0x180012cef  jnz     loc_180012E71
0x180012cf5  mov     ebx, 4
0x180012cfa  mov     [rbp+arg_8], 1
0x180012d01  lea     r9, [rbp+arg_18]
0x180012d05  mov     [rbp+arg_10], ebx
0x180012d08  lea     r8, [rbp+arg_8]
0x180012d0c  mov     [rbp+arg_18], ebx
0x180012d0f  lea     rdx, [rbp+arg_10]
0x180012d13  mov     [rsp+40h+var_20], 0
0x180012d1c  lea     rcx, aSecurityAutore; "security\\AutoRegisterIntCert"
0x180012d23  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x180012d29  test    eax, eax
0x180012d2b  jnz     short loc_180012D5A
0x180012d2d  cmp     [rbp+arg_8], eax
0x180012d30  jnz     short loc_180012D5A
0x180012d32  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d39  lea     rax, WPP_GLOBAL_Control
0x180012d40  cmp     rcx, rax
0x180012d43  jz      loc_180012E71
0x180012d49  test    [rcx+10Ch], bl
0x180012d4f  jz      loc_180012E71
0x180012d55  lea     edx, [rbx+19h]
0x180012d58  jmp     short loc_180012D93
0x180012d5a  lea     rcx, ValueName; "CertificateRegistered"
0x180012d61  call    GetDWORDKeyValue
0x180012d66  cmp     eax, 1
0x180012d69  jnz     short loc_180012DAB
0x180012d6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d72  lea     rax, WPP_GLOBAL_Control
0x180012d79  cmp     rcx, rax
0x180012d7c  jz      loc_180012E71
0x180012d82  test    [rcx+10Ch], bl
0x180012d88  jz      loc_180012E71
0x180012d8e  mov     edx, 1Eh
0x180012d93  mov     rcx, [rcx+100h]
0x180012d9a  lea     r8, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids
0x180012da1  call    WPP_SF_
0x180012da6  jmp     loc_180012E71
0x180012dab  mov     eax, 28h ; '('
0x180012db0  mov     [rbp+arg_10], ebx
0x180012db3  mov     [rbp+var_C], eax
0x180012db6  lea     r9, [rbp+var_8]
0x180012dba  mov     [rbp+var_10], eax
0x180012dbd  lea     r8, [rbp+var_10]
0x180012dc1  lea     rax, [rbp+var_C]
0x180012dc5  mov     [rbp+arg_18], ebx
0x180012dc8  lea     rdx, [rbp+var_4]
0x180012dcc  mov     [rsp+40h+var_20], rax
0x180012dd1  lea     rcx, aSecurityAutoin; "security\\AutoIntCertWaitIntervals"
0x180012dd8  mov     [rbp+var_8], ebx
0x180012ddb  mov     [rbp+var_4], ebx
0x180012dde  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x180012de4  xor     edi, edi
0x180012de6  xor     edx, edx; lpCertBuffer
0x180012de8  xor     r8d, r8d; dwCertBufferLength
0x180012deb  lea     ecx, [rdx+2]; dwFlags
0x180012dee  call    MQRegisterCertificate
0x180012df3  mov     ebx, eax
0x180012df5  test    eax, eax
0x180012df7  jns     short loc_180012E60
0x180012df9  cmp     eax, 0C00E0013h
0x180012dfe  jnz     short loc_180012E19
0x180012e00  test    sil, sil
0x180012e03  jz      short loc_180012E19
0x180012e05  cmp     edi, [rbp+var_10]
0x180012e08  jnb     short loc_180012E19
0x180012e0a  inc     edi
0x180012e0c  mov     ecx, 3A98h; dwMilliseconds
0x180012e11  call    cs:__imp_Sleep
0x180012e17  jmp     short loc_180012DE6
0x180012e19  mov     edx, ebx
0x180012e1b  lea     rcx, aAutoregisterer; "AutoRegisterError"
0x180012e22  call    SetDWORDKeyValue
0x180012e27  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e2e  lea     rax, WPP_GLOBAL_Control
0x180012e35  cmp     rcx, rax
0x180012e38  jz      short loc_180012E71
0x180012e3a  test    byte ptr [rcx+10Ch], 1
0x180012e41  jz      short loc_180012E71
0x180012e43  mov     rcx, [rcx+100h]
0x180012e4a  lea     r8, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids
0x180012e51  mov     edx, 1Fh
0x180012e56  mov     r9d, ebx
0x180012e59  call    WPP_SF_d
0x180012e5e  jmp     short loc_180012E71
0x180012e60  mov     edx, 1
0x180012e65  lea     rcx, ValueName; "CertificateRegistered"
0x180012e6c  call    SetDWORDKeyValue
0x180012e71  xor     eax, eax
0x180012e73  mov     rbx, [rsp+40h+arg_0]
0x180012e78  add     rsp, 40h
0x180012e7c  pop     rdi
0x180012e7d  pop     rsi
0x180012e7e  pop     rbp
0x180012e7f  retn
```
