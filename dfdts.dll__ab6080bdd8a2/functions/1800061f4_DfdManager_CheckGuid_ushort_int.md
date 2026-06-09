# DfdManager::CheckGuid(ushort *,int *)

- ea: `0x1800061f4`
- end: `0x180006411`
- name: `?CheckGuid@DfdManager@@AEAAJPEAGPEAH@Z`
- size: `541`
- prototype: `__int64 __fastcall(DfdManager *__hidden this, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006020`

## callees

- `0x180002c90`
- `0x1800056a8`
- `0x1800061f4`
- `0x180006e70`
- `0x180006ff8`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180006247`
- `KERNEL32!HeapAlloc` at `0x180006247`
- `KERNEL32!GetProcessHeap` at `0x180006236`
- `KERNEL32!GetProcessHeap` at `0x1800063ce`
- `KERNEL32!GetProcessHeap` at `0x1800063e7`
- `KERNEL32!GetProcessHeap` at `0x180006236`
- `KERNEL32!GetProcessHeap` at `0x1800063ce`
- `KERNEL32!GetProcessHeap` at `0x1800063e7`
- `KERNEL32!HeapFree` at `0x1800063dc`
- `KERNEL32!HeapFree` at `0x1800063f5`
- `KERNEL32!HeapFree` at `0x1800063dc`
- `KERNEL32!HeapFree` at `0x1800063f5`
- `ADVAPI32!RegOpenKeyExW` at `0x1800062ff`
- `ADVAPI32!RegOpenKeyExW` at `0x1800062ff`
- `ADVAPI32!RegCloseKey` at `0x1800063c3`
- `ADVAPI32!RegCloseKey` at `0x1800063c3`
- `ADVAPI32!RegQueryValueExW` at `0x1800063a5`
- `ADVAPI32!RegQueryValueExW` at `0x1800063a5`

## pseudocode

```c
__int64 __fastcall DfdManager::CheckGuid(DfdManager *this, unsigned __int16 *a2, int *a3)
{
  struct _STORAGE_DEVICE_UNIQUE_IDENTIFIER *v3; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v8; // rax
  WCHAR *v9; // rsi
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  int v14; // eax
  unsigned int v15; // eax
  DfdManager *v16; // rcx
  unsigned __int16 *v17; // r8
  unsigned int v18; // r9d
  int v19; // eax
  int v20; // eax
  HANDLE v21; // rax
  HANDLE v22; // rax
  DWORD Type; // [rsp+30h] [rbp-20h] BYREF
  struct _STORAGE_DEVICE_UNIQUE_IDENTIFIER *v25; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v27; // [rsp+88h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  hKey = 0;
  v25 = 0;
  Type = 4;
  v27 = 8;
  cbData = 4;
  if ( a2 )
  {
    ProcessHeap = GetProcessHeap();
    v8 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x410u);
    v9 = v8;
    if ( v8 )
    {
      v14 = StringCchPrintfW(
              v8,
              0x208u,
              L"%s\\%s",
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\DiskDiagnostics\\FailingDiskList",
              a2);
      if ( v14 >= 0 )
      {
        v15 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x20019u, &hKey);
        v10 = v15;
        if ( v15 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v12 = 26;
            v13 = v15;
            goto LABEL_7;
          }
        }
        else
        {
          v19 = DfdManager::ReadRegValue(v16, hKey, v17, v18, (unsigned __int8 **)&v25, &v27);
          v10 = v19;
          if ( v19 == 2 )
          {
            *a3 = 0;
            v10 = 0;
            v3 = v25;
          }
          else
          {
            v3 = v25;
            if ( !v19 )
            {
              v20 = DfdDuid::Equal(*((DfdDuid **)this + 1), v25);
              *a3 = v20;
              if ( v20 )
              {
                v10 = RegQueryValueExW(hKey, L"SMARTFailureInject", 0, &Type, (LPBYTE)this + 20, &cbData);
                if ( v10 == 2 )
                  v10 = 0;
              }
            }
          }
        }
      }
      else
      {
        v10 = (unsigned __int16)v14;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v12 = 25;
          goto LABEL_6;
        }
      }
    }
    else
    {
      v10 = 14;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 24;
LABEL_6:
        v13 = v10;
LABEL_7:
        WPP_SF_d(v11[2], v12, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids, v13);
      }
    }
  }
  else
  {
    v10 = 0;
    v9 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v9 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v9);
  }
  if ( v3 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v3);
  }
  return v10;
}

```

## disassembly

```asm
0x1800061f4  mov     [rsp-28h+arg_0], rbx
0x1800061f9  push    rbp
0x1800061fa  push    rsi
0x1800061fb  push    rdi
0x1800061fc  push    r14
0x1800061fe  push    r15
0x180006200  mov     rbp, rsp
0x180006203  sub     rsp, 50h
0x180006207  xor     edi, edi
0x180006209  mov     [rbp+hKey], 0
0x180006211  mov     [rbp+var_18], rdi
0x180006215  mov     r14, r8
0x180006218  mov     rbx, rdx
0x18000621b  mov     r15, rcx
0x18000621e  lea     eax, [rdi+4]
0x180006221  mov     [rbp+Type], eax
0x180006224  lea     esi, [rdi+8]
0x180006227  mov     [rbp+arg_8], esi
0x18000622a  mov     [rbp+cbData], eax
0x18000622d  test    rdx, rdx
0x180006230  jz      loc_1800063B6
0x180006236  call    cs:__imp_GetProcessHeap
0x18000623c  mov     r8d, 410h; dwBytes
0x180006242  mov     edx, esi; dwFlags
0x180006244  mov     rcx, rax; hHeap
0x180006247  call    cs:__imp_HeapAlloc
0x18000624d  mov     rsi, rax
0x180006250  test    rax, rax
0x180006253  jnz     short loc_180006294
0x180006255  lea     ebx, [rdi+0Eh]
0x180006258  mov     rcx, cs:WPP_GLOBAL_Control
0x18000625f  lea     rdx, WPP_GLOBAL_Control
0x180006266  cmp     rcx, rdx
0x180006269  jz      loc_1800063BA
0x18000626f  test    byte ptr [rcx+1Ch], 1
0x180006273  jz      loc_1800063BA
0x180006279  lea     edx, [rdi+18h]
0x18000627c  mov     r9d, ebx
0x18000627f  mov     rcx, [rcx+10h]
0x180006283  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x18000628a  call    WPP_SF_d
0x18000628f  jmp     loc_1800063BA
0x180006294  lea     r9, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000629b  mov     [rsp+50h+phkResult], rbx
0x1800062a0  lea     r8, aSS; "%s\\%s"
0x1800062a7  mov     edx, 208h; unsigned __int64
0x1800062ac  mov     rcx, rsi; unsigned __int16 *
0x1800062af  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800062b4  test    eax, eax
0x1800062b6  jns     short loc_1800062E3
0x1800062b8  movzx   ebx, ax
0x1800062bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062c2  lea     rdx, WPP_GLOBAL_Control
0x1800062c9  cmp     rcx, rdx
0x1800062cc  jz      loc_1800063BA
0x1800062d2  test    byte ptr [rcx+1Ch], 1
0x1800062d6  jz      loc_1800063BA
0x1800062dc  mov     edx, 19h
0x1800062e1  jmp     short loc_18000627C
0x1800062e3  lea     rax, [rbp+hKey]
0x1800062e7  mov     r9d, 20019h; samDesired
0x1800062ed  xor     r8d, r8d; ulOptions
0x1800062f0  mov     [rsp+50h+phkResult], rax; phkResult
0x1800062f5  mov     rdx, rsi; lpSubKey
0x1800062f8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800062ff  call    cs:__imp_RegOpenKeyExW
0x180006305  mov     ebx, eax
0x180006307  test    eax, eax
0x180006309  jz      short loc_180006339
0x18000630b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006312  lea     rdx, WPP_GLOBAL_Control
0x180006319  cmp     rcx, rdx
0x18000631c  jz      loc_1800063BA
0x180006322  test    byte ptr [rcx+1Ch], 1
0x180006326  jz      loc_1800063BA
0x18000632c  mov     edx, 1Ah
0x180006331  mov     r9d, eax
0x180006334  jmp     loc_18000627F
0x180006339  mov     rdx, [rbp+hKey]; HKEY
0x18000633d  lea     rax, [rbp+arg_8]
0x180006341  mov     [rsp+50h+lpcbData], rax; unsigned int *
0x180006346  lea     rax, [rbp+var_18]
0x18000634a  mov     [rsp+50h+phkResult], rax; unsigned __int8 **
0x18000634f  call    ?ReadRegValue@DfdManager@@AEAAJPEAUHKEY__@@PEAGKPEAPEAEPEAK@Z; DfdManager::ReadRegValue(HKEY__ *,ushort *,ulong,uchar * *,ulong *)
0x180006354  mov     ebx, eax
0x180006356  cmp     eax, 2
0x180006359  jnz     short loc_180006366
0x18000635b  mov     [r14], edi
0x18000635e  xor     ebx, ebx
0x180006360  mov     rdi, [rbp+var_18]
0x180006364  jmp     short loc_1800063BA
0x180006366  mov     rdi, [rbp+var_18]
0x18000636a  test    eax, eax
0x18000636c  jnz     short loc_1800063BA
0x18000636e  mov     rcx, [r15+8]; this
0x180006372  mov     rdx, rdi; struct _STORAGE_DEVICE_UNIQUE_IDENTIFIER *
0x180006375  call    ?Equal@DfdDuid@@QEAAHPEAU_STORAGE_DEVICE_UNIQUE_IDENTIFIER@@@Z; DfdDuid::Equal(_STORAGE_DEVICE_UNIQUE_IDENTIFIER *)
0x18000637a  mov     [r14], eax
0x18000637d  test    eax, eax
0x18000637f  jz      short loc_1800063BA
0x180006381  lea     rcx, [rbp+cbData]
0x180006385  xor     r8d, r8d; lpReserved
0x180006388  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x18000638d  lea     rax, [r15+14h]
0x180006391  mov     rcx, [rbp+hKey]; hKey
0x180006395  lea     r9, [rbp+Type]; lpType
0x180006399  lea     rdx, aSmartfailurein; "SMARTFailureInject"
0x1800063a0  mov     [rsp+50h+phkResult], rax; lpData
0x1800063a5  call    cs:__imp_RegQueryValueExW
0x1800063ab  mov     ebx, eax
0x1800063ad  cmp     eax, 2
0x1800063b0  jnz     short loc_1800063BA
0x1800063b2  xor     ebx, ebx
0x1800063b4  jmp     short loc_1800063BA
0x1800063b6  xor     ebx, ebx
0x1800063b8  xor     esi, esi
0x1800063ba  mov     rcx, [rbp+hKey]; hKey
0x1800063be  test    rcx, rcx
0x1800063c1  jz      short loc_1800063C9
0x1800063c3  call    cs:__imp_RegCloseKey
0x1800063c9  test    rsi, rsi
0x1800063cc  jz      short loc_1800063E2
0x1800063ce  call    cs:__imp_GetProcessHeap
0x1800063d4  mov     r8, rsi; lpMem
0x1800063d7  xor     edx, edx; dwFlags
0x1800063d9  mov     rcx, rax; hHeap
0x1800063dc  call    cs:__imp_HeapFree
0x1800063e2  test    rdi, rdi
0x1800063e5  jz      short loc_1800063FB
0x1800063e7  call    cs:__imp_GetProcessHeap
0x1800063ed  mov     r8, rdi; lpMem
0x1800063f0  xor     edx, edx; dwFlags
0x1800063f2  mov     rcx, rax; hHeap
0x1800063f5  call    cs:__imp_HeapFree
0x1800063fb  mov     eax, ebx
0x1800063fd  mov     rbx, [rsp+50h+arg_0]
0x180006405  add     rsp, 50h
0x180006409  pop     r15
0x18000640b  pop     r14
0x18000640d  pop     rdi
0x18000640e  pop     rsi
0x18000640f  pop     rbp
0x180006410  retn
```
