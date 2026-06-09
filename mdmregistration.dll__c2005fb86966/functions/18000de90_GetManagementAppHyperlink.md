# GetManagementAppHyperlink

- ea: `0x18000de90`
- end: `0x18000e216`
- name: `GetManagementAppHyperlink`
- size: `902`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800026d0`
- `0x18000bd08`
- `0x18000de90`
- `0x18003bf04`
- `0x18004e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000e1e4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e1e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetManagementAppHyperlink(unsigned int a1, unsigned __int16 *a2)
{
  unsigned __int64 v3; // r14
  int EnrollmentByKey; // edi
  int v5; // eax
  EEDBManager *v6; // rcx
  struct Enrollment *v7; // rbx
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rax
  __int64 v11; // [rsp+20h] [rbp-60h] BYREF
  __int64 v12; // [rsp+28h] [rbp-58h] BYREF
  __int64 v13; // [rsp+30h] [rbp-50h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-48h] BYREF
  struct Enrollment *v15; // [rsp+40h] [rbp-40h] BYREF
  struct _GUID v16; // [rsp+50h] [rbp-30h] BYREF
  struct _GUID v17; // [rsp+60h] [rbp-20h] BYREF

  v3 = a1;
  bstrString = 0;
  EnrollmentByKey = 0;
  if ( a1 && a2 )
  {
    v13 = 0;
    v12 = 0;
    v11 = 0;
    v17 = 0;
    EnrollmentByKey = (*(__int64 (__fastcall **)(void *, __int64, __int64 *))(off_1800704F8 + 32LL))(
                        &off_1800704F8,
                        8289,
                        &v13);
    if ( EnrollmentByKey >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 24LL))(v13, &v12);
      EnrollmentByKey = v5;
      if ( v5 < 0 || v5 == 1 )
      {
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      else
      {
        EnrollmentByKey = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v12 + 24LL))(v12, &v17);
        if ( EnrollmentByKey >= 0 )
        {
          v15 = 0;
          v16 = v17;
          EnrollmentByKey = EEDBManager::GetEnrollmentByKey(v6, &v16, &v15);
          v7 = v15;
          if ( EnrollmentByKey >= 0 )
            EnrollmentByKey = (**(__int64 (__fastcall ***)(struct Enrollment *, GUID *, __int64 *))v15)(
                                v15,
                                &GUID_d0f03218_7463_45ae_986b_999945717e58,
                                &v11);
          if ( v7 )
            (*(void (__fastcall **)(struct Enrollment *))(*(_QWORD *)v7 + 16LL))(v7);
          if ( EnrollmentByKey >= 0 )
          {
            if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v11 + 88LL))(v11, &bstrString) >= 0 )
            {
              v8 = v3;
              v9 = -1;
              do
                ++v9;
              while ( bstrString[v9] );
              if ( v9 <= v3 )
              {
                EnrollmentByKey = StringCchCopyW(a2, v3, bstrString);
                if ( v11 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
                if ( v12 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
                if ( v13 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
              }
              else
              {
                *a2 = 0;
                EnrollmentByKey = -2147024809;
                if ( v11 )
                  (*(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v11 + 16LL))(v11, v3);
                if ( v12 )
                  (*(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v12 + 16LL))(v12, v8);
                if ( v13 )
                  (*(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v13 + 16LL))(v13, v8);
              }
            }
            else
            {
              *a2 = 0;
              EnrollmentByKey = 0;
              if ( v11 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
              if ( v12 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
              if ( v13 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            }
          }
          else
          {
            if ( v11 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
            if ( v12 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
            if ( v13 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          }
        }
        else
        {
          if ( v12 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          if ( v13 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
      }
    }
    else if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
  SysFreeString(bstrString);
  return (unsigned int)EnrollmentByKey;
}

```

## disassembly

```asm
0x18000de90  mov     [rsp-28h+arg_10], rbx
0x18000de95  push    rbp
0x18000de96  push    rsi
0x18000de97  push    rdi
0x18000de98  push    r14
0x18000de9a  push    r15
0x18000de9c  mov     rbp, rsp
0x18000de9f  sub     rsp, 80h
0x18000dea6  mov     rax, cs:__security_cookie
0x18000dead  xor     rax, rsp
0x18000deb0  mov     [rbp+var_10], rax
0x18000deb4  mov     rsi, rdx
0x18000deb7  mov     r14d, ecx
0x18000deba  xor     r15d, r15d
0x18000debd  mov     [rbp+bstrString], r15
0x18000dec1  mov     edi, r15d
0x18000dec4  test    ecx, ecx
0x18000dec6  jz      loc_18000E1E0
0x18000decc  test    rdx, rdx
0x18000decf  jz      loc_18000E1E0
0x18000ded5  mov     [rbp+var_50], r15
0x18000ded9  mov     [rbp+var_58], r15
0x18000dedd  mov     [rbp+var_60], r15
0x18000dee1  xorps   xmm0, xmm0
0x18000dee4  movups  [rbp+var_20], xmm0
0x18000dee8  mov     rax, cs:off_1800704F8
0x18000deef  lea     r8, [rbp+var_50]
0x18000def3  mov     edx, 2061h
0x18000def8  lea     rcx, off_1800704F8
0x18000deff  mov     rax, [rax+20h]
0x18000df03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df08  mov     edi, eax
0x18000df0a  test    eax, eax
0x18000df0c  jns     short loc_18000DF55
0x18000df0e  mov     rcx, [rbp+var_60]
0x18000df12  test    rcx, rcx
0x18000df15  jz      short loc_18000DF24
0x18000df17  mov     rdx, [rcx]
0x18000df1a  mov     rax, [rdx+10h]
0x18000df1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df23  nop
0x18000df24  mov     rcx, [rbp+var_58]
0x18000df28  test    rcx, rcx
0x18000df2b  jz      short loc_18000DF3A
0x18000df2d  mov     rax, [rcx]
0x18000df30  mov     rax, [rax+10h]
0x18000df34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df39  nop
0x18000df3a  mov     rcx, [rbp+var_50]
0x18000df3e  test    rcx, rcx
0x18000df41  jz      short loc_18000DF50
0x18000df43  mov     rax, [rcx]
0x18000df46  mov     rax, [rax+10h]
0x18000df4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df4f  nop
0x18000df50  jmp     loc_18000E1E0
0x18000df55  mov     rcx, [rbp+var_50]
0x18000df59  mov     rax, [rcx]
0x18000df5c  lea     rdx, [rbp+var_58]
0x18000df60  mov     rax, [rax+18h]
0x18000df64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df69  mov     edi, eax
0x18000df6b  test    eax, eax
0x18000df6d  js      loc_18000E19E
0x18000df73  cmp     eax, 1
0x18000df76  jz      loc_18000E19E
0x18000df7c  mov     rcx, [rbp+var_58]
0x18000df80  mov     rax, [rcx]
0x18000df83  lea     rdx, [rbp+var_20]
0x18000df87  mov     rax, [rax+18h]
0x18000df8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df90  mov     edi, eax
0x18000df92  test    eax, eax
0x18000df94  jns     short loc_18000DFDD
0x18000df96  mov     rcx, [rbp+var_60]
0x18000df9a  test    rcx, rcx
0x18000df9d  jz      short loc_18000DFAC
0x18000df9f  mov     rax, [rcx]
0x18000dfa2  mov     rax, [rax+10h]
0x18000dfa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfab  nop
0x18000dfac  mov     rcx, [rbp+var_58]
0x18000dfb0  test    rcx, rcx
0x18000dfb3  jz      short loc_18000DFC2
0x18000dfb5  mov     rax, [rcx]
0x18000dfb8  mov     rax, [rax+10h]
0x18000dfbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfc1  nop
0x18000dfc2  mov     rcx, [rbp+var_50]
0x18000dfc6  test    rcx, rcx
0x18000dfc9  jz      short loc_18000DFD8
0x18000dfcb  mov     rax, [rcx]
0x18000dfce  mov     rax, [rax+10h]
0x18000dfd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfd7  nop
0x18000dfd8  jmp     loc_18000E1E0
0x18000dfdd  mov     [rbp+var_40], r15
0x18000dfe1  movaps  xmm0, [rbp+var_20]
0x18000dfe5  movdqa  xmmword ptr [rbp+var_30.Data1], xmm0
0x18000dfea  lea     r8, [rbp+var_40]; struct Enrollment **
0x18000dfee  lea     rdx, [rbp+var_30]; struct _GUID
0x18000dff2  call    ?GetEnrollmentByKey@EEDBManager@@QEAAJU_GUID@@PEAPEAVEnrollment@@@Z; EEDBManager::GetEnrollmentByKey(_GUID,Enrollment * *)
0x18000dff7  mov     edi, eax
0x18000dff9  mov     rbx, [rbp+var_40]
0x18000dffd  test    eax, eax
0x18000dfff  js      short loc_18000E01C
0x18000e001  mov     rax, [rbx]
0x18000e004  lea     r8, [rbp+var_60]
0x18000e008  lea     rdx, _GUID_d0f03218_7463_45ae_986b_999945717e58
0x18000e00f  mov     rcx, rbx
0x18000e012  mov     rax, [rax]
0x18000e015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e01a  mov     edi, eax
0x18000e01c  test    rbx, rbx
0x18000e01f  jz      short loc_18000E031
0x18000e021  mov     rax, [rbx]
0x18000e024  mov     rcx, rbx
0x18000e027  mov     rax, [rax+10h]
0x18000e02b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e030  nop
0x18000e031  test    edi, edi
0x18000e033  jns     short loc_18000E07C
0x18000e035  mov     rcx, [rbp+var_60]
0x18000e039  test    rcx, rcx
0x18000e03c  jz      short loc_18000E04B
0x18000e03e  mov     rax, [rcx]
0x18000e041  mov     rax, [rax+10h]
0x18000e045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e04a  nop
0x18000e04b  mov     rcx, [rbp+var_58]
0x18000e04f  test    rcx, rcx
0x18000e052  jz      short loc_18000E061
0x18000e054  mov     rax, [rcx]
0x18000e057  mov     rax, [rax+10h]
0x18000e05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e060  nop
0x18000e061  mov     rcx, [rbp+var_50]
0x18000e065  test    rcx, rcx
0x18000e068  jz      short loc_18000E077
0x18000e06a  mov     rax, [rcx]
0x18000e06d  mov     rax, [rax+10h]
0x18000e071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e076  nop
0x18000e077  jmp     loc_18000E1E0
0x18000e07c  mov     rcx, [rbp+var_60]
0x18000e080  mov     rax, [rcx]
0x18000e083  lea     rdx, [rbp+bstrString]
0x18000e087  mov     rax, [rax+58h]
0x18000e08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e090  test    eax, eax
0x18000e092  jns     short loc_18000E0E2
0x18000e094  mov     [rsi], r15w
0x18000e098  mov     edi, r15d
0x18000e09b  mov     rcx, [rbp+var_60]
0x18000e09f  test    rcx, rcx
0x18000e0a2  jz      short loc_18000E0B1
0x18000e0a4  mov     rax, [rcx]
0x18000e0a7  mov     rax, [rax+10h]
0x18000e0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0b0  nop
0x18000e0b1  mov     rcx, [rbp+var_58]
0x18000e0b5  test    rcx, rcx
0x18000e0b8  jz      short loc_18000E0C7
0x18000e0ba  mov     rax, [rcx]
0x18000e0bd  mov     rax, [rax+10h]
0x18000e0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0c6  nop
0x18000e0c7  mov     rcx, [rbp+var_50]
0x18000e0cb  test    rcx, rcx
0x18000e0ce  jz      short loc_18000E0DD
0x18000e0d0  mov     rax, [rcx]
0x18000e0d3  mov     rax, [rax+10h]
0x18000e0d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0dc  nop
0x18000e0dd  jmp     loc_18000E1E0
0x18000e0e2  mov     rdx, r14; unsigned __int64
0x18000e0e5  mov     rcx, [rbp+bstrString]
0x18000e0e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e0ed  inc     rax
0x18000e0f0  cmp     [rcx+rax*2], r15w
0x18000e0f5  jnz     short loc_18000E0ED
0x18000e0f7  cmp     rax, rdx
0x18000e0fa  jbe     short loc_18000E14C
0x18000e0fc  mov     [rsi], r15w
0x18000e100  mov     edi, 80070057h
0x18000e105  mov     rcx, [rbp+var_60]
0x18000e109  test    rcx, rcx
0x18000e10c  jz      short loc_18000E11B
0x18000e10e  mov     rax, [rcx]
0x18000e111  mov     rax, [rax+10h]
0x18000e115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e11a  nop
0x18000e11b  mov     rcx, [rbp+var_58]
0x18000e11f  test    rcx, rcx
0x18000e122  jz      short loc_18000E131
0x18000e124  mov     rax, [rcx]
0x18000e127  mov     rax, [rax+10h]
0x18000e12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e130  nop
0x18000e131  mov     rcx, [rbp+var_50]
0x18000e135  test    rcx, rcx
0x18000e138  jz      short loc_18000E147
0x18000e13a  mov     rax, [rcx]
0x18000e13d  mov     rax, [rax+10h]
0x18000e141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e146  nop
0x18000e147  jmp     loc_18000E1E0
0x18000e14c  mov     r8, [rbp+bstrString]; unsigned __int16 *
0x18000e150  mov     rcx, rsi; unsigned __int16 *
0x18000e153  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e158  mov     edi, eax
0x18000e15a  mov     rcx, [rbp+var_60]
0x18000e15e  test    rcx, rcx
0x18000e161  jz      short loc_18000E170
0x18000e163  mov     rax, [rcx]
0x18000e166  mov     rax, [rax+10h]
0x18000e16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e16f  nop
0x18000e170  mov     rcx, [rbp+var_58]
0x18000e174  test    rcx, rcx
0x18000e177  jz      short loc_18000E186
0x18000e179  mov     rax, [rcx]
0x18000e17c  mov     rax, [rax+10h]
0x18000e180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e185  nop
0x18000e186  mov     rcx, [rbp+var_50]
0x18000e18a  test    rcx, rcx
0x18000e18d  jz      short loc_18000E19C
0x18000e18f  mov     rax, [rcx]
0x18000e192  mov     rax, [rax+10h]
0x18000e196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e19b  nop
0x18000e19c  jmp     short loc_18000E1E0
0x18000e19e  mov     rcx, [rbp+var_60]
0x18000e1a2  test    rcx, rcx
0x18000e1a5  jz      short loc_18000E1B4
0x18000e1a7  mov     rax, [rcx]
0x18000e1aa  mov     rax, [rax+10h]
0x18000e1ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1b3  nop
0x18000e1b4  mov     rcx, [rbp+var_58]
0x18000e1b8  test    rcx, rcx
0x18000e1bb  jz      short loc_18000E1CA
0x18000e1bd  mov     rax, [rcx]
0x18000e1c0  mov     rax, [rax+10h]
0x18000e1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1c9  nop
0x18000e1ca  mov     rcx, [rbp+var_50]
0x18000e1ce  test    rcx, rcx
0x18000e1d1  jz      short loc_18000E1E0
0x18000e1d3  mov     rax, [rcx]
0x18000e1d6  mov     rax, [rax+10h]
0x18000e1da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1df  nop
0x18000e1e0  mov     rcx, [rbp+bstrString]; bstrString
0x18000e1e4  call    cs:__imp_SysFreeString
0x18000e1eb  nop     dword ptr [rax+rax+00h]
0x18000e1f0  mov     eax, edi
0x18000e1f2  mov     rcx, [rbp+var_10]
0x18000e1f6  xor     rcx, rsp; StackCookie
0x18000e1f9  call    __security_check_cookie
0x18000e1fe  mov     rbx, [rsp+80h+arg_10]
0x18000e206  add     rsp, 80h
0x18000e20d  pop     r15
0x18000e20f  pop     r14
0x18000e211  pop     rdi
0x18000e212  pop     rsi
0x18000e213  pop     rbp
0x18000e214  retn
```
