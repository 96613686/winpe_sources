# OneCore::Base::Telemetry::OneSettingsQuery::CreateHeaders(ushort const *,ushort * *)

- ea: `0x18000312c`
- end: `0x18000337f`
- name: `?CreateHeaders@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBGPEAPEAG@Z`
- size: `595`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000354c`
- `0x180006c40`

## callees

- `0x18000312c`
- `0x1800076c4`
- `0x180007ae0`
- `0x180007b54`
- `0x1800191f0`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x1800031e2`
- `ADVAPI32!RegGetValueW` at `0x180003272`
- `ADVAPI32!RegGetValueW` at `0x1800031e2`
- `ADVAPI32!RegGetValueW` at `0x180003272`
- `KERNEL32!HeapAlloc` at `0x180003208`
- `KERNEL32!HeapAlloc` at `0x18000331d`
- `KERNEL32!HeapAlloc` at `0x180003208`
- `KERNEL32!HeapAlloc` at `0x18000331d`
- `KERNEL32!GetProcessHeap` at `0x1800031f7`
- `KERNEL32!GetProcessHeap` at `0x18000328f`
- `KERNEL32!GetProcessHeap` at `0x18000330c`
- `KERNEL32!GetProcessHeap` at `0x18000333e`
- `KERNEL32!GetProcessHeap` at `0x1800031f7`
- `KERNEL32!GetProcessHeap` at `0x18000328f`
- `KERNEL32!GetProcessHeap` at `0x18000330c`
- `KERNEL32!GetProcessHeap` at `0x18000333e`
- `KERNEL32!HeapFree` at `0x18000329d`
- `KERNEL32!HeapFree` at `0x18000334c`
- `KERNEL32!HeapFree` at `0x18000329d`
- `KERNEL32!HeapFree` at `0x18000334c`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::CreateHeaders(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  unsigned int v4; // edi
  void *v5; // rbx
  LSTATUS ValueW; // eax
  bool v7; // sf
  bool v8; // cc
  unsigned __int64 v9; // rsi
  HANDLE ProcessHeap; // rax
  const unsigned __int16 *v11; // r8
  unsigned __int64 v12; // rsi
  LSTATUS v13; // eax
  HANDLE v14; // rax
  _WORD *v15; // rax
  __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  HANDLE v18; // rax
  HANDLE v19; // rax
  unsigned int pvData; // [rsp+28h] [rbp-D8h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  PVOID v24; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  pcbData = 0;
  v23 = 0;
  v24 = 0;
  v4 = 0;
  v5 = 0;
  if ( (int)StringCchPrintfW(
              SubKey,
              0x104u,
              L"%ls\\%ls\\%ls",
              (char *)this + 1080,
              (char *)this + 40,
              (char *)this + 560) >= 0 )
  {
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"ETag", 2u, 0, 0, &pcbData);
    v7 = ValueW < 0;
    v8 = ValueW <= 0;
    if ( !ValueW )
    {
      v9 = pcbData + 30;
      ProcessHeap = GetProcessHeap();
      v5 = HeapAlloc(ProcessHeap, 8u, (unsigned int)v9);
      if ( !v5 )
      {
LABEL_4:
        v12 = 0;
        goto LABEL_23;
      }
      if ( (int)StringCbCopyExW((unsigned __int16 *)v5, v9, v11, (unsigned __int16 **)&v24, &v23, pvData) < 0 )
      {
LABEL_11:
        v14 = GetProcessHeap();
        HeapFree(v14, 0, v5);
        v5 = 0;
        goto LABEL_4;
      }
      pcbData = v23;
      v13 = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"ETag", 2u, 0, v24, &pcbData);
      v7 = v13 < 0;
      v8 = v13 <= 0;
      if ( !v13 )
        goto LABEL_13;
    }
    if ( !v8 )
      v7 = 1;
    if ( v7 )
    {
      if ( v5 )
        goto LABEL_11;
      goto LABEL_18;
    }
  }
  if ( v5 )
  {
LABEL_13:
    v15 = v5;
    v16 = 0x7FFFFFFF;
    do
    {
      if ( !*v15 )
        break;
      ++v15;
      --v16;
    }
    while ( v16 );
    v4 = v16 == 0 ? 0x80070057 : 0;
    v17 = (0x7FFFFFFF - v16) & ((unsigned __int128)-(__int128)(unsigned __int64)v16 >> 64);
    if ( !v16 )
      goto LABEL_25;
    goto LABEL_19;
  }
LABEL_18:
  v17 = 0;
LABEL_19:
  v12 = v17 + 1;
  if ( !v5 )
    v12 = v17;
  if ( v12 )
  {
    v18 = GetProcessHeap();
    *a3 = (unsigned __int16 *)HeapAlloc(v18, 8u, 2 * v12);
  }
LABEL_23:
  if ( v5 )
  {
    v4 = StringCchCopyW(*a3, v12, (const unsigned __int16 *)v5);
LABEL_25:
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v5);
  }
  return v4;
}

```

## disassembly

```asm
0x18000312c  mov     [rsp-8+arg_8], rbx
0x180003131  mov     [rsp-8+arg_18], rsi
0x180003136  push    rbp
0x180003137  push    rdi
0x180003138  push    r12
0x18000313a  push    r14
0x18000313c  push    r15
0x18000313e  lea     rbp, [rsp-180h]
0x180003146  sub     rsp, 280h
0x18000314d  mov     rax, cs:__security_cookie
0x180003154  xor     rax, rsp
0x180003157  mov     [rbp+1A0h+var_30], rax
0x18000315e  xor     r12d, r12d
0x180003161  lea     rdx, [rcx+28h]
0x180003165  lea     rax, [rcx+230h]
0x18000316c  mov     [rsp+2A0h+var_260], r12d
0x180003171  mov     [rsp+2A0h+pvData], rax
0x180003176  lea     r9, [rcx+438h]
0x18000317d  mov     [rsp+2A0h+pdwType], rdx
0x180003182  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x180003187  mov     r15, r8
0x18000318a  mov     [rsp+2A0h+var_258], r12
0x18000318f  mov     edx, 104h; unsigned __int64
0x180003194  mov     [rsp+2A0h+var_250], r12
0x180003199  lea     r8, aLsLsLs; "%ls\\%ls\\%ls"
0x1800031a0  mov     edi, r12d
0x1800031a3  mov     ebx, r12d
0x1800031a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800031ab  test    eax, eax
0x1800031ad  js      loc_1800032AB
0x1800031b3  lea     rax, [rsp+2A0h+var_260]
0x1800031b8  mov     r14, 0FFFFFFFF80000002h
0x1800031bf  mov     [rsp+2A0h+pcbData], rax; pcbData
0x1800031c4  lea     r9d, [r12+2]; dwFlags
0x1800031c9  mov     [rsp+2A0h+pvData], r12; unsigned int
0x1800031ce  lea     r8, ValueName; "ETag"
0x1800031d5  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x1800031da  mov     [rsp+2A0h+pdwType], r12; pdwType
0x1800031df  mov     rcx, r14; hkey
0x1800031e2  call    cs:__imp_RegGetValueW
0x1800031e8  test    eax, eax
0x1800031ea  jnz     loc_18000327C
0x1800031f0  mov     esi, [rsp+2A0h+var_260]
0x1800031f4  add     esi, 1Eh
0x1800031f7  call    cs:__imp_GetProcessHeap
0x1800031fd  mov     r8d, esi; dwBytes
0x180003200  lea     edx, [r12+8]; dwFlags
0x180003205  mov     rcx, rax; hHeap
0x180003208  call    cs:__imp_HeapAlloc
0x18000320e  mov     rbx, rax
0x180003211  test    rax, rax
0x180003214  jnz     short loc_18000321E
0x180003216  mov     rsi, r12
0x180003219  jmp     loc_180003329
0x18000321e  lea     rax, [rsp+2A0h+var_258]
0x180003223  mov     rdx, rsi; unsigned __int64
0x180003226  lea     r9, [rsp+2A0h+var_250]; unsigned __int16 **
0x18000322b  mov     [rsp+2A0h+pdwType], rax; unsigned __int64 *
0x180003230  mov     rcx, rbx; unsigned __int16 *
0x180003233  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180003238  test    eax, eax
0x18000323a  js      short loc_18000328F
0x18000323c  mov     eax, dword ptr [rsp+2A0h+var_258]
0x180003240  lea     r8, ValueName; "ETag"
0x180003247  mov     [rsp+2A0h+var_260], eax
0x18000324b  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x180003250  lea     rax, [rsp+2A0h+var_260]
0x180003255  mov     r9d, 2; dwFlags
0x18000325b  mov     [rsp+2A0h+pcbData], rax; pcbData
0x180003260  mov     rcx, r14; hkey
0x180003263  mov     rax, [rsp+2A0h+var_250]
0x180003268  mov     [rsp+2A0h+pvData], rax; pvData
0x18000326d  mov     [rsp+2A0h+pdwType], r12; pdwType
0x180003272  call    cs:__imp_RegGetValueW
0x180003278  test    eax, eax
0x18000327a  jz      short loc_1800032B0
0x18000327c  jle     short loc_180003288
0x18000327e  movzx   eax, ax
0x180003281  or      eax, 80070000h
0x180003286  test    eax, eax
0x180003288  jns     short loc_1800032AB
0x18000328a  test    rbx, rbx
0x18000328d  jz      short loc_1800032F2
0x18000328f  call    cs:__imp_GetProcessHeap
0x180003295  mov     r8, rbx; lpMem
0x180003298  xor     edx, edx; dwFlags
0x18000329a  mov     rcx, rax; hHeap
0x18000329d  call    cs:__imp_HeapFree
0x1800032a3  mov     rbx, r12
0x1800032a6  jmp     loc_180003216
0x1800032ab  test    rbx, rbx
0x1800032ae  jz      short loc_1800032F2
0x1800032b0  mov     r8d, 7FFFFFFFh
0x1800032b6  mov     rax, rbx
0x1800032b9  mov     ecx, r8d
0x1800032bc  cmp     [rax], r12w
0x1800032c0  jz      short loc_1800032CC
0x1800032c2  add     rax, 2
0x1800032c6  sub     rcx, 1
0x1800032ca  jnz     short loc_1800032BC
0x1800032cc  mov     rax, rcx
0x1800032cf  neg     rax
0x1800032d2  mov     rax, rcx
0x1800032d5  sbb     edi, edi
0x1800032d7  sub     r8, rcx
0x1800032da  not     edi
0x1800032dc  and     edi, 80070057h
0x1800032e2  neg     rax
0x1800032e5  sbb     rdx, rdx
0x1800032e8  and     rdx, r8
0x1800032eb  test    rcx, rcx
0x1800032ee  jz      short loc_18000333E
0x1800032f0  jmp     short loc_1800032F5
0x1800032f2  mov     rdx, r12
0x1800032f5  test    rbx, rbx
0x1800032f8  lea     rsi, [rdx+1]
0x1800032fc  mov     r14, rbx
0x1800032ff  cmovz   rsi, rdx
0x180003303  test    rsi, rsi
0x180003306  jz      short loc_180003329
0x180003308  lea     rbx, [rsi+rsi]
0x18000330c  call    cs:__imp_GetProcessHeap
0x180003312  mov     r8, rbx; dwBytes
0x180003315  mov     edx, 8; dwFlags
0x18000331a  mov     rcx, rax; hHeap
0x18000331d  call    cs:__imp_HeapAlloc
0x180003323  mov     [r15], rax
0x180003326  mov     rbx, r14
0x180003329  test    rbx, rbx
0x18000332c  jz      short loc_180003352
0x18000332e  mov     rcx, [r15]; unsigned __int16 *
0x180003331  mov     r8, rbx; unsigned __int16 *
0x180003334  mov     rdx, rsi; unsigned __int64
0x180003337  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000333c  mov     edi, eax
0x18000333e  call    cs:__imp_GetProcessHeap
0x180003344  mov     r8, rbx; lpMem
0x180003347  xor     edx, edx; dwFlags
0x180003349  mov     rcx, rax; hHeap
0x18000334c  call    cs:__imp_HeapFree
0x180003352  mov     eax, edi
0x180003354  mov     rcx, [rbp+1A0h+var_30]
0x18000335b  xor     rcx, rsp; StackCookie
0x18000335e  call    __security_check_cookie
0x180003363  lea     r11, [rsp+2A0h+var_20]
0x18000336b  mov     rbx, [r11+38h]
0x18000336f  mov     rsi, [r11+48h]
0x180003373  mov     rsp, r11
0x180003376  pop     r15
0x180003378  pop     r14
0x18000337a  pop     r12
0x18000337c  pop     rdi
0x18000337d  pop     rbp
0x18000337e  retn
```
