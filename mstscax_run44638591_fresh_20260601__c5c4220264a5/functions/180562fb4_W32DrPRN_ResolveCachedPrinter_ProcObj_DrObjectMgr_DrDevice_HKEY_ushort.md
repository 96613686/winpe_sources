# W32DrPRN::ResolveCachedPrinter(ProcObj *,DrObjectMgr<DrDevice> *,HKEY__ *,ushort *)

- ea: `0x180562fb4`
- end: `0x180563595`
- name: `?ResolveCachedPrinter@W32DrPRN@@KAPEAV1@PEAVProcObj@@PEAV?$DrObjectMgr@VDrDevice@@@@PEAUHKEY__@@PEAG@Z`
- size: `1505`
- prototype: `W32DrPRN *__fastcall(struct ProcObj *, __int64, HKEY, const WCHAR *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x18055f290`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x18007b16c`
- `0x180083f40`
- `0x180085e04`
- `0x1800d2128`
- `0x1800ebae0`
- `0x1800f95a8`
- `0x18012b052`
- `0x180548f44`
- `0x180556484`
- `0x180561ad8`
- `0x180562fb4`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `msvcrt!isdigit` at `0x180563126`
- `msvcrt!isdigit` at `0x180563126`
- `KERNEL32!LocalAlloc` at `0x1805631fa`
- `KERNEL32!LocalAlloc` at `0x1805631fa`
- `ADVAPI32!RegQueryValueExW` at `0x1805630c7`
- `ADVAPI32!RegQueryValueExW` at `0x18056317f`
- `ADVAPI32!RegQueryValueExW` at `0x18056334f`
- `ADVAPI32!RegQueryValueExW` at `0x1805630c7`
- `ADVAPI32!RegQueryValueExW` at `0x18056317f`
- `ADVAPI32!RegQueryValueExW` at `0x18056334f`
- `ADVAPI32!RegCloseKey` at `0x180563415`
- `ADVAPI32!RegCloseKey` at `0x180563562`
- `ADVAPI32!RegCloseKey` at `0x180563415`
- `ADVAPI32!RegCloseKey` at `0x180563562`
- `ADVAPI32!RegCreateKeyExW` at `0x180563036`
- `ADVAPI32!RegCreateKeyExW` at `0x180563036`
- `ADVAPI32!RegDeleteValueW` at `0x18056344d`
- `ADVAPI32!RegDeleteValueW` at `0x18056344d`
- `ADVAPI32!RegDeleteKeyW` at `0x18056342c`
- `ADVAPI32!RegDeleteKeyW` at `0x18056342c`

## string_xrefs

- `0x1805630ac`: `PrinterCacheData`
- `0x180563160`: `AutoPrinterCacheData`

## pseudocode

```c
W32DrPRN *__fastcall W32DrPRN::ResolveCachedPrinter(struct ProcObj *a1, __int64 a2, HKEY a3, const WCHAR *a4)
{
  W32DrPRN *ObjectW; // rbx
  LSTATUS v6; // r14d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  const WCHAR *v8; // r13
  LSTATUS v9; // r15d
  DWORD v10; // eax
  wchar_t *v11; // rax
  wchar_t *v12; // rdi
  __int64 v13; // rax
  __int64 UniqueObjectID; // r15
  unsigned int v15; // eax
  char *v16; // r15
  BYTE *v17; // rax
  HKEY v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // eax
  HKEY v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  RefCount *v25; // rax
  unsigned int v26; // eax
  const unsigned __int16 *samDesired; // [rsp+28h] [rbp-D8h]
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  int v32; // [rsp+60h] [rbp-A0h]
  __int64 v33; // [rsp+68h] [rbp-98h]
  struct ProcObj *v34; // [rsp+70h] [rbp-90h]
  HKEY v35; // [rsp+78h] [rbp-88h]
  unsigned __int16 v36[264]; // [rsp+80h] [rbp-80h] BYREF

  v34 = a1;
  v33 = a2;
  v35 = a3;
  ObjectW = 0;
  cbData = 0;
  hKey = 0;
  Type = 0;
  v6 = RegCreateKeyExW(a3, a4, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_f096ec1401083a74ebdd09d5d4a36325_Traceguids,
        CurrentThreadActivityIdPrefix,
        v6);
    }
    return ObjectW;
  }
  v8 = L"PrinterCacheData";
  cbData = 0;
  v9 = RegQueryValueExW(hKey, L"PrinterCacheData", 0, &Type, 0, &cbData);
  v10 = cbData;
  if ( cbData < W32DrPRN::_maxCacheDataSize )
  {
    if ( !v9 && cbData )
    {
      v11 = wcsstr_0(a4, L"/");
      v12 = v11;
      if ( v11 )
      {
        if ( wcsstr_0(v11, L"/") )
        {
          v13 = -1;
          do
            ++v13;
          while ( v12[v13] );
          if ( isdigit(v12[v13 - 1]) )
            goto LABEL_64;
        }
      }
      v10 = cbData;
    }
    if ( v9 == 2 )
    {
      v8 = L"AutoPrinterCacheData";
      v32 = 0;
      cbData = 0;
      if ( !RegQueryValueExW(hKey, L"AutoPrinterCacheData", 0, &Type, 0, &cbData) && cbData )
        ObjectW = (W32DrPRN *)DrObjectMgr<DrDevice>::GetObjectW(v33, a4, 4);
    }
    else
    {
      if ( v9 || !v10 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v26 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            (unsigned int)WPP_f096ec1401083a74ebdd09d5d4a36325_Traceguids,
            v26,
            (__int64)a4);
        }
        goto LABEL_64;
      }
      UniqueObjectID = (unsigned int)DrObjectMgr<DrFile>::GetUniqueObjectID(v33);
      StringCchPrintfW(v36, 0x104u, L"PRN%ld", UniqueObjectID);
      v32 = 1;
      v36[7] = 0;
      ObjectW = (W32DrPRN *)LocalAlloc(0x40u, 0x4C8u);
      if ( ObjectW )
      {
        W32DrPRN::W32DrPRN(ObjectW, v34, a4, &sourceString, v36, samDesired, 0, UniqueObjectID, v36);
        *((_DWORD *)ObjectW + 19) = 2;
        *(_QWORD *)ObjectW = &W32DrManualPrn::`vftable'{for `W32DrDeviceAsync'};
        *((_QWORD *)ObjectW + 79) = &W32DrManualPrn::`vftable'{for `DrPRN'};
        DrDevice::Initialize(ObjectW);
        if ( (*(unsigned int (__fastcall **)(W32DrPRN *))(*(_QWORD *)ObjectW + 8LL))(ObjectW)
          && !(unsigned int)DrObjectMgr<DrDevice>::AddObject(v33, ObjectW) )
        {
          RefCount::AddRef(ObjectW);
          goto LABEL_31;
        }
        (**(void (__fastcall ***)(HLOCAL, __int64))ObjectW)(ObjectW, 1);
        ObjectW = 0;
      }
      else
      {
        ObjectW = 0;
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_64;
        }
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_f096ec1401083a74ebdd09d5d4a36325_Traceguids, v15);
      }
    }
    if ( ObjectW )
    {
LABEL_31:
      v16 = (char *)ObjectW + 632;
      if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD))(*((_QWORD *)ObjectW + 79) + 56LL))(
              (__int64)ObjectW + 632,
              cbData) )
      {
        v17 = (BYTE *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 72LL))((__int64)ObjectW + 632);
        LODWORD(v34) = RegQueryValueExW(hKey, v8, 0, &Type, v17, &cbData);
        if ( (_DWORD)v34 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          {
LABEL_41:
            if ( v32 )
            {
              if ( v18 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v18[7] & 1) != 0 && *((_BYTE *)v18 + 25) >= 3u )
              {
                v20 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_DS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  14,
                  (unsigned int)WPP_f096ec1401083a74ebdd09d5d4a36325_Traceguids,
                  v20,
                  (__int64)a4);
              }
              RegCloseKey(hKey);
              hKey = 0;
              RegDeleteKeyW(v35, a4);
            }
            else
            {
              (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v16 + 56LL))((__int64)ObjectW + 632, 0);
              RegDeleteValueW(hKey, v8);
            }
            goto LABEL_48;
          }
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_f096ec1401083a74ebdd09d5d4a36325_Traceguids,
            v19,
            (_DWORD)v34);
LABEL_40:
          v18 = WPP_GLOBAL_Control;
          goto LABEL_41;
        }
        if ( Type != 3 )
          goto LABEL_40;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 64LL))((__int64)ObjectW + 632);
        if ( !(*(unsigned int (__fastcall **)(W32DrPRN *))(*(_QWORD *)ObjectW + 8LL))(ObjectW) )
          goto LABEL_40;
      }
LABEL_48:
      if ( !(*(unsigned int (__fastcall **)(W32DrPRN *))(*(_QWORD *)ObjectW + 8LL))(ObjectW) )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control )
        {
          if ( ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v22 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_f096ec1401083a74ebdd09d5d4a36325_Traceguids, v22);
            v21 = WPP_GLOBAL_Control;
          }
          if ( v21 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v21[7] & 1) != 0 && *((_BYTE *)v21 + 25) >= 3u )
          {
            v23 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              (unsigned int)WPP_f096ec1401083a74ebdd09d5d4a36325_Traceguids,
              v23,
              (__int64)a4);
          }
        }
        v24 = (*(__int64 (__fastcall **)(W32DrPRN *))(*(_QWORD *)ObjectW + 200LL))(ObjectW);
        v25 = (RefCount *)DrObjectMgr<DrDevice>::RemoveObject(v33, v24);
        if ( v25 )
          RefCount::Release(v25);
        RefCount::Release(ObjectW);
        ObjectW = 0;
      }
    }
  }
LABEL_64:
  if ( hKey )
    RegCloseKey(hKey);
  return ObjectW;
}

```

## disassembly

```asm
0x180562fb4  mov     [rsp-8+arg_0], rbx
0x180562fb9  push    rbp
0x180562fba  push    rsi
0x180562fbb  push    rdi
0x180562fbc  push    r12
0x180562fbe  push    r13
0x180562fc0  push    r14
0x180562fc2  push    r15
0x180562fc4  lea     rbp, [rsp-1A0h]
0x180562fcc  sub     rsp, 2A0h
0x180562fd3  mov     rax, cs:__security_cookie
0x180562fda  xor     rax, rsp
0x180562fdd  mov     [rbp+1D0h+var_40], rax
0x180562fe4  xor     esi, esi
0x180562fe6  mov     [rsp+2D0h+var_260], rcx
0x180562feb  mov     [rsp+2D0h+lpdwDisposition], rsi; lpdwDisposition
0x180562ff0  lea     rcx, [rsp+2D0h+hKey]
0x180562ff5  mov     [rsp+2D0h+phkResult], rcx; phkResult
0x180562ffa  mov     rax, r8
0x180562ffd  mov     r12, r9
0x180563000  mov     [rsp+2D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180563005  mov     [rsp+2D0h+var_268], rdx
0x18056300a  xor     r9d, r9d; lpClass
0x18056300d  mov     [rsp+2D0h+samDesired], 0F003Fh; samDesired
0x180563015  xor     r8d, r8d; Reserved
0x180563018  mov     rdx, r12; lpSubKey
0x18056301b  mov     [rsp+2D0h+dwOptions], esi; dwOptions
0x18056301f  mov     rcx, rax; hKey
0x180563022  mov     [rsp+2D0h+var_258], rax
0x180563027  mov     ebx, esi
0x180563029  mov     [rsp+2D0h+cbData], esi
0x18056302d  mov     [rsp+2D0h+hKey], rsi
0x180563032  mov     [rsp+2D0h+Type], esi
0x180563036  call    cs:__imp_RegCreateKeyExW
0x18056303c  mov     r14d, eax
0x18056303f  test    eax, eax
0x180563041  jz      short loc_18056309D
0x180563043  mov     rax, cs:WPP_GLOBAL_Control
0x18056304a  lea     rsi, WPP_GLOBAL_Control
0x180563051  cmp     rax, rsi
0x180563054  jz      loc_180563568
0x18056305a  lea     edi, [rbx+1]
0x18056305d  test    [rax+1Ch], dil
0x180563061  jz      loc_180563568
0x180563067  cmp     byte ptr [rax+19h], 2
0x18056306b  jb      loc_180563568
0x180563071  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180563076  mov     rcx, cs:WPP_GLOBAL_Control
0x18056307d  lea     edx, [rbx+0Ah]
0x180563080  mov     r9d, eax
0x180563083  mov     [rsp+2D0h+dwOptions], r14d
0x180563088  lea     r8, WPP_f096ec1401083a74ebdd09d5d4a36325_Traceguids
0x18056308f  mov     rcx, [rcx+10h]
0x180563093  call    WPP_SF_Dd
0x180563098  jmp     loc_180563568
0x18056309d  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1805630a2  lea     rax, [rsp+2D0h+cbData]
0x1805630a7  mov     qword ptr [rsp+2D0h+samDesired], rax; unsigned __int16 *
0x1805630ac  lea     r13, aPrintercacheda; "PrinterCacheData"
0x1805630b3  mov     rdx, r13; lpValueName
0x1805630b6  mov     qword ptr [rsp+2D0h+dwOptions], rsi; lpData
0x1805630bb  lea     r9, [rsp+2D0h+Type]; lpType
0x1805630c0  mov     [rsp+2D0h+cbData], esi
0x1805630c4  xor     r8d, r8d; lpReserved
0x1805630c7  call    cs:__imp_RegQueryValueExW
0x1805630cd  mov     r15d, eax
0x1805630d0  mov     eax, [rsp+2D0h+cbData]
0x1805630d4  cmp     eax, cs:?_maxCacheDataSize@W32DrPRN@@1KA; ulong W32DrPRN::_maxCacheDataSize
0x1805630da  jnb     loc_180563558
0x1805630e0  test    r15d, r15d
0x1805630e3  jnz     short loc_180563138
0x1805630e5  test    eax, eax
0x1805630e7  jz      short loc_180563138
0x1805630e9  lea     rdx, asc_1806E7DE4; "/"
0x1805630f0  mov     rcx, r12; Str
0x1805630f3  call    wcsstr_0
0x1805630f8  mov     rdi, rax
0x1805630fb  test    rax, rax
0x1805630fe  jz      short loc_180563134
0x180563100  lea     rdx, asc_1806E7DE4; "/"
0x180563107  mov     rcx, rax; Str
0x18056310a  call    wcsstr_0
0x18056310f  test    rax, rax
0x180563112  jz      short loc_180563134
0x180563114  or      rax, 0FFFFFFFFFFFFFFFFh
0x180563118  inc     rax
0x18056311b  cmp     [rdi+rax*2], si
0x18056311f  jnz     short loc_180563118
0x180563121  movzx   ecx, word ptr [rdi+rax*2-2]; C
0x180563126  call    cs:__imp_isdigit
0x18056312c  test    eax, eax
0x18056312e  jnz     loc_180563558
0x180563134  mov     eax, [rsp+2D0h+cbData]
0x180563138  lea     rsi, WPP_GLOBAL_Control
0x18056313f  mov     edi, 1
0x180563144  lea     r14, WPP_f096ec1401083a74ebdd09d5d4a36325_Traceguids
0x18056314b  cmp     r15d, 2
0x18056314f  jnz     short loc_1805631B0
0x180563151  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180563156  lea     rax, [rsp+2D0h+cbData]
0x18056315b  mov     qword ptr [rsp+2D0h+samDesired], rax; lpcbData
0x180563160  lea     r13, aAutoprintercac; "AutoPrinterCacheData"
0x180563167  mov     rdx, r13; lpValueName
0x18056316a  mov     qword ptr [rsp+2D0h+dwOptions], rbx; lpData
0x18056316f  lea     r9, [rsp+2D0h+Type]; lpType
0x180563174  mov     [rsp+2D0h+var_270], ebx
0x180563178  xor     r8d, r8d; lpReserved
0x18056317b  mov     [rsp+2D0h+cbData], ebx
0x18056317f  call    cs:__imp_RegQueryValueExW
0x180563185  test    eax, eax
0x180563187  jnz     loc_1805632F6
0x18056318d  cmp     [rsp+2D0h+cbData], ebx
0x180563191  jbe     loc_1805632F6
0x180563197  mov     rcx, [rsp+2D0h+var_268]
0x18056319c  lea     r8d, [rdi+3]
0x1805631a0  mov     rdx, r12
0x1805631a3  call    ?GetObjectW@?$DrObjectMgr@VDrDevice@@@@QEAAPEAVDrDevice@@PEBGK@Z; DrObjectMgr<DrDevice>::GetObjectW(ushort const *,ulong)
0x1805631a8  mov     rbx, rax
0x1805631ab  jmp     loc_1805632F6
0x1805631b0  test    r15d, r15d
0x1805631b3  jnz     loc_180563519
0x1805631b9  test    eax, eax
0x1805631bb  jz      loc_180563519
0x1805631c1  mov     rcx, [rsp+2D0h+var_268]
0x1805631c6  call    ?GetUniqueObjectID@?$DrObjectMgr@VDrFile@@@@QEAAKXZ; DrObjectMgr<DrFile>::GetUniqueObjectID(void)
0x1805631cb  mov     r9d, eax
0x1805631ce  lea     r8, aPrnLd; "PRN%ld"
0x1805631d5  mov     edx, 104h; unsigned __int64
0x1805631da  lea     rcx, [rbp+1D0h+var_250]; unsigned __int16 *
0x1805631de  mov     r15d, eax
0x1805631e1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1805631e6  xor     ecx, ecx
0x1805631e8  mov     [rsp+2D0h+var_270], edi
0x1805631ec  mov     [rbp+1D0h+var_242], cx
0x1805631f0  mov     edx, 4C8h; uBytes
0x1805631f5  mov     ecx, 40h ; '@'; uFlags
0x1805631fa  call    cs:__imp_LocalAlloc
0x180563200  mov     rbx, rax
0x180563203  test    rax, rax
0x180563206  jz      loc_1805632B2
0x18056320c  mov     rdx, [rsp+2D0h+var_260]; struct ProcObj *
0x180563211  lea     rax, [rbp+1D0h+var_250]
0x180563215  mov     [rsp+2D0h+lpdwDisposition], rax; unsigned __int16 *
0x18056321a  lea     r9, sourceString; unsigned __int16 *
0x180563221  mov     dword ptr [rsp+2D0h+phkResult], r15d; unsigned int
0x180563226  lea     rax, [rbp+1D0h+var_250]
0x18056322a  mov     dword ptr [rsp+2D0h+lpSecurityAttributes], 0; int
0x180563232  mov     r8, r12; unsigned __int16 *
0x180563235  mov     rcx, rbx; this
0x180563238  mov     qword ptr [rsp+2D0h+dwOptions], rax; unsigned __int16 *
0x18056323d  call    ??0W32DrPRN@@QEAA@PEAVProcObj@@PEBG111HK1@Z; W32DrPRN::W32DrPRN(ProcObj *,ushort const *,ushort const *,ushort const *,ushort const *,int,ulong,ushort const *)
0x180563242  lea     rdx, ??_7W32DrManualPrn@@6BW32DrDeviceAsync@@@; const W32DrManualPrn::`vftable'{for `W32DrDeviceAsync'}
0x180563249  mov     dword ptr [rbx+4Ch], 2
0x180563250  lea     rax, ??_7W32DrManualPrn@@6BDrPRN@@@; const W32DrManualPrn::`vftable'{for `DrPRN'}
0x180563257  mov     [rbx], rdx
0x18056325a  mov     [rbx+278h], rax
0x180563261  mov     rcx, rbx
0x180563264  mov     rax, [rdx+0B0h]
0x18056326b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180563270  mov     rax, [rbx]
0x180563273  mov     rcx, rbx
0x180563276  mov     rax, [rax+8]
0x18056327a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18056327f  test    eax, eax
0x180563281  jz      short loc_18056329E
0x180563283  mov     rcx, [rsp+2D0h+var_268]
0x180563288  mov     rdx, rbx
0x18056328b  call    ?AddObject@?$DrObjectMgr@VDrDevice@@@@QEAAKPEAVDrDevice@@@Z; DrObjectMgr<DrDevice>::AddObject(DrDevice *)
0x180563290  test    eax, eax
0x180563292  jnz     short loc_18056329E
0x180563294  mov     rcx, rbx; this
0x180563297  call    ?AddRef@RefCount@@QEAAKXZ; RefCount::AddRef(void)
0x18056329c  jmp     short loc_1805632FF
0x18056329e  mov     rax, [rbx]
0x1805632a1  mov     edx, edi
0x1805632a3  mov     rcx, rbx
0x1805632a6  mov     rax, [rax]
0x1805632a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805632ae  xor     ebx, ebx
0x1805632b0  jmp     short loc_1805632F6
0x1805632b2  mov     rax, cs:WPP_GLOBAL_Control
0x1805632b9  xor     ebx, ebx
0x1805632bb  cmp     rax, rsi
0x1805632be  jz      loc_180563558
0x1805632c4  test    [rax+1Ch], dil
0x1805632c8  jz      loc_180563558
0x1805632ce  cmp     byte ptr [rax+19h], 2
0x1805632d2  jb      loc_180563558
0x1805632d8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805632dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1805632e4  lea     edx, [rbx+0Bh]
0x1805632e7  mov     r9d, eax
0x1805632ea  mov     r8, r14
0x1805632ed  mov     rcx, [rcx+10h]
0x1805632f1  call    WPP_SF_d
0x1805632f6  test    rbx, rbx
0x1805632f9  jz      loc_180563558
0x1805632ff  mov     edx, [rsp+2D0h+cbData]
0x180563303  lea     r15, [rbx+278h]
0x18056330a  mov     rax, [r15]
0x18056330d  mov     rcx, r15
0x180563310  mov     rax, [rax+38h]
0x180563314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180563319  test    eax, eax
0x18056331b  jnz     loc_180563453
0x180563321  mov     rax, [r15]
0x180563324  mov     rcx, r15
0x180563327  mov     rax, [rax+48h]
0x18056332b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180563330  lea     rcx, [rsp+2D0h+cbData]
0x180563335  xor     r8d, r8d; lpReserved
0x180563338  mov     qword ptr [rsp+2D0h+samDesired], rcx; lpcbData
0x18056333d  lea     r9, [rsp+2D0h+Type]; lpType
0x180563342  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180563347  mov     rdx, r13; lpValueName
0x18056334a  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18056334f  call    cs:__imp_RegQueryValueExW
0x180563355  mov     dword ptr [rsp+2D0h+var_260], eax
0x180563359  test    eax, eax
0x18056335b  jnz     short loc_18056338C
0x18056335d  cmp     [rsp+2D0h+Type], 3
0x180563362  jnz     short loc_1805633CC
0x180563364  mov     rax, [r15]
0x180563367  mov     rcx, r15
0x18056336a  mov     rax, [rax+40h]
0x18056336e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180563373  mov     rax, [rbx]
0x180563376  mov     rcx, rbx
0x180563379  mov     rax, [rax+8]
0x18056337d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180563382  test    eax, eax
0x180563384  jnz     loc_180563453
0x18056338a  jmp     short loc_1805633CC
0x18056338c  mov     rax, cs:WPP_GLOBAL_Control
0x180563393  cmp     rax, rsi
0x180563396  jz      short loc_1805633D3
0x180563398  test    [rax+1Ch], dil
0x18056339c  jz      short loc_1805633D3
0x18056339e  cmp     byte ptr [rax+19h], 4
0x1805633a2  jb      short loc_1805633D3
0x1805633a4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805633a9  mov     ecx, dword ptr [rsp+2D0h+var_260]
0x1805633ad  mov     edx, 0Dh
0x1805633b2  mov     [rsp+2D0h+dwOptions], ecx
0x1805633b6  mov     r9d, eax
0x1805633b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1805633c0  mov     r8, r14
0x1805633c3  mov     rcx, [rcx+10h]
0x1805633c7  call    WPP_SF_Dd
0x1805633cc  mov     rax, cs:WPP_GLOBAL_Control
0x1805633d3  cmp     [rsp+2D0h+var_270], 0
0x1805633d8  jz      short loc_180563434
0x1805633da  cmp     rax, rsi
0x1805633dd  jz      short loc_180563410
0x1805633df  test    [rax+1Ch], dil
0x1805633e3  jz      short loc_180563410
0x1805633e5  cmp     byte ptr [rax+19h], 3
0x1805633e9  jb      short loc_180563410
0x1805633eb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805633f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1805633f7  mov     edx, 0Eh
0x1805633fc  mov     r9d, eax
0x1805633ff  mov     qword ptr [rsp+2D0h+dwOptions], r12
0x180563404  mov     r8, r14
0x180563407  mov     rcx, [rcx+10h]
0x18056340b  call    WPP_SF_DS
0x180563410  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180563415  call    cs:__imp_RegCloseKey
0x18056341b  mov     rcx, [rsp+2D0h+var_258]; hKey
0x180563420  mov     rdx, r12; lpSubKey
0x180563423  mov     [rsp+2D0h+hKey], 0
0x18056342c  call    cs:__imp_RegDeleteKeyW
0x180563432  jmp     short loc_180563453
0x180563434  mov     rax, [r15]
0x180563437  xor     edx, edx
0x180563439  mov     rcx, r15
0x18056343c  mov     rax, [rax+38h]
0x180563440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180563445  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18056344a  mov     rdx, r13; lpValueName
0x18056344d  call    cs:__imp_RegDeleteValueW
0x180563453  mov     rax, [rbx]
0x180563456  mov     rcx, rbx
0x180563459  mov     rax, [rax+8]
0x18056345d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180563462  test    eax, eax
0x180563464  jnz     loc_180563558
0x18056346a  mov     rax, cs:WPP_GLOBAL_Control
0x180563471  cmp     rax, rsi
0x180563474  jz      short loc_1805634DF
0x180563476  test    [rax+1Ch], dil
0x18056347a  jz      short loc_1805634A9
0x18056347c  cmp     byte ptr [rax+19h], 2
0x180563480  jb      short loc_1805634A9
0x180563482  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180563487  mov     rcx, cs:WPP_GLOBAL_Control
0x18056348e  mov     edx, 0Fh
0x180563493  mov     r9d, eax
0x180563496  mov     r8, r14
0x180563499  mov     rcx, [rcx+10h]
  ... truncated ...
```
