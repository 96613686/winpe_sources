# SrvCryptSetKeyProperty

- ea: `0x180003d40`
- end: `0x180003f5a`
- name: `SrvCryptSetKeyProperty`
- size: `538`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _WORD *, __int64, unsigned int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180003d40`
- `0x180004470`
- `0x1800048f0`
- `0x1800055e0`
- `0x180019010`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180003d73`
- `ntdll!RtlEnterCriticalSection` at `0x180003d73`
- `ntdll!RtlLeaveCriticalSection` at `0x180003dac`
- `ntdll!RtlLeaveCriticalSection` at `0x180003dac`

## string_xrefs

- `0x180003e12`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180003eb0`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180003ed5`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180003f05`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x180003f2d`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SrvCryptSetKeyProperty(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _WORD *a4,
        __int64 a5,
        unsigned int a6,
        int a7)
{
  int v10; // esi
  _QWORD *v11; // r14
  _QWORD *v12; // rax
  int v13; // edx
  __int64 v14; // rcx
  _WORD *v15; // rax
  int v16; // ebx
  int v17; // eax
  unsigned int v19; // eax
  __int64 v20; // r9

  if ( a1 )
  {
    v10 = 0;
    v11 = 0;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
    v12 = *(_QWORD **)(a1 + 144);
    while ( v12 != (_QWORD *)(a1 + 144) )
    {
      v11 = v12 - 2;
      v12 = (_QWORD *)*v12;
      if ( v11[6] == a3 )
      {
        if ( *(_DWORD *)v11 == 1145324615 )
        {
          _InterlockedIncrement64(v11 + 1);
          v10 = 1;
        }
        break;
      }
    }
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 104));
    if ( !v10 )
      v11 = 0;
    if ( v11 )
    {
      if ( a4 )
      {
        v14 = 64;
        v15 = a4;
        while ( *v15 )
        {
          ++v15;
          if ( !--v14 )
          {
            v16 = -2146893785;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v13,
                (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
                (unsigned int)"Status",
                39,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
                108);
            goto LABEL_17;
          }
        }
        if ( a6 > 0x7FFFFFFF )
        {
          v20 = 3443;
          goto LABEL_26;
        }
        v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _WORD *, __int64, unsigned int, int))(v11[4] + 96LL))(
                *(_QWORD *)(v11[4] + 296LL),
                v11[5],
                a4,
                a5,
                a6,
                a7);
        v16 = v19;
        if ( v19 )
        {
          DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 3461);
          v16 = NormalizeNteStatus((unsigned int)v16);
        }
      }
      else
      {
        v20 = 3429;
LABEL_26:
        v16 = -2146893785;
        DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v20);
      }
LABEL_17:
      v17 = SrvDereferenceKey(v11);
      if ( v17 < 0 && v16 >= 0 )
        return (unsigned int)v17;
      return (unsigned int)v16;
    }
    else
    {
      DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 3422);
      return 2148073510LL;
    }
  }
  else
  {
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 3413);
    return 2148073510LL;
  }
}

```

## disassembly

```asm
0x180003d40  push    rbx
0x180003d42  push    rdi
0x180003d43  push    r15
0x180003d45  sub     rsp, 40h
0x180003d49  mov     r15, r9
0x180003d4c  mov     rbx, r8
0x180003d4f  mov     rdi, rcx
0x180003d52  test    rcx, rcx
0x180003d55  jz      loc_180003EAA
0x180003d5b  mov     [rsp+58h+arg_0], rbp
0x180003d60  add     rcx, 68h ; 'h'; CriticalSection
0x180003d64  mov     [rsp+58h+arg_8], rsi
0x180003d69  xor     esi, esi
0x180003d6b  mov     [rsp+58h+arg_10], r14
0x180003d70  xor     r14d, r14d
0x180003d73  call    cs:__imp_RtlEnterCriticalSection
0x180003d79  lea     rdx, [rdi+90h]
0x180003d80  mov     rax, [rdx]
0x180003d83  cmp     rax, rdx
0x180003d86  jz      short loc_180003DA8
0x180003d88  lea     r14, [rax-10h]
0x180003d8c  mov     rax, [rax]
0x180003d8f  cmp     [r14+30h], rbx
0x180003d93  jnz     short loc_180003D83
0x180003d95  cmp     dword ptr [r14], 44444447h
0x180003d9c  jnz     short loc_180003DA8
0x180003d9e  lock inc qword ptr [r14+8]
0x180003da3  mov     esi, 1
0x180003da8  lea     rcx, [rdi+68h]; CriticalSection
0x180003dac  call    cs:__imp_RtlLeaveCriticalSection
0x180003db2  mov     rbp, [rsp+58h+arg_0]
0x180003db7  xor     eax, eax
0x180003db9  test    esi, esi
0x180003dbb  mov     rsi, [rsp+58h+arg_8]
0x180003dc0  cmovz   r14, rax
0x180003dc4  test    r14, r14
0x180003dc7  jz      loc_180003ECF
0x180003dcd  test    r15, r15
0x180003dd0  jz      loc_180003EF7
0x180003dd6  mov     ecx, 40h ; '@'
0x180003ddb  mov     rax, r15
0x180003dde  xchg    ax, ax
0x180003de0  cmp     word ptr [rax], 0
0x180003de4  jz      short loc_180003E5A
0x180003de6  add     rax, 2
0x180003dea  sub     rcx, 1
0x180003dee  jnz     short loc_180003DE0
0x180003df0  mov     ebx, 80090027h
0x180003df5  mov     rcx, cs:WPP_GLOBAL_Control
0x180003dfc  lea     rax, WPP_GLOBAL_Control
0x180003e03  cmp     rcx, rax
0x180003e06  jz      short loc_180003E3A
0x180003e08  test    byte ptr [rcx+1Ch], 1
0x180003e0c  jz      short loc_180003E3A
0x180003e0e  mov     rcx, [rcx+10h]
0x180003e12  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003e19  mov     [rsp+58h+var_28], 0D6Ch
0x180003e21  lea     r9, aStatus; "Status"
0x180003e28  mov     [rsp+58h+var_30], r8
0x180003e2d  mov     [rsp+58h+var_38], 80090027h
0x180003e35  call    WPP_SF_sDsd
0x180003e3a  mov     rcx, r14
0x180003e3d  call    SrvDereferenceKey
0x180003e42  test    eax, eax
0x180003e44  js      loc_180003F50
0x180003e4a  mov     eax, ebx
0x180003e4c  mov     r14, [rsp+58h+arg_10]
0x180003e51  add     rsp, 40h
0x180003e55  pop     r15
0x180003e57  pop     rdi
0x180003e58  pop     rbx
0x180003e59  retn
0x180003e5a  mov     r8d, [rsp+58h+arg_28]
0x180003e62  cmp     r8d, 7FFFFFFFh
0x180003e69  ja      loc_180003EFF
0x180003e6f  mov     rcx, [r14+20h]
0x180003e73  mov     edx, [rsp+58h+arg_30]
0x180003e7a  mov     r9, [rsp+58h+arg_20]
0x180003e82  mov     dword ptr [rsp+58h+var_30], edx
0x180003e86  mov     rax, [rcx+60h]
0x180003e8a  mov     rcx, [rcx+128h]
0x180003e91  mov     rdx, [r14+28h]
0x180003e95  mov     [rsp+58h+var_38], r8d
0x180003e9a  mov     r8, r15
0x180003e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ea2  mov     ebx, eax
0x180003ea4  test    eax, eax
0x180003ea6  jnz     short loc_180003F27
0x180003ea8  jmp     short loc_180003E3A
0x180003eaa  mov     r9d, 0D55h
0x180003eb0  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003eb7  lea     rdx, aStatus; "Status"
0x180003ebe  mov     ecx, 80090026h
0x180003ec3  call    DebugTraceError
0x180003ec8  mov     eax, 80090026h
0x180003ecd  jmp     short loc_180003E51
0x180003ecf  mov     r9d, 0D5Eh
0x180003ed5  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003edc  lea     rdx, aStatus; "Status"
0x180003ee3  mov     ecx, 80090026h
0x180003ee8  call    DebugTraceError
0x180003eed  mov     eax, 80090026h
0x180003ef2  jmp     loc_180003E4C
0x180003ef7  mov     r9d, 0D65h
0x180003efd  jmp     short loc_180003F05
0x180003eff  mov     r9d, 0D73h
0x180003f05  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003f0c  mov     ecx, 80090027h
0x180003f11  lea     rdx, aStatus; "Status"
0x180003f18  mov     ebx, 80090027h
0x180003f1d  call    DebugTraceError
0x180003f22  jmp     loc_180003E3A
0x180003f27  mov     r9d, 0D85h
0x180003f2d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003f34  lea     rdx, aStatus; "Status"
0x180003f3b  mov     ecx, ebx
0x180003f3d  call    DebugTraceError
0x180003f42  mov     ecx, ebx
0x180003f44  call    NormalizeNteStatus
0x180003f49  mov     ebx, eax
0x180003f4b  jmp     loc_180003E3A
0x180003f50  test    ebx, ebx
0x180003f52  cmovns  ebx, eax
0x180003f55  jmp     loc_180003E4A
```
