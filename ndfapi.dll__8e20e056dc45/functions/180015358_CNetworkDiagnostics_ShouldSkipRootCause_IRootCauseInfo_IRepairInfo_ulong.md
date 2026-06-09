# CNetworkDiagnostics::ShouldSkipRootCause(IRootCauseInfo *,IRepairInfo *,ulong *)

- ea: `0x180015358`
- end: `0x180015563`
- name: `?ShouldSkipRootCause@CNetworkDiagnostics@@AEAAJPEAUIRootCauseInfo@@PEAUIRepairInfo@@PEAK@Z`
- size: `523`
- prototype: `int(CNetworkDiagnostics *__hidden this, struct IRootCauseInfo *, struct IRepairInfo *, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800151b0`
- `0x180015570`

## callees

- `0x18000cf04`
- `0x180013f78`
- `0x180015358`
- `0x18001f646`
- `0x18001f690`
- `0x180021010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180015527`
- `KERNEL32!GetLastError` at `0x180015527`
- `OLEAUT32!__imp_SysFreeString` at `0x180015540`
- `OLEAUT32!__imp_SysFreeString` at `0x180015540`
- `SHLWAPI!__imp_GUIDFromStringW` at `0x1800154d1`
- `SHLWAPI!__imp_GUIDFromStringW` at `0x1800154d1`

## pseudocode

```c
__int64 __fastcall CNetworkDiagnostics::ShouldSkipRootCause(
        CNetworkDiagnostics *this,
        struct IRootCauseInfo *a2,
        struct IRepairInfo *a3,
        unsigned int *a4)
{
  int v4; // edi
  signed int v8; // eax
  signed int LastInteractiveRepairInterfaceID; // ebx
  __int64 v10; // rax
  int v11; // esi
  int v12; // eax
  CNetDiagClient *v13; // rcx
  __int64 v14; // rax
  signed int LastError; // eax
  int v17; // [rsp+20h] [rbp-40h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-38h] BYREF
  int v19; // [rsp+30h] [rbp-30h] BYREF
  struct _GUID Buf1; // [rsp+38h] [rbp-28h] BYREF
  __int128 Buf2; // [rsp+48h] [rbp-18h] BYREF

  v4 = 0;
  *a4 = 0;
  v17 = 0;
  if ( a3 )
  {
    v8 = IsRepairInteractive(a3, &v17);
    v4 = v17;
    LastInteractiveRepairInterfaceID = v8;
  }
  else
  {
    v10 = *(_QWORD *)a2;
    *(_QWORD *)&Buf2 = 0;
    LastInteractiveRepairInterfaceID = (*(__int64 (__fastcall **)(struct IRootCauseInfo *, __int128 *))(v10 + 96))(
                                         a2,
                                         &Buf2);
    if ( LastInteractiveRepairInterfaceID < 0 )
      return (unsigned int)LastInteractiveRepairInterfaceID;
    v17 = 0;
    LastInteractiveRepairInterfaceID = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)Buf2 + 72LL))(Buf2, &v17);
    if ( LastInteractiveRepairInterfaceID >= 0 )
    {
      v11 = 0;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)Buf2 + 64LL))(Buf2);
      v12 = v17;
      if ( v17 )
      {
        while ( LastInteractiveRepairInterfaceID >= 0 )
        {
          bstrString = 0;
          LastInteractiveRepairInterfaceID = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(*(_QWORD *)Buf2 + 56LL))(
                                               Buf2,
                                               &bstrString);
          if ( LastInteractiveRepairInterfaceID >= 0 )
          {
            v19 = 0;
            LastInteractiveRepairInterfaceID = IsRepairInteractive((struct IRepairInfo *)bstrString, &v19);
            (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
            if ( LastInteractiveRepairInterfaceID >= 0 && !v19 )
            {
              v12 = v17;
              break;
            }
          }
          v12 = v17;
          if ( ++v11 >= (unsigned int)v17 )
            break;
        }
      }
      if ( v11 == v12 )
        v4 = 1;
    }
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)Buf2 + 16LL))(Buf2);
  }
  if ( v4 )
  {
    v13 = (CNetDiagClient *)*((_QWORD *)this + 2);
    Buf1 = 0;
    LastInteractiveRepairInterfaceID = CNetDiagClient::GetLastInteractiveRepairInterfaceID(v13, &Buf1);
    if ( !LastInteractiveRepairInterfaceID )
    {
      v14 = *(_QWORD *)a2;
      bstrString = 0;
      LastInteractiveRepairInterfaceID = (*(__int64 (__fastcall **)(struct IRootCauseInfo *, BSTR *))(v14 + 88))(
                                           a2,
                                           &bstrString);
      if ( LastInteractiveRepairInterfaceID >= 0 )
      {
        Buf2 = 0;
        if ( (unsigned int)GUIDFromStringW(bstrString, &Buf2) )
        {
          if ( memcmp_0(qword_1800276A8, &Buf2, 0x10u)
            && memcmp_0(qword_1800276A8, &Buf1, 0x10u)
            && memcmp_0(&Buf1, &Buf2, 0x10u) )
          {
            *a4 = 1;
          }
        }
        else
        {
          LastError = GetLastError();
          LastInteractiveRepairInterfaceID = LastError;
          if ( LastError > 0 )
            LastInteractiveRepairInterfaceID = (unsigned __int16)LastError | 0x80070000;
        }
        SysFreeString(bstrString);
      }
    }
  }
  return (unsigned int)LastInteractiveRepairInterfaceID;
}

```

## disassembly

```asm
0x180015358  push    rbp
0x18001535a  push    rbx
0x18001535b  push    rsi
0x18001535c  push    rdi
0x18001535d  push    r13
0x18001535f  push    r14
0x180015361  push    r15
0x180015363  mov     rbp, rsp
0x180015366  sub     rsp, 60h
0x18001536a  mov     rax, cs:__security_cookie
0x180015371  xor     rax, rsp
0x180015374  mov     [rbp+var_8], rax
0x180015378  xor     edi, edi
0x18001537a  mov     dword ptr [r9], 0
0x180015381  mov     [rbp+var_40], edi
0x180015384  mov     r15, r9
0x180015387  mov     r14, rdx
0x18001538a  mov     r13, rcx
0x18001538d  lea     esi, [rdi+1]
0x180015390  test    r8, r8
0x180015393  jz      short loc_1800153AB
0x180015395  lea     rdx, [rbp+var_40]; int *
0x180015399  mov     rcx, r8; struct IRepairInfo *
0x18001539c  call    ?IsRepairInteractive@@YAJPEAUIRepairInfo@@PEAH@Z; IsRepairInteractive(IRepairInfo *,int *)
0x1800153a1  mov     edi, [rbp+var_40]
0x1800153a4  mov     ebx, eax
0x1800153a6  jmp     loc_180015477
0x1800153ab  mov     rax, [rdx]
0x1800153ae  mov     rcx, r14
0x1800153b1  lea     rdx, [rbp+Buf2]
0x1800153b5  mov     qword ptr [rbp+Buf2], rdi
0x1800153b9  mov     rax, [rax+60h]
0x1800153bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153c2  mov     ebx, eax
0x1800153c4  test    eax, eax
0x1800153c6  js      loc_180015546
0x1800153cc  mov     rcx, qword ptr [rbp+Buf2]
0x1800153d0  lea     rdx, [rbp+var_40]
0x1800153d4  mov     [rbp+var_40], edi
0x1800153d7  mov     rax, [rcx]
0x1800153da  mov     rax, [rax+48h]
0x1800153de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153e3  mov     ebx, eax
0x1800153e5  test    eax, eax
0x1800153e7  js      short loc_180015467
0x1800153e9  mov     rcx, qword ptr [rbp+Buf2]
0x1800153ed  xor     esi, esi
0x1800153ef  mov     rax, [rcx]
0x1800153f2  mov     rax, [rax+40h]
0x1800153f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153fb  mov     eax, [rbp+var_40]
0x1800153fe  test    eax, eax
0x180015400  jz      short loc_18001545D
0x180015402  test    ebx, ebx
0x180015404  js      short loc_18001545D
0x180015406  mov     rcx, qword ptr [rbp+Buf2]
0x18001540a  lea     rdx, [rbp+bstrString]
0x18001540e  mov     [rbp+bstrString], rdi
0x180015412  mov     rax, [rcx]
0x180015415  mov     rax, [rax+38h]
0x180015419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001541e  mov     ebx, eax
0x180015420  test    eax, eax
0x180015422  js      short loc_18001544F
0x180015424  mov     rcx, [rbp+bstrString]; struct IRepairInfo *
0x180015428  lea     rdx, [rbp+var_30]; int *
0x18001542c  mov     [rbp+var_30], edi
0x18001542f  call    ?IsRepairInteractive@@YAJPEAUIRepairInfo@@PEAH@Z; IsRepairInteractive(IRepairInfo *,int *)
0x180015434  mov     rcx, [rbp+bstrString]
0x180015438  mov     ebx, eax
0x18001543a  mov     rax, [rcx]
0x18001543d  mov     rax, [rax+10h]
0x180015441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015446  test    ebx, ebx
0x180015448  js      short loc_18001544F
0x18001544a  cmp     [rbp+var_30], edi
0x18001544d  jz      short loc_18001545A
0x18001544f  mov     eax, [rbp+var_40]
0x180015452  inc     esi
0x180015454  cmp     esi, eax
0x180015456  jb      short loc_180015402
0x180015458  jmp     short loc_18001545D
0x18001545a  mov     eax, [rbp+var_40]
0x18001545d  cmp     esi, eax
0x18001545f  mov     esi, 1
0x180015464  cmovz   edi, esi
0x180015467  mov     rcx, qword ptr [rbp+Buf2]
0x18001546b  mov     rax, [rcx]
0x18001546e  mov     rax, [rax+10h]
0x180015472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015477  test    edi, edi
0x180015479  jz      loc_180015546
0x18001547f  mov     rcx, [r13+10h]; this
0x180015483  lea     rdx, [rbp+Buf1]; struct _GUID *
0x180015487  xorps   xmm0, xmm0
0x18001548a  movups  [rbp+Buf1], xmm0
0x18001548e  call    ?GetLastInteractiveRepairInterfaceID@CNetDiagClient@@QEAAJPEAU_GUID@@@Z; CNetDiagClient::GetLastInteractiveRepairInterfaceID(_GUID *)
0x180015493  mov     ebx, eax
0x180015495  test    eax, eax
0x180015497  jnz     loc_180015546
0x18001549d  mov     rax, [r14]
0x1800154a0  lea     rdx, [rbp+bstrString]
0x1800154a4  mov     rcx, r14
0x1800154a7  mov     [rbp+bstrString], 0
0x1800154af  mov     rax, [rax+58h]
0x1800154b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154b8  mov     ebx, eax
0x1800154ba  test    eax, eax
0x1800154bc  js      loc_180015546
0x1800154c2  mov     rcx, [rbp+bstrString]
0x1800154c6  lea     rdx, [rbp+Buf2]
0x1800154ca  xorps   xmm0, xmm0
0x1800154cd  movups  [rbp+Buf2], xmm0
0x1800154d1  call    cs:__imp_GUIDFromStringW
0x1800154d7  test    eax, eax
0x1800154d9  jz      short loc_180015527
0x1800154db  mov     edi, 10h
0x1800154e0  lea     rdx, [rbp+Buf2]; Buf2
0x1800154e4  mov     r8d, edi; Size
0x1800154e7  lea     rcx, qword_1800276A8; Buf1
0x1800154ee  call    memcmp_0
0x1800154f3  test    eax, eax
0x1800154f5  jz      short loc_18001553C
0x1800154f7  mov     r8d, edi; Size
0x1800154fa  lea     rdx, [rbp+Buf1]; Buf2
0x1800154fe  lea     rcx, qword_1800276A8; Buf1
0x180015505  call    memcmp_0
0x18001550a  test    eax, eax
0x18001550c  jz      short loc_18001553C
0x18001550e  mov     r8d, edi; Size
0x180015511  lea     rdx, [rbp+Buf2]; Buf2
0x180015515  lea     rcx, [rbp+Buf1]; Buf1
0x180015519  call    memcmp_0
0x18001551e  test    eax, eax
0x180015520  jz      short loc_18001553C
0x180015522  mov     [r15], esi
0x180015525  jmp     short loc_18001553C
0x180015527  call    cs:__imp_GetLastError
0x18001552d  mov     ebx, eax
0x18001552f  test    eax, eax
0x180015531  jle     short loc_18001553C
0x180015533  movzx   ebx, ax
0x180015536  or      ebx, 80070000h
0x18001553c  mov     rcx, [rbp+bstrString]; bstrString
0x180015540  call    cs:__imp_SysFreeString
0x180015546  mov     eax, ebx
0x180015548  mov     rcx, [rbp+var_8]
0x18001554c  xor     rcx, rsp; StackCookie
0x18001554f  call    __security_check_cookie
0x180015554  add     rsp, 60h
0x180015558  pop     r15
0x18001555a  pop     r14
0x18001555c  pop     r13
0x18001555e  pop     rdi
0x18001555f  pop     rsi
0x180015560  pop     rbx
0x180015561  pop     rbp
0x180015562  retn
```
