# DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)

- ea: `0x180027634`
- end: `0x180027e27`
- name: `?DebugString@@YAXHGHPEBD000000KPEAX@Z`
- size: `2035`
- prototype: `void(int, unsigned __int16, int, const char *, const char *, const char *, const char *, const char *, const char *, const char *, unsigned int, void *)`
- caller_count: `174`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180007c44`
- `0x18000879c`
- `0x180008d90`
- `0x180009268`
- `0x18000b8bc`
- `0x1800202e4`
- `0x180021a48`
- `0x180024520`
- `0x180024af0`
- `0x180025340`
- `0x180025550`
- `0x180025df0`
- `0x180026240`
- `0x180026560`
- `0x1800266d0`
- `0x180026ac0`
- `0x180026ea0`
- `0x180027e30`
- `0x180028f50`
- `0x18002959c`
- `0x18002c468`
- `0x18002f750`
- `0x180049cf0`
- `0x18004e85c`
- `0x180050204`
- `0x180054a10`
- `0x180054ca0`
- `0x180092930`
- `0x18009d8e0`
- `0x1800a7b14`
- `0x1800aaffc`
- `0x1800b198c`
- `0x1800b3dc8`
- `0x1800b4aac`
- `0x1800b74c0`
- `0x1800b7d84`
- `0x1800b9440`
- `0x1800b96c0`
- `0x1800b988c`
- `0x1800ba900`
- `0x1800c1a30`
- `0x1800c7394`
- `0x1800c7558`
- `0x1800c77f0`
- `0x1800cc6f0`
- `0x1800e3d54`
- `0x1801046a0`
- `0x1801140d0`
- `0x180115c90`
- `0x18012eaa0`

## callees

- `0x180014288`
- `0x180020620`
- `0x180027634`
- `0x1800433c0`
- `0x18004a014`
- `0x180087d44`
- `0x1800a5e58`
- `0x1800b6700`
- `0x1800d1eb8`
- `0x1800d20e8`
- `0x18014b2d8`
- `0x18015b080`
- `0x180265240`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180027703`
- `KERNEL32!GetCurrentThreadId` at `0x180027703`
- `KERNEL32!FormatMessageW` at `0x180027af6`
- `KERNEL32!FormatMessageW` at `0x180027b5c`
- `KERNEL32!FormatMessageW` at `0x180027af6`
- `KERNEL32!FormatMessageW` at `0x180027b5c`
- `KERNEL32!GetLastError` at `0x180027b06`
- `KERNEL32!GetLastError` at `0x180027b06`
- `KERNEL32!OutputDebugStringA` at `0x180027c3e`
- `KERNEL32!OutputDebugStringA` at `0x180027c51`
- `KERNEL32!OutputDebugStringA` at `0x180027c3e`
- `KERNEL32!OutputDebugStringA` at `0x180027c51`
- `KERNEL32!WideCharToMultiByte` at `0x180027bbe`
- `KERNEL32!WideCharToMultiByte` at `0x180027bbe`
- `KERNEL32!GlobalFree` at `0x18002785d`
- `KERNEL32!GlobalFree` at `0x180027897`
- `KERNEL32!GlobalFree` at `0x1800278d5`
- `KERNEL32!GlobalFree` at `0x180027913`
- `KERNEL32!GlobalFree` at `0x180027952`
- `KERNEL32!GlobalFree` at `0x180027995`
- `KERNEL32!GlobalFree` at `0x1800279da`
- `KERNEL32!GlobalFree` at `0x180027cb8`
- `KERNEL32!GlobalFree` at `0x180027df0`
- `KERNEL32!GlobalFree` at `0x18002785d`
- `KERNEL32!GlobalFree` at `0x180027897`
- `KERNEL32!GlobalFree` at `0x1800278d5`
- `KERNEL32!GlobalFree` at `0x180027913`
- `KERNEL32!GlobalFree` at `0x180027952`
- `KERNEL32!GlobalFree` at `0x180027995`
- `KERNEL32!GlobalFree` at `0x1800279da`
- `KERNEL32!GlobalFree` at `0x180027cb8`
- `KERNEL32!GlobalFree` at `0x180027df0`
- `KERNEL32!GetCurrentProcessId` at `0x1800276ee`
- `KERNEL32!GetCurrentProcessId` at `0x1800276ee`
- `KERNEL32!GetLocalTime` at `0x180027725`
- `KERNEL32!GetLocalTime` at `0x180027725`

## pseudocode

```c
void __fastcall DebugString(
        int a1,
        unsigned __int16 a2,
        DWORD a3,
        const char *a4,
        const char *a5,
        const char *a6,
        const char *a7,
        const char *a8,
        const char *a9,
        const char *a10)
{
  const char *v10; // r14
  int v11; // r15d
  int v12; // esi
  const char *v13; // r12
  int v14; // eax
  int CurrentThreadId; // edi
  int v16; // ebx
  __int64 *v17; // r10
  int v18; // r9d
  int v19; // edi
  va_list v20; // r12
  va_list v21; // r15
  va_list v22; // r14
  va_list v23; // rsi
  va_list v24; // rdi
  va_list v25; // rbx
  bool v26; // cc
  CHAR *v27; // rcx
  DWORD v28; // r14d
  char v29; // bl
  HINSTANCE MsgDll; // rdi
  DWORD v31; // esi
  __int64 v32; // r13
  int v33; // ebx
  char v34; // al
  const unsigned __int16 *v35; // rax
  int v36; // eax
  unsigned __int16 v37[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v38; // [rsp+64h] [rbp-9Ch]
  const char *v39; // [rsp+68h] [rbp-98h]
  DWORD dwMessageId; // [rsp+70h] [rbp-90h]
  const char *v41; // [rsp+78h] [rbp-88h]
  unsigned int v42[2]; // [rsp+80h] [rbp-80h] BYREF
  int v43; // [rsp+88h] [rbp-78h]
  int v44; // [rsp+8Ch] [rbp-74h]
  const char *v45; // [rsp+90h] [rbp-70h]
  const char *v46; // [rsp+98h] [rbp-68h]
  const char *v47; // [rsp+A0h] [rbp-60h]
  const char *v48; // [rsp+A8h] [rbp-58h]
  LPWSTR lpBuffer; // [rsp+B0h] [rbp-50h] BYREF
  DWORD nSize; // [rsp+B8h] [rbp-48h]
  char v51; // [rsp+C0h] [rbp-40h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+C8h] [rbp-38h] BYREF
  HGLOBAL hMem; // [rsp+E0h] [rbp-20h] BYREF
  int v54; // [rsp+E8h] [rbp-18h]
  _BYTE v55[512]; // [rsp+F0h] [rbp-10h] BYREF
  LPCSTR v56; // [rsp+2F0h] [rbp+1F0h]
  __int64 v57; // [rsp+2F8h] [rbp+1F8h]
  LPCSTR lpOutputString; // [rsp+300h] [rbp+200h] BYREF
  int v59; // [rsp+308h] [rbp+208h]
  char v60; // [rsp+310h] [rbp+210h] BYREF
  char v61[224]; // [rsp+330h] [rbp+230h] BYREF
  va_list Arguments[7]; // [rsp+410h] [rbp+310h] BYREF
  __int64 v63; // [rsp+448h] [rbp+348h] BYREF
  __int64 v64; // [rsp+450h] [rbp+350h] BYREF
  __int64 v65; // [rsp+458h] [rbp+358h] BYREF
  char v66[16]; // [rsp+460h] [rbp+360h] BYREF
  __int128 v67; // [rsp+470h] [rbp+370h]

  v10 = a4;
  v11 = (int)a5;
  v12 = a1;
  v13 = a6;
  v45 = a7;
  v39 = a8;
  v41 = a9;
  v14 = g_dmDiagnosticMode;
  v47 = a4;
  dwMessageId = a3;
  v38 = a2;
  v44 = a1;
  v48 = a5;
  v46 = a6;
  if ( g_dmDiagnosticMode == -1 )
  {
    SetDiagnosticMode();
    v14 = g_dmDiagnosticMode;
  }
  if ( ((v14 | 0x10) & v12) != 0 )
  {
    if ( (dword_180315320 & 1) == 0 )
    {
      dword_180315320 |= 1u;
      dword_180315324 = (unsigned __int8)GetCurrentProcessId();
    }
    CurrentThreadId = (unsigned __int8)GetCurrentThreadId();
    v16 = (unsigned __int8)MsiGetCurrentThreadId();
    SystemTime = 0;
    GetLocalTime(&SystemTime);
    v64 = 0x2973282049534DLL;
    v17 = 0;
    v63 = 0x2961282049534DLL;
    v65 = 0x2963282049534DLL;
    if ( g_scServerContext )
    {
      if ( g_scServerContext == 1 || g_scServerContext == 2 )
      {
        v17 = &v64;
      }
      else if ( g_scServerContext == 3 )
      {
        v17 = &v63;
      }
    }
    else
    {
      v17 = &v65;
    }
    v18 = 58;
    if ( CurrentThreadId != v16 )
      v18 = 33;
    if ( (int)StringCchPrintfA(
                v66,
                0x21u,
                "%s (%.2X%c%.2X) [%02u:%02u:%02u:%03u]: ",
                (const char *)v17,
                dword_180315324,
                v18,
                v16,
                SystemTime.wHour,
                SystemTime.wMinute,
                SystemTime.wSecond,
                SystemTime.wMilliseconds) >= 0 )
    {
      v59 = 256;
      v19 = v12 & 0x10;
      v43 = v19;
      lpOutputString = &v60;
      if ( (v12 & 0x10) != 0 )
      {
        v57 = 0;
        hMem = v55;
        v54 = 256;
        v56 = v10;
        *(_QWORD *)v42 = CApiConvertString::operator unsigned short const *(&hMem);
        if ( v54 > 256 )
          GlobalFree(hMem);
        v54 = 256;
        hMem = v55;
        v57 = 0;
        v56 = a5;
        v20 = (va_list)CApiConvertString::operator unsigned short const *(&hMem);
        if ( v54 > 256 )
          GlobalFree(hMem);
        v54 = 256;
        hMem = v55;
        v56 = v46;
        v57 = 0;
        v21 = (va_list)CApiConvertString::operator unsigned short const *(&hMem);
        if ( v54 > 256 )
          GlobalFree(hMem);
        v54 = 256;
        hMem = v55;
        v56 = v45;
        v57 = 0;
        v22 = (va_list)CApiConvertString::operator unsigned short const *(&hMem);
        if ( v54 > 256 )
          GlobalFree(hMem);
        v54 = 256;
        hMem = v55;
        v56 = v39;
        v57 = 0;
        v23 = (va_list)CApiConvertString::operator unsigned short const *(&hMem);
        if ( v54 > 256 )
          GlobalFree(hMem);
        v54 = 256;
        hMem = v55;
        v56 = v41;
        v57 = 0;
        v24 = (va_list)CApiConvertString::operator unsigned short const *(&hMem);
        if ( v54 > 256 )
          GlobalFree(hMem);
        v54 = 256;
        hMem = v55;
        v57 = 0;
        v56 = a10;
        v25 = (va_list)CApiConvertString::operator unsigned short const *(&hMem);
        if ( v54 > 256 )
          GlobalFree(hMem);
        Arguments[0] = *(va_list *)v42;
        Arguments[1] = v20;
        lpBuffer = (LPWSTR)&v51;
        Arguments[2] = v21;
        Arguments[3] = v22;
        Arguments[4] = v23;
        Arguments[5] = v24;
        Arguments[6] = v25;
        nSize = 1;
        if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&lpBuffer, 261, 0) )
        {
LABEL_32:
          CAPITempBuffer<unsigned short,1>::Destroy(&lpBuffer);
          v26 = v59 <= 256;
          goto LABEL_33;
        }
        v28 = dwMessageId;
        v29 = 0;
        v37[0] = dword_180310E5C;
        v42[0] = (_WORD)dword_180310E5C == 0;
        while ( !v29 )
        {
          if ( MsiSwitchLanguage(v42, v37) )
          {
            MsgDll = GetMsgDll(v37[0]);
            if ( !MsgDll
              || (v31 = v37[0], FormatMessageW(0x2800u, MsgDll, v28, v37[0], lpBuffer, nSize, Arguments))
              || GetLastError() == 122
              && (unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&lpBuffer, 1100, 0)
              && FormatMessageW(0x2800u, MsgDll, v28, v31, lpBuffer, nSize, Arguments) )
            {
              v29 = 1;
              if ( !(unsigned __int8)CAPITempBuffer<char,256>::SetSize(&lpOutputString, 1100)
                || !WideCharToMultiByte(0, 0, lpBuffer, -1, (LPSTR)lpOutputString + 32, v59 - 32, 0, 0) )
              {
                goto LABEL_32;
              }
            }
          }
          else
          {
            v29 = 1;
            *((_BYTE *)lpOutputString + 32) = 0;
          }
        }
        CAPITempBuffer<unsigned short,1>::Destroy(&lpBuffer);
        v19 = v43;
        LOBYTE(v12) = v44;
        LODWORD(v10) = (_DWORD)v47;
        v11 = (int)v48;
        v13 = v46;
      }
      else if ( (unsigned int)StringCchPrintfA(v61, 0xE0u, v10, a5, a6, v45, v39, v41, a10) == -2147024774
             && (unsigned __int8)CAPITempBuffer<char,256>::SetSize(&lpOutputString, 1100) )
      {
        v32 = (__int64)v39;
        v36 = StringCchPrintfA((char *)lpOutputString + 32, v59 - 32, v10, a5, a6, v45, v39, v41, a10);
        if ( v36 < 0 && v36 != -2147024774 )
        {
          v26 = v59 <= 256;
          goto LABEL_33;
        }
        goto LABEL_49;
      }
      v32 = (__int64)v39;
LABEL_49:
      v27 = (CHAR *)lpOutputString;
      if ( !lpOutputString || v59 < 32 )
      {
        if ( v59 <= 256 )
          return;
        goto LABEL_66;
      }
      v33 = g_dmDiagnosticMode;
      v34 = v12 & g_dmDiagnosticMode;
      *(_OWORD *)lpOutputString = *(_OWORD *)v66;
      *((_OWORD *)v27 + 1) = v67;
      if ( (v34 & 3) != 0 )
      {
        OutputDebugStringA(lpOutputString);
        OutputDebugStringA("\r\n");
        v33 = g_dmDiagnosticMode;
      }
      if ( ((unsigned __int8)v12 & (unsigned __int8)v33 & 0xC) != 0 )
      {
        g_dmDiagnosticMode = 0;
        hMem = v55;
        v56 = lpOutputString;
        v54 = 256;
        v57 = 0;
        v35 = (const unsigned __int16 *)CApiConvertString::operator unsigned short const *(&hMem);
        WriteLog(v35);
        if ( v54 > 256 )
          GlobalFree(hMem);
        g_dmDiagnosticMode = v33;
      }
      if ( v19 )
        ReportToEventLogA(v38, dwMessageId, (_DWORD)v10, v11, (__int64)v13, (__int64)v45, v32, (__int64)v41, 0, 0);
      v26 = v59 <= 256;
LABEL_33:
      if ( v26 )
        return;
      v27 = (CHAR *)lpOutputString;
LABEL_66:
      GlobalFree(v27);
    }
  }
}

```

## disassembly

```asm
0x180027634  mov     [rsp-8+arg_0], rbx
0x180027639  push    rbp
0x18002763a  push    rsi
0x18002763b  push    rdi
0x18002763c  push    r12
0x18002763e  push    r13
0x180027640  push    r14
0x180027642  push    r15
0x180027644  lea     rbp, [rsp-390h]
0x18002764c  sub     rsp, 490h
0x180027653  mov     rax, cs:__security_cookie
0x18002765a  xor     rax, rsp
0x18002765d  mov     [rbp+3C0h+var_38], rax
0x180027664  mov     rax, [rbp+3C0h+arg_30]
0x18002766b  mov     r14, r9
0x18002766e  mov     r15, [rbp+3C0h+arg_20]
0x180027675  mov     esi, ecx
0x180027677  mov     r12, [rbp+3C0h+arg_28]
0x18002767e  mov     r13, [rbp+3C0h+arg_48]
0x180027685  mov     [rbp+3C0h+var_430], rax
0x180027689  mov     rax, [rbp+3C0h+arg_38]
0x180027690  mov     [rsp+4C0h+var_458], rax
0x180027695  mov     rax, [rbp+3C0h+arg_40]
0x18002769c  mov     [rsp+4C0h+var_448], rax
0x1800276a1  mov     eax, cs:?g_dmDiagnosticMode@@3HA; int g_dmDiagnosticMode
0x1800276a7  mov     [rbp+3C0h+var_420], r9
0x1800276ab  mov     [rsp+4C0h+dwMessageId], r8d
0x1800276b0  mov     [rsp+4C0h+var_45C], dx
0x1800276b5  mov     [rbp+3C0h+var_434], ecx
0x1800276b8  mov     [rbp+3C0h+var_418], r15
0x1800276bc  mov     [rbp+3C0h+var_428], r12
0x1800276c0  cmp     eax, 0FFFFFFFFh
0x1800276c3  jnz     short loc_1800276D0
0x1800276c5  call    ?SetDiagnosticMode@@YAXXZ; SetDiagnosticMode(void)
0x1800276ca  mov     eax, cs:?g_dmDiagnosticMode@@3HA; int g_dmDiagnosticMode
0x1800276d0  or      eax, 10h
0x1800276d3  test    esi, eax
0x1800276d5  jz      loc_180027DFC
0x1800276db  mov     eax, cs:dword_180315320
0x1800276e1  test    al, 1
0x1800276e3  jnz     short loc_180027703
0x1800276e5  or      eax, 1
0x1800276e8  mov     cs:dword_180315320, eax
0x1800276ee  call    cs:__imp_GetCurrentProcessId
0x1800276f5  nop     dword ptr [rax+rax+00h]
0x1800276fa  movzx   ecx, al
0x1800276fd  mov     cs:dword_180315324, ecx
0x180027703  call    cs:__imp_GetCurrentThreadId
0x18002770a  nop     dword ptr [rax+rax+00h]
0x18002770f  movzx   edi, al
0x180027712  call    ?MsiGetCurrentThreadId@@YA?AUUniqueThreadID@@XZ; MsiGetCurrentThreadId(void)
0x180027717  xorps   xmm0, xmm0
0x18002771a  movzx   ebx, al
0x18002771d  lea     rcx, [rbp+3C0h+SystemTime]; lpSystemTime
0x180027721  movups  xmmword ptr [rbp+3C0h+SystemTime.wYear], xmm0
0x180027725  call    cs:__imp_GetLocalTime
0x18002772c  nop     dword ptr [rax+rax+00h]
0x180027731  mov     ecx, cs:?g_scServerContext@@3W4scEnum@@A; scEnum g_scServerContext
0x180027737  mov     rax, 2973282049534Dh
0x180027741  mov     [rbp+3C0h+var_70], rax
0x180027748  xor     edx, edx
0x18002774a  mov     rax, 2961282049534Dh
0x180027754  mov     r10d, edx
0x180027757  mov     [rbp+3C0h+var_78], rax
0x18002775e  mov     rax, 2963282049534Dh
0x180027768  mov     [rbp+3C0h+var_68], rax
0x18002776f  test    ecx, ecx
0x180027771  jz      short loc_180027794
0x180027773  sub     ecx, 1
0x180027776  jz      short loc_18002778B
0x180027778  sub     ecx, 1
0x18002777b  jz      short loc_18002778B
0x18002777d  cmp     ecx, 1
0x180027780  jnz     short loc_18002779B
0x180027782  lea     r10, [rbp+3C0h+var_78]
0x180027789  jmp     short loc_18002779B
0x18002778b  lea     r10, [rbp+3C0h+var_70]
0x180027792  jmp     short loc_18002779B
0x180027794  lea     r10, [rbp+3C0h+var_68]
0x18002779b  movzx   eax, [rbp+3C0h+SystemTime.wMilliseconds]
0x18002779f  mov     r9d, 3Ah ; ':'
0x1800277a5  movzx   ecx, [rbp+3C0h+SystemTime.wSecond]
0x1800277a9  cmp     edi, ebx
0x1800277ab  movzx   edx, [rbp+3C0h+SystemTime.wMinute]
0x1800277af  movzx   r8d, [rbp+3C0h+SystemTime.wHour]
0x1800277b4  mov     [rsp+4C0h+var_470], eax
0x1800277b8  lea     r11d, [r9-19h]
0x1800277bc  mov     eax, cs:dword_180315324
0x1800277c2  cmovnz  r9d, r11d
0x1800277c6  mov     dword ptr [rsp+4C0h+var_478], ecx
0x1800277ca  lea     rcx, [rbp+3C0h+var_60]; char *
0x1800277d1  mov     dword ptr [rsp+4C0h+var_480], edx
0x1800277d5  mov     edx, r11d; unsigned __int64
0x1800277d8  mov     dword ptr [rsp+4C0h+lpUsedDefaultChar], r8d
0x1800277dd  lea     r8, aS2xC2x02u02u02; "%s (%.2X%c%.2X) [%02u:%02u:%02u:%03u]: "
0x1800277e4  mov     dword ptr [rsp+4C0h+Arguments], ebx
0x1800277e8  mov     [rsp+4C0h+nSize], r9d
0x1800277ed  mov     r9, r10
0x1800277f0  mov     dword ptr [rsp+4C0h+lpBuffer], eax
0x1800277f4  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800277f9  xor     ebx, ebx
0x1800277fb  test    eax, eax
0x1800277fd  js      loc_180027DFC
0x180027803  mov     edi, esi
0x180027805  mov     [rbp+3C0h+var_1B8], 100h
0x18002780f  and     edi, 10h
0x180027812  lea     rax, [rbp+3C0h+var_1B0]
0x180027819  mov     [rbp+3C0h+var_438], edi
0x18002781c  mov     [rbp+3C0h+lpOutputString], rax
0x180027823  jz      loc_180027D1B
0x180027829  lea     rax, [rbp+3C0h+var_3D0]
0x18002782d  mov     [rbp+3C0h+var_1C8], rbx
0x180027834  mov     edi, 100h
0x180027839  mov     [rbp+3C0h+hMem], rax
0x18002783d  lea     rcx, [rbp+3C0h+hMem]
0x180027841  mov     [rbp+3C0h+var_3D8], edi
0x180027844  mov     [rbp+3C0h+var_1D0], r14
0x18002784b  call    ??BCApiConvertString@@QEAAPEBGXZ; CApiConvertString::operator ushort const *(void)
0x180027850  mov     qword ptr [rbp+3C0h+var_440], rax
0x180027854  cmp     [rbp+3C0h+var_3D8], edi
0x180027857  jle     short loc_180027869
0x180027859  mov     rcx, [rbp+3C0h+hMem]; hMem
0x18002785d  call    cs:__imp_GlobalFree
0x180027864  nop     dword ptr [rax+rax+00h]
0x180027869  lea     rax, [rbp+3C0h+var_3D0]
0x18002786d  mov     [rbp+3C0h+var_3D8], edi
0x180027870  lea     rcx, [rbp+3C0h+hMem]
0x180027874  mov     [rbp+3C0h+hMem], rax
0x180027878  mov     [rbp+3C0h+var_1C8], rbx
0x18002787f  mov     [rbp+3C0h+var_1D0], r15
0x180027886  call    ??BCApiConvertString@@QEAAPEBGXZ; CApiConvertString::operator ushort const *(void)
0x18002788b  mov     r12, rax
0x18002788e  cmp     [rbp+3C0h+var_3D8], edi
0x180027891  jle     short loc_1800278A3
0x180027893  mov     rcx, [rbp+3C0h+hMem]; hMem
0x180027897  call    cs:__imp_GlobalFree
0x18002789e  nop     dword ptr [rax+rax+00h]
0x1800278a3  lea     rax, [rbp+3C0h+var_3D0]
0x1800278a7  mov     [rbp+3C0h+var_3D8], edi
0x1800278aa  mov     [rbp+3C0h+hMem], rax
0x1800278ae  lea     rcx, [rbp+3C0h+hMem]
0x1800278b2  mov     rax, [rbp+3C0h+var_428]
0x1800278b6  mov     [rbp+3C0h+var_1D0], rax
0x1800278bd  mov     [rbp+3C0h+var_1C8], rbx
0x1800278c4  call    ??BCApiConvertString@@QEAAPEBGXZ; CApiConvertString::operator ushort const *(void)
0x1800278c9  mov     r15, rax
0x1800278cc  cmp     [rbp+3C0h+var_3D8], edi
0x1800278cf  jle     short loc_1800278E1
0x1800278d1  mov     rcx, [rbp+3C0h+hMem]; hMem
0x1800278d5  call    cs:__imp_GlobalFree
0x1800278dc  nop     dword ptr [rax+rax+00h]
0x1800278e1  lea     rax, [rbp+3C0h+var_3D0]
0x1800278e5  mov     [rbp+3C0h+var_3D8], edi
0x1800278e8  mov     [rbp+3C0h+hMem], rax
0x1800278ec  lea     rcx, [rbp+3C0h+hMem]
0x1800278f0  mov     rax, [rbp+3C0h+var_430]
0x1800278f4  mov     [rbp+3C0h+var_1D0], rax
0x1800278fb  mov     [rbp+3C0h+var_1C8], rbx
0x180027902  call    ??BCApiConvertString@@QEAAPEBGXZ; CApiConvertString::operator ushort const *(void)
0x180027907  mov     r14, rax
0x18002790a  cmp     [rbp+3C0h+var_3D8], edi
0x18002790d  jle     short loc_18002791F
0x18002790f  mov     rcx, [rbp+3C0h+hMem]; hMem
0x180027913  call    cs:__imp_GlobalFree
0x18002791a  nop     dword ptr [rax+rax+00h]
0x18002791f  lea     rax, [rbp+3C0h+var_3D0]
0x180027923  mov     [rbp+3C0h+var_3D8], edi
0x180027926  mov     [rbp+3C0h+hMem], rax
0x18002792a  lea     rcx, [rbp+3C0h+hMem]
0x18002792e  mov     rax, [rsp+4C0h+var_458]
0x180027933  mov     [rbp+3C0h+var_1D0], rax
0x18002793a  mov     [rbp+3C0h+var_1C8], rbx
0x180027941  call    ??BCApiConvertString@@QEAAPEBGXZ; CApiConvertString::operator ushort const *(void)
0x180027946  mov     rsi, rax
0x180027949  cmp     [rbp+3C0h+var_3D8], edi
0x18002794c  jle     short loc_18002795E
0x18002794e  mov     rcx, [rbp+3C0h+hMem]; hMem
0x180027952  call    cs:__imp_GlobalFree
0x180027959  nop     dword ptr [rax+rax+00h]
0x18002795e  lea     rax, [rbp+3C0h+var_3D0]
0x180027962  mov     [rbp+3C0h+var_3D8], edi
0x180027965  mov     [rbp+3C0h+hMem], rax
0x180027969  lea     rcx, [rbp+3C0h+hMem]
0x18002796d  mov     rax, [rsp+4C0h+var_448]
0x180027972  mov     [rbp+3C0h+var_1D0], rax
0x180027979  mov     [rbp+3C0h+var_1C8], rbx
0x180027980  call    ??BCApiConvertString@@QEAAPEBGXZ; CApiConvertString::operator ushort const *(void)
0x180027985  cmp     [rbp+3C0h+var_3D8], 100h
0x18002798c  mov     rdi, rax
0x18002798f  jle     short loc_1800279A1
0x180027991  mov     rcx, [rbp+3C0h+hMem]; hMem
0x180027995  call    cs:__imp_GlobalFree
0x18002799c  nop     dword ptr [rax+rax+00h]
0x1800279a1  lea     rax, [rbp+3C0h+var_3D0]
0x1800279a5  mov     [rbp+3C0h+var_3D8], 100h
0x1800279ac  lea     rcx, [rbp+3C0h+hMem]
0x1800279b0  mov     [rbp+3C0h+hMem], rax
0x1800279b4  mov     [rbp+3C0h+var_1C8], rbx
0x1800279bb  mov     [rbp+3C0h+var_1D0], r13
0x1800279c2  call    ??BCApiConvertString@@QEAAPEBGXZ; CApiConvertString::operator ushort const *(void)
0x1800279c7  mov     r13d, 100h
0x1800279cd  mov     rbx, rax
0x1800279d0  cmp     [rbp+3C0h+var_3D8], r13d
0x1800279d4  jle     short loc_1800279E6
0x1800279d6  mov     rcx, [rbp+3C0h+hMem]; hMem
0x1800279da  call    cs:__imp_GlobalFree
0x1800279e1  nop     dword ptr [rax+rax+00h]
0x1800279e6  mov     rax, qword ptr [rbp+3C0h+var_440]
0x1800279ea  lea     rcx, [rbp+3C0h+var_410]
0x1800279ee  mov     [rbp+3C0h+var_B0], rax
0x1800279f5  xor     r8d, r8d
0x1800279f8  lea     rax, [rbp+3C0h+var_400]
0x1800279fc  mov     [rbp+3C0h+var_A8], r12
0x180027a03  mov     edx, 105h
0x180027a08  mov     [rbp+3C0h+var_410], rax
0x180027a0c  mov     [rbp+3C0h+var_A0], r15
0x180027a13  mov     [rbp+3C0h+var_98], r14
0x180027a1a  mov     [rbp+3C0h+var_90], rsi
0x180027a21  mov     [rbp+3C0h+var_88], rdi
0x180027a28  mov     [rbp+3C0h+var_80], rbx
0x180027a2f  mov     [rbp+3C0h+var_408], 1
0x180027a36  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x180027a3b  xor     r15d, r15d
0x180027a3e  test    al, al
0x180027a40  jnz     short loc_180027A64
0x180027a42  lea     rcx, [rbp+3C0h+var_410]
0x180027a46  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x180027a4b  cmp     [rbp+3C0h+var_1B8], r13d
0x180027a52  jle     loc_180027DFC
0x180027a58  mov     rcx, [rbp+3C0h+lpOutputString]
0x180027a5f  jmp     loc_180027DF0
0x180027a64  movzx   eax, word ptr cs:dword_180310E5C
0x180027a6b  mov     ecx, r15d
0x180027a6e  mov     r14d, [rsp+4C0h+dwMessageId]
0x180027a73  test    ax, ax
0x180027a76  mov     bl, r15b
0x180027a79  mov     [rsp+4C0h+var_460], ax
0x180027a7e  setz    cl
0x180027a81  mov     r12d, 2800h
0x180027a87  mov     [rbp+3C0h+var_440], ecx
0x180027a8a  test    bl, bl
0x180027a8c  jnz     loc_180027BD7
0x180027a92  lea     rdx, [rsp+4C0h+var_460]; unsigned __int16 *
0x180027a97  lea     rcx, [rbp+3C0h+var_440]; unsigned int *
0x180027a9b  call    ?MsiSwitchLanguage@@YA_NAEAIAEAG@Z; MsiSwitchLanguage(uint &,ushort &)
0x180027aa0  test    al, al
0x180027aa2  jnz     short loc_180027AB3
0x180027aa4  mov     rax, [rbp+3C0h+lpOutputString]
0x180027aab  mov     bl, 1
0x180027aad  mov     [rax+20h], r15b
0x180027ab1  jmp     short loc_180027A8A
0x180027ab3  movzx   ecx, [rsp+4C0h+var_460]; unsigned __int16
0x180027ab8  call    ?GetMsgDll@@YAPEAUHINSTANCE__@@G@Z; GetMsgDll(ushort)
0x180027abd  mov     rdi, rax
0x180027ac0  test    rax, rax
0x180027ac3  jz      loc_180027B70
0x180027ac9  mov     rdx, [rbp+3C0h+var_410]
0x180027acd  lea     rax, [rbp+3C0h+var_B0]
0x180027ad4  mov     ecx, [rbp+3C0h+var_408]
0x180027ad7  mov     r8d, r14d; dwMessageId
0x180027ada  movzx   esi, [rsp+4C0h+var_460]
0x180027adf  mov     [rsp+4C0h+Arguments], rax; Arguments
0x180027ae4  mov     r9d, esi; dwLanguageId
0x180027ae7  mov     [rsp+4C0h+nSize], ecx; nSize
0x180027aeb  mov     ecx, r12d; dwFlags
0x180027aee  mov     [rsp+4C0h+lpBuffer], rdx; lpBuffer
0x180027af3  mov     rdx, rdi; lpSource
0x180027af6  call    cs:__imp_FormatMessageW
0x180027afd  nop     dword ptr [rax+rax+00h]
0x180027b02  test    eax, eax
0x180027b04  jnz     short loc_180027B70
0x180027b06  call    cs:__imp_GetLastError
0x180027b0d  nop     dword ptr [rax+rax+00h]
0x180027b12  cmp     eax, 7Ah ; 'z'
0x180027b15  jnz     loc_180027A8A
0x180027b1b  xor     r8d, r8d
0x180027b1e  lea     rcx, [rbp+3C0h+var_410]
0x180027b22  mov     edx, 44Ch
0x180027b27  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x180027b2c  test    al, al
0x180027b2e  jz      loc_180027A8A
0x180027b34  mov     rcx, [rbp+3C0h+var_410]
0x180027b38  lea     rax, [rbp+3C0h+var_B0]
0x180027b3f  mov     [rsp+4C0h+Arguments], rax; Arguments
0x180027b44  mov     r9d, esi; dwLanguageId
0x180027b47  mov     eax, [rbp+3C0h+var_408]
0x180027b4a  mov     r8d, r14d; dwMessageId
0x180027b4d  mov     [rsp+4C0h+nSize], eax; nSize
0x180027b51  mov     rdx, rdi; lpSource
0x180027b54  mov     [rsp+4C0h+lpBuffer], rcx; lpBuffer
0x180027b59  mov     ecx, r12d; dwFlags
0x180027b5c  call    cs:__imp_FormatMessageW
0x180027b63  nop     dword ptr [rax+rax+00h]
0x180027b68  test    eax, eax
0x180027b6a  jz      loc_180027A8A
0x180027b70  mov     edx, 44Ch
0x180027b75  lea     rcx, [rbp+3C0h+lpOutputString]
0x180027b7c  mov     bl, 1
0x180027b7e  call    ?SetSize@?$CAPITempBuffer@D$0BAA@@@QEAA_NH_N@Z; CAPITempBuffer<char,256>::SetSize(int,bool)
0x180027b83  test    al, al
  ... truncated ...
```
