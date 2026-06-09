# SrvCryptGetProviderProperty

- ea: `0x180002dc0`
- end: `0x180003010`
- name: `SrvCryptGetProviderProperty`
- size: `592`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *, __int64, _WORD *, __int64, unsigned int, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002dc0`
- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180005510`
- `0x180019010`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180002df6`
- `ntdll!RtlEnterCriticalSection` at `0x180002df6`
- `ntdll!RtlLeaveCriticalSection` at `0x180002e2d`
- `ntdll!RtlLeaveCriticalSection` at `0x180002e2d`

## string_xrefs

- `0x180002e84`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180002f33`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180002f83`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180002fee`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptGetProviderProperty(
        struct _RTL_CRITICAL_SECTION *a1,
        __int64 a2,
        _WORD *a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        int a7)
{
  struct _RTL_CRITICAL_SECTION *v11; // r14
  unsigned __int64 v12; // rbx
  int v13; // esi
  struct _RTL_CRITICAL_SECTION *v14; // rdi
  _QWORD *p_Type; // rax
  int v16; // edx
  int v17; // r8d
  int v18; // esi
  __int64 v19; // rdi
  __int64 v20; // rcx
  _WORD *v21; // rax
  int v22; // ebx
  int v23; // edx
  unsigned int v24; // ebx
  int v25; // r8d
  int v26; // eax
  __int64 v28; // r9

  if ( a1 )
  {
    v11 = a1 + 1;
    v12 = 0;
    v13 = 0;
    RtlEnterCriticalSection(a1 + 1);
    v14 = a1 + 2;
    p_Type = &v14->DebugInfo->Type;
    while ( p_Type != (_QWORD *)v14 )
    {
      v12 = (unsigned __int64)(p_Type - 2);
      p_Type = (_QWORD *)*p_Type;
      if ( *(_QWORD *)(v12 + 360) == a2 )
      {
        if ( *(_DWORD *)v12 == 1145324614 )
        {
          _InterlockedIncrement64((volatile signed __int64 *)(v12 + 8));
          v13 = 1;
        }
        break;
      }
    }
    RtlLeaveCriticalSection(v11);
    v18 = -v13;
    v19 = v12 & -(__int64)(v18 != 0);
    if ( v19 )
    {
      if ( a3 )
      {
        v20 = 64;
        v21 = a3;
        while ( *v21 )
        {
          ++v21;
          if ( !--v20 )
          {
            v22 = -2146893785;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v16,
                v17,
                (unsigned int)"Status",
                39,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
                57);
            goto LABEL_18;
          }
        }
        if ( !a6 )
        {
          v28 = 3136;
          goto LABEL_35;
        }
        v24 = (*(__int64 (__fastcall **)(_QWORD, _WORD *, __int64, _QWORD, __int64, int))((v12 & -(__int64)(v18 != 0))
                                                                                        + 0x48))(
                *(_QWORD *)((v12 & -(__int64)(v18 != 0)) + 0x128),
                a3,
                a4,
                a5,
                a6,
                a7);
        if ( v24 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v23,
              v25,
              (unsigned int)"Status",
              v24,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
              82);
          v22 = NormalizeNteStatus(v24);
        }
        else
        {
          v22 = 0;
        }
      }
      else
      {
        v28 = 3122;
LABEL_35:
        v22 = -2146893785;
        DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v28);
      }
LABEL_18:
      v26 = SrvDereferenceProvider(v19);
      if ( v26 < 0 && v22 >= 0 )
        return (unsigned int)v26;
    }
    else
    {
      v22 = -2146893786;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v16,
          v17,
          (unsigned int)"Status",
          38,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          43);
    }
  }
  else
  {
    v22 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
        34);
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180002dc0  push    rbx
0x180002dc2  push    rbp
0x180002dc3  push    rsi
0x180002dc4  push    rdi
0x180002dc5  push    r12
0x180002dc7  push    r13
0x180002dc9  push    r14
0x180002dcb  push    r15
0x180002dcd  sub     rsp, 48h
0x180002dd1  xor     r13d, r13d
0x180002dd4  mov     r12, r9
0x180002dd7  mov     rbp, r8
0x180002dda  mov     r15, rdx
0x180002ddd  mov     rdi, rcx
0x180002de0  test    rcx, rcx
0x180002de3  jz      loc_180002F09
0x180002de9  lea     r14, [rcx+28h]
0x180002ded  mov     ebx, r13d
0x180002df0  mov     rcx, r14; CriticalSection
0x180002df3  mov     esi, r13d
0x180002df6  call    cs:__imp_RtlEnterCriticalSection
0x180002dfc  add     rdi, 50h ; 'P'
0x180002e00  mov     rax, [rdi]
0x180002e03  cmp     rax, rdi
0x180002e06  jz      short loc_180002E2A
0x180002e08  lea     rbx, [rax-10h]
0x180002e0c  mov     rax, [rax]
0x180002e0f  cmp     [rbx+168h], r15
0x180002e16  jnz     short loc_180002E03
0x180002e18  cmp     dword ptr [rbx], 44444446h
0x180002e1e  jnz     short loc_180002E2A
0x180002e20  lock inc qword ptr [rbx+8]
0x180002e25  mov     esi, 1
0x180002e2a  mov     rcx, r14; CriticalSection
0x180002e2d  call    cs:__imp_RtlLeaveCriticalSection
0x180002e33  neg     esi
0x180002e35  sbb     rdi, rdi
0x180002e38  and     rdi, rbx
0x180002e3b  jz      loc_180002FB5
0x180002e41  test    rbp, rbp
0x180002e44  jz      loc_180002FE0
0x180002e4a  mov     ecx, 40h ; '@'
0x180002e4f  mov     rax, rbp
0x180002e52  cmp     [rax], r13w
0x180002e56  jz      short loc_180002EAE
0x180002e58  add     rax, 2
0x180002e5c  sub     rcx, 1
0x180002e60  jnz     short loc_180002E52
0x180002e62  mov     ebx, 80090027h
0x180002e67  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e6e  lea     rax, WPP_GLOBAL_Control
0x180002e75  cmp     rcx, rax
0x180002e78  jz      short loc_180002EF6
0x180002e7a  test    byte ptr [rcx+1Ch], 1
0x180002e7e  jz      short loc_180002EF6
0x180002e80  mov     rcx, [rcx+10h]
0x180002e84  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002e8b  mov     [rsp+88h+var_58], 0C39h
0x180002e93  lea     r9, aStatus; "Status"
0x180002e9a  mov     [rsp+88h+var_60], rax
0x180002e9f  mov     dword ptr [rsp+88h+var_68], 80090027h
0x180002ea7  call    WPP_SF_sDsd
0x180002eac  jmp     short loc_180002EF6
0x180002eae  mov     rcx, [rsp+88h+arg_28]
0x180002eb6  test    rcx, rcx
0x180002eb9  jz      loc_180002FE8
0x180002ebf  mov     eax, [rsp+88h+arg_30]
0x180002ec6  mov     r8, r12
0x180002ec9  mov     r9d, [rsp+88h+arg_20]
0x180002ed1  mov     rdx, rbp
0x180002ed4  mov     dword ptr [rsp+88h+var_60], eax
0x180002ed8  mov     rax, [rdi+48h]
0x180002edc  mov     [rsp+88h+var_68], rcx
0x180002ee1  mov     rcx, [rdi+128h]
0x180002ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eed  mov     ebx, eax
0x180002eef  test    eax, eax
0x180002ef1  jnz     short loc_180002F66
0x180002ef3  mov     ebx, r13d
0x180002ef6  mov     rcx, rdi
0x180002ef9  call    SrvDereferenceProvider
0x180002efe  test    eax, eax
0x180002f00  jns     short loc_180002F53
0x180002f02  test    ebx, ebx
0x180002f04  cmovns  ebx, eax
0x180002f07  jmp     short loc_180002F53
0x180002f09  mov     ebx, 80090026h
0x180002f0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f15  lea     rax, WPP_GLOBAL_Control
0x180002f1c  cmp     rcx, rax
0x180002f1f  jz      short loc_180002F53
0x180002f21  test    byte ptr [rcx+1Ch], 1
0x180002f25  jz      short loc_180002F53
0x180002f27  mov     [rsp+88h+var_58], 0C22h
0x180002f2f  mov     rcx, [rcx+10h]
0x180002f33  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002f3a  mov     [rsp+88h+var_60], rax
0x180002f3f  lea     r9, aStatus; "Status"
0x180002f46  mov     dword ptr [rsp+88h+var_68], 80090026h
0x180002f4e  call    WPP_SF_sDsd
0x180002f53  mov     eax, ebx
0x180002f55  add     rsp, 48h
0x180002f59  pop     r15
0x180002f5b  pop     r14
0x180002f5d  pop     r13
0x180002f5f  pop     r12
0x180002f61  pop     rdi
0x180002f62  pop     rsi
0x180002f63  pop     rbp
0x180002f64  pop     rbx
0x180002f65  retn
0x180002f66  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f6d  lea     rax, WPP_GLOBAL_Control
0x180002f74  cmp     rcx, rax
0x180002f77  jz      short loc_180002FA7
0x180002f79  test    byte ptr [rcx+1Ch], 1
0x180002f7d  jz      short loc_180002FA7
0x180002f7f  mov     rcx, [rcx+10h]
0x180002f83  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002f8a  mov     [rsp+88h+var_58], 0C52h
0x180002f92  lea     r9, aStatus; "Status"
0x180002f99  mov     [rsp+88h+var_60], rax
0x180002f9e  mov     dword ptr [rsp+88h+var_68], ebx
0x180002fa2  call    WPP_SF_sDsd
0x180002fa7  mov     ecx, ebx
0x180002fa9  call    NormalizeNteStatus
0x180002fae  mov     ebx, eax
0x180002fb0  jmp     loc_180002EF6
0x180002fb5  mov     ebx, 80090026h
0x180002fba  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fc1  lea     rax, WPP_GLOBAL_Control
0x180002fc8  cmp     rcx, rax
0x180002fcb  jz      short loc_180002F53
0x180002fcd  test    byte ptr [rcx+1Ch], 1
0x180002fd1  jz      short loc_180002F53
0x180002fd3  mov     [rsp+88h+var_58], 0C2Bh
0x180002fdb  jmp     loc_180002F2F
0x180002fe0  mov     r9d, 0C32h
0x180002fe6  jmp     short loc_180002FEE
0x180002fe8  mov     r9d, 0C40h
0x180002fee  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002ff5  mov     ecx, 80090027h
0x180002ffa  lea     rdx, aStatus; "Status"
0x180003001  mov     ebx, 80090027h
0x180003006  call    DebugTraceError
0x18000300b  jmp     loc_180002EF6
```
