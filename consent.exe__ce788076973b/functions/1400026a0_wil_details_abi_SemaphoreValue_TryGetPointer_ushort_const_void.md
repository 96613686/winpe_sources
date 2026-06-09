# wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)

- ea: `0x1400026a0`
- end: `0x1400029d6`
- name: `?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z`
- size: `822`
- prototype: `__int64 __fastcall(WCHAR *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000e354`

## callees

- `0x1400026a0`
- `0x140002ea0`
- `0x14000df54`
- `0x14000f588`
- `0x14000fb48`
- `0x14001e050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140002758`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140002882`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140002758`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140002882`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000276a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000276a`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetPointer(WCHAR *a1, void **a2)
{
  WCHAR *v2; // r8
  __int64 v3; // rbp
  __int64 v4; // rdi
  unsigned __int64 v5; // r15
  __int64 v6; // rax
  __int64 v7; // r10
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  wil::details *v13; // rax
  wil::details *v14; // rbx
  const char *v15; // r9
  unsigned int LastError; // esi
  int ValueFromSemaphore; // eax
  void *v19; // rdx
  WCHAR *v20; // rax
  _WORD *v21; // rdx
  wil::details *v22; // rax
  const char *v23; // r9
  wil::details *v24; // rdi
  int v25; // eax
  void *v26; // rdx
  void *v27; // rdx
  void *v28; // rdx
  __int64 v29; // rcx
  _WORD *v30; // r8
  const unsigned __int16 *v31; // r9
  _WORD *v32; // rcx
  _WORD *v33; // r8
  const unsigned __int16 *v34; // rcx
  void *v35; // rdx
  void *v36; // rdx
  int v37; // [rsp+20h] [rbp-258h] BYREF
  int v38[3]; // [rsp+24h] [rbp-254h] BYREF
  WCHAR Name[260]; // [rsp+30h] [rbp-248h] BYREF
  _BYTE v40[8]; // [rsp+238h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v2 = Name;
  v3 = 2147483646;
  *a2 = 0;
  v4 = 260;
  v5 = 0;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*a1 )
      break;
    *v2++ = *a1++;
    --v6;
    --v7;
  }
  while ( v7 );
  v10 = v2 - 1;
  v11 = 260;
  v12 = Name;
  if ( v7 )
    v10 = v2;
  *v10 = 0;
  while ( *v12 )
  {
    ++v12;
    if ( !--v11 )
      goto LABEL_10;
  }
  v29 = 2147483646;
  v30 = &v40[-2 * v11];
  v31 = L"_p0";
  do
  {
    if ( !v29 )
      break;
    if ( !*v31 )
      break;
    *v30++ = *v31++;
    --v29;
    --v11;
  }
  while ( v11 );
  v32 = v30 - 1;
  if ( v11 )
    v32 = v30;
  *v32 = 0;
LABEL_10:
  v13 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v14 = v13;
  if ( v13 )
  {
    v38[0] = 0;
    v37 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, v38);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v37);
      wil::details::CloseHandle(v14, v19);
      goto LABEL_14;
    }
    v20 = Name;
    while ( *v20 )
    {
      ++v20;
      if ( !--v4 )
        goto LABEL_24;
    }
    v33 = &v40[-2 * v4];
    v34 = L"h";
    do
    {
      if ( !v3 )
        break;
      if ( !*v34 )
        break;
      *v33++ = *v34++;
      --v3;
      --v4;
    }
    while ( v4 );
    v21 = v33 - 1;
    if ( v4 )
      v21 = v33;
    *v21 = 0;
LABEL_24:
    v22 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v24 = v22;
    if ( v22 )
    {
      v25 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v22, &v37);
      LastError = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v25,
          v37);
        wil::details::CloseHandle(v24, v35);
        wil::details::CloseHandle(v14, v36);
        goto LABEL_14;
      }
      wil::details::CloseHandle(v24, v26);
      v5 = v38[0] | (unsigned __int64)((__int64)v37 << 31);
      wil::details::CloseHandle(v14, v27);
      goto LABEL_27;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v23);
    wil::details::CloseHandle(v14, v28);
  }
  else
  {
    if ( GetLastError() == 2 )
      goto LABEL_27;
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v15);
  }
  if ( (LastError & 0x80000000) != 0 )
  {
LABEL_14:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, (unsigned int)"wil", (const char *)LastError, v37);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)LastError, v37);
    return LastError;
  }
LABEL_27:
  *a2 = (void *)(4 * v5);
  return 0;
}

```

## disassembly

```asm
0x1400026a0  mov     [rsp+arg_10], rbx
0x1400026a5  push    rbp
0x1400026a6  push    rdi
0x1400026a7  push    r12
0x1400026a9  push    r14
0x1400026ab  push    r15
0x1400026ad  sub     rsp, 250h
0x1400026b4  mov     rax, cs:__security_cookie
0x1400026bb  xor     rax, rsp
0x1400026be  mov     [rsp+278h+var_38], rax
0x1400026c6  xor     r12d, r12d
0x1400026c9  lea     r8, [rsp+278h+Name]
0x1400026ce  mov     ebp, 7FFFFFFEh
0x1400026d3  mov     [rdx], r12
0x1400026d6  mov     edi, 104h
0x1400026db  mov     r15d, r12d
0x1400026de  mov     eax, ebp
0x1400026e0  mov     r10d, edi
0x1400026e3  mov     r14, rdx
0x1400026e6  mov     r9, rcx
0x1400026e9  nop     dword ptr [rax+00000000h]
0x1400026f0  test    rax, rax
0x1400026f3  jz      short loc_140002713
0x1400026f5  movzx   ecx, word ptr [r9]
0x1400026f9  test    cx, cx
0x1400026fc  jz      short loc_140002713
0x1400026fe  mov     [r8], cx
0x140002702  add     r9, 2
0x140002706  add     r8, 2
0x14000270a  dec     rax
0x14000270d  sub     r10, 1
0x140002711  jnz     short loc_1400026F0
0x140002713  test    r10, r10
0x140002716  lea     rcx, [r8-2]
0x14000271a  mov     rdx, rdi
0x14000271d  lea     rax, [rsp+278h+Name]
0x140002722  cmovnz  rcx, r8
0x140002726  mov     [rcx], r12w
0x14000272a  nop     word ptr [rax+rax+00h]
0x140002730  cmp     [rax], r12w
0x140002734  jz      loc_140002902
0x14000273a  add     rax, 2
0x14000273e  sub     rdx, 1
0x140002742  jnz     short loc_140002730
0x140002744  lea     r8, [rsp+278h+Name]; lpName
0x140002749  mov     [rsp+278h+arg_0], rsi
0x140002751  xor     edx, edx; bInheritHandle
0x140002753  mov     ecx, 1F0003h; dwDesiredAccess
0x140002758  call    cs:__imp_OpenSemaphoreW
0x14000275e  mov     rbx, rax
0x140002761  test    rax, rax
0x140002764  jnz     loc_140002806
0x14000276a  call    cs:__imp_GetLastError
0x140002770  cmp     eax, 2
0x140002773  jz      loc_1400028C8
0x140002779  mov     rcx, [rsp+278h]; this
0x140002781  lea     r8, aWil; "wil"
0x140002788  mov     edx, 0D0h; void *
0x14000278d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140002792  mov     esi, eax
0x140002794  test    esi, esi
0x140002796  jns     loc_1400028C8
0x14000279c  mov     rcx, [rsp+278h]; this
0x1400027a4  lea     r8, aWil; "wil"
0x1400027ab  mov     r9d, esi; char *
0x1400027ae  mov     edx, 66h ; 'f'; void *
0x1400027b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400027b8  mov     rcx, [rsp+278h]; this
0x1400027c0  lea     r8, aWil; "wil"
0x1400027c7  mov     r9d, esi; char *
0x1400027ca  mov     edx, 6Fh ; 'o'; void *
0x1400027cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400027d4  mov     eax, esi
0x1400027d6  mov     rsi, [rsp+278h+arg_0]
0x1400027de  mov     rcx, [rsp+278h+var_38]
0x1400027e6  xor     rcx, rsp; StackCookie
0x1400027e9  call    __security_check_cookie
0x1400027ee  mov     rbx, [rsp+278h+arg_10]
0x1400027f6  add     rsp, 250h
0x1400027fd  pop     r15
0x1400027ff  pop     r14
0x140002801  pop     r12
0x140002803  pop     rdi
0x140002804  pop     rbp
0x140002805  retn
0x140002806  lea     rdx, [rsp+278h+var_254]; int *
0x14000280b  mov     [rsp+278h+var_254], r12d
0x140002810  mov     rcx, rbx; hHandle
0x140002813  mov     [rsp+278h+var_258], r12d; int
0x140002818  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000281d  mov     esi, eax
0x14000281f  test    eax, eax
0x140002821  jns     short loc_14000284C
0x140002823  mov     rcx, [rsp+278h]; this
0x14000282b  lea     r8, aWil; "wil"
0x140002832  mov     r9d, eax; char *
0x140002835  mov     edx, 0D6h; void *
0x14000283a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000283f  mov     rcx, rbx; this
0x140002842  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140002847  jmp     loc_14000279C
0x14000284c  lea     rax, [rsp+278h+Name]
0x140002851  cmp     [rax], r12w
0x140002855  jz      loc_140002957
0x14000285b  add     rax, 2
0x14000285f  sub     rdi, 1
0x140002863  jnz     short loc_140002851
0x140002865  jmp     short loc_140002876
0x140002867  test    rdi, rdi
0x14000286a  lea     rdx, [r8-2]
0x14000286e  cmovnz  rdx, r8
0x140002872  mov     [rdx], r12w
0x140002876  lea     r8, [rsp+278h+Name]; lpName
0x14000287b  xor     edx, edx; bInheritHandle
0x14000287d  mov     ecx, 1F0003h; dwDesiredAccess
0x140002882  call    cs:__imp_OpenSemaphoreW
0x140002888  mov     rdi, rax
0x14000288b  test    rax, rax
0x14000288e  jz      short loc_1400028DA
0x140002890  lea     rdx, [rsp+278h+var_258]; int *
0x140002895  mov     rcx, rax; hHandle
0x140002898  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000289d  mov     esi, eax
0x14000289f  test    eax, eax
0x1400028a1  js      loc_1400029A5
0x1400028a7  mov     rcx, rdi; this
0x1400028aa  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1400028af  movsxd  rax, [rsp+278h+var_254]
0x1400028b4  mov     rcx, rbx; this
0x1400028b7  movsxd  r15, [rsp+278h+var_258]
0x1400028bc  shl     r15, 1Fh
0x1400028c0  or      r15, rax
0x1400028c3  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1400028c8  lea     rax, ds:0[r15*4]
0x1400028d0  mov     [r14], rax
0x1400028d3  xor     eax, eax
0x1400028d5  jmp     loc_1400027D6
0x1400028da  mov     rcx, [rsp+278h]; this
0x1400028e2  lea     r8, aWil; "wil"
0x1400028e9  mov     edx, 0DCh; void *
0x1400028ee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400028f3  mov     rcx, rbx; this
0x1400028f6  mov     esi, eax
0x1400028f8  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1400028fd  jmp     loc_140002794
0x140002902  lea     rax, [rdx+rdx]
0x140002906  mov     rcx, rbp
0x140002909  lea     r8, [rsp+278h+var_40]
0x140002911  sub     r8, rax
0x140002914  lea     r9, aP0; "_p0"
0x14000291b  test    rdx, rdx
0x14000291e  jz      short loc_140002943
0x140002920  test    rcx, rcx
0x140002923  jz      short loc_140002943
0x140002925  movzx   eax, word ptr [r9]
0x140002929  test    ax, ax
0x14000292c  jz      short loc_140002943
0x14000292e  mov     [r8], ax
0x140002932  add     r9, 2
0x140002936  add     r8, 2
0x14000293a  dec     rcx
0x14000293d  sub     rdx, 1
0x140002941  jnz     short loc_140002920
0x140002943  test    rdx, rdx
0x140002946  lea     rcx, [r8-2]
0x14000294a  cmovnz  rcx, r8
0x14000294e  mov     [rcx], r12w
0x140002952  jmp     loc_140002744
0x140002957  lea     rax, [rdi+rdi]
0x14000295b  lea     r8, [rsp+278h+var_40]
0x140002963  sub     r8, rax
0x140002966  lea     rcx, asc_140021060; "h"
0x14000296d  test    rdi, rdi
0x140002970  jz      loc_140002867
0x140002976  test    rbp, rbp
0x140002979  jz      loc_140002867
0x14000297f  movzx   eax, word ptr [rcx]
0x140002982  test    ax, ax
0x140002985  jz      loc_140002867
0x14000298b  mov     [r8], ax
0x14000298f  add     rcx, 2
0x140002993  add     r8, 2
0x140002997  dec     rbp
0x14000299a  sub     rdi, 1
0x14000299e  jnz     short loc_140002976
0x1400029a0  jmp     loc_140002867
0x1400029a5  mov     rcx, [rsp+278h]; this
0x1400029ad  lea     r8, aWil; "wil"
0x1400029b4  mov     r9d, eax; char *
0x1400029b7  mov     edx, 0DEh; void *
0x1400029bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400029c1  mov     rcx, rdi; this
0x1400029c4  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1400029c9  mov     rcx, rbx; this
0x1400029cc  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1400029d1  jmp     loc_14000279C
```
