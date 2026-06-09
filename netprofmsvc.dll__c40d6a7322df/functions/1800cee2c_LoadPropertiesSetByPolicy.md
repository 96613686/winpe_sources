# LoadPropertiesSetByPolicy

- ea: `0x1800cee2c`
- end: `0x1800cf304`
- name: `LoadPropertiesSetByPolicy`
- size: `1240`
- prototype: `void __fastcall(HKEY hkey, wchar_t *, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800cda9c`
- `0x1800cf5a8`

## callees

- `0x18000fab0`
- `0x180014d80`
- `0x180014fb0`
- `0x180038950`
- `0x180055c20`
- `0x1800a88a0`
- `0x1800caf10`
- `0x1800cbbf0`
- `0x1800cc4bc`
- `0x1800ce64c`
- `0x1800cee2c`
- `0x1800d0440`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf0ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf0ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf23c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf247`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf252`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf25d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf23c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf247`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf252`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cf25d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800cf0ab`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800cf0ab`

## string_xrefs

- `0x1800cf07d`: `IconPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall LoadPropertiesSetByPolicy(HKEY hkey, wchar_t *a2, __int64 a3)
{
  int v6; // r8d
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v9; // r8d
  int *v10; // rsi
  int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  int v14; // r8d
  PVOID *v15; // rcx
  char LastError; // al
  int v17; // esi
  unsigned int v18; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v19; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v20; // [rsp+5Ch] [rbp-A4h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h]
  unsigned __int8 *v22; // [rsp+68h] [rbp-98h]
  unsigned __int8 *v23; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 *v24; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v25[4]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t v26[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Src[520]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v25[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids);
  v25[0] = 514;
  if ( HrRegQueryValueEx(hkey, L"NetworkName", 0, (unsigned __int8 *)(a3 + 4), v25) )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_16;
    v8 = 59;
LABEL_15:
    WPP_SF_S(v7[2], v8, &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids, a2);
    goto LABEL_16;
  }
  if ( !(unsigned int)IsValidNetworkProfileName((const wchar_t *)(a3 + 4)) )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_16;
    v8 = 58;
    goto LABEL_15;
  }
  *(_DWORD *)a3 |= 1u;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, v6, (_DWORD)a2, a3 + 4);
LABEL_16:
  v25[0] = 2050;
  if ( HrRegQueryValueEx(hkey, L"Description", 0, (unsigned __int8 *)(a3 + 518), v25) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids, a2);
  }
  else
  {
    *(_DWORD *)a3 |= 2u;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, v9, (_DWORD)a2, a3 + 518);
  }
  v25[0] = 4;
  v10 = (int *)(a3 + 2568);
  if ( HrRegQueryValueEx(hkey, L"Category", 0, (unsigned __int8 *)(a3 + 2568), v25) )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v13 = 64;
      goto LABEL_34;
    }
  }
  else
  {
    v11 = *v10;
    if ( (unsigned int)*v10 < 2 )
    {
      *(_DWORD *)a3 |= 4u;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          62,
          (unsigned int)&WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids,
          (_DWORD)a2,
          v11);
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 63;
LABEL_34:
        WPP_SF_S(v12[2], v13, &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids, a2);
      }
    }
  }
  v25[0] = 1040;
  if ( !HrRegQueryValueEx(hkey, L"IconPath", 0, (unsigned __int8 *)Src, v25) )
  {
    if ( ExpandEnvironmentStringsW(Src, (LPWSTR)(a3 + 2572), 0x208u) )
    {
      *(_DWORD *)a3 |= 8u;
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_55;
      WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, v14, (_DWORD)a2, a3 + 2572);
    }
    else
    {
      LastError = GetLastError();
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_55;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        (unsigned int)&WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids,
        (unsigned int)Src,
        LastError);
    }
    goto LABEL_54;
  }
  pv = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  if ( !(unsigned int)LoadPolicyIcon(hkey, (__int64)&v18, (__int64)&v23, (__int64)&v19, (__int64)&v24, (__int64)&v20) )
  {
    v17 = SaveIconToDisk(a2, 16, 0, (const unsigned __int8 *)pv);
    if ( !v17 )
    {
      v17 = SaveIconToDisk(a2, 24, v18, v22);
      if ( !v17 )
      {
        v17 = SaveIconToDisk(a2, 32, v19, v23);
        if ( !v17 )
          v17 = SaveIconToDisk(a2, 48, v20, v24);
      }
    }
    CoTaskMemFree(pv);
    CoTaskMemFree(v22);
    CoTaskMemFree(v23);
    CoTaskMemFree(v24);
    if ( !v17 && !GetSystem32Directory(v26) )
    {
      StringCchPrintfW((wchar_t *)(a3 + 2572), 0x208u, L"%s\\networklist\\icons\\%s", v26, a2);
      *(_DWORD *)a3 |= 0x18u;
    }
    goto LABEL_54;
  }
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids, a2);
LABEL_54:
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_55:
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 )
    WPP_SF_(v15[2], 68, &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids);
}

```

## disassembly

```asm
0x1800cee2c  push    rbp
0x1800cee2e  push    rbx
0x1800cee2f  push    rsi
0x1800cee30  push    rdi
0x1800cee31  push    r13
0x1800cee33  push    r14
0x1800cee35  push    r15
0x1800cee37  lea     rbp, [rsp-5C0h]
0x1800cee3f  sub     rsp, 6C0h
0x1800cee46  mov     rax, cs:__security_cookie
0x1800cee4d  xor     rax, rsp
0x1800cee50  mov     [rbp+5F0h+var_40], rax
0x1800cee57  mov     rbx, r8
0x1800cee5a  mov     [rbp+5F0h+var_670], 0
0x1800cee61  mov     rdi, rdx
0x1800cee64  mov     r14, rcx
0x1800cee67  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cee6e  lea     r15, WPP_GLOBAL_Control
0x1800cee75  lea     r13, WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids
0x1800cee7c  cmp     rcx, r15
0x1800cee7f  jz      short loc_1800CEE98
0x1800cee81  test    byte ptr [rcx+1Ch], 8
0x1800cee85  jz      short loc_1800CEE98
0x1800cee87  mov     rcx, [rcx+10h]
0x1800cee8b  mov     edx, 38h ; '8'
0x1800cee90  mov     r8, r13
0x1800cee93  call    WPP_SF_
0x1800cee98  lea     rax, [rbp+5F0h+var_670]
0x1800cee9c  mov     [rbp+5F0h+var_670], 202h
0x1800ceea3  lea     rsi, [rbx+4]
0x1800ceea7  mov     [rsp+6F0h+var_6D0], rax; unsigned int *
0x1800ceeac  mov     r9, rsi; unsigned __int8 *
0x1800ceeaf  lea     rdx, aNetworkname; "NetworkName"
0x1800ceeb6  xor     r8d, r8d; unsigned int *
0x1800ceeb9  mov     rcx, r14; HKEY
0x1800ceebc  call    ?HrRegQueryValueEx@@YAJPEAUHKEY__@@PEB_WPEAKPEAE2@Z; HrRegQueryValueEx(HKEY__ *,wchar_t const *,ulong *,uchar *,ulong *)
0x1800ceec1  test    eax, eax
0x1800ceec3  jnz     short loc_1800CEF17
0x1800ceec5  mov     rcx, rsi; String
0x1800ceec8  call    ?IsValidNetworkProfileName@@YAHPEB_W@Z; IsValidNetworkProfileName(wchar_t const *)
0x1800ceecd  test    eax, eax
0x1800ceecf  jz      short loc_1800CEEFE
0x1800ceed1  or      dword ptr [rbx], 1
0x1800ceed4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ceedb  cmp     rcx, r15
0x1800ceede  jz      short loc_1800CEF3D
0x1800ceee0  test    byte ptr [rcx+1Ch], 8
0x1800ceee4  jz      short loc_1800CEF3D
0x1800ceee6  mov     rcx, [rcx+10h]
0x1800ceeea  mov     edx, 39h ; '9'
0x1800ceeef  mov     r9, rdi
0x1800ceef2  mov     [rsp+6F0h+var_6D0], rsi
0x1800ceef7  call    WPP_SF_SS
0x1800ceefc  jmp     short loc_1800CEF3D
0x1800ceefe  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cef05  cmp     rcx, r15
0x1800cef08  jz      short loc_1800CEF3D
0x1800cef0a  test    byte ptr [rcx+1Ch], 1
0x1800cef0e  jz      short loc_1800CEF3D
0x1800cef10  mov     edx, 3Ah ; ':'
0x1800cef15  jmp     short loc_1800CEF2E
0x1800cef17  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cef1e  cmp     rcx, r15
0x1800cef21  jz      short loc_1800CEF3D
0x1800cef23  test    byte ptr [rcx+1Ch], 4
0x1800cef27  jz      short loc_1800CEF3D
0x1800cef29  mov     edx, 3Bh ; ';'
0x1800cef2e  mov     rcx, [rcx+10h]
0x1800cef32  mov     r9, rdi
0x1800cef35  mov     r8, r13
0x1800cef38  call    WPP_SF_S
0x1800cef3d  lea     rax, [rbp+5F0h+var_670]
0x1800cef41  mov     [rbp+5F0h+var_670], 802h
0x1800cef48  lea     rsi, [rbx+206h]
0x1800cef4f  mov     [rsp+6F0h+var_6D0], rax; unsigned int *
0x1800cef54  mov     r9, rsi; unsigned __int8 *
0x1800cef57  lea     rdx, aDescription; "Description"
0x1800cef5e  xor     r8d, r8d; unsigned int *
0x1800cef61  mov     rcx, r14; HKEY
0x1800cef64  call    ?HrRegQueryValueEx@@YAJPEAUHKEY__@@PEB_WPEAKPEAE2@Z; HrRegQueryValueEx(HKEY__ *,wchar_t const *,ulong *,uchar *,ulong *)
0x1800cef69  test    eax, eax
0x1800cef6b  jnz     short loc_1800CEF98
0x1800cef6d  or      dword ptr [rbx], 2
0x1800cef70  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cef77  cmp     rcx, r15
0x1800cef7a  jz      short loc_1800CEFBE
0x1800cef7c  test    byte ptr [rcx+1Ch], 8
0x1800cef80  jz      short loc_1800CEFBE
0x1800cef82  mov     rcx, [rcx+10h]
0x1800cef86  lea     edx, [rax+3Ch]
0x1800cef89  mov     r9, rdi
0x1800cef8c  mov     [rsp+6F0h+var_6D0], rsi
0x1800cef91  call    WPP_SF_SS
0x1800cef96  jmp     short loc_1800CEFBE
0x1800cef98  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cef9f  cmp     rcx, r15
0x1800cefa2  jz      short loc_1800CEFBE
0x1800cefa4  test    byte ptr [rcx+1Ch], 4
0x1800cefa8  jz      short loc_1800CEFBE
0x1800cefaa  mov     rcx, [rcx+10h]
0x1800cefae  mov     edx, 3Dh ; '='
0x1800cefb3  mov     r9, rdi
0x1800cefb6  mov     r8, r13
0x1800cefb9  call    WPP_SF_S
0x1800cefbe  lea     rax, [rbp+5F0h+var_670]
0x1800cefc2  mov     [rbp+5F0h+var_670], 4
0x1800cefc9  lea     rsi, [rbx+0A08h]
0x1800cefd0  mov     [rsp+6F0h+var_6D0], rax; unsigned int *
0x1800cefd5  mov     r9, rsi; unsigned __int8 *
0x1800cefd8  lea     rdx, aCategory; "Category"
0x1800cefdf  xor     r8d, r8d; unsigned int *
0x1800cefe2  mov     rcx, r14; HKEY
0x1800cefe5  call    ?HrRegQueryValueEx@@YAJPEAUHKEY__@@PEB_WPEAKPEAE2@Z; HrRegQueryValueEx(HKEY__ *,wchar_t const *,ulong *,uchar *,ulong *)
0x1800cefea  test    eax, eax
0x1800cefec  jnz     short loc_1800CF03D
0x1800cefee  mov     eax, [rsi]
0x1800ceff0  cmp     eax, 2
0x1800ceff3  jb      short loc_1800CF00E
0x1800ceff5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ceffc  cmp     rcx, r15
0x1800cefff  jz      short loc_1800CF063
0x1800cf001  test    byte ptr [rcx+1Ch], 1
0x1800cf005  jz      short loc_1800CF063
0x1800cf007  mov     edx, 3Fh ; '?'
0x1800cf00c  jmp     short loc_1800CF054
0x1800cf00e  or      dword ptr [rbx], 4
0x1800cf011  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf018  cmp     rcx, r15
0x1800cf01b  jz      short loc_1800CF063
0x1800cf01d  test    byte ptr [rcx+1Ch], 8
0x1800cf021  jz      short loc_1800CF063
0x1800cf023  mov     rcx, [rcx+10h]
0x1800cf027  mov     edx, 3Eh ; '>'
0x1800cf02c  mov     r9, rdi
0x1800cf02f  mov     dword ptr [rsp+6F0h+var_6D0], eax
0x1800cf033  mov     r8, r13
0x1800cf036  call    WPP_SF_Sd
0x1800cf03b  jmp     short loc_1800CF063
0x1800cf03d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf044  cmp     rcx, r15
0x1800cf047  jz      short loc_1800CF063
0x1800cf049  test    byte ptr [rcx+1Ch], 4
0x1800cf04d  jz      short loc_1800CF063
0x1800cf04f  mov     edx, 40h ; '@'
0x1800cf054  mov     rcx, [rcx+10h]
0x1800cf058  mov     r9, rdi
0x1800cf05b  mov     r8, r13
0x1800cf05e  call    WPP_SF_S
0x1800cf063  lea     rax, [rbp+5F0h+var_670]
0x1800cf067  mov     [rbp+5F0h+var_670], 410h
0x1800cf06e  lea     r9, [rbp+5F0h+Src]; unsigned __int8 *
0x1800cf075  mov     [rsp+6F0h+var_6D0], rax; unsigned int *
0x1800cf07a  xor     r8d, r8d; unsigned int *
0x1800cf07d  lea     rdx, aIconpath; "IconPath"
0x1800cf084  mov     rcx, r14; HKEY
0x1800cf087  call    ?HrRegQueryValueEx@@YAJPEAUHKEY__@@PEB_WPEAKPEAE2@Z; HrRegQueryValueEx(HKEY__ *,wchar_t const *,ulong *,uchar *,ulong *)
0x1800cf08c  test    eax, eax
0x1800cf08e  jnz     loc_1800CF13A
0x1800cf094  lea     rsi, [rbx+0A0Ch]
0x1800cf09b  mov     r8d, 208h; nSize
0x1800cf0a1  mov     rdx, rsi; lpDst
0x1800cf0a4  lea     rcx, [rbp+5F0h+Src]; lpSrc
0x1800cf0ab  call    cs:__imp_ExpandEnvironmentStringsW
0x1800cf0b1  test    eax, eax
0x1800cf0b3  jz      short loc_1800CF0ED
0x1800cf0b5  or      dword ptr [rbx], 8
0x1800cf0b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf0bf  cmp     rcx, r15
0x1800cf0c2  jz      loc_1800CF2E3
0x1800cf0c8  test    byte ptr [rcx+1Ch], 8
0x1800cf0cc  jz      loc_1800CF2C7
0x1800cf0d2  mov     rcx, [rcx+10h]
0x1800cf0d6  mov     edx, 41h ; 'A'
0x1800cf0db  mov     r9, rdi
0x1800cf0de  mov     [rsp+6F0h+var_6D0], rsi
0x1800cf0e3  call    WPP_SF_SS
0x1800cf0e8  jmp     loc_1800CF2C0
0x1800cf0ed  call    cs:__imp_GetLastError
0x1800cf0f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf0fa  cmp     rcx, r15
0x1800cf0fd  jz      loc_1800CF2E3
0x1800cf103  test    byte ptr [rcx+1Ch], 1
0x1800cf107  jz      loc_1800CF2C7
0x1800cf10d  test    eax, eax
0x1800cf10f  jle     short loc_1800CF119
0x1800cf111  movzx   eax, ax
0x1800cf114  or      eax, 80070000h
0x1800cf119  mov     rcx, [rcx+10h]
0x1800cf11d  lea     r9, [rbp+5F0h+Src]
0x1800cf124  mov     edx, 42h ; 'B'
0x1800cf129  mov     dword ptr [rsp+6F0h+var_6D0], eax
0x1800cf12d  mov     r8, r13
0x1800cf130  call    WPP_SF_Sd
0x1800cf135  jmp     loc_1800CF2C0
0x1800cf13a  lea     rax, [rsp+6F0h+var_694]
0x1800cf13f  mov     [rsp+6F0h+pv], 0
0x1800cf148  mov     [rsp+6F0h+var_6B0], rax; __int64
0x1800cf14d  lea     r9, [rsp+6F0h+var_688]
0x1800cf152  lea     rax, [rsp+6F0h+var_678]
0x1800cf157  mov     [rsp+6F0h+var_688], 0
0x1800cf160  mov     [rsp+6F0h+var_6B8], rax; __int64
0x1800cf165  lea     r8, [rsp+6F0h+var_6A0]
0x1800cf16a  lea     rax, [rsp+6F0h+var_698]
0x1800cf16f  mov     [rsp+6F0h+var_680], 0
0x1800cf178  mov     [rsp+6F0h+var_6C0], rax; __int64
0x1800cf17d  lea     rdx, [rsp+6F0h+pv]
0x1800cf182  lea     rax, [rsp+6F0h+var_680]
0x1800cf187  mov     [rsp+6F0h+var_678], 0
0x1800cf190  mov     [rsp+6F0h+var_6C8], rax; __int64
0x1800cf195  mov     rcx, r14; hkey
0x1800cf198  lea     rax, [rsp+6F0h+var_69C]
0x1800cf19d  mov     [rsp+6F0h+var_6A0], 0
0x1800cf1a5  mov     [rsp+6F0h+var_6D0], rax; __int64
0x1800cf1aa  mov     [rsp+6F0h+var_69C], 0
0x1800cf1b2  mov     [rsp+6F0h+var_698], 0
0x1800cf1ba  mov     [rsp+6F0h+var_694], 0
0x1800cf1c2  call    LoadPolicyIcon
0x1800cf1c7  test    eax, eax
0x1800cf1c9  jnz     loc_1800CF29A
0x1800cf1cf  mov     r9, [rsp+6F0h+pv]; unsigned __int8 *
0x1800cf1d4  lea     edx, [rax+10h]; unsigned int
0x1800cf1d7  mov     r8d, [rsp+6F0h+var_6A0]; unsigned int
0x1800cf1dc  mov     rcx, rdi; wchar_t *
0x1800cf1df  call    ?SaveIconToDisk@@YAJPEB_WKKPEBE@Z; SaveIconToDisk(wchar_t const *,ulong,ulong,uchar const *)
0x1800cf1e4  mov     esi, eax
0x1800cf1e6  test    eax, eax
0x1800cf1e8  jnz     short loc_1800CF237
0x1800cf1ea  mov     r9, [rsp+6F0h+var_688]; unsigned __int8 *
0x1800cf1ef  lea     edx, [rax+18h]; unsigned int
0x1800cf1f2  mov     r8d, [rsp+6F0h+var_69C]; unsigned int
0x1800cf1f7  mov     rcx, rdi; wchar_t *
0x1800cf1fa  call    ?SaveIconToDisk@@YAJPEB_WKKPEBE@Z; SaveIconToDisk(wchar_t const *,ulong,ulong,uchar const *)
0x1800cf1ff  mov     esi, eax
0x1800cf201  test    eax, eax
0x1800cf203  jnz     short loc_1800CF237
0x1800cf205  mov     r9, [rsp+6F0h+var_680]; unsigned __int8 *
0x1800cf20a  lea     edx, [rax+20h]; unsigned int
0x1800cf20d  mov     r8d, [rsp+6F0h+var_698]; unsigned int
0x1800cf212  mov     rcx, rdi; wchar_t *
0x1800cf215  call    ?SaveIconToDisk@@YAJPEB_WKKPEBE@Z; SaveIconToDisk(wchar_t const *,ulong,ulong,uchar const *)
0x1800cf21a  mov     esi, eax
0x1800cf21c  test    eax, eax
0x1800cf21e  jnz     short loc_1800CF237
0x1800cf220  mov     r9, [rsp+6F0h+var_678]; unsigned __int8 *
0x1800cf225  lea     edx, [rax+30h]; unsigned int
0x1800cf228  mov     r8d, [rsp+6F0h+var_694]; unsigned int
0x1800cf22d  mov     rcx, rdi; wchar_t *
0x1800cf230  call    ?SaveIconToDisk@@YAJPEB_WKKPEBE@Z; SaveIconToDisk(wchar_t const *,ulong,ulong,uchar const *)
0x1800cf235  mov     esi, eax
0x1800cf237  mov     rcx, [rsp+6F0h+pv]; pv
0x1800cf23c  call    cs:__imp_CoTaskMemFree
0x1800cf242  mov     rcx, [rsp+6F0h+var_688]; pv
0x1800cf247  call    cs:__imp_CoTaskMemFree
0x1800cf24d  mov     rcx, [rsp+6F0h+var_680]; pv
0x1800cf252  call    cs:__imp_CoTaskMemFree
0x1800cf258  mov     rcx, [rsp+6F0h+var_678]; pv
0x1800cf25d  call    cs:__imp_CoTaskMemFree
0x1800cf263  test    esi, esi
0x1800cf265  jnz     short loc_1800CF2C0
0x1800cf267  lea     rcx, [rbp+5F0h+var_660]; wchar_t *
0x1800cf26b  call    ?GetSystem32Directory@@YAKPEA_W@Z; GetSystem32Directory(wchar_t *)
0x1800cf270  test    eax, eax
0x1800cf272  jnz     short loc_1800CF2C0
0x1800cf274  lea     rcx, [rbx+0A0Ch]; wchar_t *
0x1800cf27b  mov     [rsp+6F0h+var_6D0], rdi
0x1800cf280  lea     r9, [rbp+5F0h+var_660]
0x1800cf284  mov     edx, 208h; unsigned __int64
0x1800cf289  lea     r8, aSNetworklistIc; "%s\\networklist\\icons\\%s"
0x1800cf290  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800cf295  or      dword ptr [rbx], 18h
0x1800cf298  jmp     short loc_1800CF2C0
0x1800cf29a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf2a1  cmp     rcx, r15
0x1800cf2a4  jz      short loc_1800CF2E3
0x1800cf2a6  test    byte ptr [rcx+1Ch], 4
0x1800cf2aa  jz      short loc_1800CF2C7
0x1800cf2ac  mov     rcx, [rcx+10h]
0x1800cf2b0  mov     edx, 43h ; 'C'
0x1800cf2b5  mov     r9, rdi
0x1800cf2b8  mov     r8, r13
0x1800cf2bb  call    WPP_SF_S
0x1800cf2c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf2c7  cmp     rcx, r15
0x1800cf2ca  jz      short loc_1800CF2E3
0x1800cf2cc  test    byte ptr [rcx+1Ch], 8
0x1800cf2d0  jz      short loc_1800CF2E3
0x1800cf2d2  mov     rcx, [rcx+10h]
0x1800cf2d6  mov     edx, 44h ; 'D'
0x1800cf2db  mov     r8, r13
0x1800cf2de  call    WPP_SF_
0x1800cf2e3  mov     rcx, [rbp+5F0h+var_40]
0x1800cf2ea  xor     rcx, rsp; StackCookie
0x1800cf2ed  call    __security_check_cookie
0x1800cf2f2  add     rsp, 6C0h
0x1800cf2f9  pop     r15
0x1800cf2fb  pop     r14
0x1800cf2fd  pop     r13
0x1800cf2ff  pop     rdi
0x1800cf300  pop     rsi
0x1800cf301  pop     rbx
  ... truncated ...
```
