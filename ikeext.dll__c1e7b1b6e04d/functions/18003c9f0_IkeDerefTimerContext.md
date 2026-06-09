# IkeDerefTimerContext

- ea: `0x18003c9f0`
- end: `0x18003cf95`
- name: `IkeDerefTimerContext`
- size: `1445`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, int)`
- caller_count: `15`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18003cfa0`
- `0x18003d320`
- `0x18003e7e0`
- `0x1800cb790`
- `0x1800cbb90`
- `0x1800cbce0`
- `0x1800cbd10`
- `0x1800cbf20`
- `0x1800cc0b0`
- `0x1800cc630`
- `0x1800cc7c0`
- `0x1800cc9d0`
- `0x1800ccb80`
- `0x1800cd260`
- `0x1800cddb0`

## callees

- `0x1800037c4`
- `0x180019030`
- `0x180025d88`
- `0x180028294`
- `0x18003c9f0`
- `0x18003d2ac`
- `0x180050850`
- `0x18006df9c`
- `0x1800cf350`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003ca69`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003caa2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003cb1d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003cb64`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003cd44`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003cd7d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003cddc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003ce21`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003ca69`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003caa2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003cb1d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003cb64`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003cd44`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003cd7d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003cddc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003ce21`
- `ntdll!EtwEventWriteTransfer` at `0x18003cc4d`
- `ntdll!EtwEventWriteTransfer` at `0x18003cefd`
- `ntdll!EtwEventWriteTransfer` at `0x18003cc4d`
- `ntdll!EtwEventWriteTransfer` at `0x18003cefd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ccb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cf06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cf6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ccb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cf06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cf6f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003cf15`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003cf15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cc7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cc7d`

## pseudocode

```c
void __fastcall IkeDerefTimerContext(LPCRITICAL_SECTION lpCriticalSection, int a2)
{
  _QWORD *v4; // rcx
  LPCRITICAL_SECTION v5; // rdx
  DWORD LockSemaphore; // eax
  LPVOID Value; // rax
  LPVOID v8; // r8
  __int64 v9; // rdi
  DWORD v10; // eax
  __int64 *v11; // rax
  __int64 v12; // r9
  __int64 v13; // rdi
  LPCRITICAL_SECTION v14; // rax
  DWORD v15; // ecx
  struct _RTL_CRITICAL_SECTION **v16; // rax
  struct _RTL_CRITICAL_SECTION *v17; // rcx
  DWORD v18; // ecx
  char *v19; // rax
  const WCHAR *v20; // rdx
  __int64 v21; // rax
  bool v22; // zf
  int v23; // eax
  char *v24; // rsi
  int OwningThread_high; // ecx
  unsigned int v26; // eax
  int RefTypeFromTimerType; // eax
  _QWORD *v28; // rcx
  LPCRITICAL_SECTION v29; // rdx
  DWORD v30; // eax
  LPVOID v31; // rax
  LPVOID v32; // r8
  __int64 v33; // rsi
  DWORD v34; // eax
  __int64 *v35; // rax
  __int64 v36; // r9
  LPCRITICAL_SECTION v37; // rax
  DWORD v38; // ecx
  struct _RTL_CRITICAL_SECTION **v39; // rax
  struct _RTL_CRITICAL_SECTION *v40; // rcx
  DWORD v41; // ecx
  char *v42; // rax
  const WCHAR *v43; // rdx
  int v44; // edi
  LPCVOID *p_OwningThread; // rbx
  LPCVOID v46; // [rsp+48h] [rbp-91h] BYREF
  LONG LockCount; // [rsp+50h] [rbp-89h] BYREF
  LPCRITICAL_SECTION v48; // [rsp+58h] [rbp-81h] BYREF
  LPCRITICAL_SECTION v49; // [rsp+60h] [rbp-79h] BYREF
  int v50; // [rsp+68h] [rbp-71h] BYREF
  int v51; // [rsp+6Ch] [rbp-6Dh]
  __int64 v52; // [rsp+70h] [rbp-69h]
  char *v53; // [rsp+80h] [rbp-59h] BYREF
  int v54; // [rsp+88h] [rbp-51h]
  int v55; // [rsp+8Ch] [rbp-4Dh]
  char *v56; // [rsp+90h] [rbp-49h]
  int v57; // [rsp+98h] [rbp-41h]
  int v58; // [rsp+9Ch] [rbp-3Dh]
  LPCRITICAL_SECTION *v59; // [rsp+A0h] [rbp-39h]
  __int64 v60; // [rsp+A8h] [rbp-31h]
  const WCHAR *v61; // [rsp+B0h] [rbp-29h]
  int v62; // [rsp+B8h] [rbp-21h]
  int v63; // [rsp+BCh] [rbp-1Dh]
  LPCRITICAL_SECTION *v64; // [rsp+C0h] [rbp-19h]
  __int64 v65; // [rsp+C8h] [rbp-11h]
  LONG *p_LockCount; // [rsp+D0h] [rbp-9h]
  __int64 v67; // [rsp+D8h] [rbp-1h]

  v46 = lpCriticalSection;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v5 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore, LockSemaphore == -1) )
    {
      v8 = 0;
    }
    else
    {
      Value = TlsGetValue(LockSemaphore);
      v4 = WPP_GLOBAL_Control;
      v8 = Value;
      v5 = gIkeExtGlobals;
    }
    v9 = (__int64)v8 + 8;
    if ( !v8 )
      v9 = 0;
    if ( v5
      && (v10 = (DWORD)v5[86].LockSemaphore, v10 != -1)
      && (v11 = (__int64 *)TlsGetValue(v10), v4 = WPP_GLOBAL_Control, v11) )
    {
      v12 = *v11;
    }
    else
    {
      LODWORD(v12) = 0;
    }
    WPP_SF_iSqD(
      v4[2],
      50,
      (unsigned int)WPP_4c56edd497003658c4b83fd296af3c1f_Traceguids,
      v12,
      v9,
      (__int64)lpCriticalSection,
      lpCriticalSection[2].LockCount);
  }
  v13 = -1;
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v14 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v15 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v15 != -1 )
      {
        v16 = (struct _RTL_CRITICAL_SECTION **)TlsGetValue(v15);
        if ( v16 )
        {
          v17 = *v16;
          v14 = gIkeExtGlobals;
LABEL_23:
          v48 = v17;
          v59 = &v48;
          v60 = 8;
          if ( !v14 )
            goto LABEL_31;
          v18 = (DWORD)v14[86].LockSemaphore;
          if ( v18 == -1 )
            goto LABEL_31;
          v19 = (char *)TlsGetValue(v18);
          v20 = (const WCHAR *)(v19 + 8);
          if ( !v19 )
            v20 = 0;
          if ( v20 )
          {
            v21 = -1;
            do
              v22 = v20[++v21] == 0;
            while ( !v22 );
            v23 = 2 * v21 + 2;
          }
          else
          {
LABEL_31:
            v20 = &LocaleName;
            v23 = 2;
          }
          v62 = v23;
          v61 = v20;
          v64 = &v49;
          v63 = 0;
          v49 = lpCriticalSection;
          v65 = 8;
          LockCount = lpCriticalSection[2].LockCount;
          p_LockCount = &LockCount;
          v51 = 4;
          v53 = off_180173280;
          v67 = 4;
          v50 = 184549376;
          v52 = 0;
          v54 = *(unsigned __int16 *)off_180173280;
          v56 = &byte_18015D3D7;
          v55 = 2;
          v57 = 73;
          v58 = 1;
          EtwEventWriteTransfer(qword_180173298, &v50, 0, 0, 6, &v53);
          goto LABEL_33;
        }
        v14 = gIkeExtGlobals;
      }
    }
    v17 = 0;
    goto LABEL_23;
  }
LABEL_33:
  v24 = (char *)lpCriticalSection[2].LockSemaphore;
  if ( v24 )
  {
    OwningThread_high = HIDWORD(lpCriticalSection[2].OwningThread);
    if ( ((unsigned int)(OwningThread_high - 1) <= 1 || OwningThread_high == 13) && *((_DWORD *)v24 + 146) == 1 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v24 + 48));
      *(_DWORD *)(*((_QWORD *)v24 + 137) + 16LL) = 0;
      if ( *(_DWORD *)(*((_QWORD *)v24 + 137) + 20LL) )
      {
        IkeDerefMMSA((__int64)v24, 4);
        *(_DWORD *)(*((_QWORD *)v24 + 137) + 20LL) = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v24 + 48));
    }
    if ( *((_DWORD *)lpCriticalSection[2].LockSemaphore + 146) == 2 )
    {
      v26 = HIDWORD(lpCriticalSection[2].OwningThread);
      if ( v26 <= 2 || v26 - 6 <= 2 )
        IkeClearRequestWorkInProgressStateIkeV2();
    }
    RefTypeFromTimerType = IkeGetRefTypeFromTimerType(HIDWORD(lpCriticalSection[2].OwningThread));
    IkeDerefMMSA((__int64)lpCriticalSection[2].LockSemaphore, RefTypeFromTimerType);
    lpCriticalSection[2].LockSemaphore = 0;
  }
  v22 = lpCriticalSection[2].LockCount-- == 1;
  if ( v22 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v29 = gIkeExtGlobals;
      if ( !gIkeExtGlobals || (v30 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v30 == -1) )
      {
        v32 = 0;
      }
      else
      {
        v31 = TlsGetValue(v30);
        v28 = WPP_GLOBAL_Control;
        v32 = v31;
        v29 = gIkeExtGlobals;
      }
      v33 = (__int64)v32 + 8;
      if ( !v32 )
        v33 = 0;
      if ( v29
        && (v34 = (DWORD)v29[86].LockSemaphore, v34 != -1)
        && (v35 = (__int64 *)TlsGetValue(v34), v28 = WPP_GLOBAL_Control, v35) )
      {
        v36 = *v35;
      }
      else
      {
        LODWORD(v36) = 0;
      }
      WPP_SF_iSq(
        v28[2],
        51,
        (unsigned int)WPP_4c56edd497003658c4b83fd296af3c1f_Traceguids,
        v36,
        v33,
        (__int64)lpCriticalSection);
    }
    if ( (unsigned int)dword_180173278 <= 4 )
      goto LABEL_77;
    v37 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v38 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v38 != -1 )
      {
        v39 = (struct _RTL_CRITICAL_SECTION **)TlsGetValue(v38);
        if ( v39 )
        {
          v40 = *v39;
          v37 = gIkeExtGlobals;
LABEL_68:
          v49 = v40;
          v59 = &v49;
          v60 = 8;
          if ( !v37 )
            goto LABEL_75;
          v41 = (DWORD)v37[86].LockSemaphore;
          if ( v41 == -1 )
            goto LABEL_75;
          v42 = (char *)TlsGetValue(v41);
          v43 = (const WCHAR *)(v42 + 8);
          if ( !v42 )
            v43 = 0;
          if ( v43 )
          {
            do
              v22 = v43[++v13] == 0;
            while ( !v22 );
            v44 = 2 * v13 + 2;
          }
          else
          {
LABEL_75:
            v43 = &LocaleName;
            v44 = 2;
          }
          v61 = v43;
          v64 = &v48;
          v51 = 4;
          v53 = off_180173280;
          v62 = v44;
          v63 = 0;
          v48 = lpCriticalSection;
          v65 = 8;
          v50 = 184549376;
          v52 = 0;
          v54 = *(unsigned __int16 *)off_180173280;
          v56 = (char *)&unk_18015D390;
          v55 = 2;
          v57 = 59;
          v58 = 1;
          EtwEventWriteTransfer(qword_180173298, &v50, 0, 0, 5, &v53);
LABEL_77:
          LeaveCriticalSection(lpCriticalSection);
          if ( LODWORD(lpCriticalSection[1].DebugInfo) )
          {
            DeleteCriticalSection(lpCriticalSection);
            LODWORD(lpCriticalSection[1].DebugInfo) = 0;
          }
          p_OwningThread = (LPCVOID *)&lpCriticalSection[7].OwningThread;
          if ( (*((_BYTE *)p_OwningThread + 28) & 2) != 0 )
          {
            if ( p_OwningThread[4] )
            {
              Ikev2ClearFragmentListEntryList();
              WfpMemFree(p_OwningThread + 4);
            }
          }
          WfpMemFree(p_OwningThread);
          *(_OWORD *)p_OwningThread = 0;
          *((_OWORD *)p_OwningThread + 1) = 0;
          p_OwningThread[4] = 0;
          WfpMemFree(&v46);
          return;
        }
        v37 = gIkeExtGlobals;
      }
    }
    v40 = 0;
    goto LABEL_68;
  }
  if ( a2 )
    LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18003c9f0  push    rbp
0x18003c9f2  push    rbx
0x18003c9f3  push    rsi
0x18003c9f4  push    rdi
0x18003c9f5  push    r12
0x18003c9f7  push    r13
0x18003c9f9  push    r14
0x18003c9fb  push    r15
0x18003c9fd  lea     rbp, [rsp-1Fh]
0x18003ca02  sub     rsp, 0F8h
0x18003ca09  mov     rax, cs:__security_cookie
0x18003ca10  xor     rax, rsp
0x18003ca13  mov     [rbp+57h+var_50], rax
0x18003ca17  mov     r15d, edx
0x18003ca1a  mov     [rsp+130h+var_E8], rcx
0x18003ca1f  mov     rbx, rcx
0x18003ca22  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ca29  lea     r14, WPP_GLOBAL_Control
0x18003ca30  xor     r13d, r13d
0x18003ca33  cmp     rcx, r14
0x18003ca36  jz      loc_18003CAE2
0x18003ca3c  cmp     byte ptr [rcx+19h], 4
0x18003ca40  jb      loc_18003CAE2
0x18003ca46  test    byte ptr [rcx+1Ch], 10h
0x18003ca4a  jz      loc_18003CAE2
0x18003ca50  mov     rdx, cs:gIkeExtGlobals
0x18003ca57  test    rdx, rdx
0x18003ca5a  jz      short loc_18003CA82
0x18003ca5c  mov     eax, [rdx+0D88h]
0x18003ca62  cmp     eax, 0FFFFFFFFh
0x18003ca65  jz      short loc_18003CA82
0x18003ca67  mov     ecx, eax; dwTlsIndex
0x18003ca69  call    cs:__imp_TlsGetValue
0x18003ca6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ca76  mov     r8, rax
0x18003ca79  mov     rdx, cs:gIkeExtGlobals
0x18003ca80  jmp     short loc_18003CA85
0x18003ca82  mov     r8, r13
0x18003ca85  test    r8, r8
0x18003ca88  lea     rdi, [r8+8]
0x18003ca8c  cmovz   rdi, r13
0x18003ca90  test    rdx, rdx
0x18003ca93  jz      short loc_18003CAB9
0x18003ca95  mov     eax, [rdx+0D88h]
0x18003ca9b  cmp     eax, 0FFFFFFFFh
0x18003ca9e  jz      short loc_18003CAB9
0x18003caa0  mov     ecx, eax; dwTlsIndex
0x18003caa2  call    cs:__imp_TlsGetValue
0x18003caa8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003caaf  test    rax, rax
0x18003cab2  jz      short loc_18003CAB9
0x18003cab4  mov     r9, [rax]
0x18003cab7  jmp     short loc_18003CABC
0x18003cab9  mov     r9, r13
0x18003cabc  mov     eax, [rbx+58h]
0x18003cabf  lea     r8, WPP_4c56edd497003658c4b83fd296af3c1f_Traceguids
0x18003cac6  mov     rcx, [rcx+10h]
0x18003caca  mov     edx, 32h ; '2'
0x18003cacf  mov     [rsp+130h+var_100], eax
0x18003cad3  mov     [rsp+130h+var_108], rbx
0x18003cad8  mov     [rsp+130h+var_110], rdi
0x18003cadd  call    WPP_SF_iSqD
0x18003cae2  mov     eax, cs:dword_180173278
0x18003cae8  lea     r12, _TraceLoggingMetadataEnd
0x18003caef  lea     rsi, _TraceLoggingMetadata
0x18003caf6  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18003cafd  cmp     eax, 4
0x18003cb00  jbe     loc_18003CC53
0x18003cb06  mov     rax, cs:gIkeExtGlobals
0x18003cb0d  test    rax, rax
0x18003cb10  jz      short loc_18003CB3B
0x18003cb12  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003cb18  cmp     ecx, 0FFFFFFFFh
0x18003cb1b  jz      short loc_18003CB3B
0x18003cb1d  call    cs:__imp_TlsGetValue
0x18003cb23  test    rax, rax
0x18003cb26  jz      short loc_18003CB34
0x18003cb28  mov     rcx, [rax]
0x18003cb2b  mov     rax, cs:gIkeExtGlobals
0x18003cb32  jmp     short loc_18003CB3E
0x18003cb34  mov     rax, cs:gIkeExtGlobals
0x18003cb3b  mov     rcx, r13
0x18003cb3e  mov     [rsp+130h+var_D8], rcx
0x18003cb43  lea     rcx, [rsp+130h+var_D8]
0x18003cb48  mov     [rbp+57h+var_90], rcx
0x18003cb4c  mov     [rbp+57h+var_88], 8
0x18003cb54  test    rax, rax
0x18003cb57  jz      short loc_18003CB95
0x18003cb59  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003cb5f  cmp     ecx, 0FFFFFFFFh
0x18003cb62  jz      short loc_18003CB95
0x18003cb64  call    cs:__imp_TlsGetValue
0x18003cb6a  test    rax, rax
0x18003cb6d  lea     rdx, [rax+8]
0x18003cb71  cmovz   rdx, r13
0x18003cb75  test    rdx, rdx
0x18003cb78  jz      short loc_18003CB95
0x18003cb7a  mov     rax, rdi
0x18003cb7d  nop     dword ptr [rax]
0x18003cb80  cmp     [rdx+rax*2+2], r13w
0x18003cb86  lea     rax, [rax+1]
0x18003cb8a  jnz     short loc_18003CB80
0x18003cb8c  lea     eax, ds:2[rax*2]
0x18003cb93  jmp     short loc_18003CBA1
0x18003cb95  lea     rdx, LocaleName
0x18003cb9c  mov     eax, 2
0x18003cba1  mov     [rbp+57h+var_78], eax
0x18003cba4  xor     r9d, r9d
0x18003cba7  mov     [rbp+57h+var_80], rdx
0x18003cbab  lea     rax, [rbp+57h+var_D0]
0x18003cbaf  mov     [rbp+57h+var_70], rax
0x18003cbb3  lea     rdx, [rbp+57h+var_C8]
0x18003cbb7  mov     [rbp+57h+var_74], r13d
0x18003cbbb  xor     r8d, r8d
0x18003cbbe  mov     [rbp+57h+var_D0], rbx
0x18003cbc2  mov     [rbp+57h+var_68], 8
0x18003cbca  mov     eax, [rbx+58h]
0x18003cbcd  mov     [rsp+130h+var_E0], eax
0x18003cbd1  lea     rax, [rsp+130h+var_E0]
0x18003cbd6  mov     [rbp+57h+var_60], rax
0x18003cbda  movzx   eax, cs:word_18015D3CD
0x18003cbe1  mov     [rbp+57h+var_C4], eax
0x18003cbe4  mov     rax, cs:off_180173280
0x18003cbeb  mov     [rbp+57h+var_B0], rax
0x18003cbef  mov     [rbp+57h+var_58], 4
0x18003cbf7  mov     [rbp+57h+var_C8], 0B000000h
0x18003cbfe  mov     [rbp+57h+var_C0], r13
0x18003cc02  movzx   eax, word ptr [rax]
0x18003cc05  mov     [rbp+57h+var_A8], eax
0x18003cc08  lea     rax, byte_18015D3D7
0x18003cc0f  mov     [rbp+57h+var_A0], rax
0x18003cc13  mov     rax, r12
0x18003cc16  sub     eax, esi
0x18003cc18  mov     [rbp+57h+var_A4], 2
0x18003cc1f  mov     [rbp+57h+var_98], 49h ; 'I'
0x18003cc26  mov     [rbp+57h+var_94], 1
0x18003cc2d  mov     [rsp+130h+var_F0], eax
0x18003cc31  mov     eax, [rsp+130h+var_F0]
0x18003cc35  mov     rcx, cs:qword_180173298
0x18003cc3c  lea     rax, [rbp+57h+var_B0]
0x18003cc40  mov     [rsp+130h+var_108], rax
0x18003cc45  mov     dword ptr [rsp+130h+var_110], 6
0x18003cc4d  call    cs:__imp_EtwEventWriteTransfer
0x18003cc53  mov     rsi, [rbx+68h]
0x18003cc57  test    rsi, rsi
0x18003cc5a  jz      loc_18003CCFD
0x18003cc60  mov     ecx, [rbx+64h]
0x18003cc63  lea     eax, [rcx-1]
0x18003cc66  cmp     eax, 1
0x18003cc69  jbe     short loc_18003CC70
0x18003cc6b  cmp     ecx, 0Dh
0x18003cc6e  jnz     short loc_18003CCC4
0x18003cc70  cmp     dword ptr [rsi+248h], 1
0x18003cc77  jnz     short loc_18003CCC4
0x18003cc79  lea     rcx, [rsi+30h]; lpCriticalSection
0x18003cc7d  call    cs:__imp_EnterCriticalSection
0x18003cc83  mov     rax, [rsi+448h]
0x18003cc8a  mov     [rax+10h], r13d
0x18003cc8e  mov     rax, [rsi+448h]
0x18003cc95  cmp     [rax+14h], r13d
0x18003cc99  jz      short loc_18003CCB3
0x18003cc9b  mov     edx, 4
0x18003cca0  mov     rcx, rsi
0x18003cca3  call    IkeDerefMMSA
0x18003cca8  mov     rax, [rsi+448h]
0x18003ccaf  mov     [rax+14h], r13d
0x18003ccb3  lea     rcx, [rsi+30h]; lpCriticalSection
0x18003ccb7  call    cs:__imp_LeaveCriticalSection
0x18003ccbd  lea     r14, WPP_GLOBAL_Control
0x18003ccc4  mov     rcx, [rbx+68h]
0x18003ccc8  cmp     dword ptr [rcx+248h], 2
0x18003cccf  jnz     short loc_18003CCE6
0x18003ccd1  mov     eax, [rbx+64h]
0x18003ccd4  cmp     eax, 2
0x18003ccd7  jbe     short loc_18003CCE1
0x18003ccd9  add     eax, 0FFFFFFFAh
0x18003ccdc  cmp     eax, 2
0x18003ccdf  ja      short loc_18003CCE6
0x18003cce1  call    IkeClearRequestWorkInProgressStateIkeV2
0x18003cce6  mov     ecx, [rbx+64h]
0x18003cce9  call    IkeGetRefTypeFromTimerType
0x18003ccee  mov     rcx, [rbx+68h]
0x18003ccf2  mov     edx, eax
0x18003ccf4  call    IkeDerefMMSA
0x18003ccf9  mov     [rbx+68h], r13
0x18003ccfd  add     dword ptr [rbx+58h], 0FFFFFFFFh
0x18003cd01  jnz     loc_18003CF67
0x18003cd07  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cd0e  cmp     rcx, r14
0x18003cd11  jz      loc_18003CDB6
0x18003cd17  cmp     byte ptr [rcx+19h], 4
0x18003cd1b  jb      loc_18003CDB6
0x18003cd21  test    byte ptr [rcx+1Ch], 10h
0x18003cd25  jz      loc_18003CDB6
0x18003cd2b  mov     rdx, cs:gIkeExtGlobals
0x18003cd32  test    rdx, rdx
0x18003cd35  jz      short loc_18003CD5D
0x18003cd37  mov     eax, [rdx+0D88h]
0x18003cd3d  cmp     eax, 0FFFFFFFFh
0x18003cd40  jz      short loc_18003CD5D
0x18003cd42  mov     ecx, eax; dwTlsIndex
0x18003cd44  call    cs:__imp_TlsGetValue
0x18003cd4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cd51  mov     r8, rax
0x18003cd54  mov     rdx, cs:gIkeExtGlobals
0x18003cd5b  jmp     short loc_18003CD60
0x18003cd5d  mov     r8, r13
0x18003cd60  test    r8, r8
0x18003cd63  lea     rsi, [r8+8]
0x18003cd67  cmovz   rsi, r13
0x18003cd6b  test    rdx, rdx
0x18003cd6e  jz      short loc_18003CD94
0x18003cd70  mov     eax, [rdx+0D88h]
0x18003cd76  cmp     eax, 0FFFFFFFFh
0x18003cd79  jz      short loc_18003CD94
0x18003cd7b  mov     ecx, eax; dwTlsIndex
0x18003cd7d  call    cs:__imp_TlsGetValue
0x18003cd83  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cd8a  test    rax, rax
0x18003cd8d  jz      short loc_18003CD94
0x18003cd8f  mov     r9, [rax]
0x18003cd92  jmp     short loc_18003CD97
0x18003cd94  mov     r9, r13
0x18003cd97  mov     rcx, [rcx+10h]
0x18003cd9b  lea     r8, WPP_4c56edd497003658c4b83fd296af3c1f_Traceguids
0x18003cda2  mov     edx, 33h ; '3'
0x18003cda7  mov     [rsp+130h+var_108], rbx
0x18003cdac  mov     [rsp+130h+var_110], rsi
0x18003cdb1  call    WPP_SF_iSq
0x18003cdb6  mov     eax, cs:dword_180173278
0x18003cdbc  cmp     eax, 4
0x18003cdbf  jbe     loc_18003CF03
0x18003cdc5  mov     rax, cs:gIkeExtGlobals
0x18003cdcc  test    rax, rax
0x18003cdcf  jz      short loc_18003CDFA
0x18003cdd1  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003cdd7  cmp     ecx, 0FFFFFFFFh
0x18003cdda  jz      short loc_18003CDFA
0x18003cddc  call    cs:__imp_TlsGetValue
0x18003cde2  test    rax, rax
0x18003cde5  jz      short loc_18003CDF3
0x18003cde7  mov     rcx, [rax]
0x18003cdea  mov     rax, cs:gIkeExtGlobals
0x18003cdf1  jmp     short loc_18003CDFD
0x18003cdf3  mov     rax, cs:gIkeExtGlobals
0x18003cdfa  mov     rcx, r13
0x18003cdfd  mov     [rbp+57h+var_D0], rcx
0x18003ce01  lea     rcx, [rbp+57h+var_D0]
0x18003ce05  mov     [rbp+57h+var_90], rcx
0x18003ce09  mov     [rbp+57h+var_88], 8
0x18003ce11  test    rax, rax
0x18003ce14  jz      short loc_18003CE55
0x18003ce16  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003ce1c  cmp     ecx, 0FFFFFFFFh
0x18003ce1f  jz      short loc_18003CE55
0x18003ce21  call    cs:__imp_TlsGetValue
0x18003ce27  test    rax, rax
0x18003ce2a  lea     rdx, [rax+8]
0x18003ce2e  cmovz   rdx, r13
0x18003ce32  test    rdx, rdx
0x18003ce35  jz      short loc_18003CE55
0x18003ce37  nop     word ptr [rax+rax+00000000h]
0x18003ce40  cmp     [rdx+rdi*2+2], r13w
0x18003ce46  lea     rdi, [rdi+1]
0x18003ce4a  jnz     short loc_18003CE40
0x18003ce4c  lea     edi, ds:2[rdi*2]
0x18003ce53  jmp     short loc_18003CE61
0x18003ce55  lea     rdx, LocaleName
0x18003ce5c  mov     edi, 2
0x18003ce61  mov     [rbp+57h+var_80], rdx
0x18003ce65  lea     rax, [rsp+130h+var_D8]
0x18003ce6a  mov     [rbp+57h+var_70], rax
0x18003ce6e  lea     rdx, [rbp+57h+var_C8]
0x18003ce72  movzx   eax, cs:word_18015D386
0x18003ce79  xor     r9d, r9d
0x18003ce7c  mov     [rbp+57h+var_C4], eax
0x18003ce7f  xor     r8d, r8d
0x18003ce82  mov     rax, cs:off_180173280
0x18003ce89  mov     [rbp+57h+var_B0], rax
0x18003ce8d  mov     [rbp+57h+var_78], edi
0x18003ce90  mov     [rbp+57h+var_74], r13d
0x18003ce94  mov     [rsp+130h+var_D8], rbx
0x18003ce99  mov     [rbp+57h+var_68], 8
0x18003cea1  mov     [rbp+57h+var_C8], 0B000000h
0x18003cea8  mov     [rbp+57h+var_C0], r13
0x18003ceac  movzx   eax, word ptr [rax]
0x18003ceaf  mov     [rbp+57h+var_A8], eax
0x18003ceb2  lea     rax, unk_18015D390
0x18003ceb9  mov     [rbp+57h+var_A0], rax
0x18003cebd  lea     rax, _TraceLoggingMetadata
0x18003cec4  sub     r12d, eax
0x18003cec7  mov     [rbp+57h+var_A4], 2
0x18003cece  mov     [rbp+57h+var_98], 3Bh ; ';'
0x18003ced5  mov     [rbp+57h+var_94], 1
0x18003cedc  mov     [rsp+130h+var_F0], r12d
0x18003cee1  mov     eax, [rsp+130h+var_F0]
0x18003cee5  mov     rcx, cs:qword_180173298
0x18003ceec  lea     rax, [rbp+57h+var_B0]
0x18003cef0  mov     [rsp+130h+var_108], rax
0x18003cef5  mov     dword ptr [rsp+130h+var_110], 5
  ... truncated ...
```
