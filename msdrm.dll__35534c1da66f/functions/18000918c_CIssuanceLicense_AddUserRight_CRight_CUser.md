# CIssuanceLicense::AddUserRight(CRight *,CUser *)

- ea: `0x18000918c`
- end: `0x180009597`
- name: `?AddUserRight@CIssuanceLicense@@QEAAJPEAVCRight@@PEAVCUser@@@Z`
- size: `1035`
- prototype: `int(CIssuanceLicense *__hidden this, struct CRight *, struct CUser *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004780`
- `0x180014b20`

## callees

- `0x180001284`
- `0x180001290`
- `0x180003416`
- `0x180008c28`
- `0x18000901c`
- `0x1800090b8`
- `0x18000918c`
- `0x18000d784`
- `0x18001ef30`
- `0x18001ff54`
- `0x18001ffd8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180009289`
- `msvcrt!_wcsicmp` at `0x18000937b`
- `msvcrt!_wcsicmp` at `0x180009289`
- `msvcrt!_wcsicmp` at `0x18000937b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009260`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000927d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800092a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800092cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000934d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000936e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009560`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009577`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009260`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000927d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800092a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800092cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000934d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000936e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009560`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009577`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800091c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009250`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000926d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000929a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800092c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000933d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000935d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800094c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800091c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009250`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000926d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000929a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800092c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000933d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000935d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800094c0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800092f9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800092f9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800092b5`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800092e1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800092b5`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800092e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CIssuanceLicense::AddUserRight(CIssuanceLicense *this, struct CRight *a2, struct CUser *a3)
{
  struct CUser *v3; // r12
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  unsigned int v7; // ebp
  __int64 v8; // rdi
  char *v9; // r15
  CDRMCBase *v10; // rcx
  struct CRight *v11; // r14
  struct _RTL_CRITICAL_SECTION *v12; // rbp
  const wchar_t *v13; // rsi
  const wchar_t *v14; // rdi
  unsigned int ExtendedInfoCount; // edi
  CRight *v16; // r12
  __int64 v17; // rsi
  __int64 v18; // rdi
  __int64 v19; // rbp
  const wchar_t *v20; // rsi
  __int64 v21; // rdi
  int v22; // edi
  _QWORD *v23; // rsi
  struct CUser *v24; // rbp
  int v25; // r12d
  unsigned int v26; // r13d
  __int64 v27; // rsi
  CDRMCBase *v28; // rcx
  struct CUser *v29; // rbp
  unsigned int v31; // [rsp+20h] [rbp-68h]
  unsigned int v32; // [rsp+24h] [rbp-64h]
  FILETIME FileTime2; // [rsp+28h] [rbp-60h] BYREF
  struct _FILETIME FileTime; // [rsp+30h] [rbp-58h] BYREF
  __int64 v35; // [rsp+38h] [rbp-50h]
  char *v36; // [rsp+40h] [rbp-48h]
  int v39; // [rsp+A8h] [rbp+20h]

  v35 = -2;
  v3 = a3;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  v36 = (char *)this + 88;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v7 = *((_DWORD *)this + 34);
  v31 = v7;
  v8 = 0;
  v39 = 0;
  v9 = (char *)this + 128;
  if ( v7 )
  {
    while ( 1 )
    {
      if ( (unsigned int)v8 < *((_DWORD *)v9 + 2) )
      {
        v10 = *(CDRMCBase **)(*(_QWORD *)v9 + 8 * v8);
        if ( v10 )
        {
          CDRMCBase::AddRef(v10);
          v11 = *(struct CRight **)(*(_QWORD *)v9 + 8 * v8);
          if ( v11 )
          {
            if ( (unsigned int)CDRMCBase::IsDeleted(*(CDRMCBase **)(*(_QWORD *)v9 + 8 * v8)) )
            {
              v16 = v11;
            }
            else
            {
              FileTime = 0;
              FileTime2 = 0;
              if ( v11 == a2 )
              {
                v16 = v11;
LABEL_27:
                v24 = a3;
                v22 = CRight::AddUser(v16, a3);
LABEL_33:
                if ( !v22 )
                  goto LABEL_36;
                goto LABEL_49;
              }
              v12 = (struct _RTL_CRITICAL_SECTION *)((char *)a2 + 88);
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 88));
              v13 = (const wchar_t *)*((_QWORD *)a2 + 19);
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 88));
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 88));
              v14 = (const wchar_t *)*((_QWORD *)v11 + 19);
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 88));
              if ( _wcsicmp(v14, v13)
                || (EnterCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 88)),
                    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 88)),
                    !SystemTimeToFileTime((const SYSTEMTIME *)v11 + 10, &FileTime))
                || (EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 88)),
                    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 88)),
                    !SystemTimeToFileTime((const SYSTEMTIME *)a2 + 10, &FileTime2))
                || CompareFileTime(&FileTime, &FileTime2) )
              {
                v16 = v11;
              }
              else
              {
                ExtendedInfoCount = CRight::GetExtendedInfoCount(v11);
                v16 = v11;
                if ( ExtendedInfoCount == CRight::GetExtendedInfoCount(a2) )
                {
                  v17 = 0;
                  v32 = 0;
                  if ( !CRight::GetExtendedInfoCount(v11) )
                    goto LABEL_27;
                  while ( 1 )
                  {
                    EnterCriticalSection(v12);
                    v18 = *((_QWORD *)a2 + 25);
                    LeaveCriticalSection(v12);
                    v19 = (unsigned int)v17;
                    v20 = *(const wchar_t **)(v18 + 8 * v17);
                    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 88));
                    v21 = *((_QWORD *)v11 + 25);
                    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 88));
                    if ( _wcsicmp(*(const wchar_t **)(v21 + 8 * v19), v20) )
                      break;
                    v17 = ++v32;
                    if ( v32 >= CRight::GetExtendedInfoCount(v11) )
                      goto LABEL_27;
                    v12 = (struct _RTL_CRITICAL_SECTION *)((char *)a2 + 88);
                  }
                }
              }
              v7 = v31;
              LODWORD(v8) = v39;
            }
            CDRMCBase::Release(v16);
          }
        }
      }
      v8 = (unsigned int)(v8 + 1);
      v39 = v8;
      if ( (unsigned int)v8 >= v7 )
      {
        v3 = a3;
        break;
      }
    }
  }
  v11 = a2;
  if ( a2 )
  {
    CDRMCBase::AddRef(a2);
    v22 = CRight::AddUser(a2, v3);
    if ( v22 >= 0 )
    {
      v23 = operator new[](saturated_mul((unsigned int)(*((_DWORD *)v9 + 2) + 1), 8u));
      if ( v23 )
      {
        v22 = 0;
        v23[*((unsigned int *)v9 + 2)] = a2;
        CDRMCBase::AddRef(a2);
        if ( *(_QWORD *)v9 )
          memcpy_0(v23, *(const void **)v9, 8LL * *((unsigned int *)v9 + 2));
        operator delete(*(void **)v9);
        *(_QWORD *)v9 = v23;
        ++*((_DWORD *)v9 + 2);
      }
      else
      {
        v22 = -2147024882;
      }
      operator delete(0);
    }
    v24 = a3;
    goto LABEL_33;
  }
  v24 = a3;
LABEL_36:
  EnterCriticalSection(v6);
  v22 = 0;
  v25 = 1;
  v26 = *((_DWORD *)this + 50);
  v27 = 0;
  if ( v26 )
  {
    while ( 1 )
    {
      if ( (unsigned int)v27 < *((_DWORD *)this + 50) )
      {
        v28 = *(CDRMCBase **)(*((_QWORD *)this + 24) + 8 * v27);
        if ( v28 )
        {
          CDRMCBase::AddRef(v28);
          v29 = *(struct CUser **)(*((_QWORD *)this + 24) + 8 * v27);
          if ( v29 )
          {
            if ( v29 == a3 || (unsigned int)CUser::operator==(v29, a3) )
              v25 = 0;
            CDRMCBase::Release(v29);
          }
        }
      }
      if ( !v25 )
        break;
      v27 = (unsigned int)(v27 + 1);
      if ( (unsigned int)v27 >= v26 )
      {
        v24 = a3;
        goto LABEL_47;
      }
    }
  }
  else
  {
LABEL_47:
    v22 = CPubSet<CUser>::Add((char *)this + 192, v24);
  }
  LeaveCriticalSection(v6);
LABEL_49:
  if ( v11 )
    CDRMCBase::Release(v11);
  LeaveCriticalSection(v6);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x18000918c  mov     rax, rsp
0x18000918f  mov     [rax+18h], r8
0x180009193  mov     [rax+8], rcx
0x180009197  push    rbp
0x180009198  push    rsi
0x180009199  push    rdi
0x18000919a  push    r12
0x18000919c  push    r13
0x18000919e  push    r14
0x1800091a0  push    r15
0x1800091a2  sub     rsp, 50h
0x1800091a6  mov     qword ptr [rax-50h], 0FFFFFFFFFFFFFFFEh
0x1800091ae  mov     [rax+10h], rbx
0x1800091b2  mov     r12, r8
0x1800091b5  mov     r13, rdx
0x1800091b8  mov     rsi, rcx
0x1800091bb  lea     rbx, [rcx+58h]
0x1800091bf  mov     [rax-48h], rbx
0x1800091c3  mov     rcx, rbx; lpCriticalSection
0x1800091c6  call    cs:__imp_EnterCriticalSection
0x1800091cc  nop
0x1800091cd  mov     ebp, [rsi+88h]
0x1800091d3  mov     [rsp+88h+var_68], ebp
0x1800091d7  xor     edi, edi
0x1800091d9  mov     dword ptr [rsp+88h+arg_18], edi
0x1800091e0  lea     r15, [rsi+80h]
0x1800091e7  test    ebp, ebp
0x1800091e9  jz      loc_1800093E0
0x1800091ef  cmp     edi, [r15+8]
0x1800091f3  jnb     loc_1800093BB
0x1800091f9  mov     rax, [r15]
0x1800091fc  mov     rcx, [rax+rdi*8]; this
0x180009200  test    rcx, rcx
0x180009203  jz      loc_1800093BB
0x180009209  call    ?AddRef@CDRMCBase@@QEAAKXZ; CDRMCBase::AddRef(void)
0x18000920e  mov     rax, [r15]
0x180009211  mov     r14, [rax+rdi*8]
0x180009215  test    r14, r14
0x180009218  jz      loc_1800093BE
0x18000921e  mov     rcx, r14; this
0x180009221  call    ?IsDeleted@CDRMCBase@@QEAAHXZ; CDRMCBase::IsDeleted(void)
0x180009226  test    eax, eax
0x180009228  jnz     loc_180009439
0x18000922e  mov     qword ptr [rsp+88h+FileTime.dwLowDateTime], 0
0x180009237  mov     qword ptr [rsp+88h+FileTime2.dwLowDateTime], 0
0x180009240  cmp     r14, r13
0x180009243  jz      loc_180009441
0x180009249  lea     rbp, [r13+58h]
0x18000924d  mov     rcx, rbp; lpCriticalSection
0x180009250  call    cs:__imp_EnterCriticalSection
0x180009256  mov     rsi, [r13+98h]
0x18000925d  mov     rcx, rbp; lpCriticalSection
0x180009260  call    cs:__imp_LeaveCriticalSection
0x180009266  lea     r12, [r14+58h]
0x18000926a  mov     rcx, r12; lpCriticalSection
0x18000926d  call    cs:__imp_EnterCriticalSection
0x180009273  mov     rdi, [r14+98h]
0x18000927a  mov     rcx, r12; lpCriticalSection
0x18000927d  call    cs:__imp_LeaveCriticalSection
0x180009283  mov     rdx, rsi; String2
0x180009286  mov     rcx, rdi; String1
0x180009289  call    cs:__imp__wcsicmp
0x18000928f  test    eax, eax
0x180009291  jnz     loc_1800093A5
0x180009297  mov     rcx, r12; lpCriticalSection
0x18000929a  call    cs:__imp_EnterCriticalSection
0x1800092a0  mov     rcx, r12; lpCriticalSection
0x1800092a3  call    cs:__imp_LeaveCriticalSection
0x1800092a9  lea     rcx, [r14+0A0h]; lpSystemTime
0x1800092b0  lea     rdx, [rsp+88h+FileTime]; lpFileTime
0x1800092b5  call    cs:__imp_SystemTimeToFileTime
0x1800092bb  test    eax, eax
0x1800092bd  jz      loc_1800093A5
0x1800092c3  mov     rcx, rbp; lpCriticalSection
0x1800092c6  call    cs:__imp_EnterCriticalSection
0x1800092cc  mov     rcx, rbp; lpCriticalSection
0x1800092cf  call    cs:__imp_LeaveCriticalSection
0x1800092d5  lea     rcx, [r13+0A0h]; lpSystemTime
0x1800092dc  lea     rdx, [rsp+88h+FileTime2]; lpFileTime
0x1800092e1  call    cs:__imp_SystemTimeToFileTime
0x1800092e7  test    eax, eax
0x1800092e9  jz      loc_1800093A5
0x1800092ef  lea     rdx, [rsp+88h+FileTime2]; lpFileTime2
0x1800092f4  lea     rcx, [rsp+88h+FileTime]; lpFileTime1
0x1800092f9  call    cs:__imp_CompareFileTime
0x1800092ff  test    eax, eax
0x180009301  jnz     loc_1800093A5
0x180009307  mov     rcx, r14; this
0x18000930a  call    ?GetExtendedInfoCount@CRight@@QEAAIXZ; CRight::GetExtendedInfoCount(void)
0x18000930f  mov     edi, eax
0x180009311  mov     rcx, r13; this
0x180009314  call    ?GetExtendedInfoCount@CRight@@QEAAIXZ; CRight::GetExtendedInfoCount(void)
0x180009319  mov     r12, r14
0x18000931c  cmp     edi, eax
0x18000931e  jnz     loc_1800093A8
0x180009324  xor     esi, esi
0x180009326  mov     [rsp+88h+var_64], esi
0x18000932a  mov     rcx, r14; this
0x18000932d  call    ?GetExtendedInfoCount@CRight@@QEAAIXZ; CRight::GetExtendedInfoCount(void)
0x180009332  test    eax, eax
0x180009334  jz      loc_180009444
0x18000933a  mov     rcx, rbp; lpCriticalSection
0x18000933d  call    cs:__imp_EnterCriticalSection
0x180009343  mov     rdi, [r13+0C8h]
0x18000934a  mov     rcx, rbp; lpCriticalSection
0x18000934d  call    cs:__imp_LeaveCriticalSection
0x180009353  mov     ebp, esi
0x180009355  mov     rsi, [rdi+rsi*8]
0x180009359  lea     rcx, [r14+58h]; lpCriticalSection
0x18000935d  call    cs:__imp_EnterCriticalSection
0x180009363  mov     rdi, [r14+0C8h]
0x18000936a  lea     rcx, [r14+58h]; lpCriticalSection
0x18000936e  call    cs:__imp_LeaveCriticalSection
0x180009374  mov     rdx, rsi; String2
0x180009377  mov     rcx, [rdi+rbp*8]; String1
0x18000937b  call    cs:__imp__wcsicmp
0x180009381  test    eax, eax
0x180009383  jnz     short loc_1800093A8
0x180009385  mov     esi, [rsp+88h+var_64]
0x180009389  inc     esi
0x18000938b  mov     [rsp+88h+var_64], esi
0x18000938f  mov     rcx, r14; this
0x180009392  call    ?GetExtendedInfoCount@CRight@@QEAAIXZ; CRight::GetExtendedInfoCount(void)
0x180009397  cmp     esi, eax
0x180009399  jnb     loc_180009444
0x18000939f  lea     rbp, [r13+58h]
0x1800093a3  jmp     short loc_18000933A
0x1800093a5  mov     r12, r14
0x1800093a8  mov     ebp, [rsp+88h+var_68]
0x1800093ac  mov     edi, dword ptr [rsp+88h+arg_18]
0x1800093b3  mov     rcx, r12; this
0x1800093b6  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x1800093bb  xor     r14d, r14d
0x1800093be  inc     edi
0x1800093c0  mov     dword ptr [rsp+88h+arg_18], edi
0x1800093c7  cmp     edi, ebp
0x1800093c9  jb      loc_1800091EF
0x1800093cf  test    r14, r14
0x1800093d2  jnz     loc_1800094AD
0x1800093d8  mov     r12, [rsp+88h+arg_10]
0x1800093e0  mov     r14, r13
0x1800093e3  test    r13, r13
0x1800093e6  jz      loc_1800094AD
0x1800093ec  mov     rcx, r13; this
0x1800093ef  call    ?AddRef@CDRMCBase@@QEAAKXZ; CDRMCBase::AddRef(void)
0x1800093f4  mov     rdx, r12; struct CUser *
0x1800093f7  mov     rcx, r13; this
0x1800093fa  call    ?AddUser@CRight@@QEAAJPEAVCUser@@@Z; CRight::AddUser(CUser *)
0x1800093ff  mov     edi, eax
0x180009401  test    eax, eax
0x180009403  js      loc_18000949B
0x180009409  mov     ecx, [r15+8]
0x18000940d  inc     ecx
0x18000940f  mov     eax, 8
0x180009414  mul     rcx
0x180009417  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000941e  cmovb   rax, rcx
0x180009422  mov     rcx, rax; unsigned __int64
0x180009425  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000942a  mov     rsi, rax
0x18000942d  test    rax, rax
0x180009430  jnz     short loc_18000945B
0x180009432  mov     edi, 8007000Eh
0x180009437  jmp     short loc_180009494
0x180009439  mov     r12, r14
0x18000943c  jmp     loc_1800093B3
0x180009441  mov     r12, r14
0x180009444  mov     rbp, [rsp+88h+arg_10]
0x18000944c  mov     rdx, rbp; struct CUser *
0x18000944f  mov     rcx, r12; this
0x180009452  call    ?AddUser@CRight@@QEAAJPEAVCUser@@@Z; CRight::AddUser(CUser *)
0x180009457  mov     edi, eax
0x180009459  jmp     short loc_1800094A3
0x18000945b  xor     edi, edi
0x18000945d  mov     eax, [r15+8]
0x180009461  mov     [rsi+rax*8], r13
0x180009465  mov     rcx, r13; this
0x180009468  call    ?AddRef@CDRMCBase@@QEAAKXZ; CDRMCBase::AddRef(void)
0x18000946d  mov     rdx, [r15]; Src
0x180009470  test    rdx, rdx
0x180009473  jz      short loc_180009485
0x180009475  mov     r8d, [r15+8]
0x180009479  shl     r8, 3; Size
0x18000947d  mov     rcx, rsi; void *
0x180009480  call    memcpy_0
0x180009485  mov     rcx, [r15]; Block
0x180009488  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000948d  mov     [r15], rsi
0x180009490  inc     dword ptr [r15+8]
0x180009494  xor     ecx, ecx; Block
0x180009496  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000949b  mov     rbp, [rsp+88h+arg_10]
0x1800094a3  test    edi, edi
0x1800094a5  jnz     loc_180009566
0x1800094ab  jmp     short loc_1800094B5
0x1800094ad  mov     rbp, [rsp+88h+arg_10]
0x1800094b5  mov     [rsp+88h+arg_18], rbx
0x1800094bd  mov     rcx, rbx; lpCriticalSection
0x1800094c0  call    cs:__imp_EnterCriticalSection
0x1800094c6  nop
0x1800094c7  xor     edi, edi
0x1800094c9  lea     r12d, [rdi+1]
0x1800094cd  mov     r15, [rsp+88h+arg_0]
0x1800094d5  mov     r13d, [r15+0C8h]
0x1800094dc  xor     esi, esi
0x1800094de  test    r13d, r13d
0x1800094e1  jz      short loc_18000954C
0x1800094e3  cmp     esi, [r15+0C8h]
0x1800094ea  jnb     short loc_180009538
0x1800094ec  mov     rax, [r15+0C0h]
0x1800094f3  mov     rcx, [rax+rsi*8]; this
0x1800094f7  test    rcx, rcx
0x1800094fa  jz      short loc_180009538
0x1800094fc  call    ?AddRef@CDRMCBase@@QEAAKXZ; CDRMCBase::AddRef(void)
0x180009501  mov     rax, [r15+0C0h]
0x180009508  mov     rbp, [rax+rsi*8]
0x18000950c  test    rbp, rbp
0x18000950f  jz      short loc_180009538
0x180009511  mov     rax, [rsp+88h+arg_10]
0x180009519  cmp     rbp, rax
0x18000951c  jz      short loc_18000952D
0x18000951e  mov     rdx, rax
0x180009521  mov     rcx, rbp
0x180009524  call    ??8CUser@@QEAAHPEAV0@@Z; CUser::operator==(CUser *)
0x180009529  test    eax, eax
0x18000952b  jz      short loc_180009530
0x18000952d  xor     r12d, r12d
0x180009530  mov     rcx, rbp; this
0x180009533  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x180009538  test    r12d, r12d
0x18000953b  jz      short loc_18000955D
0x18000953d  inc     esi
0x18000953f  cmp     esi, r13d
0x180009542  jb      short loc_1800094E3
0x180009544  mov     rbp, [rsp+88h+arg_10]
0x18000954c  mov     rdx, rbp
0x18000954f  lea     rcx, [r15+0C0h]
0x180009556  call    ?Add@?$CPubSet@VCUser@@@@QEAAJPEAVCUser@@@Z; CPubSet<CUser>::Add(CUser *)
0x18000955b  mov     edi, eax
0x18000955d  mov     rcx, rbx; lpCriticalSection
0x180009560  call    cs:__imp_LeaveCriticalSection
0x180009566  test    r14, r14
0x180009569  jz      short loc_180009574
0x18000956b  mov     rcx, r14; this
0x18000956e  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x180009573  nop
0x180009574  mov     rcx, rbx; lpCriticalSection
0x180009577  call    cs:__imp_LeaveCriticalSection
0x18000957d  mov     eax, edi
0x18000957f  mov     rbx, [rsp+88h+arg_8]
0x180009587  add     rsp, 50h
0x18000958b  pop     r15
0x18000958d  pop     r14
0x18000958f  pop     r13
0x180009591  pop     r12
0x180009593  pop     rdi
0x180009594  pop     rsi
0x180009595  pop     rbp
0x180009596  retn
```
