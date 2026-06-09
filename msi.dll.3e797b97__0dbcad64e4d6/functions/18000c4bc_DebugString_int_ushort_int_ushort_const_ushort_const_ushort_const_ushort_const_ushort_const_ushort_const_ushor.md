# DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)

- ea: `0x18000c4bc`
- end: `0x18000ca36`
- name: `?DebugString@@YAXHGHPEBG000000KPEAX@Z`
- size: `1402`
- prototype: `void(int, unsigned __int16, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, void *)`
- caller_count: `664`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180002820`
- `0x180003b44`
- `0x180005b1c`
- `0x1800079a8`
- `0x180007c44`
- `0x180007f3c`
- `0x180008194`
- `0x180008b40`
- `0x180008d90`
- `0x180009268`
- `0x180009c38`
- `0x18000b6a0`
- `0x18000baa0`
- `0x18000bb80`
- `0x18000bd60`
- `0x18000c040`
- `0x18000c2a0`
- `0x18000cb60`
- `0x18000cd18`
- `0x18000cf58`
- `0x18000d270`
- `0x18000ded0`
- `0x18000e5b0`
- `0x18000f930`
- `0x180011280`
- `0x18001386c`
- `0x180013fe4`
- `0x180015e80`
- `0x1800171d0`
- `0x180018f28`
- `0x18001b094`
- `0x18001b744`
- `0x18001c030`
- `0x18001def0`
- `0x18001e254`
- `0x18001e390`
- `0x18001e914`
- `0x18001f6b0`
- `0x18001fbf0`
- `0x18001fd70`
- `0x1800202e4`
- `0x180022994`
- `0x180022cb4`
- `0x1800242a0`
- `0x1800299b0`
- `0x180029d70`
- `0x18002a320`
- `0x18002a5f0`
- `0x18002ab60`
- `0x18002af50`

## callees

- `0x18000c4bc`
- `0x180010ac0`
- `0x180020620`
- `0x180087d44`
- `0x1800a5e58`
- `0x1800d1eb8`
- `0x1800d20e8`
- `0x180121fc0`
- `0x18014b5dc`
- `0x180265240`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000c598`
- `KERNEL32!GetCurrentThreadId` at `0x18000c598`
- `KERNEL32!FormatMessageW` at `0x18000c8a7`
- `KERNEL32!FormatMessageW` at `0x18000c911`
- `KERNEL32!FormatMessageW` at `0x18000c8a7`
- `KERNEL32!FormatMessageW` at `0x18000c911`
- `KERNEL32!GetLastError` at `0x18000c8bb`
- `KERNEL32!GetLastError` at `0x18000c8bb`
- `KERNEL32!OutputDebugStringW` at `0x18000c9c4`
- `KERNEL32!OutputDebugStringW` at `0x18000c9d7`
- `KERNEL32!OutputDebugStringW` at `0x18000c9c4`
- `KERNEL32!OutputDebugStringW` at `0x18000c9d7`
- `KERNEL32!GlobalFree` at `0x18000c754`
- `KERNEL32!GlobalFree` at `0x18000c754`
- `KERNEL32!GetCurrentProcessId` at `0x18000c7c5`
- `KERNEL32!GetCurrentProcessId` at `0x18000c7c5`
- `KERNEL32!GetLocalTime` at `0x18000c5be`
- `KERNEL32!GetLocalTime` at `0x18000c5be`

## string_xrefs

- `0x18000c5dc`: `MSI (a)`
- `0x18000c5eb`: `MSI (c)`
- `0x18000c5ca`: `MSI (s)`

## pseudocode

```c
void __fastcall DebugString(
        int a1,
        unsigned __int16 a2,
        DWORD a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        const unsigned __int16 *a10,
        unsigned int a11,
        void *a12)
{
  const unsigned __int16 *v13; // rdi
  const unsigned __int16 *v15; // r15
  int v16; // eax
  int CurrentThreadId; // esi
  __int128 *v18; // r10
  int v19; // r9d
  _OWORD *v20; // rcx
  int v21; // ebx
  unsigned __int8 v22; // al
  char v23; // di
  HINSTANCE MsgDll; // rbx
  DWORD v25; // r15d
  int v26; // eax
  unsigned __int16 v27[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v28; // [rsp+64h] [rbp-9Ch]
  DWORD dwMessageId; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v30; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v31; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v32; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v33; // [rsp+88h] [rbp-78h]
  unsigned int v34; // [rsp+90h] [rbp-70h] BYREF
  void *v35; // [rsp+98h] [rbp-68h]
  _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  HGLOBAL hMem; // [rsp+B0h] [rbp-50h] BYREF
  int v38; // [rsp+B8h] [rbp-48h]
  char v39; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v40[224]; // [rsp+100h] [rbp+0h] BYREF
  va_list Arguments[7]; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int128 v42; // [rsp+2F8h] [rbp+1F8h] BYREF
  __int128 v43; // [rsp+308h] [rbp+208h] BYREF
  __int128 v44; // [rsp+318h] [rbp+218h] BYREF
  unsigned __int16 v45[8]; // [rsp+330h] [rbp+230h] BYREF
  __int128 v46; // [rsp+340h] [rbp+240h]
  __int128 v47; // [rsp+350h] [rbp+250h]
  __int128 v48; // [rsp+360h] [rbp+260h]

  v13 = a6;
  v15 = a7;
  v33 = a8;
  v32 = a9;
  v35 = a12;
  v16 = g_dmDiagnosticMode;
  dwMessageId = a3;
  v28 = a2;
  v30 = a6;
  v31 = a7;
  if ( g_dmDiagnosticMode == -1 )
  {
    SetDiagnosticMode();
    v16 = g_dmDiagnosticMode;
  }
  if ( ((v16 | 0x10) & a1) == 0 )
    return;
  if ( (dword_180315328 & 1) == 0 )
  {
    dword_180315328 |= 1u;
    dword_18031532C = (unsigned __int8)GetCurrentProcessId();
  }
  *(_DWORD *)v27 = (unsigned __int8)GetCurrentThreadId();
  CurrentThreadId = (unsigned __int8)MsiGetCurrentThreadId();
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  v18 = 0;
  v43 = *(_OWORD *)L"MSI (s)";
  v42 = *(_OWORD *)L"MSI (a)";
  v44 = *(_OWORD *)L"MSI (c)";
  if ( g_scServerContext )
  {
    if ( g_scServerContext == 1 || g_scServerContext == 2 )
    {
      v18 = &v43;
    }
    else if ( g_scServerContext == 3 )
    {
      v18 = &v42;
    }
  }
  else
  {
    v18 = &v44;
  }
  v19 = 58;
  if ( *(_DWORD *)v27 != CurrentThreadId )
    v19 = 33;
  if ( (int)StringCchPrintfW(
              v45,
              0x21u,
              L"%s (%.2X%c%.2X) [%02u:%02u:%02u:%03u]: ",
              v18,
              dword_18031532C,
              v19,
              CurrentThreadId,
              SystemTime.wHour,
              SystemTime.wMinute,
              SystemTime.wSecond,
              SystemTime.wMilliseconds) < 0 )
    return;
  v38 = 256;
  hMem = &v39;
  if ( (a1 & 0x10) != 0 )
  {
    Arguments[4] = (va_list)v33;
    Arguments[5] = (va_list)v32;
    Arguments[3] = (va_list)a7;
    Arguments[2] = (va_list)a6;
    Arguments[0] = (va_list)a4;
    Arguments[1] = (va_list)a5;
    v23 = 0;
    Arguments[6] = (va_list)a10;
    v34 = (_WORD)dword_180310E5C == 0;
    v27[0] = dword_180310E5C;
    while ( MsiSwitchLanguage(&v34, v27) )
    {
      MsgDll = GetMsgDll(v27[0]);
      if ( MsgDll )
      {
        v25 = v27[0];
        if ( !FormatMessageW(0x2800u, MsgDll, dwMessageId, v27[0], (LPWSTR)hMem + 32, v38 - 32, Arguments) )
        {
          if ( GetLastError() == 122
            && (unsigned __int8)CAPITempBuffer<unsigned short,256>::SetSize(&hMem, 1100)
            && FormatMessageW(0x2800u, MsgDll, dwMessageId, v25, (LPWSTR)hMem + 32, v38 - 32, Arguments) )
          {
            v23 = 1;
          }
          if ( !v23 )
            continue;
        }
      }
      goto LABEL_41;
    }
    *((_WORD *)hMem + 32) = 0;
LABEL_41:
    v15 = v31;
    v13 = v30;
  }
  else if ( (unsigned int)StringCchPrintfW(v40, 0xE0u, a4, a5, a6, a7, v33, v32, a10) == -2147024774 )
  {
    if ( (unsigned __int8)CAPITempBuffer<unsigned short,256>::SetSize(&hMem, 1100) )
    {
      v26 = StringCchPrintfW((unsigned __int16 *)hMem + 32, v38 - 32, a4, a5, a6, a7, v33, v32, a10);
      if ( v26 < 0 && v26 != -2147024774 )
        goto LABEL_23;
    }
  }
  v20 = hMem;
  if ( !hMem || v38 < 32 )
  {
    if ( v38 > 256 )
      goto LABEL_25;
    return;
  }
  v21 = g_dmDiagnosticMode;
  v22 = g_dmDiagnosticMode;
  *(_OWORD *)hMem = *(_OWORD *)v45;
  v20[1] = v46;
  v20[2] = v47;
  v20[3] = v48;
  if ( ((unsigned __int8)a1 & v22 & 3) != 0 )
  {
    OutputDebugStringW((LPCWSTR)hMem);
    OutputDebugStringW(L"\r\n");
    v21 = g_dmDiagnosticMode;
  }
  if ( ((unsigned __int8)a1 & (unsigned __int8)v21 & 0xC) != 0 )
  {
    g_dmDiagnosticMode = 0;
    WriteLog((const unsigned __int16 *)hMem);
    g_dmDiagnosticMode = v21;
  }
  if ( (a1 & 0x10) != 0 )
    ReportToEventLogW(v28, dwMessageId, a4, a5, v13, v15, v33, v32, a11, v35);
LABEL_23:
  if ( v38 > 256 )
  {
    v20 = hMem;
LABEL_25:
    GlobalFree(v20);
  }
}

```

## disassembly

```asm
0x18000c4bc  mov     [rsp-8+arg_0], rbx
0x18000c4c1  push    rbp
0x18000c4c2  push    rsi
0x18000c4c3  push    rdi
0x18000c4c4  push    r12
0x18000c4c6  push    r13
0x18000c4c8  push    r14
0x18000c4ca  push    r15
0x18000c4cc  lea     rbp, [rsp-290h]
0x18000c4d4  sub     rsp, 390h
0x18000c4db  mov     rax, cs:__security_cookie
0x18000c4e2  xor     rax, rsp
0x18000c4e5  mov     [rbp+2C0h+var_40], rax
0x18000c4ec  mov     rax, [rbp+2C0h+arg_38]
0x18000c4f3  mov     r12, r9
0x18000c4f6  mov     rdi, [rbp+2C0h+arg_28]
0x18000c4fd  mov     r14d, ecx
0x18000c500  mov     r15, [rbp+2C0h+arg_30]
0x18000c507  mov     r13, [rbp+2C0h+arg_20]
0x18000c50e  mov     rbx, [rbp+2C0h+arg_48]
0x18000c515  mov     [rbp+2C0h+var_338], rax
0x18000c519  mov     rax, [rbp+2C0h+arg_40]
0x18000c520  mov     [rbp+2C0h+var_340], rax
0x18000c524  mov     rax, [rbp+2C0h+arg_58]
0x18000c52b  mov     [rbp+2C0h+var_328], rax
0x18000c52f  mov     eax, cs:?g_dmDiagnosticMode@@3HA; int g_dmDiagnosticMode
0x18000c535  mov     [rsp+3C0h+dwMessageId], r8d
0x18000c53a  mov     [rsp+3C0h+var_35C], dx
0x18000c53f  mov     [rsp+3C0h+var_350], rdi
0x18000c544  mov     [rsp+3C0h+var_348], r15
0x18000c549  cmp     eax, 0FFFFFFFFh
0x18000c54c  jz      loc_18000C79E
0x18000c552  or      eax, 10h
0x18000c555  test    r14d, eax
0x18000c558  jnz     short loc_18000C585
0x18000c55a  mov     rcx, [rbp+2C0h+var_40]
0x18000c561  xor     rcx, rsp; StackCookie
0x18000c564  call    __security_check_cookie
0x18000c569  mov     rbx, [rsp+3C0h+arg_0]
0x18000c571  add     rsp, 390h
0x18000c578  pop     r15
0x18000c57a  pop     r14
0x18000c57c  pop     r13
0x18000c57e  pop     r12
0x18000c580  pop     rdi
0x18000c581  pop     rsi
0x18000c582  pop     rbp
0x18000c583  retn
0x18000c585  mov     eax, cs:dword_180315328
0x18000c58b  mov     ecx, 1
0x18000c590  test    cl, al
0x18000c592  jz      loc_18000C7BD
0x18000c598  call    cs:__imp_GetCurrentThreadId
0x18000c59f  nop     dword ptr [rax+rax+00h]
0x18000c5a4  movzx   eax, al
0x18000c5a7  mov     dword ptr [rsp+3C0h+var_360], eax
0x18000c5ab  call    ?MsiGetCurrentThreadId@@YA?AUUniqueThreadID@@XZ; MsiGetCurrentThreadId(void)
0x18000c5b0  xorps   xmm0, xmm0
0x18000c5b3  movzx   esi, al
0x18000c5b6  lea     rcx, [rbp+2C0h+SystemTime]; lpSystemTime
0x18000c5ba  movups  xmmword ptr [rbp+2C0h+SystemTime.wYear], xmm0
0x18000c5be  call    cs:__imp_GetLocalTime
0x18000c5c5  nop     dword ptr [rax+rax+00h]
0x18000c5ca  movups  xmm0, xmmword ptr cs:aMsiS; "MSI (s)"
0x18000c5d1  mov     ecx, cs:?g_scServerContext@@3W4scEnum@@A; scEnum g_scServerContext
0x18000c5d7  xor     edx, edx
0x18000c5d9  mov     r10d, edx
0x18000c5dc  movups  xmm1, xmmword ptr cs:aMsiA; "MSI (a)"
0x18000c5e3  movdqu  [rbp+2C0h+var_B8], xmm0
0x18000c5eb  movups  xmm0, xmmword ptr cs:aMsiC; "MSI (c)"
0x18000c5f2  movdqu  [rbp+2C0h+var_C8], xmm1
0x18000c5fa  movdqu  [rbp+2C0h+var_A8], xmm0
0x18000c602  test    ecx, ecx
0x18000c604  jz      loc_18000C7DF
0x18000c60a  sub     ecx, 1
0x18000c60d  jnz     loc_18000C780
0x18000c613  lea     r10, [rbp+2C0h+var_B8]
0x18000c61a  movzx   eax, [rbp+2C0h+SystemTime.wMilliseconds]
0x18000c61e  mov     r9d, 3Ah ; ':'
0x18000c624  movzx   ecx, [rbp+2C0h+SystemTime.wSecond]
0x18000c628  movzx   edx, [rbp+2C0h+SystemTime.wMinute]
0x18000c62c  movzx   r8d, [rbp+2C0h+SystemTime.wHour]
0x18000c631  cmp     dword ptr [rsp+3C0h+var_360], esi
0x18000c635  lea     r11d, [r9-19h]
0x18000c639  mov     [rsp+3C0h+var_370], eax
0x18000c63d  mov     eax, cs:dword_18031532C
0x18000c643  cmovnz  r9d, r11d
0x18000c647  mov     dword ptr [rsp+3C0h+var_378], ecx
0x18000c64b  lea     rcx, [rbp+2C0h+var_90]; unsigned __int16 *
0x18000c652  mov     [rsp+3C0h+var_380], edx
0x18000c656  mov     edx, r11d; unsigned __int64
0x18000c659  mov     dword ptr [rsp+3C0h+var_388], r8d
0x18000c65e  lea     r8, aS2xC2x02u02u02_0; "%s (%.2X%c%.2X) [%02u:%02u:%02u:%03u]: "
0x18000c665  mov     dword ptr [rsp+3C0h+Arguments], esi
0x18000c669  mov     [rsp+3C0h+nSize], r9d
0x18000c66e  mov     r9, r10
0x18000c671  mov     dword ptr [rsp+3C0h+lpBuffer], eax
0x18000c675  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c67a  test    eax, eax
0x18000c67c  js      loc_18000C55A
0x18000c682  mov     esi, r14d
0x18000c685  mov     [rbp+2C0h+var_308], 100h
0x18000c68c  lea     rax, [rbp+2C0h+var_300]
0x18000c690  mov     [rbp+2C0h+hMem], rax
0x18000c694  and     esi, 10h
0x18000c697  jnz     loc_18000C7EB
0x18000c69d  mov     rax, [rbp+2C0h+var_340]
0x18000c6a1  lea     rcx, [rbp+2C0h+var_2C0]; unsigned __int16 *
0x18000c6a5  mov     qword ptr [rsp+3C0h+var_380], rbx
0x18000c6aa  mov     r9, r13
0x18000c6ad  mov     [rsp+3C0h+var_388], rax
0x18000c6b2  mov     r8, r12; unsigned __int16 *
0x18000c6b5  mov     rax, [rbp+2C0h+var_338]
0x18000c6b9  mov     edx, 0E0h; unsigned __int64
0x18000c6be  mov     [rsp+3C0h+Arguments], rax
0x18000c6c3  mov     qword ptr [rsp+3C0h+nSize], r15
0x18000c6c8  mov     [rsp+3C0h+lpBuffer], rdi
0x18000c6cd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c6d2  cmp     eax, 8007007Ah
0x18000c6d7  jz      loc_18000C955
0x18000c6dd  mov     rcx, [rbp+2C0h+hMem]
0x18000c6e1  test    rcx, rcx
0x18000c6e4  jz      loc_18000C7AE
0x18000c6ea  cmp     [rbp+2C0h+var_308], 20h ; ' '
0x18000c6ee  jl      loc_18000C7AE
0x18000c6f4  movaps  xmm0, xmmword ptr [rbp+2C0h+var_90]
0x18000c6fb  mov     ebx, cs:?g_dmDiagnosticMode@@3HA; int g_dmDiagnosticMode
0x18000c701  mov     eax, ebx
0x18000c703  movups  xmmword ptr [rcx], xmm0
0x18000c706  and     eax, r14d
0x18000c709  movaps  xmm1, [rbp+2C0h+var_80]
0x18000c710  movups  xmmword ptr [rcx+10h], xmm1
0x18000c714  movaps  xmm0, [rbp+2C0h+var_70]
0x18000c71b  movups  xmmword ptr [rcx+20h], xmm0
0x18000c71f  movaps  xmm1, [rbp+2C0h+var_60]
0x18000c726  movups  xmmword ptr [rcx+30h], xmm1
0x18000c72a  test    al, 3
0x18000c72c  jnz     loc_18000C9C0
0x18000c732  mov     eax, ebx
0x18000c734  and     eax, r14d
0x18000c737  test    al, 0Ch
0x18000c739  jnz     short loc_18000C765
0x18000c73b  test    esi, esi
0x18000c73d  jnz     loc_18000C9EE
0x18000c743  cmp     [rbp+2C0h+var_308], 100h
0x18000c74a  jle     loc_18000C55A
0x18000c750  mov     rcx, [rbp+2C0h+hMem]; hMem
0x18000c754  call    cs:__imp_GlobalFree
0x18000c75b  nop     dword ptr [rax+rax+00h]
0x18000c760  jmp     loc_18000C55A
0x18000c765  mov     rcx, [rbp+2C0h+hMem]; Src
0x18000c769  mov     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x18000c773  call    ?WriteLog@@YA_NPEBG@Z; WriteLog(ushort const *)
0x18000c778  mov     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x18000c77e  jmp     short loc_18000C73B
0x18000c780  sub     ecx, 1
0x18000c783  jz      loc_18000C613
0x18000c789  cmp     ecx, 1
0x18000c78c  jnz     loc_18000C61A
0x18000c792  lea     r10, [rbp+2C0h+var_C8]
0x18000c799  jmp     loc_18000C61A
0x18000c79e  call    ?SetDiagnosticMode@@YAXXZ; SetDiagnosticMode(void)
0x18000c7a3  mov     eax, cs:?g_dmDiagnosticMode@@3HA; int g_dmDiagnosticMode
0x18000c7a9  jmp     loc_18000C552
0x18000c7ae  cmp     [rbp+2C0h+var_308], 100h
0x18000c7b5  jle     loc_18000C55A
0x18000c7bb  jmp     short loc_18000C754
0x18000c7bd  or      eax, ecx
0x18000c7bf  mov     cs:dword_180315328, eax
0x18000c7c5  call    cs:__imp_GetCurrentProcessId
0x18000c7cc  nop     dword ptr [rax+rax+00h]
0x18000c7d1  movzx   ecx, al
0x18000c7d4  mov     cs:dword_18031532C, ecx
0x18000c7da  jmp     loc_18000C598
0x18000c7df  lea     r10, [rbp+2C0h+var_A8]
0x18000c7e6  jmp     loc_18000C61A
0x18000c7eb  mov     rax, [rbp+2C0h+var_338]
0x18000c7ef  mov     [rbp+2C0h+var_E0], rax
0x18000c7f6  mov     rax, [rbp+2C0h+var_340]
0x18000c7fa  mov     [rbp+2C0h+var_D8], rax
0x18000c801  movzx   eax, word ptr cs:dword_180310E5C
0x18000c808  mov     [rbp+2C0h+var_E8], r15
0x18000c80f  xor     r15d, r15d
0x18000c812  mov     ecx, r15d
0x18000c815  mov     [rbp+2C0h+var_F0], rdi
0x18000c81c  test    ax, ax
0x18000c81f  mov     [rbp+2C0h+var_100], r12
0x18000c826  mov     [rbp+2C0h+var_F8], r13
0x18000c82d  mov     dil, r15b
0x18000c830  setz    cl
0x18000c833  mov     [rbp+2C0h+var_D0], rbx
0x18000c83a  mov     [rbp+2C0h+var_330], ecx
0x18000c83d  mov     [rsp+3C0h+var_360], ax
0x18000c842  lea     rdx, [rsp+3C0h+var_360]; unsigned __int16 *
0x18000c847  lea     rcx, [rbp+2C0h+var_330]; unsigned int *
0x18000c84b  call    ?MsiSwitchLanguage@@YA_NAEAIAEAG@Z; MsiSwitchLanguage(uint &,ushort &)
0x18000c850  test    al, al
0x18000c852  jz      loc_18000C94A
0x18000c858  movzx   ecx, [rsp+3C0h+var_360]; unsigned __int16
0x18000c85d  call    ?GetMsgDll@@YAPEAUHINSTANCE__@@G@Z; GetMsgDll(ushort)
0x18000c862  mov     rbx, rax
0x18000c865  test    rax, rax
0x18000c868  jz      loc_18000C93B
0x18000c86e  mov     edx, [rbp+2C0h+var_308]
0x18000c871  lea     rax, [rbp+2C0h+var_100]
0x18000c878  mov     rcx, [rbp+2C0h+hMem]
0x18000c87c  add     edx, 0FFFFFFE0h
0x18000c87f  movzx   r15d, [rsp+3C0h+var_360]
0x18000c885  add     rcx, 40h ; '@'
0x18000c889  mov     r8d, [rsp+3C0h+dwMessageId]; dwMessageId
0x18000c88e  mov     r9d, r15d; dwLanguageId
0x18000c891  mov     [rsp+3C0h+Arguments], rax; Arguments
0x18000c896  mov     [rsp+3C0h+nSize], edx; nSize
0x18000c89a  mov     rdx, rbx; lpSource
0x18000c89d  mov     [rsp+3C0h+lpBuffer], rcx; lpBuffer
0x18000c8a2  mov     ecx, 2800h; dwFlags
0x18000c8a7  call    cs:__imp_FormatMessageW
0x18000c8ae  nop     dword ptr [rax+rax+00h]
0x18000c8b3  test    eax, eax
0x18000c8b5  jnz     loc_18000C93B
0x18000c8bb  call    cs:__imp_GetLastError
0x18000c8c2  nop     dword ptr [rax+rax+00h]
0x18000c8c7  cmp     eax, 7Ah ; 'z'
0x18000c8ca  jnz     short loc_18000C92F
0x18000c8cc  mov     edx, 44Ch
0x18000c8d1  lea     rcx, [rbp+2C0h+hMem]
0x18000c8d5  call    ?SetSize@?$CAPITempBuffer@G$0BAA@@@QEAA_NH_N@Z; CAPITempBuffer<ushort,256>::SetSize(int,bool)
0x18000c8da  test    al, al
0x18000c8dc  jz      short loc_18000C92F
0x18000c8de  mov     ecx, [rbp+2C0h+var_308]
0x18000c8e1  lea     rdx, [rbp+2C0h+var_100]
0x18000c8e8  mov     rax, [rbp+2C0h+hMem]
0x18000c8ec  add     ecx, 0FFFFFFE0h
0x18000c8ef  mov     r8d, [rsp+3C0h+dwMessageId]; dwMessageId
0x18000c8f4  add     rax, 40h ; '@'
0x18000c8f8  mov     [rsp+3C0h+Arguments], rdx; Arguments
0x18000c8fd  mov     r9d, r15d; dwLanguageId
0x18000c900  mov     [rsp+3C0h+nSize], ecx; nSize
0x18000c904  mov     rdx, rbx; lpSource
0x18000c907  mov     ecx, 2800h; dwFlags
0x18000c90c  mov     [rsp+3C0h+lpBuffer], rax; lpBuffer
0x18000c911  call    cs:__imp_FormatMessageW
0x18000c918  nop     dword ptr [rax+rax+00h]
0x18000c91d  xor     r15d, r15d
0x18000c920  movzx   edi, dil
0x18000c924  test    eax, eax
0x18000c926  lea     eax, [r15+1]
0x18000c92a  cmovnz  edi, eax
0x18000c92d  jmp     short loc_18000C932
0x18000c92f  xor     r15d, r15d
0x18000c932  test    dil, dil
0x18000c935  jz      loc_18000C842
0x18000c93b  mov     r15, [rsp+3C0h+var_348]
0x18000c940  mov     rdi, [rsp+3C0h+var_350]
0x18000c945  jmp     loc_18000C6DD
0x18000c94a  mov     rax, [rbp+2C0h+hMem]
0x18000c94e  mov     [rax+40h], r15w
0x18000c953  jmp     short loc_18000C93B
0x18000c955  mov     edx, 44Ch
0x18000c95a  lea     rcx, [rbp+2C0h+hMem]
0x18000c95e  call    ?SetSize@?$CAPITempBuffer@G$0BAA@@@QEAA_NH_N@Z; CAPITempBuffer<ushort,256>::SetSize(int,bool)
0x18000c963  test    al, al
0x18000c965  jz      loc_18000C6DD
0x18000c96b  mov     eax, [rbp+2C0h+var_308]
0x18000c96e  mov     r9, r13
0x18000c971  mov     rcx, [rbp+2C0h+hMem]
0x18000c975  add     eax, 0FFFFFFE0h
0x18000c978  mov     qword ptr [rsp+3C0h+var_380], rbx
0x18000c97d  add     rcx, 40h ; '@'; unsigned __int16 *
0x18000c981  movsxd  rdx, eax; unsigned __int64
0x18000c984  mov     r8, r12; unsigned __int16 *
0x18000c987  mov     rax, [rbp+2C0h+var_340]
0x18000c98b  mov     [rsp+3C0h+var_388], rax
0x18000c990  mov     rax, [rbp+2C0h+var_338]
0x18000c994  mov     [rsp+3C0h+Arguments], rax
0x18000c999  mov     qword ptr [rsp+3C0h+nSize], r15
0x18000c99e  mov     [rsp+3C0h+lpBuffer], rdi
0x18000c9a3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c9a8  test    eax, eax
0x18000c9aa  jns     loc_18000C6DD
0x18000c9b0  cmp     eax, 8007007Ah
0x18000c9b5  jz      loc_18000C6DD
0x18000c9bb  jmp     loc_18000C743
0x18000c9c0  mov     rcx, [rbp+2C0h+hMem]; lpOutputString
0x18000c9c4  call    cs:__imp_OutputDebugStringW
0x18000c9cb  nop     dword ptr [rax+rax+00h]
0x18000c9d0  lea     rcx, OutputString; "\r\n"
0x18000c9d7  call    cs:__imp_OutputDebugStringW
0x18000c9de  nop     dword ptr [rax+rax+00h]
0x18000c9e3  mov     ebx, cs:?g_dmDiagnosticMode@@3HA; int g_dmDiagnosticMode
0x18000c9e9  jmp     loc_18000C732
0x18000c9ee  mov     rax, [rbp+2C0h+var_328]
0x18000c9f2  mov     r9, r13; unsigned __int16 *
0x18000c9f5  mov     edx, [rsp+3C0h+dwMessageId]; int
0x18000c9f9  mov     r8, r12; unsigned __int16 *
0x18000c9fc  movzx   ecx, [rsp+3C0h+var_35C]; unsigned __int16
0x18000ca01  mov     [rsp+3C0h+var_378], rax; void *
0x18000ca06  mov     eax, [rbp+2C0h+arg_50]
0x18000ca0c  mov     [rsp+3C0h+var_380], eax; unsigned int
0x18000ca10  mov     rax, [rbp+2C0h+var_340]
  ... truncated ...
```
