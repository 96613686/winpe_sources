# DsRolerAbortDownlevelServerUpgrade

- ea: `0x180005400`
- end: `0x180005850`
- name: `DsRolerAbortDownlevelServerUpgrade`
- size: `1104`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003d84`
- `0x180004ef8`
- `0x180005400`
- `0x180008ea4`
- `0x180013c50`
- `0x180014e30`
- `0x1800150cc`
- `0x180015670`
- `0x180015ff0`
- `0x1800161a8`
- `0x18001f048`
- `0x180020084`
- `0x180020b08`
- `0x180020dbc`
- `0x18002c01e`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180005620`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180005620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005680`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000573f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005680`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000573f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005794`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005817`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005817`
- `ntdll!RtlFreeHeap` at `0x180005807`
- `ntdll!RtlFreeHeap` at `0x180005807`
- `CRYPT32!CryptProtectMemory` at `0x1800055dc`
- `CRYPT32!CryptProtectMemory` at `0x1800056ea`
- `CRYPT32!CryptProtectMemory` at `0x18000578a`
- `CRYPT32!CryptProtectMemory` at `0x1800055dc`
- `CRYPT32!CryptProtectMemory` at `0x1800056ea`
- `CRYPT32!CryptProtectMemory` at `0x18000578a`
- `CRYPT32!CryptUnprotectMemory` at `0x18000554f`
- `CRYPT32!CryptUnprotectMemory` at `0x1800056bb`
- `CRYPT32!CryptUnprotectMemory` at `0x180005735`
- `CRYPT32!CryptUnprotectMemory` at `0x18000554f`
- `CRYPT32!CryptUnprotectMemory` at `0x1800056bb`
- `CRYPT32!CryptUnprotectMemory` at `0x180005735`
- `netutils!NetApiBufferFree` at `0x1800057e6`
- `netutils!NetApiBufferFree` at `0x1800057e6`
- `SCECLI!SceSetupSystemByInfName` at `0x180005678`
- `SCECLI!SceSetupSystemByInfName` at `0x180005678`

## string_xrefs

- `0x1800055c1`: `Moved account %ws to %ws\n`
- `0x1800055f6`: `Setting security for server ...\n`
- `0x180005647`: `\security\logs\scesetup.log`
- `0x18000568d`: `Setting security on server files failed with %lu\n`
- `0x18000569e`: `Setting security for server finished\n`
- `0x1800057c1`: `Attempted to move account %ws to %ws\n`

## pseudocode

```c
__int64 __fastcall DsRolerAbortDownlevelServerUpgrade(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5)
{
  __int64 v7; // rdx
  unsigned int ImpersonationToken; // ebx
  DWORD v9; // r14d
  WCHAR *v10; // r12
  DWORD v11; // esi
  void *v12; // r15
  int v13; // eax
  char v14; // r13
  __int64 v15; // rax
  DWORD LastError; // eax
  int v17; // r14d
  LPVOID v19; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h]
  LPVOID pDataIn[2]; // [rsp+60h] [rbp-A0h] BYREF
  PCWSTR SourceString[2]; // [rsp+70h] [rbp-90h]
  _QWORD v24[2]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+90h] [rbp-70h] BYREF

  v21 = a2;
  v19 = 0;
  hObject = 0;
  *(_OWORD *)pDataIn = 0;
  v24[0] = a3;
  *(_OWORD *)SourceString = 0;
  v24[1] = a4;
  ImpersonationToken = DsRolepInitializeOperationHandle(a1, a2);
  if ( !ImpersonationToken )
  {
    ImpersonationToken = DsRolepCheckClientAccess(DsRolepPromoteSD, v7, 0);
    if ( !ImpersonationToken )
    {
      ImpersonationToken = DsRolepDecryptPasswordsWithKey(a1, (__int64)v24, 2u, (__int64)pDataIn, 0);
      if ( !ImpersonationToken )
      {
        v9 = WORD1(SourceString[0]);
        v10 = (WCHAR *)SourceString[1];
        v11 = WORD1(pDataIn[0]);
        v12 = pDataIn[1];
        DsRolepInitializeLogHelper(1u);
        if ( (a5 & 1) != 0 )
        {
          DsRolepLogPrintRoutine(ImpersonationToken + 4, "Performing NT4 to NT5 BDC upgrade.\n");
          ImpersonationToken = 0;
        }
        else
        {
          ImpersonationToken = DsRolepGetImpersonationToken(&hObject);
          if ( !ImpersonationToken )
          {
            ImpersonationToken = DsRolepDsGetDcForAccount(0, 0, 0, 20497, 0x2000u, (_QWORD **)&v19);
            if ( !ImpersonationToken )
            {
              DsRolepLogPrintRoutine(4, "Searching for the machine account ...\n");
              if ( !(_WORD)v11 || CryptUnprotectMemory(v12, v11, 0) )
              {
                v13 = DsRolepSetMachineAccountType(*(_QWORD *)v19, hObject, a2, v12);
                ImpersonationToken = v13;
                if ( v13 )
                {
                  v14 = 0;
                  DsRolepLogPrintRoutine(4, "DsRolepSetMachineAccountType returned %d\n", v13);
                }
                else
                {
                  v14 = 1;
                }
                if ( (_WORD)v11 && !CryptProtectMemory(v12, v11, 0) )
                  ImpersonationToken = GetLastError();
                if ( !ImpersonationToken )
                {
                  DsRolepLogPrintRoutine(4, "Setting security for server ...\n");
                  memset_0(Buffer, 0, 0x20Au);
                  if ( GetWindowsDirectoryW(Buffer, 0x104u) )
                  {
                    Buffer[260] = 0;
                    v15 = -1;
                    do
                      ++v15;
                    while ( Buffer[v15] );
                    StringCchCatNW(Buffer, (size_t)Buffer, L"\\security\\logs\\scesetup.log", 260 - v15);
                    LastError = SceSetupSystemByInfName(L"defltsv.inf", Buffer, 96, 0, 0, 0);
                  }
                  else
                  {
                    LastError = GetLastError();
                  }
                  if ( LastError )
                    DsRolepLogPrintRoutine(1, "Setting security on server files failed with %lu\n", LastError);
                  DsRolepLogPrintRoutine(4, "Setting security for server finished\n");
                  if ( (_WORD)v9 )
                  {
                    if ( !CryptUnprotectMemory(v10, v9, 0) )
                    {
                      ImpersonationToken = GetLastError();
                      if ( ImpersonationToken )
                        goto LABEL_33;
                    }
                  }
                  ImpersonationToken = DsRolepSetBuiltinAdminAccountPassword(v10);
                  if ( (_WORD)v9 && !CryptProtectMemory(v10, v9, 0) )
                    ImpersonationToken = GetLastError();
                  if ( ImpersonationToken || (ImpersonationToken = DsRolepDeleteUpgradeInfo()) != 0 )
                  {
LABEL_33:
                    if ( v14 )
                    {
                      v17 = 0;
                      if ( (_WORD)v11 && !CryptUnprotectMemory(v12, v11, 0) )
                        ImpersonationToken = GetLastError();
                      if ( !ImpersonationToken )
                        v17 = DsRolepSetMachineAccountType(*(_QWORD *)v19, hObject, v21, v12);
                      if ( (_WORD)v11 && !CryptProtectMemory(v12, v11, 0) )
                        ImpersonationToken = GetLastError();
                      if ( v17 )
                        DsRolepLogPrintRoutine(4, "DsRolepSetMachineAccountType returned %d\n", v17);
                    }
                  }
                }
              }
              else
              {
                ImpersonationToken = GetLastError();
              }
            }
          }
        }
      }
    }
  }
  DsRolepFreePasswords(pDataIn, 2);
  NetApiBufferFree(v19);
  if ( hObject )
    CloseHandle(hObject);
  DsRolepResetOperationHandle(0);
  return ImpersonationToken;
}

```

## disassembly

```asm
0x180005400  mov     [rsp-8+arg_10], rbx
0x180005405  push    rbp
0x180005406  push    rsi
0x180005407  push    rdi
0x180005408  push    r12
0x18000540a  push    r13
0x18000540c  push    r14
0x18000540e  push    r15
0x180005410  lea     rbp, [rsp-1B0h]
0x180005418  sub     rsp, 2B0h
0x18000541f  mov     rax, cs:__security_cookie
0x180005426  xor     rax, rsp
0x180005429  mov     [rbp+1E0h+var_40], rax
0x180005430  xor     r12d, r12d
0x180005433  mov     [rsp+2E0h+var_288], rdx
0x180005438  xorps   xmm0, xmm0
0x18000543b  mov     [rsp+2E0h+var_298], r12
0x180005440  mov     [rsp+2E0h+P], r12
0x180005445  mov     r13, rdx
0x180005448  mov     [rsp+2E0h+hObject], r12
0x18000544d  mov     rdi, rcx
0x180005450  movups  xmmword ptr [rsp+2E0h+pDataIn], xmm0
0x180005455  mov     [rbp+1E0h+var_260], r8
0x180005459  movups  xmmword ptr [rsp+2E0h+SourceString], xmm0
0x18000545e  mov     [rbp+1E0h+var_258], r9
0x180005462  call    DsRolepInitializeOperationHandle
0x180005467  mov     ebx, eax
0x180005469  test    eax, eax
0x18000546b  jnz     loc_1800057D2
0x180005471  xor     r8d, r8d
0x180005474  lea     rcx, DsRolepPromoteSD; pSecurityDescriptor
0x18000547b  call    DsRolepCheckClientAccess
0x180005480  mov     ebx, eax
0x180005482  test    eax, eax
0x180005484  jnz     loc_1800057D2
0x18000548a  lea     r9, [rsp+2E0h+pDataIn]
0x18000548f  mov     [rsp+2E0h+var_2C0], r12
0x180005494  lea     r8d, [r12+2]
0x180005499  mov     rcx, rdi
0x18000549c  lea     rdx, [rbp+1E0h+var_260]
0x1800054a0  call    DsRolepDecryptPasswordsWithKey
0x1800054a5  mov     ebx, eax
0x1800054a7  test    eax, eax
0x1800054a9  jnz     loc_1800057D2
0x1800054af  movzx   r14d, word ptr [rsp+2E0h+SourceString+2]
0x1800054b5  lea     ecx, [rax+1]
0x1800054b8  mov     r12, [rsp+2E0h+SourceString+8]
0x1800054bd  movzx   esi, word ptr [rsp+2E0h+pDataIn+2]
0x1800054c2  mov     r15, [rsp+2E0h+pDataIn+8]
0x1800054c7  call    DsRolepInitializeLogHelper
0x1800054cc  test    [rbp+1E0h+arg_20], 1
0x1800054d3  jz      short loc_1800054EF
0x1800054d5  lea     rdx, aPerformingNt4T; "Performing NT4 to NT5 BDC upgrade.\n"
0x1800054dc  lea     ecx, [rbx+4]
0x1800054df  call    DsRolepLogPrintRoutine
0x1800054e4  xor     r12d, r12d
0x1800054e7  mov     ebx, r12d
0x1800054ea  jmp     loc_1800057D2
0x1800054ef  lea     rcx, [rsp+2E0h+hObject]; NewTokenHandle
0x1800054f4  call    DsRolepGetImpersonationToken
0x1800054f9  mov     ebx, eax
0x1800054fb  test    eax, eax
0x1800054fd  jnz     loc_1800057CF
0x180005503  lea     rax, [rsp+2E0h+var_298]
0x180005508  mov     r9d, 5011h
0x18000550e  mov     [rsp+2E0h+var_2B8], rax
0x180005513  xor     r8d, r8d
0x180005516  xor     edx, edx
0x180005518  mov     dword ptr [rsp+2E0h+var_2C0], 2000h
0x180005520  xor     ecx, ecx
0x180005522  call    DsRolepDsGetDcForAccount
0x180005527  mov     ebx, eax
0x180005529  test    eax, eax
0x18000552b  jnz     loc_1800057CF
0x180005531  lea     edi, [rax+4]
0x180005534  mov     ecx, edi
0x180005536  lea     rdx, aSearchingForTh_0; "Searching for the machine account ...\n"
0x18000553d  call    DsRolepLogPrintRoutine
0x180005542  test    si, si
0x180005545  jz      short loc_180005566
0x180005547  mov     edx, esi; cbDataIn
0x180005549  xor     r8d, r8d; dwFlags
0x18000554c  mov     rcx, r15; pDataIn
0x18000554f  call    cs:__imp_CryptUnprotectMemory
0x180005555  test    eax, eax
0x180005557  jnz     short loc_180005566
0x180005559  call    cs:__imp_GetLastError
0x18000555f  mov     ebx, eax
0x180005561  jmp     loc_1800057CF
0x180005566  mov     rcx, [rsp+2E0h+var_298]
0x18000556b  lea     rax, [rsp+2E0h+P]
0x180005570  mov     rdx, [rsp+2E0h+hObject]
0x180005575  mov     r9, r15
0x180005578  mov     [rsp+2E0h+var_2B0], rax
0x18000557d  mov     r8, r13
0x180005580  mov     dword ptr [rsp+2E0h+var_2B8], 1000h
0x180005588  mov     rcx, [rcx]
0x18000558b  call    DsRolepSetMachineAccountType
0x180005590  xor     r9d, r9d
0x180005593  mov     ebx, eax
0x180005595  test    eax, eax
0x180005597  jnz     short loc_18000559E
0x180005599  mov     r13b, 1
0x18000559c  jmp     short loc_1800055B2
0x18000559e  mov     r8d, eax
0x1800055a1  lea     rdx, aDsrolepsetmach; "DsRolepSetMachineAccountType returned %"...
0x1800055a8  mov     ecx, edi
0x1800055aa  mov     r13b, r9b
0x1800055ad  call    DsRolepLogPrintRoutine
0x1800055b2  mov     r9, [rsp+2E0h+P]
0x1800055b7  test    r9, r9
0x1800055ba  jz      short loc_1800055CF
0x1800055bc  mov     r8, [rsp+2E0h+var_288]
0x1800055c1  lea     rdx, aMovedAccountWs; "Moved account %ws to %ws\n"
0x1800055c8  mov     ecx, edi
0x1800055ca  call    DsRolepLogPrintRoutine
0x1800055cf  test    si, si
0x1800055d2  jz      short loc_1800055EE
0x1800055d4  mov     edx, esi; cbDataIn
0x1800055d6  xor     r8d, r8d; dwFlags
0x1800055d9  mov     rcx, r15; pDataIn
0x1800055dc  call    cs:__imp_CryptProtectMemory
0x1800055e2  test    eax, eax
0x1800055e4  jnz     short loc_1800055EE
0x1800055e6  call    cs:__imp_GetLastError
0x1800055ec  mov     ebx, eax
0x1800055ee  test    ebx, ebx
0x1800055f0  jnz     loc_1800057CF
0x1800055f6  lea     rdx, aSettingSecurit; "Setting security for server ...\n"
0x1800055fd  mov     ecx, edi
0x1800055ff  call    DsRolepLogPrintRoutine
0x180005604  xor     edx, edx; Val
0x180005606  lea     rcx, [rbp+1E0h+Buffer]; void *
0x18000560a  mov     r8d, 20Ah; Size
0x180005610  call    memset_0
0x180005615  mov     ebx, 104h
0x18000561a  lea     rcx, [rbp+1E0h+Buffer]; lpBuffer
0x18000561e  mov     edx, ebx; uSize
0x180005620  call    cs:__imp_GetWindowsDirectoryW
0x180005626  xor     ecx, ecx
0x180005628  test    eax, eax
0x18000562a  jz      short loc_180005680
0x18000562c  mov     [rbp+1E0h+var_48], cx
0x180005633  lea     rdx, [rbp+1E0h+Buffer]; cchDest
0x180005637  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000563b  inc     rax
0x18000563e  cmp     [rdx+rax*2], cx
0x180005642  jnz     short loc_18000563B
0x180005644  sub     rbx, rax
0x180005647  lea     r8, aSecurityLogsSc; "\\security\\logs\\scesetup.log"
0x18000564e  mov     r9, rbx; cchToAppend
0x180005651  lea     rcx, [rbp+1E0h+Buffer]; pszDest
0x180005655  call    StringCchCatNW
0x18000565a  xor     ebx, ebx
0x18000565c  lea     rdx, [rbp+1E0h+Buffer]
0x180005660  mov     [rsp+2E0h+var_2B8], rbx
0x180005665  lea     rcx, aDefltsvInf; "defltsv.inf"
0x18000566c  xor     r9d, r9d
0x18000566f  mov     [rsp+2E0h+var_2C0], rbx
0x180005674  lea     r8d, [rbx+60h]
0x180005678  call    cs:__imp_SceSetupSystemByInfName
0x18000567e  jmp     short loc_180005686
0x180005680  call    cs:__imp_GetLastError
0x180005686  test    eax, eax
0x180005688  jz      short loc_18000569E
0x18000568a  mov     r8d, eax
0x18000568d  lea     rdx, aSettingSecurit_2; "Setting security on server files failed"...
0x180005694  mov     ecx, 1
0x180005699  call    DsRolepLogPrintRoutine
0x18000569e  lea     rdx, aSettingSecurit_0; "Setting security for server finished\n"
0x1800056a5  mov     ecx, edi
0x1800056a7  call    DsRolepLogPrintRoutine
0x1800056ac  test    r14w, r14w
0x1800056b0  jz      short loc_1800056D1
0x1800056b2  mov     edx, r14d; cbDataIn
0x1800056b5  xor     r8d, r8d; dwFlags
0x1800056b8  mov     rcx, r12; pDataIn
0x1800056bb  call    cs:__imp_CryptUnprotectMemory
0x1800056c1  test    eax, eax
0x1800056c3  jnz     short loc_1800056D1
0x1800056c5  call    cs:__imp_GetLastError
0x1800056cb  mov     ebx, eax
0x1800056cd  test    eax, eax
0x1800056cf  jnz     short loc_180005719
0x1800056d1  mov     rcx, r12; SourceString
0x1800056d4  call    DsRolepSetBuiltinAdminAccountPassword
0x1800056d9  mov     ebx, eax
0x1800056db  test    r14w, r14w
0x1800056df  jz      short loc_180005701
0x1800056e1  mov     edx, r14d; cbDataIn
0x1800056e4  xor     r8d, r8d; dwFlags
0x1800056e7  mov     rcx, r12; pDataIn
0x1800056ea  call    cs:__imp_CryptProtectMemory
0x1800056f0  xor     r12d, r12d
0x1800056f3  test    eax, eax
0x1800056f5  jnz     short loc_180005704
0x1800056f7  call    cs:__imp_GetLastError
0x1800056fd  mov     ebx, eax
0x1800056ff  jmp     short loc_180005704
0x180005701  xor     r12d, r12d
0x180005704  test    ebx, ebx
0x180005706  jnz     short loc_18000571C
0x180005708  call    DsRolepDeleteUpgradeInfo
0x18000570d  mov     ebx, eax
0x18000570f  test    eax, eax
0x180005711  jz      loc_1800057D2
0x180005717  jmp     short loc_18000571C
0x180005719  xor     r12d, r12d
0x18000571c  test    r13b, r13b
0x18000571f  jz      loc_1800057D2
0x180005725  mov     r14d, r12d
0x180005728  test    si, si
0x18000572b  jz      short loc_180005747
0x18000572d  mov     edx, esi; cbDataIn
0x18000572f  xor     r8d, r8d; dwFlags
0x180005732  mov     rcx, r15; pDataIn
0x180005735  call    cs:__imp_CryptUnprotectMemory
0x18000573b  test    eax, eax
0x18000573d  jnz     short loc_180005747
0x18000573f  call    cs:__imp_GetLastError
0x180005745  mov     ebx, eax
0x180005747  mov     r12, [rsp+2E0h+var_288]
0x18000574c  test    ebx, ebx
0x18000574e  jnz     short loc_18000577D
0x180005750  mov     rcx, [rsp+2E0h+var_298]
0x180005755  lea     rax, [rsp+2E0h+P]
0x18000575a  mov     rdx, [rsp+2E0h+hObject]
0x18000575f  mov     r9, r15
0x180005762  mov     [rsp+2E0h+var_2B0], rax
0x180005767  mov     r8, r12
0x18000576a  mov     dword ptr [rsp+2E0h+var_2B8], 2000h
0x180005772  mov     rcx, [rcx]
0x180005775  call    DsRolepSetMachineAccountType
0x18000577a  mov     r14d, eax
0x18000577d  test    si, si
0x180005780  jz      short loc_18000579C
0x180005782  mov     edx, esi; cbDataIn
0x180005784  xor     r8d, r8d; dwFlags
0x180005787  mov     rcx, r15; pDataIn
0x18000578a  call    cs:__imp_CryptProtectMemory
0x180005790  test    eax, eax
0x180005792  jnz     short loc_18000579C
0x180005794  call    cs:__imp_GetLastError
0x18000579a  mov     ebx, eax
0x18000579c  test    r14d, r14d
0x18000579f  jz      short loc_1800057B4
0x1800057a1  mov     r8d, r14d
0x1800057a4  lea     rdx, aDsrolepsetmach; "DsRolepSetMachineAccountType returned %"...
0x1800057ab  mov     ecx, edi
0x1800057ad  call    DsRolepLogPrintRoutine
0x1800057b2  jmp     short loc_1800057CF
0x1800057b4  mov     r9, [rsp+2E0h+P]
0x1800057b9  test    r9, r9
0x1800057bc  jz      short loc_1800057CF
0x1800057be  mov     r8, r12
0x1800057c1  lea     rdx, aAttemptedToMov; "Attempted to move account %ws to %ws\n"
0x1800057c8  mov     ecx, edi
0x1800057ca  call    DsRolepLogPrintRoutine
0x1800057cf  xor     r12d, r12d
0x1800057d2  mov     edx, 2
0x1800057d7  lea     rcx, [rsp+2E0h+pDataIn]
0x1800057dc  call    DsRolepFreePasswords
0x1800057e1  mov     rcx, [rsp+2E0h+var_298]; Buffer
0x1800057e6  call    cs:__imp_NetApiBufferFree
0x1800057ec  cmp     [rsp+2E0h+P], r12
0x1800057f1  jz      short loc_18000580D
0x1800057f3  mov     rcx, gs:60h
0x1800057fc  xor     edx, edx; Flags
0x1800057fe  mov     r8, [rsp+2E0h+P]; P
0x180005803  mov     rcx, [rcx+30h]; HeapHandle
0x180005807  call    cs:__imp_RtlFreeHeap
0x18000580d  mov     rcx, [rsp+2E0h+hObject]; hObject
0x180005812  test    rcx, rcx
0x180005815  jz      short loc_18000581D
0x180005817  call    cs:__imp_CloseHandle
0x18000581d  xor     ecx, ecx
0x18000581f  call    DsRolepResetOperationHandle
0x180005824  mov     eax, ebx
0x180005826  mov     rcx, [rbp+1E0h+var_40]
0x18000582d  xor     rcx, rsp; StackCookie
0x180005830  call    __security_check_cookie
0x180005835  mov     rbx, [rsp+2E0h+arg_10]
0x18000583d  add     rsp, 2B0h
0x180005844  pop     r15
0x180005846  pop     r14
0x180005848  pop     r13
0x18000584a  pop     r12
0x18000584c  pop     rdi
0x18000584d  pop     rsi
0x18000584e  pop     rbp
0x18000584f  retn
```
