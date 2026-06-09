# CAtomicRecoveryTask::TaskRoutine(void)

- ea: `0x18009e960`
- end: `0x18009f0ee`
- name: `?TaskRoutine@CAtomicRecoveryTask@@UEAAXXZ`
- size: `1934`
- prototype: `void __fastcall(CAtomicRecoveryTask *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800063b0`
- `0x180018d14`
- `0x18001f34c`
- `0x18009b528`
- `0x18009e960`
- `0x1800a05e4`
- `0x1800a06b8`
- `0x1800b83e2`
- `0x1800b8420`
- `0x1800bd010`

## string_xrefs

- `0x18009f0d8`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009e9fc`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009ea6b`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009eb38`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009eba3`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009ec1f`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009ec7b`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009ee39`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009ee9a`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009efb5`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009f016`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009e9ea`: `CAtomicRecoveryTask::TaskRoutine`
- `0x18009eb91`: `CAtomicRecoveryTask::TaskRoutine`
- `0x18009ebde`: `CAtomicRecoveryTask::TaskRoutine`
- `0x18009ede3`: `CAtomicRecoveryTask::TaskRoutine`
- `0x18009ee88`: `CAtomicRecoveryTask::TaskRoutine`
- `0x18009ef20`: `CAtomicRecoveryTask::TaskRoutine`
- `0x18009f004`: `CAtomicRecoveryTask::TaskRoutine`
- `0x18009e9d5`: `CAtomicRecoverTask::TaskRoutine - calling xa_open - DLL=%S`
- `0x18009ea4b`: `CAtomicRecoveryTask::TaskRoutine - returned from xa_open with error=%d - DLL=%S`
- `0x18009eb18`: `CAtomicRecoverTask::TaskRoutine - calling xa_recover DLL=%S`
- `0x18009ea9e`: `CAtomicRecovery: xa_open call failed. Error code = %d`
- `0x18009eb7c`: `CAtomicRecoverTask::TaskRoutine - returned from xa_recover with count=%d - DLL=%S`
- `0x18009ee73`: `CAtomicRecoverTask::TaskRoutine - returned from xa_rollback with error=%d - DLL=%S`
- `0x18009ee19`: `CAtomicRecoverTask::TaskRoutine - calling xa_rollback - DLL=%S`
- `0x18009ef95`: `CAtomicRecoverTask::TaskRoutine - calling xa_commit - DLL=%S`
- `0x18009efef`: `CAtomicRecoverTask::TaskRoutine - returned from xa_commit with error=%d - DLL=%S`
- `0x18009ec5b`: `CAtomicRecoveryTask::TaskRoutine - returned from xa_close with error=%d - DLL=%S`
- `0x18009ebff`: `CAtomicRecoverTask::TaskRoutine - calling xa_close - DLL=%S`

## pseudocode

```c
void __fastcall CAtomicRecoveryTask::TaskRoutine(CAtomicRecoveryTask *this)
{
  unsigned int v2; // r15d
  int v3; // r9d
  BOOL v4; // esi
  int v5; // r14d
  unsigned int v6; // edi
  int v7; // r12d
  int v8; // r13d
  _DWORD *v9; // r15
  _QWORD *v10; // rcx
  __int64 v11; // rax
  int v12; // [rsp+20h] [rbp-718h]
  int v13; // [rsp+20h] [rbp-718h]
  int v14; // [rsp+20h] [rbp-718h]
  int v15; // [rsp+30h] [rbp-708h]
  __int64 v16; // [rsp+38h] [rbp-700h]
  __int64 v17; // [rsp+38h] [rbp-700h]
  unsigned int v18; // [rsp+50h] [rbp-6E8h]
  __int128 v20; // [rsp+60h] [rbp-6D8h] BYREF
  __int128 v21; // [rsp+70h] [rbp-6C8h]
  _DWORD v22[352]; // [rsp+80h] [rbp-6B8h] BYREF
  char v23[256]; // [rsp+600h] [rbp-138h] BYREF

  v20 = 0;
  v21 = 0;
  v2 = XaRmId(*((_DWORD *)this + 20));
  v18 = v2;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11));
  try
  {
    TraceStringInline(
      11,
      4,
      L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
      2044,
      L"CAtomicRecoveryTask::TaskRoutine",
      0,
      L"CAtomicRecoverTask::TaskRoutine - calling xa_open - DLL=%S",
      *((_QWORD *)this + 8));
    **((_DWORD **)this + 17) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*((_QWORD *)this + 14) + 40LL))(
                                 *((_QWORD *)this + 15),
                                 v2,
                                 0);
    TraceStringInline(
      11,
      4,
      L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
      2048,
      L"CAtomicRecoveryTask::TaskRoutine",
      0,
      L"CAtomicRecoveryTask::TaskRoutine - returned from xa_open with error=%d - DLL=%S");
  }
  catch ( ... )
  {
    TraceStringInline(
      11,
      1,
      L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
      2053,
      L"CAtomicRecoveryTask::TaskRoutine",
      -2147430319,
      L"CAtomicRecoveryTask::TaskRoutine - exception thrown calling xa_open - DLL=%S",
      *((_QWORD *)this + 8));
    XA_TRACE_WARNING(0x8000D051, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 2054, *((char **)this + 8), v14);
    DtcXaException("xa_open");
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 40LL))(*((_QWORD *)this + 11));
  v3 = **((_DWORD **)this + 17);
  if ( v3 )
  {
    TracedStringCchPrintfA(v23, 0x100u, "CAtomicRecovery: xa_open call failed. Error code = %d", v3);
    DtcWriteToEventLoggerA(2u, 5u, 0x4000103Cu, 0, 0, v23, v15);
  }
  else
  {
    v4 = 1;
    v5 = 1;
    v6 = 0x1000000;
    while ( v4 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11));
      try
      {
        TraceStringInline(
          11,
          4,
          L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
          2091,
          L"CAtomicRecoveryTask::TaskRoutine",
          0,
          L"CAtomicRecoverTask::TaskRoutine - calling xa_recover DLL=%S",
          *((_QWORD *)this + 8));
        v7 = (*(__int64 (__fastcall **)(_DWORD *, __int64, _QWORD, _QWORD))(*((_QWORD *)this + 14) + 96LL))(
               v22,
               10,
               v2,
               v6);
        LODWORD(v16) = v7;
        TraceStringInline(
          11,
          4,
          L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
          2095,
          L"CAtomicRecoveryTask::TaskRoutine",
          0,
          L"CAtomicRecoverTask::TaskRoutine - returned from xa_recover with count=%d - DLL=%S",
          v16,
          *((_QWORD *)this + 8));
      }
      catch ( ... )
      {
        TraceStringInline(
          11,
          1,
          L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
          2101,
          L"CAtomicRecoveryTask::TaskRoutine",
          -2147430317,
          L"CAtomicRecoverTask::TaskRoutine - exception raised calling xa_recover - DLL=%S",
          *((_QWORD *)this + 8));
        XA_TRACE_WARNING(
          0x8000D053,
          "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
          2102,
          *((char **)this + 8),
          v13);
        DtcXaException("xa_recovery");
      }
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 40LL))(*((_QWORD *)this + 11));
      if ( v7 < 0 )
      {
        **((_DWORD **)this + 17) = v7;
        v5 = 0;
        break;
      }
      v8 = 0;
      v4 = (unsigned int)v7 >= 0xA;
      while ( v8 < v7 )
      {
        v9 = &v22[35 * v8];
        if ( !memcmp_0(&g_guidXATM, v9 + 7, 0x10u) )
        {
          v10 = (_QWORD *)*((_QWORD *)this + 13);
          v11 = *v10 - *(_QWORD *)(v9 + 11);
          if ( *v10 == *(_QWORD *)(v9 + 11) )
            v11 = v10[1] - *(_QWORD *)(v9 + 13);
          if ( !v11 )
          {
            v20 = *(_OWORD *)(v9 + 3);
            v21 = *(_OWORD *)(v9 + 11);
            if ( (*(unsigned int (__fastcall **)(_QWORD, __int128 *, __int64))(**((_QWORD **)this + 12) + 32LL))(
                   *((_QWORD *)this + 12),
                   &v20,
                   32) )
            {
              **((_DWORD **)this + 17) = -3;
            }
            else
            {
              XA_TRACE_WARNING(0x8000D027, 0, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 2339);
              v5 = 0;
            }
            v4 = 0;
            break;
          }
        }
        ++v8;
      }
      v6 = 0;
      v2 = v18;
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11));
    try
    {
      TraceStringInline(
        11,
        4,
        L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
        2354,
        L"CAtomicRecoveryTask::TaskRoutine",
        0,
        L"CAtomicRecoverTask::TaskRoutine - calling xa_close - DLL=%S",
        *((_QWORD *)this + 8));
      LODWORD(v17) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*((_QWORD *)this + 14) + 48LL))(
                       *((_QWORD *)this + 16),
                       (unsigned __int16)v2,
                       0);
      TraceStringInline(
        11,
        4,
        L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
        2358,
        L"CAtomicRecoveryTask::TaskRoutine",
        0,
        L"CAtomicRecoveryTask::TaskRoutine - returned from xa_close with error=%d - DLL=%S",
        v17,
        *((_QWORD *)this + 8));
    }
    catch ( ... )
    {
      TraceStringInline(
        11,
        1,
        L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
        2364,
        L"CAtomicRecoveryTask::TaskRoutine",
        -2147430318,
        L"CAtomicRecoveryTask::TaskRoutine - exception raised calling xa_close - DLL=%S",
        *((_QWORD *)this + 8));
      XA_TRACE_WARNING(0x8000D052, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 2365, *((char **)this + 8), v12);
      DtcXaException("xa_close");
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 40LL))(*((_QWORD *)this + 11));
    if ( v5 == 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 12) + 40LL))(*((_QWORD *)this + 12));
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 12) + 16LL))(*((_QWORD *)this + 12));
  *((_QWORD *)this + 12) = 0;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 24LL))(*((_QWORD *)this + 11));
  *((_QWORD *)this + 11) = 0;
  (*(void (__fastcall **)(CAtomicRecoveryTask *))(*(_QWORD *)this + 16LL))(this);
}

```

## disassembly

```asm
0x18009e960  mov     [rsp+arg_8], rbx
0x18009e965  mov     [rsp+arg_10], rsi
0x18009e96a  push    rdi
0x18009e96b  push    r12
0x18009e96d  push    r13
0x18009e96f  push    r14
0x18009e971  push    r15
0x18009e973  sub     rsp, 710h
0x18009e97a  mov     rax, cs:__security_cookie
0x18009e981  xor     rax, rsp
0x18009e984  mov     [rsp+738h+var_38], rax
0x18009e98c  mov     rbx, rcx
0x18009e98f  mov     [rsp+738h+var_6E0], rcx
0x18009e994  mov     [rsp+738h+var_6E4], 0
0x18009e99c  xorps   xmm0, xmm0
0x18009e99f  movups  [rsp+738h+var_6D8], xmm0
0x18009e9a4  movups  [rsp+738h+var_6C8], xmm0
0x18009e9a9  mov     ecx, [rcx+50h]; unsigned int
0x18009e9ac  call    ?XaRmId@@YAKI@Z; XaRmId(uint)
0x18009e9b1  mov     r15d, eax
0x18009e9b4  mov     [rsp+738h+var_6E8], eax
0x18009e9b8  mov     rdx, [rbx+58h]
0x18009e9bc  mov     rcx, [rdx]
0x18009e9bf  mov     rax, [rcx+20h]
0x18009e9c3  mov     rcx, rdx
0x18009e9c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e9cb  nop
0x18009e9cc  mov     rax, [rbx+40h]
0x18009e9d0  mov     [rsp+738h+var_700], rax
0x18009e9d5  lea     rax, aCatomicrecover_10; "CAtomicRecoverTask::TaskRoutine - calli"...
0x18009e9dc  mov     qword ptr [rsp+738h+var_708], rax
0x18009e9e1  mov     [rsp+738h+var_710], 0
0x18009e9ea  lea     r12, aCatomicrecover_2; "CAtomicRecoveryTask::TaskRoutine"
0x18009e9f1  mov     [rsp+738h+var_718], r12
0x18009e9f6  mov     r9d, 7FCh
0x18009e9fc  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009ea03  mov     r13d, 4
0x18009ea09  mov     edx, r13d
0x18009ea0c  lea     ecx, [r13+7]
0x18009ea10  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009ea15  mov     rax, [rbx+70h]
0x18009ea19  xor     r8d, r8d
0x18009ea1c  mov     edx, r15d
0x18009ea1f  mov     rcx, [rbx+78h]
0x18009ea23  mov     rax, [rax+28h]
0x18009ea27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ea2c  mov     rcx, [rbx+88h]
0x18009ea33  mov     [rcx], eax
0x18009ea35  mov     rcx, [rbx+88h]
0x18009ea3c  mov     rax, [rbx+40h]
0x18009ea40  mov     [rsp+738h+var_6F8], rax
0x18009ea45  mov     eax, [rcx]
0x18009ea47  mov     dword ptr [rsp+738h+var_700], eax
0x18009ea4b  lea     rax, aCatomicrecover_7; "CAtomicRecoveryTask::TaskRoutine - retu"...
0x18009ea52  mov     qword ptr [rsp+738h+var_708], rax; int
0x18009ea57  mov     [rsp+738h+var_710], 0
0x18009ea60  mov     [rsp+738h+var_718], r12
0x18009ea65  mov     r9d, 800h
0x18009ea6b  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009ea72  mov     edx, r13d
0x18009ea75  lea     ecx, [r13+7]
0x18009ea79  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009ea7e  nop
0x18009ea7f  mov     rcx, [rbx+58h]
0x18009ea83  mov     rax, [rcx]
0x18009ea86  mov     rax, [rax+28h]
0x18009ea8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ea8f  mov     rax, [rbx+88h]
0x18009ea96  mov     r9d, [rax]
0x18009ea99  test    r9d, r9d
0x18009ea9c  jz      short loc_18009EAE7
0x18009ea9e  lea     r8, aCatomicrecover_14; "CAtomicRecovery: xa_open call failed. E"...
0x18009eaa5  mov     edx, 100h; unsigned __int64
0x18009eaaa  lea     rcx, [rsp+738h+var_138]; char *
0x18009eab2  call    ?TracedStringCchPrintfA@@YAXPEAD_KPEBDZZ; TracedStringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18009eab7  lea     rax, [rsp+738h+var_138]
0x18009eabf  mov     [rsp+738h+var_710], rax; char *
0x18009eac4  mov     [rsp+738h+var_718], 0; void *
0x18009eacd  xor     r9d, r9d; unsigned int
0x18009ead0  lea     edx, [r9+5]; unsigned int
0x18009ead4  lea     ecx, [rdx-3]; unsigned int
0x18009ead7  mov     r8d, 4000103Ch; unsigned int
0x18009eadd  call    ?DtcWriteToEventLoggerA@@YAJKKKKPEAXPEADH@Z; DtcWriteToEventLoggerA(ulong,ulong,ulong,ulong,void *,char *,int)
0x18009eae2  jmp     loc_18009ECB6
0x18009eae7  mov     eax, 1
0x18009eaec  mov     esi, eax
0x18009eaee  mov     r14d, eax
0x18009eaf1  mov     edi, 1000000h
0x18009eaf6  test    esi, esi
0x18009eaf8  jz      loc_18009EBE5
0x18009eafe  mov     rcx, [rbx+58h]
0x18009eb02  mov     rax, [rcx]
0x18009eb05  mov     rax, [rax+20h]
0x18009eb09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eb0e  nop
0x18009eb0f  mov     rax, [rbx+40h]
0x18009eb13  mov     [rsp+738h+var_700], rax
0x18009eb18  lea     rax, aCatomicrecover_0; "CAtomicRecoverTask::TaskRoutine - calli"...
0x18009eb1f  mov     qword ptr [rsp+738h+var_708], rax
0x18009eb24  mov     [rsp+738h+var_710], 0
0x18009eb2d  mov     [rsp+738h+var_718], r12
0x18009eb32  mov     r9d, 82Bh
0x18009eb38  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009eb3f  mov     edx, r13d
0x18009eb42  mov     ecx, 0Bh
0x18009eb47  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009eb4c  mov     rax, [rbx+70h]
0x18009eb50  mov     r9d, edi
0x18009eb53  mov     r8d, r15d
0x18009eb56  mov     edx, 0Ah
0x18009eb5b  lea     rcx, [rsp+738h+var_6B8]
0x18009eb63  mov     rax, [rax+60h]
0x18009eb67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eb6c  mov     r12d, eax
0x18009eb6f  mov     rcx, [rbx+40h]
0x18009eb73  mov     [rsp+738h+var_6F8], rcx
0x18009eb78  mov     dword ptr [rsp+738h+var_700], eax
0x18009eb7c  lea     rax, aCatomicrecover; "CAtomicRecoverTask::TaskRoutine - retur"...
0x18009eb83  mov     qword ptr [rsp+738h+var_708], rax
0x18009eb88  mov     [rsp+738h+var_710], 0
0x18009eb91  lea     rdi, aCatomicrecover_2; "CAtomicRecoveryTask::TaskRoutine"
0x18009eb98  mov     [rsp+738h+var_718], rdi
0x18009eb9d  mov     r9d, 82Fh
0x18009eba3  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009ebaa  mov     edx, r13d
0x18009ebad  mov     ecx, 0Bh
0x18009ebb2  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009ebb7  nop
0x18009ebb8  mov     rcx, [rbx+58h]
0x18009ebbc  mov     rax, [rcx]
0x18009ebbf  mov     rax, [rax+28h]
0x18009ebc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ebc8  test    r12d, r12d
0x18009ebcb  jns     loc_18009ED22
0x18009ebd1  mov     rax, [rbx+88h]
0x18009ebd8  mov     [rax], r12d
0x18009ebdb  xor     r14d, r14d
0x18009ebde  lea     r12, aCatomicrecover_2; "CAtomicRecoveryTask::TaskRoutine"
0x18009ebe5  mov     rcx, [rbx+58h]
0x18009ebe9  mov     rax, [rcx]
0x18009ebec  mov     rax, [rax+20h]
0x18009ebf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ebf5  nop
0x18009ebf6  mov     rax, [rbx+40h]
0x18009ebfa  mov     [rsp+738h+var_700], rax
0x18009ebff  lea     rax, aCatomicrecover_11; "CAtomicRecoverTask::TaskRoutine - calli"...
0x18009ec06  mov     qword ptr [rsp+738h+var_708], rax
0x18009ec0b  mov     [rsp+738h+var_710], 0
0x18009ec14  mov     [rsp+738h+var_718], r12
0x18009ec19  mov     r9d, 932h
0x18009ec1f  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009ec26  mov     edx, r13d
0x18009ec29  mov     ecx, 0Bh
0x18009ec2e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009ec33  mov     rax, [rbx+70h]
0x18009ec37  movzx   edx, r15w
0x18009ec3b  xor     r8d, r8d
0x18009ec3e  mov     rcx, [rbx+80h]
0x18009ec45  mov     rax, [rax+30h]
0x18009ec49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ec4e  mov     rcx, [rbx+40h]
0x18009ec52  mov     [rsp+738h+var_6F8], rcx
0x18009ec57  mov     dword ptr [rsp+738h+var_700], eax
0x18009ec5b  lea     rax, aCatomicrecover_9; "CAtomicRecoveryTask::TaskRoutine - retu"...
0x18009ec62  mov     qword ptr [rsp+738h+var_708], rax
0x18009ec67  mov     [rsp+738h+var_710], 0
0x18009ec70  mov     [rsp+738h+var_718], r12
0x18009ec75  mov     r9d, 936h
0x18009ec7b  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009ec82  mov     edx, r13d
0x18009ec85  mov     ecx, 0Bh
0x18009ec8a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009ec8f  nop
0x18009ec90  mov     rcx, [rbx+58h]
0x18009ec94  mov     rax, [rcx]
0x18009ec97  mov     rax, [rax+28h]
0x18009ec9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eca0  cmp     r14d, 1
0x18009eca4  jnz     short loc_18009ECB6
0x18009eca6  mov     rcx, [rbx+60h]
0x18009ecaa  mov     rax, [rcx]
0x18009ecad  mov     rax, [rax+28h]
0x18009ecb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ecb6  mov     rcx, [rbx+60h]
0x18009ecba  mov     rax, [rcx]
0x18009ecbd  mov     rax, [rax+10h]
0x18009ecc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ecc6  mov     qword ptr [rbx+60h], 0
0x18009ecce  mov     rcx, [rbx+58h]
0x18009ecd2  mov     rax, [rcx]
0x18009ecd5  mov     rax, [rax+18h]
0x18009ecd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ecde  mov     qword ptr [rbx+58h], 0
0x18009ece6  mov     rax, [rbx]
0x18009ece9  mov     rcx, rbx
0x18009ecec  mov     rax, [rax+10h]
0x18009ecf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ecf5  mov     rcx, [rsp+738h+var_38]
0x18009ecfd  xor     rcx, rsp; StackCookie
0x18009ed00  call    __security_check_cookie
0x18009ed05  lea     r11, [rsp+738h+var_28]
0x18009ed0d  mov     rbx, [r11+38h]
0x18009ed11  mov     rsi, [r11+40h]
0x18009ed15  mov     rsp, r11
0x18009ed18  pop     r15
0x18009ed1a  pop     r14
0x18009ed1c  pop     r13
0x18009ed1e  pop     r12
0x18009ed20  pop     rdi
0x18009ed21  retn
0x18009ed22  xor     r13d, r13d
0x18009ed25  xor     esi, esi
0x18009ed27  cmp     r12d, 0Ah
0x18009ed2b  setnb   sil
0x18009ed2f  cmp     r13d, r12d
0x18009ed32  jge     loc_18009EDD8
0x18009ed38  movsxd  rax, r13d
0x18009ed3b  imul    rcx, rax, 8Ch
0x18009ed42  lea     r15, [rsp+738h+var_6B8]
0x18009ed4a  add     r15, rcx
0x18009ed4d  lea     rdx, [r15+1Ch]; Buf2
0x18009ed51  mov     r8d, 10h; Size
0x18009ed57  lea     rcx, ?g_guidXATM@@3U_GUID@@A; Buf1
0x18009ed5e  call    memcmp_0
0x18009ed63  test    eax, eax
0x18009ed65  jnz     loc_18009EF27
0x18009ed6b  mov     rcx, [rbx+68h]
0x18009ed6f  mov     rax, [rcx]
0x18009ed72  sub     rax, [r15+2Ch]
0x18009ed76  jnz     short loc_18009ED80
0x18009ed78  mov     rax, [rcx+8]
0x18009ed7c  sub     rax, [r15+34h]
0x18009ed80  test    rax, rax
0x18009ed83  jnz     loc_18009EF27
0x18009ed89  movups  xmm0, xmmword ptr [r15+0Ch]
0x18009ed8e  movdqu  [rsp+738h+var_6D8], xmm0
0x18009ed94  movups  xmm1, xmmword ptr [r15+2Ch]
0x18009ed99  movdqu  [rsp+738h+var_6C8], xmm1
0x18009ed9f  mov     rcx, [rbx+60h]
0x18009eda3  mov     rax, [rcx]
0x18009eda6  lea     rdx, [rsp+738h+var_6E4]
0x18009edab  mov     [rsp+738h+var_718], rdx
0x18009edb0  xor     r9d, r9d
0x18009edb3  lea     r8d, [r9+20h]
0x18009edb7  lea     rdx, [rsp+738h+var_6D8]
0x18009edbc  mov     rax, [rax+20h]
0x18009edc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009edc5  test    eax, eax
0x18009edc7  jz      short loc_18009EDEF
0x18009edc9  mov     rax, [rbx+88h]
0x18009edd0  mov     dword ptr [rax], 0FFFFFFFDh
0x18009edd6  xor     esi, esi
0x18009edd8  xor     edi, edi
0x18009edda  mov     r15d, [rsp+738h+var_6E8]
0x18009eddf  lea     r13d, [rdi+4]
0x18009ede3  lea     r12, aCatomicrecover_2; "CAtomicRecoveryTask::TaskRoutine"
0x18009edea  jmp     loc_18009EAF6
0x18009edef  mov     edx, [rsp+738h+var_6E4]; unsigned int
0x18009edf3  cmp     edx, 200h
0x18009edf9  jnz     loc_18009EF6F
0x18009edff  mov     rcx, [rbx+58h]
0x18009ee03  mov     rax, [rcx]
0x18009ee06  mov     rax, [rax+20h]
0x18009ee0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ee0f  nop
0x18009ee10  mov     rax, [rbx+40h]
0x18009ee14  mov     [rsp+738h+var_700], rax
0x18009ee19  lea     rax, aCatomicrecover_1; "CAtomicRecoverTask::TaskRoutine - calli"...
0x18009ee20  mov     qword ptr [rsp+738h+var_708], rax
0x18009ee25  mov     [rsp+738h+var_710], 0
0x18009ee2e  mov     [rsp+738h+var_718], rdi
0x18009ee33  mov     r9d, 87Eh
0x18009ee39  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009ee40  mov     edx, 4
0x18009ee45  lea     ecx, [rdx+7]
0x18009ee48  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009ee4d  mov     rax, [rbx+70h]
0x18009ee51  xor     r8d, r8d
0x18009ee54  mov     edx, [rsp+738h+var_6E8]
0x18009ee58  mov     rcx, r15
0x18009ee5b  mov     rax, [rax+48h]
0x18009ee5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ee64  mov     edi, eax
0x18009ee66  mov     rcx, [rbx+40h]
0x18009ee6a  mov     [rsp+738h+var_6F8], rcx
0x18009ee6f  mov     dword ptr [rsp+738h+var_700], eax
0x18009ee73  lea     rax, aCatomicrecover_5; "CAtomicRecoverTask::TaskRoutine - retur"...
0x18009ee7a  mov     qword ptr [rsp+738h+var_708], rax
0x18009ee7f  mov     [rsp+738h+var_710], 0
0x18009ee88  lea     rax, aCatomicrecover_2; "CAtomicRecoveryTask::TaskRoutine"
0x18009ee8f  mov     [rsp+738h+var_718], rax
0x18009ee94  mov     r9d, 882h
0x18009ee9a  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009eea1  mov     edx, 4
0x18009eea6  lea     ecx, [rdx+7]
0x18009eea9  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009eeae  nop
0x18009eeaf  mov     rcx, [rbx+58h]
0x18009eeb3  mov     rax, [rcx]
0x18009eeb6  mov     rax, [rax+28h]
  ... truncated ...
```
