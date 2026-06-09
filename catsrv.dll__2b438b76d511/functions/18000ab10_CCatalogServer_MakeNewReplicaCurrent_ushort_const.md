# CCatalogServer::MakeNewReplicaCurrent(ushort const *)

- ea: `0x18000ab10`
- end: `0x18000ae3f`
- name: `?MakeNewReplicaCurrent@CCatalogServer@@UEAAJPEBG@Z`
- size: `815`
- prototype: `__int64 __fastcall(CCatalogServer *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180009098`
- `0x18000a01c`
- `0x18000ab10`
- `0x18000ae48`
- `0x18000ae78`
- `0x18000e468`
- `0x18001a6c8`
- `0x18001ec1c`
- `0x180032c98`
- `0x180058010`

## import_xrefs

- `msvcrt!_errno` at `0x18000acf0`
- `msvcrt!_errno` at `0x18000acfb`
- `msvcrt!_errno` at `0x18000ada4`
- `msvcrt!_errno` at `0x18000acf0`
- `msvcrt!_errno` at `0x18000acfb`
- `msvcrt!_errno` at `0x18000ada4`
- `msvcrt!_wrename` at `0x18000ace5`
- `msvcrt!_wrename` at `0x18000ad99`
- `msvcrt!_wrename` at `0x18000ace5`
- `msvcrt!_wrename` at `0x18000ad99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac3c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000ac2d`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000ac2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000adfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ae06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ae0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000adfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ae06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ae0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000abc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ac94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ad4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000abc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ac94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ad4c`

## string_xrefs

- `0x18000adbc`: `'MakeNewReplicaCurrent:_wrename - ReplicaNew'`
- `0x18000ac5b`: `'MakeNewReplicaCurrent:RemoveDirectory - ReplicaOld'`
- `0x18000ad13`: `'MakeNewReplicaCurrent:_wrename - ReplicaCurrent'`
- `0x18000ab7b`: `com\complus\src\comcat\catsrv\reputil.cpp`
- `0x18000ab55`: `'MakeNewReplicaCurrent - ImpersonateClient'`

## pseudocode

```c
__int64 __fastcall CCatalogServer::MakeNewReplicaCurrent(CCatalogServer *this, const unsigned __int16 *a2)
{
  unsigned __int16 *v3; // rbx
  unsigned __int16 *v4; // r15
  int v6; // eax
  unsigned __int16 *v7; // rdi
  const unsigned __int16 *v8; // r9
  unsigned int v9; // r8d
  unsigned __int64 v10; // rsi
  unsigned __int16 *v11; // rax
  signed int LastError; // ecx
  unsigned __int64 v13; // r12
  unsigned __int16 *v14; // rax
  int v15; // ecx
  unsigned __int64 v16; // r12
  unsigned __int16 *v17; // rax
  int v18; // ecx
  void *ppInterface; // [rsp+20h] [rbp-58h] BYREF
  int v21; // [rsp+28h] [rbp-50h]
  __int64 v22; // [rsp+30h] [rbp-48h]
  int v23; // [rsp+38h] [rbp-40h] BYREF
  __int16 v24; // [rsp+3Ch] [rbp-3Ch]
  int v25; // [rsp+40h] [rbp-38h]
  const unsigned __int16 *v26; // [rsp+48h] [rbp-30h]
  __int64 v27; // [rsp+50h] [rbp-28h]
  __int64 v28; // [rsp+58h] [rbp-20h]
  int v29; // [rsp+60h] [rbp-18h]
  int v30; // [rsp+64h] [rbp-14h]
  int v31; // [rsp+D0h] [rbp+58h] BYREF

  ppInterface = 0;
  v3 = 0;
  v21 = 0;
  v4 = 0;
  v22 = 0;
  v6 = CImpersonate::ImpersonateClient(&ppInterface);
  v31 = v6;
  if ( v6 < 0 )
  {
    v7 = 0;
    v23 = v6;
    v8 = L"'MakeNewReplicaCurrent - ImpersonateClient'";
    v9 = 285;
LABEL_3:
    v27 = 0;
    v28 = 0;
    v29 = 0;
LABEL_4:
    v30 = 1;
    v24 = 22;
    v26 = v8;
    v25 = -1073737001;
    CError::WriteToLog((CError *)&v23, L"com\\complus\\src\\comcat\\catsrv\\reputil.cpp", v9, v8);
    goto LABEL_31;
  }
  v10 = (int)(safe_lstrlenW(a2) + 12);
  v11 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v10, 2u));
  v7 = v11;
  if ( !v11 )
  {
LABEL_6:
    v31 = -2147024882;
    goto LABEL_31;
  }
  v31 = StringCchCopyW(v11, v10, a2);
  if ( v31 >= 0 )
  {
    v31 = StringCchCatW(v7, v10, L"\\ReplicaOld");
    if ( v31 >= 0 )
    {
      v31 = CCatalogServer::DeleteRecursive((CCatalogServer *)((char *)this - 112), v7);
      if ( v31 >= 0 )
      {
        if ( !RemoveDirectoryW(v7) )
        {
          LastError = GetLastError();
          if ( (unsigned int)(LastError - 2) > 1 )
          {
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v31 = LastError;
            v8 = L"'MakeNewReplicaCurrent:RemoveDirectory - ReplicaOld'";
            v23 = LastError;
            v9 = 310;
            goto LABEL_3;
          }
        }
        v13 = (int)(safe_lstrlenW(a2) + 16);
        v14 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v13, 2u));
        v3 = v14;
        if ( !v14 )
          goto LABEL_6;
        v31 = StringCchCopyW(v14, v13, a2);
        if ( v31 >= 0 )
        {
          v31 = StringCchCatW(v3, v13, L"\\ReplicaCurrent");
          if ( v31 >= 0 )
          {
            if ( _wrename(v3, v7) == -1 && *_errno() != 2 )
            {
              v15 = *_errno();
              if ( v15 > 0 )
                v15 = (unsigned __int16)v15 | 0x80070000;
              v31 = v15;
              v8 = L"'MakeNewReplicaCurrent:_wrename - ReplicaCurrent'";
              v23 = v15;
              v9 = 332;
              goto LABEL_3;
            }
            v16 = (int)(safe_lstrlenW(a2) + 12);
            v17 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v16, 2u));
            v4 = v17;
            if ( !v17 )
              goto LABEL_6;
            v31 = StringCchCopyW(v17, v16, a2);
            if ( v31 >= 0 )
            {
              v31 = StringCchCatW(v4, v16, L"\\ReplicaNew");
              if ( v31 >= 0 )
              {
                if ( _wrename(v4, v3) != -1 )
                {
                  v31 = (*(__int64 (__fastcall **)(CCatalogServer *, const wchar_t *, unsigned __int16 *))(*(_QWORD *)this + 24LL))(
                          this,
                          L"ReplicaTargetCurrent",
                          v3);
                  goto LABEL_31;
                }
                v18 = *_errno();
                if ( v18 > 0 )
                  v18 = (unsigned __int16)v18 | 0x80070000;
                v31 = v18;
                v8 = L"'MakeNewReplicaCurrent:_wrename - ReplicaNew'";
                v23 = v18;
                v9 = 360;
                v27 = 0;
                v28 = 0;
                v29 = 0;
                goto LABEL_4;
              }
            }
          }
        }
      }
    }
  }
LABEL_31:
  CoTaskMemFree(v4);
  CoTaskMemFree(v7);
  CoTaskMemFree(v3);
  CImpersonate::Cleanup((CImpersonate *)&ppInterface, &v31);
  CImpersonate::~CImpersonate((CImpersonate *)&ppInterface);
  return (unsigned int)v31;
}

```

## disassembly

```asm
0x18000ab10  push    rbp
0x18000ab12  push    rbx
0x18000ab13  push    rsi
0x18000ab14  push    rdi
0x18000ab15  push    r12
0x18000ab17  push    r13
0x18000ab19  push    r14
0x18000ab1b  push    r15
0x18000ab1d  mov     rbp, rsp
0x18000ab20  sub     rsp, 78h
0x18000ab24  xor     r12d, r12d
0x18000ab27  mov     r13, rcx
0x18000ab2a  lea     rcx, [rbp+ppInterface]; ppInterface
0x18000ab2e  mov     [rbp+ppInterface], r12
0x18000ab32  mov     ebx, r12d
0x18000ab35  mov     [rbp+var_50], r12d
0x18000ab39  mov     r15d, r12d
0x18000ab3c  mov     [rbp+var_48], r12
0x18000ab40  mov     r14, rdx
0x18000ab43  call    ?ImpersonateClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateClient(void)
0x18000ab48  mov     [rbp+arg_10], eax
0x18000ab4b  test    eax, eax
0x18000ab4d  jns     short loc_18000AB9F
0x18000ab4f  mov     edi, r12d
0x18000ab52  mov     [rbp+var_40], eax
0x18000ab55  lea     r9, aMakenewreplica; "'MakeNewReplicaCurrent - ImpersonateCli"...
0x18000ab5c  mov     r8d, 11Dh; unsigned int
0x18000ab62  lea     esi, [r12+1]
0x18000ab67  mov     [rbp+var_28], r12
0x18000ab6b  mov     [rbp+var_20], r12
0x18000ab6f  mov     [rbp+var_18], r12d
0x18000ab73  mov     eax, 16h
0x18000ab78  mov     [rbp+var_14], esi
0x18000ab7b  lea     rdx, aComComplusSrcC_0; "com\\complus\\src\\comcat\\catsrv\\repu"...
0x18000ab82  mov     [rbp+var_3C], ax
0x18000ab86  lea     rcx, [rbp+var_40]; this
0x18000ab8a  mov     [rbp+var_30], r9
0x18000ab8e  mov     [rbp+var_38], 0C00012D7h
0x18000ab95  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000ab9a  jmp     loc_18000ADFA
0x18000ab9f  mov     rcx, r14; unsigned __int16 *
0x18000aba2  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18000aba7  add     eax, 0Ch
0x18000abaa  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000abb1  movsxd  rsi, eax
0x18000abb4  mov     eax, 2
0x18000abb9  mul     rsi
0x18000abbc  cmovb   rax, rcx
0x18000abc0  mov     rcx, rax; cb
0x18000abc3  call    cs:__imp_CoTaskMemAlloc
0x18000abc9  mov     rdi, rax
0x18000abcc  test    rax, rax
0x18000abcf  jnz     short loc_18000ABDD
0x18000abd1  mov     [rbp+arg_10], 8007000Eh
0x18000abd8  jmp     loc_18000ADFA
0x18000abdd  mov     r8, r14; unsigned __int16 *
0x18000abe0  mov     rdx, rsi; unsigned __int64
0x18000abe3  mov     rcx, rdi; unsigned __int16 *
0x18000abe6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000abeb  mov     [rbp+arg_10], eax
0x18000abee  test    eax, eax
0x18000abf0  js      loc_18000ADFA
0x18000abf6  lea     r8, aReplicaold; "\\ReplicaOld"
0x18000abfd  mov     rdx, rsi; unsigned __int64
0x18000ac00  mov     rcx, rdi; unsigned __int16 *
0x18000ac03  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ac08  mov     [rbp+arg_10], eax
0x18000ac0b  test    eax, eax
0x18000ac0d  js      loc_18000ADFA
0x18000ac13  lea     rcx, [r13-70h]; this
0x18000ac17  mov     rdx, rdi; unsigned __int16 *
0x18000ac1a  call    ?DeleteRecursive@CCatalogServer@@AEAAJPEBG@Z; CCatalogServer::DeleteRecursive(ushort const *)
0x18000ac1f  mov     [rbp+arg_10], eax
0x18000ac22  test    eax, eax
0x18000ac24  js      loc_18000ADFA
0x18000ac2a  mov     rcx, rdi; lpPathName
0x18000ac2d  call    cs:__imp_RemoveDirectoryW
0x18000ac33  mov     esi, 1
0x18000ac38  test    eax, eax
0x18000ac3a  jnz     short loc_18000AC70
0x18000ac3c  call    cs:__imp_GetLastError
0x18000ac42  mov     ecx, eax
0x18000ac44  add     eax, 0FFFFFFFEh
0x18000ac47  cmp     eax, esi
0x18000ac49  jbe     short loc_18000AC70
0x18000ac4b  test    ecx, ecx
0x18000ac4d  jle     short loc_18000AC58
0x18000ac4f  movzx   ecx, cx
0x18000ac52  or      ecx, 80070000h
0x18000ac58  mov     [rbp+arg_10], ecx
0x18000ac5b  lea     r9, aMakenewreplica_1; "'MakeNewReplicaCurrent:RemoveDirectory "...
0x18000ac62  mov     [rbp+var_40], ecx
0x18000ac65  mov     r8d, 136h
0x18000ac6b  jmp     loc_18000AB67
0x18000ac70  mov     rcx, r14; unsigned __int16 *
0x18000ac73  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18000ac78  add     eax, 10h
0x18000ac7b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ac82  movsxd  r12, eax
0x18000ac85  mov     eax, 2
0x18000ac8a  mul     r12
0x18000ac8d  cmovb   rax, rcx
0x18000ac91  mov     rcx, rax; cb
0x18000ac94  call    cs:__imp_CoTaskMemAlloc
0x18000ac9a  mov     rbx, rax
0x18000ac9d  test    rax, rax
0x18000aca0  jz      loc_18000ABD1
0x18000aca6  mov     r8, r14; unsigned __int16 *
0x18000aca9  mov     rdx, r12; unsigned __int64
0x18000acac  mov     rcx, rax; unsigned __int16 *
0x18000acaf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000acb4  mov     [rbp+arg_10], eax
0x18000acb7  test    eax, eax
0x18000acb9  js      loc_18000ADFA
0x18000acbf  lea     r8, aReplicacurrent; "\\ReplicaCurrent"
0x18000acc6  mov     rdx, r12; unsigned __int64
0x18000acc9  mov     rcx, rbx; unsigned __int16 *
0x18000accc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000acd1  xor     r12d, r12d
0x18000acd4  mov     [rbp+arg_10], eax
0x18000acd7  test    eax, eax
0x18000acd9  js      loc_18000ADFA
0x18000acdf  mov     rdx, rdi; NewFileName
0x18000ace2  mov     rcx, rbx; OldFileName
0x18000ace5  call    cs:__imp__wrename
0x18000aceb  cmp     eax, 0FFFFFFFFh
0x18000acee  jnz     short loc_18000AD28
0x18000acf0  call    cs:__imp__errno
0x18000acf6  cmp     dword ptr [rax], 2
0x18000acf9  jz      short loc_18000AD28
0x18000acfb  call    cs:__imp__errno
0x18000ad01  mov     ecx, [rax]
0x18000ad03  test    ecx, ecx
0x18000ad05  jle     short loc_18000AD10
0x18000ad07  movzx   ecx, cx
0x18000ad0a  or      ecx, 80070000h
0x18000ad10  mov     [rbp+arg_10], ecx
0x18000ad13  lea     r9, aMakenewreplica_0; "'MakeNewReplicaCurrent:_wrename - Repli"...
0x18000ad1a  mov     [rbp+var_40], ecx
0x18000ad1d  mov     r8d, 14Ch
0x18000ad23  jmp     loc_18000AB67
0x18000ad28  mov     rcx, r14; unsigned __int16 *
0x18000ad2b  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18000ad30  add     eax, 0Ch
0x18000ad33  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ad3a  movsxd  r12, eax
0x18000ad3d  mov     eax, 2
0x18000ad42  mul     r12
0x18000ad45  cmovb   rax, rcx
0x18000ad49  mov     rcx, rax; cb
0x18000ad4c  call    cs:__imp_CoTaskMemAlloc
0x18000ad52  mov     r15, rax
0x18000ad55  test    rax, rax
0x18000ad58  jz      loc_18000ABD1
0x18000ad5e  mov     r8, r14; unsigned __int16 *
0x18000ad61  mov     rdx, r12; unsigned __int64
0x18000ad64  mov     rcx, rax; unsigned __int16 *
0x18000ad67  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ad6c  xor     r14d, r14d
0x18000ad6f  mov     [rbp+arg_10], eax
0x18000ad72  test    eax, eax
0x18000ad74  js      loc_18000ADFA
0x18000ad7a  lea     r8, aReplicanew; "\\ReplicaNew"
0x18000ad81  mov     rdx, r12; unsigned __int64
0x18000ad84  mov     rcx, r15; unsigned __int16 *
0x18000ad87  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ad8c  mov     [rbp+arg_10], eax
0x18000ad8f  test    eax, eax
0x18000ad91  js      short loc_18000ADFA
0x18000ad93  mov     rdx, rbx; NewFileName
0x18000ad96  mov     rcx, r15; OldFileName
0x18000ad99  call    cs:__imp__wrename
0x18000ad9f  cmp     eax, 0FFFFFFFFh
0x18000ada2  jnz     short loc_18000ADDD
0x18000ada4  call    cs:__imp__errno
0x18000adaa  mov     ecx, [rax]
0x18000adac  test    ecx, ecx
0x18000adae  jle     short loc_18000ADB9
0x18000adb0  movzx   ecx, cx
0x18000adb3  or      ecx, 80070000h
0x18000adb9  mov     [rbp+arg_10], ecx
0x18000adbc  lea     r9, aMakenewreplica_2; "'MakeNewReplicaCurrent:_wrename - Repli"...
0x18000adc3  mov     [rbp+var_40], ecx
0x18000adc6  mov     r8d, 168h
0x18000adcc  mov     [rbp+var_28], r14
0x18000add0  mov     [rbp+var_20], r14
0x18000add4  mov     [rbp+var_18], r14d
0x18000add8  jmp     loc_18000AB73
0x18000addd  mov     rax, [r13+0]
0x18000ade1  lea     rdx, aReplicatargetc; "ReplicaTargetCurrent"
0x18000ade8  mov     r8, rbx
0x18000adeb  mov     rcx, r13
0x18000adee  mov     rax, [rax+18h]
0x18000adf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adf7  mov     [rbp+arg_10], eax
0x18000adfa  mov     rcx, r15; pv
0x18000adfd  call    cs:__imp_CoTaskMemFree
0x18000ae03  mov     rcx, rdi; pv
0x18000ae06  call    cs:__imp_CoTaskMemFree
0x18000ae0c  mov     rcx, rbx; pv
0x18000ae0f  call    cs:__imp_CoTaskMemFree
0x18000ae15  lea     rdx, [rbp+arg_10]; int *
0x18000ae19  lea     rcx, [rbp+ppInterface]; this
0x18000ae1d  call    ?Cleanup@CImpersonate@@QEAAXPEAJ@Z; CImpersonate::Cleanup(long *)
0x18000ae22  lea     rcx, [rbp+ppInterface]; this
0x18000ae26  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x18000ae2b  mov     eax, [rbp+arg_10]
0x18000ae2e  add     rsp, 78h
0x18000ae32  pop     r15
0x18000ae34  pop     r14
0x18000ae36  pop     r13
0x18000ae38  pop     r12
0x18000ae3a  pop     rdi
0x18000ae3b  pop     rsi
0x18000ae3c  pop     rbx
0x18000ae3d  pop     rbp
0x18000ae3e  retn
```
