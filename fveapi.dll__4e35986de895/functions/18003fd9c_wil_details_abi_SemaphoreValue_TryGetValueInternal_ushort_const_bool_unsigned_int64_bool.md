# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003fd9c`
- end: `0x180040095`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `761`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003fb18`
- `0x18003fd18`

## callees

- `0x18003fd9c`
- `0x18004009c`
- `0x180040240`
- `0x18004c678`
- `0x18004d984`
- `0x18004fc7c`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003fea8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003ff4e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003fea8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003ff4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ff85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ff85`

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
  int ValueFromSemaphore; // eax
  unsigned int LastError; // esi
  __int64 v23; // rdx
  WCHAR *v24; // rax
  __int64 v25; // r8
  WCHAR *v26; // rax
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rbx
  WCHAR *v29; // rdx
  wil::details *v30; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  wil::details *v33; // rbx
  void *v34; // rdx
  unsigned int v36; // r8d
  const char *v37; // r9
  int v38; // eax
  void *v39; // rdx
  void *v40; // rdx
  void *v41; // rdx
  int v42; // [rsp+20h] [rbp-E0h] BYREF
  int v43; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v44; // [rsp+28h] [rbp-D8h] BYREF
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
  v44 = v19;
  v20 = v19;
  if ( !v19 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v36, v37);
    LastError = 0;
LABEL_43:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v44);
    return LastError;
  }
  v43 = 0;
  v42 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v43);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v42);
    goto LABEL_43;
  }
  v23 = 260;
  v24 = Name;
  do
  {
    if ( !*v24 )
      break;
    ++v24;
    --v23;
  }
  while ( v23 );
  v25 = (260 - v23) & -(__int64)(v23 != 0);
  if ( v23 )
  {
    v26 = &Name[v25];
    v27 = L"h";
    v28 = 260 - v25;
    if ( 260 != v25 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v27 )
          break;
        *v26++ = *v27++;
        --v5;
        --v28;
      }
      while ( v28 );
    }
    v29 = v26 - 1;
    if ( v28 )
      v29 = v26;
    *v29 = 0;
  }
  v30 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v33 = v30;
  if ( !v30 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v31, v32);
LABEL_31:
    wil::details::CloseHandle(v20, v34);
    return LastError;
  }
  v38 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v30, &v42);
  LastError = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v38, v42);
    wil::details::CloseHandle(v33, v41);
    goto LABEL_31;
  }
  wil::details::CloseHandle(v33, v39);
  *a3 = v43 | (unsigned __int64)((__int64)v42 << 31);
  wil::details::CloseHandle(v20, v40);
  return 0;
}

```

## disassembly

```asm
0x18003fd9c  mov     [rsp-8+arg_0], rbx
0x18003fda1  mov     [rsp-8+arg_8], rsi
0x18003fda6  push    rbp
0x18003fda7  push    rdi
0x18003fda8  push    r12
0x18003fdaa  push    r14
0x18003fdac  push    r15
0x18003fdae  lea     rbp, [rsp-150h]
0x18003fdb6  sub     rsp, 250h
0x18003fdbd  mov     rax, cs:__security_cookie
0x18003fdc4  xor     rax, rsp
0x18003fdc7  mov     [rbp+170h+var_30], rax
0x18003fdce  xor     r12d, r12d
0x18003fdd1  lea     rax, [rsp+270h+Name]
0x18003fdd6  mov     r14d, 7FFFFFFEh
0x18003fddc  mov     [r8], r12
0x18003fddf  mov     ebx, 104h
0x18003fde4  mov     r9d, r14d
0x18003fde7  mov     edx, ebx
0x18003fde9  mov     r15, r8
0x18003fdec  test    r9, r9
0x18003fdef  jz      short loc_18003FE10
0x18003fdf1  movzx   r8d, word ptr [rcx]
0x18003fdf5  test    r8w, r8w
0x18003fdf9  jz      short loc_18003FE10
0x18003fdfb  mov     [rax], r8w
0x18003fdff  add     rcx, 2
0x18003fe03  add     rax, 2
0x18003fe07  dec     r9
0x18003fe0a  sub     rdx, 1
0x18003fe0e  jnz     short loc_18003FDEC
0x18003fe10  test    rdx, rdx
0x18003fe13  lea     rcx, [rax-2]
0x18003fe17  mov     rdx, rbx
0x18003fe1a  cmovnz  rcx, rax
0x18003fe1e  lea     rax, [rsp+270h+Name]
0x18003fe23  mov     [rcx], r12w
0x18003fe27  cmp     [rax], r12w
0x18003fe2b  jz      short loc_18003FE37
0x18003fe2d  add     rax, 2
0x18003fe31  sub     rdx, 1
0x18003fe35  jnz     short loc_18003FE27
0x18003fe37  mov     rcx, rbx
0x18003fe3a  mov     rax, rdx
0x18003fe3d  sub     rcx, rdx
0x18003fe40  neg     rax
0x18003fe43  sbb     r8, r8
0x18003fe46  and     r8, rcx
0x18003fe49  test    rdx, rdx
0x18003fe4c  jz      short loc_18003FE9C
0x18003fe4e  mov     rax, rbx
0x18003fe51  lea     rdx, [rsp+270h+Name]
0x18003fe56  lea     r9, aP0; "_p0"
0x18003fe5d  mov     rcx, r14
0x18003fe60  lea     rdx, [rdx+r8*2]
0x18003fe64  sub     rax, r8
0x18003fe67  jz      short loc_18003FE8D
0x18003fe69  test    rcx, rcx
0x18003fe6c  jz      short loc_18003FE8D
0x18003fe6e  movzx   r8d, word ptr [r9]
0x18003fe72  test    r8w, r8w
0x18003fe76  jz      short loc_18003FE8D
0x18003fe78  mov     [rdx], r8w
0x18003fe7c  add     r9, 2
0x18003fe80  add     rdx, 2
0x18003fe84  dec     rcx
0x18003fe87  sub     rax, 1
0x18003fe8b  jnz     short loc_18003FE69
0x18003fe8d  test    rax, rax
0x18003fe90  lea     rcx, [rdx-2]
0x18003fe94  cmovnz  rcx, rdx
0x18003fe98  mov     [rcx], r12w
0x18003fe9c  lea     r8, [rsp+270h+Name]; lpName
0x18003fea1  xor     edx, edx; bInheritHandle
0x18003fea3  mov     ecx, 1F0003h; dwDesiredAccess
0x18003fea8  call    cs:__imp_OpenSemaphoreW
0x18003feaf  nop     dword ptr [rax+rax+00h]
0x18003feb4  mov     [rsp+270h+var_248], rax
0x18003feb9  mov     rdi, rax
0x18003febc  test    rax, rax
0x18003febf  jz      loc_18003FF85
0x18003fec5  lea     rdx, [rsp+270h+var_24C]; int *
0x18003feca  mov     [rsp+270h+var_24C], r12d
0x18003fecf  mov     rcx, rax; hHandle
0x18003fed2  mov     [rsp+270h+var_250], r12d; int
0x18003fed7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003fedc  mov     esi, eax
0x18003fede  test    eax, eax
0x18003fee0  js      loc_180040066
0x18003fee6  mov     rdx, rbx
0x18003fee9  lea     rax, [rsp+270h+Name]
0x18003feee  cmp     [rax], r12w
0x18003fef2  jz      short loc_18003FEFE
0x18003fef4  add     rax, 2
0x18003fef8  sub     rdx, 1
0x18003fefc  jnz     short loc_18003FEEE
0x18003fefe  mov     rcx, rbx
0x18003ff01  mov     rax, rdx
0x18003ff04  sub     rcx, rdx
0x18003ff07  neg     rax
0x18003ff0a  sbb     r8, r8
0x18003ff0d  and     r8, rcx
0x18003ff10  test    rdx, rdx
0x18003ff13  jz      short loc_18003FF42
0x18003ff15  lea     rax, [rsp+270h+Name]
0x18003ff1a  lea     rax, [rax+r8*2]
0x18003ff1e  lea     rcx, asc_180136828; "h"
0x18003ff25  sub     rbx, r8
0x18003ff28  jz      short loc_18003FF33
0x18003ff2a  test    r14, r14
0x18003ff2d  jnz     loc_18003FFD7
0x18003ff33  test    rbx, rbx
0x18003ff36  lea     rdx, [rax-2]
0x18003ff3a  cmovnz  rdx, rax
0x18003ff3e  mov     [rdx], r12w
0x18003ff42  lea     r8, [rsp+270h+Name]; lpName
0x18003ff47  xor     edx, edx; bInheritHandle
0x18003ff49  mov     ecx, 1F0003h; dwDesiredAccess
0x18003ff4e  call    cs:__imp_OpenSemaphoreW
0x18003ff55  nop     dword ptr [rax+rax+00h]
0x18003ff5a  mov     rbx, rax
0x18003ff5d  test    rax, rax
0x18003ff60  jnz     loc_180040000
0x18003ff66  mov     rcx, [rbp+178h]; this
0x18003ff6d  mov     edx, 0DCh; void *
0x18003ff72  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003ff77  mov     esi, eax
0x18003ff79  mov     rcx, rdi; this
0x18003ff7c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18003ff81  mov     eax, esi
0x18003ff83  jmp     short loc_18003FFAB
0x18003ff85  call    cs:__imp_GetLastError
0x18003ff8c  nop     dword ptr [rax+rax+00h]
0x18003ff91  cmp     eax, 2
0x18003ff94  jz      loc_180040083
0x18003ff9a  mov     rcx, [rbp+178h]; this
0x18003ffa1  mov     edx, 0D0h; void *
0x18003ffa6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003ffab  mov     rcx, [rbp+170h+var_30]
0x18003ffb2  xor     rcx, rsp; StackCookie
0x18003ffb5  call    __security_check_cookie
0x18003ffba  lea     r11, [rsp+270h+var_20]
0x18003ffc2  mov     rbx, [r11+30h]
0x18003ffc6  mov     rsi, [r11+38h]
0x18003ffca  mov     rsp, r11
0x18003ffcd  pop     r15
0x18003ffcf  pop     r14
0x18003ffd1  pop     r12
0x18003ffd3  pop     rdi
0x18003ffd4  pop     rbp
0x18003ffd5  retn
0x18003ffd7  movzx   edx, word ptr [rcx]
0x18003ffda  test    dx, dx
0x18003ffdd  jz      loc_18003FF33
0x18003ffe3  mov     [rax], dx
0x18003ffe6  add     rcx, 2
0x18003ffea  add     rax, 2
0x18003ffee  dec     r14
0x18003fff1  sub     rbx, 1
0x18003fff5  jnz     loc_18003FF2A
0x18003fffb  jmp     loc_18003FF33
0x180040000  lea     rdx, [rsp+270h+var_250]; int *
0x180040005  mov     rcx, rbx; hHandle
0x180040008  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18004000d  mov     esi, eax
0x18004000f  test    eax, eax
0x180040011  js      short loc_18004003E
0x180040013  mov     rcx, rbx; this
0x180040016  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18004001b  movsxd  rax, [rsp+270h+var_24C]
0x180040020  movsxd  rcx, [rsp+270h+var_250]
0x180040025  shl     rcx, 1Fh
0x180040029  or      rcx, rax
0x18004002c  mov     [r15], rcx
0x18004002f  mov     rcx, rdi; this
0x180040032  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180040037  xor     eax, eax
0x180040039  jmp     loc_18003FFAB
0x18004003e  mov     rcx, [rbp+178h]; this
0x180040045  lea     r8, aWil; "wil"
0x18004004c  mov     r9d, eax; char *
0x18004004f  mov     edx, 0DEh; void *
0x180040054  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040059  mov     rcx, rbx; this
0x18004005c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180040061  jmp     loc_18003FF79
0x180040066  mov     rcx, [rbp+178h]; this
0x18004006d  lea     r8, aWil; "wil"
0x180040074  mov     r9d, eax; char *
0x180040077  mov     edx, 0D6h; void *
0x18004007c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040081  jmp     short loc_180040086
0x180040083  mov     esi, r12d
0x180040086  lea     rcx, [rsp+270h+var_248]
0x18004008b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180040090  jmp     loc_18003FF81
```
