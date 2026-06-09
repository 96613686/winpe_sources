# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180040f24`
- end: `0x1800411f9`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `725`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180040114`
- `0x180040348`

## callees

- `0x18001358c`
- `0x180040f24`
- `0x180041200`
- `0x180041358`
- `0x180041374`
- `0x1800e55cc`
- `0x1800f6f10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180041030`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180041136`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180041030`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180041136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041043`

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
  const unsigned __int16 *v14; // r9
  __int64 v15; // rcx
  WCHAR *v16; // rdx
  __int64 v17; // rax
  WCHAR *v18; // rcx
  wil::details *v19; // rax
  wil::details *v20; // rdi
  const char *v21; // r9
  int ValueFromSemaphore; // eax
  unsigned int LastError; // esi
  __int64 v25; // rdx
  WCHAR *v26; // rax
  __int64 v27; // r8
  WCHAR *v28; // rax
  const unsigned __int16 *v29; // rcx
  __int64 v30; // rbx
  WCHAR *v31; // rdx
  wil::details *v32; // rax
  const char *v33; // r9
  wil::details *v34; // rbx
  void *v35; // rdx
  int v36; // eax
  void *v37; // rdx
  void *v38; // rdx
  void *v39; // rdx
  int v40; // [rsp+20h] [rbp-E0h] BYREF
  int v41; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v42; // [rsp+28h] [rbp-D8h] BYREF
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
    v14 = L"_p0";
    v15 = 2147483646;
    v16 = &Name[v13];
    v17 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v15 )
          break;
        if ( !*v14 )
          break;
        *v16++ = *v14++;
        --v15;
        --v17;
      }
      while ( v17 );
    }
    v18 = v16 - 1;
    if ( v17 )
      v18 = v16;
    *v18 = 0;
  }
  v19 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v42 = v19;
  v20 = v19;
  if ( !v19 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v21);
    LastError = 0;
    goto LABEL_42;
  }
  v41 = 0;
  v40 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v41);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v40);
LABEL_42:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
    return LastError;
  }
  v25 = 260;
  v26 = Name;
  do
  {
    if ( !*v26 )
      break;
    ++v26;
    --v25;
  }
  while ( v25 );
  v27 = (260 - v25) & -(__int64)(v25 != 0);
  if ( v25 )
  {
    v28 = &Name[v27];
    v29 = L"h";
    v30 = 260 - v27;
    if ( 260 != v27 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v29 )
          break;
        *v28++ = *v29++;
        --v5;
        --v30;
      }
      while ( v30 );
    }
    v31 = v28 - 1;
    if ( v30 )
      v31 = v28;
    *v31 = 0;
  }
  v32 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v34 = v32;
  if ( !v32 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v33);
LABEL_35:
    wil::details::CloseHandle(v20, v35);
    return LastError;
  }
  v36 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v32, &v40);
  LastError = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v36, v40);
    wil::details::CloseHandle(v34, v39);
    goto LABEL_35;
  }
  wil::details::CloseHandle(v34, v37);
  *a3 = v41 | (unsigned __int64)((__int64)v40 << 31);
  wil::details::CloseHandle(v20, v38);
  return 0;
}

```

## disassembly

```asm
0x180040f24  mov     [rsp-8+arg_0], rbx
0x180040f29  mov     [rsp-8+arg_8], rsi
0x180040f2e  push    rbp
0x180040f2f  push    rdi
0x180040f30  push    r12
0x180040f32  push    r14
0x180040f34  push    r15
0x180040f36  lea     rbp, [rsp-150h]
0x180040f3e  sub     rsp, 250h
0x180040f45  mov     rax, cs:__security_cookie
0x180040f4c  xor     rax, rsp
0x180040f4f  mov     [rbp+170h+var_30], rax
0x180040f56  xor     r12d, r12d
0x180040f59  lea     rax, [rsp+270h+Name]
0x180040f5e  mov     r14d, 7FFFFFFEh
0x180040f64  mov     [r8], r12
0x180040f67  mov     ebx, 104h
0x180040f6c  mov     r9d, r14d
0x180040f6f  mov     edx, ebx
0x180040f71  mov     r15, r8
0x180040f74  test    r9, r9
0x180040f77  jz      short loc_180040F98
0x180040f79  movzx   r8d, word ptr [rcx]
0x180040f7d  test    r8w, r8w
0x180040f81  jz      short loc_180040F98
0x180040f83  mov     [rax], r8w
0x180040f87  add     rcx, 2
0x180040f8b  add     rax, 2
0x180040f8f  dec     r9
0x180040f92  sub     rdx, 1
0x180040f96  jnz     short loc_180040F74
0x180040f98  test    rdx, rdx
0x180040f9b  lea     rcx, [rax-2]
0x180040f9f  mov     rdx, rbx
0x180040fa2  cmovnz  rcx, rax
0x180040fa6  lea     rax, [rsp+270h+Name]
0x180040fab  mov     [rcx], r12w
0x180040faf  cmp     [rax], r12w
0x180040fb3  jz      short loc_180040FBF
0x180040fb5  add     rax, 2
0x180040fb9  sub     rdx, 1
0x180040fbd  jnz     short loc_180040FAF
0x180040fbf  mov     rcx, rbx
0x180040fc2  mov     rax, rdx
0x180040fc5  sub     rcx, rdx
0x180040fc8  neg     rax
0x180040fcb  sbb     r8, r8
0x180040fce  and     r8, rcx
0x180040fd1  test    rdx, rdx
0x180040fd4  jz      short loc_180041024
0x180040fd6  mov     rax, rbx
0x180040fd9  lea     rdx, [rsp+270h+Name]
0x180040fde  lea     r9, aP0; "_p0"
0x180040fe5  mov     rcx, r14
0x180040fe8  lea     rdx, [rdx+r8*2]
0x180040fec  sub     rax, r8
0x180040fef  jz      short loc_180041015
0x180040ff1  test    rcx, rcx
0x180040ff4  jz      short loc_180041015
0x180040ff6  movzx   r8d, word ptr [r9]
0x180040ffa  test    r8w, r8w
0x180040ffe  jz      short loc_180041015
0x180041000  mov     [rdx], r8w
0x180041004  add     r9, 2
0x180041008  add     rdx, 2
0x18004100c  dec     rcx
0x18004100f  sub     rax, 1
0x180041013  jnz     short loc_180040FF1
0x180041015  test    rax, rax
0x180041018  lea     rcx, [rdx-2]
0x18004101c  cmovnz  rcx, rdx
0x180041020  mov     [rcx], r12w
0x180041024  lea     r8, [rsp+270h+Name]; lpName
0x180041029  xor     edx, edx; bInheritHandle
0x18004102b  mov     ecx, 1F0003h; dwDesiredAccess
0x180041030  call    cs:__imp_OpenSemaphoreW
0x180041036  mov     [rsp+270h+var_248], rax
0x18004103b  mov     rdi, rax
0x18004103e  test    rax, rax
0x180041041  jnz     short loc_180041095
0x180041043  call    cs:__imp_GetLastError
0x180041049  cmp     eax, 2
0x18004104c  jz      loc_1800411F1
0x180041052  mov     rcx, [rbp+178h]; this
0x180041059  lea     r8, aWil; "wil"
0x180041060  mov     edx, 0D0h; void *
0x180041065  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004106a  mov     rcx, [rbp+170h+var_30]
0x180041071  xor     rcx, rsp; StackCookie
0x180041074  call    __security_check_cookie
0x180041079  lea     r11, [rsp+270h+var_20]
0x180041081  mov     rbx, [r11+30h]
0x180041085  mov     rsi, [r11+38h]
0x180041089  mov     rsp, r11
0x18004108c  pop     r15
0x18004108e  pop     r14
0x180041090  pop     r12
0x180041092  pop     rdi
0x180041093  pop     rbp
0x180041094  retn
0x180041095  lea     rdx, [rsp+270h+var_24C]; int *
0x18004109a  mov     [rsp+270h+var_24C], r12d
0x18004109f  mov     rcx, rdi; hHandle
0x1800410a2  mov     [rsp+270h+var_250], r12d; int
0x1800410a7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800410ac  mov     esi, eax
0x1800410ae  test    eax, eax
0x1800410b0  js      loc_1800411D0
0x1800410b6  mov     rdx, rbx
0x1800410b9  lea     rax, [rsp+270h+Name]
0x1800410be  cmp     [rax], r12w
0x1800410c2  jz      short loc_1800410CE
0x1800410c4  add     rax, 2
0x1800410c8  sub     rdx, 1
0x1800410cc  jnz     short loc_1800410BE
0x1800410ce  mov     rcx, rbx
0x1800410d1  mov     rax, rdx
0x1800410d4  sub     rcx, rdx
0x1800410d7  neg     rax
0x1800410da  sbb     r8, r8
0x1800410dd  and     r8, rcx
0x1800410e0  test    rdx, rdx
0x1800410e3  jz      short loc_18004112A
0x1800410e5  lea     rax, [rsp+270h+Name]
0x1800410ea  lea     rax, [rax+r8*2]
0x1800410ee  lea     rcx, asc_1801B1E94; "h"
0x1800410f5  sub     rbx, r8
0x1800410f8  jz      short loc_18004111B
0x1800410fa  test    r14, r14
0x1800410fd  jz      short loc_18004111B
0x1800410ff  movzx   edx, word ptr [rcx]
0x180041102  test    dx, dx
0x180041105  jz      short loc_18004111B
0x180041107  mov     [rax], dx
0x18004110a  add     rcx, 2
0x18004110e  add     rax, 2
0x180041112  dec     r14
0x180041115  sub     rbx, 1
0x180041119  jnz     short loc_1800410FA
0x18004111b  test    rbx, rbx
0x18004111e  lea     rdx, [rax-2]
0x180041122  cmovnz  rdx, rax
0x180041126  mov     [rdx], r12w
0x18004112a  lea     r8, [rsp+270h+Name]; lpName
0x18004112f  xor     edx, edx; bInheritHandle
0x180041131  mov     ecx, 1F0003h; dwDesiredAccess
0x180041136  call    cs:__imp_OpenSemaphoreW
0x18004113c  mov     rbx, rax
0x18004113f  test    rax, rax
0x180041142  jnz     short loc_18004116D
0x180041144  mov     rcx, [rbp+178h]; this
0x18004114b  lea     r8, aWil; "wil"
0x180041152  mov     edx, 0DCh; void *
0x180041157  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004115c  mov     esi, eax
0x18004115e  mov     rcx, rdi; this
0x180041161  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180041166  mov     eax, esi
0x180041168  jmp     loc_18004106A
0x18004116d  lea     rdx, [rsp+270h+var_250]; int *
0x180041172  mov     rcx, rbx; hHandle
0x180041175  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18004117a  mov     esi, eax
0x18004117c  test    eax, eax
0x18004117e  js      short loc_1800411AB
0x180041180  mov     rcx, rbx; this
0x180041183  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180041188  movsxd  rax, [rsp+270h+var_24C]
0x18004118d  movsxd  rcx, [rsp+270h+var_250]
0x180041192  shl     rcx, 1Fh
0x180041196  or      rcx, rax
0x180041199  mov     [r15], rcx
0x18004119c  mov     rcx, rdi; this
0x18004119f  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800411a4  xor     eax, eax
0x1800411a6  jmp     loc_18004106A
0x1800411ab  mov     rcx, [rbp+178h]; this
0x1800411b2  lea     r8, aWil; "wil"
0x1800411b9  mov     r9d, eax; char *
0x1800411bc  mov     edx, 0DEh; void *
0x1800411c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800411c6  mov     rcx, rbx; this
0x1800411c9  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800411ce  jmp     short loc_18004115E
0x1800411d0  mov     rcx, [rbp+178h]; this
0x1800411d7  lea     r8, aWil; "wil"
0x1800411de  mov     r9d, eax; char *
0x1800411e1  mov     edx, 0D6h; void *
0x1800411e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800411eb  nop
0x1800411ec  jmp     loc_18017DAEA
0x1800411f1  mov     esi, r12d
0x1800411f4  jmp     loc_18017DAEA
0x18017daea  lea     rcx, [rsp+270h+var_248]
0x18017daef  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18017daf4  nop
0x18017daf5  jmp     loc_180041166
```
