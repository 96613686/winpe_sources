# CMbaeManagerInternal::_GetConnectionName(_GUID const &,ushort const *,ushort * *)

- ea: `0x180015a60`
- end: `0x180015f77`
- name: `?_GetConnectionName@CMbaeManagerInternal@@AEAAJAEBU_GUID@@PEBGPEAPEAG@Z`
- size: `1303`
- prototype: `__int64 __fastcall(CMbaeManagerInternal *__hidden this, const struct _GUID *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014f20`

## callees

- `0x1800024e0`
- `0x180002f68`
- `0x180009474`
- `0x1800143bc`
- `0x180014410`
- `0x1800156cc`
- `0x1800156f0`
- `0x180015a60`
- `0x180016134`
- `0x180016254`
- `0x180032148`
- `0x180032750`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180015d48`
- `OLEAUT32!__imp_SysAllocString` at `0x180015e3f`
- `OLEAUT32!__imp_SysAllocString` at `0x180015e6b`
- `OLEAUT32!__imp_SysAllocString` at `0x180015d48`
- `OLEAUT32!__imp_SysAllocString` at `0x180015e3f`
- `OLEAUT32!__imp_SysAllocString` at `0x180015e6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180015f45`
- `OLEAUT32!__imp_SysFreeString` at `0x180015f45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015ec0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015ec0`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180015e28`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180015f36`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180015e28`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180015f36`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180015ba3`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180015dc9`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180015dff`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180015e15`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180015e57`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180015f22`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180015ba3`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180015dc9`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180015dff`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180015e15`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180015e57`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180015f22`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180015b17`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180015b17`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180015b7f`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180015da8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180015b7f`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180015da8`

## pseudocode

```c
__int64 __fastcall CMbaeManagerInternal::_GetConnectionName(
        CMbaeManagerInternal *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  unsigned int v7; // eax
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  unsigned int v10; // ebx
  unsigned int Interface; // ebx
  __int64 v12; // r8
  int v13; // edi
  int StringValue; // eax
  const unsigned __int16 *v15; // rdx
  const unsigned __int16 *v16; // r9
  wil::details::in1diag3 *v17; // rcx
  __int64 v18; // rdx
  int DwordValue; // eax
  const unsigned __int16 *v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // r9d
  bool v23; // zf
  char v24; // bl
  const char *v25; // rdx
  __int64 v26; // rax
  BSTR v27; // rax
  __int64 v28; // rcx
  OLECHAR *v29; // rbx
  unsigned int v30; // ebx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  const unsigned __int16 *v35; // r14
  unsigned __int64 v36; // rsi
  unsigned __int64 v37; // r15
  unsigned __int16 *v38; // rax
  unsigned int v39; // edi
  __int64 v40; // rcx
  unsigned __int16 *v41; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v42; // [rsp+28h] [rbp-D8h]
  __int64 v43; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v44; // [rsp+48h] [rbp-B8h] BYREF
  BYTE v45[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v46; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v47; // [rsp+60h] [rbp-A0h] BYREF
  int v48; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v49; // [rsp+68h] [rbp-98h]
  wchar_t Buffer[56]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v51; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v52; // [rsp+E8h] [rbp-18h] BYREF
  const char *v53; // [rsp+F0h] [rbp-10h]
  __int64 v54; // [rsp+F8h] [rbp-8h]
  const struct _GUID *v55; // [rsp+100h] [rbp+0h]
  __int64 v56; // [rsp+108h] [rbp+8h]
  const char *v57; // [rsp+110h] [rbp+10h]
  int v58; // [rsp+118h] [rbp+18h]
  int v59; // [rsp+11Ch] [rbp+1Ch]
  OLECHAR psz[512]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+568h] [rbp+468h]

  if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
  {
    v53 = "CMbaeManagerInternal::_GetConnectionName";
    v54 = 41;
    v55 = a2;
    v56 = 16;
    v41 = (unsigned __int16 *)&v51;
    McGenEventWrite_EventWriteTransfer(&CtlGuid_Context, CMbaeManagerInternal_cpp622, a3, 3);
  }
  v49 = 0;
  *a4 = 0;
  v48 = 0;
  v43 = 0;
  v47 = 0;
  v46 = -1;
  v7 = WwanOpenHandle(1, 0, &v48, &v46);
  if ( v7 )
  {
    v8 = v7;
    v9 = 632;
LABEL_5:
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v9,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaemanagerinternal.cpp",
            (const char *)v8,
            (unsigned int)v41);
LABEL_42:
    v33 = v43;
    v43 = 0;
    if ( v33 )
      WwanFreeMemory(v33);
    if ( v46 != -1 )
      WwanCloseHandle(v46, 0);
    return v10;
  }
  v51 = (unsigned __int16 *)&v43;
  v52 = 0;
  LOBYTE(v53) = 1;
  v42 = (unsigned __int64 *)&v52;
  v41 = (unsigned __int16 *)&v47;
  Interface = WwanQueryInterface(v46, a2, 3);
  if ( (_BYTE)v53 )
  {
    v12 = *(_QWORD *)v51;
    *(_QWORD *)v51 = v52;
    if ( v12 )
      WwanFreeMemory(v12);
  }
  if ( Interface )
  {
    v8 = Interface;
    v9 = 634;
    goto LABEL_5;
  }
  v13 = *(_DWORD *)(v43 + 12);
  *(_DWORD *)v45 = 0;
  StringValue = swprintf_s(Buffer, 0x16u, L"%s", a3);
  v17 = retaddr;
  if ( StringValue < 0 )
  {
    v18 = 641;
LABEL_13:
    wil::details::in1diag3::_Log_Hr(
      v17,
      (void *)v18,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaemanagerinternal.cpp",
      (const char *)(unsigned int)StringValue,
      (int)v41);
    goto LABEL_35;
  }
  DwordValue = MVConfigurationHelper::GetDwordValue((MVConfigurationHelper *)Buffer, v15, 4u, v16, v45);
  if ( DwordValue < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x287,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaemanagerinternal.cpp",
      (const char *)(unsigned int)DwordValue,
      (int)v41);
    goto LABEL_16;
  }
  if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 4) != 0 )
    McTemplateU0sd_EventWriteTransfer(
      retaddr,
      CMbaeManagerInternal_cpp649,
      "CMbaeManagerInternal::_GetConnectionName",
      *(unsigned int *)v45);
  if ( !*(_DWORD *)v45 )
    goto LABEL_16;
  if ( *(_DWORD *)v45 == 1 )
  {
    v23 = ((v13 - 3) & 0xFFFFFFFD) == 0;
    goto LABEL_17;
  }
  if ( *(_DWORD *)v45 != 2 )
  {
LABEL_16:
    v23 = v13 == 3;
LABEL_17:
    v24 = v23;
    goto LABEL_18;
  }
  v24 = 1;
LABEL_18:
  if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 4) != 0 )
  {
    v25 = "TRUE";
    if ( !v24 )
      v25 = "FALSE";
    LODWORD(v44) = v13;
    v53 = "CMbaeManagerInternal::_GetConnectionName";
    v54 = 41;
    v55 = (const struct _GUID *)&v44;
    v56 = 4;
    v26 = -1;
    do
      ++v26;
    while ( v25[v26] );
    v57 = v25;
    v58 = v26 + 1;
    v59 = 0;
    v41 = (unsigned __int16 *)&v51;
    McGenEventWrite_EventWriteTransfer(&CtlGuid_Context, CMbaeManagerInternal_cpp671, v21, 4);
  }
  if ( v24 )
  {
    StringValue = MVConfigurationHelper::GetStringValue((MVConfigurationHelper *)Buffer, v20, 4u, v22, v41, (LPBYTE)psz);
    v17 = retaddr;
    if ( StringValue < 0 )
    {
      v18 = 681;
      goto LABEL_13;
    }
    v27 = SysAllocString(psz);
    v29 = v27;
    if ( v27 )
    {
LABEL_51:
      v35 = v27;
      goto LABEL_52;
    }
  }
LABEL_35:
  if ( (unsigned int)(v13 - 4) <= 1 )
  {
    v27 = SysAllocString((const OLECHAR *)(v43 + 34));
    v29 = v27;
    goto LABEL_51;
  }
  v44 = 0;
  v51 = (unsigned __int16 *)&v44;
  v52 = 0;
  LOBYTE(v53) = 1;
  v42 = (unsigned __int64 *)&v52;
  v41 = (unsigned __int16 *)&v47;
  v30 = WwanQueryInterface(v46, a2, 13);
  if ( (_BYTE)v53 )
  {
    v31 = *(_QWORD *)v51;
    *(_QWORD *)v51 = v52;
    if ( v31 )
      WwanFreeMemory(v31);
  }
  if ( v30 )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x2BD,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaemanagerinternal.cpp",
            (const char *)v30,
            (unsigned int)&v47);
    v32 = v44;
    v44 = 0;
    if ( v32 )
      WwanFreeMemory(v32);
    goto LABEL_42;
  }
  v29 = SysAllocString((const OLECHAR *)(v44 + 20));
  v28 = v44;
  v44 = 0;
  if ( v28 )
    WwanFreeMemory(v28);
  v35 = v29;
LABEL_52:
  if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 4) != 0 )
    McTemplateU0sz_EventWriteTransfer(v28, CMbaeManagerInternal_cpp707, "CMbaeManagerInternal::_GetConnectionName", v29);
  v36 = -1;
  do
    ++v36;
  while ( v35[v36] );
  *a4 = 0;
  v37 = v36 + 1;
  if ( v36 + 1 < v36 || !is_mul_ok(v37, 2u) )
  {
    v39 = -2147024362;
    goto LABEL_61;
  }
  v38 = (unsigned __int16 *)CoTaskMemAlloc(2 * v37);
  *a4 = v38;
  v39 = v38 == 0 ? 0x8007000E : 0;
  if ( !v38 )
  {
LABEL_61:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C4,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaemanagerinternal.cpp",
      (const char *)v39,
      (int)v41);
    goto LABEL_62;
  }
  StringCchCopyNExW(v38, v36 + 1, v35, v36, (unsigned __int16 **)v41, v42, 0);
LABEL_62:
  v40 = v43;
  v43 = 0;
  if ( v40 )
    WwanFreeMemory(v40);
  if ( v46 != -1 )
    WwanCloseHandle(v46, 0);
  if ( v29 )
    SysFreeString(v29);
  return v39;
}

```

## disassembly

```asm
0x180015a60  mov     [rsp-8+arg_0], rbx
0x180015a65  push    rbp
0x180015a66  push    rsi
0x180015a67  push    rdi
0x180015a68  push    r12
0x180015a6a  push    r13
0x180015a6c  push    r14
0x180015a6e  push    r15
0x180015a70  lea     rbp, [rsp-430h]
0x180015a78  sub     rsp, 530h
0x180015a7f  mov     rax, cs:__security_cookie
0x180015a86  xor     rax, rsp
0x180015a89  mov     [rbp+460h+var_40], rax
0x180015a90  mov     r12, r9
0x180015a93  mov     rsi, r8
0x180015a96  mov     r14, rdx
0x180015a99  lea     rax, aCmbaemanagerin_1; "CMbaeManagerInternal::_GetConnectionNam"...
0x180015aa0  xor     r13d, r13d
0x180015aa3  lea     ebx, [r13+3]
0x180015aa7  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 1
0x180015aae  jz      short loc_180015AE7
0x180015ab0  mov     [rbp+460h+var_470], rax
0x180015ab4  mov     [rbp+460h+var_468], 29h ; ')'
0x180015abc  mov     [rbp+460h+var_460], rdx
0x180015ac0  mov     [rbp+460h+var_458], 10h
0x180015ac8  lea     rax, [rbp+460h+var_480]
0x180015acc  mov     [rsp+560h+var_540], rax; unsigned int
0x180015ad1  mov     r9d, ebx
0x180015ad4  lea     rdx, CMbaeManagerInternal_cpp622
0x180015adb  lea     rcx, CtlGuid_Context
0x180015ae2  call    McGenEventWrite_EventWriteTransfer
0x180015ae7  mov     [rsp+560h+var_4F8], r13
0x180015aec  mov     [r12], r13
0x180015af0  mov     [rsp+560h+var_4FC], r13d
0x180015af5  mov     [rsp+560h+var_520], r13
0x180015afa  mov     [rsp+560h+var_500], r13d
0x180015aff  or      r15, 0FFFFFFFFFFFFFFFFh
0x180015b03  mov     [rsp+560h+var_508], r15
0x180015b08  lea     r9, [rsp+560h+var_508]
0x180015b0d  lea     r8, [rsp+560h+var_4FC]
0x180015b12  xor     edx, edx
0x180015b14  lea     ecx, [rdx+1]
0x180015b17  call    cs:__imp_WwanOpenHandle
0x180015b1d  test    eax, eax
0x180015b1f  jz      short loc_180015B43
0x180015b21  mov     r9d, eax; char *
0x180015b24  mov     edx, 278h; void *
0x180015b29  lea     r8, aOnecoreuapNetM_4; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180015b30  mov     rcx, [rbp+468h]; this
0x180015b37  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180015b3c  mov     ebx, eax
0x180015b3e  jmp     loc_180015E06
0x180015b43  lea     rax, [rsp+560h+var_520]
0x180015b48  mov     [rbp+460h+var_480], rax
0x180015b4c  mov     [rbp+460h+var_478], r13
0x180015b50  mov     byte ptr [rbp+460h+var_470], 1
0x180015b54  mov     [rsp+560h+var_528], r13
0x180015b59  mov     qword ptr [rsp+560h+var_530], r13; unsigned int
0x180015b5e  lea     rax, [rbp+460h+var_478]
0x180015b62  mov     [rsp+560h+var_538], rax
0x180015b67  lea     rax, [rsp+560h+var_500]
0x180015b6c  mov     [rsp+560h+var_540], rax; int
0x180015b71  xor     r9d, r9d
0x180015b74  mov     r8d, ebx
0x180015b77  mov     rdx, r14
0x180015b7a  mov     rcx, [rsp+560h+var_508]
0x180015b7f  call    cs:__imp_WwanQueryInterface
0x180015b85  mov     ebx, eax
0x180015b87  cmp     byte ptr [rbp+460h+var_470], r13b
0x180015b8b  jz      short loc_180015BA9
0x180015b8d  mov     rdx, [rbp+460h+var_480]
0x180015b91  mov     r8, [rdx]
0x180015b94  mov     rcx, [rbp+460h+var_478]
0x180015b98  mov     [rdx], rcx
0x180015b9b  test    r8, r8
0x180015b9e  jz      short loc_180015BA9
0x180015ba0  mov     rcx, r8
0x180015ba3  call    cs:__imp_WwanFreeMemory
0x180015ba9  test    ebx, ebx
0x180015bab  jz      short loc_180015BBA
0x180015bad  mov     r9d, ebx
0x180015bb0  mov     edx, 27Ah
0x180015bb5  jmp     loc_180015B29
0x180015bba  mov     rax, [rsp+560h+var_520]
0x180015bbf  mov     edi, [rax+0Ch]
0x180015bc2  mov     dword ptr [rsp+560h+var_510], r13d
0x180015bc7  mov     r9, rsi
0x180015bca  lea     r8, aS_0; "%s"
0x180015bd1  mov     edx, 16h; BufferCount
0x180015bd6  lea     rcx, [rsp+560h+Buffer]; Buffer
0x180015bdb  call    swprintf_s
0x180015be0  mov     rcx, [rbp+468h]; this
0x180015be7  mov     esi, 4
0x180015bec  test    eax, eax
0x180015bee  jns     short loc_180015C09
0x180015bf0  mov     edx, 281h; void *
0x180015bf5  lea     r8, aOnecoreuapNetM_4; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180015bfc  mov     r9d, eax; char *
0x180015bff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180015c04  jmp     loc_180015D5A
0x180015c09  lea     rax, [rsp+560h+var_510]
0x180015c0e  mov     [rsp+560h+var_540], rax; int
0x180015c13  mov     r8d, esi; unsigned int
0x180015c16  lea     rcx, [rsp+560h+Buffer]; this
0x180015c1b  call    ?GetDwordValue@MVConfigurationHelper@@QEAAJPEBGK0AEAK@Z; MVConfigurationHelper::GetDwordValue(ushort const *,ulong,ushort const *,ulong &)
0x180015c20  mov     rcx, [rbp+468h]; this
0x180015c27  test    eax, eax
0x180015c29  jns     loc_180015CF5
0x180015c2f  mov     r9d, eax; char *
0x180015c32  lea     r8, aOnecoreuapNetM_4; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180015c39  mov     edx, 287h; void *
0x180015c3e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180015c43  cmp     edi, 3
0x180015c46  setz    bl
0x180015c49  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, sil
0x180015c50  jz      short loc_180015CC2
0x180015c52  lea     rax, aFalse_0; "FALSE"
0x180015c59  lea     rdx, aTrue_0; "TRUE"
0x180015c60  test    bl, bl
0x180015c62  cmovz   rdx, rax
0x180015c66  mov     dword ptr [rsp+560h+var_518], edi
0x180015c6a  lea     rax, aCmbaemanagerin_1; "CMbaeManagerInternal::_GetConnectionNam"...
0x180015c71  mov     [rbp+460h+var_470], rax
0x180015c75  mov     [rbp+460h+var_468], 29h ; ')'
0x180015c7d  lea     rax, [rsp+560h+var_518]
0x180015c82  mov     [rbp+460h+var_460], rax
0x180015c86  mov     [rbp+460h+var_458], rsi
0x180015c8a  mov     rax, r15
0x180015c8d  inc     rax
0x180015c90  cmp     [rdx+rax], r13b
0x180015c94  jnz     short loc_180015C8D
0x180015c96  inc     eax
0x180015c98  mov     [rbp+460h+var_450], rdx
0x180015c9c  mov     [rbp+460h+var_448], eax
0x180015c9f  mov     [rbp+460h+var_444], r13d
0x180015ca3  lea     rax, [rbp+460h+var_480]
0x180015ca7  mov     [rsp+560h+var_540], rax; int
0x180015cac  mov     r9d, esi
0x180015caf  lea     rdx, CMbaeManagerInternal_cpp671
0x180015cb6  lea     rcx, CtlGuid_Context
0x180015cbd  call    McGenEventWrite_EventWriteTransfer
0x180015cc2  test    bl, bl
0x180015cc4  jz      loc_180015D5A
0x180015cca  lea     rax, [rbp+460h+psz]
0x180015cce  mov     [rsp+560h+var_538], rax; unsigned __int64 *
0x180015cd3  mov     r8d, esi; unsigned int
0x180015cd6  lea     rcx, [rsp+560h+Buffer]; this
0x180015cdb  call    ?GetStringValue@MVConfigurationHelper@@QEAAJPEBGKK0PEAG@Z; MVConfigurationHelper::GetStringValue(ushort const *,ulong,ulong,ushort const *,ushort *)
0x180015ce0  mov     rcx, [rbp+468h]
0x180015ce7  test    eax, eax
0x180015ce9  jns     short loc_180015D44
0x180015ceb  mov     edx, 2A9h
0x180015cf0  jmp     loc_180015BF5
0x180015cf5  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, sil
0x180015cfc  jz      short loc_180015D16
0x180015cfe  mov     r9d, dword ptr [rsp+560h+var_510]
0x180015d03  lea     r8, aCmbaemanagerin_1; "CMbaeManagerInternal::_GetConnectionNam"...
0x180015d0a  lea     rdx, CMbaeManagerInternal_cpp649
0x180015d11  call    McTemplateU0sd_EventWriteTransfer
0x180015d16  mov     eax, dword ptr [rsp+560h+var_510]
0x180015d1a  test    eax, eax
0x180015d1c  jz      loc_180015C43
0x180015d22  sub     eax, 1
0x180015d25  jz      short loc_180015D37
0x180015d27  cmp     eax, 1
0x180015d2a  jnz     loc_180015C43
0x180015d30  mov     bl, al
0x180015d32  jmp     loc_180015C49
0x180015d37  lea     eax, [rdi-3]
0x180015d3a  test    eax, 0FFFFFFFDh
0x180015d3f  jmp     loc_180015C46
0x180015d44  lea     rcx, [rbp+460h+psz]; psz
0x180015d48  call    cs:__imp_SysAllocString
0x180015d4e  mov     rbx, rax
0x180015d51  test    rax, rax
0x180015d54  jnz     loc_180015E74
0x180015d5a  lea     eax, [rdi-4]
0x180015d5d  cmp     eax, 1
0x180015d60  jbe     loc_180015E62
0x180015d66  mov     [rsp+560h+var_518], r13
0x180015d6b  lea     rax, [rsp+560h+var_518]
0x180015d70  mov     [rbp+460h+var_480], rax
0x180015d74  mov     [rbp+460h+var_478], r13
0x180015d78  mov     byte ptr [rbp+460h+var_470], 1
0x180015d7c  mov     [rsp+560h+var_528], r13
0x180015d81  mov     qword ptr [rsp+560h+var_530], r13
0x180015d86  lea     rax, [rbp+460h+var_478]
0x180015d8a  mov     [rsp+560h+var_538], rax
0x180015d8f  lea     rax, [rsp+560h+var_500]
0x180015d94  mov     [rsp+560h+var_540], rax; unsigned int
0x180015d99  xor     r9d, r9d
0x180015d9c  lea     r8d, [r9+0Dh]
0x180015da0  mov     rdx, r14
0x180015da3  mov     rcx, [rsp+560h+var_508]
0x180015da8  call    cs:__imp_WwanQueryInterface
0x180015dae  mov     ebx, eax
0x180015db0  cmp     byte ptr [rbp+460h+var_470], r13b
0x180015db4  jz      short loc_180015DCF
0x180015db6  mov     r8, [rbp+460h+var_480]
0x180015dba  mov     rcx, [r8]
0x180015dbd  mov     rdx, [rbp+460h+var_478]
0x180015dc1  mov     [r8], rdx
0x180015dc4  test    rcx, rcx
0x180015dc7  jz      short loc_180015DCF
0x180015dc9  call    cs:__imp_WwanFreeMemory
0x180015dcf  test    ebx, ebx
0x180015dd1  jz      short loc_180015E36
0x180015dd3  mov     rcx, [rbp+468h]; this
0x180015dda  mov     r9d, ebx; char *
0x180015ddd  lea     r8, aOnecoreuapNetM_4; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180015de4  mov     edx, 2BDh; void *
0x180015de9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180015dee  mov     ebx, eax
0x180015df0  mov     rcx, [rsp+560h+var_518]
0x180015df5  mov     [rsp+560h+var_518], r13
0x180015dfa  test    rcx, rcx
0x180015dfd  jz      short loc_180015E06
0x180015dff  call    cs:__imp_WwanFreeMemory
0x180015e05  nop
0x180015e06  mov     rcx, [rsp+560h+var_520]
0x180015e0b  mov     [rsp+560h+var_520], r13
0x180015e10  test    rcx, rcx
0x180015e13  jz      short loc_180015E1C
0x180015e15  call    cs:__imp_WwanFreeMemory
0x180015e1b  nop
0x180015e1c  mov     rcx, [rsp+560h+var_508]
0x180015e21  cmp     rcx, r15
0x180015e24  jz      short loc_180015E2F
0x180015e26  xor     edx, edx
0x180015e28  call    cs:__imp_WwanCloseHandle
0x180015e2e  nop
0x180015e2f  mov     eax, ebx
0x180015e31  jmp     loc_180015F4D
0x180015e36  mov     rcx, [rsp+560h+var_518]
0x180015e3b  add     rcx, 14h; psz
0x180015e3f  call    cs:__imp_SysAllocString
0x180015e45  mov     rbx, rax
0x180015e48  mov     rcx, [rsp+560h+var_518]
0x180015e4d  mov     [rsp+560h+var_518], r13
0x180015e52  test    rcx, rcx
0x180015e55  jz      short loc_180015E5D
0x180015e57  call    cs:__imp_WwanFreeMemory
0x180015e5d  mov     r14, rbx
0x180015e60  jmp     short loc_180015E77
0x180015e62  mov     rcx, [rsp+560h+var_520]
0x180015e67  add     rcx, 22h ; '"'; psz
0x180015e6b  call    cs:__imp_SysAllocString
0x180015e71  mov     rbx, rax
0x180015e74  mov     r14, rax
0x180015e77  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, sil
0x180015e7e  jz      short loc_180015E96
0x180015e80  mov     r9, rbx
0x180015e83  lea     r8, aCmbaemanagerin_1; "CMbaeManagerInternal::_GetConnectionNam"...
0x180015e8a  lea     rdx, CMbaeManagerInternal_cpp707
0x180015e91  call    McTemplateU0sz_EventWriteTransfer
0x180015e96  mov     rsi, r15
0x180015e99  inc     rsi
0x180015e9c  cmp     [r14+rsi*2], r13w
0x180015ea1  jnz     short loc_180015E99
0x180015ea3  mov     [r12], r13
0x180015ea7  lea     r15, [rsi+1]
0x180015eab  cmp     r15, rsi
0x180015eae  jb      short loc_180015EF2
0x180015eb0  mov     eax, 2
0x180015eb5  mul     r15
0x180015eb8  test    rdx, rdx
0x180015ebb  jnz     short loc_180015EF2
0x180015ebd  mov     rcx, rax; cb
0x180015ec0  call    cs:__imp_CoTaskMemAlloc
0x180015ec6  mov     [r12], rax
0x180015eca  mov     rcx, rax
0x180015ecd  neg     rcx
0x180015ed0  sbb     edi, edi
0x180015ed2  not     edi
0x180015ed4  and     edi, 8007000Eh
0x180015eda  test    rax, rax
0x180015edd  jz      short loc_180015EF7
0x180015edf  mov     r9, rsi; unsigned __int64
0x180015ee2  mov     r8, r14; unsigned __int16 *
0x180015ee5  mov     rdx, r15; unsigned __int64
0x180015ee8  mov     rcx, rax; unsigned __int16 *
0x180015eeb  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180015ef0  jmp     short loc_180015F13
0x180015ef2  mov     edi, 80070216h
0x180015ef7  mov     rcx, [rbp+468h]; this
0x180015efe  mov     r9d, edi; char *
0x180015f01  lea     r8, aOnecoreuapNetM_4; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180015f08  mov     edx, 2C4h; void *
0x180015f0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015f12  nop
0x180015f13  mov     rcx, [rsp+560h+var_520]
0x180015f18  mov     [rsp+560h+var_520], r13
0x180015f1d  test    rcx, rcx
0x180015f20  jz      short loc_180015F29
0x180015f22  call    cs:__imp_WwanFreeMemory
0x180015f28  nop
0x180015f29  mov     rcx, [rsp+560h+var_508]
0x180015f2e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180015f32  jz      short loc_180015F3D
0x180015f34  xor     edx, edx
  ... truncated ...
```
