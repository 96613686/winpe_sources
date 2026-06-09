# AppendApplicationInfo(ushort *,ulong,uint *)

- ea: `0x1400031c0`
- end: `0x1400033ac`
- name: `?AppendApplicationInfo@@YAXPEAGKPEAI@Z`
- size: `492`
- prototype: `void __fastcall(unsigned __int16 *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004640`

## callees

- `0x1400028f4`
- `0x1400031c0`
- `0x14000407c`
- `0x1400044cc`
- `0x140006f10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140003224`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140003277`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140003224`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140003277`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14000331f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14000331f`

## pseudocode

```c
void __fastcall AppendApplicationInfo(unsigned __int16 *a1, __int64 a2, unsigned int *a3)
{
  unsigned int v4; // edx
  unsigned __int16 *v5; // r8
  unsigned int v6; // edx
  unsigned __int16 *v7; // r8
  int v8; // eax
  unsigned int v9; // edx
  unsigned __int16 *v10; // r8
  __int64 v11; // rbx
  unsigned int v12; // edx
  unsigned __int16 *v13; // r8
  OLECHAR sz[40]; // [rsp+20h] [rbp-88h] BYREF

  if ( g_fApplicationIdValid )
  {
    sz[0] = 0;
    StringFromGUID2(&g_clsidApplicationId, sz, 39);
    Buffer = 0;
    GetFormatString(0x39Fu, &Buffer);
    word_14000F300 = 0;
    StringCchPrintfW(&word_14000F300, 0x400u, &Buffer, sz);
    SafeAppend(&word_14000F300, v4, v5, a3);
    sz[0] = 0;
    StringFromGUID2(&g_clsidApplicationInstId, sz, 39);
    Buffer = 0;
    GetFormatString(0x3B0u, &Buffer);
    word_14000F300 = 0;
    StringCchPrintfW(&word_14000F300, 0x400u, &Buffer, sz);
    SafeAppend(&word_14000F300, v6, v7, a3);
  }
  v8 = g_fApplicationNameValid;
  if ( g_fApplicationNameValid )
  {
    Buffer = 0;
    GetFormatString(0x3A0u, &Buffer);
    word_14000F300 = 0;
    StringCchPrintfW(&word_14000F300, 0x400u, &Buffer, &g_wszApplicationName);
    SafeAppend(&word_14000F300, v9, v10, a3);
    v8 = g_fApplicationNameValid;
  }
  if ( !g_fApplicationIdValid && !v8 && GetModuleFileNameW(0, &Filename, 0x80u) )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(&Filename + v11) );
    do
      --v11;
    while ( v11 && *(&Filename + v11) != 92 );
    Buffer = 0;
    GetFormatString(0x3AEu, &Buffer);
    word_14000F300 = 0;
    StringCchPrintfW(&word_14000F300, 0x400u, &Buffer, &algn_14000E8E2[2 * v11]);
    SafeAppend(&word_14000F300, v12, v13, a3);
  }
}

```

## disassembly

```asm
0x1400031c0  mov     [rsp+arg_0], rbx
0x1400031c5  mov     [rsp+arg_8], rbp
0x1400031ca  push    rsi
0x1400031cb  push    rdi
0x1400031cc  push    r12
0x1400031ce  push    r14
0x1400031d0  push    r15
0x1400031d2  sub     rsp, 80h
0x1400031d9  mov     rax, cs:__security_cookie
0x1400031e0  xor     rax, rsp
0x1400031e3  mov     [rsp+0A8h+var_38], rax
0x1400031e8  xor     esi, esi
0x1400031ea  lea     r14, Buffer
0x1400031f1  cmp     cs:?g_fApplicationIdValid@@3HA, esi; int g_fApplicationIdValid
0x1400031f7  lea     r15, word_14000F300
0x1400031fe  mov     rdi, r8
0x140003201  mov     r12d, 400h
0x140003207  jz      loc_1400032B6
0x14000320d  lea     ebx, [rsi+27h]
0x140003210  mov     [rsp+0A8h+sz], si
0x140003215  mov     r8d, ebx; cchMax
0x140003218  lea     rdx, [rsp+0A8h+sz]; lpsz
0x14000321d  lea     rcx, ?g_clsidApplicationId@@3U_GUID@@A; rguid
0x140003224  call    cs:__imp_StringFromGUID2
0x14000322a  mov     rdx, r14; unsigned __int16 *
0x14000322d  mov     cs:Buffer, si
0x140003234  lea     ecx, [r12-61h]; unsigned int
0x140003239  call    ?GetFormatString@@YAXIPEAG@Z; GetFormatString(uint,ushort *)
0x14000323e  lea     r9, [rsp+0A8h+sz]
0x140003243  mov     cs:word_14000F300, si
0x14000324a  mov     r8, r14; unsigned __int16 *
0x14000324d  mov     edx, r12d; unsigned __int64
0x140003250  mov     rcx, r15; unsigned __int16 *
0x140003253  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003258  mov     r9, rdi; unsigned int *
0x14000325b  mov     rcx, r15; unsigned __int16 *
0x14000325e  call    ?SafeAppend@@YAXPEAGK0PEAI@Z; SafeAppend(ushort *,ulong,ushort *,uint *)
0x140003263  mov     r8d, ebx; cchMax
0x140003266  mov     [rsp+0A8h+sz], si
0x14000326b  lea     rdx, [rsp+0A8h+sz]; lpsz
0x140003270  lea     rcx, ?g_clsidApplicationInstId@@3U_GUID@@A; rguid
0x140003277  call    cs:__imp_StringFromGUID2
0x14000327d  mov     rdx, r14; unsigned __int16 *
0x140003280  mov     cs:Buffer, si
0x140003287  lea     ecx, [r12-50h]; unsigned int
0x14000328c  call    ?GetFormatString@@YAXIPEAG@Z; GetFormatString(uint,ushort *)
0x140003291  lea     r9, [rsp+0A8h+sz]
0x140003296  mov     cs:word_14000F300, si
0x14000329d  mov     r8, r14; unsigned __int16 *
0x1400032a0  mov     edx, r12d; unsigned __int64
0x1400032a3  mov     rcx, r15; unsigned __int16 *
0x1400032a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400032ab  mov     r9, rdi; unsigned int *
0x1400032ae  mov     rcx, r15; unsigned __int16 *
0x1400032b1  call    ?SafeAppend@@YAXPEAGK0PEAI@Z; SafeAppend(ushort *,ulong,ushort *,uint *)
0x1400032b6  mov     eax, cs:?g_fApplicationNameValid@@3HA; int g_fApplicationNameValid
0x1400032bc  test    eax, eax
0x1400032be  jz      short loc_140003301
0x1400032c0  mov     rdx, r14; unsigned __int16 *
0x1400032c3  mov     cs:Buffer, si
0x1400032ca  mov     ecx, 3A0h; unsigned int
0x1400032cf  call    ?GetFormatString@@YAXIPEAG@Z; GetFormatString(uint,ushort *)
0x1400032d4  lea     r9, ?g_wszApplicationName@@3PAGA; ushort near * g_wszApplicationName
0x1400032db  mov     cs:word_14000F300, si
0x1400032e2  mov     r8, r14; unsigned __int16 *
0x1400032e5  mov     rdx, r12; unsigned __int64
0x1400032e8  mov     rcx, r15; unsigned __int16 *
0x1400032eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400032f0  mov     r9, rdi; unsigned int *
0x1400032f3  mov     rcx, r15; unsigned __int16 *
0x1400032f6  call    ?SafeAppend@@YAXPEAGK0PEAI@Z; SafeAppend(ushort *,ulong,ushort *,uint *)
0x1400032fb  mov     eax, cs:?g_fApplicationNameValid@@3HA; int g_fApplicationNameValid
0x140003301  cmp     cs:?g_fApplicationIdValid@@3HA, esi; int g_fApplicationIdValid
0x140003307  jnz     short loc_140003383
0x140003309  test    eax, eax
0x14000330b  jnz     short loc_140003383
0x14000330d  lea     rbp, Filename
0x140003314  mov     r8d, 80h; nSize
0x14000331a  mov     rdx, rbp; lpFilename
0x14000331d  xor     ecx, ecx; hModule
0x14000331f  call    cs:__imp_GetModuleFileNameW
0x140003325  test    eax, eax
0x140003327  jz      short loc_140003383
0x140003329  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000332d  inc     rbx
0x140003330  cmp     [rbp+rbx*2+0], si
0x140003335  jnz     short loc_14000332D
0x140003337  jmp     short loc_140003341
0x140003339  cmp     word ptr [rbp+rbx*2+0], 5Ch ; '\'
0x14000333f  jz      short loc_140003347
0x140003341  sub     rbx, 1
0x140003345  jnz     short loc_140003339
0x140003347  mov     rdx, r14; unsigned __int16 *
0x14000334a  mov     cs:Buffer, si
0x140003351  mov     ecx, 3AEh; unsigned int
0x140003356  call    ?GetFormatString@@YAXIPEAG@Z; GetFormatString(uint,ushort *)
0x14000335b  lea     r9, [rbp+2]
0x14000335f  mov     cs:word_14000F300, si
0x140003366  lea     r9, [r9+rbx*2]
0x14000336a  mov     r8, r14; unsigned __int16 *
0x14000336d  mov     rdx, r12; unsigned __int64
0x140003370  mov     rcx, r15; unsigned __int16 *
0x140003373  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003378  mov     r9, rdi; unsigned int *
0x14000337b  mov     rcx, r15; unsigned __int16 *
0x14000337e  call    ?SafeAppend@@YAXPEAGK0PEAI@Z; SafeAppend(ushort *,ulong,ushort *,uint *)
0x140003383  mov     rcx, [rsp+0A8h+var_38]
0x140003388  xor     rcx, rsp; StackCookie
0x14000338b  call    __security_check_cookie
0x140003390  lea     r11, [rsp+0A8h+var_28]
0x140003398  mov     rbx, [r11+30h]
0x14000339c  mov     rbp, [r11+38h]
0x1400033a0  mov     rsp, r11
0x1400033a3  pop     r15
0x1400033a5  pop     r14
0x1400033a7  pop     r12
0x1400033a9  pop     rdi
0x1400033aa  pop     rsi
0x1400033ab  retn
```
