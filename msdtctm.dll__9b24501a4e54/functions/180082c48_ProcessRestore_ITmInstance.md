# ProcessRestore(ITmInstance *)

- ea: `0x180082c48`
- end: `0x1800830bc`
- name: `?ProcessRestore@@YAJPEAUITmInstance@@@Z`
- size: `1140`
- prototype: `__int64 __fastcall(struct ITmInstance *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180017fe8`

## callees

- `0x1800063b0`
- `0x180014c68`
- `0x180015230`
- `0x180082c48`
- `0x180085a24`
- `0x180086444`
- `0x1800b83e2`
- `0x1800b83ee`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `MSDTCPRX!CreateLegacyTmInstance` at `0x180082d89`
- `MSDTCPRX!CreateLegacyTmInstance` at `0x180082d89`

## string_xrefs

- `0x180082ce6`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180082cad`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180082d9b`: `ProcessRestore: CreateLegacyTmInstance failed`
- `0x180082dac`: `CreateLegacyTmInstance failed`
- `0x180082fe4`: `ProcessRestore, DtcGetLogPathAndSize failed`
- `0x180082ff5`: `DtcGetLogPathAndSize failed`
- `0x180083092`: `ProcessRestore, CopyContact failed`
- `0x1800830a3`: `CopyContact failed`

## pseudocode

```c
__int64 __fastcall ProcessRestore(struct ITmInstance *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  int v5; // eax
  int v6; // eax
  char *v7; // rdx
  bool v8; // si
  const wchar_t *v9; // rcx
  int v10; // eax
  int v12; // eax
  int LogPathAndSize; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  int inited; // eax
  const unsigned __int16 *v17; // rdx
  int v18; // eax
  unsigned int v19; // [rsp+20h] [rbp-E0h]
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  struct ITmInstance *v21; // [rsp+48h] [rbp-B8h] BYREF
  __int128 Buf2; // [rsp+50h] [rbp-B0h] BYREF
  __int128 Buf1; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v24; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v25[526]; // [rsp+72h] [rbp-8Eh] BYREF

  v24 = 0;
  memset_0(v25, 0, 0x208u);
  v20 = 0;
  v21 = 0;
  Buf1 = 0;
  Buf2 = 0;
  TraceFile(0, "Entering ProcessRestore", "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp", 0x9FDu);
  TraceStringInline(17, 6, L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp", 2558, L"ProcessRestore", 0, L"In");
  v2 = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, __int128 *))(*(_QWORD *)a1 + 232LL))(
         a1,
         L"MSDTC",
         &Buf1);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v4 = CreateLegacyTmInstance(0, &v21);
    v3 = v4;
    if ( v4 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, __int128 *))(*(_QWORD *)v21 + 232LL))(
             v21,
             L"MSDTC",
             &Buf2);
      v3 = v5;
      if ( v5 >= 0 )
      {
        v6 = memcmp_0(&Buf1, &Buf2, 0x10u);
        v7 = "ProcessRestore: Need to synchronize legacy contacts";
        v8 = v6 == 0;
        if ( v6 )
          v7 = "ProcessRestore: No Need to synchronize legacy contacts";
        TraceFile(v3, v7, "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp", v6 == 0 ? 2589 : 2594);
        v9 = L"Need to synchronize legacy contacts";
        if ( !v8 )
          v9 = L"No Need to synchronize legacy contacts";
        TraceStringInline(
          17,
          4,
          L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
          v8 ? 2590 : 2595,
          L"ProcessRestore",
          0,
          v9);
        v10 = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *))(*(_QWORD *)a1 + 200LL))(a1, L"MSDTC");
        v3 = v10;
        if ( v10 >= 0 )
        {
          v12 = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *))(*(_QWORD *)a1 + 200LL))(
                  a1,
                  L"MSDTCKTMRM");
          v3 = v12;
          if ( v12 >= 0 )
          {
            LogPathAndSize = DtcGetLogPathAndSize(a1, &v24, &v20);
            v3 = LogPathAndSize;
            if ( LogPathAndSize >= 0 )
            {
              inited = InitLog(a1, &v24, v14, v15, v19, v20 << 20, 1, 0);
              v3 = inited;
              if ( inited )
              {
                TraceFile(
                  inited,
                  "ProcessRestore, InitLog failed",
                  "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
                  0xA44u);
                TraceStringInline(
                  17,
                  1,
                  L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
                  2629,
                  L"ProcessRestore",
                  v3,
                  L"InitLog failed");
              }
              else if ( v8 )
              {
                v18 = CopyContact(a1, v17, v21);
                v3 = v18;
                if ( v18 < 0 )
                {
                  TraceFile(
                    v18,
                    "ProcessRestore, CopyContact failed",
                    "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
                    0xA4Du);
                  TraceStringInline(
                    17,
                    1,
                    L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
                    2638,
                    L"ProcessRestore",
                    v3,
                    L"CopyContact failed");
                }
              }
            }
            else
            {
              TraceFile(
                LogPathAndSize,
                "ProcessRestore, DtcGetLogPathAndSize failed",
                "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
                0xA35u);
              TraceStringInline(
                17,
                1,
                L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
                2614,
                L"ProcessRestore",
                v3,
                L"DtcGetLogPathAndSize failed");
            }
          }
          else
          {
            TraceFile(
              v12,
              "ProcessRestore: pLocalTmInstance->ChangeContact(DTCKTMRM_CONTACT_DESC_W) failed",
              "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
              0xA2Eu);
            TraceStringInline(
              17,
              1,
              L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
              2607,
              L"ProcessRestore",
              v3,
              L"pLocalTmInstance->ChangeContact failed");
          }
        }
        else
        {
          TraceFile(
            v10,
            "ProcessRestore: pLocalTmInstance->ChangeContact failed",
            "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
            0xA28u);
        }
      }
      else
      {
        TraceFile(
          v5,
          "ProcessRestore: pLegacyTmInstance->GetContactId failed",
          "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
          0xA11u);
        TraceStringInline(
          17,
          1,
          L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
          2578,
          L"ProcessRestore",
          v3,
          L"pLegacyTmInstance->GetContactId failed");
      }
    }
    else
    {
      TraceFile(
        v4,
        "ProcessRestore: CreateLegacyTmInstance failed",
        "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
        0xA0Au);
      TraceStringInline(
        17,
        1,
        L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
        2571,
        L"ProcessRestore",
        v3,
        L"CreateLegacyTmInstance failed");
    }
  }
  else
  {
    TraceFile(
      v2,
      "ProcessRestore: pLocalTmInstance->GetContactId failed",
      "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      0xA03u);
    TraceStringInline(
      17,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      2564,
      L"ProcessRestore",
      v3,
      L"pLocalTmInstance->GetContactId failed");
  }
  if ( v21 )
    (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)v21 + 16LL))(v21);
  TraceFile(v3, "Exiting ProcessRestore", "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp", 0xA56u);
  TraceStringInline(17, 6, L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp", 2647, L"ProcessRestore", v3, L"Out");
  return v3;
}

```

## disassembly

```asm
0x180082c48  mov     [rsp-8+arg_8], rbx
0x180082c4d  mov     [rsp-8+arg_10], rsi
0x180082c52  push    rbp
0x180082c53  push    rdi
0x180082c54  push    r12
0x180082c56  push    r13
0x180082c58  push    r14
0x180082c5a  lea     rbp, [rsp-190h]
0x180082c62  sub     rsp, 290h
0x180082c69  mov     rax, cs:__security_cookie
0x180082c70  xor     rax, rsp
0x180082c73  mov     [rbp+1B0h+var_30], rax
0x180082c7a  mov     rdi, rcx
0x180082c7d  xor     eax, eax
0x180082c7f  lea     rcx, [rsp+2B0h+var_23E]; void *
0x180082c84  mov     [rsp+2B0h+var_240], ax
0x180082c89  xor     edx, edx; Val
0x180082c8b  mov     r8d, 208h; Size
0x180082c91  call    memset_0
0x180082c96  xorps   xmm0, xmm0
0x180082c99  mov     [rsp+2B0h+var_270], 0
0x180082ca1  xorps   xmm1, xmm1
0x180082ca4  mov     [rsp+2B0h+var_268], 0
0x180082cad  lea     r12, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x180082cb4  mov     r9d, 9FDh; unsigned int
0x180082cba  mov     r8, r12; char *
0x180082cbd  lea     rdx, aEnteringProces; "Entering ProcessRestore"
0x180082cc4  xor     ecx, ecx; int
0x180082cc6  movups  [rsp+2B0h+Buf1], xmm0
0x180082ccb  movups  [rsp+2B0h+Buf2], xmm1
0x180082cd0  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180082cd5  mov     edx, 6
0x180082cda  lea     rax, aIn_0; "In"
0x180082ce1  mov     qword ptr [rsp+2B0h+var_280], rax
0x180082ce6  lea     r13, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x180082ced  lea     rsi, aProcessrestore_7; "ProcessRestore"
0x180082cf4  mov     qword ptr [rsp+2B0h+var_288], 0
0x180082cfd  mov     r9d, 9FEh
0x180082d03  mov     qword ptr [rsp+2B0h+var_290], rsi
0x180082d08  lea     r14d, [rdx+0Bh]
0x180082d0c  mov     r8, r13
0x180082d0f  mov     ecx, r14d
0x180082d12  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180082d17  mov     rax, [rdi]
0x180082d1a  lea     r8, [rsp+2B0h+Buf1]
0x180082d1f  lea     rdx, aMsdtc; "MSDTC"
0x180082d26  mov     rcx, rdi
0x180082d29  mov     rax, [rax+0E8h]
0x180082d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082d35  mov     ebx, eax
0x180082d37  test    eax, eax
0x180082d39  jns     short loc_180082D82
0x180082d3b  mov     r9d, 0A03h; unsigned int
0x180082d41  lea     rdx, aProcessrestore_4; "ProcessRestore: pLocalTmInstance->GetCo"...
0x180082d48  mov     r8, r12; char *
0x180082d4b  mov     ecx, eax; int
0x180082d4d  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180082d52  lea     rax, aPlocaltminstan_0; "pLocalTmInstance->GetContactId failed"
0x180082d59  mov     r9d, 0A04h
0x180082d5f  mov     qword ptr [rsp+2B0h+var_280], rax
0x180082d64  mov     r8, r13
0x180082d67  mov     [rsp+2B0h+var_288], ebx
0x180082d6b  mov     edx, 1
0x180082d70  mov     ecx, r14d
0x180082d73  mov     qword ptr [rsp+2B0h+var_290], rsi
0x180082d78  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180082d7d  jmp     loc_180082EF2
0x180082d82  lea     rdx, [rsp+2B0h+var_268]
0x180082d87  xor     ecx, ecx
0x180082d89  call    cs:__imp_CreateLegacyTmInstance
0x180082d8f  mov     ebx, eax
0x180082d91  test    eax, eax
0x180082d93  jns     short loc_180082DBB
0x180082d95  mov     r9d, 0A0Ah; unsigned int
0x180082d9b  lea     rdx, aProcessrestore_1; "ProcessRestore: CreateLegacyTmInstance "...
0x180082da2  mov     r8, r12; char *
0x180082da5  mov     ecx, eax; int
0x180082da7  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180082dac  lea     rax, aCreatelegacytm; "CreateLegacyTmInstance failed"
0x180082db3  mov     r9d, 0A0Bh
0x180082db9  jmp     short loc_180082D5F
0x180082dbb  mov     rcx, [rsp+2B0h+var_268]
0x180082dc0  lea     r8, [rsp+2B0h+Buf2]
0x180082dc5  lea     rdx, aMsdtc; "MSDTC"
0x180082dcc  mov     rax, [rcx]
0x180082dcf  mov     rax, [rax+0E8h]
0x180082dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082ddb  mov     ebx, eax
0x180082ddd  test    eax, eax
0x180082ddf  jns     short loc_180082E0A
0x180082de1  mov     r9d, 0A11h; unsigned int
0x180082de7  lea     rdx, aProcessrestore_6; "ProcessRestore: pLegacyTmInstance->GetC"...
0x180082dee  mov     r8, r12; char *
0x180082df1  mov     ecx, eax; int
0x180082df3  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180082df8  lea     rax, aPlegacytminsta; "pLegacyTmInstance->GetContactId failed"
0x180082dff  mov     r9d, 0A12h
0x180082e05  jmp     loc_180082D5F
0x180082e0a  mov     r8d, 10h; Size
0x180082e10  lea     rdx, [rsp+2B0h+Buf2]; Buf2
0x180082e15  lea     rcx, [rsp+2B0h+Buf1]; Buf1
0x180082e1a  call    memcmp_0
0x180082e1f  test    eax, eax
0x180082e21  lea     rdx, aProcessrestore_8; "ProcessRestore: Need to synchronize leg"...
0x180082e28  mov     r14d, 0FFFFFFFBh
0x180082e2e  mov     r8, r12; char *
0x180082e31  setz    sil
0x180082e35  mov     ecx, ebx; int
0x180082e37  mov     al, sil
0x180082e3a  neg     al
0x180082e3c  lea     rax, aProcessrestore_10; "ProcessRestore: No Need to synchronize "...
0x180082e43  sbb     r9d, r9d
0x180082e46  and     r9d, r14d
0x180082e49  add     r9d, 0A22h; unsigned int
0x180082e50  test    sil, sil
0x180082e53  cmovz   rdx, rax; char *
0x180082e57  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180082e5c  lea     rax, aNoNeedToSynchr; "No Need to synchronize legacy contacts"
0x180082e63  test    sil, sil
0x180082e66  mov     edx, 4
0x180082e6b  lea     rcx, aNeedToSynchron; "Need to synchronize legacy contacts"
0x180082e72  cmovz   rcx, rax
0x180082e76  mov     r8, r13
0x180082e79  mov     qword ptr [rsp+2B0h+var_280], rcx
0x180082e7e  mov     al, sil
0x180082e81  neg     al
0x180082e83  mov     qword ptr [rsp+2B0h+var_288], 0
0x180082e8c  lea     rax, aProcessrestore_7; "ProcessRestore"
0x180082e93  sbb     r9d, r9d
0x180082e96  mov     qword ptr [rsp+2B0h+var_290], rax; unsigned int
0x180082e9b  and     r9d, r14d
0x180082e9e  lea     r14d, [rdx+0Dh]
0x180082ea2  mov     ecx, r14d
0x180082ea5  add     r9d, 0A23h
0x180082eac  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180082eb1  mov     rax, [rdi]
0x180082eb4  lea     rdx, aMsdtc; "MSDTC"
0x180082ebb  mov     rcx, rdi
0x180082ebe  mov     rax, [rax+0C8h]
0x180082ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082eca  mov     ebx, eax
0x180082ecc  test    eax, eax
0x180082ece  jns     loc_180082F77
0x180082ed4  mov     r9d, 0A28h; unsigned int
0x180082eda  lea     rdx, aProcessrestore_0; "ProcessRestore: pLocalTmInstance->Chang"...
0x180082ee1  mov     r8, r12; char *
0x180082ee4  mov     ecx, eax; int
0x180082ee6  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180082eeb  lea     rsi, aProcessrestore_7; "ProcessRestore"
0x180082ef2  mov     rcx, [rsp+2B0h+var_268]
0x180082ef7  test    rcx, rcx
0x180082efa  jz      short loc_180082F08
0x180082efc  mov     rax, [rcx]
0x180082eff  mov     rax, [rax+10h]
0x180082f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082f08  mov     r9d, 0A56h; unsigned int
0x180082f0e  lea     rdx, aExitingProcess; "Exiting ProcessRestore"
0x180082f15  mov     r8, r12; char *
0x180082f18  mov     ecx, ebx; int
0x180082f1a  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180082f1f  lea     rax, aOut; "Out"
0x180082f26  mov     r9d, 0A57h
0x180082f2c  mov     qword ptr [rsp+2B0h+var_280], rax
0x180082f31  mov     r8, r13
0x180082f34  mov     [rsp+2B0h+var_288], ebx
0x180082f38  mov     edx, 6
0x180082f3d  mov     ecx, r14d
0x180082f40  mov     qword ptr [rsp+2B0h+var_290], rsi
0x180082f45  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180082f4a  mov     eax, ebx
0x180082f4c  mov     rcx, [rbp+1B0h+var_30]
0x180082f53  xor     rcx, rsp; StackCookie
0x180082f56  call    __security_check_cookie
0x180082f5b  lea     r11, [rsp+2B0h+var_20]
0x180082f63  mov     rbx, [r11+38h]
0x180082f67  mov     rsi, [r11+40h]
0x180082f6b  mov     rsp, r11
0x180082f6e  pop     r14
0x180082f70  pop     r13
0x180082f72  pop     r12
0x180082f74  pop     rdi
0x180082f75  pop     rbp
0x180082f76  retn
0x180082f77  mov     rax, [rdi]
0x180082f7a  lea     rdx, aMsdtcktmrm; "MSDTCKTMRM"
0x180082f81  mov     rcx, rdi
0x180082f84  mov     rax, [rax+0C8h]
0x180082f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082f90  mov     ebx, eax
0x180082f92  test    eax, eax
0x180082f94  jns     short loc_180082FC6
0x180082f96  mov     r9d, 0A2Eh; unsigned int
0x180082f9c  lea     rdx, aProcessrestore_5; "ProcessRestore: pLocalTmInstance->Chang"...
0x180082fa3  mov     r8, r12; char *
0x180082fa6  mov     ecx, eax; int
0x180082fa8  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180082fad  lea     rax, aPlocaltminstan; "pLocalTmInstance->ChangeContact failed"
0x180082fb4  mov     r9d, 0A2Fh
0x180082fba  lea     rsi, aProcessrestore_7; "ProcessRestore"
0x180082fc1  jmp     loc_180082D5F
0x180082fc6  lea     r8, [rsp+2B0h+var_270]; unsigned int *
0x180082fcb  mov     rcx, rdi; struct ITmInstance *
0x180082fce  lea     rdx, [rsp+2B0h+var_240]; unsigned __int16 *
0x180082fd3  call    ?DtcGetLogPathAndSize@@YAJPEAUITmInstance@@QEAGPEAK@Z; DtcGetLogPathAndSize(ITmInstance *,ushort * const,ulong *)
0x180082fd8  mov     ebx, eax
0x180082fda  test    eax, eax
0x180082fdc  jns     short loc_18008300E
0x180082fde  mov     r9d, 0A35h; unsigned int
0x180082fe4  lea     rdx, aProcessrestore; "ProcessRestore, DtcGetLogPathAndSize fa"...
0x180082feb  mov     r8, r12; char *
0x180082fee  mov     ecx, eax; int
0x180082ff0  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180082ff5  lea     rax, aDtcgetlogpatha; "DtcGetLogPathAndSize failed"
0x180082ffc  mov     r9d, 0A36h
0x180083002  lea     rsi, aProcessrestore_7; "ProcessRestore"
0x180083009  jmp     loc_180082D5F
0x18008300e  mov     eax, [rsp+2B0h+var_270]
0x180083012  lea     rdx, [rsp+2B0h+var_240]; unsigned __int16 *
0x180083017  shl     eax, 14h
0x18008301a  mov     rcx, rdi; struct ITmInstance *
0x18008301d  mov     [rsp+2B0h+var_278], 0; int
0x180083025  mov     [rsp+2B0h+var_280], 1; int
0x18008302d  mov     [rsp+2B0h+var_288], eax; unsigned int
0x180083031  call    ?InitLog@@YAJPEAUITmInstance@@PEAGKKKKHH@Z; InitLog(ITmInstance *,ushort *,ulong,ulong,ulong,ulong,int,int)
0x180083036  mov     ebx, eax
0x180083038  test    eax, eax
0x18008303a  jz      short loc_18008306C
0x18008303c  mov     r9d, 0A44h; unsigned int
0x180083042  lea     rdx, aProcessrestore_2; "ProcessRestore, InitLog failed"
0x180083049  mov     r8, r12; char *
0x18008304c  mov     ecx, eax; int
0x18008304e  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180083053  lea     rax, aInitlogFailed; "InitLog failed"
0x18008305a  mov     r9d, 0A45h
0x180083060  lea     rsi, aProcessrestore_7; "ProcessRestore"
0x180083067  jmp     loc_180082D5F
0x18008306c  test    sil, sil
0x18008306f  jz      loc_180082EEB
0x180083075  mov     r8, [rsp+2B0h+var_268]; struct ITmInstance *
0x18008307a  mov     rcx, rdi; struct ITmInstance *
0x18008307d  call    ?CopyContact@@YAJPEAUITmInstance@@PEBG0@Z; CopyContact(ITmInstance *,ushort const *,ITmInstance *)
0x180083082  mov     ebx, eax
0x180083084  test    eax, eax
0x180083086  jns     loc_180082EEB
0x18008308c  mov     r9d, 0A4Dh; unsigned int
0x180083092  lea     rdx, aProcessrestore_3; "ProcessRestore, CopyContact failed"
0x180083099  mov     r8, r12; char *
0x18008309c  mov     ecx, eax; int
0x18008309e  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x1800830a3  lea     rax, aCopycontactFai; "CopyContact failed"
0x1800830aa  mov     r9d, 0A4Eh
0x1800830b0  lea     rsi, aProcessrestore_7; "ProcessRestore"
0x1800830b7  jmp     loc_180082D5F
```
