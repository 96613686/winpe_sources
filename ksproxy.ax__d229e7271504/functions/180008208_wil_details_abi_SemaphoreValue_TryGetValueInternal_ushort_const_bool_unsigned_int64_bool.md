# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008208`
- end: `0x18000845d`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `597`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180008464`

## callees

- `0x180007c70`
- `0x1800081e4`
- `0x180008208`
- `0x18001b6d4`
- `0x18001b934`
- `0x18001ba6c`
- `0x18001f620`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008408`
- `KERNEL32!GetLastError` at `0x180008408`
- `KERNEL32!OpenSemaphoreW` at `0x1800082fe`
- `KERNEL32!OpenSemaphoreW` at `0x180008370`
- `KERNEL32!OpenSemaphoreW` at `0x1800082fe`
- `KERNEL32!OpenSemaphoreW` at `0x180008370`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r11
  __int64 v6; // r10
  __int64 v7; // r9
  WCHAR *v9; // rcx
  __int64 v10; // r8
  WCHAR *v11; // rax
  __int64 v12; // r9
  WCHAR *v13; // rax
  const unsigned __int16 *v14; // rcx
  __int64 v15; // rdx
  WCHAR *v16; // rcx
  HANDLE v17; // rax
  int ValueFromSemaphore; // eax
  unsigned __int64 v19; // rdx
  unsigned int LastError; // ebx
  HANDLE v21; // rax
  const char *v22; // r9
  int v23; // eax
  const char *v25; // r9
  int v26; // [rsp+20h] [rbp-E0h] BYREF
  int v27; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v28; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v29[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v6;
    --v7;
  }
  while ( v7 );
  v9 = v4 - 1;
  v10 = 260;
  if ( v7 )
    v9 = v4;
  v11 = Name;
  *v9 = 0;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  v12 = (260 - v10) & -(__int64)(v10 != 0);
  if ( v10 )
  {
    v13 = &Name[v12];
    v14 = L"_p0";
    v15 = 260 - v12;
    if ( 260 != v12 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v14 )
          break;
        *v13++ = *v14++;
        --v5;
        --v15;
      }
      while ( v15 );
    }
    v16 = v13 - 1;
    if ( v15 )
      v16 = v13;
    *v16 = 0;
  }
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v29[0] = v17;
  if ( v17 )
  {
    v27 = 0;
    v26 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v27);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, v19, L"h");
      v21 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v28 = v21;
      if ( v21 )
      {
        v23 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, &v26);
        LastError = v23;
        if ( v23 >= 0 )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v28);
          *a3 = v27 | (unsigned __int64)((__int64)v26 << 31);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v29);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v23);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v22);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v28);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
    }
    goto LABEL_29;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
LABEL_29:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v29);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v25);
}

```

## disassembly

```asm
0x180008208  push    rbp
0x18000820a  push    rbx
0x18000820b  push    rsi
0x18000820c  push    rdi
0x18000820d  lea     rbp, [rsp-168h]
0x180008215  sub     rsp, 268h
0x18000821c  mov     rax, cs:__security_cookie
0x180008223  xor     rax, rsp
0x180008226  mov     [rbp+180h+var_30], rax
0x18000822d  xor     esi, esi
0x18000822f  lea     rax, [rsp+280h+Name]
0x180008234  mov     r11d, 7FFFFFFEh
0x18000823a  mov     [r8], rsi
0x18000823d  mov     edx, 104h
0x180008242  mov     r10d, r11d
0x180008245  mov     r9d, edx
0x180008248  mov     rdi, r8
0x18000824b  test    r10, r10
0x18000824e  jz      short loc_18000826F
0x180008250  movzx   r8d, word ptr [rcx]
0x180008254  test    r8w, r8w
0x180008258  jz      short loc_18000826F
0x18000825a  mov     [rax], r8w
0x18000825e  add     rcx, 2
0x180008262  add     rax, 2
0x180008266  dec     r10
0x180008269  sub     r9, 1
0x18000826d  jnz     short loc_18000824B
0x18000826f  lea     rcx, [rax-2]
0x180008273  test    r9, r9
0x180008276  mov     r8, rdx
0x180008279  cmovnz  rcx, rax
0x18000827d  lea     rax, [rsp+280h+Name]
0x180008282  mov     [rcx], si
0x180008285  cmp     [rax], si
0x180008288  jz      short loc_180008294
0x18000828a  add     rax, 2
0x18000828e  sub     r8, 1
0x180008292  jnz     short loc_180008285
0x180008294  mov     rcx, rdx
0x180008297  mov     rax, r8
0x18000829a  sub     rcx, r8
0x18000829d  neg     rax
0x1800082a0  sbb     r9, r9
0x1800082a3  and     r9, rcx
0x1800082a6  test    r8, r8
0x1800082a9  jz      short loc_1800082F2
0x1800082ab  lea     rax, [rsp+280h+Name]
0x1800082b0  lea     rax, [rax+r9*2]
0x1800082b4  lea     rcx, aP0; "_p0"
0x1800082bb  sub     rdx, r9
0x1800082be  jz      short loc_1800082E4
0x1800082c0  test    r11, r11
0x1800082c3  jz      short loc_1800082E4
0x1800082c5  movzx   r8d, word ptr [rcx]
0x1800082c9  test    r8w, r8w
0x1800082cd  jz      short loc_1800082E4
0x1800082cf  mov     [rax], r8w
0x1800082d3  add     rcx, 2
0x1800082d7  add     rax, 2
0x1800082db  dec     r11
0x1800082de  sub     rdx, 1
0x1800082e2  jnz     short loc_1800082C0
0x1800082e4  test    rdx, rdx
0x1800082e7  lea     rcx, [rax-2]
0x1800082eb  cmovnz  rcx, rax
0x1800082ef  mov     [rcx], si
0x1800082f2  lea     r8, [rsp+280h+Name]; lpName
0x1800082f7  xor     edx, edx; bInheritHandle
0x1800082f9  mov     ecx, 1F0003h; dwDesiredAccess
0x1800082fe  call    cs:__imp_OpenSemaphoreW
0x180008305  nop     dword ptr [rax+rax+00h]
0x18000830a  mov     [rsp+280h+var_250], rax
0x18000830f  test    rax, rax
0x180008312  jz      loc_180008408
0x180008318  lea     rdx, [rsp+280h+var_25C]; int *
0x18000831d  mov     [rsp+280h+var_25C], esi
0x180008321  mov     rcx, rax; hHandle
0x180008324  mov     [rsp+280h+var_260], esi; int
0x180008328  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000832d  mov     ebx, eax
0x18000832f  test    eax, eax
0x180008331  jns     short loc_180008353
0x180008333  mov     rcx, [rbp+188h]; this
0x18000833a  lea     r8, aWil; "wil"
0x180008341  mov     r9d, eax; char *
0x180008344  mov     edx, 0D6h; void *
0x180008349  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000834e  jmp     loc_18000841B
0x180008353  lea     r8, asc_180049BC0; "h"
0x18000835a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000835f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008364  lea     r8, [rsp+280h+Name]; lpName
0x180008369  xor     edx, edx; bInheritHandle
0x18000836b  mov     ecx, 1F0003h; dwDesiredAccess
0x180008370  call    cs:__imp_OpenSemaphoreW
0x180008377  nop     dword ptr [rax+rax+00h]
0x18000837c  mov     [rsp+280h+var_258], rax
0x180008381  test    rax, rax
0x180008384  jz      short loc_1800083E2
0x180008386  lea     rdx, [rsp+280h+var_260]; int *
0x18000838b  mov     rcx, rax; hHandle
0x18000838e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008393  mov     ebx, eax
0x180008395  test    eax, eax
0x180008397  jns     short loc_1800083B6
0x180008399  mov     rcx, [rbp+188h]; this
0x1800083a0  lea     r8, aWil; "wil"
0x1800083a7  mov     r9d, eax; char *
0x1800083aa  mov     edx, 0DEh; void *
0x1800083af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800083b4  jmp     short loc_1800083FC
0x1800083b6  lea     rcx, [rsp+280h+var_258]
0x1800083bb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800083c0  movsxd  rax, [rsp+280h+var_25C]
0x1800083c5  movsxd  rcx, [rsp+280h+var_260]
0x1800083ca  shl     rcx, 1Fh
0x1800083ce  or      rcx, rax
0x1800083d1  mov     [rdi], rcx
0x1800083d4  lea     rcx, [rsp+280h+var_250]
0x1800083d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800083de  xor     eax, eax
0x1800083e0  jmp     short loc_180008441
0x1800083e2  mov     rcx, [rbp+188h]; this
0x1800083e9  lea     r8, aWil; "wil"
0x1800083f0  mov     edx, 0DCh; void *
0x1800083f5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800083fa  mov     ebx, eax
0x1800083fc  lea     rcx, [rsp+280h+var_258]
0x180008401  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008406  jmp     short loc_18000841B
0x180008408  call    cs:__imp_GetLastError
0x18000840f  nop     dword ptr [rax+rax+00h]
0x180008414  cmp     eax, 2
0x180008417  jnz     short loc_180008429
0x180008419  mov     ebx, esi
0x18000841b  lea     rcx, [rsp+280h+var_250]
0x180008420  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008425  mov     eax, ebx
0x180008427  jmp     short loc_180008441
0x180008429  mov     rcx, [rbp+188h]; this
0x180008430  lea     r8, aWil; "wil"
0x180008437  mov     edx, 0D0h; void *
0x18000843c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008441  mov     rcx, [rbp+180h+var_30]
0x180008448  xor     rcx, rsp; StackCookie
0x18000844b  call    __security_check_cookie
0x180008450  add     rsp, 268h
0x180008457  pop     rdi
0x180008458  pop     rsi
0x180008459  pop     rbx
0x18000845a  pop     rbp
0x18000845b  retn
```
