# NcaEvCollSMBProbeCollect(NCA_EVCOLL_PROBE_ *,NCA_EVCOLL_USER_PROBES_ *)

- ea: `0x180011f80`
- end: `0x18001220b`
- name: `?NcaEvCollSMBProbeCollect@@YAXPEAUNCA_EVCOLL_PROBE_@@PEAUNCA_EVCOLL_USER_PROBES_@@@Z`
- size: `651`
- prototype: `void __fastcall(struct NCA_EVCOLL_PROBE_ *, struct NCA_EVCOLL_USER_PROBES_ *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180001e90`

## callees

- `0x180001c70`
- `0x1800025c0`
- `0x1800030b0`
- `0x180004f34`
- `0x180011f80`
- `0x1800126a0`
- `0x180012740`
- `0x180017e94`
- `0x180018fd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011fc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012010`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800121f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011fc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012010`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800121f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011fa6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011fe8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011ff7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011fa6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011fe8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011ff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800120d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800120d7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800120c5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800120c5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012199`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012199`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012122`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012122`

## pseudocode

```c
void __fastcall NcaEvCollSMBProbeCollect(struct NCA_EVCOLL_PROBE_ *a1, struct NCA_EVCOLL_USER_PROBES_ *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  int v5; // esi
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  unsigned int TestType; // esi
  struct NCA_USER_ *v9; // rax
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rcx
  BOOL v13; // ebp
  char *FileW; // rax
  int v15; // edx
  int v16; // edi
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rcx
  unsigned int v20; // [rsp+80h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 280);
  v20 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)a1 + 7);
  v5 = *((_DWORD *)a1 + 55);
  if ( !v5 )
    *((_DWORD *)a1 + 55) = 1;
  LeaveCriticalSection(v2);
  if ( v5 != 1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 232));
    EnterCriticalSection(v2);
    *((_DWORD *)a1 + 55) = 0;
    LeaveCriticalSection(v2);
    if ( *((_DWORD *)a1 + 54) )
    {
      NcaEvCollProbeRearm(a1);
      TestType = NcaEvCollProbeGetTestType(*(unsigned int *)(*((_QWORD *)a1 + 4) + 32LL), &v20);
      if ( ((TestType - 1) & 0xFFFFFFFD) != 0 )
      {
        v9 = NcaUserStoreFind(*(_DWORD *)(*((_QWORD *)a1 + 4) + 32LL));
        if ( v9 )
        {
          v13 = SetThreadToken(0, *((HANDLE *)v9 + 4));
          if ( !v13 )
            GetLastError();
          if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
            McTemplateU0qz_EventWriteTransfer(v12, v11, 4, *((_QWORD *)a1 + 1));
          FileW = (char *)CreateFileW(*((LPCWSTR *)a1 + 1), 0x80000000, 1u, 0, 4u, 0x20000000u, 0);
          v16 = 0;
          *((_QWORD *)a1 + 5) = FileW;
          if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            v16 = 2;
          if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
            McTemplateU0qzq_EventWriteTransfer(2, v15, 4, *((_QWORD *)a1 + 1), v16);
          v17 = v20;
          if ( *((_DWORD *)a1 + 56) != v16 || v20 == 1 && TestType == 2 && v16 == 2 )
          {
            v18 = *((_QWORD *)a1 + 4);
            *((_DWORD *)a1 + 56) = v16;
            NcaEvCollProbesUpdateEvidenceSummary(TestType, v17, *(unsigned int *)(v18 + 32), a2);
          }
          if ( v13 )
            RevertToSelf();
          goto LABEL_33;
        }
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 79;
          v10 = 1255;
LABEL_32:
          WPP_SF_d(v6[2], v7, &WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids, v10);
        }
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 78;
          goto LABEL_31;
        }
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 77;
LABEL_31:
        v10 = 0;
        goto LABEL_32;
      }
    }
LABEL_33:
    v19 = *((_QWORD *)a1 + 5);
    if ( v19 )
    {
      NcaCloseHandle(v19);
      *((_QWORD *)a1 + 5) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 232));
  }
}

```

## disassembly

```asm
0x180011f80  mov     rax, rsp
0x180011f83  push    rbx
0x180011f84  push    rbp
0x180011f85  push    rsi
0x180011f86  push    rdi
0x180011f87  push    r14
0x180011f89  push    r15
0x180011f8b  sub     rsp, 48h
0x180011f8f  lea     rdi, [rcx+118h]
0x180011f96  mov     dword ptr [rax+8], 0
0x180011f9d  mov     rbx, rcx
0x180011fa0  mov     r15, rdx
0x180011fa3  mov     rcx, rdi; lpCriticalSection
0x180011fa6  call    cs:__imp_EnterCriticalSection
0x180011fad  nop     dword ptr [rax+rax+00h]
0x180011fb2  mov     esi, [rbx+0DCh]
0x180011fb8  test    esi, esi
0x180011fba  jnz     short loc_180011FC6
0x180011fbc  mov     dword ptr [rbx+0DCh], 1
0x180011fc6  mov     rcx, rdi; lpCriticalSection
0x180011fc9  call    cs:__imp_LeaveCriticalSection
0x180011fd0  nop     dword ptr [rax+rax+00h]
0x180011fd5  cmp     esi, 1
0x180011fd8  jz      loc_1800121FD
0x180011fde  lea     r14, [rbx+0E8h]
0x180011fe5  mov     rcx, r14; lpCriticalSection
0x180011fe8  call    cs:__imp_EnterCriticalSection
0x180011fef  nop     dword ptr [rax+rax+00h]
0x180011ff4  mov     rcx, rdi; lpCriticalSection
0x180011ff7  call    cs:__imp_EnterCriticalSection
0x180011ffe  nop     dword ptr [rax+rax+00h]
0x180012003  mov     rcx, rdi; lpCriticalSection
0x180012006  mov     dword ptr [rbx+0DCh], 0
0x180012010  call    cs:__imp_LeaveCriticalSection
0x180012017  nop     dword ptr [rax+rax+00h]
0x18001201c  cmp     dword ptr [rbx+0D8h], 0
0x180012023  jnz     short loc_180012050
0x180012025  mov     rcx, cs:WPP_GLOBAL_Control
0x18001202c  lea     rax, WPP_GLOBAL_Control
0x180012033  cmp     rcx, rax
0x180012036  jz      loc_1800121D8
0x18001203c  test    byte ptr [rcx+1Ch], 1
0x180012040  jz      loc_1800121D8
0x180012046  mov     edx, 4Dh ; 'M'
0x18001204b  jmp     loc_1800121C5
0x180012050  mov     rcx, rbx; struct NCA_EVCOLL_PROBE_ *
0x180012053  call    ?NcaEvCollProbeRearm@@YAXPEAUNCA_EVCOLL_PROBE_@@@Z; NcaEvCollProbeRearm(NCA_EVCOLL_PROBE_ *)
0x180012058  mov     rcx, [rbx+20h]
0x18001205c  lea     rdx, [rsp+78h+arg_0]
0x180012064  mov     ecx, [rcx+20h]
0x180012067  call    ?NcaEvCollProbeGetTestType@@YA?AW4NCA_PROBE_TEST_TYPE_@@KPEAH@Z; NcaEvCollProbeGetTestType(ulong,int *)
0x18001206c  mov     esi, eax
0x18001206e  lea     ecx, [rax-1]
0x180012071  test    ecx, 0FFFFFFFDh
0x180012077  jz      loc_1800121A7
0x18001207d  mov     rcx, [rbx+20h]
0x180012081  mov     ecx, [rcx+20h]; unsigned int
0x180012084  call    ?NcaUserStoreFind@@YAPEAUNCA_USER_@@K@Z; NcaUserStoreFind(ulong)
0x180012089  test    rax, rax
0x18001208c  jnz     short loc_1800120BF
0x18001208e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012095  lea     rax, WPP_GLOBAL_Control
0x18001209c  cmp     rcx, rax
0x18001209f  jz      loc_1800121D8
0x1800120a5  test    byte ptr [rcx+1Ch], 1
0x1800120a9  jz      loc_1800121D8
0x1800120af  mov     edx, 4Fh ; 'O'
0x1800120b4  mov     r9d, 4E7h
0x1800120ba  jmp     loc_1800121C8
0x1800120bf  mov     rdx, [rax+20h]; Token
0x1800120c3  xor     ecx, ecx; Thread
0x1800120c5  call    cs:__imp_SetThreadToken
0x1800120cc  nop     dword ptr [rax+rax+00h]
0x1800120d1  mov     ebp, eax
0x1800120d3  test    eax, eax
0x1800120d5  jnz     short loc_1800120E3
0x1800120d7  call    cs:__imp_GetLastError
0x1800120de  nop     dword ptr [rax+rax+00h]
0x1800120e3  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x1800120ea  mov     edi, 4
0x1800120ef  jz      short loc_1800120FD
0x1800120f1  mov     r9, [rbx+8]
0x1800120f5  mov     r8d, edi
0x1800120f8  call    McTemplateU0qz_EventWriteTransfer
0x1800120fd  mov     rcx, [rbx+8]; lpFileName
0x180012101  xor     r9d, r9d; lpSecurityAttributes
0x180012104  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18001210d  mov     edx, 80000000h; dwDesiredAccess
0x180012112  mov     [rsp+78h+dwFlagsAndAttributes], 20000000h; dwFlagsAndAttributes
0x18001211a  mov     [rsp+78h+dwCreationDisposition], edi; dwCreationDisposition
0x18001211e  lea     r8d, [r9+1]; dwShareMode
0x180012122  call    cs:__imp_CreateFileW
0x180012129  nop     dword ptr [rax+rax+00h]
0x18001212e  xor     edi, edi
0x180012130  mov     [rbx+28h], rax
0x180012134  dec     rax
0x180012137  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001213b  lea     ecx, [rdi+2]
0x18001213e  cmovbe  edi, ecx
0x180012141  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180012148  jz      short loc_180012160
0x18001214a  mov     r9, [rbx+8]
0x18001214e  lea     r8d, [rcx+2]
0x180012152  mov     [rsp+78h+dwCreationDisposition], edi
0x180012156  call    McTemplateU0qzq_EventWriteTransfer
0x18001215b  mov     ecx, 2
0x180012160  mov     edx, [rsp+78h+arg_0]
0x180012167  cmp     [rbx+0E0h], edi
0x18001216d  jnz     short loc_18001217C
0x18001216f  cmp     edx, 1
0x180012172  jnz     short loc_180012194
0x180012174  cmp     esi, ecx
0x180012176  jnz     short loc_180012194
0x180012178  cmp     edi, ecx
0x18001217a  jnz     short loc_180012194
0x18001217c  mov     r8, [rbx+20h]
0x180012180  mov     r9, r15
0x180012183  mov     [rbx+0E0h], edi
0x180012189  mov     ecx, esi
0x18001218b  mov     r8d, [r8+20h]
0x18001218f  call    ?NcaEvCollProbesUpdateEvidenceSummary@@YAXW4NCA_PROBE_TEST_TYPE_@@HKPEAUNCA_EVCOLL_USER_PROBES_@@@Z; NcaEvCollProbesUpdateEvidenceSummary(NCA_PROBE_TEST_TYPE_,int,ulong,NCA_EVCOLL_USER_PROBES_ *)
0x180012194  cmp     ebp, 1
0x180012197  jnz     short loc_1800121D8
0x180012199  call    cs:__imp_RevertToSelf
0x1800121a0  nop     dword ptr [rax+rax+00h]
0x1800121a5  jmp     short loc_1800121D8
0x1800121a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800121ae  lea     rax, WPP_GLOBAL_Control
0x1800121b5  cmp     rcx, rax
0x1800121b8  jz      short loc_1800121D8
0x1800121ba  test    byte ptr [rcx+1Ch], 1
0x1800121be  jz      short loc_1800121D8
0x1800121c0  mov     edx, 4Eh ; 'N'
0x1800121c5  xor     r9d, r9d
0x1800121c8  mov     rcx, [rcx+10h]
0x1800121cc  lea     r8, WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids
0x1800121d3  call    WPP_SF_d
0x1800121d8  mov     rcx, [rbx+28h]
0x1800121dc  test    rcx, rcx
0x1800121df  jz      short loc_1800121EE
0x1800121e1  call    NcaCloseHandle
0x1800121e6  mov     qword ptr [rbx+28h], 0
0x1800121ee  mov     rcx, r14; lpCriticalSection
0x1800121f1  call    cs:__imp_LeaveCriticalSection
0x1800121f8  nop     dword ptr [rax+rax+00h]
0x1800121fd  add     rsp, 48h
0x180012201  pop     r15
0x180012203  pop     r14
0x180012205  pop     rdi
0x180012206  pop     rsi
0x180012207  pop     rbp
0x180012208  pop     rbx
0x180012209  retn
```
