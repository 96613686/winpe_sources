# DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)

- ea: `0x18000a150`
- end: `0x18000a8d6`
- name: `?DebugString@@YAXHGHPEBD000000KPEAX@Z`
- size: `1926`
- prototype: `void(int, unsigned __int16, int, const char *, const char *, const char *, const char *, const char *, const char *, const char *, unsigned int, void *)`
- caller_count: `174`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180001f0c`
- `0x180002b20`
- `0x1800030b0`
- `0x180007cb0`
- `0x180007f20`
- `0x180008370`
- `0x1800083f0`
- `0x180008c20`
- `0x180009030`
- `0x180009340`
- `0x180009680`
- `0x180009a30`
- `0x18000a8e0`
- `0x18000bb60`
- `0x18000bdc0`
- `0x18003ca18`
- `0x18003e1ec`
- `0x180046ec0`
- `0x18004cb90`
- `0x1800523b8`
- `0x180053700`
- `0x1800546a0`
- `0x180055030`
- `0x180065a78`
- `0x18006cc60`
- `0x180081b34`
- `0x180099de4`
- `0x18009a89c`
- `0x18009ae60`
- `0x18009b280`
- `0x18009d810`
- `0x18009e43c`
- `0x18009f870`
- `0x1800a2b9c`
- `0x1800ae31c`
- `0x1800afa20`
- `0x1800afe00`
- `0x1800b1470`
- `0x1800b4680`
- `0x1800b9ef0`
- `0x1800bea48`
- `0x1800cba70`
- `0x1800cd8e4`
- `0x1800da0b4`
- `0x1800f94d0`
- `0x18010a240`
- `0x18010bb60`
- `0x180112f24`
- `0x180128b20`
- `0x18012f694`

## callees

- `0x18000a150`
- `0x18001ba40`
- `0x180025688`
- `0x18003cd20`
- `0x18004ceb0`
- `0x180051564`
- `0x180090e50`
- `0x18009dadc`
- `0x1800c3fb8`
- `0x1800c41c8`
- `0x180145b78`
- `0x180155670`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000a219`
- `KERNEL32!GetCurrentThreadId` at `0x18000a219`
- `KERNEL32!FormatMessageW` at `0x18000a5d6`
- `KERNEL32!FormatMessageW` at `0x18000a630`
- `KERNEL32!FormatMessageW` at `0x18000a5d6`
- `KERNEL32!FormatMessageW` at `0x18000a630`
- `KERNEL32!GetLastError` at `0x18000a5e0`
- `KERNEL32!GetLastError` at `0x18000a5e0`
- `KERNEL32!OutputDebugStringA` at `0x18000a706`
- `KERNEL32!OutputDebugStringA` at `0x18000a713`
- `KERNEL32!OutputDebugStringA` at `0x18000a706`
- `KERNEL32!OutputDebugStringA` at `0x18000a713`
- `KERNEL32!WideCharToMultiByte` at `0x18000a68c`
- `KERNEL32!WideCharToMultiByte` at `0x18000a68c`
- `KERNEL32!GlobalFree` at `0x18000a367`
- `KERNEL32!GlobalFree` at `0x18000a39b`
- `KERNEL32!GlobalFree` at `0x18000a3d3`
- `KERNEL32!GlobalFree` at `0x18000a40b`
- `KERNEL32!GlobalFree` at `0x18000a444`
- `KERNEL32!GlobalFree` at `0x18000a481`
- `KERNEL32!GlobalFree` at `0x18000a4c0`
- `KERNEL32!GlobalFree` at `0x18000a774`
- `KERNEL32!GlobalFree` at `0x18000a8a6`
- `KERNEL32!GlobalFree` at `0x18000a367`
- `KERNEL32!GlobalFree` at `0x18000a39b`
- `KERNEL32!GlobalFree` at `0x18000a3d3`
- `KERNEL32!GlobalFree` at `0x18000a40b`
- `KERNEL32!GlobalFree` at `0x18000a444`
- `KERNEL32!GlobalFree` at `0x18000a481`
- `KERNEL32!GlobalFree` at `0x18000a4c0`
- `KERNEL32!GlobalFree` at `0x18000a774`
- `KERNEL32!GlobalFree` at `0x18000a8a6`
- `KERNEL32!GetCurrentProcessId` at `0x18000a20a`
- `KERNEL32!GetCurrentProcessId` at `0x18000a20a`
- `KERNEL32!GetLocalTime` at `0x18000a235`
- `KERNEL32!GetLocalTime` at `0x18000a235`

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
  _SYSTEMTIME SystemTime; // [rsp+C8h] [rbp-38h] BYREF
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
    if ( (dword_18030B350 & 1) == 0 )
    {
      dword_18030B350 |= 1u;
      dword_18030B354 = (unsigned __int8)GetCurrentProcessId();
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
                dword_18030B354,
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
        v37[0] = dword_180306E9C;
        v42[0] = (_WORD)dword_180306E9C == 0;
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
0x18000a150  mov     [rsp-8+arg_0], rbx
0x18000a155  push    rbp
0x18000a156  push    rsi
0x18000a157  push    rdi
0x18000a158  push    r12
0x18000a15a  push    r13
0x18000a15c  push    r14
0x18000a15e  push    r15
0x18000a160  lea     rbp, [rsp-390h]
0x18000a168  sub     rsp, 490h
0x18000a16f  mov     rax, cs:__security_cookie
0x18000a176  xor     rax, rsp
0x18000a179  mov     [rbp+3C0h+var_38], rax
0x18000a180  mov     rax, [rbp+3C0h+arg_30]
0x18000a187  mov     r14, r9
0x18000a18a  mov     r15, [rbp+3C0h+arg_20]
0x18000a191  mov     esi, ecx
0x18000a193  mov     r12, [rbp+3C0h+arg_28]
0x18000a19a  mov     r13, [rbp+3C0h+arg_48]
0x18000a1a1  mov     [rbp+3C0h+var_430], rax
0x18000a1a5  mov     rax, [rbp+3C0h+arg_38]
0x18000a1ac  mov     [rsp+4C0h+var_458], rax
0x18000a1b1  mov     rax, [rbp+3C0h+arg_40]
0x18000a1b8  mov     [rsp+4C0h+var_448], rax
0x18000a1bd  mov     eax, cs:?g_dmDiagnosticMode@@3HA; int g_dmDiagnosticMode
0x18000a1c3  mov     [rbp+3C0h+var_420], r9
0x18000a1c7  mov     [rsp+4C0h+dwMessageId], r8d
0x18000a1cc  mov     [rsp+4C0h+var_45C], dx
0x18000a1d1  mov     [rbp+3C0h+var_434], ecx
0x18000a1d4  mov     [rbp+3C0h+var_418], r15
0x18000a1d8  mov     [rbp+3C0h+var_428], r12
0x18000a1dc  cmp     eax, 0FFFFFFFFh
0x18000a1df  jnz     short loc_18000A1EC
0x18000a1e1  call    ?SetDiagnosticMode@@YAXXZ; SetDiagnosticMode(void)
0x18000a1e6  mov     eax, cs:?g_dmDiagnosticMode@@3HA; int g_dmDiagnosticMode
0x18000a1ec  or      eax, 10h
0x18000a1ef  test    esi, eax
0x18000a1f1  jz      loc_18000A8AC
0x18000a1f7  mov     eax, cs:dword_18030B350
0x18000a1fd  test    al, 1
0x18000a1ff  jnz     short loc_18000A219
0x18000a201  or      eax, 1
0x18000a204  mov     cs:dword_18030B350, eax
0x18000a20a  call    cs:__imp_GetCurrentProcessId
0x18000a210  movzx   ecx, al
0x18000a213  mov     cs:dword_18030B354, ecx
0x18000a219  call    cs:__imp_GetCurrentThreadId
0x18000a21f  movzx   edi, al
0x18000a222  call    ?MsiGetCurrentThreadId@@YA?AUUniqueThreadID@@XZ; MsiGetCurrentThreadId(void)
0x18000a227  xorps   xmm0, xmm0
0x18000a22a  movzx   ebx, al
0x18000a22d  lea     rcx, [rbp+3C0h+SystemTime]; lpSystemTime
0x18000a231  movups  xmmword ptr [rbp+3C0h+SystemTime.wYear], xmm0
0x18000a235  call    cs:__imp_GetLocalTime
0x18000a23b  mov     ecx, cs:?g_scServerContext@@3W4scEnum@@A; scEnum g_scServerContext
0x18000a241  mov     rax, 2973282049534Dh
0x18000a24b  mov     [rbp+3C0h+var_70], rax
0x18000a252  xor     edx, edx
0x18000a254  mov     rax, 2961282049534Dh
0x18000a25e  mov     r10d, edx
0x18000a261  mov     [rbp+3C0h+var_78], rax
0x18000a268  mov     rax, 2963282049534Dh
0x18000a272  mov     [rbp+3C0h+var_68], rax
0x18000a279  test    ecx, ecx
0x18000a27b  jz      short loc_18000A29E
0x18000a27d  sub     ecx, 1
0x18000a280  jz      short loc_18000A295
0x18000a282  sub     ecx, 1
0x18000a285  jz      short loc_18000A295
0x18000a287  cmp     ecx, 1
0x18000a28a  jnz     short loc_18000A2A5
0x18000a28c  lea     r10, [rbp+3C0h+var_78]
0x18000a293  jmp     short loc_18000A2A5
0x18000a295  lea     r10, [rbp+3C0h+var_70]
0x18000a29c  jmp     short loc_18000A2A5
0x18000a29e  lea     r10, [rbp+3C0h+var_68]
0x18000a2a5  movzx   eax, [rbp+3C0h+SystemTime.wMilliseconds]
0x18000a2a9  mov     r9d, 3Ah ; ':'
0x18000a2af  movzx   ecx, [rbp+3C0h+SystemTime.wSecond]
0x18000a2b3  cmp     edi, ebx
0x18000a2b5  movzx   edx, [rbp+3C0h+SystemTime.wMinute]
0x18000a2b9  movzx   r8d, [rbp+3C0h+SystemTime.wHour]
0x18000a2be  mov     [rsp+4C0h+var_470], eax
0x18000a2c2  lea     r11d, [r9-19h]
0x18000a2c6  mov     eax, cs:dword_18030B354
0x18000a2cc  cmovnz  r9d, r11d
0x18000a2d0  mov     dword ptr [rsp+4C0h+var_478], ecx
0x18000a2d4  lea     rcx, [rbp+3C0h+var_60]; char *
0x18000a2db  mov     dword ptr [rsp+4C0h+var_480], edx
0x18000a2df  mov     edx, r11d; unsigned __int64
0x18000a2e2  mov     dword ptr [rsp+4C0h+lpUsedDefaultChar], r8d
0x18000a2e7  lea     r8, aS2xC2x02u02u02; "%s (%.2X%c%.2X) [%02u:%02u:%02u:%03u]: "
0x18000a2ee  mov     dword ptr [rsp+4C0h+Arguments], ebx
0x18000a2f2  mov     [rsp+4C0h+nSize], r9d
0x18000a2f7  mov     r9, r10
0x18000a2fa  mov     dword ptr [rsp+4C0h+lpBuffer], eax
0x18000a2fe  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000a303  xor     ebx, ebx
0x18000a305  test    eax, eax
0x18000a307  js      loc_18000A8AC
0x18000a30d  mov     edi, esi
0x18000a30f  mov     [rbp+3C0h+var_1B8], 100h
0x18000a319  and     edi, 10h
0x18000a31c  lea     rax, [rbp+3C0h+var_1B0]
0x18000a323  mov     [rbp+3C0h+var_438], edi
0x18000a326  mov     [rbp+3C0h+lpOutputString], rax
0x18000a32d  jz      loc_18000A7D1
0x18000a333  lea     rax, [rbp+3C0h+var_3D0]
0x18000a337  mov     [rbp+3C0h+var_1C8], rbx
0x18000a33e  mov     edi, 100h
0x18000a343  mov     [rbp+3C0h+hMem], rax
0x18000a347  lea     rcx, [rbp+3C0h+hMem]
0x18000a34b  mov     [rbp+3C0h+var_3D8], edi
0x18000a34e  mov     [rbp+3C0h+var_1D0], r14
0x18000a355  call    ??BCApiConvertString@@QEAAPEBGXZ; CApiConvertString::operator ushort const *(void)
0x18000a35a  mov     qword ptr [rbp+3C0h+var_440], rax
0x18000a35e  cmp     [rbp+3C0h+var_3D8], edi
0x18000a361  jle     short loc_18000A36D
0x18000a363  mov     rcx, [rbp+3C0h+hMem]; hMem
0x18000a367  call    cs:__imp_GlobalFree
0x18000a36d  lea     rax, [rbp+3C0h+var_3D0]
0x18000a371  mov     [rbp+3C0h+var_3D8], edi
0x18000a374  lea     rcx, [rbp+3C0h+hMem]
0x18000a378  mov     [rbp+3C0h+hMem], rax
0x18000a37c  mov     [rbp+3C0h+var_1C8], rbx
0x18000a383  mov     [rbp+3C0h+var_1D0], r15
0x18000a38a  call    ??BCApiConvertString@@QEAAPEBGXZ; CApiConvertString::operator ushort const *(void)
0x18000a38f  mov     r12, rax
0x18000a392  cmp     [rbp+3C0h+var_3D8], edi
0x18000a395  jle     short loc_18000A3A1
0x18000a397  mov     rcx, [rbp+3C0h+hMem]; hMem
0x18000a39b  call    cs:__imp_GlobalFree
0x18000a3a1  lea     rax, [rbp+3C0h+var_3D0]
0x18000a3a5  mov     [rbp+3C0h+var_3D8], edi
0x18000a3a8  mov     [rbp+3C0h+hMem], rax
0x18000a3ac  lea     rcx, [rbp+3C0h+hMem]
0x18000a3b0  mov     rax, [rbp+3C0h+var_428]
0x18000a3b4  mov     [rbp+3C0h+var_1D0], rax
0x18000a3bb  mov     [rbp+3C0h+var_1C8], rbx
0x18000a3c2  call    ??BCApiConvertString@@QEAAPEBGXZ; CApiConvertString::operator ushort const *(void)
0x18000a3c7  mov     r15, rax
0x18000a3ca  cmp     [rbp+3C0h+var_3D8], edi
0x18000a3cd  jle     short loc_18000A3D9
0x18000a3cf  mov     rcx, [rbp+3C0h+hMem]; hMem
0x18000a3d3  call    cs:__imp_GlobalFree
0x18000a3d9  lea     rax, [rbp+3C0h+var_3D0]
0x18000a3dd  mov     [rbp+3C0h+var_3D8], edi
0x18000a3e0  mov     [rbp+3C0h+hMem], rax
0x18000a3e4  lea     rcx, [rbp+3C0h+hMem]
0x18000a3e8  mov     rax, [rbp+3C0h+var_430]
0x18000a3ec  mov     [rbp+3C0h+var_1D0], rax
0x18000a3f3  mov     [rbp+3C0h+var_1C8], rbx
0x18000a3fa  call    ??BCApiConvertString@@QEAAPEBGXZ; CApiConvertString::operator ushort const *(void)
0x18000a3ff  mov     r14, rax
0x18000a402  cmp     [rbp+3C0h+var_3D8], edi
0x18000a405  jle     short loc_18000A411
0x18000a407  mov     rcx, [rbp+3C0h+hMem]; hMem
0x18000a40b  call    cs:__imp_GlobalFree
0x18000a411  lea     rax, [rbp+3C0h+var_3D0]
0x18000a415  mov     [rbp+3C0h+var_3D8], edi
0x18000a418  mov     [rbp+3C0h+hMem], rax
0x18000a41c  lea     rcx, [rbp+3C0h+hMem]
0x18000a420  mov     rax, [rsp+4C0h+var_458]
0x18000a425  mov     [rbp+3C0h+var_1D0], rax
0x18000a42c  mov     [rbp+3C0h+var_1C8], rbx
0x18000a433  call    ??BCApiConvertString@@QEAAPEBGXZ; CApiConvertString::operator ushort const *(void)
0x18000a438  mov     rsi, rax
0x18000a43b  cmp     [rbp+3C0h+var_3D8], edi
0x18000a43e  jle     short loc_18000A44A
0x18000a440  mov     rcx, [rbp+3C0h+hMem]; hMem
0x18000a444  call    cs:__imp_GlobalFree
0x18000a44a  lea     rax, [rbp+3C0h+var_3D0]
0x18000a44e  mov     [rbp+3C0h+var_3D8], edi
0x18000a451  mov     [rbp+3C0h+hMem], rax
0x18000a455  lea     rcx, [rbp+3C0h+hMem]
0x18000a459  mov     rax, [rsp+4C0h+var_448]
0x18000a45e  mov     [rbp+3C0h+var_1D0], rax
0x18000a465  mov     [rbp+3C0h+var_1C8], rbx
0x18000a46c  call    ??BCApiConvertString@@QEAAPEBGXZ; CApiConvertString::operator ushort const *(void)
0x18000a471  cmp     [rbp+3C0h+var_3D8], 100h
0x18000a478  mov     rdi, rax
0x18000a47b  jle     short loc_18000A487
0x18000a47d  mov     rcx, [rbp+3C0h+hMem]; hMem
0x18000a481  call    cs:__imp_GlobalFree
0x18000a487  lea     rax, [rbp+3C0h+var_3D0]
0x18000a48b  mov     [rbp+3C0h+var_3D8], 100h
0x18000a492  lea     rcx, [rbp+3C0h+hMem]
0x18000a496  mov     [rbp+3C0h+hMem], rax
0x18000a49a  mov     [rbp+3C0h+var_1C8], rbx
0x18000a4a1  mov     [rbp+3C0h+var_1D0], r13
0x18000a4a8  call    ??BCApiConvertString@@QEAAPEBGXZ; CApiConvertString::operator ushort const *(void)
0x18000a4ad  mov     r13d, 100h
0x18000a4b3  mov     rbx, rax
0x18000a4b6  cmp     [rbp+3C0h+var_3D8], r13d
0x18000a4ba  jle     short loc_18000A4C6
0x18000a4bc  mov     rcx, [rbp+3C0h+hMem]; hMem
0x18000a4c0  call    cs:__imp_GlobalFree
0x18000a4c6  mov     rax, qword ptr [rbp+3C0h+var_440]
0x18000a4ca  lea     rcx, [rbp+3C0h+var_410]
0x18000a4ce  mov     [rbp+3C0h+var_B0], rax
0x18000a4d5  xor     r8d, r8d
0x18000a4d8  lea     rax, [rbp+3C0h+var_400]
0x18000a4dc  mov     [rbp+3C0h+var_A8], r12
0x18000a4e3  mov     edx, 105h
0x18000a4e8  mov     [rbp+3C0h+var_410], rax
0x18000a4ec  mov     [rbp+3C0h+var_A0], r15
0x18000a4f3  mov     [rbp+3C0h+var_98], r14
0x18000a4fa  mov     [rbp+3C0h+var_90], rsi
0x18000a501  mov     [rbp+3C0h+var_88], rdi
0x18000a508  mov     [rbp+3C0h+var_80], rbx
0x18000a50f  mov     [rbp+3C0h+var_408], 1
0x18000a516  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x18000a51b  xor     r15d, r15d
0x18000a51e  test    al, al
0x18000a520  jnz     short loc_18000A544
0x18000a522  lea     rcx, [rbp+3C0h+var_410]
0x18000a526  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18000a52b  cmp     [rbp+3C0h+var_1B8], r13d
0x18000a532  jle     loc_18000A8AC
0x18000a538  mov     rcx, [rbp+3C0h+lpOutputString]
0x18000a53f  jmp     loc_18000A8A6
0x18000a544  movzx   eax, word ptr cs:dword_180306E9C
0x18000a54b  mov     ecx, r15d
0x18000a54e  mov     r14d, [rsp+4C0h+dwMessageId]
0x18000a553  test    ax, ax
0x18000a556  mov     bl, r15b
0x18000a559  mov     [rsp+4C0h+var_460], ax
0x18000a55e  setz    cl
0x18000a561  mov     r12d, 2800h
0x18000a567  mov     [rbp+3C0h+var_440], ecx
0x18000a56a  test    bl, bl
0x18000a56c  jnz     loc_18000A69F
0x18000a572  lea     rdx, [rsp+4C0h+var_460]; unsigned __int16 *
0x18000a577  lea     rcx, [rbp+3C0h+var_440]; unsigned int *
0x18000a57b  call    ?MsiSwitchLanguage@@YA_NAEAIAEAG@Z; MsiSwitchLanguage(uint &,ushort &)
0x18000a580  test    al, al
0x18000a582  jnz     short loc_18000A593
0x18000a584  mov     rax, [rbp+3C0h+lpOutputString]
0x18000a58b  mov     bl, 1
0x18000a58d  mov     [rax+20h], r15b
0x18000a591  jmp     short loc_18000A56A
0x18000a593  movzx   ecx, [rsp+4C0h+var_460]; unsigned __int16
0x18000a598  call    ?GetMsgDll@@YAPEAUHINSTANCE__@@G@Z; GetMsgDll(ushort)
0x18000a59d  mov     rdi, rax
0x18000a5a0  test    rax, rax
0x18000a5a3  jz      loc_18000A63E
0x18000a5a9  mov     rdx, [rbp+3C0h+var_410]
0x18000a5ad  lea     rax, [rbp+3C0h+var_B0]
0x18000a5b4  mov     ecx, [rbp+3C0h+var_408]
0x18000a5b7  mov     r8d, r14d; dwMessageId
0x18000a5ba  movzx   esi, [rsp+4C0h+var_460]
0x18000a5bf  mov     [rsp+4C0h+Arguments], rax; Arguments
0x18000a5c4  mov     r9d, esi; dwLanguageId
0x18000a5c7  mov     [rsp+4C0h+nSize], ecx; nSize
0x18000a5cb  mov     ecx, r12d; dwFlags
0x18000a5ce  mov     [rsp+4C0h+lpBuffer], rdx; lpBuffer
0x18000a5d3  mov     rdx, rdi; lpSource
0x18000a5d6  call    cs:__imp_FormatMessageW
0x18000a5dc  test    eax, eax
0x18000a5de  jnz     short loc_18000A63E
0x18000a5e0  call    cs:__imp_GetLastError
0x18000a5e6  cmp     eax, 7Ah ; 'z'
0x18000a5e9  jnz     loc_18000A56A
0x18000a5ef  xor     r8d, r8d
0x18000a5f2  lea     rcx, [rbp+3C0h+var_410]
0x18000a5f6  mov     edx, 44Ch
0x18000a5fb  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x18000a600  test    al, al
0x18000a602  jz      loc_18000A56A
0x18000a608  mov     rcx, [rbp+3C0h+var_410]
0x18000a60c  lea     rax, [rbp+3C0h+var_B0]
0x18000a613  mov     [rsp+4C0h+Arguments], rax; Arguments
0x18000a618  mov     r9d, esi; dwLanguageId
0x18000a61b  mov     eax, [rbp+3C0h+var_408]
0x18000a61e  mov     r8d, r14d; dwMessageId
0x18000a621  mov     [rsp+4C0h+nSize], eax; nSize
0x18000a625  mov     rdx, rdi; lpSource
0x18000a628  mov     [rsp+4C0h+lpBuffer], rcx; lpBuffer
0x18000a62d  mov     ecx, r12d; dwFlags
0x18000a630  call    cs:__imp_FormatMessageW
0x18000a636  test    eax, eax
0x18000a638  jz      loc_18000A56A
0x18000a63e  mov     edx, 44Ch
0x18000a643  lea     rcx, [rbp+3C0h+lpOutputString]
0x18000a64a  mov     bl, 1
0x18000a64c  call    ?SetSize@?$CAPITempBuffer@D$0BAA@@@QEAA_NH_N@Z; CAPITempBuffer<char,256>::SetSize(int,bool)
0x18000a651  test    al, al
0x18000a653  jz      loc_18000A522
0x18000a659  mov     ecx, [rbp+3C0h+var_1B8]
0x18000a65f  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000a663  mov     rax, [rbp+3C0h+lpOutputString]
0x18000a66a  add     ecx, 0FFFFFFE0h
0x18000a66d  mov     r8, [rbp+3C0h+var_410]; lpWideCharStr
0x18000a671  add     rax, 20h ; ' '
0x18000a675  mov     [rsp+4C0h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x18000a67a  xor     edx, edx; dwFlags
0x18000a67c  mov     [rsp+4C0h+Arguments], r15; lpDefaultChar
0x18000a681  mov     [rsp+4C0h+nSize], ecx; cbMultiByte
0x18000a685  xor     ecx, ecx; CodePage
0x18000a687  mov     [rsp+4C0h+lpBuffer], rax; lpMultiByteStr
  ... truncated ...
```
