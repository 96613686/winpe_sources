# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180050f4c`
- end: `0x18005124b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `767`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180050ce4`
- `0x1800513f0`

## callees

- `0x180025dd4`
- `0x180050f30`
- `0x180050f4c`
- `0x180051254`
- `0x1800513c4`
- `0x18006944c`
- `0x18006ed20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005100e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180051085`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005100e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180051085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051206`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r14
  __int64 v6; // r9
  __int64 v7; // rdx
  bool v9; // zf
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  wil::details *v14; // rax
  wil::details *v15; // rdi
  int ValueFromSemaphore; // eax
  unsigned int LastError; // esi
  __int64 v18; // rdx
  WCHAR *v19; // rax
  __int64 v20; // r8
  wil::details *v21; // rax
  const char *v22; // r9
  wil::details *v23; // rbx
  int v24; // eax
  void *v25; // rdx
  void *v26; // rdx
  void *v28; // rdx
  const unsigned __int16 *v29; // r9
  __int64 v30; // rcx
  WCHAR *v31; // rdx
  __int64 v32; // rax
  WCHAR *v33; // rcx
  WCHAR *v34; // rax
  const unsigned __int16 *v35; // rcx
  __int64 v36; // rbx
  WCHAR *v37; // rdx
  void *v38; // rdx
  const char *v39; // r9
  unsigned int v40; // ebx
  int v41; // [rsp+20h] [rbp-E0h] BYREF
  int v42[2]; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

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
  v9 = v7 == 0;
  v10 = v4 - 1;
  v11 = 260;
  if ( !v9 )
    v10 = v4;
  v12 = Name;
  *v10 = 0;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = (260 - v11) & -(__int64)(v11 != 0);
  if ( v11 )
  {
    v29 = L"_p0";
    v30 = 2147483646;
    v31 = &Name[v13];
    v32 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v30 )
          break;
        if ( !*v29 )
          break;
        *v31++ = *v29++;
        --v30;
        --v32;
      }
      while ( v32 );
    }
    v33 = v31 - 1;
    if ( v32 )
      v33 = v31;
    *v33 = 0;
  }
  v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  *(_QWORD *)v42 = v14;
  v15 = v14;
  if ( v14 )
  {
    v42[0] = 0;
    v41 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, v42);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v41);
    }
    else
    {
      v18 = 260;
      v19 = Name;
      do
      {
        if ( !*v19 )
          break;
        ++v19;
        --v18;
      }
      while ( v18 );
      v20 = (260 - v18) & -(__int64)(v18 != 0);
      if ( v18 )
      {
        v34 = &Name[v20];
        v35 = L"h";
        v36 = 260 - v20;
        if ( 260 != v20 )
        {
          do
          {
            if ( !v5 )
              break;
            if ( !*v35 )
              break;
            *v34++ = *v35++;
            --v5;
            --v36;
          }
          while ( v36 );
        }
        v37 = v34 - 1;
        if ( v36 )
          v37 = v34;
        *v37 = 0;
      }
      v21 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
      v23 = v21;
      if ( v21 )
      {
        v24 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, &v41);
        LastError = v24;
        if ( v24 >= 0 )
        {
          wil::details::CloseHandle(v23, v25);
          *a3 = v42[0] | (unsigned __int64)((__int64)v41 << 31);
          wil::details::CloseHandle(v15, v26);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v24,
          v41);
        wil::details::CloseHandle(v23, v38);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v22);
      }
    }
    wil::details::CloseHandle(v15, v28);
    return LastError;
  }
  else
  {
    if ( GetLastError() == 2 )
    {
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v42);
      return 0;
    }
    v40 = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v39);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v42);
    return v40;
  }
}

```

## disassembly

```asm
0x180050f4c  mov     [rsp-8+arg_0], rbx
0x180050f51  mov     [rsp-8+arg_8], rsi
0x180050f56  push    rbp
0x180050f57  push    rdi
0x180050f58  push    r12
0x180050f5a  push    r14
0x180050f5c  push    r15
0x180050f5e  lea     rbp, [rsp-150h]
0x180050f66  sub     rsp, 250h
0x180050f6d  mov     rax, cs:__security_cookie
0x180050f74  xor     rax, rsp
0x180050f77  mov     [rbp+170h+var_30], rax
0x180050f7e  xor     r12d, r12d
0x180050f81  lea     rax, [rsp+270h+Name]
0x180050f86  mov     r14d, 7FFFFFFEh
0x180050f8c  mov     [r8], r12
0x180050f8f  mov     ebx, 104h
0x180050f94  mov     r9d, r14d
0x180050f97  mov     edx, ebx
0x180050f99  mov     r15, r8
0x180050f9c  test    r9, r9
0x180050f9f  jz      short loc_180050FC0
0x180050fa1  movzx   r8d, word ptr [rcx]
0x180050fa5  test    r8w, r8w
0x180050fa9  jz      short loc_180050FC0
0x180050fab  mov     [rax], r8w
0x180050faf  add     rcx, 2
0x180050fb3  add     rax, 2
0x180050fb7  dec     r9
0x180050fba  sub     rdx, 1
0x180050fbe  jnz     short loc_180050F9C
0x180050fc0  test    rdx, rdx
0x180050fc3  lea     rcx, [rax-2]
0x180050fc7  mov     rdx, rbx
0x180050fca  cmovnz  rcx, rax
0x180050fce  lea     rax, [rsp+270h+Name]
0x180050fd3  mov     [rcx], r12w
0x180050fd7  cmp     [rax], r12w
0x180050fdb  jz      short loc_180050FE7
0x180050fdd  add     rax, 2
0x180050fe1  sub     rdx, 1
0x180050fe5  jnz     short loc_180050FD7
0x180050fe7  mov     rcx, rbx
0x180050fea  mov     rax, rdx
0x180050fed  sub     rcx, rdx
0x180050ff0  neg     rax
0x180050ff3  sbb     r8, r8
0x180050ff6  and     r8, rcx
0x180050ff9  test    rdx, rdx
0x180050ffc  jnz     loc_180051121
0x180051002  lea     r8, [rsp+270h+Name]; lpName
0x180051007  xor     edx, edx; bInheritHandle
0x180051009  mov     ecx, 1F0003h; dwDesiredAccess
0x18005100e  call    cs:__imp_OpenSemaphoreW
0x180051014  mov     qword ptr [rsp+270h+var_248], rax
0x180051019  mov     rdi, rax
0x18005101c  test    rax, rax
0x18005101f  jz      loc_180051206
0x180051025  lea     rdx, [rsp+270h+var_248]; int *
0x18005102a  mov     [rsp+270h+var_248], r12d
0x18005102f  mov     rcx, rax; hHandle
0x180051032  mov     [rsp+270h+var_250], r12d; int
0x180051037  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18005103c  mov     esi, eax
0x18005103e  test    eax, eax
0x180051040  js      loc_1800511E6
0x180051046  mov     rdx, rbx
0x180051049  lea     rax, [rsp+270h+Name]
0x18005104e  cmp     [rax], r12w
0x180051052  jz      short loc_18005105E
0x180051054  add     rax, 2
0x180051058  sub     rdx, 1
0x18005105c  jnz     short loc_18005104E
0x18005105e  mov     rcx, rbx
0x180051061  mov     rax, rdx
0x180051064  sub     rcx, rdx
0x180051067  neg     rax
0x18005106a  sbb     r8, r8
0x18005106d  and     r8, rcx
0x180051070  test    rdx, rdx
0x180051073  jnz     loc_180051174
0x180051079  lea     r8, [rsp+270h+Name]; lpName
0x18005107e  xor     edx, edx; bInheritHandle
0x180051080  mov     ecx, 1F0003h; dwDesiredAccess
0x180051085  call    cs:__imp_OpenSemaphoreW
0x18005108b  mov     rbx, rax
0x18005108e  test    rax, rax
0x180051091  jz      short loc_1800510D2
0x180051093  lea     rdx, [rsp+270h+var_250]; int *
0x180051098  mov     rcx, rax; hHandle
0x18005109b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800510a0  mov     esi, eax
0x1800510a2  test    eax, eax
0x1800510a4  js      loc_1800511BE
0x1800510aa  mov     rcx, rbx; this
0x1800510ad  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800510b2  movsxd  rax, [rsp+270h+var_248]
0x1800510b7  movsxd  rcx, [rsp+270h+var_250]
0x1800510bc  shl     rcx, 1Fh
0x1800510c0  or      rcx, rax
0x1800510c3  mov     [r15], rcx
0x1800510c6  mov     rcx, rdi; this
0x1800510c9  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800510ce  xor     eax, eax
0x1800510d0  jmp     short loc_1800510F6
0x1800510d2  mov     rcx, [rbp+178h]; this
0x1800510d9  lea     r8, aWil; "wil"
0x1800510e0  mov     edx, 0DCh; void *
0x1800510e5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800510ea  mov     esi, eax
0x1800510ec  mov     rcx, rdi; this
0x1800510ef  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800510f4  mov     eax, esi
0x1800510f6  mov     rcx, [rbp+170h+var_30]
0x1800510fd  xor     rcx, rsp; StackCookie
0x180051100  call    __security_check_cookie
0x180051105  lea     r11, [rsp+270h+var_20]
0x18005110d  mov     rbx, [r11+30h]
0x180051111  mov     rsi, [r11+38h]
0x180051115  mov     rsp, r11
0x180051118  pop     r15
0x18005111a  pop     r14
0x18005111c  pop     r12
0x18005111e  pop     rdi
0x18005111f  pop     rbp
0x180051120  retn
0x180051121  mov     rax, rbx
0x180051124  lea     rdx, [rsp+270h+Name]
0x180051129  lea     r9, aP0; "_p0"
0x180051130  mov     rcx, r14
0x180051133  lea     rdx, [rdx+r8*2]
0x180051137  sub     rax, r8
0x18005113a  jz      short loc_180051160
0x18005113c  test    rcx, rcx
0x18005113f  jz      short loc_180051160
0x180051141  movzx   r8d, word ptr [r9]
0x180051145  test    r8w, r8w
0x180051149  jz      short loc_180051160
0x18005114b  mov     [rdx], r8w
0x18005114f  add     r9, 2
0x180051153  add     rdx, 2
0x180051157  dec     rcx
0x18005115a  sub     rax, 1
0x18005115e  jnz     short loc_18005113C
0x180051160  test    rax, rax
0x180051163  lea     rcx, [rdx-2]
0x180051167  cmovnz  rcx, rdx
0x18005116b  mov     [rcx], r12w
0x18005116f  jmp     loc_180051002
0x180051174  lea     rax, [rsp+270h+Name]
0x180051179  lea     rax, [rax+r8*2]
0x18005117d  lea     rcx, asc_1800D14B8; "h"
0x180051184  sub     rbx, r8
0x180051187  jz      short loc_1800511AA
0x180051189  test    r14, r14
0x18005118c  jz      short loc_1800511AA
0x18005118e  movzx   edx, word ptr [rcx]
0x180051191  test    dx, dx
0x180051194  jz      short loc_1800511AA
0x180051196  mov     [rax], dx
0x180051199  add     rcx, 2
0x18005119d  add     rax, 2
0x1800511a1  dec     r14
0x1800511a4  sub     rbx, 1
0x1800511a8  jnz     short loc_180051189
0x1800511aa  test    rbx, rbx
0x1800511ad  lea     rdx, [rax-2]
0x1800511b1  cmovnz  rdx, rax
0x1800511b5  mov     [rdx], r12w
0x1800511b9  jmp     loc_180051079
0x1800511be  mov     rcx, [rbp+178h]; this
0x1800511c5  lea     r8, aWil; "wil"
0x1800511cc  mov     r9d, eax; char *
0x1800511cf  mov     edx, 0DEh; void *
0x1800511d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800511d9  mov     rcx, rbx; this
0x1800511dc  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800511e1  jmp     loc_1800510EC
0x1800511e6  mov     rcx, [rbp+178h]; this
0x1800511ed  lea     r8, aWil; "wil"
0x1800511f4  mov     r9d, eax; char *
0x1800511f7  mov     edx, 0D6h; void *
0x1800511fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051201  jmp     loc_1800510EC
0x180051206  call    cs:__imp_GetLastError
0x18005120c  cmp     eax, 2
0x18005120f  jnz     short loc_180051220
0x180051211  lea     rcx, [rsp+270h+var_248]
0x180051216  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005121b  jmp     loc_1800510CE
0x180051220  mov     rcx, [rbp+178h]; this
0x180051227  lea     r8, aWil; "wil"
0x18005122e  mov     edx, 0D0h; void *
0x180051233  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180051238  lea     rcx, [rsp+270h+var_248]
0x18005123d  mov     ebx, eax
0x18005123f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180051244  mov     eax, ebx
0x180051246  jmp     loc_1800510F6
```
