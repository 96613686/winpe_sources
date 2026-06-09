# OmaDmGetInitiationInfo

- ea: `0x180018480`
- end: `0x180018947`
- name: `OmaDmGetInitiationInfo`
- size: `1223`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fc34`

## callees

- `0x1800031b0`
- `0x180003db8`
- `0x1800075f0`
- `0x180007930`
- `0x180008290`
- `0x18000c658`
- `0x18000c718`
- `0x18000c974`
- `0x18000e004`
- `0x180014514`
- `0x180014570`
- `0x180014698`
- `0x1800174d0`
- `0x180018480`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800188ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800188df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800188ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800188df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018647`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800186c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018647`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800186c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018697`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800186f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018697`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800186f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001880d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001888c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001889d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001880d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001888c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001889d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800185b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001879f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800185b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001879f`

## pseudocode

```c
__int64 __fastcall OmaDmGetInitiationInfo(LPCWSTR lpSubKey, __int64 a2)
{
  BYTE *v4; // r13
  char *v5; // rsi
  __int64 v6; // r8
  LSTATUS AccountRootKeyByInitiationId; // ebx
  LSTATUS Value; // eax
  bool v9; // cc
  unsigned __int64 v10; // rax
  char *v11; // rax
  int v12; // ecx
  unsigned int v13; // edi
  char *v14; // r14
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  unsigned int i; // edi
  __int64 v19; // rcx
  size_t Size; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v23; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v27; // [rsp+90h] [rbp-70h]
  __int128 v28; // [rsp+A0h] [rbp-60h]
  __int128 v29; // [rsp+B0h] [rbp-50h]
  char v30[16]; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v31; // [rsp+D0h] [rbp-30h]
  __int64 v32; // [rsp+D8h] [rbp-28h]
  WCHAR SubKey[32]; // [rsp+E0h] [rbp-20h] BYREF

  hObject = 0;
  phkResult = 0;
  v23 = 0;
  Size = 0;
  v4 = 0;
  v5 = 0;
  memset_0(v26, 0, 0x40u);
  memset_0(SubKey, 0, sizeof(SubKey));
  hKey = 0;
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
  {
    v31 = L"OmaDmGetInitiationInfo";
    v32 = 46;
    McGenEventWrite_EventWriteTransfer(WP_OMADMAPI_PROVIDER_Context, FunctionEntryPointEvent, v6, 2, v30);
  }
  if ( *(_DWORD *)a2 != 64 || !(unsigned int)IsValidInitiationID(lpSubKey) )
  {
    AccountRootKeyByInitiationId = -2147024809;
    goto LABEL_42;
  }
  AccountRootKeyByInitiationId = AcquireOmaDmMutex(&hObject);
  if ( AccountRootKeyByInitiationId >= 0 )
  {
    if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 2) != 0 )
      McTemplateU0z_EventWriteTransfer(WP_OMADMAPI_PROVIDER_Context, OmaDmGetInitiationInfoCalledEvent, lpSubKey);
    AccountRootKeyByInitiationId = GetAccountRootKeyByInitiationId(lpSubKey, &hKey);
    if ( AccountRootKeyByInitiationId >= 0 )
    {
      Value = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20119u, &phkResult);
      AccountRootKeyByInitiationId = Value;
      v9 = Value <= 0;
      if ( Value )
        goto LABEL_11;
      LODWORD(v26[0]) = 64;
      AccountRootKeyByInitiationId = GetStructFromRegistry(phkResult, 8, (__int64)v26, 64, 0, 0, 0);
      if ( AccountRootKeyByInitiationId < 0 )
        goto LABEL_42;
      if ( !(_DWORD)v28 )
        goto LABEL_38;
      v10 = (unsigned __int64)(unsigned int)v28 << 6;
      if ( v10 > 0xFFFFFFFF )
      {
        LODWORD(Size) = -1;
        AccountRootKeyByInitiationId = -2147024362;
        goto LABEL_42;
      }
      LODWORD(Size) = (_DWORD)v28 << 6;
      v11 = (char *)LocalAlloc(0, (unsigned int)v10);
      v5 = v11;
      if ( !v11 )
      {
LABEL_18:
        AccountRootKeyByInitiationId = -2147024882;
        goto LABEL_42;
      }
      memset_0(v11, 0, (unsigned int)Size);
      Value = RegQueryValueExW(phkResult, L"AlertStatuses", 0, (LPDWORD)&Size + 1, 0, (LPDWORD)&Size);
      AccountRootKeyByInitiationId = Value;
      if ( Value )
      {
        if ( Value == 2 )
        {
          v12 = v28;
          goto LABEL_31;
        }
        v9 = Value <= 0;
      }
      else
      {
        if ( HIDWORD(Size) != 3 || !(_DWORD)Size )
          goto LABEL_27;
        v4 = (BYTE *)LocalAlloc(0, (unsigned int)Size);
        if ( !v4 )
          goto LABEL_18;
        Value = RegQueryValueExW(phkResult, L"AlertStatuses", 0, (LPDWORD)&Size + 1, v4, (LPDWORD)&Size);
        AccountRootKeyByInitiationId = Value;
        v9 = Value <= 0;
        if ( !Value )
        {
          if ( HIDWORD(Size) != 3 || !(_DWORD)Size || (v12 = v28, (unsigned int)Size >> 2 != (_DWORD)v28) )
          {
LABEL_27:
            AccountRootKeyByInitiationId = -2147418113;
            goto LABEL_42;
          }
LABEL_31:
          v13 = 0;
          AccountRootKeyByInitiationId = 0;
          if ( v12 )
          {
            do
            {
              v14 = &v5[64 * (unsigned __int64)v13];
              *(_DWORD *)v14 = 64;
              AccountRootKeyByInitiationId = GenerateIndexedString(L"Alert", v13, SubKey, 0x20u);
              if ( AccountRootKeyByInitiationId < 0 )
                goto LABEL_42;
              AccountRootKeyByInitiationId = RegOpenKeyExW(phkResult, SubKey, 0, 0x20119u, &v23);
              if ( AccountRootKeyByInitiationId )
              {
                if ( AccountRootKeyByInitiationId <= 0 )
                  goto LABEL_42;
                AccountRootKeyByInitiationId = (unsigned __int16)AccountRootKeyByInitiationId;
                goto LABEL_13;
              }
              AccountRootKeyByInitiationId = GetStructFromRegistry(v23, 9, (__int64)v14, 64, 0, 0, 0);
              if ( AccountRootKeyByInitiationId < 0 )
                goto LABEL_42;
              if ( v4 )
                *((_DWORD *)v14 + 12) = *(_DWORD *)&v4[4 * v13];
              RegCloseKey(v23);
              ++v13;
              v23 = 0;
            }
            while ( v13 < (unsigned int)v28 );
          }
LABEL_38:
          v15 = v27;
          *(_OWORD *)a2 = *(_OWORD *)v26;
          v16 = v28;
          *(_OWORD *)(a2 + 16) = v15;
          v17 = v29;
          *(_OWORD *)(a2 + 32) = v16;
          *(_OWORD *)(a2 + 48) = v17;
          memset_0(v26, 0, 0x40u);
          *(_QWORD *)(a2 + 24) = v5;
          v5 = 0;
          goto LABEL_42;
        }
      }
LABEL_11:
      if ( !v9 )
      {
        AccountRootKeyByInitiationId = (unsigned __int16)Value;
LABEL_13:
        AccountRootKeyByInitiationId |= 0x80070000;
      }
    }
  }
LABEL_42:
  RegCloseKey(phkResult);
  RegCloseKey(v23);
  LocalFree(v4);
  if ( v5 )
  {
    for ( i = 0; i < *(_DWORD *)(a2 + 32); ++i )
      FreeAlertInfoData(&v5[64 * (unsigned __int64)i]);
    LocalFree(v5);
  }
  OmaDmFreeInitiationInfo(v26);
  ReleaseOmaDmMutex(hObject);
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(
      v19,
      FunctionReturnValueEvent,
      L"OmaDmGetInitiationInfo",
      (unsigned int)AccountRootKeyByInitiationId);
  return (unsigned int)AccountRootKeyByInitiationId;
}

```

## disassembly

```asm
0x180018480  mov     [rsp-8+arg_10], rbx
0x180018485  push    rbp
0x180018486  push    rsi
0x180018487  push    rdi
0x180018488  push    r12
0x18001848a  push    r13
0x18001848c  push    r14
0x18001848e  push    r15
0x180018490  lea     rbp, [rsp-30h]
0x180018495  sub     rsp, 130h
0x18001849c  mov     rax, cs:__security_cookie
0x1800184a3  xor     rax, rsp
0x1800184a6  mov     [rbp+60h+var_40], rax
0x1800184aa  xor     r14d, r14d
0x1800184ad  mov     r15, rdx
0x1800184b0  mov     rdi, rcx
0x1800184b3  mov     [rsp+160h+hObject], r14
0x1800184b8  xor     edx, edx; Val
0x1800184ba  mov     [rsp+160h+var_108], r14
0x1800184bf  lea     rcx, [rbp+60h+var_E0]; void *
0x1800184c3  mov     [rsp+160h+var_100], r14
0x1800184c8  lea     r12d, [r14+40h]
0x1800184cc  mov     dword ptr [rsp+160h+Size], r14d
0x1800184d1  mov     r8d, r12d; Size
0x1800184d4  mov     dword ptr [rsp+160h+Size+4], r14d
0x1800184d9  mov     r13d, r14d
0x1800184dc  mov     esi, r14d
0x1800184df  call    memset_0
0x1800184e4  mov     r8d, r12d; Size
0x1800184e7  lea     rcx, [rbp+60h+SubKey]; void *
0x1800184eb  xor     edx, edx; Val
0x1800184ed  call    memset_0
0x1800184f2  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x1800184f9  lea     rax, aOmadmgetinitia_0; "OmaDmGetInitiationInfo"
0x180018500  mov     [rsp+160h+hKey], r14
0x180018505  jz      short loc_180018533
0x180018507  mov     [rbp+60h+var_90], rax
0x18001850b  lea     r9d, [r14+2]
0x18001850f  lea     rax, [rbp+60h+var_A0]
0x180018513  mov     [rbp+60h+var_88], 2Eh ; '.'
0x18001851b  lea     rdx, FunctionEntryPointEvent
0x180018522  mov     [rsp+160h+phkResult], rax
0x180018527  lea     rcx, WP_OMADMAPI_PROVIDER_Context
0x18001852e  call    McGenEventWrite_EventWriteTransfer
0x180018533  cmp     [r15], r12d
0x180018536  jz      short loc_180018542
0x180018538  mov     ebx, 80070057h
0x18001853d  jmp     loc_180018887
0x180018542  mov     rcx, rdi
0x180018545  call    IsValidInitiationID
0x18001854a  test    eax, eax
0x18001854c  jz      short loc_180018538
0x18001854e  lea     rcx, [rsp+160h+hObject]; void **
0x180018553  call    ?AcquireOmaDmMutex@@YAJPEAPEAX@Z; AcquireOmaDmMutex(void * *)
0x180018558  mov     ebx, eax
0x18001855a  test    eax, eax
0x18001855c  js      loc_180018887
0x180018562  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 2
0x180018569  jz      short loc_180018581
0x18001856b  mov     r8, rdi
0x18001856e  lea     rdx, OmaDmGetInitiationInfoCalledEvent
0x180018575  lea     rcx, WP_OMADMAPI_PROVIDER_Context
0x18001857c  call    McTemplateU0z_EventWriteTransfer
0x180018581  lea     rdx, [rsp+160h+hKey]
0x180018586  mov     rcx, rdi
0x180018589  call    GetAccountRootKeyByInitiationId
0x18001858e  mov     ebx, eax
0x180018590  test    eax, eax
0x180018592  js      loc_180018887
0x180018598  mov     rcx, [rsp+160h+hKey]; hKey
0x18001859d  lea     rax, [rsp+160h+var_108]
0x1800185a2  mov     r9d, 20119h; samDesired
0x1800185a8  mov     [rsp+160h+phkResult], rax; phkResult
0x1800185ad  xor     r8d, r8d; ulOptions
0x1800185b0  mov     rdx, rdi; lpSubKey
0x1800185b3  call    cs:__imp_RegOpenKeyExW
0x1800185ba  nop     dword ptr [rax+rax+00h]
0x1800185bf  mov     ebx, eax
0x1800185c1  test    eax, eax
0x1800185c3  jz      short loc_1800185D9
0x1800185c5  jle     loc_180018887
0x1800185cb  movzx   ebx, ax
0x1800185ce  or      ebx, 80070000h
0x1800185d4  jmp     loc_180018887
0x1800185d9  mov     rcx, [rsp+160h+var_108]; hKey
0x1800185de  lea     rax, [rbp+60h+var_E0]
0x1800185e2  mov     [rsp+160h+var_118], r14d; unsigned int
0x1800185e7  lea     r9, off_180025EC0; "UIMode"
0x1800185ee  mov     [rsp+160h+var_120], r14; unsigned __int8 *
0x1800185f3  xor     r8d, r8d
0x1800185f6  mov     [rsp+160h+var_128], r14; __int64
0x1800185fb  xor     edx, edx
0x1800185fd  mov     [rsp+160h+var_130], r12d; int
0x180018602  mov     [rsp+160h+lpcbData], rax; __int64
0x180018607  mov     dword ptr [rsp+160h+phkResult], 8; int
0x18001860f  mov     dword ptr [rbp+60h+var_E0], r12d
0x180018613  call    GetStructFromRegistry
0x180018618  mov     ebx, eax
0x18001861a  test    eax, eax
0x18001861c  js      loc_180018887
0x180018622  mov     eax, dword ptr [rbp+60h+var_C0]
0x180018625  test    eax, eax
0x180018627  jz      loc_180018830
0x18001862d  shl     rax, 6
0x180018631  mov     ecx, 0FFFFFFFFh
0x180018636  cmp     rax, rcx
0x180018639  ja      loc_180018879
0x18001863f  mov     edx, eax; uBytes
0x180018641  xor     ecx, ecx; uFlags
0x180018643  mov     dword ptr [rsp+160h+Size], edx
0x180018647  call    cs:__imp_LocalAlloc
0x18001864e  nop     dword ptr [rax+rax+00h]
0x180018653  mov     rsi, rax
0x180018656  test    rax, rax
0x180018659  jnz     short loc_180018665
0x18001865b  mov     ebx, 8007000Eh
0x180018660  jmp     loc_180018887
0x180018665  mov     r8d, dword ptr [rsp+160h+Size]; Size
0x18001866a  xor     edx, edx; Val
0x18001866c  mov     rcx, rsi; void *
0x18001866f  call    memset_0
0x180018674  mov     rcx, [rsp+160h+var_108]; hKey
0x180018679  lea     rax, [rsp+160h+Size]
0x18001867e  mov     [rsp+160h+lpcbData], rax; lpcbData
0x180018683  lea     r9, [rsp+160h+Size+4]; lpType
0x180018688  xor     r8d, r8d; lpReserved
0x18001868b  mov     [rsp+160h+phkResult], r14; lpData
0x180018690  lea     rdx, aAlertstatuses; "AlertStatuses"
0x180018697  call    cs:__imp_RegQueryValueExW
0x18001869e  nop     dword ptr [rax+rax+00h]
0x1800186a3  mov     ebx, eax
0x1800186a5  test    eax, eax
0x1800186a7  jnz     loc_180018730
0x1800186ad  cmp     dword ptr [rsp+160h+Size+4], 3
0x1800186b2  jnz     short loc_180018726
0x1800186b4  mov     eax, dword ptr [rsp+160h+Size]
0x1800186b8  test    eax, eax
0x1800186ba  jz      short loc_180018726
0x1800186bc  mov     edx, eax; uBytes
0x1800186be  xor     ecx, ecx; uFlags
0x1800186c0  call    cs:__imp_LocalAlloc
0x1800186c7  nop     dword ptr [rax+rax+00h]
0x1800186cc  mov     r13, rax
0x1800186cf  test    rax, rax
0x1800186d2  jz      short loc_18001865B
0x1800186d4  mov     rcx, [rsp+160h+var_108]; hKey
0x1800186d9  lea     rax, [rsp+160h+Size]
0x1800186de  mov     [rsp+160h+lpcbData], rax; lpcbData
0x1800186e3  lea     r9, [rsp+160h+Size+4]; lpType
0x1800186e8  xor     r8d, r8d; lpReserved
0x1800186eb  mov     [rsp+160h+phkResult], r13; lpData
0x1800186f0  lea     rdx, aAlertstatuses; "AlertStatuses"
0x1800186f7  call    cs:__imp_RegQueryValueExW
0x1800186fe  nop     dword ptr [rax+rax+00h]
0x180018703  mov     ebx, eax
0x180018705  test    eax, eax
0x180018707  jnz     loc_1800185C5
0x18001870d  cmp     dword ptr [rsp+160h+Size+4], 3
0x180018712  jnz     short loc_180018726
0x180018714  mov     eax, dword ptr [rsp+160h+Size]
0x180018718  test    eax, eax
0x18001871a  jz      short loc_180018726
0x18001871c  mov     ecx, dword ptr [rbp+60h+var_C0]
0x18001871f  shr     eax, 2
0x180018722  cmp     eax, ecx
0x180018724  jz      short loc_18001873F
0x180018726  mov     ebx, 8000FFFFh
0x18001872b  jmp     loc_180018887
0x180018730  cmp     eax, 2
0x180018733  jz      short loc_18001873C
0x180018735  test    eax, eax
0x180018737  jmp     loc_1800185C5
0x18001873c  mov     ecx, dword ptr [rbp+60h+var_C0]
0x18001873f  mov     edi, r14d
0x180018742  mov     ebx, r14d
0x180018745  test    ecx, ecx
0x180018747  jz      loc_180018830
0x18001874d  mov     r14d, edi
0x180018750  lea     r8, [rbp+60h+SubKey]; unsigned __int16 *
0x180018754  shl     r14, 6
0x180018758  lea     rcx, aAlert; "Alert"
0x18001875f  add     r14, rsi
0x180018762  mov     r12d, edi
0x180018765  mov     r9d, 20h ; ' '; unsigned int
0x18001876b  mov     edx, edi; unsigned int
0x18001876d  mov     dword ptr [r14], 40h ; '@'
0x180018774  call    ?GenerateIndexedString@@YAJPEBGKPEAGK@Z; GenerateIndexedString(ushort const *,ulong,ushort *,ulong)
0x180018779  mov     ebx, eax
0x18001877b  test    eax, eax
0x18001877d  js      loc_180018884
0x180018783  mov     rcx, [rsp+160h+var_108]; hKey
0x180018788  lea     rax, [rsp+160h+var_100]
0x18001878d  mov     r9d, 20119h; samDesired
0x180018793  mov     [rsp+160h+phkResult], rax; phkResult
0x180018798  xor     r8d, r8d; ulOptions
0x18001879b  lea     rdx, [rbp+60h+SubKey]; lpSubKey
0x18001879f  call    cs:__imp_RegOpenKeyExW
0x1800187a6  nop     dword ptr [rax+rax+00h]
0x1800187ab  mov     ebx, eax
0x1800187ad  xor     eax, eax
0x1800187af  test    ebx, ebx
0x1800187b1  jnz     loc_18001886A
0x1800187b7  mov     r9, cs:off_180025C48
0x1800187be  xor     r8d, r8d
0x1800187c1  mov     rcx, [rsp+160h+var_100]; hKey
0x1800187c6  xor     edx, edx
0x1800187c8  mov     [rsp+160h+var_118], eax; unsigned int
0x1800187cc  mov     [rsp+160h+var_120], rax; unsigned __int8 *
0x1800187d1  mov     [rsp+160h+var_128], rax; __int64
0x1800187d6  mov     [rsp+160h+var_130], 40h ; '@'; int
0x1800187de  mov     [rsp+160h+lpcbData], r14; __int64
0x1800187e3  mov     dword ptr [rsp+160h+phkResult], 9; int
0x1800187eb  call    GetStructFromRegistry
0x1800187f0  mov     ebx, eax
0x1800187f2  test    eax, eax
0x1800187f4  js      loc_180018884
0x1800187fa  test    r13, r13
0x1800187fd  jz      short loc_180018808
0x1800187ff  mov     eax, [r13+r12*4+0]
0x180018804  mov     [r14+30h], eax
0x180018808  mov     rcx, [rsp+160h+var_100]; hKey
0x18001880d  call    cs:__imp_RegCloseKey
0x180018814  nop     dword ptr [rax+rax+00h]
0x180018819  xor     r14d, r14d
0x18001881c  inc     edi
0x18001881e  mov     [rsp+160h+var_100], r14
0x180018823  cmp     edi, dword ptr [rbp+60h+var_C0]
0x180018826  jb      loc_18001874D
0x18001882c  lea     r12d, [r14+40h]
0x180018830  movaps  xmm0, xmmword ptr [rbp+60h+var_E0]
0x180018834  lea     rcx, [rbp+60h+var_E0]; void *
0x180018838  movaps  xmm1, [rbp+60h+var_D0]
0x18001883c  mov     r8, r12; Size
0x18001883f  movups  xmmword ptr [r15], xmm0
0x180018843  xor     edx, edx; Val
0x180018845  movaps  xmm0, [rbp+60h+var_C0]
0x180018849  movups  xmmword ptr [r15+10h], xmm1
0x18001884e  movaps  xmm1, [rbp+60h+var_B0]
0x180018852  movups  xmmword ptr [r15+20h], xmm0
0x180018857  movups  xmmword ptr [r15+30h], xmm1
0x18001885c  call    memset_0
0x180018861  mov     [r15+18h], rsi
0x180018865  mov     rsi, r14
0x180018868  jmp     short loc_180018887
0x18001886a  xor     r14d, r14d
0x18001886d  test    ebx, ebx
0x18001886f  jle     short loc_180018887
0x180018871  movzx   ebx, bx
0x180018874  jmp     loc_1800185CE
0x180018879  mov     dword ptr [rsp+160h+Size], ecx
0x18001887d  mov     ebx, 80070216h
0x180018882  jmp     short loc_180018887
0x180018884  xor     r14d, r14d
0x180018887  mov     rcx, [rsp+160h+var_108]; hKey
0x18001888c  call    cs:__imp_RegCloseKey
0x180018893  nop     dword ptr [rax+rax+00h]
0x180018898  mov     rcx, [rsp+160h+var_100]; hKey
0x18001889d  call    cs:__imp_RegCloseKey
0x1800188a4  nop     dword ptr [rax+rax+00h]
0x1800188a9  mov     rcx, r13; hMem
0x1800188ac  call    cs:__imp_LocalFree
0x1800188b3  nop     dword ptr [rax+rax+00h]
0x1800188b8  test    rsi, rsi
0x1800188bb  jz      short loc_1800188EB
0x1800188bd  mov     edi, r14d
0x1800188c0  cmp     [r15+20h], r14d
0x1800188c4  jbe     short loc_1800188DC
0x1800188c6  mov     ecx, edi
0x1800188c8  shl     rcx, 6
0x1800188cc  add     rcx, rsi; void *
0x1800188cf  call    FreeAlertInfoData
0x1800188d4  inc     edi
0x1800188d6  cmp     edi, [r15+20h]
0x1800188da  jb      short loc_1800188C6
0x1800188dc  mov     rcx, rsi; hMem
0x1800188df  call    cs:__imp_LocalFree
0x1800188e6  nop     dword ptr [rax+rax+00h]
0x1800188eb  lea     rcx, [rbp+60h+var_E0]
0x1800188ef  call    OmaDmFreeInitiationInfo
0x1800188f4  mov     rcx, [rsp+160h+hObject]; hObject
0x1800188f9  call    ?ReleaseOmaDmMutex@@YAXPEAX@Z; ReleaseOmaDmMutex(void *)
0x1800188fe  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x180018905  jz      short loc_18001891D
0x180018907  mov     r9d, ebx
0x18001890a  lea     r8, aOmadmgetinitia_0; "OmaDmGetInitiationInfo"
0x180018911  lea     rdx, FunctionReturnValueEvent
0x180018918  call    McTemplateU0zq_EventWriteTransfer
0x18001891d  mov     eax, ebx
0x18001891f  mov     rcx, [rbp+60h+var_40]
0x180018923  xor     rcx, rsp; StackCookie
0x180018926  call    __security_check_cookie
0x18001892b  mov     rbx, [rsp+160h+arg_10]
0x180018933  add     rsp, 130h
0x18001893a  pop     r15
0x18001893c  pop     r14
0x18001893e  pop     r13
0x180018940  pop     r12
0x180018942  pop     rdi
0x180018943  pop     rsi
0x180018944  pop     rbp
  ... truncated ...
```
